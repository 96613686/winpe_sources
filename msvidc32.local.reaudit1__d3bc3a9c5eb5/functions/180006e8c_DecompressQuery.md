# DecompressQuery

- ea: `0x180006e8c`
- end: `0x180007019`
- name: `DecompressQuery`
- size: `397`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005e00`
- `0x180006c1c`

## callees

- `0x180006e8c`
- `0x180007020`

## pseudocode

```c
__int64 __fastcall DecompressQuery(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        int a13,
        int a14)
{
  int v16; // r10d
  int v17; // r9d
  int v19; // r11d
  int v20; // ecx
  int v21; // r8d
  int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // rcx

  if ( !(unsigned int)DecompressQueryFmt(a1, a3) )
  {
    v16 = a7;
    if ( a7 == -1 )
      v16 = *(_DWORD *)(a3 + 4);
    v17 = a8;
    if ( a8 == -1 )
      v17 = *(_DWORD *)(a3 + 8);
    if ( a5 || a6 || v16 != *(_DWORD *)(a3 + 4) || v17 != *(_DWORD *)(a3 + 8) )
      return 4294967290LL;
    if ( !a9 )
      return 0;
    v19 = a13;
    if ( a13 == -1 )
      v19 = *(_DWORD *)(a9 + 4);
    v20 = a14;
    if ( a14 == -1 )
    {
      v20 = *(_DWORD *)(a9 + 8);
      if ( v20 < 0 )
        v20 = -v20;
    }
    v21 = *(_DWORD *)(a9 + 16);
    if ( v21 != 842217009 && ((*(_WORD *)(a9 + 14) - 8) & 0xFFE7) == 0 )
    {
      if ( !v21 )
      {
        v22 = (*(unsigned __int16 *)(a9 + 14) >> 3) - 1;
LABEL_27:
        if ( v19 == v16 && v20 == v17 )
        {
          v23 = 0;
        }
        else
        {
          if ( v19 != 2 * v16 || v20 != 2 * v17 )
            return 4294967289LL;
          v23 = 5;
        }
        v24 = (__int64)*(&DecompressWin32 + 10 * ((unsigned __int64)*(unsigned __int16 *)(a3 + 14) >> 3)
                                          + v22
                                          + v23
                                          - 10);
        if ( v24 )
        {
          *(_QWORD *)(a1 + 16) = v24;
          return 0;
        }
        return 4294967294LL;
      }
      if ( v21 == 3
        && *(_WORD *)(a9 + 14) == 16
        && *(_DWORD *)(a9 + 40) == 63488
        && *(_DWORD *)(a9 + 44) == 2016
        && *(_DWORD *)(a9 + 48) == 31 )
      {
        v22 = 4;
        goto LABEL_27;
      }
    }
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x180006e8c  mov     [rsp+arg_0], rbx
0x180006e91  mov     [rsp+arg_8], rsi
0x180006e96  push    rdi
0x180006e97  sub     rsp, 20h
0x180006e9b  mov     rdx, r8
0x180006e9e  mov     rbx, r8
0x180006ea1  mov     rdi, rcx
0x180006ea4  call    DecompressQueryFmt
0x180006ea9  test    eax, eax
0x180006eab  jnz     loc_180007004
0x180006eb1  mov     r10d, [rsp+28h+arg_30]
0x180006eb6  cmp     r10d, 0FFFFFFFFh
0x180006eba  jnz     short loc_180006EC0
0x180006ebc  mov     r10d, [rbx+4]
0x180006ec0  mov     r9d, [rsp+28h+arg_38]
0x180006ec5  cmp     r9d, 0FFFFFFFFh
0x180006ec9  jnz     short loc_180006ECF
0x180006ecb  mov     r9d, [rbx+8]
0x180006ecf  cmp     [rsp+28h+arg_20], 0
0x180006ed4  jnz     loc_180006FFD
0x180006eda  cmp     [rsp+28h+arg_28], 0
0x180006edf  jnz     loc_180006FFD
0x180006ee5  cmp     r10d, [rbx+4]
0x180006ee9  jnz     loc_180006FFD
0x180006eef  cmp     r9d, [rbx+8]
0x180006ef3  jnz     loc_180006FFD
0x180006ef9  mov     rdx, [rsp+28h+arg_40]
0x180006efe  test    rdx, rdx
0x180006f01  jnz     short loc_180006F0A
0x180006f03  xor     eax, eax
0x180006f05  jmp     loc_180007009
0x180006f0a  mov     r11d, [rsp+28h+arg_60]
0x180006f12  cmp     r11d, 0FFFFFFFFh
0x180006f16  jnz     short loc_180006F1C
0x180006f18  mov     r11d, [rdx+4]
0x180006f1c  mov     ecx, [rsp+28h+arg_68]
0x180006f23  cmp     ecx, 0FFFFFFFFh
0x180006f26  jnz     short loc_180006F31
0x180006f28  mov     ecx, [rdx+8]
0x180006f2b  test    ecx, ecx
0x180006f2d  jns     short loc_180006F31
0x180006f2f  neg     ecx
0x180006f31  mov     r8d, [rdx+10h]
0x180006f35  cmp     r8d, 32333631h
0x180006f3c  jz      loc_180007004
0x180006f42  movzx   eax, word ptr [rdx+0Eh]
0x180006f46  mov     esi, 0FFE7h
0x180006f4b  sub     ax, 8
0x180006f4f  test    si, ax
0x180006f52  jnz     loc_180007004
0x180006f58  test    r8d, r8d
0x180006f5b  jz      short loc_180006F96
0x180006f5d  cmp     r8d, 3
0x180006f61  jnz     loc_180007004
0x180006f67  cmp     word ptr [rdx+0Eh], 10h
0x180006f6c  jnz     loc_180007004
0x180006f72  cmp     dword ptr [rdx+28h], 0F800h
0x180006f79  jnz     loc_180007004
0x180006f7f  cmp     dword ptr [rdx+2Ch], 7E0h
0x180006f86  jnz     short loc_180007004
0x180006f88  cmp     dword ptr [rdx+30h], 1Fh
0x180006f8c  jnz     short loc_180007004
0x180006f8e  mov     r8d, 4
0x180006f94  jmp     short loc_180006FA2
0x180006f96  movzx   r8d, word ptr [rdx+0Eh]
0x180006f9b  shr     r8d, 3
0x180006f9f  dec     r8d
0x180006fa2  cmp     r11d, r10d
0x180006fa5  jnz     short loc_180006FB0
0x180006fa7  cmp     ecx, r9d
0x180006faa  jnz     short loc_180006FB0
0x180006fac  xor     ecx, ecx
0x180006fae  jmp     short loc_180006FC6
0x180006fb0  lea     eax, [r10+r10]
0x180006fb4  cmp     r11d, eax
0x180006fb7  jnz     short loc_180006FF6
0x180006fb9  lea     eax, [r9+r9]
0x180006fbd  cmp     ecx, eax
0x180006fbf  jnz     short loc_180006FF6
0x180006fc1  mov     ecx, 5
0x180006fc6  movzx   eax, word ptr [rbx+0Eh]
0x180006fca  shr     rax, 3
0x180006fce  lea     rdx, [rax+rax*4]
0x180006fd2  movsxd  rax, r8d
0x180006fd5  add     rcx, rax
0x180006fd8  lea     rax, [rcx+rdx*2]
0x180006fdc  lea     rcx, DecompressWin32
0x180006fe3  mov     rcx, [rcx+rax*8-50h]
0x180006fe8  test    rcx, rcx
0x180006feb  jz      short loc_180007004
0x180006fed  mov     [rdi+10h], rcx
0x180006ff1  jmp     loc_180006F03
0x180006ff6  mov     eax, 0FFFFFFF9h
0x180006ffb  jmp     short loc_180007009
0x180006ffd  mov     eax, 0FFFFFFFAh
0x180007002  jmp     short loc_180007009
0x180007004  mov     eax, 0FFFFFFFEh
0x180007009  mov     rbx, [rsp+28h+arg_0]
0x18000700e  mov     rsi, [rsp+28h+arg_8]
0x180007013  add     rsp, 20h
0x180007017  pop     rdi
0x180007018  retn
```
