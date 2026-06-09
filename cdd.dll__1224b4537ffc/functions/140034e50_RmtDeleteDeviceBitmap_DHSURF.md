# RmtDeleteDeviceBitmap(DHSURF__ *)

- ea: `0x140034e50`
- end: `0x140034e7f`
- name: `?RmtDeleteDeviceBitmap@@YAXPEAUDHSURF__@@@Z`
- size: `47`
- prototype: `void __fastcall(struct DHSURF__ *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400372d0`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x140034e59`
- `WIN32K!W32GetSessionState` at `0x140034e59`

## pseudocode

```c
void __fastcall RmtDeleteDeviceBitmap(struct DHSURF__ *a1, __int64 a2)
{
  __int64 SessionState; // rax

  SessionState = W32GetSessionState(a1, a2);
  (*(void (__fastcall **)(struct DHSURF__ *))(*(_QWORD *)(SessionState + 72) + 928LL))(a1);
}

```

## disassembly

```asm
0x140034e50  push    rbx
0x140034e52  sub     rsp, 20h
0x140034e56  mov     rbx, rcx
0x140034e59  call    cs:__imp_W32GetSessionState
0x140034e60  nop     dword ptr [rax+rax+00h]
0x140034e65  mov     rcx, rbx
0x140034e68  mov     rdx, [rax+48h]
0x140034e6c  mov     rax, [rdx+3A0h]
0x140034e73  call    _guard_dispatch_icall
0x140034e78  add     rsp, 20h
0x140034e7c  pop     rbx
0x140034e7d  retn
```
