# DsRolerDcAsDc

- ea: `0x1800058a0`
- end: `0x180005e2e`
- name: `DsRolerDcAsDc`
- size: `1422`
- prototype: `__int64 __fastcall(__int64, wchar_t *, const wchar_t *, __int64, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const WCHAR *pName2, const wchar_t *, const wchar_t *, __int64, __int64, int, int, int, _QWORD *)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task`

## callees

- `0x180003994`
- `0x180003d84`
- `0x180003fb0`
- `0x180004ef8`
- `0x180005028`
- `0x1800058a0`
- `0x18000eb40`
- `0x18000f71c`
- `0x18000ffa8`
- `0x1800150cc`
- `0x180015ff0`
- `0x1800161a8`
- `0x180016c68`
- `0x18001f6c4`
- `0x180020b08`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ddc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ddc`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180005b5f`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180005b5f`
- `netjoin!NetpValidateName` at `0x180005c14`
- `netjoin!NetpValidateName` at `0x180005c14`

## string_xrefs

- `0x180005ac0`: `	SystemVolumeRootPath  %ws\n`
- `0x180005ad5`: `	DsDatabasePath  %ws, DsLogPath  %ws\n`
- `0x180005b8f`: `Validate supplied paths\n`
- `0x180005c6b`: `Start the worker task\n`

## pseudocode

```c
__int64 __fastcall DsRolerDcAsDc(
        __int64 a1,
        wchar_t *a2,
        const wchar_t *a3,
        __int64 a4,
        const wchar_t *a5,
        const wchar_t *a6,
        const wchar_t *a7,
        const wchar_t *a8,
        const WCHAR *pName2,
        const wchar_t *a10,
        const wchar_t *a11,
        __int64 a12,
        __int64 a13,
        int a14,
        int a15,
        int a16,
        _QWORD *a17)
{
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned int IsValidProductSuite; // ebx
  STRSAFE_LPCWSTR v24; // r8
  const wchar_t *v25; // r8
  STRSAFE_LPCWSTR v26; // r8
  STRSAFE_LPCWSTR v27; // r8
  DWORD PrimaryDomainInformation; // eax
  wchar_t *v29; // rsi
  const char *v30; // rdx
  unsigned int v31; // eax
  __int64 v32; // rdx
  int v34; // [rsp+B0h] [rbp-80h] BYREF
  wchar_t *Str; // [rsp+B8h] [rbp-78h]
  PBYTE Buffer; // [rsp+C0h] [rbp-70h] BYREF
  STRSAFE_LPCWSTR v37; // [rsp+C8h] [rbp-68h]
  STRSAFE_LPCWSTR pszSrc; // [rsp+D0h] [rbp-60h]
  __int64 v39; // [rsp+D8h] [rbp-58h] BYREF
  STRSAFE_LPCWSTR v40; // [rsp+E0h] [rbp-50h]
  STRSAFE_LPCWSTR v41; // [rsp+E8h] [rbp-48h]
  STRSAFE_LPCWSTR v42; // [rsp+F0h] [rbp-40h]
  __int64 v43; // [rsp+F8h] [rbp-38h]
  _QWORD *v44; // [rsp+100h] [rbp-30h]
  _QWORD v45[3]; // [rsp+108h] [rbp-28h] BYREF
  __int64 v46[2]; // [rsp+120h] [rbp-10h] BYREF
  __int64 v47[2]; // [rsp+130h] [rbp+0h] BYREF
  __int64 v48[2]; // [rsp+140h] [rbp+10h] BYREF

  v40 = a11;
  v41 = a10;
  v44 = a17;
  v34 = 0;
  v39 = 0;
  Buffer = 0;
  v45[1] = a12;
  v45[2] = a13;
  Str = a2;
  v43 = a1;
  v42 = a5;
  pszSrc = a6;
  v37 = a7;
  v45[0] = a4;
  *(_OWORD *)v46 = 0;
  *(_OWORD *)v47 = 0;
  *(_OWORD *)v48 = 0;
  DsRolepDisableServiceStop();
  if ( !a6 )
    return 87;
  if ( !a7 )
    return 87;
  if ( !a8 )
    return 87;
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( a6[v20] );
  if ( v20 > 0x104 )
    return 87;
  v21 = -1;
  do
    ++v21;
  while ( a7[v21] );
  if ( v21 > 0x104 )
    return 87;
  do
    ++v19;
  while ( a8[v19] );
  if ( v19 > 0x104 || !a2 || !a3 || !pName2 && !a5 || (a14 & 0x10) != 0 && !pName2 || (a14 & 0x1000) != 0 && pName2 )
    return 87;
  IsValidProductSuite = DsRolepInitializeOperationHandle(v21, 0);
  if ( IsValidProductSuite )
    goto LABEL_58;
  IsValidProductSuite = DsRolepCheckClientAccess(DsRolepPromoteSD, v22, 1);
  if ( IsValidProductSuite )
    goto LABEL_57;
  DsRolepInitializeLogHelper(1);
  IsValidProductSuite = DsRolepIsValidProductSuite(pName2 == 0, 0, Str);
  if ( IsValidProductSuite )
    goto LABEL_57;
  DsRolepLogPrintRoutine(4, "Promotion request for domain controller of new domain\n");
  DsRolepLogPrintRoutine(4, "DnsDomainName  %ws\n", Str);
  DsRolepLogPrintRoutine(4, "\tFlatDomainName  %ws\n", a3);
  v24 = v42;
  if ( !v42 )
    v24 = L"(NULL)";
  DsRolepLogPrintRoutine(4, "\tSiteName  %ws\n", v24);
  DsRolepLogPrintRoutine(4, "\tSystemVolumeRootPath  %ws\n", a8);
  DsRolepLogPrintRoutine(4, "\tDsDatabasePath  %ws, DsLogPath  %ws\n", pszSrc, v37);
  v25 = pName2;
  if ( !pName2 )
    v25 = L"(NULL)";
  DsRolepLogPrintRoutine(4, "\tParentDnsDomainName  %ws\n", v25);
  v26 = v41;
  if ( !v41 )
    v26 = L"(NULL)";
  DsRolepLogPrintRoutine(4, "\tParentServer  %ws\n", v26);
  v27 = v40;
  if ( !v40 )
    v27 = L"(NULL)";
  DsRolepLogPrintRoutine(4, "\tAccount %ws\n", v27);
  DsRolepLogPrintRoutine(4, "\tOptions  %lu\n", a14);
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  IsValidProductSuite = PrimaryDomainInformation;
  if ( PrimaryDomainInformation )
  {
    v30 = "DsRoleGetPrimaryDomainInformation failed: %lu\n";
    goto LABEL_56;
  }
  if ( *(_DWORD *)Buffer != 2 )
  {
    IsValidProductSuite = 1399;
    DsRolepLogPrintRoutine(4, "Verifying domain membership failed: %lu\n", 1399);
LABEL_57:
    DsRolepResetOperationHandle(0);
    goto LABEL_58;
  }
  DsRolepLogPrintRoutine(4, "Validate supplied paths\n");
  IsValidProductSuite = DsRolepCheckFilePaths(pszSrc, v37, a8);
  if ( IsValidProductSuite )
    goto LABEL_57;
  if ( !pName2 || (a14 & 0x10) != 0 )
  {
    v29 = Str;
  }
  else
  {
    DsRolepLogPrintRoutine(4, "Child domain creation -- check the new domain name is child of parent domain name.\n");
    v29 = Str;
    PrimaryDomainInformation = DsRolepIsDnsNameChild(pName2, Str);
    IsValidProductSuite = PrimaryDomainInformation;
    if ( PrimaryDomainInformation )
    {
      v30 = "Verifying the child domain dns name failed: %lu\n";
LABEL_56:
      DsRolepLogPrintRoutine(4, v30, PrimaryDomainInformation);
      goto LABEL_57;
    }
  }
  DsRolepLogPrintRoutine(4, "Domain Creation -- check that the flat name is unique.\n");
  v31 = NetpValidateName(0, a3, 0, 0, 4);
  IsValidProductSuite = v31;
  if ( (a14 & 0x1000) != 0 && v31 == 1231 )
  {
    DsRolepLogPrintRoutine(4, "Ignoring network unreachable status\n");
  }
  else if ( v31 )
  {
    DsRolepLogPrintRoutine(4, "Flat name validation of %ws failed with %lu\n", a3, v31);
    goto LABEL_57;
  }
  IsValidProductSuite = DsRolepGetMachineType(&v34);
  if ( IsValidProductSuite )
  {
LABEL_54:
    DsRolepLogPrintRoutine(4, "This operation is not valid on a workstation or domain controller\n");
    goto LABEL_57;
  }
  if ( !v34 || v34 == 2 )
  {
    IsValidProductSuite = 1352;
    goto LABEL_54;
  }
  DsRolepLogPrintRoutine(IsValidProductSuite + 4, "Start the worker task\n");
  IsValidProductSuite = DsRolepDecryptPasswordsWithKey(
                          v43,
                          (unsigned int)v45,
                          IsValidProductSuite + 3,
                          (unsigned int)v46,
                          0);
  if ( IsValidProductSuite )
    goto LABEL_57;
  IsValidProductSuite = DsRolepBuildPromoteArgumentBlock(
                          v29,
                          a3,
                          v42,
                          pszSrc,
                          v37,
                          0,
                          a8,
                          0,
                          pName2,
                          v41,
                          v40,
                          (__int64)v47,
                          (__int64)v46,
                          (__int64)v48,
                          a14,
                          0,
                          0,
                          0,
                          a15,
                          a16,
                          (__int64)&v39);
  DsRolepFreePasswords(v46, 3);
  if ( IsValidProductSuite )
    goto LABEL_57;
  IsValidProductSuite = DsRolepSpinWorkerThread(0, v39);
  if ( IsValidProductSuite )
  {
    LOBYTE(v32) = 1;
    DsRolepFreeArgumentBlock(&v39, v32);
    goto LABEL_57;
  }
  *v44 = &DsRolepCurrentOperationHandle;
LABEL_58:
  if ( Buffer )
  {
    LocalFree(Buffer);
    Buffer = 0;
  }
  DsRolepLogPrintRoutine(4, "Request for promotion returning %lu\n", IsValidProductSuite);
  return IsValidProductSuite;
}

