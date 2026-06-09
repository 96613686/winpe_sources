# NGENService::ControllerState::Set(ulong,ulong)

- ea: `0x18000352c`
- end: `0x1800035ba`
- name: `?Set@ControllerState@NGENService@@SAXKK@Z`
- size: `142`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800046c4`
- `0x1800050b4`
- `0x1800053a0`
- `0x180005688`
- `0x18001b1e4`

## callees

- `0x18000352c`
- `0x18002e1d0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003552`
- `KERNEL32!EnterCriticalSection` at `0x180003552`
- `KERNEL32!LeaveCriticalSection` at `0x1800035b3`
- `KERNEL32!SetEvent` at `0x18000359a`
- `KERNEL32!SetEvent` at `0x18000359a`

## string_xrefs

- `0x180003587`: `New Controller state is %s. Idle considerations = 0x%08x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NGENService::ControllerState::Set(int a1, unsigned int a2)
{
  EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
  if ( NGENService::ControllerState::m_dwControllerState != a1 )
  {
    NGENService::ControllerState::m_dwControllerState = a1;
    LODWORD(NGENService::ControllerState::m_dwIdleConsiderations) = a2;
    NGENService::DebugLog(
      (NGENService *)L"New Controller state is %s. Idle considerations = 0x%08x\n",
      (const unsigned __int16 *)(&NGENService::ControllerStateDbgString)[a1],
      a2);
    SetEvent(NGENService::g_hControllerStateChange);
  }
  LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
}

```

## disassembly

```asm
0x18000352c  mov     rax, rsp
0x18000352f  mov     [rax+8], rbx
0x180003533  mov     [rax+10h], rsi
0x180003537  push    rdi
0x180003538  sub     rsp, 30h
0x18000353c  mov     edi, edx
0x18000353e  mov     ebx, ecx
0x180003540  lea     rsi, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; CriticalSection NGENService::ControllerState::m_csControllerState
0x180003547  mov     [rax-18h], rsi
0x18000354b  mov     byte ptr [rax-10h], 0
0x18000354f  mov     rcx, rsi; lpCriticalSection
0x180003552  call    cs:__imp_EnterCriticalSection
0x180003558  mov     [rsp+38h+var_10], 1
0x18000355d  mov     eax, cs:?m_dwControllerState@ControllerState@NGENService@@1V?$Volatile@K@@A; Volatile<ulong> NGENService::ControllerState::m_dwControllerState
0x180003563  cmp     eax, ebx
0x180003565  jz      short loc_1800035A1
0x180003567  mov     cs:?m_dwControllerState@ControllerState@NGENService@@1V?$Volatile@K@@A, ebx; Volatile<ulong> NGENService::ControllerState::m_dwControllerState
0x18000356d  mov     cs:?m_dwIdleConsiderations@ControllerState@NGENService@@1V?$Volatile@K@@A, edi; Volatile<ulong> NGENService::ControllerState::m_dwIdleConsiderations
0x180003573  mov     edx, cs:?m_dwControllerState@ControllerState@NGENService@@1V?$Volatile@K@@A; Volatile<ulong> NGENService::ControllerState::m_dwControllerState
0x180003579  lea     rax, ?ControllerStateDbgString@NGENService@@3PAPEBGA; ushort const * near * NGENService::ControllerStateDbgString
0x180003580  mov     r8d, edi
0x180003583  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x180003587  lea     rcx, aNewControllerS; "New Controller state is %s. Idle consid"...
0x18000358e  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180003593  mov     rcx, cs:?g_hControllerStateChange@NGENService@@3PEAXEA; hEvent
0x18000359a  call    cs:__imp_SetEvent
0x1800035a0  nop
0x1800035a1  mov     rcx, rsi
0x1800035a4  mov     rbx, [rsp+38h+arg_0]
0x1800035a9  mov     rsi, [rsp+38h+arg_8]
0x1800035ae  add     rsp, 30h
0x1800035b2  pop     rdi
0x1800035b3  jmp     cs:__imp_LeaveCriticalSection
```
