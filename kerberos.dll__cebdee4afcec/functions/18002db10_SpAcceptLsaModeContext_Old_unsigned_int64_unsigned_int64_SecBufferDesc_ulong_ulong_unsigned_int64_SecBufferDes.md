# SpAcceptLsaModeContext_Old(unsigned __int64,unsigned __int64,_SecBufferDesc *,ulong,ulong,unsigned __int64 *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x18002db10`
- end: `0x18002f89c`
- name: `?SpAcceptLsaModeContext_Old@@YAJ_K0PEAU_SecBufferDesc@@KKPEA_K1PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `7564`
- prototype: `__int64 __usercall@<rax>(struct _KERB_CREDENTIAL *@<rcx>, unsigned __int64@<rdx>, struct _SecBufferDesc *@<r8>, unsigned int@<r9d>, unsigned int, unsigned __int64 *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `1`
- callee_count: `46`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002d890`

## callees

- `0x180006680`
- `0x1800068d0`
- `0x180006920`
- `0x1800069a0`
- `0x1800093f0`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x180010e90`
- `0x1800113f0`
- `0x180016600`
- `0x180020e10`
- `0x18002bd40`
- `0x18002db10`
- `0x18002ffa8`
- `0x180036224`
- `0x18003a1f0`
- `0x18003af1c`
- `0x180041758`
- `0x180042470`
- `0x180045e58`
- `0x180046970`
- `0x180046e70`
- `0x1800484f8`
- `0x1800621d0`
- `0x1800623ac`
- `0x18006bda0`
- `0x18006ca9c`
- `0x18006d830`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x180082ef4`
- `0x18008587c`
- `0x180086c14`
- `0x18008868c`
- `0x18008a49c`
- `0x18008a694`
- `0x18008a8cc`
- `0x18008aecc`
- `0x18008af5c`
- `0x18008aff0`
- `0x18008b70c`
- `0x180092c24`
- `0x1800dd594`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlSystemTimeToLocalTime` at `0x18002e582`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18002e79a`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18002edc6`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18002e582`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18002e79a`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18002edc6`
- `ntdll!EtwLogTraceEvent` at `0x18002dd1a`
- `ntdll!EtwLogTraceEvent` at `0x18002f349`
- `ntdll!EtwLogTraceEvent` at `0x18002dd1a`
- `ntdll!EtwLogTraceEvent` at `0x18002f349`
- `ntdll!NtClose` at `0x18002f733`
- `ntdll!NtClose` at `0x18002f733`
- `ntdll!RtlInitUnicodeString` at `0x18002f1e0`
- `ntdll!RtlInitUnicodeString` at `0x18002f205`
- `ntdll!RtlInitUnicodeString` at `0x18002f22c`
- `ntdll!RtlInitUnicodeString` at `0x18002f24c`
- `ntdll!RtlInitUnicodeString` at `0x18002f263`
- `ntdll!RtlInitUnicodeString` at `0x18002f1e0`
- `ntdll!RtlInitUnicodeString` at `0x18002f205`
- `ntdll!RtlInitUnicodeString` at `0x18002f22c`
- `ntdll!RtlInitUnicodeString` at `0x18002f24c`
- `ntdll!RtlInitUnicodeString` at `0x18002f263`
- `ntdll!RtlReleaseResource` at `0x18002e028`
- `ntdll!RtlReleaseResource` at `0x18002e068`
- `ntdll!RtlReleaseResource` at `0x18002e59a`
- `ntdll!RtlReleaseResource` at `0x18002ee1b`
- `ntdll!RtlReleaseResource` at `0x18002f40d`
- `ntdll!RtlReleaseResource` at `0x18002e028`
- `ntdll!RtlReleaseResource` at `0x18002e068`
- `ntdll!RtlReleaseResource` at `0x18002e59a`
- `ntdll!RtlReleaseResource` at `0x18002ee1b`
- `ntdll!RtlReleaseResource` at `0x18002f40d`
- `ntdll!RtlAcquireResourceShared` at `0x18002dfd5`
- `ntdll!RtlAcquireResourceShared` at `0x18002e562`
- `ntdll!RtlAcquireResourceShared` at `0x18002dfd5`
- `ntdll!RtlAcquireResourceShared` at `0x18002e562`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002ee03`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002f3a1`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002f3be`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002ee03`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002f3a1`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002f3be`
- `ntdll!RtlEnterCriticalSection` at `0x18002e167`
- `ntdll!RtlEnterCriticalSection` at `0x18002e5d7`
- `ntdll!RtlEnterCriticalSection` at `0x18002e167`
- `ntdll!RtlEnterCriticalSection` at `0x18002e5d7`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e1c4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e60d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e6bd`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e1c4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e60d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e6bd`
- `MSASN1!ASN1intx2int32` at `0x18002e317`
- `MSASN1!ASN1intx2int32` at `0x18002ea00`
- `MSASN1!ASN1intx2int32` at `0x18002e317`
- `MSASN1!ASN1intx2int32` at `0x18002ea00`
- `MSASN1!ASN1intx2uint32` at `0x18002e30f`
- `MSASN1!ASN1intx2uint32` at `0x18002e9f8`
- `MSASN1!ASN1intx2uint32` at `0x18002e30f`
- `MSASN1!ASN1intx2uint32` at `0x18002e9f8`
- `MSASN1!ASN1intxisuint32` at `0x18002e2fd`
- `MSASN1!ASN1intxisuint32` at `0x18002e9e6`
- `MSASN1!ASN1intxisuint32` at `0x18002e2fd`
- `MSASN1!ASN1intxisuint32` at `0x18002e9e6`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18002f746`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18002f746`

## string_xrefs

- `0x18002ed35`: `Output token is too small - sent in %d, needed %d`
- `0x18002ef37`: `Output token is too small - sent in %d, needed %d`
- `0x18002dee7`: `Failed to map output token: 0x%x`
- `0x18002dda1`: `Failed to map Input token: 0x%x`
- `0x18002de72`: `Failed to map Mechlist token: 0x%x`
- `0x18002df64`: `SpAcceptLsaModeContext trying to complete a context with no input token!`
- `0x18002e0a4`: `Different cred handle passsed to subsequent call to AcceptSecurityContext: %p instead of %p`
- `0x18002e3f9`: `Failed to create token from ticket: 0x%x`
- `0x18002e4cb`: `Failed to create server context: 0x%x`
- `0x18002e769`: `Failed to create server context: 0x%x`
- `0x18002e701`: `Non null input token passed to AcceptSecurityContext for datagram\n`
- `0x18002f149`: `Null input token passed to AcceptSecurityContext for datagram\n`
- `0x18002ea3e`: `AcceptLsaModeContext: Creating token from ticket\n`
- `0x18002ee7f`: `SpAcceptLsaModeContext encountered null output token\n`
- `0x18002f0d0`: `Failed to create or update server context: 0x%x`
- `0x18002f714`: `Closing token handle because context creation failed (%x)\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpAcceptLsaModeContext_Old(
        struct _KERB_CREDENTIAL *a1,
        struct _KERBEROS_LIST_ENTRY *a2,
        struct _SecBufferDesc *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int64 *a6,
        struct _SecBufferDesc *a7,
        unsigned int *a8,
        union _LARGE_INTEGER *a9,
        unsigned __int8 *a10,
        struct _SecBuffer *a11)
{
  unsigned int v11; // r13d
  unsigned int *v14; // rsi
  struct _KERB_LOGON_SESSION *v15; // r15
  unsigned int *p_cbBuffer; // r14
  const void *v17; // rcx
  __int64 v18; // rcx
  struct _SecBuffer *v19; // rax
  enum _SECURITY_IMPERSONATION_LEVEL v20; // edi
  struct _KERBEROS_LIST_ENTRY *v21; // r12
  struct _SecBufferDesc *v22; // rbx
  PSecBuffer pBuffers; // rdx
  struct _SecBuffer *v24; // r8
  int v25; // eax
  const char *v26; // r9
  __int64 v27; // r8
  __int64 v28; // rcx
  int v29; // ecx
  PSecBuffer v30; // rdx
  struct _SecBuffer *v31; // r8
  struct _SecBuffer *v32; // rbx
  int v33; // ecx
  PSecBuffer v34; // rdx
  struct _SecBuffer *v35; // r8
  int v36; // ecx
  int v37; // r15d
  int v38; // esi
  struct _KERB_CREDENTIAL *v39; // rdi
  bool v40; // si
  int v41; // eax
  struct _RTL_CRITICAL_SECTION *v42; // rax
  struct _RTL_CRITICAL_SECTION *v43; // rdi
  const struct _UNICODE_STRING *v44; // rdx
  int v45; // eax
  struct KERB_AUTHENTICATOR *v46; // rdx
  int v47; // eax
  char *v48; // rcx
  unsigned int v49; // eax
  unsigned int v50; // edi
  int updated; // eax
  __int64 v52; // r8
  const char *v53; // r9
  union _LARGE_INTEGER *v54; // r9
  struct _RTL_CRITICAL_SECTION *v55; // rax
  struct _RTL_CRITICAL_SECTION *v56; // rdi
  struct _RTL_CRITICAL_SECTION *v57; // rsi
  const struct _UNICODE_STRING *v58; // rdi
  unsigned int *v59; // r15
  __int16 v60; // cx
  __int64 v61; // r8
  struct _KERB_LOGON_SESSION *v62; // rdi
  int v63; // eax
  __int64 v64; // rdx
  int v65; // r8d
  const char *v66; // rax
  int v67; // eax
  int v68; // eax
  char *v69; // rcx
  unsigned int v70; // eax
  unsigned int v71; // esi
  __int16 v72; // r15
  unsigned int v73; // r14d
  unsigned __int8 *p_ChannelBindings; // rdi
  unsigned __int64 v75; // rax
  __int64 v76; // rcx
  int v77; // edi
  unsigned int v78; // edx
  int v79; // esi
  size_t v80; // rdi
  unsigned __int64 *v81; // r13
  unsigned int v82; // ecx
  unsigned int v83; // edx
  unsigned __int8 **v84; // rbx
  unsigned __int8 **v85; // rdx
  unsigned __int8 **v86; // rcx
  struct _KERB_CONTEXT *v87; // rcx
  int v88; // eax
  _QWORD *v89; // rax
  char *v90; // r8
  unsigned int i; // r9d
  unsigned int v92; // r10d
  unsigned __int8 **v93; // r8
  unsigned __int8 **v94; // r9
  __int64 v95; // rcx
  unsigned __int8 **p_DestinationString; // rax
  unsigned __int8 **v97; // rax
  int v98; // eax
  unsigned __int64 v99; // rbx
  struct _KERB_CREDENTIAL *v100; // rcx
  const void *v101; // rcx
  const void *v102; // rcx
  unsigned int v103; // ebx
  struct _UNICODE_STRING *v105; // [rsp+20h] [rbp-100h]
  struct _UNICODE_STRING *v106; // [rsp+20h] [rbp-100h]
  int ChannelBindings; // [rsp+A0h] [rbp-80h] BYREF
  unsigned int v108; // [rsp+A4h] [rbp-7Ch] BYREF
  struct _KERB_CONTEXT *v109; // [rsp+A8h] [rbp-78h] BYREF
  struct _KERBEROS_LIST_ENTRY *v110; // [rsp+B0h] [rbp-70h]
  int v111; // [rsp+B8h] [rbp-68h] BYREF
  char v112; // [rsp+BCh] [rbp-64h]
  unsigned int v113; // [rsp+C0h] [rbp-60h] BYREF
  unsigned int v114; // [rsp+C4h] [rbp-5Ch] BYREF
  unsigned int *v115; // [rsp+C8h] [rbp-58h]
  struct _KERB_CREDENTIAL *v116; // [rsp+D0h] [rbp-50h] BYREF
  unsigned __int64 *v117; // [rsp+D8h] [rbp-48h]
  struct _LUID v118; // [rsp+E0h] [rbp-40h] BYREF
  struct _KERB_LOGON_SESSION *v119; // [rsp+E8h] [rbp-38h]
  struct KERB_AUTHENTICATOR *v120; // [rsp+F0h] [rbp-30h] BYREF
  size_t v121; // [rsp+F8h] [rbp-28h] BYREF
  struct _LSA_ADT_STRING_LIST *v122; // [rsp+100h] [rbp-20h]
  __int64 v123; // [rsp+108h] [rbp-18h] BYREF
  void *Src; // [rsp+110h] [rbp-10h] BYREF
  struct KERB_ENCRYPTED_TICKET *v125; // [rsp+118h] [rbp-8h] BYREF
  struct KERB_AP_REQUEST *v126; // [rsp+120h] [rbp+0h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+128h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+130h] [rbp+10h] BYREF
  unsigned __int8 *v129[2]; // [rsp+138h] [rbp+18h] BYREF
  void *v130; // [rsp+148h] [rbp+28h] BYREF
  PLARGE_INTEGER LocalTime[2]; // [rsp+150h] [rbp+30h] BYREF
  int v132; // [rsp+160h] [rbp+40h] BYREF
  unsigned int Size; // [rsp+164h] [rbp+44h] BYREF
  int Size_4; // [rsp+168h] [rbp+48h]
  struct _SecBuffer *v135; // [rsp+170h] [rbp+50h]
  unsigned __int8 *v136; // [rsp+178h] [rbp+58h] BYREF
  union _LARGE_INTEGER v137; // [rsp+180h] [rbp+60h] BYREF
  unsigned __int8 *v138[2]; // [rsp+188h] [rbp+68h] BYREF
  struct _UNICODE_STRING v139; // [rsp+198h] [rbp+78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+1A8h] [rbp+88h] BYREF
  char v141[8]; // [rsp+1B8h] [rbp+98h] BYREF
  struct _SecBufferDesc *v142; // [rsp+1C0h] [rbp+A0h]
  struct _UNICODE_STRING v143; // [rsp+1C8h] [rbp+A8h] BYREF
  struct _UNICODE_STRING v144; // [rsp+1D8h] [rbp+B8h] BYREF
  struct _UNICODE_STRING v145; // [rsp+1E8h] [rbp+C8h] BYREF
  struct _SecBufferDesc *v146; // [rsp+1F8h] [rbp+D8h]
  struct _SecBuffer *v147; // [rsp+200h] [rbp+E0h]
  struct _UNICODE_STRING v148; // [rsp+208h] [rbp+E8h] BYREF
  _OWORD v149[2]; // [rsp+218h] [rbp+F8h] BYREF
  __int64 v150; // [rsp+238h] [rbp+118h]
  _OWORD v151[2]; // [rsp+240h] [rbp+120h] BYREF
  __int64 v152; // [rsp+260h] [rbp+140h]
  _OWORD v153[2]; // [rsp+268h] [rbp+148h] BYREF
  __int64 v154; // [rsp+288h] [rbp+168h]
  _WORD v155[2]; // [rsp+290h] [rbp+170h] BYREF
  char v156; // [rsp+294h] [rbp+174h]
  __int128 v157; // [rsp+2A8h] [rbp+188h]
  int v158; // [rsp+2BCh] [rbp+19Ch]
  int *v159; // [rsp+2C0h] [rbp+1A0h]
  int v160; // [rsp+2C8h] [rbp+1A8h]
  PLARGE_INTEGER *v161; // [rsp+2D0h] [rbp+1B0h]
  int v162; // [rsp+2D8h] [rbp+1B8h]
  PLARGE_INTEGER v163; // [rsp+2E0h] [rbp+1C0h]
  int v164; // [rsp+2E8h] [rbp+1C8h]
  unsigned __int8 **v165; // [rsp+2F0h] [rbp+1D0h]
  int v166; // [rsp+2F8h] [rbp+1D8h]
  unsigned __int8 *v167; // [rsp+300h] [rbp+1E0h]
  int v168; // [rsp+308h] [rbp+1E8h]
  unsigned __int8 **v169; // [rsp+310h] [rbp+1F0h]
  int v170; // [rsp+318h] [rbp+1F8h]
  unsigned __int8 *v171; // [rsp+320h] [rbp+200h]
  int v172; // [rsp+328h] [rbp+208h]
  unsigned __int8 **v173; // [rsp+330h] [rbp+210h]
  int v174; // [rsp+338h] [rbp+218h]
  unsigned __int8 *v175; // [rsp+340h] [rbp+220h]
  int v176; // [rsp+348h] [rbp+228h]

  v11 = a4;
  v113 = a4;
  v146 = a3;
  v110 = a2;
  v147 = a11;
  v117 = a6;
  v142 = a7;
  v14 = a8;
  v115 = a8;
  LocalTime[0] = a9;
  v138[0] = a10;
  KerbTracerT::KerbTracerT((KerbTracerT *)v141, "SP Accept OLD", (unsigned int)a11);
  v15 = 0;
  v119 = 0;
  v116 = 0;
  ChannelBindings = 0;
  v126 = 0;
  v136 = 0;
  v135 = 0;
  v121 = 0;
  v118 = 0;
  v125 = 0;
  v120 = 0;
  memset(v149, 0, sizeof(v149));
  v150 = 0;
  memset(v153, 0, sizeof(v153));
  v154 = 0;
  memset(v151, 0, sizeof(v151));
  v152 = 0;
  v109 = 0;
  SystemTime.QuadPart = 0;
  Handle = 0;
  v108 = 0;
  v114 = 4;
  v130 = 0;
  v111 = 0;
  v143 = 0;
  v144 = 0;
  DestinationString = 0;
  v139 = 0;
  v145 = 0;
  v148 = 0;
  v112 = 0;
  Size_4 = 0;
  Src = 0;
  v129[0] = 0;
  v123 = 0;
  p_cbBuffer = 0;
  v122 = 0;
  v137.QuadPart = 0;
  v132 = 0;
  memset_0(v155, 0, 0xC0u);
  if ( a2 )
    v17 = (const void *)WORD1(a2);
  else
    v17 = 0;
  KerbTracerT::Log(7, "SpAcceptLsaModeContext_Old", 3607, "SpAcceptLsaModeContext %p called\n", v17);
  if ( KerbEventTraceFlag )
  {
    v157 = KerbAcceptSCGuid;
    v156 = 1;
    v158 = 0x20000;
    v155[0] = 48;
    EtwLogTraceEvent(KerbTraceLoggerHandle, v155);
  }
  *a8 = 0;
  *v117 = 0;
  *a9 = KerbGlobalHasNeverTime;
  *v138[0] = 0;
  v19 = v147;
  v147->pvBuffer = 0;
  v19->cbBuffer = 0;
  v20 = SecurityImpersonation;
  if ( !KerbGlobalInitialized )
  {
    ChannelBindings = -1073741604;
LABEL_8:
    v21 = v110;
LABEL_218:
    v81 = v117;
    goto LABEL_219;
  }
  v22 = v146;
  if ( v146->cBuffers )
  {
    LODWORD(v18) = 0;
    while ( 1 )
    {
      pBuffers = v146->pBuffers;
      v24 = &pBuffers[(unsigned int)v18];
      if ( (v24->BufferType & 0xFFFFFFF) == 2 )
        break;
      v18 = (unsigned int)(v18 + 1);
      if ( (unsigned int)v18 >= v146->cBuffers )
        goto LABEL_13;
    }
    p_cbBuffer = &pBuffers[(unsigned int)v18].cbBuffer;
    v25 = ((__int64 (__fastcall *)(struct _SecBuffer *, unsigned int *))LsaFunctions->MapBuffer)(v24, p_cbBuffer);
    ChannelBindings = v25;
  }
  else
  {
LABEL_13:
    v25 = ChannelBindings;
  }
  if ( v25 < 0 )
  {
    LODWORD(v105) = v25;
    v26 = "Failed to map Input token: 0x%x";
    v27 = 3656;
LABEL_16:
    KerbTracerT::Log(1, "SpAcceptLsaModeContext_Old", v27, v26, v105);
LABEL_91:
    v21 = v110;
LABEL_92:
    if ( !ChannelBindings || ChannelBindings == 590611 )
    {
      if ( v135 )
        KerbSqmNegoASCIncrement();
      else
        KerbSqmKerbASCIncrement();
    }
    p_cbBuffer = &v122->cStrings;
    goto LABEL_216;
  }
  ChannelBindings = SspGetChannelBindings(v18, v22, &Src);
  if ( ChannelBindings < 0 )
    goto LABEL_91;
  ChannelBindings = SspGetChannelBindingsResult(v28, v142, v129);
  if ( ChannelBindings < 0 )
    goto LABEL_91;
  if ( v22->cBuffers )
  {
    v29 = 0;
    while ( 1 )
    {
      v30 = v22->pBuffers;
      v31 = &v30[v29];
      if ( (v31->BufferType & 0xFFFFFFF) == 0xB )
        break;
      if ( ++v29 >= v22->cBuffers )
        goto LABEL_26;
    }
    v135 = &v30[v29];
    ChannelBindings = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))LsaFunctions->MapBuffer)(
                        v31,
                        v135);
  }
