# LdrpTouchThreadStack

- ea: `0x1800d5cac`
- end: `0x1800d5d60`
- name: `LdrpTouchThreadStack`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800d5d68`

## callees

- `0x1800d5cac`
- `0x18015ae38`
- `0x18015e730`

## string_xrefs

- `0x180167a8d`: `LdrpTouchThreadStack`

## pseudocode

```c
__int64 __fastcall LdrpTouchThreadStack(unsigned __int64 a1)
{
  struct _TEB *v2; // rdi
  __int64 result; // rax
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  _QWORD v6[8]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v7; // [rsp+88h] [rbp+10h] BYREF

  memset(v6, 0, 48);
  v7 = 0;
  v2 = NtCurrentTeb();
  result = ZwQueryVirtualMemory(-1, v2->NtTib.StackLimit, 0, v6, 48, &v7);
  if ( (int)result >= 0 )
  {
    v4 = (unsigned __int64)v2->NtTib.StackBase - 4096;
    if ( v4 > a1 )
    {
      v5 = v4 - a1;
      if ( v4 - a1 <= v6[1] + 12288LL )
        v5 = v6[1] + 12288LL;
    }
    else
    {
      v5 = v6[1] + 12288LL;
    }
    while ( v4 >= v5 )
      v4 -= 4096LL;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800d5cac  mov     rax, rsp
0x1800d5caf  mov     [rax+8], rbx
0x1800d5cb3  push    rdi
0x1800d5cb4  sub     rsp, 70h
0x1800d5cb8  mov     rbx, rcx
0x1800d5cbb  xorps   xmm0, xmm0
0x1800d5cbe  movups  xmmword ptr [rax-40h], xmm0
0x1800d5cc2  movups  xmmword ptr [rax-30h], xmm0
0x1800d5cc6  movups  xmmword ptr [rax-20h], xmm0
0x1800d5cca  mov     qword ptr [rax+10h], 0
0x1800d5cd2  mov     rdi, gs:30h
0x1800d5cdb  lea     rax, [rax+10h]
0x1800d5cdf  mov     [rsp+78h+var_50], rax
0x1800d5ce4  mov     [rsp+78h+var_58], 30h ; '0'
0x1800d5ced  lea     r9, [rsp+78h+var_40]
0x1800d5cf2  xor     r8d, r8d
0x1800d5cf5  mov     rdx, [rdi+10h]
0x1800d5cf9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800d5cfd  call    ZwQueryVirtualMemory
0x1800d5d02  test    eax, eax
0x1800d5d04  js      short loc_1800D5D42
0x1800d5d06  mov     rax, [rsp+78h+var_38]
0x1800d5d0b  add     rax, 3000h
0x1800d5d11  mov     rcx, [rdi+8]
0x1800d5d15  mov     r8d, 1000h
0x1800d5d1b  sub     rcx, r8
0x1800d5d1e  cmp     rcx, rbx
0x1800d5d21  ja      short loc_1800D5D51
0x1800d5d23  mov     rdx, rax
0x1800d5d26  cmp     rcx, rdx
0x1800d5d29  jb      short loc_1800D5D37
0x1800d5d2b  mov     eax, [rcx]
0x1800d5d2d  sub     rcx, r8
0x1800d5d30  mov     [rsp+78h+var_48], rcx
0x1800d5d35  jmp     short loc_1800D5D26
0x1800d5d37  jmp     short loc_1800D5D40
0x1800d5d39  mov     eax, 0C0000017h
0x1800d5d3e  jmp     short loc_1800D5D42
0x1800d5d40  xor     eax, eax
0x1800d5d42  mov     rbx, [rsp+78h+arg_0]
0x1800d5d4a  add     rsp, 70h
0x1800d5d4e  pop     rdi
0x1800d5d4f  retn
0x1800d5d51  mov     rdx, rcx
0x1800d5d54  sub     rdx, rbx
0x1800d5d57  cmp     rdx, rax
0x1800d5d5a  cmovbe  rdx, rax
0x1800d5d5e  jmp     short loc_1800D5D26
0x180167a84  push    rbp
0x180167a86  sub     rsp, 30h
0x180167a8a  mov     rbp, rdx
0x180167a8d  lea     rdx, aLdrptouchthrea; "LdrpTouchThreadStack"
0x180167a94  call    LdrpGenericExceptionFilter
0x180167a99  nop
0x180167a9a  add     rsp, 30h
0x180167a9e  pop     rbp
0x180167a9f  retn
```
