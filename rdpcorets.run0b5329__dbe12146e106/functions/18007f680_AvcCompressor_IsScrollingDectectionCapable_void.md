# AvcCompressor::IsScrollingDectectionCapable(void)

- ea: `0x18007f680`
- end: `0x18007fb30`
- name: `?IsScrollingDectectionCapable@AvcCompressor@@UEAAHXZ`
- size: `1200`
- prototype: `__int64 __fastcall(AvcCompressor *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800015f0`
- `0x180033940`
- `0x180033964`
- `0x180059838`
- `0x180075c6c`
- `0x18007f680`
- `0x180084758`
- `0x1800849d4`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007f6e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007f6e3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007f959`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007f9c7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007fa62`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007fafb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007f959`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007f9c7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007fa62`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007fafb`
- `OLEAUT32!__imp_VariantClear` at `0x18007fa1f`
- `OLEAUT32!__imp_VariantClear` at `0x18007fa1f`

## string_xrefs

- `0x18007f725`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007f7ed`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007f6fe`: `CreateMFT failed.`
- `0x18007f7c6`: `Create codec api failed.`

## pseudocode

```c
__int64 __fastcall AvcCompressor::IsScrollingDectectionCapable(AvcCompressor *this)
{
  unsigned int v1; // esi
  AvcEncoder *v2; // rax
  AvcEncoder *v3; // r14
  HRESULT v4; // ecx
  int v5; // r8d
  int v6; // r9d
  LPVOID v7; // rcx
  void (*v8)(void); // rax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  LPVOID v13; // rcx
  int v14; // r15d
  int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // edi
  int v18; // ebx
  unsigned int v19; // eax
  unsigned int i; // ebx
  unsigned int ActivityIdPrefix; // eax
  __int64 v22; // rcx
  LPVOID v23; // rcx
  unsigned int v25; // eax
  __int64 v26; // [rsp+50h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-19h] BYREF
  const char *v29; // [rsp+68h] [rbp-11h] BYREF
  const char *v30; // [rsp+70h] [rbp-9h] BYREF
  const char *v31; // [rsp+78h] [rbp-1h] BYREF
  const char *v32; // [rsp+80h] [rbp+7h] BYREF
  __int128 v33; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v34; // [rsp+98h] [rbp+1Fh]
  unsigned int v35; // [rsp+E8h] [rbp+6Fh] BYREF
  int v36; // [rsp+F0h] [rbp+77h] BYREF
  int v37; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = 0;
  v2 = (AvcEncoder *)operator new(0x1A8u);
  if ( v2 )
  {
    v3 = AvcEncoder::AvcEncoder(v2);
    if ( v3 )
    {
      ppv = 0;
      v4 = CoCreateInstance(&CLSID_CMSH264EncoderMFT, 0, 3u, &IID_IMFTransform, &ppv);
      if ( v4 >= 0 )
      {
        v26 = 0;
        v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
               ppv,
               &GUID_901db4c7_31ce_41a2_85dc_8fa0bf41b8da,
               &v26);
        if ( v9 >= 0 )
        {
          pv = 0;
          v35 = 0;
          if ( (*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v26 + 24LL))(
                 v26,
                 &GUID_8bfda3b8_7387_4c07_924f_fe63006cf22b) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                &WPP_1c5fb9514b053585536f3862527bab66_Traceguids,
                ActivityIdPrefix);
            }
          }
          else
          {
            v14 = (*(__int64 (__fastcall **)(__int64, GUID *, LPVOID *, unsigned int *))(*(_QWORD *)v26 + 48LL))(
                    v26,
                    &GUID_8bfda3b8_7387_4c07_924f_fe63006cf22b,
                    &pv,
                    &v35);
            if ( !v14 && v35 == 1 && *((_DWORD *)pv + 2) == 63 )
            {
              v34 = 0;
              v33 = 0;
              v15 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v26 + 64LL))(
                      v26,
                      &GUID_8bfda3b8_7387_4c07_924f_fe63006cf22b,
                      &v33);
              if ( v15 || DWORD2(v33) != -1 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  v16 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
                  WPP_SF_Dddd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    12,
                    &WPP_1c5fb9514b053585536f3862527bab66_Traceguids,
                    v16,
                    v15,
                    DWORD2(v33),
                    -1);
                }
              }
              else
              {
                v1 = 1;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v17 = v35;
              v18 = *((_DWORD *)pv + 2);
              v19 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
              WPP_SF_Dddd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                13,
                &WPP_1c5fb9514b053585536f3862527bab66_Traceguids,
                v19,
                v14,
                v17,
                v18);
            }
            for ( i = 0; i < v35; ++i )
              VariantClear((VARIANTARG *)pv + i);
            CoTaskMemFree(pv);
          }
          v22 = v26;
          if ( v26 )
          {
            v26 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          v23 = ppv;
          if ( !ppv )
            goto LABEL_42;
          ppv = 0;
          v8 = *(void (**)(void))(*(_QWORD *)v23 + 16LL);
        }
        else
        {
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v36 = 672;
            v32 = "Create codec api failed.";
            v37 = v9;
            v31 = "IsScrollingDectectionCapable";
            v30 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
            v29 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v9,
              (unsigned int)&byte_18019E3DF,
              v10,
              v11,
              (__int64)&v29,
              (__int64)&v37,
              (__int64)&v30,
              (__int64)&v36,
              (__int64)&v31,
              (__int64)&v32);
          }
          v12 = v26;
          if ( v26 )
          {
            v26 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
          v13 = ppv;
          if ( !ppv )
            goto LABEL_42;
          ppv = 0;
          v8 = *(void (**)(void))(*(_QWORD *)v13 + 16LL);
        }
      }
      else
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v36 = 666;
          v29 = "CreateMFT failed.";
          v37 = v4;
          v30 = "IsScrollingDectectionCapable";
          v31 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
          v32 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v4,
            (unsigned int)byte_18019E433,
            v5,
            v6,
            (__int64)&v32,
            (__int64)&v37,
            (__int64)&v31,
            (__int64)&v36,
            (__int64)&v30,
            (__int64)&v29);
        }
        v7 = ppv;
        if ( !ppv )
          goto LABEL_42;
        ppv = 0;
        v8 = *(void (**)(void))(*(_QWORD *)v7 + 16LL);
      }
      v8();
