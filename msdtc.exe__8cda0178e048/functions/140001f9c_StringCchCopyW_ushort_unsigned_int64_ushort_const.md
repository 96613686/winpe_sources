# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140001f9c`
- end: `0x140002007`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002010`
- `0x1400029f0`
- `0x140002ed4`
- `0x1400040dc`
- `0x14000525c`
- `0x1400060d8`

## callees

- `0x140001f9c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x140001f9c  xor     r10d, r10d
0x140001f9f  mov     r9, rcx
0x140001fa2  test    rdx, rdx
0x140001fa5  jz      short loc_140001FF8
0x140001fa7  cmp     rdx, 7FFFFFFFh
0x140001fae  jbe     short loc_140001FB7
0x140001fb0  mov     eax, 80070057h
0x140001fb5  jmp     short loc_140002002
0x140001fb7  mov     eax, 7FFFFFFEh
0x140001fbc  test    rax, rax
0x140001fbf  jz      short loc_140001FDF
0x140001fc1  movzx   ecx, word ptr [r8]
0x140001fc5  test    cx, cx
0x140001fc8  jz      short loc_140001FDF
0x140001fca  mov     [r9], cx
0x140001fce  add     r8, 2
0x140001fd2  add     r9, 2
0x140001fd6  dec     rax
0x140001fd9  sub     rdx, 1
0x140001fdd  jnz     short loc_140001FBC
0x140001fdf  test    rdx, rdx
0x140001fe2  lea     rcx, [r9-2]
0x140001fe6  cmovnz  rcx, r9
0x140001fea  neg     rdx
0x140001fed  sbb     eax, eax
0x140001fef  not     eax
0x140001ff1  and     eax, 8007007Ah
0x140001ff6  jmp     short loc_140002002
0x140001ff8  mov     eax, 80070057h
0x140001ffd  test    rdx, rdx
0x140002000  jz      short locret_140002006
0x140002002  mov     [rcx], r10w
0x140002006  retn
```
