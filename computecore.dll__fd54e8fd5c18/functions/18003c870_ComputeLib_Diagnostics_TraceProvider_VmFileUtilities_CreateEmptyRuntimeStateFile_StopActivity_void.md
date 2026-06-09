# ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile::StopActivity(void)

- ea: `0x18003c870`
- end: `0x18003cb46`
- name: `?StopActivity@VmFileUtilities_CreateEmptyRuntimeStateFile@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `726`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x18003c870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c8d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003caa0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c8d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003caa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cacd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cacd`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile *this)
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
          (int)&byte_1800C6C89,
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
          (unsigned int)word_1800C6BBA,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003c870  mov     [rsp-8+arg_8], rbx
0x18003c875  mov     [rsp-8+arg_10], rdi
0x18003c87a  push    rbp
0x18003c87b  mov     rbp, rsp
0x18003c87e  sub     rsp, 140h
0x18003c885  mov     rbx, rcx
0x18003c888  mov     rdi, [rcx+110h]
0x18003c88f  mov     eax, [rdi+48h]
0x18003c892  test    eax, eax
0x18003c894  jns     loc_18003CA79
0x18003c89a  add     rdi, 50h ; 'P'
0x18003c89e  cmp     eax, [rdi+8]
0x18003c8a1  jnz     loc_18003CA79
0x18003c8a7  test    rdi, rdi
0x18003c8aa  jz      loc_18003CA79
0x18003c8b0  mov     [rbp+SRWLock], 0
0x18003c8b8  lea     rdx, [rbp+SRWLock]
0x18003c8bc  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003c8c1  mov     rax, [rbx+110h]
0x18003c8c8  mov     dword ptr [rax], 2
0x18003c8ce  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003c8d2  test    rcx, rcx
0x18003c8d5  jz      short loc_18003C8DD
0x18003c8d7  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c8dd  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003c8e2  mov     r9, rax
0x18003c8e5  mov     ecx, [rax]
0x18003c8e7  cmp     ecx, 4
0x18003c8ea  jbe     loc_18003CB1E
0x18003c8f0  mov     rax, [rax+18h]
0x18003c8f4  mov     rcx, [r9+10h]
0x18003c8f8  test    cl, 40h
0x18003c8fb  jz      loc_18003CB1E
0x18003c901  mov     rcx, rax
0x18003c904  and     ecx, 40h
0x18003c907  cmp     rcx, rax
0x18003c90a  jnz     loc_18003CB1E
0x18003c910  mov     rax, [rdi+30h]
0x18003c914  mov     [rbp+var_50], rax
0x18003c918  mov     eax, [rdi+44h]
0x18003c91b  mov     dword ptr [rbp+var_78+4], eax
0x18003c91e  mov     eax, [rdi+10h]
0x18003c921  mov     dword ptr [rbp+var_70], eax
0x18003c924  mov     rax, [rdi+78h]
0x18003c928  mov     [rbp+var_48], rax
0x18003c92c  mov     rax, [rdi+70h]
0x18003c930  mov     [rbp+var_40], rax
0x18003c934  mov     eax, [rdi+68h]
0x18003c937  mov     dword ptr [rbp+var_70+4], eax
0x18003c93a  mov     rax, [rdi+60h]
0x18003c93e  mov     [rbp+var_38], rax
0x18003c942  mov     rax, [rdi+58h]
0x18003c946  mov     [rbp+var_30], rax
0x18003c94a  mov     eax, [rdi+50h]
0x18003c94d  mov     dword ptr [rbp+var_68], eax
0x18003c950  mov     rax, [rdi+48h]
0x18003c954  mov     [rbp+var_28], rax
0x18003c958  mov     eax, [rdi+20h]
0x18003c95b  mov     dword ptr [rbp+var_68+4], eax
0x18003c95e  mov     rax, [rdi+18h]
0x18003c962  mov     [rbp+var_20], rax
0x18003c966  mov     eax, [rdi]
0x18003c968  mov     [rbp+var_60], eax
0x18003c96b  mov     rax, [rdi+80h]
0x18003c972  mov     [rbp+var_18], rax
0x18003c976  mov     eax, [rdi+40h]
0x18003c979  mov     dword ptr [rbp+var_78], eax
0x18003c97c  mov     rax, [rdi+38h]
0x18003c980  mov     [rbp+var_10], rax
0x18003c984  mov     eax, [rdi+8]
0x18003c987  mov     dword ptr [rbp+SRWLock], eax
0x18003c98a  mov     [rbp+var_8], 1000000h
0x18003c992  mov     [rbp+var_58], 0
0x18003c99a  mov     r8, [rbx+110h]
0x18003c9a1  add     r8, 8; int
0x18003c9a5  lea     rax, [rbp+var_50]
0x18003c9a9  mov     [rsp+140h+var_90], rax; __int64
0x18003c9b1  lea     rax, [rbp+var_78+4]
0x18003c9b5  mov     [rsp+140h+var_98], rax; __int64
0x18003c9bd  lea     rax, [rbp+var_70]
0x18003c9c1  mov     [rsp+140h+var_A0], rax; __int64
0x18003c9c9  lea     rax, [rbp+var_48]
0x18003c9cd  mov     [rsp+140h+var_A8], rax; __int64
0x18003c9d5  lea     rax, [rbp+var_40]
0x18003c9d9  mov     [rsp+140h+var_B0], rax; __int64
0x18003c9e1  lea     rax, [rbp+var_70+4]
0x18003c9e5  mov     [rsp+140h+var_B8], rax; __int64
0x18003c9ed  lea     rax, [rbp+var_38]
0x18003c9f1  mov     [rsp+140h+var_C0], rax; __int64
0x18003c9f9  lea     rax, [rbp+var_30]
0x18003c9fd  mov     [rsp+140h+var_C8], rax; __int64
0x18003ca02  lea     rax, [rbp+var_68]
0x18003ca06  mov     [rsp+140h+var_D0], rax; __int64
0x18003ca0b  lea     rax, [rbp+var_28]
0x18003ca0f  mov     [rsp+140h+var_D8], rax; __int64
0x18003ca14  lea     rax, [rbp+var_68+4]
0x18003ca18  mov     [rsp+140h+var_E0], rax; __int64
0x18003ca1d  lea     rax, [rbp+var_20]
0x18003ca21  mov     [rsp+140h+var_E8], rax; __int64
0x18003ca26  lea     rax, [rbp+var_60]
0x18003ca2a  mov     [rsp+140h+var_F0], rax; __int64
0x18003ca2f  lea     rax, [rbp+var_18]
0x18003ca33  mov     [rsp+140h+var_F8], rax; __int64
0x18003ca38  lea     rax, [rbp+var_78]
0x18003ca3c  mov     [rsp+140h+var_100], rax; __int64
0x18003ca41  lea     rax, [rbp+var_10]
0x18003ca45  mov     [rsp+140h+var_108], rax; __int64
0x18003ca4a  lea     rax, [rbp+SRWLock]
0x18003ca4e  mov     [rsp+140h+var_110], rax; __int64
0x18003ca53  lea     rax, [rbp+var_8]
0x18003ca57  mov     [rsp+140h+var_118], rax; __int64
0x18003ca5c  lea     rax, [rbp+var_58]
0x18003ca60  mov     [rsp+140h+var_120], rax; __int64
0x18003ca65  lea     rdx, byte_1800C6C89; int
0x18003ca6c  mov     rcx, r9; int
0x18003ca6f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003ca74  jmp     loc_18003CB1E
0x18003ca79  mov     [rbp+SRWLock], 0
0x18003ca81  lea     rdx, [rbp+SRWLock]
0x18003ca85  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003ca8a  mov     rax, [rbx+110h]
0x18003ca91  mov     dword ptr [rax], 2
0x18003ca97  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003ca9b  test    rcx, rcx
0x18003ca9e  jz      short loc_18003CAA6
0x18003caa0  call    cs:__imp_ReleaseSRWLockExclusive
0x18003caa6  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003caab  mov     rdi, rax
0x18003caae  mov     ecx, [rax]
0x18003cab0  cmp     ecx, 4
0x18003cab3  jbe     short loc_18003CB1E
0x18003cab5  mov     rax, [rax+18h]
0x18003cab9  mov     rcx, [rdi+10h]
0x18003cabd  test    cl, 40h
0x18003cac0  jz      short loc_18003CB1E
0x18003cac2  mov     rcx, rax
0x18003cac5  and     ecx, 40h
0x18003cac8  cmp     rcx, rax
0x18003cacb  jnz     short loc_18003CB1E
0x18003cacd  call    cs:__imp_GetCurrentThreadId
0x18003cad3  mov     dword ptr [rbp+SRWLock], eax
0x18003cad6  mov     r8, [rbx+110h]
0x18003cadd  mov     eax, [r8+48h]
0x18003cae1  mov     dword ptr [rbp+var_78], eax
0x18003cae4  mov     [rbp+var_58], 0
0x18003caec  add     r8, 8
0x18003caf0  lea     rax, [rbp+SRWLock]
0x18003caf4  mov     [rsp+140h+var_110], rax
0x18003caf9  lea     rax, [rbp+var_78]
0x18003cafd  mov     [rsp+140h+var_118], rax
0x18003cb02  lea     rax, [rbp+var_58]
0x18003cb06  mov     [rsp+140h+var_120], rax
0x18003cb0b  xor     r9d, r9d
0x18003cb0e  lea     rdx, word_1800C6BBA
0x18003cb15  mov     rcx, rdi
0x18003cb18  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003cb1d  nop
0x18003cb1e  lea     rcx, [rbx+120h]; this
0x18003cb25  cmp     dword ptr [rcx+18h], 0
0x18003cb29  jz      short loc_18003CB31
0x18003cb2b  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003cb30  nop
0x18003cb31  lea     r11, [rsp+140h+var_s0]
0x18003cb39  mov     rbx, [r11+18h]
0x18003cb3d  mov     rdi, [r11+20h]
0x18003cb41  mov     rsp, r11
0x18003cb44  pop     rbp
0x18003cb45  retn
```
