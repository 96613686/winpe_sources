# HyperVStorageTrace::HyperVFile_Commit::StopActivity(void)

- ea: `0x180069bd0`
- end: `0x180069ea3`
- name: `?StopActivity@HyperVFile_Commit@HyperVStorageTrace@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(HyperVStorageTrace::HyperVFile_Commit *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180066284`
- `0x180069bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069c37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069dfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069c37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069dfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069e2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069e2a`

## pseudocode

```c
void __fastcall HyperVStorageTrace::HyperVFile_Commit::StopActivity(HyperVStorageTrace::HyperVFile_Commit *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v9; // [rsp+C8h] [rbp-78h] BYREF
  int v10; // [rsp+CCh] [rbp-74h] BYREF
  int v11; // [rsp+D0h] [rbp-70h] BYREF
  int v12; // [rsp+D4h] [rbp-6Ch] BYREF
  int v13; // [rsp+D8h] [rbp-68h] BYREF
  int v14; // [rsp+DCh] [rbp-64h] BYREF
  int v15; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v17; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v18; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v19; // [rsp+100h] [rbp-40h] BYREF
  __int64 v20; // [rsp+108h] [rbp-38h] BYREF
  __int64 v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23; // [rsp+120h] [rbp-20h] BYREF
  __int64 v24; // [rsp+128h] [rbp-18h] BYREF
  __int64 v25; // [rsp+130h] [rbp-10h] BYREF
  __int64 v26; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)HyperVStorageTrace::Instance() + 1);
    if ( *(_DWORD *)v5 > 4u && (*(_QWORD *)(v5 + 16) & 2) != 0 && (*(_QWORD *)(v5 + 24) & 2LL) == *(_QWORD *)(v5 + 24) )
    {
      v17 = *((_QWORD *)v4 + 6);
      v10 = v4[17];
      v11 = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v19 = *((_QWORD *)v4 + 14);
      v12 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v13 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v9 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v26 = 0x1000000;
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (int)&unk_1800CB2F0,
        *((_QWORD *)this + 34) + 8,
        (__int64)&v16,
        (__int64)&v26,
        (__int64)&SRWLock,
        (__int64)&v25,
        (__int64)&v9,
        (__int64)&v24,
        (__int64)&v15,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v12,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v17);
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)HyperVStorageTrace::Instance() + 1);
    if ( *(_DWORD *)v6 > 4u && (*(_QWORD *)(v6 + 16) & 2) != 0 && (*(_QWORD *)(v6 + 24) & 2LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&dword_1800CB43C,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((HyperVStorageTrace::HyperVFile_Commit *)((char *)this + 288));
}

```

## disassembly

