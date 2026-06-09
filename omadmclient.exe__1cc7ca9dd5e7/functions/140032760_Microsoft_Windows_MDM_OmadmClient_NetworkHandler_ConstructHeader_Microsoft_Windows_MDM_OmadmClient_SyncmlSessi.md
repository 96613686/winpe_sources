# Microsoft::Windows::MDM::OmadmClient::NetworkHandler::ConstructHeader(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort const *)

- ea: `0x140032760`
- end: `0x140032cfc`
- name: `?ConstructHeader@NetworkHandler@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@PEBG@Z`
- size: `1436`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::NetworkHandler *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14000b0f4`
- `0x14000e610`
- `0x140013404`
- `0x140032760`
- `0x140033c30`
- `0x140055248`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032b39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032b8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032c71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032b39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032b8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032c71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140032b4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140032b9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140032c85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140032b4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140032b9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140032c85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032c43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032c54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032cb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032c43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032c54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032cb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032cc7`
- `DMCmnUtils!BigStrcat` at `0x1400327f3`
- `DMCmnUtils!BigStrcat` at `0x1400328cf`
- `DMCmnUtils!BigStrcat` at `0x140032a5f`
- `DMCmnUtils!BigStrcat` at `0x140032bc4`
- `DMCmnUtils!BigStrcat` at `0x1400327f3`
- `DMCmnUtils!BigStrcat` at `0x1400328cf`
- `DMCmnUtils!BigStrcat` at `0x140032a5f`
- `DMCmnUtils!BigStrcat` at `0x140032bc4`
- `DMCmnUtils!MBToUnicode` at `0x140032b11`
- `DMCmnUtils!MBToUnicode` at `0x140032b11`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsLockedToMmpc` at `0x1400329ed`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsLockedToMmpc` at `0x1400329ed`

## string_xrefs

- `0x1400328c5`: `DeviceToken: `

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::NetworkHandler::ConstructHeader(
        Microsoft::Windows::MDM::OmadmClient::NetworkHandler *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2,
        const unsigned __int16 *a3)
{
  unsigned __int16 *v6; // rbx
  __int64 v7; // r8
  const unsigned __int16 *v8; // rdx
  int v9; // r14d
  int v10; // eax
  unsigned __int16 *v11; // rdi
  int v12; // eax
  __int64 v13; // r8
  int v14; // eax
  int IsLockedToMmpc; // eax
  __int64 v16; // rdx
  unsigned __int16 *v17; // rsi
  int v18; // eax
  struct COmaDmLogger *Logger; // rax
  void *v20; // r12
  HANDLE ProcessHeap; // rax
  void *v22; // r15
  HANDLE v23; // rax
  unsigned __int16 *v24; // r12
  int v25; // eax
  void *v26; // r14
  HANDLE v27; // rax
  int v29; // [rsp+20h] [rbp-69h]
  LPVOID lpMem; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v31[3]; // [rsp+38h] [rbp-51h] BYREF
  int v32; // [rsp+50h] [rbp-39h]
  int *v33; // [rsp+58h] [rbp-31h]
  int v34; // [rsp+60h] [rbp-29h] BYREF
  int v35; // [rsp+64h] [rbp-25h] BYREF
  unsigned int v36; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int16 *v37; // [rsp+70h] [rbp-19h]
  LPVOID *p_lpMem; // [rsp+78h] [rbp-11h]
  unsigned __int16 *v39; // [rsp+80h] [rbp-9h] BYREF
  char v40; // [rsp+88h] [rbp-1h]
  unsigned __int16 *v41; // [rsp+90h] [rbp+7h]
  unsigned __int16 *v42; // [rsp+98h] [rbp+Fh]
  unsigned __int16 *v43; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int EnrollmentForceAadToken; // [rsp+F8h] [rbp+6Fh] BYREF
  int v46; // [rsp+108h] [rbp+7Fh] BYREF

  EnrollmentForceAadToken = 0;
  v31[0] = 0;
  v31[1] = "ConstructHeader";
  v31[2] = COmaDmLogger::GetLogger();
  v32 = 2;
  v33 = &EnrollmentForceAadToken;
  v6 = 0;
  v37 = 0;
  if ( *((_QWORD *)a2 + 76) )
  {
    v7 = *((_QWORD *)a2 + 76);
    v8 = L"Authorization: Bearer ";
  }
  else
  {
    if ( !*((_QWORD *)a2 + 77) )
      goto LABEL_9;
    v7 = *((_QWORD *)a2 + 77);
    v8 = L"Authorization: Device ";
  }
  v37 = BigStrcat(2u, v8, v7);
  v6 = v37;
  if ( v37 )
  {
    EnrollmentForceAadToken = 0;
    v29 = 0x20000000;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 3) + 64LL))(
            *((_QWORD *)this + 3),
            *((_QWORD *)a2 + 251),
            v37,
            0xFFFFFFFFLL);
    v9 = v10;
    EnrollmentForceAadToken = v10;
    if ( v10 < 0 )
    {
      LODWORD(v31[0]) = 18035;
      HIDWORD(v31[0]) = v10;
      goto LABEL_55;
    }
