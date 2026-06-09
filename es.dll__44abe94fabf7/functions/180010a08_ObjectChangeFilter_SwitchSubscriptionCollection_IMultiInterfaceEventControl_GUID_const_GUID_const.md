# ObjectChangeFilter::SwitchSubscriptionCollection(IMultiInterfaceEventControl *,_GUID const &,_GUID const &)

- ea: `0x180010a08`
- end: `0x180011419`
- name: `?SwitchSubscriptionCollection@ObjectChangeFilter@@QEAAJPEAUIMultiInterfaceEventControl@@AEBU_GUID@@1@Z`
- size: `2577`
- prototype: `int(ObjectChangeFilter *__hidden this, struct IMultiInterfaceEventControl *, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180010510`

## callees

- `0x180003d54`
- `0x180008938`
- `0x18000c910`
- `0x180010a08`
- `0x180012f50`
- `0x18001c8f0`
- `0x180035730`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010ae9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010ae9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800110c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800110c4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010a79`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010a89`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010a99`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010cb1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010dbc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010a79`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010a89`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010a99`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010cb1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010dbc`

## string_xrefs

- `0x180010b70`: `(((EventClassID=`
- `0x180010d4e`: `)) | (EventClassID=null & PublisherID=null & InterfaceID=(`
- `0x18001116c`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800111fb`: `com\complus\src\events\tier2\notify.cpp`
- `0x180011221`: `com\complus\src\events\tier2\notify.cpp`
- `0x180011243`: `com\complus\src\events\tier2\notify.cpp`
- `0x180011292`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800112b1`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800112d3`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800112f0`: `com\complus\src\events\tier2\notify.cpp`
- `0x18001130f`: `com\complus\src\events\tier2\notify.cpp`
- `0x18001132e`: `com\complus\src\events\tier2\notify.cpp`
- `0x180011355`: `com\complus\src\events\tier2\notify.cpp`
- `0x180011372`: `com\complus\src\events\tier2\notify.cpp`
- `0x180011391`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800113b8`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800113e0`: `com\complus\src\events\tier2\notify.cpp`
- `0x180011402`: `com\complus\src\events\tier2\notify.cpp`

## pseudocode

```c
__int64 __fastcall ObjectChangeFilter::SwitchSubscriptionCollection(
        ObjectChangeFilter *this,
        struct IMultiInterfaceEventControl *a2,
        const struct _GUID *a3,
        const struct _GUID *a4)
{
  __int64 v4; // rax
  __int64 v8; // rax
  __int64 v9; // r13
  __int64 v10; // rax
  __int64 v11; // rdi
  unsigned __int64 v12; // rsi
  char *v13; // r14
  unsigned __int16 *v14; // r14
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rcx
  unsigned __int16 *v17; // rax
  int v18; // r9d
  unsigned __int64 v19; // r8
  __int64 v20; // rax
  const wchar_t *v21; // rcx
  unsigned __int16 *v22; // r10
  unsigned __int64 v23; // rdx
  unsigned __int16 *v24; // rcx
  int v25; // eax
  unsigned __int64 v26; // rcx
  unsigned __int16 *v27; // rax
  int v28; // r9d
  unsigned __int64 v29; // rax
  const wchar_t *v30; // r9
  unsigned __int16 *v31; // r8
  __int64 v32; // rcx
  unsigned __int64 v33; // rdx
  unsigned __int16 *v34; // rcx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  unsigned __int64 v38; // rcx
  unsigned __int16 *v39; // rax
  int v40; // r9d
  unsigned __int64 v41; // rax
  const wchar_t *v42; // r9
  unsigned __int16 *v43; // r8
  __int64 v44; // rcx
  unsigned __int64 v45; // rdx
  unsigned __int16 *v46; // rcx
  int v47; // eax
  int v48; // eax
  unsigned __int64 v49; // rcx
  unsigned __int16 *v50; // rax
  int v51; // r9d
  unsigned __int64 v52; // rax
  const wchar_t *v53; // r9
  unsigned __int16 *v54; // r8
  __int64 v55; // rcx
  unsigned __int64 v56; // rdx
  unsigned __int16 *v57; // rcx
  unsigned __int64 v58; // rcx
  unsigned __int16 *v59; // rax
  int v60; // r9d
  unsigned __int64 v61; // rax
  const wchar_t *v62; // r9
  unsigned __int16 *v63; // r8
  __int64 v64; // rcx
  unsigned __int64 v65; // rdx
  unsigned __int16 *v66; // rcx
  int v67; // eax
  unsigned __int64 v68; // rcx
  unsigned __int16 *v69; // rax
  int v70; // r9d
  unsigned __int64 v71; // rax
  const wchar_t *v72; // r8
  __int64 v73; // rcx
  unsigned __int16 *v74; // rdx
  unsigned __int64 i; // rdi
  unsigned __int16 *v76; // rcx
  int v77; // eax
  char *v78; // rsi
  __int64 v79; // rcx
  int v80; // eax
  int v81; // edi
  const struct _GUID *v82; // rax
  struct _GUID v83; // xmm1
  __int64 result; // rax
  __int64 v85; // rax
  int j; // ecx
  __int64 v87; // rax
  int v88; // eax
  __int64 v89; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h]
  struct IMultiInterfaceEventControl *v91; // [rsp+50h] [rbp-B0h]
  const struct _GUID *v92; // [rsp+58h] [rbp-A8h]
  OLECHAR v93[40]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR v94[40]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR v95[40]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR sz[40]; // [rsp+150h] [rbp+50h] BYREF

  v4 = *((_QWORD *)this + 12);
  v92 = a4;
  v91 = a2;
  v8 = v4 - *(_QWORD *)&a3->Data1;
  if ( !v8 )
    v8 = *((_QWORD *)this + 13) - *(_QWORD *)a3->Data4;
  if ( v8 )
    goto LABEL_4;
  v85 = *((_QWORD *)this + 14) - *(_QWORD *)&a4->Data1;
  if ( !v85 )
    v85 = *((_QWORD *)this + 15) - *(_QWORD *)a4->Data4;
  if ( v85 )
  {
LABEL_4:
    StringFromGUID2((const GUID *const)this + 3, sz, 40);
    StringFromGUID2(a3, v95, 40);
    StringFromGUID2(a4, v94, 40);
    v9 = 0;
    while ( 1 )
    {
      v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
        v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
      if ( !v10 )
        goto LABEL_8;
      v87 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_DefaultAppPartition.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_DefaultAppPartition.Data1 )
        v87 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_DefaultAppPartition.Data4;
      v11 = 270;
      if ( !v87 )
LABEL_8:
        v11 = 0;
      v12 = v11 + 2 * ((int)safe_lstrlenW(off_1800472F0[v9]) + 253LL);
      pv = CoTaskMemAlloc(v12 + 4);
      v13 = (char *)pv;
      if ( !pv )
        InternalError(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x560u, 0xC0001204, 0x11u);
      v14 = (unsigned __int16 *)(v13 + 4);
      *v14 = 0;
      if ( v11 )
      {
        v88 = StringCbPrintfW(v14, v12, L"((SubscriberPartitionID=%s) | (SubscriberPartitionID=%s)) & ", v95, v94);
        if ( v88 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x567u, 0x12u, v88);
      }
      v15 = v12 >> 1;
      if ( (v12 >> 1) - 1 > 0x7FFFFFFE )
        break;
      v16 = v12 >> 1;
      v17 = v14;
      do
      {
        if ( !*v17 )
          break;
        ++v17;
        --v16;
      }
      while ( v16 );
      v18 = v16 == 0 ? 0x80070057 : 0;
      if ( v16 )
        v19 = v15 - v16;
      else
        v19 = 0;
      if ( !v16 )
        goto LABEL_143;
      v20 = 2147483646;
      v21 = L"(((EventClassID=";
      v22 = &v14[v19];
      v23 = v15 - v19;
      if ( v15 != v19 )
      {
        do
        {
          if ( !v20 )
            break;
          if ( !*v21 )
            break;
          *v22++ = *v21++;
          --v20;
          --v23;
        }
        while ( v23 );
      }
      v24 = v22 - 1;
      v18 = v23 == 0 ? 0x8007007A : 0;
      if ( v23 )
        v24 = v22;
      *v24 = 0;
      if ( !v23 )
        goto LABEL_143;
LABEL_26:
      v25 = StringCbCatW(v14, v12, sz);
      if ( v25 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x56Du, 0x12u, v25);
      if ( !v15 || v15 > 0x7FFFFFFF )
      {
        v28 = -2147024809;
LABEL_145:
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x57Cu, 0x12u, v28);
        goto LABEL_43;
      }
      v26 = v12 >> 1;
      v27 = v14;
      do
      {
        if ( !*v27 )
          break;
        ++v27;
        --v26;
      }
      while ( v26 );
      v28 = v26 == 0 ? 0x80070057 : 0;
      if ( v26 )
        v29 = v15 - v26;
      else
        v29 = 0;
      if ( !v26 )
        goto LABEL_145;
      v30 = L") & InterfaceID=(null";
      v31 = &v14[v29];
      v32 = 2147483646;
      v33 = v15 - v29;
      if ( v15 != v29 )
      {
        do
        {
          if ( !v32 )
            break;
          if ( !*v30 )
            break;
          *v31++ = *v30++;
          --v32;
          --v33;
        }
        while ( v33 );
      }
      v34 = v31 - 1;
      v28 = v33 == 0 ? 0x8007007A : 0;
      if ( v33 )
        v34 = v31;
      *v34 = 0;
      if ( !v33 )
        goto LABEL_145;
LABEL_43:
      v35 = StringFromGUID2((const GUID *const)this + 4, v93, 40);
      if ( v35 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x581u, 0x12u, v35);
      v36 = StringCbCatW(v14, v12, L" | ");
      if ( v36 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x584u, 0x12u, v36);
      v37 = StringCbCatW(v14, v12, v93);
      if ( v37 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x587u, 0x12u, v37);
      if ( !v15 || v15 > 0x7FFFFFFF )
      {
        v40 = -2147024809;
LABEL_147:
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x58Cu, 0x12u, v40);
        goto LABEL_64;
      }
      v38 = v12 >> 1;
      v39 = v14;
      do
      {
        if ( !*v39 )
          break;
        ++v39;
        --v38;
      }
      while ( v38 );
      v40 = v38 == 0 ? 0x80070057 : 0;
      if ( v38 )
        v41 = v15 - v38;
      else
        v41 = 0;
      if ( !v38 )
        goto LABEL_147;
      v42 = L")) | (EventClassID=null & PublisherID=null & InterfaceID=(";
      v43 = &v14[v41];
      v44 = 2147483646;
      v45 = v15 - v41;
      if ( v15 != v41 )
      {
        do
        {
          if ( !v44 )
            break;
          if ( !*v42 )
            break;
          *v43++ = *v42++;
          --v44;
          --v45;
        }
        while ( v45 );
      }
      v46 = v43 - 1;
      v40 = v45 == 0 ? 0x8007007A : 0;
      if ( v45 )
        v46 = v43;
      *v46 = 0;
      if ( !v45 )
        goto LABEL_147;
LABEL_64:
      v47 = StringFromGUID2((const GUID *const)this + 4, v93, 39);
      if ( v47 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x590u, 0x12u, v47);
      v48 = StringCbCatW(v14, v12, v93);
      if ( v48 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x598u, 0x12u, v48);
      if ( !v15 || v15 > 0x7FFFFFFF )
      {
        v51 = -2147024809;
LABEL_149:
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x59Cu, 0x12u, v51);
        goto LABEL_83;
      }
      v49 = v12 >> 1;
      v50 = v14;
      do
      {
        if ( !*v50 )
          break;
        ++v50;
        --v49;
      }
      while ( v49 );
      v51 = v49 == 0 ? 0x80070057 : 0;
      if ( v49 )
        v52 = v15 - v49;
      else
        v52 = 0;
      if ( !v49 )
        goto LABEL_149;
      v53 = L")))";
      v54 = &v14[v52];
      v55 = 2147483646;
      v56 = v15 - v52;
      if ( v15 != v52 )
      {
        do
        {
          if ( !v55 )
            break;
          if ( !*v53 )
            break;
          *v54++ = *v53++;
          --v55;
          --v56;
        }
        while ( v56 );
      }
      v57 = v54 - 1;
      v51 = v56 == 0 ? 0x8007007A : 0;
      if ( v56 )
        v57 = v54;
      *v57 = 0;
      if ( !v56 )
        goto LABEL_149;
LABEL_83:
      if ( !v15 || v15 > 0x7FFFFFFF )
      {
        v60 = -2147024809;
LABEL_151:
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x5A0u, 0x12u, v60);
        goto LABEL_98;
      }
      v58 = v12 >> 1;
      v59 = v14;
      do
      {
        if ( !*v59 )
          break;
        ++v59;
        --v58;
      }
      while ( v58 );
      v60 = v58 == 0 ? 0x80070057 : 0;
      if ( v58 )
        v61 = v15 - v58;
      else
        v61 = 0;
      if ( !v58 )
        goto LABEL_151;
      v62 = L" & MethodName=(null | '";
      v63 = &v14[v61];
      v64 = 2147483646;
      v65 = v15 - v61;
      if ( v15 != v61 )
      {
        do
        {
          if ( !v64 )
            break;
          if ( !*v62 )
            break;
          *v63++ = *v62++;
          --v64;
          --v65;
        }
        while ( v65 );
      }
      v66 = v63 - 1;
      v60 = v65 == 0 ? 0x8007007A : 0;
      if ( v65 )
        v66 = v63;
      *v66 = 0;
      if ( !v65 )
        goto LABEL_151;
