# CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)

- ea: `0x18000238c`
- end: `0x180002ca2`
- name: `?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z`
- size: `2326`
- prototype: `__int64 __usercall@<rax>(CADMCOMW *__hidden this@<rcx>, unsigned int@<edx>, int@<r8d>, unsigned int@<r9d>, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, struct _METADATA_RECORD *, struct _METADATA_RECORD *, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180003230`
- `0x180003400`
- `0x180003ca0`
- `0x180003dd0`
- `0x180003ef0`
- `0x180003fd0`
- `0x1800041a0`
- `0x1800063c0`
- `0x1800087f0`
- `0x180008ae0`
- `0x180009200`
- `0x180009520`

## callees

- `0x18000238c`
- `0x180005514`
- `0x18000e978`
- `0x18000eb50`
- `0x18000ec98`
- `0x18000eeb8`
- `0x18000f30c`
- `0x18000f730`
- `0x18000fb1e`
- `0x18000fb50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002b80`
- `KERNEL32!GetLastError` at `0x180002b80`
- `AUTHZ!AuthzReportSecurityEventFromParams` at `0x180002b76`
- `AUTHZ!AuthzReportSecurityEventFromParams` at `0x180002b76`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002bd2`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002bdf`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002bec`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002bf9`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c06`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c10`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c1a`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c24`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c31`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c3e`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c48`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c52`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c5f`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c6c`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002bd2`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002bdf`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002bec`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002bf9`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c06`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c10`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c1a`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c24`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c31`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c3e`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c48`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c52`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c5f`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180002c6c`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180002c77`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180002c77`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800028f6`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002975`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002a7f`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002a96`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800028f6`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002975`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002a7f`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002a96`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000244d`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000247e`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800024a4`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800024cf`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800024fa`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x180002523`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x180002546`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000257c`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800025af`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800025e5`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000261b`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x180002654`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000267f`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800026ab`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000244d`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000247e`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800024a4`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800024cf`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800024fa`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x180002523`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x180002546`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000257c`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800025af`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800025e5`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000261b`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x180002654`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000267f`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x1800026ab`
- `IisRTL!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180002bb7`
- `IisRTL!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180002bb7`
- `IisRTL!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000292a`
- `IisRTL!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000292a`

## pseudocode

