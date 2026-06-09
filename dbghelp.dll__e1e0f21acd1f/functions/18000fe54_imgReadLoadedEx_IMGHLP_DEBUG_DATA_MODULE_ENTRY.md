# imgReadLoadedEx(_IMGHLP_DEBUG_DATA *,_MODULE_ENTRY *)

- ea: `0x18000fe54`
- end: `0x18000ffcf`
- name: `?imgReadLoadedEx@@YAHPEAU_IMGHLP_DEBUG_DATA@@PEAU_MODULE_ENTRY@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(struct _IMGHLP_DEBUG_DATA *, struct _MODULE_ENTRY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f380`

## callees

- `0x180003c04`
- `0x18000fe54`
- `0x1801aa1c4`
- `0x1801abfbc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ffa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ffa8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000fee4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000fee4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000feb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000feb8`

## string_xrefs

- `0x18000ff51`: `Reading image headers for %s from target ...`
- `0x18000ff79`: `Reading image headers for %s from target completed.`

## pseudocode

```c
BOOL __fastcall imgReadLoadedEx(struct _IMGHLP_DEBUG_DATA *a1, struct _MODULE_ENTRY *a2)
{
  BOOL result; // eax
  __int64 v5; // r14
  HANDLE CurrentProcess; // rbx
  void *v7; // rdi
  HANDLE v8; // rax
  unsigned int v9; // r9d
  int Header; // ebx
  HANDLE TargetHandle; // [rsp+70h] [rbp+18h] BYREF

  if ( (*((_BYTE *)a1 + 4276) & 1) != 0 )
  {
    *((_DWORD *)a1 + 826) = 7;
    return 1;
  }
  v5 = *((_QWORD *)a1 + 138);
  if ( (unsigned __int64)(v5 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_15;
  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v7 = (void *)*((_QWORD *)a1 + 138);
  v8 = GetCurrentProcess();
  result = DuplicateHandle(v8, v7, CurrentProcess, &TargetHandle, 0x80000000, 0, 2u);
  if ( !result )
    return result;
  if ( *((_DWORD *)a1 + 900) )
    GetFileNameFromBase(*((void **)a1 + 449), *((_QWORD *)a1 + 3), (unsigned __int16 *)a1 + 29, v9);
  *((_QWORD *)a1 + 138) = TargetHandle;
  *((_DWORD *)a1 + 827) = 6;
  if ( (unsigned int)ReadHeaderEx(a1, 2u, a2) )
    return 1;
LABEL_15:
  if ( *((_QWORD *)a1 + 3)
    && (LogXmlInfo(L"SymbolLoad", L"Reading image headers for %s from target ...", (char *)a1 + 3604),
        Header = ReadHeaderEx(a1, 1u, a2),
        LogXmlInfo(L"SymbolLoad", L"Reading image headers for %s from target completed.", (char *)a1 + 3604),
        Header) )
  {
    *((_DWORD *)a1 + 827) = 7;
    return 1;
  }
  else
  {
    CloseHandle(*((HANDLE *)a1 + 138));
    *((_QWORD *)a1 + 138) = v5;
    return 0;
  }
}

```

## disassembly

