# CWwanTranslator::DeleteProxy(ushort const *,_GUID const &)

- ea: `0x180033b84`
- end: `0x180033e1c`
- name: `?DeleteProxy@CWwanTranslator@@SAJPEBGAEBU_GUID@@@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180046960`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180033b84`

## import_xrefs

- `wcmapi!WcmDeleteProxyInformation` at `0x180033c63`
- `wcmapi!WcmDeleteProxyInformation` at `0x180033c63`

## string_xrefs

- `0x180033caf`: `Cannot find the proxy information. Could be deleted already.`
- `0x180033c04`: `CWwanTranslator::DeleteProxy`
- `0x180033cda`: `CWwanTranslator::DeleteProxy`
- `0x180033d95`: `CWwanTranslator::DeleteProxy`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall CWwanTranslator::DeleteProxy(const unsigned __int16 *a1, const struct _GUID *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // eax
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int v15[2]; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v16[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v17; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v18[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v19; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  unsigned __int16 *v21; // [rsp+80h] [rbp+20h] BYREF

  *(_OWORD *)v18 = 0;
  v19 = 0;
  *(_OWORD *)v16 = 0;
  v17 = 0;
  std::vector<unsigned short>::resize(v18);
  std::vector<unsigned short>::resize(v16);
  StringCchPrintfW(v18[0], v18[1] - v18[0], L"Enter");
  v15[0] = 2204;
  StringCchPrintfW(v16[0], v16[1] - v16[0], L"%S(%d):%s", "CWwanTranslator::DeleteProxy");
  v4 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    v21 = v16[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)qword_180076B88,
      v5,
      v6,
      (const unsigned __int16 **)&v21);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v16);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
  v7 = WcmDeleteProxyInformation(a2, a1, 1);
  if ( v7 == 2 )
  {
    *(_OWORD *)v16 = 0;
    v17 = 0;
    *(_OWORD *)v18 = 0;
    v19 = 0;
    std::vector<unsigned short>::resize(v16);
    std::vector<unsigned short>::resize(v18);
    StringCchPrintfW(v16[0], v16[1] - v16[0], L"Cannot find the proxy information. Could be deleted already.");
    v15[0] = 2210;
    StringCchPrintfW(v18[0], v18[1] - v18[0], L"%S(%d):%s", "CWwanTranslator::DeleteProxy", *(_QWORD *)v15, v16[0]);
    v8 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v8 > 4u )
    {
      v21 = v18[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v8,
        (__int64)word_180076B22,
        v9,
        v10,
        (const unsigned __int16 **)&v21);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v16);
  }
  else if ( v7 )
  {
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x8A6,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
             (const char *)v7,
             v15[0]);
  }
  *(_OWORD *)v16 = 0;
  v17 = 0;
  *(_OWORD *)v18 = 0;
  v19 = 0;
  std::vector<unsigned short>::resize(v16);
  std::vector<unsigned short>::resize(v18);
  StringCchPrintfW(v16[0], v16[1] - v16[0], L"Exit");
  v15[0] = 2217;
  StringCchPrintfW(v18[0], v18[1] - v18[0], L"%S(%d):%s", "CWwanTranslator::DeleteProxy", *(_QWORD *)v15, v16[0]);
  v11 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v11 > 5u )
  {
    v21 = v18[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v11,
      (__int64)word_180076B42,
      v12,
      v13,
      (const unsigned __int16 **)&v21);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v16);
  return 0;
}

```

## disassembly

