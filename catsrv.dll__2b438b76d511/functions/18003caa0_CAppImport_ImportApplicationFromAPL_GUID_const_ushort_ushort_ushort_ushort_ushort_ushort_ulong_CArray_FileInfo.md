# CAppImport::ImportApplicationFromAPL(_GUID const &,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ulong,CArray<FileInfo *,FileInfo * const &> * *,CArray<CompInfo *,CompInfo * const &> * *)

- ea: `0x18003caa0`
- end: `0x18003d4b3`
- name: `?ImportApplicationFromAPL@CAppImport@@AEAAJAEBU_GUID@@PEAG11111KPEAPEAV?$CArray@PEAUFileInfo@@AEBQEAU1@@@PEAPEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@@Z`
- size: `2579`
- prototype: `__int64 __usercall@<rax>(CAppImport *this@<rcx>, LPCWSTR lpFileName, __int64, __int64, __int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c380`

## callees

- `0x180011d74`
- `0x18001a6c8`
- `0x180030044`
- `0x18003ac0c`
- `0x18003b308`
- `0x18003caa0`
- `0x18003d92c`
- `0x18003e730`
- `0x18003fb58`
- `0x180041220`
- `0x1800413e0`
- `0x180049054`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003cf28`
- `msvcrt!_wcsicmp` at `0x18003cf28`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003cc64`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003d2b5`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003cc64`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003d2b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf05`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003cef7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003cef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ceee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d17c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ceee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d17c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cb65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cb9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cb65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cb9e`

## pseudocode

