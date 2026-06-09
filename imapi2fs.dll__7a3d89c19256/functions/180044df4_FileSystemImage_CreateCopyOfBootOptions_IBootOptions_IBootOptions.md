# FileSystemImage::CreateCopyOfBootOptions(IBootOptions *,IBootOptions * *)

- ea: `0x180044df4`
- end: `0x180046001`
- name: `?CreateCopyOfBootOptions@FileSystemImage@@AEAAXPEAUIBootOptions@@PEAPEAU2@@Z`
- size: `4621`
- prototype: `void __fastcall(FileSystemImage *__hidden this, struct IBootOptions *, struct IBootOptions **)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180047fa8`
- `0x180057e60`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x18000960c`
- `0x180018eec`
- `0x1800251dc`
- `0x180028798`
- `0x180028ca8`
- `0x18002d4e4`
- `0x180044df4`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180044eae`
- `ole32!CoCreateInstance` at `0x180044eae`
- `ole32!CreateStreamOnHGlobal` at `0x180044f52`
- `ole32!CreateStreamOnHGlobal` at `0x180044f52`
- `OLEAUT32!__imp_SysFreeString` at `0x1800457e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800457e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall FileSystemImage::CreateCopyOfBootOptions(FileSystemImage *this, struct IBootOptions *a2, LPVOID *a3)
{
  CIMAPIException *v5; // rax
  CIMAPIException *v6; // rax
  HRESULT v7; // esi
  CIMAPIException *v8; // rdi
  CIMAPIException *v9; // rax
  CIMAPIException *v10; // rax
  __int64 v11; // rax
  HRESULT v12; // esi
  CIMAPIException *v13; // rdi
  CIMAPIException *v14; // rax
  CIMAPIException *v15; // rax
  __int64 v16; // rax
  int v17; // esi
  int v18; // esi
  CIMAPIException *v19; // rdi
  CIMAPIException *v20; // rax
  CIMAPIException *v21; // rax
  __int64 v22; // rax
  int v23; // esi
  int v24; // edi
  CIMAPIException *v25; // rsi
  CIMAPIException *v26; // rax
  CIMAPIException *v27; // rax
  __int64 v28; // rax
  unsigned int v29; // edx
  CIMAPIException *v30; // rsi
  CIMAPIException *v31; // rax
  CIMAPIException *v32; // rax
  __int64 v33; // rax
  CIMAPIException *v34; // rsi
  CIMAPIException *v35; // rax
  CIMAPIException *v36; // rax
  __int64 v37; // rax
  int v38; // r14d
  CIMAPIException *v39; // rdi
  CIMAPIException *v40; // rax
  CIMAPIException *v41; // rax
  __int64 v42; // rax
  int v43; // r14d
  CIMAPIException *v44; // rdi
  CIMAPIException *v45; // rax
  CIMAPIException *v46; // rax
  __int64 v47; // rax
  int v48; // r14d
  CIMAPIException *v49; // rdi
  CIMAPIException *v50; // rax
  CIMAPIException *v51; // rax
  __int64 v52; // rax
  int v53; // r14d
  int v54; // esi
  CIMAPIException *v55; // rdi
  CIMAPIException *v56; // rax
  CIMAPIException *v57; // rax
  __int64 v58; // rax
  int v59; // esi
  CIMAPIException *v60; // rdi
  CIMAPIException *v61; // rax
  CIMAPIException *v62; // rax
  __int64 v63; // rax
  int v64; // esi
  CIMAPIException *v65; // rdi
  CIMAPIException *v66; // rax
  CIMAPIException *v67; // rax
  __int64 v68; // rax
  int v69; // esi
  CIMAPIException *v70; // rdi
  CIMAPIException *v71; // rax
  CIMAPIException *v72; // rax
  __int64 v73; // rax
  CIMAPIException *v74; // rdi
  CIMAPIException *v75; // rax
  CIMAPIException *v76; // rax
  __int64 v77; // rax
  CIMAPIException *v78; // rdi
  CIMAPIException *v79; // rax
  CIMAPIException *v80; // rax
  __int64 v81; // rax
  CIMAPIException *v82; // rax
  CIMAPIException *v83; // rax
  CIMAPIException *v84; // rax
  CIMAPIException *v85; // rax
  CIMAPIException *v86; // rax
  CIMAPIException *v87; // rax
  CIMAPIException *v88; // rax
  CIMAPIException *v89; // rax
  CIMAPIException *v90; // rax
  CIMAPIException *v91; // rax
  CIMAPIException *v92; // rax
  CIMAPIException *v93; // rax
  CIMAPIException *v94; // rax
  CIMAPIException *v95; // rax
  CIMAPIException *v96; // rax
  CIMAPIException *v97; // rax
  CIMAPIException *v98; // [rsp+30h] [rbp-E88h] BYREF
  CIMAPIException *v99; // [rsp+38h] [rbp-E80h] BYREF
  CIMAPIException *v100; // [rsp+40h] [rbp-E78h]
  LPVOID ppv; // [rsp+48h] [rbp-E70h] BYREF
  unsigned int v102; // [rsp+50h] [rbp-E68h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-E60h] BYREF
  __int64 v104; // [rsp+60h] [rbp-E58h] BYREF
  int v105; // [rsp+68h] [rbp-E50h] BYREF
  unsigned int v106; // [rsp+6Ch] [rbp-E4Ch] BYREF
  unsigned int v107; // [rsp+70h] [rbp-E48h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-E40h] BYREF
  _BYTE v109[8]; // [rsp+80h] [rbp-E38h] BYREF
  _BYTE v110[8]; // [rsp+88h] [rbp-E30h] BYREF
  _BYTE v111[8]; // [rsp+90h] [rbp-E28h] BYREF
  _BYTE v112[8]; // [rsp+98h] [rbp-E20h] BYREF
  _BYTE v113[8]; // [rsp+A0h] [rbp-E18h] BYREF
  _BYTE v114[8]; // [rsp+A8h] [rbp-E10h] BYREF
  _BYTE v115[8]; // [rsp+B0h] [rbp-E08h] BYREF
  _BYTE v116[8]; // [rsp+B8h] [rbp-E00h] BYREF
  _BYTE v117[8]; // [rsp+C0h] [rbp-DF8h] BYREF
  _BYTE v118[8]; // [rsp+C8h] [rbp-DF0h] BYREF
  _BYTE v119[8]; // [rsp+D0h] [rbp-DE8h] BYREF
  _BYTE v120[8]; // [rsp+D8h] [rbp-DE0h] BYREF
  _BYTE v121[8]; // [rsp+E0h] [rbp-DD8h] BYREF
  _BYTE v122[8]; // [rsp+E8h] [rbp-DD0h] BYREF
  _BYTE v123[8]; // [rsp+F0h] [rbp-DC8h] BYREF
  _BYTE v124[8]; // [rsp+F8h] [rbp-DC0h] BYREF
  _BYTE v125[88]; // [rsp+100h] [rbp-DB8h] BYREF
  _BYTE v126[88]; // [rsp+158h] [rbp-D60h] BYREF
  _BYTE v127[88]; // [rsp+1B0h] [rbp-D08h] BYREF
  _BYTE v128[88]; // [rsp+208h] [rbp-CB0h] BYREF
  _BYTE v129[88]; // [rsp+260h] [rbp-C58h] BYREF
  _BYTE v130[88]; // [rsp+2B8h] [rbp-C00h] BYREF
  _BYTE v131[88]; // [rsp+310h] [rbp-BA8h] BYREF
  _BYTE v132[88]; // [rsp+368h] [rbp-B50h] BYREF
  _BYTE v133[88]; // [rsp+3C0h] [rbp-AF8h] BYREF
  _BYTE v134[88]; // [rsp+418h] [rbp-AA0h] BYREF
  _BYTE v135[88]; // [rsp+470h] [rbp-A48h] BYREF
  _BYTE v136[88]; // [rsp+4C8h] [rbp-9F0h] BYREF
  _BYTE v137[88]; // [rsp+520h] [rbp-998h] BYREF
  _BYTE v138[88]; // [rsp+578h] [rbp-940h] BYREF
  _BYTE v139[88]; // [rsp+5D0h] [rbp-8E8h] BYREF
  _BYTE pExceptionObject[88]; // [rsp+628h] [rbp-890h] BYREF
  _BYTE v141[2048]; // [rsp+680h] [rbp-838h] BYREF

  try
  {
    ppv = 0;
    v104 = 0;
    ppstm = 0;
    bstrString = 0;
    if ( *((_DWORD *)this + 152) )
    {
      v5 = (CIMAPIException *)operator new(0x58u);
      v99 = v5;
      if ( v5 )
        v6 = CIMAPIException::CIMAPIException(v5, -1062555319);
      else
        v6 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v6);
      if ( v98 )
      {
        if ( *(_QWORD *)v98 )
        {
          v82 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
          CIMAPIException::SetCodeRefInfo(v82, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 457);
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v124, &v98);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v124;
        }
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v125,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v125;
    }
    v7 = CoCreateInstance(&CLSID_BootOptions, 0, 0x17u, &GUID_2c941fd4_975b_59be_a960_9a2a262853a5, &ppv);
    if ( v7 < 0 )
    {
      v8 = (CIMAPIException *)operator new(0x58u);
      v98 = v8;
      if ( v8 )
      {
        v9 = (CIMAPIException *)operator new(0x58u);
        v100 = v9;
        if ( v9 )
          v10 = CIMAPIException::CIMAPIException(v9, v7);
        else
          v10 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v10);
        v11 = CIMAPIException::CIMAPIException(v8, &v99);
      }
      else
      {
        v11 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v11);
      if ( v98 && *(_QWORD *)v98 )
      {
        v83 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v83, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 467);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v109, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v109;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v126,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v126;
    }
    v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v12 < 0 )
    {
      v13 = (CIMAPIException *)operator new(0x58u);
      v100 = v13;
      if ( v13 )
      {
        v14 = (CIMAPIException *)operator new(0x58u);
        v98 = v14;
        if ( v14 )
          v15 = CIMAPIException::CIMAPIException(v14, v12);
        else
          v15 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v15);
        v16 = CIMAPIException::CIMAPIException(v13, &v99);
      }
      else
      {
        v16 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v16);
      if ( v98 && *(_QWORD *)v98 )
      {
        v84 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v84, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 474);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v110, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v110;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v127,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v127;
    }
    v17 = ((__int64 (__fastcall *)(struct IBootOptions *, __int64 *))a2->lpVtbl->get_BootImage)(a2, &v104);
    if ( v17 < 0 || !v104 )
    {
      v78 = (CIMAPIException *)operator new(0x58u);
      v100 = v78;
      if ( v78 )
      {
        v79 = (CIMAPIException *)operator new(0x58u);
        v98 = v79;
        if ( v79 )
          v80 = CIMAPIException::CIMAPIException(v79, v17);
        else
          v80 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v80);
        v81 = CIMAPIException::CIMAPIException(v78, &v99);
      }
      else
      {
        v81 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v81);
      if ( !v98 || !*(_QWORD *)v98 )
      {
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)pExceptionObject,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)pExceptionObject;
      }
      v97 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
      CIMAPIException::SetCodeRefInfo(v97, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 482);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v123, &v98);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v123;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v104 + 40LL))(v104, 0, 0, 0);
    if ( v18 < 0 )
    {
      v19 = (CIMAPIException *)operator new(0x58u);
      v100 = v19;
      if ( v19 )
      {
        v20 = (CIMAPIException *)operator new(0x58u);
        v98 = v20;
        if ( v20 )
          v21 = CIMAPIException::CIMAPIException(v20, v18);
        else
          v21 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v21);
        v22 = CIMAPIException::CIMAPIException(v19, &v99);
      }
      else
      {
        v22 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v22);
      if ( v98 && *(_QWORD *)v98 )
      {
        v85 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v85, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 490);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v111, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v111;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v128,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v128;
    }
    v23 = 0;
    do
    {
      v102 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, unsigned int *))(*(_QWORD *)v104 + 24LL))(
              v104,
              v141,
              2048,
              &v102);
      if ( v24 < 0 )
      {
        v25 = (CIMAPIException *)operator new(0x58u);
        v100 = v25;
        if ( v25 )
        {
          v26 = (CIMAPIException *)operator new(0x58u);
          v98 = v26;
          if ( v26 )
            v27 = CIMAPIException::CIMAPIException(v26, v24);
          else
            v27 = 0;
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v27);
          v28 = CIMAPIException::CIMAPIException(v25, &v99);
        }
        else
        {
          v28 = 0;
        }
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v28);
        if ( v98 && *(_QWORD *)v98 )
        {
          v86 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
          CIMAPIException::SetCodeRefInfo(v86, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 503);
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v112, &v98);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v112;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v129,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v129;
      }
      v29 = v102;
      if ( v102 )
      {
        v24 = (*(__int64 (__fastcall **)(LPSTREAM, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)ppstm + 32LL))(
                ppstm,
                v141,
                v102,
                0);
        if ( v24 < 0 )
        {
          v30 = (CIMAPIException *)operator new(0x58u);
          v100 = v30;
          if ( v30 )
          {
            v31 = (CIMAPIException *)operator new(0x58u);
            v98 = v31;
            if ( v31 )
              v32 = CIMAPIException::CIMAPIException(v31, v24);
            else
              v32 = 0;
            SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v32);
            v33 = CIMAPIException::CIMAPIException(v30, &v99);
          }
          else
          {
            v33 = 0;
          }
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v33);
          if ( v98 && *(_QWORD *)v98 )
          {
            v87 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
            CIMAPIException::SetCodeRefInfo(v87, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 510);
            SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v113, &v98);
            throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v113;
          }
          CIMAPIException::CIMAPIException(
            (CIMAPIException *)v130,
            (const struct CIMAPIException *)&CIMAPIException::badAlloc);
          throw (CIMAPIException *)v130;
        }
        v29 = v102;
      }
      v23 += v29;
    }
    while ( v29 >= 0x800 );
    if ( !v23 )
    {
      v34 = (CIMAPIException *)operator new(0x58u);
      v100 = v34;
      if ( v34 )
      {
        v35 = (CIMAPIException *)operator new(0x58u);
        v98 = v35;
        if ( v35 )
          v36 = CIMAPIException::CIMAPIException(v35, v24);
        else
          v36 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v36);
        v37 = CIMAPIException::CIMAPIException(v34, &v99);
      }
      else
      {
        v37 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v37);
      if ( v98 && *(_QWORD *)v98 )
      {
        v88 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v88, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 520);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v114, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v114;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v131,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v131;
    }
    v106 = 0;
    v107 = 0;
    v105 = 0;
    v38 = ((__int64 (__fastcall *)(struct IBootOptions *, BSTR *))a2->lpVtbl->get_Manufacturer)(a2, &bstrString);
    if ( v38 < 0 )
    {
      v39 = (CIMAPIException *)operator new(0x58u);
      v100 = v39;
      if ( v39 )
      {
        v40 = (CIMAPIException *)operator new(0x58u);
        v98 = v40;
        if ( v40 )
          v41 = CIMAPIException::CIMAPIException(v40, v38);
        else
          v41 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v41);
        v42 = CIMAPIException::CIMAPIException(v39, &v99);
      }
      else
      {
        v42 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v42);
      if ( v98 && *(_QWORD *)v98 )
      {
        v89 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v89, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 531);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v115, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v115;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v132,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v132;
    }
    v43 = ((__int64 (__fastcall *)(struct IBootOptions *, unsigned int *))a2->lpVtbl->get_PlatformId)(a2, &v106);
    if ( v43 < 0 )
    {
      v44 = (CIMAPIException *)operator new(0x58u);
      v100 = v44;
      if ( v44 )
      {
        v45 = (CIMAPIException *)operator new(0x58u);
        v98 = v45;
        if ( v45 )
          v46 = CIMAPIException::CIMAPIException(v45, v43);
        else
          v46 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v46);
        v47 = CIMAPIException::CIMAPIException(v44, &v99);
      }
      else
      {
        v47 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v47);
      if ( v98 && *(_QWORD *)v98 )
      {
        v90 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v90, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 536);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v116, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v116;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v133,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v133;
    }
    v48 = ((__int64 (__fastcall *)(struct IBootOptions *, unsigned int *))a2->lpVtbl->get_Emulation)(a2, &v107);
    if ( v48 < 0 )
    {
      v49 = (CIMAPIException *)operator new(0x58u);
      v100 = v49;
      if ( v49 )
      {
        v50 = (CIMAPIException *)operator new(0x58u);
        v98 = v50;
        if ( v50 )
          v51 = CIMAPIException::CIMAPIException(v50, v48);
        else
          v51 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v51);
        v52 = CIMAPIException::CIMAPIException(v49, &v99);
      }
      else
      {
        v52 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v52);
      if ( v98 && *(_QWORD *)v98 )
      {
        v91 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v91, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 541);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v117, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v117;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v134,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v134;
    }
    v53 = ((__int64 (__fastcall *)(struct IBootOptions *, int *))a2->lpVtbl->get_ImageSize)(a2, &v105);
    if ( v53 < 0 || v105 != v23 )
    {
      v74 = (CIMAPIException *)operator new(0x58u);
      v100 = v74;
      if ( v74 )
      {
        v75 = (CIMAPIException *)operator new(0x58u);
        v98 = v75;
        if ( v75 )
          v76 = CIMAPIException::CIMAPIException(v75, v53);
        else
          v76 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v76);
        v77 = CIMAPIException::CIMAPIException(v74, &v99);
      }
      else
      {
        v77 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v77);
      if ( v98 && *(_QWORD *)v98 )
      {
        v96 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v96, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 546);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v122, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v122;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v139,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v139;
    }
    v54 = (*(__int64 (__fastcall **)(LPVOID, LPSTREAM))(*(_QWORD *)ppv + 120LL))(ppv, ppstm);
    if ( v54 < 0 )
    {
      v55 = (CIMAPIException *)operator new(0x58u);
      v100 = v55;
      if ( v55 )
      {
        v56 = (CIMAPIException *)operator new(0x58u);
        v98 = v56;
        if ( v56 )
          v57 = CIMAPIException::CIMAPIException(v56, v54);
        else
          v57 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v57);
        v58 = CIMAPIException::CIMAPIException(v55, &v99);
      }
      else
      {
        v58 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v58);
      if ( v98 && *(_QWORD *)v98 )
      {
        v92 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v92, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 556);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v118, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v118;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v135,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v135;
    }
    v59 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 72LL))(ppv, bstrString);
    if ( v59 < 0 )
    {
      v60 = (CIMAPIException *)operator new(0x58u);
      v100 = v60;
      if ( v60 )
      {
        v61 = (CIMAPIException *)operator new(0x58u);
        v98 = v61;
        if ( v61 )
          v62 = CIMAPIException::CIMAPIException(v61, v59);
        else
          v62 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v62);
        v63 = CIMAPIException::CIMAPIException(v60, &v99);
      }
      else
      {
        v63 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v63);
      if ( v98 && *(_QWORD *)v98 )
      {
        v93 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v93, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 561);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v119, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v119;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v136,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v136;
    }
    v64 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 88LL))(ppv, v106);
    if ( v64 < 0 )
    {
      v65 = (CIMAPIException *)operator new(0x58u);
      v100 = v65;
      if ( v65 )
      {
        v66 = (CIMAPIException *)operator new(0x58u);
        v98 = v66;
        if ( v66 )
          v67 = CIMAPIException::CIMAPIException(v66, v64);
        else
          v67 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v67);
        v68 = CIMAPIException::CIMAPIException(v65, &v99);
      }
      else
      {
        v68 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v68);
      if ( v98 && *(_QWORD *)v98 )
      {
        v94 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v94, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 566);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v120, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v120;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v137,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v137;
    }
    v69 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 104LL))(ppv, v107);
    if ( v69 < 0 )
    {
      v70 = (CIMAPIException *)operator new(0x58u);
      v100 = v70;
      if ( v70 )
      {
        v71 = (CIMAPIException *)operator new(0x58u);
        v98 = v71;
        if ( v71 )
          v72 = CIMAPIException::CIMAPIException(v71, v69);
        else
          v72 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v99, v72);
        v73 = CIMAPIException::CIMAPIException(v70, &v99);
      }
      else
      {
        v73 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v98, v73);
      if ( v98 && *(_QWORD *)v98 )
      {
        v95 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v98);
        CIMAPIException::SetCodeRefInfo(v95, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 571);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v121, &v98);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v121;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v138,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v138;
    }
  }
  catch ( ... )
  {
    if ( ppstm )
    {
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      ppstm = 0;
    }
    if ( v104 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
      v104 = 0;
    }
    Utility::SysFreeStringAndNull(&bstrString);
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    throw;
  }
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( v104 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
    v104 = 0;
  }
  SysFreeString(bstrString);
  *a3 = ppv;
}

```

