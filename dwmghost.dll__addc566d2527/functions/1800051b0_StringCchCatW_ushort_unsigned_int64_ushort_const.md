# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800051b0`
- end: `0x18000526b`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000385c`
- `0x180005300`
- `0x1800060e0`

## callees

- `0x1800051b0`

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
0x1800051b0  mov     [rsp+arg_0], rbx
0x1800051b5  mov     [rsp+arg_8], rdi
0x1800051ba  lea     rax, [rdx-1]
0x1800051be  mov     r10d, 7FFFFFFEh
0x1800051c4  mov     r9, rdx
0x1800051c7  mov     rbx, rcx
0x1800051ca  cmp     rax, r10
0x1800051cd  ja      loc_180005259
0x1800051d3  mov     r11, rdx
0x1800051d6  mov     rax, rcx
0x1800051d9  xor     edi, edi
0x1800051db  cmp     [rax], di
0x1800051de  jz      short loc_1800051EA
0x1800051e0  add     rax, 2
0x1800051e4  sub     r11, 1
0x1800051e8  jnz     short loc_1800051DB
0x1800051ea  mov     rax, r11
0x1800051ed  mov     rcx, r9
0x1800051f0  neg     rax
0x1800051f3  mov     rax, r11
0x1800051f6  sbb     edx, edx
0x1800051f8  sub     rcx, r11
0x1800051fb  not     edx
0x1800051fd  and     edx, 80070057h
0x180005203  neg     rax
0x180005206  sbb     rax, rax
0x180005209  and     rax, rcx
0x18000520c  test    r11, r11
0x18000520f  jz      short loc_18000525E
0x180005211  sub     r9, rax
0x180005214  lea     rax, [rbx+rax*2]
0x180005218  jz      short loc_18000523C
0x18000521a  test    r10, r10
0x18000521d  jz      short loc_18000523C
0x18000521f  movzx   ecx, word ptr [r8]
0x180005223  test    cx, cx
0x180005226  jz      short loc_18000523C
0x180005228  mov     [rax], cx
0x18000522b  add     r8, 2
0x18000522f  add     rax, 2
0x180005233  dec     r10
0x180005236  sub     r9, 1
0x18000523a  jnz     short loc_18000521A
0x18000523c  test    r9, r9
0x18000523f  lea     rcx, [rax-2]
0x180005243  cmovnz  rcx, rax
0x180005247  neg     r9
0x18000524a  sbb     edx, edx
0x18000524c  not     edx
0x18000524e  and     edx, 8007007Ah
0x180005254  mov     [rcx], di
0x180005257  jmp     short loc_18000525E
0x180005259  mov     edx, 80070057h
0x18000525e  mov     rbx, [rsp+arg_0]
0x180005263  mov     eax, edx
0x180005265  mov     rdi, [rsp+arg_8]
0x18000526a  retn
```
