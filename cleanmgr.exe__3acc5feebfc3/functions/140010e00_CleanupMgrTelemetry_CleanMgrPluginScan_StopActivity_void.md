# CleanupMgrTelemetry::CleanMgrPluginScan::StopActivity(void)

- ea: `0x140010e00`
- end: `0x140011022`
- name: `?StopActivity@CleanMgrPluginScan@CleanupMgrTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(CleanupMgrTelemetry::CleanMgrPluginScan *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400012b8`
- `0x1400019bc`
- `0x1400022a0`
- `0x14000e15c`
- `0x14000fc6c`
- `0x140010e00`
- `0x140016020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140010fc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140010fc2`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::CleanMgrPluginScan::StopActivity(CleanupMgrTelemetry::CleanMgrPluginScan *this)
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
        (__int64)byte_14001C645,
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
        (__int64)word_14001C5F2,
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
0x140010e00  push    rbp
0x140010e02  push    rbx
0x140010e03  push    rdi
0x140010e04  lea     rbp, [rsp-47h]
0x140010e09  sub     rsp, 100h
0x140010e10  mov     rdi, [rcx+110h]
0x140010e17  mov     rbx, rcx
0x140010e1a  mov     eax, [rdi+48h]
0x140010e1d  test    eax, eax
0x140010e1f  jns     loc_140010F98
0x140010e25  add     rdi, 50h ; 'P'
0x140010e29  cmp     eax, [rdi+8]
0x140010e2c  jnz     loc_140010F98
0x140010e32  test    rdi, rdi
0x140010e35  jz      loc_140010F98
0x140010e3b  call    ?zInternalStop@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140010e40  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x140010e45  mov     r9, rax
0x140010e48  mov     ecx, [rax]
0x140010e4a  cmp     ecx, 5
0x140010e4d  jbe     loc_140011010
0x140010e53  mov     rdx, 400000000000h
0x140010e5d  mov     rcx, rax
0x140010e60  call    _tlgKeywordOn
0x140010e65  test    al, al
0x140010e67  jz      loc_140011010
0x140010e6d  mov     rax, [rdi+70h]
0x140010e71  lea     rdx, byte_14001C645
0x140010e78  mov     rcx, [rdi+78h]
0x140010e7c  mov     r8, [rbx+110h]
0x140010e83  mov     [rbp+57h+var_60], rax
0x140010e87  add     r8, 8
0x140010e8b  mov     eax, [rdi+68h]
0x140010e8e  mov     [rbp+57h+arg_0], eax
0x140010e91  mov     rax, [rdi+60h]
0x140010e95  mov     [rbp+57h+var_58], rax
0x140010e99  mov     rax, [rdi+58h]
0x140010e9d  mov     [rbp+57h+var_50], rax
0x140010ea1  mov     eax, [rdi+50h]
0x140010ea4  mov     [rbp+57h+arg_8], eax
0x140010ea7  mov     rax, [rdi+48h]
0x140010eab  mov     [rbp+57h+var_48], rax
0x140010eaf  mov     eax, [rdi+20h]
0x140010eb2  mov     dword ptr [rbp+57h+arg_10], eax
0x140010eb5  mov     rax, [rdi+18h]
0x140010eb9  mov     [rbp+57h+var_40], rax
0x140010ebd  mov     eax, [rdi]
0x140010ebf  mov     [rbp+57h+arg_18], eax
0x140010ec2  mov     rax, [rdi+80h]
0x140010ec9  mov     [rbp+57h+var_38], rax
0x140010ecd  mov     eax, [rdi+40h]
0x140010ed0  mov     [rbp+57h+var_70], eax
0x140010ed3  mov     rax, [rdi+38h]
0x140010ed7  mov     [rbp+57h+var_30], rax
0x140010edb  mov     eax, [rdi+8]
0x140010ede  mov     [rbp+57h+var_6C], eax
0x140010ee1  mov     eax, 1000000h
0x140010ee6  mov     [rbp+57h+var_28], rax
0x140010eea  mov     [rbp+57h+var_20], rax
0x140010eee  lea     rax, [rbp+57h+var_68]
0x140010ef2  mov     [rsp+110h+var_78], rax
0x140010efa  lea     rax, [rbp+57h+var_60]
0x140010efe  mov     [rsp+110h+var_80], rax
0x140010f06  lea     rax, [rbp+57h+arg_0]
0x140010f0a  mov     [rsp+110h+var_88], rax
0x140010f12  lea     rax, [rbp+57h+var_58]
0x140010f16  mov     [rsp+110h+var_90], rax
0x140010f1e  lea     rax, [rbp+57h+var_50]
0x140010f22  mov     [rsp+110h+var_98], rax
0x140010f27  lea     rax, [rbp+57h+arg_8]
0x140010f2b  mov     [rsp+110h+var_A0], rax
0x140010f30  lea     rax, [rbp+57h+var_48]
0x140010f34  mov     [rsp+110h+var_A8], rax
0x140010f39  lea     rax, [rbp+57h+arg_10]
0x140010f3d  mov     [rsp+110h+var_B0], rax
0x140010f42  lea     rax, [rbp+57h+var_40]
0x140010f46  mov     [rsp+110h+var_B8], rax
0x140010f4b  lea     rax, [rbp+57h+arg_18]
0x140010f4f  mov     [rsp+110h+var_C0], rax
0x140010f54  lea     rax, [rbp+57h+var_38]
0x140010f58  mov     [rsp+110h+var_C8], rax
0x140010f5d  lea     rax, [rbp+57h+var_70]
0x140010f61  mov     [rsp+110h+var_D0], rax
0x140010f66  lea     rax, [rbp+57h+var_30]
0x140010f6a  mov     [rsp+110h+var_D8], rax
0x140010f6f  lea     rax, [rbp+57h+var_6C]
0x140010f73  mov     [rsp+110h+var_E0], rax
0x140010f78  lea     rax, [rbp+57h+var_28]
0x140010f7c  mov     [rsp+110h+var_E8], rax
0x140010f81  lea     rax, [rbp+57h+var_20]
0x140010f85  mov     [rbp+57h+var_68], rcx
0x140010f89  mov     rcx, r9
0x140010f8c  mov     [rsp+110h+var_F0], rax
0x140010f91  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140010f96  jmp     short loc_140011010
0x140010f98  call    ?zInternalStop@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140010f9d  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x140010fa2  mov     rdi, rax
0x140010fa5  mov     ecx, [rax]
0x140010fa7  cmp     ecx, 5
0x140010faa  jbe     short loc_140011010
0x140010fac  mov     rdx, 400000000000h
0x140010fb6  mov     rcx, rax
0x140010fb9  call    _tlgKeywordOn
0x140010fbe  test    al, al
0x140010fc0  jz      short loc_140011010
0x140010fc2  call    cs:__imp_GetCurrentThreadId
0x140010fc8  mov     r8, [rbx+110h]
0x140010fcf  lea     rdx, word_14001C5F2
0x140010fd6  mov     [rbp+57h+arg_0], eax
0x140010fd9  mov     rcx, rdi
0x140010fdc  mov     eax, [r8+48h]
0x140010fe0  add     r8, 8
0x140010fe4  mov     [rbp+57h+arg_8], eax
0x140010fe7  mov     eax, 1000000h
0x140010fec  mov     [rbp+57h+arg_10], rax
0x140010ff0  lea     rax, [rbp+57h+arg_0]
0x140010ff4  mov     [rsp+110h+var_E0], rax
0x140010ff9  lea     rax, [rbp+57h+arg_8]
0x140010ffd  mov     [rsp+110h+var_E8], rax
0x140011002  lea     rax, [rbp+57h+arg_10]
0x140011006  mov     [rsp+110h+var_F0], rax
0x14001100b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140011010  mov     rcx, rbx
0x140011013  add     rsp, 100h
0x14001101a  pop     rdi
0x14001101b  pop     rbx
0x14001101c  pop     rbp
0x14001101d  jmp     ?IgnoreCurrentThread@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
