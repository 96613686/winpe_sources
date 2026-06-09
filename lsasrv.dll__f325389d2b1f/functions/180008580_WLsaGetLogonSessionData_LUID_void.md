# WLsaGetLogonSessionData(_LUID *,void * *)

- ea: `0x180008580`
- end: `0x18000910f`
- name: `?WLsaGetLogonSessionData@@YAJPEAU_LUID@@PEAPEAX@Z`
- size: `2959`
- prototype: `__int64 __fastcall(struct _LUID *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800079c0`

## callees

- `0x180007268`
- `0x180007dd8`
- `0x180008054`
- `0x180008580`
- `0x180009330`
- `0x1800093b0`
- `0x180009410`
- `0x180009470`
- `0x180009690`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180008603`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800087a7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180008603`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800087a7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008621`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008621`
- `ntdll!RtlAcquireResourceExclusive` at `0x180008912`
- `ntdll!RtlAcquireResourceExclusive` at `0x180008912`
- `ntdll!RtlReleaseResource` at `0x18000881e`
- `ntdll!RtlReleaseResource` at `0x180008934`
- `ntdll!RtlReleaseResource` at `0x180008b7e`
- `ntdll!RtlReleaseResource` at `0x180008fe5`
- `ntdll!RtlReleaseResource` at `0x180009004`
- `ntdll!RtlReleaseResource` at `0x180009051`
- `ntdll!RtlReleaseResource` at `0x18000881e`
- `ntdll!RtlReleaseResource` at `0x180008934`
- `ntdll!RtlReleaseResource` at `0x180008b7e`
- `ntdll!RtlReleaseResource` at `0x180008fe5`
- `ntdll!RtlReleaseResource` at `0x180009004`
- `ntdll!RtlReleaseResource` at `0x180009051`
- `ntdll!RtlAcquireResourceShared` at `0x1800085e1`
- `ntdll!RtlAcquireResourceShared` at `0x1800085e1`
- `ntdll!RtlLengthSid` at `0x1800086a6`
- `ntdll!RtlLengthSid` at `0x1800086a6`

## pseudocode