LABEL_26:
  if ( ChannelBindings < 0 )
  {
    LODWORD(v105) = ChannelBindings;
    v26 = "Failed to map Mechlist token: 0x%x";
    v27 = 3698;
    goto LABEL_16;
  }
  v32 = 0;
  if ( v142->cBuffers )
  {
    v33 = 0;
    while ( 1 )
    {
      v34 = v142->pBuffers;
      v35 = &v34[v33];
      if ( (v35->BufferType & 0xFFFFFFF) == 2 )
        break;
      if ( ++v33 >= v142->cBuffers )
        goto LABEL_34;
    }
    v32 = &v34[v33];
    ChannelBindings = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))LsaFunctions->MapBuffer)(
                        v35,
                        v32);
  }
LABEL_34:
  if ( ChannelBindings < 0 )
  {
    LODWORD(v105) = ChannelBindings;
    v26 = "Failed to map output token: 0x%x";
    v27 = 3719;
    goto LABEL_16;
  }
  if ( v110 )
  {
    ChannelBindings = KerbReferenceContext(v110, 0, &v109);
    if ( !v109 )
    {
      v21 = v110;
      KerbTracerT::Log(
        1,
        "SpAcceptLsaModeContext_Old",
        3740,
        "Failed to reference context %p.",
        (const void *)WORD1(v110));
      goto LABEL_92;
    }
    if ( !p_cbBuffer )
    {
      if ( !v135 )
      {
        KerbTracerT::Log(
          1,
          "SpAcceptLsaModeContext_Old",
          3748,
          "SpAcceptLsaModeContext trying to complete a context with no input token!");
LABEL_42:
        ChannelBindings = -2146893048;
        p_cbBuffer = 0;
        goto LABEL_8;
      }
      v36 = *((_DWORD *)v109 + 54);
      if ( v36 != 5 )
      {
        KerbTracerT::Log(1, "SpAcceptLsaModeContext_Old", 3756, "Invalid context state: %d", v36);
        goto LABEL_42;
      }
      v118 = (struct _LUID)*((_QWORD *)v109 + 14);
LABEL_103:
      ChannelBindings = 0;
      if ( v32 )
        v32->cbBuffer = 0;
      RtlAcquireResourceShared(&KerbContextResource, 1u);
      *v14 = KerbMapContextFlags(*((_DWORD *)v109 + 48));
      RtlSystemTimeToLocalTime(v54 + 3, LocalTime[0]);
      v21 = v110;
      *v117 = (unsigned __int64)v110;
      RtlReleaseResource(&KerbContextResource);
      goto LABEL_92;
    }
    RtlAcquireResourceShared(&KerbContextResource, 1u);
    v37 = *((_DWORD *)v109 + 54);
    if ( ((v37 - 2) & 0xFFFFFFF9) != 0 || v37 == 8 || (v38 = *((_DWORD *)v109 + 49), (v38 & 4) == 0) )
    {
      KerbTracerT::Log(1, "SpAcceptLsaModeContext_Old", 3779, "Invalid context state: %d", *((_DWORD *)v109 + 54));
      ChannelBindings = -1073741816;
      RtlReleaseResource(&KerbContextResource);
      goto LABEL_91;
    }
    v108 = *((_DWORD *)v109 + 48);
    v118 = (struct _LUID)*((_QWORD *)v109 + 14);
    v39 = (struct _KERB_CREDENTIAL *)*((_QWORD *)v109 + 16);
    Size_4 = *((_DWORD *)v109 + 26);
    RtlReleaseResource(&KerbContextResource);
    v40 = (v38 & 8) != 0;
  }
  else
  {
    v40 = 0;
    v39 = 0;
    v37 = 9;
  }
  if ( a1 )
  {
    if ( v39 && a1 != v39 )
    {
      KerbTracerT::Log(
        1,
        "SpAcceptLsaModeContext_Old",
        3802,
        "Different cred handle passsed to subsequent call to AcceptSecurityContext: %p instead of %p",
        (const void *)WORD1(a1),
        (const void *)WORD1(v39));
      ChannelBindings = -1073741070;
      v15 = v119;
      p_cbBuffer = (unsigned int *)v119;
LABEL_56:
      v20 = SecurityImpersonation;
      v21 = v110;
LABEL_217:
      v14 = v115;
      goto LABEL_218;
    }
  }
  else
  {
    a1 = v39;
  }
  v41 = KerbReferenceCredentialEx(a1, 1u, 0, 0, &v116);
  ChannelBindings = v41;
  if ( v41 < 0 )
  {
    LODWORD(v106) = v41;
    v20 = SecurityImpersonation;
    KerbTracerT::Log(
      2,
      "SpAcceptLsaModeContext_Old",
      3825,
      "SpAcceptLsaModeContext failed to locate credential 0x%x\n",
      v106);
    goto LABEL_91;
  }
  if ( v37 != 4 )
  {
    v118 = *(struct _LUID *)((char *)v116 + 28);
    v55 = (struct _RTL_CRITICAL_SECTION *)KerbLocateLogonSession(&v118, 0);
    v56 = v55;
    v119 = (struct _KERB_LOGON_SESSION *)v55;
    if ( !v55 )
    {
      v15 = 0;
      goto LABEL_63;
    }
    v57 = v55 + 2;
    RtlEnterCriticalSection(v55 + 2);
    if ( (*((_DWORD *)v116 + 16) & 0x8000000) != 0 )
    {
      v20 = SecurityImpersonation;
      KerbTracerT::Log(2, "SpAcceptLsaModeContext_Old", 4144, "Trying to use a local logon session with Kerberos\n");
      RtlLeaveCriticalSection(v57);
      ChannelBindings = -2146893042;
LABEL_110:
      p_cbBuffer = 0;
      v21 = v110;
LABEL_216:
      v15 = v119;
      goto LABEL_217;
    }
    if ( *((_QWORD *)v116 + 9) )
    {
      v114 |= 8u;
      ChannelBindings = KerbDuplicateStringEx(&v143, (const struct _UNICODE_STRING *)(*((_QWORD *)v116 + 9) + 16LL));
      if ( ChannelBindings >= 0 )
        ChannelBindings = KerbDuplicateStringEx(&v144, *((const struct _UNICODE_STRING **)v116 + 9));
      v58 = (const struct _UNICODE_STRING *)&v56[3];
    }
    else
    {
      v58 = (const struct _UNICODE_STRING *)&v56[3];
      ChannelBindings = KerbDuplicateStringEx(&v143, v58 + 1);
      if ( ChannelBindings >= 0 )
        ChannelBindings = KerbDuplicateStringEx(&v144, v58);
    }
    KerbTracerT::Log(
      9,
      "SpAcceptLsaModeContext_Old",
      4185,
      "SpAcceptLsaModeContext: Accepting context for %wZ\\%wZ\n",
      &v58[1],
      v58);
    RtlLeaveCriticalSection(v57);
    if ( ChannelBindings < 0 )
      goto LABEL_90;
    if ( (v11 & 0x400) != 0 )
    {
      KerbTracerT::Log(14, "SpAcceptLsaModeContext_Old", 4201, "Accepting datagram first call\n");
      if ( p_cbBuffer && *p_cbBuffer > 4 )
      {
        v20 = SecurityImpersonation;
        KerbTracerT::Log(
          2,
          "SpAcceptLsaModeContext_Old",
          4211,
          "Non null input token passed to AcceptSecurityContext for datagram\n");
        ChannelBindings = -2146893048;
        goto LABEL_110;
      }
      v108 |= 0x400u;
      updated = KerbCreateEmptyContext(v116, v108, v114, 0, &v118, &v109, &SystemTime);
      ChannelBindings = updated;
      if ( updated < 0 )
      {
        v53 = "Failed to create server context: 0x%x";
        v52 = 4235;
        goto LABEL_89;
      }
      v59 = v115;
      if ( v32 )
        v32->cbBuffer = 0;
LABEL_126:
      *v117 = (unsigned __int64)v109;
      RtlSystemTimeToLocalTime(&SystemTime, LocalTime[0]);
      *v59 |= KerbMapContextFlags(v108);
      if ( v112 || (v60 & 0x600) != 0 )
        ChannelBindings = 590610;
      goto LABEL_90;
    }
    KerbTracerT::Log(14, "SpAcceptLsaModeContext_Old", 4246, "Accepting connection first call\n");
    if ( !p_cbBuffer || (v61 = *p_cbBuffer, !(_DWORD)v61) )
    {
      v20 = SecurityImpersonation;
      KerbTracerT::Log(
        2,
        "SpAcceptLsaModeContext_Old",
        4255,
        "Null input token passed to AcceptSecurityContext for datagram\n");
      ChannelBindings = -2146893048;
      goto LABEL_91;
    }
    v62 = v119;
    v63 = KerbVerifyApRequest(
            &v109,
            *((_QWORD *)p_cbBuffer + 1),
            v61,
            v11,
            v119,
            v116,
            &v126,
            &v125,
            &v120,
            v149,
            v153,
            v151,
            &v108,
            &v114,
            &v111,
            &v132,
            Src,
            v129[0],
            0);
    v64 = (unsigned int)v63;
    ChannelBindings = v63;
    if ( v63 < 0 )
    {
      v65 = v111;
      if ( ((v111 - 33) & 0xFFFFFFFB) == 0 )
      {
        KerbUpdateSkewTime(1u);
        LODWORD(v64) = ChannelBindings;
        v65 = v111;
      }
      v66 = "true";
      if ( v65 != 69 )
        v66 = "false";
      v20 = SecurityImpersonation;
      KerbTracerT::Log(
        2,
        "SpAcceptLsaModeContext_Old",
        4300,
        "Failed to verify AP request (need u2u? %s): %#x",
        v66,
        v64);
      goto LABEL_155;
    }
    v108 |= 0x800u;
    if ( v63 == 280 )
    {
      v112 = 1;
      v59 = v115;
      LOWORD(v11) = v113;
      v67 = KerbHandleTgtRequest(
              v62,
              v116,
              *((unsigned __int8 **)p_cbBuffer + 1),
              *p_cbBuffer,
              v113,
              v32,
              &v118,
              v115,
              &v109,
              &SystemTime,
              &v111);
      ChannelBindings = v67;
      if ( v67 >= 0 )
      {
        v108 |= 0x20u;
        KerbTracerT::Log(
          25,
          "SpAcceptLsaModeContext_Old",
          4345,
          "SpAcceptLsaModeContext handled TGT request and use_session_key set, ContextAttributes %#x\n",
          *((_DWORD *)v109 + 49));
        goto LABEL_126;
      }
      v20 = SecurityImpersonation;
      if ( v67 == -1073741789 )
        goto LABEL_91;
LABEL_155:
      v15 = v119;
      goto LABEL_156;
    }
    if ( v37 != 6 )
      KerbUpdateSkewTime(0);
    if ( v120 && (*(_BYTE *)v120 & 0x20) != 0 )
    {
      v68 = ASN1intxisuint32((char *)v120 + 104, v64);
      v69 = (char *)v120 + 104;
      if ( v68 )
        v70 = ASN1intx2uint32(v69);
      else
        v70 = ASN1intx2int32(v69);
      v71 = v70;
    }
    else
    {
      v71 = 0;
    }
    HIDWORD(v121) = v71;
    v72 = v113;
    v73 = v113 & 0x400000;
    if ( (v113 & 0x400000) != 0 )
      KerbTracerT::Log(1, "SpAcceptLsaModeContext_Old", 4392, "Deprecated flag ASC_REQ_CONTEXT_REPLAY\n");
    KerbTracerT::Log(14, "SpAcceptLsaModeContext_Old", 4415, "AcceptLsaModeContext: Creating token from ticket\n");
    updated = KerbCreateTokenFromTicketEx(
                (*((_DWORD *)v116 + 16) >> 25) & 1,
                v135 != 0,
                (struct _UNICODE_STRING **)&v118,
                v126,
                (__int64)v125,
                (__int64)v120,
                v108,
                (__int64)v151,
                &v143,
                &v144,
                (struct _KERB_ENCRYPTION_KEY *)v149,
                (__int64)v109,
                &v118,
                &v130,
                &Handle,
                &DestinationString,
                &v139,
                &v145,
                (__int64)&v123,
                &v137);
    ChannelBindings = updated;
    if ( updated == 280 )
    {
      v111 = 41;
      v20 = SecurityImpersonation;
      KerbTracerT::Log(
        2,
        "SpAcceptLsaModeContext_Old",
        4452,
        "SpAcceptLsaModeContext LOOPBACK asking the caller to try with a new ticket\n");
      ChannelBindings = KerbMapKerbError(v111);
      LOWORD(v11) = v72;
      goto LABEL_155;
    }
    if ( updated < 0 )
    {
      v52 = 4460;
      goto LABEL_88;
    }
    v82 = v108;
    if ( (v108 & 0x202) != 0 )
    {
      if ( !v32 )
      {
        ChannelBindings = -2146893048;
        KerbTracerT::Log(
          1,
          "SpAcceptLsaModeContext_Old",
          4478,
          "SpAcceptLsaModeContext encountered null output token\n");
        goto LABEL_90;
      }
      KerbTracerT::Log(14, "SpAcceptLsaModeContext_Old", 4486, "SpAcceptLsaModeContext: Building AP reply\n");
      updated = KerbBuildApReply(
                  v120,
                  v126,
                  v108,
                  &v114,
                  (struct _KERB_ENCRYPTION_KEY *)v153,
                  (struct _KERB_ENCRYPTION_KEY *)v149,
                  (unsigned int *)&v121 + 1,
                  &v136,
                  (unsigned int *)&v121);
      ChannelBindings = updated;
      if ( updated < 0 )
      {
        v53 = "Failed to build AP reply: 0x%x";
        v52 = 4505;
        goto LABEL_89;
      }
      KerbTelemetry::KerbRecordMaxTokenSize((KerbTelemetry *)(unsigned int)v121, v83);
      if ( (v72 & 0x100) != 0 )
      {
        v32->pvBuffer = v136;
        v136 = 0;
        v59 = v115;
        *v115 |= 0x100u;
      }
      else
      {
        if ( v32->cbBuffer < (unsigned int)v121 )
        {
          KerbTracerT::Log(
            1,
            "SpAcceptLsaModeContext_Old",
            4527,
            "Output token is too small - sent in %d, needed %d",
            v32->cbBuffer,
            v121);
          KerbReportBufferTooSmallError(v121, v32->cbBuffer, v109, 0);
          v32->cbBuffer = v121;
          ChannelBindings = -1073741789;
          v20 = SecurityImpersonation;
          goto LABEL_110;
        }
        memcpy_0(v32->pvBuffer, v136, (unsigned int)v121);
        v59 = v115;
      }
      v32->cbBuffer = v121;
    }
    else
    {
      v59 = v115;
      if ( !v32 )
      {
LABEL_203:
        if ( v73 )
        {
          v82 |= 0x400000u;
          v108 = v82;
        }
        if ( v109 )
          updated = KerbUpdateServerContext(
                      v109,
                      v125,
                      v126,
                      (struct _KERB_ENCRYPTION_KEY *)v149,
                      &v118,
                      &v130,
                      v82,
                      v114,
                      0,
                      HIDWORD(v121),
                      v71,
                      &Handle,
                      &DestinationString,
                      &v139,
                      &v145,
                      &SystemTime);
        else
          updated = KerbCreateServerContext(
                      v119,
                      v116,
                      v125,
                      v126,
                      (struct _KERB_ENCRYPTION_KEY *)v149,
                      &v118,
                      &v130,
                      v82,
                      v114,
                      0,
                      HIDWORD(v121),
                      v71,
                      &Handle,
                      &DestinationString,
                      &v139,
                      &v145,
                      &v109,
                      &SystemTime);
        ChannelBindings = updated;
        if ( updated < 0 )
        {
          v53 = "Failed to create or update server context: 0x%x";
          v52 = 4629;
          goto LABEL_89;
        }
        if ( (*((_DWORD *)v109 + 49) & 0x400) != 0 )
        {
          KerbFreeKey((char *)v109 + 376);
          if ( (unsigned int)KerbDuplicateAsn1KeyToKey((char *)v109 + 376, (char *)v120 + 80, *((_QWORD *)v109 + 17)) )
          {
            ChannelBindings = -1073741670;
            KerbTracerT::Log(1, "SpAcceptLsaModeContext_Old", 4644, "failed to duplicate old session key\n");
            goto LABEL_90;
          }
        }
        goto LABEL_126;
      }
      v32->cbBuffer = 0;
    }
    v82 = v108;
    goto LABEL_203;
  }
  if ( (v108 & 0x400) == 0 )
  {
    updated = KerbVerifyApReply(v109, *((unsigned __int8 **)p_cbBuffer + 1), *p_cbBuffer, (unsigned int *)&v121 + 1);
    ChannelBindings = updated;
    if ( updated < 0 )
    {
      v53 = "Failed to verify AP reply: 0x%x";
      v52 = 4089;
      goto LABEL_89;
    }
    goto LABEL_102;
  }
  v42 = (struct _RTL_CRITICAL_SECTION *)KerbLocateLogonSession(&v118, 0);
  v15 = (struct _KERB_LOGON_SESSION *)v42;
  v119 = (struct _KERB_LOGON_SESSION *)v42;
  if ( !v42 )
  {
LABEL_63:
    ChannelBindings = -1073741729;
    p_cbBuffer = 0;
    goto LABEL_56;
  }
  v43 = v42 + 2;
  RtlEnterCriticalSection(v42 + 2);
  if ( v40 )
  {
    ChannelBindings = KerbDuplicateStringEx(&v143, (const struct _UNICODE_STRING *)(*((_QWORD *)v116 + 9) + 16LL));
    if ( ChannelBindings < 0 )
      goto LABEL_70;
    v44 = (const struct _UNICODE_STRING *)*((_QWORD *)v116 + 9);
  }
  else
  {
    ChannelBindings = KerbDuplicateStringEx(&v143, (const struct _UNICODE_STRING *)((char *)v15 + 136));
    if ( ChannelBindings < 0 )
      goto LABEL_70;
    v44 = (const struct _UNICODE_STRING *)((char *)v15 + 120);
  }
  ChannelBindings = KerbDuplicateStringEx(&v144, v44);
