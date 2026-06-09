# itrp_SH_Common

- ea: `0x14002ddc0`
- end: `0x14002dedf`
- name: `itrp_SH_Common`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002d8c0`

## callees

- `0x14000ff80`
- `0x14002ddc0`
- `0x140098010`

## pseudocode

```c
_QWORD *__fastcall itrp_SH_Common(__int64 a1, _DWORD *a2, _DWORD *a3, _DWORD *a4, char a5)
{
  __int64 v5; // r10
  _QWORD *v10; // rdi
  __int64 v11; // rsi
  int v12; // eax
  int v13; // edx
  __int64 v14; // r11
  __int64 v15; // rcx
  __int64 v16; // rax
  _QWORD *result; // rax
  int v18; // r12d
  __int64 v19; // rax

  v5 = a1;
  if ( (a5 & 1) == 0 )
    v5 = a1 + 8;
  v10 = *(_QWORD **)v5;
  v11 = *(int *)(a1 + 4LL * !(a5 & 1) + 84);
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(a1 + 112))(
          a1,
          (unsigned int)(*(_DWORD *)(4 * v11 + **(_QWORD **)v5)
                       - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v5 + 16LL) + 4 * v11)),
          (unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v5 + 8LL) + 4 * v11)
                       - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v5 + 24LL) + 4 * v11)));
  v13 = *(__int16 *)(a1 + 98);
  v14 = v12;
  *a3 = 0;
  *a2 = 0;
  v15 = *(__int16 *)(a1 + 28);
  if ( (_WORD)v13 == 0x4000 )
  {
    if ( (_WORD)v15 )
      *a2 = (((v12 * v15) >> 13) + 1) >> 1;
    v16 = *(__int16 *)(a1 + 30);
    *a4 = v11;
    if ( (_WORD)v16 )
      *a3 = (((v14 * v16) >> 13) + 1) >> 1;
    return v10;
  }
  else
  {
    v18 = v13;
    if ( (_WORD)v15 )
      *a2 = CompDiv(v13, v12 * (__int64)*(__int16 *)(a1 + 28));
    v19 = *(__int16 *)(a1 + 30);
    if ( (_WORD)v19 )
      *a3 = CompDiv(v18, v14 * v19);
    result = v10;
    *a4 = v11;
  }
  return result;
}

```

## disassembly

```asm
0x14002ddc0  push    rbx
0x14002ddc2  push    rbp
0x14002ddc3  push    rsi
0x14002ddc4  push    rdi
0x14002ddc5  push    r14
0x14002ddc7  push    r15
0x14002ddc9  sub     rsp, 28h
0x14002ddcd  mov     r11d, [rsp+58h+arg_20]
0x14002ddd5  lea     rax, [rcx+8]
0x14002ddd9  mov     r10, rcx
0x14002dddc  mov     rbx, rcx
0x14002dddf  and     r11d, 1
0x14002dde3  mov     r14, r8
0x14002dde6  mov     rbp, rdx
0x14002dde9  mov     r15, r9
0x14002ddec  cmovz   r10, rax
0x14002ddf0  xor     r11, 1
0x14002ddf4  mov     rdi, [r10]
0x14002ddf7  movsxd  rsi, dword ptr [rcx+r11*4+54h]
0x14002ddfc  lea     r9, ds:0[rsi*4]
0x14002de04  mov     rcx, [rdi+8]
0x14002de08  mov     rax, [rdi+18h]
0x14002de0c  mov     r8d, [rcx+r9]
0x14002de10  mov     rcx, [rdi]
0x14002de13  sub     r8d, [rax+r9]
0x14002de17  mov     rax, [rdi+10h]
0x14002de1b  mov     edx, [r9+rcx]
0x14002de1f  mov     rcx, rbx
0x14002de22  sub     edx, [rax+r9]
0x14002de26  mov     rax, [rbx+70h]
0x14002de2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002de2f  movsx   edx, word ptr [rbx+62h]
0x14002de33  xor     ecx, ecx
0x14002de35  movsxd  r11, eax
0x14002de38  mov     eax, 4000h
0x14002de3d  mov     [r14], ecx
0x14002de40  mov     [rbp+0], ecx
0x14002de43  movsx   rcx, word ptr [rbx+1Ch]
0x14002de48  cmp     dx, ax
0x14002de4b  jnz     short loc_14002DE97
0x14002de4d  test    cx, cx
0x14002de50  jz      short loc_14002DE66
0x14002de52  mov     rax, rcx
0x14002de55  imul    rax, r11
0x14002de59  sar     rax, 0Dh
0x14002de5d  inc     rax
0x14002de60  sar     rax, 1
0x14002de63  mov     [rbp+0], eax
0x14002de66  movsx   rax, word ptr [rbx+1Eh]
0x14002de6b  mov     [r15], esi
0x14002de6e  test    ax, ax
0x14002de71  jz      short loc_14002DE87
0x14002de73  mov     rcx, rax
0x14002de76  imul    rcx, r11
0x14002de7a  sar     rcx, 0Dh
0x14002de7e  inc     rcx
0x14002de81  sar     rcx, 1
0x14002de84  mov     [r14], ecx
0x14002de87  mov     rax, rdi
0x14002de8a  add     rsp, 28h
0x14002de8e  pop     r15
0x14002de90  pop     r14
0x14002de92  pop     rdi
0x14002de93  pop     rsi
0x14002de94  pop     rbp
0x14002de95  pop     rbx
0x14002de96  retn
0x14002de97  mov     [rsp+58h+arg_0], r12
0x14002de9c  mov     r12d, edx
0x14002de9f  test    cx, cx
0x14002dea2  jz      short loc_14002DEB6
0x14002dea4  mov     rdx, rcx
0x14002dea7  mov     ecx, r12d
0x14002deaa  imul    rdx, r11
0x14002deae  call    CompDiv
0x14002deb3  mov     [rbp+0], eax
0x14002deb6  movsx   rax, word ptr [rbx+1Eh]
0x14002debb  test    ax, ax
0x14002debe  jz      short loc_14002DED2
0x14002dec0  mov     rdx, rax
0x14002dec3  mov     ecx, r12d
0x14002dec6  imul    rdx, r11
0x14002deca  call    CompDiv
0x14002decf  mov     [r14], eax
0x14002ded2  mov     r12, [rsp+58h+arg_0]
0x14002ded7  mov     rax, rdi
0x14002deda  mov     [r15], esi
0x14002dedd  jmp     short loc_14002DE8A
```
