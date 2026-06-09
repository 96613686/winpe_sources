# CGhostProcess::RemoveGhostWindow(CGhostWindow *)

- ea: `0x180009518`
- end: `0x180009578`
- name: `?RemoveGhostWindow@CGhostProcess@@QEAAJPEAVCGhostWindow@@@Z`
- size: `96`
- prototype: `__int64 __fastcall(CGhostProcess *__hidden this, struct CGhostWindow *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800075a0`

## callees

- `0x180008ea0`
- `0x180008fb4`
- `0x1800094b8`
- `0x180009518`
- `0x180009f60`
- `0x180009f70`

## pseudocode

```c
__int64 __fastcall CGhostProcess::RemoveGhostWindow(CGhostProcess *this, struct CGhostWindow *a2)
{
  unsigned __int32 v3; // edi

  v3 = _InterlockedDecrement((volatile signed __int32 *)this + 15);
  if ( !v3 )
  {
    CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
    CGhostProcess::DestroySiblingFrostWindows(this);
    if ( *((_DWORD *)this + 28) )
      CGhostProcess::CancelHangReporting(this);
    CGhostProcess::ReleaseCurrentWerDlgOwner(this);
    CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
  }
  return v3;
}

```

## disassembly

```asm
0x180009518  mov     [rsp+arg_0], rbx
0x18000951d  mov     [rsp+arg_8], rsi
0x180009522  push    rdi
0x180009523  sub     rsp, 20h
0x180009527  mov     rbx, rcx
0x18000952a  or      edi, 0FFFFFFFFh
0x18000952d  lock xadd [rcx+3Ch], edi
0x180009532  sub     edi, 1
0x180009535  jnz     short loc_180009566
0x180009537  add     rcx, 10h; lpCriticalSection
0x18000953b  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180009540  mov     rcx, rbx; this
0x180009543  call    ?DestroySiblingFrostWindows@CGhostProcess@@AEAAHXZ; CGhostProcess::DestroySiblingFrostWindows(void)
0x180009548  cmp     [rbx+70h], edi
0x18000954b  jz      short loc_180009555
0x18000954d  mov     rcx, rbx; this
0x180009550  call    ?CancelHangReporting@CGhostProcess@@AEAAHXZ; CGhostProcess::CancelHangReporting(void)
0x180009555  mov     rcx, rbx; this
0x180009558  call    ?ReleaseCurrentWerDlgOwner@CGhostProcess@@AEAAHXZ; CGhostProcess::ReleaseCurrentWerDlgOwner(void)
0x18000955d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180009561  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180009566  mov     rbx, [rsp+28h+arg_0]
0x18000956b  mov     eax, edi
0x18000956d  mov     rsi, [rsp+28h+arg_8]
0x180009572  add     rsp, 20h
0x180009576  pop     rdi
0x180009577  retn
```