LABEL_70:
  RtlLeaveCriticalSection(v43);
  if ( ChannelBindings < 0 )
  {
LABEL_90:
    v20 = SecurityImpersonation;
    goto LABEL_91;
  }
  v45 = KerbVerifyApRequest(
          &v109,
          *((_QWORD *)p_cbBuffer + 1),
          *p_cbBuffer,
          v11,
          v15,
          v116,
          &v126,
          &v125,
          &v120,
          v149,
          v153,
          v151,
          &v108,
          &v114,
          &v111,
          &v132,
          Src,
          v129[0],
          0);
  ChannelBindings = v45;
  if ( v45 != 280 && (v45 != -2146893042 || v111 != 69) )
  {
    if ( v45 < 0 )
    {
      KerbTracerT::Log(1, "SpAcceptLsaModeContext_Old", 3940, "Failed to verify AP request: 0x%x", v45);
      if ( v111 == 37 )
        KerbUpdateSkewTime(1u);
      goto LABEL_99;
    }
    if ( (v113 & 0x400000) != 0 )
      v108 |= 0x400000u;
    KerbUpdateSkewTime(0);
    v46 = v120;
    if ( v120 && (*(_BYTE *)v120 & 0x20) != 0 )
    {
      v47 = ASN1intxisuint32((char *)v120 + 104, v120);
      v48 = (char *)v120 + 104;
      if ( v47 )
        v49 = ASN1intx2uint32(v48);
      else
        v49 = ASN1intx2int32(v48);
      v50 = v49;
      v46 = v120;
    }
    else
    {
      v50 = 0;
    }
    updated = KerbCreateTokenFromTicketEx(
                (*((_DWORD *)v116 + 16) >> 25) & 1,
                0,
                (struct _UNICODE_STRING **)&v118,
                v126,
                (__int64)v125,
                (__int64)v46,
                v108,
                (__int64)v151,
                &v143,
                &v144,
                (struct _KERB_ENCRYPTION_KEY *)v149,
                (__int64)v109,
                &v118,
                &v130,
                &Handle,
                &DestinationString,
                &v139,
                &v145,
                (__int64)&v123,
                &v137);
    ChannelBindings = updated;
    if ( updated < 0 )
    {
      v52 = 4047;
LABEL_88:
      v53 = "Failed to create token from ticket: 0x%x";
LABEL_89:
      LODWORD(v106) = updated;
      KerbTracerT::Log(1, "SpAcceptLsaModeContext_Old", v52, v53, v106);
      goto LABEL_90;
    }
    updated = KerbUpdateServerContext(
                v109,
                v125,
                v126,
                (struct _KERB_ENCRYPTION_KEY *)v149,
                &v118,
                &v130,
                v108,
                v114,
                0,
                HIDWORD(v121),
                v50,
                &Handle,
                &DestinationString,
                &v139,
                &v145,
                &SystemTime);
    ChannelBindings = updated;
    if ( updated < 0 )
    {
      v53 = "Failed to create server context: 0x%x";
      v52 = 4072;
      goto LABEL_89;
    }
LABEL_102:
    v14 = v115;
    v20 = SecurityImpersonation;
    goto LABEL_103;
  }
  KerbTracerT::Log(1, "SpAcceptLsaModeContext_Old", 3932, "Won't allow user2user with Datagram");
  ChannelBindings = -2146893048;
  v111 = 40;
