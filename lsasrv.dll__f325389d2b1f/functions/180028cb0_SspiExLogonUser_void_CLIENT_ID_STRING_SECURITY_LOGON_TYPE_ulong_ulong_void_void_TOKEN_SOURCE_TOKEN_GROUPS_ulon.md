# SspiExLogonUser(void *,_CLIENT_ID *,_STRING *,_SECURITY_LOGON_TYPE,ulong,ulong,void *,void *,_TOKEN_SOURCE *,_TOKEN_GROUPS *,ulong,uchar *,long *,void * *,ulong *,_LUID *,void * *,_QUOTA_LIMITS *)

- ea: `0x180028cb0`
- end: `0x1800293b1`
- name: `?SspiExLogonUser@@YAJPEAXPEAU_CLIENT_ID@@PEAU_STRING@@W4_SECURITY_LOGON_TYPE@@KK00PEAU_TOKEN_SOURCE@@PEAU_TOKEN_GROUPS@@KPEAEPEAJPEAPEAXPEAKPEAU_LUID@@8PEAU_QUOTA_LIMITS@@@Z`
- size: `1793`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct _CLIENT_ID *@<rdx>, struct _STRING *@<r8>, enum _SECURITY_LOGON_TYPE@<r9d>, unsigned int, unsigned int, void *, void *, struct _TOKEN_SOURCE *, struct _TOKEN_GROUPS *, unsigned int, unsigned __int8 *, int *, void **, unsigned int *, struct _LUID *, void **, struct _QUOTA_LIMITS *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009690`
- `0x18000c324`
- `0x180011278`
- `0x1800283d4`
- `0x180028cb0`
- `0x1800293c0`
- `0x18002abd0`
- `0x18002b390`
- `0x180056fec`
- `0x18005e058`
- `0x180082b20`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800de1e4`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x180029094`
- `ntdll!RtlSubAuthoritySid` at `0x180029094`
- `ntdll!RtlValidSid` at `0x18002904e`
- `ntdll!RtlValidSid` at `0x18002904e`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18002906e`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18002906e`
- `ntdll!RtlEqualUnicodeString` at `0x1800292df`
- `ntdll!RtlEqualUnicodeString` at `0x1800292f9`
- `ntdll!RtlEqualUnicodeString` at `0x1800292df`
- `ntdll!RtlEqualUnicodeString` at `0x1800292f9`
- `ntdll!RtlInitUnicodeString` at `0x18002929d`
- `ntdll!RtlInitUnicodeString` at `0x1800292b4`
- `ntdll!RtlInitUnicodeString` at `0x18002929d`
- `ntdll!RtlInitUnicodeString` at `0x1800292b4`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800293a0`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800293a0`

## pseudocode

```c
__int64 __fastcall SspiExLogonUser(
        void *a1,
        struct _CLIENT_ID *a2,
        struct _STRING *a3,
        enum _SECURITY_LOGON_TYPE a4,
        unsigned int a5,
        unsigned int a6,
        void *a7,
        char *a8,
        struct _TOKEN_SOURCE *a9,
        struct _TOKEN_GROUPS *a10,
        unsigned int a11,
        unsigned __int8 *a12,
        int *a13,
        void **a14,
        unsigned int *a15,
        struct _LUID *a16,
        void **a17,
        struct _QUOTA_LIMITS *a18)
{
  char *v19; // r14
  int v21; // ebx
  unsigned int v22; // r12d
  int v23; // eax
  unsigned int v24; // ebx
  unsigned int v25; // ecx
  char v26; // si
  LsaHandleCache *v27; // r10
  struct _LUID *v28; // r14
  struct _LUID v29; // rdx
  int v30; // eax
  void **v31; // rcx
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  struct _QUOTA_LIMITS *v34; // rcx
  SIZE_T PagedPoolLimit; // rax
  void *v36; // rax
  char v38; // di
  DWORD i; // esi
  PSID Sid; // rbx
  PSID_IDENTIFIER_AUTHORITY v41; // rax
  int v42; // edx
  unsigned int *v43; // rax
  unsigned int v44; // edx
  ULONG v45; // eax
  LsaHandleCache *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // r9
  const UNICODE_STRING *Package; // rax
  const UNICODE_STRING *v50; // r12
  unsigned __int8 v51[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v52; // [rsp+54h] [rbp-ACh]
  unsigned __int16 v53; // [rsp+58h] [rbp-A8h]
  unsigned int v54; // [rsp+5Ch] [rbp-A4h] BYREF
  enum _SECURITY_LOGON_TYPE v55; // [rsp+60h] [rbp-A0h]
  int v56; // [rsp+64h] [rbp-9Ch] BYREF
  void *v57; // [rsp+68h] [rbp-98h]
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData; // [rsp+70h] [rbp-90h] BYREF
  struct _LUID v59; // [rsp+78h] [rbp-88h] BYREF
  struct _LUID *v60; // [rsp+80h] [rbp-80h]
  struct _STRING *v61; // [rsp+88h] [rbp-78h]
  struct _CLIENT_ID *v62; // [rsp+90h] [rbp-70h]
  void **v63; // [rsp+98h] [rbp-68h]
  unsigned int *v64; // [rsp+A0h] [rbp-60h]
  struct _QUOTA_LIMITS *v65; // [rsp+A8h] [rbp-58h]
  void **v66; // [rsp+B0h] [rbp-50h]
  int *v67; // [rsp+B8h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  UNICODE_STRING String2; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v70; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v71; // [rsp+F0h] [rbp-10h] BYREF
  char v72[46]; // [rsp+F2h] [rbp-Eh] BYREF
  struct _STRING v73; // [rsp+120h] [rbp+20h] BYREF
  enum _SECURITY_LOGON_TYPE v74; // [rsp+130h] [rbp+30h]
  unsigned int v75; // [rsp+134h] [rbp+34h]
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE v76; // [rsp+138h] [rbp+38h]
  unsigned int v77; // [rsp+140h] [rbp+40h]
  DWORD GroupCount; // [rsp+144h] [rbp+44h]
  struct _TOKEN_GROUPS *v79; // [rsp+148h] [rbp+48h]
  __int128 v80; // [rsp+150h] [rbp+50h]
  int v81; // [rsp+160h] [rbp+60h]
  void *v82; // [rsp+168h] [rbp+68h]
  unsigned int v83; // [rsp+170h] [rbp+70h]
  struct _LUID v84; // [rsp+178h] [rbp+78h]
  void *v85; // [rsp+180h] [rbp+80h]
  struct _QUOTA_LIMITS v86; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v87; // [rsp+1D8h] [rbp+D8h]
  _BYTE lpTlsValue[24]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned int v89; // [rsp+1F8h] [rbp+F8h]
  unsigned int v90; // [rsp+200h] [rbp+100h]
  unsigned int v91; // [rsp+224h] [rbp+124h]

  v19 = a8;
  v57 = a7;
  v67 = a13;
  v63 = a14;
  v64 = a15;
  v60 = a16;
  v66 = a17;
  v61 = a3;
  v62 = a2;
  v65 = a18;
  v55 = a4;
  memset_0(lpTlsValue, 0, 0x1E8u);
  v53 = 1280;
  v51[0] = 0;
  v52 = 0;
  v71 = 0;
  v70 = 0;
  memset_0(v72, 0, 0xEEu);
  v56 = 0;
  AuthData = 0;
  v54 = 0;
  v59 = 0;
  SpmpEventWrite(&SSPIEX_LOGON_USER_START, 0);
  v21 = SspipBuildCallInfo(a1, a2, 0, 0, 0, 0, a12, 0, (struct _LSA_CALL_INFO *)lpTlsValue);
  if ( v21 < 0 )
    goto LABEL_19;
  v22 = a11;
  v91 = a11;
  v23 = LsapCheckCallerSuppliedCallFlags((struct _LSA_CALL_INFO *)lpTlsValue);
  v21 = v23;
  if ( v23 < 0 )
  {
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v47 = 19;
LABEL_56:
    v48 = (unsigned int)v23;
LABEL_50:
    WPP_SF_d(*((_QWORD *)v46 + 2), v47, WPP_70ad1dbafaf332f23371a09dd7075615_Traceguids, v48);
    goto LABEL_19;
  }
  if ( a10 )
  {
    if ( (v90 & 0x200) == 0 )
    {
      v21 = -1073741790;
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v47 = 20;
      goto LABEL_57;
    }
    v38 = 0;
    for ( i = 0; i < a10->GroupCount; ++i )
    {
      Sid = a10->Groups[i].Sid;
      if ( !RtlValidSid(Sid) )
      {
        v21 = -1073741704;
        v46 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v47 = 21;
          v48 = i;
          goto LABEL_50;
        }
        goto LABEL_19;
      }
      if ( !v38 )
      {
        v41 = RtlIdentifierAuthoritySid(Sid);
        v42 = *(_DWORD *)v41->Value - v52;
        if ( *(_DWORD *)v41->Value == v52 )
          v42 = *(unsigned __int16 *)&v41->Value[4] - v53;
        if ( !v42 )
        {
          v43 = RtlSubAuthoritySid(Sid, 0);
          v23 = LsapCheckVirtualAccountRestriction(*v43, v89);
          v21 = v23;
          if ( v23 < 0 )
          {
            v46 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v47 = 22;
              goto LABEL_56;
            }
            goto LABEL_19;
          }
          v38 = 1;
        }
      }
    }
  }
  v24 = a6;
  v25 = v90;
  if ( a6 < 0x18 || *(_DWORD *)a8 != 32769 )
    goto LABEL_6;
  v44 = *((_DWORD *)a8 + 2);
  if ( v44 >= 0xFFFFFFE8 )
  {
    v21 = -1073741675;
    goto LABEL_19;
  }
  if ( a6 < v44 + 24 )
  {
LABEL_6:
    v26 = 0;
    goto LABEL_7;
  }
  v56 = *((_DWORD *)a8 + 1);
  if ( (v90 & 0x200) == 0 )
  {
    v21 = -1073741790;
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v47 = 23;
LABEL_57:
    v48 = 3221225506LL;
    goto LABEL_50;
  }
  v26 = 1;
  v57 = (void *)*((_QWORD *)a8 + 2);
  v19 = a8 + 24;
  v24 = v44;
