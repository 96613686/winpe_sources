# NfsSetServerConfiguration(_MI_Context *,_MSFT_NfsServerConfig_Self *,_MSFT_NfsServerConfig const *,_MI_PropertySet const *)

- ea: `0x180012690`
- end: `0x180013236`
- name: `?NfsSetServerConfiguration@@YAXPEAU_MI_Context@@PEAU_MSFT_NfsServerConfig_Self@@PEBU_MSFT_NfsServerConfig@@PEBU_MI_PropertySet@@@Z`
- size: `2982`
- prototype: `void(struct _MI_Context *, struct _MSFT_NfsServerConfig_Self *, const struct _MSFT_NfsServerConfig *, const struct _MI_PropertySet *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180008f50`

## callees

- `0x1800098c4`
- `0x18000be78`
- `0x18000bff0`
- `0x18000e030`
- `0x18000e1b0`
- `0x18000e310`
- `0x18000e350`
- `0x18000f544`
- `0x180010184`
- `0x180011874`
- `0x180012690`
- `0x180013a40`
- `0x180013b84`
- `0x18002143c`
- `0x180021598`
- `0x180021744`
- `0x1800221d0`
- `0x180022318`
- `0x1800226a8`
- `0x180031f28`
- `0x1800331a4`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012db8`
- `msvcrt!_wcsicmp` at `0x180012df4`
- `msvcrt!_wcsicmp` at `0x180012e28`
- `msvcrt!_wcsicmp` at `0x180012db8`
- `msvcrt!_wcsicmp` at `0x180012df4`
- `msvcrt!_wcsicmp` at `0x180012e28`
- `KERNEL32!GetFileAttributesW` at `0x180012d87`
- `KERNEL32!GetFileAttributesW` at `0x180012d87`

## string_xrefs

- `0x180012918`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x180012c4b`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x180012ed3`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x180012f26`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x180013046`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x180013098`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x1800130ec`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x180013135`: `SYSTEM\CurrentControlSet\Services\NfsServer\Parameters`
- `0x18001290a`: `Protocols`
- `0x180012911`: `Protocols`
- `0x18001308a`: `Protocols`
- `0x180013091`: `Protocols`
- `0x1800130e2`: `DirectoryCachePages`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NfsSetServerConfiguration(
        struct _MI_Context *a1,
        struct _MSFT_NfsServerConfig_Self *a2,
        const struct _MSFT_NfsServerConfig *a3,
        struct _MI_PropertySet *a4)
{
  int v8; // r12d
  enum _MI_Result CimProperty; // ebx
  unsigned int v10; // r14d
  char v11; // r15
  bool v12; // r8
  bool v13; // r9
  bool v14; // r10
  char v15; // al
  char v16; // cl
  char v17; // dl
  unsigned int v18; // r8d
  unsigned int v19; // eax
  unsigned int v20; // ecx
  unsigned int v21; // eax
  int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // eax
  int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // eax
  int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // eax
  int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // eax
  int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // eax
  int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // eax
  int v40; // ecx
  unsigned int Value; // eax
  char v42; // dl
  char v43; // al
  int v44; // ecx
  unsigned int v45; // ecx
  const WCHAR *v46; // rcx
  __int64 v47; // rax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // edx
  __int64 v51; // r9
  unsigned int v52; // r8d
  int v53; // ecx
  unsigned int v54; // eax
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // eax
  __int64 v59; // [rsp+20h] [rbp-E0h]
  unsigned int v60; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v61; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v62; // [rsp+48h] [rbp-B8h] BYREF
  int v63; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v64; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v65; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v66; // [rsp+58h] [rbp-A8h] BYREF
  int v67; // [rsp+5Ch] [rbp-A4h] BYREF
  struct _MI_ConstStringA v68; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v69; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v70[2]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v71; // [rsp+88h] [rbp-78h]
  struct _MI_Context *v72; // [rsp+90h] [rbp-70h]
  int v73; // [rsp+98h] [rbp-68h]
  __int64 v74; // [rsp+9Ch] [rbp-64h]
  struct _MI_PropertySet *v75; // [rsp+A8h] [rbp-58h]
  struct _MSFT_NfsServerConfig_Self *v76; // [rsp+B0h] [rbp-50h] BYREF
  int v77; // [rsp+B8h] [rbp-48h]
  _BYTE v78[48]; // [rsp+C0h] [rbp-40h] BYREF
  MI_Instance self; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t *String2; // [rsp+160h] [rbp+60h]
  char v81; // [rsp+168h] [rbp+68h]
  char v82; // [rsp+184h] [rbp+84h]
  char v83; // [rsp+185h] [rbp+85h]
  char v84; // [rsp+187h] [rbp+87h]
  char v85; // [rsp+188h] [rbp+88h]
  char v86; // [rsp+18Ah] [rbp+8Ah]
  char v87; // [rsp+18Bh] [rbp+8Bh]
  wchar_t *v88; // [rsp+258h] [rbp+158h]
  char v89; // [rsp+260h] [rbp+160h]
  wchar_t *v90; // [rsp+268h] [rbp+168h]
  char v91; // [rsp+270h] [rbp+170h]

