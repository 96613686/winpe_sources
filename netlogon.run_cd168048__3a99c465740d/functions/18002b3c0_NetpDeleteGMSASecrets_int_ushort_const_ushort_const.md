# NetpDeleteGMSASecrets(int,ushort const *,ushort const *)

- ea: `0x18002b3c0`
- end: `0x18002b555`
- name: `?NetpDeleteGMSASecrets@@YAJHPEBG0@Z`
- size: `405`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x180007518`
- `0x18002b3c0`
- `0x18002bbe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b46c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b46c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b511`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b511`
- `LSASRV!LsarClose` at `0x18002b52a`
- `LSASRV!LsarClose` at `0x18002b52a`
- `LSASRV!LsarDeleteObject` at `0x18002b4c0`
- `LSASRV!LsarDeleteObject` at `0x18002b4c0`
- `LSASRV!LsarOpenSecret` at `0x18002b495`
- `LSASRV!LsarOpenSecret` at `0x18002b495`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002b460`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002b460`
- `ntdll!RtlInitUnicodeString` at `0x18002b441`
- `ntdll!RtlInitUnicodeString` at `0x18002b441`
- `ntdll!RtlReleaseResource` at `0x18002b4f2`
- `ntdll!RtlReleaseResource` at `0x18002b4f2`

## string_xrefs

- `0x18002b4a7`: `LsarOpenSecret failed 0x%08X\n`
- `0x18002b3e4`: `Entering NetpDeleteGMSASecrets\n`
- `0x18002b4d2`: `LsarDeleteObject failed 0x%08X\n`
- `0x18002b539`: `Exiting NetpDeleteGMSASecrets with Status 0x%08X\n`

## pseudocode

```c
__int64 __fastcall NetpDeleteGMSASecrets(int a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int SecretName; // eax
  unsigned int v7; // ebx
  int v8; // edi
  int v9; // eax
  int v10; // eax
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-40h] BYREF
  PCWSTR SourceString; // [rsp+88h] [rbp+20h] BYREF

  v12 = 0;
  SourceString = 0;
  DestinationString = 0;
  NlPrintRoutine(0x40u, L"Entering NetpDeleteGMSASecrets\n");
  SecretName = NetpGetSecretName(a1, a2, a3, (unsigned __int16 **)&SourceString);
  v7 = SecretName;
  if ( SecretName >= 0 )
  {
    v8 = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    if ( a1 )
    {
      v8 = 1;
      RtlAcquireResourceExclusive(&NlGlobalGMSADPAPILock, 1u);
      dword_1800F7D10 = GetCurrentThreadId();
    }
    v9 = LsarOpenSecret(NlGlobalLsaPolicyHandle, &DestinationString, 983043, &v12);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v10 = LsarDeleteObject(&v12);
      v7 = v10;
      if ( v10 >= 0 )
        v7 = 0;
      else
        NlPrintRoutine(0x40u, L"LsarDeleteObject failed 0x%08X\n", (unsigned int)v10);
    }
    else
    {
      NlPrintRoutine(0x40u, L"LsarOpenSecret failed 0x%08X\n", (unsigned int)v9);
    }
    if ( v8 )
    {
      dword_1800F7D10 = -1;
      RtlReleaseResource(&NlGlobalGMSADPAPILock);
    }
  }
  else
  {
    NlPrintRoutine(0x40u, L"NetpGetSecretName failed 0x%08X\n", (unsigned int)SecretName);
  }
  if ( SourceString )
    LocalFree((HLOCAL)SourceString);
  if ( v12 )
    LsarClose(&v12);
  NlPrintRoutine(0x40u, L"Exiting NetpDeleteGMSASecrets with Status 0x%08X\n", v7);
  return v7;
}

```

## disassembly

