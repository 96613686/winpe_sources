# ValidateBitmapInfoHeader

- ea: `0x180002604`
- end: `0x18000275b`
- name: `ValidateBitmapInfoHeader`
- size: `343`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022e4`
- `0x1800023bc`

## callees

- `0x180002604`

## pseudocode

```c
_BOOL8 __fastcall ValidateBitmapInfoHeader(unsigned int *a1)
{
  __int64 v1; // rsi
  int v3; // eax
  unsigned __int16 v4; // r9
  unsigned int v5; // r10d
  unsigned int v6; // ecx
  int v7; // r11d
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // r10d
  unsigned int v11; // edx
  unsigned int v12; // r10d
  __int64 v13; // rcx

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
  v6 = a1[1];
  v7 = -v3;
  if ( v3 > 0 )
    v7 = v3;
  v8 = v5 * v6;
  if ( v8 / v5 != a1[1] )
    return 0;
  v9 = ((v8 >> 3) + 3) & 0xFFFFFFFC;
  v10 = v7 * v9;
  if ( v9 )
  {
    if ( v10 / v9 != v7 )
      return 0;
  }
  if ( v10 > 0x40000000 )
    return 0;
  if ( a1[5] > 0x40000000 )
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
  return v1 + v13 + 4 * (unsigned __int64)v11 <= 0x90C
      && (v12 && v12 != 3 || !a1[5] || v7 * (((a1[1] * v4 + 31) >> 3) & 0x1FFFFFFC) <= a1[5]);
}

```

## disassembly

```asm
0x180002604  push    rbp
0x180002606  push    rsi
0x180002607  push    r14
0x180002609  mov     esi, [rcx]
0x18000260b  mov     r8, rcx
0x18000260e  lea     eax, [rsi-28h]
0x180002611  cmp     eax, 0FD8h
0x180002616  ja      loc_180002754
0x18000261c  xor     ebp, ebp
0x18000261e  cmp     [rcx+4], ebp
0x180002621  jz      loc_180002754
0x180002627  mov     eax, [rcx+8]
0x18000262a  test    eax, eax
0x18000262c  jz      loc_180002754
0x180002632  movzx   r9d, word ptr [rcx+0Eh]
0x180002637  lea     r10d, [rbp+20h]
0x18000263b  test    r9w, r9w
0x18000263f  jz      short loc_180002645
0x180002641  movzx   r10d, r9w
0x180002645  mov     ecx, 0C8h
0x18000264a  cmp     r9w, cx
0x18000264e  ja      loc_180002754
0x180002654  mov     ecx, [r8+4]
0x180002658  mov     r11d, eax
0x18000265b  neg     r11d
0x18000265e  cmovs   r11d, eax
0x180002662  imul    ecx, r10d
0x180002666  test    r10d, r10d
0x180002669  jz      short loc_18000267C
0x18000266b  xor     edx, edx
0x18000266d  mov     eax, ecx
0x18000266f  div     r10d
0x180002672  cmp     eax, [r8+4]
0x180002676  jnz     loc_180002754
0x18000267c  shr     ecx, 3
0x18000267f  add     ecx, 3
0x180002682  and     ecx, 0FFFFFFFCh
0x180002685  mov     r10d, ecx
0x180002688  imul    r10d, r11d
0x18000268c  test    ecx, ecx
0x18000268e  jz      short loc_1800026A0
0x180002690  xor     edx, edx
0x180002692  mov     eax, r10d
0x180002695  div     ecx
0x180002697  cmp     eax, r11d
0x18000269a  jnz     loc_180002754
0x1800026a0  mov     eax, 40000000h
0x1800026a5  cmp     r10d, eax
0x1800026a8  ja      loc_180002754
0x1800026ae  cmp     [r8+14h], eax
0x1800026b2  ja      loc_180002754
0x1800026b8  mov     edx, [r8+20h]
0x1800026bc  cmp     edx, 100h
0x1800026c2  ja      loc_180002754
0x1800026c8  mov     r14d, 1
0x1800026ce  test    edx, edx
0x1800026d0  jnz     short loc_1800026E8
0x1800026d2  movzx   eax, r9w
0x1800026d6  sub     ax, r14w
0x1800026da  cmp     ax, 7
0x1800026de  ja      short loc_1800026E8
0x1800026e0  mov     ecx, r9d
0x1800026e3  mov     edx, r14d
0x1800026e6  shl     edx, cl
0x1800026e8  mov     r10d, [r8+10h]
0x1800026ec  cmp     r10d, 3
0x1800026f0  jnz     short loc_180002700
0x1800026f2  lea     eax, [r9-10h]
0x1800026f6  mov     ecx, 0FFEFh
0x1800026fb  test    cx, ax
0x1800026fe  jnz     short loc_180002754
0x180002700  cmp     r10d, 3
0x180002704  mov     eax, edx
0x180002706  mov     ecx, 0Ch
0x18000270b  cmovnz  rcx, rbp
0x18000270f  lea     rcx, [rcx+rax*4]
0x180002713  add     rcx, rsi
0x180002716  cmp     rcx, 90Ch
0x18000271d  ja      short loc_180002754
0x18000271f  test    r10d, r10d
0x180002722  jz      short loc_18000272A
0x180002724  cmp     r10d, 3
0x180002728  jnz     short loc_18000274F
0x18000272a  cmp     [r8+14h], ebp
0x18000272e  jz      short loc_18000274F
0x180002730  movzx   ecx, r9w
0x180002734  imul    ecx, [r8+4]
0x180002739  add     ecx, 1Fh
0x18000273c  shr     ecx, 3
0x18000273f  and     ecx, 1FFFFFFCh
0x180002745  imul    ecx, r11d
0x180002749  cmp     ecx, [r8+14h]
0x18000274d  ja      short loc_180002754
0x18000274f  mov     eax, r14d
0x180002752  jmp     short loc_180002756
0x180002754  xor     eax, eax
0x180002756  pop     r14
0x180002758  pop     rsi
0x180002759  pop     rbp
0x18000275a  retn
```