LABEL_7:
  if ( a5 != NegPackageId )
  {
    DestinationString = 0;
    String2 = 0;
    RtlInitUnicodeString(&DestinationString, L"NTLM");
    RtlInitUnicodeString(&String2, L"MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
    Package = (const UNICODE_STRING *)SpmpLocatePackage(a5);
    if ( !Package )
      goto LABEL_10;
    v50 = Package + 3;
    if ( !RtlEqualUnicodeString(Package + 3, &DestinationString, 1u) && !RtlEqualUnicodeString(v50, &String2, 1u) )
    {
      v22 = a11;
      goto LABEL_10;
    }
    v25 = v90;
    v22 = a11;
  }
  if ( (int)LsapConvertLogonAuthInfo((v25 >> 6) & 1, v55, v19, v24, v57, &AuthData, &v54, &v59, v51) >= 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_70ad1dbafaf332f23371a09dd7075615_Traceguids);
      v27 = WPP_GLOBAL_Control;
    }
    v45 = NegPackageId;
    if ( a5 != NegPackageId && v27 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v27 + 2), 25, WPP_70ad1dbafaf332f23371a09dd7075615_Traceguids, a5);
      v27 = WPP_GLOBAL_Control;
      v45 = NegPackageId;
    }
    v29 = v59;
    v28 = v60;
    v75 = v45;
    v76 = AuthData;
    v77 = v54;
    goto LABEL_11;
  }
  v51[0] = 0;
