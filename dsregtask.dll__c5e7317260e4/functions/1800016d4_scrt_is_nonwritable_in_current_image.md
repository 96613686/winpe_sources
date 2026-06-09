# __scrt_is_nonwritable_in_current_image

- ea: `0x1800016d4`
- end: `0x18000176c`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001148`

## callees

- `0x1800016d4`

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
0x1800016d4  sub     rsp, 18h
0x1800016d8  mov     r8, rcx
0x1800016db  mov     eax, 5A4Dh
0x1800016e0  cmp     cs:180000000h, ax
0x1800016e7  jnz     short loc_180001761
0x1800016e9  movsxd  rcx, dword ptr cs:18000003Ch
0x1800016f0  lea     rdx, cs:180000000h
0x1800016f7  add     rcx, rdx
0x1800016fa  cmp     dword ptr [rcx], 4550h
0x180001700  jnz     short loc_180001761
0x180001702  mov     eax, 20Bh
0x180001707  cmp     [rcx+18h], ax
0x18000170b  jnz     short loc_180001761
0x18000170d  sub     r8, rdx
0x180001710  movzx   edx, word ptr [rcx+14h]
0x180001714  add     rdx, 18h
0x180001718  add     rdx, rcx
0x18000171b  movzx   eax, word ptr [rcx+6]
0x18000171f  lea     rcx, [rax+rax*4]
0x180001723  lea     r9, [rdx+rcx*8]
0x180001727  mov     [rsp+18h+var_18], rdx
0x18000172b  cmp     rdx, r9
0x18000172e  jz      short loc_180001748
0x180001730  mov     ecx, [rdx+0Ch]
0x180001733  cmp     r8, rcx
0x180001736  jb      short loc_180001742
0x180001738  mov     eax, [rdx+8]
0x18000173b  add     eax, ecx
0x18000173d  cmp     r8, rax
0x180001740  jb      short loc_18000174A
0x180001742  add     rdx, 28h ; '('
0x180001746  jmp     short loc_180001727
0x180001748  xor     edx, edx
0x18000174a  test    rdx, rdx
0x18000174d  jnz     short loc_180001753
0x18000174f  xor     al, al
0x180001751  jmp     short loc_180001767
0x180001753  cmp     dword ptr [rdx+24h], 0
0x180001757  jge     short loc_18000175D
0x180001759  xor     al, al
0x18000175b  jmp     short loc_180001767
0x18000175d  mov     al, 1
0x18000175f  jmp     short loc_180001767
0x180001761  xor     al, al
0x180001763  jmp     short loc_180001767
0x180001765  xor     al, al
0x180001767  add     rsp, 18h
0x18000176b  retn
0x180003808  push    rbp
0x18000380a  mov     rbp, rdx
0x18000380d  mov     rax, [rcx]
0x180003810  xor     ecx, ecx
0x180003812  cmp     dword ptr [rax], 0C0000005h
0x180003818  setz    cl
0x18000381b  mov     eax, ecx
0x18000381d  pop     rbp
0x18000381e  retn
```
