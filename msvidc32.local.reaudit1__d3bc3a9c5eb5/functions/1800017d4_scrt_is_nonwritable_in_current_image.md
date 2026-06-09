# __scrt_is_nonwritable_in_current_image

- ea: `0x1800017d4`
- end: `0x18000186c`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x1800017d4`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  _DWORD *v2; // rcx
  unsigned __int64 v3; // r8
  _DWORD *v4; // rdx
  _DWORD *v5; // r9
  unsigned __int64 v6; // rcx

  if ( MEMORY[0x180000000] != 23117 )
    return 0;
  v2 = (_DWORD *)(0x180000000LL + MEMORY[0x18000003C]);
  if ( *v2 != 17744 || *(_WORD *)(0x180000018LL + MEMORY[0x18000003C]) != 523 )
    return 0;
  v3 = a1 - 0x180000000LL;
  v4 = (_DWORD *)((char *)v2 + *(unsigned __int16 *)(0x180000014LL + MEMORY[0x18000003C]) + 24);
  v5 = &v4[10 * *(unsigned __int16 *)(0x180000006LL + MEMORY[0x18000003C])];
  while ( v4 != v5 )
  {
    v6 = (unsigned int)v4[3];
    if ( v3 >= v6 && v3 < (unsigned int)(v6 + v4[2]) )
      return v4 && v4[9] >= 0;
    v4 += 10;
  }
  v4 = 0;
  return v4 && v4[9] >= 0;
}

```

## disassembly

```asm
0x1800017d4  sub     rsp, 18h
0x1800017d8  mov     r8, rcx
0x1800017db  mov     eax, 5A4Dh
0x1800017e0  cmp     cs:180000000h, ax
0x1800017e7  jnz     short loc_180001861
0x1800017e9  movsxd  rcx, dword ptr cs:18000003Ch
0x1800017f0  lea     rdx, cs:180000000h
0x1800017f7  add     rcx, rdx
0x1800017fa  cmp     dword ptr [rcx], 4550h
0x180001800  jnz     short loc_180001861
0x180001802  mov     eax, 20Bh
0x180001807  cmp     [rcx+18h], ax
0x18000180b  jnz     short loc_180001861
0x18000180d  sub     r8, rdx
0x180001810  movzx   edx, word ptr [rcx+14h]
0x180001814  add     rdx, 18h
0x180001818  add     rdx, rcx
0x18000181b  movzx   eax, word ptr [rcx+6]
0x18000181f  lea     rcx, [rax+rax*4]
0x180001823  lea     r9, [rdx+rcx*8]
0x180001827  mov     [rsp+18h+var_18], rdx
0x18000182b  cmp     rdx, r9
0x18000182e  jz      short loc_180001848
0x180001830  mov     ecx, [rdx+0Ch]
0x180001833  cmp     r8, rcx
0x180001836  jb      short loc_180001842
0x180001838  mov     eax, [rdx+8]
0x18000183b  add     eax, ecx
0x18000183d  cmp     r8, rax
0x180001840  jb      short loc_18000184A
0x180001842  add     rdx, 28h ; '('
0x180001846  jmp     short loc_180001827
0x180001848  xor     edx, edx
0x18000184a  test    rdx, rdx
0x18000184d  jnz     short loc_180001853
0x18000184f  xor     al, al
0x180001851  jmp     short loc_180001867
0x180001853  cmp     dword ptr [rdx+24h], 0
0x180001857  jge     short loc_18000185D
0x180001859  xor     al, al
0x18000185b  jmp     short loc_180001867
0x18000185d  mov     al, 1
0x18000185f  jmp     short loc_180001867
0x180001861  xor     al, al
0x180001863  jmp     short loc_180001867
0x180001865  xor     al, al
0x180001867  add     rsp, 18h
0x18000186b  retn
0x180007d98  push    rbp
0x180007d9a  mov     rbp, rdx
0x180007d9d  mov     rax, [rcx]
0x180007da0  xor     ecx, ecx
0x180007da2  cmp     dword ptr [rax], 0C0000005h
0x180007da8  setz    cl
0x180007dab  mov     eax, ecx
0x180007dad  pop     rbp
0x180007dae  retn
```
