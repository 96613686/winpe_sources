# MDMPushProvider::InitializeActivity::StopActivity(void)

- ea: `0x18002e670`
- end: `0x18002e8df`
- name: `?StopActivity@InitializeActivity@MDMPushProvider@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(MDMPushProvider::InitializeActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001cb4`
- `0x180001ff8`
- `0x18002cc70`
- `0x18002cef8`
- `0x18002d36c`
- `0x18002e670`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e880`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e6ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e86b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e6ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e86b`

## pseudocode

```c
void __fastcall MDMPushProvider::InitializeActivity::StopActivity(MDMPushProvider::InitializeActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  const unsigned __int16 *v7; // rcx
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-70h] BYREF
  const OLECHAR *v19; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-60h] BYREF
  const OLECHAR *v21; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-48h] BYREF
  const OLECHAR *v24; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+110h] [rbp-30h] BYREF
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
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = MDMPushProvider::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = (const OLECHAR *)*((_QWORD *)v4 + 12);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = (const OLECHAR *)*((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v7;
      LODWORD(SRWLock) = v4[17];
      v30 = v4[4];
      v19 = (const OLECHAR *)*((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v6,
        (__int64)&word_18004786E,
        v8 + 8,
        (__int64)v6,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v32,
        &v22,
        &v21,
        (__int64)&v31,
        &v20,
        &v19,
        (__int64)&v30,
        (__int64)&SRWLock,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = MDMPushProvider::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)byte_18004781B,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002e670  push    rbp
0x18002e672  push    rbx
0x18002e673  push    rdi
0x18002e674  lea     rbp, [rsp+10h]
0x18002e679  sub     rsp, 130h
0x18002e680  mov     rdi, [rcx+110h]
0x18002e687  mov     rbx, rcx
0x18002e68a  mov     eax, [rdi+48h]
0x18002e68d  test    eax, eax
0x18002e68f  jns     loc_18002E84C
0x18002e695  add     rdi, 50h ; 'P'
0x18002e699  cmp     eax, [rdi+8]
0x18002e69c  jnz     loc_18002E84C
0x18002e6a2  test    rdi, rdi
0x18002e6a5  jz      loc_18002E84C
0x18002e6ab  lea     rdx, [rbp+SRWLock]
0x18002e6af  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e6b4  mov     rax, [rbx+110h]
0x18002e6bb  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002e6bf  mov     dword ptr [rax], 2
0x18002e6c5  test    rcx, rcx
0x18002e6c8  jz      short loc_18002E6D0
0x18002e6ca  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e6d0  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002e6d5  mov     r9, rax
0x18002e6d8  mov     ecx, [rax]
0x18002e6da  cmp     ecx, 5
0x18002e6dd  jbe     loc_18002E8CD
0x18002e6e3  mov     rax, [rdi+70h]
0x18002e6e7  lea     rdx, word_18004786E
0x18002e6ee  mov     rcx, [rdi+30h]
0x18002e6f2  mov     [rbp+var_60], rax
0x18002e6f6  mov     eax, [rdi+68h]
0x18002e6f9  mov     r8, [rbx+110h]
0x18002e700  mov     dword ptr [rbp+arg_10], eax
0x18002e703  add     r8, 8
0x18002e707  mov     rax, [rdi+60h]
0x18002e70b  mov     [rbp+var_58], rax
0x18002e70f  mov     rax, [rdi+58h]
0x18002e713  mov     [rbp+var_50], rax
0x18002e717  mov     eax, [rdi+50h]
0x18002e71a  mov     [rbp+arg_18], eax
0x18002e71d  mov     rax, [rdi+48h]
0x18002e721  mov     [rbp+var_48], rax
0x18002e725  mov     eax, [rdi+20h]
0x18002e728  mov     [rbp+var_80], eax
0x18002e72b  mov     rax, [rdi+18h]
0x18002e72f  mov     [rbp+var_40], rax
0x18002e733  mov     eax, [rdi]
0x18002e735  mov     [rbp+var_7C], eax
0x18002e738  mov     rax, [rdi+80h]
0x18002e73f  mov     [rbp+var_38], rax
0x18002e743  mov     eax, [rdi+40h]
0x18002e746  mov     [rbp+var_78], eax
0x18002e749  mov     rax, [rdi+38h]
0x18002e74d  mov     [rbp+var_30], rax
0x18002e751  mov     eax, [rdi+8]
0x18002e754  mov     [rbp+var_74], eax
0x18002e757  lea     rax, [rbp+var_70]
0x18002e75b  mov     [rsp+140h+var_90], rax
0x18002e763  lea     rax, [rbp+SRWLock]
0x18002e767  mov     [rsp+140h+var_98], rax
0x18002e76f  lea     rax, [rbp+arg_8]
0x18002e773  mov     [rsp+140h+var_A0], rax
0x18002e77b  lea     rax, [rbp+var_68]
0x18002e77f  mov     [rsp+140h+var_A8], rax
0x18002e787  lea     rax, [rbp+var_60]
0x18002e78b  mov     [rsp+140h+var_B0], rax
0x18002e793  lea     rax, [rbp+arg_10]
0x18002e797  mov     [rsp+140h+var_B8], rax
0x18002e79f  lea     rax, [rbp+var_58]
0x18002e7a3  mov     [rsp+140h+var_C0], rax
0x18002e7ab  lea     rax, [rbp+var_50]
0x18002e7af  mov     [rsp+140h+var_C8], rax
0x18002e7b4  lea     rax, [rbp+arg_18]
0x18002e7b8  mov     [rsp+140h+var_D0], rax
0x18002e7bd  lea     rax, [rbp+var_48]
0x18002e7c1  mov     [rsp+140h+var_D8], rax
0x18002e7c6  lea     rax, [rbp+var_80]
0x18002e7ca  mov     [rsp+140h+var_E0], rax
0x18002e7cf  lea     rax, [rbp+var_40]
0x18002e7d3  mov     [rsp+140h+var_E8], rax
0x18002e7d8  lea     rax, [rbp+var_7C]
0x18002e7dc  mov     [rsp+140h+var_F0], rax
0x18002e7e1  lea     rax, [rbp+var_38]
0x18002e7e5  mov     [rsp+140h+var_F8], rax
0x18002e7ea  lea     rax, [rbp+var_78]
0x18002e7ee  mov     [rsp+140h+var_100], rax
0x18002e7f3  lea     rax, [rbp+var_30]
0x18002e7f7  mov     [rsp+140h+var_108], rax
0x18002e7fc  lea     rax, [rbp+var_74]
0x18002e800  mov     [rbp+var_70], rcx
0x18002e804  mov     ecx, [rdi+44h]
0x18002e807  mov     [rsp+140h+var_110], rax
0x18002e80c  lea     rax, [rbp+var_28]
0x18002e810  mov     dword ptr [rbp+SRWLock], ecx
0x18002e813  mov     ecx, [rdi+10h]
0x18002e816  mov     [rbp+arg_8], ecx
0x18002e819  mov     rcx, [rdi+78h]
0x18002e81d  mov     [rsp+140h+var_118], rax
0x18002e822  lea     rax, [rbp+var_20]
0x18002e826  mov     [rbp+var_68], rcx
0x18002e82a  mov     rcx, r9
0x18002e82d  mov     [rsp+140h+var_120], rax
0x18002e832  mov     [rbp+var_28], 1000000h
0x18002e83a  mov     [rbp+var_20], 0
0x18002e842  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002e847  jmp     loc_18002E8CD
0x18002e84c  lea     rdx, [rbp+SRWLock]
0x18002e850  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e855  mov     rax, [rbx+110h]
0x18002e85c  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002e860  mov     dword ptr [rax], 2
0x18002e866  test    rcx, rcx
0x18002e869  jz      short loc_18002E871
0x18002e86b  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e871  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002e876  mov     rdi, rax
0x18002e879  mov     ecx, [rax]
0x18002e87b  cmp     ecx, 5
0x18002e87e  jbe     short loc_18002E8CD
0x18002e880  call    cs:__imp_GetCurrentThreadId
0x18002e886  mov     r8, [rbx+110h]
0x18002e88d  lea     rdx, byte_18004781B
0x18002e894  mov     dword ptr [rbp+SRWLock], eax
0x18002e897  lea     rax, [rbp+SRWLock]
0x18002e89b  mov     [rsp+140h+var_110], rax
0x18002e8a0  lea     rax, [rbp+arg_8]
0x18002e8a4  mov     [rsp+140h+var_118], rax
0x18002e8a9  lea     rax, [rbp+arg_10]
0x18002e8ad  mov     ecx, [r8+48h]
0x18002e8b1  add     r8, 8
0x18002e8b5  mov     [rbp+arg_8], ecx
0x18002e8b8  mov     rcx, rdi
0x18002e8bb  mov     [rsp+140h+var_120], rax
0x18002e8c0  mov     [rbp+arg_10], 0
0x18002e8c8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002e8cd  mov     rcx, rbx
0x18002e8d0  add     rsp, 130h
0x18002e8d7  pop     rdi
0x18002e8d8  pop     rbx
0x18002e8d9  pop     rbp
0x18002e8da  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
