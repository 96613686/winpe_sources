# RmtCreateDeviceBitmap(DHPDEV__ *,tagSIZE,ulong)

- ea: `0x140034c70`
- end: `0x140034cbe`
- name: `?RmtCreateDeviceBitmap@@YAPEAUHBITMAP__@@PEAUDHPDEV__@@UtagSIZE@@K@Z`
- size: `78`
- prototype: `HBITMAP __fastcall(struct DHPDEV__ *, struct tagSIZE, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400372d0`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x140034c88`
- `WIN32K!W32GetSessionState` at `0x140034c88`

## pseudocode

```c
__int64 __fastcall RmtCreateDeviceBitmap(struct DHPDEV__ *a1, struct tagSIZE a2, unsigned int a3)
{
  __int64 v6; // rax

  v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD))W32GetSessionState)(a1, a2);
  return (*(__int64 (__fastcall **)(_QWORD, struct tagSIZE, _QWORD))(*(_QWORD *)(v6 + 72) + 920LL))(
           *(_QWORD *)a1,
           a2,
           a3);
}

```

## disassembly

```asm
0x140034c70  mov     [rsp+arg_0], rbx
0x140034c75  mov     [rsp+arg_8], rsi
0x140034c7a  push    rdi
0x140034c7b  sub     rsp, 20h
0x140034c7f  mov     edi, r8d
0x140034c82  mov     rbx, rdx
0x140034c85  mov     rsi, rcx
0x140034c88  call    cs:__imp_W32GetSessionState
0x140034c8f  nop     dword ptr [rax+rax+00h]
0x140034c94  mov     rcx, [rsi]
0x140034c97  mov     r8d, edi
0x140034c9a  mov     rdx, [rax+48h]
0x140034c9e  mov     rax, [rdx+398h]
0x140034ca5  mov     rdx, rbx
0x140034ca8  call    _guard_dispatch_icall
0x140034cad  mov     rbx, [rsp+28h+arg_0]
0x140034cb2  mov     rsi, [rsp+28h+arg_8]
0x140034cb7  add     rsp, 20h
0x140034cbb  pop     rdi
0x140034cbc  retn
```
