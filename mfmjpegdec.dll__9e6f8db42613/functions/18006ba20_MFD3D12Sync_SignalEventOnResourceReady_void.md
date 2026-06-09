# MFD3D12Sync::SignalEventOnResourceReady(void *)

- ea: `0x18006ba20`
- end: `0x18006baf5`
- name: `?SignalEventOnResourceReady@MFD3D12Sync@@UEAAJPEAX@Z`
- size: `213`
- prototype: `__int64 __fastcall(MFD3D12Sync *__hidden this, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18002312c`
- `0x180054b90`
- `0x180056638`
- `0x18006ba20`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bab1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bab1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ba89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ba89`

## string_xrefs

- `0x18006ba3b`: `MFD3D12Sync::SignalEventOnResourceReady`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MFD3D12Sync::SignalEventOnResourceReady(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  unsigned int v5; // edi
  char v7; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v7, "MFD3D12Sync::SignalEventOnResourceReady", 184);
  if ( g_wppLevels >= 0x10u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids, this, a2);
  if ( LOBYTE(this[4].LockCount) )
  {
    v4 = this + 2;
    EnterCriticalSection(this + 2);
    v5 = (*(__int64 (__fastcall **)(_QWORD, PRTL_CRITICAL_SECTION_DEBUG, void *))(**(_QWORD **)&this[3].LockCount + 72LL))(
           *(_QWORD *)&this[3].LockCount,
           this[4].DebugInfo,
           a2);
    LeaveCriticalSection(v4);
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, PRTL_CRITICAL_SECTION_DEBUG, void *))(**(_QWORD **)&this[3].LockCount + 72LL))(
           *(_QWORD *)&this[3].LockCount,
           this[4].DebugInfo,
           a2);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v7);
  return v5;
}

```

## disassembly

```asm
0x18006ba20  mov     [rsp+arg_8], rbx
0x18006ba25  mov     [rsp+arg_10], rsi
0x18006ba2a  push    rdi
0x18006ba2b  sub     rsp, 30h
0x18006ba2f  mov     rsi, rdx
0x18006ba32  mov     rdi, rcx
0x18006ba35  mov     r8d, 0B8h; int
0x18006ba3b  lea     rdx, aMfd3d12syncSig; "MFD3D12Sync::SignalEventOnResourceReady"
0x18006ba42  lea     rcx, [rsp+38h+arg_0]; this
0x18006ba47  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006ba4c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x18006ba53  jb      short loc_18006BA79
0x18006ba55  mov     edx, 2Bh ; '+'
0x18006ba5a  mov     [rsp+38h+var_18], rsi
0x18006ba5f  mov     r9, rdi
0x18006ba62  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x18006ba69  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ba70  mov     rcx, [rcx+10h]
0x18006ba74  call    WPP_SF_qq
0x18006ba79  cmp     byte ptr [rdi+0A8h], 0
0x18006ba80  jz      short loc_18006BABA
0x18006ba82  lea     rbx, [rdi+50h]
0x18006ba86  mov     rcx, rbx; lpCriticalSection
0x18006ba89  call    cs:__imp_EnterCriticalSection
0x18006ba8f  mov     rcx, [rdi+80h]
0x18006ba96  mov     rax, [rcx]
0x18006ba99  mov     r8, rsi
0x18006ba9c  mov     rdx, [rdi+0A0h]
0x18006baa3  mov     rax, [rax+48h]
0x18006baa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006baac  mov     edi, eax
0x18006baae  mov     rcx, rbx; lpCriticalSection
0x18006bab1  call    cs:__imp_LeaveCriticalSection
0x18006bab7  nop
0x18006bab8  jmp     short loc_18006BAD9
0x18006baba  mov     rcx, [rdi+80h]
0x18006bac1  mov     rax, [rcx]
0x18006bac4  mov     r8, rsi
0x18006bac7  mov     rdx, [rdi+0A0h]
0x18006bace  mov     rax, [rax+48h]
0x18006bad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bad7  mov     edi, eax
0x18006bad9  lea     rcx, [rsp+38h+arg_0]; this
0x18006bade  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006bae3  mov     eax, edi
0x18006bae5  mov     rbx, [rsp+38h+arg_8]
0x18006baea  mov     rsi, [rsp+38h+arg_10]
0x18006baef  add     rsp, 30h
0x18006baf3  pop     rdi
0x18006baf4  retn
```