LABEL_99:
  LOWORD(v11) = v113;
  v20 = SecurityImpersonation;
LABEL_156:
  if ( !v32 || !v111 && (v11 & 0x8000) == 0 && (v108 & 0x4000) == 0 )
    goto LABEL_91;
  Src = 0;
  Size = 0;
  p_ChannelBindings = 0;
  v129[0] = 0;
  v113 = 0;
  if ( (v11 & 0x400) != 0 )
    goto LABEL_90;
  if ( ChannelBindings == -1073740965 )
    goto LABEL_90;
  if ( (v11 & 0x8000) == 0 )
  {
    v75 = (unsigned int)(v111 - 32);
    if ( (unsigned int)v75 > 0x25 )
      goto LABEL_90;
    v76 = 0x2000000223LL;
    if ( !_bittest64(&v76, v75) )
      goto LABEL_90;
  }
  if ( !v109 && (int)KerbCreateEmptyContext(v116, v108, v114, 0, &v118, &v109, &SystemTime) < 0 )
    goto LABEL_90;
  if ( v111 )
  {
    if ( v111 == 69 )
    {
      v77 = KerbBuildTgtErrorReply(v15, v116, v109, &v113, v129);
      KerbTracerT::Log(
        25,
        "SpAcceptLsaModeContext_Old",
        4757,
        "SpAcceptLsaModeContext called KerbBuildTgtErrorReply %#x\n",
        v77);
      if ( v77 == -1073740792 )
      {
        v111 = 67;
      }
      else if ( v77 < 0 )
      {
        KerbTracerT::Log(1, "SpAcceptLsaModeContext_Old", 4765, "Failed to build tgt error reply: 0x%x. Ignoring", v77);
      }
      p_ChannelBindings = v129[0];
    }
  }
  else
  {
    v111 = 60;
    p_ChannelBindings = (unsigned __int8 *)&ChannelBindings;
    v113 = 4;
  }
  v79 = KerbBuildGssErrorMessage(v111, p_ChannelBindings, v113, v109, &Size, (unsigned __int8 **)&Src);
  if ( p_ChannelBindings && p_ChannelBindings != (unsigned __int8 *)&ChannelBindings )
    KerbFree(p_ChannelBindings);
  if ( v79 < 0 )
    goto LABEL_90;
  v80 = Size;
  KerbTelemetry::KerbRecordMaxTokenSize((KerbTelemetry *)Size, v78);
  if ( (v11 & 0x100) != 0 )
  {
    v32->cbBuffer = v80;
    v32->pvBuffer = Src;
    v14 = v115;
    *v115 |= 0x100u;
  }
  else
  {
    if ( v32->cbBuffer < (unsigned int)v80 )
    {
      KerbTracerT::Log(
        1,
        "SpAcceptLsaModeContext_Old",
        4806,
        "Output token is too small - sent in %d, needed %d",
        v32->cbBuffer,
        v80);
      KerbReportBufferTooSmallError(v80, v32->cbBuffer, v109, 0);
      KerbFree(Src);
      v32->cbBuffer = v80;
      ChannelBindings = -1073741789;
      p_cbBuffer = &v122->cStrings;
      goto LABEL_56;
    }
    memcpy_0(v32->pvBuffer, Src, v80);
    v32->cbBuffer = v80;
    KerbFree(Src);
    v14 = v115;
  }
  *v14 |= 0x8000u;
  v81 = v117;
  *v117 = (unsigned __int64)v109;
  RtlSystemTimeToLocalTime(&SystemTime, LocalTime[0]);
  *v14 |= KerbMapContextFlags(v108);
  if ( v111 == 69 )
  {
    KerbTracerT::Log(
      25,
      "SpAcceptLsaModeContext_Old",
      4857,
      "SpInitLsaModeContext (TGT in error reply) USER2USER-INBOUND set\n");
    RtlAcquireResourceExclusive(&KerbContextResource, 1u);
    *((_DWORD *)v109 + 49) |= 0x10u;
    RtlReleaseResource(&KerbContextResource);
  }
  ChannelBindings = 590610;
  v20 = SecurityImpersonation;
  p_cbBuffer = &v122->cStrings;
  v21 = v110;