```c
__int64 __fastcall CADMCOMW::AuditAccess(
        CADMCOMW *this,
        DWORD a2,
        signed int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned int a8,
        struct _METADATA_RECORD *a9,
        struct _METADATA_RECORD *a10,
        const unsigned __int16 *a11)
{
  char v15; // si
  USHORT v16; // di
  int CallerInfo; // ebx
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rcx
  unsigned int v24; // r8d
  __int64 v25; // rax
  unsigned __int64 v26; // rcx
  __int64 v27; // rax
  unsigned __int64 v28; // rdx
  __int64 v29; // rax
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  unsigned int v32; // ecx
  const struct STRU *v33; // rdi
  int v34; // eax
  __int64 v35; // rax
  unsigned __int64 v36; // rcx
  unsigned int v37; // r8d
  __int64 v38; // rax
  unsigned __int64 v39; // rcx
  __int64 v40; // rax
  PSID v41; // r9
  DWORD v42; // r8d
  unsigned __int64 v43; // rcx
  AUTHZ_SECURITY_EVENT_PROVIDER_HANDLE v44; // rdx
  signed int LastError; // eax
  struct _AUDIT_PARAMS pParams; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v48; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwAuditId; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v50; // [rsp+58h] [rbp-A8h]
  struct _METADATA_RECORD *v51; // [rsp+60h] [rbp-A0h]
  _QWORD v52[4]; // [rsp+68h] [rbp-98h] BYREF
  PSID pUserSid; // [rsp+88h] [rbp-78h]
  int v54; // [rsp+90h] [rbp-70h]
  __int16 v55; // [rsp+94h] [rbp-6Ch]
  _BYTE v56[32]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-48h]
  _BYTE v58[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v59; // [rsp+F0h] [rbp-10h]
  _BYTE v60[32]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v61; // [rsp+128h] [rbp+28h]
  _BYTE v62[32]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v63; // [rsp+160h] [rbp+60h]
  _BYTE v64[32]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v65; // [rsp+198h] [rbp+98h]
  _BYTE v66[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v67; // [rsp+1D0h] [rbp+D0h]
  _BYTE v68[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v69; // [rsp+208h] [rbp+108h]
  _BYTE v70[32]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v71; // [rsp+240h] [rbp+140h]
  _BYTE v72[32]; // [rsp+258h] [rbp+158h] BYREF
  __int64 v73; // [rsp+278h] [rbp+178h]
  _BYTE v74[56]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v75[32]; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int64 v76; // [rsp+2E8h] [rbp+1E8h]
  _BYTE v77[32]; // [rsp+300h] [rbp+200h] BYREF
  __int64 v78; // [rsp+320h] [rbp+220h]
  _BYTE v79[32]; // [rsp+338h] [rbp+238h] BYREF
  __int64 v80; // [rsp+358h] [rbp+258h]
  _BYTE v81[64]; // [rsp+370h] [rbp+270h] BYREF
  _DWORD v82[4]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _QWORD v83[2]; // [rsp+3C0h] [rbp+2C0h]
  int v84; // [rsp+3D0h] [rbp+2D0h]
  __int64 v85; // [rsp+3E0h] [rbp+2E0h]
  int v86; // [rsp+3F0h] [rbp+2F0h]
  __int64 v87; // [rsp+400h] [rbp+300h]
  __int64 v88; // [rsp+7B0h] [rbp+6B0h] BYREF
  int v89; // [rsp+7B8h] [rbp+6B8h]
  __int64 v90; // [rsp+7C0h] [rbp+6C0h] BYREF
  int v91; // [rsp+7C8h] [rbp+6C8h]
  unsigned __int16 v92[12]; // [rsp+7D0h] [rbp+6D0h] BYREF
  _OWORD v93[2]; // [rsp+7E8h] [rbp+6E8h] BYREF
  __int64 v94; // [rsp+808h] [rbp+708h]
  _OWORD v95[2]; // [rsp+810h] [rbp+710h] BYREF
  __int64 v96; // [rsp+830h] [rbp+730h]
  _OWORD v97[3]; // [rsp+838h] [rbp+738h] BYREF
  __int16 v98; // [rsp+868h] [rbp+768h]
  _OWORD v99[4]; // [rsp+870h] [rbp+770h] BYREF
  _OWORD v100[4]; // [rsp+8B0h] [rbp+7B0h] BYREF
  _OWORD v101[4]; // [rsp+8F0h] [rbp+7F0h] BYREF
  _OWORD v102[4]; // [rsp+930h] [rbp+830h] BYREF
  unsigned __int16 v103[56]; // [rsp+970h] [rbp+870h] BYREF
  unsigned __int16 v104[56]; // [rsp+9E0h] [rbp+8E0h] BYREF
  unsigned __int16 v105[104]; // [rsp+A50h] [rbp+950h] BYREF
  unsigned __int16 v106[104]; // [rsp+B20h] [rbp+A20h] BYREF

  v48 = a5;
  v50 = a7;
  v51 = a10;
  dwAuditId = a2;
  pUserSid = v52;
  v52[0] = 0;
  v54 = 32;
  v55 = 256;
  memset(&pParams, 0, sizeof(pParams));
  v94 = 0;
  memset(v93, 0, sizeof(v93));
  STRU::STRU((STRU *)v72, (unsigned __int16 *)v93, 0x14u);
  v96 = 0;
  memset(v95, 0, sizeof(v95));
  STRU::STRU((STRU *)v70, (unsigned __int16 *)v95, 0x14u);
  v88 = 0;
  v89 = 0;
  STRU::STRU((STRU *)v60, (unsigned __int16 *)&v88, 6u);
  memset_0(v105, 0, 0xC8u);
  STRU::STRU((STRU *)v58, v105, 0x64u);
  memset_0(v103, 0, 0x64u);
  STRU::STRU((STRU *)v68, v103, 0x32u);
  memset_0(v104, 0, 0x64u);
  STRU::STRU((STRU *)v66, v104, 0x32u);
  v90 = 0;
  v91 = 0;
  STRU::STRU((STRU *)v64, (unsigned __int16 *)&v90, 6u);
  memset(v99, 0, 60);
  STRU::STRU((STRU *)v62, (unsigned __int16 *)v99, 0x1Eu);
  memset(v100, 0, 60);
  STRU::STRU((STRU *)v56, (unsigned __int16 *)v100, 0x1Eu);
  memset(v101, 0, 60);
  STRU::STRU((STRU *)v81, (unsigned __int16 *)v101, 0x1Eu);
  memset(v102, 0, 60);
  STRU::STRU((STRU *)v79, (unsigned __int16 *)v102, 0x1Eu);
  v98 = 0;
  memset(v97, 0, sizeof(v97));
  STRU::STRU((STRU *)v77, (unsigned __int16 *)v97, 0x19u);
  memset(v92, 0, 22);
  STRU::STRU((STRU *)v75, v92, 0xBu);
  memset_0(v106, 0, 0xC8u);
  STRU::STRU((STRU *)v74, v106, 0x64u);
  memset_0(v82, 0, 0x400u);
  v15 = 1;
  v16 = 3;
  switch ( a2 )
  {
    case 0x1197u:
      goto LABEL_14;
    case 0x1198u:
      v15 = 33;
      break;
    case 0x1199u:
      v15 = 29;
      break;
    case 0x119Au:
      v15 = 13;
      break;
    case 0x119Cu:
LABEL_14:
      v15 = 3;
      break;
    case 0x119Eu:
    case 0x119Fu:
      v15 = 32;
      break;
    case 0x11A0u:
      v15 = 35;
      break;
  }
  CallerInfo = RetrieveCallerInfo((struct BUFFER *)v52, (struct STRU *)v72, (struct STRU *)v70, (struct STRU *)v77);
  if ( CallerInfo < 0 )
    goto LABEL_57;
  v83[0] = v73;
  v85 = v71;
  v87 = v78;
  v82[0] = 2;
  v84 = 2;
  v86 = 2;
  pParams.Count = 3;
  if ( (v15 & 1) != 0 )
  {
    CallerInfo = RetrieveFullPath(this, a4, v48, (struct STRU *)v68);
    if ( CallerInfo < 0 )
      goto LABEL_57;
    v18 = v69;
    v19 = 32LL * pParams.Count;
    v16 = pParams.Count + 1;
    v82[v19 / 4] = 2;
    v83[v19 / 8] = v18;
    pParams.Count = v16;
  }
  if ( (v15 & 2) != 0 )
  {
    RetrieveFullPath(this, a6, v50, (struct STRU *)v66);
    v20 = v67;
    v21 = 32LL * pParams.Count;
    v16 = ++pParams.Count;
    v82[v21 / 4] = 2;
    v83[v21 / 8] = v20;
  }
  if ( (v15 & 4) != 0 )
  {
    CallerInfo = RetrievePropertyName(*((struct IMDCOM **)this + 4), a8, (struct STRU *)v62);
    if ( CallerInfo < 0 )
      goto LABEL_57;
    CallerInfo = DisplayDwordRadix(a8, (struct STRU *)v64, 10);
    if ( CallerInfo < 0 )
      goto LABEL_57;
    v22 = v65;
    v23 = 32LL * pParams.Count;
    v24 = (unsigned __int16)(pParams.Count + 1);
    v82[v23 / 4] = 2;
    v83[v23 / 8] = v22;
    v25 = v63;
    v26 = 32LL * v24;
    v16 = v24 + 1;
    pParams.Count = v24 + 1;
    v82[v26 / 4] = 2;
    v83[v26 / 8] = v25;
  }
  if ( (v15 & 8) != 0 )
  {
    if ( a9 )
    {
      if ( (a9->dwMDAttributes & 0x20) != 0 )
      {
        CallerInfo = STRU::Copy((STRU *)v56, L"METADATA_ISINHERITED\r\n");
        if ( CallerInfo < 0 )
          goto LABEL_57;
      }
      CallerInfo = DisplayValue(a9, (struct STRU *)v81);
      if ( CallerInfo < 0 )
        goto LABEL_57;
      CallerInfo = STRU::Append((STRU *)v56, (const struct STRU *)v81);
      if ( CallerInfo < 0 )
        goto LABEL_57;
    }
    else if ( (int)STRU::Copy((STRU *)v56, L"-") < 0 )
    {
      CallerInfo = -2147024882;
      goto LABEL_57;
    }
    v27 = v57;
    v28 = 32LL * pParams.Count;
    v16 = ++pParams.Count;
    v82[v28 / 4] = 2;
    v83[v28 / 8] = v27;
  }
  if ( (v15 & 0x10) != 0 )
  {
    CallerInfo = DisplayValue(v51, (struct STRU *)v79);
    if ( CallerInfo < 0 )
      goto LABEL_57;
    v29 = v80;
    v30 = 32LL * pParams.Count;
    v16 = ++pParams.Count;
    v82[v30 / 4] = 2;
    v83[v30 / 8] = v29;
  }
  if ( (v15 & 0x20) != 0 )
  {
    v31 = 32LL * v16;
    pParams.Count = v16 + 1;
    v82[v31 / 4] = 2;
    v83[v31 / 8] = a11;
  }
  v33 = (CADMCOMW *)((char *)this + 200);
  LODWORD(v48) = *((_DWORD *)this + 42);
  v32 = (unsigned int)v48;
  if ( CADMCOMW::sm_dwProcessIdThis != (_DWORD)v48 || *((_DWORD *)this + 62) )
  {
    if ( this == (CADMCOMW *)-200LL )
    {
      CallerInfo = -2147024809;
      goto LABEL_57;
    }
  }
  else
  {
    CallerInfo = CADMCOMW::GetCallerPIDAndProcessName(
                   (CADMCOMW *)(unsigned int)v48,
                   (unsigned int *)&v48,
                   (struct STRU *)v74,
                   0,
                   *((_DWORD *)this + 224));
    if ( CallerInfo < 0 )
      goto LABEL_57;
    v32 = (unsigned int)v48;
    v33 = (const struct STRU *)v74;
  }
  if ( v32 == -1 )
  {
    CallerInfo = STRU::Copy((STRU *)v60, L"-");
    if ( CallerInfo < 0 )
      goto LABEL_48;
    v34 = STRU::Copy((STRU *)v58, L"-");
  }
  else
  {
    CallerInfo = DisplayDwordRadix(v32, (struct STRU *)v60, 10);
    if ( CallerInfo < 0 )
    {
LABEL_48:
      if ( CallerInfo < 0 )
        goto LABEL_57;
      goto LABEL_49;
    }
    v34 = STRU::Copy((STRU *)v58, v33);
  }
  CallerInfo = v34;
  if ( v34 < 0 )
    goto LABEL_48;
LABEL_49:
  v35 = v61;
  v36 = 32LL * pParams.Count;
  v37 = (unsigned __int16)(pParams.Count + 1);
  v82[v36 / 4] = 2;
  v83[v36 / 8] = v35;
  v38 = v59;
  v39 = 32LL * v37;
  pParams.Count = v37 + 1;
  v82[v39 / 4] = 2;
  v83[v39 / 8] = v38;
  CallerInfo = DisplayAsHex(a3, (struct STRU *)v75);
  if ( CallerInfo >= 0 )
  {
    v40 = v76;
    v41 = pUserSid;
    v42 = dwAuditId;
    v43 = 32LL * pParams.Count++;
    v44 = g_hEventProvider;
    pParams.Length = 24;
    v82[v43 / 4] = 2;
    v83[v43 / 8] = v40;
    pParams.Parameters = (AUDIT_PARAM *)v82;
    pParams.Flags = a3 >= 0;
    if ( AuthzReportSecurityEventFromParams(0, v44, v42, v41, &pParams) )
    {
      CallerInfo = 0;
    }
    else
    {
      LastError = GetLastError();
      CallerInfo = LastError;
      if ( LastError > 0 )
        CallerInfo = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_57:
  STRU::~STRU((STRU *)v74);
  STRU::~STRU((STRU *)v75);
  STRU::~STRU((STRU *)v77);
  STRU::~STRU((STRU *)v79);
  STRU::~STRU((STRU *)v81);
  STRU::~STRU((STRU *)v56);
  STRU::~STRU((STRU *)v62);
  STRU::~STRU((STRU *)v64);
  STRU::~STRU((STRU *)v66);
  STRU::~STRU((STRU *)v68);
  STRU::~STRU((STRU *)v58);
  STRU::~STRU((STRU *)v60);
  STRU::~STRU((STRU *)v70);
  STRU::~STRU((STRU *)v72);
  BUFFER::~BUFFER((BUFFER *)v52);
  return (unsigned int)CallerInfo;
}

```

