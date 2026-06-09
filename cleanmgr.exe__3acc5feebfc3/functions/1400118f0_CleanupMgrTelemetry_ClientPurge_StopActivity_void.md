# CleanupMgrTelemetry::ClientPurge::StopActivity(void)

- ea: `0x1400118f0`
- end: `0x140011b12`
- name: `?StopActivity@ClientPurge@CleanupMgrTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(CleanupMgrTelemetry::ClientPurge *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400012b8`
- `0x1400019bc`
- `0x1400022a0`
- `0x14000e15c`
- `0x14000fc6c`
- `0x1400118f0`
- `0x140016020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011ab2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011ab2`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::ClientPurge::StopActivity(CleanupMgrTelemetry::ClientPurge *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v20; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v21; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v22; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v23; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v25; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v26; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v27; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v28; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v29[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v30; // [rsp+120h] [rbp+67h] BYREF
  int v31; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+130h] [rbp+77h] BYREF
  int v33; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = g_hProvider::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v30 = v4[26];
      v22 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v32) = v4[8];
      v25 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v33 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v18 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v19 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0x1000000;
      v20 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&word_14001C35E,
        v10 + 8,
        v8,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v19,
        &v27,
        (__int64)&v18,
        &v26,
        (__int64)&v33,
        &v25,
        (__int64)&v32,
        &v24,
        (__int64)&v31,
        &v23,
        &v22,
        (__int64)&v30,
        &v21,
        &v20);
    }
  }
  else
  {
    wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = g_hProvider::Provider(v11);
    v14 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v16 + 72);
      v32 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)word_14001C312,
        v16 + 8,
        v17,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1400118f0  push    rbp
