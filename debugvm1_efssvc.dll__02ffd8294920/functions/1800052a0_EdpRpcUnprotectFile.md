# EdpRpcUnprotectFile

- ea: `0x1800052a0`
- end: `0x18000549c`
- name: `EdpRpcUnprotectFile`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x1800052a0`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005452`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005452`
- `RPCRT4!RpcRevertToSelf` at `0x18000537d`
- `RPCRT4!RpcRevertToSelf` at `0x18000537d`
- `RPCRT4!RpcImpersonateClient` at `0x1800053d5`
- `RPCRT4!RpcImpersonateClient` at `0x1800053f0`
- `RPCRT4!RpcImpersonateClient` at `0x1800053d5`
- `RPCRT4!RpcImpersonateClient` at `0x1800053f0`
- `ntdll!RtlFreeHeap` at `0x180005472`
- `ntdll!RtlFreeHeap` at `0x180005472`
- `ntdll!RtlInitUnicodeString` at `0x18000535b`
- `ntdll!RtlInitUnicodeString` at `0x18000535b`
- `ntdll!RtlNtStatusToDosError` at `0x1800053a7`
- `ntdll!RtlNtStatusToDosError` at `0x1800053a7`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x1800053e8`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x1800053e8`
- `EFSCORE!EfsDllDecryptFileSrv` at `0x18000540a`
- `EFSCORE!EfsDllDecryptFileSrv` at `0x18000540a`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005339`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005339`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x180005369`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x180005369`
- `EFSCORE!EfsDllFreeHeap` at `0x180005481`
- `EFSCORE!EfsDllFreeHeap` at `0x180005481`
- `EFSCORE!EfsDllGetLogFile` at `0x180005399`
- `EFSCORE!EfsDllGetLogFile` at `0x180005399`

## pseudocode

```c
__int64 __fastcall EdpRpcUnprotectFile(__int64 a1, __int64 a2, int a3)
{
  signed int v5; // ebx
  int v6; // eax
  int v7; // ecx
  RPC_STATUS LocalFileName; // eax
  int v9; // ecx
  RPC_STATUS v10; // r8d
  NTSTATUS LogFile; // eax
  NTSTATUS v12; // edi
  int v13; // ecx
  int v14; // eax
  char v16; // [rsp+20h] [rbp-69h]
  PCWSTR SourceString; // [rsp+30h] [rbp-59h] BYREF
  PVOID P[2]; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v20[128]; // [rsp+60h] [rbp-29h] BYREF
  __int16 v21; // [rsp+F8h] [rbp+6Fh] BYREF
  HANDLE hObject; // [rsp+108h] [rbp+7Fh] BYREF

  memset_0(v20, 0, 0x70u);
  hObject = 0;
  v21 = 0;
  SourceString = 0;
  DestinationString = 0;
  *(_OWORD *)P = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    goto LABEL_27;
  }
  v6 = EdpBeginLocalOnlyRpcCall(v20);
  v5 = v6;
  if ( v6 < 0 )
  {
    fnEfsLogTrace1(v7, (unsigned int)EFS_API_ERROR, v6, 6, 74);
    goto LABEL_25;
  }
  LocalFileName = EfsDllGetLocalFileName(a2, 1, &SourceString, &v21);
  if ( LocalFileName )
  {
    v16 = 82;
LABEL_7:
    v10 = LocalFileName;
LABEL_23:
    fnEfsLogTrace1(v9, (unsigned int)EFS_API_ERROR, v10, 6, v16);
    goto LABEL_24;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  LocalFileName = EfsDllGetVolumeRoot(&DestinationString, P);
  if ( LocalFileName )
  {
    v16 = 94;
    goto LABEL_7;
  }
  LocalFileName = RpcRevertToSelf();
  if ( LocalFileName )
  {
    v16 = 100;
    goto LABEL_7;
  }
  LogFile = EfsDllGetLogFile(P, &hObject);
  v12 = LogFile;
  if ( LogFile >= 0 )
  {
    if ( !RpcImpersonateClient(0) )
    {
      v14 = EfsDllDecryptFileSrv(v20, &DestinationString, hObject, a3 | 1u);
      v5 = v14;
      if ( v14 > 0 )
        v5 = (unsigned __int16)v14 | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_24;
      v16 = -120;
      v10 = v5;
      goto LABEL_23;
    }
    if ( hObject )
      EfsDllMarkFileForDelete();
  }
  else if ( RtlNtStatusToDosError(LogFile) == 317 )
  {
    fnEfsLogTrace1(v13, (unsigned int)EFS_API_ERROR, v12, 6, 111);
  }
  RpcImpersonateClient(0);
LABEL_24:
  EdpCleanupLocalOnlyRpcCall(v20);
LABEL_25:
  if ( hObject )
    CloseHandle(hObject);
LABEL_27:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  if ( SourceString )
    EfsDllFreeHeap();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800052a0  mov     [rsp-8+arg_0], rbx
0x1800052a5  push    rbp
0x1800052a6  push    rsi
0x1800052a7  push    rdi
0x1800052a8  lea     rbp, [rsp-47h]
0x1800052ad  sub     rsp, 0D0h
0x1800052b4  mov     rdi, rdx
0x1800052b7  lea     rcx, [rbp+57h+var_80]; void *
0x1800052bb  xor     edx, edx; Val
0x1800052bd  mov     esi, r8d
0x1800052c0  lea     r8d, [rdx+70h]; Size
0x1800052c4  call    memset_0
0x1800052c9  xor     eax, eax
0x1800052cb  mov     [rbp+57h+hObject], 0
0x1800052d3  mov     [rbp+57h+arg_8], ax
0x1800052d7  xorps   xmm0, xmm0
0x1800052da  mov     [rbp+57h+SourceString], rax
0x1800052de  xorps   xmm1, xmm1
0x1800052e1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800052e5  movups  xmmword ptr [rbp+57h+P], xmm1
0x1800052e9  test    rdi, rdi
0x1800052ec  jnz     short loc_1800052F8
0x1800052ee  mov     ebx, 80070057h
0x1800052f3  jmp     loc_180005458
0x1800052f8  lea     rcx, [rbp+57h+var_80]
0x1800052fc  call    EdpBeginLocalOnlyRpcCall
0x180005301  mov     ebx, eax
0x180005303  test    eax, eax
0x180005305  jns     short loc_180005329
0x180005307  mov     r9d, 6
0x18000530d  mov     dword ptr [rsp+0E0h+var_C0], 114Ah
0x180005315  mov     r8d, eax
0x180005318  lea     rdx, EFS_API_ERROR
0x18000531f  call    fnEfsLogTrace1
0x180005324  jmp     loc_180005449
0x180005329  lea     r9, [rbp+57h+arg_8]
0x18000532d  mov     edx, 1
0x180005332  lea     r8, [rbp+57h+SourceString]
0x180005336  mov     rcx, rdi
0x180005339  call    cs:__imp_EfsDllGetLocalFileName
0x18000533f  test    eax, eax
0x180005341  jz      short loc_180005353
0x180005343  mov     dword ptr [rsp+0E0h+var_C0], 1152h
0x18000534b  mov     r8d, eax
0x18000534e  jmp     loc_18000542E
0x180005353  mov     rdx, [rbp+57h+SourceString]; SourceString
0x180005357  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000535b  call    cs:__imp_RtlInitUnicodeString
0x180005361  lea     rdx, [rbp+57h+P]
0x180005365  lea     rcx, [rbp+57h+DestinationString]
0x180005369  call    cs:__imp_EfsDllGetVolumeRoot
0x18000536f  test    eax, eax
0x180005371  jz      short loc_18000537D
0x180005373  mov     dword ptr [rsp+0E0h+var_C0], 115Eh
0x18000537b  jmp     short loc_18000534B
0x18000537d  call    cs:__imp_RpcRevertToSelf
0x180005383  test    eax, eax
0x180005385  jz      short loc_180005391
0x180005387  mov     dword ptr [rsp+0E0h+var_C0], 1164h
0x18000538f  jmp     short loc_18000534B
0x180005391  lea     rdx, [rbp+57h+hObject]
0x180005395  lea     rcx, [rbp+57h+P]
0x180005399  call    cs:__imp_EfsDllGetLogFile
0x18000539f  mov     edi, eax
0x1800053a1  test    eax, eax
0x1800053a3  jns     short loc_1800053D3
0x1800053a5  mov     ecx, eax; Status
0x1800053a7  call    cs:__imp_RtlNtStatusToDosError
0x1800053ad  cmp     eax, 13Dh
0x1800053b2  jnz     short loc_1800053EE
0x1800053b4  mov     r9d, 6
0x1800053ba  mov     dword ptr [rsp+0E0h+var_C0], 116Fh
0x1800053c2  mov     r8d, edi
0x1800053c5  lea     rdx, EFS_API_ERROR
0x1800053cc  call    fnEfsLogTrace1
0x1800053d1  jmp     short loc_1800053EE
0x1800053d3  xor     ecx, ecx; BindingHandle
0x1800053d5  call    cs:__imp_RpcImpersonateClient
0x1800053db  test    eax, eax
0x1800053dd  jz      short loc_1800053F8
0x1800053df  mov     rcx, [rbp+57h+hObject]
0x1800053e3  test    rcx, rcx
0x1800053e6  jz      short loc_1800053EE
0x1800053e8  call    cs:__imp_EfsDllMarkFileForDelete
0x1800053ee  xor     ecx, ecx; BindingHandle
0x1800053f0  call    cs:__imp_RpcImpersonateClient
0x1800053f6  jmp     short loc_180005440
0x1800053f8  mov     r8, [rbp+57h+hObject]
0x1800053fc  lea     rdx, [rbp+57h+DestinationString]
0x180005400  or      esi, 1
0x180005403  lea     rcx, [rbp+57h+var_80]
0x180005407  mov     r9d, esi
0x18000540a  call    cs:__imp_EfsDllDecryptFileSrv
0x180005410  mov     ebx, eax
0x180005412  test    eax, eax
0x180005414  jle     short loc_18000541F
0x180005416  movzx   ebx, ax
0x180005419  or      ebx, 80070000h
0x18000541f  test    ebx, ebx
0x180005421  jns     short loc_180005440
0x180005423  mov     dword ptr [rsp+0E0h+var_C0], 1188h
0x18000542b  mov     r8d, ebx
0x18000542e  mov     r9d, 6
0x180005434  lea     rdx, EFS_API_ERROR
0x18000543b  call    fnEfsLogTrace1
0x180005440  lea     rcx, [rbp+57h+var_80]
0x180005444  call    EdpCleanupLocalOnlyRpcCall
0x180005449  mov     rcx, [rbp+57h+hObject]; hObject
0x18000544d  test    rcx, rcx
0x180005450  jz      short loc_180005458
0x180005452  call    cs:__imp_CloseHandle
0x180005458  cmp     [rbp+57h+P+8], 0
0x18000545d  jz      short loc_180005478
0x18000545f  mov     rcx, gs:60h
0x180005468  xor     edx, edx; Flags
0x18000546a  mov     r8, [rbp+57h+P+8]; P
0x18000546e  mov     rcx, [rcx+30h]; HeapHandle
0x180005472  call    cs:__imp_RtlFreeHeap
0x180005478  mov     rcx, [rbp+57h+SourceString]
0x18000547c  test    rcx, rcx
0x18000547f  jz      short loc_180005487
0x180005481  call    cs:__imp_EfsDllFreeHeap
0x180005487  mov     eax, ebx
0x180005489  mov     rbx, [rsp+0E0h+arg_0]
0x180005491  add     rsp, 0D0h
0x180005498  pop     rdi
0x180005499  pop     rsi
0x18000549a  pop     rbp
0x18000549b  retn
```
