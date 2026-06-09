# CMasterClock::CreateDefaultMasterClock(IReferenceClock * *)

- ea: `0x18000a974`
- end: `0x18000aa14`
- name: `?CreateDefaultMasterClock@CMasterClock@@QEAAJPEAPEAUIReferenceClock@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(CMasterClock *__hidden this, struct IReferenceClock **)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001a840`
- `0x18001c7f0`
- `0x18001f51c`

## callees

- `0x18000a974`
- `0x18000b274`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a9fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a9fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a990`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a990`

## pseudocode

```c
__int64 __fastcall CMasterClock::CreateDefaultMasterClock(HANDLE *this, struct IReferenceClock **a2)
{
  char *v4; // rdi
  unsigned int v5; // edi
  __int64 v6; // rax

  WaitForSingleObject(this[13], 0xFFFFFFFF);
  v4 = (char *)(this + 4);
  if ( !(*((__int64 (__fastcall **)(char *))this[4] + 5))((char *)this + 32) )
    CMasterClock::UpdateClockList((CMasterClock *)this);
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 40LL))((char *)this + 32) )
  {
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 40LL))((char *)this + 32);
    v5 = (*(__int64 (__fastcall **)(struct IReferenceClock **, HANDLE *))(*(_QWORD *)(v6 + 16) + 288LL))(a2, this);
  }
  else
  {
    v5 = -2147467262;
  }
  ReleaseMutex(this[13]);
  return v5;
}

```

## disassembly

```asm
0x18000a974  mov     [rsp+arg_0], rbx
0x18000a979  mov     [rsp+arg_8], rsi
0x18000a97e  push    rdi
0x18000a97f  sub     rsp, 20h
0x18000a983  mov     rsi, rdx
0x18000a986  mov     rbx, rcx
0x18000a989  mov     rcx, [rcx+68h]; hHandle
0x18000a98d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a990  call    cs:__imp_WaitForSingleObject
0x18000a996  lea     rdi, [rbx+20h]
0x18000a99a  mov     rax, [rdi]
0x18000a99d  mov     rcx, rdi
0x18000a9a0  mov     rax, [rax+28h]
0x18000a9a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9a9  test    rax, rax
0x18000a9ac  jnz     short loc_18000A9B6
0x18000a9ae  mov     rcx, rbx; this
0x18000a9b1  call    ?UpdateClockList@CMasterClock@@AEAAJXZ; CMasterClock::UpdateClockList(void)
0x18000a9b6  mov     rax, [rdi]
0x18000a9b9  mov     rcx, rdi
0x18000a9bc  mov     rax, [rax+28h]
0x18000a9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9c5  test    rax, rax
0x18000a9c8  jnz     short loc_18000A9D1
0x18000a9ca  mov     edi, 80004002h
0x18000a9cf  jmp     short loc_18000A9F8
0x18000a9d1  mov     rax, [rdi]
0x18000a9d4  mov     rcx, rdi
0x18000a9d7  mov     rax, [rax+28h]
0x18000a9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e0  mov     rdx, rbx
0x18000a9e3  mov     rcx, [rax+10h]
0x18000a9e7  mov     rax, [rcx+120h]
0x18000a9ee  mov     rcx, rsi
0x18000a9f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9f6  mov     edi, eax
0x18000a9f8  mov     rcx, [rbx+68h]; hMutex
0x18000a9fc  call    cs:__imp_ReleaseMutex
0x18000aa02  mov     rbx, [rsp+28h+arg_0]
0x18000aa07  mov     eax, edi
0x18000aa09  mov     rsi, [rsp+28h+arg_8]
0x18000aa0e  add     rsp, 20h
0x18000aa12  pop     rdi
0x18000aa13  retn
```