```c
__int64 __fastcall CAppImport::ImportApplicationFromAPL(
        CAppImport *this,
        struct _GUID *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *lpFileName,
        __int64 a6,
        __int64 a7,
        unsigned __int16 *a8,
        unsigned int a9,
        _QWORD *a10,
        __int64 a11)
{
  const WCHAR *v11; // r12
  struct _GUID *v13; // rsi
  struct _GUID *v14; // r15
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // r14
  signed int FileList; // ebx
  int SimpleTableDispenser; // eax
  bool v20; // zf
  int v21; // eax
  int v22; // r12d
  unsigned int v23; // esi
  _QWORD *v24; // rax
  struct ISimpleTableRead *v25; // rcx
  signed int LastError; // eax
  int v28; // r13d
  unsigned int Data1; // esi
  struct ISimpleTableDispenser *v30; // rcx
  int v31; // esi
  signed int v32; // eax
  int v33; // r12d
  struct _GUID **v34; // [rsp+28h] [rbp-D8h]
  struct _GUID **v35; // [rsp+28h] [rbp-D8h]
  struct _GUID *pv; // [rsp+50h] [rbp-B0h]
  struct ISimpleTableRead *v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  int v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v41; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *String2; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID *v43; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v44; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID Buf1; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v46; // [rsp+A8h] [rbp-58h] BYREF
  int v47; // [rsp+ACh] [rbp-54h] BYREF
  int v48; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v49[3]; // [rsp+B4h] [rbp-4Ch] BYREF
  struct _GUID v50; // [rsp+C0h] [rbp-40h] BYREF
  int v51; // [rsp+D0h] [rbp-30h]
  int v52; // [rsp+D4h] [rbp-2Ch]
  struct _GUID *v53; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID *v54; // [rsp+E8h] [rbp-18h] BYREF
  _WORD *v55; // [rsp+F0h] [rbp-10h] BYREF
  struct _GUID v56; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v57; // [rsp+110h] [rbp+10h]
  struct _GUID v58; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v59; // [rsp+130h] [rbp+30h]
  __int64 v60; // [rsp+138h] [rbp+38h]
  unsigned __int16 *v61; // [rsp+140h] [rbp+40h] BYREF
  int v62; // [rsp+148h] [rbp+48h]
  int v63; // [rsp+14Ch] [rbp+4Ch]
  int v64; // [rsp+150h] [rbp+50h]
  int v65; // [rsp+154h] [rbp+54h]
  struct _GUID v66; // [rsp+160h] [rbp+60h] BYREF

  v11 = lpFileName;
  *(_QWORD *)&v50.Data1 = a6;
  v13 = 0;
  *(_QWORD *)&v58.Data1 = a7;
  v57 = a8;
  v14 = 0;
  v59 = a10;
  v60 = a11;
  v44 = a4;
  *(_QWORD *)&v56.Data1 = a3;
  v43 = a2;
  v46 = 0;
  pv = 0;
  v54 = 0;
  v49[0] = 0;
  v53 = 0;
  v41 = 0;
  v55 = 0;
  v40 = 0;
  v39 = 0;
  String2 = 0;
  v66 = 0;
  v48 = 0;
  v37 = 0;
  v38 = 0;
  v15 = CoTaskMemAlloc(0x20u);
  *(_QWORD *)&Buf1.Data1 = v15;
  if ( v15 )
  {
    v15[1] = 0;
    *v15 = &CArray<DllInfo *,DllInfo * const &>::`vftable';
    *(_QWORD *)((char *)v15 + 20) = 0;
    *((_DWORD *)v15 + 4) = 0;
  }
  else
  {
    v15 = 0;
  }
  *((_QWORD *)this + 11) = v15;
  if ( !v15 )
    return 2147942414LL;
  v16 = CoTaskMemAlloc(0x20u);
  *(_QWORD *)&Buf1.Data1 = v16;
  v17 = (__int64)v16;
  if ( !v16 )
    return 2147942414LL;
  v16[1] = 0;
  *v16 = &CArray<CompInfo *,CompInfo * const &>::`vftable';
  *(_QWORD *)((char *)v16 + 20) = 0;
  *((_DWORD *)v16 + 4) = 0;
  Buf1 = 0;
  FileList = CAppImport::ImportPartitionInfo(this, lpFileName, a9, &Buf1);
  if ( FileList >= 0 )
  {
    if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      LODWORD(v13) = 1;
      *((struct _GUID *)this + 6) = Buf1;
    }
    v61 = lpFileName;
    v62 = 0;
    v63 = -268435455;
    v64 = 130;
    v37 = 0;
    v65 = 2 * safe_lstrlenW(lpFileName) + 2;
    if ( !*((_QWORD *)this + 9) )
    {
      *(_QWORD *)&Buf1.Data1 = 0;
      SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &Buf1);
      v20 = SimpleTableDispenser == 0;
      if ( SimpleTableDispenser < 0 )
      {
LABEL_14:
        if ( !v20 )
        {
          FileList = -2146368504;
LABEL_32:
          v13 = pv;
          goto LABEL_33;
        }
        if ( !v37 )
        {
          FileList = -2147024882;
          goto LABEL_32;
        }
        FileList = (*(__int64 (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v37 + 24LL))(v37);
        if ( FileList )
          goto LABEL_32;
        FileList = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v37 + 72LL))(
                     v37,
                     0,
                     0,
                     0,
                     0,
                     0,
                     0,
                     &v46,
                     0);
        if ( FileList < 0 )
          goto LABEL_32;
        if ( v46 > 1 )
        {
          FileList = -2147418113;
          goto LABEL_32;
        }
        if ( (*(unsigned int (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v37 + 40LL))(v37) == -2146367487 )
        {
          FileList = (_DWORD)v13 == 0 ? 0x80110408 : 0;
          goto LABEL_32;
        }
        FileList = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, _QWORD, int *, int *, wchar_t **))(*(_QWORD *)v37 + 64LL))(
                     v37,
                     0,
                     &v40,
                     &v39,
                     &String2);
        if ( FileList )
          goto LABEL_32;
        v66 = *(struct _GUID *)String2;
        FileList = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, int *, wchar_t **))(*(_QWORD *)v37 + 64LL))(
                     v37,
                     33,
                     &v40,
                     &v39,
                     &String2);
        if ( FileList )
          goto LABEL_32;
        v22 = 256;
        v23 = (2 * (a9 & 1)) | 1;
        if ( String2 && *(_DWORD *)String2 == 1 )
        {
          v22 = 768;
          v23 = (2 * (a9 & 1)) | 5;
        }
        FileList = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, int *, wchar_t **))(*(_QWORD *)v37 + 64LL))(
                     v37,
                     16,
                     &v40,
                     &v39,
                     &String2);
        if ( FileList )
          goto LABEL_31;
        if ( !String2 )
        {
          FileList = -2147418113;
          goto LABEL_31;
        }
        _wcsicmp(L"Inproc", String2);
        g_guidAppIdForQuery = GUID_NULL;
        FileList = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, int *, _WORD **))(*(_QWORD *)v37 + 64LL))(
                     v37,
                     17,
                     &v40,
                     &v39,
                     &v55);
        if ( FileList )
          goto LABEL_31;
        FileList = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD, _QWORD, wchar_t **))(*(_QWORD *)v37 + 64LL))(
                     v37,
                     53,
                     0,
                     0,
                     &String2);
        if ( FileList )
          goto LABEL_31;
        v28 = v23 | (*(_DWORD *)String2 != 0 ? 8 : 0);
        Data1 = v23 & 8 | (*(_DWORD *)String2 != 0 ? 8 : 0);
        Buf1.Data1 = Data1;
        if ( Data1 )
        {
          v30 = (struct ISimpleTableDispenser *)*((_QWORD *)this + 9);
          v47 = 0;
          FileList = CheckIfCLRPresent(v30, &v47);
          if ( FileList )
            goto LABEL_31;
          if ( !v47 )
          {
            FileList = -2147467224;
            goto LABEL_31;
          }
        }
        FileList = CAppImport::CreateFileList(
                     (__int64)this,
                     (__int64)&v66,
                     *((_QWORD *)this + 11),
                     lpFileName,
                     *(wchar_t **)&v56.Data1,
                     v44,
                     v28);
        if ( FileList )
          goto LABEL_31;
        v56 = *v43;
        FileList = CAppImport::UpdateApplicationTable(
                     this,
                     &v56,
                     v37,
                     *(unsigned __int16 **)&v50.Data1,
                     *(unsigned __int16 **)&v58.Data1,
                     v57,
                     v44,
                     v22);
        if ( FileList )
          goto LABEL_31;
        if ( *(int *)(*((_QWORD *)this + 11) + 16LL) > 0 )
        {
          v50 = v66;
          FileList = CAppImport::CreateInstallList(
                       this,
                       &v50,
                       lpFileName,
                       (LPVOID *)&v54,
                       v49,
                       &v53,
                       &v41,
                       (enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *)&v48);
          if ( FileList )
          {
            v13 = v54;
            v14 = v53;
            v11 = lpFileName;
            goto LABEL_33;
          }
          v31 = v48;
          v34 = (struct _GUID **)*((_QWORD *)this + 11);
          pv = v54;
          v50 = *v43;
          v32 = CAppImport::RegisterImportedModules(
                  (__int64)this,
                  (__int128 *)&v50,
                  v22,
                  (__int64)v54,
                  v49[0],
                  (__int64)v34,
                  v17,
                  v48);
          v14 = v53;
          FileList = v32;
          if ( v32 )
            goto LABEL_31;
          if ( v41 )
          {
            v35 = (struct _GUID **)*((_QWORD *)this + 11);
            v50 = *v43;
            FileList = CAppImport::RegisterImportedModules(
                         (__int64)this,
                         (__int128 *)&v50,
                         v22 | 0x400u,
                         (__int64)v53,
                         v41,
                         (__int64)v35,
                         v17,
                         v31);
            if ( FileList )
              goto LABEL_31;
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v14 )
          {
            CoTaskMemFree(v14);
            v14 = 0;
          }
          Data1 = Buf1.Data1;
        }
        FileList = CAppImport::UpdateClassTable(this, v22, v17);
        if ( FileList )
          goto LABEL_31;
        FileList = CAppImport::UpdateLegacyClassTable(this, &v66, lpFileName, v22);
        if ( FileList < 0 )
          goto LABEL_31;
        v58 = v66;
        v50 = *v43;
        FileList = CAppImport::UpdateRoleTables(this, &v58, &v50, lpFileName, a9);
        if ( FileList )
          goto LABEL_31;
        if ( Data1 )
        {
          if ( (v28 & 4) != 0 )
          {
            v50 = *v43;
            FileList = CAppImport::UpdateSoapActivation(this, &v50, v44, v37);
            if ( FileList < 0 )
              goto LABEL_31;
          }
        }
        v33 = v22 & 0x200;
        if ( !v33 && (!v55 || ((*v55 - 78) & 0xFFDF) != 0) )
        {
LABEL_31:
          v11 = lpFileName;
          goto LABEL_32;
        }
        v20 = *((_QWORD *)this + 9) == 0;
        *(_QWORD *)&v50.Data1 = v43;
        Buf1.Data1 = 1;
        *(_QWORD *)v50.Data4 = 0;
        v51 = 72;
        v52 = 16;
        v38 = 0;
        if ( v20 )
        {
          v44 = 0;
          FileList = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v44);
          if ( FileList < 0 )
            goto LABEL_78;
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, (signed __int64)v44, 0) )
            (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v44 + 16LL))(v44);
        }
        FileList = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, struct _GUID *, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                     *((_QWORD *)this + 9),
                     didCOMSERVICES,
                     &TID_APPLICATION,
                     &v50,
                     1,
                     1,
                     8388612,
                     &v38);
LABEL_78:
        if ( !FileList )
        {
          if ( v38 )
          {
            FileList = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 24LL))(v38);
            if ( !FileList )
            {
              FileList = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 40LL))(v38);
              if ( !FileList )
              {
                FileList = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 128LL))(v38);
                if ( !FileList
                  && (!v33
                   || (FileList = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct _GUID *))(*(_QWORD *)v38 + 160LL))(
                                    v38,
                                    33,
                                    0,
                                    &Buf1)) == 0) )
                {
                  if ( !Data1
                    || (v28 & 4) == 0
                    || (v41 = 1,
                        (FileList = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v38 + 160LL))(
                                      v38,
                                      53,
                                      0,
                                      &v41)) == 0) )
                  {
                    if ( !v55
                      || ((*v55 - 78) & 0xFFDF) != 0
                      || (FileList = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 160LL))(v38, 17)) == 0 )
                    {
                      FileList = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 144LL))(v38);
                      if ( !FileList )
                        FileList = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 96LL))(v38);
                    }
                  }
                }
              }
            }
          }
          else
          {
            FileList = -2147024882;
          }
        }
        goto LABEL_31;
      }
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, *(signed __int64 *)&Buf1.Data1, 0) )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&Buf1.Data1 + 16LL))(*(_QWORD *)&Buf1.Data1);
    }
    v21 = memcmp_0(tidCOMSERVICES_APLICATION_EXPORT, &TID_APPLICATION, 0x10u);
    v20 = (*(unsigned int (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, struct ISimpleTableRead **))(**((_QWORD **)this + 9) + 24LL))(
            *((_QWORD *)this + 9),
            didCOMSERVICES,
            tidCOMSERVICES_APLICATION_EXPORT,
            &v61,
            1,
            1,
            v21 != 0 ? 7 : 5,
            &v37) == 0;
    goto LABEL_14;
  }
LABEL_33:
  *v59 = *((_QWORD *)this + 11);
  v24 = (_QWORD *)v60;
  v25 = v37;
  *((_QWORD *)this + 11) = 0;
  *v24 = v17;
  if ( v25 )
  {
    (*(void (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v25 + 16LL))(v25);
    v37 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v13 )
    CoTaskMemFree(v13);
  if ( v14 )
    CoTaskMemFree(v14);
  if ( !DeleteFileW(v11) && !FileList )
  {
    LastError = GetLastError();
    FileList = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)FileList;
}

```

