# SsprHandleAuthenticateMessage

- ea: `0x1800157b0`
- end: `0x1800182ff`
- name: `SsprHandleAuthenticateMessage`
- size: `11087`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014dc0`

## callees

- `0x180009e00`
- `0x18000a020`
- `0x18000ad30`
- `0x18000cba0`
- `0x180010ce0`
- `0x180010ef0`
- `0x1800112c0`
- `0x180011d10`
- `0x180012760`
- `0x180013660`
- `0x180014404`
- `0x18001451c`
- `0x1800157b0`
- `0x180018308`
- `0x18001a470`
- `0x18001f80c`
- `0x180021fa4`
- `0x180026760`
- `0x18002ed58`
- `0x18002ee3c`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x180030844`
- `0x18003509c`
- `0x18004d40c`
- `0x18004f528`
- `0x18004f734`
- `0x18004f788`
- `0x180050890`
- `0x1800511ec`
- `0x180051a98`
- `0x1800581a8`
- `0x18006bd68`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `NtlmShared!MsvpAvlGet` at `0x180016c64`
- `NtlmShared!MsvpAvlGet` at `0x180016c79`
- `NtlmShared!MsvpAvlGet` at `0x180016d3d`
- `NtlmShared!MsvpAvlGet` at `0x180016d58`
- `NtlmShared!MsvpAvlGet` at `0x180016d7b`
- `NtlmShared!MsvpAvlGet` at `0x180016c64`
- `NtlmShared!MsvpAvlGet` at `0x180016c79`
- `NtlmShared!MsvpAvlGet` at `0x180016d3d`
- `NtlmShared!MsvpAvlGet` at `0x180016d58`
- `NtlmShared!MsvpAvlGet` at `0x180016d7b`
- `NtlmShared!MsvpAvlGetTimestamp` at `0x180016af1`
- `NtlmShared!MsvpAvlGetTimestamp` at `0x180016af1`
- `NtlmShared!MsvpAvlGetFlags` at `0x180016d1c`
- `NtlmShared!MsvpAvlGetFlags` at `0x180016d1c`
- `ntdll!RtlLengthSid` at `0x1800173c6`
- `ntdll!RtlLengthSid` at `0x1800173c6`
- `ntdll!EtwLogTraceEvent` at `0x180016477`
- `ntdll!EtwLogTraceEvent` at `0x180016477`
- `ntdll!RtlOemStringToUnicodeString` at `0x180016312`
- `ntdll!RtlOemStringToUnicodeString` at `0x180016339`
- `ntdll!RtlOemStringToUnicodeString` at `0x180016358`
- `ntdll!RtlOemStringToUnicodeString` at `0x180016312`
- `ntdll!RtlOemStringToUnicodeString` at `0x180016339`
- `ntdll!RtlOemStringToUnicodeString` at `0x180016358`
- `ntdll!NtClose` at `0x180018095`
- `ntdll!NtClose` at `0x180018095`
- `ntdll!RtlFreeUnicodeString` at `0x1800180b1`
- `ntdll!RtlFreeUnicodeString` at `0x1800180c8`
- `ntdll!RtlFreeUnicodeString` at `0x1800180df`
- `ntdll!RtlFreeUnicodeString` at `0x1800180b1`
- `ntdll!RtlFreeUnicodeString` at `0x1800180c8`
- `ntdll!RtlFreeUnicodeString` at `0x1800180df`
- `ntdll!RtlEqualUnicodeString` at `0x180017b4a`
- `ntdll!RtlEqualUnicodeString` at `0x180017bc9`
- `ntdll!RtlEqualUnicodeString` at `0x180017b4a`
- `ntdll!RtlEqualUnicodeString` at `0x180017bc9`
- `ntdll!RtlInitString` at `0x180017213`
- `ntdll!RtlInitString` at `0x180017213`
- `ntdll!RtlInitUnicodeString` at `0x1800159c5`
- `ntdll!RtlInitUnicodeString` at `0x1800159d1`
- `ntdll!RtlInitUnicodeString` at `0x1800159dd`
- `ntdll!RtlInitUnicodeString` at `0x1800159c5`
- `ntdll!RtlInitUnicodeString` at `0x1800159d1`
- `ntdll!RtlInitUnicodeString` at `0x1800159dd`
- `LSASRV!LsaIAuditLogonEx` at `0x180017e51`
- `LSASRV!LsaIAuditLogonEx` at `0x180017e51`
- `LSASRV!LsaISetSupplementalTokenInfo` at `0x1800176c4`
- `LSASRV!LsaISetSupplementalTokenInfo` at `0x1800176c4`
- `LSASRV!LsaISetPackageAttrInLogonSession` at `0x180017390`
- `LSASRV!LsaISetPackageAttrInLogonSession` at `0x180017390`

## pseudocode