LABEL_9:
    v11 = 0;
    v41 = 0;
    if ( *((_QWORD *)a2 + 77) )
    {
      v46 = 0;
      EnrollmentForceAadToken = DmGetEnrollmentForceAadToken(*((_QWORD *)a2 + 70), 1, (__int64)&v46);
      if ( EnrollmentForceAadToken >= 0 && (v46 & 1) != 0 )
      {
        v11 = BigStrcat(2u, L"DeviceToken: ", *((_QWORD *)a2 + 77));
        v41 = v11;
        if ( !v11 )
        {
          v9 = -2147024882;
          EnrollmentForceAadToken = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2E1,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
            (const char *)0x8007000ELL,
            v29);
          goto LABEL_54;
        }
        EnrollmentForceAadToken = 0;
        v29 = 0x20000000;
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 3) + 64LL))(
                *((_QWORD *)this + 3),
                *((_QWORD *)a2 + 251),
                v11,
                0xFFFFFFFFLL);
        v9 = v12;
        EnrollmentForceAadToken = v12;
        if ( v12 < 0 )
        {
          LODWORD(v31[0]) = 18081;
          HIDWORD(v31[0]) = v12;
LABEL_53:
          LocalFree(v11);
LABEL_54:
          if ( !v6 )
            goto LABEL_56;
LABEL_55:
          LocalFree(v6);
          goto LABEL_56;
        }
      }
    }
    v13 = *((_QWORD *)a2 + 178);
    if ( v13 )
    {
      v29 = 0x20000000;
      v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 3) + 64LL))(
              *((_QWORD *)this + 3),
              *((_QWORD *)a2 + 251),
              v13,
              0xFFFFFFFFLL);
      v9 = v14;
      EnrollmentForceAadToken = v14;
      if ( v14 < 0 )
      {
        LODWORD(v31[0]) = 18033;
LABEL_19:
        HIDWORD(v31[0]) = v14;
        goto LABEL_52;
      }
    }
    if ( *((_DWORD *)a2 + 132) )
    {
      if ( *((_QWORD *)a2 + 250) )
      {
        v29 = 0x20000000;
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, __int64))(**((_QWORD **)this + 3)
                                                                                           + 64LL))(
                *((_QWORD *)this + 3),
                *((_QWORD *)a2 + 251),
                a3,
                0xFFFFFFFFLL);
        v9 = v14;
        EnrollmentForceAadToken = v14;
        if ( v14 < 0 )
        {
          LODWORD(v31[0]) = 18034;
          goto LABEL_19;
        }
      }
    }
    v34 = 0;
    IsLockedToMmpc = Mmpc_Lockdown_IsLockedToMmpc(&v34);
    v9 = IsLockedToMmpc;
    if ( IsLockedToMmpc < 0 )
    {
      v16 = 771;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
        (const char *)(unsigned int)IsLockedToMmpc,
        v29);
      goto LABEL_52;
    }
    v35 = 0;
    IsLockedToMmpc = Mmpc_IsOnPremiseSupportingDevice(&v35);
    v9 = IsLockedToMmpc;
    if ( IsLockedToMmpc < 0 )
    {
      v16 = 774;
      goto LABEL_26;
    }
    v17 = 0;
    v42 = 0;
    if ( *((_QWORD *)a2 + 82) )
    {
      v17 = BigStrcat(2u, L"client-request-id: ", *((_QWORD *)a2 + 82));
      v42 = v17;
      if ( !v17 )
      {
        v9 = -2147024882;
        EnrollmentForceAadToken = -2147024882;
        v31[0] = 0x8007000E0000469FuLL;
        goto LABEL_52;
      }
      EnrollmentForceAadToken = 0;
      v29 = 0x20000000;
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 3) + 64LL))(
              *((_QWORD *)this + 3),
              *((_QWORD *)a2 + 251),
              v17,
              0xFFFFFFFFLL);
      v9 = v18;
      EnrollmentForceAadToken = v18;
      if ( v18 < 0 )
      {
        LODWORD(v31[0]) = 18077;
        HIDWORD(v31[0]) = v18;
LABEL_51:
        LocalFree(v17);
LABEL_52:
        if ( !v11 )
          goto LABEL_54;
        goto LABEL_53;
      }
    }
    if ( COmaDmLogger::GetLogger() != (struct COmaDmLogger *)-16LL )
    {
      lpMem = 0;
      v36 = 0;
      p_lpMem = &lpMem;
      v39 = 0;
      v40 = 1;
      Logger = COmaDmLogger::GetLogger();
      v9 = MBToUnicode((const char *)Logger + 16, 0xFDE9u, &v39, &v36);
      if ( v40 )
      {
        v20 = *p_lpMem;
        *p_lpMem = v39;
        if ( v20 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v20);
        }
      }
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31E,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
          (const char *)(unsigned int)v9,
          v29);
        v22 = lpMem;
        lpMem = 0;
        goto LABEL_40;
      }
      v43 = 0;
      v24 = BigStrcat(2u, L"MS-CV: ", lpMem);
      v43 = v24;
      if ( !v24 )
      {
        v9 = -2147024882;
        EnrollmentForceAadToken = -2147024882;
        v31[0] = 0x8007000E000046A0uLL;
LABEL_44:
        v22 = lpMem;
        lpMem = 0;
LABEL_40:
        if ( v22 )
        {
          v23 = GetProcessHeap();
          HeapFree(v23, 0, v22);
        }
LABEL_50:
        if ( !v17 )
          goto LABEL_52;
        goto LABEL_51;
      }
      EnrollmentForceAadToken = 0;
      v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64, int))(**((_QWORD **)this + 3) + 64LL))(
              *((_QWORD *)this + 3),
              *((_QWORD *)a2 + 251),
              v24,
              0xFFFFFFFFLL,
              0x20000000);
      v9 = v25;
      EnrollmentForceAadToken = v25;
      if ( v25 < 0 )
      {
        LODWORD(v31[0]) = 18078;
        HIDWORD(v31[0]) = v25;
        LocalFree(v24);
        goto LABEL_44;
      }
      LocalFree(v24);
      v26 = lpMem;
      lpMem = 0;
      if ( v26 )
      {
        v27 = GetProcessHeap();
        HeapFree(v27, 0, v26);
      }
    }
    v9 = EnrollmentForceAadToken;
    goto LABEL_50;
  }
  v9 = -2147024882;
  EnrollmentForceAadToken = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2CA,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
    (const char *)0x8007000ELL,
    v29);
