# IcpGetContainerHelper(unsigned __int64 *,char const *,char const *,ulong,ulong,int)

- ea: `0x180029480`
- end: `0x1800299ea`
- name: `?IcpGetContainerHelper@@YAJPEA_KPEBD1KKH@Z`
- size: `1386`
- prototype: `int(unsigned __int64 *, const char *, const char *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029a34`
- `0x180029a6c`

## callees

- `0x18002937c`
- `0x180029480`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `ADVAPI32!CryptSetProvParam` at `0x180029950`
- `ADVAPI32!CryptSetProvParam` at `0x180029950`
- `ADVAPI32!CryptReleaseContext` at `0x1800299a6`
- `ADVAPI32!CryptReleaseContext` at `0x1800299a6`
- `ADVAPI32!CryptAcquireContextA` at `0x180029543`
- `ADVAPI32!CryptAcquireContextA` at `0x18002960b`
- `ADVAPI32!CryptAcquireContextA` at `0x180029757`
- `ADVAPI32!CryptAcquireContextA` at `0x180029543`
- `ADVAPI32!CryptAcquireContextA` at `0x18002960b`
- `ADVAPI32!CryptAcquireContextA` at `0x180029757`
- `ADVAPI32!InitializeAcl` at `0x1800298e0`
- `ADVAPI32!InitializeAcl` at `0x1800298e0`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002984f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180029894`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002984f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180029894`
- `ADVAPI32!FreeSid` at `0x180029981`
- `ADVAPI32!FreeSid` at `0x180029990`
- `ADVAPI32!FreeSid` at `0x180029981`
- `ADVAPI32!FreeSid` at `0x180029990`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180029933`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180029933`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180029805`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180029805`
- `ADVAPI32!GetLengthSid` at `0x1800298a7`
- `ADVAPI32!GetLengthSid` at `0x1800298b3`
- `ADVAPI32!GetLengthSid` at `0x1800298a7`
- `ADVAPI32!GetLengthSid` at `0x1800298b3`
- `ADVAPI32!AddAccessAllowedAce` at `0x180029904`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002991b`
- `ADVAPI32!AddAccessAllowedAce` at `0x180029904`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002991b`
- `ole32!CoTaskMemAlloc` at `0x1800298c0`
- `ole32!CoTaskMemAlloc` at `0x1800298c0`
- `ole32!CoTaskMemFree` at `0x180029971`
- `ole32!CoTaskMemFree` at `0x180029971`
- `KERNEL32!LeaveCriticalSection` at `0x1800299c4`
- `KERNEL32!LeaveCriticalSection` at `0x1800299c4`
- `KERNEL32!EnterCriticalSection` at `0x18002951c`
- `KERNEL32!EnterCriticalSection` at `0x18002951c`
- `KERNEL32!GetVersionExA` at `0x1800297d3`
- `KERNEL32!GetVersionExA` at `0x1800297d3`
- `IisRTL!PuDbgPrint` at `0x180029598`
- `IisRTL!PuDbgPrint` at `0x1800295f1`
- `IisRTL!PuDbgPrint` at `0x180029673`
- `IisRTL!PuDbgPrint` at `0x1800296d1`
- `IisRTL!PuDbgPrint` at `0x180029736`
- `IisRTL!PuDbgPrint` at `0x1800297a2`
- `IisRTL!PuDbgPrint` at `0x180029598`
- `IisRTL!PuDbgPrint` at `0x1800295f1`
- `IisRTL!PuDbgPrint` at `0x180029673`
- `IisRTL!PuDbgPrint` at `0x1800296d1`
- `IisRTL!PuDbgPrint` at `0x180029736`
- `IisRTL!PuDbgPrint` at `0x1800297a2`

## string_xrefs

