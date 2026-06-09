# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180004228`
- end: `0x1800042e3`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025d0`
- `0x180002b00`
- `0x180003158`

## callees

- `0x180004228`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180004228  mov     [rsp+arg_0], rbx
0x18000422d  mov     [rsp+arg_8], rdi
0x180004232  lea     rax, [rdx-1]
0x180004236  mov     r10d, 7FFFFFFEh
0x18000423c  mov     r9, rdx
0x18000423f  mov     rbx, rcx
0x180004242  cmp     rax, r10
0x180004245  ja      loc_1800042D1
0x18000424b  mov     r11, rdx
0x18000424e  mov     rax, rcx
0x180004251  xor     edi, edi
0x180004253  cmp     [rax], di
0x180004256  jz      short loc_180004262
0x180004258  add     rax, 2
0x18000425c  sub     r11, 1
0x180004260  jnz     short loc_180004253
0x180004262  mov     rax, r11
0x180004265  mov     rcx, r9
0x180004268  neg     rax
0x18000426b  mov     rax, r11
0x18000426e  sbb     edx, edx
0x180004270  sub     rcx, r11
0x180004273  not     edx
0x180004275  and     edx, 80070057h
0x18000427b  neg     rax
0x18000427e  sbb     rax, rax
0x180004281  and     rax, rcx
0x180004284  test    r11, r11
0x180004287  jz      short loc_1800042D6
0x180004289  sub     r9, rax
0x18000428c  lea     rax, [rbx+rax*2]
0x180004290  jz      short loc_1800042B4
0x180004292  test    r10, r10
0x180004295  jz      short loc_1800042B4
0x180004297  movzx   ecx, word ptr [r8]
0x18000429b  test    cx, cx
0x18000429e  jz      short loc_1800042B4
0x1800042a0  mov     [rax], cx
0x1800042a3  add     r8, 2
0x1800042a7  add     rax, 2
0x1800042ab  dec     r10
0x1800042ae  sub     r9, 1
0x1800042b2  jnz     short loc_180004292
0x1800042b4  test    r9, r9
0x1800042b7  lea     rcx, [rax-2]
0x1800042bb  cmovnz  rcx, rax
0x1800042bf  neg     r9
0x1800042c2  sbb     edx, edx
0x1800042c4  not     edx
0x1800042c6  and     edx, 8007007Ah
0x1800042cc  mov     [rcx], di
0x1800042cf  jmp     short loc_1800042D6
0x1800042d1  mov     edx, 80070057h
0x1800042d6  mov     rbx, [rsp+arg_0]
0x1800042db  mov     eax, edx
0x1800042dd  mov     rdi, [rsp+arg_8]
0x1800042e2  retn
```
