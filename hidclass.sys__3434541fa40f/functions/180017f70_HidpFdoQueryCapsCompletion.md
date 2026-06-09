# HidpFdoQueryCapsCompletion

- ea: `0x180017f70`
- end: `0x180017f95`
- name: `HidpFdoQueryCapsCompletion`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x180017f7e`
- `ntoskrnl!KeSetEvent` at `0x180017f7e`

## pseudocode

```c
__int64 __fastcall HidpFdoQueryCapsCompletion(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 1, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x180017f70  sub     rsp, 28h
0x180017f74  mov     rcx, r8; Event
0x180017f77  xor     r8d, r8d; Wait
0x180017f7a  lea     edx, [r8+1]; Increment
0x180017f7e  call    cs:__imp_KeSetEvent
0x180017f85  nop     dword ptr [rax+rax+00h]
0x180017f8a  mov     eax, 0C0000016h
0x180017f8f  add     rsp, 28h
0x180017f93  retn
```