```asm
0x180069bd0  mov     [rsp-8+arg_8], rbx
0x180069bd5  mov     [rsp-8+arg_10], rdi
0x180069bda  push    rbp
0x180069bdb  mov     rbp, rsp
0x180069bde  sub     rsp, 140h
0x180069be5  mov     rbx, rcx
0x180069be8  mov     rdi, [rcx+110h]
0x180069bef  mov     eax, [rdi+48h]
0x180069bf2  test    eax, eax
0x180069bf4  jns     loc_180069DD6
0x180069bfa  add     rdi, 50h ; 'P'
0x180069bfe  cmp     eax, [rdi+8]
0x180069c01  jnz     loc_180069DD6
0x180069c07  test    rdi, rdi
0x180069c0a  jz      loc_180069DD6
0x180069c10  mov     [rbp+SRWLock], 0
0x180069c18  lea     rdx, [rbp+SRWLock]
0x180069c1c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069c21  mov     rax, [rbx+110h]
0x180069c28  mov     dword ptr [rax], 2
0x180069c2e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180069c32  test    rcx, rcx
0x180069c35  jz      short loc_180069C3D
0x180069c37  call    cs:__imp_ReleaseSRWLockExclusive
0x180069c3d  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180069c42  mov     rcx, [rax+8]; int
0x180069c46  mov     eax, [rcx]
0x180069c48  cmp     eax, 4
0x180069c4b  jbe     loc_180069E7B
0x180069c51  mov     rdx, [rcx+18h]
0x180069c55  mov     rax, [rcx+10h]
0x180069c59  test    al, 2
0x180069c5b  jz      loc_180069E7B
0x180069c61  mov     rax, rdx
0x180069c64  and     eax, 2
0x180069c67  cmp     rax, rdx
0x180069c6a  jnz     loc_180069E7B
0x180069c70  mov     rax, [rdi+30h]
0x180069c74  mov     [rbp+var_50], rax
0x180069c78  mov     eax, [rdi+44h]
0x180069c7b  mov     dword ptr [rbp+var_78+4], eax
0x180069c7e  mov     eax, [rdi+10h]
0x180069c81  mov     dword ptr [rbp+var_70], eax
0x180069c84  mov     rax, [rdi+78h]
0x180069c88  mov     [rbp+var_48], rax
0x180069c8c  mov     rax, [rdi+70h]
0x180069c90  mov     [rbp+var_40], rax
0x180069c94  mov     eax, [rdi+68h]
0x180069c97  mov     dword ptr [rbp+var_70+4], eax
0x180069c9a  mov     rax, [rdi+60h]
0x180069c9e  mov     [rbp+var_38], rax
0x180069ca2  mov     rax, [rdi+58h]
0x180069ca6  mov     [rbp+var_30], rax
0x180069caa  mov     eax, [rdi+50h]
0x180069cad  mov     dword ptr [rbp+var_68], eax
0x180069cb0  mov     rax, [rdi+48h]
0x180069cb4  mov     [rbp+var_28], rax
0x180069cb8  mov     eax, [rdi+20h]
0x180069cbb  mov     dword ptr [rbp+var_68+4], eax
0x180069cbe  mov     rax, [rdi+18h]
0x180069cc2  mov     [rbp+var_20], rax
0x180069cc6  mov     eax, [rdi]
0x180069cc8  mov     [rbp+var_60], eax
0x180069ccb  mov     rax, [rdi+80h]
0x180069cd2  mov     [rbp+var_18], rax
0x180069cd6  mov     eax, [rdi+40h]
0x180069cd9  mov     dword ptr [rbp+var_78], eax
0x180069cdc  mov     rax, [rdi+38h]
0x180069ce0  mov     [rbp+var_10], rax
0x180069ce4  mov     eax, [rdi+8]
0x180069ce7  mov     dword ptr [rbp+SRWLock], eax
0x180069cea  mov     [rbp+var_8], 1000000h
0x180069cf2  mov     [rbp+var_58], 0
0x180069cfa  mov     r8, [rbx+110h]
0x180069d01  add     r8, 8; int
0x180069d05  lea     rax, [rbp+var_50]
0x180069d09  mov     [rsp+140h+var_90], rax; __int64
0x180069d11  lea     rax, [rbp+var_78+4]
0x180069d15  mov     [rsp+140h+var_98], rax; __int64
0x180069d1d  lea     rax, [rbp+var_70]
0x180069d21  mov     [rsp+140h+var_A0], rax; __int64
0x180069d29  lea     rax, [rbp+var_48]
0x180069d2d  mov     [rsp+140h+var_A8], rax; __int64
0x180069d35  lea     rax, [rbp+var_40]
0x180069d39  mov     [rsp+140h+var_B0], rax; __int64
0x180069d41  lea     rax, [rbp+var_70+4]
0x180069d45  mov     [rsp+140h+var_B8], rax; __int64
0x180069d4d  lea     rax, [rbp+var_38]
0x180069d51  mov     [rsp+140h+var_C0], rax; __int64
0x180069d59  lea     rax, [rbp+var_30]
0x180069d5d  mov     [rsp+140h+var_C8], rax; __int64
0x180069d62  lea     rax, [rbp+var_68]
0x180069d66  mov     [rsp+140h+var_D0], rax; __int64
0x180069d6b  lea     rax, [rbp+var_28]
0x180069d6f  mov     [rsp+140h+var_D8], rax; __int64
0x180069d74  lea     rax, [rbp+var_68+4]
0x180069d78  mov     [rsp+140h+var_E0], rax; __int64
0x180069d7d  lea     rax, [rbp+var_20]
0x180069d81  mov     [rsp+140h+var_E8], rax; __int64
0x180069d86  lea     rax, [rbp+var_60]
0x180069d8a  mov     [rsp+140h+var_F0], rax; __int64
0x180069d8f  lea     rax, [rbp+var_18]
0x180069d93  mov     [rsp+140h+var_F8], rax; __int64
0x180069d98  lea     rax, [rbp+var_78]
0x180069d9c  mov     [rsp+140h+var_100], rax; __int64
0x180069da1  lea     rax, [rbp+var_10]
0x180069da5  mov     [rsp+140h+var_108], rax; __int64
0x180069daa  lea     rax, [rbp+SRWLock]
0x180069dae  mov     [rsp+140h+var_110], rax; __int64
0x180069db3  lea     rax, [rbp+var_8]
0x180069db7  mov     [rsp+140h+var_118], rax; __int64
0x180069dbc  lea     rax, [rbp+var_58]
0x180069dc0  mov     [rsp+140h+var_120], rax; __int64
0x180069dc5  lea     rdx, unk_1800CB2F0; int
0x180069dcc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180069dd1  jmp     loc_180069E7B
0x180069dd6  mov     [rbp+SRWLock], 0
0x180069dde  lea     rdx, [rbp+SRWLock]
0x180069de2  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069de7  mov     rax, [rbx+110h]
0x180069dee  mov     dword ptr [rax], 2
0x180069df4  mov     rcx, [rbp+SRWLock]; SRWLock
0x180069df8  test    rcx, rcx
0x180069dfb  jz      short loc_180069E03
0x180069dfd  call    cs:__imp_ReleaseSRWLockExclusive
0x180069e03  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180069e08  mov     rdi, [rax+8]
0x180069e0c  mov     eax, [rdi]
0x180069e0e  cmp     eax, 4
0x180069e11  jbe     short loc_180069E7B
0x180069e13  mov     rcx, [rdi+18h]
0x180069e17  mov     rax, [rdi+10h]
0x180069e1b  test    al, 2
0x180069e1d  jz      short loc_180069E7B
0x180069e1f  mov     rax, rcx
0x180069e22  and     eax, 2
0x180069e25  cmp     rax, rcx
0x180069e28  jnz     short loc_180069E7B
0x180069e2a  call    cs:__imp_GetCurrentThreadId
0x180069e30  mov     dword ptr [rbp+SRWLock], eax
0x180069e33  mov     r8, [rbx+110h]
0x180069e3a  mov     eax, [r8+48h]
0x180069e3e  mov     dword ptr [rbp+var_78], eax
0x180069e41  mov     [rbp+var_58], 0
0x180069e49  add     r8, 8
0x180069e4d  lea     rax, [rbp+SRWLock]
0x180069e51  mov     [rsp+140h+var_110], rax
0x180069e56  lea     rax, [rbp+var_78]
0x180069e5a  mov     [rsp+140h+var_118], rax
0x180069e5f  lea     rax, [rbp+var_58]
0x180069e63  mov     [rsp+140h+var_120], rax
0x180069e68  xor     r9d, r9d
0x180069e6b  lea     rdx, dword_1800CB43C
0x180069e72  mov     rcx, rdi
0x180069e75  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180069e7a  nop
0x180069e7b  lea     rcx, [rbx+120h]; this
0x180069e82  cmp     dword ptr [rcx+18h], 0
0x180069e86  jz      short loc_180069E8E
0x180069e88  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180069e8d  nop
0x180069e8e  lea     r11, [rsp+140h+var_s0]
0x180069e96  mov     rbx, [r11+18h]
0x180069e9a  mov     rdi, [r11+20h]
0x180069e9e  mov     rsp, r11
0x180069ea1  pop     rbp
0x180069ea2  retn
```