```c
__int64 __fastcall WLsaGetLogonSessionData(struct _LUID *a1, void **a2)
{
  int v2; // r13d
  struct _LSAP_LOGON_SESSION *LogonSession; // rbx
  int v4; // r14d
  void *v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned __int16 v8; // r12
  unsigned __int16 v9; // r14
  unsigned __int16 v10; // si
  void *v11; // rcx
  size_t v12; // rdi
  int v13; // edx
  unsigned __int16 v14; // r15
  bool v15; // zf
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  _DWORD *p_IsMember; // r12
  unsigned int v20; // eax
  size_t v21; // rcx
  _DWORD *v22; // rax
  char *v23; // rcx
  char *v24; // rsi
  _WORD *v25; // r14
  unsigned __int16 *v26; // rsi
  size_t v27; // r8
  size_t v28; // r13
  __int16 v30; // ax
  unsigned __int64 v31; // rcx
  __int64 v32; // rdx
  unsigned __int64 v33; // rdx
  void *v34; // rsp
  void *v35; // rsp
  char *v36; // r14
  char *v37; // r14
  const void *v38; // rdx
  unsigned __int16 v39; // di
  unsigned __int64 v40; // rax
  char *v41; // rdi
  char *v42; // rdi
  unsigned __int16 *v43; // rdi
  struct _RTL_RESOURCE *v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // r13
  _DWORD *v48; // r15
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rcx
  void *v52; // rsp
  void *v53; // rsp
  size_t v54; // rax
  char *v55; // rax
  char *v56; // rsi
  char *v57; // rdi
  void *v58; // rax
  __int64 v59; // rdi
  size_t v60; // r8
  unsigned __int16 v61; // cx
  __int16 v62; // cx
  __int64 v63; // rax
  void *v64; // rdx
  size_t v65; // r8
  char *v66; // rdi
  char *v67; // rsi
  struct _LSAP_SECURITY_PACKAGE *v68; // rcx
  __int64 v69; // rax
  char *v70; // rdi
  char *v71; // rsi
  size_t v72; // r8
  void *v73; // rdx
  __int64 v74; // rax
  char *v75; // rdi
  char *v76; // rsi
  size_t v77; // rax
  size_t v78; // r8
  char *v79; // rdi
  char *v80; // rsi
  size_t v81; // rax
  char *v82; // rdi
  char *v83; // rsi
  size_t v84; // r14
  void *v85; // rdx
  size_t v86; // r8
  __int16 v87; // ax
  void *v88; // rdx
  char *v89; // rdi
  char *v90; // r14
  size_t v91; // rsi
  size_t v92; // r8
  unsigned __int16 v93; // cx
  void *v94; // rdx
  char *v95; // rsi
  char *v96; // r14
  __int64 v97; // rdi
  char *v98; // rsi
  char *v99; // r14
  __int16 v100; // ax
  __int64 v101; // rcx
  _DWORD *v102; // rax
  _BYTE v103[32]; // [rsp+0h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+20h] [rbp+0h] BYREF
  int v105; // [rsp+24h] [rbp+4h]
  void *v106; // [rsp+28h] [rbp+8h] BYREF
  int v107; // [rsp+30h] [rbp+10h]
  int v108; // [rsp+34h] [rbp+14h]
  int v109; // [rsp+38h] [rbp+18h]
  size_t Size; // [rsp+40h] [rbp+20h]
  unsigned int v111; // [rsp+48h] [rbp+28h]
  int v112; // [rsp+4Ch] [rbp+2Ch]
  int v113; // [rsp+50h] [rbp+30h]
  int v114; // [rsp+54h] [rbp+34h]
  struct _LSAP_SECURITY_PACKAGE *Package; // [rsp+58h] [rbp+38h]
  void *Src; // [rsp+60h] [rbp+40h]
  size_t v117; // [rsp+68h] [rbp+48h]
  void *v118; // [rsp+70h] [rbp+50h]
  size_t v119; // [rsp+78h] [rbp+58h]
  PVOID v120; // [rsp+80h] [rbp+60h]
  size_t v121; // [rsp+88h] [rbp+68h]
  void *v122; // [rsp+90h] [rbp+70h]
  size_t v123; // [rsp+98h] [rbp+78h]
  void *v124; // [rsp+A0h] [rbp+80h]
  void *v125; // [rsp+A8h] [rbp+88h]
  PVOID P; // [rsp+B0h] [rbp+90h]
  void **v127; // [rsp+B8h] [rbp+98h]

  v2 = 0;
  v127 = a2;
  IsMember = 0;
  LogonSession = LsapLocateLogonSession(a1);
  if ( LogonSession )
  {
    v4 = LsapImpersonateClientEx(0);
    if ( v4 < 0 )
    {
      v48 = 0;
      p_IsMember = 0;
LABEL_45:
      LsapReleaseLogonSession(LogonSession);
      if ( v48 && *(v48 - 2) == 1885431112 )
        ((void (__fastcall *)(_DWORD *))g_pfnFree)(v48 - 2);
      if ( p_IsMember )
      {
        if ( *(p_IsMember - 2) == 1885431112 )
          ((void (__fastcall *)(_DWORD *))g_pfnFree)(p_IsMember - 2);
      }
      return (unsigned int)v4;
    }
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)LogonSession + 16), 1u);
    v5 = (void *)*((_QWORD *)LogonSession + 28);
    if ( v5 && CheckTokenMembership(0, v5, &IsMember) )
    {
      if ( IsMember )
        goto LABEL_6;
    }
    else
    {
      IsMember = 0;
    }
    if ( !CheckTokenMembership(0, *((PSID *)WellKnownSids + 96), &IsMember) )
      IsMember = 0;
LABEL_6:
    RevertToSelf();
    if ( IsMember )
    {
      Package = SpmpLocatePackage(*((_QWORD *)LogonSession + 38));
      if ( Package )
      {
        if ( *((_QWORD *)LogonSession + 21) )
        {
          v8 = *((_WORD *)LogonSession + 80);
          v105 = v8;
        }
        else
        {
          v8 = 0;
          v105 = 0;
        }
        if ( *((_QWORD *)LogonSession + 23) )
        {
          v9 = *((_WORD *)LogonSession + 88);
          v107 = v9;
        }
        else
        {
          v9 = 0;
          v107 = 0;
        }
        if ( *((_QWORD *)LogonSession + 34) )
        {
          v10 = *((_WORD *)LogonSession + 132);
          v112 = v10;
        }
        else
        {
          v10 = 0;
          v112 = 0;
        }
        v11 = (void *)*((_QWORD *)LogonSession + 28);
        if ( v11 )
          v12 = RtlLengthSid(v11);
        else
          v12 = 0;
        v111 = v12;
        if ( *((_QWORD *)LogonSession + 77) )
          v13 = *((unsigned __int16 *)LogonSession + 304);
        else
          v13 = 0;
        v108 = v13;
        if ( *((_QWORD *)LogonSession + 25) )
        {
          v14 = *((_WORD *)LogonSession + 96);
          v113 = v14;
        }
        else
        {
          v14 = 0;
          v113 = 0;
        }
        if ( *((_QWORD *)LogonSession + 79) )
          v2 = *((unsigned __int16 *)LogonSession + 312);
        v15 = *((_QWORD *)LogonSession + 81) == 0;
        v114 = v2;
        if ( v15 )
          v16 = 0;
        else
          v16 = *((unsigned __int16 *)LogonSession + 320);
        v109 = v16;
        v17 = v9
            + v10
            + (unsigned __int16)v13
            + v14
            + (unsigned __int16)v2
            + (unsigned __int16)v16
            + ((v12 + 7) & 0xFFFFFFF8);
        v18 = v8;
        v17 += 14;
        p_IsMember = 0;
        v15 = v17 + v18 == 0;
        v20 = v17 + v18;
        LODWORD(Size) = v20;
        if ( v15 )
          goto LABEL_25;
        v106 = (void *)v20;
        if ( v20 > (unsigned __int64)g_ulMaxStackAllocSize )
          goto LABEL_25;
        v31 = v20 + g_ulAdditionalProbeSize + 8;
        if ( v31 < v20 || !(unsigned int)VerifyStackAvailable(v31, v20, v6, v7) )
          goto LABEL_25;
        v21 = (size_t)v106;
        v32 = (__int64)v106 + 23;
        if ( (char *)v106 + 23 <= (char *)v106 + 8 )
          v32 = 0xFFFFFFFFFFFFFF0LL;
        v33 = v32 & 0xFFFFFFFFFFFFFFF0uLL;
        v34 = alloca(v33);
        v35 = alloca(v33);
        p_IsMember = &IsMember;
        if ( v103 == (_BYTE *)-32LL || (IsMember = 1801679955, (p_IsMember = &v106) == 0) )
        {
LABEL_25:
          v21 = (unsigned int)Size;
          v106 = (void *)(unsigned int)Size;
          if ( (unsigned __int64)(unsigned int)Size + 8 >= (unsigned int)Size )
          {
            v22 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)((unsigned int)Size + 8LL);
            v21 = (size_t)v106;
            p_IsMember = v22;
            if ( v22 )
            {
              *v22 = 1885431112;
              p_IsMember = v22 + 2;
            }
          }
        }
        if ( p_IsMember )
        {
          v117 = v9;
          v118 = (char *)p_IsMember + 2 * ((unsigned __int64)(unsigned __int16)v105 >> 1) + 2;
          v106 = (char *)v118 + 2 * ((unsigned __int64)v9 >> 1) + 2;
          memset_0(p_IsMember, 0, v21);
          if ( (_WORD)v105 )
            memcpy_0(p_IsMember, *((const void **)LogonSession + 21), (unsigned __int16)v105);
          if ( v9 )
            memcpy_0(v118, *((const void **)LogonSession + 23), v117);
          v36 = (char *)v106;
          if ( v10 )
            memcpy_0(v106, *((const void **)LogonSession + 34), v10);
          v119 = v10;
          v37 = &v36[2 * ((unsigned __int64)v10 >> 1) + 2];
          if ( (_DWORD)v12 )
          {
            v38 = (const void *)*((_QWORD *)LogonSession + 28);
            Src = v37;
            memcpy_0(v37, v38, v12);
            v37 = (char *)((unsigned __int64)&v37[v12 + 1] & 0xFFFFFFFFFFFFFFFEuLL);
          }
          else
          {
            Src = 0;
          }
          v39 = v108;
          if ( (_WORD)v108 )
            memcpy_0(v37, *((const void **)LogonSession + 77), (unsigned __int16)v108);
          v117 = v39;
          v40 = (unsigned __int64)v39 >> 1;
          v41 = &v37[2 * v40 + 2];
          v122 = v41;
          if ( v14 )
            memcpy_0(&v37[2 * v40 + 2], *((const void **)LogonSession + 25), v14);
          v121 = v14;
          v42 = &v41[2 * ((unsigned __int64)v14 >> 1) + 2];
          v124 = v42;
          if ( (_WORD)v2 )
            memcpy_0(v42, *((const void **)LogonSession + 79), (unsigned __int16)v2);
          v123 = (unsigned __int16)v2;
          v125 = &v42[2 * ((unsigned __int64)(unsigned __int16)v2 >> 1) + 2];
          if ( (_WORD)v109 )
            memcpy_0(
              &v42[2 * ((unsigned __int64)(unsigned __int16)v2 >> 1) + 2],
              *((const void **)LogonSession + 81),
              (unsigned __int16)v109);
          v26 = (unsigned __int16 *)*((_QWORD *)LogonSession + 57);
          v120 = v26;
          if ( v26 )
            _InterlockedIncrement((volatile signed __int32 *)v26 + 4);
          v43 = (unsigned __int16 *)*((_QWORD *)LogonSession + 61);
          v44 = (struct _RTL_RESOURCE *)((char *)LogonSession + 16);
          P = v43;
          if ( v43 )
          {
            _InterlockedIncrement((volatile signed __int32 *)v43 + 4);
            RtlReleaseResource(v44);
            v47 = *((unsigned __int16 *)Package + 24) + (_DWORD)Size + 278 + (unsigned int)v43[12];
          }
          else
          {
            RtlReleaseResource(v44);
            v47 = (unsigned int)*((unsigned __int16 *)Package + 24) + (_DWORD)Size + 278;
          }
          if ( v26 )
            v47 = v26[12] + (unsigned int)v47;
          v48 = 0;
          if ( !(_DWORD)v47 )
            goto LABEL_111;
          if ( (unsigned int)v47 > (unsigned __int64)g_ulMaxStackAllocSize )
            goto LABEL_111;
          v49 = (unsigned int)v47 + g_ulAdditionalProbeSize + 8;
          if ( v49 < (unsigned int)v47
            || !(unsigned int)VerifyStackAvailable((unsigned int)v47 + g_ulAdditionalProbeSize + 8, v49, v45, v46) )
          {
            goto LABEL_111;
          }
          v50 = (unsigned int)v47 + 23LL;
          if ( v50 <= (unsigned __int64)(unsigned int)v47 + 8 )
            v50 = 0xFFFFFFFFFFFFFF0LL;
          v51 = v50 & 0xFFFFFFFFFFFFFFF0uLL;
          v52 = alloca(v51);
          v53 = alloca(v51);
          v48 = &IsMember;
          if ( v103 == (_BYTE *)-32LL || (IsMember = 1801679955, (v48 = &v106) == 0) )
          {
LABEL_111:
            v54 = (unsigned int)v47;
            if ( v47 + 8 < (unsigned __int64)(unsigned int)v47 )
            {
LABEL_97:
              if ( v48 )
              {
                memset_0(v48, 0, v54);
                v55 = (char *)LsapClientAllocate(v47);
                Size = (size_t)v55;
                if ( v55 )
                {
                  *v48 = 272;
                  v56 = v55 + 272;
                  v57 = (char *)(v48 + 68);
                  *(_QWORD *)(v48 + 1) = *((_QWORD *)LogonSession + 14);
                  v48[16] = *((_DWORD *)LogonSession + 58);
                  v48[17] = *((_DWORD *)LogonSession + 62);
                  *((_QWORD *)v48 + 10) = *((_QWORD *)LogonSession + 32);
                  v48[34] = *((_DWORD *)LogonSession + 144);
                  *((_OWORD *)v48 + 9) = *(_OWORD *)((char *)LogonSession + 584);
                  *((_QWORD *)v48 + 20) = *((_QWORD *)LogonSession + 75);
                  *((_QWORD *)v48 + 29) = *((_QWORD *)LogonSession + 82);
                  *((_QWORD *)v48 + 30) = *((_QWORD *)LogonSession + 83);
                  *((_QWORD *)v48 + 31) = *((_QWORD *)LogonSession + 84);
                  *((_QWORD *)v48 + 32) = *((_QWORD *)LogonSession + 85);
                  *((_QWORD *)v48 + 33) = *((_QWORD *)LogonSession + 86);
                  v58 = Src;
                  if ( Src )
                  {
                    v59 = v111;
                    v60 = v111;
                    *((_QWORD *)v48 + 9) = v56;
                    memcpy_0(v48 + 68, v58, v60);
                    v56 += v59;
                    v57 = (char *)v48 + v59 + 272;
                  }
                  else
                  {
                    *((_QWORD *)v48 + 9) = 0;
                  }
                  v61 = v105;
                  *((_WORD *)v48 + 8) = v105;
                  *((_QWORD *)v48 + 3) = v56;
                  *((_WORD *)v48 + 9) = v61 + 2;
                  memcpy_0(v57, p_IsMember, v61);
                  v62 = v107;
                  v63 = (unsigned __int16)v105;
                  v64 = v118;
                  v65 = (unsigned __int16)v107;
                  *(_WORD *)&v57[(unsigned __int16)v105] = 0;
                  v66 = &v57[v63 + 2];
                  *((_WORD *)v48 + 16) = v62;
                  v67 = &v56[*((unsigned __int16 *)v48 + 9)];
                  *((_WORD *)v48 + 17) = v62 + 2;
                  *((_QWORD *)v48 + 5) = v67;
                  memcpy_0(v66, v64, v65);
                  v68 = Package;
                  v69 = (unsigned __int16)v107;
                  *(_WORD *)&v66[(unsigned __int16)v107] = 0;
                  v70 = &v66[v69 + 2];
                  v71 = &v67[*((unsigned __int16 *)v48 + 17)];
                  LOWORD(v69) = *((_WORD *)v68 + 24);
                  *((_WORD *)v48 + 24) = v69;
                  *((_WORD *)v48 + 25) = v69 + 2;
                  *((_QWORD *)v48 + 7) = v71;
                  memcpy_0(v70, *((const void **)v68 + 7), *((unsigned __int16 *)v68 + 24));
                  v72 = v119;
                  v73 = v106;
                  v74 = *((unsigned __int16 *)Package + 24);
                  *(_WORD *)&v70[v74] = 0;
                  v75 = &v70[v74 + 2];
                  v76 = &v71[*((unsigned __int16 *)v48 + 25)];
                  LOWORD(v74) = v112;
                  *((_WORD *)v48 + 44) = v112;
                  *((_WORD *)v48 + 45) = v74 + 2;
                  *((_QWORD *)v48 + 12) = v76;
                  memcpy_0(v75, v73, v72);
                  v77 = v119;
                  v78 = v117;
                  *(_WORD *)&v75[v119] = 0;
                  v79 = &v75[v77 + 2];
                  v80 = &v76[*((unsigned __int16 *)v48 + 45)];
                  LOWORD(v77) = v108;
                  *((_WORD *)v48 + 84) = v108;
                  *((_WORD *)v48 + 85) = v77 + 2;
                  *((_QWORD *)v48 + 22) = v80;
                  memcpy_0(v79, v37, v78);
                  v81 = v117;
                  *(_WORD *)&v79[v117] = 0;
                  v82 = &v79[v81 + 2];
                  v83 = &v80[*((unsigned __int16 *)v48 + 85)];
                  LOWORD(v81) = v113;
                  *((_WORD *)v48 + 92) = v113;
                  *((_WORD *)v48 + 93) = v81 + 2;
                  v84 = v121;
                  v85 = v122;
                  v86 = v121;
                  *((_QWORD *)v48 + 24) = v83;
                  memcpy_0(v82, v85, v86);
                  v87 = v114;
                  v88 = v124;
                  *(_WORD *)&v82[v84] = 0;
                  v89 = &v82[v84 + 2];
                  *((_WORD *)v48 + 100) = v87;
                  v90 = &v83[*((unsigned __int16 *)v48 + 93)];
                  *((_WORD *)v48 + 101) = v87 + 2;
                  v91 = v123;
                  v92 = v123;
                  *((_QWORD *)v48 + 26) = v90;
                  memcpy_0(v89, v88, v92);
                  v93 = v109;
                  v94 = v125;
                  *(_WORD *)&v89[v91] = 0;
                  v95 = &v89[v91 + 2];
                  v96 = &v90[*((unsigned __int16 *)v48 + 101)];
                  v97 = v93;
                  *((_WORD *)v48 + 108) = v93;
                  *((_WORD *)v48 + 109) = v93 + 2;
                  *((_QWORD *)v48 + 28) = v96;
                  memcpy_0(v95, v94, v93);
                  *(_WORD *)&v95[v97] = 0;
                  v98 = &v95[v97 + 2];
                  v43 = (unsigned __int16 *)P;
                  v99 = (__int64)&v96[*((unsigned __int16 *)v48 + 109)];
                  if ( P )
                  {
                    v100 = *((_WORD *)P + 12);
                    *((_WORD *)v48 + 52) = v100;
                    *((_WORD *)v48 + 53) = v100 + 2;
                    *((_QWORD *)v48 + 14) = v99;
                    memcpy_0(v98, *((const void **)v43 + 4), v43[12]);
                    v101 = v43[12];
                    v98[v101] = 0;
                    v24 = &v98[v101 + 1];
                    *v24 = 0;
                    v23 = v99 + *((unsigned __int16 *)v48 + 53);
                  }
                  else
                  {
                    *((_QWORD *)v48 + 14) = v99;
                    v48[26] = 0;
                    v23 = v99;
                    *v98 = 0;
                    v24 = v98 + 1;
                    *v24 = 0;
                  }
                  v25 = v24 + 1;
                  v26 = (unsigned __int16 *)v120;
                  if ( v120 )
                  {
                    v30 = *((_WORD *)v120 + 12);
                    *((_WORD *)v48 + 60) = v30;
                    *((_QWORD *)v48 + 16) = v23;
                    *((_WORD *)v48 + 61) = v30 + 2;
                    memcpy_0(v25, *((const void **)v26 + 4), v26[12]);
                    *(_WORD *)((char *)v25 + v26[12]) = 0;
                  }
                  else
                  {
                    *((_QWORD *)v48 + 16) = v23;
                    v48[30] = 0;
                    *v25 = 0;
                  }
                  v27 = (unsigned int)v47;
                  v28 = Size;
                  v4 = LsapCopyToClient(v48, (void *)Size, v27);
                  *v127 = (void *)v28;
                }
                else
                {
                  v4 = -1073741801;
                }
              }
              else
              {
                v4 = -1073741801;
              }
              if ( v43 || v26 )
              {
                RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)LogonSession + 16), 1u);
                if ( v43 )
                  LsapDerefDsNameMap(v43);
                if ( v26 )
                  LsapDerefDsNameMap(v26);
                RtlReleaseResource((PRTL_RESOURCE)((char *)LogonSession + 16));
              }
              goto LABEL_45;
            }
            v102 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
            v48 = v102;
            if ( v102 )
            {
              *v102 = 1885431112;
              v48 = v102 + 2;
            }
          }
          v54 = (unsigned int)v47;
          goto LABEL_97;
        }
        RtlReleaseResource((PRTL_RESOURCE)((char *)LogonSession + 16));
        v4 = -1073741801;
        LsapReleaseLogonSession(LogonSession);
      }
      else
      {
        RtlReleaseResource((PRTL_RESOURCE)((char *)LogonSession + 16));
        v4 = -1073741729;
        LsapReleaseLogonSession(LogonSession);
      }
    }
    else
    {
      RtlReleaseResource((PRTL_RESOURCE)((char *)LogonSession + 16));
      v4 = -1073741790;
      LsapReleaseLogonSession(LogonSession);
    }
    return (unsigned int)v4;
  }
  return 3221225567LL;
}

```

