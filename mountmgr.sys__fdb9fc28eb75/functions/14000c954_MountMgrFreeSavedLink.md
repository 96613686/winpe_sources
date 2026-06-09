# MountMgrFreeSavedLink

- ea: `0x14000c954`
- end: `0x14000c9f1`
- name: `MountMgrFreeSavedLink`
- size: `157`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14000d7a0`
- `0x140014fc0`

## callees

- `0x14000c954`
- `0x140018cd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c997`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c997`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9d4`

## pseudocode

```c
void __fastcall MountMgrFreeSavedLink(PVOID *P)
{
  void **v2; // rdi
  void *v3; // rbx
  void **v4; // rax

  v2 = P + 2;
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    if ( *((void ***)v3 + 1) != v2 || (v4 = *(void ***)v3, *(void **)(*(_QWORD *)v3 + 8LL) != v3) )
      __fastfail(3u);
    *v2 = v4;
    v4[1] = v2;
    GlobalDeleteSymbolicLink((__int64)v3 + 24);
    ExFreePoolWithTag(*((PVOID *)v3 + 4), 0);
    ExFreePoolWithTag(v3, 0);
  }
  ExFreePoolWithTag(P[4], 0);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000c954  mov     [rsp+arg_0], rbx
0x14000c959  mov     [rsp+arg_8], rsi
0x14000c95e  push    rdi
0x14000c95f  sub     rsp, 20h
0x14000c963  mov     rsi, rcx
0x14000c966  lea     rdi, [rcx+10h]
0x14000c96a  mov     rbx, [rdi]
0x14000c96d  cmp     rbx, rdi
0x14000c970  jz      short loc_14000C9BD
0x14000c972  cmp     [rbx+8], rdi
0x14000c976  jnz     short loc_14000C9B6
0x14000c978  mov     rax, [rbx]
0x14000c97b  cmp     [rax+8], rbx
0x14000c97f  jnz     short loc_14000C9B6
0x14000c981  mov     [rdi], rax
0x14000c984  lea     rcx, [rbx+18h]
0x14000c988  mov     [rax+8], rdi
0x14000c98c  call    GlobalDeleteSymbolicLink
0x14000c991  mov     rcx, [rbx+20h]; P
0x14000c995  xor     edx, edx; Tag
0x14000c997  call    cs:__imp_ExFreePoolWithTag
0x14000c99e  nop     dword ptr [rax+rax+00h]
0x14000c9a3  xor     edx, edx; Tag
0x14000c9a5  mov     rcx, rbx; P
0x14000c9a8  call    cs:__imp_ExFreePoolWithTag
0x14000c9af  nop     dword ptr [rax+rax+00h]
0x14000c9b4  jmp     short loc_14000C96A
0x14000c9b6  mov     ecx, 3
0x14000c9bb  int     29h; Win8: RtlFailFast(ecx)
0x14000c9bd  mov     rcx, [rsi+20h]; P
0x14000c9c1  xor     edx, edx; Tag
0x14000c9c3  call    cs:__imp_ExFreePoolWithTag
0x14000c9ca  nop     dword ptr [rax+rax+00h]
0x14000c9cf  xor     edx, edx; Tag
0x14000c9d1  mov     rcx, rsi; P
0x14000c9d4  call    cs:__imp_ExFreePoolWithTag
0x14000c9db  nop     dword ptr [rax+rax+00h]
0x14000c9e0  mov     rbx, [rsp+28h+arg_0]
0x14000c9e5  mov     rsi, [rsp+28h+arg_8]
0x14000c9ea  add     rsp, 20h
0x14000c9ee  pop     rdi
0x14000c9ef  retn
```