LABEL_10:
  v27 = WPP_GLOBAL_Control;
  v76 = v19;
  v28 = v60;
  v75 = a5;
  v77 = v24;
  v29 = *v60;
LABEL_11:
  v84 = v29;
  v87 = v22;
  v79 = a10;
  if ( a10 )
    GroupCount = a10->GroupCount;
  v74 = v55;
  v80 = (__int128)*a9;
  if ( v61 )
    v73 = *v61;
  *(_QWORD *)&v70 = &v71;
  if ( v27 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v27 + 7) & 0x400) != 0 )
    WPP_SF_aZqddDDD(
      *((_QWORD *)v27 + 2),
      v29.LowPart,
      v55,
      (unsigned int)&v73,
      (char)v62->UniqueProcess,
      a5,
      v55,
      v22,
      v29.HighPart,
      v29.LowPart);
  v30 = LsapAuApiDispatchLogonUser(
          (void **)&v70,
          v57,
          &v86,
          v51[0],
          (PULONG)((unsigned __int64)&v56 & -(__int64)(v26 != 0)));
  v31 = v63;
  v21 = v30;
  v32 = *(_OWORD *)&v86.NonPagedPoolLimit;
  v33 = *(_OWORD *)&v86.MaximumWorkingSetSize;
  *v28 = v84;
  *v31 = v82;
  *v64 = v83;
  v34 = v65;
  PagedPoolLimit = v86.PagedPoolLimit;
  *(_OWORD *)&v65->NonPagedPoolLimit = v32;
  v34->PagedPoolLimit = PagedPoolLimit;
  v36 = v85;
  *(_QWORD *)&v32 = v86.TimeLimit.QuadPart;
  *(_OWORD *)&v34->MaximumWorkingSetSize = v33;
  v34->TimeLimit.QuadPart = v32;
  *v66 = v36;
  *v67 = v81;