## disassembly

```asm
0x180008580  push    rbp
0x180008582  push    rbx
0x180008583  push    rsi
0x180008584  push    rdi
0x180008585  push    r12
0x180008587  push    r13
0x180008589  push    r14
0x18000858b  push    r15
0x18000858d  sub     rsp, 0D8h
0x180008594  lea     rbp, [rsp+20h]
0x180008599  mov     rax, cs:__security_cookie
0x1800085a0  xor     rax, rbp
0x1800085a3  mov     [rbp+0F0h+var_50], rax
0x1800085aa  xor     r13d, r13d
0x1800085ad  mov     [rbp+0F0h+var_58], rdx
0x1800085b4  mov     [rbp+0F0h+IsMember], r13d
0x1800085b8  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x1800085bd  mov     rbx, rax
0x1800085c0  test    rax, rax
0x1800085c3  jz      loc_180009043
0x1800085c9  xor     ecx, ecx; int *
0x1800085cb  call    ?LsapImpersonateClientEx@@YAJPEAH@Z; LsapImpersonateClientEx(int *)
0x1800085d0  mov     r14d, eax
0x1800085d3  test    eax, eax
0x1800085d5  js      loc_180009104
0x1800085db  mov     dl, 1; Wait
0x1800085dd  lea     rcx, [rbx+10h]; Resource
0x1800085e1  call    cs:__imp_RtlAcquireResourceShared
0x1800085e8  nop     dword ptr [rax+rax+00h]
0x1800085ed  mov     rdx, [rbx+0E0h]; SidToCheck
0x1800085f4  test    rdx, rdx
0x1800085f7  jz      loc_18000878F
0x1800085fd  lea     r8, [rbp+0F0h+IsMember]; IsMember
0x180008601  xor     ecx, ecx; TokenHandle
0x180008603  call    cs:__imp_CheckTokenMembership
0x18000860a  nop     dword ptr [rax+rax+00h]
0x18000860f  test    eax, eax
0x180008611  jz      loc_18000878F
0x180008617  cmp     [rbp+0F0h+IsMember], r13d
0x18000861b  jz      loc_180008793
0x180008621  call    cs:__imp_RevertToSelf
0x180008628  nop     dword ptr [rax+rax+00h]
0x18000862d  cmp     [rbp+0F0h+IsMember], r13d
0x180008631  jz      loc_18000881A
0x180008637  mov     rcx, [rbx+130h]; unsigned __int64
0x18000863e  call    ?SpmpLocatePackage@@YAPEAU_LSAP_SECURITY_PACKAGE@@_K@Z; SpmpLocatePackage(unsigned __int64)
0x180008643  mov     [rbp+0F0h+var_B8], rax
0x180008647  test    rax, rax
0x18000864a  jz      loc_18000904D
0x180008650  cmp     [rbx+0A8h], r13
0x180008657  jz      loc_18000880E
0x18000865d  movzx   r12d, word ptr [rbx+0A0h]
0x180008665  mov     [rbp+0F0h+var_EC], r12d
0x180008669  cmp     [rbx+0B8h], r13
0x180008670  jz      loc_1800087E2
0x180008676  movzx   r14d, word ptr [rbx+0B0h]
0x18000867e  mov     [rbp+0F0h+var_E0], r14d
0x180008682  cmp     [rbx+110h], r13
0x180008689  jnz     loc_180008780
0x18000868f  mov     esi, r13d
0x180008692  mov     dword ptr [rbp+0F0h+var_C8+4], r13d
0x180008696  mov     rcx, [rbx+0E0h]; Sid
0x18000869d  test    rcx, rcx
0x1800086a0  jz      loc_1800087EE
0x1800086a6  call    cs:__imp_RtlLengthSid
0x1800086ad  nop     dword ptr [rax+rax+00h]
0x1800086b2  mov     edi, eax
0x1800086b4  mov     dword ptr [rbp+0F0h+var_C8], edi
0x1800086b7  cmp     [rbx+268h], r13
0x1800086be  jnz     loc_180008802
0x1800086c4  mov     edx, r13d
0x1800086c7  mov     [rbp+0F0h+var_DC], edx
0x1800086ca  cmp     [rbx+0C8h], r13
0x1800086d1  jnz     loc_1800087D1
0x1800086d7  mov     r15d, r13d
0x1800086da  mov     [rbp+0F0h+var_C0], r13d
0x1800086de  cmp     [rbx+278h], r13
0x1800086e5  jnz     loc_1800087C4
0x1800086eb  cmp     qword ptr [rbx+288h], 0
0x1800086f3  mov     [rbp+0F0h+var_BC], r13d
0x1800086f7  jnz     loc_1800087F6
0x1800086fd  xor     eax, eax
0x1800086ff  mov     [rbp+0F0h+var_D8], eax
0x180008702  lea     ecx, [rdi+7]
0x180008705  and     ecx, 0FFFFFFF8h
0x180008708  movzx   eax, ax
0x18000870b  add     ecx, eax
0x18000870d  movzx   eax, r13w
0x180008711  add     ecx, eax
0x180008713  movzx   eax, r15w
0x180008717  add     ecx, eax
0x180008719  movzx   eax, dx
0x18000871c  add     ecx, eax
0x18000871e  movzx   eax, si
0x180008721  add     ecx, eax
0x180008723  movzx   eax, r14w
0x180008727  add     ecx, eax
0x180008729  movzx   eax, r12w
0x18000872d  add     ecx, 0Eh
0x180008730  xor     r12d, r12d
0x180008733  add     eax, ecx
0x180008735  mov     dword ptr [rbp+0F0h+Size], eax
0x180008738  jnz     loc_180008989
0x18000873e  mov     ecx, dword ptr [rbp+0F0h+Size]
0x180008741  mov     [rbp+0F0h+var_E8], rcx
0x180008745  lea     rax, [rcx+8]
0x180008749  cmp     rax, rcx
0x18000874c  jb      loc_180008A0D
0x180008752  mov     rcx, rax
0x180008755  mov     rax, cs:g_pfnAllocate
0x18000875c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008761  mov     rcx, [rbp+0F0h+var_E8]
0x180008765  mov     r12, rax
0x180008768  test    rax, rax
0x18000876b  jz      loc_180008A0D
0x180008771  mov     dword ptr [rax], 70616548h
0x180008777  add     r12, 8
0x18000877b  jmp     loc_180008A0D
0x180008780  movzx   esi, word ptr [rbx+108h]
0x180008787  mov     dword ptr [rbp+0F0h+var_C8+4], esi
0x18000878a  jmp     loc_180008696
0x18000878f  mov     [rbp+0F0h+IsMember], r13d
0x180008793  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18000879a  lea     r8, [rbp+0F0h+IsMember]; IsMember
0x18000879e  xor     ecx, ecx; TokenHandle
0x1800087a0  mov     rdx, [rdx+300h]; SidToCheck
0x1800087a7  call    cs:__imp_CheckTokenMembership
0x1800087ae  nop     dword ptr [rax+rax+00h]
0x1800087b3  test    eax, eax
0x1800087b5  jnz     loc_180008621
0x1800087bb  mov     [rbp+0F0h+IsMember], r13d
0x1800087bf  jmp     loc_180008621
0x1800087c4  movzx   r13d, word ptr [rbx+270h]
0x1800087cc  jmp     loc_1800086EB
0x1800087d1  movzx   r15d, word ptr [rbx+0C0h]
0x1800087d9  mov     [rbp+0F0h+var_C0], r15d
0x1800087dd  jmp     loc_1800086DE
0x1800087e2  mov     r14d, r13d
0x1800087e5  mov     [rbp+0F0h+var_E0], r13d
0x1800087e9  jmp     loc_180008682
0x1800087ee  mov     edi, r13d
0x1800087f1  jmp     loc_1800086B4
0x1800087f6  movzx   eax, word ptr [rbx+280h]
0x1800087fd  jmp     loc_1800086FF
0x180008802  movzx   edx, word ptr [rbx+260h]
0x180008809  jmp     loc_1800086C7
0x18000880e  mov     r12d, r13d
0x180008811  mov     [rbp+0F0h+var_EC], r13d
0x180008815  jmp     loc_180008669
0x18000881a  lea     rcx, [rbx+10h]; Resource
0x18000881e  call    cs:__imp_RtlReleaseResource
0x180008825  nop     dword ptr [rax+rax+00h]
0x18000882a  mov     rcx, rbx; struct _LSAP_LOGON_SESSION *
0x18000882d  mov     r14d, 0C0000022h
0x180008833  call    ?LsapReleaseLogonSession@@YAXPEAU_LSAP_LOGON_SESSION@@@Z; LsapReleaseLogonSession(_LSAP_LOGON_SESSION *)
0x180008838  jmp     short loc_1800088AB
0x18000883a  xor     eax, eax
0x18000883c  mov     [r15+70h], r14
0x180008840  mov     [r15+68h], eax
0x180008844  mov     rcx, r14
0x180008847  mov     [rsi], al
0x180008849  inc     rsi
0x18000884c  mov     [rsi], al
0x18000884e  lea     r14, [rsi+1]
0x180008852  mov     rsi, [rbp+0F0h+var_90]
0x180008856  test    rsi, rsi
0x180008859  jnz     loc_180008945
0x18000885f  xor     eax, eax
0x180008861  mov     [r15+80h], rcx
0x180008868  mov     [r15+78h], eax
0x18000886c  mov     [r14], ax
0x180008870  mov     r8d, r13d; Size
0x180008873  mov     rcx, r15; Src
0x180008876  mov     r13, [rbp+0F0h+Size]
0x18000887a  mov     rdx, r13; void *
0x18000887d  call    ?LsapCopyToClient@@YAJPEAX0K@Z; LsapCopyToClient(void *,void *,ulong)
0x180008882  mov     r14d, eax
0x180008885  mov     rax, [rbp+0F0h+var_58]
0x18000888c  mov     [rax], r13
0x18000888f  test    rdi, rdi
0x180008892  jnz     short loc_18000890C
0x180008894  test    rsi, rsi
0x180008897  jnz     short loc_18000890C
0x180008899  mov     rcx, rbx; struct _LSAP_LOGON_SESSION *
0x18000889c  call    ?LsapReleaseLogonSession@@YAXPEAU_LSAP_LOGON_SESSION@@@Z; LsapReleaseLogonSession(_LSAP_LOGON_SESSION *)
0x1800088a1  test    r15, r15
0x1800088a4  jnz     short loc_1800088D2
0x1800088a6  test    r12, r12
0x1800088a9  jnz     short loc_1800088EE
0x1800088ab  mov     eax, r14d
0x1800088ae  mov     rcx, [rbp+0F0h+var_50]
0x1800088b5  xor     rcx, rbp; StackCookie
0x1800088b8  call    __security_check_cookie
0x1800088bd  lea     rsp, [rbp+0B8h]
0x1800088c4  pop     r15
0x1800088c6  pop     r14
0x1800088c8  pop     r13
0x1800088ca  pop     r12
0x1800088cc  pop     rdi
0x1800088cd  pop     rsi
0x1800088ce  pop     rbx
0x1800088cf  pop     rbp
0x1800088d0  retn
0x1800088d2  cmp     dword ptr [r15-8], 70616548h
0x1800088da  lea     rcx, [r15-8]
0x1800088de  jnz     short loc_1800088A6
0x1800088e0  mov     rax, cs:g_pfnFree
0x1800088e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ec  jmp     short loc_1800088A6
0x1800088ee  cmp     dword ptr [r12-8], 70616548h
0x1800088f7  lea     rcx, [r12-8]
0x1800088fc  jnz     short loc_1800088AB
0x1800088fe  mov     rax, cs:g_pfnFree
0x180008905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000890a  jmp     short loc_1800088AB
0x18000890c  mov     dl, 1; Wait
0x18000890e  lea     rcx, [rbx+10h]; Resource
0x180008912  call    cs:__imp_RtlAcquireResourceExclusive
0x180008919  nop     dword ptr [rax+rax+00h]
0x18000891e  test    rdi, rdi
0x180008921  jz      short loc_18000892B
0x180008923  mov     rcx, rdi; P
0x180008926  call    ?LsapDerefDsNameMap@@YAXPEAU_LSAP_DS_NAME_MAP@@@Z; LsapDerefDsNameMap(_LSAP_DS_NAME_MAP *)
0x18000892b  test    rsi, rsi
0x18000892e  jnz     short loc_18000897F
0x180008930  lea     rcx, [rbx+10h]; Resource
0x180008934  call    cs:__imp_RtlReleaseResource
0x18000893b  nop     dword ptr [rax+rax+00h]
0x180008940  jmp     loc_180008899
0x180008945  movzx   eax, word ptr [rsi+18h]
0x180008949  mov     [r15+78h], ax
0x18000894e  add     ax, 2
0x180008952  mov     [r15+80h], rcx
0x180008959  mov     rcx, r14; void *
0x18000895c  mov     [r15+7Ah], ax
0x180008961  movzx   r8d, word ptr [rsi+18h]; Size
0x180008966  mov     rdx, [rsi+20h]; Src
0x18000896a  call    memcpy_0
0x18000896f  movzx   eax, word ptr [rsi+18h]
0x180008973  mov     word ptr [rax+r14], 0
0x18000897a  jmp     loc_180008870
0x18000897f  mov     rcx, rsi; P
0x180008982  call    ?LsapDerefDsNameMap@@YAXPEAU_LSAP_DS_NAME_MAP@@@Z; LsapDerefDsNameMap(_LSAP_DS_NAME_MAP *)
0x180008987  jmp     short loc_180008930
0x180008989  mov     edx, eax
0x18000898b  cmp     rdx, cs:g_ulMaxStackAllocSize
0x180008992  mov     [rbp+0F0h+var_E8], rdx
0x180008996  ja      loc_18000873E
0x18000899c  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800089a3  add     rcx, 8
0x1800089a7  add     rcx, rdx
0x1800089aa  cmp     rcx, rdx
0x1800089ad  jb      loc_18000873E
0x1800089b3  call    VerifyStackAvailable
0x1800089b8  test    eax, eax
0x1800089ba  jz      loc_18000873E
0x1800089c0  mov     rcx, [rbp+0F0h+var_E8]
0x1800089c4  mov     r8, 0FFFFFFFFFFFFFF0h
0x1800089ce  lea     rax, [rcx+8]
0x1800089d2  lea     rdx, [rax+0Fh]
0x1800089d6  cmp     rdx, rax
0x1800089d9  ja      short loc_1800089DE
0x1800089db  mov     rdx, r8
0x1800089de  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800089e2  mov     rax, rdx
0x1800089e5  call    _alloca_probe
0x1800089ea  sub     rsp, rdx
0x1800089ed  lea     r12, [rsp+110h+IsMember]
0x1800089f2  test    r12, r12
0x1800089f5  jz      loc_18000873E
0x1800089fb  mov     dword ptr [r12], 6B637453h
0x180008a03  add     r12, 8
0x180008a07  jz      loc_18000873E
0x180008a0d  test    r12, r12
0x180008a10  jz      loc_180008FE1
0x180008a16  movzx   eax, word ptr [rbp+0F0h+var_EC]
0x180008a1a  mov     r8, rcx; Size
0x180008a1d  shr     rax, 1
0x180008a20  mov     rcx, r12; void *
0x180008a23  inc     rax
0x180008a26  lea     rdx, [r12+rax*2]
0x180008a2a  movzx   eax, r14w
0x180008a2e  mov     [rbp+0F0h+var_A8], rax
0x180008a32  shr     rax, 1
0x180008a35  inc     rax
0x180008a38  mov     [rbp+0F0h+var_A0], rdx
0x180008a3c  lea     rax, [rdx+rax*2]
0x180008a40  xor     edx, edx; Val
0x180008a42  mov     [rbp+0F0h+var_E8], rax
0x180008a46  call    memset_0
0x180008a4b  mov     eax, [rbp+0F0h+var_EC]
0x180008a4e  test    ax, ax
0x180008a51  jz      short loc_180008A66
0x180008a53  mov     rdx, [rbx+0A8h]; Src
0x180008a5a  mov     rcx, r12; void *
0x180008a5d  movzx   r8d, ax; Size
0x180008a61  call    memcpy_0
0x180008a66  test    r14w, r14w
0x180008a6a  jz      short loc_180008A80
0x180008a6c  mov     r8, [rbp+0F0h+var_A8]; Size
  ... truncated ...
```
