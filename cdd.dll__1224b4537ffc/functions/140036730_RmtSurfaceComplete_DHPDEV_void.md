# RmtSurfaceComplete(DHPDEV__ *,void *)

- ea: `0x140036730`
- end: `0x14003676f`
- name: `?RmtSurfaceComplete@@YAHPEAUDHPDEV__@@PEAX@Z`
- size: `63`
- prototype: `__int64 __fastcall(struct DHPDEV__ *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400372d0`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x140036740`
- `WIN32K!W32GetSessionState` at `0x140036740`

## pseudocode

```c
__int64 __fastcall RmtSurfaceComplete(struct DHPDEV__ *a1, void *a2)
{
  __int64 SessionState; // rax

  SessionState = W32GetSessionState(a1, a2);
  return (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)(SessionState + 72) + 832LL))(*((_QWORD *)a1 + 1), a2);
}

```

## disassembly

```asm
0x140036730  mov     [rsp+arg_0], rbx
0x140036735  push    rdi
0x140036736  sub     rsp, 20h
0x14003673a  mov     rbx, rdx
0x14003673d  mov     rdi, rcx
0x140036740  call    cs:__imp_W32GetSessionState
0x140036747  nop     dword ptr [rax+rax+00h]
0x14003674c  mov     rcx, [rdi+8]
0x140036750  mov     rdx, rbx
0x140036753  mov     r8, [rax+48h]
0x140036757  mov     rax, [r8+340h]
0x14003675e  call    _guard_dispatch_icall
0x140036763  mov     rbx, [rsp+28h+arg_0]
0x140036768  add     rsp, 20h
0x14003676c  pop     rdi
0x14003676d  retn
```
