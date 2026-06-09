# FIPfNotifiedContextsDelete

- ea: `0x14001645c`
- end: `0x14001648e`
- name: `FIPfNotifiedContextsDelete`
- size: `50`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140015a48`
- `0x14001606c`

## callees

- `0x140003a00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001647b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001647b`

## pseudocode

```c
void __fastcall FIPfNotifiedContextsDelete(void (__fastcall **P)(_QWORD, _QWORD))
{
  P[4](P[3], P[5]);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14001645c  push    rbx
0x14001645e  sub     rsp, 20h
0x140016462  mov     rax, [rcx+20h]
0x140016466  mov     rbx, rcx
0x140016469  mov     rdx, [rcx+28h]
0x14001646d  mov     rcx, [rcx+18h]
0x140016471  call    _guard_dispatch_icall
0x140016476  xor     edx, edx; Tag
0x140016478  mov     rcx, rbx; P
0x14001647b  call    cs:__imp_ExFreePoolWithTag
0x140016482  nop     dword ptr [rax+rax+00h]
0x140016487  add     rsp, 20h
0x14001648b  pop     rbx
0x14001648c  retn
```