```

## disassembly

```asm
0x1800058a0  mov     [rsp-8+arg_18], rbx
0x1800058a5  push    rbp
0x1800058a6  push    rsi
0x1800058a7  push    rdi
0x1800058a8  push    r12
0x1800058aa  push    r13
0x1800058ac  push    r14
0x1800058ae  push    r15
0x1800058b0  lea     rbp, [rsp-30h]
0x1800058b5  sub     rsp, 160h
0x1800058bc  mov     rax, cs:__security_cookie
0x1800058c3  xor     rax, rsp
0x1800058c6  mov     [rbp+60h+var_40], rax
0x1800058ca  mov     rax, [rbp+60h+arg_50]
0x1800058d1  xorps   xmm0, xmm0
0x1800058d4  mov     r12, [rbp+60h+arg_20]
0x1800058db  mov     r15, r8
0x1800058de  mov     r14, [rbp+60h+arg_28]
0x1800058e5  mov     rsi, rdx
0x1800058e8  mov     rbx, [rbp+60h+arg_30]
0x1800058ef  mov     rdi, [rbp+60h+pName2]
0x1800058f6  mov     r13, [rbp+60h+arg_38]
0x1800058fd  mov     [rbp+60h+var_B0], rax
0x180005901  mov     rax, [rbp+60h+arg_48]
0x180005908  mov     [rbp+60h+var_A8], rax
0x18000590c  mov     rax, [rbp+60h+arg_80]
0x180005913  mov     [rbp+60h+var_90], rax
0x180005917  xor     eax, eax
0x180005919  mov     [rbp+60h+var_E0], eax
0x18000591c  mov     [rbp+60h+var_B8], rax
0x180005920  mov     [rbp+60h+Buffer], rax
0x180005924  mov     rax, [rbp+60h+arg_58]
0x18000592b  mov     [rbp+60h+var_80], rax
0x18000592f  mov     rax, [rbp+60h+arg_60]
0x180005936  mov     [rbp+60h+var_78], rax
0x18000593a  mov     [rbp+60h+Str], rdx
0x18000593e  mov     [rbp+60h+var_98], rcx
0x180005942  mov     [rbp+60h+var_A0], r12
0x180005946  mov     [rbp+60h+pszSrc], r14
0x18000594a  mov     [rbp+60h+var_C8], rbx
0x18000594e  mov     [rbp+60h+var_88], r9
0x180005952  movups  xmmword ptr [rbp+60h+var_70], xmm0
0x180005956  movups  xmmword ptr [rbp+60h+var_60], xmm0
0x18000595a  movups  xmmword ptr [rbp+60h+var_50], xmm0
0x18000595e  call    DsRolepDisableServiceStop
0x180005963  xor     edx, edx
0x180005965  test    r14, r14
0x180005968  jz      loc_180005E02
0x18000596e  test    rbx, rbx
0x180005971  jz      loc_180005E02
0x180005977  test    r13, r13
0x18000597a  jz      loc_180005E02
0x180005980  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005984  mov     rcx, rax
0x180005987  inc     rcx
0x18000598a  cmp     [r14+rcx*2], dx
0x18000598f  jnz     short loc_180005987
0x180005991  mov     r8d, 104h
0x180005997  cmp     rcx, r8
0x18000599a  ja      loc_180005E02
0x1800059a0  mov     rcx, rax
0x1800059a3  inc     rcx
0x1800059a6  cmp     [rbx+rcx*2], dx
0x1800059aa  jnz     short loc_1800059A3
0x1800059ac  cmp     rcx, r8
0x1800059af  ja      loc_180005E02
0x1800059b5  inc     rax
0x1800059b8  cmp     [r13+rax*2+0], dx
0x1800059be  jnz     short loc_1800059B5
0x1800059c0  cmp     rax, r8
0x1800059c3  ja      loc_180005E02
0x1800059c9  test    rsi, rsi
0x1800059cc  jz      loc_180005E02
0x1800059d2  test    r15, r15
0x1800059d5  jz      loc_180005E02
0x1800059db  test    rdi, rdi
0x1800059de  jnz     short loc_1800059E9
0x1800059e0  test    r12, r12
0x1800059e3  jz      loc_180005E02
0x1800059e9  mov     r12d, [rbp+60h+arg_68]
0x1800059f0  mov     esi, r12d
0x1800059f3  and     esi, 10h
0x1800059f6  jz      short loc_180005A01
0x1800059f8  test    rdi, rdi
0x1800059fb  jz      loc_180005E02
0x180005a01  mov     r14d, r12d
0x180005a04  and     r14d, 1000h
0x180005a0b  jz      short loc_180005A16
0x180005a0d  test    rdi, rdi
0x180005a10  jnz     loc_180005E02
0x180005a16  call    DsRolepInitializeOperationHandle
0x180005a1b  mov     ebx, eax
0x180005a1d  test    eax, eax
0x180005a1f  jnz     loc_180005DD3
0x180005a25  mov     r8b, 1
0x180005a28  lea     rcx, DsRolepPromoteSD; pSecurityDescriptor
0x180005a2f  call    DsRolepCheckClientAccess
0x180005a34  mov     ebx, eax
0x180005a36  test    eax, eax
0x180005a38  jnz     loc_180005DCC
0x180005a3e  lea     ecx, [rax+1]
0x180005a41  call    DsRolepInitializeLogHelper
0x180005a46  mov     r8, [rbp+60h+Str]
0x180005a4a  xor     ecx, ecx
0x180005a4c  test    rdi, rdi
0x180005a4f  setz    cl
0x180005a52  xor     edx, edx
0x180005a54  call    DsRolepIsValidProductSuite
0x180005a59  mov     ebx, eax
0x180005a5b  test    eax, eax
0x180005a5d  jnz     loc_180005DCC
0x180005a63  lea     ebx, [rax+4]
0x180005a66  mov     ecx, ebx
0x180005a68  lea     rdx, aPromotionReque_0; "Promotion request for domain controller"...
0x180005a6f  call    DsRolepLogPrintRoutine
0x180005a74  mov     r8, [rbp+60h+Str]
0x180005a78  lea     rdx, aDnsdomainnameW; "DnsDomainName  %ws\n"
0x180005a7f  mov     ecx, ebx
0x180005a81  call    DsRolepLogPrintRoutine
0x180005a86  mov     r8, r15
0x180005a89  lea     rdx, aFlatdomainname; "\tFlatDomainName  %ws\n"
0x180005a90  mov     ecx, ebx
0x180005a92  call    DsRolepLogPrintRoutine
0x180005a97  mov     rax, [rbp+60h+var_A0]
0x180005a9b  lea     rbx, aNull; "(NULL)"
0x180005aa2  test    rax, rax
0x180005aa5  lea     rdx, aSitenameWs; "\tSiteName  %ws\n"
0x180005aac  mov     r8, rax
0x180005aaf  mov     ecx, 4
0x180005ab4  cmovz   r8, rbx
0x180005ab8  call    DsRolepLogPrintRoutine
0x180005abd  mov     r8, r13
0x180005ac0  lea     rdx, aSystemvolumero; "\tSystemVolumeRootPath  %ws\n"
0x180005ac7  mov     ecx, 4
0x180005acc  call    DsRolepLogPrintRoutine
0x180005ad1  mov     r9, [rbp+60h+var_C8]
0x180005ad5  lea     rdx, aDsdatabasepath; "\tDsDatabasePath  %ws, DsLogPath  %ws\n"
0x180005adc  mov     r8, [rbp+60h+pszSrc]
0x180005ae0  mov     ecx, 4
0x180005ae5  call    DsRolepLogPrintRoutine
0x180005aea  test    rdi, rdi
0x180005aed  lea     rdx, aParentdnsdomai; "\tParentDnsDomainName  %ws\n"
0x180005af4  mov     r8, rdi
0x180005af7  mov     ecx, 4
0x180005afc  cmovz   r8, rbx
0x180005b00  call    DsRolepLogPrintRoutine
0x180005b05  mov     rax, [rbp+60h+var_A8]
0x180005b09  lea     rdx, aParentserverWs; "\tParentServer  %ws\n"
0x180005b10  test    rax, rax
0x180005b13  mov     r8, rax
0x180005b16  mov     ecx, 4
0x180005b1b  cmovz   r8, rbx
0x180005b1f  call    DsRolepLogPrintRoutine
0x180005b24  mov     rax, [rbp+60h+var_B0]
0x180005b28  lea     rdx, aAccountWs; "\tAccount %ws\n"
0x180005b2f  test    rax, rax
0x180005b32  mov     r8, rax
0x180005b35  cmovz   r8, rbx
0x180005b39  mov     ebx, 4
0x180005b3e  mov     ecx, ebx
0x180005b40  call    DsRolepLogPrintRoutine
0x180005b45  mov     r8d, r12d
0x180005b48  lea     rdx, aOptionsLu; "\tOptions  %lu\n"
0x180005b4f  mov     ecx, ebx
0x180005b51  call    DsRolepLogPrintRoutine
0x180005b56  lea     r8, [rbp+60h+Buffer]; Buffer
0x180005b5a  xor     ecx, ecx; lpServer
0x180005b5c  lea     edx, [rbx-3]; InfoLevel
0x180005b5f  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180005b65  mov     ebx, eax
0x180005b67  test    eax, eax
0x180005b69  jnz     loc_180005DB8
0x180005b6f  mov     rax, [rbp+60h+Buffer]
0x180005b73  lea     ecx, [rbx+4]
0x180005b76  cmp     dword ptr [rax], 2
0x180005b79  jz      short loc_180005B8F
0x180005b7b  mov     ebx, 577h
0x180005b80  lea     rdx, aVerifyingDomai; "Verifying domain membership failed: %lu"...
0x180005b87  mov     r8d, ebx
0x180005b8a  jmp     loc_180005DC7
0x180005b8f  lea     rdx, aValidateSuppli; "Validate supplied paths\n"
0x180005b96  call    DsRolepLogPrintRoutine
0x180005b9b  mov     rdx, [rbp+60h+var_C8]; STRSAFE_PCNZWCH
0x180005b9f  mov     r8, r13; STRSAFE_PCNZWCH
0x180005ba2  mov     rcx, [rbp+60h+pszSrc]; pszSrc
0x180005ba6  call    DsRolepCheckFilePaths
0x180005bab  mov     ebx, eax
0x180005bad  test    eax, eax
0x180005baf  jnz     loc_180005DCC
0x180005bb5  test    rdi, rdi
0x180005bb8  jz      short loc_180005BEE
0x180005bba  test    esi, esi
0x180005bbc  jnz     short loc_180005BEE
0x180005bbe  lea     rdx, aChildDomainCre; "Child domain creation -- check the new "...
0x180005bc5  lea     ecx, [rax+4]
0x180005bc8  call    DsRolepLogPrintRoutine
0x180005bcd  mov     rsi, [rbp+60h+Str]
0x180005bd1  mov     rcx, rdi; pName2
0x180005bd4  mov     rdx, rsi; Str
0x180005bd7  call    DsRolepIsDnsNameChild
0x180005bdc  mov     ebx, eax
0x180005bde  test    eax, eax
0x180005be0  jz      short loc_180005BF2
0x180005be2  lea     rdx, aVerifyingTheCh; "Verifying the child domain dns name fai"...
0x180005be9  jmp     loc_180005DBF
0x180005bee  mov     rsi, [rbp+60h+Str]
0x180005bf2  mov     ebx, 4
0x180005bf7  lea     rdx, aDomainCreation; "Domain Creation -- check that the flat "...
0x180005bfe  mov     ecx, ebx
0x180005c00  call    DsRolepLogPrintRoutine
0x180005c05  xor     r9d, r9d
0x180005c08  mov     dword ptr [rsp+190h+var_170], ebx
0x180005c0c  xor     r8d, r8d
0x180005c0f  mov     rdx, r15
0x180005c12  xor     ecx, ecx
0x180005c14  call    cs:__imp_NetpValidateName
0x180005c1a  mov     ebx, eax
0x180005c1c  test    r14d, r14d
0x180005c1f  jz      loc_180005D6D
0x180005c25  cmp     eax, 4CFh
0x180005c2a  jnz     loc_180005D6D
0x180005c30  lea     rdx, aIgnoringNetwor; "Ignoring network unreachable status\n"
0x180005c37  mov     ecx, 4
0x180005c3c  call    DsRolepLogPrintRoutine
0x180005c41  xor     r14d, r14d
0x180005c44  lea     rcx, [rbp+60h+var_E0]
0x180005c48  call    DsRolepGetMachineType
0x180005c4d  mov     ebx, eax
0x180005c4f  test    eax, eax
0x180005c51  jnz     loc_180005DA5
0x180005c57  mov     eax, [rbp+60h+var_E0]
0x180005c5a  test    eax, eax
0x180005c5c  jz      loc_180005DA0
0x180005c62  cmp     eax, 2
0x180005c65  jz      loc_180005DA0
0x180005c6b  lea     rdx, aStartTheWorker; "Start the worker task\n"
0x180005c72  lea     ecx, [rbx+4]
0x180005c75  call    DsRolepLogPrintRoutine
0x180005c7a  mov     rcx, [rbp+60h+var_98]
0x180005c7e  lea     r9, [rbp+60h+var_70]
0x180005c82  lea     r8d, [rbx+3]
0x180005c86  mov     [rsp+190h+var_170], r14
0x180005c8b  lea     rdx, [rbp+60h+var_88]
0x180005c8f  call    DsRolepDecryptPasswordsWithKey
0x180005c94  mov     ebx, eax
0x180005c96  test    eax, eax
0x180005c98  jnz     loc_180005DCC
0x180005c9e  mov     r9, [rbp+60h+pszSrc]; STRSAFE_LPCWSTR
0x180005ca2  lea     rax, [rbp+60h+var_B8]
0x180005ca6  mov     r8, [rbp+60h+var_A0]; STRSAFE_LPCWSTR
0x180005caa  mov     rdx, r15; STRSAFE_LPCWSTR
0x180005cad  mov     [rsp+190h+var_F0], rax; __int64
0x180005cb5  mov     rcx, rsi; pszSrc
0x180005cb8  mov     eax, [rbp+60h+arg_78]
0x180005cbe  mov     [rsp+190h+var_F8], eax; int
0x180005cc5  mov     eax, [rbp+60h+arg_70]
0x180005ccb  mov     [rsp+190h+var_100], eax; int
0x180005cd2  lea     rax, [rbp+60h+var_50]
0x180005cd6  mov     [rsp+190h+var_108], r14; __int64
0x180005cde  mov     [rsp+190h+var_110], r14; __int64
0x180005ce6  mov     [rsp+190h+var_118], r14d; int
0x180005ceb  mov     [rsp+190h+var_120], r12d; int
0x180005cf0  mov     [rsp+190h+var_128], rax; __int64
0x180005cf5  lea     rax, [rbp+60h+var_70]
0x180005cf9  mov     [rsp+190h+var_130], rax; __int64
0x180005cfe  lea     rax, [rbp+60h+var_60]
0x180005d02  mov     [rsp+190h+var_138], rax; __int64
0x180005d07  mov     rax, [rbp+60h+var_B0]
0x180005d0b  mov     [rsp+190h+var_140], rax; STRSAFE_LPCWSTR
0x180005d10  mov     rax, [rbp+60h+var_A8]
0x180005d14  mov     [rsp+190h+var_148], rax; STRSAFE_LPCWSTR
0x180005d19  mov     rax, [rbp+60h+var_C8]
0x180005d1d  mov     [rsp+190h+var_150], rdi; STRSAFE_LPCWSTR
0x180005d22  mov     [rsp+190h+var_158], r14; __int64
0x180005d27  mov     [rsp+190h+var_160], r13; STRSAFE_LPCWSTR
0x180005d2c  mov     [rsp+190h+var_168], r14; __int64
0x180005d31  mov     [rsp+190h+var_170], rax; STRSAFE_LPCWSTR
0x180005d36  call    DsRolepBuildPromoteArgumentBlock
0x180005d3b  mov     edx, 3
0x180005d40  lea     rcx, [rbp+60h+var_70]
0x180005d44  mov     ebx, eax
0x180005d46  call    DsRolepFreePasswords
0x180005d4b  test    ebx, ebx
0x180005d4d  jnz     short loc_180005DCC
0x180005d4f  mov     rdx, [rbp+60h+var_B8]
0x180005d53  xor     ecx, ecx
0x180005d55  call    DsRolepSpinWorkerThread
0x180005d5a  mov     ebx, eax
0x180005d5c  test    eax, eax
0x180005d5e  jz      short loc_180005D90
0x180005d60  mov     dl, 1
0x180005d62  lea     rcx, [rbp+60h+var_B8]
0x180005d66  call    DsRolepFreeArgumentBlock
0x180005d6b  jmp     short loc_180005DCC
0x180005d6d  xor     r14d, r14d
0x180005d70  test    eax, eax
0x180005d72  jz      loc_180005C44
0x180005d78  mov     r9d, eax
0x180005d7b  lea     rdx, aFlatNameValida; "Flat name validation of %ws failed with"...
0x180005d82  mov     r8, r15
  ... truncated ...
```
