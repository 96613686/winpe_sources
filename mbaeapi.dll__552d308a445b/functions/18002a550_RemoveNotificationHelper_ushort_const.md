# RemoveNotificationHelper(ushort const *)

- ea: `0x18002a550`
- end: `0x18002a84c`
- name: `?RemoveNotificationHelper@@YAJPEBG@Z`
- size: `764`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002a540`
- `0x18002a860`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x18002a550`
- `0x18002b26c`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a589`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a589`

## string_xrefs

- `0x18002a5d1`: `CoCreateInstance failed with hr=0x%08x.`
- `0x18002a6ba`: `CreateAppEndpoint failed with hr=0x%08x.`
- `0x18002a5fc`: `RemoveNotificationHelper`
- `0x18002a6e5`: `RemoveNotificationHelper`
- `0x18002a7cc`: `RemoveNotificationHelper`
- `0x18002a7a1`: `RemoveNotifications failed with hr=0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RemoveNotificationHelper(const unsigned __int16 *a1)
{
  HRESULT v2; // ebx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned __int16 **v6; // rcx
  LPVOID v7; // rbx
  __int64 (__fastcall *v8)(LPVOID, __int64 *); // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  LPVOID *ppv; // [rsp+20h] [rbp-50h]
  LPVOID *ppva; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v18[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h]
  unsigned __int16 *v20[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v21; // [rsp+68h] [rbp-8h]
  __int64 v22; // [rsp+A8h] [rbp+38h] BYREF
  LPVOID v23; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 *v24; // [rsp+B8h] [rbp+48h] BYREF

  v23 = 0;
  v22 = 0;
  v2 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &v23);
  if ( v2 >= 0 )
  {
    v7 = v23;
    v8 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v23 + 24LL);
    if ( v22 )
      winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(&v22);
    v2 = v8(v7, &v22);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, wchar_t *, wchar_t *, _QWORD, const unsigned __int16 *, _QWORD))(*(_QWORD *)v22 + 80LL))(
             v22,
             aSystem_0,
             aWindowsSystemt,
             0,
             a1,
             0);
      if ( v2 >= 0 )
        goto LABEL_16;
      *(_OWORD *)v18 = 0;
      v19 = 0;
      *(_OWORD *)v20 = 0;
      v21 = 0;
      std::vector<unsigned short>::resize(v18);
      std::vector<unsigned short>::resize(v20);
      StringCchPrintfW(v18[0], v18[1] - v18[0], L"RemoveNotifications failed with hr=0x%08x.", (unsigned int)v2);
      LODWORD(ppva) = 262;
      StringCchPrintfW(v20[0], v20[1] - v20[0], L"%S(%d):%s", "RemoveNotificationHelper", ppva, v18[0]);
      v12 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v12 > 2u )
      {
        v24 = v20[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v12,
          (__int64)&word_180075FFE,
          v13,
          v14,
          (const unsigned __int16 **)&v24);
      }
    }
    else
    {
      *(_OWORD *)v18 = 0;
      v19 = 0;
      *(_OWORD *)v20 = 0;
      v21 = 0;
      std::vector<unsigned short>::resize(v18);
      std::vector<unsigned short>::resize(v20);
      StringCchPrintfW(v18[0], v18[1] - v18[0], L"CreateAppEndpoint failed with hr=0x%08x.", (unsigned int)v2);
      LODWORD(ppv) = 253;
      StringCchPrintfW(v20[0], v20[1] - v20[0], L"%S(%d):%s", "RemoveNotificationHelper", ppv, v18[0]);
      v9 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v9 > 2u )
      {
        v24 = v20[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v9,
          (__int64)&byte_18007601F,
          v10,
          v11,
          (const unsigned __int16 **)&v24);
      }
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
    v6 = v18;
  }
  else
  {
    *(_OWORD *)v20 = 0;
    v21 = 0;
    *(_OWORD *)v18 = 0;
    v19 = 0;
    std::vector<unsigned short>::resize(v20);
    std::vector<unsigned short>::resize(v18);
    StringCchPrintfW(v20[0], v20[1] - v20[0], L"CoCreateInstance failed with hr=0x%08x.", (unsigned int)v2);
    LODWORD(ppv) = 245;
    StringCchPrintfW(v18[0], v18[1] - v18[0], L"%S(%d):%s", "RemoveNotificationHelper", ppv, v20[0]);
    v3 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v3 > 2u )
    {
      v24 = v18[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v3,
        (__int64)qword_180076040,
        v4,
        v5,
        (const unsigned __int16 **)&v24);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
    v6 = v20;
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v6);
LABEL_16:
  if ( v22 )
    winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(&v22);
  if ( v23 )
    winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(&v23);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002a550  push    rbp
0x18002a552  push    rbx
0x18002a553  push    rsi
0x18002a554  push    rdi
0x18002a555  push    r14
0x18002a557  mov     rbp, rsp
0x18002a55a  sub     rsp, 70h
0x18002a55e  mov     rsi, rcx
0x18002a561  xor     r14d, r14d
0x18002a564  mov     [rbp+arg_10], r14
0x18002a568  mov     [rbp+arg_8], r14
0x18002a56c  lea     rax, [rbp+arg_10]
0x18002a570  mov     [rsp+70h+ppv], rax; ppv
0x18002a575  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18002a57c  xor     edx, edx; pUnkOuter
0x18002a57e  lea     r8d, [r14+4]; dwClsContext
0x18002a582  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18002a589  call    cs:__imp_CoCreateInstance
0x18002a58f  mov     ebx, eax
0x18002a591  test    eax, eax
0x18002a593  jns     loc_18002A64F
0x18002a599  xorps   xmm0, xmm0
0x18002a59c  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18002a5a1  mov     [rbp+var_8], r14
0x18002a5a5  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18002a5aa  mov     [rbp+var_20], r14
0x18002a5ae  lea     rcx, [rbp+var_18]
0x18002a5b2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a5b7  lea     rcx, [rbp+var_30]
0x18002a5bb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a5c0  mov     rdx, [rbp+var_18+8]
0x18002a5c4  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18002a5c8  sub     rdx, rcx
0x18002a5cb  sar     rdx, 1; unsigned __int64
0x18002a5ce  mov     r9d, ebx
0x18002a5d1  lea     r8, aCocreateinstan; "CoCreateInstance failed with hr=0x%08x."
0x18002a5d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a5dd  mov     rdx, [rbp+var_30+8]
0x18002a5e1  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18002a5e5  sub     rdx, rcx
0x18002a5e8  sar     rdx, 1; unsigned __int64
0x18002a5eb  mov     rax, [rbp+var_18]
0x18002a5ef  mov     [rsp+70h+var_48], rax
0x18002a5f4  mov     dword ptr [rsp+70h+ppv], 0F5h
0x18002a5fc  lea     r9, aRemovenotifica; "RemoveNotificationHelper"
0x18002a603  lea     r8, aSDS; "%S(%d):%s"
0x18002a60a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a60f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18002a614  mov     ecx, [rax]
0x18002a616  cmp     ecx, 2
0x18002a619  jbe     short loc_18002A63C
0x18002a61b  mov     rcx, [rbp+var_30]
0x18002a61f  mov     [rbp+arg_18], rcx
0x18002a623  lea     rcx, [rbp+arg_18]
0x18002a627  mov     [rsp+70h+ppv], rcx
0x18002a62c  lea     rdx, qword_180076040
0x18002a633  mov     rcx, rax
0x18002a636  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002a63b  nop
0x18002a63c  lea     rcx, [rbp+var_30]
0x18002a640  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002a645  nop
0x18002a646  lea     rcx, [rbp+var_18]
0x18002a64a  jmp     loc_18002A81A
0x18002a64f  mov     rbx, [rbp+arg_10]
0x18002a653  mov     rax, [rbx]
0x18002a656  mov     rdi, [rax+18h]
0x18002a65a  cmp     [rbp+arg_8], r14
0x18002a65e  jz      short loc_18002A669
0x18002a660  lea     rcx, [rbp+arg_8]
0x18002a664  call    ?unconditional_release_ref@?$com_ptr@UIWpnAppEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(void)
0x18002a669  lea     rdx, [rbp+arg_8]
0x18002a66d  mov     rcx, rbx
0x18002a670  mov     rax, rdi
0x18002a673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a678  mov     ebx, eax
0x18002a67a  test    eax, eax
0x18002a67c  jns     loc_18002A734
0x18002a682  xorps   xmm0, xmm0
0x18002a685  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18002a68a  mov     [rbp+var_20], r14
0x18002a68e  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18002a693  mov     [rbp+var_8], r14
0x18002a697  lea     rcx, [rbp+var_30]
0x18002a69b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a6a0  lea     rcx, [rbp+var_18]
0x18002a6a4  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a6a9  mov     rdx, [rbp+var_30+8]
0x18002a6ad  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18002a6b1  sub     rdx, rcx
0x18002a6b4  sar     rdx, 1; unsigned __int64
0x18002a6b7  mov     r9d, ebx
0x18002a6ba  lea     r8, aCreateappendpo; "CreateAppEndpoint failed with hr=0x%08x"...
0x18002a6c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a6c6  mov     rdx, [rbp+var_18+8]
0x18002a6ca  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18002a6ce  sub     rdx, rcx
0x18002a6d1  sar     rdx, 1; unsigned __int64
0x18002a6d4  mov     rax, [rbp+var_30]
0x18002a6d8  mov     [rsp+70h+var_48], rax
0x18002a6dd  mov     dword ptr [rsp+70h+ppv], 0FDh
0x18002a6e5  lea     r9, aRemovenotifica; "RemoveNotificationHelper"
0x18002a6ec  lea     r8, aSDS; "%S(%d):%s"
0x18002a6f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a6f8  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18002a6fd  mov     ecx, [rax]
0x18002a6ff  cmp     ecx, 2
0x18002a702  jbe     short loc_18002A725
0x18002a704  mov     rcx, [rbp+var_18]
0x18002a708  mov     [rbp+arg_18], rcx
0x18002a70c  lea     rcx, [rbp+arg_18]
0x18002a710  mov     [rsp+70h+ppv], rcx
0x18002a715  lea     rdx, byte_18007601F
0x18002a71c  mov     rcx, rax
0x18002a71f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002a724  nop
0x18002a725  lea     rcx, [rbp+var_18]
0x18002a729  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002a72e  nop
0x18002a72f  jmp     loc_18002A816
0x18002a734  mov     rcx, [rbp+arg_8]
0x18002a738  mov     rax, [rcx]
0x18002a73b  mov     [rsp+70h+var_48], r14
0x18002a740  mov     [rsp+70h+ppv], rsi
0x18002a745  xor     r9d, r9d
0x18002a748  lea     r8, aWindowsSystemt; "Windows.SystemToast.Wwansvc"
0x18002a74f  lea     rdx, aSystem_0; "System"
0x18002a756  mov     rax, [rax+50h]
0x18002a75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a75f  mov     ebx, eax
0x18002a761  test    eax, eax
0x18002a763  jns     loc_18002A820
0x18002a769  xorps   xmm0, xmm0
0x18002a76c  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18002a771  mov     [rbp+var_20], r14
0x18002a775  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18002a77a  mov     [rbp+var_8], r14
0x18002a77e  lea     rcx, [rbp+var_30]
0x18002a782  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a787  lea     rcx, [rbp+var_18]
0x18002a78b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a790  mov     rdx, [rbp+var_30+8]
0x18002a794  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18002a798  sub     rdx, rcx
0x18002a79b  sar     rdx, 1; unsigned __int64
0x18002a79e  mov     r9d, ebx
0x18002a7a1  lea     r8, aRemovenotifica_0; "RemoveNotifications failed with hr=0x%0"...
0x18002a7a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a7ad  mov     rdx, [rbp+var_18+8]
0x18002a7b1  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18002a7b5  sub     rdx, rcx
0x18002a7b8  sar     rdx, 1; unsigned __int64
0x18002a7bb  mov     rax, [rbp+var_30]
0x18002a7bf  mov     [rsp+70h+var_48], rax
0x18002a7c4  mov     dword ptr [rsp+70h+ppv], 106h
0x18002a7cc  lea     r9, aRemovenotifica; "RemoveNotificationHelper"
0x18002a7d3  lea     r8, aSDS; "%S(%d):%s"
0x18002a7da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a7df  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18002a7e4  mov     ecx, [rax]
0x18002a7e6  cmp     ecx, 2
0x18002a7e9  jbe     short loc_18002A80C
0x18002a7eb  mov     rcx, [rbp+var_18]
0x18002a7ef  mov     [rbp+arg_18], rcx
0x18002a7f3  lea     rcx, [rbp+arg_18]
0x18002a7f7  mov     [rsp+70h+ppv], rcx
0x18002a7fc  lea     rdx, word_180075FFE
0x18002a803  mov     rcx, rax
0x18002a806  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002a80b  nop
0x18002a80c  lea     rcx, [rbp+var_18]
0x18002a810  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002a815  nop
0x18002a816  lea     rcx, [rbp+var_30]
0x18002a81a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002a81f  nop
0x18002a820  cmp     [rbp+arg_8], r14
0x18002a824  jz      short loc_18002A830
0x18002a826  lea     rcx, [rbp+arg_8]
0x18002a82a  call    ?unconditional_release_ref@?$com_ptr@UIWpnAppEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(void)
0x18002a82f  nop
0x18002a830  cmp     [rbp+arg_10], r14
0x18002a834  jz      short loc_18002A83F
0x18002a836  lea     rcx, [rbp+arg_10]
0x18002a83a  call    ?unconditional_release_ref@?$com_ptr@UIWpnAppEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnAppEndpoint>::unconditional_release_ref(void)
0x18002a83f  mov     eax, ebx
0x18002a841  add     rsp, 70h
0x18002a845  pop     r14
0x18002a847  pop     rdi
0x18002a848  pop     rsi
0x18002a849  pop     rbx
0x18002a84a  pop     rbp
0x18002a84b  retn
```