- `0x180029578`: `IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) with CRYPT_VERIFYCONTEXT failed err=0x%x\n`
- `0x180029653`: `IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) failed err=0x%x.toast.\n`
- `0x18002972a`: `CryptAcquireContext(%p,%p,%p,%d,%d) returned NTE_BAD_KEYSET, so lets create a keyset now...\n`
- `0x180029782`: `IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IcpGetContainerHelper(
        unsigned __int64 *a1,
        const char *a2,
        const char *a3,
        DWORD a4,
        unsigned int dwFlags,
        int a6)
{
  struct _ACL *v11; // rdi
  int LastError; // ebx
  int v13; // eax
  unsigned int v14; // r12d
  __int64 v15; // r8
  int v16; // ebx
  DWORD LengthSid; // ebx
  DWORD v18; // ebx
  struct _ACL *v19; // rax
  HCRYPTPROV phProv; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwProvType; // [rsp+68h] [rbp-98h]
  LPCSTR szContainer; // [rsp+70h] [rbp-90h]
  PSID v23; // [rsp+78h] [rbp-88h] BYREF
  PSID pSid; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 *v25; // [rsp+88h] [rbp-78h]
  _OWORD pSecurityDescriptor[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+B0h] [rbp-50h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp-48h] BYREF
  struct _OSVERSIONINFOA VersionInformation; // [rsp+C0h] [rbp-40h] BYREF

  szContainer = a2;
  v25 = a1;
  dwProvType = a4;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v27 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  if ( !dword_180048964 )
  {
    *a1 = 1984918096;
    return 0;
  }
  phProv = 0;
  pSid = 0;
  v11 = 0;
  v23 = 0;
  EnterCriticalSection(&IcpGlobals);
  if ( !a2 )
  {
    if ( !CryptAcquireContextA(&phProv, 0, a3, a4, 0xF0000000) )
    {
      LastError = IcpGetLastError();
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\contain.cxx",
          569,
          "IcpGetContainerHelper",
          "IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) with CRYPT_VERIFYCONTEXT failed err=0x%x\n",
          LastError);
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\crypto\\contain.cxx",
            570,
            "IcpGetContainerHelper",
            "args for CryptAcquireContext(%p,%p,%p,%d,%d)\n",
            &phProv,
            0,
            a3,
            dwProvType,
            -268435456);
      }
      goto LABEL_41;
    }
LABEL_39:
    *v25 = phProv;
    LastError = 0;
    if ( v11 )
      goto LABEL_40;
LABEL_41:
    if ( v23 )
      FreeSid(v23);
    if ( pSid )
      FreeSid(pSid);
    if ( phProv )
    {
      if ( LastError < 0 )
        CryptReleaseContext(phProv, 0);
    }
    goto LABEL_49;
  }
  if ( !CryptAcquireContextA(&phProv, a2, a3, a4, dwFlags) )
  {
    v13 = IcpGetLastError();
    LastError = v13;
    if ( v13 < 0 )
    {
      if ( v13 == -2146893802 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\crypto\\contain.cxx",
            619,
            "IcpGetContainerHelper",
            "CryptAcquireContext(%p,%p,%p,%d,%d) returned NTE_BAD_KEYSET, so lets create a keyset now...\n",
            &phProv,
            szContainer,
            a3,
            dwProvType,
            dwFlags);
        v14 = dwFlags | 8;
        if ( CryptAcquireContextA(&phProv, szContainer, a3, dwProvType, dwFlags | 8)
          || (LastError = IcpGetLastError(), LastError >= 0) )
        {
          VersionInformation.dwOSVersionInfoSize = 148;
          v16 = 0;
          if ( GetVersionExA(&VersionInformation) )
            LOBYTE(v16) = VersionInformation.dwPlatformId == 2;
          if ( a6 && v16 )
          {
            if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
              || !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid)
              || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v23) )
            {
              LastError = IcpGetLastError();
              goto LABEL_41;
            }
            LengthSid = GetLengthSid(v23);
            v18 = GetLengthSid(pSid) + 28 + LengthSid;
            v19 = (struct _ACL *)CoTaskMemAlloc(v18);
            v11 = v19;
            if ( !v19 )
            {
              LastError = -2147024888;
              goto LABEL_41;
            }
            if ( !InitializeAcl(v19, v18, 2u)
              || !AddAccessAllowedAce(v11, 2u, 0xF003Fu, pSid)
              || !AddAccessAllowedAce(v11, 2u, 0xF003Fu, v23)
              || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v11, 0)
              || !CryptSetProvParam(phProv, 8u, (const BYTE *)pSecurityDescriptor, 4u) )
            {
              LastError = IcpGetLastError();
LABEL_40:
              CoTaskMemFree(v11);
              goto LABEL_41;
            }
          }
          goto LABEL_39;
        }
        if ( (g_dwDebugFlags & 3) == 0
          || (PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\crypto\\contain.cxx",
                642,
                "IcpGetContainerHelper",
                "IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) failed err=0x%x.\n",
                LastError),
              (g_dwDebugFlags & 3) == 0) )
        {
LABEL_15:
          phProv = 0;
          goto LABEL_41;
        }
        v15 = 643;
      }
      else
      {
        if ( (g_dwDebugFlags & 3) == 0 )
          goto LABEL_15;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\contain.cxx",
          611,
          "IcpGetContainerHelper",
          "IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) failed err=0x%x.toast.\n",
          v13);
        if ( (g_dwDebugFlags & 3) == 0 )
          goto LABEL_15;
        v14 = dwFlags | 8;
        v15 = 612;
      }
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\contain.cxx",
        v15,
        "IcpGetContainerHelper",
        "args for CryptAcquireContext(%p,%p,%p,%d,%d)\n",
        &phProv,
        szContainer,
        a3,
        dwProvType,
        v14);
      goto LABEL_15;
    }
  }
  LastError = 0;
  *v25 = phProv;
LABEL_49:
  LeaveCriticalSection(&IcpGlobals);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180029480  push    rbp
0x180029482  push    rbx
0x180029483  push    rsi
0x180029484  push    rdi
0x180029485  push    r12
0x180029487  push    r13
0x180029489  push    r14
0x18002948b  lea     rbp, [rsp-70h]
0x180029490  sub     rsp, 170h
0x180029497  mov     rax, cs:__security_cookie
0x18002949e  xor     rax, rsp
0x1800294a1  mov     [rbp+0A0h+var_40], rax
0x1800294a5  xorps   xmm0, xmm0
0x1800294a8  mov     [rsp+1A0h+szContainer], rdx
0x1800294ad  mov     ebx, r9d
0x1800294b0  mov     [rbp+0A0h+var_118], rcx
0x1800294b4  mov     r13, r8
0x1800294b7  mov     [rsp+1A0h+dwProvType], ebx
0x1800294bb  mov     rsi, rdx
0x1800294be  mov     word ptr [rbp+0A0h+pIdentifierAuthority.Value+4], 500h
0x1800294c4  mov     rdi, rcx
0x1800294c7  xor     eax, eax
0x1800294c9  xor     r14d, r14d
0x1800294cc  mov     [rbp+0A0h+var_F0], rax
0x1800294d0  xor     edx, edx; Val
0x1800294d2  mov     dword ptr [rbp+0A0h+pIdentifierAuthority.Value], r14d
0x1800294d6  mov     r8d, 94h; Size
0x1800294dc  lea     rcx, [rbp+0A0h+VersionInformation]; void *
0x1800294e0  movups  [rbp+0A0h+pSecurityDescriptor], xmm0
0x1800294e4  movups  [rbp+0A0h+var_100], xmm0
0x1800294e8  call    memset_0
0x1800294ed  cmp     cs:dword_180048964, r14d
0x1800294f4  jnz     short loc_180029504
0x1800294f6  mov     qword ptr [rdi], 764F7250h
0x1800294fd  xor     eax, eax
0x1800294ff  jmp     loc_1800299CC
0x180029504  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x18002950b  mov     [rsp+1A0h+phProv], r14
0x180029510  mov     [rbp+0A0h+var_120], r14
0x180029514  mov     rdi, r14
0x180029517  mov     [rsp+1A0h+var_128], r14
0x18002951c  call    cs:__imp_EnterCriticalSection
0x180029522  lea     rcx, [rsp+1A0h+phProv]; phProv
0x180029527  mov     r9d, ebx; dwProvType
0x18002952a  mov     r8, r13; szProvider
0x18002952d  test    rsi, rsi
0x180029530  jnz     loc_1800295FC
0x180029536  mov     r12d, 0F0000000h
0x18002953c  xor     edx, edx; szContainer
0x18002953e  mov     [rsp+1A0h+dwFlags], r12d; dwFlags
0x180029543  call    cs:__imp_CryptAcquireContextA
0x180029549  test    eax, eax
0x18002954b  jnz     loc_18002995A
0x180029551  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180029556  mov     ebx, eax
0x180029558  lea     r14, aIcpgetcontaine_2; "IcpGetContainerHelper"
0x18002955f  mov     eax, cs:g_dwDebugFlags
0x180029565  mov     sil, 3
0x180029568  test    sil, al
0x18002956b  jz      loc_180029977
0x180029571  mov     rcx, cs:g_pDebug
0x180029578  lea     rax, aIcpgetcontaine; "IcpGetContainerHelper. CryptAcquireCont"...
0x18002957f  mov     [rsp+1A0h+nSubAuthority3], ebx
0x180029583  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x18002958a  mov     r9, r14
0x18002958d  mov     qword ptr [rsp+1A0h+dwFlags], rax
0x180029592  mov     r8d, 239h
0x180029598  call    cs:__imp_PuDbgPrint
0x18002959e  mov     eax, cs:g_dwDebugFlags
0x1800295a4  test    sil, al
0x1800295a7  jz      loc_180029977
0x1800295ad  mov     eax, [rsp+1A0h+dwProvType]
0x1800295b1  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x1800295b8  mov     rcx, cs:g_pDebug
0x1800295bf  mov     r9, r14
0x1800295c2  mov     [rsp+1A0h+nSubAuthority7], r12d
0x1800295c7  mov     r8d, 23Ah
0x1800295cd  mov     [rsp+1A0h+nSubAuthority6], eax
0x1800295d1  lea     rax, [rsp+1A0h+phProv]
0x1800295d6  mov     qword ptr [rsp+1A0h+nSubAuthority5], r13
0x1800295db  mov     qword ptr [rsp+1A0h+nSubAuthority4], rdi
0x1800295e0  mov     qword ptr [rsp+1A0h+nSubAuthority3], rax
0x1800295e5  lea     rax, aArgsForCryptac; "args for CryptAcquireContext(%p,%p,%p,%"...
0x1800295ec  mov     qword ptr [rsp+1A0h+dwFlags], rax
0x1800295f1  call    cs:__imp_PuDbgPrint
0x1800295f7  jmp     loc_180029977
0x1800295fc  mov     r12d, [rbp+0A0h+arg_20]
0x180029603  mov     rdx, rsi; szContainer
0x180029606  mov     [rsp+1A0h+dwFlags], r12d; dwFlags
0x18002960b  call    cs:__imp_CryptAcquireContextA
0x180029611  test    eax, eax
0x180029613  jnz     loc_1800299AE
0x180029619  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002961e  mov     ebx, eax
0x180029620  test    eax, eax
0x180029622  jns     loc_1800299AE
0x180029628  lea     r14, aIcpgetcontaine_2; "IcpGetContainerHelper"
0x18002962f  mov     sil, 3
0x180029632  cmp     eax, 80090016h
0x180029637  jz      loc_1800296E4
0x18002963d  mov     eax, cs:g_dwDebugFlags
0x180029643  test    sil, al
0x180029646  jz      loc_1800296D7
0x18002964c  mov     rcx, cs:g_pDebug
0x180029653  lea     rax, aIcpgetcontaine_0; "IcpGetContainerHelper. CryptAcquireCont"...
0x18002965a  mov     [rsp+1A0h+nSubAuthority3], ebx
0x18002965e  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x180029665  mov     r9, r14
0x180029668  mov     qword ptr [rsp+1A0h+dwFlags], rax
0x18002966d  mov     r8d, 263h
0x180029673  call    cs:__imp_PuDbgPrint
0x180029679  mov     eax, cs:g_dwDebugFlags
0x18002967f  test    sil, al
0x180029682  jz      short loc_1800296D7
0x180029684  or      r12d, 8
0x180029688  mov     r8d, 264h
0x18002968e  mov     eax, [rsp+1A0h+dwProvType]
0x180029692  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x180029699  mov     rcx, cs:g_pDebug
0x1800296a0  mov     r9, r14
0x1800296a3  mov     [rsp+1A0h+nSubAuthority7], r12d
0x1800296a8  mov     [rsp+1A0h+nSubAuthority6], eax
0x1800296ac  mov     rax, [rsp+1A0h+szContainer]
0x1800296b1  mov     qword ptr [rsp+1A0h+nSubAuthority5], r13
0x1800296b6  mov     qword ptr [rsp+1A0h+nSubAuthority4], rax
0x1800296bb  lea     rax, [rsp+1A0h+phProv]
0x1800296c0  mov     qword ptr [rsp+1A0h+nSubAuthority3], rax
0x1800296c5  lea     rax, aArgsForCryptac; "args for CryptAcquireContext(%p,%p,%p,%"...
0x1800296cc  mov     qword ptr [rsp+1A0h+dwFlags], rax
0x1800296d1  call    cs:__imp_PuDbgPrint
0x1800296d7  xor     r14d, r14d
0x1800296da  mov     [rsp+1A0h+phProv], r14
0x1800296df  jmp     loc_180029977
0x1800296e4  test    byte ptr cs:g_dwDebugFlags, sil
0x1800296eb  jz      short loc_18002973C
0x1800296ed  mov     eax, [rsp+1A0h+dwProvType]
0x1800296f1  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x1800296f8  mov     rcx, cs:g_pDebug
0x1800296ff  mov     r9, r14
0x180029702  mov     [rsp+1A0h+nSubAuthority7], r12d
0x180029707  mov     r8d, 26Bh
0x18002970d  mov     [rsp+1A0h+nSubAuthority6], eax
0x180029711  mov     rax, [rsp+1A0h+szContainer]
0x180029716  mov     qword ptr [rsp+1A0h+nSubAuthority5], r13
0x18002971b  mov     qword ptr [rsp+1A0h+nSubAuthority4], rax
0x180029720  lea     rax, [rsp+1A0h+phProv]
0x180029725  mov     qword ptr [rsp+1A0h+nSubAuthority3], rax
0x18002972a  lea     rax, aCryptacquireco; "CryptAcquireContext(%p,%p,%p,%d,%d) ret"...
0x180029731  mov     qword ptr [rsp+1A0h+dwFlags], rax
0x180029736  call    cs:__imp_PuDbgPrint
0x18002973c  mov     r9d, [rsp+1A0h+dwProvType]; dwProvType
0x180029741  lea     rcx, [rsp+1A0h+phProv]; phProv
0x180029746  mov     rdx, [rsp+1A0h+szContainer]; szContainer
0x18002974b  or      r12d, 8
0x18002974f  mov     r8, r13; szProvider
0x180029752  mov     [rsp+1A0h+dwFlags], r12d; dwFlags
0x180029757  call    cs:__imp_CryptAcquireContextA
0x18002975d  test    eax, eax
0x18002975f  jnz     short loc_1800297C2
0x180029761  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180029766  mov     ebx, eax
0x180029768  test    eax, eax
0x18002976a  jns     short loc_1800297C2
0x18002976c  mov     eax, cs:g_dwDebugFlags
0x180029772  test    sil, al
0x180029775  jz      loc_1800296D7
0x18002977b  mov     rcx, cs:g_pDebug
0x180029782  lea     rax, aIcpgetcontaine_1; "IcpGetContainerHelper. CryptAcquireCont"...
0x180029789  mov     [rsp+1A0h+nSubAuthority3], ebx
0x18002978d  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x180029794  mov     r9, r14
0x180029797  mov     qword ptr [rsp+1A0h+dwFlags], rax
0x18002979c  mov     r8d, 282h
0x1800297a2  call    cs:__imp_PuDbgPrint
0x1800297a8  mov     eax, cs:g_dwDebugFlags
0x1800297ae  test    sil, al
0x1800297b1  jz      loc_1800296D7
0x1800297b7  mov     r8d, 283h
0x1800297bd  jmp     loc_18002968E
0x1800297c2  xor     r14d, r14d
0x1800297c5  mov     [rbp+0A0h+VersionInformation.dwOSVersionInfoSize], 94h
0x1800297cc  lea     rcx, [rbp+0A0h+VersionInformation]; lpVersionInformation
0x1800297d0  mov     ebx, r14d
0x1800297d3  call    cs:__imp_GetVersionExA
0x1800297d9  lea     esi, [r14+2]
0x1800297dd  test    eax, eax
0x1800297df  jz      short loc_1800297E7
0x1800297e1  cmp     [rbp+0A0h+VersionInformation.dwPlatformId], esi
0x1800297e4  setz    bl
0x1800297e7  cmp     [rbp+0A0h+arg_28], r14d
0x1800297ee  jz      loc_18002995A
0x1800297f4  test    ebx, ebx
0x1800297f6  jz      loc_18002995A
0x1800297fc  mov     edx, 1; dwRevision
0x180029801  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180029805  call    cs:__imp_InitializeSecurityDescriptor
0x18002980b  test    eax, eax
0x18002980d  jnz     short loc_18002981B
0x18002980f  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180029814  mov     ebx, eax
0x180029816  jmp     loc_180029977
0x18002981b  lea     rax, [rbp+0A0h+var_120]
0x18002981f  xor     r9d, r9d; nSubAuthority1
0x180029822  mov     [rsp+1A0h+pSid], rax; pSid
0x180029827  lea     rcx, [rbp+0A0h+pIdentifierAuthority]; pIdentifierAuthority
0x18002982b  mov     [rsp+1A0h+nSubAuthority7], r14d; nSubAuthority7
0x180029830  mov     dl, 1; nSubAuthorityCount
0x180029832  mov     [rsp+1A0h+nSubAuthority6], r14d; nSubAuthority6
0x180029837  mov     [rsp+1A0h+nSubAuthority5], r14d; nSubAuthority5
0x18002983c  lea     r8d, [r9+12h]; nSubAuthority0
0x180029840  mov     [rsp+1A0h+nSubAuthority4], r14d; nSubAuthority4
0x180029845  mov     [rsp+1A0h+nSubAuthority3], r14d; nSubAuthority3
0x18002984a  mov     [rsp+1A0h+dwFlags], r14d; nSubAuthority2
0x18002984f  call    cs:__imp_AllocateAndInitializeSid
0x180029855  test    eax, eax
0x180029857  jz      short loc_18002980F
0x180029859  lea     rax, [rsp+1A0h+var_128]
0x18002985e  mov     r9d, 220h; nSubAuthority1
0x180029864  mov     [rsp+1A0h+pSid], rax; pSid
0x180029869  lea     rcx, [rbp+0A0h+pIdentifierAuthority]; pIdentifierAuthority
0x18002986d  mov     [rsp+1A0h+nSubAuthority7], r14d; nSubAuthority7
0x180029872  mov     r8d, 20h ; ' '; nSubAuthority0
0x180029878  mov     [rsp+1A0h+nSubAuthority6], r14d; nSubAuthority6
0x18002987d  mov     dl, sil; nSubAuthorityCount
0x180029880  mov     [rsp+1A0h+nSubAuthority5], r14d; nSubAuthority5
0x180029885  mov     [rsp+1A0h+nSubAuthority4], r14d; nSubAuthority4
0x18002988a  mov     [rsp+1A0h+nSubAuthority3], r14d; nSubAuthority3
0x18002988f  mov     [rsp+1A0h+dwFlags], r14d; nSubAuthority2
0x180029894  call    cs:__imp_AllocateAndInitializeSid
0x18002989a  test    eax, eax
0x18002989c  jz      loc_18002980F
0x1800298a2  mov     rcx, [rsp+1A0h+var_128]; pSid
0x1800298a7  call    cs:__imp_GetLengthSid
0x1800298ad  mov     rcx, [rbp+0A0h+var_120]; pSid
0x1800298b1  mov     ebx, eax
0x1800298b3  call    cs:__imp_GetLengthSid
0x1800298b9  add     eax, 1Ch
0x1800298bc  add     ebx, eax
0x1800298be  mov     ecx, ebx; cb
0x1800298c0  call    cs:__imp_CoTaskMemAlloc
0x1800298c6  mov     rdi, rax
0x1800298c9  test    rax, rax
0x1800298cc  jnz     short loc_1800298D8
0x1800298ce  mov     ebx, 80070008h
0x1800298d3  jmp     loc_180029977
0x1800298d8  mov     r8d, esi; dwAclRevision
0x1800298db  mov     edx, ebx; nAclLength
0x1800298dd  mov     rcx, rdi; pAcl
0x1800298e0  call    cs:__imp_InitializeAcl
0x1800298e6  test    eax, eax
0x1800298e8  jnz     short loc_1800298F3
0x1800298ea  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x1800298ef  mov     ebx, eax
0x1800298f1  jmp     short loc_18002996E
0x1800298f3  mov     r9, [rbp+0A0h+var_120]; pSid
0x1800298f7  mov     ebx, 0F003Fh
0x1800298fc  mov     r8d, ebx; AccessMask
0x1800298ff  mov     edx, esi; dwAceRevision
0x180029901  mov     rcx, rdi; pAcl
0x180029904  call    cs:__imp_AddAccessAllowedAce
0x18002990a  test    eax, eax
0x18002990c  jz      short loc_1800298EA
0x18002990e  mov     r9, [rsp+1A0h+var_128]; pSid
0x180029913  mov     r8d, ebx; AccessMask
0x180029916  mov     edx, esi; dwAceRevision
0x180029918  mov     rcx, rdi; pAcl
0x18002991b  call    cs:__imp_AddAccessAllowedAce
0x180029921  test    eax, eax
0x180029923  jz      short loc_1800298EA
0x180029925  xor     r9d, r9d; bDaclDefaulted
0x180029928  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18002992c  mov     r8, rdi; pDacl
0x18002992f  lea     edx, [r9+1]; bDaclPresent
0x180029933  call    cs:__imp_SetSecurityDescriptorDacl
0x180029939  test    eax, eax
0x18002993b  jz      short loc_1800298EA
0x18002993d  mov     rcx, [rsp+1A0h+phProv]; hProv
0x180029942  lea     r8, [rbp+0A0h+pSecurityDescriptor]; pbData
0x180029946  mov     r9d, 4; dwFlags
0x18002994c  lea     edx, [r9+4]; dwParam
0x180029950  call    cs:__imp_CryptSetProvParam
0x180029956  test    eax, eax
0x180029958  jz      short loc_1800298EA
0x18002995a  mov     rcx, [rbp+0A0h+var_118]
0x18002995e  mov     rax, [rsp+1A0h+phProv]
0x180029963  mov     [rcx], rax
0x180029966  mov     ebx, r14d
0x180029969  test    rdi, rdi
0x18002996c  jz      short loc_180029977
0x18002996e  mov     rcx, rdi; pv
0x180029971  call    cs:__imp_CoTaskMemFree
0x180029977  mov     rcx, [rsp+1A0h+var_128]; pSid
0x18002997c  test    rcx, rcx
0x18002997f  jz      short loc_180029987
0x180029981  call    cs:__imp_FreeSid
0x180029987  mov     rcx, [rbp+0A0h+var_120]; pSid
0x18002998b  test    rcx, rcx
0x18002998e  jz      short loc_180029996
0x180029990  call    cs:__imp_FreeSid
0x180029996  mov     rcx, [rsp+1A0h+phProv]; hProv
  ... truncated ...
```
