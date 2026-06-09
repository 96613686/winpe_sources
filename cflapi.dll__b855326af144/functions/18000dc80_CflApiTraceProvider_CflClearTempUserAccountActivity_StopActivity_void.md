# CflApiTraceProvider::CflClearTempUserAccountActivity::StopActivity(void)

- ea: `0x18000dc80`
- end: `0x18000deee`
- name: `?StopActivity@CflClearTempUserAccountActivity@CflApiTraceProvider@@MEAAXXZ`
- size: `622`
- prototype: `void __fastcall(CflApiTraceProvider::CflClearTempUserAccountActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800012bc`
- `0x1800015d0`
- `0x18000a290`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000dc80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dcda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000de79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dcda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000de79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000de8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000de8f`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflClearTempUserAccountActivity::StopActivity(
        CflApiTraceProvider::CflClearTempUserAccountActivity *this)
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
        (unsigned int)byte_180037573,
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
        (unsigned int)byte_180037513,
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
0x18000dc80  push    rbp
0x18000dc82  push    rbx
0x18000dc83  push    rdi
0x18000dc84  lea     rbp, [rsp+10h]
0x18000dc89  sub     rsp, 130h
0x18000dc90  mov     rdi, [rcx+110h]
0x18000dc97  mov     rbx, rcx
0x18000dc9a  mov     eax, [rdi+48h]
0x18000dc9d  test    eax, eax
0x18000dc9f  jns     loc_18000DE5A
0x18000dca5  add     rdi, 50h ; 'P'
0x18000dca9  cmp     eax, [rdi+8]
0x18000dcac  jnz     loc_18000DE5A
0x18000dcb2  test    rdi, rdi
0x18000dcb5  jz      loc_18000DE5A
0x18000dcbb  lea     rdx, [rbp+SRWLock]
0x18000dcbf  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000dcc4  mov     rax, [rbx+110h]
0x18000dccb  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000dccf  mov     dword ptr [rax], 2
0x18000dcd5  test    rcx, rcx
0x18000dcd8  jz      short loc_18000DCE0
0x18000dcda  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dce0  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000dce5  mov     rcx, [rax+8]
0x18000dce9  mov     eax, [rcx]
0x18000dceb  cmp     eax, 5
0x18000dcee  jbe     loc_18000DEDC
0x18000dcf4  mov     rax, [rdi+30h]
0x18000dcf8  lea     rdx, byte_180037573
0x18000dcff  mov     [rbp+var_70], rax
0x18000dd03  mov     eax, [rdi+44h]
0x18000dd06  mov     dword ptr [rbp+SRWLock], eax
0x18000dd09  mov     eax, [rdi+10h]
0x18000dd0c  mov     [rbp+arg_8], eax
0x18000dd0f  mov     rax, [rdi+78h]
0x18000dd13  mov     [rbp+var_68], rax
0x18000dd17  mov     rax, [rdi+70h]
0x18000dd1b  mov     [rbp+var_60], rax
0x18000dd1f  mov     eax, [rdi+68h]
0x18000dd22  mov     r8, [rbx+110h]
0x18000dd29  mov     dword ptr [rbp+arg_10], eax
0x18000dd2c  add     r8, 8
0x18000dd30  mov     rax, [rdi+60h]
0x18000dd34  mov     [rbp+var_58], rax
0x18000dd38  mov     rax, [rdi+58h]
0x18000dd3c  mov     [rbp+var_50], rax
0x18000dd40  mov     eax, [rdi+50h]
0x18000dd43  mov     [rbp+arg_18], eax
0x18000dd46  mov     rax, [rdi+48h]
0x18000dd4a  mov     [rbp+var_48], rax
0x18000dd4e  mov     eax, [rdi+20h]
0x18000dd51  mov     [rbp+var_80], eax
0x18000dd54  mov     rax, [rdi+18h]
0x18000dd58  mov     [rbp+var_40], rax
0x18000dd5c  mov     eax, [rdi]
0x18000dd5e  mov     [rbp+var_7C], eax
0x18000dd61  mov     rax, [rdi+80h]
0x18000dd68  mov     [rbp+var_38], rax
0x18000dd6c  mov     eax, [rdi+40h]
0x18000dd6f  mov     [rbp+var_78], eax
0x18000dd72  mov     rax, [rdi+38h]
0x18000dd76  mov     [rbp+var_30], rax
0x18000dd7a  mov     eax, [rdi+8]
0x18000dd7d  mov     [rbp+var_74], eax
0x18000dd80  lea     rax, [rbp+var_70]
0x18000dd84  mov     [rsp+140h+var_90], rax
0x18000dd8c  lea     rax, [rbp+SRWLock]
0x18000dd90  mov     [rsp+140h+var_98], rax
0x18000dd98  lea     rax, [rbp+arg_8]
0x18000dd9c  mov     [rsp+140h+var_A0], rax
0x18000dda4  lea     rax, [rbp+var_68]
0x18000dda8  mov     [rsp+140h+var_A8], rax
0x18000ddb0  lea     rax, [rbp+var_60]
0x18000ddb4  mov     [rsp+140h+var_B0], rax
0x18000ddbc  lea     rax, [rbp+arg_10]
0x18000ddc0  mov     [rsp+140h+var_B8], rax
0x18000ddc8  lea     rax, [rbp+var_58]
0x18000ddcc  mov     [rsp+140h+var_C0], rax
0x18000ddd4  lea     rax, [rbp+var_50]
0x18000ddd8  mov     [rsp+140h+var_C8], rax
0x18000dddd  lea     rax, [rbp+arg_18]
0x18000dde1  mov     [rsp+140h+var_D0], rax
0x18000dde6  lea     rax, [rbp+var_48]
0x18000ddea  mov     [rsp+140h+var_D8], rax
0x18000ddef  lea     rax, [rbp+var_80]
0x18000ddf3  mov     [rsp+140h+var_E0], rax
0x18000ddf8  lea     rax, [rbp+var_40]
0x18000ddfc  mov     [rsp+140h+var_E8], rax
0x18000de01  lea     rax, [rbp+var_7C]
0x18000de05  mov     [rsp+140h+var_F0], rax
0x18000de0a  lea     rax, [rbp+var_38]
0x18000de0e  mov     [rsp+140h+var_F8], rax
0x18000de13  lea     rax, [rbp+var_78]
0x18000de17  mov     [rsp+140h+var_100], rax
0x18000de1c  lea     rax, [rbp+var_30]
0x18000de20  mov     [rsp+140h+var_108], rax
0x18000de25  lea     rax, [rbp+var_74]
0x18000de29  mov     [rsp+140h+var_110], rax
0x18000de2e  lea     rax, [rbp+var_28]
0x18000de32  mov     [rsp+140h+var_118], rax
0x18000de37  lea     rax, [rbp+var_20]
0x18000de3b  mov     [rsp+140h+var_120], rax
0x18000de40  mov     [rbp+var_28], 1000000h
0x18000de48  mov     [rbp+var_20], 0
0x18000de50  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000de55  jmp     loc_18000DEDC
0x18000de5a  lea     rdx, [rbp+SRWLock]
0x18000de5e  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000de63  mov     rax, [rbx+110h]
0x18000de6a  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000de6e  mov     dword ptr [rax], 2
0x18000de74  test    rcx, rcx
0x18000de77  jz      short loc_18000DE7F
0x18000de79  call    cs:__imp_ReleaseSRWLockExclusive
0x18000de7f  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000de84  mov     rdi, [rax+8]
0x18000de88  mov     eax, [rdi]
0x18000de8a  cmp     eax, 5
0x18000de8d  jbe     short loc_18000DEDC
0x18000de8f  call    cs:__imp_GetCurrentThreadId
0x18000de95  mov     r8, [rbx+110h]
0x18000de9c  lea     rdx, byte_180037513
0x18000dea3  mov     dword ptr [rbp+SRWLock], eax
0x18000dea6  mov     rcx, rdi
0x18000dea9  mov     eax, [r8+48h]
0x18000dead  add     r8, 8
0x18000deb1  mov     [rbp+arg_8], eax
0x18000deb4  lea     rax, [rbp+SRWLock]
0x18000deb8  mov     [rsp+140h+var_110], rax
0x18000debd  lea     rax, [rbp+arg_8]
0x18000dec1  mov     [rsp+140h+var_118], rax
0x18000dec6  lea     rax, [rbp+arg_10]
0x18000deca  mov     [rsp+140h+var_120], rax
0x18000decf  mov     [rbp+arg_10], 0
0x18000ded7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000dedc  mov     rcx, rbx
0x18000dedf  add     rsp, 130h
0x18000dee6  pop     rdi
0x18000dee7  pop     rbx
0x18000dee8  pop     rbp
0x18000dee9  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
