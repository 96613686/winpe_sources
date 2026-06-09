# CflApiTraceProvider::CflDeserializeSessionContextActivity::StopActivity(void)

- ea: `0x18000df00`
- end: `0x18000e16e`
- name: `?StopActivity@CflDeserializeSessionContextActivity@CflApiTraceProvider@@MEAAXXZ`
- size: `622`
- prototype: `void __fastcall(CflApiTraceProvider::CflDeserializeSessionContextActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800012bc`
- `0x1800015d0`
- `0x18000a290`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000df00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000df5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e0f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000df5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e0f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e10f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e10f`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflDeserializeSessionContextActivity::StopActivity(
        CflApiTraceProvider::CflDeserializeSessionContextActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  _DWORD *v6; // rcx
  int v7; // r9d
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  _DWORD *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = (_DWORD *)*((_QWORD *)CflApiTraceProvider::Instance() + 1);
    if ( *v6 > 5u )
    {
      v18 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v20 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v6,
        (unsigned int)byte_180036451,
        v8 + 8,
        v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&SRWLock,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = (_DWORD *)*((_QWORD *)CflApiTraceProvider::Instance() + 1);
    if ( *v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)&dword_1800363EC,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000df00  push    rbp
0x18000df02  push    rbx
0x18000df03  push    rdi
0x18000df04  lea     rbp, [rsp+10h]
0x18000df09  sub     rsp, 130h
0x18000df10  mov     rdi, [rcx+110h]
0x18000df17  mov     rbx, rcx
0x18000df1a  mov     eax, [rdi+48h]
0x18000df1d  test    eax, eax
0x18000df1f  jns     loc_18000E0DA
0x18000df25  add     rdi, 50h ; 'P'
0x18000df29  cmp     eax, [rdi+8]
0x18000df2c  jnz     loc_18000E0DA
0x18000df32  test    rdi, rdi
0x18000df35  jz      loc_18000E0DA
0x18000df3b  lea     rdx, [rbp+SRWLock]
0x18000df3f  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000df44  mov     rax, [rbx+110h]
0x18000df4b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000df4f  mov     dword ptr [rax], 2
0x18000df55  test    rcx, rcx
0x18000df58  jz      short loc_18000DF60
0x18000df5a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000df60  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000df65  mov     rcx, [rax+8]
0x18000df69  mov     eax, [rcx]
0x18000df6b  cmp     eax, 5
0x18000df6e  jbe     loc_18000E15C
0x18000df74  mov     rax, [rdi+30h]
0x18000df78  lea     rdx, byte_180036451
0x18000df7f  mov     [rbp+var_70], rax
0x18000df83  mov     eax, [rdi+44h]
0x18000df86  mov     dword ptr [rbp+SRWLock], eax
0x18000df89  mov     eax, [rdi+10h]
0x18000df8c  mov     [rbp+arg_8], eax
0x18000df8f  mov     rax, [rdi+78h]
0x18000df93  mov     [rbp+var_68], rax
0x18000df97  mov     rax, [rdi+70h]
0x18000df9b  mov     [rbp+var_60], rax
0x18000df9f  mov     eax, [rdi+68h]
0x18000dfa2  mov     r8, [rbx+110h]
0x18000dfa9  mov     dword ptr [rbp+arg_10], eax
0x18000dfac  add     r8, 8
0x18000dfb0  mov     rax, [rdi+60h]
0x18000dfb4  mov     [rbp+var_58], rax
0x18000dfb8  mov     rax, [rdi+58h]
0x18000dfbc  mov     [rbp+var_50], rax
0x18000dfc0  mov     eax, [rdi+50h]
0x18000dfc3  mov     [rbp+arg_18], eax
0x18000dfc6  mov     rax, [rdi+48h]
0x18000dfca  mov     [rbp+var_48], rax
0x18000dfce  mov     eax, [rdi+20h]
0x18000dfd1  mov     [rbp+var_80], eax
0x18000dfd4  mov     rax, [rdi+18h]
0x18000dfd8  mov     [rbp+var_40], rax
0x18000dfdc  mov     eax, [rdi]
0x18000dfde  mov     [rbp+var_7C], eax
0x18000dfe1  mov     rax, [rdi+80h]
0x18000dfe8  mov     [rbp+var_38], rax
0x18000dfec  mov     eax, [rdi+40h]
0x18000dfef  mov     [rbp+var_78], eax
0x18000dff2  mov     rax, [rdi+38h]
0x18000dff6  mov     [rbp+var_30], rax
0x18000dffa  mov     eax, [rdi+8]
0x18000dffd  mov     [rbp+var_74], eax
0x18000e000  lea     rax, [rbp+var_70]
0x18000e004  mov     [rsp+140h+var_90], rax
0x18000e00c  lea     rax, [rbp+SRWLock]
0x18000e010  mov     [rsp+140h+var_98], rax
0x18000e018  lea     rax, [rbp+arg_8]
0x18000e01c  mov     [rsp+140h+var_A0], rax
0x18000e024  lea     rax, [rbp+var_68]
0x18000e028  mov     [rsp+140h+var_A8], rax
0x18000e030  lea     rax, [rbp+var_60]
0x18000e034  mov     [rsp+140h+var_B0], rax
0x18000e03c  lea     rax, [rbp+arg_10]
0x18000e040  mov     [rsp+140h+var_B8], rax
0x18000e048  lea     rax, [rbp+var_58]
0x18000e04c  mov     [rsp+140h+var_C0], rax
0x18000e054  lea     rax, [rbp+var_50]
0x18000e058  mov     [rsp+140h+var_C8], rax
0x18000e05d  lea     rax, [rbp+arg_18]
0x18000e061  mov     [rsp+140h+var_D0], rax
0x18000e066  lea     rax, [rbp+var_48]
0x18000e06a  mov     [rsp+140h+var_D8], rax
0x18000e06f  lea     rax, [rbp+var_80]
0x18000e073  mov     [rsp+140h+var_E0], rax
0x18000e078  lea     rax, [rbp+var_40]
0x18000e07c  mov     [rsp+140h+var_E8], rax
0x18000e081  lea     rax, [rbp+var_7C]
0x18000e085  mov     [rsp+140h+var_F0], rax
0x18000e08a  lea     rax, [rbp+var_38]
0x18000e08e  mov     [rsp+140h+var_F8], rax
0x18000e093  lea     rax, [rbp+var_78]
0x18000e097  mov     [rsp+140h+var_100], rax
0x18000e09c  lea     rax, [rbp+var_30]
0x18000e0a0  mov     [rsp+140h+var_108], rax
0x18000e0a5  lea     rax, [rbp+var_74]
0x18000e0a9  mov     [rsp+140h+var_110], rax
0x18000e0ae  lea     rax, [rbp+var_28]
0x18000e0b2  mov     [rsp+140h+var_118], rax
0x18000e0b7  lea     rax, [rbp+var_20]
0x18000e0bb  mov     [rsp+140h+var_120], rax
0x18000e0c0  mov     [rbp+var_28], 1000000h
0x18000e0c8  mov     [rbp+var_20], 0
0x18000e0d0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000e0d5  jmp     loc_18000E15C
0x18000e0da  lea     rdx, [rbp+SRWLock]
0x18000e0de  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e0e3  mov     rax, [rbx+110h]
0x18000e0ea  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000e0ee  mov     dword ptr [rax], 2
0x18000e0f4  test    rcx, rcx
0x18000e0f7  jz      short loc_18000E0FF
0x18000e0f9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e0ff  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000e104  mov     rdi, [rax+8]
0x18000e108  mov     eax, [rdi]
0x18000e10a  cmp     eax, 5
0x18000e10d  jbe     short loc_18000E15C
0x18000e10f  call    cs:__imp_GetCurrentThreadId
0x18000e115  mov     r8, [rbx+110h]
0x18000e11c  lea     rdx, dword_1800363EC
0x18000e123  mov     dword ptr [rbp+SRWLock], eax
0x18000e126  mov     rcx, rdi
0x18000e129  mov     eax, [r8+48h]
0x18000e12d  add     r8, 8
0x18000e131  mov     [rbp+arg_8], eax
0x18000e134  lea     rax, [rbp+SRWLock]
0x18000e138  mov     [rsp+140h+var_110], rax
0x18000e13d  lea     rax, [rbp+arg_8]
0x18000e141  mov     [rsp+140h+var_118], rax
0x18000e146  lea     rax, [rbp+arg_10]
0x18000e14a  mov     [rsp+140h+var_120], rax
0x18000e14f  mov     [rbp+arg_10], 0
0x18000e157  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000e15c  mov     rcx, rbx
0x18000e15f  add     rsp, 130h
0x18000e166  pop     rdi
0x18000e167  pop     rbx
0x18000e168  pop     rbp
0x18000e169  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