LABEL_19:
  SspipCleanupCallInfo((struct _LSA_CALL_INFO *)lpTlsValue);
  if ( v79 && v79 != a10 )
    LsapFreeTokenGroups(v79);
  if ( AuthData )
    SspiFreeAuthIdentity(AuthData);
  SpmpEventWrite(&SSPIEX_LOGON_USER_STOP, 0);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180028cb0  mov     [rsp-8+arg_10], rbx
0x180028cb5  push    rbp
0x180028cb6  push    rsi
0x180028cb7  push    rdi
0x180028cb8  push    r12
0x180028cba  push    r13
0x180028cbc  push    r14
0x180028cbe  push    r15
0x180028cc0  lea     rbp, [rsp-2E0h]
0x180028cc8  sub     rsp, 3E0h
0x180028ccf  mov     rax, cs:__security_cookie
0x180028cd6  xor     rax, rsp
0x180028cd9  mov     [rbp+310h+var_40], rax
0x180028ce0  mov     rax, [rbp+310h+arg_30]
0x180028ce7  mov     rsi, rdx
0x180028cea  mov     r14, [rbp+310h+arg_38]
0x180028cf1  mov     rdi, rcx
0x180028cf4  mov     r15, [rbp+310h+arg_48]
0x180028cfb  lea     rcx, [rbp+310h+var_230]; void *
0x180028d02  mov     r13d, [rbp+310h+arg_20]
0x180028d09  mov     rbx, [rbp+310h+arg_58]
0x180028d10  mov     [rsp+410h+var_3A8], rax
0x180028d15  mov     rax, [rbp+310h+arg_60]
0x180028d1c  mov     [rbp+310h+var_358], rax
0x180028d20  mov     rax, [rbp+310h+arg_68]
0x180028d27  mov     [rbp+310h+var_378], rax
0x180028d2b  mov     rax, [rbp+310h+arg_70]
0x180028d32  mov     [rbp+310h+var_370], rax
0x180028d36  mov     rax, [rbp+310h+arg_78]
0x180028d3d  mov     [rbp+310h+var_390], rax
0x180028d41  mov     rax, [rbp+310h+arg_80]
0x180028d48  mov     [rbp+310h+var_360], rax
0x180028d4c  mov     rax, [rbp+310h+arg_88]
0x180028d53  mov     [rbp+310h+var_388], r8
0x180028d57  mov     r8d, 1E8h; Size
0x180028d5d  mov     [rbp+310h+var_380], rdx
0x180028d61  xor     edx, edx; Val
0x180028d63  mov     [rbp+310h+var_368], rax
0x180028d67  mov     [rsp+410h+var_3B0], r9d
0x180028d6c  call    memset_0
0x180028d71  xor     eax, eax
0x180028d73  mov     [rsp+410h+var_3B8], 500h
0x180028d7a  xorps   xmm0, xmm0
0x180028d7d  mov     [rsp+410h+var_3C0], al
0x180028d81  xor     edx, edx; Val
0x180028d83  mov     [rsp+410h+var_3BC], eax
0x180028d87  mov     r8d, 0EEh; Size
0x180028d8d  mov     [rbp+310h+var_320], ax
0x180028d91  lea     rcx, [rbp+310h+var_31E]; void *
0x180028d95  movups  [rbp+310h+var_330], xmm0
0x180028d99  call    memset_0
0x180028d9e  xor     eax, eax
0x180028da0  lea     rcx, SSPIEX_LOGON_USER_START; struct _EVENT_DESCRIPTOR *
0x180028da7  xor     edx, edx; unsigned __int16 *
0x180028da9  mov     [rsp+410h+var_3AC], eax
0x180028dad  mov     [rsp+410h+AuthData], rax
0x180028db2  mov     [rsp+410h+var_3B4], eax
0x180028db6  mov     qword ptr [rsp+410h+var_398.LowPart], rax
0x180028dbb  call    ?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180028dc0  lea     rax, [rbp+310h+var_230]
0x180028dc7  xor     r9d, r9d; unsigned int
0x180028dca  mov     [rsp+410h+lpTlsValue], rax; lpTlsValue
0x180028dcf  xor     r8d, r8d; unsigned int *
0x180028dd2  xor     eax, eax
0x180028dd4  mov     rdx, rsi; struct _CLIENT_ID *
0x180028dd7  mov     [rsp+410h+var_3D8], rax; struct _UNICODE_STRING *
0x180028ddc  mov     rcx, rdi; void *
0x180028ddf  mov     [rsp+410h+var_3E0], rbx; void *
0x180028de4  mov     [rsp+410h+String1], rax; String1
0x180028de9  mov     [rsp+410h+var_3F0], rax; struct _SecHandle *
0x180028dee  call    ?SspipBuildCallInfo@@YAJPEAXPEAU_CLIENT_ID@@PEAKKPEAU_SecHandle@@PEAU_UNICODE_STRING@@04PEAU_LSA_CALL_INFO@@@Z; SspipBuildCallInfo(void *,_CLIENT_ID *,ulong *,ulong,_SecHandle *,_UNICODE_STRING *,void *,_UNICODE_STRING *,_LSA_CALL_INFO *)
0x180028df3  mov     ebx, eax
0x180028df5  test    eax, eax
0x180028df7  js      loc_180028FBC
0x180028dfd  mov     r12d, [rbp+310h+arg_50]
0x180028e04  lea     rcx, [rbp+310h+var_230]; struct _LSA_CALL_INFO *
0x180028e0b  mov     [rbp+310h+var_1EC], r12d
0x180028e12  call    ?LsapCheckCallerSuppliedCallFlags@@YAJPEAU_LSA_CALL_INFO@@@Z; LsapCheckCallerSuppliedCallFlags(_LSA_CALL_INFO *)
0x180028e17  mov     ebx, eax
0x180028e19  test    eax, eax
0x180028e1b  js      loc_1800291C1
0x180028e21  test    r15, r15
0x180028e24  jnz     loc_180029023
0x180028e2a  mov     ebx, [rbp+310h+arg_28]
0x180028e30  mov     ecx, [rbp+310h+var_210]
0x180028e36  cmp     ebx, 18h
0x180028e39  jb      short loc_180028E48
0x180028e3b  cmp     dword ptr [r14], 8001h
0x180028e42  jz      loc_1800290BC
0x180028e48  xor     sil, sil
0x180028e4b  cmp     r13d, dword ptr cs:?NegPackageId@@3_KA; unsigned __int64 NegPackageId
0x180028e52  lea     rdi, WPP_GLOBAL_Control
0x180028e59  jnz     loc_180029284
0x180028e5f  mov     edx, [rsp+410h+var_3B0]; enum _SECURITY_LOGON_TYPE
0x180028e63  lea     rax, [rsp+410h+var_3C0]
0x180028e68  mov     [rsp+410h+lpTlsValue], rax; unsigned __int8 *
0x180028e6d  mov     r9d, ebx; unsigned int
0x180028e70  lea     rax, [rsp+410h+var_398]
0x180028e75  shr     ecx, 6
0x180028e78  mov     [rsp+410h+var_3D8], rax; struct _LUID *
0x180028e7d  and     ecx, 1; int
0x180028e80  lea     rax, [rsp+410h+var_3B4]
0x180028e85  mov     r8, r14; void *
0x180028e88  mov     [rsp+410h+var_3E0], rax; unsigned int *
0x180028e8d  lea     rax, [rsp+410h+AuthData]
0x180028e92  mov     [rsp+410h+String1], rax; void **
0x180028e97  mov     rax, [rsp+410h+var_3A8]
0x180028e9c  mov     [rsp+410h+var_3F0], rax; void *
0x180028ea1  call    ?LsapConvertLogonAuthInfo@@YAJHW4_SECURITY_LOGON_TYPE@@PEAXK1PEAPEAXPEAKPEAU_LUID@@PEAE@Z; LsapConvertLogonAuthInfo(int,_SECURITY_LOGON_TYPE,void *,ulong,void *,void * *,ulong *,_LUID *,uchar *)
0x180028ea6  test    eax, eax
0x180028ea8  jns     loc_18002910D
0x180028eae  mov     [rsp+410h+var_3C0], 0
0x180028eb3  mov     r10, cs:WPP_GLOBAL_Control
0x180028eba  mov     [rbp+310h+var_2D8], r14
0x180028ebe  mov     r14, [rbp+310h+var_390]
0x180028ec2  mov     [rbp+310h+var_2DC], r13d
0x180028ec6  mov     [rbp+310h+var_2D0], ebx
0x180028ec9  mov     rdx, [r14]
0x180028ecc  mov     [rbp+310h+var_298], rdx
0x180028ed0  mov     [rbp+310h+var_238], r12d
0x180028ed7  mov     [rbp+310h+var_2C8], r15
0x180028edb  test    r15, r15
0x180028ede  jz      short loc_180028EE6
0x180028ee0  mov     eax, [r15]
0x180028ee3  mov     [rbp+310h+var_2CC], eax
0x180028ee6  mov     rax, [rbp+310h+arg_40]
0x180028eed  mov     r8d, [rsp+410h+var_3B0]
0x180028ef2  mov     [rbp+310h+var_2E0], r8d
0x180028ef6  movups  xmm0, xmmword ptr [rax]
0x180028ef9  mov     rax, [rbp+310h+var_388]
0x180028efd  movdqu  [rbp+310h+var_2C0], xmm0
0x180028f02  test    rax, rax
0x180028f05  jz      short loc_180028F0F
0x180028f07  movups  xmm0, xmmword ptr [rax]
0x180028f0a  movdqu  [rbp+310h+var_2F0], xmm0
0x180028f0f  lea     rax, [rbp+310h+var_320]
0x180028f13  mov     qword ptr [rbp+310h+var_330], rax
0x180028f17  cmp     r10, rdi
0x180028f1a  jz      short loc_180028F2A
0x180028f1c  test    dword ptr [r10+1Ch], 400h
0x180028f24  jnz     loc_180029364
0x180028f2a  mov     r9b, [rsp+410h+var_3C0]; unsigned __int8
0x180028f2f  lea     rcx, [rsp+410h+var_3AC]
0x180028f34  mov     rdx, [rsp+410h+var_3A8]; void *
0x180028f39  lea     r8, [rbp+310h+var_288]; struct _QUOTA_LIMITS *
0x180028f40  neg     sil
0x180028f43  sbb     rax, rax
0x180028f46  and     rax, rcx
0x180028f49  lea     rcx, [rbp+310h+var_330]; struct _LSAP_CLIENT_REQUEST *
0x180028f4d  mov     [rsp+410h+var_3F0], rax; PULONG
0x180028f52  call    ?LsapAuApiDispatchLogonUser@@YAJPEAU_LSAP_CLIENT_REQUEST@@PEAXPEAU_QUOTA_LIMITS@@EPEAK@Z; LsapAuApiDispatchLogonUser(_LSAP_CLIENT_REQUEST *,void *,_QUOTA_LIMITS *,uchar,ulong *)
0x180028f57  mov     rcx, [rbp+310h+var_378]
0x180028f5b  mov     ebx, eax
0x180028f5d  mov     rax, [rbp+310h+var_298]
0x180028f61  movaps  xmm0, xmmword ptr [rbp+310h+var_288.NonPagedPoolLimit]
0x180028f68  movaps  xmm1, xmmword ptr [rbp+310h+var_288.MaximumWorkingSetSize]
0x180028f6f  mov     [r14], rax
0x180028f72  mov     rax, [rbp+310h+var_2A8]
0x180028f76  mov     [rcx], rax
0x180028f79  mov     rcx, [rbp+310h+var_370]
0x180028f7d  mov     eax, [rbp+310h+var_2A0]
0x180028f80  mov     [rcx], eax
0x180028f82  mov     rcx, [rbp+310h+var_368]
0x180028f86  mov     rax, [rbp+310h+var_288.PagedPoolLimit]
0x180028f8d  movups  xmmword ptr [rcx+8], xmm0
0x180028f91  mov     [rcx], rax
0x180028f94  mov     rax, [rbp+310h+var_290]
0x180028f9b  movsd   xmm0, qword ptr [rbp+310h+var_288.TimeLimit]
0x180028fa3  movups  xmmword ptr [rcx+18h], xmm1
0x180028fa7  movsd   qword ptr [rcx+28h], xmm0
0x180028fac  mov     rcx, [rbp+310h+var_360]
0x180028fb0  mov     [rcx], rax
0x180028fb3  mov     rcx, [rbp+310h+var_358]
0x180028fb7  mov     eax, [rbp+310h+var_2B0]
0x180028fba  mov     [rcx], eax
0x180028fbc  lea     rcx, [rbp+310h+var_230]; struct _LSA_CALL_INFO *
0x180028fc3  call    ?SspipCleanupCallInfo@@YAXPEAU_LSA_CALL_INFO@@@Z; SspipCleanupCallInfo(_LSA_CALL_INFO *)
0x180028fc8  mov     rcx, [rbp+310h+var_2C8]; struct _TOKEN_GROUPS *
0x180028fcc  test    rcx, rcx
0x180028fcf  jz      short loc_180028FDA
0x180028fd1  cmp     rcx, r15
0x180028fd4  jnz     loc_180029103
0x180028fda  mov     rcx, [rsp+410h+AuthData]; AuthData
0x180028fdf  test    rcx, rcx
0x180028fe2  jnz     loc_1800293A0
0x180028fe8  xor     edx, edx; unsigned __int16 *
0x180028fea  lea     rcx, SSPIEX_LOGON_USER_STOP; struct _EVENT_DESCRIPTOR *
0x180028ff1  call    ?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180028ff6  mov     eax, ebx
0x180028ff8  mov     rcx, [rbp+310h+var_40]
0x180028fff  xor     rcx, rsp; StackCookie
0x180029002  call    __security_check_cookie
0x180029007  mov     rbx, [rsp+410h+arg_10]
0x18002900f  add     rsp, 3E0h
0x180029016  pop     r15
0x180029018  pop     r14
0x18002901a  pop     r13
0x18002901c  pop     r12
0x18002901e  pop     rdi
0x18002901f  pop     rsi
0x180029020  pop     rbp
0x180029021  retn
0x180029023  test    [rbp+310h+var_210], 200h
0x18002902d  jz      loc_18002914E
0x180029033  xor     dil, dil
0x180029036  xor     esi, esi
0x180029038  cmp     esi, [r15]
0x18002903b  jnb     loc_180028E2A
0x180029041  mov     eax, esi
0x180029043  add     rax, rax
0x180029046  mov     rbx, [r15+rax*8+8]
0x18002904b  mov     rcx, rbx; Sid
0x18002904e  call    cs:__imp_RtlValidSid
0x180029055  nop     dword ptr [rax+rax+00h]
0x18002905a  test    al, al
0x18002905c  jz      loc_18002917E
0x180029062  test    dil, dil
0x180029065  jz      short loc_18002906B
0x180029067  inc     esi
0x180029069  jmp     short loc_180029038
0x18002906b  mov     rcx, rbx; Sid
0x18002906e  call    cs:__imp_RtlIdentifierAuthoritySid
0x180029075  nop     dword ptr [rax+rax+00h]
0x18002907a  mov     edx, [rax]
0x18002907c  sub     edx, [rsp+410h+var_3BC]
0x180029080  jnz     short loc_18002908D
0x180029082  movzx   edx, word ptr [rax+4]
0x180029086  movzx   eax, [rsp+410h+var_3B8]
0x18002908b  sub     edx, eax; SubAuthority
0x18002908d  test    edx, edx
0x18002908f  jnz     short loc_180029067
0x180029091  mov     rcx, rbx; Sid
0x180029094  call    cs:__imp_RtlSubAuthoritySid
0x18002909b  nop     dword ptr [rax+rax+00h]
0x1800290a0  mov     edx, [rbp+310h+var_218]; unsigned int
0x1800290a6  mov     ecx, [rax]; unsigned int
0x1800290a8  call    ?LsapCheckVirtualAccountRestriction@@YAJKK@Z; LsapCheckVirtualAccountRestriction(ulong,ulong)
0x1800290ad  mov     ebx, eax
0x1800290af  test    eax, eax
0x1800290b1  js      loc_180029239
0x1800290b7  mov     dil, 1
0x1800290ba  jmp     short loc_180029067
0x1800290bc  mov     edx, [r14+8]
0x1800290c0  lea     eax, [rdx+18h]
0x1800290c3  cmp     eax, 18h
0x1800290c6  jb      short loc_1800290F9
0x1800290c8  cmp     ebx, eax
0x1800290ca  jb      loc_180028E48
0x1800290d0  mov     eax, [r14+4]
0x1800290d4  mov     [rsp+410h+var_3AC], eax
0x1800290d8  bt      ecx, 9
0x1800290dc  jnb     loc_18002925C
0x1800290e2  mov     rax, [r14+10h]
0x1800290e6  mov     sil, 1
0x1800290e9  mov     [rsp+410h+var_3A8], rax
0x1800290ee  add     r14, 18h
0x1800290f2  mov     ebx, edx
0x1800290f4  jmp     loc_180028E4B
0x1800290f9  mov     ebx, 0C0000095h
0x1800290fe  jmp     loc_180028FBC
0x180029103  call    ?LsapFreeTokenGroups@@YAXPEAU_TOKEN_GROUPS@@@Z; LsapFreeTokenGroups(_TOKEN_GROUPS *)
0x180029108  jmp     loc_180028FDA
0x18002910d  mov     r10, cs:WPP_GLOBAL_Control
0x180029114  cmp     r10, rdi
0x180029117  jnz     loc_180029327
0x18002911d  mov     rax, cs:?NegPackageId@@3_KA; unsigned __int64 NegPackageId
0x180029124  cmp     r13d, eax
0x180029127  jnz     loc_180029356
0x18002912d  mov     rdx, qword ptr [rsp+410h+var_398.LowPart]
0x180029132  mov     r14, [rbp+310h+var_390]
0x180029136  mov     [rbp+310h+var_2DC], eax
0x180029139  mov     rax, [rsp+410h+AuthData]
0x18002913e  mov     [rbp+310h+var_2D8], rax
0x180029142  mov     eax, [rsp+410h+var_3B4]
0x180029146  mov     [rbp+310h+var_2D0], eax
0x180029149  jmp     loc_180028ECC
0x18002914e  mov     ebx, 0C0000022h
0x180029153  mov     rcx, cs:WPP_GLOBAL_Control
0x18002915a  lea     rdi, WPP_GLOBAL_Control
0x180029161  cmp     rcx, rdi
0x180029164  jz      loc_180028FBC
0x18002916a  test    byte ptr [rcx+1Ch], 1
0x18002916e  jz      loc_180028FBC
0x180029174  mov     edx, 14h
0x180029179  jmp     loc_18002922E
0x18002917e  mov     ebx, 0C0000078h
0x180029183  mov     rcx, cs:WPP_GLOBAL_Control
0x18002918a  lea     rdi, WPP_GLOBAL_Control
0x180029191  cmp     rcx, rdi
0x180029194  jz      loc_180028FBC
0x18002919a  test    byte ptr [rcx+1Ch], 1
0x18002919e  jz      loc_180028FBC
0x1800291a4  mov     edx, 15h
0x1800291a9  mov     r9d, esi
0x1800291ac  mov     rcx, [rcx+10h]
0x1800291b0  lea     r8, WPP_70ad1dbafaf332f23371a09dd7075615_Traceguids
0x1800291b7  call    WPP_SF_d
0x1800291bc  jmp     loc_180028FBC
0x1800291c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800291c8  lea     rdi, WPP_GLOBAL_Control
  ... truncated ...
```