```asm
0x18002b3c0  mov     rax, rsp
0x18002b3c3  push    rbx
0x18002b3c4  push    rbp
0x18002b3c5  push    rdi
0x18002b3c6  push    r15
0x18002b3c8  sub     rsp, 48h
0x18002b3cc  mov     rdi, rdx
0x18002b3cf  mov     qword ptr [rax-48h], 0
0x18002b3d7  mov     ebp, ecx
0x18002b3d9  mov     qword ptr [rax+20h], 0
0x18002b3e1  xorps   xmm0, xmm0
0x18002b3e4  lea     rdx, aEnteringNetpde; "Entering NetpDeleteGMSASecrets\n"
0x18002b3eb  mov     r15d, 40h ; '@'
0x18002b3f1  mov     rbx, r8
0x18002b3f4  mov     ecx, r15d; unsigned int
0x18002b3f7  movups  xmmword ptr [rax-40h], xmm0
0x18002b3fb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b400  lea     r9, [rsp+68h+SourceString]; unsigned __int16 **
0x18002b408  mov     r8, rbx; unsigned __int16 *
0x18002b40b  mov     rdx, rdi; unsigned __int16 *
0x18002b40e  mov     ecx, ebp; int
0x18002b410  call    ?NetpGetSecretName@@YAJHPEBG0PEAPEAG@Z; NetpGetSecretName(int,ushort const *,ushort const *,ushort * *)
0x18002b415  mov     ebx, eax
0x18002b417  test    eax, eax
0x18002b419  jns     short loc_18002B432
0x18002b41b  mov     r8d, eax
0x18002b41e  lea     rdx, aNetpgetsecretn; "NetpGetSecretName failed 0x%08X\n"
0x18002b425  mov     ecx, r15d; unsigned int
0x18002b428  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b42d  jmp     loc_18002B4FE
0x18002b432  mov     rdx, [rsp+68h+SourceString]; SourceString
0x18002b43a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18002b43f  xor     edi, edi
0x18002b441  call    cs:__imp_RtlInitUnicodeString
0x18002b448  nop     dword ptr [rax+rax+00h]
0x18002b44d  test    ebp, ebp
0x18002b44f  jz      short loc_18002B47E
0x18002b451  mov     edi, 1
0x18002b456  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x18002b45d  mov     dl, dil; Wait
0x18002b460  call    cs:__imp_RtlAcquireResourceExclusive
0x18002b467  nop     dword ptr [rax+rax+00h]
0x18002b46c  call    cs:__imp_GetCurrentThreadId
0x18002b473  nop     dword ptr [rax+rax+00h]
0x18002b478  mov     cs:dword_1800F7D10, eax
0x18002b47e  mov     rcx, cs:?NlGlobalLsaPolicyHandle@@3PEAXEA; void * NlGlobalLsaPolicyHandle
0x18002b485  lea     r9, [rsp+68h+var_48]
0x18002b48a  mov     r8d, 0F0003h
0x18002b490  lea     rdx, [rsp+68h+DestinationString]
0x18002b495  call    cs:__imp_LsarOpenSecret
0x18002b49c  nop     dword ptr [rax+rax+00h]
0x18002b4a1  mov     ebx, eax
0x18002b4a3  test    eax, eax
0x18002b4a5  jns     short loc_18002B4BB
0x18002b4a7  lea     rdx, aLsaropensecret; "LsarOpenSecret failed 0x%08X\n"
0x18002b4ae  mov     r8d, eax
0x18002b4b1  mov     ecx, r15d; unsigned int
0x18002b4b4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b4b9  jmp     short loc_18002B4DD
0x18002b4bb  lea     rcx, [rsp+68h+var_48]
0x18002b4c0  call    cs:__imp_LsarDeleteObject
0x18002b4c7  nop     dword ptr [rax+rax+00h]
0x18002b4cc  mov     ebx, eax
0x18002b4ce  test    eax, eax
0x18002b4d0  jns     short loc_18002B4DB
0x18002b4d2  lea     rdx, aLsardeleteobje; "LsarDeleteObject failed 0x%08X\n"
0x18002b4d9  jmp     short loc_18002B4AE
0x18002b4db  xor     ebx, ebx
0x18002b4dd  test    edi, edi
0x18002b4df  jz      short loc_18002B4FE
0x18002b4e1  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x18002b4e8  mov     cs:dword_1800F7D10, 0FFFFFFFFh
0x18002b4f2  call    cs:__imp_RtlReleaseResource
0x18002b4f9  nop     dword ptr [rax+rax+00h]
0x18002b4fe  cmp     [rsp+68h+SourceString], 0
0x18002b507  jz      short loc_18002B51D
0x18002b509  mov     rcx, [rsp+68h+SourceString]; hMem
0x18002b511  call    cs:__imp_LocalFree
0x18002b518  nop     dword ptr [rax+rax+00h]
0x18002b51d  cmp     [rsp+68h+var_48], 0
0x18002b523  jz      short loc_18002B536
0x18002b525  lea     rcx, [rsp+68h+var_48]
0x18002b52a  call    cs:__imp_LsarClose
0x18002b531  nop     dword ptr [rax+rax+00h]
0x18002b536  mov     r8d, ebx
0x18002b539  lea     rdx, aExitingNetpdel; "Exiting NetpDeleteGMSASecrets with Stat"...
0x18002b540  mov     ecx, r15d; unsigned int
0x18002b543  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b548  mov     eax, ebx
0x18002b54a  add     rsp, 48h
0x18002b54e  pop     r15
0x18002b550  pop     rdi
0x18002b551  pop     rbp
0x18002b552  pop     rbx
0x18002b553  retn
```
