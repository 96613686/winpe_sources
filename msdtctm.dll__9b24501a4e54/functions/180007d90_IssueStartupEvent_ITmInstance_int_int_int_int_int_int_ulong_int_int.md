# IssueStartupEvent(ITmInstance *,int,int,int,int,int,int,ulong,int,int)

- ea: `0x180007d90`
- end: `0x180008626`
- name: `?IssueStartupEvent@@YAXPEAUITmInstance@@HHHHHHKHH@Z`
- size: `2198`
- prototype: `void __fastcall(struct ITmInstance *, int, int, int, int, int, int, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006750`

## callees

- `0x180007d90`
- `0x18000862c`
- `0x180008a50`
- `0x18001075c`
- `0x180014b94`
- `0x180015230`
- `0x180016f3c`
- `0x1800240b0`
- `0x1800240f0`
- `0x1800240fc`
- `0x180025104`
- `0x180085f64`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000815d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000815d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007e11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007e11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000844f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000844f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800080e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800080e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800083d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800083d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000843d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000843d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007eef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007f33`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007eef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007f33`
- `OLEAUT32!__imp_SysAllocString` at `0x1800081ef`
- `OLEAUT32!__imp_SysAllocString` at `0x1800081ef`
- `OLEAUT32!__imp_SysFreeString` at `0x180008255`
- `OLEAUT32!__imp_SysFreeString` at `0x180008255`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000801d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000801d`
- `ADVAPI32!DeregisterEventSource` at `0x180008458`
- `ADVAPI32!DeregisterEventSource` at `0x180008458`
- `ADVAPI32!RegisterEventSourceW` at `0x18000838a`
- `ADVAPI32!RegisterEventSourceW` at `0x18000838a`
- `ADVAPI32!ReportEventW` at `0x180008433`
- `ADVAPI32!ReportEventW` at `0x180008433`

## string_xrefs

- `0x180007f85`: `com\complus\dtc\shared\util\scm.cpp`
- `0x18000819c`: `com\complus\dtc\shared\util\scm.cpp`
- `0x180007f8c`: `CService::InternalInit call failed`
- `0x1800081a3`: `QueryServiceConfigW call failed`

## pseudocode

```c
void __fastcall IssueStartupEvent(
        struct ITmInstance *a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        __int16 a8,
        int a9,
        int a10)
{
  unsigned __int16 near **v11; // r14
  unsigned __int16 near **v12; // rax
  unsigned __int16 near **v13; // rax
  unsigned __int16 near **v14; // rax
  unsigned __int16 near **v15; // rax
  unsigned __int16 near **v16; // rax
  unsigned __int16 near **v17; // rax
  int v18; // edi
  UINT v19; // ebx
  int v20; // r15d
  int v21; // esi
  UINT v22; // edx
  unsigned __int16 near **v23; // rax
  SC_HANDLE *v24; // rax
  unsigned __int16 *v25; // rdx
  struct CServiceControlManager *v26; // r8
  unsigned int v27; // r9d
  SC_HANDLE *v28; // r13
  int v29; // eax
  signed int v30; // r15d
  struct _QUERY_SERVICE_CONFIGW *v31; // rdi
  int i; // esi
  __int64 v33; // rbx
  struct _QUERY_SERVICE_CONFIGW *v34; // rax
  signed int LastError; // eax
  const unsigned __int16 *lpServiceStartName; // r8
  __int64 v37; // rax
  DWORD dwDataSize; // r15d
  OLECHAR *v39; // rsi
  int v40; // edi
  signed int v41; // eax
  BSTR v42; // rax
  unsigned __int16 near **v43; // rax
  int (__fastcall *v44)(struct ITmInstance *, const wchar_t *, _OWORD *, __int64, __int64 *); // rax
  int v45; // ecx
  unsigned __int16 near **v46; // rax
  const WCHAR *v47; // rdx
  HANDLE v48; // rdi
  void *v49; // rsi
  void *lpRawData; // r14
  int ServiceNameFromTmInstance; // eax
  __int64 v52; // rax
  SIZE_T v53; // r12
  void *v54; // rax
  void *v55; // r13
  __int64 v56; // rax
  bool v57; // zf
  unsigned __int16 *ppv; // [rsp+20h] [rbp-150h]
  DWORD Size; // [rsp+F0h] [rbp-80h] BYREF
  BOOL Size_4; // [rsp+F4h] [rbp-7Ch] BYREF
  LPVOID Src; // [rsp+F8h] [rbp-78h] BYREF
  int v62; // [rsp+100h] [rbp-70h] BYREF
  int v63; // [rsp+108h] [rbp-68h] BYREF
  int v64; // [rsp+110h] [rbp-60h] BYREF
  BOOL v65; // [rsp+118h] [rbp-58h] BYREF
  DWORD CurrentProcessId; // [rsp+11Ch] [rbp-54h] BYREF
  __int64 v67; // [rsp+120h] [rbp-50h] BYREF
  __int64 v68; // [rsp+128h] [rbp-48h] BYREF
  __int64 v69; // [rsp+130h] [rbp-40h] BYREF
  __int64 v70; // [rsp+138h] [rbp-38h] BYREF
  SC_HANDLE *v71; // [rsp+140h] [rbp-30h]
  LPCWSTR Strings[2]; // [rsp+150h] [rbp-20h] BYREF
  __int128 v73; // [rsp+160h] [rbp-10h]
  __int128 v74; // [rsp+170h] [rbp+0h]
  __int128 v75; // [rsp+180h] [rbp+10h]
  __int128 v76; // [rsp+190h] [rbp+20h]
  __int128 v77; // [rsp+1A0h] [rbp+30h]
  WCHAR Buffer; // [rsp+1B0h] [rbp+40h] BYREF
  __int128 v79; // [rsp+1B2h] [rbp+42h]
  __int128 v80; // [rsp+1C2h] [rbp+52h]
  __int128 v81; // [rsp+1D2h] [rbp+62h]
  __int128 v82; // [rsp+1E2h] [rbp+72h]
  __int128 v83; // [rsp+1F2h] [rbp+82h]
  __int64 v84; // [rsp+202h] [rbp+92h]
  _OWORD v85[5]; // [rsp+210h] [rbp+A0h] BYREF
  unsigned __int16 v86[256]; // [rsp+260h] [rbp+F0h] BYREF
  WCHAR psz[264]; // [rsp+460h] [rbp+2F0h] BYREF

  v64 = a2;
  v63 = a3;
  *(_OWORD *)Strings = 0;
  Buffer = 0;
  v73 = 0;
  v84 = 0;
  v74 = 0;
  v62 = a4;
  v75 = 0;
  Size_4 = 0;
  v76 = 0;
  v77 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v11 = &g_wszTrue;
  CurrentProcessId = GetCurrentProcessId();
  v12 = &g_wszTrue;
  if ( !v64 )
    v12 = &g_wszFalse;
  Strings[0] = (LPCWSTR)v12;
  v13 = &g_wszTrue;
  if ( !v63 )
    v13 = &g_wszFalse;
  Strings[1] = (LPCWSTR)v13;
  v14 = &g_wszTrue;
  if ( !v62 )
    v14 = &g_wszFalse;
  *(_QWORD *)&v73 = v14;
  v15 = &g_wszTrue;
  if ( !a5 )
    v15 = &g_wszFalse;
  *((_QWORD *)&v73 + 1) = v15;
  v16 = &g_wszTrue;
  if ( !a6 )
    v16 = &g_wszFalse;
  *(_QWORD *)&v74 = v16;
  v17 = &g_wszTrue;
  if ( !a7 )
    v17 = &g_wszFalse;
  *((_QWORD *)&v74 + 1) = v17;
  v18 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64))(*(_QWORD *)a1 + 344LL))(
          a1,
          L"SuppressDuplicateDuration",
          86400000);
  v19 = 111;
  v20 = a8 & 0x100;
  v21 = a8 & 0x200;
  if ( (a8 & 0x200) != 0 )
  {
    v22 = 111;
  }
  else
  {
    v22 = 112;
    if ( (a8 & 0x100) == 0 )
      v22 = 113;
  }
  if ( !LoadStringW(z_hModRes_Vsp1, v22, &Buffer, 45) )
    goto LABEL_105;
  v23 = &g_wszFalse;
  if ( v18 )
    v23 = &g_wszTrue;
  *(_QWORD *)&v75 = v23;
  v65 = v18 != 0;
  if ( !v21 )
    v19 = 113 - (v20 != 0);
  if ( !LoadStringW(z_hModRes_Vsp1, v19, &Buffer, 45) )
  {
LABEL_105:
    GetLastError();
    return;
  }
  *((_QWORD *)&v75 + 1) = &Buffer;
  v24 = (SC_HANDLE *)operator new(0x18u);
  v71 = v24;
  v28 = v24;
  if ( !v24 )
    return;
  *(_DWORD *)v24 = 1;
  v24[1] = 0;
  v24[2] = 0;
  v29 = CService::InternalInit((CService *)v24, v25, v26, v27, ppv);
  if ( v29 < 0 )
  {
    TraceFile(v29, "CService::InternalInit call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x13Cu);
    CService::Release((CService *)v28);
    return;
  }
  _InterlockedIncrement((volatile signed __int32 *)v28);
  CService::Release((CService *)v28);
  v30 = 0;
  Size = 64;
  v31 = 0;
  for ( i = 2; ; --i )
  {
    v33 = -1;
    if ( !i )
      break;
    if ( v31 )
      operator delete(v31);
    v34 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](Size);
    v31 = v34;
    if ( !v34 )
    {
      v30 = -2147024882;
LABEL_55:
      TraceFile(v30, "QueryServiceConfigW call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x1E8u);
      goto LABEL_43;
    }
    memset_0(v34, 0, Size);
    if ( QueryServiceConfigW(v28[2], v31, Size, &Size) )
    {
      v30 = 0;
      goto LABEL_38;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      v30 = (unsigned __int16)LastError | 0x80070000;
    else
      v30 = LastError;
    if ( LastError != 122 )
      break;
  }
  if ( v30 < 0 )
    goto LABEL_55;
LABEL_38:
  lpServiceStartName = v31->lpServiceStartName;
  if ( lpServiceStartName )
  {
    v37 = -1;
    do
      ++v37;
    while ( lpServiceStartName[v37] );
    if ( (unsigned int)(v37 + 1) <= 0x100 )
      StringCchCopyW(v86, 0x100u, lpServiceStartName);
  }
LABEL_43:
  if ( v31 )
    operator delete(v31);
  if ( v30 >= 0 )
  {
    dwDataSize = 0;
    *(_QWORD *)&v76 = v86;
    Src = 0;
    v70 = 0;
    v69 = 0;
    v68 = 0;
    v39 = 0;
    v67 = 0;
    LOWORD(Size) = 0;
    v40 = CoCreateInstance(
            &GUID_304ce942_6e39_40d8_943a_b913c40c9cd4,
            0,
            1u,
            &GUID_f7898af5_cac4_4632_a2ec_da06e5111af2,
            &Src);
    if ( v40 >= 0 )
    {
      v40 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)Src + 56LL))(Src, &v70);
      if ( v40 >= 0 )
      {
        v40 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 56LL))(v70, &v69);
        if ( v40 >= 0 )
        {
          v40 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v69 + 160LL))(v69, &v68);
          if ( v40 >= 0 )
          {
            if ( GetSystemDirectoryW(psz, 0x105u) )
            {
              v40 = StringCchPrintfW(psz, 0x105u, L"%s\\%s", psz, L"Msdtc.exe");
              if ( v40 >= 0 )
              {
                v42 = SysAllocString(psz);
                v39 = v42;
                if ( v42 )
                {
                  if ( (*(int (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v68 + 80LL))(v68, v42, &v67) < 0 )
                  {
                    Size_4 = 0;
                    v40 = 0;
                  }
                  else
                  {
                    v40 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v67 + 136LL))(v67, &Size);
                    if ( v40 >= 0 )
                      Size_4 = (_WORD)Size == 0xFFFF;
                  }
                }
                else
                {
                  v40 = -2147024882;
                }
              }
            }
            else
            {
              v41 = GetLastError();
              v40 = v41;
              if ( v41 > 0 )
                v40 = (unsigned __int16)v41 | 0x80070000;
            }
          }
        }
      }
    }
    SysFreeString(v39);
    if ( v67 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    if ( v68 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    if ( v69 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    if ( v70 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    if ( Src )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)Src + 16LL))(Src);
    if ( v40 >= 0 )
    {
      if ( Size_4 )
      {
        v43 = &g_wszTrue;
LABEL_76:
        *((_QWORD *)&v76 + 1) = v43;
        v44 = *(int (__fastcall **)(struct ITmInstance *, const wchar_t *, _OWORD *, __int64, __int64 *))(*(_QWORD *)a1 + 360LL);
        memset(v85, 0, sizeof(v85));
        if ( v44(a1, L"TransactionBridge", v85, 80, &qword_180125D60) < 0 || (v45 = 1, !LOWORD(v85[0])) )
          v45 = 0;
        a10 = v45;
        v46 = &g_wszTrue;
        v47 = L"MSDTC 2";
        if ( !v45 )
          v46 = &g_wszFalse;
        *(_QWORD *)&v77 = v46;
        if ( !a9 )
          v11 = &g_wszFalse;
        *((_QWORD *)&v77 + 1) = v11;
        if ( !g_fEventSourceMsdtcCore )
          v47 = L"MSDTC Client 2";
        v48 = RegisterEventSourceW(0, v47);
        if ( v48 )
        {
          v49 = 0;
          lpRawData = 0;
          Src = 0;
          if ( g_fEventSourceMsdtcCore )
          {
            ServiceNameFromTmInstance = GetServiceNameFromTmInstance((unsigned __int16 **)&Src);
            v49 = Src;
            if ( ServiceNameFromTmInstance >= 0 )
            {
              if ( Src )
              {
                v52 = -1;
                do
                  ++v52;
                while ( *((_WORD *)Src + v52) );
                v53 = (unsigned int)(2 * v52);
                v54 = CoTaskMemAlloc(v53);
                v55 = v54;
                if ( v54 )
                {
                  dwDataSize = v53;
                  memcpy_0(v54, v49, (unsigned int)v53);
                  lpRawData = v55;
                }
                v28 = v71;
              }
            }
          }
          if ( !ReportEventW(v48, 4u, 2u, 0x4000106Au, 0, 0xCu, dwDataSize, Strings, lpRawData) )
            GetLastError();
          CoTaskMemFree(v49);
          CoTaskMemFree(lpRawData);
          DeregisterEventSource(v48);
        }
        v56 = -1;
        do
          v57 = v86[++v56] == 0;
        while ( !v57 );
        do
          v57 = *(&Buffer + ++v33) == 0;
        while ( !v57 );
        CTrace::TraceEvent(
          (CTrace *)&g_Trace,
          1u,
          0,
          &stru_180125D68,
          0xFu,
          4,
          &CurrentProcessId,
          4,
          &v64,
          4,
          &v63,
          4,
          &v62,
          4,
          &a5,
          4,
          &a6,
          4,
          &a7,
          2 * v33 + 2,
          &Buffer,
          2 * v56 + 2,
          v86,
          4,
          &Size_4,
          4,
          &a10,
          4,
          &v65,
          0);
        goto LABEL_101;
      }
    }
    else
    {
      Size_4 = 0;
    }
    v43 = &g_wszFalse;
    goto LABEL_76;
  }
