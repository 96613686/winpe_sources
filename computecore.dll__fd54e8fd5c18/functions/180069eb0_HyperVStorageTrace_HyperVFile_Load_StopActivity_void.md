# HyperVStorageTrace::HyperVFile_Load::StopActivity(void)

- ea: `0x180069eb0`
- end: `0x18006a183`
- name: `?StopActivity@HyperVFile_Load@HyperVStorageTrace@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(HyperVStorageTrace::HyperVFile_Load *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180066284`
- `0x180069eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069f17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a0dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069f17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a0dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a10a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a10a`

## pseudocode

```c
void __fastcall HyperVStorageTrace::HyperVFile_Load::StopActivity(HyperVStorageTrace::HyperVFile_Load *this)
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
        (int)&word_1800CB836,
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
        (unsigned int)qword_1800CB980,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((HyperVStorageTrace::HyperVFile_Load *)((char *)this + 288));
}

```

## disassembly

```asm
0x180069eb0  mov     [rsp-8+arg_8], rbx
0x180069eb5  mov     [rsp-8+arg_10], rdi
0x180069eba  push    rbp
0x180069ebb  mov     rbp, rsp
0x180069ebe  sub     rsp, 140h
0x180069ec5  mov     rbx, rcx
0x180069ec8  mov     rdi, [rcx+110h]
0x180069ecf  mov     eax, [rdi+48h]
0x180069ed2  test    eax, eax
0x180069ed4  jns     loc_18006A0B6
0x180069eda  add     rdi, 50h ; 'P'
0x180069ede  cmp     eax, [rdi+8]
0x180069ee1  jnz     loc_18006A0B6
0x180069ee7  test    rdi, rdi
0x180069eea  jz      loc_18006A0B6
0x180069ef0  mov     [rbp+SRWLock], 0
0x180069ef8  lea     rdx, [rbp+SRWLock]
0x180069efc  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069f01  mov     rax, [rbx+110h]
0x180069f08  mov     dword ptr [rax], 2
0x180069f0e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180069f12  test    rcx, rcx
0x180069f15  jz      short loc_180069F1D
0x180069f17  call    cs:__imp_ReleaseSRWLockExclusive
0x180069f1d  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180069f22  mov     rcx, [rax+8]; int
0x180069f26  mov     eax, [rcx]
0x180069f28  cmp     eax, 4
0x180069f2b  jbe     loc_18006A15B
0x180069f31  mov     rdx, [rcx+18h]
0x180069f35  mov     rax, [rcx+10h]
0x180069f39  test    al, 2
0x180069f3b  jz      loc_18006A15B
0x180069f41  mov     rax, rdx
0x180069f44  and     eax, 2
0x180069f47  cmp     rax, rdx
0x180069f4a  jnz     loc_18006A15B
0x180069f50  mov     rax, [rdi+30h]
0x180069f54  mov     [rbp+var_50], rax
0x180069f58  mov     eax, [rdi+44h]
0x180069f5b  mov     dword ptr [rbp+var_78+4], eax
0x180069f5e  mov     eax, [rdi+10h]
0x180069f61  mov     dword ptr [rbp+var_70], eax
0x180069f64  mov     rax, [rdi+78h]
0x180069f68  mov     [rbp+var_48], rax
0x180069f6c  mov     rax, [rdi+70h]
0x180069f70  mov     [rbp+var_40], rax
0x180069f74  mov     eax, [rdi+68h]
0x180069f77  mov     dword ptr [rbp+var_70+4], eax
0x180069f7a  mov     rax, [rdi+60h]
0x180069f7e  mov     [rbp+var_38], rax
0x180069f82  mov     rax, [rdi+58h]
0x180069f86  mov     [rbp+var_30], rax
0x180069f8a  mov     eax, [rdi+50h]
0x180069f8d  mov     dword ptr [rbp+var_68], eax
0x180069f90  mov     rax, [rdi+48h]
0x180069f94  mov     [rbp+var_28], rax
0x180069f98  mov     eax, [rdi+20h]
0x180069f9b  mov     dword ptr [rbp+var_68+4], eax
0x180069f9e  mov     rax, [rdi+18h]
0x180069fa2  mov     [rbp+var_20], rax
0x180069fa6  mov     eax, [rdi]
0x180069fa8  mov     [rbp+var_60], eax
0x180069fab  mov     rax, [rdi+80h]
0x180069fb2  mov     [rbp+var_18], rax
0x180069fb6  mov     eax, [rdi+40h]
0x180069fb9  mov     dword ptr [rbp+var_78], eax
0x180069fbc  mov     rax, [rdi+38h]
0x180069fc0  mov     [rbp+var_10], rax
0x180069fc4  mov     eax, [rdi+8]
0x180069fc7  mov     dword ptr [rbp+SRWLock], eax
0x180069fca  mov     [rbp+var_8], 1000000h
0x180069fd2  mov     [rbp+var_58], 0
0x180069fda  mov     r8, [rbx+110h]
0x180069fe1  add     r8, 8; int
0x180069fe5  lea     rax, [rbp+var_50]
0x180069fe9  mov     [rsp+140h+var_90], rax; __int64
0x180069ff1  lea     rax, [rbp+var_78+4]
0x180069ff5  mov     [rsp+140h+var_98], rax; __int64
0x180069ffd  lea     rax, [rbp+var_70]
0x18006a001  mov     [rsp+140h+var_A0], rax; __int64
0x18006a009  lea     rax, [rbp+var_48]
0x18006a00d  mov     [rsp+140h+var_A8], rax; __int64
0x18006a015  lea     rax, [rbp+var_40]
0x18006a019  mov     [rsp+140h+var_B0], rax; __int64
0x18006a021  lea     rax, [rbp+var_70+4]
0x18006a025  mov     [rsp+140h+var_B8], rax; __int64
0x18006a02d  lea     rax, [rbp+var_38]
0x18006a031  mov     [rsp+140h+var_C0], rax; __int64
0x18006a039  lea     rax, [rbp+var_30]
0x18006a03d  mov     [rsp+140h+var_C8], rax; __int64
0x18006a042  lea     rax, [rbp+var_68]
0x18006a046  mov     [rsp+140h+var_D0], rax; __int64
0x18006a04b  lea     rax, [rbp+var_28]
0x18006a04f  mov     [rsp+140h+var_D8], rax; __int64
0x18006a054  lea     rax, [rbp+var_68+4]
0x18006a058  mov     [rsp+140h+var_E0], rax; __int64
0x18006a05d  lea     rax, [rbp+var_20]
0x18006a061  mov     [rsp+140h+var_E8], rax; __int64
0x18006a066  lea     rax, [rbp+var_60]
0x18006a06a  mov     [rsp+140h+var_F0], rax; __int64
0x18006a06f  lea     rax, [rbp+var_18]
0x18006a073  mov     [rsp+140h+var_F8], rax; __int64
0x18006a078  lea     rax, [rbp+var_78]
0x18006a07c  mov     [rsp+140h+var_100], rax; __int64
0x18006a081  lea     rax, [rbp+var_10]
0x18006a085  mov     [rsp+140h+var_108], rax; __int64
0x18006a08a  lea     rax, [rbp+SRWLock]
0x18006a08e  mov     [rsp+140h+var_110], rax; __int64
0x18006a093  lea     rax, [rbp+var_8]
0x18006a097  mov     [rsp+140h+var_118], rax; __int64
0x18006a09c  lea     rax, [rbp+var_58]
0x18006a0a0  mov     [rsp+140h+var_120], rax; __int64
0x18006a0a5  lea     rdx, word_1800CB836; int
0x18006a0ac  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006a0b1  jmp     loc_18006A15B
0x18006a0b6  mov     [rbp+SRWLock], 0
0x18006a0be  lea     rdx, [rbp+SRWLock]
0x18006a0c2  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006a0c7  mov     rax, [rbx+110h]
0x18006a0ce  mov     dword ptr [rax], 2
0x18006a0d4  mov     rcx, [rbp+SRWLock]; SRWLock
0x18006a0d8  test    rcx, rcx
0x18006a0db  jz      short loc_18006A0E3
0x18006a0dd  call    cs:__imp_ReleaseSRWLockExclusive
0x18006a0e3  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18006a0e8  mov     rdi, [rax+8]
0x18006a0ec  mov     eax, [rdi]
0x18006a0ee  cmp     eax, 4
0x18006a0f1  jbe     short loc_18006A15B
0x18006a0f3  mov     rcx, [rdi+18h]
0x18006a0f7  mov     rax, [rdi+10h]
0x18006a0fb  test    al, 2
0x18006a0fd  jz      short loc_18006A15B
0x18006a0ff  mov     rax, rcx
0x18006a102  and     eax, 2
0x18006a105  cmp     rax, rcx
0x18006a108  jnz     short loc_18006A15B
0x18006a10a  call    cs:__imp_GetCurrentThreadId
0x18006a110  mov     dword ptr [rbp+SRWLock], eax
0x18006a113  mov     r8, [rbx+110h]
0x18006a11a  mov     eax, [r8+48h]
0x18006a11e  mov     dword ptr [rbp+var_78], eax
0x18006a121  mov     [rbp+var_58], 0
0x18006a129  add     r8, 8
0x18006a12d  lea     rax, [rbp+SRWLock]
0x18006a131  mov     [rsp+140h+var_110], rax
0x18006a136  lea     rax, [rbp+var_78]
0x18006a13a  mov     [rsp+140h+var_118], rax
0x18006a13f  lea     rax, [rbp+var_58]
0x18006a143  mov     [rsp+140h+var_120], rax
0x18006a148  xor     r9d, r9d
0x18006a14b  lea     rdx, qword_1800CB980
0x18006a152  mov     rcx, rdi
0x18006a155  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006a15a  nop
0x18006a15b  lea     rcx, [rbx+120h]; this
0x18006a162  cmp     dword ptr [rcx+18h], 0
0x18006a166  jz      short loc_18006A16E
0x18006a168  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18006a16d  nop
0x18006a16e  lea     r11, [rsp+140h+var_s0]
0x18006a176  mov     rbx, [r11+18h]
0x18006a17a  mov     rdi, [r11+20h]
0x18006a17e  mov     rsp, r11
0x18006a181  pop     rbp
0x18006a182  retn
```