```asm
0x180033b84  mov     [rsp-8+arg_0], rbx
0x180033b89  mov     [rsp-8+arg_8], rdi
0x180033b8e  push    rbp
0x180033b8f  mov     rbp, rsp
0x180033b92  sub     rsp, 60h
0x180033b96  mov     rbx, rdx
0x180033b99  mov     rdi, rcx
0x180033b9c  xorps   xmm0, xmm0
0x180033b9f  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180033ba4  mov     [rbp+var_8], 0
0x180033bac  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180033bb1  mov     [rbp+var_20], 0
0x180033bb9  lea     rcx, [rbp+var_18]
0x180033bbd  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180033bc2  lea     rcx, [rbp+var_30]
0x180033bc6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180033bcb  mov     rdx, [rbp+var_18+8]
0x180033bcf  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180033bd3  sub     rdx, rcx
0x180033bd6  sar     rdx, 1; unsigned __int64
0x180033bd9  lea     r8, aEnter; "Enter"
0x180033be0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033be5  mov     rdx, [rbp+var_30+8]
0x180033be9  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180033bed  sub     rdx, rcx
0x180033bf0  sar     rdx, 1; unsigned __int64
0x180033bf3  mov     rax, [rbp+var_18]
0x180033bf7  mov     [rsp+60h+var_38], rax
0x180033bfc  mov     [rsp+60h+var_40], 89Ch
0x180033c04  lea     r9, aCwwantranslato_24; "CWwanTranslator::DeleteProxy"
0x180033c0b  lea     r8, aSDS; "%S(%d):%s"
0x180033c12  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033c17  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180033c1c  mov     ecx, [rax]
0x180033c1e  cmp     ecx, 5
0x180033c21  jbe     short loc_180033C44
0x180033c23  mov     rcx, [rbp+var_30]
0x180033c27  mov     [rbp+arg_10], rcx
0x180033c2b  lea     rcx, [rbp+arg_10]
0x180033c2f  mov     qword ptr [rsp+60h+var_40], rcx; unsigned int
0x180033c34  lea     rdx, qword_180076B88
0x180033c3b  mov     rcx, rax
0x180033c3e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180033c43  nop
0x180033c44  lea     rcx, [rbp+var_30]
0x180033c48  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180033c4d  nop
0x180033c4e  lea     rcx, [rbp+var_18]
0x180033c52  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180033c57  mov     r8d, 1
0x180033c5d  mov     rdx, rdi
0x180033c60  mov     rcx, rbx
0x180033c63  call    cs:__imp_WcmDeleteProxyInformation
0x180033c69  cmp     eax, 2
0x180033c6c  jnz     loc_180033DFA
0x180033c72  xorps   xmm0, xmm0
0x180033c75  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180033c7a  mov     [rbp+var_20], 0
0x180033c82  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180033c87  mov     [rbp+var_8], 0
0x180033c8f  lea     rcx, [rbp+var_30]
0x180033c93  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180033c98  lea     rcx, [rbp+var_18]
0x180033c9c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180033ca1  mov     rdx, [rbp+var_30+8]
0x180033ca5  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180033ca9  sub     rdx, rcx
0x180033cac  sar     rdx, 1; unsigned __int64
0x180033caf  lea     r8, aCannotFindTheP; "Cannot find the proxy information. Coul"...
0x180033cb6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033cbb  mov     rdx, [rbp+var_18+8]
0x180033cbf  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180033cc3  sub     rdx, rcx
0x180033cc6  sar     rdx, 1; unsigned __int64
0x180033cc9  mov     rax, [rbp+var_30]
0x180033ccd  mov     [rsp+60h+var_38], rax
0x180033cd2  mov     [rsp+60h+var_40], 8A2h
0x180033cda  lea     r9, aCwwantranslato_24; "CWwanTranslator::DeleteProxy"
0x180033ce1  lea     r8, aSDS; "%S(%d):%s"
0x180033ce8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033ced  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180033cf2  mov     ecx, [rax]
0x180033cf4  cmp     ecx, 4
0x180033cf7  jbe     short loc_180033D1A
0x180033cf9  mov     rcx, [rbp+var_18]
0x180033cfd  mov     [rbp+arg_10], rcx
0x180033d01  lea     rcx, [rbp+arg_10]
0x180033d05  mov     qword ptr [rsp+60h+var_40], rcx
0x180033d0a  lea     rdx, word_180076B22
0x180033d11  mov     rcx, rax
0x180033d14  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180033d19  nop
0x180033d1a  lea     rcx, [rbp+var_18]
0x180033d1e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180033d23  nop
0x180033d24  lea     rcx, [rbp+var_30]
0x180033d28  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180033d2d  xorps   xmm0, xmm0
0x180033d30  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180033d35  mov     [rbp+var_20], 0
0x180033d3d  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180033d42  mov     [rbp+var_8], 0
0x180033d4a  lea     rcx, [rbp+var_30]
0x180033d4e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180033d53  lea     rcx, [rbp+var_18]
0x180033d57  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180033d5c  mov     rdx, [rbp+var_30+8]
0x180033d60  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180033d64  sub     rdx, rcx
0x180033d67  sar     rdx, 1; unsigned __int64
0x180033d6a  lea     r8, aExit; "Exit"
0x180033d71  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033d76  mov     rdx, [rbp+var_18+8]
0x180033d7a  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180033d7e  sub     rdx, rcx
0x180033d81  sar     rdx, 1; unsigned __int64
0x180033d84  mov     rax, [rbp+var_30]
0x180033d88  mov     [rsp+60h+var_38], rax
0x180033d8d  mov     [rsp+60h+var_40], 8A9h
0x180033d95  lea     r9, aCwwantranslato_24; "CWwanTranslator::DeleteProxy"
0x180033d9c  lea     r8, aSDS; "%S(%d):%s"
0x180033da3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033da8  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180033dad  mov     ecx, [rax]
0x180033daf  cmp     ecx, 5
0x180033db2  jbe     short loc_180033DD5
0x180033db4  mov     rcx, [rbp+var_18]
0x180033db8  mov     [rbp+arg_10], rcx
0x180033dbc  lea     rcx, [rbp+arg_10]
0x180033dc0  mov     qword ptr [rsp+60h+var_40], rcx
0x180033dc5  lea     rdx, word_180076B42
0x180033dcc  mov     rcx, rax
0x180033dcf  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180033dd4  nop
0x180033dd5  lea     rcx, [rbp+var_18]
0x180033dd9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180033dde  nop
0x180033ddf  lea     rcx, [rbp+var_30]
0x180033de3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180033de8  xor     eax, eax
0x180033dea  mov     rbx, [rsp+60h+arg_0]
0x180033def  mov     rdi, [rsp+60h+arg_8]
0x180033df4  add     rsp, 60h
0x180033df8  pop     rbp
0x180033df9  retn
0x180033dfa  test    eax, eax
0x180033dfc  jz      loc_180033D2D
0x180033e02  mov     rcx, [rbp+8]; this
0x180033e06  mov     r9d, eax; char *
0x180033e09  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180033e10  mov     edx, 8A6h; void *
0x180033e15  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033e1a  jmp     short loc_180033DEA
```
