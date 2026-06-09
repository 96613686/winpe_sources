# ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmAccess::StopActivity(void)

- ea: `0x18003cb50`
- end: `0x18003ce26`
- name: `?StopActivity@VmFileUtilities_GrantVmAccess@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `726`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmAccess *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x18003cb50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cbb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cd80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cbb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cd80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cdad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cdad`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmAccess::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmAccess *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  int v15; // [rsp+D0h] [rbp-70h] BYREF
  int v16; // [rsp+D4h] [rbp-6Ch] BYREF
  int v17; // [rsp+D8h] [rbp-68h] BYREF
  int v18; // [rsp+DCh] [rbp-64h] BYREF
  int v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27; // [rsp+120h] [rbp-20h] BYREF
  __int64 v28; // [rsp+128h] [rbp-18h] BYREF
  __int64 v29; // [rsp+130h] [rbp-10h] BYREF
  __int64 v30; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x40) != 0 && (v7 & 0x40) == v7 )
      {
        v21 = *((_QWORD *)v4 + 6);
        v14 = v4[17];
        v15 = v4[4];
        v22 = *((_QWORD *)v4 + 15);
        v23 = *((_QWORD *)v4 + 14);
        v16 = v4[26];
        v24 = *((_QWORD *)v4 + 12);
        v25 = *((_QWORD *)v4 + 11);
        v17 = v4[20];
        v26 = *((_QWORD *)v4 + 9);
        v18 = v4[8];
        v27 = *((_QWORD *)v4 + 3);
        v19 = *v4;
        v28 = *((_QWORD *)v4 + 16);
        v13 = v4[16];
        v29 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (int)v6,
          (int)&word_1800C72F2,
          *((_QWORD *)this + 34) + 8,
          (__int64)&v20,
          (__int64)&v30,
          (__int64)&SRWLock,
          (__int64)&v29,
          (__int64)&v13,
          (__int64)&v28,
          (__int64)&v19,
          (__int64)&v27,
          (__int64)&v18,
          (__int64)&v26,
          (__int64)&v17,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v16,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v21);
      }
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x40) != 0 && (v10 & 0x40) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)byte_1800C6EB1,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmAccess *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003cb50  mov     [rsp-8+arg_8], rbx
0x18003cb55  mov     [rsp-8+arg_10], rdi
0x18003cb5a  push    rbp
0x18003cb5b  mov     rbp, rsp
0x18003cb5e  sub     rsp, 140h
0x18003cb65  mov     rbx, rcx
0x18003cb68  mov     rdi, [rcx+110h]
0x18003cb6f  mov     eax, [rdi+48h]
0x18003cb72  test    eax, eax
0x18003cb74  jns     loc_18003CD59
0x18003cb7a  add     rdi, 50h ; 'P'
0x18003cb7e  cmp     eax, [rdi+8]
0x18003cb81  jnz     loc_18003CD59
0x18003cb87  test    rdi, rdi
0x18003cb8a  jz      loc_18003CD59
0x18003cb90  mov     [rbp+SRWLock], 0
0x18003cb98  lea     rdx, [rbp+SRWLock]
0x18003cb9c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003cba1  mov     rax, [rbx+110h]
0x18003cba8  mov     dword ptr [rax], 2
0x18003cbae  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003cbb2  test    rcx, rcx
0x18003cbb5  jz      short loc_18003CBBD
0x18003cbb7  call    cs:__imp_ReleaseSRWLockExclusive
0x18003cbbd  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003cbc2  mov     r9, rax
0x18003cbc5  mov     ecx, [rax]
0x18003cbc7  cmp     ecx, 4
0x18003cbca  jbe     loc_18003CDFE
0x18003cbd0  mov     rax, [rax+18h]
0x18003cbd4  mov     rcx, [r9+10h]
0x18003cbd8  test    cl, 40h
0x18003cbdb  jz      loc_18003CDFE
0x18003cbe1  mov     rcx, rax
0x18003cbe4  and     ecx, 40h
0x18003cbe7  cmp     rcx, rax
0x18003cbea  jnz     loc_18003CDFE
0x18003cbf0  mov     rax, [rdi+30h]
0x18003cbf4  mov     [rbp+var_50], rax
0x18003cbf8  mov     eax, [rdi+44h]
0x18003cbfb  mov     dword ptr [rbp+var_78+4], eax
0x18003cbfe  mov     eax, [rdi+10h]
0x18003cc01  mov     dword ptr [rbp+var_70], eax
0x18003cc04  mov     rax, [rdi+78h]
0x18003cc08  mov     [rbp+var_48], rax
0x18003cc0c  mov     rax, [rdi+70h]
0x18003cc10  mov     [rbp+var_40], rax
0x18003cc14  mov     eax, [rdi+68h]
0x18003cc17  mov     dword ptr [rbp+var_70+4], eax
0x18003cc1a  mov     rax, [rdi+60h]
0x18003cc1e  mov     [rbp+var_38], rax
0x18003cc22  mov     rax, [rdi+58h]
0x18003cc26  mov     [rbp+var_30], rax
0x18003cc2a  mov     eax, [rdi+50h]
0x18003cc2d  mov     dword ptr [rbp+var_68], eax
0x18003cc30  mov     rax, [rdi+48h]
0x18003cc34  mov     [rbp+var_28], rax
0x18003cc38  mov     eax, [rdi+20h]
0x18003cc3b  mov     dword ptr [rbp+var_68+4], eax
0x18003cc3e  mov     rax, [rdi+18h]
0x18003cc42  mov     [rbp+var_20], rax
0x18003cc46  mov     eax, [rdi]
0x18003cc48  mov     [rbp+var_60], eax
0x18003cc4b  mov     rax, [rdi+80h]
0x18003cc52  mov     [rbp+var_18], rax
0x18003cc56  mov     eax, [rdi+40h]
0x18003cc59  mov     dword ptr [rbp+var_78], eax
0x18003cc5c  mov     rax, [rdi+38h]
0x18003cc60  mov     [rbp+var_10], rax
0x18003cc64  mov     eax, [rdi+8]
0x18003cc67  mov     dword ptr [rbp+SRWLock], eax
0x18003cc6a  mov     [rbp+var_8], 1000000h
0x18003cc72  mov     [rbp+var_58], 0
0x18003cc7a  mov     r8, [rbx+110h]
0x18003cc81  add     r8, 8; int
0x18003cc85  lea     rax, [rbp+var_50]
0x18003cc89  mov     [rsp+140h+var_90], rax; __int64
0x18003cc91  lea     rax, [rbp+var_78+4]
0x18003cc95  mov     [rsp+140h+var_98], rax; __int64
0x18003cc9d  lea     rax, [rbp+var_70]
0x18003cca1  mov     [rsp+140h+var_A0], rax; __int64
0x18003cca9  lea     rax, [rbp+var_48]
0x18003ccad  mov     [rsp+140h+var_A8], rax; __int64
0x18003ccb5  lea     rax, [rbp+var_40]
0x18003ccb9  mov     [rsp+140h+var_B0], rax; __int64
0x18003ccc1  lea     rax, [rbp+var_70+4]
0x18003ccc5  mov     [rsp+140h+var_B8], rax; __int64
0x18003cccd  lea     rax, [rbp+var_38]
0x18003ccd1  mov     [rsp+140h+var_C0], rax; __int64
0x18003ccd9  lea     rax, [rbp+var_30]
0x18003ccdd  mov     [rsp+140h+var_C8], rax; __int64
0x18003cce2  lea     rax, [rbp+var_68]
0x18003cce6  mov     [rsp+140h+var_D0], rax; __int64
0x18003cceb  lea     rax, [rbp+var_28]
0x18003ccef  mov     [rsp+140h+var_D8], rax; __int64
0x18003ccf4  lea     rax, [rbp+var_68+4]
0x18003ccf8  mov     [rsp+140h+var_E0], rax; __int64
0x18003ccfd  lea     rax, [rbp+var_20]
0x18003cd01  mov     [rsp+140h+var_E8], rax; __int64
0x18003cd06  lea     rax, [rbp+var_60]
0x18003cd0a  mov     [rsp+140h+var_F0], rax; __int64
0x18003cd0f  lea     rax, [rbp+var_18]
0x18003cd13  mov     [rsp+140h+var_F8], rax; __int64
0x18003cd18  lea     rax, [rbp+var_78]
0x18003cd1c  mov     [rsp+140h+var_100], rax; __int64
0x18003cd21  lea     rax, [rbp+var_10]
0x18003cd25  mov     [rsp+140h+var_108], rax; __int64
0x18003cd2a  lea     rax, [rbp+SRWLock]
0x18003cd2e  mov     [rsp+140h+var_110], rax; __int64
0x18003cd33  lea     rax, [rbp+var_8]
0x18003cd37  mov     [rsp+140h+var_118], rax; __int64
0x18003cd3c  lea     rax, [rbp+var_58]
0x18003cd40  mov     [rsp+140h+var_120], rax; __int64
0x18003cd45  lea     rdx, word_1800C72F2; int
0x18003cd4c  mov     rcx, r9; int
0x18003cd4f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003cd54  jmp     loc_18003CDFE
0x18003cd59  mov     [rbp+SRWLock], 0
0x18003cd61  lea     rdx, [rbp+SRWLock]
0x18003cd65  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003cd6a  mov     rax, [rbx+110h]
0x18003cd71  mov     dword ptr [rax], 2
0x18003cd77  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003cd7b  test    rcx, rcx
0x18003cd7e  jz      short loc_18003CD86
0x18003cd80  call    cs:__imp_ReleaseSRWLockExclusive
0x18003cd86  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003cd8b  mov     rdi, rax
0x18003cd8e  mov     ecx, [rax]
0x18003cd90  cmp     ecx, 4
0x18003cd93  jbe     short loc_18003CDFE
0x18003cd95  mov     rax, [rax+18h]
0x18003cd99  mov     rcx, [rdi+10h]
0x18003cd9d  test    cl, 40h
0x18003cda0  jz      short loc_18003CDFE
0x18003cda2  mov     rcx, rax
0x18003cda5  and     ecx, 40h
0x18003cda8  cmp     rcx, rax
0x18003cdab  jnz     short loc_18003CDFE
0x18003cdad  call    cs:__imp_GetCurrentThreadId
0x18003cdb3  mov     dword ptr [rbp+SRWLock], eax
0x18003cdb6  mov     r8, [rbx+110h]
0x18003cdbd  mov     eax, [r8+48h]
0x18003cdc1  mov     dword ptr [rbp+var_78], eax
0x18003cdc4  mov     [rbp+var_58], 0
0x18003cdcc  add     r8, 8
0x18003cdd0  lea     rax, [rbp+SRWLock]
0x18003cdd4  mov     [rsp+140h+var_110], rax
0x18003cdd9  lea     rax, [rbp+var_78]
0x18003cddd  mov     [rsp+140h+var_118], rax
0x18003cde2  lea     rax, [rbp+var_58]
0x18003cde6  mov     [rsp+140h+var_120], rax
0x18003cdeb  xor     r9d, r9d
0x18003cdee  lea     rdx, byte_1800C6EB1
0x18003cdf5  mov     rcx, rdi
0x18003cdf8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003cdfd  nop
0x18003cdfe  lea     rcx, [rbx+120h]; this
0x18003ce05  cmp     dword ptr [rcx+18h], 0
0x18003ce09  jz      short loc_18003CE11
0x18003ce0b  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003ce10  nop
0x18003ce11  lea     r11, [rsp+140h+var_s0]
0x18003ce19  mov     rbx, [r11+18h]
0x18003ce1d  mov     rdi, [r11+20h]
0x18003ce21  mov     rsp, r11
0x18003ce24  pop     rbp
0x18003ce25  retn
```
