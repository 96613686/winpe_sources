# MupAllocFileContextForRelativeOpen

- ea: `0x140019330`
- end: `0x140019490`
- name: `MupAllocFileContextForRelativeOpen`
- size: `352`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140019548`

## callees

- `0x1400056c0`
- `0x140019330`
- `0x1400194a0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400193e7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400193e7`

## pseudocode

```c
__int64 __fastcall MupAllocFileContextForRelativeOpen(PCUNICODE_STRING Source, __int64 a2, __int64 *a3)
{
  __int64 v4; // rsi
  int v6; // r14d
  char v7; // r12
  int v8; // r9d
  __int64 v9; // rcx
  __int64 v10; // rbp
  unsigned int v11; // eax
  unsigned int appended; // edi
  _WORD *v13; // rbx
  __int16 v15; // dx
  char v16; // [rsp+60h] [rbp+8h]

  v4 = *(unsigned __int16 *)(a2 + 96) >> 1;
  v6 = Source->Length >> 1;
  v7 = 0;
  v16 = 0;
  v8 = *(unsigned __int16 *)(a2 + 96) >> 1;
  if ( v6 && (_DWORD)v4 )
  {
    v15 = *(_WORD *)(*(_QWORD *)(a2 + 104) + 2LL * (unsigned int)(v4 - 1));
    if ( *Source->Buffer == 58 )
    {
      if ( v15 == 92 )
      {
        v7 = 1;
        v8 = v4 - 1;
      }
    }
    else if ( v15 != 92 )
    {
      v16 = 1;
      v8 = v4 + 1;
    }
  }
  v9 = (unsigned int)(v6 + v8);
  if ( (unsigned int)(2 * v9) > 0xFFFE )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v10 = MupAllocFileContext(v9);
    if ( v10 )
    {
      v11 = *(unsigned __int16 *)(a2 + 96);
      appended = 0;
      v13 = (_WORD *)(v10 + 96);
      if ( (_WORD)v11 )
      {
        *v13 = v11;
        *(_OWORD *)(v10 + 40) = *(_OWORD *)v13;
        memmove(*(void **)(v10 + 104), *(const void **)(a2 + 104), v11);
      }
      if ( v16 )
      {
        *(_WORD *)(*(_QWORD *)(v10 + 104) + 2 * v4) = 92;
        *v13 += 2;
      }
      else if ( v7 )
      {
        *v13 -= 2;
      }
      if ( v6 )
        appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)(v10 + 96), Source);
      *(_WORD *)(v10 + 40) = *v13;
      if ( !appended )
        *a3 = v10;
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
0x140019330  mov     [rsp+arg_8], rbx
0x140019335  mov     [rsp+arg_10], r8
0x14001933a  push    rbp
0x14001933b  push    rsi
0x14001933c  push    rdi
0x14001933d  push    r12
0x14001933f  push    r13
0x140019341  push    r14
0x140019343  push    r15
0x140019345  sub     rsp, 20h
0x140019349  movzx   esi, word ptr [rdx+60h]
0x14001934d  xor     ebx, ebx
0x14001934f  movzx   r14d, word ptr [rcx]
0x140019353  mov     r15, rdx
0x140019356  shr     esi, 1
0x140019358  mov     r13, rcx
0x14001935b  shr     r14d, 1
0x14001935e  mov     r12b, bl
0x140019361  lea     r10d, [rbx+5Ch]
0x140019365  mov     [rsp+58h+arg_0], bl
0x140019369  mov     r9d, esi
0x14001936c  jnz     loc_140019420
0x140019372  lea     ecx, [r14+r9]
0x140019376  lea     eax, [rcx+rcx]
0x140019379  cmp     eax, 0FFFEh
0x14001937e  ja      loc_14001946C
0x140019384  call    MupAllocFileContext
0x140019389  mov     rbp, rax
0x14001938c  test    rax, rax
0x14001938f  jz      loc_140019473
0x140019395  movzx   eax, word ptr [r15+60h]
0x14001939a  mov     edi, ebx
0x14001939c  lea     rbx, [rbp+60h]
0x1400193a0  test    ax, ax
0x1400193a3  jz      short loc_1400193C0
0x1400193a5  mov     [rbx], ax
0x1400193a8  mov     r8d, eax; Size
0x1400193ab  movups  xmm0, xmmword ptr [rbx]
0x1400193ae  movdqu  xmmword ptr [rbp+28h], xmm0
0x1400193b3  mov     rdx, [r15+68h]; Src
0x1400193b7  mov     rcx, [rbx+8]; void *
0x1400193bb  call    memmove
0x1400193c0  xor     r15d, r15d
0x1400193c3  cmp     [rsp+58h+arg_0], r15b
0x1400193c8  jz      loc_14001947A
0x1400193ce  mov     rax, [rbx+8]
0x1400193d2  mov     word ptr [rax+rsi*2], 5Ch ; '\'
0x1400193d8  add     word ptr [rbx], 2
0x1400193dc  test    r14d, r14d
0x1400193df  jz      short loc_1400193F5
0x1400193e1  mov     rdx, r13; Source
0x1400193e4  mov     rcx, rbx; Destination
0x1400193e7  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400193ee  nop     dword ptr [rax+rax+00h]
0x1400193f3  mov     edi, eax
0x1400193f5  movzx   ecx, word ptr [rbx]
0x1400193f8  mov     [rbp+28h], cx
0x1400193fc  test    edi, edi
0x1400193fe  jnz     short loc_140019408
0x140019400  mov     rax, [rsp+58h+arg_10]
0x140019405  mov     [rax], rbp
0x140019408  mov     rbx, [rsp+58h+arg_8]
0x14001940d  mov     eax, edi
0x14001940f  add     rsp, 20h
0x140019413  pop     r15
0x140019415  pop     r14
0x140019417  pop     r13
0x140019419  pop     r12
0x14001941b  pop     rdi
0x14001941c  pop     rsi
0x14001941d  pop     rbp
0x14001941e  retn
0x140019420  test    esi, esi
0x140019422  jz      loc_140019372
0x140019428  mov     rax, [rdx+68h]
0x14001942c  lea     r8d, [rsi-1]
0x140019430  movzx   edx, word ptr [rax+r8*2]
0x140019435  mov     rax, [rcx+8]
0x140019439  cmp     word ptr [rax], 3Ah ; ':'
0x14001943d  jz      short loc_140019457
0x14001943f  cmp     dx, r10w
0x140019443  jz      loc_140019372
0x140019449  mov     [rsp+58h+arg_0], 1
0x14001944e  lea     r9d, [rsi+1]
0x140019452  jmp     loc_140019372
0x140019457  cmp     dx, r10w
0x14001945b  jnz     loc_140019372
0x140019461  mov     r12b, 1
0x140019464  mov     r9d, r8d
0x140019467  jmp     loc_140019372
0x14001946c  mov     edi, 0C000000Dh
0x140019471  jmp     short loc_140019408
0x140019473  mov     edi, 0C000009Ah
0x140019478  jmp     short loc_140019408
0x14001947a  test    r12b, r12b
0x14001947d  jz      loc_1400193DC
0x140019483  mov     eax, 0FFFEh
0x140019488  add     [rbx], ax
0x14001948b  jmp     loc_1400193DC
```