```c
__int64 __fastcall SsprHandleAuthenticateMessage(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        unsigned int a4,
        void *Src,
        unsigned int a6,
        __int64 a7,
        _DWORD *a8,
        _UNKNOWN ***a9,
        _DWORD *a10,
        _QWORD *a11,
        _OWORD *a12,
        _DWORD *a13,
        int *a14,
        void *a15,
        _DWORD *a16,
        _DWORD *a17,
        _DWORD *a18,
        SspTelemetry *a19)
{
  char *v20; // rsi
  unsigned __int8 v21; // r14
  unsigned __int32 v22; // r13d
  _QWORD *v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // r8
  char v26; // r15
  int v27; // eax
  int SessionKey; // edi
  _QWORD *v29; // rcx
  _UNKNOWN **v30; // rdx
  __int64 v31; // rdx
  unsigned int v32; // edi
  _DWORD *v33; // rbx
  char *Context; // rax
  _QWORD *v35; // r12
  __int64 v36; // rcx
  unsigned int v37; // edx
  _DWORD *v38; // r15
  _QWORD *v39; // rcx
  __int64 v40; // rdx
  int Message; // eax
  NtlmLogging *v42; // rdi
  _DWORD *v43; // r15
  int v44; // eax
  __int64 v45; // rax
  _QWORD *v46; // r11
  __int64 v47; // r11
  _WORD *v48; // r12
  _WORD *v49; // rbx
  unsigned int v50; // edx
  int v51; // eax
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // r9
  int v55; // ecx
  int v56; // eax
  unsigned int v57; // r12d
  __int64 v58; // rdx
  NtlmLogging *v59; // r13
  char *v60; // rbx
  __int128 v61; // xmm0
  __int64 v62; // rax
  __int64 v63; // r9
  __int64 v64; // r8
  __int64 v65; // rdx
  int v66; // eax
  __int64 v67; // r8
  __int64 i; // rdx
  char v69; // cl
  char v70; // al
  char v71; // cl
  __int64 v72; // rbx
  unsigned int v73; // r15d
  char v74; // dl
  __int64 v75; // rax
  __int64 v76; // rcx
  _DWORD *v77; // r15
  unsigned int v78; // ebx
  struct _MSV1_0_INTERACTIVE_LOGON *v79; // rax
  struct _MSV1_0_INTERACTIVE_LOGON *v80; // r13
  __int64 v81; // rdx
  unsigned int v82; // ebx
  __int64 v83; // rdi
  unsigned __int16 v84; // r12
  int v85; // ecx
  int v86; // ecx
  int v87; // eax
  unsigned __int16 v88; // cx
  __int64 v89; // rcx
  int v90; // eax
  unsigned int v91; // edx
  int *v92; // rbx
  unsigned int v93; // r15d
  __int64 v94; // rdi
  __int64 v95; // rax
  __int64 v96; // rdx
  int Flags; // eax
  __int64 v98; // rax
  __int64 v99; // rax
  _QWORD *v100; // rcx
  int v101; // edx
  const WCHAR *v102; // rdi
  void *LsaHeap; // rax
  int v104; // r8d
  int v105; // r9d
  __int64 v106; // rcx
  unsigned int v107; // edi
  unsigned int v108; // r12d
  struct _MSV1_0_INTERACTIVE_LOGON *v109; // rax
  unsigned int v110; // ebx
  int v111; // ecx
  int v112; // ecx
  int v113; // ecx
  int v114; // ecx
  struct _MSV1_0_INTERACTIVE_LOGON *v115; // rcx
  int v116; // eax
  struct _MSV1_0_INTERACTIVE_LOGON *v117; // rbx
  _DWORD *v118; // r13
  unsigned int v119; // eax
  int v120; // r8d
  int v121; // eax
  char *v122; // rbx
  ULONG v123; // eax
  const void *v124; // rdx
  unsigned int v125; // ebx
  int v126; // r8d
  int *v127; // r12
  size_t v128; // rbx
  unsigned int *v129; // rax
  HANDLE v130; // rbx
  int v131; // eax
  __int64 v132; // rax
  char v133; // r8
  __int64 j; // rdx
  char v135; // cl
  char v136; // al
  __int64 v137; // rdx
  bool v138; // zf
  __m128i v139; // xmm6
  struct _MSV1_0_INTERACTIVE_LOGON *v140; // rax
  char v141; // dl
  int *v142; // rcx
  char v143; // r8
  int v144; // eax
  char v145; // cl
  int v146; // ecx
  _DWORD *v147; // rbx
  __int64 v148; // rdx
  PUNICODE_STRING v149; // rdx
  const struct _SSP_CONTEXT *pbIV; // [rsp+28h] [rbp-E0h]
  int v152; // [rsp+30h] [rbp-D8h]
  __int64 v153; // [rsp+38h] [rbp-D0h]
  char *v154; // [rsp+40h] [rbp-C8h]
  HANDLE *p_Handle; // [rsp+60h] [rbp-A8h]
  char v156; // [rsp+88h] [rbp-80h]
  char v157; // [rsp+89h] [rbp-7Fh]
  char v158; // [rsp+8Ah] [rbp-7Eh]
  char v159; // [rsp+8Bh] [rbp-7Dh]
  unsigned int v160; // [rsp+98h] [rbp-70h]
  NTSTATUS Timestamp; // [rsp+9Ch] [rbp-6Ch]
  int v162[2]; // [rsp+A0h] [rbp-68h] BYREF
  size_t Size; // [rsp+A8h] [rbp-60h] BYREF
  struct _MSV1_0_INTERACTIVE_LOGON *v164; // [rsp+B0h] [rbp-58h]
  struct _MSV1_0_INTERACTIVE_LOGON *v165; // [rsp+B8h] [rbp-50h]
  __int64 v166; // [rsp+C0h] [rbp-48h] BYREF
  unsigned int *v167; // [rsp+C8h] [rbp-40h]
  _BYTE *v168; // [rsp+D0h] [rbp-38h]
  int v169; // [rsp+D8h] [rbp-30h] BYREF
  int v170; // [rsp+DCh] [rbp-2Ch] BYREF
  unsigned int v171; // [rsp+E0h] [rbp-28h]
  _DWORD *v172; // [rsp+E8h] [rbp-20h]
  BOOL v173; // [rsp+F0h] [rbp-18h]
  NtlmLogging *v174; // [rsp+F8h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+100h] [rbp-8h] BYREF
  LUID v176; // [rsp+108h] [rbp+0h] BYREF
  __int64 v177; // [rsp+110h] [rbp+8h]
  struct _UNICODE_STRING DestinationString; // [rsp+118h] [rbp+10h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+128h] [rbp+20h] BYREF
  struct _UNICODE_STRING v180; // [rsp+138h] [rbp+30h] BYREF
  _QWORD *v181; // [rsp+148h] [rbp+40h]
  __int64 v182; // [rsp+150h] [rbp+48h] BYREF
  PUNICODE_STRING v183; // [rsp+158h] [rbp+50h] BYREF
  __int64 v184; // [rsp+160h] [rbp+58h] BYREF
  __int128 v185; // [rsp+168h] [rbp+60h] BYREF
  void *v186; // [rsp+178h] [rbp+70h] BYREF
  int v187; // [rsp+180h] [rbp+78h]
  int v188; // [rsp+184h] [rbp+7Ch] BYREF
  int v189; // [rsp+188h] [rbp+80h]
  __int64 v190; // [rsp+190h] [rbp+88h] BYREF
  __int64 v191; // [rsp+198h] [rbp+90h] BYREF
  const wchar_t *v192; // [rsp+1A0h] [rbp+98h]
  __int128 v193; // [rsp+1A8h] [rbp+A0h] BYREF
  int *v194; // [rsp+1B8h] [rbp+B0h]
  void *v195; // [rsp+1C0h] [rbp+B8h] BYREF
  int v196; // [rsp+1C8h] [rbp+C0h] BYREF
  _DWORD *v197; // [rsp+1D0h] [rbp+C8h]
  _DWORD *v198; // [rsp+1D8h] [rbp+D0h]
  SspTelemetry *v199; // [rsp+1E0h] [rbp+D8h]
  __int128 v200; // [rsp+1E8h] [rbp+E0h] BYREF
  _QWORD *v201; // [rsp+1F8h] [rbp+F0h]
  _UNKNOWN ***v202; // [rsp+200h] [rbp+F8h]
  _OWORD *v203; // [rsp+208h] [rbp+100h]
  _DWORD *v204; // [rsp+210h] [rbp+108h]
  STRING v205; // [rsp+218h] [rbp+110h] BYREF
  STRING SourceString; // [rsp+228h] [rbp+120h] BYREF
  STRING v207; // [rsp+238h] [rbp+130h] BYREF
  __int128 v208; // [rsp+248h] [rbp+140h] BYREF
  __int64 v209; // [rsp+258h] [rbp+150h]
  struct _STRING v210; // [rsp+260h] [rbp+158h] BYREF
  struct _SECPKG_PRIMARY_CRED v211; // [rsp+278h] [rbp+170h] BYREF
  char v212[12]; // [rsp+348h] [rbp+240h] BYREF
  _OWORD Buf2[2]; // [rsp+354h] [rbp+24Ch] BYREF
  __int64 v214; // [rsp+374h] [rbp+26Ch]
  __int128 v215; // [rsp+3A8h] [rbp+2A0h] BYREF
  __int16 v216; // [rsp+3B8h] [rbp+2B0h] BYREF
  _BYTE v217[22]; // [rsp+3BAh] [rbp+2B2h] BYREF
  __int128 v218; // [rsp+3D0h] [rbp+2C8h]
  int v219; // [rsp+3E4h] [rbp+2DCh]
  int *v220; // [rsp+3E8h] [rbp+2E0h]
  int v221; // [rsp+3F0h] [rbp+2E8h]
  _QWORD *v222; // [rsp+3F8h] [rbp+2F0h]
  int v223; // [rsp+400h] [rbp+2F8h]
  _QWORD *v224; // [rsp+408h] [rbp+300h]
  int v225; // [rsp+410h] [rbp+308h]
  char *v226; // [rsp+418h] [rbp+310h]
  int v227; // [rsp+420h] [rbp+318h]
  struct _UNICODE_STRING *p_UnicodeString; // [rsp+428h] [rbp+320h]
  int v229; // [rsp+430h] [rbp+328h]
  PWSTR Buffer; // [rsp+438h] [rbp+330h]
  int Length; // [rsp+440h] [rbp+338h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+448h] [rbp+340h]
  int v233; // [rsp+450h] [rbp+348h]
  PWSTR v234; // [rsp+458h] [rbp+350h]
  int v235; // [rsp+460h] [rbp+358h]
  struct _UNICODE_STRING *v236; // [rsp+468h] [rbp+360h]
  int v237; // [rsp+470h] [rbp+368h]
  PWSTR v238; // [rsp+478h] [rbp+370h]
  int v239; // [rsp+480h] [rbp+378h]
  int v240; // [rsp+4E8h] [rbp+3E0h] BYREF
  char v241; // [rsp+4ECh] [rbp+3E4h]
  __int16 v242; // [rsp+4EDh] [rbp+3E5h]
  char v243; // [rsp+4EFh] [rbp+3E7h]
  int v244; // [rsp+4F0h] [rbp+3E8h]
  char v245; // [rsp+4F4h] [rbp+3ECh]
  __int16 v246; // [rsp+4F5h] [rbp+3EDh]
  char v247; // [rsp+4F7h] [rbp+3EFh]
  int v248; // [rsp+4F8h] [rbp+3F0h]
  char v249; // [rsp+4FCh] [rbp+3F4h]
  __int16 v250; // [rsp+4FDh] [rbp+3F5h]
  char v251; // [rsp+4FFh] [rbp+3F7h]
  int v252; // [rsp+500h] [rbp+3F8h]
  char v253; // [rsp+504h] [rbp+3FCh]
  __int16 v254; // [rsp+505h] [rbp+3FDh]
  char v255; // [rsp+507h] [rbp+3FFh]
  int v256; // [rsp+508h] [rbp+400h]
  char v257; // [rsp+50Ch] [rbp+404h]
  __int16 v258; // [rsp+50Dh] [rbp+405h]
  char v259; // [rsp+50Fh] [rbp+407h]
  char v260; // [rsp+510h] [rbp+408h] BYREF
  int v261[4]; // [rsp+518h] [rbp+410h] BYREF
  __int64 v262; // [rsp+528h] [rbp+420h]
  __int128 v263; // [rsp+538h] [rbp+430h] BYREF
  __int64 v264; // [rsp+548h] [rbp+440h]
  _BYTE v265[80]; // [rsp+558h] [rbp+450h] BYREF

  v197 = a8;
  v20 = 0;
  v21 = 0;
  v202 = a9;
  v22 = 0;
  v172 = a10;
  v203 = a12;
  v204 = a13;
  v186 = a15;
  v198 = a17;
  v171 = a3;
  v181 = a2;
  Timestamp = 0;
  *(_QWORD *)v162 = 0;
  v174 = 0;
  v184 = 0;
  v164 = 0;
  v165 = 0;
  v188 = 0;
  v166 = 0;
  v170 = 0;
  v191 = 0;
  v192 = 0;
  v177 = 0;
  v176 = 0;
  Handle = 0;
  v158 = 0;
  v195 = 0;
  v159 = 0;
  v182 = 0;
  v190 = 0;
  v183 = 0;
  v173 = 0;
  v168 = 0;
  v156 = 0;
  v199 = a19;
  Size = a4;
  v201 = a16;
  v194 = a14;
  SourceString = 0;
  v157 = 1;
  v207 = 0;
  v205 = 0;
  DestinationString = 0;
  UnicodeString = 0;
  v180 = 0;
  v215 = 0;
  v210 = 0;
  v263 = 0;
  *(_OWORD *)v261 = 0;
  memset_0(&v211, 0, sizeof(v211));
  v189 = 0;
  v200 = 0;
  v169 = 0;
  v167 = 0;
  v160 = 0;
  v216 = 0;
  memset_0(v217, 0, 0x12Eu);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
  *v172 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&UnicodeString, 0);
  RtlInitUnicodeString(&v180, 0);
  v23 = v186;
  *a14 = 0;
  *a16 = -1;
  a16[1] = 0x7FFFFFFF;
  *v23 = *(_QWORD *)a16;
  *v198 = 0;
  memset_0(&v211, 0, sizeof(v211));
  v24 = v181;
  if ( *v181 )
  {
    v33 = v197;
  }
  else
  {
    v159 = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
    v209 = 0;
    v208 = 0;
    if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v208) || (WORD4(v208) & 0x200) == 0 )
    {
      SessionKey = -1073741727;
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_39;
      v40 = 38;
      goto LABEL_56;
    }
    LOBYTE(v25) = 1;
    v26 = 0;
    v27 = SspCredentialReferenceCredentialEx(a1, 0, v25, &v195);
    SessionKey = v27;
    if ( v27 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      v30 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_427;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
        (unsigned int)v27);
      goto LABEL_426;
    }
    if ( a6 < 0xC )
    {
      v29 = WPP_GLOBAL_Control;
      v30 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v31 = 40;
LABEL_18:
      WPP_SF_(v29[2], v31, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
      v29 = WPP_GLOBAL_Control;
LABEL_19:
      SessionKey = -2146893048;
LABEL_427:
      if ( v195 )
      {
        SspCredentialDereferenceCredential(v195);
        v29 = WPP_GLOBAL_Control;
      }
      if ( v26 )
        goto LABEL_152;
      v35 = a11;
      goto LABEL_155;
    }
    v32 = v171;
    if ( (v171 & 0x100) != 0 )
    {
      v29 = WPP_GLOBAL_Control;
      v30 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
        v29 = WPP_GLOBAL_Control;
      }
      SessionKey = -1073741637;
      goto LABEL_427;
    }
    v33 = v197;
    if ( *v197 < 0x30u )
    {
      v29 = WPP_GLOBAL_Control;
      v30 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v31 = 42;
      goto LABEL_18;
    }
    Context = (char *)SspContextAllocateContext();
    *(_QWORD *)v162 = Context;
    v20 = Context;
    if ( !Context )
    {
      v29 = WPP_GLOBAL_Control;
      v30 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
        v29 = WPP_GLOBAL_Control;
      }
      SessionKey = -1073741801;
      goto LABEL_427;
    }
    SspContextDereferenceContext(Context);
    v184 = a7;
    *v181 = v20;
    *((_QWORD *)v20 + 11) = v195;
    v195 = 0;
    if ( !a7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
      SessionKey = -1073741801;
      goto LABEL_39;
    }
    *((_QWORD *)v20 + 12) = *(_QWORD *)a7;
    v37 = *(_DWORD *)(a7 + 8) & 0xFF000000;
    *((_DWORD *)v20 + 18) = 2;
    *((_DWORD *)v20 + 12) = 1;
    v22 = v37 != 0 ? _byteswap_ulong(v37) : 0;
    v24 = v181;
    v173 = v37 != 0;
    if ( (v32 & 0x200000) != 0 )
    {
      v38 = v172;
      *v172 |= 0x200000u;
      *((_DWORD *)v20 + 13) |= 0x200000u;
      goto LABEL_59;
    }
    v173 = v37 != 0;
  }
  v38 = v172;
LABEL_59:
  SessionKey = SspContextReferenceContext(*v24, 0, v162);
  if ( SessionKey < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
    v20 = *(char **)v162;
    goto LABEL_39;
  }
  v20 = *(char **)v162;
  if ( ((*(_DWORD *)(*(_QWORD *)v162 + 72LL) - 2) & 0xFFFFFFFD) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
    SessionKey = -2146893040;
    goto LABEL_39;
  }
  if ( (unsigned int)Size < 0x48 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
        (unsigned int)Size);
    goto LABEL_73;
  }
  Message = SspContextGetMessage(Src, (unsigned int)Size, 3, (char **)&v174);
  SessionKey = Message;
  if ( Message < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
        (unsigned int)Message);
    goto LABEL_39;
  }
  v42 = v174;
  if ( v159 )
    *((_DWORD *)v20 + 12) |= *((_DWORD *)v174 + 15);
  if ( *((_DWORD *)v20 + 18) == 4 )
  {
    memset_0(v212, 0, 0x58u);
    *v33 = 0;
    memset(Buf2, 0, sizeof(Buf2));
    v214 = 0;
    if ( !memcmp_0((char *)v42 + 12, Buf2, 0x28u) )
    {
      *v38 = 0x8000000;
      SessionKey = 0;
      v29 = WPP_GLOBAL_Control;
      v35 = a11;
LABEL_157:
      if ( v182 && (*(_WORD *)v182 || (*v38 & 0x100000) != 0) && !v156 )
      {
        v191 = 1048590;
        v192 = L"NTLM V2";
        *(_QWORD *)&v261[2] = L"NTLM V1";
        *(_QWORD *)v261 = 1048590;
        v55 = *((_DWORD *)v20 + 12);
        if ( (v55 & 0x40000030) != 0 )
        {
          v56 = 128;
          if ( (v55 & 0x80u) != 0 )
          {
            v56 = 40;
            if ( v55 < 0 )
              v56 = 56;
          }
        }
        else
        {
          v56 = 0;
        }
        if ( (*v198 & 0x3800) != 0 || (v142 = v261, (*((_DWORD *)v20 + 12) & 0x4000) != 0) )
          v142 = (int *)&v191;
        LODWORD(p_Handle) = v56;
        LODWORD(v154) = v160;
        LODWORD(v153) = 3;
        LsaIAuditLogonEx(0, 0, v182, v190, v183, v168, v153, v154, &v215, &v176, v142, p_Handle);
        v29 = WPP_GLOBAL_Control;
      }
      goto LABEL_43;
    }
    SessionKey = -2146893048;
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_39:
      v35 = a11;
      goto LABEL_40;
    }
    v40 = 49;
LABEL_56:
    WPP_SF_(v39[2], v40, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
    goto LABEL_39;
  }
  v43 = v20 + 48;
  if ( (v20[48] & 0x40) != 0 )
  {
    v44 = *((_DWORD *)v42 + 15);
    if ( (v44 & 0x40) == 0 )
    {
LABEL_73:
      SessionKey = -2146893048;
      goto LABEL_39;
    }
    *v43 = v44;
    if ( (v44 & 0x30) != 0 )
    {
      v44 |= 0x40000000u;
      *v43 = v44;
    }
    if ( (v44 & 0x80000) != 0 )
    {
      if ( (v44 & 0x80u) != 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
      }
      *v43 &= ~0x80u;
    }
    if ( (*((_DWORD *)v42 + 15) & 0x2000000) != 0 )
    {
      v45 = *((_QWORD *)v42 + 8);
      *((_QWORD *)v20 + 27) = v45;
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      {
LABEL_101:
        if ( (unsigned __int8)v20[223] >= 0xFu && (*v43 & 0x80080) == 0 )
        {
          if ( v46 != &WPP_GLOBAL_Control && (*((_BYTE *)v46 + 28) & 2) != 0 )
            WPP_SF_(v46[2], 53, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
          v189 = 1;
        }
        goto LABEL_107;
      }
      WPP_SF_iiiii(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
        *((_QWORD *)v42 + 8),
        (unsigned __int8)v45,
        (unsigned __int8)v20[217],
        *((unsigned __int16 *)v20 + 109),
        (unsigned __int8)v20[223]);
    }
    v46 = WPP_GLOBAL_Control;
    goto LABEL_101;
  }
LABEL_107:
  if ( !v159
    && !(unsigned int)SsprCheckMinimumSecurity(
                        *((unsigned int *)v42 + 15),
                        (unsigned int)NtLmGlobalMinimumServerSecurity) )
  {
    SessionKey = -2146893054;
    if ( (_UNKNOWN **)v47 != &WPP_GLOBAL_Control && (*(_BYTE *)(v47 + 28) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(v47 + 16), 54, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
    v262 = 0;
    *(_OWORD *)v261 = 0;
    if ( ((unsigned __int8 (__fastcall *)(int *))LsaFunctions->GetCallInfo)(v261) )
      SspLogMinimumSecurityFailure(
        (unsigned int)v261[0],
        (unsigned int)*v43,
        (unsigned int)NtLmGlobalMinimumServerSecurity,
        0);
    goto LABEL_39;
  }
  v48 = (_WORD *)((char *)v42 + 12);
  v21 = *(_BYTE *)v43 & 1;
  if ( !SspConvertRelativeToAbsolute((__int64)v42, Size, (unsigned __int16 *)v42 + 6, (__int64)v261, 0, 1) )
    goto LABEL_73;
  v49 = (_WORD *)((char *)v42 + 20);
  if ( !SspConvertRelativeToAbsolute((__int64)v42, Size, (unsigned __int16 *)v42 + 10, (__int64)&v263, 0, 1)
    || !SspConvertRelativeToAbsolute((__int64)v42, Size, (unsigned __int16 *)v42 + 14, (__int64)&SourceString, v21, 1)
    || !SspConvertRelativeToAbsolute((__int64)v42, Size, (unsigned __int16 *)v42 + 18, (__int64)&v207, v21, 1)
    || !SspConvertRelativeToAbsolute((__int64)v42, Size, (unsigned __int16 *)v42 + 22, (__int64)&v205, v21, 1)
    || (*v43 & 0x40000000) != 0
    && (!SspConvertRelativeToAbsolute((__int64)v42, Size, (unsigned __int16 *)v42 + 26, (__int64)&v191, 0, 1)
     || (*v43 & 0x4000) == 0 && !v192) )
  {
    goto LABEL_73;
  }
  if ( v21 )
  {
    DestinationString = (struct _UNICODE_STRING)SourceString;
    v180 = (struct _UNICODE_STRING)v205;
    UnicodeString = (struct _UNICODE_STRING)v207;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
    Timestamp = RtlOemStringToUnicodeString(&DestinationString, &SourceString, 1u);
    SessionKey = Timestamp;
    if ( Timestamp < 0
      || (Timestamp = RtlOemStringToUnicodeString(&UnicodeString, &v207, 1u), SessionKey = Timestamp, Timestamp < 0)
      || (Timestamp = RtlOemStringToUnicodeString(&v180, &v205, 1u), SessionKey = Timestamp, Timestamp < 0) )
    {
      v21 = 0;
      goto LABEL_39;
    }
  }
  if ( NtlmGlobalEventTraceFlag )
  {
    v217[2] = 0;
    v221 = 4;
    v216 = 208;
    v220 = &v196;
    v222 = v181;
    v224 = v181;
    p_UnicodeString = &UnicodeString;
    Buffer = UnicodeString.Buffer;
    Length = UnicodeString.Length;
    p_DestinationString = &DestinationString;
    v234 = DestinationString.Buffer;
    v235 = DestinationString.Length;
    v236 = &v180;
    v223 = 8;
    v225 = 8;
    v238 = v180.Buffer;
    v227 = 4;
    v229 = 2;
    v233 = 2;
    v237 = 2;
    v239 = v180.Length;
    v218 = NtlmAcceptGuid;
    v219 = 1179648;
    v196 = 3;
    v226 = v20 + 48;
    EtwLogTraceEvent(NtlmGlobalTraceLoggerHandle, &v216);
  }
  if ( (*v43 & 0x4000) != 0
    && *((_QWORD *)v20 + 10)
    && !DestinationString.Length
    && !UnicodeString.Length
    && !v180.Length
    && !*v49
    && !*v48 )
  {
    Handle = (HANDLE)*((_QWORD *)v20 + 10);
    *((_QWORD *)v20 + 10) = 0;
    v177 = 0x7FFFFFFFFFFFFFFFLL;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
    v50 = v171;
    if ( (v171 & 1) != 0 )
    {
      *v172 |= 1u;
      *((_DWORD *)v20 + 13) |= 1u;
    }
    *((_DWORD *)v20 + 72) |= 1u;
    v51 = SspVerifyAscChannelBindings((__int64)(v20 + 348), a18, v199, v50, (__int64)pbIV, v20[364] == 0, v20 + 348, 16);
    SessionKey = v51;
    if ( v51 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_152;
      v53 = 57;
      v54 = (unsigned int)v51;
LABEL_150:
      WPP_SF_Lq(v29[2], v53, v52, v54, v20);
      goto LABEL_151;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids, v20);
      v29 = WPP_GLOBAL_Control;
    }
    v57 = Size;
    if ( (unsigned int)Size < 0x58 )
    {
      if ( v29 == &WPP_GLOBAL_Control || (*((_BYTE *)v29 + 28) & 1) == 0 )
        goto LABEL_172;
      v58 = 59;
      goto LABEL_170;
    }
    v59 = v174;
    v60 = (char *)v174 + 72;
    v61 = *(_OWORD *)((char *)v174 + 72);
    v154 = (char *)v174 + 72;
    *(_OWORD *)((char *)v174 + 72) = 0;
    v62 = *((_QWORD *)v20 + 40);
    v63 = *((unsigned int *)v20 + 82);
    v64 = *((_QWORD *)v20 + 38);
    v65 = *((unsigned int *)v20 + 78);
    HIDWORD(v153) = HIDWORD(v59);
    v152 = v57;
    *(_OWORD *)v261 = v61;
    v66 = SsprMICHandshakeMessages(v20 + 104, v65, v64, v63, v62);
    Timestamp = v66;
    if ( v66 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      v30 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_172;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
        (unsigned int)v66);
      goto LABEL_171;
    }
    LOBYTE(v67) = 0;
    for ( i = 0; i != 16; ++i )
    {
      v69 = v60[i];
      v70 = *((_BYTE *)v261 + i);
      LOBYTE(v67) = v70 ^ v69 | v67;
    }
    if ( (_BYTE)v67 )
    {
      v29 = WPP_GLOBAL_Control;
      v30 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_172;
      v58 = 61;
      goto LABEL_170;
    }
    v30 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids, v20);
    *((_DWORD *)v20 + 72) |= 1u;
    v71 = 0;
    v72 = v177;
    v73 = 0;
    v74 = 1;
LABEL_392:
    if ( (*((_DWORD *)v59 + 15) & 0x8030) == 0 )
    {
      v157 = 0;
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_438;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
LABEL_437:
      v29 = WPP_GLOBAL_Control;
LABEL_438:
      v141 = v156;
      goto LABEL_439;
    }
    v157 = v74;
    if ( !v74 )
    {
      v157 = 0;
      goto LABEL_437;
    }
    v67 = (unsigned int)Timestamp;
    v160 = v73;
    v158 = v71;
    if ( (v169 & 2) == 0 )
    {
      v157 = v74;
      v158 = v71;
      v141 = v156;
      v29 = WPP_GLOBAL_Control;
      v160 = v73;
LABEL_439:
      if ( (v169 & 2) != 0 && !v141 )
      {
        if ( v29 == &WPP_GLOBAL_Control || (*((_BYTE *)v29 + 28) & 1) == 0 )
          goto LABEL_172;
        v58 = 98;
        goto LABEL_170;
      }
      goto LABEL_414;
    }
    if ( v57 >= 0x58 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
      v139 = *(__m128i *)((char *)v59 + 72);
      v154 = (char *)v59 + 72;
      *(_OWORD *)((char *)v59 + 72) = 0;
      HIDWORD(v153) = HIDWORD(v59);
      v152 = v57;
      Timestamp = SsprMICHandshakeMessages(
                    v20 + 104,
                    *((unsigned int *)v20 + 78),
                    *((_QWORD *)v20 + 38),
                    *((unsigned int *)v20 + 82),
                    *((_QWORD *)v20 + 40));
      v67 = (unsigned int)Timestamp;
      if ( Timestamp >= 0 )
      {
        if ( *((_QWORD *)v59 + 9) == v139.m128i_i64[0] && *((_QWORD *)v59 + 10) == _mm_srli_si128(v139, 8).m128i_u64[0] )
        {
          v140 = v164;
          *((_DWORD *)v20 + 72) |= 1u;
          v164 = v140;
          v160 = v73;
LABEL_414:
          v26 = 1;
          if ( !v166
            || !*(_WORD *)(v166 + 48)
            || RtlEqualUnicodeString((PCUNICODE_STRING)(v20 + 120), (PCUNICODE_STRING)(v166 + 48), 1u) )
          {
            goto LABEL_540;
          }
          if ( *((_QWORD *)v20 + 16) )
          {
            ((void (*)(void))LsaFunctions->FreePrivateHeap)();
            *((_QWORD *)v20 + 16) = 0;
            *((_WORD *)v20 + 61) = 0;
            *((_WORD *)v20 + 60) = 0;
          }
          SessionKey = NtLmDuplicateUnicodeString(v20 + 120, v166 + 48);
          if ( SessionKey >= 0 )
          {
LABEL_540:
            if ( !v170
              || !v211.DownlevelName.Length
              || RtlEqualUnicodeString((PCUNICODE_STRING)(v20 + 136), &v211.DownlevelName, 1u) )
            {
              goto LABEL_444;
            }
            if ( *((_QWORD *)v20 + 18) )
            {
              ((void (*)(void))LsaFunctions->FreePrivateHeap)();
              *((_QWORD *)v20 + 18) = 0;
              *((_WORD *)v20 + 69) = 0;
              *((_WORD *)v20 + 68) = 0;
            }
            SessionKey = NtLmDuplicateUnicodeString(v20 + 136, &v211.DownlevelName);
            if ( SessionKey >= 0 )
            {
LABEL_444:
              SspContextSetTimeStamp(v20, v72, v67);
              v35 = a11;
              SessionKey = 0;
              *a11 = SspContextGetTimeStamp();
              if ( v159 )
              {
                v30 = *v202;
                if ( *v202 )
                {
                  *v30 = (_UNKNOWN *)v176;
                  *((_DWORD *)v30 + 4) = *(_DWORD *)(v166 + 24);
                  *(_OWORD *)((char *)v30 + 20) = *(_OWORD *)(v166 + 28);
                  *(_UNKNOWN **)((char *)v30 + 36) = *(_UNKNOWN **)(v166 + 64);
                  v30[1] = *(_UNKNOWN **)(v166 + 8);
                }
                else
                {
                  SessionKey = -2146893056;
                }
              }
              else
              {
                *v197 = 0;
              }
              v29 = WPP_GLOBAL_Control;
              goto LABEL_153;
            }
LABEL_426:
            v29 = WPP_GLOBAL_Control;
            goto LABEL_427;
          }
LABEL_151:
          v29 = WPP_GLOBAL_Control;
          goto LABEL_152;
        }
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
          v29 = WPP_GLOBAL_Control;
        }
        SessionKey = -2146893048;
      }
      else
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
            (unsigned int)Timestamp);
          v29 = WPP_GLOBAL_Control;
          LODWORD(v67) = Timestamp;
        }
        SessionKey = v67;
      }
      v160 = v73;
      goto LABEL_152;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_172;
    v58 = 94;
LABEL_170:
    WPP_SF_(v29[2], v58, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
LABEL_171:
    v29 = WPP_GLOBAL_Control;
LABEL_172:
    SessionKey = -2146893048;
    goto LABEL_152;
  }
  *v43 &= ~0x4000u;
  if ( (unsigned int)NtLmGlobalBlockInbound >= 2 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
      v29 = WPP_GLOBAL_Control;
    }
    v75 = *((_QWORD *)v20 + 11);
    SessionKey = -2146893054;
    if ( v75 )
    {
      SspLogNTLMServerBlockedChallenge(*(unsigned int *)(v75 + 32), v75 + 24, 1);
      v29 = WPP_GLOBAL_Control;
    }
    goto LABEL_152;
  }
  if ( (unsigned int)NtLmGlobalAuditInbound >= 2 )
  {
    v76 = *((_QWORD *)v20 + 11);
    if ( v76 )
      SspLogNTLMServerBlockedChallenge(*(unsigned int *)(v76 + 32), v76 + 24, 0);
  }
  SessionKey = NtLmDuplicateUnicodeString(v20 + 136, &UnicodeString);
  if ( SessionKey < 0 )
    goto LABEL_151;
  SessionKey = NtLmDuplicateUnicodeString(v20 + 120, &DestinationString);
  if ( SessionKey < 0 )
    goto LABEL_151;
  v77 = 0;
  *(_QWORD *)&v193 = 0;
  if ( v173 )
  {
    v107 = (unsigned __int16)*v48
         + (((unsigned __int16)*v49 + 7) & 0xFFFFFFF8)
         + ((DestinationString.Length + v180.Length + UnicodeString.Length + 111) & 0xFFFFFFF8);
    v109 = (struct _MSV1_0_INTERACTIVE_LOGON *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocatePrivateHeap)(v107);
    v108 = 0;
    v165 = v109;
    if ( !v109 )
    {
      SessionKey = -1073741801;
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_152;
      v81 = 75;
      goto LABEL_203;
    }
    v109->MessageType = MsV1_0SubAuthLogon;
    *(_QWORD *)v162 = (char *)v109 + 104;
    v110 = (_DWORD)v109 + v107;
    SspContextCopyStringAbsolute(
      (_DWORD)v109,
      (_DWORD)v109 + 8,
      (unsigned int)&DestinationString,
      (_DWORD)v109 + v107,
      (__int64)v162);
    SspContextCopyStringAbsolute(v111, (_DWORD)v165 + 24, (unsigned int)&UnicodeString, v110, (__int64)v162);
    SspContextCopyStringAbsolute(v112, (_DWORD)v165 + 40, (unsigned int)&v180, v110, (__int64)v162);
    v113 = (int)v165;
    *(_QWORD *)&v165[1].MessageType = *((_QWORD *)v20 + 12);
    *(_QWORD *)v162 = (*(_QWORD *)v162 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
    SspContextCopyStringAbsolute(v113, v113 + 64, (unsigned int)v261, v110, (__int64)v162);
    *(_QWORD *)v162 = (*(_QWORD *)v162 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
    SspContextCopyStringAbsolute(v114, (_DWORD)v165 + 80, (unsigned int)&v263, v110, (__int64)v162);
    v115 = v165;
    v116 = 32;
    *(_DWORD *)&v165[1].Password.Length = 32;
    *(_DWORD *)(&v115[1].Password.MaximumLength + 1) = v22;
    if ( v159 )
    {
      v116 = *(_DWORD *)(v184 + 8) | 2;
      *(_DWORD *)&v115[1].Password.Length = v116;
    }
    if ( (*((_DWORD *)v20 + 13) & 0x200000) != 0 )
      v116 |= 0x800u;
    *(_DWORD *)&v115[1].Password.Length = v116 | 0x2040;
LABEL_297:
    v117 = v164;
    v118 = v20 + 48;
    if ( (*((_DWORD *)v20 + 12) & 0x80000) != 0 && *((_WORD *)v174 + 6) >= 8u )
      *(_DWORD *)&v164[1].Password.Length |= 0x80u;
    RtlInitString(&v210, 0);
    v215 = 0x207073536D4C744EuLL;
    *(_QWORD *)v162 = 0;
    *(_QWORD *)&v193 = 0;
    if ( v173 )
      v119 = LsaApLogonUserEx2(
               -1,
               Network,
               v165,
               (unsigned __int64)v165,
               v107,
               &v166,
               (__int64)&v188,
               &v176,
               (int *)&Size + 1,
               &v170,
               (__int64 *)v162,
               &v182,
               &v190,
               &v183,
               &v211,
               (unsigned __int8 **)&v193);
    else
      v119 = LsaApLogonUserEx2(
               -1,
               Network,
               v117,
               (unsigned __int64)v117,
               v108,
               &v166,
               (__int64)&v188,
               &v176,
               (int *)&Size + 1,
               &v170,
               (__int64 *)v162,
               &v182,
               &v190,
               &v183,
               &v211,
               (unsigned __int8 **)&v193);
    Timestamp = v119;
    v120 = v119;
    if ( (v119 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, v119, v119, v20);
        v120 = Timestamp;
      }
      v121 = -1073741276;
      SessionKey = v120;
      if ( v120 != -1073741276 )
      {
        v121 = v120;
        if ( v120 == -1073741714 )
          v121 = HIDWORD(Size);
      }
      *v194 = v121;
      goto LABEL_151;
    }
    if ( (Size & 0x8000000000000000uLL) != 0LL )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          77,
          WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
          HIDWORD(Size));
        v29 = WPP_GLOBAL_Control;
      }
      SessionKey = HIDWORD(Size);
      goto LABEL_152;
    }
    if ( v159 )
      LsaISetPackageAttrInLogonSession(&v176, 1, v119);
    if ( v170 )
    {
      v122 = *(char **)v162;
      v123 = RtlLengthSid(*(PSID *)(*(_QWORD *)v162 + 8LL));
      if ( v123 > 0x44 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
          v29 = WPP_GLOBAL_Control;
        }
        SessionKey = -2146893052;
        goto LABEL_152;
      }
      v124 = (const void *)*((_QWORD *)v122 + 1);
      v168 = v265;
      memcpy_0(v265, v124, v123);
    }
    else
    {
      *v172 |= 0x100000u;
      *((_DWORD *)v20 + 13) |= 0x100000u;
      *v118 |= 0x800u;
      v168 = NtLmGlobalAnonymousSid;
    }
    v125 = 2 - ((*v118 & 0x100000) != 0);
    v160 = v125;
    p_Handle = &Handle;
    HIDWORD(v154) = HIDWORD(v183);
    HIDWORD(v153) = 0;
    v152 = v162[0];
    Timestamp = ((__int64 (__fastcall *)(LUID *, __int128 *, __int64, _QWORD, int))LsaFunctions->CreateTokenEx)(
                  &v176,
                  &v215,
                  3,
                  v125,
                  v170);
    v126 = Timestamp;
    if ( Timestamp < 0 && !Handle )
    {
      ((void (__fastcall *)(LUID *, _UNKNOWN **, _QWORD))LsaFunctions->DeleteLogonSession)(
        &v176,
        v30,
        (unsigned int)Timestamp);
      v126 = Timestamp;
    }
    v127 = v194;
    if ( v126 == -1073741714 )
    {
      *v194 = HIDWORD(Size);
      goto LABEL_332;
    }
    *v194 = v126;
    if ( v126 < 0 )
    {
LABEL_332:
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
          (unsigned int)v126);
        v29 = WPP_GLOBAL_Control;
        v126 = Timestamp;
      }
      SessionKey = v126;
      goto LABEL_152;
    }
    if ( (Size & 0x8000000000000000uLL) != 0LL )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
          HIDWORD(Size));
        v29 = WPP_GLOBAL_Control;
      }
      SessionKey = HIDWORD(Size);
      v160 = v125;
      goto LABEL_152;
    }
    v158 = 1;
    if ( v77 )
    {
      LODWORD(v177) = *v77;
      v128 = (unsigned __int64)(unsigned int)v177 >> 16;
      v129 = (unsigned int *)((__int64 (__fastcall *)(size_t))LsaFunctions->AllocatePrivateHeap)(v128);
      v167 = v129;
      if ( !v129 )
      {
        SessionKey = -1073741801;
        goto LABEL_151;
      }
      memcpy_0(v129, v77 + 1, v128);
      if ( *v167 > WORD1(v177) )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
          v29 = WPP_GLOBAL_Control;
        }
        SessionKey = -2146893048;
        goto LABEL_152;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
          *v167,
          v167[1]);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
    }
    v130 = Handle;
    v131 = LsaISetSupplementalTokenInfo(&Handle, v167, 0);
    SessionKey = v131;
    if ( v131 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids,
          (unsigned int)v131);
        v29 = WPP_GLOBAL_Control;
      }
      goto LABEL_152;
    }
    if ( v130 != Handle )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_365;
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids, v130, Handle);
    }
    v29 = WPP_GLOBAL_Control;
LABEL_365:
    if ( !v159 && (*(_BYTE *)(v166 + 24) & 2) != 0 )
    {
      if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 )
      {
        WPP_SF_(v29[2], 89, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
        v29 = WPP_GLOBAL_Control;
      }
      SessionKey = -2146893044;
      goto LABEL_152;
    }
    v132 = v166;
    v73 = v160;
    if ( (*(_BYTE *)(v166 + 24) & 1) != 0 )
    {
      v156 = 1;
      v157 = 0;
      *v127 = -1073741724;
    }
    if ( (*(_DWORD *)(v132 + 24) & 0x3800) == 0 && !(_WORD)v263 && LOWORD(v261[0]) == 24 )
    {
      v263 = 0;
      v133 = 0;
      for ( j = 0; j != 16; ++j )
      {
        v135 = *(_BYTE *)(v166 + j + 28);
        v136 = *((_BYTE *)&v263 + j);
        v133 |= v136 ^ v135;
      }
      if ( !v133 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
        v157 = 0;
      }
    }
    v137 = v166;
    v72 = *(_QWORD *)(v166 + 8);
    *v201 = *(_QWORD *)(v166 + 16);
    *(_QWORD *)v186 = *(_QWORD *)(v137 + 8);
    *v198 = *(_DWORD *)(v137 + 24);
    v138 = (*v118 & 0x40000000) == 0;
    v59 = v174;
    if ( !v138 && *((_WORD *)v174 + 26) == 16 )
      *(_OWORD *)(v20 + 104) = *(_OWORD *)v192;
    SessionKey = SsprMakeSessionKey((int)v20, (int)v261, (int)v166 + 28, (int)v166 + 64, 0);
    if ( SessionKey >= 0 )
    {
      v74 = v157;
      if ( !v157 )
        goto LABEL_437;
      v57 = Size;
      v71 = 1;
      v158 = 1;
      goto LABEL_392;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_152;
    v81 = 92;
LABEL_203:
    WPP_SF_(v29[2], v81, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
    goto LABEL_151;
  }
  v78 = (((unsigned __int16)*v49 + 7) & 0xFFFFFFF8)
      + ((DestinationString.Length + v180.Length + UnicodeString.Length + 111) & 0xFFFFFFF8)
      + (unsigned __int16)*v48;
  LODWORD(v177) = v78;
  v79 = (struct _MSV1_0_INTERACTIVE_LOGON *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocatePrivateHeap)(v78);
  v164 = v79;
  v80 = v79;
  if ( !v79 )
  {
    SessionKey = -1073741801;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_152;
    v81 = 64;
    goto LABEL_203;
  }
  v79->MessageType = MsV1_0NetworkLogon;
  v187 = 0;
  *(_QWORD *)v162 = (char *)v79 + 104;
  v82 = (_DWORD)v79 + v78;
  v83 = 0;
  v84 = 0;
  SspContextCopyStringAbsolute(0, (_DWORD)v79 + 8, (unsigned int)&DestinationString, v82, (__int64)v162);
  SspContextCopyStringAbsolute(v85, (_DWORD)v80 + 24, (unsigned int)&UnicodeString, v82, (__int64)v162);
  SspContextCopyStringAbsolute(v86, (_DWORD)v80 + 40, (unsigned int)&v180, v82, (__int64)v162);
  *(_QWORD *)&v80[1].MessageType = *((_QWORD *)v20 + 12);
  *(_QWORD *)v162 = (*(_QWORD *)v162 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
  SspContextCopyStringAbsolute((unsigned int)v162, (_DWORD)v80 + 64, (unsigned int)&v263, v82, (__int64)v162);
  *(_QWORD *)v162 = (*(_QWORD *)v162 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
  SspContextCopyStringAbsolute((unsigned int)v162, (_DWORD)v80 + 80, (unsigned int)v261, v82, (__int64)v162);
  *(_DWORD *)&v80[1].Password.Length = 32;
  if ( v159 )
  {
    v87 = *(_DWORD *)(v184 + 8) | 2;
    *(_DWORD *)&v80[1].Password.Length = v87;
    if ( (*((_DWORD *)v20 + 13) & 0x200000) != 0 )
      v87 |= 0x800u;
  }
  else
  {
    v87 = 2080;
  }
  v88 = v263;
  *(_DWORD *)&v80[1].Password.Length = v87 | 0x2240;
  if ( v88 < 0x2Cu )
  {
    v100 = 0;
    goto LABEL_256;
  }
  v185 = 0;
  if ( *(_BYTE *)(*((_QWORD *)&v263 + 1) + 16LL) > 1u || !*(_BYTE *)(*((_QWORD *)&v263 + 1) + 17LL) )
  {
    SessionKey = -2146893048;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_152;
    v81 = 65;
    goto LABEL_203;
  }
  *((_QWORD *)&v185 + 1) = *((_QWORD *)&v263 + 1) + 44LL;
  LOWORD(v185) = v88 - 48;
  WORD1(v185) = v88 - 48;
  if ( v88 < 0x30u )
  {
    SessionKey = -2146893048;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_152;
    v81 = 66;
    goto LABEL_203;
  }
  if ( NtLmGlobalAllowLegacySrvCall && v159 )
  {
LABEL_238:
    Flags = MsvpAvlGetFlags(&v185, &v169);
    Timestamp = Flags;
    if ( Flags == -1073741275 )
    {
      v169 = 0;
    }
    else if ( Flags < 0 )
    {
      goto LABEL_245;
    }
    *(_QWORD *)&v193 = MsvpAvlGet(*((_QWORD *)&v185 + 1), 8, WORD1(v185));
    v98 = MsvpAvlGet(*((_QWORD *)&v185 + 1), 10, WORD1(v185));
    v83 = v98;
    if ( v98 )
      v187 = *(unsigned __int16 *)(v98 + 2);
    v99 = MsvpAvlGet(*((_QWORD *)&v185 + 1), 9, WORD1(v185));
    v100 = 0;
    v77 = (_DWORD *)v99;
    if ( v99 )
      v84 = *(_WORD *)(v99 + 2);
LABEL_256:
    if ( !v80->UserName.Length
      && !v80[1].LogonDomainName.Length
      && (!v80[1].UserName.Length || v80[1].UserName.Length == 1 && !*(_BYTE *)v80[1].UserName.Buffer) )
    {
      goto LABEL_287;
    }
    if ( v83 )
    {
      v101 = (unsigned __int16)v187;
      v100 = (_QWORD *)(v83 + 4);
    }
    else
    {
      v101 = 0;
    }
    SessionKey = SspVerifyAscChannelBindings((__int64)v100, a18, v199, v171, (__int64)pbIV, v83 != 0, v100, v101);
    if ( SessionKey < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_152;
      v53 = 72;
      v54 = (unsigned int)SessionKey;
      goto LABEL_150;
    }
    if ( v77 )
    {
      if ( !v84 || (v169 & 4) != 0 )
      {
        v102 = &::Src;
        v84 = 2;
      }
      else
      {
        v102 = (const WCHAR *)(v77 + 1);
      }
      LsaHeap = (void *)NtLmAllocateLsaHeap(v84);
      *((_QWORD *)v20 + 42) = LsaHeap;
      if ( !LsaHeap )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
          v29 = WPP_GLOBAL_Control;
        }
        SessionKey = -1073741801;
        goto LABEL_152;
      }
      memcpy_0(LsaHeap, v102, v84);
      *((_DWORD *)v20 + 86) = v84;
    }
    Flags = SspLookupChallenge(&v80[1], &v200);
    Timestamp = Flags;
    if ( Flags >= 0 )
    {
      v264 = 0;
      v263 = 0;
      if ( ((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v263) )
        MsvpReportRejectedLoopbackEvent((unsigned int)v263, &v200);
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v106 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        *(_QWORD *)&v261[2] = 8;
        *(_QWORD *)v261 = v80 + 1;
        WPP_SF_s_HEX_Z(v106, 8, v104, v105, (__int64)v261, (__int64)&v200);
        v29 = WPP_GLOBAL_Control;
      }
      SessionKey = -1073741715;
      goto LABEL_152;
    }
    if ( Flags == -1073741275 )
    {
LABEL_287:
      v77 = (_DWORD *)v193;
      v107 = 0;
      v108 = v177;
      goto LABEL_297;
    }
LABEL_245:
    SessionKey = Flags;
    goto LABEL_151;
  }
  v184 = 0;
  Timestamp = MsvpAvlGetTimestamp(&v185, &v184);
  if ( Timestamp || v184 != *((_QWORD *)v20 + 37) )
  {
    SessionKey = -2146893048;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_152;
    v81 = 67;
    goto LABEL_203;
  }
  v89 = *((_QWORD *)v20 + 40);
  v242 = 0;
  v243 = 0;
  v246 = 0;
  v247 = 0;
  v250 = 0;
  v251 = 0;
  v254 = 0;
  v255 = 0;
  v258 = 0;
  v259 = 0;
  v90 = *(_DWORD *)(v89 + 20);
  v240 = 1;
  v241 = 1;
  v244 = 2;
  v245 = 1;
  v248 = 3;
  v249 = 0;
  v252 = 4;
  v253 = 0;
  v256 = 5;
  v257 = 0;
  if ( (v90 & 0x800000) == 0 )
  {
    SessionKey = -2146893048;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_152;
    v81 = 68;
    goto LABEL_203;
  }
  v91 = *((_DWORD *)v20 + 82);
  v193 = 0;
  if ( !SspConvertRelativeToAbsolute(v89, v91, (unsigned __int16 *)(v89 + 40), (__int64)&v193, v90 & 1, 0) )
  {
    SessionKey = -2146893048;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_152;
    v81 = 69;
    goto LABEL_203;
  }
  v92 = &v240;
  while ( 1 )
  {
    v93 = *v92;
    v94 = MsvpAvlGet(*((_QWORD *)&v193 + 1), (unsigned int)*v92, WORD1(v193));
    v95 = MsvpAvlGet(*((_QWORD *)&v185 + 1), v93, WORD1(v185));
    if ( v95 )
      break;
    if ( *((_BYTE *)v92 + 4) )
    {
      SessionKey = -2146893048;
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v96 = 70;
LABEL_233:
        WPP_SF_d(v29[2], v96, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids, v93);
        goto LABEL_151;
      }
      goto LABEL_152;
    }
LABEL_237:
    v92 += 2;
    if ( v92 == (int *)&v260 )
      goto LABEL_238;
  }
  if ( v94
    && *(_WORD *)(v94 + 2) == *(_WORD *)(v95 + 2)
    && !memcmp_0((const void *)(v94 + 4), (const void *)(v95 + 4), *(unsigned __int16 *)(v94 + 2)) )
  {
    goto LABEL_237;
  }
  SessionKey = -2146893048;
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v96 = 71;
    goto LABEL_233;
  }
LABEL_152:
  v35 = a11;
LABEL_153:
  if ( v20 )
  {
    LODWORD(pbIV) = SessionKey;
    NtlmLogging::SspLogNTLMCServerResponse(
      v174,
      (const struct _AUTHENTICATE_MESSAGE *)(unsigned int)Size,
      v21,
      (int)v20,
      pbIV,
      v152);
    v29 = WPP_GLOBAL_Control;
  }
LABEL_155:
  if ( SessionKey >= 0 )
  {
    v38 = v172;
    goto LABEL_157;
  }
LABEL_40:
  v36 = (unsigned int)Timestamp;
  if ( Timestamp >= 0 )
    v36 = (unsigned int)SessionKey;
  LODWORD(v153) = 3;
  ((void (__fastcall *)(__int64, _QWORD, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, _QWORD, __int64, __int128 *, LUID *))LsaFunctions->AuditLogon)(
    v36,
    HIDWORD(Size),
    &UnicodeString,
    &DestinationString,
    &v180,
    0,
    v153,
    &v215,
    &v176);
  v29 = WPP_GLOBAL_Control;
LABEL_43:
  if ( v20 )
  {
    if ( SessionKey == -1073740781 && (unsigned __int8)v20[223] < 0xAu )
    {
      if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 2) != 0 )
        WPP_SF_(v29[2], 99, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
      SessionKey = -1073741724;
    }
    v143 = v159;
    v20[208] = 1;
    *((_DWORD *)v20 + 51) = SessionKey;
    v20[209] = v159;
    if ( SessionKey < 0 )
    {
      *((_DWORD *)v20 + 18) = 0;
    }
    else
    {
      *((_DWORD *)v20 + 18) = 4;
      *((_QWORD *)v20 + 10) = Handle;
      Handle = 0;
      *v203 = *(_OWORD *)(v20 + 104);
      if ( v189 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids);
          v143 = v159;
        }
        *((_DWORD *)v20 + 12) |= 0x80u;
      }
      v30 = (_UNKNOWN **)v172;
      if ( v157 )
      {
        v144 = *v172;
        if ( (v20[48] & 0x20) != 0 )
        {
          v144 |= 0x10u;
          *v172 = v144;
        }
        if ( (v20[48] & 0x10) != 0 )
        {
          v144 |= 0x2000Cu;
          *(_DWORD *)v30 = v144;
        }
        if ( (*((_DWORD *)v20 + 12) & 0x8030) != 0 )
        {
          v145 = v171;
          if ( (v171 & 4) != 0 )
          {
            v144 |= 4u;
            *(_DWORD *)v30 = v144;
          }
          if ( (v145 & 8) != 0 )
          {
            v144 |= 8u;
            *(_DWORD *)v30 = v144;
          }
        }
      }
      else
      {
        *((_DWORD *)v20 + 12) &= 0xFFFFFFCF;
        v144 = *(_DWORD *)v30;
      }
      if ( (*((_DWORD *)v20 + 12) & 0x100000) != 0 )
      {
        v144 |= 0x80000u;
        *(_DWORD *)v30 = v144;
      }
      v146 = *((_DWORD *)v20 + 12);
      if ( (v146 & 0x40) != 0 )
      {
        v144 |= 0x400u;
        *(_DWORD *)v30 = v144;
        v146 = *((_DWORD *)v20 + 12);
      }
      if ( (v171 & 0x200000) != 0 )
      {
        *(_DWORD *)v30 = v144 | 0x200000;
        v146 = *((_DWORD *)v20 + 12);
      }
      if ( (*((_DWORD *)v20 + 13) & 0x2000C) == 0x20000 )
      {
        *((_DWORD *)v20 + 12) |= 0x40u;
        v146 = *((_DWORD *)v20 + 12);
      }
      *v204 = v146;
    }
    if ( v143 )
    {
      if ( SessionKey < 0 )
      {
        v186 = 0;
        LOBYTE(v30) = 1;
        SspContextReferenceContext(*v181, v30, &v186);
        if ( v186 )
          SspContextDereferenceContext(v186);
      }
    }
    v147 = v172;
    *((_DWORD *)v20 + 14) = *v172 & 0xFFFFFEFF;
    *((_QWORD *)v20 + 8) = *v35;
    SspContextDereferenceContext(v20);
    v29 = WPP_GLOBAL_Control;
  }
  else
  {
    v147 = v172;
  }
  if ( v174 )
  {
    ((void (__fastcall *)(NtlmLogging *))LsaFunctions->FreePrivateHeap)(v174);
    v29 = WPP_GLOBAL_Control;
  }
  if ( v164 )
  {
    ((void (__fastcall *)(struct _MSV1_0_INTERACTIVE_LOGON *))LsaFunctions->FreePrivateHeap)(v164);
    v29 = WPP_GLOBAL_Control;
  }
  if ( v165 )
  {
    ((void (__fastcall *)(struct _MSV1_0_INTERACTIVE_LOGON *))LsaFunctions->FreePrivateHeap)(v165);
    v29 = WPP_GLOBAL_Control;
  }
  if ( v166 )
  {
    ((void (__fastcall *)(__int64))LsaFunctions->FreeLsaHeap)(v166);
    v29 = WPP_GLOBAL_Control;
  }
  if ( Handle && v158 )
  {
    NtClose(Handle);
    v29 = WPP_GLOBAL_Control;
  }
  if ( !v21 )
  {
    if ( DestinationString.Buffer )
    {
      RtlFreeUnicodeString(&DestinationString);
      v29 = WPP_GLOBAL_Control;
    }
    if ( UnicodeString.Buffer )
    {
      RtlFreeUnicodeString(&UnicodeString);
      v29 = WPP_GLOBAL_Control;
    }
    if ( v180.Buffer )
    {
      RtlFreeUnicodeString(&v180);
      v29 = WPP_GLOBAL_Control;
    }
  }
  if ( v182 )
  {
    if ( *(_QWORD *)(v182 + 8) )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    ((void (__fastcall *)(__int64))LsaFunctions->FreeLsaHeap)(v182);
    v29 = WPP_GLOBAL_Control;
  }
  v148 = v190;
  if ( v190 )
  {
    if ( *(_QWORD *)(v190 + 8) )
    {
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
      v148 = v190;
    }
    ((void (__fastcall *)(__int64))LsaFunctions->FreeLsaHeap)(v148);
    v29 = WPP_GLOBAL_Control;
  }
  v149 = v183;
  if ( v183 )
  {
    if ( v183->Buffer )
    {
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
      v149 = v183;
    }
    ((void (__fastcall *)(PUNICODE_STRING))LsaFunctions->FreeLsaHeap)(v149);
    v29 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)&v200 + 1) )
  {
    ((void (__fastcall *)(_QWORD))LsaFunctions->FreePrivateHeap)(*((_QWORD *)&v200 + 1));
    v29 = WPP_GLOBAL_Control;
  }
  if ( v211.DownlevelName.Buffer )
  {
    ((void (__fastcall *)(PWSTR))LsaFunctions->FreeLsaHeap)(v211.DownlevelName.Buffer);
    v29 = WPP_GLOBAL_Control;
  }
  if ( v211.DomainName.Buffer )
  {
    ((void (__fastcall *)(PWSTR))LsaFunctions->FreeLsaHeap)(v211.DomainName.Buffer);
    v29 = WPP_GLOBAL_Control;
  }
  if ( v211.UserSid )
  {
    ((void (__fastcall *)(PSID))LsaFunctions->FreeLsaHeap)(v211.UserSid);
    v29 = WPP_GLOBAL_Control;
  }
  if ( v211.LogonServer.Buffer )
  {
    ((void (__fastcall *)(PWSTR))LsaFunctions->FreeLsaHeap)(v211.LogonServer.Buffer);
    v29 = WPP_GLOBAL_Control;
  }
  if ( v167 )
  {
    ((void (__fastcall *)(unsigned int *))LsaFunctions->FreePrivateHeap)(v167);
    v29 = WPP_GLOBAL_Control;
  }
  if ( SessionKey < 0 )
  {
    *v147 |= 0x4000u;
    v29 = WPP_GLOBAL_Control;
  }
  if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x200) != 0 )
    WPP_SF_d(v29[2], 101, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids, (unsigned int)SessionKey);
  return (unsigned int)SessionKey;
}

```

