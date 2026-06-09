# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006f90`
- end: `0x180007037`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `167`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180009490`
- `0x18000beb8`
- `0x18000c4dc`
- `0x18000c78c`
- `0x18000c93c`
- `0x18000cdcc`
- `0x18000cff4`
- `0x18000e578`
- `0x18000e7f8`
- `0x180013504`
- `0x1800135a4`
- `0x180019d4c`

## callees

- `0x180006f90`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v4; // r9
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rax
  __int64 v7; // rdx
  unsigned __int16 *v8; // rcx
  __int64 result; // rax

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
    return 2147942487LL;
  v4 = a2;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  if ( !v4 )
    return 2147942487LL;
  v6 = &a1[a2 - v4];
  v7 = v4;
  do
  {
    if ( !v3 )
      break;
    if ( !*a3 )
      break;
    *v6++ = *a3++;
    --v3;
    --v7;
  }
  while ( v7 );
  v8 = v6 - 1;
  if ( v7 )
    v8 = v6;
  *v8 = 0;
  result = 2147942522LL;
  if ( v7 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180006f90  mov     [rsp+arg_0], rbx
0x180006f95  lea     rax, [rdx-1]
0x180006f99  mov     r10d, 7FFFFFFEh
0x180006f9f  mov     rbx, rcx
0x180006fa2  cmp     rax, r10
0x180006fa5  ja      loc_18000702F
0x180006fab  mov     r9, rdx
0x180006fae  mov     rax, rcx
0x180006fb1  cmp     word ptr [rax], 0
0x180006fb5  jz      short loc_180006FC1
0x180006fb7  add     rax, 2
0x180006fbb  sub     r9, 1
0x180006fbf  jnz     short loc_180006FB1
0x180006fc1  xor     eax, eax
0x180006fc3  mov     rcx, rdx
0x180006fc6  sub     rcx, r9
0x180006fc9  mov     r11d, 80070057h
0x180006fcf  test    r9, r9
0x180006fd2  cmovz   rcx, rax
0x180006fd6  cmovnz  r11d, eax
0x180006fda  jz      short loc_18000702A
0x180006fdc  lea     rax, [rbx+rcx*2]
0x180006fe0  sub     rdx, rcx
0x180006fe3  jz      short loc_180007007
0x180006fe5  test    r10, r10
0x180006fe8  jz      short loc_180007007
0x180006fea  movzx   ecx, word ptr [r8]
0x180006fee  test    cx, cx
0x180006ff1  jz      short loc_180007007
0x180006ff3  mov     [rax], cx
0x180006ff6  add     r8, 2
0x180006ffa  add     rax, 2
0x180006ffe  dec     r10
0x180007001  sub     rdx, 1
0x180007005  jnz     short loc_180006FE5
0x180007007  lea     rcx, [rax-2]
0x18000700b  test    rdx, rdx
0x18000700e  cmovnz  rcx, rax
0x180007012  xor     eax, eax
0x180007014  mov     [rcx], ax
0x180007017  xor     ecx, ecx
0x180007019  test    rdx, rdx
0x18000701c  mov     eax, 8007007Ah
0x180007021  cmovnz  eax, ecx
0x180007024  mov     rbx, [rsp+arg_0]
0x180007029  retn
0x18000702a  mov     eax, r11d
0x18000702d  jmp     short loc_180007024
0x18000702f  mov     r11d, 80070057h
0x180007035  jmp     short loc_18000702A
```