LABEL_42:
      AvcEncoder::~AvcEncoder(v3);
      operator delete(v3);
      return v1;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v25 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_1c5fb9514b053585536f3862527bab66_Traceguids, v25);
  }
  return 0;
}

```

## disassembly

```asm
0x18007f680  push    rbp
0x18007f682  push    rsi
0x18007f683  push    r12
0x18007f685  push    r14
0x18007f687  lea     rbp, [rsp-3Fh]
0x18007f68c  sub     rsp, 0B8h
0x18007f693  xor     r12d, r12d
0x18007f696  mov     ecx, 1A8h; Size
0x18007f69b  mov     esi, r12d
0x18007f69e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007f6a3  test    rax, rax
0x18007f6a6  jz      loc_18007FAD9
0x18007f6ac  mov     rcx, rax; this
0x18007f6af  call    ??0AvcEncoder@@QEAA@XZ; AvcEncoder::AvcEncoder(void)
0x18007f6b4  mov     r14, rax
0x18007f6b7  test    rax, rax
0x18007f6ba  jz      loc_18007FAD9
0x18007f6c0  lea     rax, [rbp+57h+var_78]
0x18007f6c4  mov     [rbp+57h+var_78], r12
0x18007f6c8  lea     r9, IID_IMFTransform; riid
0x18007f6cf  mov     [rsp+0D0h+ppv], rax; ppv
0x18007f6d4  xor     edx, edx; pUnkOuter
0x18007f6d6  lea     rcx, CLSID_CMSH264EncoderMFT; rclsid
0x18007f6dd  mov     r8d, 3; dwClsContext
0x18007f6e3  call    cs:__imp_CoCreateInstance
0x18007f6e9  mov     ecx, eax
0x18007f6eb  test    eax, eax
0x18007f6ed  jns     loc_18007F793
0x18007f6f3  mov     eax, cs:dword_1801B76C8
0x18007f6f9  cmp     eax, 2
0x18007f6fc  jbe     short loc_18007F776
0x18007f6fe  lea     rax, aCreatemftFaile; "CreateMFT failed."
0x18007f705  mov     [rbp+57h+arg_10], 29Ah
0x18007f70c  mov     [rbp+57h+var_68], rax
0x18007f710  lea     rdx, byte_18019E433
0x18007f717  lea     rax, aIsscrollingdec; "IsScrollingDectectionCapable"
0x18007f71e  mov     [rbp+57h+arg_18], ecx
0x18007f721  mov     [rbp+57h+var_60], rax
0x18007f725  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007f72c  mov     [rbp+57h+var_58], rax
0x18007f730  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007f737  mov     [rbp+57h+var_50], rax
0x18007f73b  lea     rax, [rbp+57h+var_68]
0x18007f73f  mov     [rsp+0D0h+var_88], rax
0x18007f744  lea     rax, [rbp+57h+var_60]
0x18007f748  mov     [rsp+0D0h+var_90], rax
0x18007f74d  lea     rax, [rbp+57h+arg_10]
0x18007f751  mov     [rsp+0D0h+var_98], rax
0x18007f756  lea     rax, [rbp+57h+var_58]
0x18007f75a  mov     [rsp+0D0h+var_A0], rax
0x18007f75f  lea     rax, [rbp+57h+arg_18]
0x18007f763  mov     [rsp+0D0h+var_A8], rax
0x18007f768  lea     rax, [rbp+57h+var_50]
0x18007f76c  mov     [rsp+0D0h+ppv], rax
0x18007f771  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007f776  mov     rcx, [rbp+57h+var_78]
0x18007f77a  test    rcx, rcx
0x18007f77d  jz      loc_18007FAB9
0x18007f783  mov     [rbp+57h+var_78], r12
0x18007f787  mov     rax, [rcx]
0x18007f78a  mov     rax, [rax+10h]
0x18007f78e  jmp     loc_18007FAB4
0x18007f793  mov     rcx, [rbp+57h+var_78]
0x18007f797  lea     r8, [rbp+57h+var_80]
0x18007f79b  mov     [rbp+57h+var_80], r12
0x18007f79f  lea     rdx, _GUID_901db4c7_31ce_41a2_85dc_8fa0bf41b8da
0x18007f7a6  mov     rax, [rcx]
0x18007f7a9  mov     rax, [rax]
0x18007f7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f7b1  mov     ecx, eax
0x18007f7b3  test    eax, eax
0x18007f7b5  jns     loc_18007F874
0x18007f7bb  mov     eax, cs:dword_1801B76C8
0x18007f7c1  cmp     eax, 2
0x18007f7c4  jbe     short loc_18007F83E
0x18007f7c6  lea     rax, aCreateCodecApi; "Create codec api failed."
0x18007f7cd  mov     [rbp+57h+arg_10], 2A0h
0x18007f7d4  mov     [rbp+57h+var_50], rax
0x18007f7d8  lea     rdx, byte_18019E3DF
0x18007f7df  lea     rax, aIsscrollingdec; "IsScrollingDectectionCapable"
0x18007f7e6  mov     [rbp+57h+arg_18], ecx
0x18007f7e9  mov     [rbp+57h+var_58], rax
0x18007f7ed  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007f7f4  mov     [rbp+57h+var_60], rax
0x18007f7f8  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007f7ff  mov     [rbp+57h+var_68], rax
0x18007f803  lea     rax, [rbp+57h+var_50]
0x18007f807  mov     [rsp+0D0h+var_88], rax
0x18007f80c  lea     rax, [rbp+57h+var_58]
0x18007f810  mov     [rsp+0D0h+var_90], rax
0x18007f815  lea     rax, [rbp+57h+arg_10]
0x18007f819  mov     [rsp+0D0h+var_98], rax
0x18007f81e  lea     rax, [rbp+57h+var_60]
0x18007f822  mov     [rsp+0D0h+var_A0], rax
0x18007f827  lea     rax, [rbp+57h+arg_18]
0x18007f82b  mov     [rsp+0D0h+var_A8], rax
0x18007f830  lea     rax, [rbp+57h+var_68]
0x18007f834  mov     [rsp+0D0h+ppv], rax
0x18007f839  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007f83e  mov     rcx, [rbp+57h+var_80]
0x18007f842  test    rcx, rcx
0x18007f845  jz      short loc_18007F857
0x18007f847  mov     [rbp+57h+var_80], r12
0x18007f84b  mov     rax, [rcx]
0x18007f84e  mov     rax, [rax+10h]
0x18007f852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f857  mov     rcx, [rbp+57h+var_78]
0x18007f85b  test    rcx, rcx
0x18007f85e  jz      loc_18007FAB9
0x18007f864  mov     [rbp+57h+var_78], r12
0x18007f868  mov     rax, [rcx]
0x18007f86b  mov     rax, [rax+10h]
0x18007f86f  jmp     loc_18007FAB4
0x18007f874  mov     rcx, [rbp+57h+var_80]
0x18007f878  lea     rdx, _GUID_8bfda3b8_7387_4c07_924f_fe63006cf22b
0x18007f87f  mov     [rbp+57h+pv], r12
0x18007f883  mov     [rbp+57h+arg_8], r12d
0x18007f887  mov     rax, [rcx]
0x18007f88a  mov     rax, [rax+18h]
0x18007f88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f893  test    eax, eax
0x18007f895  jnz     loc_18007FA40
0x18007f89b  mov     rcx, [rbp+57h+var_80]
0x18007f89f  lea     r9, [rbp+57h+arg_8]
0x18007f8a3  mov     [rsp+0D0h+var_20], rbx
0x18007f8ab  lea     r8, [rbp+57h+pv]
0x18007f8af  lea     rdx, _GUID_8bfda3b8_7387_4c07_924f_fe63006cf22b
0x18007f8b6  mov     [rsp+0D0h+var_30], r15
0x18007f8be  mov     rax, [rcx]
0x18007f8c1  mov     rax, [rax+30h]
0x18007f8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f8ca  mov     r15d, eax
0x18007f8cd  test    eax, eax
0x18007f8cf  jnz     loc_18007F993
0x18007f8d5  cmp     [rbp+57h+arg_8], 1
0x18007f8d9  jnz     loc_18007F993
0x18007f8df  mov     rax, [rbp+57h+pv]
0x18007f8e3  cmp     dword ptr [rax+8], 3Fh ; '?'
0x18007f8e7  jnz     loc_18007F993
0x18007f8ed  mov     rcx, [rbp+57h+var_80]
0x18007f8f1  lea     r8, [rbp+57h+var_48]
0x18007f8f5  xor     eax, eax
0x18007f8f7  lea     rdx, _GUID_8bfda3b8_7387_4c07_924f_fe63006cf22b
0x18007f8fe  mov     [rbp+57h+var_38], rax
0x18007f902  xorps   xmm0, xmm0
0x18007f905  movups  [rbp+57h+var_48], xmm0
0x18007f909  mov     rax, [rcx]
0x18007f90c  mov     rax, [rax+40h]
0x18007f910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f915  mov     ebx, eax
0x18007f917  test    eax, eax
0x18007f919  jnz     short loc_18007F92B
0x18007f91b  cmp     dword ptr [rbp+57h+var_48+8], 0FFFFFFFFh
0x18007f91f  jnz     short loc_18007F92B
0x18007f921  mov     esi, 1
0x18007f926  jmp     loc_18007FA01
0x18007f92b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f932  lea     rax, WPP_GLOBAL_Control
0x18007f939  cmp     rcx, rax
0x18007f93c  jz      loc_18007FA01
0x18007f942  test    dword ptr [rcx+1Ch], 100h
0x18007f949  jz      loc_18007FA01
0x18007f94f  cmp     byte ptr [rcx+19h], 5
0x18007f953  jb      loc_18007FA01
0x18007f959  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18007f95f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f966  lea     r8, WPP_1c5fb9514b053585536f3862527bab66_Traceguids
0x18007f96d  mov     r9d, eax
0x18007f970  mov     dword ptr [rsp+0D0h+var_A0], 0FFFFFFFFh
0x18007f978  mov     eax, dword ptr [rbp+57h+var_48+8]
0x18007f97b  mov     edx, 0Ch
0x18007f980  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18007f984  mov     rcx, [rcx+10h]
0x18007f988  mov     dword ptr [rsp+0D0h+ppv], ebx
0x18007f98c  call    WPP_SF_Dddd
0x18007f991  jmp     short loc_18007FA01
0x18007f993  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f99a  lea     rax, WPP_GLOBAL_Control
0x18007f9a1  cmp     rcx, rax
0x18007f9a4  jz      short loc_18007FA01
0x18007f9a6  test    dword ptr [rcx+1Ch], 100h
0x18007f9ad  jz      short loc_18007FA01
0x18007f9af  cmp     byte ptr [rcx+19h], 5
0x18007f9b3  jb      short loc_18007FA01
0x18007f9b5  mov     rax, [rbp+57h+pv]
0x18007f9b9  mov     [rsp+0D0h+var_28], rdi
0x18007f9c1  mov     edi, [rbp+57h+arg_8]
0x18007f9c4  mov     ebx, [rax+8]
0x18007f9c7  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18007f9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f9d4  lea     r8, WPP_1c5fb9514b053585536f3862527bab66_Traceguids
0x18007f9db  mov     dword ptr [rsp+0D0h+var_A0], ebx
0x18007f9df  mov     edx, 0Dh
0x18007f9e4  mov     dword ptr [rsp+0D0h+var_A8], edi
0x18007f9e8  mov     r9d, eax
0x18007f9eb  mov     dword ptr [rsp+0D0h+ppv], r15d
0x18007f9f0  mov     rcx, [rcx+10h]
0x18007f9f4  call    WPP_SF_Dddd
0x18007f9f9  mov     rdi, [rsp+0D0h+var_28]
0x18007fa01  mov     r15, [rsp+0D0h+var_30]
0x18007fa09  mov     ebx, r12d
0x18007fa0c  cmp     [rbp+57h+arg_8], ebx
0x18007fa0f  jbe     short loc_18007FA2C
0x18007fa11  mov     eax, ebx
0x18007fa13  lea     rcx, [rax+rax*2]
0x18007fa17  mov     rax, [rbp+57h+pv]
0x18007fa1b  lea     rcx, [rax+rcx*8]; pvarg
0x18007fa1f  call    cs:__imp_VariantClear
0x18007fa25  inc     ebx
0x18007fa27  cmp     ebx, [rbp+57h+arg_8]
0x18007fa2a  jb      short loc_18007FA11
0x18007fa2c  mov     rcx, [rbp+57h+pv]; pv
0x18007fa30  call    cs:__imp_CoTaskMemFree
0x18007fa36  mov     rbx, [rsp+0D0h+var_20]
0x18007fa3e  jmp     short loc_18007FA87
0x18007fa40  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fa47  lea     rax, WPP_GLOBAL_Control
0x18007fa4e  cmp     rcx, rax
0x18007fa51  jz      short loc_18007FA87
0x18007fa53  test    dword ptr [rcx+1Ch], 100h
0x18007fa5a  jz      short loc_18007FA87
0x18007fa5c  cmp     byte ptr [rcx+19h], 5
0x18007fa60  jb      short loc_18007FA87
0x18007fa62  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18007fa68  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fa6f  lea     r8, WPP_1c5fb9514b053585536f3862527bab66_Traceguids
0x18007fa76  mov     edx, 0Eh
0x18007fa7b  mov     r9d, eax
0x18007fa7e  mov     rcx, [rcx+10h]
0x18007fa82  call    WPP_SF_d
0x18007fa87  mov     rcx, [rbp+57h+var_80]
0x18007fa8b  test    rcx, rcx
0x18007fa8e  jz      short loc_18007FAA0
0x18007fa90  mov     [rbp+57h+var_80], r12
0x18007fa94  mov     rax, [rcx]
0x18007fa97  mov     rax, [rax+10h]
0x18007fa9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007faa0  mov     rcx, [rbp+57h+var_78]
0x18007faa4  test    rcx, rcx
0x18007faa7  jz      short loc_18007FAB9
0x18007faa9  mov     [rbp+57h+var_78], r12
0x18007faad  mov     rdx, [rcx]
0x18007fab0  mov     rax, [rdx+10h]
0x18007fab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fab9  mov     rcx, r14; this
0x18007fabc  call    ??1AvcEncoder@@QEAA@XZ; AvcEncoder::~AvcEncoder(void)
0x18007fac1  mov     rcx, r14; Block
0x18007fac4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007fac9  mov     eax, esi
0x18007facb  add     rsp, 0B8h
0x18007fad2  pop     r14
0x18007fad4  pop     r12
0x18007fad6  pop     rsi
0x18007fad7  pop     rbp
0x18007fad8  retn
0x18007fad9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fae0  lea     rax, WPP_GLOBAL_Control
0x18007fae7  cmp     rcx, rax
0x18007faea  jz      short loc_18007FB20
0x18007faec  test    dword ptr [rcx+1Ch], 100h
0x18007faf3  jz      short loc_18007FB20
0x18007faf5  cmp     byte ptr [rcx+19h], 5
0x18007faf9  jb      short loc_18007FB20
0x18007fafb  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18007fb01  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fb08  lea     r8, WPP_1c5fb9514b053585536f3862527bab66_Traceguids
0x18007fb0f  mov     edx, 0Fh
0x18007fb14  mov     r9d, eax
0x18007fb17  mov     rcx, [rcx+10h]
0x18007fb1b  call    WPP_SF_d
0x18007fb20  mov     eax, esi
0x18007fb22  add     rsp, 0B8h
0x18007fb29  pop     r14
0x18007fb2b  pop     r12
0x18007fb2d  pop     rsi
0x18007fb2e  pop     rbp
0x18007fb2f  retn
```