  v75 = a4;
  v8 = 0;
  v69 = 0;
  v65 = 0;
  v62 = 0;
  v60 = 0;
  v63 = 600;
  v64 = 0;
  v61 = 0;
  v67 = 0;
  v66 = 0;
  CNfsRegHive::CNfsRegHive((CNfsRegHive *)v78, 0);
  v70[0] = &CWMIContext::`vftable';
  v72 = a1;
  v70[1] = 0;
  v71 = 0;
  v74 = 0;
  v73 = 0;
  memset_0(&self, 0, 0x1A0u);
  v76 = a2;
  v77 = 0;
  CLock::AcquireLock((CLock *)&v76);
  if ( a4 )
  {
    CimProperty = ServerPropertyToModify(a4, &v64);
    v10 = v64;
    if ( CimProperty == MI_RESULT_OK && !v64 )
    {
LABEL_195:
      if ( !a1 )
        goto LABEL_198;
      goto LABEL_196;
    }
  }
  else
  {
    v10 = 536868858;
  }
  if ( !a1 || !a1->ft )
  {
    CimProperty = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_195;
  }
  CimProperty = ((unsigned int (__fastcall *)(struct _MI_Context *, void *, MI_Instance *))a1->ft->ConstructInstance)(
                  a1,
                  &MSFT_NfsServerConfig_rtti,
                  &self);
  if ( CimProperty )
    goto LABEL_196;
  CimProperty = NfsGetCimProperty(&self, (struct _NFS_CIMPROPERTY_REGKEY_PAIR *)off_180054C20, 0xEu);
  if ( CimProperty == MI_RESULT_OK )
  {
    v11 = 0;
    v12 = 1;
    v13 = 1;
    v14 = 1;
    if ( v83 )
      v12 = v82 != 0;
    if ( *((_BYTE *)a3 + 149) && (v10 & 0x80u) != 0 )
    {
      v11 = v12;
      if ( *((_BYTE *)a3 + 148) )
      {
        v15 = 1;
        v11 = !v12;
      }
      else
      {
        v15 = 0;
      }
      v12 = v15;
    }
    if ( v85 )
      v13 = v84 != 0;
    if ( *((_BYTE *)a3 + 152) && (v10 & 0x100) != 0 )
    {
      v16 = *((_BYTE *)a3 + 151);
      if ( (v16 != 0) != v13 )
        v11 = 1;
      v13 = v16 != 0;
    }
    if ( v87 )
      v14 = v86 != 0;
    if ( *((_BYTE *)a3 + 155) && (v10 & 0x200) != 0 )
    {
      v17 = *((_BYTE *)a3 + 154);
      if ( (v17 != 0) != v14 )
        v11 = 1;
      v14 = v17 != 0;
    }
    if ( !v12 && !v13 && !v14 )
    {
      v18 = -1073737651;
LABEL_36:
      CimProperty = MI_RESULT_INVALID_PARAMETER;
      CWMIContext::WriteMIError((CWMIContext *)v70, MI_RESULT_INVALID_PARAMETER, v18);
      goto LABEL_193;
    }
    v64 = 0;
    if ( (v10 & 0xFE000) == 0 )
    {
LABEL_102:
      v62 = 4;
      Value = CNfsRegHive::GetValue(
                (CNfsRegHive *)v78,
                L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
                L"LogonTimeOut",
                L"LogonTimeOut",
                0x10u,
                0,
                &v63,
                &v62);
      CimProperty = MapWinErrorToMIResult(Value);
      if ( CimProperty )
        goto LABEL_193;
      if ( (v10 & 0x20) == 0 || (v42 = 1, !*((_BYTE *)a3 + 137)) )
        v42 = 0;
      if ( (v10 & 0x40) == 0 || (v43 = 1, !*((_BYTE *)a3 + 144)) )
        v43 = 0;
      if ( v42 || v43 )
      {
        if ( v43 )
        {
          v44 = *((_DWORD *)a3 + 35);
          v63 = v44;
          if ( (unsigned int)(v44 - 1) > 0x7FFFFFFE )
          {
            CimProperty = MI_RESULT_INVALID_PARAMETER;
            CWMIContext::WriteMIError((CWMIContext *)v70, MI_RESULT_INVALID_PARAMETER, 0xC0001036, 0x7FFFFFFF);
            goto LABEL_193;
          }
        }
        else
        {
          v44 = v63;
        }
        v8 = 1;
        if ( v42 )
        {
          if ( *((_BYTE *)a3 + 136) )
          {
            if ( v44 == -1 )
            {
              v63 = 600;
              CWMIContext::WriteVerbose((CWMIContext *)v70, 0x40001038u, 600, 0xFFFFFFFFLL);
            }
          }
          else
          {
            if ( v44 != -1 )
              CWMIContext::WriteWarning((CWMIContext *)v70, 0x80001037, 0, 0xFFFFFFFFLL);
            v63 = -1;
          }
        }
      }
      if ( *((_BYTE *)a3 + 132) )
      {
        if ( (v10 & 0x10) != 0 )
        {
          v45 = *((_DWORD *)a3 + 32);
          v65 = v45;
          if ( v45 - 4 > 0x7C || (v45 & 3) != 0 )
          {
            v18 = -1073737646;
            goto LABEL_36;
          }
        }
      }
      if ( *((_BYTE *)a3 + 120) && (v10 & 8) != 0 )
      {
        v46 = (const WCHAR *)*((_QWORD *)a3 + 14);
        v47 = -1;
        do
          ++v47;
        while ( v46[v47] );
        if ( v47 && GetFileAttributesW(v46) == -1 )
        {
          CimProperty = MI_RESULT_INVALID_PARAMETER;
          CWMIContext::WriteError((CWMIContext *)v70, 0x57u, 0xC0001053);
        }
        if ( !v81 || _wcsicmp(*((const wchar_t **)a3 + 14), String2) )
          v11 = 1;
        if ( CimProperty )
          goto LABEL_193;
      }
      if ( *((_BYTE *)a3 + 368) && (v10 & 0x400000) != 0 && (!v89 || _wcsicmp(*((const wchar_t **)a3 + 45), v88)) )
        v11 = 1;
      if ( *((_BYTE *)a3 + 384) && (v10 & 0x800000) != 0 && (!v91 || _wcsicmp(*((const wchar_t **)a3 + 47), v90)) )
        v11 = 1;
      if ( *((_BYTE *)a3 + 164) && (v10 & 0x1000) != 0 && (unsigned int)(*((_DWORD *)a3 + 40) - 1) > 0xE0F )
      {
        CWMIContext::WriteMIError((CWMIContext *)v70, MI_RESULT_INVALID_PARAMETER, 0xC0001040, 3600);
        goto LABEL_152;
      }
      if ( *((_BYTE *)a3 + 104) )
      {
        if ( (v10 & 2) != 0 )
        {
          v68 = *(struct _MI_ConstStringA *)((char *)a3 + 88);
          CimProperty = GetAuditValue(&v68, &v69);
          if ( CimProperty )
            goto LABEL_193;
        }
      }
      v62 = 4;
      v48 = CNfsRegHive::GetValue(
              (CNfsRegHive *)v78,
              L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
              L"GracePeriodInSeconds",
              L"GracePeriodInSeconds",
              0x10u,
              0,
              &v66,
              &v62);
      CimProperty = MapWinErrorToMIResult(v48);
      if ( CimProperty )
        goto LABEL_193;
      v62 = 4;
      v49 = CNfsRegHive::GetValue(
              (CNfsRegHive *)v78,
              L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
              L"LeaseTime",
              L"LeaseTime",
              0x10u,
              0,
              &v67,
              &v62);
      CimProperty = MapWinErrorToMIResult(v49);
      if ( CimProperty )
        goto LABEL_193;
      if ( *((_BYTE *)a3 + 340) && (v10 & 0x10000000) != 0 )
      {
        v50 = *((_DWORD *)a3 + 84);
        v66 = v50;
        if ( v50 - 10 > 0x24E )
        {
          v51 = (unsigned int)(CimProperty + 10);
          v52 = -1073737663;
LABEL_162:
          LODWORD(v59) = 600;
          CWMIContext::WriteMIError((CWMIContext *)v70, MI_RESULT_INVALID_PARAMETER, v52, v51, v59);
          goto LABEL_152;
        }
      }
      else
      {
        v50 = v66;
      }
      if ( *((_BYTE *)a3 + 400) && (v10 & 0x2000000) != 0 )
      {
        v53 = *((_DWORD *)a3 + 99);
        v67 = v53;
        if ( (unsigned int)(v53 - 5) > 0x127 )
        {
          LODWORD(v59) = 300;
          CWMIContext::WriteMIError((CWMIContext *)v70, MI_RESULT_INVALID_PARAMETER, 0xC0001042, 5, v59);
          goto LABEL_152;
        }
      }
      else
      {
        v53 = v67;
      }
      if ( v50 < 2 * v53 )
      {
        CWMIContext::WriteMIError((CWMIContext *)v70, MI_RESULT_INVALID_PARAMETER, 0xC0001044);
        goto LABEL_152;
      }
      if ( !*((_BYTE *)a3 + 412) || (v10 & 0x8000000) == 0 || (unsigned int)(*((_DWORD *)a3 + 102) - 1) <= 0x257 )
      {
        if ( !v8
          || (v54 = CNfsRegHive::SetValue(
                      (CNfsRegHive *)v78,
                      L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
                      L"LogonTimeOut",
                      L"LogonTimeOut",
                      4u,
                      &v63,
                      4u),
              (CimProperty = MapWinErrorToMIResult(v54)) == MI_RESULT_OK) )
        {
          if ( v60 == v64
            || (v55 = CNfsRegHive::SetValue(
                        (CNfsRegHive *)v78,
                        L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
                        L"Protocols",
                        L"Protocols",
                        4u,
                        &v60,
                        4u),
                CimProperty = MapWinErrorToMIResult(v55),
                v11 = 1,
                CimProperty == MI_RESULT_OK) )
          {
            if ( !*((_BYTE *)a3 + 132)
              || (v10 & 0x10) == 0
              || (v65 >>= 2,
                  v56 = CNfsRegHive::SetValue(
                          (CNfsRegHive *)v78,
                          L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
                          L"DirectoryCachePages",
                          L"DirectoryCachePages",
                          4u,
                          &v65,
                          4u),
                  (CimProperty = MapWinErrorToMIResult(v56)) == MI_RESULT_OK) )
            {
              if ( !*((_BYTE *)a3 + 104)
                || (v10 & 2) == 0
                || (v57 = CNfsRegHive::SetValue(
                            (CNfsRegHive *)v78,
                            L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
                            L"AuditBits",
                            L"AuditBits",
                            4u,
                            &v69,
                            4u),
                    (CimProperty = MapWinErrorToMIResult(v57)) == MI_RESULT_OK) )
              {
                CimProperty = NfsSetCimProperty(
                                (const struct _MI_Instance *)a3,
                                v75,
                                (struct _NFS_CIMPROPERTY_REGKEY_PAIR *)off_180054C20,
                                0xEu);
                if ( CimProperty == MI_RESULT_OK )
                {
                  CNfsRegHive::Refresh((CNfsRegHive *)v78);
                  if ( *((_BYTE *)a3 + 405) )
                  {
                    if ( *((_BYTE *)a3 + 404) == 1 && (v10 & 0x4000000) != 0 )
                    {
                      v58 = FlushMappingCache();
                      if ( v58 )
                        CWMIContext::WriteError((CWMIContext *)v70, v58, 0xC0001045);
                    }
                  }
                  if ( v11 )
                    CWMIContext::WriteWarning((CWMIContext *)v70, 0x4000104Eu);
                }
              }
            }
          }
        }
        goto LABEL_193;
      }
      v51 = 1;
      v52 = -1073737661;
      goto LABEL_162;
    }
    v62 = 4;
    v19 = CNfsRegHive::GetValue(
            (CNfsRegHive *)v78,
            L"SYSTEM\\CurrentControlSet\\Services\\NfsServer\\Parameters",
            L"Protocols",
            L"Protocols",
            0x10u,
            0,
            &v60,
            &v62);
    CimProperty = MapWinErrorToMIResult(v19);
    if ( CimProperty )
      goto LABEL_193;
    v64 = v60;
    if ( *((_BYTE *)a3 + 328) && (v10 & 0x2000) != 0 )
    {
      v68 = *(struct _MI_ConstStringA *)((char *)a3 + 312);
      if ( !ValidateProtocols(&v68, &v61) )
        goto LABEL_152;
      if ( (v61 & 1) != 0 )
        v20 = v60 | 0x1001;
      else
        v20 = v60 & 0xFFFFEFFE;
      v21 = v20 & 0xFFFFDFFD;
      v22 = v20 | 0x2002;
      if ( (v61 & 2) == 0 )
        v22 = v21;
      v60 = v22;
    }
    if ( *((_BYTE *)a3 + 208) && (v10 & 0x4000) != 0 )
    {
      v68 = (struct _MI_ConstStringA)*((_OWORD *)a3 + 12);
      if ( !ValidateProtocols(&v68, &v61) )
        goto LABEL_152;
      if ( (v61 & 1) != 0 )
        v23 = v60 | 0x4004;
      else
        v23 = v60 & 0xFFFFBFFB;
      v24 = v23 & 0xFFFF7FF7;
      v25 = v23 | 0x8008;
      if ( (v61 & 2) == 0 )
        v25 = v24;
      v60 = v25;
    }
    if ( *((_BYTE *)a3 + 232) && (v10 & 0x8000) != 0 )
    {
      v68 = *(struct _MI_ConstStringA *)((char *)a3 + 216);
      if ( !ValidateProtocols(&v68, &v61) )
        goto LABEL_152;
      if ( (v61 & 1) != 0 )
        v26 = v60 | 0x10010;
      else
        v26 = v60 & 0xFFFEFFEF;
      v27 = v26 & 0xFFFDFFDF;
      v28 = v26 | 0x20020;
      if ( (v61 & 2) == 0 )
        v28 = v27;
      v60 = v28;
    }
    if ( *((_BYTE *)a3 + 280) && (v10 & 0x10000) != 0 )
    {
      v68 = *(struct _MI_ConstStringA *)((char *)a3 + 264);
      if ( !ValidateProtocols(&v68, &v61) )
        goto LABEL_152;
      if ( (v61 & 1) != 0 )
        v29 = v60 | 0x40040;
      else
        v29 = v60 & 0xFFFBFFBF;
      v30 = v29 & 0xFFF7FF7F;
      v31 = v29 | 0x80080;
      if ( (v61 & 2) == 0 )
        v31 = v30;
      v60 = v31;
    }
    if ( *((_BYTE *)a3 + 304) && (v10 & 0x20000) != 0 )
    {
      v68 = (struct _MI_ConstStringA)*((_OWORD *)a3 + 18);
      if ( !ValidateProtocols(&v68, &v61) )
        goto LABEL_152;
      if ( (v61 & 1) != 0 )
        v32 = v60 | 0x100100;
      else
        v32 = v60 & 0xFFEFFEFF;
      v33 = v32 & 0xFFDFFDFF;
      v34 = v32 | 0x200200;
      if ( (v61 & 2) == 0 )
        v34 = v33;
      v60 = v34;
    }
    if ( *((_BYTE *)a3 + 184) && (v10 & 0x40000) != 0 )
    {
      v68 = *(struct _MI_ConstStringA *)((char *)a3 + 168);
      if ( !ValidateProtocols(&v68, &v61) )
        goto LABEL_152;
      if ( (v61 & 1) != 0 )
        v35 = v60 | 0x400400;
      else
        v35 = v60 & 0xFFBFFBFF;
      v36 = v35 & 0xFF7FF7FF;
      v37 = v35 | 0x800800;
      if ( (v61 & 2) == 0 )
        v37 = v36;
      v60 = v37;
    }
    if ( !*((_BYTE *)a3 + 256) || (v10 & 0x80000) == 0 )
      goto LABEL_102;
    v68 = (struct _MI_ConstStringA)*((_OWORD *)a3 + 15);
    if ( ValidateProtocols(&v68, &v61) )
    {
      if ( (v61 & 1) != 0 )
        v38 = v60 | 0x5000000;
      else
        v38 = v60 & 0xFAFFFFFF;
      v39 = v38 & 0xF5FFFFFF;
      v40 = v38 | 0xA000000;
      if ( (v61 & 2) == 0 )
        v40 = v39;
      v60 = v40;
      goto LABEL_102;
    }
LABEL_152:
    CimProperty = MI_RESULT_INVALID_PARAMETER;
  }
LABEL_193:
  MI_Instance_Destruct(&self);
LABEL_196:
  if ( a1->ft )
    ((void (__fastcall *)(struct _MI_Context *, _QWORD))a1->ft->PostResult)(a1, (unsigned int)CimProperty);
LABEL_198:
  CLock::ReleaseLock((CLock *)&v76);
  CWMIContext::~CWMIContext((CWMIContext *)v70);
  CNfsRegHive::~CNfsRegHive((CNfsRegHive *)v78);
}

```

## disassembly

```asm
0x180012690  mov     [rsp-8+arg_8], rbx
0x180012695  push    rbp
0x180012696  push    rsi
0x180012697  push    rdi
0x180012698  push    r12
0x18001269a  push    r13
0x18001269c  push    r14
0x18001269e  push    r15
0x1800126a0  lea     rbp, [rsp-1A0h]
0x1800126a8  sub     rsp, 2A0h
0x1800126af  mov     rax, cs:__security_cookie
0x1800126b6  xor     rax, rsp
0x1800126b9  mov     [rbp+1D0h+var_40], rax
0x1800126c0  mov     rdi, r9
0x1800126c3  mov     [rbp+1D0h+var_228], r9
0x1800126c7  mov     rsi, r8
0x1800126ca  mov     rbx, rdx
0x1800126cd  mov     r13, rcx
0x1800126d0  xor     r12d, r12d
0x1800126d3  mov     [rsp+2D0h+var_260], r12d
0x1800126d8  mov     [rsp+2D0h+var_27C], r12d
0x1800126dd  mov     [rsp+2D0h+var_288], r12d
0x1800126e2  mov     [rsp+2D0h+var_290], r12d
0x1800126e7  mov     [rsp+2D0h+var_284], 258h
0x1800126ef  mov     [rsp+2D0h+var_280], r12d
0x1800126f4  mov     [rsp+2D0h+var_28C], r12d
0x1800126f9  mov     [rsp+2D0h+var_274], r12d
0x1800126fe  mov     [rsp+2D0h+var_278], r12d
0x180012703  xor     edx, edx; int
0x180012705  lea     rcx, [rbp+1D0h+var_210]; this
0x180012709  call    ??0CNfsRegHive@@QEAA@H@Z; CNfsRegHive::CNfsRegHive(int)
0x18001270e  nop
0x18001270f  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180012716  mov     [rsp+2D0h+var_258], rax
0x18001271b  mov     [rbp+1D0h+var_240], r13
0x18001271f  mov     [rbp+1D0h+var_250], r12
0x180012723  mov     [rbp+1D0h+var_248], r12w
0x180012728  mov     [rbp+1D0h+var_234], r12
0x18001272c  mov     [rbp+1D0h+var_238], r12d
0x180012730  xor     edx, edx; Val
0x180012732  mov     r8d, 1A0h; Size
0x180012738  lea     rcx, [rbp+1D0h+self]; void *
0x18001273c  call    memset_0
0x180012741  mov     [rbp+1D0h+var_220], rbx
0x180012745  mov     [rbp+1D0h+var_218], r12d
0x180012749  lea     rcx, [rbp+1D0h+var_220]; this
0x18001274d  call    ?AcquireLock@CLock@@QEAAXXZ; CLock::AcquireLock(void)
0x180012752  test    rdi, rdi
0x180012755  jz      short loc_18001277A
0x180012757  lea     rdx, [rsp+2D0h+var_280]; unsigned int *
0x18001275c  mov     rcx, rdi; struct _MI_PropertySet *
0x18001275f  call    ?ServerPropertyToModify@@YA?AW4_MI_Result@@PEBU_MI_PropertySet@@PEAK@Z; ServerPropertyToModify(_MI_PropertySet const *,ulong *)
0x180012764  mov     ebx, eax
0x180012766  mov     r14d, [rsp+2D0h+var_280]
0x18001276b  test    eax, eax
0x18001276d  jnz     short loc_180012780
0x18001276f  test    r14d, r14d
0x180012772  jz      loc_1800131D2
0x180012778  jmp     short loc_180012780
0x18001277a  mov     r14d, 1FFFF7FAh
0x180012780  test    r13, r13
0x180012783  jz      loc_1800131CD
0x180012789  mov     rax, [r13+0]
0x18001278d  test    rax, rax
0x180012790  jz      loc_1800131CD
0x180012796  lea     r8, [rbp+1D0h+self]
0x18001279a  lea     rdx, MSFT_NfsServerConfig_rtti
0x1800127a1  mov     rcx, r13
0x1800127a4  mov     rax, [rax+18h]
0x1800127a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ad  mov     ebx, eax
0x1800127af  test    eax, eax
0x1800127b1  jnz     loc_1800131D7
0x1800127b7  lea     r8d, [rax+0Eh]; unsigned int
0x1800127bb  lea     rdx, off_180054C20; struct _NFS_CIMPROPERTY_REGKEY_PAIR *
0x1800127c2  lea     rcx, [rbp+1D0h+self]; self
0x1800127c6  call    ?NfsGetCimProperty@@YA?AW4_MI_Result@@PEAU_MI_Instance@@PEAU_NFS_CIMPROPERTY_REGKEY_PAIR@@K@Z; NfsGetCimProperty(_MI_Instance *,_NFS_CIMPROPERTY_REGKEY_PAIR *,ulong)
0x1800127cb  mov     ebx, eax
0x1800127cd  test    eax, eax
0x1800127cf  jnz     loc_1800131C2
0x1800127d5  mov     r15b, r12b
0x1800127d8  lea     r11d, [rax+1]
0x1800127dc  mov     r8b, r11b
0x1800127df  mov     r9b, r11b
0x1800127e2  mov     r10b, r11b
0x1800127e5  cmp     [rbp+1D0h+var_14B], r12b
0x1800127ec  jz      short loc_1800127F9
0x1800127ee  cmp     [rbp+1D0h+var_14C], r12b
0x1800127f5  setnz   r8b
0x1800127f9  cmp     [rsi+95h], r12b
0x180012800  jz      short loc_180012821
0x180012802  test    r14b, r14b
0x180012805  jns     short loc_180012821
0x180012807  mov     r15b, r8b
0x18001280a  cmp     [rsi+94h], r12b
0x180012811  jz      short loc_18001281B
0x180012813  mov     al, r11b
0x180012816  xor     r15b, r11b
0x180012819  jmp     short loc_18001281E
0x18001281b  mov     al, r12b
0x18001281e  mov     r8b, al
0x180012821  cmp     [rbp+1D0h+var_148], r12b
0x180012828  jz      short loc_180012835
0x18001282a  cmp     [rbp+1D0h+var_149], r12b
0x180012831  setnz   r9b
0x180012835  cmp     [rsi+98h], r12b
0x18001283c  jz      short loc_180012861
0x18001283e  bt      r14d, 8
0x180012843  jnb     short loc_180012861
0x180012845  mov     cl, [rsi+97h]
0x18001284b  test    cl, cl
0x18001284d  setnz   al
0x180012850  movzx   r15d, r15b
0x180012854  cmp     al, r9b
0x180012857  cmovnz  r15d, r11d
0x18001285b  test    cl, cl
0x18001285d  setnz   r9b
0x180012861  cmp     [rbp+1D0h+var_145], r12b
0x180012868  jz      short loc_180012875
0x18001286a  cmp     [rbp+1D0h+var_146], r12b
0x180012871  setnz   r10b
0x180012875  cmp     [rsi+9Bh], r12b
0x18001287c  jz      short loc_1800128A1
0x18001287e  bt      r14d, 9
0x180012883  jnb     short loc_1800128A1
0x180012885  mov     dl, [rsi+9Ah]
0x18001288b  test    dl, dl
0x18001288d  setnz   al
0x180012890  movzx   r15d, r15b
0x180012894  cmp     al, r10b
0x180012897  cmovnz  r15d, r11d
0x18001289b  test    dl, dl
0x18001289d  setnz   r10b
0x1800128a1  test    r8b, r8b
0x1800128a4  jnz     short loc_1800128CE
0x1800128a6  test    r9b, r9b
0x1800128a9  jnz     short loc_1800128CE
0x1800128ab  test    r10b, r10b
0x1800128ae  jnz     short loc_1800128CE
0x1800128b0  mov     edi, 4
0x1800128b5  mov     r8d, 0C000104Dh; unsigned int
0x1800128bb  mov     ebx, edi
0x1800128bd  mov     edx, edi; enum _MI_Result
0x1800128bf  lea     rcx, [rsp+2D0h+var_258]; this
0x1800128c4  call    ?WriteMIError@CWMIContext@@UEAAXW4_MI_Result@@KZZ; CWMIContext::WriteMIError(_MI_Result,ulong,...)
0x1800128c9  jmp     loc_1800131C2
0x1800128ce  mov     [rsp+2D0h+var_280], r12d
0x1800128d3  mov     edi, 4
0x1800128d8  test    r14d, 0FE000h
0x1800128df  jz      loc_180012C18
0x1800128e5  mov     [rsp+2D0h+var_288], edi
0x1800128e9  lea     rax, [rsp+2D0h+var_288]
0x1800128ee  mov     [rsp+2D0h+var_298], rax; unsigned int *
0x1800128f3  lea     rax, [rsp+2D0h+var_290]
0x1800128f8  mov     [rsp+2D0h+var_2A0], rax; void *
0x1800128fd  mov     [rsp+2D0h+var_2A8], r12; unsigned int *
0x180012902  mov     dword ptr [rsp+2D0h+var_2B0], 10h; unsigned int
0x18001290a  lea     r9, ValueName; "Protocols"
0x180012911  lea     r8, ValueName; "Protocols"
0x180012918  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x18001291f  lea     rcx, [rbp+1D0h+var_210]; this
0x180012923  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x180012928  mov     ecx, eax; unsigned int
0x18001292a  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18001292f  mov     ebx, eax
0x180012931  test    eax, eax
0x180012933  jnz     loc_1800131C2
0x180012939  mov     eax, [rsp+2D0h+var_290]
0x18001293d  mov     [rsp+2D0h+var_280], eax
0x180012941  cmp     [rsi+148h], r12b
0x180012948  jz      short loc_1800129AC
0x18001294a  bt      r14d, 0Dh
0x18001294f  jnb     short loc_1800129AC
0x180012951  movups  xmm0, xmmword ptr [rsi+138h]
0x180012958  movdqu  xmmword ptr [rsp+2D0h+var_270.data], xmm0
0x18001295e  lea     rdx, [rsp+2D0h+var_28C]; unsigned int *
0x180012963  lea     rcx, [rsp+2D0h+var_270]; struct _MI_ConstStringA
0x180012968  call    ?ValidateProtocols@@YAEU_MI_ConstStringA@@PEAK@Z; ValidateProtocols(_MI_ConstStringA,ulong *)
0x18001296d  test    al, al
0x18001296f  jz      loc_180012E6D
0x180012975  mov     edx, [rsp+2D0h+var_28C]
0x180012979  mov     ecx, [rsp+2D0h+var_290]
0x18001297d  test    dl, 1
0x180012980  jz      short loc_18001298A
0x180012982  or      ecx, 1001h
0x180012988  jmp     short loc_180012990
0x18001298a  and     ecx, 0FFFFEFFEh
0x180012990  mov     bl, 2
0x180012992  mov     eax, ecx
0x180012994  and     eax, 0FFFFDFFDh
0x180012999  or      ecx, 2002h
0x18001299f  test    byte ptr [rsp+2D0h+var_28C], bl
0x1800129a3  cmovz   ecx, eax
0x1800129a6  mov     [rsp+2D0h+var_290], ecx
0x1800129aa  jmp     short loc_1800129AE
0x1800129ac  mov     bl, 2
0x1800129ae  cmp     [rsi+0D0h], r12b
0x1800129b5  jz      short loc_180012A15
0x1800129b7  bt      r14d, 0Eh
0x1800129bc  jnb     short loc_180012A15
0x1800129be  movups  xmm0, xmmword ptr [rsi+0C0h]
0x1800129c5  movdqu  xmmword ptr [rsp+2D0h+var_270.data], xmm0
0x1800129cb  lea     rdx, [rsp+2D0h+var_28C]; unsigned int *
0x1800129d0  lea     rcx, [rsp+2D0h+var_270]; struct _MI_ConstStringA
0x1800129d5  call    ?ValidateProtocols@@YAEU_MI_ConstStringA@@PEAK@Z; ValidateProtocols(_MI_ConstStringA,ulong *)
0x1800129da  test    al, al
0x1800129dc  jz      loc_180012E6D
0x1800129e2  mov     edx, [rsp+2D0h+var_28C]
0x1800129e6  mov     ecx, [rsp+2D0h+var_290]
0x1800129ea  test    dl, 1
0x1800129ed  jz      short loc_1800129F7
0x1800129ef  or      ecx, 4004h
0x1800129f5  jmp     short loc_1800129FD
0x1800129f7  and     ecx, 0FFFFBFFBh
0x1800129fd  mov     eax, ecx
0x1800129ff  and     eax, 0FFFF7FF7h
0x180012a04  or      ecx, 8008h
0x180012a0a  test    byte ptr [rsp+2D0h+var_28C], bl
0x180012a0e  cmovz   ecx, eax
0x180012a11  mov     [rsp+2D0h+var_290], ecx
0x180012a15  cmp     [rsi+0E8h], r12b
0x180012a1c  jz      short loc_180012A7C
0x180012a1e  bt      r14d, 0Fh
0x180012a23  jnb     short loc_180012A7C
0x180012a25  movups  xmm0, xmmword ptr [rsi+0D8h]
0x180012a2c  movdqu  xmmword ptr [rsp+2D0h+var_270.data], xmm0
0x180012a32  lea     rdx, [rsp+2D0h+var_28C]; unsigned int *
0x180012a37  lea     rcx, [rsp+2D0h+var_270]; struct _MI_ConstStringA
0x180012a3c  call    ?ValidateProtocols@@YAEU_MI_ConstStringA@@PEAK@Z; ValidateProtocols(_MI_ConstStringA,ulong *)
0x180012a41  test    al, al
0x180012a43  jz      loc_180012E6D
0x180012a49  mov     edx, [rsp+2D0h+var_28C]
0x180012a4d  mov     ecx, [rsp+2D0h+var_290]
0x180012a51  test    dl, 1
0x180012a54  jz      short loc_180012A5E
0x180012a56  or      ecx, 10010h
0x180012a5c  jmp     short loc_180012A64
0x180012a5e  and     ecx, 0FFFEFFEFh
0x180012a64  mov     eax, ecx
0x180012a66  and     eax, 0FFFDFFDFh
0x180012a6b  or      ecx, 20020h
0x180012a71  test    byte ptr [rsp+2D0h+var_28C], bl
0x180012a75  cmovz   ecx, eax
0x180012a78  mov     [rsp+2D0h+var_290], ecx
0x180012a7c  cmp     [rsi+118h], r12b
0x180012a83  jz      short loc_180012AE3
0x180012a85  bt      r14d, 10h
0x180012a8a  jnb     short loc_180012AE3
0x180012a8c  movups  xmm0, xmmword ptr [rsi+108h]
0x180012a93  movdqu  xmmword ptr [rsp+2D0h+var_270.data], xmm0
0x180012a99  lea     rdx, [rsp+2D0h+var_28C]; unsigned int *
0x180012a9e  lea     rcx, [rsp+2D0h+var_270]; struct _MI_ConstStringA
0x180012aa3  call    ?ValidateProtocols@@YAEU_MI_ConstStringA@@PEAK@Z; ValidateProtocols(_MI_ConstStringA,ulong *)
0x180012aa8  test    al, al
0x180012aaa  jz      loc_180012E6D
0x180012ab0  mov     edx, [rsp+2D0h+var_28C]
0x180012ab4  mov     ecx, [rsp+2D0h+var_290]
0x180012ab8  test    dl, 1
0x180012abb  jz      short loc_180012AC5
0x180012abd  or      ecx, 40040h
0x180012ac3  jmp     short loc_180012ACB
0x180012ac5  and     ecx, 0FFFBFFBFh
0x180012acb  mov     eax, ecx
0x180012acd  and     eax, 0FFF7FF7Fh
0x180012ad2  or      ecx, 80080h
0x180012ad8  test    byte ptr [rsp+2D0h+var_28C], bl
0x180012adc  cmovz   ecx, eax
0x180012adf  mov     [rsp+2D0h+var_290], ecx
0x180012ae3  cmp     [rsi+130h], r12b
0x180012aea  jz      short loc_180012B4A
0x180012aec  bt      r14d, 11h
0x180012af1  jnb     short loc_180012B4A
0x180012af3  movups  xmm0, xmmword ptr [rsi+120h]
0x180012afa  movdqu  xmmword ptr [rsp+2D0h+var_270.data], xmm0
0x180012b00  lea     rdx, [rsp+2D0h+var_28C]; unsigned int *
0x180012b05  lea     rcx, [rsp+2D0h+var_270]; struct _MI_ConstStringA
0x180012b0a  call    ?ValidateProtocols@@YAEU_MI_ConstStringA@@PEAK@Z; ValidateProtocols(_MI_ConstStringA,ulong *)
0x180012b0f  test    al, al
0x180012b11  jz      loc_180012E6D
0x180012b17  mov     edx, [rsp+2D0h+var_28C]
0x180012b1b  mov     ecx, [rsp+2D0h+var_290]
0x180012b1f  test    dl, 1
0x180012b22  jz      short loc_180012B2C
0x180012b24  or      ecx, 100100h
0x180012b2a  jmp     short loc_180012B32
0x180012b2c  and     ecx, 0FFEFFEFFh
0x180012b32  mov     eax, ecx
0x180012b34  and     eax, 0FFDFFDFFh
0x180012b39  or      ecx, 200200h
0x180012b3f  test    byte ptr [rsp+2D0h+var_28C], bl
0x180012b43  cmovz   ecx, eax
0x180012b46  mov     [rsp+2D0h+var_290], ecx
0x180012b4a  cmp     [rsi+0B8h], r12b
0x180012b51  jz      short loc_180012BB1
0x180012b53  bt      r14d, 12h
0x180012b58  jnb     short loc_180012BB1
0x180012b5a  movups  xmm0, xmmword ptr [rsi+0A8h]
0x180012b61  movdqu  xmmword ptr [rsp+2D0h+var_270.data], xmm0
0x180012b67  lea     rdx, [rsp+2D0h+var_28C]; unsigned int *
0x180012b6c  lea     rcx, [rsp+2D0h+var_270]; struct _MI_ConstStringA
  ... truncated ...
```