LABEL_98:
      v67 = StringCbCatW(v14, v12, off_1800472F0[v9]);
      if ( v67 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x5A3u, 0x12u, v67);
      if ( !v15 || v15 > 0x7FFFFFFF )
      {
        v70 = -2147024809;
LABEL_153:
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x5A6u, 0x12u, v70);
        goto LABEL_115;
      }
      v68 = v12 >> 1;
      v69 = v14;
      do
      {
        if ( !*v69 )
          break;
        ++v69;
        --v68;
      }
      while ( v68 );
      v70 = v68 == 0 ? 0x80070057 : 0;
      if ( v68 )
        v71 = v15 - v68;
      else
        v71 = 0;
      if ( !v68 )
        goto LABEL_153;
      v72 = L"')";
      v73 = 2147483646;
      v74 = &v14[v71];
      for ( i = v15 - v71; i; --i )
      {
        if ( !v73 )
          break;
        if ( !*v72 )
          break;
        *v74++ = *v72++;
        --v73;
      }
      v76 = v74 - 1;
      v70 = i == 0 ? 0x8007007A : 0;
      if ( i )
        v76 = v74;
      *v76 = 0;
      if ( !i )
        goto LABEL_153;
LABEL_115:
      v77 = safe_lstrlenW(v14);
      *(_DWORD *)pv = v77;
      v89 = 0;
      v78 = (char *)this + 8 * v9;
      v79 = *((_QWORD *)v78 + 10);
      if ( v79 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
        *((_QWORD *)v78 + 10) = 0;
      }
      v80 = ((__int64 (__fastcall *)(struct IMultiInterfaceEventControl *, char *, wchar_t *, unsigned __int16 *, _QWORD, __int64 *))v91->lpVtbl->GetSubscriptions)(
              v91,
              (char *)this + 64,
              off_1800472F0[v9],
              v14,
              0,
              &v89);
      v81 = v80;
      if ( v80 < 0 )
      {
        LogMessage_HR(0x24u, 0x80001109, v80, 1u, v14);
LABEL_129:
        InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x5C2u, 0x14u, v81);
        goto LABEL_119;
      }
      v81 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v89 + 72LL))(v89, v78 + 80);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      if ( v81 < 0 )
        goto LABEL_129;