LABEL_219:
  if ( KerbEventTraceFlag )
  {
    v129[0] = (unsigned __int8 *)524296;
    v129[1] = (unsigned __int8 *)L"NONE";
    *(_OWORD *)LocalTime = 0;
    v84 = (unsigned __int8 **)((char *)v109 + 296);
    if ( v109 )
    {
      if ( *((_QWORD *)v109 + 41) )
      {
        RtlInitUnicodeString((PUNICODE_STRING)LocalTime, L"CredMan");
        v85 = *(unsigned __int8 ***)(*((_QWORD *)v109 + 41) + 64LL);
        goto LABEL_231;
      }
    }
    else
    {
      v84 = v129;
    }
    if ( v116 && *((_QWORD *)v116 + 9) )
    {
      RtlInitUnicodeString((PUNICODE_STRING)LocalTime, L"Supplied");
      v85 = (unsigned __int8 **)*((_QWORD *)v116 + 9);
    }
    else
    {
      if ( v109 )
      {
        RtlInitUnicodeString((PUNICODE_STRING)LocalTime, L"Context");
        v86 = (unsigned __int8 **)((char *)v109 + 72);
        v85 = (unsigned __int8 **)((char *)v109 + 56);
LABEL_233:
        v159 = &ChannelBindings;
        v160 = 4;
        v161 = LocalTime;
        v162 = 2;
        v163 = LocalTime[1];
        v164 = LOWORD(LocalTime[0]);
        v165 = v86;
        v166 = 2;
        v167 = v86[1];
        v168 = *(unsigned __int16 *)v86;
        v169 = v85;
        v170 = 2;
        v171 = v85[1];
        v172 = *(unsigned __int16 *)v85;
        v173 = v84;
        v174 = 2;
        v175 = v84[1];
        v176 = *(unsigned __int16 *)v84;
        v155[0] = 192;
        v157 = KerbAcceptSCGuid;
        v156 = 2;
        v158 = 1179648;
        EtwLogTraceEvent(KerbTraceLoggerHandle, v155);
        goto LABEL_234;
      }
      if ( !v15 )
      {
        RtlInitUnicodeString((PUNICODE_STRING)LocalTime, L"None");
        v86 = v129;
        v85 = v129;
        goto LABEL_233;
      }
      RtlInitUnicodeString((PUNICODE_STRING)LocalTime, L"LogonSession");
      v85 = (unsigned __int8 **)((char *)v15 + 120);
    }
LABEL_231:
    v86 = v85 + 2;
    goto LABEL_233;
  }
