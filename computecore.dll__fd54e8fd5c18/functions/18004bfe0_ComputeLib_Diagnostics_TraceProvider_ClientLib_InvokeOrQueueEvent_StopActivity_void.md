# ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent::StopActivity(void)

- ea: `0x18004bfe0`
- end: `0x18004c2c0`
- name: `?StopActivity@ClientLib_InvokeOrQueueEvent@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x18004bfe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c047`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c215`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c047`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c215`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c247`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c247`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *this)
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
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x10000LL) != 0 && (v7 & 0x10000) == v7 )
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
          (int)&dword_1800C7EAC,
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
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x10000LL) != 0 && (v10 & 0x10000) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&word_1800C86D6,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *)((char *)this + 288));
}

```

## disassembly

```asm
0x18004bfe0  mov     [rsp-8+arg_8], rbx
0x18004bfe5  mov     [rsp-8+arg_10], rdi
0x18004bfea  push    rbp
0x18004bfeb  mov     rbp, rsp
0x18004bfee  sub     rsp, 140h
0x18004bff5  mov     rbx, rcx
0x18004bff8  mov     rdi, [rcx+110h]
0x18004bfff  mov     eax, [rdi+48h]
0x18004c002  test    eax, eax
0x18004c004  jns     loc_18004C1EE
0x18004c00a  add     rdi, 50h ; 'P'
0x18004c00e  cmp     eax, [rdi+8]
0x18004c011  jnz     loc_18004C1EE
0x18004c017  test    rdi, rdi
0x18004c01a  jz      loc_18004C1EE
0x18004c020  mov     [rbp+SRWLock], 0
0x18004c028  lea     rdx, [rbp+SRWLock]
0x18004c02c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004c031  mov     rax, [rbx+110h]
0x18004c038  mov     dword ptr [rax], 2
0x18004c03e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004c042  test    rcx, rcx
0x18004c045  jz      short loc_18004C04D
0x18004c047  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c04d  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004c052  mov     r9, rax
0x18004c055  mov     ecx, [rax]
0x18004c057  cmp     ecx, 5
0x18004c05a  jbe     loc_18004C298
0x18004c060  mov     rax, [rax+18h]
0x18004c064  mov     rcx, [r9+10h]
0x18004c068  mov     edx, 10000h
0x18004c06d  test    rdx, rcx
0x18004c070  jz      loc_18004C298
0x18004c076  mov     rcx, rax
0x18004c079  and     rcx, rdx
0x18004c07c  cmp     rcx, rax
0x18004c07f  jnz     loc_18004C298
0x18004c085  mov     rax, [rdi+30h]
0x18004c089  mov     [rbp+var_50], rax
0x18004c08d  mov     eax, [rdi+44h]
0x18004c090  mov     dword ptr [rbp+var_78+4], eax
0x18004c093  mov     eax, [rdi+10h]
0x18004c096  mov     dword ptr [rbp+var_70], eax
0x18004c099  mov     rax, [rdi+78h]
0x18004c09d  mov     [rbp+var_48], rax
0x18004c0a1  mov     rax, [rdi+70h]
0x18004c0a5  mov     [rbp+var_40], rax
0x18004c0a9  mov     eax, [rdi+68h]
0x18004c0ac  mov     dword ptr [rbp+var_70+4], eax
0x18004c0af  mov     rax, [rdi+60h]
0x18004c0b3  mov     [rbp+var_38], rax
0x18004c0b7  mov     rax, [rdi+58h]
0x18004c0bb  mov     [rbp+var_30], rax
0x18004c0bf  mov     eax, [rdi+50h]
0x18004c0c2  mov     dword ptr [rbp+var_68], eax
0x18004c0c5  mov     rax, [rdi+48h]
0x18004c0c9  mov     [rbp+var_28], rax
0x18004c0cd  mov     eax, [rdi+20h]
0x18004c0d0  mov     dword ptr [rbp+var_68+4], eax
0x18004c0d3  mov     rax, [rdi+18h]
0x18004c0d7  mov     [rbp+var_20], rax
0x18004c0db  mov     eax, [rdi]
0x18004c0dd  mov     [rbp+var_60], eax
0x18004c0e0  mov     rax, [rdi+80h]
0x18004c0e7  mov     [rbp+var_18], rax
0x18004c0eb  mov     eax, [rdi+40h]
0x18004c0ee  mov     dword ptr [rbp+var_78], eax
0x18004c0f1  mov     rax, [rdi+38h]
0x18004c0f5  mov     [rbp+var_10], rax
0x18004c0f9  mov     eax, [rdi+8]
0x18004c0fc  mov     dword ptr [rbp+SRWLock], eax
0x18004c0ff  mov     [rbp+var_8], 1000000h
0x18004c107  mov     [rbp+var_58], 0
0x18004c10f  mov     r8, [rbx+110h]
0x18004c116  add     r8, 8; int
0x18004c11a  lea     rax, [rbp+var_50]
0x18004c11e  mov     [rsp+140h+var_90], rax; __int64
0x18004c126  lea     rax, [rbp+var_78+4]
0x18004c12a  mov     [rsp+140h+var_98], rax; __int64
0x18004c132  lea     rax, [rbp+var_70]
0x18004c136  mov     [rsp+140h+var_A0], rax; __int64
0x18004c13e  lea     rax, [rbp+var_48]
0x18004c142  mov     [rsp+140h+var_A8], rax; __int64
0x18004c14a  lea     rax, [rbp+var_40]
0x18004c14e  mov     [rsp+140h+var_B0], rax; __int64
0x18004c156  lea     rax, [rbp+var_70+4]
0x18004c15a  mov     [rsp+140h+var_B8], rax; __int64
0x18004c162  lea     rax, [rbp+var_38]
0x18004c166  mov     [rsp+140h+var_C0], rax; __int64
0x18004c16e  lea     rax, [rbp+var_30]
0x18004c172  mov     [rsp+140h+var_C8], rax; __int64
0x18004c177  lea     rax, [rbp+var_68]
0x18004c17b  mov     [rsp+140h+var_D0], rax; __int64
0x18004c180  lea     rax, [rbp+var_28]
0x18004c184  mov     [rsp+140h+var_D8], rax; __int64
0x18004c189  lea     rax, [rbp+var_68+4]
0x18004c18d  mov     [rsp+140h+var_E0], rax; __int64
0x18004c192  lea     rax, [rbp+var_20]
0x18004c196  mov     [rsp+140h+var_E8], rax; __int64
0x18004c19b  lea     rax, [rbp+var_60]
0x18004c19f  mov     [rsp+140h+var_F0], rax; __int64
0x18004c1a4  lea     rax, [rbp+var_18]
0x18004c1a8  mov     [rsp+140h+var_F8], rax; __int64
0x18004c1ad  lea     rax, [rbp+var_78]
0x18004c1b1  mov     [rsp+140h+var_100], rax; __int64
0x18004c1b6  lea     rax, [rbp+var_10]
0x18004c1ba  mov     [rsp+140h+var_108], rax; __int64
0x18004c1bf  lea     rax, [rbp+SRWLock]
0x18004c1c3  mov     [rsp+140h+var_110], rax; __int64
0x18004c1c8  lea     rax, [rbp+var_8]
0x18004c1cc  mov     [rsp+140h+var_118], rax; __int64
0x18004c1d1  lea     rax, [rbp+var_58]
0x18004c1d5  mov     [rsp+140h+var_120], rax; __int64
0x18004c1da  lea     rdx, dword_1800C7EAC; int
0x18004c1e1  mov     rcx, r9; int
0x18004c1e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004c1e9  jmp     loc_18004C298
0x18004c1ee  mov     [rbp+SRWLock], 0
0x18004c1f6  lea     rdx, [rbp+SRWLock]
0x18004c1fa  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004c1ff  mov     rax, [rbx+110h]
0x18004c206  mov     dword ptr [rax], 2
0x18004c20c  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004c210  test    rcx, rcx
0x18004c213  jz      short loc_18004C21B
0x18004c215  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c21b  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004c220  mov     rdi, rax
0x18004c223  mov     ecx, [rax]
0x18004c225  cmp     ecx, 5
0x18004c228  jbe     short loc_18004C298
0x18004c22a  mov     rax, [rax+18h]
0x18004c22e  mov     rcx, [rdi+10h]
0x18004c232  mov     edx, 10000h
0x18004c237  test    rdx, rcx
0x18004c23a  jz      short loc_18004C298
0x18004c23c  mov     rcx, rax
0x18004c23f  and     rcx, rdx
0x18004c242  cmp     rcx, rax
0x18004c245  jnz     short loc_18004C298
0x18004c247  call    cs:__imp_GetCurrentThreadId
0x18004c24d  mov     dword ptr [rbp+SRWLock], eax
0x18004c250  mov     r8, [rbx+110h]
0x18004c257  mov     eax, [r8+48h]
0x18004c25b  mov     dword ptr [rbp+var_78], eax
0x18004c25e  mov     [rbp+var_58], 0
0x18004c266  add     r8, 8
0x18004c26a  lea     rax, [rbp+SRWLock]
0x18004c26e  mov     [rsp+140h+var_110], rax
0x18004c273  lea     rax, [rbp+var_78]
0x18004c277  mov     [rsp+140h+var_118], rax
0x18004c27c  lea     rax, [rbp+var_58]
0x18004c280  mov     [rsp+140h+var_120], rax
0x18004c285  xor     r9d, r9d
0x18004c288  lea     rdx, word_1800C86D6
0x18004c28f  mov     rcx, rdi
0x18004c292  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004c297  nop
0x18004c298  lea     rcx, [rbx+120h]; this
0x18004c29f  cmp     dword ptr [rcx+18h], 0
0x18004c2a3  jz      short loc_18004C2AB
0x18004c2a5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004c2aa  nop
0x18004c2ab  lea     r11, [rsp+140h+var_s0]
0x18004c2b3  mov     rbx, [r11+18h]
0x18004c2b7  mov     rdi, [r11+20h]
0x18004c2bb  mov     rsp, r11
0x18004c2be  pop     rbp
0x18004c2bf  retn
```