## disassembly

```asm
0x1800157b0  mov     rax, rsp
0x1800157b3  push    rbp
0x1800157b4  push    rbx
0x1800157b5  push    rsi
0x1800157b6  push    rdi
0x1800157b7  push    r12
0x1800157b9  push    r13
0x1800157bb  push    r14
0x1800157bd  push    r15
0x1800157bf  lea     rbp, [rax-508h]
0x1800157c6  sub     rsp, 5C8h
0x1800157cd  movaps  xmmword ptr [rax-58h], xmm6
0x1800157d1  mov     rax, cs:__security_cookie
0x1800157d8  xor     rax, rsp
0x1800157db  mov     [rbp+500h+var_60], rax
0x1800157e2  mov     rax, [rbp+500h+arg_38]
0x1800157e9  xorps   xmm0, xmm0
0x1800157ec  mov     r15, [rbp+500h+arg_78]
0x1800157f3  xorps   xmm1, xmm1
0x1800157f6  mov     rdi, [rbp+500h+arg_68]
0x1800157fd  mov     rbx, rcx
0x180015800  mov     r12, [rbp+500h+Src]
0x180015807  xor     ecx, ecx
0x180015809  mov     [rbp+500h+var_438], rax
0x180015810  mov     esi, ecx
0x180015812  mov     rax, [rbp+500h+arg_40]
0x180015819  mov     r14b, cl
0x18001581c  mov     [rbp+500h+var_408], rax
0x180015823  mov     r13d, ecx
0x180015826  mov     rax, [rbp+500h+arg_48]
0x18001582d  mov     [rbp+500h+var_520], rax
0x180015831  mov     rax, [rbp+500h+arg_50]
0x180015838  mov     [rbp+500h+var_578], rax
0x18001583c  mov     rax, [rbp+500h+arg_58]
0x180015843  mov     [rbp+500h+var_400], rax
0x18001584a  mov     rax, [rbp+500h+arg_60]
0x180015851  mov     [rbp+500h+var_3F8], rax
0x180015858  mov     rax, [rbp+500h+arg_70]
0x18001585f  mov     [rbp+500h+var_490], rax
0x180015863  mov     rax, [rbp+500h+arg_80]
0x18001586a  mov     [rbp+500h+var_430], rax
0x180015871  mov     rax, [rbp+500h+arg_90]
0x180015878  mov     [rbp+500h+var_528], r8d
0x18001587c  mov     r8d, 0C8h; Size
0x180015882  mov     [rbp+500h+var_4C0], rdx
0x180015886  xor     edx, edx; Val
0x180015888  mov     [rbp+500h+var_56C], ecx
0x18001588b  mov     qword ptr [rbp+500h+var_568], rcx
0x18001588f  mov     [rbp+500h+var_510], rcx
0x180015893  mov     [rbp+500h+var_4A8], rcx
0x180015897  mov     [rbp+500h+var_558], rcx
0x18001589b  mov     [rbp+500h+var_550], rcx
0x18001589f  mov     [rbp+500h+var_484], ecx
0x1800158a2  mov     [rbp+500h+var_548], rcx
0x1800158a6  mov     [rbp+500h+var_52C], ecx
0x1800158a9  mov     [rbp+500h+var_470], rcx
0x1800158b0  mov     [rbp+500h+var_468], rcx
0x1800158b7  mov     [rbp+500h+var_4F8], rcx
0x1800158bb  mov     [rbp+500h+var_500], rcx
0x1800158bf  mov     [rbp+500h+Handle], rcx
0x1800158c3  mov     [rbp+500h+var_57E], cl
0x1800158c6  mov     dword ptr [rbp+500h+Size+4], ecx
0x1800158c9  mov     [rbp+500h+var_448], rcx
0x1800158d0  mov     [rbp+500h+var_57D], cl
0x1800158d3  mov     [rbp+500h+var_4B8], rcx
0x1800158d7  mov     [rbp+500h+var_478], rcx
0x1800158de  mov     [rbp+500h+var_4B0], rcx
0x1800158e2  mov     [rbp+500h+var_518], ecx
0x1800158e5  mov     [rbp+500h+var_538], rcx
0x1800158e9  mov     [rbp+500h+var_580], cl
0x1800158ec  lea     rcx, [rbp+500h+var_390]; void *
0x1800158f3  mov     [rbp+500h+var_428], rax
0x1800158fa  mov     dword ptr [rbp+500h+Size], r9d
0x1800158fe  mov     [rbp+500h+var_410], r15
0x180015905  mov     [rbp+500h+var_450], rdi
0x18001590c  movups  xmmword ptr [rbp+500h+SourceString.Length], xmm0
0x180015913  mov     [rbp+500h+var_57F], 1
0x180015917  movups  xmmword ptr [rbp+500h+var_3D0.Length], xmm1
0x18001591e  movups  xmmword ptr [rbp+500h+var_3F0.Length], xmm0
0x180015925  movups  xmmword ptr [rbp+500h+DestinationString.Length], xmm0
0x180015929  movups  xmmword ptr [rbp+500h+UnicodeString.Length], xmm1
0x18001592d  movups  xmmword ptr [rbp+500h+var_4D0.Length], xmm0
0x180015931  movdqu  [rbp+500h+var_260], xmm0
0x180015939  movups  xmmword ptr [rbp+500h+var_3A8.Length], xmm0
0x180015940  movups  [rbp+500h+var_D0], xmm0
0x180015947  movups  xmmword ptr [rbp+500h+var_F0], xmm1
0x18001594e  call    memset_0
0x180015953  xor     eax, eax
0x180015955  xorps   xmm0, xmm0
0x180015958  mov     [rbp+500h+var_480], eax
0x18001595e  xor     edx, edx; Val
0x180015960  movups  [rbp+500h+var_420], xmm0
0x180015967  mov     [rbp+500h+var_530], eax
0x18001596a  mov     [rbp+500h+var_540], rax
0x18001596e  mov     [rbp+500h+var_570], eax
0x180015971  mov     [rbp+500h+var_250], ax
0x180015978  mov     r8d, 12Eh; Size
0x18001597e  lea     rcx, [rbp+500h+var_24E]; void *
0x180015985  call    memset_0
0x18001598a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015991  lea     rax, WPP_GLOBAL_Control
0x180015998  cmp     rcx, rax
0x18001599b  jz      short loc_1800159B9
0x18001599d  test    dword ptr [rcx+1Ch], 200h
0x1800159a4  jz      short loc_1800159B9
0x1800159a6  mov     rcx, [rcx+10h]
0x1800159aa  lea     edx, [rsi+24h]
0x1800159ad  lea     r8, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids
0x1800159b4  call    WPP_SF_
0x1800159b9  mov     rax, [rbp+500h+var_520]
0x1800159bd  lea     rcx, [rbp+500h+DestinationString]; DestinationString
0x1800159c1  xor     edx, edx; SourceString
0x1800159c3  mov     [rax], esi
0x1800159c5  call    cs:__imp_RtlInitUnicodeString
0x1800159cb  xor     edx, edx; SourceString
0x1800159cd  lea     rcx, [rbp+500h+UnicodeString]; DestinationString
0x1800159d1  call    cs:__imp_RtlInitUnicodeString
0x1800159d7  xor     edx, edx; SourceString
0x1800159d9  lea     rcx, [rbp+500h+var_4D0]; DestinationString
0x1800159dd  call    cs:__imp_RtlInitUnicodeString
0x1800159e3  mov     rcx, [rbp+500h+var_490]
0x1800159e7  xor     edx, edx; Val
0x1800159e9  mov     [rdi], esi
0x1800159eb  mov     r8d, 0C8h; Size
0x1800159f1  mov     dword ptr [r15], 0FFFFFFFFh
0x1800159f8  xor     edi, edi
0x1800159fa  mov     dword ptr [r15+4], 7FFFFFFFh
0x180015a02  mov     rax, [r15]
0x180015a05  mov     [rcx], rax
0x180015a08  lea     rcx, [rbp+500h+var_390]; void *
0x180015a0f  mov     rax, [rbp+500h+var_430]
0x180015a16  mov     [rax], edi
0x180015a18  call    memset_0
0x180015a1d  mov     rcx, [rbp+500h+var_4C0]
0x180015a21  cmp     [rcx], rdi
0x180015a24  jnz     loc_180015DC1
0x180015a2a  lea     r13d, [rdi+1]
0x180015a2e  mov     [rbp+500h+var_57D], r13b
0x180015a32  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a39  lea     r15, WPP_GLOBAL_Control
0x180015a40  cmp     rcx, r15
0x180015a43  jz      short loc_180015A61
0x180015a45  test    dword ptr [rcx+1Ch], 200h
0x180015a4c  jz      short loc_180015A61
0x180015a4e  mov     rcx, [rcx+10h]
0x180015a52  lea     edx, [rdi+25h]
0x180015a55  lea     r8, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids
0x180015a5c  call    WPP_SF_
0x180015a61  xor     eax, eax
0x180015a63  lea     rcx, [rbp+500h+var_3C0]
0x180015a6a  mov     [rbp+500h+var_3B0], rax
0x180015a71  xorps   xmm0, xmm0
0x180015a74  mov     rax, cs:LsaFunctions
0x180015a7b  movups  [rbp+500h+var_3C0], xmm0
0x180015a82  mov     rax, [rax+0C0h]
0x180015a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a8e  test    al, al
0x180015a90  jz      loc_180015D88
0x180015a96  test    dword ptr [rbp+500h+var_3C0+8], 200h
0x180015aa0  jz      loc_180015D88
0x180015aa6  lea     r9, [rbp+500h+var_448]
0x180015aad  mov     r8b, r13b
0x180015ab0  xor     edx, edx
0x180015ab2  mov     rcx, rbx
0x180015ab5  mov     r15b, dil
0x180015ab8  call    SspCredentialReferenceCredentialEx
0x180015abd  mov     edi, eax
0x180015abf  test    eax, eax
0x180015ac1  jns     short loc_180015B01
0x180015ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180015aca  lea     rdx, WPP_GLOBAL_Control
0x180015ad1  cmp     rcx, rdx
0x180015ad4  jz      loc_180017C29
0x180015ada  test    byte ptr [rcx+1Ch], 1
0x180015ade  jz      loc_180017C29
0x180015ae4  mov     rcx, [rcx+10h]
0x180015ae8  lea     r8, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids
0x180015aef  mov     edx, 27h ; '''
0x180015af4  mov     r9d, eax
0x180015af7  call    WPP_SF_d
0x180015afc  jmp     loc_180017C22
0x180015b01  cmp     [rbp+500h+arg_28], 0Ch
0x180015b08  jnb     short loc_180015B49
0x180015b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b11  lea     rdx, WPP_GLOBAL_Control
0x180015b18  cmp     rcx, rdx
0x180015b1b  jz      short loc_180015B3F
0x180015b1d  test    byte ptr [rcx+1Ch], 1
0x180015b21  jz      short loc_180015B3F
0x180015b23  mov     edx, 28h ; '('
0x180015b28  mov     rcx, [rcx+10h]
0x180015b2c  lea     r8, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids
0x180015b33  call    WPP_SF_
0x180015b38  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b3f  mov     edi, 80090308h
0x180015b44  jmp     loc_180017C29
0x180015b49  mov     edi, [rbp+500h+var_528]
0x180015b4c  bt      edi, 8
0x180015b50  jnb     short loc_180015B91
0x180015b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b59  lea     rdx, WPP_GLOBAL_Control
0x180015b60  cmp     rcx, rdx
0x180015b63  jz      short loc_180015B87
0x180015b65  test    byte ptr [rcx+1Ch], 1
0x180015b69  jz      short loc_180015B87
0x180015b6b  mov     rcx, [rcx+10h]
0x180015b6f  lea     r8, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids
0x180015b76  mov     edx, 29h ; ')'
0x180015b7b  call    WPP_SF_
0x180015b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b87  mov     edi, 0C00000BBh
0x180015b8c  jmp     loc_180017C29
0x180015b91  mov     rbx, [rbp+500h+var_438]
0x180015b98  cmp     dword ptr [rbx], 30h ; '0'
0x180015b9b  jnb     short loc_180015BC0
0x180015b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ba4  lea     rdx, WPP_GLOBAL_Control
0x180015bab  cmp     rcx, rdx
0x180015bae  jz      short loc_180015B3F
0x180015bb0  test    byte ptr [rcx+1Ch], 1
0x180015bb4  jz      short loc_180015B3F
0x180015bb6  mov     edx, 2Ah ; '*'
0x180015bbb  jmp     loc_180015B28
0x180015bc0  call    SspContextAllocateContext
0x180015bc5  mov     qword ptr [rbp+500h+var_568], rax
0x180015bc9  mov     rsi, rax
0x180015bcc  test    rax, rax
0x180015bcf  jnz     short loc_180015C0E
0x180015bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bd8  lea     rdx, WPP_GLOBAL_Control
0x180015bdf  cmp     rcx, rdx
0x180015be2  jz      short loc_180015C04
0x180015be4  test    byte ptr [rcx+1Ch], 1
0x180015be8  jz      short loc_180015C04
0x180015bea  mov     rcx, [rcx+10h]
0x180015bee  lea     edx, [rax+2Bh]
0x180015bf1  lea     r8, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids
0x180015bf8  call    WPP_SF_
0x180015bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c04  mov     edi, 0C0000017h
0x180015c09  jmp     loc_180017C29
0x180015c0e  mov     rcx, rsi; void *
0x180015c11  call    SspContextDereferenceContext
0x180015c16  mov     rax, [rbp+500h+var_4C0]
0x180015c1a  xor     r8d, r8d
0x180015c1d  mov     r15, [rbp+500h+arg_30]
0x180015c24  mov     [rbp+500h+var_4A8], r15
0x180015c28  mov     [rax], rsi
0x180015c2b  mov     rax, [rbp+500h+var_448]
0x180015c32  mov     [rsi+58h], rax
0x180015c36  mov     [rbp+500h+var_448], r8
0x180015c3d  test    r15, r15
0x180015c40  jnz     loc_180015D2F
0x180015c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c4d  lea     rdx, WPP_GLOBAL_Control
0x180015c54  cmp     rcx, rdx
0x180015c57  jz      short loc_180015C73
0x180015c59  test    byte ptr [rcx+1Ch], 1
0x180015c5d  jz      short loc_180015C73
0x180015c5f  mov     rcx, [rcx+10h]
0x180015c63  lea     edx, [r8+2Ch]
0x180015c67  lea     r8, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids
0x180015c6e  call    WPP_SF_
0x180015c73  mov     edi, 0C0000017h
0x180015c78  mov     r12, [rbp+500h+var_578]
0x180015c7c  xor     ebx, ebx
0x180015c7e  mov     ecx, [rbp+500h+var_56C]
0x180015c81  lea     rdx, [rbp+500h+var_500]
0x180015c85  mov     rax, cs:LsaFunctions
0x180015c8c  lea     r9, [rbp+500h+DestinationString]
0x180015c90  mov     [rsp+600h+var_5C0], rdx
0x180015c95  lea     r8, [rbp+500h+UnicodeString]
0x180015c99  lea     rdx, [rbp+500h+var_260]
0x180015ca0  test    ecx, ecx
0x180015ca2  mov     [rsp+600h+var_5C8], rdx
0x180015ca7  lea     rdx, [rbp+500h+var_4D0]
0x180015cab  mov     rax, [rax+0A8h]
0x180015cb2  cmovns  ecx, edi
0x180015cb5  mov     dword ptr [rsp+600h+var_5D0], 3
0x180015cbd  mov     qword ptr [rsp+600h+var_5D8], rbx
0x180015cc2  mov     [rsp+600h+pbIV], rdx
0x180015cc7  mov     edx, dword ptr [rbp+500h+Size+4]
0x180015cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180015cd6  mov     r15d, 10h
0x180015cdc  test    rsi, rsi
0x180015cdf  jz      loc_180017FE8
0x180015ce5  cmp     edi, 0C0000413h
0x180015ceb  jnz     loc_180017E63
0x180015cf1  cmp     byte ptr [rsi+0DFh], 0Ah
0x180015cf8  jnb     loc_180017E63
0x180015cfe  lea     rbx, WPP_GLOBAL_Control
0x180015d05  cmp     rcx, rbx
0x180015d08  jz      short loc_180015D25
0x180015d0a  test    byte ptr [rcx+1Ch], 2
0x180015d0e  jz      short loc_180015D25
0x180015d10  mov     rcx, [rcx+10h]
0x180015d14  lea     r8, WPP_6a4910cf88383945ace0d56244c4efaf_Traceguids
0x180015d1b  mov     edx, 63h ; 'c'
0x180015d20  call    WPP_SF_
  ... truncated ...
```
