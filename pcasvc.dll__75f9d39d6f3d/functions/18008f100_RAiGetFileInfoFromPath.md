# RAiGetFileInfoFromPath

- ea: `0x18008f100`
- end: `0x18008f2a0`
- name: `RAiGetFileInfoFromPath`
- size: `416`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, RPC_BINDING_HANDLE BindingHandle, LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callees

- `0x180005180`
- `0x18000dc08`
- `0x180012920`
- `0x18008f100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f1a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f1a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f288`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f288`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008f197`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008f197`
- `RPCRT4!RpcImpersonateClient` at `0x18008f134`
- `RPCRT4!RpcImpersonateClient` at `0x18008f134`
- `RPCRT4!RpcRevertToSelfEx` at `0x18008f279`
- `RPCRT4!RpcRevertToSelfEx` at `0x18008f279`

## string_xrefs

- `0x18008f1ac`: `Failed to open the file %S [%d]`
- `0x18008f151`: `RAiGetFileInfoFromPath`
- `0x18008f1bf`: `RAiGetFileInfoFromPath`
- `0x18008f25e`: `RAiGetFileInfoFromPath`
- `0x18008f140`: `Failed to impersonate RPC client [%d]`

## pseudocode

```c
__int64 __fastcall RAiGetFileInfoFromPath(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        RPC_BINDING_HANDLE BindingHandle,
        LPCWSTR lpFileName)
{
  RPC_STATUS v12; // eax
  unsigned int ProgramInfo; // ebx
  HANDLE FileW; // rsi
  DWORD LastError; // eax
  const char *v16; // r9
  int v17; // r8d
  unsigned int v19; // [rsp+40h] [rbp-48h] BYREF
  int v20[17]; // [rsp+44h] [rbp-44h] BYREF

  v19 = 0;
  v20[0] = 0;
  v12 = RpcImpersonateClient(BindingHandle);
  ProgramInfo = v12;
  if ( v12 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"RAiGetFileInfoFromPath",
      716,
      (unsigned int)"Failed to impersonate RPC client [%d]",
      v12);
    return ProgramInfo;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v16 = "Failed to open the file %S [%d]";
    v17 = 730;
    ProgramInfo = LastError;
LABEL_5:
    AslLogCallPrintf(1, (unsigned int)"RAiGetFileInfoFromPath", v17, (_DWORD)v16, (char)lpFileName);
    goto LABEL_11;
  }
  ProgramInfo = PcaUtilityGetProgramInfo(a1, a2, a3, a4, a5, &v19, v20, lpFileName);
  if ( ProgramInfo )
  {
    v16 = "Failed to get info about file %S [%d]";
    v17 = 747;
    goto LABEL_5;
  }
  if ( StringCchPrintfW(a6, 0x104u, L"%d", v19) >= 0 )
  {
    ProgramInfo = 0;
  }
  else
  {
    ProgramInfo = 122;
    AslLogCallPrintf(
      1,
      (unsigned int)"RAiGetFileInfoFromPath",
      753,
      (unsigned int)"Failed to format the language code for the file [%d]",
      122);
  }
LABEL_11:
  RpcRevertToSelfEx(BindingHandle);
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return ProgramInfo;
}

