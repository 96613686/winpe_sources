# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400020a4`
- end: `0x14000215f`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400023ac`

## callees

- `0x1400020a4`

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
0x1400020a4  mov     [rsp+arg_0], rbx
0x1400020a9  mov     [rsp+arg_8], rdi
0x1400020ae  lea     rax, [rdx-1]
0x1400020b2  mov     r10d, 7FFFFFFEh
0x1400020b8  mov     r9, rdx
0x1400020bb  mov     rbx, rcx
0x1400020be  cmp     rax, r10
0x1400020c1  ja      loc_14000214D
0x1400020c7  mov     r11, rdx
0x1400020ca  mov     rax, rcx
0x1400020cd  xor     edi, edi
0x1400020cf  cmp     [rax], di
0x1400020d2  jz      short loc_1400020DE
0x1400020d4  add     rax, 2
0x1400020d8  sub     r11, 1
0x1400020dc  jnz     short loc_1400020CF
0x1400020de  mov     rax, r11
0x1400020e1  mov     rcx, r9
0x1400020e4  neg     rax
0x1400020e7  mov     rax, r11
0x1400020ea  sbb     edx, edx
0x1400020ec  sub     rcx, r11
0x1400020ef  not     edx
0x1400020f1  and     edx, 80070057h
0x1400020f7  neg     rax
0x1400020fa  sbb     rax, rax
0x1400020fd  and     rax, rcx
0x140002100  test    r11, r11
0x140002103  jz      short loc_140002152
0x140002105  sub     r9, rax
0x140002108  lea     rax, [rbx+rax*2]
0x14000210c  jz      short loc_140002130
0x14000210e  test    r10, r10
0x140002111  jz      short loc_140002130
0x140002113  movzx   ecx, word ptr [r8]
0x140002117  test    cx, cx
0x14000211a  jz      short loc_140002130
0x14000211c  mov     [rax], cx
0x14000211f  add     r8, 2
0x140002123  add     rax, 2
0x140002127  dec     r10
0x14000212a  sub     r9, 1
0x14000212e  jnz     short loc_14000210E
0x140002130  test    r9, r9
0x140002133  lea     rcx, [rax-2]
0x140002137  cmovnz  rcx, rax
0x14000213b  neg     r9
0x14000213e  sbb     edx, edx
0x140002140  not     edx
0x140002142  and     edx, 8007007Ah
0x140002148  mov     [rcx], di
0x14000214b  jmp     short loc_140002152
0x14000214d  mov     edx, 80070057h
0x140002152  mov     rbx, [rsp+arg_0]
0x140002157  mov     eax, edx
0x140002159  mov     rdi, [rsp+arg_8]
0x14000215e  retn
```