```asm
0x18000fe54  mov     [rsp+arg_0], rbx
0x18000fe59  mov     [rsp+arg_8], rsi
0x18000fe5e  push    rdi
0x18000fe5f  push    r14
0x18000fe61  push    r15
0x18000fe63  sub     rsp, 40h
0x18000fe67  mov     r15, rdx
0x18000fe6a  mov     rsi, rcx
0x18000fe6d  test    byte ptr [rcx+10B4h], 1
0x18000fe74  jz      short loc_18000FE8A
0x18000fe76  mov     dword ptr [rcx+0CE8h], 7
0x18000fe80  mov     eax, 1
0x18000fe85  jmp     loc_18000FFBB
0x18000fe8a  mov     r14, [rcx+450h]
0x18000fe91  lea     rax, [r14-1]
0x18000fe95  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000fe99  ja      loc_18000FF40
0x18000fe9f  mov     [rsp+58h+TargetHandle], 0
0x18000fea8  call    cs:__imp_GetCurrentProcess
0x18000feae  mov     rbx, rax
0x18000feb1  mov     rdi, [rsi+450h]
0x18000feb8  call    cs:__imp_GetCurrentProcess
0x18000febe  mov     [rsp+58h+dwOptions], 2; dwOptions
0x18000fec6  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x18000fece  mov     [rsp+58h+dwDesiredAccess], 80000000h; dwDesiredAccess
0x18000fed6  lea     r9, [rsp+58h+TargetHandle]; lpTargetHandle
0x18000fedb  mov     r8, rbx; hTargetProcessHandle
0x18000fede  mov     rdx, rdi; hSourceHandle
0x18000fee1  mov     rcx, rax; hSourceProcessHandle
0x18000fee4  call    cs:__imp_DuplicateHandle
0x18000feea  test    eax, eax
0x18000feec  jz      loc_18000FFBB
0x18000fef2  cmp     dword ptr [rsi+0E10h], 0
0x18000fef9  jz      short loc_18000FF0F
0x18000fefb  lea     r8, [rsi+3Ah]; unsigned __int16 *
0x18000feff  mov     rdx, [rsi+18h]; unsigned __int64
0x18000ff03  mov     rcx, [rsi+0E08h]; void *
0x18000ff0a  call    ?GetFileNameFromBase@@YAHPEAX_KPEAGK@Z; GetFileNameFromBase(void *,unsigned __int64,ushort *,ulong)
0x18000ff0f  mov     rax, [rsp+58h+TargetHandle]
0x18000ff14  mov     [rsi+450h], rax
0x18000ff1b  mov     dword ptr [rsi+0CECh], 6
0x18000ff25  mov     r8, r15; struct _MODULE_ENTRY *
0x18000ff28  mov     edx, 2; unsigned int
0x18000ff2d  mov     rcx, rsi; struct _IMGHLP_DEBUG_DATA *
0x18000ff30  call    ?ReadHeaderEx@@YAHPEAU_IMGHLP_DEBUG_DATA@@KPEAU_MODULE_ENTRY@@@Z; ReadHeaderEx(_IMGHLP_DEBUG_DATA *,ulong,_MODULE_ENTRY *)
0x18000ff35  test    eax, eax
0x18000ff37  jz      short loc_18000FF40
0x18000ff39  mov     eax, 1
0x18000ff3e  jmp     short loc_18000FFBB
0x18000ff40  cmp     qword ptr [rsi+18h], 0
0x18000ff45  jz      short loc_18000FFA1
0x18000ff47  lea     rdi, [rsi+0E14h]
0x18000ff4e  mov     r8, rdi
0x18000ff51  lea     rdx, aReadingImageHe_0; "Reading image headers for %s from targe"...
0x18000ff58  lea     rcx, aSymbolload; "SymbolLoad"
0x18000ff5f  call    ?LogXmlInfo@@YAXPEBG0ZZ; LogXmlInfo(ushort const *,ushort const *,...)
0x18000ff64  mov     r8, r15; struct _MODULE_ENTRY *
0x18000ff67  mov     edx, 1; unsigned int
0x18000ff6c  mov     rcx, rsi; struct _IMGHLP_DEBUG_DATA *
0x18000ff6f  call    ?ReadHeaderEx@@YAHPEAU_IMGHLP_DEBUG_DATA@@KPEAU_MODULE_ENTRY@@@Z; ReadHeaderEx(_IMGHLP_DEBUG_DATA *,ulong,_MODULE_ENTRY *)
0x18000ff74  mov     ebx, eax
0x18000ff76  mov     r8, rdi
0x18000ff79  lea     rdx, aReadingImageHe; "Reading image headers for %s from targe"...
0x18000ff80  lea     rcx, aSymbolload; "SymbolLoad"
0x18000ff87  call    ?LogXmlInfo@@YAXPEBG0ZZ; LogXmlInfo(ushort const *,ushort const *,...)
0x18000ff8c  test    ebx, ebx
0x18000ff8e  jz      short loc_18000FFA1
0x18000ff90  mov     dword ptr [rsi+0CECh], 7
0x18000ff9a  mov     eax, 1
0x18000ff9f  jmp     short loc_18000FFBB
0x18000ffa1  mov     rcx, [rsi+450h]; hObject
0x18000ffa8  call    cs:__imp_CloseHandle
0x18000ffae  mov     [rsi+450h], r14
0x18000ffb5  xor     eax, eax
0x18000ffb7  jmp     short loc_18000FFBB
0x18000ffb9  xor     eax, eax
0x18000ffbb  mov     rbx, [rsp+58h+arg_0]
0x18000ffc0  mov     rsi, [rsp+58h+arg_8]
0x18000ffc5  add     rsp, 40h
0x18000ffc9  pop     r15
0x18000ffcb  pop     r14
0x18000ffcd  pop     rdi
0x18000ffce  retn
```
