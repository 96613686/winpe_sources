# HyperVStorageTrace::HyperVFile_Unlock::StopActivity(void)

- ea: `0x18006aff0`
- end: `0x18006b2c3`
- name: `?StopActivity@HyperVFile_Unlock@HyperVStorageTrace@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(HyperVStorageTrace::HyperVFile_Unlock *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180066284`
- `0x18006aff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b057`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b21d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b057`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b21d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b24a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b24a`

## pseudocode

```c
void __fastcall HyperVStorageTrace::HyperVFile_Unlock::StopActivity(HyperVStorageTrace::HyperVFile_Unlock *this)
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
        (int)&dword_1800CAF04,
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
        (unsigned int)word_1800CAEB2,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((HyperVStorageTrace::HyperVFile_Unlock *)((char *)this + 288));
}

```

## disassembly

```asm
0x18006aff0  mov     [rsp-8+arg_8], rbx
0x18006aff5  mov     [rsp-8+arg_10], rdi
0x18006affa  push    rbp
0x18006affb  mov     rbp, rsp
0x18006affe  sub     rsp, 140h
0x18006b005  mov     rbx, rcx
0x18006b008  mov     rdi, [rcx+110h]
0x18006b00f  mov     eax, [rdi+48h]
0x18006b012  test    eax, eax
0x18006b014  jns     loc_18006B1F6
0x18006b01a  add     rdi, 50h ; 'P'
0x18006b01e  cmp     eax, [rdi+8]
0x18006b021  jnz     loc_18006B1F6
0x18006b027  test    rdi, rdi
0x18006b02a  jz      loc_18006B1F6
0x18006b030  mov     [rbp+SRWLock], 0
0x18006b038  lea     rdx, [rbp+SRWLock]
0x18006b03c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006b041  mov     rax, [rbx+110h]
0x18006b048  mov     dword ptr [rax], 2
0x18006b04e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18006b052  test    rcx, rcx
0x18006b055  jz      short loc_18006B05D
0x18006b057  call    cs:__imp_ReleaseSRWLockExclusive
0x18006b05d  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18006b062  mov     rcx, [rax+8]; int
0x18006b066  mov     eax, [rcx]
0x18006b068  cmp     eax, 4
0x18006b06b  jbe     loc_18006B29B
0x18006b071  mov     rdx, [rcx+18h]
0x18006b075  mov     rax, [rcx+10h]
0x18006b079  test    al, 2
0x18006b07b  jz      loc_18006B29B
0x18006b081  mov     rax, rdx
0x18006b084  and     eax, 2
0x18006b087  cmp     rax, rdx
0x18006b08a  jnz     loc_18006B29B
0x18006b090  mov     rax, [rdi+30h]
0x18006b094  mov     [rbp+var_50], rax
0x18006b098  mov     eax, [rdi+44h]
0x18006b09b  mov     dword ptr [rbp+var_78+4], eax
0x18006b09e  mov     eax, [rdi+10h]
0x18006b0a1  mov     dword ptr [rbp+var_70], eax
0x18006b0a4  mov     rax, [rdi+78h]
0x18006b0a8  mov     [rbp+var_48], rax
0x18006b0ac  mov     rax, [rdi+70h]
0x18006b0b0  mov     [rbp+var_40], rax
0x18006b0b4  mov     eax, [rdi+68h]
0x18006b0b7  mov     dword ptr [rbp+var_70+4], eax
0x18006b0ba  mov     rax, [rdi+60h]
0x18006b0be  mov     [rbp+var_38], rax
0x18006b0c2  mov     rax, [rdi+58h]
0x18006b0c6  mov     [rbp+var_30], rax
0x18006b0ca  mov     eax, [rdi+50h]
0x18006b0cd  mov     dword ptr [rbp+var_68], eax
0x18006b0d0  mov     rax, [rdi+48h]
0x18006b0d4  mov     [rbp+var_28], rax
0x18006b0d8  mov     eax, [rdi+20h]
0x18006b0db  mov     dword ptr [rbp+var_68+4], eax
0x18006b0de  mov     rax, [rdi+18h]
0x18006b0e2  mov     [rbp+var_20], rax
0x18006b0e6  mov     eax, [rdi]
0x18006b0e8  mov     [rbp+var_60], eax
0x18006b0eb  mov     rax, [rdi+80h]
0x18006b0f2  mov     [rbp+var_18], rax
0x18006b0f6  mov     eax, [rdi+40h]
0x18006b0f9  mov     dword ptr [rbp+var_78], eax
0x18006b0fc  mov     rax, [rdi+38h]
0x18006b100  mov     [rbp+var_10], rax
0x18006b104  mov     eax, [rdi+8]
0x18006b107  mov     dword ptr [rbp+SRWLock], eax
0x18006b10a  mov     [rbp+var_8], 1000000h
0x18006b112  mov     [rbp+var_58], 0
0x18006b11a  mov     r8, [rbx+110h]
0x18006b121  add     r8, 8; int
0x18006b125  lea     rax, [rbp+var_50]
0x18006b129  mov     [rsp+140h+var_90], rax; __int64
0x18006b131  lea     rax, [rbp+var_78+4]
0x18006b135  mov     [rsp+140h+var_98], rax; __int64
0x18006b13d  lea     rax, [rbp+var_70]
0x18006b141  mov     [rsp+140h+var_A0], rax; __int64
0x18006b149  lea     rax, [rbp+var_48]
0x18006b14d  mov     [rsp+140h+var_A8], rax; __int64
0x18006b155  lea     rax, [rbp+var_40]
0x18006b159  mov     [rsp+140h+var_B0], rax; __int64
0x18006b161  lea     rax, [rbp+var_70+4]
0x18006b165  mov     [rsp+140h+var_B8], rax; __int64
0x18006b16d  lea     rax, [rbp+var_38]
0x18006b171  mov     [rsp+140h+var_C0], rax; __int64
0x18006b179  lea     rax, [rbp+var_30]
0x18006b17d  mov     [rsp+140h+var_C8], rax; __int64
0x18006b182  lea     rax, [rbp+var_68]
0x18006b186  mov     [rsp+140h+var_D0], rax; __int64
0x18006b18b  lea     rax, [rbp+var_28]
0x18006b18f  mov     [rsp+140h+var_D8], rax; __int64
0x18006b194  lea     rax, [rbp+var_68+4]
0x18006b198  mov     [rsp+140h+var_E0], rax; __int64
0x18006b19d  lea     rax, [rbp+var_20]
0x18006b1a1  mov     [rsp+140h+var_E8], rax; __int64
0x18006b1a6  lea     rax, [rbp+var_60]
0x18006b1aa  mov     [rsp+140h+var_F0], rax; __int64
0x18006b1af  lea     rax, [rbp+var_18]
0x18006b1b3  mov     [rsp+140h+var_F8], rax; __int64
0x18006b1b8  lea     rax, [rbp+var_78]
0x18006b1bc  mov     [rsp+140h+var_100], rax; __int64
0x18006b1c1  lea     rax, [rbp+var_10]
0x18006b1c5  mov     [rsp+140h+var_108], rax; __int64
0x18006b1ca  lea     rax, [rbp+SRWLock]
0x18006b1ce  mov     [rsp+140h+var_110], rax; __int64
0x18006b1d3  lea     rax, [rbp+var_8]
0x18006b1d7  mov     [rsp+140h+var_118], rax; __int64
0x18006b1dc  lea     rax, [rbp+var_58]
0x18006b1e0  mov     [rsp+140h+var_120], rax; __int64
0x18006b1e5  lea     rdx, dword_1800CAF04; int
0x18006b1ec  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006b1f1  jmp     loc_18006B29B
0x18006b1f6  mov     [rbp+SRWLock], 0
0x18006b1fe  lea     rdx, [rbp+SRWLock]
0x18006b202  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006b207  mov     rax, [rbx+110h]
0x18006b20e  mov     dword ptr [rax], 2
0x18006b214  mov     rcx, [rbp+SRWLock]; SRWLock
0x18006b218  test    rcx, rcx
0x18006b21b  jz      short loc_18006B223
0x18006b21d  call    cs:__imp_ReleaseSRWLockExclusive
0x18006b223  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18006b228  mov     rdi, [rax+8]
0x18006b22c  mov     eax, [rdi]
0x18006b22e  cmp     eax, 4
0x18006b231  jbe     short loc_18006B29B
0x18006b233  mov     rcx, [rdi+18h]
0x18006b237  mov     rax, [rdi+10h]
0x18006b23b  test    al, 2
0x18006b23d  jz      short loc_18006B29B
0x18006b23f  mov     rax, rcx
0x18006b242  and     eax, 2
0x18006b245  cmp     rax, rcx
0x18006b248  jnz     short loc_18006B29B
0x18006b24a  call    cs:__imp_GetCurrentThreadId
0x18006b250  mov     dword ptr [rbp+SRWLock], eax
0x18006b253  mov     r8, [rbx+110h]
0x18006b25a  mov     eax, [r8+48h]
0x18006b25e  mov     dword ptr [rbp+var_78], eax
0x18006b261  mov     [rbp+var_58], 0
0x18006b269  add     r8, 8
0x18006b26d  lea     rax, [rbp+SRWLock]
0x18006b271  mov     [rsp+140h+var_110], rax
0x18006b276  lea     rax, [rbp+var_78]
0x18006b27a  mov     [rsp+140h+var_118], rax
0x18006b27f  lea     rax, [rbp+var_58]
0x18006b283  mov     [rsp+140h+var_120], rax
0x18006b288  xor     r9d, r9d
0x18006b28b  lea     rdx, word_1800CAEB2
0x18006b292  mov     rcx, rdi
0x18006b295  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006b29a  nop
0x18006b29b  lea     rcx, [rbx+120h]; this
0x18006b2a2  cmp     dword ptr [rcx+18h], 0
0x18006b2a6  jz      short loc_18006B2AE
0x18006b2a8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18006b2ad  nop
0x18006b2ae  lea     r11, [rsp+140h+var_s0]
0x18006b2b6  mov     rbx, [r11+18h]
0x18006b2ba  mov     rdi, [r11+20h]
0x18006b2be  mov     rsp, r11
0x18006b2c1  pop     rbp
0x18006b2c2  retn
```
