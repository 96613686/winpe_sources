# __scrt_is_nonwritable_in_current_image

- ea: `0x1800017ec`
- end: `0x180001884`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001158`

## callees

- `0x1800017ec`

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
0x1800017ec  sub     rsp, 18h
0x1800017f0  mov     r8, rcx
0x1800017f3  mov     eax, 5A4Dh
0x1800017f8  cmp     cs:180000000h, ax
0x1800017ff  jnz     short loc_180001879
0x180001801  movsxd  rcx, dword ptr cs:18000003Ch
0x180001808  lea     rdx, cs:180000000h
0x18000180f  add     rcx, rdx
0x180001812  cmp     dword ptr [rcx], 4550h
0x180001818  jnz     short loc_180001879
0x18000181a  mov     eax, 20Bh
0x18000181f  cmp     [rcx+18h], ax
0x180001823  jnz     short loc_180001879
0x180001825  sub     r8, rdx
0x180001828  movzx   edx, word ptr [rcx+14h]
0x18000182c  add     rdx, 18h
0x180001830  add     rdx, rcx
0x180001833  movzx   eax, word ptr [rcx+6]
0x180001837  lea     rcx, [rax+rax*4]
0x18000183b  lea     r9, [rdx+rcx*8]
0x18000183f  mov     [rsp+18h+var_18], rdx
0x180001843  cmp     rdx, r9
0x180001846  jz      short loc_180001860
0x180001848  mov     ecx, [rdx+0Ch]
0x18000184b  cmp     r8, rcx
0x18000184e  jb      short loc_18000185A
0x180001850  mov     eax, [rdx+8]
0x180001853  add     eax, ecx
0x180001855  cmp     r8, rax
0x180001858  jb      short loc_180001862
0x18000185a  add     rdx, 28h ; '('
0x18000185e  jmp     short loc_18000183F
0x180001860  xor     edx, edx
0x180001862  test    rdx, rdx
0x180001865  jnz     short loc_18000186B
0x180001867  xor     al, al
0x180001869  jmp     short loc_18000187F
0x18000186b  cmp     dword ptr [rdx+24h], 0
0x18000186f  jge     short loc_180001875
0x180001871  xor     al, al
0x180001873  jmp     short loc_18000187F
0x180001875  mov     al, 1
0x180001877  jmp     short loc_18000187F
0x180001879  xor     al, al
0x18000187b  jmp     short loc_18000187F
0x18000187d  xor     al, al
0x18000187f  add     rsp, 18h
0x180001883  retn
0x180002398  push    rbp
0x18000239a  mov     rbp, rdx
0x18000239d  mov     rax, [rcx]
0x1800023a0  xor     ecx, ecx
0x1800023a2  cmp     dword ptr [rax], 0C0000005h
0x1800023a8  setz    cl
0x1800023ab  mov     eax, ecx
0x1800023ad  pop     rbp
0x1800023ae  retn
```
