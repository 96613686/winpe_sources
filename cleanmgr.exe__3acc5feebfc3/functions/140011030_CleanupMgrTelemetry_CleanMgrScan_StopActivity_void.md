# CleanupMgrTelemetry::CleanMgrScan::StopActivity(void)

- ea: `0x140011030`
- end: `0x140011252`
- name: `?StopActivity@CleanMgrScan@CleanupMgrTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(CleanupMgrTelemetry::CleanMgrScan *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400012b8`
- `0x1400019bc`
- `0x1400022a0`
- `0x14000e15c`
- `0x14000fc6c`
- `0x140011030`
- `0x140016020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400111f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400111f2`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::CleanMgrScan::StopActivity(CleanupMgrTelemetry::CleanMgrScan *this)
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
        (__int64)&dword_14001C7BC,
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
        (__int64)&byte_14001C76F,
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
0x140011030  push    rbp
0x140011032  push    rbx
0x140011033  push    rdi
0x140011034  lea     rbp, [rsp-47h]
0x140011039  sub     rsp, 100h
0x140011040  mov     rdi, [rcx+110h]
0x140011047  mov     rbx, rcx
0x14001104a  mov     eax, [rdi+48h]
0x14001104d  test    eax, eax
0x14001104f  jns     loc_1400111C8
0x140011055  add     rdi, 50h ; 'P'
0x140011059  cmp     eax, [rdi+8]
0x14001105c  jnz     loc_1400111C8
0x140011062  test    rdi, rdi
0x140011065  jz      loc_1400111C8
0x14001106b  call    ?zInternalStop@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140011070  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x140011075  mov     r9, rax
0x140011078  mov     ecx, [rax]
0x14001107a  cmp     ecx, 5
0x14001107d  jbe     loc_140011240
0x140011083  mov     rdx, 400000000000h
0x14001108d  mov     rcx, rax
0x140011090  call    _tlgKeywordOn
0x140011095  test    al, al
0x140011097  jz      loc_140011240
0x14001109d  mov     rax, [rdi+70h]
0x1400110a1  lea     rdx, dword_14001C7BC
0x1400110a8  mov     rcx, [rdi+78h]
0x1400110ac  mov     r8, [rbx+110h]
0x1400110b3  mov     [rbp+57h+var_60], rax
0x1400110b7  add     r8, 8
0x1400110bb  mov     eax, [rdi+68h]
0x1400110be  mov     [rbp+57h+arg_0], eax
0x1400110c1  mov     rax, [rdi+60h]
0x1400110c5  mov     [rbp+57h+var_58], rax
0x1400110c9  mov     rax, [rdi+58h]
0x1400110cd  mov     [rbp+57h+var_50], rax
0x1400110d1  mov     eax, [rdi+50h]
0x1400110d4  mov     [rbp+57h+arg_8], eax
0x1400110d7  mov     rax, [rdi+48h]
0x1400110db  mov     [rbp+57h+var_48], rax
0x1400110df  mov     eax, [rdi+20h]
0x1400110e2  mov     dword ptr [rbp+57h+arg_10], eax
0x1400110e5  mov     rax, [rdi+18h]
0x1400110e9  mov     [rbp+57h+var_40], rax
0x1400110ed  mov     eax, [rdi]
0x1400110ef  mov     [rbp+57h+arg_18], eax
0x1400110f2  mov     rax, [rdi+80h]
0x1400110f9  mov     [rbp+57h+var_38], rax
0x1400110fd  mov     eax, [rdi+40h]
0x140011100  mov     [rbp+57h+var_70], eax
0x140011103  mov     rax, [rdi+38h]
0x140011107  mov     [rbp+57h+var_30], rax
0x14001110b  mov     eax, [rdi+8]
0x14001110e  mov     [rbp+57h+var_6C], eax
0x140011111  mov     eax, 1000000h
0x140011116  mov     [rbp+57h+var_28], rax
0x14001111a  mov     [rbp+57h+var_20], rax
0x14001111e  lea     rax, [rbp+57h+var_68]
0x140011122  mov     [rsp+110h+var_78], rax
0x14001112a  lea     rax, [rbp+57h+var_60]
0x14001112e  mov     [rsp+110h+var_80], rax
0x140011136  lea     rax, [rbp+57h+arg_0]
0x14001113a  mov     [rsp+110h+var_88], rax
0x140011142  lea     rax, [rbp+57h+var_58]
0x140011146  mov     [rsp+110h+var_90], rax
0x14001114e  lea     rax, [rbp+57h+var_50]
0x140011152  mov     [rsp+110h+var_98], rax
0x140011157  lea     rax, [rbp+57h+arg_8]
0x14001115b  mov     [rsp+110h+var_A0], rax
0x140011160  lea     rax, [rbp+57h+var_48]
0x140011164  mov     [rsp+110h+var_A8], rax
0x140011169  lea     rax, [rbp+57h+arg_10]
0x14001116d  mov     [rsp+110h+var_B0], rax
0x140011172  lea     rax, [rbp+57h+var_40]
0x140011176  mov     [rsp+110h+var_B8], rax
0x14001117b  lea     rax, [rbp+57h+arg_18]
0x14001117f  mov     [rsp+110h+var_C0], rax
0x140011184  lea     rax, [rbp+57h+var_38]
0x140011188  mov     [rsp+110h+var_C8], rax
0x14001118d  lea     rax, [rbp+57h+var_70]
0x140011191  mov     [rsp+110h+var_D0], rax
0x140011196  lea     rax, [rbp+57h+var_30]
0x14001119a  mov     [rsp+110h+var_D8], rax
0x14001119f  lea     rax, [rbp+57h+var_6C]
0x1400111a3  mov     [rsp+110h+var_E0], rax
0x1400111a8  lea     rax, [rbp+57h+var_28]
0x1400111ac  mov     [rsp+110h+var_E8], rax
0x1400111b1  lea     rax, [rbp+57h+var_20]
0x1400111b5  mov     [rbp+57h+var_68], rcx
0x1400111b9  mov     rcx, r9
0x1400111bc  mov     [rsp+110h+var_F0], rax
0x1400111c1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1400111c6  jmp     short loc_140011240
0x1400111c8  call    ?zInternalStop@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400111cd  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x1400111d2  mov     rdi, rax
0x1400111d5  mov     ecx, [rax]
0x1400111d7  cmp     ecx, 5
0x1400111da  jbe     short loc_140011240
0x1400111dc  mov     rdx, 400000000000h
0x1400111e6  mov     rcx, rax
0x1400111e9  call    _tlgKeywordOn
0x1400111ee  test    al, al
0x1400111f0  jz      short loc_140011240
0x1400111f2  call    cs:__imp_GetCurrentThreadId
0x1400111f8  mov     r8, [rbx+110h]
0x1400111ff  lea     rdx, byte_14001C76F
0x140011206  mov     [rbp+57h+arg_0], eax
0x140011209  mov     rcx, rdi
0x14001120c  mov     eax, [r8+48h]
0x140011210  add     r8, 8
0x140011214  mov     [rbp+57h+arg_8], eax
0x140011217  mov     eax, 1000000h
0x14001121c  mov     [rbp+57h+arg_10], rax
0x140011220  lea     rax, [rbp+57h+arg_0]
0x140011224  mov     [rsp+110h+var_E0], rax
0x140011229  lea     rax, [rbp+57h+arg_8]
0x14001122d  mov     [rsp+110h+var_E8], rax
0x140011232  lea     rax, [rbp+57h+arg_10]
0x140011236  mov     [rsp+110h+var_F0], rax
0x14001123b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140011240  mov     rcx, rbx
0x140011243  add     rsp, 100h
0x14001124a  pop     rdi
0x14001124b  pop     rbx
0x14001124c  pop     rbp
0x14001124d  jmp     ?IgnoreCurrentThread@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
