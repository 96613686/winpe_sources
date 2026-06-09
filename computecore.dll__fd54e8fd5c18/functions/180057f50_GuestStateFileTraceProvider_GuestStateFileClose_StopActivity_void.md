# GuestStateFileTraceProvider::GuestStateFileClose::StopActivity(void)

- ea: `0x180057f50`
- end: `0x180058230`
- name: `?StopActivity@GuestStateFileClose@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileClose *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x180057f50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057fb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058185`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057fb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800581b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800581b7`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileClose::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileClose *this)
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
    v5 = GuestStateFileTraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x1000LL) != 0 && (v7 & 0x1000) == v7 )
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
          (int)&word_1800C92AA,
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
    v8 = GuestStateFileTraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x1000LL) != 0 && (v10 & 0x1000) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&word_1800C9256,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileClose *)((char *)this + 288));
}

```

## disassembly

```asm
0x180057f50  mov     [rsp-8+arg_8], rbx
0x180057f55  mov     [rsp-8+arg_10], rdi
0x180057f5a  push    rbp
0x180057f5b  mov     rbp, rsp
0x180057f5e  sub     rsp, 140h
0x180057f65  mov     rbx, rcx
0x180057f68  mov     rdi, [rcx+110h]
0x180057f6f  mov     eax, [rdi+48h]
0x180057f72  test    eax, eax
0x180057f74  jns     loc_18005815E
0x180057f7a  add     rdi, 50h ; 'P'
0x180057f7e  cmp     eax, [rdi+8]
0x180057f81  jnz     loc_18005815E
0x180057f87  test    rdi, rdi
0x180057f8a  jz      loc_18005815E
0x180057f90  mov     [rbp+SRWLock], 0
0x180057f98  lea     rdx, [rbp+SRWLock]
0x180057f9c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180057fa1  mov     rax, [rbx+110h]
0x180057fa8  mov     dword ptr [rax], 2
0x180057fae  mov     rcx, [rbp+SRWLock]; SRWLock
0x180057fb2  test    rcx, rcx
0x180057fb5  jz      short loc_180057FBD
0x180057fb7  call    cs:__imp_ReleaseSRWLockExclusive
0x180057fbd  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180057fc2  mov     r9, rax
0x180057fc5  mov     ecx, [rax]
0x180057fc7  cmp     ecx, 4
0x180057fca  jbe     loc_180058208
0x180057fd0  mov     rax, [rax+18h]
0x180057fd4  mov     rcx, [r9+10h]
0x180057fd8  mov     edx, 1000h
0x180057fdd  test    rdx, rcx
0x180057fe0  jz      loc_180058208
0x180057fe6  mov     rcx, rax
0x180057fe9  and     rcx, rdx
0x180057fec  cmp     rcx, rax
0x180057fef  jnz     loc_180058208
0x180057ff5  mov     rax, [rdi+30h]
0x180057ff9  mov     [rbp+var_50], rax
0x180057ffd  mov     eax, [rdi+44h]
0x180058000  mov     dword ptr [rbp+var_78+4], eax
0x180058003  mov     eax, [rdi+10h]
0x180058006  mov     dword ptr [rbp+var_70], eax
0x180058009  mov     rax, [rdi+78h]
0x18005800d  mov     [rbp+var_48], rax
0x180058011  mov     rax, [rdi+70h]
0x180058015  mov     [rbp+var_40], rax
0x180058019  mov     eax, [rdi+68h]
0x18005801c  mov     dword ptr [rbp+var_70+4], eax
0x18005801f  mov     rax, [rdi+60h]
0x180058023  mov     [rbp+var_38], rax
0x180058027  mov     rax, [rdi+58h]
0x18005802b  mov     [rbp+var_30], rax
0x18005802f  mov     eax, [rdi+50h]
0x180058032  mov     dword ptr [rbp+var_68], eax
0x180058035  mov     rax, [rdi+48h]
0x180058039  mov     [rbp+var_28], rax
0x18005803d  mov     eax, [rdi+20h]
0x180058040  mov     dword ptr [rbp+var_68+4], eax
0x180058043  mov     rax, [rdi+18h]
0x180058047  mov     [rbp+var_20], rax
0x18005804b  mov     eax, [rdi]
0x18005804d  mov     [rbp+var_60], eax
0x180058050  mov     rax, [rdi+80h]
0x180058057  mov     [rbp+var_18], rax
0x18005805b  mov     eax, [rdi+40h]
0x18005805e  mov     dword ptr [rbp+var_78], eax
0x180058061  mov     rax, [rdi+38h]
0x180058065  mov     [rbp+var_10], rax
0x180058069  mov     eax, [rdi+8]
0x18005806c  mov     dword ptr [rbp+SRWLock], eax
0x18005806f  mov     [rbp+var_8], 1000000h
0x180058077  mov     [rbp+var_58], 0
0x18005807f  mov     r8, [rbx+110h]
0x180058086  add     r8, 8; int
0x18005808a  lea     rax, [rbp+var_50]
0x18005808e  mov     [rsp+140h+var_90], rax; __int64
0x180058096  lea     rax, [rbp+var_78+4]
0x18005809a  mov     [rsp+140h+var_98], rax; __int64
0x1800580a2  lea     rax, [rbp+var_70]
0x1800580a6  mov     [rsp+140h+var_A0], rax; __int64
0x1800580ae  lea     rax, [rbp+var_48]
0x1800580b2  mov     [rsp+140h+var_A8], rax; __int64
0x1800580ba  lea     rax, [rbp+var_40]
0x1800580be  mov     [rsp+140h+var_B0], rax; __int64
0x1800580c6  lea     rax, [rbp+var_70+4]
0x1800580ca  mov     [rsp+140h+var_B8], rax; __int64
0x1800580d2  lea     rax, [rbp+var_38]
0x1800580d6  mov     [rsp+140h+var_C0], rax; __int64
0x1800580de  lea     rax, [rbp+var_30]
0x1800580e2  mov     [rsp+140h+var_C8], rax; __int64
0x1800580e7  lea     rax, [rbp+var_68]
0x1800580eb  mov     [rsp+140h+var_D0], rax; __int64
0x1800580f0  lea     rax, [rbp+var_28]
0x1800580f4  mov     [rsp+140h+var_D8], rax; __int64
0x1800580f9  lea     rax, [rbp+var_68+4]
0x1800580fd  mov     [rsp+140h+var_E0], rax; __int64
0x180058102  lea     rax, [rbp+var_20]
0x180058106  mov     [rsp+140h+var_E8], rax; __int64
0x18005810b  lea     rax, [rbp+var_60]
0x18005810f  mov     [rsp+140h+var_F0], rax; __int64
0x180058114  lea     rax, [rbp+var_18]
0x180058118  mov     [rsp+140h+var_F8], rax; __int64
0x18005811d  lea     rax, [rbp+var_78]
0x180058121  mov     [rsp+140h+var_100], rax; __int64
0x180058126  lea     rax, [rbp+var_10]
0x18005812a  mov     [rsp+140h+var_108], rax; __int64
0x18005812f  lea     rax, [rbp+SRWLock]
0x180058133  mov     [rsp+140h+var_110], rax; __int64
0x180058138  lea     rax, [rbp+var_8]
0x18005813c  mov     [rsp+140h+var_118], rax; __int64
0x180058141  lea     rax, [rbp+var_58]
0x180058145  mov     [rsp+140h+var_120], rax; __int64
0x18005814a  lea     rdx, word_1800C92AA; int
0x180058151  mov     rcx, r9; int
0x180058154  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180058159  jmp     loc_180058208
0x18005815e  mov     [rbp+SRWLock], 0
0x180058166  lea     rdx, [rbp+SRWLock]
0x18005816a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005816f  mov     rax, [rbx+110h]
0x180058176  mov     dword ptr [rax], 2
0x18005817c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180058180  test    rcx, rcx
0x180058183  jz      short loc_18005818B
0x180058185  call    cs:__imp_ReleaseSRWLockExclusive
0x18005818b  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180058190  mov     rdi, rax
0x180058193  mov     ecx, [rax]
0x180058195  cmp     ecx, 4
0x180058198  jbe     short loc_180058208
0x18005819a  mov     rax, [rax+18h]
0x18005819e  mov     rcx, [rdi+10h]
0x1800581a2  mov     edx, 1000h
0x1800581a7  test    rdx, rcx
0x1800581aa  jz      short loc_180058208
0x1800581ac  mov     rcx, rax
0x1800581af  and     rcx, rdx
0x1800581b2  cmp     rcx, rax
0x1800581b5  jnz     short loc_180058208
0x1800581b7  call    cs:__imp_GetCurrentThreadId
0x1800581bd  mov     dword ptr [rbp+SRWLock], eax
0x1800581c0  mov     r8, [rbx+110h]
0x1800581c7  mov     eax, [r8+48h]
0x1800581cb  mov     dword ptr [rbp+var_78], eax
0x1800581ce  mov     [rbp+var_58], 0
0x1800581d6  add     r8, 8
0x1800581da  lea     rax, [rbp+SRWLock]
0x1800581de  mov     [rsp+140h+var_110], rax
0x1800581e3  lea     rax, [rbp+var_78]
0x1800581e7  mov     [rsp+140h+var_118], rax
0x1800581ec  lea     rax, [rbp+var_58]
0x1800581f0  mov     [rsp+140h+var_120], rax
0x1800581f5  xor     r9d, r9d
0x1800581f8  lea     rdx, word_1800C9256
0x1800581ff  mov     rcx, rdi
0x180058202  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180058207  nop
0x180058208  lea     rcx, [rbx+120h]; this
0x18005820f  cmp     dword ptr [rcx+18h], 0
0x180058213  jz      short loc_18005821B
0x180058215  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005821a  nop
0x18005821b  lea     r11, [rsp+140h+var_s0]
0x180058223  mov     rbx, [r11+18h]
0x180058227  mov     rdi, [r11+20h]
0x18005822b  mov     rsp, r11
0x18005822e  pop     rbp
0x18005822f  retn
```
