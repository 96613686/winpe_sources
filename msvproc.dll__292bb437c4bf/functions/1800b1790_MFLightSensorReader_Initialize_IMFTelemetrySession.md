# MFLightSensorReader::Initialize(IMFTelemetrySession *)

- ea: `0x1800b1790`
- end: `0x1800b1ebe`
- name: `?Initialize@MFLightSensorReader@@QEAAJPEAUIMFTelemetrySession@@@Z`
- size: `1838`
- prototype: `__int64 __fastcall(MFLightSensorReader *__hidden this, struct IMFTelemetrySession *)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180011a8c`
- `0x1800244c4`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x1800124bc`
- `0x180025b08`
- `0x18003639c`
- `0x1800364d0`
- `0x18003ce50`
- `0x180054140`
- `0x18006723c`
- `0x1800b12bc`
- `0x1800b1790`
- `0x1800b28f0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b18b0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b18b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b18d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b19c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1a85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1b57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1bfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1d23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1dd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b18d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b19c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1a85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1b57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1bfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1d23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1dd3`

## string_xrefs

- `0x1800b17d1`: `MFLightSensorReader::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MFLightSensorReader::Initialize(MFLightSensorReader *this, struct IMFTelemetrySession *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int64 v6; // rbx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r14
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 (__fastcall *v15)(__int64, char *); // rbx
  _QWORD *v16; // rdi
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  char *v26; // rax
  __int64 v27; // rcx
  _QWORD *v28; // rdx
  __int64 v29; // rcx
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  unsigned int v36; // ebx
  int ActivationFactory; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v39[4]; // [rsp+34h] [rbp-25h] BYREF
  __int64 v40; // [rsp+38h] [rbp-21h] BYREF
  struct IMFTelemetrySession *v41; // [rsp+40h] [rbp-19h] BYREF
  char v42; // [rsp+48h] [rbp-11h] BYREF
  _QWORD v43[2]; // [rsp+50h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  __int64 v45; // [rsp+78h] [rbp+1Fh]

  v41 = a2;
  ActivationFactory = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v39, "MFLightSensorReader::Initialize", 14);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 3) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 296LL))(*((_QWORD *)this + 3));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 3) + 280LL))(
                                                            *((_QWORD *)this + 3),
                                                            v43);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
  }
  v43[0] = this;
  v43[1] = &ActivationFactory;
  Microsoft::WRL::ComPtr<IMFTelemetrySession>::operator=((char *)this + 24, a2);
  *(_OWORD *)((char *)this + 40) = *(_OWORD *)&LightValueRanges;
  *(_OWORD *)((char *)this + 56) = xmmword_18013FFC0;
  *((_DWORD *)this + 18) = 100000;
  v45 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Devices.Sensors.LightSensor",
    0x24u,
    0x23u);
  v6 = v45;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 8);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_45db8c84_c3a8_471e_9a53_6457fad87c0e, (char *)this + 8);
  v45 = 0;
  if ( ActivationFactory >= 0 )
  {
    v11 = *((_QWORD *)this + 1);
    if ( v11 )
    {
      v15 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v11 + 48LL);
      v16 = (_QWORD *)((char *)this + 16);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 16);
      ActivationFactory = v15(v11, (char *)this + 16);
      if ( ActivationFactory >= 0 )
      {
        if ( *v16 )
        {
          ActivationFactory = MFLightSensorReader::SetMinimumReportInterval(this);
          if ( ActivationFactory >= 0 )
          {
            v26 = (char *)Microsoft::WRL::Details::Make<LightReadingChangedListener,IMFTelemetrySession * &>(&v40, &v41);
            v27 = 0;
            if ( &v42 != v26 )
            {
              v27 = *(_QWORD *)v26;
              *(_QWORD *)v26 = 0;
            }
            v28 = *(_QWORD **)this;
            *(_QWORD *)this = v27;
            if ( v28 )
              (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
            v29 = v40;
            if ( v40 )
            {
              v40 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            }
            if ( *(_QWORD *)this )
            {
              ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(*(_QWORD *)*v16 + 80LL))(
                                    *v16,
                                    *(_QWORD *)this,
                                    (char *)this + 32);
              if ( ActivationFactory >= 0 )
              {
                if ( (unsigned __int8)byte_180153DE0 >= 8u )
                  WPP_SF_q(
                    *((_QWORD *)WPP_GLOBAL_Control + 42),
                    21,
                    &WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids,
                    this);
                MFLightSensorReader::readOEMLevels(this);
              }
              else
              {
                v33 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v34;
                  if ( v34
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
                  {
                    v33 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v33 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v33 + 8) )
                {
                  v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                  if ( ActivationFactory < 0 && *((_DWORD *)v35 + 499) != ActivationFactory )
                    CallStackContext::TraceFailure(v35, "MFLightSensorReader::Initialize", 44, ActivationFactory);
                }
                if ( g_wppLevels )
                {
                  v10 = 20;
                  goto LABEL_16;
                }
              }
            }
            else
            {
              if ( (unsigned __int8)byte_180153DE0 >= 8u )
                WPP_SF_qq(
                  *((_QWORD *)WPP_GLOBAL_Control + 42),
                  18,
                  &WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids,
                  this,
                  0);
              ActivationFactory = -2147024882;
              v30 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v31;
                if ( v31
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                {
                  v30 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v30 = &qword_180153440;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                }
              }
              if ( *((_BYTE *)v30 + 8) )
              {
                v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                if ( ActivationFactory < 0 && *((_DWORD *)v32 + 499) != ActivationFactory )
                  CallStackContext::TraceFailure(v32, "MFLightSensorReader::Initialize", 41, ActivationFactory);
              }
              if ( g_wppLevels )
              {
                v10 = 19;
                goto LABEL_16;
              }
            }
          }
          else
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v24;
              if ( v24
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
              {
                v23 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v23 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v23 + 8) )
            {
              v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
              if ( ActivationFactory < 0 && *((_DWORD *)v25 + 499) != ActivationFactory )
                CallStackContext::TraceFailure(v25, "MFLightSensorReader::Initialize", 34, ActivationFactory);
            }
            if ( g_wppLevels )
            {
              v10 = 17;
              goto LABEL_16;
            }
          }
        }
        else
        {
          if ( (unsigned __int8)byte_180153DE0 >= 8u )
            WPP_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              15,
              &WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids,
              this,
              0);
          ActivationFactory = -2147024882;
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( ActivationFactory < 0 && *((_DWORD *)v22 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v22, "MFLightSensorReader::Initialize", 31, ActivationFactory);
          }
          if ( g_wppLevels )
          {
            v10 = 16;
            goto LABEL_16;
          }
        }
      }
      else
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( ActivationFactory < 0 && *((_DWORD *)v19 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v19, "MFLightSensorReader::Initialize", 27, ActivationFactory);
        }
        if ( g_wppLevels )
        {
          v10 = 14;
          goto LABEL_16;
        }
      }
    }
    else
    {
      if ( (unsigned __int8)byte_180153DE0 >= 8u )
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 42), 12, &WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids, this, 0);
      ActivationFactory = -2147024882;
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( ActivationFactory < 0 && *((_DWORD *)v14 + 499) != ActivationFactory )
          CallStackContext::TraceFailure(v14, "MFLightSensorReader::Initialize", 24, ActivationFactory);
      }
      if ( g_wppLevels )
      {
        v10 = 13;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( ActivationFactory < 0 && *((_DWORD *)v9 + 499) != ActivationFactory )
        CallStackContext::TraceFailure(v9, "MFLightSensorReader::Initialize", 20, ActivationFactory);
    }
    if ( g_wppLevels )
    {
      v10 = 11;
LABEL_16:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids,
        this,
        ActivationFactory);
    }
  }
  v36 = ActivationFactory;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v39);
  return v36;
}

