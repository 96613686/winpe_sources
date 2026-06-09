# DwmpDxGetWindowSharedSurface

- ea: `0x180002200`
- end: `0x1800028cd`
- name: `DwmpDxGetWindowSharedSurface`
- size: `1741`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002200`
- `0x1800028e0`
- `0x180002e90`
- `0x180003370`
- `0x1800035d0`
- `0x1800035e0`
- `0x180003a90`
- `0x180003bc0`
- `0x180004300`
- `0x18000ab44`
- `0x18000be7c`
- `0x18000bf40`
- `0x18000bff4`
- `0x18000d0a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002399`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002633`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002851`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002399`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002633`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002851`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002301`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002301`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000257d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000257d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002548`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002442`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002442`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002709`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800027b5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000283e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800027b5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000283e`
- `USER32!DwmGetDxSharedSurface` at `0x180002573`
- `USER32!DwmGetDxSharedSurface` at `0x18000280b`
- `USER32!DwmGetDxSharedSurface` at `0x180002573`
- `USER32!DwmGetDxSharedSurface` at `0x18000280b`
- `USER32!IsThreadDesktopComposited` at `0x180002356`
- `USER32!IsThreadDesktopComposited` at `0x180002356`
- `GDI32!__imp_DwmQueryCompositionId` at `0x180002257`
- `GDI32!__imp_DwmQueryCompositionId` at `0x18000236f`
- `GDI32!__imp_DwmQueryCompositionId` at `0x1800026ed`
- `GDI32!__imp_DwmQueryCompositionId` at `0x18000281b`
- `GDI32!__imp_DwmQueryCompositionId` at `0x180002257`
- `GDI32!__imp_DwmQueryCompositionId` at `0x18000236f`
- `GDI32!__imp_DwmQueryCompositionId` at `0x1800026ed`
- `GDI32!__imp_DwmQueryCompositionId` at `0x18000281b`

## pseudocode

```c
__int64 __fastcall DwmpDxGetWindowSharedSurface(
        HWND a1,
        struct _LUID a2,
        HMONITOR a3,
        unsigned int a4,
        DXGI_FORMAT *a5,
        _QWORD *a6,
        _QWORD *a7)
{
  DXGI_FORMAT *v7; // r13
  __int64 v8; // r12
  int v11; // edx
  void *v12; // r14
  signed int v13; // edi
  int v14; // r13d
  struct CDwmHwndData *Element; // rax
  unsigned __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // ecx
  unsigned int v19; // eax
  int v20; // edx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // edx
  unsigned int v24; // edx
  int ProxyRedirectionSurface; // eax
  unsigned __int64 v26; // rax
  _QWORD *v27; // rcx
  signed int LastError; // eax
  int v30; // ecx
  char v31; // r13
  int updated; // eax
  unsigned int v33; // edx
  bool v34; // [rsp+40h] [rbp-B1h] BYREF
  int v35; // [rsp+44h] [rbp-ADh] BYREF
  HWND hWnd; // [rsp+48h] [rbp-A9h]
  unsigned int CompositionId; // [rsp+50h] [rbp-A1h]
  int v38; // [rsp+54h] [rbp-9Dh]
  unsigned int v39; // [rsp+58h] [rbp-99h] BYREF
  _QWORD *v40; // [rsp+60h] [rbp-91h]
  struct _LUID v41; // [rsp+68h] [rbp-89h] BYREF
  int v42; // [rsp+70h] [rbp-81h]
  void *v43; // [rsp+78h] [rbp-79h] BYREF
  DXGI_FORMAT *v44; // [rsp+80h] [rbp-71h]
  __int64 v45; // [rsp+88h] [rbp-69h] BYREF
  HANDLE hHandle; // [rsp+90h] [rbp-61h] BYREF
  unsigned __int64 v47; // [rsp+98h] [rbp-59h] BYREF
  unsigned __int64 v48; // [rsp+A0h] [rbp-51h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-49h]
  HMONITOR v50; // [rsp+B0h] [rbp-41h]
  struct _LUID v51; // [rsp+B8h] [rbp-39h]
  DXGI_FORMAT v52[8]; // [rsp+C0h] [rbp-31h] BYREF

  v7 = a5;
  v8 = 0;
  v44 = a5;
  v40 = a6;
  v38 = 0;
  v50 = a3;
  hWnd = a1;
  v51 = a2;
  v43 = 0;
  CompositionId = DwmQueryCompositionId();
  v12 = 0;
  v48 = 0;
  v41 = 0;
  v35 = 0;
  memset(v52, 0, 28);
  if ( !a5 )
  {
    v13 = -2147024809;
    DoStackCaptureDirect(-2147024809, 0x245u);
    goto LABEL_35;
  }
  if ( !a6 )
  {
    v13 = -2147024809;
    DoStackCaptureDirect(-2147024809, 0x246u);
    goto LABEL_35;
  }
  v13 = 0;
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0xxxqq_EtwEventWriteTransfer(0, v11, (_DWORD)hWnd, a2.LowPart, (char)v50, a4, *a5);
  v14 = 0;
  hHandle = 0;
  v47 = 0;
  v49 = 0;
  *v40 = 0;
  memset(v52, 0, 28);
  EnterCriticalSection(&CDwmHwndData::s_cs);
  Element = CDwmHwndData::FindElement(hWnd);
  if ( Element )
  {
    hHandle = (HANDLE)*((_QWORD *)Element + 3);
    v16 = *((_QWORD *)Element + 4);
    v49 = *((_QWORD *)Element + 5);
    v47 = v16;
  }
  LeaveCriticalSection(&CDwmHwndData::s_cs);
  while ( 1 )
  {
    ++v38;
    v17 = IsRemoteFxOpenGLWorkarondEnabled(hWnd);
    v18 = a4 & 0xFFFFFFEF;
    if ( !v17 )
      v18 = a4;
    v19 = v18 & 0x10;
    v20 = v18 & 8;
    v39 = v19;
    a4 = v18;
    v42 = v20;
    if ( (v18 & 0x10) == 0 )
    {
      v21 = 1;
      if ( v20 )
        v21 = v19;
      goto LABEL_13;
    }
    if ( (v18 & 8) != 0 )
      goto LABEL_80;
    v35 = 0;
    LODWORD(v45) = v18 & 0x80;
    if ( (v18 & 0x80) != 0 )
      v35 = 4;
    v41 = a2;
    SetLastError(0);
    if ( (unsigned int)DwmGetDxSharedSurface(hWnd, &v52[2], &v41, &v52[1], &v35, &v48) )
      break;
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( v13 >= 0 )
      v13 = -2003304445;
    DoStackCaptureDirect(v13, 0x2AAu);
LABEL_62:
    if ( IsNoDeviceBitmap(v13) )
    {
      v31 = 0;
      v34 = 1;
      if ( (unsigned __int8)((__int64 (*)(void))_____not_null_V_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_34__Z____function_wistd__YA_NAEBV_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_45__Z__Z)() )
        VistaBltTelemetryReport(4);
      goto LABEL_69;
    }
    if ( !v42 )
    {
      if ( IsNoDeviceBitmap(v30) )
        v21 = 4;
      else
        v21 = 7;
      goto LABEL_13;
    }
LABEL_80:
    v21 = 2;
LABEL_13:
    if ( (unsigned __int8)_____not_null_V_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_34__Z____function_wistd__YA_NAEBV_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_45__Z__Z(v21) )
      VistaBltTelemetryReport(v22);
    if ( !(unsigned int)IsThreadDesktopComposited() )
    {
      v14 = -2144980991;
      goto LABEL_28;
    }
    if ( (a4 & 1) != 0 )
    {
      if ( v12
        || (CompositionId = DwmQueryCompositionId(), OpenComposedEvent(CompositionId, v24, &v43), (v12 = v43) != 0) )
      {
        WaitForSingleObject(v12, 0x1Eu);
      }
      else
      {
        Sleep(0x1Eu);
      }
    }
    v52[0] = DXGI_FORMAT_R32G32B32A32_UINT|0x80000000;
    *(_QWORD *)&v52[2] = 0;
    if ( v42 )
    {
      DrawBlack(hWnd);
    }
    else if ( !v39 )
    {
      v34 = 0;
      ProxyRedirectionSurface = GetProxyRedirectionSurface(hWnd, a2, v50, a4, &v52[1], (void **)&v52[2], &v34);
      v13 = ProxyRedirectionSurface;
      if ( ProxyRedirectionSurface < 0 )
      {
        DoStackCaptureDirect(ProxyRedirectionSurface, 0x38Eu);
        goto LABEL_34;
      }
      if ( v34 )
      {
        v45 = 0;
        v39 = 0;
        v35 = 4;
        v41 = a2;
        DwmGetDxSharedSurface(hWnd, &v45, &v41, &v39, &v35, &v48);
      }
      *(_QWORD *)&v52[4] = *(_QWORD *)&v52[2] | ((_QWORD)hWnd << 32) | 0x8000000000000000uLL;
    }
    if ( v14 != -2003304299 )
      goto LABEL_28;
LABEL_86:
    if ( CompositionId == (unsigned int)DwmQueryCompositionId() )
    {
      if ( v12 )
        goto LABEL_100;
    }
    else if ( v12 )
    {
      CloseHandle(v12);
      v43 = 0;
    }
    CompositionId = DwmQueryCompositionId();
    OpenComposedEvent(CompositionId, v33, &v43);
    v12 = v43;
    if ( v43 )
LABEL_100:
      WaitForSingleObject(v12, 0x64u);
    else
      Sleep(5u);
  }
  if ( v13 < 0 )
    goto LABEL_62;
  v31 = 1;
  v34 = 0;
  if ( __PAIR64__(v51.HighPart, a2.LowPart) != v41 )
    v34 = (_DWORD)v45 == 0;
LABEL_69:
  if ( (a4 & 1) != 0 )
  {
    if ( !*(_QWORD *)&v52[2] && v31 )
      goto LABEL_85;
    if ( hHandle && v49 == *(_QWORD *)&v52[2] )
    {
      WaitForSingleObject(hHandle, 0x1Eu);
    }
    else
    {
      updated = UpdateDxBltEvent(hWnd, *(unsigned __int64 *)&v52[2], &hHandle, &v47);
      v13 = updated;
      if ( updated < 0 )
      {
        DoStackCaptureDirect(updated, 0x2DEu);
        goto LABEL_34;
      }
    }
    v26 = v47;
  }
  else
  {
    v26 = v48;
  }
  *(_QWORD *)&v52[4] = v26;
  if ( !*(_QWORD *)&v52[2] && v31 )
  {
LABEL_85:
    v14 = -2003304299;
    goto LABEL_86;
  }
  v14 = 2502661;
  v52[0] = DXGI_FORMAT_R32G32B32A32_UINT|0x80000000;
  if ( v34 )
    v14 = 2502664;
LABEL_28:
  if ( v12 )
    CloseHandle(v12);
  if ( v14 < 0 )
  {
LABEL_33:
    v13 = v14;
    goto LABEL_34;
  }
  if ( v52[0] == (DXGI_FORMAT_R32G32B32A32_UINT|0x80000000) )
  {
    v8 = *(_QWORD *)&v52[4];
    *v40 = *(_QWORD *)&v52[2];
    *v44 = v52[1];
    goto LABEL_33;
  }
  v13 = -2147418113;
  DoStackCaptureDirect(-2147418113, 0x3E1u);
LABEL_34:
  v7 = v44;
LABEL_35:
  if ( a7 )
    *a7 = v8;
  if ( v13 > -2003304300 )
  {
    if ( v13 == -2003304299 )
      goto LABEL_50;
    if ( v13 != -2003304290 )
    {
      if ( v13 != -2003292404 )
        goto LABEL_42;
      goto LABEL_50;
    }
    v13 = -2144980987;
    goto LABEL_43;
  }
  if ( v13 == -2003304300 || v13 == -2003304304 || v13 == -2003304303 || v13 == -2003304302 )
    goto LABEL_50;
LABEL_42:
  if ( v13 >= 0 || v13 == -2144980991 )
  {
LABEL_43:
    v27 = v40;
    goto LABEL_44;
  }
  if ( v13 == -2144980987 )
  {
    v27 = v40;
    goto LABEL_44;
  }
LABEL_50:
  v27 = v40;
  v13 = 0;
  if ( v40 )
    *v40 = 0;
LABEL_44:
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0xqxxqq_EtwEventWriteTransfer((_DWORD)v27, v23, (_DWORD)hWnd, v13, *v27, v8, *v7, v38);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180002200  push    rbp
0x180002202  push    rbx
0x180002203  push    rsi
0x180002204  push    rdi
0x180002205  push    r12
0x180002207  push    r13
0x180002209  push    r14
0x18000220b  push    r15
0x18000220d  lea     rbp, [rsp-7]
0x180002212  sub     rsp, 0F8h
0x180002219  mov     rax, cs:__security_cookie
0x180002220  xor     rax, rsp
0x180002223  mov     [rbp+3Fh+var_50], rax
0x180002227  mov     r13, [rbp+3Fh+arg_20]
0x18000222b  xor     r12d, r12d
0x18000222e  mov     rdi, [rbp+3Fh+arg_28]
0x180002232  mov     r15d, r9d
0x180002235  mov     rsi, [rbp+3Fh+arg_30]
0x180002239  mov     rbx, rdx
0x18000223c  mov     [rbp+3Fh+var_B0], r13
0x180002240  mov     [rsp+130h+var_D0], rdi
0x180002245  mov     [rsp+130h+var_DC], r12d
0x18000224a  mov     [rbp+3Fh+var_80], r8
0x18000224e  mov     [rsp+130h+hWnd], rcx
0x180002253  mov     [rbp+3Fh+var_78], rdx
0x180002257  call    cs:__imp_DwmQueryCompositionId
0x18000225d  mov     [rbp+3Fh+var_B8], r12
0x180002261  xorps   xmm0, xmm0
0x180002264  mov     [rsp+130h+var_E0], eax
0x180002268  mov     r14d, r12d
0x18000226b  mov     [rbp+3Fh+var_90], r12
0x18000226f  mov     [rsp+130h+var_C8], r12
0x180002274  mov     [rsp+130h+var_EC], r12d
0x180002279  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x18000227d  movups  xmmword ptr [rbp+3Fh+var_70+0Ch], xmm0
0x180002281  test    r13, r13
0x180002284  jz      loc_18000250D
0x18000228a  test    rdi, rdi
0x18000228d  jz      loc_18000274F
0x180002293  xor     ecx, ecx
0x180002295  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x18000229c  mov     edi, ecx
0x18000229e  jnz     loc_180002765
0x1800022a4  mov     rax, [rsp+130h+var_D0]
0x1800022a9  xorps   xmm0, xmm0
0x1800022ac  mov     r13d, ecx
0x1800022af  mov     [rbp+3Fh+hHandle], rcx
0x1800022b3  mov     [rbp+3Fh+var_98], rcx
0x1800022b7  mov     [rbp+3Fh+var_88], rcx
0x1800022bb  mov     [rax], rcx
0x1800022be  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; lpCriticalSection
0x1800022c5  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x1800022c9  movups  xmmword ptr [rbp+3Fh+var_70+0Ch], xmm0
0x1800022cd  call    cs:__imp_EnterCriticalSection
0x1800022d3  mov     rcx, [rsp+130h+hWnd]; HWND
0x1800022d8  call    ?FindElement@CDwmHwndData@@SAPEAV1@PEAUHWND__@@@Z; CDwmHwndData::FindElement(HWND__ *)
0x1800022dd  test    rax, rax
0x1800022e0  jz      short loc_1800022FA
0x1800022e2  mov     rcx, [rax+18h]
0x1800022e6  mov     [rbp+3Fh+hHandle], rcx
0x1800022ea  mov     rcx, [rax+20h]
0x1800022ee  mov     rax, [rax+28h]
0x1800022f2  mov     [rbp+3Fh+var_88], rax
0x1800022f6  mov     [rbp+3Fh+var_98], rcx
0x1800022fa  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; lpCriticalSection
0x180002301  call    cs:__imp_LeaveCriticalSection
0x180002307  mov     rcx, [rsp+130h+hWnd]; hWnd
0x18000230c  inc     [rsp+130h+var_DC]
0x180002310  call    ?IsRemoteFxOpenGLWorkarondEnabled@@YAHPEAUHWND__@@@Z; IsRemoteFxOpenGLWorkarondEnabled(HWND__ *)
0x180002315  mov     ecx, r15d
0x180002318  and     ecx, 0FFFFFFEFh
0x18000231b  test    eax, eax
0x18000231d  cmovz   ecx, r15d
0x180002321  mov     eax, ecx
0x180002323  mov     edx, ecx
0x180002325  and     eax, 10h
0x180002328  and     edx, 8
0x18000232b  mov     [rsp+130h+var_D8], eax
0x18000232f  mov     r15d, ecx
0x180002332  mov     [rsp+130h+var_C0], edx
0x180002336  test    eax, eax
0x180002338  jnz     loc_180002523
0x18000233e  test    edx, edx
0x180002340  mov     ecx, 1
0x180002345  cmovnz  ecx, eax
0x180002348  call    ??$__not_null@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@@__function@wistd@@YA_NAEBV_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@45@@Z@@Z; wistd::__function::__not_null<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_>(`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_ const &)
0x18000234d  test    al, al
0x18000234f  jz      short loc_180002356
0x180002351  call    ?VistaBltTelemetryReport@@YAXW4VistaBltReason@@@Z; VistaBltTelemetryReport(VistaBltReason)
0x180002356  call    cs:__imp_IsThreadDesktopComposited
0x18000235c  test    eax, eax
0x18000235e  jz      loc_1800026BF
0x180002364  test    r15b, 1
0x180002368  jz      short loc_18000239F
0x18000236a  test    r14, r14
0x18000236d  jnz     short loc_180002391
0x18000236f  call    cs:__imp_DwmQueryCompositionId
0x180002375  mov     ecx, eax; unsigned int
0x180002377  mov     [rsp+130h+var_E0], eax
0x18000237b  lea     r8, [rbp+3Fh+var_B8]; void **
0x18000237f  call    ?OpenComposedEvent@@YAJIKPEAPEAX@Z; OpenComposedEvent(uint,ulong,void * *)
0x180002384  mov     r14, [rbp+3Fh+var_B8]
0x180002388  test    r14, r14
0x18000238b  jz      loc_1800027B0
0x180002391  mov     edx, 1Eh; dwMilliseconds
0x180002396  mov     rcx, r14; hHandle
0x180002399  call    cs:__imp_WaitForSingleObject
0x18000239f  mov     [rbp+3Fh+var_70], 80000003h
0x1800023a6  mov     qword ptr [rbp+3Fh+var_70+8], r12
0x1800023aa  cmp     [rsp+130h+var_C0], r12d
0x1800023af  jnz     loc_1800027C0
0x1800023b5  cmp     [rsp+130h+var_D8], r12d
0x1800023ba  jnz     loc_18000266B
0x1800023c0  mov     r8, [rbp+3Fh+var_80]; HMONITOR
0x1800023c4  lea     rax, [rsp+130h+var_F0]
0x1800023c9  mov     rcx, [rsp+130h+hWnd]; HWND
0x1800023ce  mov     r9d, r15d; unsigned int
0x1800023d1  mov     [rsp+130h+var_100], rax; bool *
0x1800023d6  mov     rdx, rbx; struct _LUID
0x1800023d9  lea     rax, [rbp+3Fh+var_70+8]
0x1800023dd  mov     [rsp+130h+var_F0], r12b
0x1800023e2  mov     [rsp+130h+var_108], rax; void **
0x1800023e7  lea     rax, [rbp+3Fh+var_70+4]
0x1800023eb  mov     [rsp+130h+var_110], rax; enum DXGI_FORMAT *
0x1800023f0  call    ?GetProxyRedirectionSurface@@YAJPEAUHWND__@@U_LUID@@PEAUHMONITOR__@@KPEAW4DXGI_FORMAT@@PEAPEAXPEA_N@Z; GetProxyRedirectionSurface(HWND__ *,_LUID,HMONITOR__ *,ulong,DXGI_FORMAT *,void * *,bool *)
0x1800023f5  mov     edi, eax
0x1800023f7  test    eax, eax
0x1800023f9  jns     loc_180002642
0x1800023ff  mov     edx, 38Eh; unsigned int
0x180002404  mov     ecx, eax; int
0x180002406  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18000240b  jmp     short loc_180002476
0x18000240d  mov     rax, [rbp+3Fh+var_90]
0x180002411  mov     [rbp+3Fh+var_60], rax
0x180002415  cmp     qword ptr [rbp+3Fh+var_70+8], r12
0x180002419  jz      loc_1800026DE
0x18000241f  cmp     [rsp+130h+var_F0], r12b
0x180002424  mov     eax, 263008h
0x180002429  mov     r13d, 263005h
0x18000242f  mov     [rbp+3Fh+var_70], 80000003h
0x180002436  cmovnz  r13d, eax
0x18000243a  test    r14, r14
0x18000243d  jz      short loc_180002448
0x18000243f  mov     rcx, r14; hObject
0x180002442  call    cs:__imp_CloseHandle
0x180002448  test    r13d, r13d
0x18000244b  js      short loc_180002473
0x18000244d  cmp     [rbp+3Fh+var_70], 80000003h
0x180002454  jnz     loc_18000285C
0x18000245a  mov     rcx, [rsp+130h+var_D0]
0x18000245f  mov     rax, qword ptr [rbp+3Fh+var_70+8]
0x180002463  mov     r12, [rbp+3Fh+var_60]
0x180002467  mov     [rcx], rax
0x18000246a  mov     rcx, [rbp+3Fh+var_B0]
0x18000246e  mov     eax, [rbp+3Fh+var_70+4]
0x180002471  mov     [rcx], eax
0x180002473  mov     edi, r13d
0x180002476  mov     r13, [rbp+3Fh+var_B0]
0x18000247a  test    rsi, rsi
0x18000247d  jz      short loc_180002482
0x18000247f  mov     [rsi], r12
0x180002482  cmp     edi, 88980094h
0x180002488  jg      short loc_1800024E0
0x18000248a  jz      short loc_1800024FC
0x18000248c  cmp     edi, 88980090h
0x180002492  jz      short loc_1800024FC
0x180002494  cmp     edi, 88980091h
0x18000249a  jz      short loc_1800024FC
0x18000249c  cmp     edi, 88980092h
0x1800024a2  jz      short loc_1800024FC
0x1800024a4  test    edi, edi
0x1800024a6  js      loc_180002872
0x1800024ac  mov     rcx, [rsp+130h+var_D0]
0x1800024b1  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x1800024b8  jnz     loc_18000289E
0x1800024be  mov     eax, edi
0x1800024c0  mov     rcx, [rbp+3Fh+var_50]
0x1800024c4  xor     rcx, rsp; StackCookie
0x1800024c7  call    __security_check_cookie
0x1800024cc  add     rsp, 0F8h
0x1800024d3  pop     r15
0x1800024d5  pop     r14
0x1800024d7  pop     r13
0x1800024d9  pop     r12
0x1800024db  pop     rdi
0x1800024dc  pop     rsi
0x1800024dd  pop     rbx
0x1800024de  pop     rbp
0x1800024df  retn
0x1800024e0  cmp     edi, 88980095h
0x1800024e6  jz      short loc_1800024FC
0x1800024e8  cmp     edi, 8898009Eh
0x1800024ee  jz      loc_180002894
0x1800024f4  cmp     edi, 88982F0Ch
0x1800024fa  jnz     short loc_1800024A4
0x1800024fc  mov     rcx, [rsp+130h+var_D0]
0x180002501  xor     edi, edi
0x180002503  test    rcx, rcx
0x180002506  jz      short loc_1800024B1
0x180002508  mov     [rcx], rdi
0x18000250b  jmp     short loc_1800024B1
0x18000250d  mov     edi, 80070057h
0x180002512  mov     edx, 245h; unsigned int
0x180002517  mov     ecx, edi; int
0x180002519  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18000251e  jmp     loc_18000247A
0x180002523  test    edx, edx
0x180002525  jnz     loc_18000268C
0x18000252b  mov     eax, r15d
0x18000252e  mov     [rsp+130h+var_EC], r12d
0x180002533  and     eax, 80h
0x180002538  mov     dword ptr [rbp+3Fh+var_A8], eax
0x18000253b  jnz     loc_18000278F
0x180002541  xor     ecx, ecx; dwErrCode
0x180002543  mov     [rsp+130h+var_C8], rbx
0x180002548  call    cs:__imp_SetLastError
0x18000254e  mov     rcx, [rsp+130h+hWnd]
0x180002553  lea     rax, [rbp+3Fh+var_90]
0x180002557  mov     [rsp+130h+var_108], rax
0x18000255c  lea     r9, [rbp+3Fh+var_70+4]
0x180002560  lea     rax, [rsp+130h+var_EC]
0x180002565  lea     r8, [rsp+130h+var_C8]
0x18000256a  mov     [rsp+130h+var_110], rax
0x18000256f  lea     rdx, [rbp+3Fh+var_70+8]
0x180002573  call    cs:__imp_DwmGetDxSharedSurface
0x180002579  test    eax, eax
0x18000257b  jnz     short loc_1800025E2
0x18000257d  call    cs:__imp_GetLastError
0x180002583  mov     edi, eax
0x180002585  test    eax, eax
0x180002587  jle     short loc_180002592
0x180002589  movzx   edi, ax
0x18000258c  or      edi, 80070000h
0x180002592  test    edi, edi
0x180002594  mov     eax, 88980003h
0x180002599  mov     edx, 2AAh; unsigned int
0x18000259e  cmovns  edi, eax
0x1800025a1  mov     ecx, edi; int
0x1800025a3  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x1800025a8  mov     ecx, edi; int
0x1800025aa  call    ?IsNoDeviceBitmap@@YA_NJ@Z; IsNoDeviceBitmap(long)
0x1800025af  test    al, al
0x1800025b1  jnz     loc_180002723
0x1800025b7  mov     edx, [rsp+130h+var_C0]
0x1800025bb  test    edx, edx
0x1800025bd  jnz     loc_18000268C
0x1800025c3  test    edi, edi
0x1800025c5  jns     loc_1800027A6
0x1800025cb  call    ?IsNoDeviceBitmap@@YA_NJ@Z; IsNoDeviceBitmap(long)
0x1800025d0  test    al, al
0x1800025d2  jnz     loc_18000279C
0x1800025d8  mov     ecx, 7
0x1800025dd  jmp     loc_180002348
0x1800025e2  test    edi, edi
0x1800025e4  js      short loc_1800025A8
0x1800025e6  mov     r13b, 1
0x1800025e9  mov     [rsp+130h+var_F0], r12b
0x1800025ee  cmp     ebx, dword ptr [rsp+130h+var_C8]
0x1800025f2  jnz     loc_1800026CA
0x1800025f8  mov     eax, dword ptr [rbp+3Fh+var_78+4]
0x1800025fb  cmp     eax, dword ptr [rsp+130h+var_C8+4]
0x1800025ff  jnz     loc_1800026CA
0x180002605  test    r15b, 1
0x180002609  jz      loc_18000240D
0x18000260f  mov     rdx, qword ptr [rbp+3Fh+var_70+8]; unsigned __int64
0x180002613  test    rdx, rdx
0x180002616  jz      loc_180002718
0x18000261c  mov     rax, [rbp+3Fh+hHandle]
0x180002620  test    rax, rax
0x180002623  jz      short loc_180002696
0x180002625  cmp     [rbp+3Fh+var_88], rdx
0x180002629  jnz     short loc_180002696
0x18000262b  mov     edx, 1Eh; dwMilliseconds
0x180002630  mov     rcx, rax; hHandle
0x180002633  call    cs:__imp_WaitForSingleObject
0x180002639  mov     rax, [rbp+3Fh+var_98]
0x18000263d  jmp     loc_180002411
0x180002642  cmp     [rsp+130h+var_F0], r12b
0x180002647  jnz     loc_1800027CF
0x18000264d  mov     rax, [rsp+130h+hWnd]
0x180002652  mov     rcx, 8000000000000000h
0x18000265c  shl     rax, 20h
0x180002660  or      rax, qword ptr [rbp+3Fh+var_70+8]
0x180002664  or      rax, rcx
0x180002667  mov     [rbp+3Fh+var_60], rax
0x18000266b  cmp     r13d, 88980095h
0x180002672  jz      short loc_1800026ED
0x180002674  cmp     r13d, 8898009Ah
0x18000267b  jnz     loc_18000243A
0x180002681  mov     r13d, 80263007h
0x180002687  jmp     loc_18000243A
0x18000268c  mov     ecx, 2
0x180002691  jmp     loc_180002348
0x180002696  mov     rcx, [rsp+130h+hWnd]; HWND
0x18000269b  lea     r9, [rbp+3Fh+var_98]; unsigned __int64 *
0x18000269f  lea     r8, [rbp+3Fh+hHandle]; void **
0x1800026a3  call    ?UpdateDxBltEvent@@YAJPEAUHWND__@@_KPEAPEAXPEA_K@Z; UpdateDxBltEvent(HWND__ *,unsigned __int64,void * *,unsigned __int64 *)
0x1800026a8  mov     edi, eax
0x1800026aa  test    eax, eax
0x1800026ac  jns     short loc_180002639
  ... truncated ...
```
