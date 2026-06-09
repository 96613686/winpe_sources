# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)

- ea: `0x18000d4b8`
- end: `0x18000d74d`
- name: `?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z`
- size: `661`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this, bool, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000e11c`

## callees

- `0x1800016a8`
- `0x180001b0c`
- `0x18000247c`
- `0x18000b044`
- `0x18000c3bc`
- `0x18000d4b8`
- `0x18000fac8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d6ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d6ce`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this,
        char a2,
        char a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // rdi
  int v9; // eax
  int *v10; // rdi
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r9
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  _BYTE v19[4]; // [rsp+C0h] [rbp-80h] BYREF
  int v20; // [rsp+C4h] [rbp-7Ch] BYREF
  DWORD v21; // [rsp+C8h] [rbp-78h] BYREF
  int v22; // [rsp+CCh] [rbp-74h] BYREF
  int v23; // [rsp+D0h] [rbp-70h] BYREF
  int v24; // [rsp+D4h] [rbp-6Ch] BYREF
  int v25; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v27; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v28; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v29; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v30; // [rsp+100h] [rbp-40h] BYREF
  __int64 v31; // [rsp+108h] [rbp-38h] BYREF
  __int64 v32; // [rsp+110h] [rbp-30h] BYREF
  __int64 v33; // [rsp+118h] [rbp-28h] BYREF
  __int64 v34; // [rsp+120h] [rbp-20h] BYREF
  __int64 v35; // [rsp+128h] [rbp-18h] BYREF
  _QWORD v36[8]; // [rsp+130h] [rbp-10h] BYREF
  char v37; // [rsp+180h] [rbp+40h] BYREF

  v4 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = (int *)(v4 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      v29 = *((_QWORD *)v10 + 15);
      v30 = *((_QWORD *)v10 + 14);
      v13 = *((_QWORD *)this + 34);
      v22 = v10[26];
      v31 = *((_QWORD *)v10 + 12);
      v32 = *((_QWORD *)v10 + 11);
      v23 = v10[20];
      v33 = *((_QWORD *)v10 + 9);
      v24 = v10[8];
      v34 = *((_QWORD *)v10 + 3);
      v25 = *v10;
      v35 = *((_QWORD *)v10 + 16);
      v20 = v10[16];
      v36[0] = *((_QWORD *)v10 + 7);
      v21 = v10[2];
      v28 = a4;
      v37 = a3;
      v19[0] = a2;
      v26 = 0x1000000;
      v27 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v12,
        (__int64)&dword_1800290D4,
        v13 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v21,
        v36,
        (__int64)&v20,
        &v35,
        (__int64)&v25,
        &v34,
        (__int64)&v24,
        &v33,
        (__int64)&v23,
        &v32,
        &v31,
        (__int64)&v22,
        &v30,
        &v29,
        (__int64)v19,
        (__int64)&v37,
        &v28);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL) )
    {
      v27 = a4;
      v37 = a3;
      v19[0] = a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v21 = CurrentThreadId;
      v20 = *(_DWORD *)(v17 + 72);
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v15,
        (__int64)&byte_180028A3F,
        v17 + 8,
        v18,
        (__int64)&v26,
        (__int64)&v20,
        (__int64)&v21,
        (__int64)v19,
        (__int64)&v37,
        &v27);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000d4b8  push    rbp
0x18000d4ba  push    rbx
0x18000d4bb  push    rsi
0x18000d4bc  push    rdi
0x18000d4bd  push    r14
0x18000d4bf  push    r15
0x18000d4c1  lea     rbp, [rsp-8]
0x18000d4c6  sub     rsp, 148h
0x18000d4cd  mov     rdi, [rcx+110h]
0x18000d4d4  mov     rsi, r9
0x18000d4d7  mov     r14b, r8b
0x18000d4da  mov     r15b, dl
0x18000d4dd  mov     rbx, rcx
0x18000d4e0  mov     eax, [rdi+48h]
0x18000d4e3  test    eax, eax
0x18000d4e5  jns     loc_18000D694
0x18000d4eb  add     rdi, 50h ; 'P'
0x18000d4ef  cmp     eax, [rdi+8]
0x18000d4f2  jnz     loc_18000D694
0x18000d4f8  test    rdi, rdi
0x18000d4fb  jz      loc_18000D694
0x18000d501  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000d506  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000d50b  mov     r9, rax
0x18000d50e  mov     ecx, [rax]
0x18000d510  cmp     ecx, 5
0x18000d513  jbe     loc_18000D736
0x18000d519  mov     rdx, 400000000000h
0x18000d523  mov     rcx, rax
0x18000d526  call    _tlgKeywordOn
0x18000d52b  test    al, al
0x18000d52d  jz      loc_18000D736
0x18000d533  mov     rax, [rdi+78h]
0x18000d537  lea     rdx, dword_1800290D4
0x18000d53e  mov     [rbp+30h+var_78], rax
0x18000d542  mov     rcx, r9
0x18000d545  mov     rax, [rdi+70h]
0x18000d549  mov     [rbp+30h+var_70], rax
0x18000d54d  mov     eax, [rdi+68h]
0x18000d550  mov     r8, [rbx+110h]
0x18000d557  mov     [rbp+30h+var_A4], eax
0x18000d55a  add     r8, 8
0x18000d55e  mov     rax, [rdi+60h]
0x18000d562  mov     [rbp+30h+var_68], rax
0x18000d566  mov     rax, [rdi+58h]
0x18000d56a  mov     [rbp+30h+var_60], rax
0x18000d56e  mov     eax, [rdi+50h]
0x18000d571  mov     [rbp+30h+var_A0], eax
0x18000d574  mov     rax, [rdi+48h]
0x18000d578  mov     [rbp+30h+var_58], rax
0x18000d57c  mov     eax, [rdi+20h]
0x18000d57f  mov     [rbp+30h+var_9C], eax
0x18000d582  mov     rax, [rdi+18h]
0x18000d586  mov     [rbp+30h+var_50], rax
0x18000d58a  mov     eax, [rdi]
0x18000d58c  mov     [rbp+30h+var_98], eax
0x18000d58f  mov     rax, [rdi+80h]
0x18000d596  mov     [rbp+30h+var_48], rax
0x18000d59a  mov     eax, [rdi+40h]
0x18000d59d  mov     [rbp+30h+var_AC], eax
0x18000d5a0  mov     rax, [rdi+38h]
0x18000d5a4  mov     [rbp+30h+var_40], rax
0x18000d5a8  mov     eax, [rdi+8]
0x18000d5ab  mov     [rbp+30h+var_A8], eax
0x18000d5ae  lea     rax, [rbp+30h+var_80]
0x18000d5b2  mov     [rsp+170h+var_C0], rax
0x18000d5ba  lea     rax, [rbp+30h+arg_0]
0x18000d5be  mov     [rsp+170h+var_C8], rax
0x18000d5c6  lea     rax, [rbp+30h+var_B0]
0x18000d5ca  mov     [rsp+170h+var_D0], rax
0x18000d5d2  lea     rax, [rbp+30h+var_78]
0x18000d5d6  mov     [rsp+170h+var_D8], rax
0x18000d5de  lea     rax, [rbp+30h+var_70]
0x18000d5e2  mov     [rsp+170h+var_E0], rax
0x18000d5ea  lea     rax, [rbp+30h+var_A4]
0x18000d5ee  mov     [rsp+170h+var_E8], rax
0x18000d5f6  lea     rax, [rbp+30h+var_68]
0x18000d5fa  mov     [rsp+170h+var_F0], rax
0x18000d602  lea     rax, [rbp+30h+var_60]
0x18000d606  mov     [rsp+170h+var_F8], rax
0x18000d60b  lea     rax, [rbp+30h+var_A0]
0x18000d60f  mov     [rsp+170h+var_100], rax
0x18000d614  lea     rax, [rbp+30h+var_58]
0x18000d618  mov     [rsp+170h+var_108], rax
0x18000d61d  lea     rax, [rbp+30h+var_9C]
0x18000d621  mov     [rsp+170h+var_110], rax
0x18000d626  lea     rax, [rbp+30h+var_50]
0x18000d62a  mov     [rsp+170h+var_118], rax
0x18000d62f  lea     rax, [rbp+30h+var_98]
0x18000d633  mov     [rsp+170h+var_120], rax
0x18000d638  lea     rax, [rbp+30h+var_48]
0x18000d63c  mov     [rsp+170h+var_128], rax
0x18000d641  lea     rax, [rbp+30h+var_AC]
0x18000d645  mov     [rsp+170h+var_130], rax
0x18000d64a  lea     rax, [rbp+30h+var_40]
0x18000d64e  mov     [rsp+170h+var_138], rax
0x18000d653  lea     rax, [rbp+30h+var_A8]
0x18000d657  mov     [rsp+170h+var_140], rax
0x18000d65c  lea     rax, [rbp+30h+var_90]
0x18000d660  mov     [rsp+170h+var_148], rax
0x18000d665  lea     rax, [rbp+30h+var_88]
0x18000d669  mov     [rsp+170h+var_150], rax
0x18000d66e  mov     [rbp+30h+var_80], rsi
0x18000d672  mov     [rbp+30h+arg_0], r14b
0x18000d676  mov     [rbp+30h+var_B0], r15b
0x18000d67a  mov     [rbp+30h+var_90], 1000000h
0x18000d682  mov     [rbp+30h+var_88], 0
0x18000d68a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U5@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@76@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18000d68f  jmp     loc_18000D736
0x18000d694  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000d699  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000d69e  mov     rdi, rax
0x18000d6a1  mov     ecx, [rax]
0x18000d6a3  cmp     ecx, 5
0x18000d6a6  jbe     loc_18000D736
0x18000d6ac  mov     rdx, 400000000000h
0x18000d6b6  mov     rcx, rax
0x18000d6b9  call    _tlgKeywordOn
0x18000d6be  test    al, al
0x18000d6c0  jz      short loc_18000D736
0x18000d6c2  mov     [rbp+30h+var_88], rsi
0x18000d6c6  mov     [rbp+30h+arg_0], r14b
0x18000d6ca  mov     [rbp+30h+var_B0], r15b
0x18000d6ce  call    cs:__imp_GetCurrentThreadId
0x18000d6d4  mov     r8, [rbx+110h]
0x18000d6db  lea     rdx, byte_180028A3F
0x18000d6e2  mov     [rbp+30h+var_A8], eax
0x18000d6e5  mov     rcx, rdi
0x18000d6e8  mov     eax, [r8+48h]
0x18000d6ec  add     r8, 8
0x18000d6f0  mov     [rbp+30h+var_AC], eax
0x18000d6f3  lea     rax, [rbp+30h+var_88]
0x18000d6f7  mov     [rsp+170h+var_128], rax
0x18000d6fc  lea     rax, [rbp+30h+arg_0]
0x18000d700  mov     [rsp+170h+var_130], rax
0x18000d705  lea     rax, [rbp+30h+var_B0]
0x18000d709  mov     [rsp+170h+var_138], rax
0x18000d70e  lea     rax, [rbp+30h+var_A8]
0x18000d712  mov     [rsp+170h+var_140], rax
0x18000d717  lea     rax, [rbp+30h+var_AC]
0x18000d71b  mov     [rsp+170h+var_148], rax
0x18000d720  lea     rax, [rbp+30h+var_90]
0x18000d724  mov     [rsp+170h+var_150], rax
0x18000d729  mov     [rbp+30h+var_90], 0
0x18000d731  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U3@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@5AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18000d736  mov     rcx, rbx
0x18000d739  add     rsp, 148h
0x18000d740  pop     r15
0x18000d742  pop     r14
0x18000d744  pop     rdi
0x18000d745  pop     rsi
0x18000d746  pop     rbx
0x18000d747  pop     rbp
0x18000d748  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
