# EdpRpcUnprotectFile

- ea: `0x180005640`
- end: `0x18000588b`
- name: `EdpRpcUnprotectFile`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180005640`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000582e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000582e`
- `RPCRT4!RpcRevertToSelf` at `0x18000572f`
- `RPCRT4!RpcRevertToSelf` at `0x18000572f`
- `RPCRT4!RpcImpersonateClient` at `0x180005799`
- `RPCRT4!RpcImpersonateClient` at `0x1800057c0`
- `RPCRT4!RpcImpersonateClient` at `0x180005799`
- `RPCRT4!RpcImpersonateClient` at `0x1800057c0`
- `ntdll!RtlFreeHeap` at `0x180005854`
- `ntdll!RtlFreeHeap` at `0x180005854`
- `ntdll!RtlInitUnicodeString` at `0x180005701`
- `ntdll!RtlInitUnicodeString` at `0x180005701`
- `ntdll!RtlNtStatusToDosError` at `0x180005765`
- `ntdll!RtlNtStatusToDosError` at `0x180005765`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x1800057b2`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x1800057b2`
- `EFSCORE!EfsDllDecryptFileSrv` at `0x1800057e0`
- `EFSCORE!EfsDllDecryptFileSrv` at `0x1800057e0`
- `EFSCORE!EfsDllGetLocalFileName` at `0x1800056d9`
- `EFSCORE!EfsDllGetLocalFileName` at `0x1800056d9`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x180005715`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x180005715`
- `EFSCORE!EfsDllFreeHeap` at `0x180005869`
- `EFSCORE!EfsDllFreeHeap` at `0x180005869`
- `EFSCORE!EfsDllGetLogFile` at `0x180005751`
- `EFSCORE!EfsDllGetLogFile` at `0x180005751`

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
0x180005640  mov     [rsp-8+arg_0], rbx
0x180005645  push    rbp
0x180005646  push    rsi
0x180005647  push    rdi
0x180005648  lea     rbp, [rsp-47h]
0x18000564d  sub     rsp, 0D0h
0x180005654  mov     rdi, rdx
0x180005657  lea     rcx, [rbp+57h+var_80]; void *
0x18000565b  xor     edx, edx; Val
0x18000565d  mov     esi, r8d
0x180005660  lea     r8d, [rdx+70h]; Size
0x180005664  call    memset_0
0x180005669  xor     eax, eax
0x18000566b  mov     [rbp+57h+hObject], 0
0x180005673  mov     [rbp+57h+arg_8], ax
0x180005677  xorps   xmm0, xmm0
0x18000567a  mov     [rbp+57h+SourceString], rax
0x18000567e  xorps   xmm1, xmm1
0x180005681  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180005685  movups  xmmword ptr [rbp+57h+P], xmm1
0x180005689  test    rdi, rdi
0x18000568c  jnz     short loc_180005698
0x18000568e  mov     ebx, 80070057h
0x180005693  jmp     loc_18000583A
0x180005698  lea     rcx, [rbp+57h+var_80]
0x18000569c  call    EdpBeginLocalOnlyRpcCall
0x1800056a1  mov     ebx, eax
0x1800056a3  test    eax, eax
0x1800056a5  jns     short loc_1800056C9
0x1800056a7  mov     r9d, 6
0x1800056ad  mov     dword ptr [rsp+0E0h+var_C0], 114Ah
0x1800056b5  mov     r8d, eax
0x1800056b8  lea     rdx, EFS_API_ERROR
0x1800056bf  call    fnEfsLogTrace1
0x1800056c4  jmp     loc_180005825
0x1800056c9  lea     r9, [rbp+57h+arg_8]
0x1800056cd  mov     edx, 1
0x1800056d2  lea     r8, [rbp+57h+SourceString]
0x1800056d6  mov     rcx, rdi
0x1800056d9  call    cs:__imp_EfsDllGetLocalFileName
0x1800056e0  nop     dword ptr [rax+rax+00h]
0x1800056e5  test    eax, eax
0x1800056e7  jz      short loc_1800056F9
0x1800056e9  mov     dword ptr [rsp+0E0h+var_C0], 1152h
0x1800056f1  mov     r8d, eax
0x1800056f4  jmp     loc_18000580A
0x1800056f9  mov     rdx, [rbp+57h+SourceString]; SourceString
0x1800056fd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180005701  call    cs:__imp_RtlInitUnicodeString
0x180005708  nop     dword ptr [rax+rax+00h]
0x18000570d  lea     rdx, [rbp+57h+P]
0x180005711  lea     rcx, [rbp+57h+DestinationString]
0x180005715  call    cs:__imp_EfsDllGetVolumeRoot
0x18000571c  nop     dword ptr [rax+rax+00h]
0x180005721  test    eax, eax
0x180005723  jz      short loc_18000572F
0x180005725  mov     dword ptr [rsp+0E0h+var_C0], 115Eh
0x18000572d  jmp     short loc_1800056F1
0x18000572f  call    cs:__imp_RpcRevertToSelf
0x180005736  nop     dword ptr [rax+rax+00h]
0x18000573b  test    eax, eax
0x18000573d  jz      short loc_180005749
0x18000573f  mov     dword ptr [rsp+0E0h+var_C0], 1164h
0x180005747  jmp     short loc_1800056F1
0x180005749  lea     rdx, [rbp+57h+hObject]
0x18000574d  lea     rcx, [rbp+57h+P]
0x180005751  call    cs:__imp_EfsDllGetLogFile
0x180005758  nop     dword ptr [rax+rax+00h]
0x18000575d  mov     edi, eax
0x18000575f  test    eax, eax
0x180005761  jns     short loc_180005797
0x180005763  mov     ecx, eax; Status
0x180005765  call    cs:__imp_RtlNtStatusToDosError
0x18000576c  nop     dword ptr [rax+rax+00h]
0x180005771  cmp     eax, 13Dh
0x180005776  jnz     short loc_1800057BE
0x180005778  mov     r9d, 6
0x18000577e  mov     dword ptr [rsp+0E0h+var_C0], 116Fh
0x180005786  mov     r8d, edi
0x180005789  lea     rdx, EFS_API_ERROR
0x180005790  call    fnEfsLogTrace1
0x180005795  jmp     short loc_1800057BE
0x180005797  xor     ecx, ecx; BindingHandle
0x180005799  call    cs:__imp_RpcImpersonateClient
0x1800057a0  nop     dword ptr [rax+rax+00h]
0x1800057a5  test    eax, eax
0x1800057a7  jz      short loc_1800057CE
0x1800057a9  mov     rcx, [rbp+57h+hObject]
0x1800057ad  test    rcx, rcx
0x1800057b0  jz      short loc_1800057BE
0x1800057b2  call    cs:__imp_EfsDllMarkFileForDelete
0x1800057b9  nop     dword ptr [rax+rax+00h]
0x1800057be  xor     ecx, ecx; BindingHandle
0x1800057c0  call    cs:__imp_RpcImpersonateClient
0x1800057c7  nop     dword ptr [rax+rax+00h]
0x1800057cc  jmp     short loc_18000581C
0x1800057ce  mov     r8, [rbp+57h+hObject]
0x1800057d2  lea     rdx, [rbp+57h+DestinationString]
0x1800057d6  or      esi, 1
0x1800057d9  lea     rcx, [rbp+57h+var_80]
0x1800057dd  mov     r9d, esi
0x1800057e0  call    cs:__imp_EfsDllDecryptFileSrv
0x1800057e7  nop     dword ptr [rax+rax+00h]
0x1800057ec  mov     ebx, eax
0x1800057ee  test    eax, eax
0x1800057f0  jle     short loc_1800057FB
0x1800057f2  movzx   ebx, ax
0x1800057f5  or      ebx, 80070000h
0x1800057fb  test    ebx, ebx
0x1800057fd  jns     short loc_18000581C
0x1800057ff  mov     dword ptr [rsp+0E0h+var_C0], 1188h
0x180005807  mov     r8d, ebx
0x18000580a  mov     r9d, 6
0x180005810  lea     rdx, EFS_API_ERROR
0x180005817  call    fnEfsLogTrace1
0x18000581c  lea     rcx, [rbp+57h+var_80]
0x180005820  call    EdpCleanupLocalOnlyRpcCall
0x180005825  mov     rcx, [rbp+57h+hObject]; hObject
0x180005829  test    rcx, rcx
0x18000582c  jz      short loc_18000583A
0x18000582e  call    cs:__imp_CloseHandle
0x180005835  nop     dword ptr [rax+rax+00h]
0x18000583a  cmp     [rbp+57h+P+8], 0
0x18000583f  jz      short loc_180005860
0x180005841  mov     rcx, gs:60h
0x18000584a  xor     edx, edx; Flags
0x18000584c  mov     r8, [rbp+57h+P+8]; P
0x180005850  mov     rcx, [rcx+30h]; HeapHandle
0x180005854  call    cs:__imp_RtlFreeHeap
0x18000585b  nop     dword ptr [rax+rax+00h]
0x180005860  mov     rcx, [rbp+57h+SourceString]
0x180005864  test    rcx, rcx
0x180005867  jz      short loc_180005875
0x180005869  call    cs:__imp_EfsDllFreeHeap
0x180005870  nop     dword ptr [rax+rax+00h]
0x180005875  mov     eax, ebx
0x180005877  mov     rbx, [rsp+0E0h+arg_0]
0x18000587f  add     rsp, 0D0h
0x180005886  pop     rdi
0x180005887  pop     rsi
0x180005888  pop     rbp
0x180005889  retn
```
