# NbtTdiCompletionRoutine

- ea: `0x1400178f0`
- end: `0x14001794d`
- name: `NbtTdiCompletionRoutine`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400178f0`
- `0x1400401c4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140017910`
- `ntoskrnl!KeSetEvent` at `0x140017910`

## pseudocode

```c
__int64 __fastcall NbtTdiCompletionRoutine(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  if ( (xmmword_140038420 & 0x10) != 0 )
    WPP_SF_qqq(1028, 20, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids, a3, a2, a1);
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400178f0  push    rbx
0x1400178f2  sub     rsp, 30h
0x1400178f6  mov     rbx, r8
0x1400178f9  mov     r9, rcx
0x1400178fc  mov     r8, rdx
0x1400178ff  test    byte ptr cs:xmmword_140038420, 10h
0x140017906  jnz     short loc_140017928
0x140017908  xor     r8d, r8d; Wait
0x14001790b  xor     edx, edx; Increment
0x14001790d  mov     rcx, rbx; Event
0x140017910  call    cs:__imp_KeSetEvent
0x140017917  nop     dword ptr [rax+rax+00h]
0x14001791c  mov     eax, 0C0000016h
0x140017921  add     rsp, 30h
0x140017925  pop     rbx
0x140017926  retn
0x140017928  mov     [rsp+38h+var_10], r9
0x14001792d  mov     edx, 14h
0x140017932  mov     [rsp+38h+var_18], r8
0x140017937  mov     ecx, 404h
0x14001793c  lea     r8, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids
0x140017943  mov     r9, rbx
0x140017946  call    WPP_SF_qqq
0x14001794b  jmp     short loc_140017908
```
