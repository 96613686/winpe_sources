# DsRolerUpgradeDownlevelServer

- ea: `0x180006c30`
- end: `0x180006fc7`
- name: `DsRolerUpgradeDownlevelServer`
- size: `919`
- prototype: `__int64 __fastcall(int, int, int, int, STRSAFE_LPCWSTR, STRSAFE_LPCWSTR, PCWSTR pName2, STRSAFE_LPCWSTR, STRSAFE_LPCWSTR, __int64, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003994`
- `0x180003d84`
- `0x180003fb0`
- `0x180004ef8`
- `0x180006c30`
- `0x18000eb40`
- `0x18000f71c`
- `0x18000ffa8`
- `0x18001428c`
- `0x1800150cc`
- `0x180015ff0`
- `0x1800161a8`
- `0x180016c68`
- `0x180020b08`
- `0x180020dbc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180006e95`
- `ntdll!RtlNtStatusToDosError` at `0x180006e95`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180006e8d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180006e8d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180006e81`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180006e81`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006f8a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006f8a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180006e68`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180006e68`

## string_xrefs

- `0x180006d4c`: `	SystemVolumeRootPath  %ws\n`
- `0x180006d5d`: `	DsDatabasePath  %ws, DsLogPath  %ws\n`
- `0x180006e06`: `Validate supplied paths\n`

## pseudocode

```c
__int64 __fastcall DsRolerUpgradeDownlevelServer(
        __int64 a1,
        wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        STRSAFE_LPCWSTR a5,
        STRSAFE_LPCWSTR a6,
        PCWSTR pName2,
        STRSAFE_LPCWSTR a8,
        STRSAFE_LPCWSTR a9,
        __int64 a10,
        __int64 a11,
        int a12,
        _QWORD *a13)
{
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // ebx
  const wchar_t *v20; // r8
  int v21; // ebx
  __int64 v22; // rdx
  _BYTE v24[4]; // [rsp+B8h] [rbp-80h] BYREF
  int v25; // [rsp+BCh] [rbp-7Ch] BYREF
  PVOID PolicyHandle; // [rsp+C0h] [rbp-78h] BYREF
  __int64 v27; // [rsp+C8h] [rbp-70h] BYREF
  PVOID Buffer; // [rsp+D0h] [rbp-68h] BYREF
  _QWORD v29[2]; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v30[2]; // [rsp+E8h] [rbp-50h] BYREF
  __int64 v31[2]; // [rsp+F8h] [rbp-40h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+108h] [rbp-30h] BYREF

  v24[0] = 0;
  v29[0] = a10;
  v29[1] = a11;
  *(_OWORD *)&ObjectAttributes.ObjectName = 0;
  v25 = 0;
  v27 = 0;
  *a13 = 0;
  PolicyHandle = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  Buffer = 0;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  *(_OWORD *)v30 = 0;
  *(_OWORD *)v31 = 0;
  DsRolepDisableServiceStop();
  if ( !a2 || !a4 || !a5 || !a6 )
    return 87;
  v19 = DsRolepInitializeOperationHandle(v17, v16);
  if ( !v19 )
  {
    v19 = DsRolepCheckClientAccess(DsRolepPromoteSD, v18, 1);
    if ( !v19 )
    {
      DsRolepInitializeLogHelper(1u);
      DsRolepLogPrintRoutine(4, "DsRolerDcAsDc: DnsDomainName  %ws\n", a2);
      v20 = a3;
      if ( !a3 )
        v20 = L"(NULL)";
      DsRolepLogPrintRoutine(4, "\tSiteName  %ws\n", v20);
      DsRolepLogPrintRoutine(4, "\tSystemVolumeRootPath  %ws\n", a6);
      DsRolepLogPrintRoutine(4, "\tDsDatabasePath  %ws, DsLogPath  %ws\n", a4, a5);
      if ( pName2 )
        DsRolepLogPrintRoutine(4, "\tParentDnsDomainName  %ws\n", pName2);
      if ( a8 )
        DsRolepLogPrintRoutine(4, "\tParentServer  %ws\n", a8);
      if ( a9 )
        DsRolepLogPrintRoutine(4, "\tAccount %ws\n", a9);
      DsRolepLogPrintRoutine(4, "\tOptions  %lu\n", a12);
      v19 = DsRolepQueryUpgradeInfo(v24, &v25);
      if ( !v19 )
      {
        if ( !v24[0] || v25 == 2 )
          return 1352;
        DsRolepLogPrintRoutine(4, "Validate supplied paths\n");
        v19 = DsRolepCheckFilePaths(a4, a5, a6);
        if ( !v19 )
        {
          if ( !pName2 || (a12 & 0x10) != 0 || !(unsigned int)DsRolepIsDnsNameChild(pName2, a2) )
          {
            memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
            v21 = LsaOpenPolicy(0, &ObjectAttributes, 0x2000000u, &PolicyHandle);
            if ( v21 >= 0 )
            {
              v21 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &Buffer);
              LsaClose(PolicyHandle);
            }
            RtlNtStatusToDosError(v21);
          }
          v19 = DsRolepDecryptPasswordsWithKey(a1, (__int64)v29, 2u, (__int64)v30, 0);
          if ( !v19 )
            v19 = DsRolepBuildPromoteArgumentBlock(
                    a2,
                    *((STRSAFE_LPCWSTR *)Buffer + 1),
                    a3,
                    a4,
                    a5,
                    0,
                    a6,
                    0,
                    pName2,
                    a8,
                    a9,
                    (__int64)v30,
                    0,
                    (__int64)v31,
                    a12 | 0x20u,
                    0,
                    0,
                    0,
                    0,
                    0,
                    (__int64)&v27);
          DsRolepFreePasswords(v30, 2);
          if ( !v19 )
          {
            v19 = DsRolepSpinWorkerThread(0, v27);
            if ( !v19 )
            {
              *a13 = &DsRolepCurrentOperationHandle;
              goto LABEL_31;
            }
            LOBYTE(v22) = 1;
            DsRolepFreeArgumentBlock(&v27, v22);
          }
          DsRolepResetOperationHandle(0);
LABEL_31:
          LsaFreeMemory(Buffer);
        }
      }
    }
  }
  return v19;
}

```

