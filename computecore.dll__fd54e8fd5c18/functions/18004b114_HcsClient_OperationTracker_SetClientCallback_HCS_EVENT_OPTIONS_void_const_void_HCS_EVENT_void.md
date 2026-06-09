# HcsClient::OperationTracker::SetClientCallback(HCS_EVENT_OPTIONS,void const *,void (*)(HCS_EVENT *,void *))

- ea: `0x18004b114`
- end: `0x18004b2aa`
- name: `?SetClientCallback@OperationTracker@HcsClient@@QEAAXW4HCS_EVENT_OPTIONS@@PEBXP6AXPEAUHCS_EVENT@@PEAX@Z@Z`
- size: `406`
- prototype: `void __fastcall(HcsClient::OperationTracker *__hidden this, enum HCS_EVENT_OPTIONS, const void *, void (*)(struct HCS_EVENT *, void *))`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800172c0`
- `0x18001b880`
- `0x180045c80`

## callees

- `0x180001d20`
- `0x1800067c0`
- `0x180014de4`
- `0x18001587c`
- `0x18002a03c`
- `0x18002a610`
- `0x18004b114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b253`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b253`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004b22e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004b22e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004b245`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004b245`

## string_xrefs

- `0x18004b280`: `onecore\vm\compute\dll\lib\core\operationtracker.cpp`
- `0x18004b298`: `onecore\vm\compute\dll\lib\core\operationtracker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HcsClient::OperationTracker::SetClientCallback(
        PSRWLOCK *this,
        enum HCS_EVENT_OPTIONS a2,
        RTL_SRWLOCK *a3,
        RTL_SRWLOCK *a4)
{
  bool v8; // al
  _QWORD *v9; // rdi
  const struct _tlgProvider_t *v10; // rax
  PSRWLOCK v11; // rbx
  int v12; // [rsp+20h] [rbp-58h]
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v14[16]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  CallbackManager::Enter(this[13]);
  if ( v14[8] )
  {
    if ( a4 )
    {
      v8 = this[9] != this[10] && !this[2];
      if ( (a2 & 2) != 0 )
      {
        *((_DWORD *)this + 40) = 2;
      }
      else if ( (a2 & 4) != 0 )
      {
        *((_DWORD *)this + 40) = 3;
      }
    }
    else
    {
      if ( a2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1AA,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\operationtracker.cpp",
          (const char *)0x80070057LL,
          v12);
      if ( a3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1AB,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\operationtracker.cpp",
          (const char *)0x80070057LL,
          v12);
      v8 = 0;
      a4 = 0;
    }
    *((_DWORD *)this + 8) = a2;
    this[3] = a3;
    this[2] = a4;
    if ( v8 )
    {
      v9 = this + 14;
      if ( (unsigned __int64)this[17] > 7 )
        v9 = (_QWORD *)*v9;
      v10 = ComputeLib::Diagnostics::TraceProvider::Provider();
      if ( *(_DWORD *)v10 > 5u
        && (*((_QWORD *)v10 + 2) & 0x10000LL) != 0
        && (*((_QWORD *)v10 + 3) & 0x10000LL) == *((_QWORD *)v10 + 3) )
      {
        v13 = (__int64)v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (int)v10,
          (__int64)&v13);
      }
      *((_BYTE *)this + 96) = 1;
      v11 = this[13];
      AcquireSRWLockExclusive(v11 + 5);
      if ( !LODWORD(v11[7].Ptr) )
      {
        LODWORD(v11[7].Ptr) = 1;
        SubmitThreadpoolWork((PTP_WORK)v11[4].Ptr);
      }
      if ( v11 != (PSRWLOCK)-40LL )
        ReleaseSRWLockExclusive(v11 + 5);
    }
  }
  std::_Optional_destruct_base<CallbackReference,0>::~_Optional_destruct_base<CallbackReference,0>(v14);
}

```

## disassembly

