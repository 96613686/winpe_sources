# NetpDeleteGMSASecrets(int,ushort const *,ushort const *)

- ea: `0x180029c60`
- end: `0x180029dc4`
- name: `?NetpDeleteGMSASecrets@@YAJHPEBG0@Z`
- size: `356`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x180007278`
- `0x180029c60`
- `0x18002a3b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029d00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029d00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d8d`
- `LSASRV!LsarClose` at `0x180029da0`
- `LSASRV!LsarClose` at `0x180029da0`
- `LSASRV!LsarDeleteObject` at `0x180029d48`
- `LSASRV!LsarDeleteObject` at `0x180029d48`
- `LSASRV!LsarOpenSecret` at `0x180029d23`
- `LSASRV!LsarOpenSecret` at `0x180029d23`
- `ntdll!RtlAcquireResourceExclusive` at `0x180029cfa`
- `ntdll!RtlAcquireResourceExclusive` at `0x180029cfa`
- `ntdll!RtlInitUnicodeString` at `0x180029ce1`
- `ntdll!RtlInitUnicodeString` at `0x180029ce1`
- `ntdll!RtlReleaseResource` at `0x180029d74`
- `ntdll!RtlReleaseResource` at `0x180029d74`

## string_xrefs

- `0x180029d2f`: `LsarOpenSecret failed 0x%08X\n`
- `0x180029c84`: `Entering NetpDeleteGMSASecrets\n`
- `0x180029d54`: `LsarDeleteObject failed 0x%08X\n`
- `0x180029da9`: `Exiting NetpDeleteGMSASecrets with Status 0x%08X\n`

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
      dword_1800F0D10 = GetCurrentThreadId();
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
      dword_1800F0D10 = -1;
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
0x180029c60  mov     rax, rsp
0x180029c63  push    rbx
0x180029c64  push    rbp
0x180029c65  push    rdi
0x180029c66  push    r15
0x180029c68  sub     rsp, 48h
0x180029c6c  mov     rdi, rdx
0x180029c6f  mov     qword ptr [rax-48h], 0
0x180029c77  mov     ebp, ecx
0x180029c79  mov     qword ptr [rax+20h], 0
0x180029c81  xorps   xmm0, xmm0
0x180029c84  lea     rdx, aEnteringNetpde; "Entering NetpDeleteGMSASecrets\n"
0x180029c8b  mov     r15d, 40h ; '@'
0x180029c91  mov     rbx, r8
0x180029c94  mov     ecx, r15d; unsigned int
0x180029c97  movups  xmmword ptr [rax-40h], xmm0
0x180029c9b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180029ca0  lea     r9, [rsp+68h+SourceString]; unsigned __int16 **
0x180029ca8  mov     r8, rbx; unsigned __int16 *
0x180029cab  mov     rdx, rdi; unsigned __int16 *
0x180029cae  mov     ecx, ebp; int
0x180029cb0  call    ?NetpGetSecretName@@YAJHPEBG0PEAPEAG@Z; NetpGetSecretName(int,ushort const *,ushort const *,ushort * *)
0x180029cb5  mov     ebx, eax
0x180029cb7  test    eax, eax
0x180029cb9  jns     short loc_180029CD2
0x180029cbb  mov     r8d, eax
0x180029cbe  lea     rdx, aNetpgetsecretn; "NetpGetSecretName failed 0x%08X\n"
0x180029cc5  mov     ecx, r15d; unsigned int
0x180029cc8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180029ccd  jmp     loc_180029D7A
0x180029cd2  mov     rdx, [rsp+68h+SourceString]; SourceString
0x180029cda  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180029cdf  xor     edi, edi
0x180029ce1  call    cs:__imp_RtlInitUnicodeString
0x180029ce7  test    ebp, ebp
0x180029ce9  jz      short loc_180029D0C
0x180029ceb  mov     edi, 1
0x180029cf0  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x180029cf7  mov     dl, dil; Wait
0x180029cfa  call    cs:__imp_RtlAcquireResourceExclusive
0x180029d00  call    cs:__imp_GetCurrentThreadId
0x180029d06  mov     cs:dword_1800F0D10, eax
0x180029d0c  mov     rcx, cs:?NlGlobalLsaPolicyHandle@@3PEAXEA; void * NlGlobalLsaPolicyHandle
0x180029d13  lea     r9, [rsp+68h+var_48]
0x180029d18  mov     r8d, 0F0003h
0x180029d1e  lea     rdx, [rsp+68h+DestinationString]
0x180029d23  call    cs:__imp_LsarOpenSecret
0x180029d29  mov     ebx, eax
0x180029d2b  test    eax, eax
0x180029d2d  jns     short loc_180029D43
0x180029d2f  lea     rdx, aLsaropensecret; "LsarOpenSecret failed 0x%08X\n"
0x180029d36  mov     r8d, eax
0x180029d39  mov     ecx, r15d; unsigned int
0x180029d3c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180029d41  jmp     short loc_180029D5F
0x180029d43  lea     rcx, [rsp+68h+var_48]
0x180029d48  call    cs:__imp_LsarDeleteObject
0x180029d4e  mov     ebx, eax
0x180029d50  test    eax, eax
0x180029d52  jns     short loc_180029D5D
0x180029d54  lea     rdx, aLsardeleteobje; "LsarDeleteObject failed 0x%08X\n"
0x180029d5b  jmp     short loc_180029D36
0x180029d5d  xor     ebx, ebx
0x180029d5f  test    edi, edi
0x180029d61  jz      short loc_180029D7A
0x180029d63  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x180029d6a  mov     cs:dword_1800F0D10, 0FFFFFFFFh
0x180029d74  call    cs:__imp_RtlReleaseResource
0x180029d7a  cmp     [rsp+68h+SourceString], 0
0x180029d83  jz      short loc_180029D93
0x180029d85  mov     rcx, [rsp+68h+SourceString]; hMem
0x180029d8d  call    cs:__imp_LocalFree
0x180029d93  cmp     [rsp+68h+var_48], 0
0x180029d99  jz      short loc_180029DA6
0x180029d9b  lea     rcx, [rsp+68h+var_48]
0x180029da0  call    cs:__imp_LsarClose
0x180029da6  mov     r8d, ebx
0x180029da9  lea     rdx, aExitingNetpdel; "Exiting NetpDeleteGMSASecrets with Stat"...
0x180029db0  mov     ecx, r15d; unsigned int
0x180029db3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180029db8  mov     eax, ebx
0x180029dba  add     rsp, 48h
0x180029dbe  pop     r15
0x180029dc0  pop     rdi
0x180029dc1  pop     rbp
0x180029dc2  pop     rbx
0x180029dc3  retn
```
