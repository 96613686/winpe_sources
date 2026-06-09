# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x1800042ec`
- end: `0x180004369`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002170`
- `0x180003a68`
- `0x180003f0c`
- `0x180004370`

## callees

- `0x1800042ec`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v4; // r10
  unsigned __int16 *v5; // r11
  unsigned int v6; // edx

  v4 = a2;
  v5 = a1;
  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || a4 > 0x7FFFFFFE )
    {
      v6 = -2147024809;
    }
    else
    {
      do
      {
        if ( !a4 )
          break;
        if ( !*a3 )
          break;
        *v5++ = *a3++;
        --a4;
        --v4;
      }
      while ( v4 );
      a1 = v5 - 1;
      if ( v4 )
        a1 = v5;
      v6 = v4 == 0 ? 0x8007007A : 0;
    }
    *a1 = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x1800042ec  mov     [rsp+arg_0], rbx
0x1800042f1  xor     ebx, ebx
0x1800042f3  mov     r10, rdx
0x1800042f6  mov     r11, rcx
0x1800042f9  test    rdx, rdx
0x1800042fc  jz      short loc_180004354
0x1800042fe  cmp     rdx, 7FFFFFFFh
0x180004305  jbe     short loc_18000430E
0x180004307  mov     edx, 80070057h
0x18000430c  jmp     short loc_18000435E
0x18000430e  cmp     r9, 7FFFFFFEh
0x180004315  ja      short loc_180004307
0x180004317  test    r9, r9
0x18000431a  jz      short loc_18000433A
0x18000431c  movzx   eax, word ptr [r8]
0x180004320  test    ax, ax
0x180004323  jz      short loc_18000433A
0x180004325  mov     [r11], ax
0x180004329  add     r8, 2
0x18000432d  add     r11, 2
0x180004331  dec     r9
0x180004334  sub     r10, 1
0x180004338  jnz     short loc_180004317
0x18000433a  test    r10, r10
0x18000433d  lea     rcx, [r11-2]
0x180004341  cmovnz  rcx, r11
0x180004345  neg     r10
0x180004348  sbb     edx, edx
0x18000434a  not     edx
0x18000434c  and     edx, 8007007Ah
0x180004352  jmp     short loc_18000435E
0x180004354  mov     edx, 80070057h
0x180004359  test    r10, r10
0x18000435c  jz      short loc_180004361
0x18000435e  mov     [rcx], bx
0x180004361  mov     rbx, [rsp+arg_0]
0x180004366  mov     eax, edx
0x180004368  retn
```