LABEL_119:
      CoTaskMemFree(pv);
      if ( ++v9 == 2 )
      {
        v82 = v92;
        *((struct _GUID *)this + 6) = *a3;
        v83 = *v82;
        result = (unsigned int)v81;
        *((struct _GUID *)this + 7) = v83;
        return result;
      }
    }
    v18 = -2147024809;
LABEL_143:
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x56Au, 0x12u, v18);
    goto LABEL_26;
  }
  for ( j = 0; j < 2; ++j )
  {
    if ( !*((_QWORD *)this + (unsigned int)j + 10) )
      goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x180010a08  push    rbp
0x180010a0a  push    rbx
0x180010a0b  push    rsi
0x180010a0c  push    rdi
0x180010a0d  push    r12
0x180010a0f  push    r13
0x180010a11  push    r14
0x180010a13  push    r15
0x180010a15  lea     rbp, [rsp-0B8h]
0x180010a1d  sub     rsp, 1B8h
0x180010a24  mov     rax, cs:__security_cookie
0x180010a2b  xor     rax, rsp
0x180010a2e  mov     [rbp+0F0h+var_50], rax
0x180010a35  mov     rax, [rcx+60h]
0x180010a39  mov     rdi, r9
0x180010a3c  mov     r12, r8
0x180010a3f  mov     [rsp+1F0h+var_198], r9
0x180010a44  mov     r15, rcx
0x180010a47  mov     [rsp+1F0h+var_1A0], rdx
0x180010a4c  sub     rax, [r8]
0x180010a4f  jnz     short loc_180010A59
0x180010a51  mov     rax, [rcx+68h]
0x180010a55  sub     rax, [r8+8]
0x180010a59  xor     esi, esi
0x180010a5b  test    rax, rax
0x180010a5e  jz      loc_1800110F4
0x180010a64  mov     r14d, 28h ; '('
0x180010a6a  lea     rcx, [r15+30h]; rguid
0x180010a6e  mov     r8d, r14d; cchMax
0x180010a71  lea     rdx, [rbp+0F0h+sz]; lpsz
0x180010a75  lea     rbx, [r15+40h]
0x180010a79  call    cs:__imp_StringFromGUID2
0x180010a7f  mov     r8d, r14d; cchMax
0x180010a82  lea     rdx, [rbp+0F0h+var_F0]; lpsz
0x180010a86  mov     rcx, r12; rguid
0x180010a89  call    cs:__imp_StringFromGUID2
0x180010a8f  mov     r8d, r14d; cchMax
0x180010a92  lea     rdx, [rbp+0F0h+var_140]; lpsz
0x180010a96  mov     rcx, rdi; rguid
0x180010a99  call    cs:__imp_StringFromGUID2
0x180010a9f  mov     r13, rsi
0x180010aa2  mov     rax, [r12]
0x180010aa6  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180010aad  jnz     short loc_180010ABB
0x180010aaf  mov     rax, [r12+8]
0x180010ab4  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180010abb  test    rax, rax
0x180010abe  jnz     loc_180011185
0x180010ac4  mov     rdi, rsi
0x180010ac7  lea     rax, off_1800472F0; "ChangedEventClass"
0x180010ace  mov     rcx, [rax+r13*8]; unsigned __int16 *
0x180010ad2  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180010ad7  movsxd  rcx, eax
0x180010ada  add     rcx, 0FDh
0x180010ae1  lea     rsi, [rdi+rcx*2]
0x180010ae5  lea     rcx, [rsi+4]; cb
0x180010ae9  call    cs:__imp_CoTaskMemAlloc
0x180010aef  xor     r11d, r11d
0x180010af2  mov     [rsp+1F0h+pv], rax
0x180010af7  mov     r14, rax
0x180010afa  test    rax, rax
0x180010afd  jz      loc_1800111F6
0x180010b03  add     r14, 4
0x180010b07  mov     [r14], r11w
0x180010b0b  test    rdi, rdi
0x180010b0e  jnz     loc_18001125C
0x180010b14  mov     rdi, rsi
0x180010b17  mov     edx, 7FFFFFFEh
0x180010b1c  shr     rdi, 1
0x180010b1f  lea     rax, [rdi-1]
0x180010b23  cmp     rax, rdx
0x180010b26  ja      loc_1800112A6
0x180010b2c  mov     rcx, rdi
0x180010b2f  mov     rax, r14
0x180010b32  mov     r8, rdi
0x180010b35  cmp     [rax], r11w
0x180010b39  jz      short loc_180010B45
0x180010b3b  add     rax, 2
0x180010b3f  sub     rcx, 1
0x180010b43  jnz     short loc_180010B35
0x180010b45  mov     rax, rcx
0x180010b48  neg     rax
0x180010b4b  sbb     r9d, r9d
0x180010b4e  not     r9d
0x180010b51  and     r9d, 80070057h
0x180010b58  test    rcx, rcx
0x180010b5b  jz      loc_1800111C6
0x180010b61  sub     r8, rcx
0x180010b64  test    rcx, rcx
0x180010b67  jz      loc_1800112AC
0x180010b6d  mov     rax, rdx
0x180010b70  lea     rcx, aEventclassid_0; "(((EventClassID="
0x180010b77  mov     rdx, rdi
0x180010b7a  lea     r10, [r14+r8*2]
0x180010b7e  sub     rdx, r8
0x180010b81  jz      short loc_180010BA7
0x180010b83  test    rax, rax
0x180010b86  jz      short loc_180010BA7
0x180010b88  movzx   r8d, word ptr [rcx]
0x180010b8c  test    r8w, r8w
0x180010b90  jz      short loc_180010BA7
0x180010b92  mov     [r10], r8w
0x180010b96  add     rcx, 2
0x180010b9a  add     r10, 2
0x180010b9e  dec     rax
0x180010ba1  sub     rdx, 1
0x180010ba5  jnz     short loc_180010B83
0x180010ba7  mov     rax, rdx
0x180010baa  lea     rcx, [r10-2]
0x180010bae  neg     rax
0x180010bb1  sbb     r9d, r9d
0x180010bb4  not     r9d
0x180010bb7  and     r9d, 8007007Ah
0x180010bbe  test    rdx, rdx
0x180010bc1  cmovnz  rcx, r10
0x180010bc5  mov     [rcx], r11w
0x180010bc9  jz      loc_1800112AC
0x180010bcf  lea     r8, [rbp+0F0h+sz]; unsigned __int16 *
0x180010bd3  mov     rdx, rsi; unsigned __int64
0x180010bd6  mov     rcx, r14; unsigned __int16 *
0x180010bd9  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180010bde  xor     r10d, r10d
0x180010be1  test    eax, eax
0x180010be3  js      loc_18001121B
0x180010be9  test    rdi, rdi
0x180010bec  jz      loc_1800112C8
0x180010bf2  cmp     rdi, 7FFFFFFFh
0x180010bf9  ja      loc_1800112C8
0x180010bff  mov     rcx, rdi
0x180010c02  mov     rax, r14
0x180010c05  cmp     [rax], r10w
0x180010c09  jz      short loc_180010C15
0x180010c0b  add     rax, 2
0x180010c0f  sub     rcx, 1
0x180010c13  jnz     short loc_180010C05
0x180010c15  mov     rax, rcx
0x180010c18  neg     rax
0x180010c1b  sbb     r9d, r9d
0x180010c1e  not     r9d
0x180010c21  and     r9d, 80070057h
0x180010c28  test    rcx, rcx
0x180010c2b  jz      loc_1800111CE
0x180010c31  mov     rax, rdi
0x180010c34  sub     rax, rcx
0x180010c37  test    rcx, rcx
0x180010c3a  jz      loc_1800112CE
0x180010c40  mov     rdx, rdi
0x180010c43  lea     r9, aInterfaceidNul; ") & InterfaceID=(null"
0x180010c4a  lea     r8, [r14+rax*2]
0x180010c4e  mov     ecx, 7FFFFFFEh
0x180010c53  sub     rdx, rax
0x180010c56  jz      short loc_180010C7B
0x180010c58  test    rcx, rcx
0x180010c5b  jz      short loc_180010C7B
0x180010c5d  movzx   eax, word ptr [r9]
0x180010c61  test    ax, ax
0x180010c64  jz      short loc_180010C7B
0x180010c66  mov     [r8], ax
0x180010c6a  add     r9, 2
0x180010c6e  add     r8, 2
0x180010c72  dec     rcx
0x180010c75  sub     rdx, 1
0x180010c79  jnz     short loc_180010C58
0x180010c7b  mov     rax, rdx
0x180010c7e  lea     rcx, [r8-2]
0x180010c82  neg     rax
0x180010c85  sbb     r9d, r9d
0x180010c88  not     r9d
0x180010c8b  and     r9d, 8007007Ah
0x180010c92  test    rdx, rdx
0x180010c95  cmovnz  rcx, r8
0x180010c99  mov     [rcx], r10w
0x180010c9d  jz      loc_1800112CE
0x180010ca3  mov     r8d, 28h ; '('; cchMax
0x180010ca9  lea     rdx, [rsp+1F0h+var_190]; lpsz
0x180010cae  mov     rcx, rbx; rguid
0x180010cb1  call    cs:__imp_StringFromGUID2
0x180010cb7  test    eax, eax
0x180010cb9  js      loc_1800112EA
0x180010cbf  lea     r8, asc_180052A78; " | "
0x180010cc6  mov     rdx, rsi; unsigned __int64
0x180010cc9  mov     rcx, r14; unsigned __int16 *
0x180010ccc  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180010cd1  test    eax, eax
0x180010cd3  js      loc_180011309
0x180010cd9  lea     r8, [rsp+1F0h+var_190]; unsigned __int16 *
0x180010cde  mov     rdx, rsi; unsigned __int64
0x180010ce1  mov     rcx, r14; unsigned __int16 *
0x180010ce4  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180010ce9  xor     r10d, r10d
0x180010cec  test    eax, eax
0x180010cee  js      loc_180011328
0x180010cf4  test    rdi, rdi
0x180010cf7  jz      loc_18001134A
0x180010cfd  cmp     rdi, 7FFFFFFFh
0x180010d04  ja      loc_18001134A
0x180010d0a  mov     rcx, rdi
0x180010d0d  mov     rax, r14
0x180010d10  cmp     [rax], r10w
0x180010d14  jz      short loc_180010D20
0x180010d16  add     rax, 2
0x180010d1a  sub     rcx, 1
0x180010d1e  jnz     short loc_180010D10
0x180010d20  mov     rax, rcx
0x180010d23  neg     rax
0x180010d26  sbb     r9d, r9d
0x180010d29  not     r9d
0x180010d2c  and     r9d, 80070057h
0x180010d33  test    rcx, rcx
0x180010d36  jz      loc_1800111D6
0x180010d3c  mov     rax, rdi
0x180010d3f  sub     rax, rcx
0x180010d42  test    rcx, rcx
0x180010d45  jz      loc_180011350
0x180010d4b  mov     rdx, rdi
0x180010d4e  lea     r9, aEventclassidNu; ")) | (EventClassID=null & PublisherID=n"...
0x180010d55  lea     r8, [r14+rax*2]
0x180010d59  mov     ecx, 7FFFFFFEh
0x180010d5e  sub     rdx, rax
0x180010d61  jz      short loc_180010D86
0x180010d63  test    rcx, rcx
0x180010d66  jz      short loc_180010D86
0x180010d68  movzx   eax, word ptr [r9]
0x180010d6c  test    ax, ax
0x180010d6f  jz      short loc_180010D86
0x180010d71  mov     [r8], ax
0x180010d75  add     r9, 2
0x180010d79  add     r8, 2
0x180010d7d  dec     rcx
0x180010d80  sub     rdx, 1
0x180010d84  jnz     short loc_180010D63
0x180010d86  mov     rax, rdx
0x180010d89  lea     rcx, [r8-2]
0x180010d8d  neg     rax
0x180010d90  sbb     r9d, r9d
0x180010d93  not     r9d
0x180010d96  and     r9d, 8007007Ah
0x180010d9d  test    rdx, rdx
0x180010da0  cmovnz  rcx, r8
0x180010da4  mov     [rcx], r10w
0x180010da8  jz      loc_180011350
0x180010dae  mov     r8d, 27h ; '''; cchMax
0x180010db4  lea     rdx, [rsp+1F0h+var_190]; lpsz
0x180010db9  mov     rcx, rbx; rguid
0x180010dbc  call    cs:__imp_StringFromGUID2
0x180010dc2  test    eax, eax
0x180010dc4  js      loc_18001136C
0x180010dca  lea     r8, [rsp+1F0h+var_190]; unsigned __int16 *
0x180010dcf  mov     rdx, rsi; unsigned __int64
0x180010dd2  mov     rcx, r14; unsigned __int16 *
0x180010dd5  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180010dda  xor     r10d, r10d
0x180010ddd  test    eax, eax
0x180010ddf  js      loc_18001138B
0x180010de5  test    rdi, rdi
0x180010de8  jz      loc_1800113AD
0x180010dee  cmp     rdi, 7FFFFFFFh
0x180010df5  ja      loc_1800113AD
0x180010dfb  mov     rcx, rdi
0x180010dfe  mov     rax, r14
0x180010e01  cmp     [rax], r10w
0x180010e05  jz      short loc_180010E11
0x180010e07  add     rax, 2
0x180010e0b  sub     rcx, 1
0x180010e0f  jnz     short loc_180010E01
0x180010e11  mov     rax, rcx
0x180010e14  mov     r11d, 80070057h
0x180010e1a  neg     rax
0x180010e1d  sbb     r9d, r9d
0x180010e20  not     r9d
0x180010e23  and     r9d, r11d
0x180010e26  test    rcx, rcx
0x180010e29  jz      loc_1800111DE
0x180010e2f  mov     rax, rdi
0x180010e32  sub     rax, rcx
0x180010e35  test    rcx, rcx
0x180010e38  jz      loc_1800113B3
0x180010e3e  mov     rdx, rdi
0x180010e41  lea     r9, asc_180052A38; ")))"
0x180010e48  lea     r8, [r14+rax*2]
0x180010e4c  mov     ecx, 7FFFFFFEh
0x180010e51  sub     rdx, rax
0x180010e54  jz      short loc_180010E79
0x180010e56  test    rcx, rcx
0x180010e59  jz      short loc_180010E79
0x180010e5b  movzx   eax, word ptr [r9]
0x180010e5f  test    ax, ax
0x180010e62  jz      short loc_180010E79
0x180010e64  mov     [r8], ax
0x180010e68  add     r9, 2
0x180010e6c  add     r8, 2
0x180010e70  dec     rcx
0x180010e73  sub     rdx, 1
0x180010e77  jnz     short loc_180010E56
0x180010e79  mov     rax, rdx
0x180010e7c  lea     rcx, [r8-2]
0x180010e80  neg     rax
0x180010e83  sbb     r9d, r9d
0x180010e86  not     r9d
0x180010e89  and     r9d, 8007007Ah
  ... truncated ...
```
