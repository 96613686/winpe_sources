# CAOIDAllocAndCopy(ushort *,ushort * *)

- ea: `0x18002a5d0`
- end: `0x18002a662`
- name: `?CAOIDAllocAndCopy@@YAJPEAGPEAPEAG@Z`
- size: `146`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18002a668`
- `0x18002ab94`
- `0x18002c24c`

## callees

- `0x180005f00`
- `0x180011158`
- `0x18002a5d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a626`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a626`

## pseudocode

```c
__int64 __fastcall CAOIDAllocAndCopy(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rdi
  unsigned __int16 *v6; // rax
  SIZE_T uBytes; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || !a1 )
    return 2147942487LL;
  uBytes = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v5 = v4 + 1;
  if ( v4 + 1 < v4 || (int)ULongLongMult(v4 + 1, 2u, &uBytes) < 0 )
    return 2147942934LL;
  v6 = (unsigned __int16 *)LocalAlloc(0x40u, uBytes);
  *a2 = v6;
  if ( !v6 )
    return 2147942414LL;
  StringCchCopyW(v6, v5, a1);
  return 0;
}

```

## disassembly

```asm
0x18002a5d0  push    rbx
0x18002a5d2  push    rbp
0x18002a5d3  push    rsi
0x18002a5d4  push    rdi
0x18002a5d5  sub     rsp, 28h
0x18002a5d9  xor     ebp, ebp
0x18002a5db  mov     rsi, rdx
0x18002a5de  mov     rbx, rcx
0x18002a5e1  test    rdx, rdx
0x18002a5e4  jz      short loc_18002A654
0x18002a5e6  test    rcx, rcx
0x18002a5e9  jz      short loc_18002A654
0x18002a5eb  mov     [rsp+48h+uBytes], rbp
0x18002a5f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a5f4  inc     rax
0x18002a5f7  cmp     [rcx+rax*2], bp
0x18002a5fb  jnz     short loc_18002A5F4
0x18002a5fd  lea     rdi, [rax+1]
0x18002a601  cmp     rdi, rax
0x18002a604  jb      short loc_18002A64D
0x18002a606  lea     r8, [rsp+48h+uBytes]; unsigned __int64 *
0x18002a60b  mov     edx, 2; unsigned __int64
0x18002a610  mov     rcx, rdi; unsigned __int64
0x18002a613  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002a618  test    eax, eax
0x18002a61a  js      short loc_18002A64D
0x18002a61c  mov     rdx, [rsp+48h+uBytes]; uBytes
0x18002a621  mov     ecx, 40h ; '@'; uFlags
0x18002a626  call    cs:__imp_LocalAlloc
0x18002a62c  mov     [rsi], rax
0x18002a62f  test    rax, rax
0x18002a632  jnz     short loc_18002A63B
0x18002a634  mov     eax, 8007000Eh
0x18002a639  jmp     short loc_18002A659
0x18002a63b  mov     r8, rbx; unsigned __int16 *
0x18002a63e  mov     rdx, rdi; unsigned __int64
0x18002a641  mov     rcx, rax; unsigned __int16 *
0x18002a644  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a649  xor     eax, eax
0x18002a64b  jmp     short loc_18002A659
0x18002a64d  mov     eax, 80070216h
0x18002a652  jmp     short loc_18002A659
0x18002a654  mov     eax, 80070057h
0x18002a659  add     rsp, 28h
0x18002a65d  pop     rdi
0x18002a65e  pop     rsi
0x18002a65f  pop     rbp
0x18002a660  pop     rbx
0x18002a661  retn
```