0x1400118f2  push    rbx
0x1400118f3  push    rdi
0x1400118f4  lea     rbp, [rsp-47h]
0x1400118f9  sub     rsp, 100h
0x140011900  mov     rdi, [rcx+110h]
0x140011907  mov     rbx, rcx
0x14001190a  mov     eax, [rdi+48h]
0x14001190d  test    eax, eax
0x14001190f  jns     loc_140011A88
0x140011915  add     rdi, 50h ; 'P'
0x140011919  cmp     eax, [rdi+8]
0x14001191c  jnz     loc_140011A88
0x140011922  test    rdi, rdi
0x140011925  jz      loc_140011A88
0x14001192b  call    ?zInternalStop@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140011930  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x140011935  mov     r9, rax
0x140011938  mov     ecx, [rax]
0x14001193a  cmp     ecx, 5
0x14001193d  jbe     loc_140011B00
0x140011943  mov     rdx, 400000000000h
0x14001194d  mov     rcx, rax
0x140011950  call    _tlgKeywordOn
0x140011955  test    al, al
0x140011957  jz      loc_140011B00
0x14001195d  mov     rax, [rdi+70h]
0x140011961  lea     rdx, word_14001C35E
0x140011968  mov     rcx, [rdi+78h]
0x14001196c  mov     r8, [rbx+110h]
0x140011973  mov     [rbp+57h+var_60], rax
0x140011977  add     r8, 8
0x14001197b  mov     eax, [rdi+68h]
0x14001197e  mov     [rbp+57h+arg_0], eax
0x140011981  mov     rax, [rdi+60h]
0x140011985  mov     [rbp+57h+var_58], rax
0x140011989  mov     rax, [rdi+58h]
0x14001198d  mov     [rbp+57h+var_50], rax
0x140011991  mov     eax, [rdi+50h]
0x140011994  mov     [rbp+57h+arg_8], eax
0x140011997  mov     rax, [rdi+48h]
0x14001199b  mov     [rbp+57h+var_48], rax
0x14001199f  mov     eax, [rdi+20h]
0x1400119a2  mov     dword ptr [rbp+57h+arg_10], eax
0x1400119a5  mov     rax, [rdi+18h]
0x1400119a9  mov     [rbp+57h+var_40], rax
0x1400119ad  mov     eax, [rdi]
0x1400119af  mov     [rbp+57h+arg_18], eax
0x1400119b2  mov     rax, [rdi+80h]
0x1400119b9  mov     [rbp+57h+var_38], rax
0x1400119bd  mov     eax, [rdi+40h]
0x1400119c0  mov     [rbp+57h+var_70], eax
0x1400119c3  mov     rax, [rdi+38h]
0x1400119c7  mov     [rbp+57h+var_30], rax
0x1400119cb  mov     eax, [rdi+8]
0x1400119ce  mov     [rbp+57h+var_6C], eax
0x1400119d1  mov     eax, 1000000h
0x1400119d6  mov     [rbp+57h+var_28], rax
0x1400119da  mov     [rbp+57h+var_20], rax
0x1400119de  lea     rax, [rbp+57h+var_68]
0x1400119e2  mov     [rsp+110h+var_78], rax
0x1400119ea  lea     rax, [rbp+57h+var_60]
0x1400119ee  mov     [rsp+110h+var_80], rax
0x1400119f6  lea     rax, [rbp+57h+arg_0]
0x1400119fa  mov     [rsp+110h+var_88], rax
0x140011a02  lea     rax, [rbp+57h+var_58]
0x140011a06  mov     [rsp+110h+var_90], rax
0x140011a0e  lea     rax, [rbp+57h+var_50]
0x140011a12  mov     [rsp+110h+var_98], rax
0x140011a17  lea     rax, [rbp+57h+arg_8]
0x140011a1b  mov     [rsp+110h+var_A0], rax
0x140011a20  lea     rax, [rbp+57h+var_48]
0x140011a24  mov     [rsp+110h+var_A8], rax
0x140011a29  lea     rax, [rbp+57h+arg_10]
0x140011a2d  mov     [rsp+110h+var_B0], rax
0x140011a32  lea     rax, [rbp+57h+var_40]
0x140011a36  mov     [rsp+110h+var_B8], rax
0x140011a3b  lea     rax, [rbp+57h+arg_18]
0x140011a3f  mov     [rsp+110h+var_C0], rax
0x140011a44  lea     rax, [rbp+57h+var_38]
0x140011a48  mov     [rsp+110h+var_C8], rax
0x140011a4d  lea     rax, [rbp+57h+var_70]
0x140011a51  mov     [rsp+110h+var_D0], rax
0x140011a56  lea     rax, [rbp+57h+var_30]
0x140011a5a  mov     [rsp+110h+var_D8], rax
0x140011a5f  lea     rax, [rbp+57h+var_6C]
0x140011a63  mov     [rsp+110h+var_E0], rax
0x140011a68  lea     rax, [rbp+57h+var_28]
0x140011a6c  mov     [rsp+110h+var_E8], rax
0x140011a71  lea     rax, [rbp+57h+var_20]
0x140011a75  mov     [rbp+57h+var_68], rcx
0x140011a79  mov     rcx, r9
0x140011a7c  mov     [rsp+110h+var_F0], rax
0x140011a81  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140011a86  jmp     short loc_140011B00
0x140011a88  call    ?zInternalStop@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140011a8d  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x140011a92  mov     rdi, rax
0x140011a95  mov     ecx, [rax]
0x140011a97  cmp     ecx, 5
0x140011a9a  jbe     short loc_140011B00
0x140011a9c  mov     rdx, 400000000000h
0x140011aa6  mov     rcx, rax
0x140011aa9  call    _tlgKeywordOn
0x140011aae  test    al, al
0x140011ab0  jz      short loc_140011B00
0x140011ab2  call    cs:__imp_GetCurrentThreadId
0x140011ab8  mov     r8, [rbx+110h]
0x140011abf  lea     rdx, word_14001C312
0x140011ac6  mov     [rbp+57h+arg_0], eax
0x140011ac9  mov     rcx, rdi
0x140011acc  mov     eax, [r8+48h]
0x140011ad0  add     r8, 8
0x140011ad4  mov     [rbp+57h+arg_8], eax
0x140011ad7  mov     eax, 1000000h
0x140011adc  mov     [rbp+57h+arg_10], rax
0x140011ae0  lea     rax, [rbp+57h+arg_0]
0x140011ae4  mov     [rsp+110h+var_E0], rax
0x140011ae9  lea     rax, [rbp+57h+arg_8]
0x140011aed  mov     [rsp+110h+var_E8], rax
0x140011af2  lea     rax, [rbp+57h+arg_10]
0x140011af6  mov     [rsp+110h+var_F0], rax
0x140011afb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140011b00  mov     rcx, rbx
0x140011b03  add     rsp, 100h
0x140011b0a  pop     rdi
0x140011b0b  pop     rbx
0x140011b0c  pop     rbp
0x140011b0d  jmp     ?IgnoreCurrentThread@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
