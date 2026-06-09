# ValidateBitmapInfoHeader

- ea: `0x1800072d0`
- end: `0x18000742a`
- name: `ValidateBitmapInfoHeader`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007020`

## callees

- `0x1800072d0`

## pseudocode

```c
_BOOL8 __fastcall ValidateBitmapInfoHeader(unsigned int *a1)
{
  __int64 v1; // rsi
  int v3; // r10d
  unsigned __int16 v4; // r9
  unsigned int v5; // ebx
  int v6; // r11d
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // edx
  unsigned int v12; // r11d
  __int64 v13; // rcx
  int v14; // ecx

  v1 = *a1;
  if ( (unsigned int)(v1 - 40) > 0xFD8 )
    return 0;
  if ( !a1[1] )
    return 0;
  v3 = a1[2];
  if ( !v3 )
    return 0;
  v4 = *((_WORD *)a1 + 7);
  v5 = 32;
  if ( v4 )
    v5 = v4;
  if ( v4 > 0xC8u )
    return 0;
  v6 = a1[2];
  if ( v3 < 0 )
    v6 = -v3;
  v7 = v5 * a1[1];
  if ( v7 / v5 != a1[1] )
    return 0;
  v8 = ((v7 >> 3) + 3) & 0xFFFFFFFC;
  v9 = v6 * v8;
  if ( v8 )
  {
    if ( v9 / v8 != v6 )
      return 0;
  }
  if ( v9 > 0x40000000 )
    return 0;
  v10 = a1[5];
  if ( v10 > 0x40000000 )
    return 0;
  v11 = a1[8];
  if ( v11 > 0x100 )
    return 0;
  if ( !v11 && (unsigned __int16)(v4 - 1) <= 7u )
    v11 = 1 << v4;
  v12 = a1[4];
  if ( v12 == 3 && ((v4 - 16) & 0xFFEF) != 0 )
    return 0;
  v13 = 12;
  if ( v12 != 3 )
    v13 = 0;
  if ( v1 + v13 + 4 * (unsigned __int64)v11 > 0x90C )
    return 0;
  if ( v12 && v12 != 3 )
    return 1;
  if ( !v10 )
    return 1;
  v14 = -v3;
  if ( v3 > 0 )
    v14 = v3;
  return v14 * (((a1[1] * v4 + 31) >> 3) & 0x1FFFFFFC) <= v10;
}

```

## disassembly

```asm
0x1800072d0  push    rbx
0x1800072d2  push    rbp
0x1800072d3  push    rsi
0x1800072d4  push    r14
0x1800072d6  mov     esi, [rcx]
0x1800072d8  mov     r8, rcx
0x1800072db  lea     eax, [rsi-28h]
0x1800072de  cmp     eax, 0FD8h
0x1800072e3  ja      loc_180007422
0x1800072e9  xor     ebp, ebp
0x1800072eb  cmp     [rcx+4], ebp
0x1800072ee  jz      loc_180007422
0x1800072f4  mov     r10d, [rcx+8]
0x1800072f8  test    r10d, r10d
0x1800072fb  jz      loc_180007422
0x180007301  movzx   r9d, word ptr [rcx+0Eh]
0x180007306  lea     ebx, [rbp+20h]
0x180007309  test    r9w, r9w
0x18000730d  jz      short loc_180007313
0x18000730f  movzx   ebx, r9w
0x180007313  mov     eax, 0C8h
0x180007318  cmp     r9w, ax
0x18000731c  ja      loc_180007422
0x180007322  mov     r11d, r10d
0x180007325  test    r10d, r10d
0x180007328  jns     short loc_18000732D
0x18000732a  neg     r11d
0x18000732d  mov     ecx, [rcx+4]
0x180007330  imul    ecx, ebx
0x180007333  test    ebx, ebx
0x180007335  jz      short loc_180007347
0x180007337  xor     edx, edx
0x180007339  mov     eax, ecx
0x18000733b  div     ebx
0x18000733d  cmp     eax, [r8+4]
0x180007341  jnz     loc_180007422
0x180007347  shr     ecx, 3
0x18000734a  add     ecx, 3
0x18000734d  and     ecx, 0FFFFFFFCh
0x180007350  mov     ebx, ecx
0x180007352  imul    ebx, r11d
0x180007356  test    ecx, ecx
0x180007358  jz      short loc_180007369
0x18000735a  xor     edx, edx
0x18000735c  mov     eax, ebx
0x18000735e  div     ecx
0x180007360  cmp     eax, r11d
0x180007363  jnz     loc_180007422
0x180007369  mov     eax, 40000000h
0x18000736e  cmp     ebx, eax
0x180007370  ja      loc_180007422
0x180007376  mov     ebx, [r8+14h]
0x18000737a  cmp     ebx, eax
0x18000737c  ja      loc_180007422
0x180007382  mov     edx, [r8+20h]
0x180007386  cmp     edx, 100h
0x18000738c  ja      loc_180007422
0x180007392  mov     r14d, 1
0x180007398  test    edx, edx
0x18000739a  jnz     short loc_1800073B2
0x18000739c  movzx   eax, r9w
0x1800073a0  sub     ax, r14w
0x1800073a4  cmp     ax, 7
0x1800073a8  ja      short loc_1800073B2
0x1800073aa  mov     ecx, r9d
0x1800073ad  mov     edx, r14d
0x1800073b0  shl     edx, cl
0x1800073b2  mov     r11d, [r8+10h]
0x1800073b6  cmp     r11d, 3
0x1800073ba  jnz     short loc_1800073CA
0x1800073bc  lea     eax, [r9-10h]
0x1800073c0  mov     ecx, 0FFEFh
0x1800073c5  test    cx, ax
0x1800073c8  jnz     short loc_180007422
0x1800073ca  cmp     r11d, 3
0x1800073ce  mov     eax, edx
0x1800073d0  mov     ecx, 0Ch
0x1800073d5  cmovnz  rcx, rbp
0x1800073d9  lea     rcx, [rcx+rax*4]
0x1800073dd  add     rcx, rsi
0x1800073e0  cmp     rcx, 90Ch
0x1800073e7  ja      short loc_180007422
0x1800073e9  test    r11d, r11d
0x1800073ec  jz      short loc_1800073F4
0x1800073ee  cmp     r11d, 3
0x1800073f2  jnz     short loc_18000741D
0x1800073f4  test    ebx, ebx
0x1800073f6  jz      short loc_18000741D
0x1800073f8  movzx   edx, r9w
0x1800073fc  mov     ecx, r10d
0x1800073ff  imul    edx, [r8+4]
0x180007404  add     edx, 1Fh
0x180007407  shr     edx, 3
0x18000740a  and     edx, 1FFFFFFCh
0x180007410  neg     ecx
0x180007412  cmovs   ecx, r10d
0x180007416  imul    edx, ecx
0x180007419  cmp     edx, ebx
0x18000741b  ja      short loc_180007422
0x18000741d  mov     eax, r14d
0x180007420  jmp     short loc_180007424
0x180007422  xor     eax, eax
0x180007424  pop     r14
0x180007426  pop     rsi
0x180007427  pop     rbp
0x180007428  pop     rbx
0x180007429  retn
```
