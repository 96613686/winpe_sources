# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x180008de0`
- end: `0x180009025`
- name: `?ReportStopActivity@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800087b8`
- `0x1800091c4`

## callees

- `0x180001010`
- `0x1800019bc`
- `0x180001e74`
- `0x180008ca0`
- `0x180008de0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fb0`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  __int64 v16; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  int v21; // [rsp+A0h] [rbp-19h] BYREF
  int v22; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-11h] BYREF
  __int64 *v24; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v25; // [rsp+B8h] [rbp-1h] BYREF
  __int64 *v26; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v27; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v28; // [rsp+D0h] [rbp+17h] BYREF
  __int64 *v29; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v30; // [rsp+E0h] [rbp+27h] BYREF
  const unsigned __int16 *v31; // [rsp+E8h] [rbp+2Fh] BYREF
  int v32; // [rsp+120h] [rbp+67h] BYREF
  DWORD v33; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 *v34; // [rsp+130h] [rbp+77h] BYREF
  const unsigned __int16 *v35; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
      if ( *(_DWORD *)v7 > 2u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL, v8, v7) )
      {
        v10 = *(__int64 **)(v6 + 120);
        v11 = a1[34];
        v25 = *(const unsigned __int16 **)(v6 + 112);
        v33 = *(_DWORD *)(v6 + 104);
        v26 = *(__int64 **)(v6 + 96);
        v27 = *(const unsigned __int16 **)(v6 + 88);
        v32 = *(_DWORD *)(v6 + 80);
        v28 = *(const unsigned __int16 **)(v6 + 72);
        LODWORD(v34) = *(_DWORD *)(v6 + 32);
        v29 = *(__int64 **)(v6 + 24);
        LODWORD(v35) = *(_DWORD *)v6;
        v30 = *(const unsigned __int16 **)(v6 + 128);
        v21 = *(_DWORD *)(v6 + 64);
        v31 = *(const unsigned __int16 **)(v6 + 56);
        v22 = *(_DWORD *)(v6 + 8);
        v24 = v10;
        v23 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v9,
          (__int64)qword_18001F818,
          v11 + 8,
          v9,
          (__int64)&v23,
          (__int64)&v22,
          &v31,
          (__int64)&v21,
          &v30,
          (__int64)&v35,
          &v29,
          (__int64)&v34,
          &v28,
          (__int64)&v32,
          &v27,
          &v26,
          (__int64)&v33,
          &v25,
          &v24);
      }
    }
    else
    {
      v12 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
      v15 = (__int64)v12;
      if ( *(_DWORD *)v12 > 2u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL, v13, v14) )
      {
        v16 = a1[34];
        v34 = *(__int64 **)(v16 + 56);
        v35 = *(const unsigned __int16 **)(v16 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v18 = a1[34];
        v33 = CurrentThreadId;
        v32 = a2;
        v23 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v15,
          (__int64)&byte_18001F92F,
          v18 + 8,
          v19,
          (__int64)&v23,
          (__int64)&v32,
          (__int64)&v33,
          &v35,
          &v34);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x180008de0  push    rbp
0x180008de2  push    rbx
0x180008de3  push    rsi
0x180008de4  push    rdi
0x180008de5  lea     rbp, [rsp-3Fh]
0x180008dea  sub     rsp, 0F8h
0x180008df1  mov     esi, edx
0x180008df3  mov     rbx, rcx
0x180008df6  test    edx, edx
0x180008df8  jns     loc_18000900B
0x180008dfe  mov     rdi, [rcx+110h]
0x180008e05  mov     eax, [rdi+48h]
0x180008e08  test    eax, eax
0x180008e0a  jns     loc_180008F70
0x180008e10  add     rdi, 50h ; 'P'
0x180008e14  cmp     eax, [rdi+8]
0x180008e17  jnz     loc_180008F70
0x180008e1d  test    rdi, rdi
0x180008e20  jz      loc_180008F70
0x180008e26  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180008e2b  mov     r9, rax
0x180008e2e  mov     ecx, [rax]
0x180008e30  cmp     ecx, 2
0x180008e33  jbe     loc_18000900B
0x180008e39  mov     rdx, 200000000000h
0x180008e43  mov     rcx, rax
0x180008e46  call    _tlgKeywordOn
0x180008e4b  test    al, al
0x180008e4d  jz      loc_18000900B
0x180008e53  mov     rax, [rdi+70h]
0x180008e57  lea     rdx, qword_18001F818
0x180008e5e  mov     rcx, [rdi+78h]
0x180008e62  mov     r8, [rbx+110h]
0x180008e69  mov     [rbp+57h+var_58], rax
0x180008e6d  add     r8, 8
0x180008e71  mov     eax, [rdi+68h]
0x180008e74  mov     [rbp+57h+arg_8], eax
0x180008e77  mov     rax, [rdi+60h]
0x180008e7b  mov     [rbp+57h+var_50], rax
0x180008e7f  mov     rax, [rdi+58h]
0x180008e83  mov     [rbp+57h+var_48], rax
0x180008e87  mov     eax, [rdi+50h]
0x180008e8a  mov     [rbp+57h+arg_0], eax
0x180008e8d  mov     rax, [rdi+48h]
0x180008e91  mov     [rbp+57h+var_40], rax
0x180008e95  mov     eax, [rdi+20h]
0x180008e98  mov     dword ptr [rbp+57h+arg_10], eax
0x180008e9b  mov     rax, [rdi+18h]
0x180008e9f  mov     [rbp+57h+var_38], rax
0x180008ea3  mov     eax, [rdi]
0x180008ea5  mov     dword ptr [rbp+57h+arg_18], eax
0x180008ea8  mov     rax, [rdi+80h]
0x180008eaf  mov     [rbp+57h+var_30], rax
0x180008eb3  mov     eax, [rdi+40h]
0x180008eb6  mov     [rbp+57h+var_70], eax
0x180008eb9  mov     rax, [rdi+38h]
0x180008ebd  mov     [rbp+57h+var_28], rax
0x180008ec1  mov     eax, [rdi+8]
0x180008ec4  mov     [rbp+57h+var_6C], eax
0x180008ec7  lea     rax, [rbp+57h+var_60]
0x180008ecb  mov     [rsp+110h+var_80], rax
0x180008ed3  lea     rax, [rbp+57h+var_58]
0x180008ed7  mov     [rsp+110h+var_88], rax
0x180008edf  lea     rax, [rbp+57h+arg_8]
0x180008ee3  mov     [rsp+110h+var_90], rax
0x180008eeb  lea     rax, [rbp+57h+var_50]
0x180008eef  mov     [rsp+110h+var_98], rax
0x180008ef4  lea     rax, [rbp+57h+var_48]
0x180008ef8  mov     [rsp+110h+var_A0], rax
0x180008efd  lea     rax, [rbp+57h+arg_0]
0x180008f01  mov     [rsp+110h+var_A8], rax
0x180008f06  lea     rax, [rbp+57h+var_40]
0x180008f0a  mov     [rsp+110h+var_B0], rax
0x180008f0f  lea     rax, [rbp+57h+arg_10]
0x180008f13  mov     [rsp+110h+var_B8], rax
0x180008f18  lea     rax, [rbp+57h+var_38]
0x180008f1c  mov     [rsp+110h+var_C0], rax
0x180008f21  lea     rax, [rbp+57h+arg_18]
0x180008f25  mov     [rsp+110h+var_C8], rax
0x180008f2a  lea     rax, [rbp+57h+var_30]
0x180008f2e  mov     [rsp+110h+var_D0], rax
0x180008f33  lea     rax, [rbp+57h+var_70]
0x180008f37  mov     [rsp+110h+var_D8], rax
0x180008f3c  lea     rax, [rbp+57h+var_28]
0x180008f40  mov     [rsp+110h+var_E0], rax
0x180008f45  lea     rax, [rbp+57h+var_6C]
0x180008f49  mov     [rsp+110h+var_E8], rax
0x180008f4e  lea     rax, [rbp+57h+var_68]
0x180008f52  mov     [rbp+57h+var_60], rcx
0x180008f56  mov     rcx, r9
0x180008f59  mov     [rsp+110h+var_F0], rax
0x180008f5e  mov     [rbp+57h+var_68], 1000000h
0x180008f66  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180008f6b  jmp     loc_18000900B
0x180008f70  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180008f75  mov     rdi, rax
0x180008f78  mov     ecx, [rax]
0x180008f7a  cmp     ecx, 2
0x180008f7d  jbe     loc_18000900B
0x180008f83  mov     rdx, 200000000000h
0x180008f8d  mov     rcx, rax
0x180008f90  call    _tlgKeywordOn
0x180008f95  test    al, al
0x180008f97  jz      short loc_18000900B
0x180008f99  mov     rcx, [rbx+110h]
0x180008fa0  mov     rax, [rcx+38h]
0x180008fa4  mov     [rbp+57h+arg_10], rax
0x180008fa8  mov     rax, [rcx+30h]
0x180008fac  mov     [rbp+57h+arg_18], rax
0x180008fb0  call    cs:__imp_GetCurrentThreadId
0x180008fb6  mov     r8, [rbx+110h]
0x180008fbd  lea     rdx, byte_18001F92F
0x180008fc4  mov     [rbp+57h+arg_8], eax
0x180008fc7  add     r8, 8
0x180008fcb  lea     rax, [rbp+57h+arg_10]
0x180008fcf  mov     [rbp+57h+arg_0], esi
0x180008fd2  mov     [rsp+110h+var_D0], rax
0x180008fd7  mov     rcx, rdi
0x180008fda  lea     rax, [rbp+57h+arg_18]
0x180008fde  mov     [rbp+57h+var_68], 1000000h
0x180008fe6  mov     [rsp+110h+var_D8], rax
0x180008feb  lea     rax, [rbp+57h+arg_8]
0x180008fef  mov     [rsp+110h+var_E0], rax
0x180008ff4  lea     rax, [rbp+57h+arg_0]
0x180008ff8  mov     [rsp+110h+var_E8], rax
0x180008ffd  lea     rax, [rbp+57h+var_68]
0x180009001  mov     [rsp+110h+var_F0], rax
0x180009006  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000900b  mov     rax, [rbx]
0x18000900e  mov     rcx, rbx
0x180009011  mov     rax, [rax+8]
0x180009015  add     rsp, 0F8h
0x18000901c  pop     rdi
0x18000901d  pop     rsi
0x18000901e  pop     rbx
0x18000901f  pop     rbp
0x180009020  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
