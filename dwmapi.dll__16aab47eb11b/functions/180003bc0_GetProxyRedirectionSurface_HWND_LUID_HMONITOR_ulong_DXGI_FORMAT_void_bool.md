# GetProxyRedirectionSurface(HWND__ *,_LUID,HMONITOR__ *,ulong,DXGI_FORMAT *,void * *,bool *)

- ea: `0x180003bc0`
- end: `0x1800042ec`
- name: `?GetProxyRedirectionSurface@@YAJPEAUHWND__@@U_LUID@@PEAUHMONITOR__@@KPEAW4DXGI_FORMAT@@PEAPEAXPEA_N@Z`
- size: `1836`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, struct _LUID@<rdx>, HMONITOR@<r8>, unsigned int@<r9d>, enum DXGI_FORMAT *, void **, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002200`

## callees

- `0x180003370`
- `0x180003bc0`
- `0x180005534`
- `0x1800075d0`
- `0x180009fe8`
- `0x18000c2b4`
- `0x18000d0a0`
- `0x18000ddc4`
- `0x180017010`

## import_xrefs

- `ntdll!RtlInitializeGenericTable` at `0x180003f58`
- `ntdll!RtlInitializeGenericTable` at `0x180003f58`
- `ntdll!RtlLookupElementGenericTable` at `0x180003ca8`
- `ntdll!RtlLookupElementGenericTable` at `0x180003ca8`
- `ntdll!RtlInsertElementGenericTable` at `0x180003fbb`
- `ntdll!RtlInsertElementGenericTable` at `0x180003fbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000406d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000406d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ccd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ccd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ffa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004028`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004059`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000408e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ffa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004028`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004059`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000408e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004007`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004035`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004007`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004035`
- `USER32!GetWindowRect` at `0x180003ce9`
- `USER32!GetWindowRect` at `0x180003ce9`

## string_xrefs

- `0x180004000`: `dxgi.dll`
- `0x18000402e`: `d3d11.dll`
- `0x180004066`: `CreateDXGIFactory`
- `0x18000409b`: `D3D11CreateDevice`

## pseudocode

