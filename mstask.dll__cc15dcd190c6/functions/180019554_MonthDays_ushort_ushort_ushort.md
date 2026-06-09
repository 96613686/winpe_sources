# MonthDays(ushort,ushort,ushort *)

- ea: `0x180019554`
- end: `0x1800195b0`
- name: `?MonthDays@@YAJGGPEAG@Z`
- size: `92`
- prototype: `__int64 __fastcall(unsigned __int16, unsigned __int16, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018c0`
- `0x18000e7f8`
- `0x18000eef4`
- `0x180019440`

## callees

- `0x1800194a4`
- `0x180019554`

## pseudocode

```c
__int64 __fastcall MonthDays(unsigned __int16 a1, unsigned __int16 a2, unsigned __int16 *a3)
{
  __int16 v4; // r11

  if ( (unsigned __int16)(a1 - 1) > 0xBu )
    return 2147942487LL;
  *a3 = byte_18001E798[a1];
  if ( a1 == 2 && a2 )
  {
    if ( (unsigned int)IsLeapYear(a2) )
      *a3 = v4 + 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180019554  mov     [rsp+arg_0], rbx
0x180019559  push    rdi
0x18001955a  sub     rsp, 20h
0x18001955e  lea     eax, [rcx-1]
0x180019561  mov     rbx, r8
0x180019564  cmp     ax, 0Bh
0x180019568  ja      short loc_1800195A0
0x18001956a  movzx   eax, cx
0x18001956d  lea     r8, byte_18001E798
0x180019574  movzx   r11d, byte ptr [rax+r8]
0x180019579  mov     [rbx], r11w
0x18001957d  cmp     cx, 2
0x180019581  jnz     short loc_18001959C
0x180019583  test    dx, dx
0x180019586  jz      short loc_18001959C
0x180019588  movzx   ecx, dx; unsigned __int16
0x18001958b  call    ?IsLeapYear@@YAHG@Z; IsLeapYear(ushort)
0x180019590  test    eax, eax
0x180019592  jz      short loc_18001959C
0x180019594  inc     r11w
0x180019598  mov     [rbx], r11w
0x18001959c  xor     eax, eax
0x18001959e  jmp     short loc_1800195A5
0x1800195a0  mov     eax, 80070057h
0x1800195a5  mov     rbx, [rsp+28h+arg_0]
0x1800195aa  add     rsp, 20h
0x1800195ae  pop     rdi
0x1800195af  retn
```