```

## disassembly

```asm
0x18008f100  push    rbx
0x18008f102  push    rbp
0x18008f103  push    rsi
0x18008f104  push    r12
0x18008f106  push    r13
0x18008f108  push    r14
0x18008f10a  push    r15
0x18008f10c  sub     rsp, 50h
0x18008f110  mov     r13, rcx
0x18008f113  mov     [rsp+88h+var_48], 0
0x18008f11b  mov     rcx, [rsp+88h+BindingHandle]; BindingHandle
0x18008f123  mov     r14, r9
0x18008f126  mov     r15, r8
0x18008f129  mov     [rsp+88h+var_44], 0
0x18008f131  mov     r12, rdx
0x18008f134  call    cs:__imp_RpcImpersonateClient
0x18008f13a  mov     ebx, eax
0x18008f13c  test    eax, eax
0x18008f13e  jz      short loc_18008F167
0x18008f140  lea     r9, aFailedToImpers; "Failed to impersonate RPC client [%d]"
0x18008f147  mov     [rsp+88h+dwCreationDisposition], eax
0x18008f14b  mov     r8d, 2CCh
0x18008f151  lea     rdx, aRaigetfileinfo; "RAiGetFileInfoFromPath"
0x18008f158  mov     ecx, 1
0x18008f15d  call    AslLogCallPrintf
0x18008f162  jmp     loc_18008F28E
0x18008f167  mov     rbp, [rsp+88h+lpFileName]
0x18008f16f  xor     r9d, r9d; lpSecurityAttributes
0x18008f172  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18008f17b  mov     edx, 80000000h; dwDesiredAccess
0x18008f180  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008f188  mov     rcx, rbp; lpFileName
0x18008f18b  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18008f193  lea     r8d, [r9+1]; dwShareMode
0x18008f197  call    cs:__imp_CreateFileW
0x18008f19d  mov     rsi, rax
0x18008f1a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008f1a4  jnz     short loc_18008F1DA
0x18008f1a6  call    cs:__imp_GetLastError
0x18008f1ac  lea     r9, aFailedToOpenTh_0; "Failed to open the file %S [%d]"
0x18008f1b3  mov     r8d, 2DAh
0x18008f1b9  mov     ebx, eax
0x18008f1bb  mov     [rsp+88h+dwFlagsAndAttributes], eax
0x18008f1bf  lea     rdx, aRaigetfileinfo; "RAiGetFileInfoFromPath"
0x18008f1c6  mov     ecx, 1
0x18008f1cb  mov     qword ptr [rsp+88h+dwCreationDisposition], rbp
0x18008f1d0  call    AslLogCallPrintf
0x18008f1d5  jmp     loc_18008F271
0x18008f1da  mov     [rsp+88h+var_50], rbp; unsigned __int16 *
0x18008f1df  lea     rax, [rsp+88h+var_44]
0x18008f1e4  mov     [rsp+88h+hTemplateFile], rax; int *
0x18008f1e9  mov     r9, r14; unsigned __int16 *
0x18008f1ec  lea     rax, [rsp+88h+var_48]
0x18008f1f1  mov     r8, r15; unsigned __int16 *
0x18008f1f4  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax; unsigned int *
0x18008f1f9  mov     rdx, r12; unsigned __int16 *
0x18008f1fc  mov     rax, [rsp+88h+arg_20]
0x18008f204  mov     rcx, r13; unsigned __int16 *
0x18008f207  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; unsigned __int16 *
0x18008f20c  call    ?PcaUtilityGetProgramInfo@@YAKPEAG0000PEAIPEAHPEBG@Z; PcaUtilityGetProgramInfo(ushort *,ushort *,ushort *,ushort *,ushort *,uint *,int *,ushort const *)
0x18008f211  mov     ebx, eax
0x18008f213  test    eax, eax
0x18008f215  jz      short loc_18008F226
0x18008f217  lea     r9, aFailedToGetInf; "Failed to get info about file %S [%d]"
0x18008f21e  mov     r8d, 2EBh
0x18008f224  jmp     short loc_18008F1BB
0x18008f226  mov     r9d, [rsp+88h+var_48]
0x18008f22b  lea     r8, aD; "%d"
0x18008f232  mov     rcx, [rsp+88h+arg_28]; unsigned __int16 *
0x18008f23a  mov     edx, 104h; unsigned __int64
0x18008f23f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008f244  test    eax, eax
0x18008f246  jns     short loc_18008F26F
0x18008f248  mov     ebx, 7Ah ; 'z'
0x18008f24d  lea     r9, aFailedToFormat_5; "Failed to format the language code for "...
0x18008f254  mov     r8d, 2F1h
0x18008f25a  mov     [rsp+88h+dwCreationDisposition], ebx
0x18008f25e  lea     rdx, aRaigetfileinfo; "RAiGetFileInfoFromPath"
0x18008f265  lea     ecx, [rbx-79h]
0x18008f268  call    AslLogCallPrintf
0x18008f26d  jmp     short loc_18008F271
0x18008f26f  xor     ebx, ebx
0x18008f271  mov     rcx, [rsp+88h+BindingHandle]; BindingHandle
0x18008f279  call    cs:__imp_RpcRevertToSelfEx
0x18008f27f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18008f283  jz      short loc_18008F28E
0x18008f285  mov     rcx, rsi; hObject
0x18008f288  call    cs:__imp_CloseHandle
0x18008f28e  mov     eax, ebx
0x18008f290  add     rsp, 50h
0x18008f294  pop     r15
0x18008f296  pop     r14
0x18008f298  pop     r13
0x18008f29a  pop     r12
0x18008f29c  pop     rsi
0x18008f29d  pop     rbp
0x18008f29e  pop     rbx
0x18008f29f  retn
```