LABEL_101:
  if ( v28 )
    CService::Release((CService *)v28);
}

```

## disassembly

```asm
0x180007d90  push    rbp
0x180007d92  push    rbx
0x180007d93  push    rsi
0x180007d94  push    rdi
0x180007d95  push    r12
0x180007d97  push    r13
0x180007d99  push    r14
0x180007d9b  push    r15
0x180007d9d  lea     rbp, [rsp-518h]
0x180007da5  sub     rsp, 688h
0x180007dac  mov     rax, cs:__security_cookie
0x180007db3  xor     rax, rsp
0x180007db6  mov     [rbp+550h+var_50], rax
0x180007dbd  xorps   xmm0, xmm0
0x180007dc0  mov     [rbp+550h+var_5B0], edx
0x180007dc3  xor     eax, eax
0x180007dc5  mov     [rbp+550h+var_5B8], r8d
0x180007dc9  movups  xmmword ptr [rbp+550h+Strings], xmm0
0x180007dcd  mov     [rbp+550h+Buffer], ax
0x180007dd1  mov     r12, rcx
0x180007dd4  movups  [rbp+550h+var_560], xmm0
0x180007dd8  mov     [rbp+550h+var_4BE], rax
0x180007ddf  movups  [rbp+550h+var_550], xmm0
0x180007de3  mov     [rbp+550h+var_5C0], r9d
0x180007de7  movups  [rbp+550h+var_540], xmm0
0x180007deb  mov     dword ptr [rbp+550h+Size+4], 0
0x180007df2  movups  [rbp+550h+var_530], xmm0
0x180007df6  movups  [rbp+550h+var_520], xmm0
0x180007dfa  movups  [rbp+550h+var_50E], xmm0
0x180007dfe  movups  [rbp+550h+var_4FE], xmm0
0x180007e02  movups  [rbp+550h+var_4EE], xmm0
0x180007e06  movups  [rbp+550h+var_4DE], xmm0
0x180007e0a  movups  [rbp+550h+var_4CE], xmm0
0x180007e11  call    cs:__imp_GetCurrentProcessId
0x180007e17  cmp     [rbp+550h+var_5B0], 0
0x180007e1b  lea     r14, ?g_wszTrue@@3PAGA; ushort near * g_wszTrue
0x180007e22  mov     [rbp+550h+var_5A4], eax
0x180007e25  lea     r13, ?g_wszFalse@@3PAGA; ushort near * g_wszFalse
0x180007e2c  mov     rax, r14
0x180007e2f  lea     rdx, aSuppressduplic_0; "SuppressDuplicateDuration"
0x180007e36  cmovz   rax, r13
0x180007e3a  mov     r8d, 5265C00h
0x180007e40  cmp     [rbp+550h+var_5B8], 0
0x180007e44  mov     rcx, r12
0x180007e47  mov     [rbp+550h+Strings], rax
0x180007e4b  mov     rax, r14
0x180007e4e  cmovz   rax, r13
0x180007e52  cmp     [rbp+550h+var_5C0], 0
0x180007e56  mov     [rbp+550h+Strings+8], rax
0x180007e5a  mov     rax, r14
0x180007e5d  cmovz   rax, r13
0x180007e61  cmp     [rbp+550h+arg_20], 0
0x180007e68  mov     qword ptr [rbp+550h+var_560], rax
0x180007e6c  mov     rax, r14
0x180007e6f  cmovz   rax, r13
0x180007e73  cmp     [rbp+550h+arg_28], 0
0x180007e7a  mov     qword ptr [rbp+550h+var_560+8], rax
0x180007e7e  mov     rax, r14
0x180007e81  cmovz   rax, r13
0x180007e85  cmp     [rbp+550h+arg_30], 0
0x180007e8c  mov     qword ptr [rbp+550h+var_550], rax
0x180007e90  mov     rax, r14
0x180007e93  cmovz   rax, r13
0x180007e97  mov     qword ptr [rbp+550h+var_550+8], rax
0x180007e9b  mov     rax, [r12]
0x180007e9f  mov     rax, [rax+158h]
0x180007ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eab  mov     r15d, dword ptr [rbp+550h+arg_38]
0x180007eb2  mov     edi, eax
0x180007eb4  mov     esi, r15d
0x180007eb7  mov     ebx, 6Fh ; 'o'
0x180007ebc  and     r15d, 100h
0x180007ec3  and     esi, 200h
0x180007ec9  jz      short loc_180007ECF
0x180007ecb  mov     edx, ebx
0x180007ecd  jmp     short loc_180007EDE
0x180007ecf  mov     edx, 70h ; 'p'
0x180007ed4  test    r15d, r15d
0x180007ed7  jnz     short loc_180007EDE
0x180007ed9  mov     edx, 71h ; 'q'; uID
0x180007ede  mov     rcx, cs:?z_hModRes_Vsp1@@3PEAUHINSTANCE__@@EA; hInstance
0x180007ee5  lea     r8, [rbp+550h+Buffer]; lpBuffer
0x180007ee9  mov     r9d, 2Dh ; '-'; cchBufferMax
0x180007eef  call    cs:__imp_LoadStringW
0x180007ef5  test    eax, eax
0x180007ef7  jz      loc_1800085FD
0x180007efd  test    edi, edi
0x180007eff  mov     rax, r13
0x180007f02  cmovnz  rax, r14
0x180007f06  mov     qword ptr [rbp+550h+var_540], rax
0x180007f0a  xor     eax, eax
0x180007f0c  test    edi, edi
0x180007f0e  setnz   al
0x180007f11  mov     [rbp+550h+var_5A8], eax
0x180007f14  test    esi, esi
0x180007f16  jnz     short loc_180007F20
0x180007f18  neg     r15d
0x180007f1b  sbb     ebx, ebx
0x180007f1d  add     ebx, 71h ; 'q'
0x180007f20  mov     rcx, cs:?z_hModRes_Vsp1@@3PEAUHINSTANCE__@@EA; hInstance
0x180007f27  lea     r8, [rbp+550h+Buffer]; lpBuffer
0x180007f2b  mov     r9d, 2Dh ; '-'; cchBufferMax
0x180007f31  mov     edx, ebx; uID
0x180007f33  call    cs:__imp_LoadStringW
0x180007f39  test    eax, eax
0x180007f3b  jz      loc_1800085FD
0x180007f41  lea     rax, [rbp+550h+Buffer]
0x180007f45  mov     ecx, 18h; Size
0x180007f4a  mov     qword ptr [rbp+550h+var_540+8], rax
0x180007f4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007f53  mov     [rbp+550h+var_580], rax
0x180007f57  mov     r13, rax
0x180007f5a  test    rax, rax
0x180007f5d  jz      loc_180008603
0x180007f63  xor     ebx, ebx
0x180007f65  mov     dword ptr [rax], 1
0x180007f6b  mov     rcx, rax; this
0x180007f6e  mov     [rax+8], rbx
0x180007f72  mov     [rax+10h], rbx
0x180007f76  call    ?InternalInit@CService@@IEAAJPEAGPEAVCServiceControlManager@@K0@Z; CService::InternalInit(ushort *,CServiceControlManager *,ulong,ushort *)
0x180007f7b  test    eax, eax
0x180007f7d  jns     short loc_180007FA7
0x180007f7f  mov     r9d, 13Ch; unsigned int
0x180007f85  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x180007f8c  lea     rdx, aCserviceIntern; "CService::InternalInit call failed"
0x180007f93  mov     ecx, eax; int
0x180007f95  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180007f9a  mov     rcx, r13; this
0x180007f9d  call    ?Release@CService@@QEAAKXZ; CService::Release(void)
0x180007fa2  jmp     loc_180008603
0x180007fa7  lock inc dword ptr [r13+0]
0x180007fac  mov     rcx, r13; this
0x180007faf  call    ?Release@CService@@QEAAKXZ; CService::Release(void)
0x180007fb4  mov     r15d, ebx
0x180007fb7  mov     dword ptr [rbp+550h+Size], 40h ; '@'
0x180007fbe  mov     rdi, rbx
0x180007fc1  mov     esi, 2
0x180007fc6  nop     word ptr [rax+rax+00000000h]
0x180007fd0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180007fd7  test    esi, esi
0x180007fd9  jz      loc_18000818D
0x180007fdf  test    rdi, rdi
0x180007fe2  jz      short loc_180007FEC
0x180007fe4  mov     rcx, rdi; Block
0x180007fe7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007fec  mov     ecx, dword ptr [rbp+550h+Size]; unsigned __int64
0x180007fef  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007ff4  mov     rdi, rax
0x180007ff7  test    rax, rax
0x180007ffa  jz      loc_180008185
0x180008000  mov     r8d, dword ptr [rbp+550h+Size]; Size
0x180008004  xor     edx, edx; Val
0x180008006  mov     rcx, rax; void *
0x180008009  call    memset_0
0x18000800e  mov     r8d, dword ptr [rbp+550h+Size]; cbBufSize
0x180008012  lea     r9, [rbp+550h+Size]; pcbBytesNeeded
0x180008016  mov     rcx, [r13+10h]; hService
0x18000801a  mov     rdx, rdi; lpServiceConfig
0x18000801d  call    cs:__imp_QueryServiceConfigW
0x180008023  test    eax, eax
0x180008025  jnz     short loc_18000804E
0x180008027  call    cs:__imp_GetLastError
0x18000802d  test    eax, eax
0x18000802f  jg      short loc_180008036
0x180008031  mov     r15d, eax
0x180008034  jmp     short loc_180008041
0x180008036  movzx   r15d, ax
0x18000803a  or      r15d, 80070000h
0x180008041  cmp     eax, 7Ah ; 'z'
0x180008044  jnz     loc_18000818D
0x18000804a  dec     esi
0x18000804c  jmp     short loc_180007FD0
0x18000804e  xor     r15d, r15d
0x180008051  mov     r8, [rdi+30h]; unsigned __int16 *
0x180008055  test    r8, r8
0x180008058  jz      short loc_180008085
0x18000805a  mov     rax, rbx
0x18000805d  nop     dword ptr [rax]
0x180008060  inc     rax
0x180008063  cmp     word ptr [r8+rax*2], 0
0x180008069  jnz     short loc_180008060
0x18000806b  inc     eax
0x18000806d  cmp     eax, 100h
0x180008072  ja      short loc_180008085
0x180008074  mov     edx, 100h; unsigned __int64
0x180008079  lea     rcx, [rbp+550h+var_460]; unsigned __int16 *
0x180008080  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008085  test    rdi, rdi
0x180008088  jz      short loc_180008092
0x18000808a  mov     rcx, rdi; Block
0x18000808d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008092  test    r15d, r15d
0x180008095  js      loc_1800085D5
0x18000809b  xor     r15d, r15d
0x18000809e  lea     rax, [rbp+550h+var_460]
0x1800080a5  mov     qword ptr [rbp+550h+var_530], rax
0x1800080a9  lea     r9, _GUID_f7898af5_cac4_4632_a2ec_da06e5111af2; riid
0x1800080b0  lea     rax, [rbp+550h+Src]
0x1800080b4  mov     [rbp+550h+Src], r15
0x1800080b8  xor     edx, edx; pUnkOuter
0x1800080ba  mov     [rsp+6C0h+ppv], rax; ppv
0x1800080bf  mov     r8d, 1; dwClsContext
0x1800080c5  mov     [rbp+550h+var_588], r15
0x1800080c9  lea     rcx, _GUID_304ce942_6e39_40d8_943a_b913c40c9cd4; rclsid
0x1800080d0  mov     [rbp+550h+var_590], r15
0x1800080d4  mov     [rbp+550h+var_598], r15
0x1800080d8  mov     esi, r15d
0x1800080db  mov     [rbp+550h+var_5A0], r15
0x1800080df  mov     word ptr [rbp+550h+Size], r15w
0x1800080e4  call    cs:__imp_CoCreateInstance
0x1800080ea  mov     edi, eax
0x1800080ec  test    eax, eax
0x1800080ee  js      loc_180008252
0x1800080f4  mov     rcx, [rbp+550h+Src]
0x1800080f8  lea     rdx, [rbp+550h+var_588]
0x1800080fc  mov     rax, [rcx]
0x1800080ff  mov     rax, [rax+38h]
0x180008103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008108  mov     edi, eax
0x18000810a  test    eax, eax
0x18000810c  js      loc_180008252
0x180008112  mov     rcx, [rbp+550h+var_588]
0x180008116  lea     rdx, [rbp+550h+var_590]
0x18000811a  mov     rax, [rcx]
0x18000811d  mov     rax, [rax+38h]
0x180008121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008126  mov     edi, eax
0x180008128  test    eax, eax
0x18000812a  js      loc_180008252
0x180008130  mov     rcx, [rbp+550h+var_590]
0x180008134  lea     rdx, [rbp+550h+var_598]
0x180008138  mov     rax, [rcx]
0x18000813b  mov     rax, [rax+0A0h]
0x180008142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008147  mov     edi, eax
0x180008149  test    eax, eax
0x18000814b  js      loc_180008252
0x180008151  mov     edx, 105h; uSize
0x180008156  lea     rcx, [rbp+550h+psz]; lpBuffer
0x18000815d  call    cs:__imp_GetSystemDirectoryW
0x180008163  test    eax, eax
0x180008165  jnz     short loc_1800081B7
0x180008167  call    cs:__imp_GetLastError
0x18000816d  mov     edi, eax
0x18000816f  test    eax, eax
0x180008171  jle     loc_180008252
0x180008177  movzx   edi, ax
0x18000817a  or      edi, 80070000h
0x180008180  jmp     loc_180008252
0x180008185  mov     r15d, 8007000Eh
0x18000818b  jmp     short loc_180008196
0x18000818d  test    r15d, r15d
0x180008190  jns     loc_180008051
0x180008196  mov     r9d, 1E8h; unsigned int
0x18000819c  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x1800081a3  lea     rdx, aQueryserviceco; "QueryServiceConfigW call failed"
0x1800081aa  mov     ecx, r15d; int
0x1800081ad  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800081b2  jmp     loc_180008085
0x1800081b7  lea     rax, aMsdtcExe; "Msdtc.exe"
0x1800081be  mov     edx, 105h; unsigned __int64
0x1800081c3  lea     r9, [rbp+550h+psz]
0x1800081ca  mov     [rsp+6C0h+ppv], rax
0x1800081cf  lea     r8, aSS_1; "%s\\%s"
0x1800081d6  lea     rcx, [rbp+550h+psz]; unsigned __int16 *
0x1800081dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800081e2  mov     edi, eax
0x1800081e4  test    eax, eax
0x1800081e6  js      short loc_180008252
0x1800081e8  lea     rcx, [rbp+550h+psz]; psz
0x1800081ef  call    cs:__imp_SysAllocString
0x1800081f5  mov     rsi, rax
0x1800081f8  test    rax, rax
0x1800081fb  jnz     short loc_180008204
0x1800081fd  mov     edi, 8007000Eh
0x180008202  jmp     short loc_180008252
0x180008204  mov     rcx, [rbp+550h+var_598]
0x180008208  lea     r8, [rbp+550h+var_5A0]
0x18000820c  mov     rdx, rsi
0x18000820f  mov     rax, [rcx]
0x180008212  mov     rax, [rax+50h]
0x180008216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000821b  test    eax, eax
0x18000821d  js      short loc_18000824B
0x18000821f  mov     rcx, [rbp+550h+var_5A0]
0x180008223  lea     rdx, [rbp+550h+Size]
0x180008227  mov     rax, [rcx]
0x18000822a  mov     rax, [rax+88h]
0x180008231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008236  mov     edi, eax
0x180008238  test    eax, eax
0x18000823a  js      short loc_180008252
0x18000823c  cmp     word ptr [rbp+550h+Size], bx
0x180008240  mov     eax, r15d
0x180008243  setz    al
0x180008246  mov     dword ptr [rbp+550h+Size+4], eax
0x180008249  jmp     short loc_180008252
0x18000824b  mov     dword ptr [rbp+550h+Size+4], r15d
0x18000824f  mov     edi, r15d
0x180008252  mov     rcx, rsi; bstrString
  ... truncated ...
```