## disassembly

```asm
0x180006c30  mov     rax, rsp
0x180006c33  mov     [rax+20h], r9
0x180006c37  mov     [rax+18h], r8
0x180006c3b  mov     [rax+10h], rdx
0x180006c3f  mov     [rax+8], rcx
0x180006c43  push    rbp
0x180006c44  push    rbx
0x180006c45  push    rsi
0x180006c46  push    rdi
0x180006c47  push    r12
0x180006c49  push    r13
0x180006c4b  push    r14
0x180006c4d  push    r15
0x180006c4f  lea     rbp, [rax-48h]
0x180006c53  sub     rsp, 138h
0x180006c5a  xorps   xmm0, xmm0
0x180006c5d  xor     r12d, r12d
0x180006c60  xor     eax, eax
0x180006c62  mov     [rbp+40h+var_C0], r12b
0x180006c66  mov     rax, [rbp+40h+arg_48]
0x180006c6d  mov     rdi, r9
0x180006c70  mov     [rbp+40h+var_A0], rax
0x180006c74  mov     r15, r8
0x180006c77  mov     rax, [rbp+40h+arg_50]
0x180006c7e  mov     rsi, rdx
0x180006c81  mov     [rbp+40h+var_98], rax
0x180006c85  mov     rax, [rbp+40h+arg_60]
0x180006c8c  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x180006c90  mov     [rbp+40h+var_BC], r12d
0x180006c94  mov     [rbp+40h+var_B0], r12
0x180006c98  mov     [rax], r12
0x180006c9b  mov     [rbp+40h+PolicyHandle], r12
0x180006c9f  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x180006ca3  mov     [rbp+40h+Buffer], r12
0x180006ca7  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x180006cab  movups  xmmword ptr [rbp+40h+var_90], xmm0
0x180006caf  movups  xmmword ptr [rbp+40h+var_80], xmm0
0x180006cb3  call    DsRolepDisableServiceStop
0x180006cb8  test    rsi, rsi
0x180006cbb  jz      loc_180006FAC
0x180006cc1  test    rdi, rdi
0x180006cc4  jz      loc_180006FAC
0x180006cca  mov     r14, [rbp+40h+arg_20]
0x180006cce  test    r14, r14
0x180006cd1  jz      loc_180006FAC
0x180006cd7  mov     r13, [rbp+40h+arg_28]
0x180006cdb  test    r13, r13
0x180006cde  jz      loc_180006FAC
0x180006ce4  call    DsRolepInitializeOperationHandle
0x180006ce9  mov     ebx, eax
0x180006ceb  test    eax, eax
0x180006ced  jnz     loc_180006FB1
0x180006cf3  mov     r8b, 1
0x180006cf6  lea     rcx, DsRolepPromoteSD; pSecurityDescriptor
0x180006cfd  call    DsRolepCheckClientAccess
0x180006d02  mov     ebx, eax
0x180006d04  test    eax, eax
0x180006d06  jnz     loc_180006FB1
0x180006d0c  lea     ecx, [rax+1]
0x180006d0f  call    DsRolepInitializeLogHelper
0x180006d14  lea     ebx, [r12+4]
0x180006d19  mov     r8, rsi
0x180006d1c  mov     ecx, ebx
0x180006d1e  lea     rdx, aDsrolerdcasdcD; "DsRolerDcAsDc: DnsDomainName  %ws\n"
0x180006d25  call    DsRolepLogPrintRoutine
0x180006d2a  lea     rax, aNull; "(NULL)"
0x180006d31  test    r15, r15
0x180006d34  mov     r8, r15
0x180006d37  lea     rdx, aSitenameWs; "\tSiteName  %ws\n"
0x180006d3e  cmovz   r8, rax
0x180006d42  mov     ecx, ebx
0x180006d44  call    DsRolepLogPrintRoutine
0x180006d49  mov     r8, r13
0x180006d4c  lea     rdx, aSystemvolumero; "\tSystemVolumeRootPath  %ws\n"
0x180006d53  mov     ecx, ebx
0x180006d55  call    DsRolepLogPrintRoutine
0x180006d5a  mov     r9, r14
0x180006d5d  lea     rdx, aDsdatabasepath; "\tDsDatabasePath  %ws, DsLogPath  %ws\n"
0x180006d64  mov     r8, rdi
0x180006d67  mov     ecx, ebx
0x180006d69  call    DsRolepLogPrintRoutine
0x180006d6e  mov     rsi, [rbp+40h+pName2]
0x180006d75  test    rsi, rsi
0x180006d78  jz      short loc_180006D8B
0x180006d7a  mov     r8, rsi
0x180006d7d  lea     rdx, aParentdnsdomai; "\tParentDnsDomainName  %ws\n"
0x180006d84  mov     ecx, ebx
0x180006d86  call    DsRolepLogPrintRoutine
0x180006d8b  mov     r12, [rbp+40h+arg_38]
0x180006d92  test    r12, r12
0x180006d95  jz      short loc_180006DA8
0x180006d97  mov     r8, r12
0x180006d9a  lea     rdx, aParentserverWs; "\tParentServer  %ws\n"
0x180006da1  mov     ecx, ebx
0x180006da3  call    DsRolepLogPrintRoutine
0x180006da8  mov     r15, [rbp+40h+arg_40]
0x180006daf  test    r15, r15
0x180006db2  jz      short loc_180006DC5
0x180006db4  mov     r8, r15
0x180006db7  lea     rdx, aAccountWs; "\tAccount %ws\n"
0x180006dbe  mov     ecx, ebx
0x180006dc0  call    DsRolepLogPrintRoutine
0x180006dc5  mov     edi, [rbp+40h+arg_58]
0x180006dcb  lea     rdx, aOptionsLu; "\tOptions  %lu\n"
0x180006dd2  mov     r8d, edi
0x180006dd5  mov     ecx, ebx
0x180006dd7  call    DsRolepLogPrintRoutine
0x180006ddc  lea     rdx, [rbp+40h+var_BC]
0x180006de0  lea     rcx, [rbp+40h+var_C0]
0x180006de4  call    DsRolepQueryUpgradeInfo
0x180006de9  mov     ebx, eax
0x180006deb  test    eax, eax
0x180006ded  jnz     loc_180006FB1
0x180006df3  cmp     [rbp+40h+var_C0], al
0x180006df6  jz      loc_180006FA5
0x180006dfc  cmp     [rbp+40h+var_BC], 2
0x180006e00  jz      loc_180006FA5
0x180006e06  lea     rdx, aValidateSuppli; "Validate supplied paths\n"
0x180006e0d  lea     ecx, [rax+4]
0x180006e10  call    DsRolepLogPrintRoutine
0x180006e15  mov     rcx, [rbp+40h+pszSrc]; pszSrc
0x180006e19  mov     r8, r13; STRSAFE_PCNZWCH
0x180006e1c  mov     rdx, r14; STRSAFE_PCNZWCH
0x180006e1f  call    DsRolepCheckFilePaths
0x180006e24  mov     ebx, eax
0x180006e26  test    eax, eax
0x180006e28  jnz     loc_180006FB1
0x180006e2e  test    rsi, rsi
0x180006e31  jz      short loc_180006E49
0x180006e33  test    dil, 10h
0x180006e37  jnz     short loc_180006E49
0x180006e39  mov     rdx, [rbp+40h+Str]; Str
0x180006e3d  mov     rcx, rsi; pName2
0x180006e40  call    DsRolepIsDnsNameChild
0x180006e45  test    eax, eax
0x180006e47  jnz     short loc_180006E9B
0x180006e49  xorps   xmm0, xmm0
0x180006e4c  lea     r9, [rbp+40h+PolicyHandle]; PolicyHandle
0x180006e50  mov     r8d, 2000000h; DesiredAccess
0x180006e56  lea     rdx, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x180006e5a  xor     ecx, ecx; SystemName
0x180006e5c  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x180006e60  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x180006e64  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006e68  call    cs:__imp_LsaOpenPolicy
0x180006e6e  mov     ebx, eax
0x180006e70  test    eax, eax
0x180006e72  js      short loc_180006E93
0x180006e74  mov     rcx, [rbp+40h+PolicyHandle]; PolicyHandle
0x180006e78  lea     r8, [rbp+40h+Buffer]; Buffer
0x180006e7c  mov     edx, 3; InformationClass
0x180006e81  call    cs:__imp_LsaQueryInformationPolicy
0x180006e87  mov     rcx, [rbp+40h+PolicyHandle]; ObjectHandle
0x180006e8b  mov     ebx, eax
0x180006e8d  call    cs:__imp_LsaClose
0x180006e93  mov     ecx, ebx; Status
0x180006e95  call    cs:__imp_RtlNtStatusToDosError
0x180006e9b  mov     rcx, [rbp+40h+arg_0]
0x180006e9f  lea     r9, [rbp+40h+var_90]
0x180006ea3  mov     r8d, 2
0x180006ea9  mov     [rsp+170h+var_150], 0
0x180006eb2  lea     rdx, [rbp+40h+var_A0]
0x180006eb6  call    DsRolepDecryptPasswordsWithKey
0x180006ebb  xor     ecx, ecx
0x180006ebd  mov     ebx, eax
0x180006ebf  test    eax, eax
0x180006ec1  jnz     loc_180006F51
0x180006ec7  mov     rdx, [rbp+40h+Buffer]
0x180006ecb  lea     rax, [rbp+40h+var_B0]
0x180006ecf  mov     r9, [rbp+40h+pszSrc]; STRSAFE_LPCWSTR
0x180006ed3  or      edi, 20h
0x180006ed6  mov     r8, [rbp+40h+arg_10]; STRSAFE_LPCWSTR
0x180006eda  mov     [rsp+0A0h], rax; __int64
0x180006ee2  lea     rax, [rbp+40h+var_80]
0x180006ee6  mov     rdx, [rdx+8]; STRSAFE_LPCWSTR
0x180006eea  mov     [rsp+170h+var_D8], ecx; int
0x180006ef1  mov     [rsp+170h+var_E0], ecx; int
0x180006ef8  mov     [rsp+170h+var_E8], rcx; __int64
0x180006f00  mov     [rsp+170h+var_F0], rcx; __int64
0x180006f08  mov     [rsp+170h+var_F8], ecx; int
0x180006f0c  mov     [rsp+170h+var_100], edi; int
0x180006f10  mov     [rsp+170h+var_108], rax; __int64
0x180006f15  lea     rax, [rbp+40h+var_90]
0x180006f19  mov     [rsp+170h+var_110], rcx; __int64
0x180006f1e  mov     [rsp+170h+var_118], rax; __int64
0x180006f23  mov     [rsp+170h+var_120], r15; STRSAFE_LPCWSTR
0x180006f28  mov     [rsp+170h+var_128], r12; STRSAFE_LPCWSTR
0x180006f2d  mov     [rsp+170h+var_130], rsi; STRSAFE_LPCWSTR
0x180006f32  mov     [rsp+170h+var_138], rcx; __int64
0x180006f37  mov     [rsp+170h+var_140], r13; STRSAFE_LPCWSTR
0x180006f3c  mov     [rsp+170h+var_148], rcx; __int64
0x180006f41  mov     rcx, [rbp+40h+Str]; pszSrc
0x180006f45  mov     [rsp+170h+var_150], r14; STRSAFE_LPCWSTR
0x180006f4a  call    DsRolepBuildPromoteArgumentBlock
0x180006f4f  mov     ebx, eax
0x180006f51  mov     edx, 2
0x180006f56  lea     rcx, [rbp+40h+var_90]
0x180006f5a  call    DsRolepFreePasswords
0x180006f5f  test    ebx, ebx
0x180006f61  jnz     short loc_180006F7F
0x180006f63  mov     rdx, [rbp+40h+var_B0]
0x180006f67  xor     ecx, ecx
0x180006f69  call    DsRolepSpinWorkerThread
0x180006f6e  mov     ebx, eax
0x180006f70  test    eax, eax
0x180006f72  jz      short loc_180006F92
0x180006f74  mov     dl, 1
0x180006f76  lea     rcx, [rbp+40h+var_B0]
0x180006f7a  call    DsRolepFreeArgumentBlock
0x180006f7f  xor     ecx, ecx
0x180006f81  call    DsRolepResetOperationHandle
0x180006f86  mov     rcx, [rbp+40h+Buffer]; Buffer
0x180006f8a  call    cs:__imp_LsaFreeMemory
0x180006f90  jmp     short loc_180006FB1
0x180006f92  mov     rax, [rbp+40h+arg_60]
0x180006f99  lea     rcx, DsRolepCurrentOperationHandle
0x180006fa0  mov     [rax], rcx
0x180006fa3  jmp     short loc_180006F86
0x180006fa5  mov     ebx, 548h
0x180006faa  jmp     short loc_180006FB1
0x180006fac  mov     ebx, 57h ; 'W'
0x180006fb1  mov     eax, ebx
0x180006fb3  add     rsp, 138h
0x180006fba  pop     r15
0x180006fbc  pop     r14
0x180006fbe  pop     r13
0x180006fc0  pop     r12
0x180006fc2  pop     rdi
0x180006fc3  pop     rsi
0x180006fc4  pop     rbx
0x180006fc5  pop     rbp
0x180006fc6  retn
```