## disassembly

```asm
0x18000238c  push    rbp
0x18000238e  push    rbx
0x18000238f  push    rsi
0x180002390  push    rdi
0x180002391  push    r12
0x180002393  push    r13
0x180002395  push    r14
0x180002397  push    r15
0x180002399  lea     rbp, [rsp-0B08h]
0x1800023a1  sub     rsp, 0C08h
0x1800023a8  mov     rax, cs:__security_cookie
0x1800023af  xor     rax, rsp
0x1800023b2  mov     [rbp+0B40h+var_50], rax
0x1800023b9  mov     rax, [rbp+0B40h+arg_20]
0x1800023c0  xorps   xmm1, xmm1
0x1800023c3  mov     r15, [rbp+0B40h+arg_40]
0x1800023ca  mov     r12d, r8d
0x1800023cd  mov     [rsp+0C40h+var_BF8], rax
0x1800023d2  mov     ebx, edx
0x1800023d4  mov     rax, [rbp+0B40h+arg_30]
0x1800023db  mov     r14, rcx
0x1800023de  mov     [rsp+0C40h+var_BE8], rax
0x1800023e3  lea     rcx, [rbp+0B40h+var_9E8]
0x1800023ea  mov     rax, [rbp+0B40h+arg_48]
0x1800023f1  xorps   xmm0, xmm0
0x1800023f4  mov     [rsp+0C40h+var_BE0], rax
0x1800023f9  mov     r13d, r9d
0x1800023fc  lea     rax, [rsp+0C40h+var_BD8]
0x180002401  mov     [rsp+0C40h+dwAuditId], edx
0x180002405  mov     [rbp+0B40h+pUserSid], rax
0x180002409  lea     rdx, [rbp+0B40h+var_458]
0x180002410  xor     eax, eax
0x180002412  mov     [rsp+0C40h+var_BD8], 0
0x18000241b  mov     [rbp+0B40h+var_BB0], 20h ; ' '
0x180002422  mov     [rbp+0B40h+var_BAC], 100h
0x180002428  movups  xmmword ptr [rsp+0C40h+var_C10.Length], xmm0
0x18000242d  lea     edi, [rax+14h]
0x180002430  mov     [rsp+0C40h+var_C10.Parameters], rax
0x180002435  mov     r8d, edi
0x180002438  mov     [rbp+0B40h+var_438], rax
0x18000243f  movups  [rbp+0B40h+var_458], xmm1
0x180002446  movups  [rbp+0B40h+var_448], xmm1
0x18000244d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002453  xorps   xmm0, xmm0
0x180002456  lea     rdx, [rbp+0B40h+var_430]
0x18000245d  xor     eax, eax
0x18000245f  lea     rcx, [rbp+0B40h+var_A20]
0x180002466  mov     r8d, edi
0x180002469  mov     [rbp+0B40h+var_410], rax
0x180002470  movups  [rbp+0B40h+var_430], xmm0
0x180002477  movups  [rbp+0B40h+var_420], xmm0
0x18000247e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002484  xor     eax, eax
0x180002486  lea     esi, [rdi-0Eh]
0x180002489  mov     r8d, esi
0x18000248c  mov     [rbp+0B40h+var_490], rax
0x180002493  lea     rdx, [rbp+0B40h+var_490]
0x18000249a  mov     [rbp+0B40h+var_488], eax
0x1800024a0  lea     rcx, [rbp+0B40h+var_B38]
0x1800024a4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800024aa  xor     edx, edx; Val
0x1800024ac  lea     rcx, [rbp+0B40h+var_1F0]; void *
0x1800024b3  mov     r8d, 0C8h; Size
0x1800024b9  call    memset_0
0x1800024be  lea     edi, [rsi+5Eh]
0x1800024c1  mov     r8d, edi
0x1800024c4  lea     rdx, [rbp+0B40h+var_1F0]
0x1800024cb  lea     rcx, [rbp+0B40h+var_B70]
0x1800024cf  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800024d5  mov     r8d, edi; Size
0x1800024d8  lea     rcx, [rbp+0B40h+var_2D0]; void *
0x1800024df  xor     edx, edx; Val
0x1800024e1  call    memset_0
0x1800024e6  lea     edi, [rsi+2Ch]
0x1800024e9  mov     r8d, edi
0x1800024ec  lea     rdx, [rbp+0B40h+var_2D0]
0x1800024f3  lea     rcx, [rbp+0B40h+var_A58]
0x1800024fa  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002500  xor     edx, edx; Val
0x180002502  lea     r8d, [rsi+5Eh]; Size
0x180002506  lea     rcx, [rbp+0B40h+var_260]; void *
0x18000250d  call    memset_0
0x180002512  mov     r8d, edi
0x180002515  lea     rdx, [rbp+0B40h+var_260]
0x18000251c  lea     rcx, [rbp+0B40h+var_A90]
0x180002523  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002529  xor     eax, eax
0x18000252b  lea     rdx, [rbp+0B40h+var_480]
0x180002532  mov     r8d, esi
0x180002535  mov     [rbp+0B40h+var_480], rax
0x18000253c  lea     rcx, [rbp+0B40h+var_AC8]
0x180002540  mov     [rbp+0B40h+var_478], eax
0x180002546  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000254c  xorps   xmm0, xmm0
0x18000254f  movups  xmmword ptr [rbp+0B40h+var_3B0], xmm0
0x180002556  lea     edi, [rsi+18h]
0x180002559  mov     r8d, edi
0x18000255c  lea     rdx, [rbp+0B40h+var_3D0]
0x180002563  lea     rcx, [rbp+0B40h+var_B00]
0x180002567  movups  [rbp+0B40h+var_3D0], xmm0
0x18000256e  movups  [rbp+0B40h+var_3C0], xmm0
0x180002575  movups  xmmword ptr [rbp+0B40h+var_3B0+0Ch], xmm0
0x18000257c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002582  xorps   xmm0, xmm0
0x180002585  lea     rdx, [rbp+0B40h+var_390]
0x18000258c  movups  xmmword ptr [rbp+0B40h+var_370], xmm0
0x180002593  mov     r8d, edi
0x180002596  lea     rcx, [rbp+0B40h+var_BA8]
0x18000259a  movups  xmmword ptr [rbp+0B40h+var_370+0Ch], xmm0
0x1800025a1  movups  [rbp+0B40h+var_390], xmm0
0x1800025a8  movups  [rbp+0B40h+var_380], xmm0
0x1800025af  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800025b5  xorps   xmm0, xmm0
0x1800025b8  lea     rdx, [rbp+0B40h+var_350]
0x1800025bf  movups  xmmword ptr [rbp+0B40h+var_330], xmm0
0x1800025c6  mov     r8d, edi
0x1800025c9  lea     rcx, [rbp+0B40h+var_8D0]
0x1800025d0  movups  xmmword ptr [rbp+0B40h+var_330+0Ch], xmm0
0x1800025d7  movups  [rbp+0B40h+var_350], xmm0
0x1800025de  movups  [rbp+0B40h+var_340], xmm0
0x1800025e5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800025eb  xorps   xmm0, xmm0
0x1800025ee  lea     rdx, [rbp+0B40h+var_310]
0x1800025f5  movups  xmmword ptr [rbp+0B40h+var_2F0], xmm0
0x1800025fc  mov     r8d, edi
0x1800025ff  lea     rcx, [rbp+0B40h+var_908]
0x180002606  movups  xmmword ptr [rbp+0B40h+var_2F0+0Ch], xmm0
0x18000260d  movups  [rbp+0B40h+var_310], xmm0
0x180002614  movups  [rbp+0B40h+var_300], xmm0
0x18000261b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002621  xorps   xmm0, xmm0
0x180002624  lea     r8d, [rsi+13h]
0x180002628  xor     eax, eax
0x18000262a  lea     rdx, [rbp+0B40h+var_408]
0x180002631  lea     rcx, [rbp+0B40h+var_940]
0x180002638  mov     [rbp+0B40h+var_3D8], ax
0x18000263f  movups  [rbp+0B40h+var_408], xmm0
0x180002646  movups  [rbp+0B40h+var_3F8], xmm0
0x18000264d  movups  [rbp+0B40h+var_3E8], xmm0
0x180002654  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000265a  xorps   xmm0, xmm0
0x18000265d  lea     r8d, [rsi+5]
0x180002661  xor     eax, eax
0x180002663  lea     rdx, [rbp+0B40h+var_470]
0x18000266a  movups  xmmword ptr [rbp+0B40h+var_470], xmm0
0x180002671  lea     rcx, [rbp+0B40h+var_978]
0x180002678  mov     qword ptr [rbp+0B40h+var_470+0Eh], rax
0x18000267f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002685  xor     edx, edx; Val
0x180002687  lea     rcx, [rbp+0B40h+var_120]; void *
0x18000268e  mov     r8d, 0C8h; Size
0x180002694  call    memset_0
0x180002699  lea     r8d, [rsi+5Eh]
0x18000269d  lea     rdx, [rbp+0B40h+var_120]
0x1800026a4  lea     rcx, [rbp+0B40h+var_9B0]
0x1800026ab  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800026b1  xor     edx, edx; Val
0x1800026b3  lea     rcx, [rbp+0B40h+var_890]; void *
0x1800026ba  mov     r8d, 400h; Size
0x1800026c0  call    memset_0
0x1800026c5  mov     eax, ebx
0x1800026c7  lea     esi, [rdi-1Dh]
0x1800026ca  lea     edi, [rsi+2]
0x1800026cd  sub     eax, 1197h
0x1800026d2  jz      short loc_180002713
0x1800026d4  sub     eax, esi
0x1800026d6  jz      short loc_18000270C
0x1800026d8  sub     eax, esi
0x1800026da  jz      short loc_180002705
0x1800026dc  sub     eax, esi
0x1800026de  jz      short loc_1800026FE
0x1800026e0  sub     eax, 2
0x1800026e3  jz      short loc_180002713
0x1800026e5  sub     eax, 2
0x1800026e8  jz      short loc_1800026F7
0x1800026ea  sub     eax, esi
0x1800026ec  jz      short loc_1800026F7
0x1800026ee  cmp     eax, esi
0x1800026f0  jnz     short loc_180002715
0x1800026f2  lea     esi, [rdi+20h]
0x1800026f5  jmp     short loc_180002715
0x1800026f7  mov     esi, 20h ; ' '
0x1800026fc  jmp     short loc_180002715
0x1800026fe  mov     esi, 0Dh
0x180002703  jmp     short loc_180002715
0x180002705  mov     esi, 1Dh
0x18000270a  jmp     short loc_180002715
0x18000270c  mov     esi, 21h ; '!'
0x180002711  jmp     short loc_180002715
0x180002713  mov     esi, edi
0x180002715  lea     r9, [rbp+0B40h+var_940]; struct STRU *
0x18000271c  lea     r8, [rbp+0B40h+var_A20]; struct STRU *
0x180002723  lea     rdx, [rbp+0B40h+var_9E8]; struct STRU *
0x18000272a  lea     rcx, [rsp+0C40h+var_BD8]; struct BUFFER *
0x18000272f  call    ?RetrieveCallerInfo@@YAJPEAVBUFFER@@PEAVSTRU@@11@Z; RetrieveCallerInfo(BUFFER *,STRU *,STRU *,STRU *)
0x180002734  mov     ebx, eax
0x180002736  test    eax, eax
0x180002738  js      loc_180002BCB
0x18000273e  mov     rax, [rbp+0B40h+var_9C8]
0x180002745  mov     ecx, 2
0x18000274a  mov     [rbp+0B40h+var_880], rax
0x180002751  mov     rax, [rbp+0B40h+var_A00]
0x180002758  mov     [rbp+0B40h+var_860], rax
0x18000275f  mov     rax, [rbp+0B40h+var_920]
0x180002766  lea     ebx, [rcx-1]
0x180002769  mov     [rbp+0B40h+var_840], rax
0x180002770  mov     [rbp+0B40h+var_890], ecx
0x180002776  mov     [rbp+0B40h+var_870], ecx
0x18000277c  mov     [rbp+0B40h+var_850], ecx
0x180002782  mov     [rsp+0C40h+var_C10.Count], di
0x180002787  test    bl, sil
0x18000278a  jz      short loc_1800027E3
0x18000278c  mov     r8, [rsp+0C40h+var_BF8]; unsigned __int16 *
0x180002791  lea     r9, [rbp+0B40h+var_A58]; struct STRU *
0x180002798  mov     edx, r13d; unsigned int
0x18000279b  mov     rcx, r14; struct CADMCOMW *
0x18000279e  call    ?RetrieveFullPath@@YAJPEAVCADMCOMW@@KPEBGPEAVSTRU@@@Z; RetrieveFullPath(CADMCOMW *,ulong,ushort const *,STRU *)
0x1800027a3  mov     ebx, eax
0x1800027a5  test    eax, eax
0x1800027a7  js      loc_180002BCB
0x1800027ad  movzx   edi, [rsp+0C40h+var_C10.Count]
0x1800027b2  mov     r13d, 2
0x1800027b8  mov     rax, [rbp+0B40h+var_A38]
0x1800027bf  mov     ecx, edi
0x1800027c1  shl     rcx, 5
0x1800027c5  lea     ebx, [r13-1]
0x1800027c9  add     di, bx
0x1800027cc  mov     [rbp+rcx+0B40h+var_890], r13d
0x1800027d4  mov     [rbp+rcx+0B40h+var_880], rax
0x1800027dc  mov     [rsp+0C40h+var_C10.Count], di
0x1800027e1  jmp     short loc_1800027E9
0x1800027e3  mov     r13d, 2
0x1800027e9  test    r13b, sil
0x1800027ec  jz      short loc_180002832
0x1800027ee  mov     r8, [rsp+0C40h+var_BE8]; unsigned __int16 *
0x1800027f3  lea     r9, [rbp+0B40h+var_A90]; struct STRU *
0x1800027fa  mov     edx, [rbp+0B40h+arg_28]; unsigned int
0x180002800  mov     rcx, r14; struct CADMCOMW *
0x180002803  call    ?RetrieveFullPath@@YAJPEAVCADMCOMW@@KPEBGPEAVSTRU@@@Z; RetrieveFullPath(CADMCOMW *,ulong,ushort const *,STRU *)
0x180002808  movzx   edi, [rsp+0C40h+var_C10.Count]
0x18000280d  mov     rax, [rbp+0B40h+var_A70]
0x180002814  mov     ecx, edi
0x180002816  shl     rcx, 5
0x18000281a  add     di, bx
0x18000281d  mov     [rsp+0C40h+var_C10.Count], di
0x180002822  mov     [rbp+rcx+0B40h+var_890], r13d
0x18000282a  mov     [rbp+rcx+0B40h+var_880], rax
0x180002832  test    sil, 4
0x180002836  jz      loc_1800028D1
0x18000283c  mov     edx, [rbp+0B40h+arg_38]; unsigned int
0x180002842  lea     r8, [rbp+0B40h+var_B00]; struct STRU *
0x180002846  mov     rcx, [r14+20h]; struct IMDCOM *
0x18000284a  call    ?RetrievePropertyName@@YAJPEAUIMDCOM@@KPEAVSTRU@@@Z; RetrievePropertyName(IMDCOM *,ulong,STRU *)
0x18000284f  mov     ebx, eax
0x180002851  test    eax, eax
0x180002853  js      loc_180002BCB
0x180002859  mov     ecx, [rbp+0B40h+arg_38]; unsigned int
0x18000285f  lea     rdx, [rbp+0B40h+var_AC8]; struct STRU *
0x180002863  mov     r8d, 0Ah; int
0x180002869  call    ?DisplayDwordRadix@@YAJKPEAVSTRU@@H@Z; DisplayDwordRadix(ulong,STRU *,int)
0x18000286e  mov     ebx, eax
0x180002870  test    eax, eax
0x180002872  js      loc_180002BCB
0x180002878  movzx   edx, [rsp+0C40h+var_C10.Count]
0x18000287d  mov     r9d, 1
0x180002883  mov     rax, [rbp+0B40h+var_AA8]
0x18000288a  mov     ecx, edx
0x18000288c  shl     rcx, 5
0x180002890  add     dx, r9w
0x180002894  movzx   r8d, dx
0x180002898  mov     [rbp+rcx+0B40h+var_890], r13d
0x1800028a0  mov     [rbp+rcx+0B40h+var_880], rax
0x1800028a8  mov     ecx, r8d
0x1800028ab  mov     rax, [rbp+0B40h+var_AE0]
0x1800028af  shl     rcx, 5
0x1800028b3  add     r8w, r9w
0x1800028b7  movzx   edi, r8w
0x1800028bb  mov     [rsp+0C40h+var_C10.Count], r8w
0x1800028c1  mov     [rbp+rcx+0B40h+var_890], r13d
0x1800028c9  mov     [rbp+rcx+0B40h+var_880], rax
0x1800028d1  test    sil, 8
0x1800028d5  jz      loc_180002989
0x1800028db  test    r15, r15
0x1800028de  jz      loc_18000296A
0x1800028e4  test    byte ptr [r15+4], 20h
0x1800028e9  jz      short loc_180002906
0x1800028eb  lea     rdx, aMetadataIsinhe; "METADATA_ISINHERITED\r\n"
0x1800028f2  lea     rcx, [rbp+0B40h+var_BA8]
0x1800028f6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800028fc  mov     ebx, eax
0x1800028fe  test    eax, eax
0x180002900  js      loc_180002BCB
0x180002906  lea     rdx, [rbp+0B40h+var_8D0]; struct STRU *
0x18000290d  mov     rcx, r15; struct _METADATA_RECORD *
0x180002910  call    ?DisplayValue@@YAJPEAU_METADATA_RECORD@@PEAVSTRU@@@Z; DisplayValue(_METADATA_RECORD *,STRU *)
0x180002915  mov     ebx, eax
0x180002917  test    eax, eax
0x180002919  js      loc_180002BCB
0x18000291f  lea     rdx, [rbp+0B40h+var_8D0]
0x180002926  lea     rcx, [rbp+0B40h+var_BA8]
  ... truncated ...
```
