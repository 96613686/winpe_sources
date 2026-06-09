# HyperVStorageTrace::HyperVFile_Reload::StopActivity(void)

- ea: `0x18006aa30`
- end: `0x18006ad03`
- name: `?StopActivity@HyperVFile_Reload@HyperVStorageTrace@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(HyperVStorageTrace::HyperVFile_Reload *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180066284`
- `0x18006aa30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006aa97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006ac5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006aa97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006ac5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006ac8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006ac8a`

## pseudocode

```c
void __fastcall HyperVStorageTrace::HyperVFile_Reload::StopActivity(HyperVStorageTrace::HyperVFile_Reload *this)
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
        (int)&unk_1800CB698,
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
        (unsigned int)&dword_1800CB7E4,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((HyperVStorageTrace::HyperVFile_Reload *)((char *)this + 288));
}

```

## disassembly

```asm
0x18006aa30  mov     [rsp-8+arg_8], rbx
0x18006aa35  mov     [rsp-8+arg_10], rdi
0x18006aa3a  push    rbp
0x18006aa3b  mov     rbp, rsp
0x18006aa3e  sub     rsp, 140h
0x18006aa45  mov     rbx, rcx
0x18006aa48  mov     rdi, [rcx+110h]
0x18006aa4f  mov     eax, [rdi+48h]
0x18006aa52  test    eax, eax
0x18006aa54  jns     loc_18006AC36
0x18006aa5a  add     rdi, 50h ; 'P'
0x18006aa5e  cmp     eax, [rdi+8]
0x18006aa61  jnz     loc_18006AC36
0x18006aa67  test    rdi, rdi
0x18006aa6a  jz      loc_18006AC36
0x18006aa70  mov     [rbp+SRWLock], 0
0x18006aa78  lea     rdx, [rbp+SRWLock]
0x18006aa7c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006aa81  mov     rax, [rbx+110h]
0x18006aa88  mov     dword ptr [rax], 2
0x18006aa8e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18006aa92  test    rcx, rcx
0x18006aa95  jz      short loc_18006AA9D
0x18006aa97  call    cs:__imp_ReleaseSRWLockExclusive
0x18006aa9d  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18006aaa2  mov     rcx, [rax+8]; int
0x18006aaa6  mov     eax, [rcx]
0x18006aaa8  cmp     eax, 4
0x18006aaab  jbe     loc_18006ACDB
0x18006aab1  mov     rdx, [rcx+18h]
0x18006aab5  mov     rax, [rcx+10h]
0x18006aab9  test    al, 2
0x18006aabb  jz      loc_18006ACDB
0x18006aac1  mov     rax, rdx
0x18006aac4  and     eax, 2
0x18006aac7  cmp     rax, rdx
0x18006aaca  jnz     loc_18006ACDB
0x18006aad0  mov     rax, [rdi+30h]
0x18006aad4  mov     [rbp+var_50], rax
0x18006aad8  mov     eax, [rdi+44h]
0x18006aadb  mov     dword ptr [rbp+var_78+4], eax
0x18006aade  mov     eax, [rdi+10h]
0x18006aae1  mov     dword ptr [rbp+var_70], eax
0x18006aae4  mov     rax, [rdi+78h]
0x18006aae8  mov     [rbp+var_48], rax
0x18006aaec  mov     rax, [rdi+70h]
0x18006aaf0  mov     [rbp+var_40], rax
0x18006aaf4  mov     eax, [rdi+68h]
0x18006aaf7  mov     dword ptr [rbp+var_70+4], eax
0x18006aafa  mov     rax, [rdi+60h]
0x18006aafe  mov     [rbp+var_38], rax
0x18006ab02  mov     rax, [rdi+58h]
0x18006ab06  mov     [rbp+var_30], rax
0x18006ab0a  mov     eax, [rdi+50h]
0x18006ab0d  mov     dword ptr [rbp+var_68], eax
0x18006ab10  mov     rax, [rdi+48h]
0x18006ab14  mov     [rbp+var_28], rax
0x18006ab18  mov     eax, [rdi+20h]
0x18006ab1b  mov     dword ptr [rbp+var_68+4], eax
0x18006ab1e  mov     rax, [rdi+18h]
0x18006ab22  mov     [rbp+var_20], rax
0x18006ab26  mov     eax, [rdi]
0x18006ab28  mov     [rbp+var_60], eax
0x18006ab2b  mov     rax, [rdi+80h]
0x18006ab32  mov     [rbp+var_18], rax
0x18006ab36  mov     eax, [rdi+40h]
0x18006ab39  mov     dword ptr [rbp+var_78], eax
0x18006ab3c  mov     rax, [rdi+38h]
0x18006ab40  mov     [rbp+var_10], rax
0x18006ab44  mov     eax, [rdi+8]
0x18006ab47  mov     dword ptr [rbp+SRWLock], eax
0x18006ab4a  mov     [rbp+var_8], 1000000h
0x18006ab52  mov     [rbp+var_58], 0
0x18006ab5a  mov     r8, [rbx+110h]
0x18006ab61  add     r8, 8; int
0x18006ab65  lea     rax, [rbp+var_50]
0x18006ab69  mov     [rsp+140h+var_90], rax; __int64
0x18006ab71  lea     rax, [rbp+var_78+4]
0x18006ab75  mov     [rsp+140h+var_98], rax; __int64
0x18006ab7d  lea     rax, [rbp+var_70]
0x18006ab81  mov     [rsp+140h+var_A0], rax; __int64
0x18006ab89  lea     rax, [rbp+var_48]
0x18006ab8d  mov     [rsp+140h+var_A8], rax; __int64
0x18006ab95  lea     rax, [rbp+var_40]
0x18006ab99  mov     [rsp+140h+var_B0], rax; __int64
0x18006aba1  lea     rax, [rbp+var_70+4]
0x18006aba5  mov     [rsp+140h+var_B8], rax; __int64
0x18006abad  lea     rax, [rbp+var_38]
0x18006abb1  mov     [rsp+140h+var_C0], rax; __int64
0x18006abb9  lea     rax, [rbp+var_30]
0x18006abbd  mov     [rsp+140h+var_C8], rax; __int64
0x18006abc2  lea     rax, [rbp+var_68]
0x18006abc6  mov     [rsp+140h+var_D0], rax; __int64
0x18006abcb  lea     rax, [rbp+var_28]
0x18006abcf  mov     [rsp+140h+var_D8], rax; __int64
0x18006abd4  lea     rax, [rbp+var_68+4]
0x18006abd8  mov     [rsp+140h+var_E0], rax; __int64
0x18006abdd  lea     rax, [rbp+var_20]
0x18006abe1  mov     [rsp+140h+var_E8], rax; __int64
0x18006abe6  lea     rax, [rbp+var_60]
0x18006abea  mov     [rsp+140h+var_F0], rax; __int64
0x18006abef  lea     rax, [rbp+var_18]
0x18006abf3  mov     [rsp+140h+var_F8], rax; __int64
0x18006abf8  lea     rax, [rbp+var_78]
0x18006abfc  mov     [rsp+140h+var_100], rax; __int64
0x18006ac01  lea     rax, [rbp+var_10]
0x18006ac05  mov     [rsp+140h+var_108], rax; __int64
0x18006ac0a  lea     rax, [rbp+SRWLock]
0x18006ac0e  mov     [rsp+140h+var_110], rax; __int64
0x18006ac13  lea     rax, [rbp+var_8]
0x18006ac17  mov     [rsp+140h+var_118], rax; __int64
0x18006ac1c  lea     rax, [rbp+var_58]
0x18006ac20  mov     [rsp+140h+var_120], rax; __int64
0x18006ac25  lea     rdx, unk_1800CB698; int
0x18006ac2c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006ac31  jmp     loc_18006ACDB
0x18006ac36  mov     [rbp+SRWLock], 0
0x18006ac3e  lea     rdx, [rbp+SRWLock]
0x18006ac42  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006ac47  mov     rax, [rbx+110h]
0x18006ac4e  mov     dword ptr [rax], 2
0x18006ac54  mov     rcx, [rbp+SRWLock]; SRWLock
0x18006ac58  test    rcx, rcx
0x18006ac5b  jz      short loc_18006AC63
0x18006ac5d  call    cs:__imp_ReleaseSRWLockExclusive
0x18006ac63  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18006ac68  mov     rdi, [rax+8]
0x18006ac6c  mov     eax, [rdi]
0x18006ac6e  cmp     eax, 4
0x18006ac71  jbe     short loc_18006ACDB
0x18006ac73  mov     rcx, [rdi+18h]
0x18006ac77  mov     rax, [rdi+10h]
0x18006ac7b  test    al, 2
0x18006ac7d  jz      short loc_18006ACDB
0x18006ac7f  mov     rax, rcx
0x18006ac82  and     eax, 2
0x18006ac85  cmp     rax, rcx
0x18006ac88  jnz     short loc_18006ACDB
0x18006ac8a  call    cs:__imp_GetCurrentThreadId
0x18006ac90  mov     dword ptr [rbp+SRWLock], eax
0x18006ac93  mov     r8, [rbx+110h]
0x18006ac9a  mov     eax, [r8+48h]
0x18006ac9e  mov     dword ptr [rbp+var_78], eax
0x18006aca1  mov     [rbp+var_58], 0
0x18006aca9  add     r8, 8
0x18006acad  lea     rax, [rbp+SRWLock]
0x18006acb1  mov     [rsp+140h+var_110], rax
0x18006acb6  lea     rax, [rbp+var_78]
0x18006acba  mov     [rsp+140h+var_118], rax
0x18006acbf  lea     rax, [rbp+var_58]
0x18006acc3  mov     [rsp+140h+var_120], rax
0x18006acc8  xor     r9d, r9d
0x18006accb  lea     rdx, dword_1800CB7E4
0x18006acd2  mov     rcx, rdi
0x18006acd5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006acda  nop
0x18006acdb  lea     rcx, [rbx+120h]; this
0x18006ace2  cmp     dword ptr [rcx+18h], 0
0x18006ace6  jz      short loc_18006ACEE
0x18006ace8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18006aced  nop
0x18006acee  lea     r11, [rsp+140h+var_s0]
0x18006acf6  mov     rbx, [r11+18h]
0x18006acfa  mov     rdi, [r11+20h]
0x18006acfe  mov     rsp, r11
0x18006ad01  pop     rbp
0x18006ad02  retn
```
