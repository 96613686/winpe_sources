# SEND_QUEUE::StartSends(void)

- ea: `0x180002250`
- end: `0x1800022c0`
- name: `?StartSends@SEND_QUEUE@@QEAAJXZ`
- size: `112`
- prototype: `__int64 __fastcall(SEND_QUEUE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005294`
- `0x180006ce8`

## callees

- `0x180002004`
- `0x180002250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002266`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002266`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000229a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000229a`

## pseudocode

```c
__int64 __fastcall SEND_QUEUE::StartSends(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // edi

  EnterCriticalSection(this + 1);
  if ( HIDWORD(this[2].DebugInfo) )
  {
    v2 = -2147023901;
  }
  else
  {
    v2 = 0;
    LODWORD(this[2].LockSemaphore) = 1;
    if ( !this[2].RecursionCount
      || HIDWORD(this->OwningThread) >= LODWORD(this[2].OwningThread)
      || HIDWORD(this[2].OwningThread) )
    {
      HIDWORD(this[2].LockSemaphore) = 1;
    }
  }
  LeaveCriticalSection(this + 1);
  if ( v2 >= 0 )
    return (unsigned int)SEND_QUEUE::Send(this);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002250  mov     [rsp+arg_0], rbx
0x180002255  mov     [rsp+arg_8], rsi
0x18000225a  push    rdi
0x18000225b  sub     rsp, 20h
0x18000225f  mov     rbx, rcx
0x180002262  add     rcx, 28h ; '('; lpCriticalSection
0x180002266  call    cs:__imp_EnterCriticalSection
0x18000226c  cmp     dword ptr [rbx+54h], 0
0x180002270  jz      short loc_180002279
0x180002272  mov     edi, 800703E3h
0x180002277  jmp     short loc_180002296
0x180002279  xor     edi, edi
0x18000227b  lea     ecx, [rdi+1]
0x18000227e  mov     [rbx+68h], ecx
0x180002281  cmp     [rbx+5Ch], edi
0x180002284  jz      short loc_180002293
0x180002286  mov     eax, [rbx+60h]
0x180002289  cmp     [rbx+14h], eax
0x18000228c  jnb     short loc_180002293
0x18000228e  cmp     [rbx+64h], edi
0x180002291  jz      short loc_180002296
0x180002293  mov     [rbx+6Ch], ecx
0x180002296  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000229a  call    cs:__imp_LeaveCriticalSection
0x1800022a0  test    edi, edi
0x1800022a2  js      short loc_1800022AE
0x1800022a4  mov     rcx, rbx; this
0x1800022a7  call    ?Send@SEND_QUEUE@@AEAAJXZ; SEND_QUEUE::Send(void)
0x1800022ac  mov     edi, eax
0x1800022ae  mov     rbx, [rsp+28h+arg_0]
0x1800022b3  mov     eax, edi
0x1800022b5  mov     rsi, [rsp+28h+arg_8]
0x1800022ba  add     rsp, 20h
0x1800022be  pop     rdi
0x1800022bf  retn
```
