# UpdateWNFTrigger(int,int)

- ea: `0x1800517f0`
- end: `0x1800525cc`
- name: `?UpdateWNFTrigger@@YAJHH@Z`
- size: `3548`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000924c`
- `0x18002f880`

## callees

- `0x1800517f0`
- `0x1800525d4`
- `0x18006d428`
- `0x18006e28c`
- `0x1800703ec`
- `0x180075ec0`
- `0x18007d770`
- `0x1800b5b8c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800518ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800518ba`
- `OLEAUT32!__imp_SysAllocString` at `0x180051aaa`
- `OLEAUT32!__imp_SysAllocString` at `0x180051b34`
- `OLEAUT32!__imp_SysAllocString` at `0x180051bc9`
- `OLEAUT32!__imp_SysAllocString` at `0x180051c1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180052072`
- `OLEAUT32!__imp_SysAllocString` at `0x1800520c6`
- `OLEAUT32!__imp_SysAllocString` at `0x180052125`
- `OLEAUT32!__imp_SysAllocString` at `0x180052253`
- `OLEAUT32!__imp_SysAllocString` at `0x1800522ae`
- `OLEAUT32!__imp_SysAllocString` at `0x180051aaa`
- `OLEAUT32!__imp_SysAllocString` at `0x180051b34`
- `OLEAUT32!__imp_SysAllocString` at `0x180051bc9`
- `OLEAUT32!__imp_SysAllocString` at `0x180051c1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180052072`
- `OLEAUT32!__imp_SysAllocString` at `0x1800520c6`
- `OLEAUT32!__imp_SysAllocString` at `0x180052125`
- `OLEAUT32!__imp_SysAllocString` at `0x180052253`
- `OLEAUT32!__imp_SysAllocString` at `0x1800522ae`
- `OLEAUT32!__imp_VariantInit` at `0x18005196f`
- `OLEAUT32!__imp_VariantInit` at `0x180051985`
- `OLEAUT32!__imp_VariantInit` at `0x18005199c`
- `OLEAUT32!__imp_VariantInit` at `0x1800519b2`
- `OLEAUT32!__imp_VariantInit` at `0x1800520ad`
- `OLEAUT32!__imp_VariantInit` at `0x18005223a`
- `OLEAUT32!__imp_VariantInit` at `0x18005196f`
- `OLEAUT32!__imp_VariantInit` at `0x180051985`
- `OLEAUT32!__imp_VariantInit` at `0x18005199c`
- `OLEAUT32!__imp_VariantInit` at `0x1800519b2`
- `OLEAUT32!__imp_VariantInit` at `0x1800520ad`
- `OLEAUT32!__imp_VariantInit` at `0x18005223a`
- `OLEAUT32!__imp_VariantClear` at `0x180051a10`
- `OLEAUT32!__imp_VariantClear` at `0x180051a27`
- `OLEAUT32!__imp_VariantClear` at `0x180051a3d`
- `OLEAUT32!__imp_VariantClear` at `0x180051a53`
- `OLEAUT32!__imp_VariantClear` at `0x1800521c7`
- `OLEAUT32!__imp_VariantClear` at `0x1800521dd`
- `OLEAUT32!__imp_VariantClear` at `0x1800521f3`
- `OLEAUT32!__imp_VariantClear` at `0x18005234f`
- `OLEAUT32!__imp_VariantClear` at `0x180052365`
- `OLEAUT32!__imp_VariantClear` at `0x18005237c`
- `OLEAUT32!__imp_VariantClear` at `0x180051a10`
- `OLEAUT32!__imp_VariantClear` at `0x180051a27`
- `OLEAUT32!__imp_VariantClear` at `0x180051a3d`
- `OLEAUT32!__imp_VariantClear` at `0x180051a53`
- `OLEAUT32!__imp_VariantClear` at `0x1800521c7`
- `OLEAUT32!__imp_VariantClear` at `0x1800521dd`
- `OLEAUT32!__imp_VariantClear` at `0x1800521f3`
- `OLEAUT32!__imp_VariantClear` at `0x18005234f`
- `OLEAUT32!__imp_VariantClear` at `0x180052365`
- `OLEAUT32!__imp_VariantClear` at `0x18005237c`

## string_xrefs

- `0x18005192e`: `StartTaskScheduler status: 0x%x`
- `0x180051951`: `StartTaskScheduler status: 0x%x`
- `0x18005185c`: `UpdateWNFTrigger called : bMachine = %d, bEnableWNFTRigger = %d`
- `0x180051885`: `UpdateWNFTrigger called : bMachine = %d, bEnableWNFTRigger = %d`
- `0x1800518df`: `UpdateWNFTrigger failed to get reference of TaskScheduler 0x%x`
- `0x180051905`: `UpdateWNFTrigger failed to get reference of TaskScheduler 0x%x`
- `0x180051ca0`: `UpdateWNFTrigger failed: 0x%x`
- `0x180051cc5`: `UpdateWNFTrigger failed: 0x%x`
- `0x180051cf4`: `UpdateWNFTrigger task didn't exist. No task to update.`
- `0x180051d17`: `UpdateWNFTrigger task didn't exist. No task to update.`
- `0x180051d6e`: `UpdateWNFTrigger failed to get task definition: 0x%x`
- `0x180051d9e`: `UpdateWNFTrigger failed to get task definition: 0x%x`
- `0x180051dec`: `UpdateWNFTrigger failed to get trigger collection: 0x%x`
- `0x180051e1c`: `UpdateWNFTrigger failed to get trigger collection: 0x%x`
- `0x180051e72`: `UpdateWNFTrigger has no trigger to update`
- `0x180051e9f`: `UpdateWNFTrigger has no trigger to update`
- `0x180051eca`: `UpdateWNFTrigger has %d triggers to process.`
- `0x180051ef3`: `UpdateWNFTrigger has %d triggers to process.`
- `0x18005202a`: `UpdateWNFTrigger failed updating trigger %d: 0x%x`
- `0x180052055`: `UpdateWNFTrigger failed updating trigger %d: 0x%x`
- `0x1800523a5`: `UpdateWNFTrigger did not change the trigger`
- `0x1800523c7`: `UpdateWNFTrigger did not change the trigger`
- `0x180052474`: `UpdateWNFTrigger (GetFolder (gp)) failed: 0x%x`
- `0x18005248f`: `UpdateWNFTrigger (GetFolder (gp)) failed: 0x%x`
- `0x1800524b2`: `UpdateWNFTrigger (GetFolder (root)) failed: 0x%x`
- `0x1800524da`: `UpdateWNFTrigger (GetFolder (root)) failed: 0x%x`
- `0x180052527`: `UpdateWNFTrigger failed to connect to TaskService: 0x%x`
- `0x18005254f`: `UpdateWNFTrigger failed to connect to TaskService: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=44
__int64 __fastcall UpdateWNFTrigger(unsigned int a1, unsigned int a2)
{
  HRESULT v4; // ebx
  void (*v5)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v6; // rdx
  __int64 started; // r8
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v10; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v12; // xmm8
  IRecordInfo *v13; // xmm9_8
  __int128 v14; // xmm6
  IRecordInfo *v15; // xmm7_8
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  HRESULT v19; // eax
  LPVOID v20; // rbx
  __int64 v21; // rsi
  _bstr_t::Data_t *v22; // rax
  _bstr_t::Data_t *v23; // rdi
  BSTR v24; // rax
  __int64 *v25; // rbx
  __int64 v26; // rsi
  _bstr_t::Data_t *v27; // rax
  _bstr_t::Data_t *v28; // rdi
  BSTR v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rsi
  _bstr_t::Data_t *v32; // rax
  _bstr_t::Data_t *v33; // rdi
  BSTR v34; // rax
  BSTR v35; // rax
  __int64 v36; // rcx
  int v37; // eax
  __int64 (__fastcall ***v38)(_QWORD, GUID *, _QWORD *); // rcx
  unsigned int i; // r14d
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, _QWORD, _QWORD); // rbx
  unsigned int v42; // eax
  __int64 v43; // rdx
  int v44; // eax
  __int64 v45; // rsi
  __int64 v46; // r14
  IRecordInfo *v47; // rax
  __int128 v48; // xmm8
  IRecordInfo *v49; // xmm9_8
  __int128 v50; // xmm10
  IRecordInfo *v51; // xmm11_8
  IRecordInfo *v52; // rax
  __int128 v53; // xmm6
  IRecordInfo *v54; // xmm7_8
  __int64 v55; // rbx
  _bstr_t::Data_t *v56; // rax
  _bstr_t::Data_t *v57; // rdi
  BSTR v58; // rax
  HRESULT v59; // eax
  HRESULT v60; // eax
  HRESULT v61; // eax
  __int128 v62; // xmm8
  IRecordInfo *v63; // xmm9_8
  __int128 v64; // xmm10
  IRecordInfo *v65; // xmm11_8
  BSTR v66; // rax
  __int128 v67; // xmm6
  IRecordInfo *v68; // xmm7_8
  __int64 v69; // rbx
  _bstr_t::Data_t *v70; // rax
  _bstr_t::Data_t *v71; // rdi
  BSTR v72; // rax
  HRESULT v73; // eax
  HRESULT v74; // eax
  HRESULT v75; // eax
  void (*v76)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v77; // rdx
  VARIANTARG pvarSrc; // [rsp+58h] [rbp-B0h] BYREF
  IRecordInfo *v80; // [rsp+70h] [rbp-98h]
  __int64 v81; // [rsp+78h] [rbp-90h] BYREF
  __int64 v82; // [rsp+80h] [rbp-88h] BYREF
  __int64 v83; // [rsp+88h] [rbp-80h] BYREF
  __int64 v84; // [rsp+90h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v86; // [rsp+A0h] [rbp-68h] BYREF
  __int64 *v87; // [rsp+B8h] [rbp-50h] BYREF
  _bstr_t::Data_t *v88; // [rsp+C0h] [rbp-48h]
  VARIANTARG pvarg; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v90; // [rsp+E8h] [rbp-20h] BYREF
  IRecordInfo *v91; // [rsp+F8h] [rbp-10h]
  __int128 v92; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v93; // [rsp+118h] [rbp+10h]
  VARIANTARG v94; // [rsp+128h] [rbp+20h] BYREF
  VARIANTARG v95; // [rsp+148h] [rbp+40h] BYREF
  __int128 v96; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v97; // [rsp+178h] [rbp+70h]
  _bstr_t::Data_t *v98; // [rsp+238h] [rbp+130h] BYREF
  __int64 (__fastcall ***v99)(_QWORD, GUID *, __int64 *); // [rsp+240h] [rbp+138h] BYREF

  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"UpdateWNFTrigger called : bMachine = %d, bEnableWNFTRigger = %d", a1, a2);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"UpdateWNFTrigger called : bMachine = %d, bEnableWNFTRigger = %d", a1, a2);
    }
  }
  ppv = 0;
  *(_QWORD *)&pvarSrc.vt = 0;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v4 < 0 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_195;
    v5 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v6 = L"UpdateWNFTrigger failed to get reference of TaskScheduler 0x%x";
LABEL_191:
      v5(2u, v6, (unsigned int)v4);
      goto LABEL_195;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      RedirectDebugMsg(2u, L"UpdateWNFTrigger failed to get reference of TaskScheduler 0x%x", (unsigned int)v4);
    goto LABEL_195;
  }
  started = (unsigned int)StartTaskScheduler();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"StartTaskScheduler status: 0x%x", started);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"StartTaskScheduler status: 0x%x", started);
    }
  }
  v8 = ppv;
  v9 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
  VariantInit(&pvarg);
  v10 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v95);
  v12 = *(_OWORD *)&v95.vt;
  v13 = v95.pRecInfo;
  VariantInit((VARIANTARG *)&pvarSrc.decVal.8);
  v14 = *(_OWORD *)&pvarSrc.decVal.Lo32;
  v15 = v80;
  VariantInit(&v86);
  v96 = v10;
  v97 = pRecInfo;
  v90 = v12;
  v91 = v13;
  v92 = v14;
  v93 = v15;
  v94 = v86;
  v4 = v9(v8, &v94, &v92, &v90, &v96);
  v16 = VariantClear(&v86);
  if ( v16 < 0 )
    _com_issue_error(v16);
  v17 = VariantClear((VARIANTARG *)&pvarSrc.decVal.8);
  if ( v17 < 0 )
    _com_issue_error(v17);
  v18 = VariantClear(&v95);
  if ( v18 < 0 )
    _com_issue_error(v18);
  v19 = VariantClear(&pvarg);
  if ( v19 < 0 )
    _com_issue_error(v19);
  if ( v4 >= 0 )
  {
    v87 = 0;
    v20 = ppv;
    v21 = *(_QWORD *)ppv;
    v22 = (_bstr_t::Data_t *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v23 = v22;
    v98 = v22;
    if ( v22 )
    {
      *((_QWORD *)v22 + 1) = 0;
      *((_DWORD *)v22 + 4) = 1;
      v24 = SysAllocString(L"\\");
      *(_QWORD *)v23 = v24;
      if ( !v24 )
        _com_issue_error(-2147024882);
    }
    else
    {
      v23 = 0;
    }
    v98 = v23;
    if ( v23 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 **))(v21 + 56))(v20, *(_QWORD *)v23, &v87);
      _bstr_t::Data_t::Release(v23);
      if ( v4 < 0 )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_184;
        v76 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"UpdateWNFTrigger (GetFolder (root)) failed: 0x%x", (unsigned int)v4);
          goto LABEL_184;
        }
        v77 = L"UpdateWNFTrigger (GetFolder (root)) failed: 0x%x";
LABEL_180:
        v76(2u, v77, (unsigned int)v4);
LABEL_184:
        if ( v87 )
          (*(void (__fastcall **)(__int64 *))(*v87 + 16))(v87);
        goto LABEL_195;
      }
      v25 = v87;
      v26 = *v87;
      v27 = (_bstr_t::Data_t *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v28 = v27;
      v98 = v27;
      if ( v27 )
      {
        *((_QWORD *)v27 + 1) = 0;
        *((_DWORD *)v27 + 4) = 1;
        v29 = SysAllocString(L"Microsoft\\Windows\\GroupPolicy");
        *(_QWORD *)v28 = v29;
        if ( !v29 )
          _com_issue_error(-2147024882);
      }
      else
      {
        v28 = 0;
      }
      v98 = v28;
      if ( v28 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, VARIANTARG *))(v26 + 72))(v25, *(_QWORD *)v28, &pvarSrc);
        _bstr_t::Data_t::Release(v28);
        if ( v4 >= 0 )
        {
          v84 = 0;
          v30 = *(_QWORD *)&pvarSrc.vt;
          v31 = **(_QWORD **)&pvarSrc.vt;
          v32 = (_bstr_t::Data_t *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
          v33 = v32;
          v98 = v32;
          if ( a1 )
          {
            if ( v32 )
            {
              *((_QWORD *)v32 + 1) = 0;
              *((_DWORD *)v32 + 4) = 1;
              v34 = SysAllocString(L"{3E0A038B-D834-4930-9981-E89C9BFF83AA}");
              *(_QWORD *)v33 = v34;
              if ( !v34 )
                _com_issue_error(-2147024882);
            }
            else
            {
              v33 = 0;
            }
            v98 = v33;
            if ( v33 )
              goto LABEL_54;
          }
          else
          {
            if ( v32 )
            {
              *((_QWORD *)v32 + 1) = 0;
              *((_DWORD *)v32 + 4) = 1;
              v35 = SysAllocString(L"{A7719E0F-10DB-4640-AD8C-490CC6AD5202}");
              *(_QWORD *)v33 = v35;
              if ( !v35 )
                _com_issue_error(-2147024882);
            }
            else
            {
              v33 = 0;
            }
            v98 = v33;
            if ( v33 )
            {
LABEL_54:
              v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(v31 + 104))(v30, *(_QWORD *)v33, &v84);
              _bstr_t::Data_t::Release(v33);
              if ( v4 < 0 )
              {
                if ( v4 == -2147024894 )
                {
                  if ( a2 )
                  {
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(4u, L"UpdateWNFTrigger task didn't exist. No task to update.");
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(4u, L"UpdateWNFTrigger task didn't exist. No task to update.");
                      }
                    }
                  }
                  else
                  {
                    v4 = 0;
                  }
                }
                else if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(2u, L"UpdateWNFTrigger failed: 0x%x", (unsigned int)v4);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(2u, L"UpdateWNFTrigger failed: 0x%x", (unsigned int)v4);
                  }
                }
              }
              v36 = v84;
              if ( !v84 )
                goto LABEL_166;
              v82 = 0;
              v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v84 + 152LL))(v84, &v82);
              if ( v4 < 0 )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(2u, L"UpdateWNFTrigger failed to get task definition: 0x%x", (unsigned int)v4);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(2u, L"UpdateWNFTrigger failed to get task definition: 0x%x", (unsigned int)v4);
                  }
                }
LABEL_163:
                if ( v82 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
                v36 = v84;
LABEL_166:
                if ( v36 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                goto LABEL_184;
              }
              v83 = 0;
              v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v82 + 72LL))(v82, &v83);
              if ( v4 < 0 )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(2u, L"UpdateWNFTrigger failed to get trigger collection: 0x%x", (unsigned int)v4);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(2u, L"UpdateWNFTrigger failed to get trigger collection: 0x%x", (unsigned int)v4);
                  }
                }
LABEL_161:
                if ( v83 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
                goto LABEL_163;
              }
              LODWORD(v98) = 0;
              v4 = (*(__int64 (__fastcall **)(__int64, _bstr_t::Data_t **))(*(_QWORD *)v83 + 56LL))(v83, &v98);
              v37 = (int)v98;
              if ( !(_DWORD)v98 )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(2u, L"UpdateWNFTrigger has no trigger to update");
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(2u, L"UpdateWNFTrigger has no trigger to update");
                  }
                }
                goto LABEL_161;
              }
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"UpdateWNFTrigger has %d triggers to process.", (unsigned int)v98);
                }
                else
                {
                  if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
                    goto LABEL_99;
                  RedirectDebugMsg(4u, L"UpdateWNFTrigger has %d triggers to process.", (unsigned int)v98);
                }
                v37 = (int)v98;
              }
LABEL_99:
              v38 = 0;
              v99 = 0;
              v81 = 0;
              for ( i = 0; (int)i < v37; ++i )
              {
                if ( v38 )
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v38)[2])(v38);
                v99 = 0;
                v40 = v83;
                v41 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v83 + 64LL);
                pvarSrc.iVal = 3;
                *((_DWORD *)&pvarSrc.decVal + 4) = i + 1;
                v42 = _variant_t::operator long((VARIANTARG *)&pvarSrc.decVal.8);
                v4 = v41(v40, v42, &v99);
                _variant_t::~_variant_t((VARIANTARG *)&pvarSrc.decVal.8);
                if ( v4 >= 0 )
                {
                  if ( v81 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
                  v81 = 0;
                  v4 = (**v99)(v99, &IID_IWnfStateChangeTrigger, &v81);
                  if ( v4 >= 0 )
                  {
                    LOWORD(v43) = -(a2 != 0);
                    v44 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 152LL))(v81, v43);
                    if ( v44 < 0 && *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(2u, L"UpdateWNFTrigger failed updating trigger %d: 0x%x", i, (unsigned int)v44);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(2u, L"UpdateWNFTrigger failed updating trigger %d: 0x%x", i, (unsigned int)v44);
                      }
                    }
                    v45 = *(_QWORD *)&pvarSrc.vt;
                    v46 = **(_QWORD **)&pvarSrc.vt;
                    v47 = (IRecordInfo *)SysAllocString(L"O:BAG:DAD:P(A;;GA;;;SY)");
                    if ( a1 )
                    {
                      if ( !v47 )
                        _com_issue_error(-2147024882);
                      v86.vt = 8;
                      v86.llVal = (LONGLONG)v47;
                      v48 = *(_OWORD *)&v86.vt;
                      v49 = v86.pRecInfo;
                      VariantInit(&pvarg);
                      v50 = *(_OWORD *)&pvarg.vt;
                      v51 = pvarg.pRecInfo;
                      v52 = (IRecordInfo *)SysAllocString(L"S-1-5-20");
                      if ( !v52 )
                        _com_issue_error(-2147024882);
                      pvarSrc.iVal = 8;
                      pvarSrc.pRecInfo = v52;
                      v53 = *(_OWORD *)&pvarSrc.decVal.Lo32;
                      v54 = v80;
                      v55 = v82;
                      v56 = (_bstr_t::Data_t *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
                      v57 = v56;
                      v88 = v56;
                      if ( v56 )
                      {
                        *((_QWORD *)v56 + 1) = 0;
                        *((_DWORD *)v56 + 4) = 1;
                        v58 = SysAllocString(L"{3E0A038B-D834-4930-9981-E89C9BFF83AA}");
                        *(_QWORD *)v57 = v58;
                        if ( !v58 )
                          _com_issue_error(-2147024882);
                      }
                      else
                      {
                        v57 = 0;
                      }
                      v88 = v57;
                      if ( !v57 )
                        _com_issue_error(-2147024882);
                      *(_OWORD *)&v94.vt = v48;
                      v94.pRecInfo = v49;
                      v92 = v50;
                      v93 = v51;
                      v90 = v53;
                      v91 = v54;
                      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int128 *, __int128 *, int, VARIANTARG *, _QWORD))(v46 + 136))(
                             v45,
                             *(_QWORD *)v57,
                             v55,
                             4,
                             &v90,
                             &v92,
                             5,
                             &v94,
                             0);
                      _bstr_t::Data_t::Release(v57);
                      v59 = VariantClear((VARIANTARG *)&pvarSrc.decVal.8);
                      if ( v59 < 0 )
                        _com_issue_error(v59);
                      v60 = VariantClear(&pvarg);
                      if ( v60 < 0 )
                        _com_issue_error(v60);
                      v61 = VariantClear(&v86);
                      if ( v61 < 0 )
                        _com_issue_error(v61);
                    }
                    else
                    {
                      if ( !v47 )
                        _com_issue_error(-2147024882);
                      pvarSrc.iVal = 8;
                      pvarSrc.pRecInfo = v47;
                      v62 = *(_OWORD *)&pvarSrc.decVal.Lo32;
                      v63 = v80;
                      VariantInit(&pvarg);
                      v64 = *(_OWORD *)&pvarg.vt;
                      v65 = pvarg.pRecInfo;
                      v66 = SysAllocString(L"S-1-5-20");
                      if ( !v66 )
                        _com_issue_error(-2147024882);
                      v86.vt = 8;
                      v86.llVal = (LONGLONG)v66;
                      v67 = *(_OWORD *)&v86.vt;
                      v68 = v86.pRecInfo;
                      v69 = v82;
                      v70 = (_bstr_t::Data_t *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
                      v71 = v70;
                      v88 = v70;
                      if ( v70 )
                      {
                        *((_QWORD *)v70 + 1) = 0;
                        *((_DWORD *)v70 + 4) = 1;
                        v72 = SysAllocString(L"{A7719E0F-10DB-4640-AD8C-490CC6AD5202}");
                        *(_QWORD *)v71 = v72;
                        if ( !v72 )
                          _com_issue_error(-2147024882);
                      }
                      else
                      {
                        v71 = 0;
                      }
                      v88 = v71;
                      if ( !v71 )
                        _com_issue_error(-2147024882);
                      *(_OWORD *)&v94.vt = v62;
                      v94.pRecInfo = v63;
                      v92 = v64;
                      v93 = v65;
                      v90 = v67;
                      v91 = v68;
                      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int128 *, __int128 *, int, VARIANTARG *, _QWORD))(v46 + 136))(
                             v45,
                             *(_QWORD *)v71,
                             v69,
                             4,
                             &v90,
                             &v92,
                             5,
                             &v94,
                             0);
                      _bstr_t::Data_t::Release(v71);
                      v73 = VariantClear(&v86);
                      if ( v73 < 0 )
                        _com_issue_error(v73);
                      v74 = VariantClear(&pvarg);
                      if ( v74 < 0 )
                        _com_issue_error(v74);
                      v75 = VariantClear((VARIANTARG *)&pvarSrc.decVal.8);
                      if ( v75 < 0 )
                        _com_issue_error(v75);
                    }
                    goto LABEL_156;
                  }
                }
                v37 = (int)v98;
                v38 = v99;
              }
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_157;
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"UpdateWNFTrigger did not change the trigger");
              }
              else
              {
                if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
                {
LABEL_157:
                  if ( v81 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
                    v38 = v99;
                  }
                  if ( v38 )
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v38)[2])(v38);
                  goto LABEL_161;
                }
                RedirectDebugMsg(2u, L"UpdateWNFTrigger did not change the trigger");
              }
LABEL_156:
              v38 = v99;
              goto LABEL_157;
            }
          }
          _com_issue_error(-2147024882);
        }
        if ( !a2 )
        {
          v4 = 0;
          goto LABEL_184;
        }
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_184;
        v76 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"UpdateWNFTrigger (GetFolder (gp)) failed: 0x%x", (unsigned int)v4);
          goto LABEL_184;
        }
        v77 = L"UpdateWNFTrigger (GetFolder (gp)) failed: 0x%x";
        goto LABEL_180;
      }
    }
    _com_issue_error(-2147024882);
  }
  if ( !*(_DWORD *)&g_dwDebugLevel )
    goto LABEL_195;
  v5 = g_lpDebugMsg;
  if ( g_lpDebugMsg )
  {
    v6 = L"UpdateWNFTrigger failed to connect to TaskService: 0x%x";
    goto LABEL_191;
  }
  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    RedirectDebugMsg(2u, L"UpdateWNFTrigger failed to connect to TaskService: 0x%x", (unsigned int)v4);
LABEL_195:
  if ( *(_QWORD *)&pvarSrc.vt )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pvarSrc.vt + 16LL))(*(_QWORD *)&pvarSrc.vt);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800517f0  mov     rax, rsp
0x1800517f3  mov     [rax+8], rbx
0x1800517f7  push    rbp
0x1800517f8  push    rsi
0x1800517f9  push    rdi
0x1800517fa  push    r12
0x1800517fc  push    r13
0x1800517fe  push    r14
0x180051800  push    r15
0x180051802  lea     rbp, [rax-118h]
0x180051809  sub     rsp, 1E0h
0x180051810  movaps  xmmword ptr [rax-48h], xmm6
0x180051814  movaps  xmmword ptr [rax-58h], xmm7
0x180051818  movaps  xmmword ptr [rax-68h], xmm8
0x18005181d  movaps  xmmword ptr [rax-78h], xmm9
0x180051822  movaps  xmmword ptr [rax-88h], xmm10
0x18005182a  movaps  xmmword ptr [rax-98h], xmm11
0x180051832  mov     r15d, edx
0x180051835  mov     r13d, ecx
0x180051838  mov     r14d, 4
0x18005183e  xor     r12d, r12d
0x180051841  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180051848  jz      short loc_180051894
0x18005184a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180051851  test    rax, rax
0x180051854  jz      short loc_18005186D
0x180051856  mov     r9d, edx
0x180051859  mov     r8d, ecx
0x18005185c  lea     rdx, aUpdatewnftrigg_7; "UpdateWNFTrigger called : bMachine = %d"...
0x180051863  mov     ecx, r14d
0x180051866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005186b  jmp     short loc_180051894
0x18005186d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180051874  jz      short loc_180051894
0x180051876  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005187d  jz      short loc_180051894
0x18005187f  mov     r9d, r15d
0x180051882  mov     r8d, r13d
0x180051885  lea     rdx, aUpdatewnftrigg_7; "UpdateWNFTrigger called : bMachine = %d"...
0x18005188c  mov     ecx, r14d; unsigned int
0x18005188f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180051894  mov     [rbp+110h+var_180], r12
0x180051898  mov     qword ptr [rsp+210h+pvarSrc], r12
0x18005189d  lea     rax, [rbp+110h+var_180]
0x1800518a1  mov     [rsp+210h+ppv], rax; ppv
0x1800518a6  lea     r9, IID_ITaskService; riid
0x1800518ad  xor     edx, edx; pUnkOuter
0x1800518af  lea     r8d, [rdx+1]; dwClsContext
0x1800518b3  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800518ba  call    cs:__imp_CoCreateInstance
0x1800518c0  mov     ebx, eax
0x1800518c2  test    eax, eax
0x1800518c4  jns     short loc_180051911
0x1800518c6  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800518cd  jz      loc_180052564
0x1800518d3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800518da  test    rax, rax
0x1800518dd  jz      short loc_1800518EB
0x1800518df  lea     rdx, aUpdatewnftrigg_5; "UpdateWNFTrigger failed to get referenc"...
0x1800518e6  jmp     loc_18005252E
0x1800518eb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800518f2  jz      loc_180052564
0x1800518f8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800518ff  jz      loc_180052564
0x180051905  lea     rdx, aUpdatewnftrigg_5; "UpdateWNFTrigger failed to get referenc"...
0x18005190c  jmp     loc_180052556
0x180051911  call    ?StartTaskScheduler@@YAJXZ; StartTaskScheduler(void)
0x180051916  mov     r8d, eax
0x180051919  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180051920  jz      short loc_180051960
0x180051922  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180051929  test    rax, rax
0x18005192c  jz      short loc_18005193F
0x18005192e  lea     rdx, aStarttasksched; "StartTaskScheduler status: 0x%x"
0x180051935  mov     ecx, r14d
0x180051938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005193d  jmp     short loc_180051960
0x18005193f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180051946  jz      short loc_180051960
0x180051948  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005194f  jz      short loc_180051960
0x180051951  lea     rdx, aStarttasksched; "StartTaskScheduler status: 0x%x"
0x180051958  mov     ecx, r14d; unsigned int
0x18005195b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180051960  mov     rdi, [rbp+110h+var_180]
0x180051964  mov     rax, [rdi]
0x180051967  mov     rbx, [rax+50h]
0x18005196b  lea     rcx, [rbp+110h+pvarg]; pvarg
0x18005196f  call    cs:__imp_VariantInit
0x180051975  nop
0x180051976  movups  xmm10, xmmword ptr [rbp+110h+pvarg]
0x18005197b  movsd   xmm11, qword ptr [rbp+110h+pvarg+10h]
0x180051981  lea     rcx, [rbp+110h+var_D0]; pvarg
0x180051985  call    cs:__imp_VariantInit
0x18005198b  nop
0x18005198c  movups  xmm8, xmmword ptr [rbp+110h+var_D0]
0x180051991  movsd   xmm9, qword ptr [rbp+110h+var_D0+10h]
0x180051997  lea     rcx, [rsp+210h+pvarSrc+8]; pvarg
0x18005199c  call    cs:__imp_VariantInit
0x1800519a2  nop
0x1800519a3  movups  xmm6, xmmword ptr [rsp+210h+pvarSrc+8]
0x1800519a8  movsd   xmm7, [rsp+210h+var_1A8]
0x1800519ae  lea     rcx, [rbp+110h+var_178]; pvarg
0x1800519b2  call    cs:__imp_VariantInit
0x1800519b8  nop
0x1800519b9  movups  xmm0, xmmword ptr [rbp+110h+var_178]
0x1800519bd  movsd   xmm1, qword ptr [rbp+110h+var_178+10h]
0x1800519c2  movaps  [rbp+110h+var_B0], xmm10
0x1800519c7  movsd   [rbp+110h+var_A0], xmm11
0x1800519cd  movaps  [rbp+110h+var_130], xmm8
0x1800519d2  movsd   [rbp+110h+var_120], xmm9
0x1800519d8  movaps  [rbp+110h+var_110], xmm6
0x1800519dc  movsd   [rbp+110h+var_100], xmm7
0x1800519e1  movaps  [rbp+110h+var_F0], xmm0
0x1800519e5  movsd   [rbp+110h+var_E0], xmm1
0x1800519ea  lea     rax, [rbp+110h+var_B0]
0x1800519ee  mov     [rsp+210h+ppv], rax
0x1800519f3  lea     r9, [rbp+110h+var_130]
0x1800519f7  lea     r8, [rbp+110h+var_110]
0x1800519fb  lea     rdx, [rbp+110h+var_F0]
0x1800519ff  mov     rcx, rdi
0x180051a02  mov     rax, rbx
0x180051a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a0a  mov     ebx, eax
0x180051a0c  lea     rcx, [rbp+110h+var_178]; pvarg
0x180051a10  call    cs:__imp_VariantClear
0x180051a16  test    eax, eax
0x180051a18  jns     short loc_180051A22
0x180051a1a  mov     ecx, eax; int
0x180051a1c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180051a22  lea     rcx, [rsp+210h+pvarSrc+8]; pvarg
0x180051a27  call    cs:__imp_VariantClear
0x180051a2d  test    eax, eax
0x180051a2f  jns     short loc_180051A39
0x180051a31  mov     ecx, eax; int
0x180051a33  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180051a39  lea     rcx, [rbp+110h+var_D0]; pvarg
0x180051a3d  call    cs:__imp_VariantClear
0x180051a43  test    eax, eax
0x180051a45  jns     short loc_180051A4F
0x180051a47  mov     ecx, eax; int
0x180051a49  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180051a4f  lea     rcx, [rbp+110h+pvarg]; pvarg
0x180051a53  call    cs:__imp_VariantClear
0x180051a59  test    eax, eax
0x180051a5b  jns     short loc_180051A65
0x180051a5d  mov     ecx, eax; int
0x180051a5f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180051a65  test    ebx, ebx
0x180051a67  js      loc_180052512
0x180051a6d  mov     [rbp+110h+var_160], r12
0x180051a71  mov     rbx, [rbp+110h+var_180]
0x180051a75  mov     rsi, [rbx]
0x180051a78  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180051a7f  mov     ecx, 18h; unsigned __int64
0x180051a84  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180051a89  mov     rdi, rax
0x180051a8c  mov     [rbp+110h+arg_10], rax
0x180051a93  test    rax, rax
0x180051a96  jz      short loc_180051AC3
0x180051a98  mov     [rax+8], r12
0x180051a9c  mov     dword ptr [rax+10h], 1
0x180051aa3  lea     rcx, asc_1800C3A8C; "\\"
0x180051aaa  call    cs:__imp_SysAllocString
0x180051ab0  mov     [rdi], rax
0x180051ab3  test    rax, rax
0x180051ab6  jnz     short loc_180051AC6
0x180051ab8  mov     ecx, 8007000Eh; int
0x180051abd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180051ac3  mov     rdi, r12
0x180051ac6  mov     [rbp+110h+arg_10], rdi
0x180051acd  test    rdi, rdi
0x180051ad0  jz      loc_180052507
0x180051ad6  lea     r8, [rbp+110h+var_160]
0x180051ada  mov     rdx, [rdi]
0x180051add  mov     rcx, rbx
0x180051ae0  mov     rax, [rsi+38h]
0x180051ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ae9  mov     ebx, eax
0x180051aeb  mov     rcx, rdi; this
0x180051aee  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x180051af3  test    ebx, ebx
0x180051af5  js      loc_18005249D
0x180051afb  mov     rbx, [rbp+110h+var_160]
0x180051aff  mov     rsi, [rbx]
0x180051b02  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180051b09  mov     ecx, 18h; unsigned __int64
0x180051b0e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180051b13  mov     rdi, rax
0x180051b16  mov     [rbp+110h+arg_10], rax
0x180051b1d  test    rax, rax
0x180051b20  jz      short loc_180051B4D
0x180051b22  mov     [rax+8], r12
0x180051b26  mov     dword ptr [rax+10h], 1
0x180051b2d  lea     rcx, aMicrosoftWindo; "Microsoft\\Windows\\GroupPolicy"
0x180051b34  call    cs:__imp_SysAllocString
0x180051b3a  mov     [rdi], rax
0x180051b3d  test    rax, rax
0x180051b40  jnz     short loc_180051B50
0x180051b42  mov     ecx, 8007000Eh; int
0x180051b47  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180051b4d  mov     rdi, r12
0x180051b50  mov     [rbp+110h+arg_10], rdi
0x180051b57  test    rdi, rdi
0x180051b5a  jz      loc_180052507
0x180051b60  lea     r8, [rsp+210h+pvarSrc]
0x180051b65  mov     rdx, [rdi]
0x180051b68  mov     rcx, rbx
0x180051b6b  mov     rax, [rsi+48h]
0x180051b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b74  mov     ebx, eax
0x180051b76  mov     rcx, rdi; this
0x180051b79  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x180051b7e  test    ebx, ebx
0x180051b80  js      loc_180052456
0x180051b86  mov     [rbp+110h+var_188], r12
0x180051b8a  mov     rbx, qword ptr [rsp+210h+pvarSrc]
0x180051b8f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180051b96  mov     ecx, 18h; unsigned __int64
0x180051b9b  mov     rsi, [rbx]
0x180051b9e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180051ba3  mov     rdi, rax
0x180051ba6  mov     [rbp+110h+arg_10], rax
0x180051bad  test    r13d, r13d
0x180051bb0  jz      short loc_180051C08
0x180051bb2  test    rax, rax
0x180051bb5  jz      short loc_180051BE2
0x180051bb7  mov     [rax+8], r12
0x180051bbb  mov     dword ptr [rax+10h], 1
0x180051bc2  lea     rcx, a3e0a038bD83449; "{3E0A038B-D834-4930-9981-E89C9BFF83AA}"
0x180051bc9  call    cs:__imp_SysAllocString
0x180051bcf  mov     [rdi], rax
0x180051bd2  test    rax, rax
0x180051bd5  jnz     short loc_180051BE5
0x180051bd7  mov     ecx, 8007000Eh; int
0x180051bdc  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180051be2  mov     rdi, r12
0x180051be5  mov     [rbp+110h+arg_10], rdi
0x180051bec  test    rdi, rdi
0x180051bef  jz      short loc_180051C47
0x180051bf1  lea     r8, [rbp+110h+var_188]
0x180051bf5  mov     rdx, [rdi]
0x180051bf8  mov     rcx, rbx
0x180051bfb  mov     rax, [rsi+68h]
0x180051bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c04  mov     ebx, eax
0x180051c06  jmp     short loc_180051C67
0x180051c08  test    rax, rax
0x180051c0b  jz      short loc_180051C38
0x180051c0d  mov     [rax+8], r12
0x180051c11  mov     dword ptr [rax+10h], 1
0x180051c18  lea     rcx, aA7719e0f10db46; "{A7719E0F-10DB-4640-AD8C-490CC6AD5202}"
0x180051c1f  call    cs:__imp_SysAllocString
0x180051c25  mov     [rdi], rax
0x180051c28  test    rax, rax
0x180051c2b  jnz     short loc_180051C3B
0x180051c2d  mov     ecx, 8007000Eh; int
0x180051c32  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180051c38  mov     rdi, r12
0x180051c3b  mov     [rbp+110h+arg_10], rdi
0x180051c42  test    rdi, rdi
0x180051c45  jnz     short loc_180051C52
0x180051c47  mov     ecx, 8007000Eh; int
0x180051c4c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180051c52  lea     r8, [rbp+110h+var_188]
0x180051c56  mov     rdx, [rdi]
0x180051c59  mov     rcx, rbx
0x180051c5c  mov     rax, [rsi+68h]
0x180051c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c65  mov     ebx, eax
0x180051c67  mov     rcx, rdi; this
0x180051c6a  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x180051c6f  mov     esi, 2
0x180051c74  test    ebx, ebx
0x180051c76  jns     loc_180051D26
0x180051c7c  cmp     ebx, 80070002h
0x180051c82  jz      short loc_180051CD5
0x180051c84  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180051c8b  jz      loc_180051D26
0x180051c91  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180051c98  test    rax, rax
0x180051c9b  jz      short loc_180051CB0
0x180051c9d  mov     r8d, ebx
0x180051ca0  lea     rdx, aUpdatewnftrigg_8; "UpdateWNFTrigger failed: 0x%x"
0x180051ca7  mov     ecx, esi
0x180051ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051cae  jmp     short loc_180051D26
0x180051cb0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180051cb7  jz      short loc_180051D26
0x180051cb9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180051cc0  jz      short loc_180051D26
0x180051cc2  mov     r8d, ebx
0x180051cc5  lea     rdx, aUpdatewnftrigg_8; "UpdateWNFTrigger failed: 0x%x"
0x180051ccc  mov     ecx, esi; unsigned int
0x180051cce  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180051cd3  jmp     short loc_180051D26
0x180051cd5  test    r15d, r15d
0x180051cd8  jnz     short loc_180051CDF
0x180051cda  mov     ebx, r12d
0x180051cdd  jmp     short loc_180051D26
  ... truncated ...
```
