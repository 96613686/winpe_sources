# RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180023d58`
- end: `0x180023db4`
- name: `?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `92`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180023e34`
- `0x180024190`
- `0x1800244f0`
- `0x180024650`
- `0x180024a3c`

## callees

- `0x180023d58`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyNW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3, unsigned __int64 a4)
{
  __int64 result; // rax
  __int64 v6; // r8
  unsigned __int16 *v7; // rax

  if ( a4 <= 0x7FFFFFFE )
  {
    v6 = 64;
    do
    {
      if ( !a4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --a4;
      --v6;
    }
    while ( v6 );
    v7 = a1 - 1;
    if ( v6 )
      v7 = a1;
    *v7 = 0;
    return v6 == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = 3221225485LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180023d58  xor     edx, edx
0x180023d5a  mov     rax, r8
0x180023d5d  cmp     r9, 7FFFFFFEh
0x180023d64  jbe     short loc_180023D6F
0x180023d66  mov     eax, 0C000000Dh
0x180023d6b  mov     [rcx], dx
0x180023d6e  retn
0x180023d6f  mov     r8d, 40h ; '@'
0x180023d75  test    r9, r9
0x180023d78  jz      short loc_180023D99
0x180023d7a  movzx   r10d, word ptr [rax]
0x180023d7e  test    r10w, r10w
0x180023d82  jz      short loc_180023D99
0x180023d84  mov     [rcx], r10w
0x180023d88  add     rax, 2
0x180023d8c  add     rcx, 2
0x180023d90  dec     r9
0x180023d93  sub     r8, 1
0x180023d97  jnz     short loc_180023D75
0x180023d99  test    r8, r8
0x180023d9c  lea     rax, [rcx-2]
0x180023da0  cmovnz  rax, rcx
0x180023da4  neg     r8
0x180023da7  mov     [rax], dx
0x180023daa  sbb     eax, eax
0x180023dac  not     eax
0x180023dae  and     eax, 80000005h
0x180023db3  retn
```