```

## disassembly

```asm
0x1800b1790  mov     [rsp-8+arg_10], rbx
0x1800b1795  mov     [rsp-8+arg_18], rsi
0x1800b179a  push    rbp
0x1800b179b  push    rdi
0x1800b179c  push    r12
0x1800b179e  push    r14
0x1800b17a0  push    r15
0x1800b17a2  lea     rbp, [rsp-37h]
0x1800b17a7  sub     rsp, 90h
0x1800b17ae  mov     rax, cs:__security_cookie
0x1800b17b5  xor     rax, rsp
0x1800b17b8  mov     [rbp+57h+var_30], rax
0x1800b17bc  mov     r14, rdx
0x1800b17bf  mov     rsi, rcx
0x1800b17c2  mov     [rbp+57h+var_70], rdx
0x1800b17c6  xor     r15d, r15d
0x1800b17c9  mov     [rbp+57h+var_80], r15d
0x1800b17cd  lea     r8d, [r15+0Eh]; int
0x1800b17d1  lea     r12, aMflightsensorr_1; "MFLightSensorReader::Initialize"
0x1800b17d8  mov     rdx, r12; char *
0x1800b17db  lea     rcx, [rbp+57h+var_7C]; this
0x1800b17df  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b17e4  nop
0x1800b17e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b17ec  cmp     [rcx+8], r15b
0x1800b17f0  jz      short loc_1800B183D
0x1800b17f2  cmp     [rsi+18h], r15
0x1800b17f6  jz      short loc_1800B183D
0x1800b17f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b17fd  mov     rdi, rax
0x1800b1800  mov     rcx, [rsi+18h]
0x1800b1804  mov     rdx, [rcx]
0x1800b1807  mov     rax, [rdx+128h]
0x1800b180e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1813  mov     ebx, eax
0x1800b1815  mov     rcx, [rsi+18h]
0x1800b1819  mov     rdx, [rcx]
0x1800b181c  mov     rax, [rdx+118h]
0x1800b1823  lea     rdx, [rbp+57h+var_60]
0x1800b1827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b182c  movups  xmm0, xmmword ptr [rax]
0x1800b182f  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800b1837  mov     [rdi+7E0h], ebx
0x1800b183d  mov     [rbp+57h+var_60], rsi
0x1800b1841  lea     rax, [rbp+57h+var_80]
0x1800b1845  mov     [rbp+57h+var_58], rax
0x1800b1849  lea     rcx, [rsi+18h]
0x1800b184d  mov     rdx, r14
0x1800b1850  call    ??4?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFTelemetrySession@@@Z; Microsoft::WRL::ComPtr<IMFTelemetrySession>::operator=(IMFTelemetrySession *)
0x1800b1855  movups  xmm0, cs:?LightValueRanges@@3QBIB; uint const near * const LightValueRanges
0x1800b185c  movups  xmmword ptr [rsi+28h], xmm0
0x1800b1860  movups  xmm1, cs:xmmword_18013FFC0
0x1800b1867  movups  xmmword ptr [rsi+38h], xmm1
0x1800b186b  mov     eax, cs:dword_18013FFD0
0x1800b1871  mov     [rsi+48h], eax
0x1800b1874  lea     r14, [rsi+8]
0x1800b1878  mov     [rbp+57h+var_38], r15
0x1800b187c  mov     r9d, 23h ; '#'; unsigned int
0x1800b1882  lea     r8d, [r9+1]; unsigned int
0x1800b1886  lea     rdx, ?RuntimeClass_Windows_Devices_Sensors_LightSensor@@3QBGB; "Windows.Devices.Sensors.LightSensor"
0x1800b188d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800b1891  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b1896  nop
0x1800b1897  mov     rbx, [rbp+57h+var_38]
0x1800b189b  mov     rcx, r14
0x1800b189e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b18a3  mov     r8, r14
0x1800b18a6  lea     rdx, _GUID_45db8c84_c3a8_471e_9a53_6457fad87c0e
0x1800b18ad  mov     rcx, rbx
0x1800b18b0  call    cs:__imp_RoGetActivationFactory
0x1800b18b6  nop
0x1800b18b7  mov     [rbp+57h+var_80], eax
0x1800b18ba  mov     [rbp+57h+var_38], r15
0x1800b18be  test    eax, eax
0x1800b18c0  jns     loc_1800B1979
0x1800b18c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b18cd  test    rcx, rcx
0x1800b18d0  jnz     short loc_1800B1913
0x1800b18d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b18d8  mov     rcx, rax
0x1800b18db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b18e2  test    rax, rax
0x1800b18e5  jz      short loc_1800B1905
0x1800b18e7  mov     rax, [rax]
0x1800b18ea  mov     edx, 7F0h
0x1800b18ef  mov     rax, [rax+8]
0x1800b18f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b18f8  test    eax, eax
0x1800b18fa  jz      short loc_1800B1905
0x1800b18fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1903  jmp     short loc_1800B1913
0x1800b1905  lea     rcx, qword_180153440; this
0x1800b190c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1913  cmp     [rcx+8], r15b
0x1800b1917  jz      short loc_1800B1941
0x1800b1919  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b191e  mov     r9d, [rbp+57h+var_80]; int
0x1800b1922  test    r9d, r9d
0x1800b1925  jns     short loc_1800B1941
0x1800b1927  cmp     [rax+7CCh], r9d
0x1800b192e  jz      short loc_1800B1941
0x1800b1930  mov     r8d, 14h; int
0x1800b1936  mov     rdx, r12; char *
0x1800b1939  mov     rcx, rax; this
0x1800b193c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b1941  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b1948  jb      loc_1800B1E88
0x1800b194e  mov     edx, 0Bh
0x1800b1953  mov     eax, [rbp+57h+var_80]
0x1800b1956  mov     dword ptr [rsp+0B0h+var_90], eax
0x1800b195a  mov     r9, rsi
0x1800b195d  lea     r8, WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids
0x1800b1964  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b196b  mov     rcx, [rcx+10h]
0x1800b196f  call    WPP_SF_qD
0x1800b1974  jmp     loc_1800B1E88
0x1800b1979  mov     r14, [r14]
0x1800b197c  test    r14, r14
0x1800b197f  jnz     loc_1800B1A4D
0x1800b1985  cmp     cs:byte_180153DE0, 8
0x1800b198c  jb      short loc_1800B19B4
0x1800b198e  lea     edx, [r14+0Ch]
0x1800b1992  mov     [rsp+0B0h+var_90], r15
0x1800b1997  mov     r9, rsi
0x1800b199a  lea     r8, WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids
0x1800b19a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b19a8  mov     rcx, [rcx+150h]
0x1800b19af  call    WPP_SF_qq
0x1800b19b4  mov     [rbp+57h+var_80], 8007000Eh
0x1800b19bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b19c2  test    rcx, rcx
0x1800b19c5  jnz     short loc_1800B1A08
0x1800b19c7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b19cd  mov     rcx, rax
0x1800b19d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b19d7  test    rax, rax
0x1800b19da  jz      short loc_1800B19FA
0x1800b19dc  mov     rax, [rax]
0x1800b19df  mov     edx, 7F0h
0x1800b19e4  mov     rax, [rax+8]
0x1800b19e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b19ed  test    eax, eax
0x1800b19ef  jz      short loc_1800B19FA
0x1800b19f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b19f8  jmp     short loc_1800B1A08
0x1800b19fa  lea     rcx, qword_180153440; this
0x1800b1a01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1a08  cmp     [rcx+8], r15b
0x1800b1a0c  jz      short loc_1800B1A36
0x1800b1a0e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1a13  mov     r9d, [rbp+57h+var_80]; int
0x1800b1a17  test    r9d, r9d
0x1800b1a1a  jns     short loc_1800B1A36
0x1800b1a1c  cmp     [rax+7CCh], r9d
0x1800b1a23  jz      short loc_1800B1A36
0x1800b1a25  mov     r8d, 18h; int
0x1800b1a2b  mov     rdx, r12; char *
0x1800b1a2e  mov     rcx, rax; this
0x1800b1a31  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b1a36  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b1a3d  jb      loc_1800B1E88
0x1800b1a43  mov     edx, 0Dh
0x1800b1a48  jmp     loc_1800B1953
0x1800b1a4d  mov     rax, [r14]
0x1800b1a50  mov     rbx, [rax+30h]
0x1800b1a54  lea     rdi, [rsi+10h]
0x1800b1a58  mov     rcx, rdi
0x1800b1a5b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b1a60  mov     rdx, rdi
0x1800b1a63  mov     rcx, r14
0x1800b1a66  mov     rax, rbx
0x1800b1a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1a6e  mov     [rbp+57h+var_80], eax
0x1800b1a71  test    eax, eax
0x1800b1a73  jns     loc_1800B1B0B
0x1800b1a79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1a80  test    rcx, rcx
0x1800b1a83  jnz     short loc_1800B1AC6
0x1800b1a85  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b1a8b  mov     rcx, rax
0x1800b1a8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1a95  test    rax, rax
0x1800b1a98  jz      short loc_1800B1AB8
0x1800b1a9a  mov     rax, [rax]
0x1800b1a9d  mov     edx, 7F0h
0x1800b1aa2  mov     rax, [rax+8]
0x1800b1aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1aab  test    eax, eax
0x1800b1aad  jz      short loc_1800B1AB8
0x1800b1aaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1ab6  jmp     short loc_1800B1AC6
0x1800b1ab8  lea     rcx, qword_180153440; this
0x1800b1abf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1ac6  cmp     [rcx+8], r15b
0x1800b1aca  jz      short loc_1800B1AF4
0x1800b1acc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1ad1  mov     r9d, [rbp+57h+var_80]; int
0x1800b1ad5  test    r9d, r9d
0x1800b1ad8  jns     short loc_1800B1AF4
0x1800b1ada  cmp     [rax+7CCh], r9d
0x1800b1ae1  jz      short loc_1800B1AF4
0x1800b1ae3  mov     r8d, 1Bh; int
0x1800b1ae9  mov     rdx, r12; char *
0x1800b1aec  mov     rcx, rax; this
0x1800b1aef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b1af4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b1afb  jb      loc_1800B1E88
0x1800b1b01  mov     edx, 0Eh
0x1800b1b06  jmp     loc_1800B1953
0x1800b1b0b  cmp     [rdi], r15
0x1800b1b0e  jnz     loc_1800B1BDD
0x1800b1b14  cmp     cs:byte_180153DE0, 8
0x1800b1b1b  jb      short loc_1800B1B44
0x1800b1b1d  mov     edx, 0Fh
0x1800b1b22  mov     [rsp+0B0h+var_90], r15
0x1800b1b27  mov     r9, rsi
0x1800b1b2a  lea     r8, WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids
0x1800b1b31  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1b38  mov     rcx, [rcx+150h]
0x1800b1b3f  call    WPP_SF_qq
0x1800b1b44  mov     [rbp+57h+var_80], 8007000Eh
0x1800b1b4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1b52  test    rcx, rcx
0x1800b1b55  jnz     short loc_1800B1B98
0x1800b1b57  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b1b5d  mov     rcx, rax
0x1800b1b60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1b67  test    rax, rax
0x1800b1b6a  jz      short loc_1800B1B8A
0x1800b1b6c  mov     rax, [rax]
0x1800b1b6f  mov     edx, 7F0h
0x1800b1b74  mov     rax, [rax+8]
0x1800b1b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1b7d  test    eax, eax
0x1800b1b7f  jz      short loc_1800B1B8A
0x1800b1b81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1b88  jmp     short loc_1800B1B98
0x1800b1b8a  lea     rcx, qword_180153440; this
0x1800b1b91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1b98  cmp     [rcx+8], r15b
0x1800b1b9c  jz      short loc_1800B1BC6
0x1800b1b9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1ba3  mov     r9d, [rbp+57h+var_80]; int
0x1800b1ba7  test    r9d, r9d
0x1800b1baa  jns     short loc_1800B1BC6
0x1800b1bac  cmp     [rax+7CCh], r9d
0x1800b1bb3  jz      short loc_1800B1BC6
0x1800b1bb5  mov     r8d, 1Fh; int
0x1800b1bbb  mov     rdx, r12; char *
0x1800b1bbe  mov     rcx, rax; this
0x1800b1bc1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b1bc6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b1bcd  jb      loc_1800B1E88
0x1800b1bd3  mov     edx, 10h
0x1800b1bd8  jmp     loc_1800B1953
0x1800b1bdd  mov     rcx, rsi; this
0x1800b1be0  call    ?SetMinimumReportInterval@MFLightSensorReader@@QEAAJI@Z; MFLightSensorReader::SetMinimumReportInterval(uint)
0x1800b1be5  mov     [rbp+57h+var_80], eax
0x1800b1be8  test    eax, eax
0x1800b1bea  jns     loc_1800B1C82
0x1800b1bf0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1bf7  test    rcx, rcx
0x1800b1bfa  jnz     short loc_1800B1C3D
0x1800b1bfc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b1c02  mov     rcx, rax
0x1800b1c05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1c0c  test    rax, rax
0x1800b1c0f  jz      short loc_1800B1C2F
0x1800b1c11  mov     rax, [rax]
0x1800b1c14  mov     edx, 7F0h
0x1800b1c19  mov     rax, [rax+8]
0x1800b1c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1c22  test    eax, eax
0x1800b1c24  jz      short loc_1800B1C2F
0x1800b1c26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1c2d  jmp     short loc_1800B1C3D
0x1800b1c2f  lea     rcx, qword_180153440; this
0x1800b1c36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1c3d  cmp     [rcx+8], r15b
0x1800b1c41  jz      short loc_1800B1C6B
0x1800b1c43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1c48  mov     r9d, [rbp+57h+var_80]; int
0x1800b1c4c  test    r9d, r9d
0x1800b1c4f  jns     short loc_1800B1C6B
0x1800b1c51  cmp     [rax+7CCh], r9d
0x1800b1c58  jz      short loc_1800B1C6B
0x1800b1c5a  mov     r8d, 22h ; '"'; int
0x1800b1c60  mov     rdx, r12; char *
0x1800b1c63  mov     rcx, rax; this
0x1800b1c66  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b1c6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b1c72  jb      loc_1800B1E88
0x1800b1c78  mov     edx, 11h
0x1800b1c7d  jmp     loc_1800B1953
0x1800b1c82  lea     rdx, [rbp+57h+var_70]
0x1800b1c86  lea     rcx, [rbp+57h+var_78]
0x1800b1c8a  call    ??$Make@VLightReadingChangedListener@@AEAPEAUIMFTelemetrySession@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VLightReadingChangedListener@@@12@AEAPEAUIMFTelemetrySession@@@Z; Microsoft::WRL::Details::Make<LightReadingChangedListener,IMFTelemetrySession * &>(IMFTelemetrySession * &)
0x1800b1c8f  mov     rcx, r15
0x1800b1c92  lea     rdx, [rbp+57h+var_68]
0x1800b1c96  cmp     rdx, rax
  ... truncated ...
```