## disassembly

```asm
0x18003caa0  push    rbp
0x18003caa2  push    rbx
0x18003caa3  push    rsi
0x18003caa4  push    rdi
0x18003caa5  push    r12
0x18003caa7  push    r13
0x18003caa9  push    r14
0x18003caab  push    r15
0x18003caad  lea     rbp, [rsp-88h]
0x18003cab5  sub     rsp, 188h
0x18003cabc  mov     rax, cs:__security_cookie
0x18003cac3  xor     rax, rsp
0x18003cac6  mov     [rbp+0C0h+var_50], rax
0x18003caca  mov     rax, [rbp+0C0h+arg_28]
0x18003cad1  xor     ebx, ebx
0x18003cad3  mov     r12, [rbp+0C0h+lpFileName]
0x18003cada  mov     rdi, rcx
0x18003cadd  mov     qword ptr [rbp+0C0h+var_100.Data1], rax
0x18003cae1  xorps   xmm0, xmm0
0x18003cae4  mov     rax, [rbp+0C0h+arg_30]
0x18003caeb  mov     esi, ebx
0x18003caed  mov     qword ptr [rbp+0C0h+var_A0.Data1], rax
0x18003caf1  lea     r14d, [rbx+20h]
0x18003caf5  mov     rax, [rbp+0C0h+arg_38]
0x18003cafc  mov     ecx, r14d; cb
0x18003caff  mov     [rbp+0C0h+var_B0], rax
0x18003cb03  mov     r15d, ebx
0x18003cb06  mov     rax, [rbp+0C0h+arg_48]
0x18003cb0d  mov     [rbp+0C0h+var_90], rax
0x18003cb11  mov     rax, [rbp+0C0h+arg_50]
0x18003cb18  mov     [rbp+0C0h+var_88], rax
0x18003cb1c  mov     [rbp+0C0h+var_130], r9
0x18003cb20  mov     qword ptr [rbp+0C0h+var_C0.Data1], r8
0x18003cb24  mov     [rbp+0C0h+var_138], rdx
0x18003cb28  mov     [rsp+1C0h+var_168], r12
0x18003cb2d  mov     [rbp+0C0h+var_118], ebx
0x18003cb30  mov     [rsp+1C0h+pv], rbx
0x18003cb35  mov     [rbp+0C0h+var_D8], rbx
0x18003cb39  mov     [rbp+0C0h+var_10C], ebx
0x18003cb3c  mov     [rbp+0C0h+var_E0], rbx
0x18003cb40  mov     [rsp+1C0h+var_148], ebx
0x18003cb44  mov     [rbp+0C0h+var_D0], rbx
0x18003cb48  mov     [rsp+1C0h+var_14C], ebx
0x18003cb4c  mov     [rsp+1C0h+var_150], ebx
0x18003cb50  mov     [rbp+0C0h+String2], rbx
0x18003cb54  movups  xmmword ptr [rbp+0C0h+var_60.Data1], xmm0
0x18003cb58  mov     [rbp+0C0h+var_110], ebx
0x18003cb5b  mov     [rsp+1C0h+var_160], rbx
0x18003cb60  mov     [rsp+1C0h+var_158], rbx
0x18003cb65  call    cs:__imp_CoTaskMemAlloc
0x18003cb6b  mov     qword ptr [rbp+0C0h+Buf1], rax
0x18003cb6f  test    rax, rax
0x18003cb72  jz      short loc_18003CB8B
0x18003cb74  lea     rcx, ??_7?$CArray@PEAUDllInfo@@AEBQEAU1@@@6B@; const CArray<DllInfo *,DllInfo * const &>::`vftable'
0x18003cb7b  mov     [rax+8], rbx
0x18003cb7f  mov     [rax], rcx
0x18003cb82  mov     [rax+14h], rbx
0x18003cb86  mov     [rax+10h], ebx
0x18003cb89  jmp     short loc_18003CB8E
0x18003cb8b  mov     rax, rbx
0x18003cb8e  mov     [rdi+58h], rax
0x18003cb92  test    rax, rax
0x18003cb95  jz      loc_18003D48E
0x18003cb9b  mov     rcx, r14; cb
0x18003cb9e  call    cs:__imp_CoTaskMemAlloc
0x18003cba4  mov     qword ptr [rbp+0C0h+Buf1], rax
0x18003cba8  mov     r14, rax
0x18003cbab  test    rax, rax
0x18003cbae  jz      loc_18003D48E
0x18003cbb4  mov     [r14+8], rbx
0x18003cbb8  lea     rax, ??_7?$CArray@PEAUCompInfo@@AEBQEAU1@@@6B@; const CArray<CompInfo *,CompInfo * const &>::`vftable'
0x18003cbbf  mov     [r14], rax
0x18003cbc2  mov     [r14+14h], rbx
0x18003cbc6  mov     [r14+10h], ebx
0x18003cbca  test    r14, r14
0x18003cbcd  jz      loc_18003D48E
0x18003cbd3  mov     r13d, [rbp+0C0h+arg_40]
0x18003cbda  lea     r9, [rbp+0C0h+Buf1]; struct _GUID *
0x18003cbde  xorps   xmm0, xmm0
0x18003cbe1  mov     r8d, r13d; unsigned int
0x18003cbe4  mov     rdx, r12; unsigned __int16 *
0x18003cbe7  mov     rcx, rdi; this
0x18003cbea  movups  [rbp+0C0h+Buf1], xmm0
0x18003cbee  call    ?ImportPartitionInfo@CAppImport@@AEAAJPEBGKPEAU_GUID@@@Z; CAppImport::ImportPartitionInfo(ushort const *,ulong,_GUID *)
0x18003cbf3  mov     ebx, eax
0x18003cbf5  test    eax, eax
0x18003cbf7  js      loc_18003CE80
0x18003cbfd  xor     ebx, ebx
0x18003cbff  lea     rdx, GUID_NULL; Buf2
0x18003cc06  lea     rcx, [rbp+0C0h+Buf1]; Buf1
0x18003cc0a  lea     r8d, [rbx+10h]; Size
0x18003cc0e  call    memcmp_0
0x18003cc13  test    eax, eax
0x18003cc15  jz      short loc_18003CC23
0x18003cc17  movups  xmm0, [rbp+0C0h+Buf1]
0x18003cc1b  lea     esi, [rbx+1]
0x18003cc1e  movdqu  xmmword ptr [rdi+60h], xmm0
0x18003cc23  mov     rcx, r12; unsigned __int16 *
0x18003cc26  mov     [rbp+0C0h+var_80], r12
0x18003cc2a  mov     [rbp+0C0h+var_78], ebx
0x18003cc2d  mov     [rbp+0C0h+var_74], 0F0000001h
0x18003cc34  mov     [rbp+0C0h+var_70], 82h
0x18003cc3b  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003cc40  mov     [rsp+1C0h+var_160], rbx
0x18003cc45  lea     eax, ds:2[rax*2]
0x18003cc4c  mov     [rbp+0C0h+var_6C], eax
0x18003cc4f  cmp     [rdi+48h], rbx
0x18003cc53  jnz     short loc_18003CC90
0x18003cc55  lea     rdx, [rbp+0C0h+Buf1]
0x18003cc59  mov     qword ptr [rbp+0C0h+Buf1], rbx
0x18003cc5d  lea     rcx, IID_ISimpleTableDispenser
0x18003cc64  call    cs:__imp_GetSimpleTableDispenser
0x18003cc6a  test    eax, eax
0x18003cc6c  js      loc_18003CCF6
0x18003cc72  mov     rcx, qword ptr [rbp+0C0h+Buf1]
0x18003cc76  xor     eax, eax
0x18003cc78  lock cmpxchg [rdi+48h], rcx
0x18003cc7e  jz      short loc_18003CC90
0x18003cc80  mov     rcx, qword ptr [rbp+0C0h+Buf1]
0x18003cc84  mov     rax, [rcx]
0x18003cc87  mov     rax, [rax+10h]
0x18003cc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc90  mov     r8d, 10h; Size
0x18003cc96  lea     rdx, TID_APPLICATION; Buf2
0x18003cc9d  lea     rcx, tidCOMSERVICES_APLICATION_EXPORT; Buf1
0x18003cca4  call    memcmp_0
0x18003cca9  mov     r10, [rdi+48h]
0x18003ccad  lea     rdx, [rsp+1C0h+var_160]
0x18003ccb2  mov     [rsp+1C0h+var_188], rdx
0x18003ccb7  lea     r9, [rbp+0C0h+var_80]
0x18003ccbb  neg     eax
0x18003ccbd  lea     r8, tidCOMSERVICES_APLICATION_EXPORT
0x18003ccc4  lea     rdx, didCOMSERVICES
0x18003cccb  mov     rax, [r10]
0x18003ccce  sbb     ecx, ecx
0x18003ccd0  and     ecx, 2
0x18003ccd3  add     ecx, 5
0x18003ccd6  mov     dword ptr [rsp+1C0h+var_190], ecx
0x18003ccda  mov     ecx, 1
0x18003ccdf  mov     rax, [rax+18h]
0x18003cce3  mov     dword ptr [rsp+1C0h+var_198], ecx
0x18003cce7  mov     [rsp+1C0h+var_1A0], rcx
0x18003ccec  mov     rcx, r10
0x18003ccef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccf4  test    eax, eax
0x18003ccf6  jz      short loc_18003CD02
0x18003ccf8  mov     ebx, 80110408h
0x18003ccfd  jmp     loc_18003CE7B
0x18003cd02  cmp     [rsp+1C0h+var_160], rbx
0x18003cd07  jnz     short loc_18003CD13
0x18003cd09  mov     ebx, 8007000Eh
0x18003cd0e  jmp     loc_18003CE7B
0x18003cd13  mov     rcx, [rsp+1C0h+var_160]
0x18003cd18  mov     rax, [rcx]
0x18003cd1b  mov     rax, [rax+18h]
0x18003cd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd24  mov     ebx, eax
0x18003cd26  test    eax, eax
0x18003cd28  jnz     loc_18003CE7B
0x18003cd2e  mov     rcx, [rsp+1C0h+var_160]
0x18003cd33  lea     rdx, [rbp+0C0h+var_118]
0x18003cd37  xor     ebx, ebx
0x18003cd39  xor     r9d, r9d
0x18003cd3c  mov     [rsp+1C0h+var_180], rbx
0x18003cd41  xor     r8d, r8d
0x18003cd44  mov     [rsp+1C0h+var_188], rdx
0x18003cd49  xor     edx, edx
0x18003cd4b  mov     rax, [rcx]
0x18003cd4e  mov     [rsp+1C0h+var_190], rbx
0x18003cd53  mov     [rsp+1C0h+var_198], rbx
0x18003cd58  mov     [rsp+1C0h+var_1A0], rbx
0x18003cd5d  mov     rax, [rax+48h]
0x18003cd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd66  mov     ebx, eax
0x18003cd68  test    eax, eax
0x18003cd6a  js      loc_18003CE7B
0x18003cd70  cmp     [rbp+0C0h+var_118], 1
0x18003cd74  ja      loc_18003D484
0x18003cd7a  mov     rcx, [rsp+1C0h+var_160]
0x18003cd7f  mov     rax, [rcx]
0x18003cd82  mov     rax, [rax+28h]
0x18003cd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd8b  cmp     eax, 80110801h
0x18003cd90  jnz     short loc_18003CDA4
0x18003cd92  neg     esi
0x18003cd94  mov     ebx, 80110408h
0x18003cd99  sbb     eax, eax
0x18003cd9b  not     eax
0x18003cd9d  and     ebx, eax
0x18003cd9f  jmp     loc_18003CE7B
0x18003cda4  mov     rcx, [rsp+1C0h+var_160]
0x18003cda9  lea     rdx, [rbp+0C0h+String2]
0x18003cdad  mov     [rsp+1C0h+var_1A0], rdx
0x18003cdb2  lea     r9, [rsp+1C0h+var_150]
0x18003cdb7  lea     r8, [rsp+1C0h+var_14C]
0x18003cdbc  xor     edx, edx
0x18003cdbe  mov     rax, [rcx]
0x18003cdc1  mov     rax, [rax+40h]
0x18003cdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cdca  mov     ebx, eax
0x18003cdcc  test    eax, eax
0x18003cdce  jnz     loc_18003CE7B
0x18003cdd4  mov     rax, [rbp+0C0h+String2]
0x18003cdd8  lea     rdx, [rbp+0C0h+String2]
0x18003cddc  mov     rcx, [rsp+1C0h+var_160]
0x18003cde1  lea     r9, [rsp+1C0h+var_150]
0x18003cde6  mov     [rsp+1C0h+var_1A0], rdx
0x18003cdeb  lea     r8, [rsp+1C0h+var_14C]
0x18003cdf0  lea     edx, [rbx+21h]
0x18003cdf3  movups  xmm0, xmmword ptr [rax]
0x18003cdf6  movdqu  xmmword ptr [rbp+0C0h+var_60.Data1], xmm0
0x18003cdfb  mov     rax, [rcx]
0x18003cdfe  mov     rax, [rax+40h]
0x18003ce02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce07  mov     ebx, eax
0x18003ce09  test    eax, eax
0x18003ce0b  jnz     short loc_18003CE7B
0x18003ce0d  mov     rax, [rbp+0C0h+String2]
0x18003ce11  mov     esi, r13d
0x18003ce14  and     esi, 1
0x18003ce17  mov     r12d, 100h
0x18003ce1d  add     esi, esi
0x18003ce1f  or      esi, 1
0x18003ce22  test    rax, rax
0x18003ce25  jz      short loc_18003CE35
0x18003ce27  cmp     dword ptr [rax], 1
0x18003ce2a  jnz     short loc_18003CE35
0x18003ce2c  mov     r12d, 300h
0x18003ce32  or      esi, 4
0x18003ce35  mov     rcx, [rsp+1C0h+var_160]
0x18003ce3a  lea     rdx, [rbp+0C0h+String2]
0x18003ce3e  mov     [rsp+1C0h+var_1A0], rdx
0x18003ce43  lea     r9, [rsp+1C0h+var_150]
0x18003ce48  lea     r8, [rsp+1C0h+var_14C]
0x18003ce4d  mov     edx, 10h
0x18003ce52  mov     rax, [rcx]
0x18003ce55  mov     rax, [rax+40h]
0x18003ce59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce5e  mov     ebx, eax
0x18003ce60  test    eax, eax
0x18003ce62  jnz     short loc_18003CE76
0x18003ce64  mov     rdx, [rbp+0C0h+String2]; String2
0x18003ce68  test    rdx, rdx
0x18003ce6b  jnz     loc_18003CF21
0x18003ce71  mov     ebx, 8000FFFFh
0x18003ce76  mov     r12, [rsp+1C0h+var_168]
0x18003ce7b  mov     rsi, [rsp+1C0h+pv]
0x18003ce80  mov     rax, [rdi+58h]
0x18003ce84  mov     rcx, [rbp+0C0h+var_90]
0x18003ce88  mov     [rcx], rax
0x18003ce8b  mov     rax, [rbp+0C0h+var_88]
0x18003ce8f  mov     rcx, [rsp+1C0h+var_160]
0x18003ce94  mov     qword ptr [rdi+58h], 0
0x18003ce9c  mov     [rax], r14
0x18003ce9f  test    rcx, rcx
0x18003cea2  jz      short loc_18003CEB9
0x18003cea4  mov     rax, [rcx]
0x18003cea7  mov     rax, [rax+10h]
0x18003ceab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ceb0  mov     [rsp+1C0h+var_160], 0
0x18003ceb9  mov     rcx, [rsp+1C0h+var_158]
0x18003cebe  test    rcx, rcx
0x18003cec1  jz      short loc_18003CED8
0x18003cec3  mov     rax, [rcx]
0x18003cec6  mov     rax, [rax+10h]
0x18003ceca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cecf  mov     [rsp+1C0h+var_158], 0
0x18003ced8  test    rsi, rsi
0x18003cedb  jz      short loc_18003CEE6
0x18003cedd  mov     rcx, rsi; pv
0x18003cee0  call    cs:__imp_CoTaskMemFree
0x18003cee6  test    r15, r15
0x18003cee9  jz      short loc_18003CEF4
0x18003ceeb  mov     rcx, r15; pv
0x18003ceee  call    cs:__imp_CoTaskMemFree
0x18003cef4  mov     rcx, r12; lpFileName
0x18003cef7  call    cs:__imp_DeleteFileW
0x18003cefd  test    eax, eax
0x18003ceff  jnz     short loc_18003CF1A
0x18003cf01  test    ebx, ebx
0x18003cf03  jnz     short loc_18003CF1A
0x18003cf05  call    cs:__imp_GetLastError
0x18003cf0b  mov     ebx, eax
0x18003cf0d  test    eax, eax
0x18003cf0f  jle     short loc_18003CF1A
0x18003cf11  movzx   ebx, ax
0x18003cf14  or      ebx, 80070000h
0x18003cf1a  mov     eax, ebx
0x18003cf1c  jmp     loc_18003D493
0x18003cf21  lea     rcx, aInproc; "Inproc"
0x18003cf28  call    cs:__imp__wcsicmp
0x18003cf2e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003cf35  mov     rcx, [rsp+1C0h+var_160]
0x18003cf3a  lea     rdx, [rbp+0C0h+var_D0]
0x18003cf3e  mov     [rsp+1C0h+var_1A0], rdx
0x18003cf43  lea     r9, [rsp+1C0h+var_150]
0x18003cf48  movdqu  xmmword ptr cs:?g_guidAppIdForQuery@@3U_GUID@@A.Data1, xmm0; _GUID g_guidAppIdForQuery ...
0x18003cf50  lea     r8, [rsp+1C0h+var_14C]
0x18003cf55  mov     edx, 11h
0x18003cf5a  mov     rax, [rcx]
  ... truncated ...
```
