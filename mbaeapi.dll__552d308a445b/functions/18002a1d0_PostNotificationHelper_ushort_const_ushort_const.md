# PostNotificationHelper(ushort const *,ushort const *)

- ea: `0x18002a1d0`
- end: `0x18002a530`
- name: `?PostNotificationHelper@@YAJPEBG0@Z`
- size: `864`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002a870`
- `0x18002ac30`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x18002a1d0`
- `0x18002b26c`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a216`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a216`

## string_xrefs

- `0x18002a25e`: `CoCreateInstance failed with hr=0x%08x.`
- `0x18002a347`: `CreateAppEndpoint failed with hr=0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PostNotificationHelper(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HRESULT Instance; // ebx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned __int16 **v8; // rcx
  LPVOID v9; // rbx
  __int64 (__fastcall *v10)(LPVOID, __int64 *); // rdi
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  LPVOID *ppv; // [rsp+20h] [rbp-99h]
  LPVOID *ppva; // [rsp+20h] [rbp-99h]
  LPVOID v20[2]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int16 *v21[2]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-9h]
  unsigned __int16 *v23[2]; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v24; // [rsp+D0h] [rbp+17h]
  unsigned __int16 *v25[2]; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh]
  unsigned __int16 *v27; // [rsp+130h] [rbp+77h] BYREF
  __int64 v28; // [rsp+138h] [rbp+7Fh] BYREF

  v20[0] = 0;
  v28 = 0;
  Instance = CoCreateInstance(
               &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
               0,
               4u,
               &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
               v20);
  if ( Instance >= 0 )
  {
    v9 = v20[0];
    v10 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v20[0] + 24LL);
    if ( v28 )
      winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(&v28);
    Instance = v10(v9, &v28);
    if ( Instance >= 0 )
    {
      LODWORD(v27) = 0;
      v21[0] = 0;
      LODWORD(v21[1]) = 0;
      Instance = (*(__int64 (__fastcall **)(__int64, wchar_t *, wchar_t *, _QWORD, _DWORD, const unsigned __int16 *, const unsigned __int16 *, _QWORD, unsigned __int16 **, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, unsigned __int16 **))(*(_QWORD *)v28 + 64LL))(
                   v28,
                   aSystem_0,
                   aWindowsSystemt,
                   0,
                   0,
                   a1,
                   a2,
                   0,
                   v21,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0,
                   &v27);
      if ( Instance >= 0 )
        goto LABEL_16;
      *(_OWORD *)v25 = 0;
      v26 = 0;
      *(_OWORD *)v23 = 0;
      v24 = 0;
      std::vector<unsigned short>::resize(v25);
      std::vector<unsigned short>::resize(v23);
      StringCchPrintfW(v25[0], v25[1] - v25[0], L"PostNotification failed with hr=0x%08x.", (unsigned int)Instance);
      LODWORD(ppva) = 230;
      StringCchPrintfW(v23[0], v23[1] - v23[0], L"%S(%d):%s", "PostNotificationHelper", ppva, v25[0]);
      v14 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v14 > 2u )
      {
        v21[0] = v23[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v14,
          (__int64)byte_180076061,
          v15,
          v16,
          (const unsigned __int16 **)v21);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v23);
      v8 = v25;
    }
    else
    {
      *(_OWORD *)v21 = 0;
      v22 = 0;
      *(_OWORD *)v23 = 0;
      v24 = 0;
      std::vector<unsigned short>::resize(v21);
      std::vector<unsigned short>::resize(v23);
      StringCchPrintfW(v21[0], v21[1] - v21[0], L"CreateAppEndpoint failed with hr=0x%08x.", (unsigned int)Instance);
      LODWORD(ppv) = 203;
      StringCchPrintfW(v23[0], v23[1] - v23[0], L"%S(%d):%s", "PostNotificationHelper", ppv, v21[0]);
      v11 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v11 > 2u )
      {
        v27 = v23[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v11,
          (__int64)word_180076082,
          v12,
          v13,
          (const unsigned __int16 **)&v27);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v23);
      v8 = v21;
    }
  }
  else
  {
    *(_OWORD *)v23 = 0;
    v24 = 0;
    *(_OWORD *)v21 = 0;
    v22 = 0;
    std::vector<unsigned short>::resize(v23);
    std::vector<unsigned short>::resize(v21);
    StringCchPrintfW(v23[0], v23[1] - v23[0], L"CoCreateInstance failed with hr=0x%08x.", (unsigned int)Instance);
    LODWORD(ppv) = 195;
    StringCchPrintfW(v21[0], v21[1] - v21[0], L"%S(%d):%s", "PostNotificationHelper", ppv, v23[0]);
    v5 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v5 > 2u )
    {
      v27 = v21[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v5,
        (__int64)byte_1800760A3,
        v6,
        v7,
        (const unsigned __int16 **)&v27);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
    v8 = v23;
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v8);
LABEL_16:
  if ( v28 )
    winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(&v28);
  if ( v20[0] )
    winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(v20);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002a1d0  mov     [rsp-8+arg_0], rbx
0x18002a1d5  push    rbp
0x18002a1d6  push    rsi
0x18002a1d7  push    rdi
0x18002a1d8  push    r14
0x18002a1da  push    r15
0x18002a1dc  lea     rbp, [rsp-37h]
0x18002a1e1  sub     rsp, 0F0h
0x18002a1e8  mov     rsi, rdx
0x18002a1eb  mov     r14, rcx
0x18002a1ee  xor     r15d, r15d
0x18002a1f1  mov     [rbp+57h+var_80], r15
0x18002a1f5  mov     [rbp+57h+arg_18], r15
0x18002a1f9  lea     rax, [rbp+57h+var_80]
0x18002a1fd  mov     [rsp+110h+ppv], rax; ppv
0x18002a202  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18002a209  xor     edx, edx; pUnkOuter
0x18002a20b  lea     r8d, [r15+4]; dwClsContext
0x18002a20f  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18002a216  call    cs:__imp_CoCreateInstance
0x18002a21c  mov     ebx, eax
0x18002a21e  test    eax, eax
0x18002a220  jns     loc_18002A2DC
0x18002a226  xorps   xmm0, xmm0
0x18002a229  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18002a22e  mov     [rbp+57h+var_40], r15
0x18002a232  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x18002a237  mov     [rbp+57h+var_60], r15
0x18002a23b  lea     rcx, [rbp+57h+var_50]
0x18002a23f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a244  lea     rcx, [rbp+57h+var_70]
0x18002a248  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a24d  mov     rdx, [rbp+57h+var_50+8]
0x18002a251  mov     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x18002a255  sub     rdx, rcx
0x18002a258  sar     rdx, 1; unsigned __int64
0x18002a25b  mov     r9d, ebx
0x18002a25e  lea     r8, aCocreateinstan; "CoCreateInstance failed with hr=0x%08x."
0x18002a265  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a26a  mov     rdx, [rbp+57h+var_70+8]
0x18002a26e  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18002a272  sub     rdx, rcx
0x18002a275  sar     rdx, 1; unsigned __int64
0x18002a278  mov     rax, [rbp+57h+var_50]
0x18002a27c  mov     [rsp+110h+var_E8], rax
0x18002a281  mov     dword ptr [rsp+110h+ppv], 0C3h
0x18002a289  lea     r9, aPostnotificati; "PostNotificationHelper"
0x18002a290  lea     r8, aSDS; "%S(%d):%s"
0x18002a297  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a29c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18002a2a1  mov     ecx, [rax]
0x18002a2a3  cmp     ecx, 2
0x18002a2a6  jbe     short loc_18002A2C9
0x18002a2a8  mov     rcx, [rbp+57h+var_70]
0x18002a2ac  mov     [rbp+57h+arg_10], rcx
0x18002a2b0  lea     rcx, [rbp+57h+arg_10]
0x18002a2b4  mov     [rsp+110h+ppv], rcx
0x18002a2b9  lea     rdx, byte_1800760A3
0x18002a2c0  mov     rcx, rax
0x18002a2c3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002a2c8  nop
0x18002a2c9  lea     rcx, [rbp+57h+var_70]
0x18002a2cd  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002a2d2  nop
0x18002a2d3  lea     rcx, [rbp+57h+var_50]
0x18002a2d7  jmp     loc_18002A4F2
0x18002a2dc  mov     rbx, [rbp+57h+var_80]
0x18002a2e0  mov     rax, [rbx]
0x18002a2e3  mov     rdi, [rax+18h]
0x18002a2e7  cmp     [rbp+57h+arg_18], r15
0x18002a2eb  jz      short loc_18002A2F6
0x18002a2ed  lea     rcx, [rbp+57h+arg_18]
0x18002a2f1  call    ?unconditional_release_ref@?$com_ptr@UIWpnAppEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(void)
0x18002a2f6  lea     rdx, [rbp+57h+arg_18]
0x18002a2fa  mov     rcx, rbx
0x18002a2fd  mov     rax, rdi
0x18002a300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a305  mov     ebx, eax
0x18002a307  test    eax, eax
0x18002a309  jns     loc_18002A3C5
0x18002a30f  xorps   xmm0, xmm0
0x18002a312  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x18002a317  mov     [rbp+57h+var_60], r15
0x18002a31b  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18002a320  mov     [rbp+57h+var_40], r15
0x18002a324  lea     rcx, [rbp+57h+var_70]
0x18002a328  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a32d  lea     rcx, [rbp+57h+var_50]
0x18002a331  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a336  mov     rdx, [rbp+57h+var_70+8]
0x18002a33a  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18002a33e  sub     rdx, rcx
0x18002a341  sar     rdx, 1; unsigned __int64
0x18002a344  mov     r9d, ebx
0x18002a347  lea     r8, aCreateappendpo; "CreateAppEndpoint failed with hr=0x%08x"...
0x18002a34e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a353  mov     rdx, [rbp+57h+var_50+8]
0x18002a357  mov     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x18002a35b  sub     rdx, rcx
0x18002a35e  sar     rdx, 1; unsigned __int64
0x18002a361  mov     rax, [rbp+57h+var_70]
0x18002a365  mov     [rsp+110h+var_E8], rax
0x18002a36a  mov     dword ptr [rsp+110h+ppv], 0CBh
0x18002a372  lea     r9, aPostnotificati; "PostNotificationHelper"
0x18002a379  lea     r8, aSDS; "%S(%d):%s"
0x18002a380  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a385  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18002a38a  mov     ecx, [rax]
0x18002a38c  cmp     ecx, 2
0x18002a38f  jbe     short loc_18002A3B2
0x18002a391  mov     rcx, [rbp+57h+var_50]
0x18002a395  mov     [rbp+57h+arg_10], rcx
0x18002a399  lea     rcx, [rbp+57h+arg_10]
0x18002a39d  mov     [rsp+110h+ppv], rcx
0x18002a3a2  lea     rdx, word_180076082
0x18002a3a9  mov     rcx, rax
0x18002a3ac  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002a3b1  nop
0x18002a3b2  lea     rcx, [rbp+57h+var_50]
0x18002a3b6  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002a3bb  nop
0x18002a3bc  lea     rcx, [rbp+57h+var_70]
0x18002a3c0  jmp     loc_18002A4F2
0x18002a3c5  mov     dword ptr [rbp+57h+arg_10], r15d
0x18002a3c9  xor     eax, eax
0x18002a3cb  mov     rcx, [rbp+57h+arg_18]
0x18002a3cf  mov     [rbp+57h+var_70], rax
0x18002a3d3  mov     dword ptr [rbp+57h+var_70+8], eax
0x18002a3d6  mov     rax, [rcx]
0x18002a3d9  lea     rdx, [rbp+57h+arg_10]
0x18002a3dd  mov     [rsp+110h+var_98], rdx
0x18002a3e2  mov     [rsp+110h+var_A0], r15d
0x18002a3e7  mov     [rsp+110h+var_A8], r15
0x18002a3ec  mov     [rsp+110h+var_B0], r15
0x18002a3f1  mov     [rsp+110h+var_B8], r15
0x18002a3f6  mov     [rsp+110h+var_C0], r15d
0x18002a3fb  mov     [rsp+110h+var_C8], r15d
0x18002a400  lea     rdx, [rbp+57h+var_70]
0x18002a404  mov     [rsp+110h+var_D0], rdx
0x18002a409  mov     [rsp+110h+var_D8], r15
0x18002a40e  mov     [rsp+110h+var_E0], rsi
0x18002a413  mov     [rsp+110h+var_E8], r14
0x18002a418  mov     dword ptr [rsp+110h+ppv], r15d
0x18002a41d  xor     r9d, r9d
0x18002a420  lea     r8, aWindowsSystemt; "Windows.SystemToast.Wwansvc"
0x18002a427  lea     rdx, aSystem_0; "System"
0x18002a42e  mov     rax, [rax+40h]
0x18002a432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a437  mov     ebx, eax
0x18002a439  test    eax, eax
0x18002a43b  jns     loc_18002A4F8
0x18002a441  xorps   xmm0, xmm0
0x18002a444  movdqu  xmmword ptr [rbp+57h+var_38], xmm0
0x18002a449  mov     [rbp+57h+var_28], r15
0x18002a44d  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18002a452  mov     [rbp+57h+var_40], r15
0x18002a456  lea     rcx, [rbp+57h+var_38]
0x18002a45a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a45f  lea     rcx, [rbp+57h+var_50]
0x18002a463  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a468  mov     rdx, [rbp+57h+var_38+8]
0x18002a46c  mov     rcx, [rbp+57h+var_38]; unsigned __int16 *
0x18002a470  sub     rdx, rcx
0x18002a473  sar     rdx, 1; unsigned __int64
0x18002a476  mov     r9d, ebx
0x18002a479  lea     r8, aPostnotificati_0; "PostNotification failed with hr=0x%08x."
0x18002a480  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a485  mov     rdx, [rbp+57h+var_50+8]
0x18002a489  mov     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x18002a48d  sub     rdx, rcx
0x18002a490  sar     rdx, 1; unsigned __int64
0x18002a493  mov     rax, [rbp+57h+var_38]
0x18002a497  mov     [rsp+110h+var_E8], rax
0x18002a49c  mov     dword ptr [rsp+110h+ppv], 0E6h
0x18002a4a4  lea     r9, aPostnotificati; "PostNotificationHelper"
0x18002a4ab  lea     r8, aSDS; "%S(%d):%s"
0x18002a4b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a4b7  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18002a4bc  mov     ecx, [rax]
0x18002a4be  cmp     ecx, 2
0x18002a4c1  jbe     short loc_18002A4E4
0x18002a4c3  mov     rcx, [rbp+57h+var_50]
0x18002a4c7  mov     [rbp+57h+var_70], rcx
0x18002a4cb  lea     rcx, [rbp+57h+var_70]
0x18002a4cf  mov     [rsp+110h+ppv], rcx
0x18002a4d4  lea     rdx, byte_180076061
0x18002a4db  mov     rcx, rax
0x18002a4de  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002a4e3  nop
0x18002a4e4  lea     rcx, [rbp+57h+var_50]
0x18002a4e8  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002a4ed  nop
0x18002a4ee  lea     rcx, [rbp+57h+var_38]
0x18002a4f2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002a4f7  nop
0x18002a4f8  cmp     [rbp+57h+arg_18], r15
0x18002a4fc  jz      short loc_18002A508
0x18002a4fe  lea     rcx, [rbp+57h+arg_18]
0x18002a502  call    ?unconditional_release_ref@?$com_ptr@UIWpnAppEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(void)
0x18002a507  nop
0x18002a508  cmp     [rbp+57h+var_80], r15
0x18002a50c  jz      short loc_18002A517
0x18002a50e  lea     rcx, [rbp+57h+var_80]
0x18002a512  call    ?unconditional_release_ref@?$com_ptr@UIWpnAppEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(void)
0x18002a517  mov     eax, ebx
0x18002a519  mov     rbx, [rsp+110h+arg_0]
0x18002a521  add     rsp, 0F0h
0x18002a528  pop     r15
0x18002a52a  pop     r14
0x18002a52c  pop     rdi
0x18002a52d  pop     rsi
0x18002a52e  pop     rbp
0x18002a52f  retn
```