LABEL_234:
  if ( v125 && (*(_BYTE *)v125 & 0x20) != 0 )
    KerbGetClientNetbiosAddress(&v148, *((struct PKERB_HOST_ADDRESSES_s **)v125 + 19));
  v87 = v109;
  if ( v109 )
  {
    if ( ChannelBindings >= 0 )
    {
      RtlAcquireResourceExclusive(&KerbContextResource, 1u);
      if ( ChannelBindings )
      {
        if ( (*v14 & 0x8000) != 0 )
        {
          *((_DWORD *)v109 + 54) = 6;
        }
        else if ( !v112 )
        {
          *((_DWORD *)v109 + 54) = 4;
        }
      }
      else
      {
        *((_DWORD *)v109 + 54) = 5;
      }
    }
    else
    {
      if ( !v21 )
      {
        KerbReferenceContextByPointer(v109, 1u);
        KerbDereferenceContext(v109);
LABEL_249:
        v87 = v109;
        goto LABEL_250;
      }
      RtlAcquireResourceExclusive(&KerbContextResource, 1u);
      *((_DWORD *)v109 + 54) = 9;
    }
    RtlReleaseResource(&KerbContextResource);
    goto LABEL_249;
  }
LABEL_250:
  if ( !ChannelBindings && (v108 & 0x400) == 0 )
  {
    if ( v135 )
    {
      v88 = *((_DWORD *)v87 + 49);
      if ( (v88 & 0x4000) == 0 )
      {
        *((_DWORD *)v87 + 49) = v88 | 0x4000;
        *v14 |= 0x2000000u;
        v87 = v109;
      }
    }
    ChannelBindings = KerbGenerateOrVerifyMechlistMIC(v87, v146, v142);
    v87 = v109;
  }
  if ( v137.QuadPart && v87 )
  {
    *((union _LARGE_INTEGER *)v87 + 6) = v137;
    v87 = v109;
  }
  if ( !ChannelBindings )
  {
    ChannelBindings = KerbMapContext(v87, v138[0], v147);
    KerbTracerT::Log(
      3,
      "SpAcceptLsaModeContext_Old",
      5054,
      "SpAcceptLsaModeContext called KerbMapContext ContextAttributes %#x, %#x\n",
      *((_DWORD *)v109 + 49),
      ChannelBindings);
    v87 = v109;
  }
  if ( (v108 & 0x20000) != 0 )
  {
    v20 = SecurityIdentification;
  }
  else if ( (v108 & 1) != 0 )
  {
    v20 = SecurityDelegation;
  }
  if ( ChannelBindings )
  {
    v92 = ChannelBindings;
    if ( ChannelBindings >= 0 )
      goto LABEL_286;
    v138[0] = 0;
    v138[1] = 0;
    v93 = v138;
    v94 = v138;
    if ( v87 )
    {
      if ( *((_WORD *)v87 + 28) )
        v93 = (unsigned __int8 **)((char *)v87 + 56);
      if ( *((_WORD *)v87 + 36) )
        v94 = (unsigned __int8 **)((char *)v87 + 72);
      v95 = 3221225581LL;
    }
    else
    {
      p_DestinationString = (unsigned __int8 **)&DestinationString;
      if ( !DestinationString.Length )
        p_DestinationString = v138;
      v93 = p_DestinationString;
      v97 = (unsigned __int8 **)&v139;
      if ( !v139.Length )
        v97 = v138;
      v94 = v97;
      v95 = (unsigned int)ChannelBindings;
      v92 = 0;
    }
    ((void (__fastcall *)(__int64, _QWORD, unsigned __int8 **, unsigned __int8 **, unsigned __int64, _QWORD, int, enum _SECURITY_IMPERSONATION_LEVEL, struct _TOKEN_SOURCE *, struct _LUID *))LsaFunctions->AuditLogonEx)(
      v95,
      v92,
      v93,
      v94,
      (unsigned __int64)&v148 & -(__int64)(v148.Length != 0),
      0,
      3,
      v20,
      &KerberosSource,
      &v118);
  }
  else
  {
    if ( v123 )
    {
      v89 = MIDL_user_allocate(24LL * *(unsigned int *)(v123 + 16) + 16);
      p_cbBuffer = (unsigned int *)v89;
      if ( v89 )
      {
        v90 = (char *)(v89 + 2);
        *(_DWORD *)v89 = *(_DWORD *)(v123 + 16);
        v89[1] = v89 + 2;
        for ( i = 0; i < *(_DWORD *)(v123 + 16); ++i )
        {
          *(_DWORD *)v90 = 0;
          *((_WORD *)v90 + 4) = *(_WORD *)(*(_QWORD *)(v123 + 24) + 16LL * i);
          *((_WORD *)v90 + 5) = *(_WORD *)(*(_QWORD *)(v123 + 24) + 16LL * i + 2);
          *((_QWORD *)v90 + 2) = *(_QWORD *)(*(_QWORD *)(v123 + 24) + 16LL * i + 8);
          v90 += 24;
        }
      }
      v87 = v109;
    }
    KerbAuditLogon(ChannelBindings, ChannelBindings, v87, v20, &v148, &v118, (struct _LSA_ADT_STRING_LIST *)p_cbBuffer);
  }
  v87 = v109;
LABEL_286:
  if ( v87 )
    KerbDereferenceContext(v87);
  if ( v15 )
    KerbDereferenceLogonSession(v15);
  if ( v116 )
    KerbDereferenceCredential(v116);
  if ( v125 )
    KerbFreeData(51);
  if ( v120 )
    KerbFreeData(52);
  if ( v126 )
    KerbFreeData(53);
  if ( v136 )
    KerbFree(v136);
  KerbFreeKey(v149);
  KerbFreeKey(v151);
  if ( v130 )
    KerbFree(v130);
  if ( Handle )
  {
    KerbTracerT::Log(
      3,
      "SpAcceptLsaModeContext_Old",
      5239,
      "Closing token handle because context creation failed (%x)\n",
      ChannelBindings);
    NtClose(Handle);
  }
  if ( !v21 )
    LsaIModifyPerformanceCounter(1, 0, 0);
  KerbFreeKey(v153);
  KerbFreeString((__int64)&v143);
  KerbFreeString((__int64)&v144);
  KerbFreeString((__int64)&v139);
  KerbFreeString((__int64)&v145);
  KerbFreeString((__int64)&DestinationString);
  KerbFreeString((__int64)&v148);
  if ( p_cbBuffer )
    KerbFree(p_cbBuffer);
  if ( v123 )
    KerbFree(v123);
  v98 = ChannelBindings;
  if ( !ChannelBindings )
  {
    v99 = *v81;
    if ( *v81 )
    {
      v100 = *(struct _KERB_CREDENTIAL **)(v99 + 128);
      if ( v100 )
      {
        KerbDereferenceCredential(v100);
        *(_QWORD *)(v99 + 128) = 0;
        v98 = ChannelBindings;
      }
    }
  }
  if ( *v81 )
    v101 = (const void *)*((unsigned __int16 *)v81 + 1);
  else
    v101 = 0;
  KerbTracerT::Log(
    17,
    "SpAcceptLsaModeContext_Old",
    5284,
    "SpAcceptLsaModeContext returned 0x%x, Context %p, Pid 0x%x\n",
    v98,
    v101,
    Size_4);
  if ( v109 )
    v102 = (const void *)WORD1(v109);
  else
    v102 = 0;
  KerbTracerT::Log(
    7,
    "SpAcceptLsaModeContext_Old",
    5285,
    "SpAcceptLsaModeContext (%p) returned 0x%x\n",
    v102,
    ChannelBindings);
  KerbTracerT::CaptureLastStatus(ChannelBindings);
  v103 = ChannelBindings;
  KerbTracerT::~KerbTracerT((KerbTracerT *)v141);
  return v103;
}