```asm
0x18004b114  push    rbx
0x18004b116  push    rbp
0x18004b117  push    rsi
0x18004b118  push    rdi
0x18004b119  sub     rsp, 58h
0x18004b11d  mov     rax, cs:__security_cookie
0x18004b124  xor     rax, rsp
0x18004b127  mov     [rsp+78h+var_30], rax
0x18004b12c  mov     rsi, r9
0x18004b12f  mov     rbp, r8
0x18004b132  mov     edi, edx
0x18004b134  mov     rbx, rcx
0x18004b137  lea     rdx, [rsp+78h+var_40]
0x18004b13c  mov     rcx, [rcx+68h]; SRWLock
0x18004b140  call    ?Enter@CallbackManager@@QEAA?AV?$optional@VCallbackReference@@@std@@XZ; CallbackManager::Enter(void)
0x18004b145  nop
0x18004b146  cmp     [rsp+78h+var_38], 0
0x18004b14b  jz      loc_18004B25A
0x18004b151  test    rsi, rsi
0x18004b154  jz      short loc_18004B191
0x18004b156  mov     rax, [rbx+50h]
0x18004b15a  cmp     [rbx+48h], rax
0x18004b15e  jz      short loc_18004B16B
0x18004b160  cmp     qword ptr [rbx+10h], 0
0x18004b165  jnz     short loc_18004B16B
0x18004b167  mov     al, 1
0x18004b169  jmp     short loc_18004B16D
0x18004b16b  xor     al, al
0x18004b16d  test    dil, 2
0x18004b171  jz      short loc_18004B17F
0x18004b173  mov     dword ptr [rbx+0A0h], 2
0x18004b17d  jmp     short loc_18004B1B0
0x18004b17f  test    dil, 4
0x18004b183  jz      short loc_18004B1B0
0x18004b185  mov     dword ptr [rbx+0A0h], 3
0x18004b18f  jmp     short loc_18004B1B0
0x18004b191  mov     rcx, [rsp+78h]; this
0x18004b196  test    edi, edi
0x18004b198  jnz     loc_18004B292
0x18004b19e  mov     rcx, [rsp+78h]; this
0x18004b1a3  test    rbp, rbp
0x18004b1a6  jnz     loc_18004B27A
0x18004b1ac  xor     al, al
0x18004b1ae  xor     esi, esi
0x18004b1b0  mov     [rbx+20h], edi
0x18004b1b3  mov     [rbx+18h], rbp
0x18004b1b7  mov     [rbx+10h], rsi
0x18004b1bb  test    al, al
0x18004b1bd  jz      loc_18004B25A
0x18004b1c3  lea     rdi, [rbx+70h]
0x18004b1c7  cmp     qword ptr [rdi+18h], 7
0x18004b1cc  jbe     short loc_18004B1D1
0x18004b1ce  mov     rdi, [rdi]
0x18004b1d1  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b1d6  mov     ecx, [rax]
0x18004b1d8  cmp     ecx, 5
0x18004b1db  jbe     short loc_18004B21F
0x18004b1dd  mov     rdx, [rax+18h]
0x18004b1e1  mov     rcx, [rax+10h]
0x18004b1e5  mov     r8d, 10000h
0x18004b1eb  test    r8, rcx
0x18004b1ee  jz      short loc_18004B21F
0x18004b1f0  mov     rcx, rdx
0x18004b1f3  and     rcx, r8
0x18004b1f6  cmp     rcx, rdx
0x18004b1f9  jnz     short loc_18004B21F
0x18004b1fb  mov     [rsp+78h+var_48], rdi
0x18004b200  lea     rcx, [rsp+78h+var_48]
0x18004b205  mov     qword ptr [rsp+78h+var_58], rcx; __int64
0x18004b20a  xor     r9d, r9d
0x18004b20d  xor     r8d, r8d
0x18004b210  lea     rdx, byte_1800C77DD
0x18004b217  mov     rcx, rax; int
0x18004b21a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004b21f  mov     byte ptr [rbx+60h], 1
0x18004b223  mov     rbx, [rbx+68h]
0x18004b227  lea     rdi, [rbx+28h]
0x18004b22b  mov     rcx, rdi; SRWLock
0x18004b22e  call    cs:__imp_AcquireSRWLockExclusive
0x18004b234  cmp     dword ptr [rbx+38h], 0
0x18004b238  jnz     short loc_18004B24B
0x18004b23a  mov     dword ptr [rbx+38h], 1
0x18004b241  mov     rcx, [rbx+20h]; pwk
0x18004b245  call    cs:__imp_SubmitThreadpoolWork
0x18004b24b  test    rdi, rdi
0x18004b24e  jz      short loc_18004B25A
0x18004b250  mov     rcx, rdi; SRWLock
0x18004b253  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b259  nop
0x18004b25a  lea     rcx, [rsp+78h+var_40]
0x18004b25f  call    ??1?$_Optional_destruct_base@VCallbackReference@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<CallbackReference,0>::~_Optional_destruct_base<CallbackReference,0>(void)
0x18004b264  mov     rcx, [rsp+78h+var_30]
0x18004b269  xor     rcx, rsp; StackCookie
0x18004b26c  call    __security_check_cookie
0x18004b271  add     rsp, 58h
0x18004b275  pop     rdi
0x18004b276  pop     rsi
0x18004b277  pop     rbp
0x18004b278  pop     rbx
0x18004b279  retn
0x18004b27a  mov     r9d, 80070057h; char *
0x18004b280  lea     r8, aOnecoreVmCompu_7; "onecore\\vm\\compute\\dll\\lib\\core\\o"...
0x18004b287  mov     edx, 1ABh; void *
0x18004b28c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b292  mov     r9d, 80070057h; char *
0x18004b298  lea     r8, aOnecoreVmCompu_7; "onecore\\vm\\compute\\dll\\lib\\core\\o"...
0x18004b29f  mov     edx, 1AAh; void *
0x18004b2a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
