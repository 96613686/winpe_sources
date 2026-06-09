# LuafvUnlinkFsContextFromDvfcb

- ea: `0x1400142a8`
- end: `0x140014325`
- name: `LuafvUnlinkFsContextFromDvfcb`
- size: `125`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140020400`

## callees

- `0x1400142a8`
- `0x14001432c`

## import_xrefs

- `FLTMGR!FltReleasePushLockEx` at `0x1400142f9`
- `FLTMGR!FltReleasePushLockEx` at `0x1400142f9`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400142c7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400142c7`

## pseudocode

```c
__int64 __fastcall LuafvUnlinkFsContextFromDvfcb(__int64 a1)
{
  __int64 v1; // rdi
  _QWORD *v3; // rbx
  __int64 v4; // rdx
  _QWORD *v5; // rax

  v1 = *(_QWORD *)(a1 + 192);
  FltAcquirePushLockExclusiveEx(v1 + 64, 0);
  v3 = (_QWORD *)(a1 + 176);
  v4 = *v3;
  if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
    __fastfail(3u);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  FltReleasePushLockEx(v1 + 64, 0);
  return DereferenceDvfcb(v1);
}

```

## disassembly

```asm
0x1400142a8  mov     [rsp+arg_0], rbx
0x1400142ad  mov     [rsp+arg_8], rsi
0x1400142b2  push    rdi
0x1400142b3  sub     rsp, 20h
0x1400142b7  mov     rdi, [rcx+0C0h]
0x1400142be  mov     rbx, rcx
0x1400142c1  xor     edx, edx
0x1400142c3  lea     rcx, [rdi+40h]
0x1400142c7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400142ce  nop     dword ptr [rax+rax+00h]
0x1400142d3  add     rbx, 0B0h
0x1400142da  mov     rdx, [rbx]
0x1400142dd  cmp     [rdx+8], rbx
0x1400142e1  jnz     short loc_14001431E
0x1400142e3  mov     rax, [rbx+8]
0x1400142e7  cmp     [rax], rbx
0x1400142ea  jnz     short loc_14001431E
0x1400142ec  mov     [rax], rdx
0x1400142ef  lea     rcx, [rdi+40h]
0x1400142f3  mov     [rdx+8], rax
0x1400142f7  xor     edx, edx
0x1400142f9  call    cs:__imp_FltReleasePushLockEx
0x140014300  nop     dword ptr [rax+rax+00h]
0x140014305  mov     rcx, rdi
0x140014308  call    DereferenceDvfcb
0x14001430d  mov     rbx, [rsp+28h+arg_0]
0x140014312  mov     rsi, [rsp+28h+arg_8]
0x140014317  add     rsp, 20h
0x14001431b  pop     rdi
0x14001431c  retn
0x14001431e  mov     ecx, 3
0x140014323  int     29h; Win8: RtlFailFast(ecx)
```
