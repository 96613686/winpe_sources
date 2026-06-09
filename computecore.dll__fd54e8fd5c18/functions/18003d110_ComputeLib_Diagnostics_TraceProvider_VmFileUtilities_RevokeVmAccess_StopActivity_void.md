# ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmAccess::StopActivity(void)

- ea: `0x18003d110`
- end: `0x18003d3e6`
- name: `?StopActivity@VmFileUtilities_RevokeVmAccess@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `726`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmAccess *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x18003d110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d177`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d340`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d177`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d340`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d36d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d36d`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmAccess::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmAccess *this)
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
          (int)&byte_1800C7133,
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
          (unsigned int)&byte_1800C6DEF,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmAccess *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003d110  mov     [rsp-8+arg_8], rbx
0x18003d115  mov     [rsp-8+arg_10], rdi
0x18003d11a  push    rbp
0x18003d11b  mov     rbp, rsp
0x18003d11e  sub     rsp, 140h
0x18003d125  mov     rbx, rcx
0x18003d128  mov     rdi, [rcx+110h]
0x18003d12f  mov     eax, [rdi+48h]
0x18003d132  test    eax, eax
0x18003d134  jns     loc_18003D319
0x18003d13a  add     rdi, 50h ; 'P'
0x18003d13e  cmp     eax, [rdi+8]
0x18003d141  jnz     loc_18003D319
0x18003d147  test    rdi, rdi
0x18003d14a  jz      loc_18003D319
0x18003d150  mov     [rbp+SRWLock], 0
0x18003d158  lea     rdx, [rbp+SRWLock]
0x18003d15c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003d161  mov     rax, [rbx+110h]
0x18003d168  mov     dword ptr [rax], 2
0x18003d16e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003d172  test    rcx, rcx
0x18003d175  jz      short loc_18003D17D
0x18003d177  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d17d  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003d182  mov     r9, rax
0x18003d185  mov     ecx, [rax]
0x18003d187  cmp     ecx, 4
0x18003d18a  jbe     loc_18003D3BE
0x18003d190  mov     rax, [rax+18h]
0x18003d194  mov     rcx, [r9+10h]
0x18003d198  test    cl, 40h
0x18003d19b  jz      loc_18003D3BE
0x18003d1a1  mov     rcx, rax
0x18003d1a4  and     ecx, 40h
0x18003d1a7  cmp     rcx, rax
0x18003d1aa  jnz     loc_18003D3BE
0x18003d1b0  mov     rax, [rdi+30h]
0x18003d1b4  mov     [rbp+var_50], rax
0x18003d1b8  mov     eax, [rdi+44h]
0x18003d1bb  mov     dword ptr [rbp+var_78+4], eax
0x18003d1be  mov     eax, [rdi+10h]
0x18003d1c1  mov     dword ptr [rbp+var_70], eax
0x18003d1c4  mov     rax, [rdi+78h]
0x18003d1c8  mov     [rbp+var_48], rax
0x18003d1cc  mov     rax, [rdi+70h]
0x18003d1d0  mov     [rbp+var_40], rax
0x18003d1d4  mov     eax, [rdi+68h]
0x18003d1d7  mov     dword ptr [rbp+var_70+4], eax
0x18003d1da  mov     rax, [rdi+60h]
0x18003d1de  mov     [rbp+var_38], rax
0x18003d1e2  mov     rax, [rdi+58h]
0x18003d1e6  mov     [rbp+var_30], rax
0x18003d1ea  mov     eax, [rdi+50h]
0x18003d1ed  mov     dword ptr [rbp+var_68], eax
0x18003d1f0  mov     rax, [rdi+48h]
0x18003d1f4  mov     [rbp+var_28], rax
0x18003d1f8  mov     eax, [rdi+20h]
0x18003d1fb  mov     dword ptr [rbp+var_68+4], eax
0x18003d1fe  mov     rax, [rdi+18h]
0x18003d202  mov     [rbp+var_20], rax
0x18003d206  mov     eax, [rdi]
0x18003d208  mov     [rbp+var_60], eax
0x18003d20b  mov     rax, [rdi+80h]
0x18003d212  mov     [rbp+var_18], rax
0x18003d216  mov     eax, [rdi+40h]
0x18003d219  mov     dword ptr [rbp+var_78], eax
0x18003d21c  mov     rax, [rdi+38h]
0x18003d220  mov     [rbp+var_10], rax
0x18003d224  mov     eax, [rdi+8]
0x18003d227  mov     dword ptr [rbp+SRWLock], eax
0x18003d22a  mov     [rbp+var_8], 1000000h
0x18003d232  mov     [rbp+var_58], 0
0x18003d23a  mov     r8, [rbx+110h]
0x18003d241  add     r8, 8; int
0x18003d245  lea     rax, [rbp+var_50]
0x18003d249  mov     [rsp+140h+var_90], rax; __int64
0x18003d251  lea     rax, [rbp+var_78+4]
0x18003d255  mov     [rsp+140h+var_98], rax; __int64
0x18003d25d  lea     rax, [rbp+var_70]
0x18003d261  mov     [rsp+140h+var_A0], rax; __int64
0x18003d269  lea     rax, [rbp+var_48]
0x18003d26d  mov     [rsp+140h+var_A8], rax; __int64
0x18003d275  lea     rax, [rbp+var_40]
0x18003d279  mov     [rsp+140h+var_B0], rax; __int64
0x18003d281  lea     rax, [rbp+var_70+4]
0x18003d285  mov     [rsp+140h+var_B8], rax; __int64
0x18003d28d  lea     rax, [rbp+var_38]
0x18003d291  mov     [rsp+140h+var_C0], rax; __int64
0x18003d299  lea     rax, [rbp+var_30]
0x18003d29d  mov     [rsp+140h+var_C8], rax; __int64
0x18003d2a2  lea     rax, [rbp+var_68]
0x18003d2a6  mov     [rsp+140h+var_D0], rax; __int64
0x18003d2ab  lea     rax, [rbp+var_28]
0x18003d2af  mov     [rsp+140h+var_D8], rax; __int64
0x18003d2b4  lea     rax, [rbp+var_68+4]
0x18003d2b8  mov     [rsp+140h+var_E0], rax; __int64
0x18003d2bd  lea     rax, [rbp+var_20]
0x18003d2c1  mov     [rsp+140h+var_E8], rax; __int64
0x18003d2c6  lea     rax, [rbp+var_60]
0x18003d2ca  mov     [rsp+140h+var_F0], rax; __int64
0x18003d2cf  lea     rax, [rbp+var_18]
0x18003d2d3  mov     [rsp+140h+var_F8], rax; __int64
0x18003d2d8  lea     rax, [rbp+var_78]
0x18003d2dc  mov     [rsp+140h+var_100], rax; __int64
0x18003d2e1  lea     rax, [rbp+var_10]
0x18003d2e5  mov     [rsp+140h+var_108], rax; __int64
0x18003d2ea  lea     rax, [rbp+SRWLock]
0x18003d2ee  mov     [rsp+140h+var_110], rax; __int64
0x18003d2f3  lea     rax, [rbp+var_8]
0x18003d2f7  mov     [rsp+140h+var_118], rax; __int64
0x18003d2fc  lea     rax, [rbp+var_58]
0x18003d300  mov     [rsp+140h+var_120], rax; __int64
0x18003d305  lea     rdx, byte_1800C7133; int
0x18003d30c  mov     rcx, r9; int
0x18003d30f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003d314  jmp     loc_18003D3BE
0x18003d319  mov     [rbp+SRWLock], 0
0x18003d321  lea     rdx, [rbp+SRWLock]
0x18003d325  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003d32a  mov     rax, [rbx+110h]
0x18003d331  mov     dword ptr [rax], 2
0x18003d337  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003d33b  test    rcx, rcx
0x18003d33e  jz      short loc_18003D346
0x18003d340  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d346  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003d34b  mov     rdi, rax
0x18003d34e  mov     ecx, [rax]
0x18003d350  cmp     ecx, 4
0x18003d353  jbe     short loc_18003D3BE
0x18003d355  mov     rax, [rax+18h]
0x18003d359  mov     rcx, [rdi+10h]
0x18003d35d  test    cl, 40h
0x18003d360  jz      short loc_18003D3BE
0x18003d362  mov     rcx, rax
0x18003d365  and     ecx, 40h
0x18003d368  cmp     rcx, rax
0x18003d36b  jnz     short loc_18003D3BE
0x18003d36d  call    cs:__imp_GetCurrentThreadId
0x18003d373  mov     dword ptr [rbp+SRWLock], eax
0x18003d376  mov     r8, [rbx+110h]
0x18003d37d  mov     eax, [r8+48h]
0x18003d381  mov     dword ptr [rbp+var_78], eax
0x18003d384  mov     [rbp+var_58], 0
0x18003d38c  add     r8, 8
0x18003d390  lea     rax, [rbp+SRWLock]
0x18003d394  mov     [rsp+140h+var_110], rax
0x18003d399  lea     rax, [rbp+var_78]
0x18003d39d  mov     [rsp+140h+var_118], rax
0x18003d3a2  lea     rax, [rbp+var_58]
0x18003d3a6  mov     [rsp+140h+var_120], rax
0x18003d3ab  xor     r9d, r9d
0x18003d3ae  lea     rdx, byte_1800C6DEF
0x18003d3b5  mov     rcx, rdi
0x18003d3b8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003d3bd  nop
0x18003d3be  lea     rcx, [rbx+120h]; this
0x18003d3c5  cmp     dword ptr [rcx+18h], 0
0x18003d3c9  jz      short loc_18003D3D1
0x18003d3cb  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003d3d0  nop
0x18003d3d1  lea     r11, [rsp+140h+var_s0]
0x18003d3d9  mov     rbx, [r11+18h]
0x18003d3dd  mov     rdi, [r11+20h]
0x18003d3e1  mov     rsp, r11
0x18003d3e4  pop     rbp
0x18003d3e5  retn
```
