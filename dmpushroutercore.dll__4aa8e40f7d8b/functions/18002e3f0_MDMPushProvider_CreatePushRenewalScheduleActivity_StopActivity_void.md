# MDMPushProvider::CreatePushRenewalScheduleActivity::StopActivity(void)

- ea: `0x18002e3f0`
- end: `0x18002e65f`
- name: `?StopActivity@CreatePushRenewalScheduleActivity@MDMPushProvider@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(MDMPushProvider::CreatePushRenewalScheduleActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001cb4`
- `0x180001ff8`
- `0x18002cc70`
- `0x18002cef8`
- `0x18002d36c`
- `0x18002e3f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e600`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e600`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e44a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e5eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e44a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e5eb`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushRenewalScheduleActivity::StopActivity(
        MDMPushProvider::CreatePushRenewalScheduleActivity *this)
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
        (unsigned int)&dword_180047064,
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
        (unsigned int)byte_18004778D,
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
0x18002e3f0  push    rbp
0x18002e3f2  push    rbx
0x18002e3f3  push    rdi
0x18002e3f4  lea     rbp, [rsp+10h]
0x18002e3f9  sub     rsp, 130h
0x18002e400  mov     rdi, [rcx+110h]
0x18002e407  mov     rbx, rcx
0x18002e40a  mov     eax, [rdi+48h]
0x18002e40d  test    eax, eax
0x18002e40f  jns     loc_18002E5CC
0x18002e415  add     rdi, 50h ; 'P'
0x18002e419  cmp     eax, [rdi+8]
0x18002e41c  jnz     loc_18002E5CC
0x18002e422  test    rdi, rdi
0x18002e425  jz      loc_18002E5CC
0x18002e42b  lea     rdx, [rbp+SRWLock]
0x18002e42f  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e434  mov     rax, [rbx+110h]
0x18002e43b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002e43f  mov     dword ptr [rax], 2
0x18002e445  test    rcx, rcx
0x18002e448  jz      short loc_18002E450
0x18002e44a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e450  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002e455  mov     r9, rax
0x18002e458  mov     ecx, [rax]
0x18002e45a  cmp     ecx, 5
0x18002e45d  jbe     loc_18002E64D
0x18002e463  mov     rax, [rdi+70h]
0x18002e467  lea     rdx, dword_180047064
0x18002e46e  mov     rcx, [rdi+30h]
0x18002e472  mov     [rbp+var_60], rax
0x18002e476  mov     eax, [rdi+68h]
0x18002e479  mov     r8, [rbx+110h]
0x18002e480  mov     dword ptr [rbp+arg_10], eax
0x18002e483  add     r8, 8
0x18002e487  mov     rax, [rdi+60h]
0x18002e48b  mov     [rbp+var_58], rax
0x18002e48f  mov     rax, [rdi+58h]
0x18002e493  mov     [rbp+var_50], rax
0x18002e497  mov     eax, [rdi+50h]
0x18002e49a  mov     [rbp+arg_18], eax
0x18002e49d  mov     rax, [rdi+48h]
0x18002e4a1  mov     [rbp+var_48], rax
0x18002e4a5  mov     eax, [rdi+20h]
0x18002e4a8  mov     [rbp+var_80], eax
0x18002e4ab  mov     rax, [rdi+18h]
0x18002e4af  mov     [rbp+var_40], rax
0x18002e4b3  mov     eax, [rdi]
0x18002e4b5  mov     [rbp+var_7C], eax
0x18002e4b8  mov     rax, [rdi+80h]
0x18002e4bf  mov     [rbp+var_38], rax
0x18002e4c3  mov     eax, [rdi+40h]
0x18002e4c6  mov     [rbp+var_78], eax
0x18002e4c9  mov     rax, [rdi+38h]
0x18002e4cd  mov     [rbp+var_30], rax
0x18002e4d1  mov     eax, [rdi+8]
0x18002e4d4  mov     [rbp+var_74], eax
0x18002e4d7  lea     rax, [rbp+var_70]
0x18002e4db  mov     [rsp+140h+var_90], rax
0x18002e4e3  lea     rax, [rbp+SRWLock]
0x18002e4e7  mov     [rsp+140h+var_98], rax
0x18002e4ef  lea     rax, [rbp+arg_8]
0x18002e4f3  mov     [rsp+140h+var_A0], rax
0x18002e4fb  lea     rax, [rbp+var_68]
0x18002e4ff  mov     [rsp+140h+var_A8], rax
0x18002e507  lea     rax, [rbp+var_60]
0x18002e50b  mov     [rsp+140h+var_B0], rax
0x18002e513  lea     rax, [rbp+arg_10]
0x18002e517  mov     [rsp+140h+var_B8], rax
0x18002e51f  lea     rax, [rbp+var_58]
0x18002e523  mov     [rsp+140h+var_C0], rax
0x18002e52b  lea     rax, [rbp+var_50]
0x18002e52f  mov     [rsp+140h+var_C8], rax
0x18002e534  lea     rax, [rbp+arg_18]
0x18002e538  mov     [rsp+140h+var_D0], rax
0x18002e53d  lea     rax, [rbp+var_48]
0x18002e541  mov     [rsp+140h+var_D8], rax
0x18002e546  lea     rax, [rbp+var_80]
0x18002e54a  mov     [rsp+140h+var_E0], rax
0x18002e54f  lea     rax, [rbp+var_40]
0x18002e553  mov     [rsp+140h+var_E8], rax
0x18002e558  lea     rax, [rbp+var_7C]
0x18002e55c  mov     [rsp+140h+var_F0], rax
0x18002e561  lea     rax, [rbp+var_38]
0x18002e565  mov     [rsp+140h+var_F8], rax
0x18002e56a  lea     rax, [rbp+var_78]
0x18002e56e  mov     [rsp+140h+var_100], rax
0x18002e573  lea     rax, [rbp+var_30]
0x18002e577  mov     [rsp+140h+var_108], rax
0x18002e57c  lea     rax, [rbp+var_74]
0x18002e580  mov     [rbp+var_70], rcx
0x18002e584  mov     ecx, [rdi+44h]
0x18002e587  mov     [rsp+140h+var_110], rax
0x18002e58c  lea     rax, [rbp+var_28]
0x18002e590  mov     dword ptr [rbp+SRWLock], ecx
0x18002e593  mov     ecx, [rdi+10h]
0x18002e596  mov     [rbp+arg_8], ecx
0x18002e599  mov     rcx, [rdi+78h]
0x18002e59d  mov     [rsp+140h+var_118], rax
0x18002e5a2  lea     rax, [rbp+var_20]
0x18002e5a6  mov     [rbp+var_68], rcx
0x18002e5aa  mov     rcx, r9
0x18002e5ad  mov     [rsp+140h+var_120], rax
0x18002e5b2  mov     [rbp+var_28], 1000000h
0x18002e5ba  mov     [rbp+var_20], 0
0x18002e5c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002e5c7  jmp     loc_18002E64D
0x18002e5cc  lea     rdx, [rbp+SRWLock]
0x18002e5d0  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e5d5  mov     rax, [rbx+110h]
0x18002e5dc  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002e5e0  mov     dword ptr [rax], 2
0x18002e5e6  test    rcx, rcx
0x18002e5e9  jz      short loc_18002E5F1
0x18002e5eb  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e5f1  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002e5f6  mov     rdi, rax
0x18002e5f9  mov     ecx, [rax]
0x18002e5fb  cmp     ecx, 5
0x18002e5fe  jbe     short loc_18002E64D
0x18002e600  call    cs:__imp_GetCurrentThreadId
0x18002e606  mov     r8, [rbx+110h]
0x18002e60d  lea     rdx, byte_18004778D
0x18002e614  mov     dword ptr [rbp+SRWLock], eax
0x18002e617  lea     rax, [rbp+SRWLock]
0x18002e61b  mov     [rsp+140h+var_110], rax
0x18002e620  lea     rax, [rbp+arg_8]
0x18002e624  mov     [rsp+140h+var_118], rax
0x18002e629  lea     rax, [rbp+arg_10]
0x18002e62d  mov     ecx, [r8+48h]
0x18002e631  add     r8, 8
0x18002e635  mov     [rbp+arg_8], ecx
0x18002e638  mov     rcx, rdi
0x18002e63b  mov     [rsp+140h+var_120], rax
0x18002e640  mov     [rbp+arg_10], 0
0x18002e648  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002e64d  mov     rcx, rbx
0x18002e650  add     rsp, 130h
0x18002e657  pop     rdi
0x18002e658  pop     rbx
0x18002e659  pop     rbp
0x18002e65a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
