# ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmGroupAccess::StopActivity(void)

- ea: `0x18003d3f0`
- end: `0x18003d6c6`
- name: `?StopActivity@VmFileUtilities_RevokeVmGroupAccess@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `726`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmGroupAccess *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x18003d3f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d457`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d620`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d457`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d620`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d64d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d64d`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmGroupAccess::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmGroupAccess *this)
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
          (int)&dword_1800C6A5C,
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
          (unsigned int)byte_1800C685B,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmGroupAccess *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003d3f0  mov     [rsp-8+arg_8], rbx
0x18003d3f5  mov     [rsp-8+arg_10], rdi
0x18003d3fa  push    rbp
0x18003d3fb  mov     rbp, rsp
0x18003d3fe  sub     rsp, 140h
0x18003d405  mov     rbx, rcx
0x18003d408  mov     rdi, [rcx+110h]
0x18003d40f  mov     eax, [rdi+48h]
0x18003d412  test    eax, eax
0x18003d414  jns     loc_18003D5F9
0x18003d41a  add     rdi, 50h ; 'P'
0x18003d41e  cmp     eax, [rdi+8]
0x18003d421  jnz     loc_18003D5F9
0x18003d427  test    rdi, rdi
0x18003d42a  jz      loc_18003D5F9
0x18003d430  mov     [rbp+SRWLock], 0
0x18003d438  lea     rdx, [rbp+SRWLock]
0x18003d43c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003d441  mov     rax, [rbx+110h]
0x18003d448  mov     dword ptr [rax], 2
0x18003d44e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003d452  test    rcx, rcx
0x18003d455  jz      short loc_18003D45D
0x18003d457  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d45d  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003d462  mov     r9, rax
0x18003d465  mov     ecx, [rax]
0x18003d467  cmp     ecx, 4
0x18003d46a  jbe     loc_18003D69E
0x18003d470  mov     rax, [rax+18h]
0x18003d474  mov     rcx, [r9+10h]
0x18003d478  test    cl, 40h
0x18003d47b  jz      loc_18003D69E
0x18003d481  mov     rcx, rax
0x18003d484  and     ecx, 40h
0x18003d487  cmp     rcx, rax
0x18003d48a  jnz     loc_18003D69E
0x18003d490  mov     rax, [rdi+30h]
0x18003d494  mov     [rbp+var_50], rax
0x18003d498  mov     eax, [rdi+44h]
0x18003d49b  mov     dword ptr [rbp+var_78+4], eax
0x18003d49e  mov     eax, [rdi+10h]
0x18003d4a1  mov     dword ptr [rbp+var_70], eax
0x18003d4a4  mov     rax, [rdi+78h]
0x18003d4a8  mov     [rbp+var_48], rax
0x18003d4ac  mov     rax, [rdi+70h]
0x18003d4b0  mov     [rbp+var_40], rax
0x18003d4b4  mov     eax, [rdi+68h]
0x18003d4b7  mov     dword ptr [rbp+var_70+4], eax
0x18003d4ba  mov     rax, [rdi+60h]
0x18003d4be  mov     [rbp+var_38], rax
0x18003d4c2  mov     rax, [rdi+58h]
0x18003d4c6  mov     [rbp+var_30], rax
0x18003d4ca  mov     eax, [rdi+50h]
0x18003d4cd  mov     dword ptr [rbp+var_68], eax
0x18003d4d0  mov     rax, [rdi+48h]
0x18003d4d4  mov     [rbp+var_28], rax
0x18003d4d8  mov     eax, [rdi+20h]
0x18003d4db  mov     dword ptr [rbp+var_68+4], eax
0x18003d4de  mov     rax, [rdi+18h]
0x18003d4e2  mov     [rbp+var_20], rax
0x18003d4e6  mov     eax, [rdi]
0x18003d4e8  mov     [rbp+var_60], eax
0x18003d4eb  mov     rax, [rdi+80h]
0x18003d4f2  mov     [rbp+var_18], rax
0x18003d4f6  mov     eax, [rdi+40h]
0x18003d4f9  mov     dword ptr [rbp+var_78], eax
0x18003d4fc  mov     rax, [rdi+38h]
0x18003d500  mov     [rbp+var_10], rax
0x18003d504  mov     eax, [rdi+8]
0x18003d507  mov     dword ptr [rbp+SRWLock], eax
0x18003d50a  mov     [rbp+var_8], 1000000h
0x18003d512  mov     [rbp+var_58], 0
0x18003d51a  mov     r8, [rbx+110h]
0x18003d521  add     r8, 8; int
0x18003d525  lea     rax, [rbp+var_50]
0x18003d529  mov     [rsp+140h+var_90], rax; __int64
0x18003d531  lea     rax, [rbp+var_78+4]
0x18003d535  mov     [rsp+140h+var_98], rax; __int64
0x18003d53d  lea     rax, [rbp+var_70]
0x18003d541  mov     [rsp+140h+var_A0], rax; __int64
0x18003d549  lea     rax, [rbp+var_48]
0x18003d54d  mov     [rsp+140h+var_A8], rax; __int64
0x18003d555  lea     rax, [rbp+var_40]
0x18003d559  mov     [rsp+140h+var_B0], rax; __int64
0x18003d561  lea     rax, [rbp+var_70+4]
0x18003d565  mov     [rsp+140h+var_B8], rax; __int64
0x18003d56d  lea     rax, [rbp+var_38]
0x18003d571  mov     [rsp+140h+var_C0], rax; __int64
0x18003d579  lea     rax, [rbp+var_30]
0x18003d57d  mov     [rsp+140h+var_C8], rax; __int64
0x18003d582  lea     rax, [rbp+var_68]
0x18003d586  mov     [rsp+140h+var_D0], rax; __int64
0x18003d58b  lea     rax, [rbp+var_28]
0x18003d58f  mov     [rsp+140h+var_D8], rax; __int64
0x18003d594  lea     rax, [rbp+var_68+4]
0x18003d598  mov     [rsp+140h+var_E0], rax; __int64
0x18003d59d  lea     rax, [rbp+var_20]
0x18003d5a1  mov     [rsp+140h+var_E8], rax; __int64
0x18003d5a6  lea     rax, [rbp+var_60]
0x18003d5aa  mov     [rsp+140h+var_F0], rax; __int64
0x18003d5af  lea     rax, [rbp+var_18]
0x18003d5b3  mov     [rsp+140h+var_F8], rax; __int64
0x18003d5b8  lea     rax, [rbp+var_78]
0x18003d5bc  mov     [rsp+140h+var_100], rax; __int64
0x18003d5c1  lea     rax, [rbp+var_10]
0x18003d5c5  mov     [rsp+140h+var_108], rax; __int64
0x18003d5ca  lea     rax, [rbp+SRWLock]
0x18003d5ce  mov     [rsp+140h+var_110], rax; __int64
0x18003d5d3  lea     rax, [rbp+var_8]
0x18003d5d7  mov     [rsp+140h+var_118], rax; __int64
0x18003d5dc  lea     rax, [rbp+var_58]
0x18003d5e0  mov     [rsp+140h+var_120], rax; __int64
0x18003d5e5  lea     rdx, dword_1800C6A5C; int
0x18003d5ec  mov     rcx, r9; int
0x18003d5ef  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003d5f4  jmp     loc_18003D69E
0x18003d5f9  mov     [rbp+SRWLock], 0
0x18003d601  lea     rdx, [rbp+SRWLock]
0x18003d605  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003d60a  mov     rax, [rbx+110h]
0x18003d611  mov     dword ptr [rax], 2
0x18003d617  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003d61b  test    rcx, rcx
0x18003d61e  jz      short loc_18003D626
0x18003d620  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d626  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003d62b  mov     rdi, rax
0x18003d62e  mov     ecx, [rax]
0x18003d630  cmp     ecx, 4
0x18003d633  jbe     short loc_18003D69E
0x18003d635  mov     rax, [rax+18h]
0x18003d639  mov     rcx, [rdi+10h]
0x18003d63d  test    cl, 40h
0x18003d640  jz      short loc_18003D69E
0x18003d642  mov     rcx, rax
0x18003d645  and     ecx, 40h
0x18003d648  cmp     rcx, rax
0x18003d64b  jnz     short loc_18003D69E
0x18003d64d  call    cs:__imp_GetCurrentThreadId
0x18003d653  mov     dword ptr [rbp+SRWLock], eax
0x18003d656  mov     r8, [rbx+110h]
0x18003d65d  mov     eax, [r8+48h]
0x18003d661  mov     dword ptr [rbp+var_78], eax
0x18003d664  mov     [rbp+var_58], 0
0x18003d66c  add     r8, 8
0x18003d670  lea     rax, [rbp+SRWLock]
0x18003d674  mov     [rsp+140h+var_110], rax
0x18003d679  lea     rax, [rbp+var_78]
0x18003d67d  mov     [rsp+140h+var_118], rax
0x18003d682  lea     rax, [rbp+var_58]
0x18003d686  mov     [rsp+140h+var_120], rax
0x18003d68b  xor     r9d, r9d
0x18003d68e  lea     rdx, byte_1800C685B
0x18003d695  mov     rcx, rdi
0x18003d698  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003d69d  nop
0x18003d69e  lea     rcx, [rbx+120h]; this
0x18003d6a5  cmp     dword ptr [rcx+18h], 0
0x18003d6a9  jz      short loc_18003D6B1
0x18003d6ab  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003d6b0  nop
0x18003d6b1  lea     r11, [rsp+140h+var_s0]
0x18003d6b9  mov     rbx, [r11+18h]
0x18003d6bd  mov     rdi, [r11+20h]
0x18003d6c1  mov     rsp, r11
0x18003d6c4  pop     rbp
0x18003d6c5  retn
```
