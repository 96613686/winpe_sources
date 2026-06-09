# MupAllocFileContextForRelativeOpen

- ea: `0x140019380`
- end: `0x1400194e0`
- name: `MupAllocFileContextForRelativeOpen`
- size: `352`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140019598`

## callees

- `0x1400056c0`
- `0x140019380`
- `0x1400194f0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140019437`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140019437`

## pseudocode

```c
__int64 __fastcall MupAllocFileContextForRelativeOpen(PCUNICODE_STRING Source, __int64 a2, __int64 *a3)
{
  __int64 v4; // rsi
  int v6; // r14d
  char v7; // r12
  int v8; // r9d
  __int64 v9; // rbp
  unsigned int v10; // eax
  unsigned int appended; // edi
  _WORD *v12; // rbx
  __int16 v14; // dx
  char v15; // [rsp+60h] [rbp+8h]

  v4 = *(unsigned __int16 *)(a2 + 96) >> 1;
  v6 = Source->Length >> 1;
  v7 = 0;
  v15 = 0;
  v8 = *(unsigned __int16 *)(a2 + 96) >> 1;
  if ( v6 && (_DWORD)v4 )
  {
    v14 = *(_WORD *)(*(_QWORD *)(a2 + 104) + 2LL * (unsigned int)(v4 - 1));
    if ( *Source->Buffer == 58 )
    {
      if ( v14 == 92 )
      {
        v7 = 1;
        v8 = v4 - 1;
      }
    }
    else if ( v14 != 92 )
    {
      v15 = 1;
      v8 = v4 + 1;
    }
  }
  if ( (unsigned int)(2 * (v6 + v8)) > 0xFFFE )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v9 = MupAllocFileContext();
    if ( v9 )
    {
      v10 = *(unsigned __int16 *)(a2 + 96);
      appended = 0;
      v12 = (_WORD *)(v9 + 96);
      if ( (_WORD)v10 )
      {
        *v12 = v10;
        *(_OWORD *)(v9 + 40) = *(_OWORD *)v12;
        memmove(*(void **)(v9 + 104), *(const void **)(a2 + 104), v10);
      }
      if ( v15 )
      {
        *(_WORD *)(*(_QWORD *)(v9 + 104) + 2 * v4) = 92;
        *v12 += 2;
      }
      else if ( v7 )
      {
        *v12 -= 2;
      }
      if ( v6 )
        appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)(v9 + 96), Source);
      *(_WORD *)(v9 + 40) = *v12;
      if ( !appended )
        *a3 = v9;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return appended;
}

```

## disassembly

```asm
0x140019380  mov     [rsp+arg_8], rbx
0x140019385  mov     [rsp+arg_10], r8
0x14001938a  push    rbp
0x14001938b  push    rsi
0x14001938c  push    rdi
0x14001938d  push    r12
0x14001938f  push    r13
0x140019391  push    r14
0x140019393  push    r15
0x140019395  sub     rsp, 20h
0x140019399  movzx   esi, word ptr [rdx+60h]
0x14001939d  xor     ebx, ebx
0x14001939f  movzx   r14d, word ptr [rcx]
0x1400193a3  mov     r15, rdx
0x1400193a6  shr     esi, 1
0x1400193a8  mov     r13, rcx
0x1400193ab  shr     r14d, 1
0x1400193ae  mov     r12b, bl
0x1400193b1  lea     r10d, [rbx+5Ch]
0x1400193b5  mov     [rsp+58h+arg_0], bl
0x1400193b9  mov     r9d, esi
0x1400193bc  jnz     loc_140019470
0x1400193c2  lea     ecx, [r14+r9]
0x1400193c6  lea     eax, [rcx+rcx]
0x1400193c9  cmp     eax, 0FFFEh
0x1400193ce  ja      loc_1400194BC
0x1400193d4  call    MupAllocFileContext
0x1400193d9  mov     rbp, rax
0x1400193dc  test    rax, rax
0x1400193df  jz      loc_1400194C3
0x1400193e5  movzx   eax, word ptr [r15+60h]
0x1400193ea  mov     edi, ebx
0x1400193ec  lea     rbx, [rbp+60h]
0x1400193f0  test    ax, ax
0x1400193f3  jz      short loc_140019410
0x1400193f5  mov     [rbx], ax
0x1400193f8  mov     r8d, eax; Size
0x1400193fb  movups  xmm0, xmmword ptr [rbx]
0x1400193fe  movdqu  xmmword ptr [rbp+28h], xmm0
0x140019403  mov     rdx, [r15+68h]; Src
0x140019407  mov     rcx, [rbx+8]; void *
0x14001940b  call    memmove
0x140019410  xor     r15d, r15d
0x140019413  cmp     [rsp+58h+arg_0], r15b
0x140019418  jz      loc_1400194CA
0x14001941e  mov     rax, [rbx+8]
0x140019422  mov     word ptr [rax+rsi*2], 5Ch ; '\'
0x140019428  add     word ptr [rbx], 2
0x14001942c  test    r14d, r14d
0x14001942f  jz      short loc_140019445
0x140019431  mov     rdx, r13; Source
0x140019434  mov     rcx, rbx; Destination
0x140019437  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001943e  nop     dword ptr [rax+rax+00h]
0x140019443  mov     edi, eax
0x140019445  movzx   ecx, word ptr [rbx]
0x140019448  mov     [rbp+28h], cx
0x14001944c  test    edi, edi
0x14001944e  jnz     short loc_140019458
0x140019450  mov     rax, [rsp+58h+arg_10]
0x140019455  mov     [rax], rbp
0x140019458  mov     rbx, [rsp+58h+arg_8]
0x14001945d  mov     eax, edi
0x14001945f  add     rsp, 20h
0x140019463  pop     r15
0x140019465  pop     r14
0x140019467  pop     r13
0x140019469  pop     r12
0x14001946b  pop     rdi
0x14001946c  pop     rsi
0x14001946d  pop     rbp
0x14001946e  retn
0x140019470  test    esi, esi
0x140019472  jz      loc_1400193C2
0x140019478  mov     rax, [rdx+68h]
0x14001947c  lea     r8d, [rsi-1]
0x140019480  movzx   edx, word ptr [rax+r8*2]
0x140019485  mov     rax, [rcx+8]
0x140019489  cmp     word ptr [rax], 3Ah ; ':'
0x14001948d  jz      short loc_1400194A7
0x14001948f  cmp     dx, r10w
0x140019493  jz      loc_1400193C2
0x140019499  mov     [rsp+58h+arg_0], 1
0x14001949e  lea     r9d, [rsi+1]
0x1400194a2  jmp     loc_1400193C2
0x1400194a7  cmp     dx, r10w
0x1400194ab  jnz     loc_1400193C2
0x1400194b1  mov     r12b, 1
0x1400194b4  mov     r9d, r8d
0x1400194b7  jmp     loc_1400193C2
0x1400194bc  mov     edi, 0C000000Dh
0x1400194c1  jmp     short loc_140019458
0x1400194c3  mov     edi, 0C000009Ah
0x1400194c8  jmp     short loc_140019458
0x1400194ca  test    r12b, r12b
0x1400194cd  jz      loc_14001942C
0x1400194d3  mov     eax, 0FFFEh
0x1400194d8  add     [rbx], ax
0x1400194db  jmp     loc_14001942C
```
