# LuafvInsertElementTableFull

- ea: `0x14001cf78`
- end: `0x14001d00a`
- name: `LuafvInsertElementTableFull`
- size: `146`
- prototype: `struct _RTL_SPLAY_LINKS *__fastcall(__int64, struct _RTL_SPLAY_LINKS *, bool *, struct _RTL_SPLAY_LINKS *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001ce44`

## callees

- `0x14001cf78`

## import_xrefs

- `ntoskrnl!RtlSplay` at `0x14001cfc6`
- `ntoskrnl!RtlSplay` at `0x14001cfc6`

## pseudocode

```c
struct _RTL_SPLAY_LINKS *__fastcall LuafvInsertElementTableFull(
        __int64 a1,
        struct _RTL_SPLAY_LINKS *a2,
        bool *a3,
        struct _RTL_SPLAY_LINKS *a4,
        int a5)
{
  struct _RTL_SPLAY_LINKS *v6; // rbx

  v6 = a2;
  if ( a5 == 1 )
  {
    v6 = a4;
  }
  else
  {
    a2->Parent = a2;
    a2->LeftChild = 0;
    a2->RightChild = 0;
    ++*(_DWORD *)(a1 + 16);
    if ( a5 )
    {
      if ( a5 == 2 )
        a4->LeftChild = a2;
      else
        a4->RightChild = a2;
      a2->Parent = a4;
    }
    else
    {
      *(_QWORD *)a1 = a2;
    }
  }
  *(_QWORD *)a1 = RtlSplay(v6);
  if ( a3 )
    *a3 = a5 != 1;
  return v6;
}

```

## disassembly

```asm
0x14001cf78  mov     [rsp+arg_0], rbx
0x14001cf7d  mov     [rsp+arg_8], rdi
0x14001cf82  push    r14
0x14001cf84  sub     rsp, 20h
0x14001cf88  cmp     [rsp+28h+arg_20], 1
0x14001cf8d  mov     r14, r8
0x14001cf90  mov     rbx, rdx
0x14001cf93  mov     rdi, rcx
0x14001cf96  jz      short loc_14001D000
0x14001cf98  mov     [rdx], rdx
0x14001cf9b  mov     qword ptr [rdx+8], 0
0x14001cfa3  mov     qword ptr [rdx+10h], 0
0x14001cfab  inc     dword ptr [rcx+10h]
0x14001cfae  cmp     [rsp+28h+arg_20], 0
0x14001cfb3  jz      short loc_14001D005
0x14001cfb5  cmp     [rsp+28h+arg_20], 2
0x14001cfba  jnz     short loc_14001CFFA
0x14001cfbc  mov     [r9+8], rdx
0x14001cfc0  mov     [rdx], r9
0x14001cfc3  mov     rcx, rbx; Links
0x14001cfc6  call    cs:__imp_RtlSplay
0x14001cfcd  nop     dword ptr [rax+rax+00h]
0x14001cfd2  mov     [rdi], rax
0x14001cfd5  test    r14, r14
0x14001cfd8  jz      short loc_14001CFE5
0x14001cfda  cmp     [rsp+28h+arg_20], 1
0x14001cfdf  setnz   cl
0x14001cfe2  mov     [r14], cl
0x14001cfe5  mov     rdi, [rsp+28h+arg_8]
0x14001cfea  mov     rax, rbx
0x14001cfed  mov     rbx, [rsp+28h+arg_0]
0x14001cff2  add     rsp, 20h
0x14001cff6  pop     r14
0x14001cff8  retn
0x14001cffa  mov     [r9+10h], rdx
0x14001cffe  jmp     short loc_14001CFC0
0x14001d000  mov     rbx, r9
0x14001d003  jmp     short loc_14001CFC3
0x14001d005  mov     [rcx], rdx
0x14001d008  jmp     short loc_14001CFC3
```