```

## disassembly

```asm
0x18002db10  push    rbp
0x18002db12  push    rbx
0x18002db13  push    rsi
0x18002db14  push    rdi
0x18002db15  push    r12
0x18002db17  push    r13
0x18002db19  push    r14
0x18002db1b  push    r15
0x18002db1d  lea     rbp, [rsp-248h]
0x18002db25  sub     rsp, 368h
0x18002db2c  mov     rax, cs:__security_cookie
0x18002db33  xor     rax, rsp
0x18002db36  mov     [rbp+280h+var_50], rax
0x18002db3d  mov     r13d, r9d
0x18002db40  mov     [rbp+280h+var_2E0], r9d
0x18002db44  mov     [rbp+280h+var_1A8], r8
0x18002db4b  mov     rdi, rdx
0x18002db4e  mov     [rbp+280h+var_2F0], rdx
0x18002db52  mov     r12, rcx
0x18002db55  mov     r8, [rbp+280h+arg_50]; unsigned int
0x18002db5c  mov     [rbp+280h+var_1A0], r8
0x18002db63  mov     rax, [rbp+280h+arg_28]
0x18002db6a  mov     [rbp+280h+var_2C8], rax
0x18002db6e  mov     rax, [rbp+280h+arg_30]
0x18002db75  mov     [rbp+280h+var_1E0], rax
0x18002db7c  mov     rsi, [rbp+280h+arg_38]
0x18002db83  mov     [rbp+280h+var_2D8], rsi
0x18002db87  mov     rbx, [rbp+280h+arg_40]
0x18002db8e  mov     [rbp+280h+LocalTime], rbx
0x18002db92  mov     rax, [rbp+280h+arg_48]
0x18002db99  mov     [rbp+280h+var_218], rax
0x18002db9d  lea     rdx, aSpAcceptOld; "SP Accept OLD"
0x18002dba4  lea     rcx, [rbp+280h+var_1E8]; this
0x18002dbab  call    ??0KerbTracerT@@QEAA@PEBDK@Z; KerbTracerT::KerbTracerT(char const *,ulong)
0x18002dbb0  nop
0x18002dbb1  xor     ecx, ecx
0x18002dbb3  mov     r15d, ecx
0x18002dbb6  mov     [rbp+280h+var_2B8], rcx
0x18002dbba  mov     [rbp+280h+var_2D0], rcx
0x18002dbbe  mov     [rbp+280h+var_300], ecx
0x18002dbc1  mov     [rbp+280h+var_280], rcx
0x18002dbc5  mov     [rbp+280h+var_228], rcx
0x18002dbc9  mov     [rbp+280h+var_230], rcx
0x18002dbcd  mov     dword ptr [rbp+280h+var_2A8], ecx
0x18002dbd0  mov     qword ptr [rbp+280h+var_2C0.LowPart], rcx
0x18002dbd4  mov     [rbp+280h+var_288], rcx
0x18002dbd8  mov     [rbp+280h+var_2B0], rcx
0x18002dbdc  xorps   xmm0, xmm0
0x18002dbdf  xor     eax, eax
0x18002dbe1  movups  [rbp+280h+var_188], xmm0
0x18002dbe8  movups  [rbp+280h+var_178], xmm0
0x18002dbef  mov     [rbp+280h+var_168], rax
0x18002dbf6  xorps   xmm1, xmm1
0x18002dbf9  movups  [rbp+280h+var_138], xmm1
0x18002dc00  movups  [rbp+280h+var_128], xmm1
0x18002dc07  mov     [rbp+280h+var_118], rax
0x18002dc0e  movups  [rbp+280h+var_160], xmm0
0x18002dc15  movups  [rbp+280h+var_150], xmm0
0x18002dc1c  mov     [rbp+280h+var_140], rax
0x18002dc23  mov     [rbp+280h+var_2F8], rcx
0x18002dc27  mov     qword ptr [rbp+280h+SystemTime], rcx
0x18002dc2b  mov     [rbp+280h+Handle], rcx
0x18002dc2f  mov     [rbp+280h+var_2FC], ecx
0x18002dc32  mov     [rbp+280h+var_2DC], 4
0x18002dc39  mov     dword ptr [rbp+280h+var_2A8+4], ecx
0x18002dc3c  mov     [rbp+280h+var_258], rcx
0x18002dc40  mov     [rbp+280h+var_2E8], ecx
0x18002dc43  movups  xmmword ptr [rbp+280h+var_1D8.Length], xmm0
0x18002dc4a  movups  xmmword ptr [rbp+280h+var_1C8.Length], xmm1
0x18002dc51  movups  xmmword ptr [rbp+280h+var_1F8.Length], xmm0
0x18002dc58  movups  xmmword ptr [rbp+280h+var_208.Length], xmm1
0x18002dc5c  movups  xmmword ptr [rbp+280h+var_1B8.Length], xmm0
0x18002dc63  movups  xmmword ptr [rbp+280h+var_198.Length], xmm1
0x18002dc6a  mov     [rbp+280h+var_2E4], cl
0x18002dc6d  mov     dword ptr [rbp+280h+Size+4], ecx
0x18002dc70  mov     [rbp+280h+Src], rcx
0x18002dc74  mov     [rbp+280h+var_268], rcx
0x18002dc78  mov     [rbp+280h+var_298], rcx
0x18002dc7c  mov     r14d, ecx
0x18002dc7f  mov     [rbp+280h+var_2A0], rcx
0x18002dc83  mov     [rbp+280h+var_220], rcx
0x18002dc87  mov     [rbp+280h+var_240], ecx
0x18002dc8a  xor     edx, edx; Val
0x18002dc8c  mov     r8d, 0C0h; Size
0x18002dc92  lea     rcx, [rbp+280h+var_110]; void *
0x18002dc99  call    memset_0
0x18002dc9e  test    rdi, rdi
0x18002dca1  jz      short loc_18002DCB1
0x18002dca3  mov     rax, rdi
0x18002dca6  shr     rax, 10h
0x18002dcaa  movzx   ecx, ax
0x18002dcad  xor     edi, edi
0x18002dcaf  jmp     short loc_18002DCB4
0x18002dcb1  mov     rcx, rdi
0x18002dcb4  mov     [rsp+3A0h+var_380], rcx
0x18002dcb9  lea     r9, aSpacceptlsamod_6; "SpAcceptLsaModeContext %p called\n"
0x18002dcc0  mov     r8d, 0E17h
0x18002dcc6  lea     rdx, aSpacceptlsamod_22; "SpAcceptLsaModeContext_Old"
0x18002dccd  mov     ecx, 7
0x18002dcd2  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18002dcd7  cmp     cs:KerbEventTraceFlag, dil
0x18002dcde  jz      short loc_18002DD20
0x18002dce0  movups  xmm0, cs:KerbAcceptSCGuid
0x18002dce7  movdqu  [rbp+280h+var_F8], xmm0
0x18002dcef  mov     [rbp+280h+var_10C], 1
0x18002dcf6  mov     [rbp+280h+var_E4], 20000h
0x18002dd00  mov     eax, 30h ; '0'
0x18002dd05  mov     [rbp+280h+var_110], ax
0x18002dd0c  lea     rdx, [rbp+280h+var_110]
0x18002dd13  mov     rcx, cs:KerbTraceLoggerHandle
0x18002dd1a  call    cs:__imp_EtwLogTraceEvent
0x18002dd20  mov     [rsi], edi
0x18002dd22  mov     rax, [rbp+280h+var_2C8]
0x18002dd26  mov     [rax], rdi
0x18002dd29  mov     rax, cs:?KerbGlobalHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalHasNeverTime
0x18002dd30  mov     [rbx], rax
0x18002dd33  mov     rax, [rbp+280h+var_218]
0x18002dd37  mov     [rax], dil
0x18002dd3a  mov     rax, [rbp+280h+var_1A0]
0x18002dd41  mov     [rax+8], rdi
0x18002dd45  mov     [rax], edi
0x18002dd47  mov     edi, 2
0x18002dd4c  cmp     cs:?KerbGlobalInitialized@@3EA, r14b; uchar KerbGlobalInitialized
0x18002dd53  jnz     short loc_18002DD65
0x18002dd55  mov     [rbp+280h+var_300], 0C00000DCh
0x18002dd5c  mov     r12, [rbp+280h+var_2F0]
0x18002dd60  jmp     loc_18002F186
0x18002dd65  mov     rbx, [rbp+280h+var_1A8]
0x18002dd6c  cmp     [rbx+4], r14d
0x18002dd70  jbe     short loc_18002DD96
0x18002dd72  xor     ecx, ecx
0x18002dd74  mov     rdx, [rbx+8]
0x18002dd78  mov     r8d, ecx
0x18002dd7b  shl     r8, 4
0x18002dd7f  add     r8, rdx
0x18002dd82  mov     eax, [r8+4]
0x18002dd86  and     eax, 0FFFFFFFh
0x18002dd8b  cmp     eax, edi
0x18002dd8d  jz      short loc_18002DDC4
0x18002dd8f  inc     ecx
0x18002dd91  cmp     ecx, [rbx+4]
0x18002dd94  jb      short loc_18002DD78
0x18002dd96  mov     eax, [rbp+280h+var_300]
0x18002dd99  test    eax, eax
0x18002dd9b  jns     short loc_18002DDE5
0x18002dd9d  mov     dword ptr [rsp+3A0h+var_380], eax
0x18002dda1  lea     r9, aFailedToMapInp; "Failed to map Input token: 0x%x"
0x18002dda8  mov     r8d, 0E48h
0x18002ddae  mov     ecx, 1
0x18002ddb3  lea     rdx, aSpacceptlsamod_22; "SpAcceptLsaModeContext_Old"
0x18002ddba  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18002ddbf  jmp     loc_18002E41A
0x18002ddc4  mov     r14, r8
0x18002ddc7  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18002ddce  mov     rdx, r8
0x18002ddd1  mov     rcx, r8
0x18002ddd4  mov     rax, [rax+98h]
0x18002dddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dde0  mov     [rbp+280h+var_300], eax
0x18002dde3  jmp     short loc_18002DD99
0x18002dde5  lea     r8, [rbp+280h+Src]
0x18002dde9  mov     rdx, rbx
0x18002ddec  call    SspGetChannelBindings
0x18002ddf1  mov     [rbp+280h+var_300], eax
0x18002ddf4  test    eax, eax
0x18002ddf6  js      loc_18002E41A
0x18002ddfc  lea     r8, [rbp+280h+var_268]
0x18002de00  mov     rdx, [rbp+280h+var_1E0]
0x18002de07  call    SspGetChannelBindingsResult
0x18002de0c  mov     [rbp+280h+var_300], eax
0x18002de0f  test    eax, eax
0x18002de11  js      loc_18002E41A
0x18002de17  cmp     [rbx+4], r15d
0x18002de1b  jbe     short loc_18002DE64
0x18002de1d  xor     ecx, ecx
0x18002de1f  mov     rdx, [rbx+8]
0x18002de23  mov     r8d, ecx
0x18002de26  shl     r8, 4
0x18002de2a  add     r8, rdx
0x18002de2d  mov     eax, [r8+4]
0x18002de31  and     eax, 0FFFFFFFh
0x18002de36  cmp     eax, 0Bh
0x18002de39  jz      short loc_18002DE44
0x18002de3b  inc     ecx
0x18002de3d  cmp     ecx, [rbx+4]
0x18002de40  jb      short loc_18002DE23
0x18002de42  jmp     short loc_18002DE64
0x18002de44  mov     [rbp+280h+var_230], r8
0x18002de48  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18002de4f  mov     rdx, r8
0x18002de52  mov     rcx, r8
0x18002de55  mov     rax, [rax+98h]
0x18002de5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de61  mov     [rbp+280h+var_300], eax
0x18002de64  mov     r10d, [rbp+280h+var_300]
0x18002de68  test    r10d, r10d
0x18002de6b  jns     short loc_18002DE84
0x18002de6d  mov     dword ptr [rsp+3A0h+var_380], r10d
0x18002de72  lea     r9, aFailedToMapMec; "Failed to map Mechlist token: 0x%x"
0x18002de79  mov     r8d, 0E72h
0x18002de7f  jmp     loc_18002DDAE
0x18002de84  xor     ebx, ebx
0x18002de86  mov     r9, [rbp+280h+var_1E0]
0x18002de8d  cmp     [r9+4], ebx
0x18002de91  jbe     short loc_18002DED9
0x18002de93  xor     ecx, ecx
0x18002de95  mov     rdx, [r9+8]
0x18002de99  mov     r8d, ecx
0x18002de9c  shl     r8, 4
0x18002dea0  add     r8, rdx
0x18002dea3  mov     eax, [r8+4]
0x18002dea7  and     eax, 0FFFFFFFh
0x18002deac  cmp     eax, edi
0x18002deae  jz      short loc_18002DEBA
0x18002deb0  inc     ecx
0x18002deb2  cmp     ecx, [r9+4]
0x18002deb6  jb      short loc_18002DE99
0x18002deb8  jmp     short loc_18002DED9
0x18002deba  mov     rbx, r8
0x18002debd  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18002dec4  mov     rdx, r8
0x18002dec7  mov     rcx, r8
0x18002deca  mov     rax, [rax+98h]
0x18002ded1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ded6  mov     [rbp+280h+var_300], eax
0x18002ded9  mov     r10d, [rbp+280h+var_300]
0x18002dedd  test    r10d, r10d
0x18002dee0  jns     short loc_18002DEF9
0x18002dee2  mov     dword ptr [rsp+3A0h+var_380], r10d
0x18002dee7  lea     r9, aFailedToMapOut; "Failed to map output token: 0x%x"
0x18002deee  mov     r8d, 0E87h
0x18002def4  jmp     loc_18002DDAE
0x18002def9  mov     rax, [rbp+280h+var_2F0]
0x18002defd  test    rax, rax
0x18002df00  jz      loc_18002E073
0x18002df06  lea     r8, [rbp+280h+var_2F8]; struct _KERB_CONTEXT **
0x18002df0a  xor     edx, edx; unsigned __int8
0x18002df0c  mov     rcx, rax; struct _KERBEROS_LIST_ENTRY *
0x18002df0f  call    ?KerbReferenceContext@@YAJ_KEPEAPEAU_KERB_CONTEXT@@@Z; KerbReferenceContext(unsigned __int64,uchar,_KERB_CONTEXT * *)
0x18002df14  mov     [rbp+280h+var_300], eax
0x18002df17  mov     rax, [rbp+280h+var_2F8]
0x18002df1b  test    rax, rax
0x18002df1e  jnz     short loc_18002DF56
0x18002df20  mov     r12, [rbp+280h+var_2F0]
0x18002df24  mov     rax, r12
0x18002df27  shr     rax, 10h
0x18002df2b  movzx   eax, ax
0x18002df2e  mov     [rsp+3A0h+var_380], rax
0x18002df33  lea     r9, aFailedToRefere_0; "Failed to reference context %p."
0x18002df3a  mov     r8d, 0E9Ch
0x18002df40  lea     rdx, aSpacceptlsamod_22; "SpAcceptLsaModeContext_Old"
0x18002df47  mov     ecx, 1
0x18002df4c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18002df51  jmp     loc_18002E41E
0x18002df56  test    r14, r14
0x18002df59  jnz     short loc_18002DFCC
0x18002df5b  xor     r12d, r12d
0x18002df5e  cmp     [rbp+280h+var_230], r12
0x18002df62  jnz     short loc_18002DF90
0x18002df64  lea     r9, aSpacceptlsamod_15; "SpAcceptLsaModeContext trying to comple"...
0x18002df6b  mov     r8d, 0EA4h
0x18002df71  lea     rdx, aSpacceptlsamod_22; "SpAcceptLsaModeContext_Old"
0x18002df78  lea     ecx, [r14+1]
0x18002df7c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18002df81  mov     [rbp+280h+var_300], 80090308h
0x18002df88  mov     r14, r12
0x18002df8b  jmp     loc_18002DD5C
0x18002df90  mov     ecx, [rax+0D8h]
0x18002df96  cmp     ecx, 5
0x18002df99  jz      short loc_18002DFBF
0x18002df9b  mov     dword ptr [rsp+3A0h+var_380], ecx
0x18002df9f  lea     r9, aInvalidContext; "Invalid context state: %d"
0x18002dfa6  mov     r8d, 0EACh
0x18002dfac  lea     rdx, aSpacceptlsamod_22; "SpAcceptLsaModeContext_Old"
0x18002dfb3  mov     ecx, 1
0x18002dfb8  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18002dfbd  jmp     short loc_18002DF81
0x18002dfbf  mov     rax, [rax+70h]
0x18002dfc3  mov     qword ptr [rbp+280h+var_2C0.LowPart], rax
0x18002dfc7  jmp     loc_18002E54D
0x18002dfcc  mov     dl, 1; Wait
0x18002dfce  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18002dfd5  call    cs:__imp_RtlAcquireResourceShared
0x18002dfdb  mov     rcx, [rbp+280h+var_2F8]
0x18002dfdf  mov     r15d, [rcx+0D8h]
0x18002dfe6  lea     eax, [r15-2]
0x18002dfea  test    eax, 0FFFFFFF9h
0x18002dfef  jnz     short loc_18002E037
0x18002dff1  cmp     r15d, 8
0x18002dff5  jz      short loc_18002E037
0x18002dff7  mov     esi, [rcx+0C4h]
0x18002dffd  test    sil, 4
0x18002e001  jz      short loc_18002E037
0x18002e003  mov     eax, [rcx+0C0h]
0x18002e009  mov     [rbp+280h+var_2FC], eax
0x18002e00c  mov     rax, [rcx+70h]
0x18002e010  mov     qword ptr [rbp+280h+var_2C0.LowPart], rax
0x18002e014  mov     rdi, [rcx+80h]
0x18002e01b  mov     eax, [rcx+68h]
0x18002e01e  mov     dword ptr [rbp+280h+Size+4], eax
  ... truncated ...
```
