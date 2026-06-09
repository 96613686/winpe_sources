# CAppExport::ExportLegacyClasses(_GUID,ushort *,ulong)

- ea: `0x18004f3a0`
- end: `0x1800501f5`
- name: `?ExportLegacyClasses@CAppExport@@AEAAJU_GUID@@PEAGK@Z`
- size: `3669`
- prototype: `__int64 __fastcall(CAppExport *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fe08`

## callees

- `0x18001a6c8`
- `0x18004d864`
- `0x18004f2a4`
- `0x18004f3a0`
- `0x1800501fc`
- `0x180055502`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004fe4b`
- `msvcrt!_wcsicmp` at `0x18004fe4b`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004f447`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004f579`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004f447`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004f579`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004fff9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180050054`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800500ae`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180050120`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004fff9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180050054`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800500ae`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180050120`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050195`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050195`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f649`

## pseudocode

```c
__int64 __fastcall CAppExport::ExportLegacyClasses(CAppExport *this, struct _GUID *a2, unsigned __int16 *a3, int a4)
{
  char v7; // si
  bool v8; // zf
  HRESULT SimpleTableDispenser; // ebx
  int v10; // eax
  _QWORD *v11; // rdi
  unsigned __int64 v12; // r8
  int v13; // r13d
  int v14; // eax
  __int64 v15; // r8
  unsigned int **v16; // r12
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  unsigned __int16 **v24; // r14
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 v29; // r8
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 v32; // r8
  __int64 v33; // r8
  const wchar_t **v34; // rsi
  unsigned int v35; // r12d
  CAppExport *v36; // rcx
  unsigned __int64 v37; // r9
  unsigned __int16 *v38; // rsi
  __int64 v39; // r14
  __int64 v41; // [rsp+28h] [rbp-D8h]
  unsigned int v42; // [rsp+50h] [rbp-B0h] BYREF
  signed __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h]
  __int64 v45; // [rsp+68h] [rbp-98h]
  int v46; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v47; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v48; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v49; // [rsp+88h] [rbp-78h] BYREF
  GUID v50; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v51; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID *v52; // [rsp+A8h] [rbp-58h] BYREF
  int v53; // [rsp+B0h] [rbp-50h]
  int v54; // [rsp+B4h] [rbp-4Ch]
  int v55; // [rsp+B8h] [rbp-48h]
  int v56; // [rsp+BCh] [rbp-44h]
  unsigned __int16 *v57; // [rsp+C0h] [rbp-40h] BYREF
  int v58; // [rsp+C8h] [rbp-38h]
  int v59; // [rsp+CCh] [rbp-34h]
  int v60; // [rsp+D0h] [rbp-30h]
  int v61; // [rsp+D4h] [rbp-2Ch]
  GUID pguid; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v63[264]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v64[264]; // [rsp+300h] [rbp+200h] BYREF

  v46 = a4;
  v45 = 0;
  v7 = a4;
  memset_0(v63, 0, 0x208u);
  v8 = *((_QWORD *)this + 22) == 0;
  v52 = a2;
  v53 = 0;
  v54 = 9;
  v55 = 72;
  v56 = 16;
  v44 = 0;
  if ( !v8 )
  {
LABEL_5:
    memcmp_0(tidCOMSERVICES_LEGACYCLASSES, &TID_APPLICATION, 0x10u);
    LODWORD(v41) = 1;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, struct _GUID **, __int64))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             tidCOMSERVICES_LEGACYCLASSES,
                             &v52,
                             1);
    goto LABEL_6;
  }
  v43 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v43);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, v43, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v43 + 16LL))(v43);
    goto LABEL_5;
  }
LABEL_6:
  if ( SimpleTableDispenser < 0 )
    goto LABEL_132;
  if ( !v44 )
  {
    SimpleTableDispenser = -2147024882;
    goto LABEL_134;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 24LL))(v44);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_132;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 32LL))(v44);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_132;
  v57 = a3;
  v58 = 0;
  v59 = -268435455;
  v60 = 130;
  v10 = safe_lstrlenW(a3);
  v8 = *((_QWORD *)this + 22) == 0;
  v45 = 0;
  v61 = 2 * v10 + 2;
  if ( !v8 )
    goto LABEL_15;
  v43 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v43);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, v43, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v43 + 16LL))(v43);
LABEL_15:
    memcmp_0(tidCOMSERVICES_LEGACYCLASSES_EXPORT, &TID_APPLICATION, 0x10u);
    LODWORD(v41) = 1;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             tidCOMSERVICES_LEGACYCLASSES_EXPORT,
                             &v57,
                             1);
  }
  if ( SimpleTableDispenser < 0 )
    goto LABEL_132;
  if ( !v45 )
    goto LABEL_18;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 24LL))(v45);
  if ( SimpleTableDispenser >= 0 )
  {
    v11 = CoTaskMemAlloc(0xD8u);
    if ( v11 )
    {
      v13 = v7 & 0x20;
      if ( (v7 & 0x20) == 0 )
      {
        v63[0] = 0;
        goto LABEL_26;
      }
      SimpleTableDispenser = CAppExport::GetCurrentRSN(this, v63, v12);
      if ( SimpleTableDispenser >= 0 )
      {
LABEL_26:
        while ( 1 )
        {
          v47 = 0;
          v49 = 0;
          v48 = 0;
          v51 = 0;
          LODWORD(v43) = 0;
          v42 = 0;
          v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 40LL))(v44);
          SimpleTableDispenser = v14;
          if ( v14 == -2146367487 )
            break;
          if ( v14 < 0 )
            goto LABEL_131;
          if ( v7 < 0 )
          {
            SimpleTableDispenser = -2146367462;
            goto LABEL_131;
          }
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 120LL))(v45);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          memset_0(v11, 0, 0xD8u);
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   0,
                                   &v43,
                                   &v42,
                                   v11);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v15 = 0;
          if ( (_DWORD)v43 == 128 )
            v15 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   0,
                                   v15,
                                   *v11);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v16 = (unsigned int **)(v11 + 1);
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   1,
                                   &v43,
                                   &v42,
                                   v11 + 1);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v17 = 0;
          if ( (_DWORD)v43 == 128 )
            v17 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned int *))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   1,
                                   v17,
                                   *v16);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   2,
                                   &v43,
                                   &v42,
                                   v11 + 2);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v18 = 0;
          if ( (_DWORD)v43 == 128 )
            v18 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   2,
                                   v18,
                                   v11[2]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   3,
                                   &v43,
                                   &v42,
                                   v11 + 3);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v19 = 0;
          if ( (_DWORD)v43 == 128 )
            v19 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   3,
                                   v19,
                                   v11[3]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   8,
                                   &v43,
                                   &v42,
                                   v11 + 4);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v20 = 0;
          if ( (_DWORD)v43 == 128 )
            v20 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   4,
                                   v20,
                                   v11[4]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   9,
                                   &v43,
                                   &v42,
                                   v11 + 5);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v21 = 0;
          if ( (_DWORD)v43 == 128 )
            v21 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   5,
                                   v21,
                                   v11[5]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   11,
                                   &v43,
                                   &v42,
                                   v11 + 6);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v22 = 0;
          if ( (_DWORD)v43 == 128 )
            v22 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   6,
                                   v22,
                                   v11[6]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   12,
                                   &v43,
                                   &v42,
                                   v11 + 7);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v23 = 0;
          if ( (_DWORD)v43 == 128 )
            v23 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   7,
                                   v23,
                                   v11[7]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v24 = (unsigned __int16 **)(v11 + 8);
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   13,
                                   &v43,
                                   &v42,
                                   v11 + 8);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v25 = 0;
          if ( (_DWORD)v43 == 128 )
            v25 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned __int16 *))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   8,
                                   v25,
                                   *v24);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   14,
                                   &v43,
                                   &v42,
                                   v11 + 9);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v26 = 0;
          if ( (_DWORD)v43 == 128 )
            v26 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   9,
                                   v26,
                                   v11[9]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   15,
                                   &v43,
                                   &v42,
                                   v11 + 10);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v27 = 0;
          if ( (_DWORD)v43 == 128 )
            v27 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   10,
                                   v27,
                                   v11[10]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   19,
                                   &v43,
                                   &v42,
                                   v11 + 13);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v28 = 0;
          if ( (_DWORD)v43 == 128 )
            v28 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   13,
                                   v28,
                                   v11[13]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   22,
                                   &v43,
                                   &v42,
                                   v11 + 16);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v29 = 0;
          if ( (_DWORD)v43 == 128 )
            v29 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   16,
                                   v29,
                                   v11[16]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   10,
                                   &v43,
                                   &v42,
                                   v11 + 18);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v30 = 0;
          if ( (_DWORD)v43 == 128 )
            v30 = v42;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                   v45,
                                   18,
                                   v30,
                                   v11[18]);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          if ( (v46 & 0x10) != 0 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                     v44,
                                     20,
                                     &v43,
                                     &v42,
                                     v11 + 14);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            v31 = 0;
            if ( (_DWORD)v43 == 128 )
              v31 = v42;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                     v45,
                                     14,
                                     v31,
                                     v11[14]);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                     v44,
                                     21,
                                     &v43,
                                     &v42,
                                     v11 + 15);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            v32 = 0;
            if ( (_DWORD)v43 == 128 )
              v32 = v42;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                     v45,
                                     15,
                                     v32,
                                     v11[15]);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
          }
          if ( !v13 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                     v44,
                                     16,
                                     &v43,
                                     &v42,
                                     v11 + 11);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            v33 = 0;
            if ( (_DWORD)v43 == 128 )
              v33 = v42;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v45 + 160LL))(
                                     v45,
                                     11,
                                     v33,
                                     v11[11]);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
          }
          v34 = (const wchar_t **)(v11 + 12);
          v35 = **v16;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   17,
                                   &v43,
                                   &v42,
                                   v11 + 12);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          if ( *v34 )
          {
            if ( !_wcsicmp(*v34, L"Interactive User") )
            {
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v45 + 160LL))(
                                       v45,
                                       12,
                                       0,
                                       *v34);
              if ( SimpleTableDispenser < 0 )
                goto LABEL_131;
            }
          }
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v44 + 64LL))(
                                   v44,
                                   13,
                                   &v43,
                                   &v42,
                                   v11 + 8);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          if ( !*v24 && v13 )
            *v24 = v63;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 160LL))(v45, 8);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          if ( !v13 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, const unsigned __int16 **))(*(_QWORD *)v44 + 64LL))(
                                     v44,
                                     5,
                                     &v43,
                                     &v42,
                                     &v47);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, const unsigned __int16 **))(*(_QWORD *)v44 + 64LL))(
                                     v44,
                                     4,
                                     &v43,
                                     &v42,
                                     &v48);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, const unsigned __int16 **))(*(_QWORD *)v44 + 64LL))(
                                     v44,
                                     7,
                                     &v43,
                                     &v42,
                                     &v49);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, signed __int64 *, unsigned int *, unsigned __int16 **))(*(_QWORD *)v44 + 64LL))(
                                     v44,
                                     16,
                                     &v43,
                                     &v42,
                                     &v51);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
          }
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 144LL))(v45);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_131;
          v38 = (unsigned __int16 *)v11[2];
          v39 = v11[3];
          if ( v47 )
          {
            pguid = 0;
            SimpleTableDispenser = CoCreateGuid(&pguid);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            v50 = pguid;
            SimpleTableDispenser = CAppExport::AddLegacyClass(this, v47, (__int128 *)&v50, v38, v39, v41, 3, v35);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
          }
          if ( v48 )
          {
            pguid = 0;
            SimpleTableDispenser = CoCreateGuid(&pguid);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            v50 = pguid;
            SimpleTableDispenser = CAppExport::AddLegacyClass(this, v48, (__int128 *)&v50, v38, v39, v41, 3, v35);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
          }
          if ( v49 )
          {
            pguid = 0;
            SimpleTableDispenser = CoCreateGuid(&pguid);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            v50 = pguid;
            SimpleTableDispenser = CAppExport::AddLegacyClass(this, v49, (__int128 *)&v50, v38, v39, v41, 4, v35);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
          }
          if ( v51 )
          {
            pguid = 0;
            SimpleTableDispenser = CAppExport::GetDllSurrogateFile(v36, v51, v64, v37);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            SimpleTableDispenser = CoCreateGuid(&pguid);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
            v50 = pguid;
            SimpleTableDispenser = CAppExport::AddLegacyClass(this, v64, (__int128 *)&v50, v38, v39, v41, 5, v35);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_131;
          }
          v7 = v46;
        }
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 96LL))(v45);
      }
LABEL_131:
      memset_0(v11, 0, 0xD8u);
      CoTaskMemFree(v11);
      goto LABEL_132;
    }
LABEL_18:
    SimpleTableDispenser = -2147024882;
  }
LABEL_132:
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
LABEL_134:
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18004f3a0  push    rbp
0x18004f3a2  push    rbx
0x18004f3a3  push    rsi
0x18004f3a4  push    rdi
0x18004f3a5  push    r12
0x18004f3a7  push    r13
0x18004f3a9  push    r14
0x18004f3ab  push    r15
0x18004f3ad  lea     rbp, [rsp-428h]
0x18004f3b5  sub     rsp, 528h
0x18004f3bc  mov     rax, cs:__security_cookie
0x18004f3c3  xor     rax, rsp
0x18004f3c6  mov     [rbp+460h+var_50], rax
0x18004f3cd  mov     rdi, r8
0x18004f3d0  mov     [rsp+560h+var_4F0], r9d
0x18004f3d5  mov     rbx, rdx
0x18004f3d8  mov     [rsp+560h+var_4F8], 0
0x18004f3e1  mov     r15, rcx
0x18004f3e4  xor     edx, edx; Val
0x18004f3e6  mov     r8d, 208h; Size
0x18004f3ec  lea     rcx, [rbp+460h+var_470]; void *
0x18004f3f0  mov     esi, r9d
0x18004f3f3  call    memset_0
0x18004f3f8  cmp     qword ptr [r15+0B0h], 0
0x18004f400  mov     r14d, 10h
0x18004f406  mov     [rbp+460h+var_4B8], rbx
0x18004f40a  mov     [rbp+460h+var_4B0], 0
0x18004f411  mov     [rbp+460h+var_4AC], 9
0x18004f418  lea     r12d, [r14-0Fh]
0x18004f41c  mov     [rbp+460h+var_4A8], 48h ; 'H'
0x18004f423  mov     [rbp+460h+var_4A4], r14d
0x18004f427  mov     [rsp+560h+var_500], 0
0x18004f430  jnz     short loc_18004F47A
0x18004f432  lea     rdx, [rsp+560h+var_508]
0x18004f437  mov     [rsp+560h+var_508], 0
0x18004f440  lea     rcx, IID_ISimpleTableDispenser
0x18004f447  call    cs:__imp_GetSimpleTableDispenser
0x18004f44d  mov     ebx, eax
0x18004f44f  test    eax, eax
0x18004f451  js      loc_18004F4D9
0x18004f457  mov     rcx, [rsp+560h+var_508]
0x18004f45c  xor     eax, eax
0x18004f45e  lock cmpxchg [r15+0B0h], rcx
0x18004f467  jz      short loc_18004F47A
0x18004f469  mov     rcx, [rsp+560h+var_508]
0x18004f46e  mov     rax, [rcx]
0x18004f471  mov     rax, [rax+10h]
0x18004f475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f47a  mov     r8, r14; Size
0x18004f47d  lea     rdx, TID_APPLICATION; Buf2
0x18004f484  lea     rcx, tidCOMSERVICES_LEGACYCLASSES; Buf1
0x18004f48b  call    memcmp_0
0x18004f490  mov     rcx, [r15+0B0h]
0x18004f497  lea     r9, [rsp+560h+var_500]
0x18004f49c  mov     [rsp+560h+var_528], r9
0x18004f4a1  lea     r8, tidCOMSERVICES_LEGACYCLASSES
0x18004f4a8  neg     eax
0x18004f4aa  lea     r9, [rbp+460h+var_4B8]
0x18004f4ae  mov     rax, [rcx]
0x18004f4b1  sbb     edx, edx
0x18004f4b3  and     edx, 2
0x18004f4b6  add     edx, 5
0x18004f4b9  mov     [rsp+560h+var_530], edx
0x18004f4bd  lea     rdx, didCOMSERVICES
0x18004f4c4  mov     rax, [rax+18h]
0x18004f4c8  mov     dword ptr [rsp+560h+var_538], r12d
0x18004f4cd  mov     [rsp+560h+var_540], r12
0x18004f4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4d7  mov     ebx, eax
0x18004f4d9  test    ebx, ebx
0x18004f4db  js      loc_18005019B
0x18004f4e1  mov     rcx, [rsp+560h+var_500]
0x18004f4e6  test    rcx, rcx
0x18004f4e9  jnz     short loc_18004F4F5
0x18004f4eb  mov     ebx, 8007000Eh
0x18004f4f0  jmp     loc_1800501BA
0x18004f4f5  mov     rax, [rcx]
0x18004f4f8  mov     rax, [rax+18h]
0x18004f4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f501  mov     ebx, eax
0x18004f503  test    eax, eax
0x18004f505  js      loc_18005019B
0x18004f50b  mov     rcx, [rsp+560h+var_500]
0x18004f510  mov     rax, [rcx]
0x18004f513  mov     rax, [rax+20h]
0x18004f517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f51c  mov     ebx, eax
0x18004f51e  test    eax, eax
0x18004f520  js      loc_18005019B
0x18004f526  mov     rcx, rdi; unsigned __int16 *
0x18004f529  mov     [rbp+460h+var_4A0], rdi
0x18004f52d  mov     [rbp+460h+var_498], 0
0x18004f534  mov     [rbp+460h+var_494], 0F0000001h
0x18004f53b  mov     [rbp+460h+var_490], 82h
0x18004f542  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004f547  cmp     qword ptr [r15+0B0h], 0
0x18004f54f  mov     [rsp+560h+var_4F8], 0
0x18004f558  lea     eax, ds:2[rax*2]
0x18004f55f  mov     [rbp+460h+var_48C], eax
0x18004f562  jnz     short loc_18004F5AC
0x18004f564  lea     rdx, [rsp+560h+var_508]
0x18004f569  mov     [rsp+560h+var_508], 0
0x18004f572  lea     rcx, IID_ISimpleTableDispenser
0x18004f579  call    cs:__imp_GetSimpleTableDispenser
0x18004f57f  mov     ebx, eax
0x18004f581  test    eax, eax
0x18004f583  js      loc_18004F60F
0x18004f589  mov     rcx, [rsp+560h+var_508]
0x18004f58e  xor     eax, eax
0x18004f590  lock cmpxchg [r15+0B0h], rcx
0x18004f599  jz      short loc_18004F5AC
0x18004f59b  mov     rcx, [rsp+560h+var_508]
0x18004f5a0  mov     rax, [rcx]
0x18004f5a3  mov     rax, [rax+10h]
0x18004f5a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5ac  mov     r8, r14; Size
0x18004f5af  lea     rdx, TID_APPLICATION; Buf2
0x18004f5b6  lea     rcx, tidCOMSERVICES_LEGACYCLASSES_EXPORT; Buf1
0x18004f5bd  call    memcmp_0
0x18004f5c2  mov     rcx, [r15+0B0h]
0x18004f5c9  lea     r10, [rsp+560h+var_4F8]
0x18004f5ce  neg     eax
0x18004f5d0  mov     [rsp+560h+var_528], r10
0x18004f5d5  lea     r8, tidCOMSERVICES_LEGACYCLASSES_EXPORT
0x18004f5dc  sbb     r9d, r9d
0x18004f5df  lea     rdx, didCOMSERVICES
0x18004f5e6  mov     rax, [rcx]
0x18004f5e9  and     r9d, 2
0x18004f5ed  add     r9d, 4
0x18004f5f1  mov     [rsp+560h+var_530], r9d
0x18004f5f6  lea     r9, [rbp+460h+var_4A0]
0x18004f5fa  mov     dword ptr [rsp+560h+var_538], r12d
0x18004f5ff  mov     rax, [rax+18h]
0x18004f603  mov     [rsp+560h+var_540], r12
0x18004f608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f60d  mov     ebx, eax
0x18004f60f  test    ebx, ebx
0x18004f611  js      loc_18005019B
0x18004f617  cmp     [rsp+560h+var_4F8], 0
0x18004f61d  jnz     short loc_18004F629
0x18004f61f  mov     ebx, 8007000Eh
0x18004f624  jmp     loc_18005019B
0x18004f629  mov     rcx, [rsp+560h+var_4F8]
0x18004f62e  mov     rax, [rcx]
0x18004f631  mov     rax, [rax+18h]
0x18004f635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f63a  mov     ebx, eax
0x18004f63c  test    eax, eax
0x18004f63e  js      loc_18005019B
0x18004f644  mov     ecx, 0D8h; cb
0x18004f649  call    cs:__imp_CoTaskMemAlloc
0x18004f64f  mov     rdi, rax
0x18004f652  test    rax, rax
0x18004f655  jz      short loc_18004F61F
0x18004f657  mov     r13d, esi
0x18004f65a  and     r13d, 20h
0x18004f65e  jz      short loc_18004F678
0x18004f660  lea     rdx, [rbp+460h+var_470]; unsigned __int16 *
0x18004f664  mov     rcx, r15; this
0x18004f667  call    ?GetCurrentRSN@CAppExport@@AEAAJPEAG_K@Z; CAppExport::GetCurrentRSN(ushort *,unsigned __int64)
0x18004f66c  mov     ebx, eax
0x18004f66e  test    eax, eax
0x18004f670  js      loc_180050182
0x18004f676  jmp     short loc_18004F684
0x18004f678  xor     eax, eax
0x18004f67a  mov     [rbp+460h+var_470], ax
0x18004f67e  jmp     short loc_18004F684
0x18004f680  mov     esi, [rsp+560h+var_4F0]
0x18004f684  mov     rcx, [rsp+560h+var_500]
0x18004f689  mov     r14d, 80h
0x18004f68f  mov     [rsp+560h+var_4E8], 0
0x18004f698  mov     [rbp+460h+var_4D8], 0
0x18004f6a0  mov     [rbp+460h+var_4E0], 0
0x18004f6a8  mov     [rbp+460h+var_4C0], 0
0x18004f6b0  mov     dword ptr [rsp+560h+var_508], 0
0x18004f6b8  mov     [rsp+560h+var_510], 0
0x18004f6c0  mov     rax, [rcx]
0x18004f6c3  mov     rax, [rax+28h]
0x18004f6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6cc  mov     ebx, eax
0x18004f6ce  cmp     eax, 80110801h
0x18004f6d3  jz      loc_18005016F
0x18004f6d9  test    eax, eax
0x18004f6db  js      loc_180050182
0x18004f6e1  test    r14b, sil
0x18004f6e4  jnz     loc_180050168
0x18004f6ea  mov     rcx, [rsp+560h+var_4F8]
0x18004f6ef  mov     rax, [rcx]
0x18004f6f2  mov     rax, [rax+78h]
0x18004f6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6fb  mov     ebx, eax
0x18004f6fd  test    eax, eax
0x18004f6ff  js      loc_180050182
0x18004f705  xor     edx, edx; Val
0x18004f707  lea     r8d, [r14+58h]; Size
0x18004f70b  mov     rcx, rdi; void *
0x18004f70e  call    memset_0
0x18004f713  mov     rcx, [rsp+560h+var_500]
0x18004f718  lea     r9, [rsp+560h+var_510]
0x18004f71d  lea     r8, [rsp+560h+var_508]
0x18004f722  mov     [rsp+560h+var_540], rdi
0x18004f727  xor     edx, edx
0x18004f729  mov     rax, [rcx]
0x18004f72c  mov     rax, [rax+40h]
0x18004f730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f735  mov     ebx, eax
0x18004f737  test    eax, eax
0x18004f739  js      loc_180050182
0x18004f73f  mov     rcx, [rsp+560h+var_4F8]
0x18004f744  xor     r8d, r8d
0x18004f747  cmp     dword ptr [rsp+560h+var_508], r14d
0x18004f74c  mov     r9, [rdi]
0x18004f74f  cmovz   r8d, [rsp+560h+var_510]
0x18004f755  xor     edx, edx
0x18004f757  mov     rax, [rcx]
0x18004f75a  mov     rax, [rax+0A0h]
0x18004f761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f766  mov     ebx, eax
0x18004f768  test    eax, eax
0x18004f76a  js      loc_180050182
0x18004f770  mov     rcx, [rsp+560h+var_500]
0x18004f775  lea     r12, [rdi+8]
0x18004f779  lea     r9, [rsp+560h+var_510]
0x18004f77e  mov     [rsp+560h+var_540], r12
0x18004f783  lea     r8, [rsp+560h+var_508]
0x18004f788  lea     edx, [r14-7Fh]
0x18004f78c  mov     rax, [rcx]
0x18004f78f  mov     rax, [rax+40h]
0x18004f793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f798  mov     ebx, eax
0x18004f79a  test    eax, eax
0x18004f79c  js      loc_180050182
0x18004f7a2  mov     rcx, [rsp+560h+var_4F8]
0x18004f7a7  lea     edx, [r14-7Fh]
0x18004f7ab  mov     r9, [r12]
0x18004f7af  xor     r8d, r8d
0x18004f7b2  cmp     dword ptr [rsp+560h+var_508], r14d
0x18004f7b7  mov     rax, [rcx]
0x18004f7ba  cmovz   r8d, [rsp+560h+var_510]
0x18004f7c0  mov     rax, [rax+0A0h]
0x18004f7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7cc  mov     ebx, eax
0x18004f7ce  test    eax, eax
0x18004f7d0  js      loc_180050182
0x18004f7d6  mov     rcx, [rsp+560h+var_500]
0x18004f7db  lea     rsi, [rdi+10h]
0x18004f7df  lea     r9, [rsp+560h+var_510]
0x18004f7e4  mov     [rsp+560h+var_540], rsi
0x18004f7e9  lea     r8, [rsp+560h+var_508]
0x18004f7ee  lea     edx, [r14-7Eh]
0x18004f7f2  mov     rax, [rcx]
0x18004f7f5  mov     rax, [rax+40h]
0x18004f7f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7fe  mov     ebx, eax
0x18004f800  test    eax, eax
0x18004f802  js      loc_180050182
0x18004f808  mov     rcx, [rsp+560h+var_4F8]
0x18004f80d  lea     edx, [r14-7Eh]
0x18004f811  mov     r9, [rsi]
0x18004f814  xor     r8d, r8d
0x18004f817  cmp     dword ptr [rsp+560h+var_508], r14d
0x18004f81c  mov     rax, [rcx]
0x18004f81f  cmovz   r8d, [rsp+560h+var_510]
0x18004f825  mov     rax, [rax+0A0h]
0x18004f82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f831  mov     ebx, eax
0x18004f833  test    eax, eax
0x18004f835  js      loc_180050182
0x18004f83b  mov     rcx, [rsp+560h+var_500]
0x18004f840  lea     rsi, [rdi+18h]
0x18004f844  lea     r9, [rsp+560h+var_510]
0x18004f849  mov     [rsp+560h+var_540], rsi
0x18004f84e  lea     r8, [rsp+560h+var_508]
0x18004f853  lea     edx, [r14-7Dh]
0x18004f857  mov     rax, [rcx]
0x18004f85a  mov     rax, [rax+40h]
0x18004f85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f863  mov     ebx, eax
0x18004f865  test    eax, eax
0x18004f867  js      loc_180050182
0x18004f86d  mov     rcx, [rsp+560h+var_4F8]
0x18004f872  lea     edx, [r14-7Dh]
0x18004f876  mov     r9, [rsi]
0x18004f879  xor     r8d, r8d
0x18004f87c  cmp     dword ptr [rsp+560h+var_508], r14d
0x18004f881  mov     rax, [rcx]
0x18004f884  cmovz   r8d, [rsp+560h+var_510]
0x18004f88a  mov     rax, [rax+0A0h]
0x18004f891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f896  mov     ebx, eax
0x18004f898  test    eax, eax
0x18004f89a  js      loc_180050182
0x18004f8a0  mov     rcx, [rsp+560h+var_500]
0x18004f8a5  lea     rsi, [rdi+20h]
0x18004f8a9  lea     r9, [rsp+560h+var_510]
0x18004f8ae  mov     [rsp+560h+var_540], rsi
0x18004f8b3  lea     r8, [rsp+560h+var_508]
0x18004f8b8  lea     edx, [r14-78h]
0x18004f8bc  mov     rax, [rcx]
0x18004f8bf  mov     rax, [rax+40h]
  ... truncated ...
```