LABEL_56:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v31);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140032760  mov     [rsp-8+arg_0], rbx
0x140032765  push    rbp
0x140032766  push    rsi
0x140032767  push    rdi
0x140032768  push    r12
0x14003276a  push    r13
0x14003276c  push    r14
0x14003276e  push    r15
0x140032770  lea     rbp, [rsp-27h]
0x140032775  sub     rsp, 0B0h
0x14003277c  mov     rsi, r8
0x14003277f  mov     r15, rdx
0x140032782  mov     r13, rcx
0x140032785  xor     r12d, r12d
0x140032788  mov     [rbp+57h+arg_8], r12d
0x14003278c  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140032791  mov     [rbp+57h+var_A8], r12
0x140032795  lea     rcx, aConstructheade; "ConstructHeader"
0x14003279c  mov     [rbp+57h+var_A0], rcx
0x1400327a0  mov     [rbp+57h+var_98], rax
0x1400327a4  lea     r14d, [r12+2]
0x1400327a9  mov     [rbp+57h+var_90], r14d
0x1400327ad  lea     rax, [rbp+57h+arg_8]
0x1400327b1  mov     [rbp+57h+var_88], rax
0x1400327b5  mov     ebx, r12d
0x1400327b8  mov     [rbp+57h+var_70], rbx
0x1400327bc  cmp     [r15+260h], r12
0x1400327c3  jz      short loc_1400327D5
0x1400327c5  mov     r8, [r15+260h]
0x1400327cc  lea     rdx, ?gc_szAuthorizationUserHeaders@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "Authorization: Bearer "
0x1400327d3  jmp     short loc_1400327F0
0x1400327d5  cmp     [r15+268h], r12
0x1400327dc  jz      loc_14003287C
0x1400327e2  mov     r8, [r15+268h]
0x1400327e9  lea     rdx, ?gc_szAuthorizationDeviceHeaders@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "Authorization: Device "
0x1400327f0  mov     ecx, r14d
0x1400327f3  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x1400327fa  nop     dword ptr [rax+rax+00h]
0x1400327ff  mov     [rbp+57h+var_70], rax
0x140032803  mov     rbx, rax
0x140032806  test    rax, rax
0x140032809  jnz     short loc_140032833
0x14003280b  mov     r14d, 8007000Eh
0x140032811  mov     [rbp+57h+arg_8], r14d
0x140032815  mov     rcx, [rbp+5Fh]; this
0x140032819  mov     r9d, r14d; char *
0x14003281c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140032823  mov     edx, 2CAh; void *
0x140032828  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003282d  nop
0x14003282e  jmp     loc_140032CD4
0x140032833  mov     [rbp+57h+arg_8], r12d
0x140032837  mov     rcx, [r13+18h]
0x14003283b  mov     rax, [rcx]
0x14003283e  mov     [rsp+0E0h+var_C0], 20000000h; int
0x140032846  or      r9d, 0FFFFFFFFh
0x14003284a  mov     r8, rbx
0x14003284d  mov     rdx, [r15+7D8h]
0x140032854  mov     rax, [rax+40h]
0x140032858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003285d  mov     r14d, eax
0x140032860  mov     [rbp+57h+arg_8], eax
0x140032863  test    eax, eax
0x140032865  jns     short loc_140032876
0x140032867  mov     dword ptr [rbp+57h+var_A8], 4673h
0x14003286e  mov     dword ptr [rbp+57h+var_A8+4], eax
0x140032871  jmp     loc_140032CC4
0x140032876  mov     r14d, 2
0x14003287c  mov     rdi, r12
0x14003287f  mov     [rbp+57h+var_50], r12
0x140032883  cmp     [r15+268h], r12
0x14003288a  jz      loc_140032952
0x140032890  mov     [rbp+57h+arg_18], r12d
0x140032894  lea     r8, [rbp+57h+arg_18]
0x140032898  mov     edx, 1
0x14003289d  mov     rcx, [r15+230h]
0x1400328a4  call    ?DmGetEnrollmentForceAadToken@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAK@Z; DmGetEnrollmentForceAadToken(ushort const *,tagDMACCOUNTLOOKUPTYPE,ulong *)
0x1400328a9  mov     [rbp+57h+arg_8], eax
0x1400328ac  test    eax, eax
0x1400328ae  js      loc_140032952
0x1400328b4  test    byte ptr [rbp+57h+arg_18], 1
0x1400328b8  jz      loc_140032952
0x1400328be  mov     r8, [r15+268h]
0x1400328c5  lea     rdx, ?gc_szExtraDeviceTokenHeaders@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "DeviceToken: "
0x1400328cc  mov     ecx, r14d
0x1400328cf  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x1400328d6  nop     dword ptr [rax+rax+00h]
0x1400328db  mov     rdi, rax
0x1400328de  mov     [rbp+57h+var_50], rax
0x1400328e2  test    rax, rax
0x1400328e5  jnz     short loc_14003290F
0x1400328e7  mov     r14d, 8007000Eh
0x1400328ed  mov     [rbp+57h+arg_8], r14d
0x1400328f1  mov     rcx, [rbp+5Fh]; this
0x1400328f5  mov     r9d, r14d; char *
0x1400328f8  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400328ff  mov     edx, 2E1h; void *
0x140032904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140032909  nop
0x14003290a  jmp     loc_140032CBF
0x14003290f  mov     [rbp+57h+arg_8], r12d
0x140032913  mov     rcx, [r13+18h]
0x140032917  mov     rax, [rcx]
0x14003291a  mov     [rsp+0E0h+var_C0], 20000000h
0x140032922  or      r9d, 0FFFFFFFFh
0x140032926  mov     r8, rdi
0x140032929  mov     rdx, [r15+7D8h]
0x140032930  mov     rax, [rax+40h]
0x140032934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032939  mov     r14d, eax
0x14003293c  mov     [rbp+57h+arg_8], eax
0x14003293f  test    eax, eax
0x140032941  jns     short loc_140032952
0x140032943  mov     dword ptr [rbp+57h+var_A8], 46A1h
0x14003294a  mov     dword ptr [rbp+57h+var_A8+4], eax
0x14003294d  jmp     loc_140032CAF
0x140032952  mov     r8, [r15+590h]
0x140032959  test    r8, r8
0x14003295c  jz      short loc_14003299A
0x14003295e  mov     rcx, [r13+18h]
0x140032962  mov     rax, [rcx]
0x140032965  mov     [rsp+0E0h+var_C0], 20000000h
0x14003296d  or      r9d, 0FFFFFFFFh
0x140032971  mov     rdx, [r15+7D8h]
0x140032978  mov     rax, [rax+40h]
0x14003297c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032981  mov     r14d, eax
0x140032984  mov     [rbp+57h+arg_8], eax
0x140032987  test    eax, eax
0x140032989  jns     short loc_14003299A
0x14003298b  mov     dword ptr [rbp+57h+var_A8], 4671h
0x140032992  mov     dword ptr [rbp+57h+var_A8+4], eax
0x140032995  jmp     loc_140032CAA
0x14003299a  cmp     [r15+210h], r12d
0x1400329a1  jz      short loc_1400329E5
0x1400329a3  cmp     [r15+7D0h], r12
0x1400329aa  jz      short loc_1400329E5
0x1400329ac  mov     rcx, [r13+18h]
0x1400329b0  mov     rax, [rcx]
0x1400329b3  mov     [rsp+0E0h+var_C0], 20000000h
0x1400329bb  or      r9d, 0FFFFFFFFh
0x1400329bf  mov     r8, rsi
0x1400329c2  mov     rdx, [r15+7D8h]
0x1400329c9  mov     rax, [rax+40h]
0x1400329cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400329d2  mov     r14d, eax
0x1400329d5  mov     [rbp+57h+arg_8], eax
0x1400329d8  test    eax, eax
0x1400329da  jns     short loc_1400329E5
0x1400329dc  mov     dword ptr [rbp+57h+var_A8], 4672h
0x1400329e3  jmp     short loc_140032992
0x1400329e5  mov     [rbp+57h+var_80], r12d
0x1400329e9  lea     rcx, [rbp+57h+var_80]
0x1400329ed  call    cs:__imp_Mmpc_Lockdown_IsLockedToMmpc
0x1400329f4  nop     dword ptr [rax+rax+00h]
0x1400329f9  mov     r14d, eax
0x1400329fc  test    eax, eax
0x1400329fe  jns     short loc_140032A1D
0x140032a00  mov     edx, 303h; void *
0x140032a05  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140032a0c  mov     r9d, eax; char *
0x140032a0f  mov     rcx, [rbp+5Fh]; this
0x140032a13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140032a18  jmp     loc_140032CAA
0x140032a1d  mov     [rbp+57h+var_7C], r12d
0x140032a21  lea     rcx, [rbp+57h+var_7C]; int *
0x140032a25  call    ?Mmpc_IsOnPremiseSupportingDevice@@YAJPEAH@Z; Mmpc_IsOnPremiseSupportingDevice(int *)
0x140032a2a  mov     r14d, eax
0x140032a2d  test    eax, eax
0x140032a2f  jns     short loc_140032A38
0x140032a31  mov     edx, 306h
0x140032a36  jmp     short loc_140032A05
0x140032a38  mov     rsi, r12
0x140032a3b  mov     [rbp+57h+var_48], r12
0x140032a3f  cmp     [r15+290h], r12
0x140032a46  jz      loc_140032AD4
0x140032a4c  mov     r8, [r15+290h]
0x140032a53  lea     rdx, ?gc_szClientRequestIdHeaders@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "client-request-id: "
0x140032a5a  mov     ecx, 2
0x140032a5f  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x140032a66  nop     dword ptr [rax+rax+00h]
0x140032a6b  mov     rsi, rax
0x140032a6e  mov     [rbp+57h+var_48], rax
0x140032a72  test    rax, rax
0x140032a75  jnz     short loc_140032A91
0x140032a77  mov     r14d, 8007000Eh
0x140032a7d  mov     [rbp+57h+arg_8], r14d
0x140032a81  mov     dword ptr [rbp+57h+var_A8], 469Fh
0x140032a88  mov     dword ptr [rbp+57h+var_A8+4], r14d
0x140032a8c  jmp     loc_140032CAA
0x140032a91  mov     [rbp+57h+arg_8], r12d
0x140032a95  mov     rcx, [r13+18h]
0x140032a99  mov     rax, [rcx]
0x140032a9c  mov     [rsp+0E0h+var_C0], 20000000h
0x140032aa4  or      r9d, 0FFFFFFFFh
0x140032aa8  mov     r8, rsi
0x140032aab  mov     rdx, [r15+7D8h]
0x140032ab2  mov     rax, [rax+40h]
0x140032ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032abb  mov     r14d, eax
0x140032abe  mov     [rbp+57h+arg_8], eax
0x140032ac1  test    eax, eax
0x140032ac3  jns     short loc_140032AD4
0x140032ac5  mov     dword ptr [rbp+57h+var_A8], 469Dh
0x140032acc  mov     dword ptr [rbp+57h+var_A8+4], eax
0x140032acf  jmp     loc_140032C9A
0x140032ad4  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140032ad9  add     rax, 10h
0x140032add  jz      loc_140032C91
0x140032ae3  mov     [rbp+57h+lpMem], r12
0x140032ae7  mov     [rbp+57h+var_78], r12d
0x140032aeb  lea     rax, [rbp+57h+lpMem]
0x140032aef  mov     [rbp+57h+var_68], rax
0x140032af3  mov     [rbp+57h+var_60], r12
0x140032af7  mov     [rbp+57h+var_58], 1
0x140032afb  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140032b00  lea     rcx, [rax+10h]
0x140032b04  lea     r9, [rbp+57h+var_78]
0x140032b08  lea     r8, [rbp+57h+var_60]
0x140032b0c  mov     edx, 0FDE9h
0x140032b11  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x140032b18  nop     dword ptr [rax+rax+00h]
0x140032b1d  mov     r14d, eax
0x140032b20  cmp     [rbp+57h+var_58], r12b
0x140032b24  jz      short loc_140032B5C
0x140032b26  mov     rcx, [rbp+57h+var_68]
0x140032b2a  mov     r12, [rcx]
0x140032b2d  mov     rax, [rbp+57h+var_60]
0x140032b31  mov     [rcx], rax
0x140032b34  test    r12, r12
0x140032b37  jz      short loc_140032B59
0x140032b39  call    cs:__imp_GetProcessHeap
0x140032b40  nop     dword ptr [rax+rax+00h]
0x140032b45  mov     rcx, rax; hHeap
0x140032b48  mov     r8, r12; lpMem
0x140032b4b  xor     edx, edx; dwFlags
0x140032b4d  call    cs:__imp_HeapFree
0x140032b54  nop     dword ptr [rax+rax+00h]
0x140032b59  xor     r12d, r12d
0x140032b5c  test    r14d, r14d
0x140032b5f  jns     short loc_140032BB0
0x140032b61  mov     rcx, [rbp+5Fh]; this
0x140032b65  mov     r9d, r14d; char *
0x140032b68  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140032b6f  mov     edx, 31Eh; void *
0x140032b74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140032b79  nop
0x140032b7a  mov     r15, [rbp+57h+lpMem]
0x140032b7e  mov     [rbp+57h+lpMem], r12
0x140032b82  test    r15, r15
0x140032b85  jz      loc_140032C95
0x140032b8b  call    cs:__imp_GetProcessHeap
0x140032b92  nop     dword ptr [rax+rax+00h]
0x140032b97  mov     rcx, rax; hHeap
0x140032b9a  mov     r8, r15; lpMem
0x140032b9d  xor     edx, edx; dwFlags
0x140032b9f  call    cs:__imp_HeapFree
0x140032ba6  nop     dword ptr [rax+rax+00h]
0x140032bab  jmp     loc_140032C95
0x140032bb0  mov     [rbp+57h+var_40], r12
0x140032bb4  mov     r8, [rbp+57h+lpMem]
0x140032bb8  lea     rdx, ?gc_szCorrelationIdHeaders@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "MS-CV: "
0x140032bbf  mov     ecx, 2
0x140032bc4  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x140032bcb  nop     dword ptr [rax+rax+00h]
0x140032bd0  mov     r12, rax
0x140032bd3  mov     [rbp+57h+var_40], rax
0x140032bd7  test    rax, rax
0x140032bda  jnz     short loc_140032BFF
0x140032bdc  mov     r14d, 8007000Eh
0x140032be2  mov     [rbp+57h+arg_8], r14d
0x140032be6  mov     dword ptr [rbp+57h+var_A8], 46A0h
0x140032bed  mov     dword ptr [rbp+57h+var_A8+4], r14d
0x140032bf1  mov     r15, [rbp+57h+lpMem]
0x140032bf5  mov     [rbp+57h+lpMem], 0
0x140032bfd  jmp     short loc_140032B82
0x140032bff  mov     [rbp+57h+arg_8], 0
0x140032c06  mov     rcx, [r13+18h]
0x140032c0a  mov     rax, [rcx]
0x140032c0d  mov     [rsp+0E0h+var_C0], 20000000h
0x140032c15  or      r9d, 0FFFFFFFFh
0x140032c19  mov     r8, r12
0x140032c1c  mov     rdx, [r15+7D8h]
0x140032c23  mov     rax, [rax+40h]
0x140032c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032c2c  mov     r14d, eax
0x140032c2f  mov     [rbp+57h+arg_8], eax
0x140032c32  test    eax, eax
0x140032c34  jns     short loc_140032C51
0x140032c36  mov     dword ptr [rbp+57h+var_A8], 469Eh
0x140032c3d  mov     dword ptr [rbp+57h+var_A8+4], eax
0x140032c40  mov     rcx, r12; hMem
0x140032c43  call    cs:__imp_LocalFree
0x140032c4a  nop     dword ptr [rax+rax+00h]
0x140032c4f  jmp     short loc_140032BF1
0x140032c51  mov     rcx, r12; hMem
0x140032c54  call    cs:__imp_LocalFree
0x140032c5b  nop     dword ptr [rax+rax+00h]
0x140032c60  nop
0x140032c61  mov     r14, [rbp+57h+lpMem]
  ... truncated ...
```
