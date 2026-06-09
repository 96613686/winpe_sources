# IsCmdExe(ushort const *)

- ea: `0x1800045fc`
- end: `0x180004672`
- name: `?IsCmdExe@@YAHPEBG@Z`
- size: `118`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000337c`

## callees

- `0x1800045fc`

## pseudocode

```c
__int64 __fastcall IsCmdExe(const unsigned __int16 *a1)
{
  __int16 v1; // ax

  v1 = *a1;
  if ( !*a1 )
    return 0;
  while ( v1 != 99 && *a1 != 67
       || ((a1[1] - 77) & 0xFFDF) != 0
       || ((a1[2] - 68) & 0xFFDF) != 0
       || a1[3] != 46
       || ((a1[4] - 69) & 0xFFDF) != 0
       || ((a1[5] - 88) & 0xFFDF) != 0
       || ((a1[6] - 69) & 0xFFDF) != 0 )
  {
    v1 = *++a1;
    if ( !*a1 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800045fc  movzx   eax, word ptr [rcx]
0x1800045ff  test    ax, ax
0x180004602  jz      short loc_180004669
0x180004604  mov     edx, 0FFDFh
0x180004609  cmp     ax, 63h ; 'c'
0x18000460d  jz      short loc_180004615
0x18000460f  cmp     word ptr [rcx], 43h ; 'C'
0x180004613  jnz     short loc_18000465D
0x180004615  movzx   eax, word ptr [rcx+2]
0x180004619  sub     ax, 4Dh ; 'M'
0x18000461d  test    dx, ax
0x180004620  jnz     short loc_18000465D
0x180004622  movzx   eax, word ptr [rcx+4]
0x180004626  sub     ax, 44h ; 'D'
0x18000462a  test    dx, ax
0x18000462d  jnz     short loc_18000465D
0x18000462f  cmp     word ptr [rcx+6], 2Eh ; '.'
0x180004634  jnz     short loc_18000465D
0x180004636  movzx   eax, word ptr [rcx+8]
0x18000463a  sub     ax, 45h ; 'E'
0x18000463e  test    dx, ax
0x180004641  jnz     short loc_18000465D
0x180004643  movzx   eax, word ptr [rcx+0Ah]
0x180004647  sub     ax, 58h ; 'X'
0x18000464b  test    dx, ax
0x18000464e  jnz     short loc_18000465D
0x180004650  movzx   eax, word ptr [rcx+0Ch]
0x180004654  sub     ax, 45h ; 'E'
0x180004658  test    dx, ax
0x18000465b  jz      short loc_18000466C
0x18000465d  add     rcx, 2
0x180004661  movzx   eax, word ptr [rcx]
0x180004664  test    ax, ax
0x180004667  jnz     short loc_180004609
0x180004669  xor     eax, eax
0x18000466b  retn
0x18000466c  mov     eax, 1
0x180004671  retn
```
