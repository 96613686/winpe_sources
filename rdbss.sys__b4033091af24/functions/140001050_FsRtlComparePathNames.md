# FsRtlComparePathNames

- ea: `0x140001050`
- end: `0x14000122c`
- name: `FsRtlComparePathNames`
- size: `476`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140060f10`
- `0x140074a00`
- `0x140075f70`

## callees

- `0x140001050`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400010eb`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400010fe`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400010eb`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400010fe`

## pseudocode

```c
__int64 __fastcall FsRtlComparePathNames(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 a3,
        unsigned __int16 *a4)
{
  unsigned __int16 v4; // ax
  unsigned __int16 *v5; // r13
  unsigned int v8; // ebp
  unsigned int v9; // esi
  __int64 v10; // rbx
  unsigned int v11; // eax
  int v12; // edi
  WCHAR v13; // r14
  WCHAR v14; // ax
  int v15; // ecx
  int v16; // eax
  unsigned __int16 v18; // r8
  unsigned __int16 v19; // dx
  int v20; // edx
  int v21; // r8d
  __int16 v22; // dx
  __int16 v23; // r8
  char v24; // [rsp+60h] [rbp+18h] BYREF

  v4 = *a1;
  v5 = (unsigned __int16 *)&v24;
  v8 = a3;
  if ( *a1 >= *a2 )
    v4 = *a2;
  v9 = v4 >> 1;
  if ( a4 )
    v5 = a4;
  v10 = 0;
  *v5 = 0;
  while ( 1 )
  {
    v11 = v8;
    if ( v9 < v8 )
      v11 = v9;
    if ( (unsigned int)v10 >= v11 )
      break;
    LOWORD(v12) = *(_WORD *)(2 * v10 + *((_QWORD *)a1 + 1));
    v13 = *(_WORD *)(2 * v10 + *((_QWORD *)a2 + 1));
    if ( (_WORD)v12 != v13 )
    {
      v12 = RtlUpcaseUnicodeChar(v12);
      v14 = RtlUpcaseUnicodeChar(v13);
      if ( (_WORD)v12 != v14 )
      {
        if ( v12 == 92 )
          return 0xFFFFFFFFLL;
        if ( v14 == 92 )
          return 1;
        if ( v12 == 58 )
          return 0xFFFFFFFFLL;
        if ( v14 == 58 )
          return 1;
        v15 = v14;
        v16 = v12;
        return (unsigned int)(v16 - v15);
      }
    }
    if ( (_WORD)v12 == 92 || (_WORD)v12 == 58 )
      *v5 = 2 * v10;
    v10 = (unsigned int)(v10 + 1);
  }
  while ( 1 )
  {
    if ( (unsigned int)v10 >= v9 )
    {
      v18 = *a2;
      v19 = *a1;
      if ( *a1 > *a2 )
      {
        v22 = *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v10);
        if ( v22 == 92 || v22 == 58 )
        {
          *v5 = v18;
          v16 = *a1;
          v15 = *a2;
          return (unsigned int)(v16 - v15);
        }
      }
      else if ( v19 >= v18 || (v23 = *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v10), v23 == 92) || v23 == 58 )
      {
        *v5 = v19;
      }
      v16 = *a1;
      v15 = *a2;
      return (unsigned int)(v16 - v15);
    }
    v20 = *(unsigned __int16 *)(2 * v10 + *((_QWORD *)a1 + 1));
    v21 = *(unsigned __int16 *)(2 * v10 + *((_QWORD *)a2 + 1));
    if ( (_WORD)v20 != (_WORD)v21 )
      break;
    if ( v20 == 92 || v20 == 58 )
      *v5 = 2 * v10;
    v10 = (unsigned int)(v10 + 1);
  }
  if ( v20 == 92 )
    return 0xFFFFFFFFLL;
  if ( v21 == 92 )
    return 1;
  if ( v20 == 58 )
    return 0xFFFFFFFFLL;
  if ( v21 == 58 )
    return 1;
  else
    return (unsigned int)(v20 - v21);
}

