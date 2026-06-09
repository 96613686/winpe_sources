# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180009880`
- end: `0x18000991c`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `156`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009440`
- `0x18000a710`
- `0x18000b610`

## callees

- `0x180009880`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned __int16 *v4; // r9
  unsigned int v5; // r8d
  const unsigned __int16 *v6; // rax
  __int64 v7; // rcx

  v4 = a1;
  if ( !a1 && a2 || a2 > 0x7FFFFFFF )
  {
    v5 = -2147024809;
LABEL_17:
    *a1 = 0;
    return v5;
  }
  v6 = &qword_1800132F0;
  if ( a3 )
    v6 = a3;
  if ( a2 )
  {
    v7 = 2147483646;
    do
    {
      if ( !v7 )
        break;
      if ( !*v6 )
        break;
      *v4++ = *v6++;
      --v7;
      --a2;
    }
    while ( a2 );
    a1 = v4 - 1;
    if ( a2 )
      a1 = v4;
    v5 = a2 == 0 ? 0x8007007A : 0;
    goto LABEL_17;
  }
  v5 = 0;
  if ( *v6 )
    return a1 != 0 ? -2147024774 : -2147024809;
  return v5;
}

```

## disassembly

```asm
0x180009880  xor     r10d, r10d
0x180009883  mov     r9, rcx
0x180009886  test    rcx, rcx
0x180009889  jnz     short loc_180009890
0x18000988b  test    rdx, rdx
0x18000988e  jnz     short loc_180009899
0x180009890  cmp     rdx, 7FFFFFFFh
0x180009897  jbe     short loc_1800098A1
0x180009899  mov     r8d, 80070057h
0x18000989f  jmp     short loc_180009914
0x1800098a1  test    r8, r8
0x1800098a4  lea     rax, qword_1800132F0
0x1800098ab  cmovnz  rax, r8
0x1800098af  test    rdx, rdx
0x1800098b2  jnz     short loc_1800098D0
0x1800098b4  mov     r8d, r10d
0x1800098b7  cmp     [rax], r10w
0x1800098bb  jz      short loc_180009918
0x1800098bd  neg     r9
0x1800098c0  mov     r8d, 80070057h
0x1800098c6  sbb     eax, eax
0x1800098c8  and     eax, 23h
0x1800098cb  add     r8d, eax
0x1800098ce  jmp     short loc_180009918
0x1800098d0  mov     ecx, 7FFFFFFEh
0x1800098d5  test    rcx, rcx
0x1800098d8  jz      short loc_1800098F9
0x1800098da  movzx   r8d, word ptr [rax]
0x1800098de  test    r8w, r8w
0x1800098e2  jz      short loc_1800098F9
0x1800098e4  mov     [r9], r8w
0x1800098e8  add     rax, 2
0x1800098ec  add     r9, 2
0x1800098f0  dec     rcx
0x1800098f3  sub     rdx, 1
0x1800098f7  jnz     short loc_1800098D5
0x1800098f9  test    rdx, rdx
0x1800098fc  lea     rcx, [r9-2]
0x180009900  cmovnz  rcx, r9
0x180009904  neg     rdx
0x180009907  sbb     r8d, r8d
0x18000990a  not     r8d
0x18000990d  and     r8d, 8007007Ah
0x180009914  mov     [rcx], r10w
0x180009918  mov     eax, r8d
0x18000991b  retn
```
