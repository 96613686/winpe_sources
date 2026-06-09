# WriteProperty(ID2D1Properties *,uint,IXmlWriter *)

- ea: `0x18020a550`
- end: `0x18020b194`
- name: `?WriteProperty@@YAJPEAUID2D1Properties@@IPEAUIXmlWriter@@@Z`
- size: `3140`
- prototype: `__int64 __fastcall(struct ID2D1Properties *, unsigned int, struct IXmlWriter *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18020a15c`

## callees

- `0x18001fd58`
- `0x1800389c0`
- `0x1801b0294`
- `0x18020a550`
- `0x18020b19c`
- `0x18025b100`
- `0x18025bb98`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18020ae47`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18020ae47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18020ae70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18020ae70`

## pseudocode

```c
__int64 __fastcall WriteProperty(struct ID2D1Properties *a1, __int64 a2, struct IXmlWriter *a3)
{
  unsigned int v4; // edi
  int v6; // esi
  __int64 v7; // rax
  int v8; // eax
  HRESULT v9; // ebx
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  const unsigned __int16 *v15; // r8
  bool v16; // sf
  __int64 (__fastcall *v18)(struct ID2D1Properties *, _QWORD, _QWORD, LPOLESTR *, int); // rax
  __int64 v19; // rax
  __int64 (__fastcall *v20)(struct ID2D1Properties *, _QWORD, _QWORD, IID *, int); // rax
  __int64 v21; // rax
  __int64 v22; // rax
  char v23; // di
  unsigned int v24; // esi
  unsigned int j; // ebx
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  unsigned int v29; // eax
  unsigned __int64 v30; // rcx
  unsigned int v31; // esi
  unsigned int i; // ebx
  const unsigned __int16 *v33; // r8
  unsigned __int64 v34; // rdx
  unsigned __int16 *v35; // rcx
  int v36; // eax
  unsigned int v37; // edi
  float v38; // [rsp+C8h] [rbp-80h] BYREF
  double v39; // [rsp+D0h] [rbp-78h] BYREF
  double v40[2]; // [rsp+D8h] [rbp-70h] BYREF
  LPOLESTR lpsz[2]; // [rsp+E8h] [rbp-60h] BYREF
  __int128 v42; // [rsp+F8h] [rbp-50h]
  __int128 v43; // [rsp+108h] [rbp-40h]
  int v44; // [rsp+118h] [rbp-30h]
  int v45; // [rsp+11Ch] [rbp-2Ch]
  int v46; // [rsp+120h] [rbp-28h]
  int v47; // [rsp+124h] [rbp-24h]
  IID rclsid; // [rsp+128h] [rbp-20h] BYREF
  int v49; // [rsp+138h] [rbp-10h] BYREF
  float v50; // [rsp+13Ch] [rbp-Ch]
  float v51; // [rsp+140h] [rbp-8h]
  float v52; // [rsp+144h] [rbp-4h]
  float v53; // [rsp+148h] [rbp+0h]
  int v54; // [rsp+14Ch] [rbp+4h]
  int v55; // [rsp+150h] [rbp+8h]
  int v56; // [rsp+154h] [rbp+Ch]
  int v57; // [rsp+158h] [rbp+10h]
  int v58; // [rsp+15Ch] [rbp+14h]
  int v59; // [rsp+160h] [rbp+18h]
  int v60; // [rsp+164h] [rbp+1Ch]
  int v61; // [rsp+168h] [rbp+20h]
  int v62; // [rsp+16Ch] [rbp+24h]
  int v63; // [rsp+170h] [rbp+28h]
  int v64; // [rsp+174h] [rbp+2Ch]
  int v65; // [rsp+178h] [rbp+30h]
  int v66; // [rsp+17Ch] [rbp+34h]
  int v67; // [rsp+180h] [rbp+38h]
  int v68; // [rsp+184h] [rbp+3Ch]
  float v69[100]; // [rsp+188h] [rbp+40h] BYREF
  unsigned __int16 v70[304]; // [rsp+318h] [rbp+1D0h] BYREF
  _BYTE v71[608]; // [rsp+578h] [rbp+430h] BYREF

  v4 = a2;
  v6 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, __int64, _BYTE *, __int64))(*(_QWORD *)a1 + 32LL))(
         a1,
         a2,
         v71,
         300);
  if ( v6 >= 0 )
  {
    v7 = *(_QWORD *)a1;
    v70[0] = 0;
    v8 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD))(v7 + 48))(a1, v4);
    if ( v8 <= 8 )
    {
      switch ( v8 )
      {
        case 8:
          v9 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, LPOLESTR *, int))(*(_QWORD *)a1 + 88LL))(
                 a1,
                 v4,
                 0,
                 lpsz,
                 16);
          if ( v9 < 0 )
            break;
          v10 = StringCchPrintfW(
                  v70,
                  0x12Cu,
                  L"(%f,%f,%f,%f)",
                  *(float *)lpsz,
                  *((float *)lpsz + 1),
                  *(float *)&lpsz[1],
                  *((float *)&lpsz[1] + 1));
          goto LABEL_27;
        case 1:
          v10 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, unsigned __int16 *, int))(*(_QWORD *)a1 + 88LL))(
                  a1,
                  v4,
                  0,
                  v70,
                  600);
          goto LABEL_27;
        case 2:
          v14 = *(_QWORD *)a1;
          v38 = 0.0;
          v9 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, float *, int))(v14 + 88))(
                 a1,
                 v4,
                 0,
                 &v38,
                 4);
          if ( v9 >= 0 )
          {
            v15 = L"true";
            if ( v38 == 0.0 )
              v15 = L"false";
            v10 = StringCchCopyW(v70, 0x12Cu, v15);
            goto LABEL_27;
          }
          break;
        case 3:
          v13 = *(_QWORD *)a1;
          v38 = 0.0;
          v9 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, float *, int))(v13 + 88))(
                 a1,
                 v4,
                 0,
                 &v38,
                 4);
          if ( v9 >= 0 )
          {
            v10 = StringCchPrintfW(v70, 0x12Cu, L"%u", v38);
            goto LABEL_27;
          }
          break;
        case 4:
          v12 = *(_QWORD *)a1;
          v38 = 0.0;
          v9 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, float *, int))(v12 + 88))(
                 a1,
                 v4,
                 0,
                 &v38,
                 4);
          if ( v9 >= 0 )
          {
            v10 = StringCchPrintfW(v70, 0x12Cu, L"%d", v38);
            goto LABEL_27;
          }
          break;
        case 5:
          v11 = *(_QWORD *)a1;
          v38 = 0.0;
          v9 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, float *, int))(v11 + 88))(
                 a1,
                 v4,
                 0,
                 &v38,
                 4);
          if ( v9 >= 0 )
          {
            v10 = StringCchPrintfW(v70, 0x12Cu, L"%f", v38);
            goto LABEL_27;
          }
          break;
        case 6:
          v9 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, LPOLESTR *, int))(*(_QWORD *)a1 + 88LL))(
                 a1,
                 v4,
                 0,
                 lpsz,
                 8);
          if ( v9 >= 0 )
          {
            v10 = StringCchPrintfW(v70, 0x12Cu, L"(%f,%f)", *(float *)lpsz, *((float *)lpsz + 1));
            goto LABEL_27;
          }
          break;
        case 7:
          v9 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, LPOLESTR *, int))(*(_QWORD *)a1 + 88LL))(
                 a1,
                 v4,
                 0,
                 lpsz,
                 12);
          if ( v9 >= 0 )
          {
            v10 = StringCchPrintfW(v70, 0x12Cu, L"(%f,%f,%f)", *(float *)lpsz, *((float *)lpsz + 1), *(float *)&lpsz[1]);
            goto LABEL_27;
          }
          break;
        default:
          goto LABEL_69;
      }
LABEL_29:
      DoStackCapture(v9);
      return (unsigned int)v9;
    }
    if ( v8 == 9 )
    {
      v6 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, float *, int))(*(_QWORD *)a1 + 88LL))(
             a1,
             v4,
             0,
             v69,
             400);
      if ( v6 >= 0 )
      {
        v29 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD))(*(_QWORD *)a1 + 96LL))(a1, v4);
        LODWORD(v30) = 0;
        v31 = v29 >> 2;
        for ( i = 0; i < v31; ++i )
        {
          if ( (unsigned int)v30 >= 0x12C )
          {
            v9 = -2147024774;
            goto LABEL_29;
          }
          v33 = L"%f";
          v34 = 300LL - (unsigned int)v30;
          v35 = &v70[(unsigned int)v30];
          if ( i )
            v33 = L", %f";
          v36 = StringCchPrintfW(v35, v34, v33, v69[i]);
          v37 = v36;
          if ( v36 < 0 )
          {
            DoStackCapture(v36);
            return v37;
          }
          v30 = -1;
          do
            ++v30;
          while ( v70[v30] );
          if ( v30 > 0x12C )
            LODWORD(v30) = 300;
        }
        goto LABEL_69;
      }
    }
    else
    {
      if ( v8 != 11 )
      {
        switch ( v8 )
        {
          case 13:
            v20 = *(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, IID *, int))(*(_QWORD *)a1 + 88LL);
            rclsid = 0;
            v9 = v20(a1, v4, 0, &rclsid, 16);
            if ( v9 < 0 )
              goto LABEL_29;
            lpsz[0] = 0;
            v9 = StringFromCLSID(&rclsid, lpsz);
            if ( v9 < 0 )
              goto LABEL_29;
            v9 = StringCchCopyW(v70, 0x12Cu, lpsz[0]);
            CoTaskMemFree(lpsz[0]);
            v16 = v9 < 0;
LABEL_28:
            if ( v16 )
              goto LABEL_29;
LABEL_69:
            v9 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, _BYTE *, _QWORD, unsigned __int16 *))a3->lpVtbl->WriteAttributeString)(
                   a3,
                   0,
                   v71,
                   0,
                   v70);
            if ( v9 >= 0 )
              return (unsigned int)v9;
            goto LABEL_29;
          case 14:
            *(_QWORD *)&v42 = 0;
            v19 = *(_QWORD *)a1;
            *(_OWORD *)lpsz = 0;
            v9 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, LPOLESTR *, int))(v19 + 88))(
                   a1,
                   v4,
                   0,
                   lpsz,
                   24);
            if ( v9 < 0 )
              goto LABEL_29;
            v10 = StringCchPrintfW(
                    v70,
                    0x12Cu,
                    L"(%f,%f,%f,%f,%f,%f)",
                    *(float *)lpsz,
                    *((float *)lpsz + 1),
                    *(float *)&lpsz[1],
                    *((float *)&lpsz[1] + 1),
                    *(float *)&v42,
                    *((float *)&v42 + 1));
            break;
          case 15:
            v18 = *(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, LPOLESTR *, int))(*(_QWORD *)a1 + 88LL);
            *(_OWORD *)lpsz = 0;
            v42 = 0;
            v43 = 0;
            v9 = v18(a1, v4, 0, lpsz, 48);
            if ( v9 < 0 )
              goto LABEL_29;
            v10 = StringCchPrintfW(
                    v70,
                    0x12Cu,
                    L"(%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f)",
                    *(float *)lpsz,
                    *((float *)lpsz + 1),
                    *(float *)&lpsz[1],
                    *((float *)&lpsz[1] + 1),
                    *(float *)&v42,
                    *((float *)&v42 + 1),
                    *((float *)&v42 + 2),
                    *((float *)&v42 + 3),
                    *(float *)&v43,
                    *((float *)&v43 + 1),
                    *((float *)&v43 + 2),
                    *((float *)&v43 + 3));
            break;
          case 16:
            memset_0(lpsz, 0, 0x40u);
            v9 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, LPOLESTR *, int))(*(_QWORD *)a1 + 88LL))(
                   a1,
                   v4,
                   0,
                   lpsz,
                   64);
            if ( v9 < 0 )
              goto LABEL_29;
            v10 = StringCchPrintfW(
                    v70,
                    0x12Cu,
                    L"(%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f)",
                    *(float *)lpsz,
                    *((float *)lpsz + 1),
                    *(float *)&lpsz[1],
                    *((float *)&lpsz[1] + 1),
                    *(float *)&v42,
                    *((float *)&v42 + 1),
                    *((float *)&v42 + 2),
                    *((float *)&v42 + 3),
                    *(float *)&v43,
                    *((float *)&v43 + 1),
                    *((float *)&v43 + 2),
                    *((float *)&v43 + 3),
                    v44,
                    v45,
                    v46,
                    v47);
            break;
          case 17:
            memset_0(&v49, 0, 0x50u);
            v9 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, int *, int))(*(_QWORD *)a1 + 88LL))(
                   a1,
                   v4,
                   0,
                   &v49,
                   80);
            if ( v9 < 0 )
              goto LABEL_29;
            *(double *)lpsz = v53;
            *(double *)&rclsid.Data1 = v52;
            v39 = v51;
            v40[0] = v50;
            v10 = StringCchPrintfW(
                    v70,
                    0x12Cu,
                    L"(%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f)",
                    v49,
                    v50,
                    v51,
                    v52,
                    v53,
                    v54,
                    v55,
                    v56,
                    v57,
                    v58,
                    v59,
                    v60,
                    v61,
                    v62,
                    v63,
                    v64,
                    v65,
                    v66,
                    v67,
                    v68);
            break;
          default:
            goto LABEL_69;
        }
LABEL_27:
        v9 = v10;
        v16 = v10 < 0;
        goto LABEL_28;
      }
      v21 = *(_QWORD *)a1;
      v38 = 0.0;
      v6 = (*(__int64 (__fastcall **)(struct ID2D1Properties *, _QWORD, _QWORD, float *, int))(v21 + 88))(
             a1,
             v4,
             0,
             &v38,
             4);
      if ( v6 >= 0 )
      {
        v22 = *(_QWORD *)a1;
        lpsz[0] = 0;
        if ( (*(int (__fastcall **)(struct ID2D1Properties *, _QWORD, LPOLESTR *))(v22 + 104))(a1, v4, lpsz) < 0
          || !lpsz[0] )
        {
          goto LABEL_67;
        }
        v39 = 0.0;
        v23 = 0;
        if ( (*(int (__fastcall **)(LPOLESTR, __int64, double *))(*(_QWORD *)lpsz[0] + 104LL))(
               lpsz[0],
               2147483653LL,
               &v39) >= 0
          && v39 != 0.0 )
        {
          v24 = (*(__int64 (__fastcall **)(double))(**(_QWORD **)&v39 + 24LL))(COERCE_DOUBLE(*(_QWORD *)&v39));
          for ( j = 0; ; ++j )
          {
            if ( j >= v24 )
              goto LABEL_66;
            *(_QWORD *)&rclsid.Data1 = 0;
            if ( (*(int (__fastcall **)(double, _QWORD, IID *))(**(_QWORD **)&v39 + 104LL))(
                   COERCE_DOUBLE(*(_QWORD *)&v39),
                   j,
                   &rclsid) >= 0 )
            {
              if ( *(_QWORD *)&rclsid.Data1 )
              {
                v26 = **(_QWORD **)&rclsid.Data1;
                LODWORD(v40[0]) = 0;
                (*(void (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, double *, int))(v26 + 80))(
                  *(_QWORD *)&rclsid.Data1,
                  L"Index",
                  0,
                  v40,
                  4);
                if ( LODWORD(v40[0]) == LODWORD(v38) )
                  break;
              }
            }
            ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&rclsid);
          }
          if ( !(*(unsigned int (__fastcall **)(double, _QWORD))(**(_QWORD **)&v39 + 40LL))(
                  COERCE_DOUBLE(*(_QWORD *)&v39),
                  j) )
          {
LABEL_65:
            ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&rclsid);
            goto LABEL_66;
          }
          v27 = (*(__int64 (__fastcall **)(double, _QWORD, unsigned __int16 *, __int64))(**(_QWORD **)&v39 + 32LL))(
                  COERCE_DOUBLE(*(_QWORD *)&v39),
                  j,
                  v70,
                  300);
          v9 = v27;
          if ( v27 >= 0 )
          {
            v23 = 1;
            goto LABEL_65;
          }
          DoStackCapture(v27);
          ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&rclsid);
          ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v39);
LABEL_73:
          ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(lpsz);
          return (unsigned int)v9;
        }
LABEL_66:
        ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v39);
        if ( !v23 )
        {
LABEL_67:
          v28 = StringCchPrintfW(v70, 0x12Cu, L"%u", v38);
          v9 = v28;
          if ( v28 < 0 )
          {
            DoStackCapture(v28);
            goto LABEL_73;
          }
        }
        ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(lpsz);
        goto LABEL_69;
      }
    }
  }
  DoStackCapture(v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18020a550  mov     rax, rsp
0x18020a553  push    rbp
0x18020a554  push    rbx
0x18020a555  push    rsi
0x18020a556  push    rdi
0x18020a557  push    r12
0x18020a559  push    r14
0x18020a55b  push    r15
0x18020a55d  lea     rbp, [rax-778h]
0x18020a564  sub     rsp, 880h
0x18020a56b  movaps  xmmword ptr [rax-48h], xmm6
0x18020a56f  movaps  xmmword ptr [rax-58h], xmm7
0x18020a573  movaps  xmmword ptr [rax-68h], xmm8
0x18020a578  movaps  xmmword ptr [rax-78h], xmm9
0x18020a57d  movaps  xmmword ptr [rax-88h], xmm10
0x18020a585  movaps  xmmword ptr [rax-98h], xmm11
0x18020a58d  movaps  xmmword ptr [rax-0A8h], xmm12
0x18020a595  movaps  xmmword ptr [rax-0B8h], xmm13
0x18020a59d  movaps  xmmword ptr [rax-0C8h], xmm14
0x18020a5a5  movaps  xmmword ptr [rax-0D8h], xmm15
0x18020a5ad  mov     rax, cs:__security_cookie
0x18020a5b4  xor     rax, rsp
0x18020a5b7  mov     [rbp+770h+var_E0], rax
0x18020a5be  mov     rax, [rcx]
0x18020a5c1  mov     r14, r8
0x18020a5c4  mov     r12d, 12Ch
0x18020a5ca  lea     r8, [rbp+770h+var_340]
0x18020a5d1  mov     r9d, r12d
0x18020a5d4  mov     edi, edx
0x18020a5d6  mov     rbx, rcx
0x18020a5d9  mov     rax, [rax+20h]
0x18020a5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a5e2  xor     r15d, r15d
0x18020a5e5  mov     esi, eax
0x18020a5e7  test    eax, eax
0x18020a5e9  js      loc_18020B12E
0x18020a5ef  mov     rax, [rbx]
0x18020a5f2  mov     edx, edi
0x18020a5f4  mov     rcx, rbx
0x18020a5f7  mov     [rbp+770h+var_5A0], r15w
0x18020a5ff  mov     rax, [rax+30h]
0x18020a603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a608  mov     r8d, eax
0x18020a60b  cmp     eax, 8
0x18020a60e  jg      loc_18020A905
0x18020a614  jz      loc_18020A88D
0x18020a61a  sub     r8d, 1
0x18020a61e  jz      loc_18020A852
0x18020a624  sub     r8d, 1
0x18020a628  jz      loc_18020A801
0x18020a62e  sub     r8d, 1
0x18020a632  jz      loc_18020A7B7
0x18020a638  sub     r8d, 1
0x18020a63c  jz      loc_18020A780
0x18020a642  sub     r8d, 1
0x18020a646  jz      loc_18020A72A
0x18020a64c  sub     r8d, 1
0x18020a650  jz      short loc_18020A6CA
0x18020a652  cmp     r8d, 1
0x18020a656  jnz     loc_18020B000
0x18020a65c  mov     rax, [rbx]
0x18020a65f  lea     r9, [rbp+770h+lpsz]
0x18020a663  xor     r8d, r8d
0x18020a666  mov     dword ptr [rsp+8B0h+var_890], 0Ch
0x18020a66e  mov     edx, edi
0x18020a670  mov     rcx, rbx
0x18020a673  mov     rax, [rax+58h]
0x18020a677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a67c  mov     ebx, eax
0x18020a67e  test    eax, eax
0x18020a680  js      loc_18020A87F
0x18020a686  movss   xmm0, dword ptr [rbp+770h+lpsz+8]
0x18020a68b  lea     r8, aFFF; "(%f,%f,%f)"
0x18020a692  movss   xmm3, dword ptr [rbp+770h+lpsz]
0x18020a697  lea     rcx, [rbp+770h+var_5A0]; unsigned __int16 *
0x18020a69e  movss   xmm1, dword ptr [rbp+770h+lpsz+4]
0x18020a6a3  mov     edx, r12d; unsigned __int64
0x18020a6a6  cvtps2pd xmm0, xmm0
0x18020a6a9  cvtps2pd xmm3, xmm3
0x18020a6ac  cvtps2pd xmm1, xmm1
0x18020a6af  movsd   [rsp+8B0h+var_888], xmm0
0x18020a6b5  movq    r9, xmm3
0x18020a6ba  movsd   [rsp+8B0h+var_890], xmm1
0x18020a6c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18020a6c5  jmp     loc_18020A875
0x18020a6ca  mov     rax, [rbx]
0x18020a6cd  lea     r9, [rbp+770h+lpsz]
0x18020a6d1  xor     r8d, r8d
0x18020a6d4  mov     dword ptr [rsp+8B0h+var_890], 8
0x18020a6dc  mov     edx, edi
0x18020a6de  mov     rcx, rbx
0x18020a6e1  mov     rax, [rax+58h]
0x18020a6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a6ea  mov     ebx, eax
0x18020a6ec  test    eax, eax
0x18020a6ee  js      loc_18020A87F
0x18020a6f4  movss   xmm3, dword ptr [rbp+770h+lpsz]
0x18020a6f9  lea     r8, aFF; "(%f,%f)"
0x18020a700  movss   xmm0, dword ptr [rbp+770h+lpsz+4]
0x18020a705  lea     rcx, [rbp+770h+var_5A0]; unsigned __int16 *
0x18020a70c  cvtps2pd xmm3, xmm3
0x18020a70f  mov     rdx, r12; unsigned __int64
0x18020a712  cvtps2pd xmm0, xmm0
0x18020a715  movq    r9, xmm3
0x18020a71a  movsd   [rsp+8B0h+var_890], xmm0
0x18020a720  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18020a725  jmp     loc_18020A875
0x18020a72a  mov     rax, [rbx]
0x18020a72d  lea     r9, [rbp+770h+var_7F0]
0x18020a731  xor     r8d, r8d
0x18020a734  mov     [rbp+770h+var_7F0], r15d
0x18020a738  mov     edx, edi
0x18020a73a  mov     dword ptr [rsp+8B0h+var_890], 4
0x18020a742  mov     rcx, rbx
0x18020a745  mov     rax, [rax+58h]
0x18020a749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a74e  mov     ebx, eax
0x18020a750  test    eax, eax
0x18020a752  js      loc_18020A87F
0x18020a758  movss   xmm3, [rbp+770h+var_7F0]
0x18020a75d  lea     r8, asc_1803CB2A0; "%f"
0x18020a764  cvtps2pd xmm3, xmm3
0x18020a767  mov     rdx, r12; unsigned __int64
0x18020a76a  lea     rcx, [rbp+770h+var_5A0]; unsigned __int16 *
0x18020a771  movq    r9, xmm3
0x18020a776  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18020a77b  jmp     loc_18020A875
0x18020a780  mov     rax, [rbx]
0x18020a783  lea     r9, [rbp+770h+var_7F0]
0x18020a787  xor     r8d, r8d
0x18020a78a  mov     [rbp+770h+var_7F0], r15d
0x18020a78e  mov     edx, edi
0x18020a790  mov     dword ptr [rsp+8B0h+var_890], 4
0x18020a798  mov     rcx, rbx
0x18020a79b  mov     rax, [rax+58h]
0x18020a79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a7a4  mov     ebx, eax
0x18020a7a6  test    eax, eax
0x18020a7a8  js      loc_18020A87F
0x18020a7ae  lea     r8, aD; "%d"
0x18020a7b5  jmp     short loc_18020A7EC
0x18020a7b7  mov     rax, [rbx]
0x18020a7ba  lea     r9, [rbp+770h+var_7F0]
0x18020a7be  xor     r8d, r8d
0x18020a7c1  mov     [rbp+770h+var_7F0], r15d
0x18020a7c5  mov     edx, edi
0x18020a7c7  mov     dword ptr [rsp+8B0h+var_890], 4
0x18020a7cf  mov     rcx, rbx
0x18020a7d2  mov     rax, [rax+58h]
0x18020a7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a7db  mov     ebx, eax
0x18020a7dd  test    eax, eax
0x18020a7df  js      loc_18020A87F
0x18020a7e5  lea     r8, aU; "%u"
0x18020a7ec  mov     r9d, [rbp+770h+var_7F0]
0x18020a7f0  lea     rcx, [rbp+770h+var_5A0]; unsigned __int16 *
0x18020a7f7  mov     rdx, r12; unsigned __int64
0x18020a7fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18020a7ff  jmp     short loc_18020A875
0x18020a801  mov     rax, [rbx]
0x18020a804  lea     r9, [rbp+770h+var_7F0]
0x18020a808  xor     r8d, r8d
0x18020a80b  mov     [rbp+770h+var_7F0], r15d
0x18020a80f  mov     edx, edi
0x18020a811  mov     dword ptr [rsp+8B0h+var_890], 4
0x18020a819  mov     rcx, rbx
0x18020a81c  mov     rax, [rax+58h]
0x18020a820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a825  mov     ebx, eax
0x18020a827  test    eax, eax
0x18020a829  js      short loc_18020A87F
0x18020a82b  cmp     [rbp+770h+var_7F0], r15d
0x18020a82f  lea     rax, aFalse; "false"
0x18020a836  lea     r8, aTrue; "true"
0x18020a83d  mov     rdx, r12; unsigned __int64
0x18020a840  cmovz   r8, rax; unsigned __int16 *
0x18020a844  lea     rcx, [rbp+770h+var_5A0]; unsigned __int16 *
0x18020a84b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18020a850  jmp     short loc_18020A875
0x18020a852  mov     rax, [rbx]
0x18020a855  lea     r9, [rbp+770h+var_5A0]
0x18020a85c  xor     r8d, r8d
0x18020a85f  mov     dword ptr [rsp+8B0h+var_890], 258h
0x18020a867  mov     edx, edi
0x18020a869  mov     rcx, rbx
0x18020a86c  mov     rax, [rax+58h]
0x18020a870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a875  mov     ebx, eax
0x18020a877  test    eax, eax
0x18020a879  jns     loc_18020B000
0x18020a87f  mov     ecx, ebx; int
0x18020a881  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18020a886  mov     eax, ebx
0x18020a888  jmp     loc_18020B137
0x18020a88d  mov     rax, [rbx]
0x18020a890  lea     r9, [rbp+770h+lpsz]
0x18020a894  xor     r8d, r8d
0x18020a897  mov     dword ptr [rsp+8B0h+var_890], 10h
0x18020a89f  mov     edx, edi
0x18020a8a1  mov     rcx, rbx
0x18020a8a4  mov     rax, [rax+58h]
0x18020a8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a8ad  mov     ebx, eax
0x18020a8af  test    eax, eax
0x18020a8b1  js      short loc_18020A87F
0x18020a8b3  movss   xmm0, dword ptr [rbp+770h+lpsz+0Ch]
0x18020a8b8  lea     r8, aFFFF; "(%f,%f,%f,%f)"
0x18020a8bf  movss   xmm1, dword ptr [rbp+770h+lpsz+8]
0x18020a8c4  lea     rcx, [rbp+770h+var_5A0]; unsigned __int16 *
0x18020a8cb  movss   xmm3, dword ptr [rbp+770h+lpsz]
0x18020a8d0  mov     rdx, r12; unsigned __int64
0x18020a8d3  movss   xmm2, dword ptr [rbp+770h+lpsz+4]
0x18020a8d8  cvtps2pd xmm0, xmm0
0x18020a8db  cvtps2pd xmm1, xmm1
0x18020a8de  movsd   [rsp+8B0h+var_880], xmm0
0x18020a8e4  cvtps2pd xmm3, xmm3
0x18020a8e7  cvtps2pd xmm2, xmm2
0x18020a8ea  movsd   [rsp+8B0h+var_888], xmm1
0x18020a8f0  movq    r9, xmm3
0x18020a8f5  movsd   [rsp+8B0h+var_890], xmm2
0x18020a8fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18020a900  jmp     loc_18020A875
0x18020a905  sub     r8d, 9
0x18020a909  jz      loc_18020B066
0x18020a90f  sub     r8d, 2
0x18020a913  jz      loc_18020AE7D
0x18020a919  sub     r8d, 2
0x18020a91d  jz      loc_18020AE0A
0x18020a923  sub     r8d, 1
0x18020a927  jz      loc_18020AD65
0x18020a92d  sub     r8d, 1
0x18020a931  jz      loc_18020AC5E
0x18020a937  sub     r8d, 1
0x18020a93b  jz      loc_18020AB0A
0x18020a941  cmp     r8d, 1
0x18020a945  jnz     loc_18020B000
0x18020a94b  lea     esi, [r8+4Fh]
0x18020a94f  xor     edx, edx; Val
0x18020a951  mov     r8d, esi; Size
0x18020a954  lea     rcx, [rbp+770h+var_780]; void *
0x18020a958  call    memset_0
0x18020a95d  mov     rax, [rbx]
0x18020a960  lea     r9, [rbp+770h+var_780]
0x18020a964  xor     r8d, r8d
0x18020a967  mov     dword ptr [rsp+8B0h+var_890], esi
0x18020a96b  mov     edx, edi
0x18020a96d  mov     rcx, rbx
0x18020a970  mov     rax, [rax+58h]
0x18020a974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020a979  mov     ebx, eax
0x18020a97b  test    eax, eax
0x18020a97d  js      loc_18020A87F
0x18020a983  movss   xmm3, [rbp+770h+var_770]
0x18020a988  lea     r8, aFFFFFFFFFFFFFF_0; "(%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f,%f"...
0x18020a98f  movss   xmm0, [rbp+770h+var_734]
0x18020a994  lea     rcx, [rbp+770h+var_5A0]; unsigned __int16 *
0x18020a99b  movss   xmm1, [rbp+770h+var_738]
0x18020a9a0  mov     rdx, r12; unsigned __int64
0x18020a9a3  movss   xmm2, [rbp+770h+var_73C]
0x18020a9a8  movss   xmm4, [rbp+770h+var_740]
0x18020a9ad  movss   xmm5, [rbp+770h+var_744]
0x18020a9b2  movss   xmm6, [rbp+770h+var_748]
0x18020a9b7  movss   xmm7, [rbp+770h+var_74C]
0x18020a9bc  movss   xmm8, [rbp+770h+var_750]
0x18020a9c2  movss   xmm9, [rbp+770h+var_754]
0x18020a9c8  movss   xmm10, [rbp+770h+var_758]
0x18020a9ce  movss   xmm11, [rbp+770h+var_75C]
0x18020a9d4  movss   xmm12, [rbp+770h+var_760]
0x18020a9da  movss   xmm13, [rbp+770h+var_764]
0x18020a9e0  movss   xmm14, [rbp+770h+var_768]
0x18020a9e6  movss   xmm15, [rbp+770h+var_76C]
0x18020a9ec  cvtps2pd xmm3, xmm3
0x18020a9ef  cvtps2pd xmm0, xmm0
0x18020a9f2  movsd   [rbp+770h+lpsz], xmm3
0x18020a9f7  movss   xmm3, [rbp+770h+var_774]
0x18020a9fc  movsd   [rsp+8B0h+var_800], xmm0
0x18020aa05  movsd   xmm0, [rbp+770h+lpsz]
0x18020aa0a  cvtps2pd xmm3, xmm3
0x18020aa0d  cvtps2pd xmm1, xmm1
0x18020aa10  movsd   qword ptr [rbp+770h+rclsid.Data1], xmm3
0x18020aa15  movss   xmm3, [rbp+770h+var_778]
0x18020aa1a  movsd   [rsp+8B0h+var_808], xmm1
0x18020aa23  movsd   xmm1, qword ptr [rbp+770h+rclsid.Data1]
0x18020aa28  cvtps2pd xmm3, xmm3
0x18020aa2b  cvtps2pd xmm2, xmm2
0x18020aa2e  movsd   [rbp+770h+var_7E8], xmm3
0x18020aa33  movss   xmm3, [rbp+770h+var_77C]
0x18020aa38  movsd   [rsp+8B0h+var_810], xmm2
0x18020aa41  movsd   xmm2, [rbp+770h+var_7E8]
0x18020aa46  cvtps2pd xmm3, xmm3
0x18020aa49  cvtps2pd xmm4, xmm4
0x18020aa4c  movsd   [rbp+770h+var_7E0], xmm3
0x18020aa51  movss   xmm3, [rbp+770h+var_780]
0x18020aa56  movsd   [rsp+8B0h+var_818], xmm4
0x18020aa5f  cvtps2pd xmm5, xmm5
0x18020aa62  cvtps2pd xmm6, xmm6
0x18020aa65  movsd   [rsp+8B0h+var_820], xmm5
0x18020aa6e  movsd   [rsp+8B0h+var_828], xmm6
0x18020aa77  cvtps2pd xmm7, xmm7
0x18020aa7a  cvtps2pd xmm8, xmm8
  ... truncated ...
```