```c
__int64 __fastcall GetProxyRedirectionSurface(
        HWND a1,
        struct _LUID a2,
        HMONITOR a3,
        __int64 a4,
        enum DXGI_FORMAT *a5,
        void **a6,
        bool *a7)
{
  DWORD LowPart; // ebx
  LONG HighPart; // r12d
  int inserted; // eax
  const struct std::nothrow_t *v11; // rdx
  signed int v12; // edi
  struct CDwmHwndData *v13; // r14
  struct _RTL_GENERIC_TABLE *v14; // rsi
  _QWORD *v15; // rax
  _QWORD *v16; // rsi
  __int64 v17; // rdx
  void **v18; // r12
  int v19; // ebx
  int v20; // r14d
  bool *v21; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  unsigned int v25; // edx
  int v26; // ecx
  signed int LastError; // eax
  signed int v28; // eax
  signed int v29; // eax
  signed int v30; // eax
  int v31; // eax
  struct _RTL_GENERIC_TABLE *v32; // rax
  unsigned int v33; // edx
  int (*ProcAddress)(const struct _GUID *, void **); // rax
  unsigned int v35; // r14d
  _QWORD *v36; // r15
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  struct IDXGIAdapter *v42; // [rsp+60h] [rbp-A0h] BYREF
  struct CDwmHwndData *v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  __int64 v45; // [rsp+78h] [rbp-88h] BYREF
  struct _RTL_CRITICAL_SECTION *v46; // [rsp+80h] [rbp-80h] BYREF
  HWND hWnd; // [rsp+88h] [rbp-78h]
  void **v48; // [rsp+90h] [rbp-70h]
  enum DXGI_FORMAT *v49; // [rsp+98h] [rbp-68h]
  bool *v50; // [rsp+A0h] [rbp-60h]
  _DWORD Buffer[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h]
  __int64 v53; // [rsp+B8h] [rbp-48h]
  __int128 v54; // [rsp+C0h] [rbp-40h]
  char v55; // [rsp+D0h] [rbp-30h]
  _DWORD v56[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  __int128 v59; // [rsp+F0h] [rbp-10h]
  char v60; // [rsp+100h] [rbp+0h]
  struct tagRECT Rect; // [rsp+108h] [rbp+8h] BYREF
  __m128i si128; // [rsp+118h] [rbp+18h] BYREF
  int v63; // [rsp+128h] [rbp+28h]
  __int64 v64; // [rsp+12Ch] [rbp+2Ch]
  int v65; // [rsp+134h] [rbp+34h]
  __int64 v66; // [rsp+138h] [rbp+38h]
  int v67; // [rsp+140h] [rbp+40h]
  _BYTE v68[296]; // [rsp+150h] [rbp+50h] BYREF
  int v69; // [rsp+278h] [rbp+178h]
  int v70; // [rsp+27Ch] [rbp+17Ch]

  v49 = a5;
  v48 = a6;
  hWnd = a1;
  LowPart = a2.LowPart;
  v50 = a7;
  HighPart = a2.HighPart;
  v44 = 0;
  v42 = 0;
  v45 = 0;
  Rect = 0;
  v46 = &CDwmHwndData::s_cs;
  EnterCriticalSection(&CDwmHwndData::s_cs);
  v43 = 0;
  inserted = CDwmHwndData::InsertElement(a1, &v43);
  v12 = inserted;
  if ( inserted < 0 )
  {
    DoStackCaptureDirect(inserted, 0x7Cu);
    LeaveCriticalSection(&CDwmHwndData::s_cs);
    goto LABEL_11;
  }
  v13 = v43;
  v14 = (struct _RTL_GENERIC_TABLE *)*((_QWORD *)v43 + 6);
  if ( !v14 )
  {
    v32 = (struct _RTL_GENERIC_TABLE *)operator new[](0x48u, v11);
    v14 = v32;
    if ( !v32 )
    {
      *((_QWORD *)v13 + 6) = 0;
      v33 = 129;
      goto LABEL_51;
    }
    RtlInitializeGenericTable(
      v32,
      CGenericTableMap<unsigned __int64,CProxySurfaceElement>::CompareTableData,
      CGenericTableMap<unsigned __int64,CDwmHwndData>::AllocTableData,
      CGenericTableMap<unsigned __int64,CProxySurfaceElement>::FreeTableData,
      0);
    *((_QWORD *)v13 + 6) = v14;
  }
  v52 = 0;
  v53 = 0;
  v55 = 0;
  Buffer[0] = LowPart;
  Buffer[1] = HighPart;
  v54 = 0;
  v15 = RtlLookupElementGenericTable(v14, Buffer);
  v16 = v15;
  if ( !v15 )
  {
    v56[0] = LowPart;
    v56[1] = HighPart;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v16 = RtlInsertElementGenericTable(*((PRTL_GENERIC_TABLE *)v13 + 6), v56, 0x30u, 0);
    if ( v16 )
      goto LABEL_5;
    v33 = 148;
LABEL_51:
    v12 = -2147024882;
    DoStackCaptureDirect(-2147024882, v33);
    CGuard<CDwmCS>::~CGuard<CDwmCS>(&v46);
    goto LABEL_11;
  }
  v17 = v15[3];
  if ( v17 && (*(int (__fastcall **)(__int64))(*(_QWORD *)v17 + 312LL))(v17) < 0 )
  {
    v23 = v16[4];
    v16[1] = 0;
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v16[4] = 0;
    }
    v24 = v16[3];
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v16[3] = 0;
    }
  }
LABEL_5:
  LeaveCriticalSection(&CDwmHwndData::s_cs);
  if ( !v16[3] )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v63 = 37376;
    LODWORD(v64) = 37120;
    LODWORD(v43) = 0;
    if ( !g_hDXGI )
    {
      SetLastError(0);
      g_hDXGI = LoadLibraryW(L"dxgi.dll");
      if ( !g_hDXGI )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        v25 = 171;
        if ( v12 >= 0 )
          v12 = -2003304445;
        goto LABEL_26;
      }
    }
    if ( !g_hD3D )
    {
      SetLastError(0);
      g_hD3D = LoadLibraryW(L"d3d11.dll");
      if ( !g_hD3D )
      {
        v28 = GetLastError();
        v12 = v28;
        if ( v28 > 0 )
          v12 = (unsigned __int16)v28 | 0x80070000;
        v25 = 176;
        if ( v12 >= 0 )
          v12 = -2003304445;
        goto LABEL_26;
      }
    }
    ProcAddress = g_pfnCreateDXGIFactory;
    if ( !g_pfnCreateDXGIFactory )
    {
      SetLastError(0);
      ProcAddress = (int (*)(const struct _GUID *, void **))GetProcAddress(g_hDXGI, "CreateDXGIFactory");
      g_pfnCreateDXGIFactory = ProcAddress;
      if ( !ProcAddress )
      {
        v29 = GetLastError();
        v12 = v29;
        if ( v29 > 0 )
          v12 = (unsigned __int16)v29 | 0x80070000;
        v25 = 181;
        if ( v12 >= 0 )
          v12 = -2003304445;
        goto LABEL_26;
      }
    }
    if ( !g_pfnD3D11CreateDevice )
    {
      SetLastError(0);
      g_pfnD3D11CreateDevice = (int (*)(struct IDXGIAdapter *, enum D3D_DRIVER_TYPE, HINSTANCE, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, unsigned int, struct ID3D11Device **, enum D3D_FEATURE_LEVEL *, struct ID3D11DeviceContext **))GetProcAddress(g_hD3D, "D3D11CreateDevice");
      if ( !g_pfnD3D11CreateDevice )
      {
        v30 = GetLastError();
        v12 = v30;
        if ( v30 > 0 )
          v12 = (unsigned __int16)v30 | 0x80070000;
        v25 = 186;
        if ( v12 >= 0 )
          v12 = -2003304445;
        goto LABEL_26;
      }
      ProcAddress = g_pfnCreateDXGIFactory;
    }
    v35 = 0;
    v31 = ((__int64 (__fastcall *)(GUID *, __int64 *))ProcAddress)(&GUID_7b7166ec_21c7_44ae_b21a_c9ae321ae369, &v45);
    v12 = v31;
    if ( v31 < 0 )
    {
      v25 = 190;
LABEL_76:
      v26 = v31;
      goto LABEL_27;
    }
    while ( (*(int (__fastcall **)(__int64, _QWORD, struct IDXGIAdapter **))(*(_QWORD *)v45 + 56LL))(v45, v35, &v42) >= 0 )
    {
      memset_0(v68, 0, 0x130u);
      v31 = ((__int64 (__fastcall *)(struct IDXGIAdapter *, _BYTE *))v42->lpVtbl->GetDesc)(v42, v68);
      v12 = v31;
      if ( v31 < 0 )
      {
        v25 = 196;
        goto LABEL_76;
      }
      if ( v69 == LowPart && v70 == HighPart )
        break;
      if ( v42 )
      {
        ((void (__fastcall *)(struct IDXGIAdapter *))v42->lpVtbl->Release)(v42);
        v42 = 0;
      }
      ++v35;
    }
    if ( v42 )
    {
      v31 = ((__int64 (__fastcall *)(struct IDXGIAdapter *, _QWORD, _QWORD, _QWORD, __m128i *, int, int, _QWORD *, struct CDwmHwndData **, _QWORD))g_pfnD3D11CreateDevice)(
              v42,
              0,
              0,
              0,
              &si128,
              6,
              7,
              v16 + 3,
              &v43,
              0);
      v12 = v31;
      if ( v31 >= 0 )
      {
        *((_BYTE *)v16 + 40) = IsHybridDiscrete(v42);
        goto LABEL_6;
      }
      v25 = 221;
      goto LABEL_76;
    }
    v12 = -2147024809;
    v25 = 209;
LABEL_26:
    v26 = v12;
LABEL_27:
    DoStackCaptureDirect(v26, v25);
    goto LABEL_85;
  }
LABEL_6:
  GetWindowRect(hWnd, &Rect);
  v18 = (void **)(v16 + 1);
  v19 = Rect.right - Rect.left;
  v20 = Rect.bottom - Rect.top;
  if ( v16[1] && v16[4] && v19 == *((_DWORD *)v16 + 4) && v20 == *((_DWORD *)v16 + 5) )
  {
LABEL_10:
    *v48 = *v18;
    v21 = v50;
    *v49 = DXGI_FORMAT_B8G8R8A8_UNORM;
    *v21 = *((_BYTE *)v16 + 40);
    if ( v12 >= 0 )
      goto LABEL_11;
    goto LABEL_85;
  }
  v36 = v16 + 4;
  *((_DWORD *)v16 + 4) = v19;
  v37 = v16[4];
  *((_DWORD *)v16 + 5) = v20;
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    *v36 = 0;
  }
  v38 = v16[3];
  *v18 = 0;
  si128.m128i_i64[1] = 0x100000001LL;
  v64 = 1;
  si128.m128i_i64[0] = __PAIR64__(v20, v19);
  v63 = 87;
  v65 = 0;
  v66 = 8;
  v67 = 2;
  v39 = (*(__int64 (__fastcall **)(__int64, __m128i *, _QWORD, _QWORD *))(*(_QWORD *)v38 + 40LL))(
          v38,
          &si128,
          0,
          v16 + 4);
  v12 = v39;
  if ( v39 >= 0 )
  {
    v31 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v36)(
            *v36,
            &GUID_035f3ab4_482e_4e50_b41f_8a7f8bd8960b,
            &v44);
    v12 = v31;
    if ( v31 < 0 )
    {
      v25 = 259;
    }
    else
    {
      v31 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v44 + 64LL))(v44, v16 + 1);
      v12 = v31;
      if ( v31 >= 0 )
        goto LABEL_10;
      v25 = 261;
    }
    goto LABEL_76;
  }
  DoStackCaptureDirect(v39, 0x101u);
LABEL_85:
  if ( v16 )
  {
    v40 = v16[3];
    v16[1] = 0;
    if ( v40 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v16[3] = 0;
    }
    v41 = v16[4];
    if ( v41 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      v16[4] = 0;
    }
  }
LABEL_11:
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v42 )
  {
    ((void (__fastcall *)(struct IDXGIAdapter *))v42->lpVtbl->Release)(v42);
    v42 = 0;
  }
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp-8+arg_10], rbx
0x180003bc5  push    rbp
0x180003bc6  push    rsi
0x180003bc7  push    rdi
0x180003bc8  push    r12
0x180003bca  push    r13
0x180003bcc  push    r14
0x180003bce  push    r15
0x180003bd0  lea     rbp, [rsp-190h]
0x180003bd8  sub     rsp, 290h
0x180003bdf  mov     rax, cs:__security_cookie
0x180003be6  xor     rax, rsp
0x180003be9  mov     [rbp+1C0h+var_40], rax
0x180003bf0  mov     rax, [rbp+1C0h+arg_20]
0x180003bf7  lea     r13, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; CDwmCS CDwmHwndData::s_cs
0x180003bfe  mov     [rbp+1C0h+var_228], rax
0x180003c02  xor     r15d, r15d
0x180003c05  mov     rax, [rbp+1C0h+arg_28]
0x180003c0c  mov     rdi, rcx
0x180003c0f  mov     [rbp+1C0h+var_230], rax
0x180003c13  mov     r12, rdx
0x180003c16  mov     rax, [rbp+1C0h+arg_30]
0x180003c1d  xorps   xmm0, xmm0
0x180003c20  mov     [rbp+1C0h+hWnd], rcx
0x180003c24  mov     rbx, rdx
0x180003c27  mov     rcx, r13; lpCriticalSection
0x180003c2a  mov     [rbp+1C0h+var_220], rax
0x180003c2e  shr     r12, 20h
0x180003c32  mov     [rsp+2C0h+var_250], r15
0x180003c37  mov     [rsp+2C0h+var_260], r15
0x180003c3c  mov     [rsp+2C0h+var_248], r15
0x180003c41  movups  xmmword ptr [rbp+1C0h+Rect.left], xmm0
0x180003c45  mov     [rbp+1C0h+var_240], r13
0x180003c49  call    cs:__imp_EnterCriticalSection
0x180003c4f  lea     rdx, [rsp+2C0h+var_258]; struct CDwmHwndData **
0x180003c54  mov     [rsp+2C0h+var_258], r15
0x180003c59  mov     rcx, rdi; HWND
0x180003c5c  call    ?InsertElement@CDwmHwndData@@SAJPEAUHWND__@@PEAPEAV1@@Z; CDwmHwndData::InsertElement(HWND__ *,CDwmHwndData * *)
0x180003c61  mov     edi, eax
0x180003c63  test    eax, eax
0x180003c65  js      loc_180003DFD
0x180003c6b  mov     r14, [rsp+2C0h+var_258]
0x180003c70  mov     rsi, [r14+30h]
0x180003c74  test    rsi, rsi
0x180003c77  jz      loc_180003F29
0x180003c7d  mov     [rbp+1C0h+var_210], r15
0x180003c81  lea     rdx, [rbp+1C0h+Buffer]; Buffer
0x180003c85  mov     [rbp+1C0h+var_208], r15
0x180003c89  xorps   xmm0, xmm0
0x180003c8c  mov     [rbp+1C0h+var_1F0], r15b
0x180003c90  mov     rcx, rsi; Table
0x180003c93  mov     eax, ebx
0x180003c95  movsxd  r15, r12d
0x180003c98  shl     r15, 20h
0x180003c9c  or      r15, rax
0x180003c9f  mov     [rbp+1C0h+Buffer], r15
0x180003ca3  movdqu  [rbp+1C0h+var_200], xmm0
0x180003ca8  call    cs:__imp_RtlLookupElementGenericTable
0x180003cae  mov     rsi, rax
0x180003cb1  test    rax, rax
0x180003cb4  jz      loc_180003F91
0x180003cba  mov     rdx, [rax+18h]
0x180003cbe  xor     r15d, r15d
0x180003cc1  test    rdx, rdx
0x180003cc4  jnz     loc_180003DA4
0x180003cca  mov     rcx, r13; lpCriticalSection
0x180003ccd  call    cs:__imp_LeaveCriticalSection
0x180003cd3  lea     r13, [rsi+18h]
0x180003cd7  cmp     [r13+0], r15
0x180003cdb  jz      loc_180003FCF
0x180003ce1  mov     rcx, [rbp+1C0h+hWnd]; hWnd
0x180003ce5  lea     rdx, [rbp+1C0h+Rect]; lpRect
0x180003ce9  call    cs:__imp_GetWindowRect
0x180003cef  mov     ebx, [rbp+1C0h+Rect.right]
0x180003cf2  lea     r12, [rsi+8]
0x180003cf6  mov     r14d, [rbp+1C0h+Rect.bottom]
0x180003cfa  sub     ebx, [rbp+1C0h+Rect.left]
0x180003cfd  sub     r14d, [rbp+1C0h+Rect.top]
0x180003d01  cmp     [r12], r15
0x180003d05  jz      loc_180004191
0x180003d0b  cmp     [rsi+20h], r15
0x180003d0f  jz      loc_180004191
0x180003d15  cmp     ebx, [rsi+10h]
0x180003d18  jnz     loc_180004191
0x180003d1e  cmp     r14d, [rsi+14h]
0x180003d22  jnz     loc_180004191
0x180003d28  mov     rax, [r12]
0x180003d2c  mov     rcx, [rbp+1C0h+var_230]
0x180003d30  mov     [rcx], rax
0x180003d33  mov     rax, [rbp+1C0h+var_228]
0x180003d37  mov     rcx, [rbp+1C0h+var_220]
0x180003d3b  mov     dword ptr [rax], 57h ; 'W'
0x180003d41  mov     al, [rsi+28h]
0x180003d44  mov     [rcx], al
0x180003d46  test    edi, edi
0x180003d48  js      loc_180004267
0x180003d4e  mov     rcx, [rsp+2C0h+var_250]
0x180003d53  test    rcx, rcx
0x180003d56  jnz     loc_1800042AF
0x180003d5c  mov     rcx, [rsp+2C0h+var_260]
0x180003d61  test    rcx, rcx
0x180003d64  jnz     loc_1800042C5
0x180003d6a  mov     rcx, [rsp+2C0h+var_248]
0x180003d6f  test    rcx, rcx
0x180003d72  jnz     loc_1800042DB
0x180003d78  mov     eax, edi
0x180003d7a  mov     rcx, [rbp+1C0h+var_40]
0x180003d81  xor     rcx, rsp; StackCookie
0x180003d84  call    __security_check_cookie
0x180003d89  mov     rbx, [rsp+2C0h+arg_10]
0x180003d91  add     rsp, 290h
0x180003d98  pop     r15
0x180003d9a  pop     r14
0x180003d9c  pop     r13
0x180003d9e  pop     r12
0x180003da0  pop     rdi
0x180003da1  pop     rsi
0x180003da2  pop     rbp
0x180003da3  retn
0x180003da4  mov     rcx, [rdx]
0x180003da7  mov     rax, [rcx+138h]
0x180003dae  mov     rcx, rdx
0x180003db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db6  test    eax, eax
0x180003db8  jns     loc_180003CCA
0x180003dbe  mov     rcx, [rsi+20h]
0x180003dc2  mov     [rsi+8], r15
0x180003dc6  test    rcx, rcx
0x180003dc9  jz      short loc_180003DDB
0x180003dcb  mov     rax, [rcx]
0x180003dce  mov     rax, [rax+10h]
0x180003dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dd7  mov     [rsi+20h], r15
0x180003ddb  mov     rcx, [rsi+18h]
0x180003ddf  test    rcx, rcx
0x180003de2  jz      loc_180003CCA
0x180003de8  mov     rax, [rcx]
0x180003deb  mov     rax, [rax+10h]
0x180003def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003df4  mov     [rsi+18h], r15
0x180003df8  jmp     loc_180003CCA
0x180003dfd  mov     edx, 7Ch ; '|'; unsigned int
0x180003e02  mov     ecx, eax; int
0x180003e04  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180003e09  mov     rcx, r13; lpCriticalSection
0x180003e0c  call    cs:__imp_LeaveCriticalSection
0x180003e12  jmp     loc_180003D4E
0x180003e17  test    edi, edi
0x180003e19  mov     eax, 88980003h
0x180003e1e  mov     edx, 0ABh; unsigned int
0x180003e23  cmovns  edi, eax
0x180003e26  mov     ecx, edi; int
0x180003e28  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180003e2d  jmp     loc_180004267
0x180003e32  call    cs:__imp_GetLastError
0x180003e38  mov     edi, eax
0x180003e3a  test    eax, eax
0x180003e3c  jle     short loc_180003E17
0x180003e3e  movzx   edi, ax
0x180003e41  or      edi, 80070000h
0x180003e47  jmp     short loc_180003E17
0x180003e49  call    cs:__imp_GetLastError
0x180003e4f  mov     edi, eax
0x180003e51  test    eax, eax
0x180003e53  jle     short loc_180003E5E
0x180003e55  movzx   edi, ax
0x180003e58  or      edi, 80070000h
0x180003e5e  test    edi, edi
0x180003e60  mov     eax, 88980003h
0x180003e65  mov     edx, 0B0h
0x180003e6a  cmovns  edi, eax
0x180003e6d  jmp     short loc_180003E26
0x180003e6f  call    cs:__imp_GetLastError
0x180003e75  mov     edi, eax
0x180003e77  test    eax, eax
0x180003e79  jle     short loc_180003E84
0x180003e7b  movzx   edi, ax
0x180003e7e  or      edi, 80070000h
0x180003e84  test    edi, edi
0x180003e86  mov     eax, 88980003h
0x180003e8b  mov     edx, 0B5h
0x180003e90  cmovns  edi, eax
0x180003e93  jmp     short loc_180003E26
0x180003e95  call    cs:__imp_GetLastError
0x180003e9b  mov     edi, eax
0x180003e9d  test    eax, eax
0x180003e9f  jle     short loc_180003EAA
0x180003ea1  movzx   edi, ax
0x180003ea4  or      edi, 80070000h
0x180003eaa  test    edi, edi
0x180003eac  mov     eax, 88980003h
0x180003eb1  mov     edx, 0BAh
0x180003eb6  cmovns  edi, eax
0x180003eb9  jmp     loc_180003E26
0x180003ebe  mov     rcx, [rsp+2C0h+var_260]
0x180003ec3  test    rcx, rcx
0x180003ec6  jz      loc_18000416F
0x180003ecc  mov     [rsp+2C0h+var_278], r15
0x180003ed1  lea     rax, [rsp+2C0h+var_258]
0x180003ed6  mov     [rsp+2C0h+var_280], rax
0x180003edb  xor     r9d, r9d
0x180003ede  mov     [rsp+2C0h+var_288], r13
0x180003ee3  lea     rax, [rbp+1C0h+var_1A8]
0x180003ee7  mov     [rsp+2C0h+var_290], 7
0x180003eef  xor     r8d, r8d
0x180003ef2  mov     [rsp+2C0h+var_298], 6
0x180003efa  xor     edx, edx
0x180003efc  mov     [rsp+2C0h+TableContext], rax
0x180003f01  mov     rax, cs:?g_pfnD3D11CreateDevice@@3P6AJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@ZEA; long (*g_pfnD3D11CreateDevice)(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)
0x180003f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f0d  mov     edi, eax
0x180003f0f  test    eax, eax
0x180003f11  js      loc_18000417E
0x180003f17  mov     rcx, [rsp+2C0h+var_260]; struct IDXGIAdapter *
0x180003f1c  call    ?IsHybridDiscrete@@YA_NPEAUIDXGIAdapter@@@Z; IsHybridDiscrete(IDXGIAdapter *)
0x180003f21  mov     [rsi+28h], al
0x180003f24  jmp     loc_180003CE1
0x180003f29  mov     ecx, 48h ; 'H'; unsigned __int64
0x180003f2e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003f33  mov     rsi, rax
0x180003f36  test    rax, rax
0x180003f39  jz      short loc_180003F67
0x180003f3b  lea     r9, ?FreeTableData@?$CGenericTableMap@_KVCProxySurfaceElement@@@@CAXPEAU_RTL_GENERIC_TABLE@@PEAX@Z; FreeRoutine
0x180003f42  mov     [rsp+2C0h+TableContext], r15; TableContext
0x180003f47  lea     r8, ?AllocTableData@?$CGenericTableMap@_KVCDwmHwndData@@@@CAPEAXPEAU_RTL_GENERIC_TABLE@@K@Z; AllocateRoutine
0x180003f4e  mov     rcx, rax; Table
0x180003f51  lea     rdx, ?CompareTableData@?$CGenericTableMap@_KVCProxySurfaceElement@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z; CompareRoutine
0x180003f58  call    cs:__imp_RtlInitializeGenericTable
0x180003f5e  mov     [r14+30h], rsi
0x180003f62  jmp     loc_180003C7D
0x180003f67  mov     [r14+30h], r15
0x180003f6b  mov     edx, 81h
0x180003f70  jmp     short loc_180003F77
0x180003f72  mov     edx, 94h; unsigned int
0x180003f77  mov     ecx, 8007000Eh; int
0x180003f7c  mov     edi, ecx
0x180003f7e  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180003f83  lea     rcx, [rbp+1C0h+var_240]
0x180003f87  call    ??1?$CGuard@VCDwmCS@@@@QEAA@XZ; CGuard<CDwmCS>::~CGuard<CDwmCS>(void)
0x180003f8c  jmp     loc_180003D4E
0x180003f91  mov     [rbp+1C0h+var_1E8], r15
0x180003f95  lea     rdx, [rbp+1C0h+var_1E8]; Buffer
0x180003f99  xor     r15d, r15d
0x180003f9c  xorps   xmm0, xmm0
0x180003f9f  mov     [rbp+1C0h+var_1E0], r15
0x180003fa3  xor     r9d, r9d; NewElement
0x180003fa6  mov     [rbp+1C0h+var_1D8], r15
0x180003faa  movdqu  [rbp+1C0h+var_1D0], xmm0
0x180003faf  mov     [rbp+1C0h+var_1C0], r15b
0x180003fb3  lea     r8d, [r15+30h]; BufferSize
0x180003fb7  mov     rcx, [r14+30h]; Table
0x180003fbb  call    cs:__imp_RtlInsertElementGenericTable
0x180003fc1  mov     rsi, rax
0x180003fc4  test    rax, rax
0x180003fc7  jnz     loc_180003CCA
0x180003fcd  jmp     short loc_180003F72
0x180003fcf  cmp     cs:?g_hDXGI@@3PEAUHINSTANCE__@@EA, r15; HINSTANCE__ * g_hDXGI
0x180003fd6  movdqa  xmm0, cs:__xmm@000093000000a0000000a1000000b000
0x180003fde  movdqu  [rbp+1C0h+var_1A8], xmm0
0x180003fe3  mov     [rbp+1C0h+var_198], 9200h
0x180003fea  mov     dword ptr [rbp+1C0h+var_194], 9100h
0x180003ff1  mov     dword ptr [rsp+2C0h+var_258], r15d
0x180003ff6  jnz     short loc_18000401D
0x180003ff8  xor     ecx, ecx; dwErrCode
0x180003ffa  call    cs:__imp_SetLastError
0x180004000  lea     rcx, LibFileName; "dxgi.dll"
0x180004007  call    cs:__imp_LoadLibraryW
0x18000400d  mov     cs:?g_hDXGI@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hDXGI
0x180004014  test    rax, rax
0x180004017  jz      loc_180003E32
0x18000401d  cmp     cs:?g_hD3D@@3PEAUHINSTANCE__@@EA, r15; HINSTANCE__ * g_hD3D
0x180004024  jnz     short loc_18000404B
0x180004026  xor     ecx, ecx; dwErrCode
0x180004028  call    cs:__imp_SetLastError
0x18000402e  lea     rcx, aD3d11Dll; "d3d11.dll"
0x180004035  call    cs:__imp_LoadLibraryW
0x18000403b  mov     cs:?g_hD3D@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hD3D
0x180004042  test    rax, rax
0x180004045  jz      loc_180003E49
0x18000404b  mov     rax, cs:?g_pfnCreateDXGIFactory@@3P6AJAEBU_GUID@@PEAPEAX@ZEA; long (*g_pfnCreateDXGIFactory)(_GUID const &,void * *)
0x180004052  test    rax, rax
0x180004055  jnz     short loc_180004083
0x180004057  xor     ecx, ecx; dwErrCode
0x180004059  call    cs:__imp_SetLastError
0x18000405f  mov     rcx, cs:?g_hDXGI@@3PEAUHINSTANCE__@@EA; hModule
0x180004066  lea     rdx, ProcName; "CreateDXGIFactory"
0x18000406d  call    cs:__imp_GetProcAddress
0x180004073  mov     cs:?g_pfnCreateDXGIFactory@@3P6AJAEBU_GUID@@PEAPEAX@ZEA, rax; long (*g_pfnCreateDXGIFactory)(_GUID const &,void * *)
0x18000407a  test    rax, rax
0x18000407d  jz      loc_180003E6F
0x180004083  cmp     cs:?g_pfnD3D11CreateDevice@@3P6AJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@ZEA, r15; long (*g_pfnD3D11CreateDevice)(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)
0x18000408a  jnz     short loc_1800040BF
0x18000408c  xor     ecx, ecx; dwErrCode
0x18000408e  call    cs:__imp_SetLastError
0x180004094  mov     rcx, cs:?g_hD3D@@3PEAUHINSTANCE__@@EA; hModule
0x18000409b  lea     rdx, aD3d11createdev; "D3D11CreateDevice"
0x1800040a2  call    cs:__imp_GetProcAddress
0x1800040a8  mov     cs:?g_pfnD3D11CreateDevice@@3P6AJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@ZEA, rax; long (*g_pfnD3D11CreateDevice)(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)
0x1800040af  test    rax, rax
0x1800040b2  jz      loc_180003E95
  ... truncated ...
```
