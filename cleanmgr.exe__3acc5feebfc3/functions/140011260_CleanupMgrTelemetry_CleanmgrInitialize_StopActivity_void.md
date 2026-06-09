# CleanupMgrTelemetry::CleanmgrInitialize::StopActivity(void)

- ea: `0x140011260`
- end: `0x140011482`
- name: `?StopActivity@CleanmgrInitialize@CleanupMgrTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(CleanupMgrTelemetry::CleanmgrInitialize *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400012b8`
- `0x1400019bc`
- `0x1400022a0`
- `0x14000e15c`
- `0x14000fc6c`
- `0x140011260`
- `0x140016020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011422`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011422`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::CleanmgrInitialize::StopActivity(CleanupMgrTelemetry::CleanmgrInitialize *this)
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
        (__int64)&byte_14001CC47,
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
        (__int64)&dword_14001CBF4,
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
0x140011260  push    rbp
0x140011262  push    rbx
0x140011263  push    rdi
0x140011264  lea     rbp, [rsp-47h]
0x140011269  sub     rsp, 100h
0x140011270  mov     rdi, [rcx+110h]
0x140011277  mov     rbx, rcx
0x14001127a  mov     eax, [rdi+48h]
0x14001127d  test    eax, eax
0x14001127f  jns     loc_1400113F8
0x140011285  add     rdi, 50h ; 'P'
0x140011289  cmp     eax, [rdi+8]
0x14001128c  jnz     loc_1400113F8
0x140011292  test    rdi, rdi
0x140011295  jz      loc_1400113F8
0x14001129b  call    ?zInternalStop@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400112a0  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x1400112a5  mov     r9, rax
0x1400112a8  mov     ecx, [rax]
0x1400112aa  cmp     ecx, 5
0x1400112ad  jbe     loc_140011470
0x1400112b3  mov     rdx, 400000000000h
0x1400112bd  mov     rcx, rax
0x1400112c0  call    _tlgKeywordOn
0x1400112c5  test    al, al
0x1400112c7  jz      loc_140011470
0x1400112cd  mov     rax, [rdi+70h]
0x1400112d1  lea     rdx, byte_14001CC47
0x1400112d8  mov     rcx, [rdi+78h]
0x1400112dc  mov     r8, [rbx+110h]
0x1400112e3  mov     [rbp+57h+var_60], rax
0x1400112e7  add     r8, 8
0x1400112eb  mov     eax, [rdi+68h]
0x1400112ee  mov     [rbp+57h+arg_0], eax
0x1400112f1  mov     rax, [rdi+60h]
0x1400112f5  mov     [rbp+57h+var_58], rax
0x1400112f9  mov     rax, [rdi+58h]
0x1400112fd  mov     [rbp+57h+var_50], rax
0x140011301  mov     eax, [rdi+50h]
0x140011304  mov     [rbp+57h+arg_8], eax
0x140011307  mov     rax, [rdi+48h]
0x14001130b  mov     [rbp+57h+var_48], rax
0x14001130f  mov     eax, [rdi+20h]
0x140011312  mov     dword ptr [rbp+57h+arg_10], eax
0x140011315  mov     rax, [rdi+18h]
0x140011319  mov     [rbp+57h+var_40], rax
0x14001131d  mov     eax, [rdi]
0x14001131f  mov     [rbp+57h+arg_18], eax
0x140011322  mov     rax, [rdi+80h]
0x140011329  mov     [rbp+57h+var_38], rax
0x14001132d  mov     eax, [rdi+40h]
0x140011330  mov     [rbp+57h+var_70], eax
0x140011333  mov     rax, [rdi+38h]
0x140011337  mov     [rbp+57h+var_30], rax
0x14001133b  mov     eax, [rdi+8]
0x14001133e  mov     [rbp+57h+var_6C], eax
0x140011341  mov     eax, 1000000h
0x140011346  mov     [rbp+57h+var_28], rax
0x14001134a  mov     [rbp+57h+var_20], rax
0x14001134e  lea     rax, [rbp+57h+var_68]
0x140011352  mov     [rsp+110h+var_78], rax
0x14001135a  lea     rax, [rbp+57h+var_60]
0x14001135e  mov     [rsp+110h+var_80], rax
0x140011366  lea     rax, [rbp+57h+arg_0]
0x14001136a  mov     [rsp+110h+var_88], rax
0x140011372  lea     rax, [rbp+57h+var_58]
0x140011376  mov     [rsp+110h+var_90], rax
0x14001137e  lea     rax, [rbp+57h+var_50]
0x140011382  mov     [rsp+110h+var_98], rax
0x140011387  lea     rax, [rbp+57h+arg_8]
0x14001138b  mov     [rsp+110h+var_A0], rax
0x140011390  lea     rax, [rbp+57h+var_48]
0x140011394  mov     [rsp+110h+var_A8], rax
0x140011399  lea     rax, [rbp+57h+arg_10]
0x14001139d  mov     [rsp+110h+var_B0], rax
0x1400113a2  lea     rax, [rbp+57h+var_40]
0x1400113a6  mov     [rsp+110h+var_B8], rax
0x1400113ab  lea     rax, [rbp+57h+arg_18]
0x1400113af  mov     [rsp+110h+var_C0], rax
0x1400113b4  lea     rax, [rbp+57h+var_38]
0x1400113b8  mov     [rsp+110h+var_C8], rax
0x1400113bd  lea     rax, [rbp+57h+var_70]
0x1400113c1  mov     [rsp+110h+var_D0], rax
0x1400113c6  lea     rax, [rbp+57h+var_30]
0x1400113ca  mov     [rsp+110h+var_D8], rax
0x1400113cf  lea     rax, [rbp+57h+var_6C]
0x1400113d3  mov     [rsp+110h+var_E0], rax
0x1400113d8  lea     rax, [rbp+57h+var_28]
0x1400113dc  mov     [rsp+110h+var_E8], rax
0x1400113e1  lea     rax, [rbp+57h+var_20]
0x1400113e5  mov     [rbp+57h+var_68], rcx
0x1400113e9  mov     rcx, r9
0x1400113ec  mov     [rsp+110h+var_F0], rax
0x1400113f1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1400113f6  jmp     short loc_140011470
0x1400113f8  call    ?zInternalStop@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400113fd  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x140011402  mov     rdi, rax
0x140011405  mov     ecx, [rax]
0x140011407  cmp     ecx, 5
0x14001140a  jbe     short loc_140011470
0x14001140c  mov     rdx, 400000000000h
0x140011416  mov     rcx, rax
0x140011419  call    _tlgKeywordOn
0x14001141e  test    al, al
0x140011420  jz      short loc_140011470
0x140011422  call    cs:__imp_GetCurrentThreadId
0x140011428  mov     r8, [rbx+110h]
0x14001142f  lea     rdx, dword_14001CBF4
0x140011436  mov     [rbp+57h+arg_0], eax
0x140011439  mov     rcx, rdi
0x14001143c  mov     eax, [r8+48h]
0x140011440  add     r8, 8
0x140011444  mov     [rbp+57h+arg_8], eax
0x140011447  mov     eax, 1000000h
0x14001144c  mov     [rbp+57h+arg_10], rax
0x140011450  lea     rax, [rbp+57h+arg_0]
0x140011454  mov     [rsp+110h+var_E0], rax
0x140011459  lea     rax, [rbp+57h+arg_8]
0x14001145d  mov     [rsp+110h+var_E8], rax
0x140011462  lea     rax, [rbp+57h+arg_10]
0x140011466  mov     [rsp+110h+var_F0], rax
0x14001146b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140011470  mov     rcx, rbx
0x140011473  add     rsp, 100h
0x14001147a  pop     rdi
0x14001147b  pop     rbx
0x14001147c  pop     rbp
0x14001147d  jmp     ?IgnoreCurrentThread@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
