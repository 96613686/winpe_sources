# pSetupConcatenatePaths

- ea: `0x180007188`
- end: `0x18000730f`
- name: `pSetupConcatenatePaths`
- size: `391`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800070a0`
- `0x18001df9c`
- `0x1800202d0`
- `0x180020384`
- `0x180020878`

## callees

- `0x180007188`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000729b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000729b`

## pseudocode

```c
_BOOL8 __fastcall pSetupConcatenatePaths(__int64 a1, _WORD *a2, unsigned int a3)
{
  __int64 v3; // r10
  __int64 v5; // r9
  int v7; // ecx
  bool v8; // zf
  unsigned __int64 v9; // r8
  _WORD *v10; // r9
  DWORD v11; // ebx
  __int64 v12; // rax
  _WORD *v13; // rcx
  unsigned int v14; // edx
  __int64 v16; // rax

  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a1 + 2 * v5) );
  do
    ++v3;
  while ( a2[v3] );
  if ( (_DWORD)v5
    && (*(_WORD *)(a1 + 2LL * (unsigned int)v5 - 2) == 92 || *(_WORD *)(a1 + 2LL * (unsigned int)v5 - 2) == 47) )
  {
    LODWORD(v5) = v5 - 1;
  }
  if ( *a2 == 92 || *a2 == 47 )
  {
    v7 = 1;
    LODWORD(v3) = v3 - 1;
  }
  else
  {
    v7 = 0;
  }
  if ( (int)v5 + (int)v3 + 2 > a3 )
  {
    v11 = 206;
LABEL_24:
    SetLastError(v11);
    return v11 == 0;
  }
  if ( !v7 )
  {
    if ( (unsigned int)v5 >= a3 )
      goto LABEL_32;
    v16 = (unsigned int)v5;
    LODWORD(v5) = v5 + 1;
    *(_WORD *)(a1 + 2 * v16) = 92;
  }
  if ( (unsigned int)v5 >= a3 )
  {
LABEL_32:
    v11 = 206;
    goto LABEL_19;
  }
  v8 = a3 == (_DWORD)v5;
  v9 = a3 - (unsigned int)v5;
  v10 = (_WORD *)(a1 + 2LL * (unsigned int)v5);
  if ( v8 )
  {
    LOWORD(v14) = 87;
    if ( !v9 )
    {
LABEL_36:
      v11 = (unsigned __int16)v14;
      goto LABEL_19;
    }
LABEL_35:
    *v10 = 0;
    goto LABEL_36;
  }
  if ( v9 > 0x7FFFFFFF )
  {
    LOWORD(v14) = 87;
    goto LABEL_35;
  }
  v11 = 0;
  v12 = 2147483646;
  do
  {
    if ( !v12 )
      break;
    if ( !*a2 )
      break;
    *v10++ = *a2++;
    --v12;
    --v9;
  }
  while ( v9 );
  v13 = v10 - 1;
  v14 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v13 = v10;
  *v13 = 0;
  if ( !v9 )
    goto LABEL_36;
LABEL_19:
  if ( a3 )
    *(_WORD *)(a1 + 2LL * (a3 - 1)) = 0;
  if ( v11 )
    goto LABEL_24;
  return v11 == 0;
}

```

## disassembly

