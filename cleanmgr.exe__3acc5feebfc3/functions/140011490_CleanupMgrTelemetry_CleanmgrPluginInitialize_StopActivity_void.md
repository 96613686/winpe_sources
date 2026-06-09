# CleanupMgrTelemetry::CleanmgrPluginInitialize::StopActivity(void)

- ea: `0x140011490`
- end: `0x1400116b2`
- name: `?StopActivity@CleanmgrPluginInitialize@CleanupMgrTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(CleanupMgrTelemetry::CleanmgrPluginInitialize *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400012b8`
- `0x1400019bc`
- `0x1400022a0`
- `0x14000e15c`
- `0x14000fc6c`
- `0x140011490`
- `0x140016020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011652`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011652`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::CleanmgrPluginInitialize::StopActivity(
        CleanupMgrTelemetry::CleanmgrPluginInitialize *this)
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
        (__int64)byte_14001C939,
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
        (__int64)&unk_14001C8E0,
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
0x140011490  push    rbp
0x140011492  push    rbx
0x140011493  push    rdi
0x140011494  lea     rbp, [rsp-47h]
0x140011499  sub     rsp, 100h
0x1400114a0  mov     rdi, [rcx+110h]
0x1400114a7  mov     rbx, rcx
0x1400114aa  mov     eax, [rdi+48h]
0x1400114ad  test    eax, eax
0x1400114af  jns     loc_140011628
0x1400114b5  add     rdi, 50h ; 'P'
0x1400114b9  cmp     eax, [rdi+8]
0x1400114bc  jnz     loc_140011628
0x1400114c2  test    rdi, rdi
0x1400114c5  jz      loc_140011628
0x1400114cb  call    ?zInternalStop@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400114d0  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x1400114d5  mov     r9, rax
0x1400114d8  mov     ecx, [rax]
0x1400114da  cmp     ecx, 5
0x1400114dd  jbe     loc_1400116A0
0x1400114e3  mov     rdx, 400000000000h
0x1400114ed  mov     rcx, rax
0x1400114f0  call    _tlgKeywordOn
0x1400114f5  test    al, al
0x1400114f7  jz      loc_1400116A0
0x1400114fd  mov     rax, [rdi+70h]
0x140011501  lea     rdx, byte_14001C939
0x140011508  mov     rcx, [rdi+78h]
0x14001150c  mov     r8, [rbx+110h]
0x140011513  mov     [rbp+57h+var_60], rax
0x140011517  add     r8, 8
0x14001151b  mov     eax, [rdi+68h]
0x14001151e  mov     [rbp+57h+arg_0], eax
0x140011521  mov     rax, [rdi+60h]
0x140011525  mov     [rbp+57h+var_58], rax
0x140011529  mov     rax, [rdi+58h]
0x14001152d  mov     [rbp+57h+var_50], rax
0x140011531  mov     eax, [rdi+50h]
0x140011534  mov     [rbp+57h+arg_8], eax
0x140011537  mov     rax, [rdi+48h]
0x14001153b  mov     [rbp+57h+var_48], rax
0x14001153f  mov     eax, [rdi+20h]
0x140011542  mov     dword ptr [rbp+57h+arg_10], eax
0x140011545  mov     rax, [rdi+18h]
0x140011549  mov     [rbp+57h+var_40], rax
0x14001154d  mov     eax, [rdi]
0x14001154f  mov     [rbp+57h+arg_18], eax
0x140011552  mov     rax, [rdi+80h]
0x140011559  mov     [rbp+57h+var_38], rax
0x14001155d  mov     eax, [rdi+40h]
0x140011560  mov     [rbp+57h+var_70], eax
0x140011563  mov     rax, [rdi+38h]
0x140011567  mov     [rbp+57h+var_30], rax
0x14001156b  mov     eax, [rdi+8]
0x14001156e  mov     [rbp+57h+var_6C], eax
0x140011571  mov     eax, 1000000h
0x140011576  mov     [rbp+57h+var_28], rax
0x14001157a  mov     [rbp+57h+var_20], rax
0x14001157e  lea     rax, [rbp+57h+var_68]
0x140011582  mov     [rsp+110h+var_78], rax
0x14001158a  lea     rax, [rbp+57h+var_60]
0x14001158e  mov     [rsp+110h+var_80], rax
0x140011596  lea     rax, [rbp+57h+arg_0]
0x14001159a  mov     [rsp+110h+var_88], rax
0x1400115a2  lea     rax, [rbp+57h+var_58]
0x1400115a6  mov     [rsp+110h+var_90], rax
0x1400115ae  lea     rax, [rbp+57h+var_50]
0x1400115b2  mov     [rsp+110h+var_98], rax
0x1400115b7  lea     rax, [rbp+57h+arg_8]
0x1400115bb  mov     [rsp+110h+var_A0], rax
0x1400115c0  lea     rax, [rbp+57h+var_48]
0x1400115c4  mov     [rsp+110h+var_A8], rax
0x1400115c9  lea     rax, [rbp+57h+arg_10]
0x1400115cd  mov     [rsp+110h+var_B0], rax
0x1400115d2  lea     rax, [rbp+57h+var_40]
0x1400115d6  mov     [rsp+110h+var_B8], rax
0x1400115db  lea     rax, [rbp+57h+arg_18]
0x1400115df  mov     [rsp+110h+var_C0], rax
0x1400115e4  lea     rax, [rbp+57h+var_38]
0x1400115e8  mov     [rsp+110h+var_C8], rax
0x1400115ed  lea     rax, [rbp+57h+var_70]
0x1400115f1  mov     [rsp+110h+var_D0], rax
0x1400115f6  lea     rax, [rbp+57h+var_30]
0x1400115fa  mov     [rsp+110h+var_D8], rax
0x1400115ff  lea     rax, [rbp+57h+var_6C]
0x140011603  mov     [rsp+110h+var_E0], rax
0x140011608  lea     rax, [rbp+57h+var_28]
0x14001160c  mov     [rsp+110h+var_E8], rax
0x140011611  lea     rax, [rbp+57h+var_20]
0x140011615  mov     [rbp+57h+var_68], rcx
0x140011619  mov     rcx, r9
0x14001161c  mov     [rsp+110h+var_F0], rax
0x140011621  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140011626  jmp     short loc_1400116A0
0x140011628  call    ?zInternalStop@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14001162d  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x140011632  mov     rdi, rax
0x140011635  mov     ecx, [rax]
0x140011637  cmp     ecx, 5
0x14001163a  jbe     short loc_1400116A0
0x14001163c  mov     rdx, 400000000000h
0x140011646  mov     rcx, rax
0x140011649  call    _tlgKeywordOn
0x14001164e  test    al, al
0x140011650  jz      short loc_1400116A0
0x140011652  call    cs:__imp_GetCurrentThreadId
0x140011658  mov     r8, [rbx+110h]
0x14001165f  lea     rdx, unk_14001C8E0
0x140011666  mov     [rbp+57h+arg_0], eax
0x140011669  mov     rcx, rdi
0x14001166c  mov     eax, [r8+48h]
0x140011670  add     r8, 8
0x140011674  mov     [rbp+57h+arg_8], eax
0x140011677  mov     eax, 1000000h
0x14001167c  mov     [rbp+57h+arg_10], rax
0x140011680  lea     rax, [rbp+57h+arg_0]
0x140011684  mov     [rsp+110h+var_E0], rax
0x140011689  lea     rax, [rbp+57h+arg_8]
0x14001168d  mov     [rsp+110h+var_E8], rax
0x140011692  lea     rax, [rbp+57h+arg_10]
0x140011696  mov     [rsp+110h+var_F0], rax
0x14001169b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400116a0  mov     rcx, rbx
0x1400116a3  add     rsp, 100h
0x1400116aa  pop     rdi
0x1400116ab  pop     rbx
0x1400116ac  pop     rbp
0x1400116ad  jmp     ?IgnoreCurrentThread@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
