# _anonymous_namespace_::IsWizardUser

- ea: `0x14001f5bc`
- end: `0x14001f721`
- name: `_anonymous_namespace_::IsWizardUser`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14001dccc`

## callees

- `0x140002368`
- `0x14001f4f0`
- `0x14001f5bc`
- `0x1400202b4`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x14001f676`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14001f676`
- `ADVAPI32!GetTokenInformation` at `0x14001f60f`
- `ADVAPI32!GetTokenInformation` at `0x14001f659`
- `ADVAPI32!GetTokenInformation` at `0x14001f60f`
- `ADVAPI32!GetTokenInformation` at `0x14001f659`
- `ADVAPI32!OpenProcessToken` at `0x14001f5e3`
- `ADVAPI32!OpenProcessToken` at `0x14001f5e3`
- `KERNEL32!GetLastError` at `0x14001f61d`
- `KERNEL32!GetLastError` at `0x14001f61d`
- `KERNEL32!CloseHandle` at `0x14001f711`
- `KERNEL32!CloseHandle` at `0x14001f711`
- `KERNEL32!LocalFree` at `0x14001f6fe`
- `KERNEL32!LocalFree` at `0x14001f6fe`
- `KERNEL32!GetCurrentProcess` at `0x14001f5d1`
- `KERNEL32!GetCurrentProcess` at `0x14001f5d1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14001f707`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14001f707`

## pseudocode

```c
bool anonymous_namespace_::IsWizardUser()
{
  bool v0; // bl
  HANDLE CurrentProcess; // rax
  void **v2; // rdi
  void *v3; // rcx
  unsigned int v4; // r9d
  const unsigned __int16 *v5; // rbx
  unsigned int v6; // r9d
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  int v9; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v2 = (void **)operator new[](TokenInformationLength);
      if ( v2 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
        {
          v3 = *v2;
          StringSid = 0;
          if ( ConvertSidToStringSidW(v3, &StringSid) )
          {
            v5 = StringSid;
            v9 = 0;
            SHRegGetBOOLWithREGSAM(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
              L"LaunchUserOOBE",
              v4,
              &v9);
            v0 = 1;
            if ( !v9 )
            {
              v9 = 0;
              SHRegGetBOOLWithREGSAM(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ExperienceManagerData",
                L"LaunchCflScenario",
                v6,
                &v9);
              if ( !v9 && !IsCamCxhOnlyUser(v5) )
                v0 = 0;
            }
            LocalFree(StringSid);
          }
        }
        operator delete[](v2);
      }
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x14001f5bc  push    rbp
0x14001f5be  push    rbx
0x14001f5bf  push    rdi
0x14001f5c0  mov     rbp, rsp
0x14001f5c3  sub     rsp, 30h
0x14001f5c7  xor     bl, bl
0x14001f5c9  mov     [rbp+TokenHandle], 0
0x14001f5d1  call    cs:__imp_GetCurrentProcess
0x14001f5d7  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14001f5db  mov     edx, 8; DesiredAccess
0x14001f5e0  mov     rcx, rax; ProcessHandle
0x14001f5e3  call    cs:__imp_OpenProcessToken
0x14001f5e9  test    eax, eax
0x14001f5eb  jz      loc_14001F717
0x14001f5f1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14001f5f5  lea     rax, [rbp+TokenInformationLength]
0x14001f5f9  xor     r9d, r9d; TokenInformationLength
0x14001f5fc  mov     [rbp+TokenInformationLength], 0
0x14001f603  xor     r8d, r8d; TokenInformation
0x14001f606  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14001f60b  lea     edx, [r9+1]; TokenInformationClass
0x14001f60f  call    cs:__imp_GetTokenInformation
0x14001f615  test    eax, eax
0x14001f617  jnz     loc_14001F70D
0x14001f61d  call    cs:__imp_GetLastError
0x14001f623  cmp     eax, 7Ah ; 'z'
0x14001f626  jnz     loc_14001F70D
0x14001f62c  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x14001f62f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001f634  mov     rdi, rax
0x14001f637  test    rax, rax
0x14001f63a  jz      loc_14001F70D
0x14001f640  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14001f644  lea     rax, [rbp+TokenInformationLength]
0x14001f648  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14001f64c  mov     r8, rdi; TokenInformation
0x14001f64f  mov     edx, 1; TokenInformationClass
0x14001f654  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14001f659  call    cs:__imp_GetTokenInformation
0x14001f65f  test    eax, eax
0x14001f661  jz      loc_14001F704
0x14001f667  mov     rcx, [rdi]; Sid
0x14001f66a  lea     rdx, [rbp+StringSid]; StringSid
0x14001f66e  mov     [rbp+StringSid], 0
0x14001f676  call    cs:__imp_ConvertSidToStringSidW
0x14001f67c  test    eax, eax
0x14001f67e  jz      loc_14001F704
0x14001f684  mov     rbx, [rbp+StringSid]
0x14001f688  lea     rax, [rbp+arg_8]
0x14001f68c  lea     r8, aLaunchuseroobe; "LaunchUserOOBE"
0x14001f693  mov     [rsp+30h+ReturnLength], rax; int *
0x14001f698  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001f69f  mov     [rbp+arg_8], 0
0x14001f6a6  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x14001f6ad  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x14001f6b2  cmp     [rbp+arg_8], 0
0x14001f6b6  jnz     short loc_14001F6F8
0x14001f6b8  lea     rax, [rbp+arg_8]
0x14001f6bc  mov     [rbp+arg_8], 0
0x14001f6c3  lea     r8, aLaunchcflscena; "LaunchCflScenario"
0x14001f6ca  mov     [rsp+30h+ReturnLength], rax; int *
0x14001f6cf  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001f6d6  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x14001f6dd  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x14001f6e2  cmp     [rbp+arg_8], 0
0x14001f6e6  jnz     short loc_14001F6F8
0x14001f6e8  mov     rcx, rbx; unsigned __int16 *
0x14001f6eb  call    ?IsCamCxhOnlyUser@@YA_NPEBG@Z; IsCamCxhOnlyUser(ushort const *)
0x14001f6f0  test    al, al
0x14001f6f2  jnz     short loc_14001F6F8
0x14001f6f4  xor     bl, bl
0x14001f6f6  jmp     short loc_14001F6FA
0x14001f6f8  mov     bl, 1
0x14001f6fa  mov     rcx, [rbp+StringSid]; hMem
0x14001f6fe  call    cs:__imp_LocalFree
0x14001f704  mov     rcx, rdi
0x14001f707  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14001f70d  mov     rcx, [rbp+TokenHandle]; hObject
0x14001f711  call    cs:__imp_CloseHandle
0x14001f717  mov     al, bl
0x14001f719  add     rsp, 30h
0x14001f71d  pop     rdi
0x14001f71e  pop     rbx
0x14001f71f  pop     rbp
0x14001f720  retn
```