```asm
0x180007188  mov     [rsp+arg_0], rbx
0x18000718d  mov     [rsp+arg_8], rsi
0x180007192  push    rdi
0x180007193  sub     rsp, 20h
0x180007197  or      r10, 0FFFFFFFFFFFFFFFFh
0x18000719b  mov     r11d, r8d
0x18000719e  mov     r9, r10
0x1800071a1  xor     esi, esi
0x1800071a3  mov     rdi, rcx
0x1800071a6  inc     r9
0x1800071a9  cmp     [rcx+r9*2], si
0x1800071ae  jnz     short loc_1800071A6
0x1800071b0  inc     r10
0x1800071b3  cmp     [rdx+r10*2], si
0x1800071b8  jnz     short loc_1800071B0
0x1800071ba  or      ebx, 0FFFFFFFFh
0x1800071bd  mov     r8d, 5Ch ; '\'
0x1800071c3  test    r9d, r9d
0x1800071c6  jnz     loc_1800072A3
0x1800071cc  cmp     [rdx], r8w
0x1800071d0  jnz     loc_1800072D7
0x1800071d6  mov     ecx, 1
0x1800071db  add     r10d, ebx
0x1800071de  lea     eax, [r10+2]
0x1800071e2  add     eax, r9d
0x1800071e5  cmp     eax, r11d
0x1800071e8  ja      loc_180007294
0x1800071ee  test    ecx, ecx
0x1800071f0  jz      loc_1800072C2
0x1800071f6  cmp     r9d, r11d
0x1800071f9  jnb     loc_1800072E8
0x1800071ff  mov     eax, r9d
0x180007202  mov     r8d, r11d
0x180007205  sub     r8d, r9d
0x180007208  lea     r9, [rdi+rax*2]
0x18000720c  jz      loc_1800072F9
0x180007212  cmp     r8, 7FFFFFFFh
0x180007219  ja      loc_1800072F2
0x18000721f  mov     ebx, esi
0x180007221  mov     eax, 7FFFFFFEh
0x180007226  test    rax, rax
0x180007229  jz      short loc_180007248
0x18000722b  movzx   ecx, word ptr [rdx]
0x18000722e  test    cx, cx
0x180007231  jz      short loc_180007248
0x180007233  mov     [r9], cx
0x180007237  add     rdx, 2
0x18000723b  add     r9, 2
0x18000723f  dec     rax
0x180007242  sub     r8, 1
0x180007246  jnz     short loc_180007226
0x180007248  mov     rax, r8
0x18000724b  lea     rcx, [r9-2]
0x18000724f  neg     rax
0x180007252  sbb     edx, edx
0x180007254  not     edx
0x180007256  and     edx, 8007007Ah
0x18000725c  test    r8, r8
0x18000725f  cmovnz  rcx, r9
0x180007263  mov     [rcx], si
0x180007266  jz      loc_180007307
0x18000726c  test    r11d, r11d
0x18000726f  jz      short loc_180007279
0x180007271  lea     eax, [r11-1]
0x180007275  mov     [rdi+rax*2], si
0x180007279  test    ebx, ebx
0x18000727b  jnz     short loc_180007299
0x18000727d  test    ebx, ebx
0x18000727f  mov     eax, esi
0x180007281  mov     rbx, [rsp+28h+arg_0]
0x180007286  mov     rsi, [rsp+28h+arg_8]
0x18000728b  setz    al
0x18000728e  add     rsp, 20h
0x180007292  pop     rdi
0x180007293  retn
0x180007294  mov     ebx, 0CEh
0x180007299  mov     ecx, ebx; dwErrCode
0x18000729b  call    cs:__imp_SetLastError
0x1800072a1  jmp     short loc_18000727D
0x1800072a3  mov     eax, r9d
0x1800072a6  cmp     [rcx+rax*2-2], r8w
0x1800072ac  jz      short loc_1800072BA
0x1800072ae  cmp     word ptr [rcx+rax*2-2], 2Fh ; '/'
0x1800072b4  jnz     loc_1800071CC
0x1800072ba  add     r9d, ebx
0x1800072bd  jmp     loc_1800071CC
0x1800072c2  cmp     r9d, r11d
0x1800072c5  jnb     short loc_1800072E8
0x1800072c7  mov     eax, r9d
0x1800072ca  inc     r9d
0x1800072cd  mov     [rdi+rax*2], r8w
0x1800072d2  jmp     loc_1800071F6
0x1800072d7  cmp     word ptr [rdx], 2Fh ; '/'
0x1800072db  jz      loc_1800071D6
0x1800072e1  mov     ecx, esi
0x1800072e3  jmp     loc_1800071DE
0x1800072e8  mov     ebx, 0CEh
0x1800072ed  jmp     loc_18000726C
0x1800072f2  mov     edx, 80070057h
0x1800072f7  jmp     short loc_180007303
0x1800072f9  mov     edx, 80070057h
0x1800072fe  test    r8, r8
0x180007301  jz      short loc_180007307
0x180007303  mov     [r9], si
0x180007307  movzx   ebx, dx
0x18000730a  jmp     loc_18000726C
```
