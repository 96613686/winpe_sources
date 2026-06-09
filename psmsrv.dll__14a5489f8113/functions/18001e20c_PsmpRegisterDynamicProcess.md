# PsmpRegisterDynamicProcess

- ea: `0x18001e20c`
- end: `0x18001e4f9`
- name: `PsmpRegisterDynamicProcess`
- size: `749`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002bb70`

## callees

- `0x180001580`
- `0x180003ec8`
- `0x180008cc0`
- `0x180009b40`
- `0x1800180d0`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001e20c`
- `0x18002cfc4`

## import_xrefs

- `ntdll!NtIsProcessInJob` at `0x18001e307`
- `ntdll!NtIsProcessInJob` at `0x18001e32d`
- `ntdll!NtIsProcessInJob` at `0x18001e307`
- `ntdll!NtIsProcessInJob` at `0x18001e32d`
- `ntdll!NtClose` at `0x18001e4ca`
- `ntdll!NtClose` at `0x18001e4ca`
- `ntdll!NtOpenProcessTokenEx` at `0x18001e27e`
- `ntdll!NtOpenProcessTokenEx` at `0x18001e3a3`
- `ntdll!NtOpenProcessTokenEx` at `0x18001e27e`
- `ntdll!NtOpenProcessTokenEx` at `0x18001e3a3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001e26a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001e26a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e4ab`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e4ab`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x18001e362`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x18001e362`
- `api-ms-win-core-psm-key-l1-1-0!PsmIsDynamicKey` at `0x18001e2b2`
- `api-ms-win-core-psm-key-l1-1-0!PsmIsDynamicKey` at `0x18001e2b2`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetApplicationNameFromKey` at `0x18001e38d`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetApplicationNameFromKey` at `0x18001e38d`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18001e433`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18001e433`

## pseudocode

```c
__int64 __fastcall PsmpRegisterDynamicProcess(HANDLE ProcessHandle)
{
  __int64 v2; // rdi
  int ClientApplicationInformation; // ebx
  int ApplicationByManagerForUser; // eax
  void *v5; // rdx
  unsigned __int8 v6; // r14
  int v8; // [rsp+54h] [rbp-ACh] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+58h] [rbp-A8h] BYREF
  void *TokenHandle[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v11[29]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Sid2[72]; // [rsp+248h] [rbp+148h] BYREF
  __int16 v13; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v14[142]; // [rsp+292h] [rbp+192h] BYREF
  WCHAR packageFullName[128]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR packageFamilyName[128]; // [rsp+420h] [rbp+320h] BYREF

  memset_0(v11, 0, 0x220u);
  v2 = 0;
  v8 = 0;
  *(_QWORD *)packageFamilyNameLength = 0;
  TokenHandle[0] = 0;
  RtlAcquireSRWLockExclusive(&PsmpDynamicProcessLock);
  ClientApplicationInformation = NtOpenProcessTokenEx(ProcessHandle, 8u, 0, TokenHandle);
  if ( ClientApplicationInformation >= 0 )
  {
    ClientApplicationInformation = PsmpQueryClientApplicationInformation(ProcessHandle, TokenHandle[0], v11, 0);
    if ( ClientApplicationInformation >= 0 )
    {
      if ( (unsigned __int8)PsmIsDynamicKey((char *)v11 + 8) )
      {
        ClientApplicationInformation = -1073741637;
      }
      else
      {
        ApplicationByManagerForUser = PsmpFindApplicationByManagerForUser(
                                        Sid2,
                                        v11[0],
                                        (__int64)v11 + 8,
                                        DWORD1(v11[0]),
                                        0,
                                        (__int64 *)packageFamilyNameLength);
        v2 = *(_QWORD *)packageFamilyNameLength;
        ClientApplicationInformation = ApplicationByManagerForUser;
        if ( ApplicationByManagerForUser >= 0 )
        {
          ClientApplicationInformation = NtIsProcessInJob(
                                           ProcessHandle,
                                           *(HANDLE *)(*(_QWORD *)packageFamilyNameLength + 184LL));
          if ( ClientApplicationInformation == 291 )
          {
            v5 = *(void **)(v2 + 200);
            if ( !v5
              || (ClientApplicationInformation = NtIsProcessInJob(ProcessHandle, v5), ClientApplicationInformation == 291) )
            {
              v8 = 256;
              v6 = Sid2[69] & 1;
              PsmGetPackageFullNameFromKey((char *)v11 + 8, packageFullName, &v8);
              v8 = 130;
              v13 = 33;
              PsmGetApplicationNameFromKey((char *)v11 + 8, v14, &v8);
              ClientApplicationInformation = NtOpenProcessTokenEx(ProcessHandle, 0x88u, 0, TokenHandle);
              if ( ClientApplicationInformation >= 0 )
              {
                ClientApplicationInformation = PsmpAdjustActivationToken(
                                                 TokenHandle[0],
                                                 (unsigned int)v6 - 0x40000000,
                                                 0,
                                                 packageFullName,
                                                 &v13,
                                                 0,
                                                 0,
                                                 0,
                                                 0,
                                                 0);
                if ( ClientApplicationInformation >= 0 )
                {
                  packageFamilyNameLength[0] = 128;
                  ClientApplicationInformation = PackageFamilyNameFromFullName(
                                                   packageFullName,
                                                   packageFamilyNameLength,
                                                   packageFamilyName);
                  if ( ClientApplicationInformation
                    || (ClientApplicationInformation = HamOptInIsPackageFamilyNameEnabledEx(packageFamilyName)) != 0 )
                  {
                    if ( ClientApplicationInformation > 0 )
                      ClientApplicationInformation = (unsigned __int16)ClientApplicationInformation | 0xC0070000;
                  }
                  else
                  {
                    ClientApplicationInformation = PsmRegisterApplicationProcessEx(ProcessHandle, 0);
                    if ( ClientApplicationInformation >= 0 )
                      ClientApplicationInformation = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  RtlReleaseSRWLockExclusive(&PsmpDynamicProcessLock);
  if ( v2 )
    PsmpDereferenceApplicationEx(v2, 0);
  if ( TokenHandle[0] )
    NtClose(TokenHandle[0]);
  return (unsigned int)ClientApplicationInformation;
}

```

## disassembly

```asm
0x18001e20c  mov     [rsp-8+arg_8], rbx
0x18001e211  mov     [rsp-8+arg_10], rsi
0x18001e216  push    rbp
0x18001e217  push    rdi
0x18001e218  push    r14
0x18001e21a  lea     rbp, [rsp-430h]
0x18001e222  sub     rsp, 530h
0x18001e229  mov     rax, cs:__security_cookie
0x18001e230  xor     rax, rsp
0x18001e233  mov     [rbp+440h+var_20], rax
0x18001e23a  mov     rsi, rcx
0x18001e23d  xor     edx, edx; Val
0x18001e23f  lea     rcx, [rsp+540h+var_4D0]; void *
0x18001e244  mov     r8d, 220h; Size
0x18001e24a  call    memset_0
0x18001e24f  xor     edi, edi
0x18001e251  mov     [rsp+540h+var_4EC], 0
0x18001e259  lea     rcx, PsmpDynamicProcessLock
0x18001e260  mov     qword ptr [rsp+540h+packageFamilyNameLength], rdi
0x18001e265  mov     [rsp+540h+TokenHandle], rdi
0x18001e26a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001e270  lea     r9, [rsp+540h+TokenHandle]; TokenHandle
0x18001e275  xor     r8d, r8d; HandleAttributes
0x18001e278  lea     edx, [rdi+8]; DesiredAccess
0x18001e27b  mov     rcx, rsi; ProcessHandle
0x18001e27e  call    cs:__imp_NtOpenProcessTokenEx
0x18001e284  mov     ebx, eax
0x18001e286  test    eax, eax
0x18001e288  js      loc_18001E4A4
0x18001e28e  mov     rdx, [rsp+540h+TokenHandle]; TokenHandle
0x18001e293  lea     r8, [rsp+540h+var_4D0]
0x18001e298  xor     r9d, r9d
0x18001e29b  mov     rcx, rsi; ProcessHandle
0x18001e29e  call    PsmpQueryClientApplicationInformation
0x18001e2a3  mov     ebx, eax
0x18001e2a5  test    eax, eax
0x18001e2a7  js      loc_18001E4A4
0x18001e2ad  lea     rcx, [rsp+540h+var_4C8]
0x18001e2b2  call    cs:__imp_PsmIsDynamicKey
0x18001e2b8  test    al, al
0x18001e2ba  jz      short loc_18001E2C6
0x18001e2bc  mov     ebx, 0C00000BBh
0x18001e2c1  jmp     loc_18001E4A4
0x18001e2c6  mov     r9d, [rsp+540h+var_4CC]
0x18001e2cb  lea     rax, [rsp+540h+packageFamilyNameLength]
0x18001e2d0  mov     edx, [rsp+540h+var_4D0]
0x18001e2d4  lea     r8, [rsp+540h+var_4C8]
0x18001e2d9  mov     [rsp+540h+var_518], rax; __int64
0x18001e2de  lea     rcx, [rbp+440h+Sid2]; Sid2
0x18001e2e5  mov     dword ptr [rsp+540h+var_520], edi; int
0x18001e2e9  call    PsmpFindApplicationByManagerForUser
0x18001e2ee  mov     rdi, qword ptr [rsp+540h+packageFamilyNameLength]
0x18001e2f3  mov     ebx, eax
0x18001e2f5  test    eax, eax
0x18001e2f7  js      loc_18001E4A4
0x18001e2fd  mov     rdx, [rdi+0B8h]; JobHandle
0x18001e304  mov     rcx, rsi; ProcessHandle
0x18001e307  call    cs:__imp_NtIsProcessInJob
0x18001e30d  mov     r14d, 123h
0x18001e313  mov     ebx, eax
0x18001e315  cmp     eax, r14d
0x18001e318  jnz     loc_18001E4A4
0x18001e31e  mov     rdx, [rdi+0C8h]; JobHandle
0x18001e325  test    rdx, rdx
0x18001e328  jz      short loc_18001E33E
0x18001e32a  mov     rcx, rsi; ProcessHandle
0x18001e32d  call    cs:__imp_NtIsProcessInJob
0x18001e333  mov     ebx, eax
0x18001e335  cmp     eax, r14d
0x18001e338  jnz     loc_18001E4A4
0x18001e33e  mov     r14b, [rbp+440h+var_2B3]
0x18001e345  lea     r8, [rsp+540h+var_4EC]
0x18001e34a  lea     rdx, [rbp+440h+packageFullName]
0x18001e351  mov     [rsp+540h+var_4EC], 100h
0x18001e359  lea     rcx, [rsp+540h+var_4C8]
0x18001e35e  and     r14b, 1
0x18001e362  call    cs:__imp_PsmGetPackageFullNameFromKey
0x18001e368  mov     eax, 21h ; '!'
0x18001e36d  mov     [rsp+540h+var_4EC], 82h
0x18001e375  lea     r8, [rsp+540h+var_4EC]
0x18001e37a  mov     [rbp+440h+var_2B0], ax
0x18001e381  lea     rdx, [rbp+440h+var_2AE]
0x18001e388  lea     rcx, [rsp+540h+var_4C8]
0x18001e38d  call    cs:__imp_PsmGetApplicationNameFromKey
0x18001e393  lea     r9, [rsp+540h+TokenHandle]; TokenHandle
0x18001e398  xor     r8d, r8d; HandleAttributes
0x18001e39b  mov     edx, 88h; DesiredAccess
0x18001e3a0  mov     rcx, rsi; ProcessHandle
0x18001e3a3  call    cs:__imp_NtOpenProcessTokenEx
0x18001e3a9  mov     ebx, eax
0x18001e3ab  test    eax, eax
0x18001e3ad  js      loc_18001E4A4
0x18001e3b3  mov     rcx, [rsp+540h+TokenHandle]
0x18001e3b8  lea     rax, [rbp+440h+var_2B0]
0x18001e3bf  mov     [rsp+540h+var_4F8], 0
0x18001e3c8  lea     r9, [rbp+440h+packageFullName]
0x18001e3cf  mov     [rsp+540h+var_500], 0
0x18001e3d8  xor     r8d, r8d
0x18001e3db  mov     [rsp+540h+var_508], 0
0x18001e3e4  movzx   edx, r14b
0x18001e3e8  mov     [rsp+540h+var_510], 0
0x18001e3f1  sub     edx, 40000000h
0x18001e3f7  mov     dword ptr [rsp+540h+var_518], 0
0x18001e3ff  mov     [rsp+540h+var_520], rax
0x18001e404  call    PsmpAdjustActivationToken
0x18001e409  mov     ebx, eax
0x18001e40b  test    eax, eax
0x18001e40d  js      loc_18001E4A4
0x18001e413  lea     r8, [rbp+440h+packageFamilyName]; packageFamilyName
0x18001e41a  mov     [rsp+540h+var_4F0], 0
0x18001e41f  lea     rdx, [rsp+540h+packageFamilyNameLength]; packageFamilyNameLength
0x18001e424  mov     [rsp+540h+packageFamilyNameLength], 80h
0x18001e42c  lea     rcx, [rbp+440h+packageFullName]; packageFullName
0x18001e433  call    cs:__imp_PackageFamilyNameFromFullName
0x18001e439  mov     ebx, eax
0x18001e43b  test    eax, eax
0x18001e43d  jnz     short loc_18001E497
0x18001e43f  lea     r8, [rsp+540h+var_4F0]
0x18001e444  lea     rcx, [rbp+440h+packageFamilyName]; lpValueName
0x18001e44b  call    HamOptInIsPackageFamilyNameEnabledEx
0x18001e450  mov     ebx, eax
0x18001e452  test    eax, eax
0x18001e454  jnz     short loc_18001E497
0x18001e456  mov     al, [rsp+540h+var_4F0]
0x18001e45a  neg     al
0x18001e45c  mov     [rsp+540h+var_520], 0; __int64
0x18001e465  mov     rcx, rsi; ProcessHandle
0x18001e468  sbb     edx, edx
0x18001e46a  and     edx, 7Fh
0x18001e46d  inc     edx
0x18001e46f  mov     r9d, edx
0x18001e472  or      r9d, 2
0x18001e476  test    byte ptr [rdi+84h], 80h
0x18001e47d  cmovz   r9d, edx
0x18001e481  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e485  xor     edx, edx
0x18001e487  call    PsmRegisterApplicationProcessEx
0x18001e48c  mov     ebx, eax
0x18001e48e  xor     eax, eax
0x18001e490  test    ebx, ebx
0x18001e492  cmovns  ebx, eax
0x18001e495  jmp     short loc_18001E4A4
0x18001e497  test    ebx, ebx
0x18001e499  jle     short loc_18001E4A4
0x18001e49b  movzx   ebx, bx
0x18001e49e  or      ebx, 0C0070000h
0x18001e4a4  lea     rcx, PsmpDynamicProcessLock
0x18001e4ab  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001e4b1  test    rdi, rdi
0x18001e4b4  jz      short loc_18001E4C0
0x18001e4b6  xor     edx, edx
0x18001e4b8  mov     rcx, rdi
0x18001e4bb  call    PsmpDereferenceApplicationEx
0x18001e4c0  mov     rcx, [rsp+540h+TokenHandle]; Handle
0x18001e4c5  test    rcx, rcx
0x18001e4c8  jz      short loc_18001E4D0
0x18001e4ca  call    cs:__imp_NtClose
0x18001e4d0  mov     eax, ebx
0x18001e4d2  mov     rcx, [rbp+440h+var_20]
0x18001e4d9  xor     rcx, rsp; StackCookie
0x18001e4dc  call    __security_check_cookie
0x18001e4e1  lea     r11, [rsp+540h+var_10]
0x18001e4e9  mov     rbx, [r11+28h]
0x18001e4ed  mov     rsi, [r11+30h]
0x18001e4f1  mov     rsp, r11
0x18001e4f4  pop     r14
0x18001e4f6  pop     rdi
0x18001e4f7  pop     rbp
0x18001e4f8  retn
```
