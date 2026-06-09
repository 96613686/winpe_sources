# MDMPushProvider::CreatePushLaunchScheduleActivity::StopActivity(void)

- ea: `0x18002e170`
- end: `0x18002e3df`
- name: `?StopActivity@CreatePushLaunchScheduleActivity@MDMPushProvider@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(MDMPushProvider::CreatePushLaunchScheduleActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001cb4`
- `0x180001ff8`
- `0x18002cc70`
- `0x18002cef8`
- `0x18002d36c`
- `0x18002e170`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e380`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e1ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e36b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e1ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e36b`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushLaunchScheduleActivity::StopActivity(
        MDMPushProvider::CreatePushLaunchScheduleActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // r9d
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+100h] [rbp-40h] BYREF
  __int64 v26; // [rsp+108h] [rbp-38h] BYREF
  __int64 v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v29[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  int v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = MDMPushProvider::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      v7 = *((_QWORD *)v4 + 6);
      v21 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v32) = v4[26];
      v22 = *((_QWORD *)v4 + 12);
      v23 = *((_QWORD *)v4 + 11);
      v33 = v4[20];
      v24 = *((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = *((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v19 = v7;
      LODWORD(SRWLock) = v4[17];
      v31 = v4[4];
      v20 = *((_QWORD *)v4 + 15);
      v28 = 0x1000000;
      v29[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v6,
        (unsigned int)word_180047632,
        v8 + 8,
        (_DWORD)v6,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v33,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v31,
        (__int64)&SRWLock,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = MDMPushProvider::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v31 = *(_DWORD *)(v13 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)byte_1800475D1,
        v13 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002e170  push    rbp
0x18002e172  push    rbx
0x18002e173  push    rdi
0x18002e174  lea     rbp, [rsp+10h]
0x18002e179  sub     rsp, 130h
0x18002e180  mov     rdi, [rcx+110h]
0x18002e187  mov     rbx, rcx
0x18002e18a  mov     eax, [rdi+48h]
0x18002e18d  test    eax, eax
0x18002e18f  jns     loc_18002E34C
0x18002e195  add     rdi, 50h ; 'P'
0x18002e199  cmp     eax, [rdi+8]
0x18002e19c  jnz     loc_18002E34C
0x18002e1a2  test    rdi, rdi
0x18002e1a5  jz      loc_18002E34C
0x18002e1ab  lea     rdx, [rbp+SRWLock]
0x18002e1af  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e1b4  mov     rax, [rbx+110h]
0x18002e1bb  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002e1bf  mov     dword ptr [rax], 2
0x18002e1c5  test    rcx, rcx
0x18002e1c8  jz      short loc_18002E1D0
0x18002e1ca  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e1d0  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002e1d5  mov     r9, rax
0x18002e1d8  mov     ecx, [rax]
0x18002e1da  cmp     ecx, 5
0x18002e1dd  jbe     loc_18002E3CD
0x18002e1e3  mov     rax, [rdi+70h]
0x18002e1e7  lea     rdx, word_180047632
0x18002e1ee  mov     rcx, [rdi+30h]
0x18002e1f2  mov     [rbp+var_60], rax
0x18002e1f6  mov     eax, [rdi+68h]
0x18002e1f9  mov     r8, [rbx+110h]
0x18002e200  mov     dword ptr [rbp+arg_10], eax
0x18002e203  add     r8, 8
0x18002e207  mov     rax, [rdi+60h]
0x18002e20b  mov     [rbp+var_58], rax
0x18002e20f  mov     rax, [rdi+58h]
0x18002e213  mov     [rbp+var_50], rax
0x18002e217  mov     eax, [rdi+50h]
0x18002e21a  mov     [rbp+arg_18], eax
0x18002e21d  mov     rax, [rdi+48h]
0x18002e221  mov     [rbp+var_48], rax
0x18002e225  mov     eax, [rdi+20h]
0x18002e228  mov     [rbp+var_80], eax
0x18002e22b  mov     rax, [rdi+18h]
0x18002e22f  mov     [rbp+var_40], rax
0x18002e233  mov     eax, [rdi]
0x18002e235  mov     [rbp+var_7C], eax
0x18002e238  mov     rax, [rdi+80h]
0x18002e23f  mov     [rbp+var_38], rax
0x18002e243  mov     eax, [rdi+40h]
0x18002e246  mov     [rbp+var_78], eax
0x18002e249  mov     rax, [rdi+38h]
0x18002e24d  mov     [rbp+var_30], rax
0x18002e251  mov     eax, [rdi+8]
0x18002e254  mov     [rbp+var_74], eax
0x18002e257  lea     rax, [rbp+var_70]
0x18002e25b  mov     [rsp+140h+var_90], rax
0x18002e263  lea     rax, [rbp+SRWLock]
0x18002e267  mov     [rsp+140h+var_98], rax
0x18002e26f  lea     rax, [rbp+arg_8]
0x18002e273  mov     [rsp+140h+var_A0], rax
0x18002e27b  lea     rax, [rbp+var_68]
0x18002e27f  mov     [rsp+140h+var_A8], rax
0x18002e287  lea     rax, [rbp+var_60]
0x18002e28b  mov     [rsp+140h+var_B0], rax
0x18002e293  lea     rax, [rbp+arg_10]
0x18002e297  mov     [rsp+140h+var_B8], rax
0x18002e29f  lea     rax, [rbp+var_58]
0x18002e2a3  mov     [rsp+140h+var_C0], rax
0x18002e2ab  lea     rax, [rbp+var_50]
0x18002e2af  mov     [rsp+140h+var_C8], rax
0x18002e2b4  lea     rax, [rbp+arg_18]
0x18002e2b8  mov     [rsp+140h+var_D0], rax
0x18002e2bd  lea     rax, [rbp+var_48]
0x18002e2c1  mov     [rsp+140h+var_D8], rax
0x18002e2c6  lea     rax, [rbp+var_80]
0x18002e2ca  mov     [rsp+140h+var_E0], rax
0x18002e2cf  lea     rax, [rbp+var_40]
0x18002e2d3  mov     [rsp+140h+var_E8], rax
0x18002e2d8  lea     rax, [rbp+var_7C]
0x18002e2dc  mov     [rsp+140h+var_F0], rax
0x18002e2e1  lea     rax, [rbp+var_38]
0x18002e2e5  mov     [rsp+140h+var_F8], rax
0x18002e2ea  lea     rax, [rbp+var_78]
0x18002e2ee  mov     [rsp+140h+var_100], rax
0x18002e2f3  lea     rax, [rbp+var_30]
0x18002e2f7  mov     [rsp+140h+var_108], rax
0x18002e2fc  lea     rax, [rbp+var_74]
0x18002e300  mov     [rbp+var_70], rcx
0x18002e304  mov     ecx, [rdi+44h]
0x18002e307  mov     [rsp+140h+var_110], rax
0x18002e30c  lea     rax, [rbp+var_28]
0x18002e310  mov     dword ptr [rbp+SRWLock], ecx
0x18002e313  mov     ecx, [rdi+10h]
0x18002e316  mov     [rbp+arg_8], ecx
0x18002e319  mov     rcx, [rdi+78h]
0x18002e31d  mov     [rsp+140h+var_118], rax
0x18002e322  lea     rax, [rbp+var_20]
0x18002e326  mov     [rbp+var_68], rcx
0x18002e32a  mov     rcx, r9
0x18002e32d  mov     [rsp+140h+var_120], rax
0x18002e332  mov     [rbp+var_28], 1000000h
0x18002e33a  mov     [rbp+var_20], 0
0x18002e342  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002e347  jmp     loc_18002E3CD
0x18002e34c  lea     rdx, [rbp+SRWLock]
0x18002e350  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e355  mov     rax, [rbx+110h]
0x18002e35c  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002e360  mov     dword ptr [rax], 2
0x18002e366  test    rcx, rcx
0x18002e369  jz      short loc_18002E371
0x18002e36b  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e371  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002e376  mov     rdi, rax
0x18002e379  mov     ecx, [rax]
0x18002e37b  cmp     ecx, 5
0x18002e37e  jbe     short loc_18002E3CD
0x18002e380  call    cs:__imp_GetCurrentThreadId
0x18002e386  mov     r8, [rbx+110h]
0x18002e38d  lea     rdx, byte_1800475D1
0x18002e394  mov     dword ptr [rbp+SRWLock], eax
0x18002e397  lea     rax, [rbp+SRWLock]
0x18002e39b  mov     [rsp+140h+var_110], rax
0x18002e3a0  lea     rax, [rbp+arg_8]
0x18002e3a4  mov     [rsp+140h+var_118], rax
0x18002e3a9  lea     rax, [rbp+arg_10]
0x18002e3ad  mov     ecx, [r8+48h]
0x18002e3b1  add     r8, 8
0x18002e3b5  mov     [rbp+arg_8], ecx
0x18002e3b8  mov     rcx, rdi
0x18002e3bb  mov     [rsp+140h+var_120], rax
0x18002e3c0  mov     [rbp+arg_10], 0
0x18002e3c8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002e3cd  mov     rcx, rbx
0x18002e3d0  add     rsp, 130h
0x18002e3d7  pop     rdi
0x18002e3d8  pop     rbx
0x18002e3d9  pop     rbp
0x18002e3da  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