```

## disassembly

```asm
0x140001050  mov     [rsp+arg_18], rbx
0x140001055  push    rbp
0x140001056  push    rsi
0x140001057  push    r12
0x140001059  push    r13
0x14000105b  push    r15
0x14000105d  sub     rsp, 20h
0x140001061  movzx   eax, word ptr [rcx]
0x140001064  lea     r13, [rsp+48h+arg_10]
0x140001069  movzx   r10d, word ptr [rdx]
0x14000106d  mov     r12, rdx
0x140001070  cmp     ax, r10w
0x140001074  mov     [rsp+48h+arg_0], rdi
0x140001079  mov     r15, rcx
0x14000107c  movzx   ebp, r8w
0x140001080  cmovnb  ax, r10w
0x140001085  mov     [rsp+48h+arg_8], r14
0x14000108a  movzx   esi, ax
0x14000108d  shr     esi, 1
0x14000108f  test    r9, r9
0x140001092  cmovnz  r13, r9
0x140001096  xor     eax, eax
0x140001098  xor     ebx, ebx
0x14000109a  mov     [r13+0], ax
0x14000109f  nop
0x1400010a0  cmp     esi, ebp
0x1400010a2  mov     eax, ebp
0x1400010a4  cmovb   eax, esi
0x1400010a7  cmp     ebx, eax
0x1400010a9  jnb     loc_140001155
0x1400010af  mov     rax, [r15+8]
0x1400010b3  lea     rcx, [rbx+rbx]
0x1400010b7  movzx   edi, word ptr [rcx+rax]
0x1400010bb  mov     rax, [r12+8]
0x1400010c0  movzx   r14d, word ptr [rcx+rax]
0x1400010c5  cmp     di, r14w
0x1400010c9  jnz     short loc_1400010E8
0x1400010cb  cmp     di, 5Ch ; '\'
0x1400010cf  jz      short loc_1400010DB
0x1400010d1  cmp     di, 3Ah ; ':'
0x1400010d5  jz      short loc_1400010DB
0x1400010d7  inc     ebx
0x1400010d9  jmp     short loc_1400010A0
0x1400010db  movzx   eax, bx
0x1400010de  add     ax, ax
0x1400010e1  mov     [r13+0], ax
0x1400010e6  jmp     short loc_1400010D7
0x1400010e8  movzx   ecx, di; SourceCharacter
0x1400010eb  call    cs:__imp_RtlUpcaseUnicodeChar
0x1400010f2  nop     dword ptr [rax+rax+00h]
0x1400010f7  movzx   ecx, r14w; SourceCharacter
0x1400010fb  movzx   edi, ax
0x1400010fe  call    cs:__imp_RtlUpcaseUnicodeChar
0x140001105  nop     dword ptr [rax+rax+00h]
0x14000110a  cmp     di, ax
0x14000110d  jz      short loc_1400010CB
0x14000110f  cmp     edi, 5Ch ; '\'
0x140001112  jz      loc_1400011A6
0x140001118  cmp     ax, 5Ch ; '\'
0x14000111c  jz      loc_1400011FF
0x140001122  cmp     edi, 3Ah ; ':'
0x140001125  jz      short loc_1400011A6
0x140001127  cmp     ax, 3Ah ; ':'
0x14000112b  jz      loc_1400011FF
0x140001131  movzx   ecx, ax
0x140001134  mov     eax, edi
0x140001136  sub     eax, ecx
0x140001138  mov     r14, [rsp+48h+arg_8]
0x14000113d  mov     rdi, [rsp+48h+arg_0]
0x140001142  mov     rbx, [rsp+48h+arg_18]
0x140001147  add     rsp, 20h
0x14000114b  pop     r15
0x14000114d  pop     r13
0x14000114f  pop     r12
0x140001151  pop     rsi
0x140001152  pop     rbp
0x140001153  retn
0x140001155  cmp     ebx, esi
0x140001157  jb      short loc_14000117A
0x140001159  movzx   r8d, word ptr [r12]
0x14000115e  movzx   edx, word ptr [r15]
0x140001162  cmp     dx, r8w
0x140001166  ja      short loc_1400011AD
0x140001168  jb      short loc_1400011CE
0x14000116a  mov     [r13+0], dx
0x14000116f  movzx   eax, word ptr [r15]
0x140001173  movzx   ecx, word ptr [r12]
0x140001178  jmp     short loc_140001136
0x14000117a  mov     rax, [r15+8]
0x14000117e  lea     rcx, [rbx+rbx]
0x140001182  movzx   edx, word ptr [rcx+rax]
0x140001186  mov     rax, [r12+8]
0x14000118b  movzx   r8d, word ptr [rcx+rax]
0x140001190  cmp     dx, r8w
0x140001194  jz      short loc_1400011E8
0x140001196  cmp     edx, 5Ch ; '\'
0x140001199  jz      short loc_1400011A6
0x14000119b  cmp     r8d, 5Ch ; '\'
0x14000119f  jz      short loc_1400011FF
0x1400011a1  cmp     edx, 3Ah ; ':'
0x1400011a4  jnz     short loc_1400011F9
0x1400011a6  mov     eax, 0FFFFFFFFh
0x1400011ab  jmp     short loc_140001138
0x1400011ad  mov     rax, [r15+8]
0x1400011b1  movzx   edx, word ptr [rax+rbx*2]
0x1400011b5  cmp     dx, 5Ch ; '\'
0x1400011b9  jnz     short loc_140001209
0x1400011bb  mov     [r13+0], r8w
0x1400011c0  movzx   eax, word ptr [r15]
0x1400011c4  movzx   ecx, word ptr [r12]
0x1400011c9  jmp     loc_140001136
0x1400011ce  mov     rax, [r12+8]
0x1400011d3  movzx   r8d, word ptr [rax+rbx*2]
0x1400011d8  cmp     r8w, 5Ch ; '\'
0x1400011dd  jz      short loc_14000116A
0x1400011df  cmp     r8w, 3Ah ; ':'
0x1400011e4  jnz     short loc_14000116F
0x1400011e6  jmp     short loc_14000116A
0x1400011e8  cmp     edx, 5Ch ; '\'
0x1400011eb  jz      short loc_140001215
0x1400011ed  cmp     edx, 3Ah ; ':'
0x1400011f0  jz      short loc_140001215
0x1400011f2  inc     ebx
0x1400011f4  jmp     loc_140001155
0x1400011f9  cmp     r8d, 3Ah ; ':'
0x1400011fd  jnz     short loc_140001222
0x1400011ff  mov     eax, 1
0x140001204  jmp     loc_140001138
0x140001209  cmp     dx, 3Ah ; ':'
0x14000120d  jnz     loc_14000116F
0x140001213  jmp     short loc_1400011BB
0x140001215  movzx   eax, bx
0x140001218  add     ax, ax
0x14000121b  mov     [r13+0], ax
0x140001220  jmp     short loc_1400011F2
0x140001222  mov     eax, edx
0x140001224  sub     eax, r8d
0x140001227  jmp     loc_140001138
```
