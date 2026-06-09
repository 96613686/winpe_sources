# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180009f58`
- end: `0x180009fd5`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c14c`
- `0x18000c494`

## callees

- `0x180009f58`

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
0x180009f58  mov     [rsp+arg_0], rbx
0x180009f5d  xor     ebx, ebx
0x180009f5f  mov     r10, rdx
0x180009f62  mov     r11, rcx
0x180009f65  test    rdx, rdx
0x180009f68  jz      short loc_180009FC0
0x180009f6a  cmp     rdx, 7FFFFFFFh
0x180009f71  jbe     short loc_180009F7A
0x180009f73  mov     edx, 80070057h
0x180009f78  jmp     short loc_180009FCA
0x180009f7a  cmp     r9, 7FFFFFFEh
0x180009f81  ja      short loc_180009F73
0x180009f83  test    r9, r9
0x180009f86  jz      short loc_180009FA6
0x180009f88  movzx   eax, word ptr [r8]
0x180009f8c  test    ax, ax
0x180009f8f  jz      short loc_180009FA6
0x180009f91  mov     [r11], ax
0x180009f95  add     r8, 2
0x180009f99  add     r11, 2
0x180009f9d  dec     r9
0x180009fa0  sub     r10, 1
0x180009fa4  jnz     short loc_180009F83
0x180009fa6  test    r10, r10
0x180009fa9  lea     rcx, [r11-2]
0x180009fad  cmovnz  rcx, r11
0x180009fb1  neg     r10
0x180009fb4  sbb     edx, edx
0x180009fb6  not     edx
0x180009fb8  and     edx, 8007007Ah
0x180009fbe  jmp     short loc_180009FCA
0x180009fc0  mov     edx, 80070057h
0x180009fc5  test    r10, r10
0x180009fc8  jz      short loc_180009FCD
0x180009fca  mov     [rcx], bx
0x180009fcd  mov     rbx, [rsp+arg_0]
0x180009fd2  mov     eax, edx
0x180009fd4  retn
```