## disassembly

```asm
0x180044df4  mov     [rsp+arg_0], rbx
0x180044df9  push    rsi
0x180044dfa  push    rdi
0x180044dfb  push    r12
0x180044dfd  push    r14
0x180044dff  push    r15
0x180044e01  sub     rsp, 0E90h
0x180044e08  mov     rax, cs:__security_cookie
0x180044e0f  xor     rax, rsp
0x180044e12  mov     [rsp+0EB8h+var_38], rax
0x180044e1a  mov     r15, r8
0x180044e1d  mov     rbx, rdx
0x180044e20  xor     r12d, r12d
0x180044e23  mov     [rsp+0EB8h+var_E70], r12
0x180044e28  mov     [rsp+0EB8h+var_E58], r12
0x180044e2d  mov     [rsp+0EB8h+ppstm], r12
0x180044e32  mov     [rsp+0EB8h+bstrString], r12
0x180044e37  cmp     [rcx+260h], r12d
0x180044e3e  jz      short loc_180044E90
0x180044e40  lea     ecx, [r12+58h]; unsigned __int64
0x180044e45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044e4a  mov     [rsp+0EB8h+var_E80], rax
0x180044e4f  test    rax, rax
0x180044e52  jz      short loc_180044E63
0x180044e54  mov     edx, 0C0AAB149h; int
0x180044e59  mov     rcx, rax; this
0x180044e5c  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180044e61  jmp     short loc_180044E66
0x180044e63  mov     rax, r12
0x180044e66  mov     rdx, rax
0x180044e69  lea     rcx, [rsp+0EB8h+var_E88]
0x180044e6e  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180044e73  nop
0x180044e74  mov     rax, [rsp+0EB8h+var_E88]
0x180044e79  test    rax, rax
0x180044e7c  jz      loc_18004598D
0x180044e82  cmp     [rax], r12
0x180044e85  jz      loc_18004598D
0x180044e8b  jmp     loc_180045948
0x180044e90  lea     rax, [rsp+0EB8h+var_E70]
0x180044e95  mov     [rsp+0EB8h+ppv], rax; ppv
0x180044e9a  lea     r9, _GUID_2c941fd4_975b_59be_a960_9a2a262853a5; riid
0x180044ea1  xor     edx, edx; pUnkOuter
0x180044ea3  lea     r8d, [rdx+17h]; dwClsContext
0x180044ea7  lea     rcx, CLSID_BootOptions; rclsid
0x180044eae  call    cs:__imp_CoCreateInstance
0x180044eb4  mov     esi, eax
0x180044eb6  test    eax, eax
0x180044eb8  jns     loc_180044F46
0x180044ebe  mov     ebx, 58h ; 'X'
0x180044ec3  mov     ecx, ebx; unsigned __int64
0x180044ec5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044eca  mov     rdi, rax
0x180044ecd  mov     [rsp+0EB8h+var_E88], rax
0x180044ed2  test    rax, rax
0x180044ed5  jz      short loc_180044F19
0x180044ed7  mov     ecx, ebx; unsigned __int64
0x180044ed9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044ede  mov     [rsp+0EB8h+var_E78], rax
0x180044ee3  test    rax, rax
0x180044ee6  jz      short loc_180044EF4
0x180044ee8  mov     edx, esi; int
0x180044eea  mov     rcx, rax; this
0x180044eed  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180044ef2  jmp     short loc_180044EF7
0x180044ef4  mov     rax, r12
0x180044ef7  mov     rdx, rax
0x180044efa  lea     rcx, [rsp+0EB8h+var_E80]
0x180044eff  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180044f04  mov     r8d, 0C0AAB148h
0x180044f0a  lea     rdx, [rsp+0EB8h+var_E80]; void *
0x180044f0f  mov     rcx, rdi; this
0x180044f12  call    ??0CIMAPIException@@QEAA@V?$SmartClassPtr@VCIMAPIException@@V1@@@JZZ; CIMAPIException::CIMAPIException(SmartClassPtr<CIMAPIException,CIMAPIException>,long,...)
0x180044f17  jmp     short loc_180044F1C
0x180044f19  mov     rax, r12
0x180044f1c  mov     rdx, rax
0x180044f1f  lea     rcx, [rsp+0EB8h+var_E88]
0x180044f24  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180044f29  nop
0x180044f2a  mov     rax, [rsp+0EB8h+var_E88]
0x180044f2f  test    rax, rax
0x180044f32  jz      loc_1800459FB
0x180044f38  cmp     [rax], r12
0x180044f3b  jz      loc_1800459FB
0x180044f41  jmp     loc_1800459B6
0x180044f46  lea     r8, [rsp+0EB8h+ppstm]; ppstm
0x180044f4b  mov     edx, 1; fDeleteOnRelease
0x180044f50  xor     ecx, ecx; hGlobal
0x180044f52  call    cs:__imp_CreateStreamOnHGlobal
0x180044f58  mov     esi, eax
0x180044f5a  test    eax, eax
0x180044f5c  jns     loc_180044FEA
0x180044f62  mov     ebx, 58h ; 'X'
0x180044f67  mov     ecx, ebx; unsigned __int64
0x180044f69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044f6e  mov     rdi, rax
0x180044f71  mov     [rsp+0EB8h+var_E78], rax
0x180044f76  test    rax, rax
0x180044f79  jz      short loc_180044FBD
0x180044f7b  mov     ecx, ebx; unsigned __int64
0x180044f7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044f82  mov     [rsp+0EB8h+var_E88], rax
0x180044f87  test    rax, rax
0x180044f8a  jz      short loc_180044F98
0x180044f8c  mov     edx, esi; int
0x180044f8e  mov     rcx, rax; this
0x180044f91  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180044f96  jmp     short loc_180044F9B
0x180044f98  mov     rax, r12
0x180044f9b  mov     rdx, rax
0x180044f9e  lea     rcx, [rsp+0EB8h+var_E80]
0x180044fa3  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180044fa8  mov     r8d, 0C0AAB148h
0x180044fae  lea     rdx, [rsp+0EB8h+var_E80]; void *
0x180044fb3  mov     rcx, rdi; this
0x180044fb6  call    ??0CIMAPIException@@QEAA@V?$SmartClassPtr@VCIMAPIException@@V1@@@JZZ; CIMAPIException::CIMAPIException(SmartClassPtr<CIMAPIException,CIMAPIException>,long,...)
0x180044fbb  jmp     short loc_180044FC0
0x180044fbd  mov     rax, r12
0x180044fc0  mov     rdx, rax
0x180044fc3  lea     rcx, [rsp+0EB8h+var_E88]
0x180044fc8  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180044fcd  nop
0x180044fce  mov     rax, [rsp+0EB8h+var_E88]
0x180044fd3  test    rax, rax
0x180044fd6  jz      loc_180045A69
0x180044fdc  cmp     [rax], r12
0x180044fdf  jz      loc_180045A69
0x180044fe5  jmp     loc_180045A24
0x180044fea  mov     rax, [rbx]
0x180044fed  lea     rdx, [rsp+0EB8h+var_E58]
0x180044ff2  mov     rcx, rbx
0x180044ff5  mov     rax, [rax+38h]
0x180044ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ffe  mov     esi, eax
0x180045000  test    eax, eax
0x180045002  js      loc_1800458A0
0x180045008  mov     rcx, [rsp+0EB8h+var_E58]
0x18004500d  test    rcx, rcx
0x180045010  jz      loc_1800458A0
0x180045016  mov     rdx, r12
0x180045019  mov     rax, [rcx]
0x18004501c  xor     r9d, r9d
0x18004501f  xor     r8d, r8d
0x180045022  mov     rax, [rax+28h]
0x180045026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004502b  mov     esi, eax
0x18004502d  test    eax, eax
0x18004502f  jns     loc_1800450BD
0x180045035  mov     ebx, 58h ; 'X'
0x18004503a  mov     ecx, ebx; unsigned __int64
0x18004503c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045041  mov     rdi, rax
0x180045044  mov     [rsp+0EB8h+var_E78], rax
0x180045049  test    rax, rax
0x18004504c  jz      short loc_180045090
0x18004504e  mov     ecx, ebx; unsigned __int64
0x180045050  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045055  mov     [rsp+0EB8h+var_E88], rax
0x18004505a  test    rax, rax
0x18004505d  jz      short loc_18004506B
0x18004505f  mov     edx, esi; int
0x180045061  mov     rcx, rax; this
0x180045064  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180045069  jmp     short loc_18004506E
0x18004506b  mov     rax, r12
0x18004506e  mov     rdx, rax
0x180045071  lea     rcx, [rsp+0EB8h+var_E80]
0x180045076  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18004507b  mov     r8d, 0C0AAB148h
0x180045081  lea     rdx, [rsp+0EB8h+var_E80]; void *
0x180045086  mov     rcx, rdi; this
0x180045089  call    ??0CIMAPIException@@QEAA@V?$SmartClassPtr@VCIMAPIException@@V1@@@JZZ; CIMAPIException::CIMAPIException(SmartClassPtr<CIMAPIException,CIMAPIException>,long,...)
0x18004508e  jmp     short loc_180045093
0x180045090  mov     rax, r12
0x180045093  mov     rdx, rax
0x180045096  lea     rcx, [rsp+0EB8h+var_E88]
0x18004509b  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800450a0  nop
0x1800450a1  mov     rax, [rsp+0EB8h+var_E88]
0x1800450a6  test    rax, rax
0x1800450a9  jz      loc_180045AD7
0x1800450af  cmp     [rax], r12
0x1800450b2  jz      loc_180045AD7
0x1800450b8  jmp     loc_180045A92
0x1800450bd  mov     esi, r12d
0x1800450c0  mov     r14d, 800h
0x1800450c6  mov     [rsp+0EB8h+var_E68], r12d
0x1800450cb  mov     rcx, [rsp+0EB8h+var_E58]
0x1800450d0  mov     rax, [rcx]
0x1800450d3  lea     r9, [rsp+0EB8h+var_E68]
0x1800450d8  mov     r8d, r14d
0x1800450db  lea     rdx, [rsp+0EB8h+var_838]
0x1800450e3  mov     rax, [rax+18h]
0x1800450e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450ec  mov     edi, eax
0x1800450ee  test    eax, eax
0x1800450f0  jns     loc_18004517E
0x1800450f6  mov     ebx, 58h ; 'X'
0x1800450fb  mov     ecx, ebx; unsigned __int64
0x1800450fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045102  mov     rsi, rax
0x180045105  mov     [rsp+0EB8h+var_E78], rax
0x18004510a  test    rax, rax
0x18004510d  jz      short loc_180045151
0x18004510f  mov     ecx, ebx; unsigned __int64
0x180045111  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045116  mov     [rsp+0EB8h+var_E88], rax
0x18004511b  test    rax, rax
0x18004511e  jz      short loc_18004512C
0x180045120  mov     edx, edi; int
0x180045122  mov     rcx, rax; this
0x180045125  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18004512a  jmp     short loc_18004512F
0x18004512c  mov     rax, r12
0x18004512f  mov     rdx, rax
0x180045132  lea     rcx, [rsp+0EB8h+var_E80]
0x180045137  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18004513c  mov     r8d, 0C0AAB148h
0x180045142  lea     rdx, [rsp+0EB8h+var_E80]; void *
0x180045147  mov     rcx, rsi; this
0x18004514a  call    ??0CIMAPIException@@QEAA@V?$SmartClassPtr@VCIMAPIException@@V1@@@JZZ; CIMAPIException::CIMAPIException(SmartClassPtr<CIMAPIException,CIMAPIException>,long,...)
0x18004514f  jmp     short loc_180045154
0x180045151  mov     rax, r12
0x180045154  mov     rdx, rax
0x180045157  lea     rcx, [rsp+0EB8h+var_E88]
0x18004515c  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180045161  nop
0x180045162  mov     rax, [rsp+0EB8h+var_E88]
0x180045167  test    rax, rax
0x18004516a  jz      loc_180045B45
0x180045170  cmp     [rax], r12
0x180045173  jz      loc_180045B45
0x180045179  jmp     loc_180045B00
0x18004517e  mov     edx, [rsp+0EB8h+var_E68]
0x180045182  test    edx, edx
0x180045184  jz      loc_18004523F
0x18004518a  mov     rcx, [rsp+0EB8h+ppstm]
0x18004518f  mov     rax, [rcx]
0x180045192  xor     r9d, r9d
0x180045195  mov     r8d, edx
0x180045198  lea     rdx, [rsp+0EB8h+var_838]
0x1800451a0  mov     rax, [rax+20h]
0x1800451a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451a9  mov     edi, eax
0x1800451ab  test    eax, eax
0x1800451ad  jns     loc_18004523B
0x1800451b3  mov     ebx, 58h ; 'X'
0x1800451b8  mov     ecx, ebx; unsigned __int64
0x1800451ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800451bf  mov     rsi, rax
0x1800451c2  mov     [rsp+0EB8h+var_E78], rax
0x1800451c7  test    rax, rax
0x1800451ca  jz      short loc_18004520E
0x1800451cc  mov     ecx, ebx; unsigned __int64
0x1800451ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800451d3  mov     [rsp+0EB8h+var_E88], rax
0x1800451d8  test    rax, rax
0x1800451db  jz      short loc_1800451E9
0x1800451dd  mov     edx, edi; int
0x1800451df  mov     rcx, rax; this
0x1800451e2  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800451e7  jmp     short loc_1800451EC
0x1800451e9  mov     rax, r12
0x1800451ec  mov     rdx, rax
0x1800451ef  lea     rcx, [rsp+0EB8h+var_E80]
0x1800451f4  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800451f9  mov     r8d, 0C0AAB148h
0x1800451ff  lea     rdx, [rsp+0EB8h+var_E80]; void *
0x180045204  mov     rcx, rsi; this
0x180045207  call    ??0CIMAPIException@@QEAA@V?$SmartClassPtr@VCIMAPIException@@V1@@@JZZ; CIMAPIException::CIMAPIException(SmartClassPtr<CIMAPIException,CIMAPIException>,long,...)
0x18004520c  jmp     short loc_180045211
0x18004520e  mov     rax, r12
0x180045211  mov     rdx, rax
0x180045214  lea     rcx, [rsp+0EB8h+var_E88]
0x180045219  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18004521e  nop
0x18004521f  mov     rax, [rsp+0EB8h+var_E88]
0x180045224  test    rax, rax
0x180045227  jz      loc_180045BB3
0x18004522d  cmp     [rax], r12
0x180045230  jz      loc_180045BB3
0x180045236  jmp     loc_180045B6E
0x18004523b  mov     edx, [rsp+0EB8h+var_E68]
0x18004523f  add     esi, edx
0x180045241  cmp     edx, r14d
0x180045244  jnb     loc_1800450C6
0x18004524a  test    esi, esi
0x18004524c  jnz     loc_1800452D8
0x180045252  lea     ebx, [rsi+58h]
0x180045255  mov     ecx, ebx; unsigned __int64
0x180045257  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004525c  mov     rsi, rax
0x18004525f  mov     [rsp+0EB8h+var_E78], rax
0x180045264  test    rax, rax
0x180045267  jz      short loc_1800452AB
0x180045269  mov     ecx, ebx; unsigned __int64
0x18004526b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045270  mov     [rsp+0EB8h+var_E88], rax
0x180045275  test    rax, rax
0x180045278  jz      short loc_180045286
  ... truncated ...
```
