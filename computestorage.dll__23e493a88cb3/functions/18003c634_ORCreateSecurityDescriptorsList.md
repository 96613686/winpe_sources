# ORCreateSecurityDescriptorsList

- ea: `0x18003c634`
- end: `0x18003c7df`
- name: `ORCreateSecurityDescriptorsList`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003bbfc`

## callees

- `0x180003172`
- `0x180038b00`
- `0x18003c634`
- `0x18003c7e8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003c682`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003c723`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003c682`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003c723`

## pseudocode

```c
__int64 __fastcall ORCreateSecurityDescriptorsList(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 v5; // rbx
  _QWORD *v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rbp
  _QWORD *v9; // rcx
  __int64 v10; // r15
  __int64 i; // rcx
  __int64 v12; // r14
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rbx

  v3 = ORConvertOffsetToAbsolute(*(unsigned int *)(a2 + 44), *(_QWORD *)(a1 + 16));
  v4 = v3;
  if ( !v3
    || *(int *)v3 > 0
    || (v5 = v3 + 4, *(_WORD *)(v3 + 4) != 27507)
    || !IsValidSecurityDescriptor((PSECURITY_DESCRIPTOR)(v3 + 24)) )
  {
LABEL_20:
    v7 = 1009;
    goto LABEL_21;
  }
  v6 = o__aligned_malloc_0(0x28u, 0x10u);
  if ( !v6 )
  {
LABEL_6:
    v7 = 8;
LABEL_21:
    ORFreeSecurityCellList(a1);
    return v7;
  }
  *v6 = 0;
  v8 = a1 + 64;
  v6[1] = 0;
  v6[3] = 0;
  v6[4] = 0;
  v6[2] = v5;
  v9 = *(_QWORD **)(a1 + 72);
  if ( *v9 != a1 + 64 )
LABEL_19:
    __fastfail(3u);
  *v6 = v8;
  v10 = v4;
  v6[1] = v9;
  *v9 = v6;
  *(_QWORD *)(a1 + 72) = v6;
  for ( i = *(unsigned int *)(v5 + 4); ; i = *(unsigned int *)(v16 + 8) )
  {
    v15 = ORConvertOffsetToAbsolute(i, *(_QWORD *)(a1 + 16));
    v16 = v15;
    if ( v15 == v4 )
      break;
    if ( !v15 )
      goto LABEL_20;
    if ( *(int *)v15 > 0 )
      goto LABEL_20;
    v12 = v15 + 4;
    if ( *(_WORD *)(v15 + 4) != 27507
      || !IsValidSecurityDescriptor((PSECURITY_DESCRIPTOR)(v15 + 24))
      || ORConvertOffsetToAbsolute(*(unsigned int *)(v16 + 12), *(_QWORD *)(a1 + 16)) != v10 )
    {
      goto LABEL_20;
    }
    v13 = o__aligned_malloc_0(0x28u, 0x10u);
    if ( !v13 )
      goto LABEL_6;
    *v13 = 0;
    v13[1] = 0;
    v13[3] = 0;
    v13[4] = 0;
    v13[2] = v12;
    v14 = *(_QWORD **)(a1 + 72);
    if ( *v14 != v8 )
      goto LABEL_19;
    *v13 = v8;
    v10 = v16;
    v13[1] = v14;
    *v14 = v13;
    *(_QWORD *)(a1 + 72) = v13;
  }
  return 0;
}

```

## disassembly

```asm
0x18003c634  push    rbx
0x18003c636  push    rbp
0x18003c637  push    rsi
0x18003c638  push    rdi
0x18003c639  push    r13
0x18003c63b  push    r14
0x18003c63d  push    r15
0x18003c63f  sub     rsp, 20h
0x18003c643  mov     rax, rdx
0x18003c646  mov     rsi, rcx
0x18003c649  mov     rdx, [rcx+10h]
0x18003c64d  mov     ecx, [rax+2Ch]
0x18003c650  call    ORConvertOffsetToAbsolute
0x18003c655  mov     rdi, rax
0x18003c658  test    rax, rax
0x18003c65b  jz      loc_18003C7C0
0x18003c661  cmp     dword ptr [rax], 0
0x18003c664  jg      loc_18003C7C0
0x18003c66a  lea     rbx, [rax+4]
0x18003c66e  mov     r13d, 6B73h
0x18003c674  cmp     [rbx], r13w
0x18003c678  jnz     loc_18003C7C0
0x18003c67e  lea     rcx, [rbx+14h]; pSecurityDescriptor
0x18003c682  call    cs:__imp_IsValidSecurityDescriptor
0x18003c689  nop     dword ptr [rax+rax+00h]
0x18003c68e  test    eax, eax
0x18003c690  jz      loc_18003C7C0
0x18003c696  mov     edx, 10h; Alignment
0x18003c69b  lea     ecx, [rdx+18h]; Size
0x18003c69e  call    _o__aligned_malloc_0
0x18003c6a3  test    rax, rax
0x18003c6a6  jnz     short loc_18003C6B2
0x18003c6a8  mov     ebx, 8
0x18003c6ad  jmp     loc_18003C7C5
0x18003c6b2  mov     qword ptr [rax], 0
0x18003c6b9  lea     rbp, [rsi+40h]
0x18003c6bd  mov     qword ptr [rax+8], 0
0x18003c6c5  mov     qword ptr [rax+18h], 0
0x18003c6cd  mov     qword ptr [rax+20h], 0
0x18003c6d5  mov     [rax+10h], rbx
0x18003c6d9  mov     rcx, [rbp+8]
0x18003c6dd  cmp     [rcx], rbp
0x18003c6e0  jnz     loc_18003C7B9
0x18003c6e6  mov     [rax], rbp
0x18003c6e9  mov     r15, rdi
0x18003c6ec  mov     [rax+8], rcx
0x18003c6f0  mov     [rcx], rax
0x18003c6f3  mov     [rbp+8], rax
0x18003c6f7  mov     ecx, [rbx+4]
0x18003c6fa  jmp     loc_18003C7A0
0x18003c6ff  test    rbx, rbx
0x18003c702  jz      loc_18003C7C0
0x18003c708  cmp     dword ptr [rbx], 0
0x18003c70b  jg      loc_18003C7C0
0x18003c711  lea     r14, [rbx+4]
0x18003c715  cmp     [r14], r13w
0x18003c719  jnz     loc_18003C7C0
0x18003c71f  lea     rcx, [rbx+18h]; pSecurityDescriptor
0x18003c723  call    cs:__imp_IsValidSecurityDescriptor
0x18003c72a  nop     dword ptr [rax+rax+00h]
0x18003c72f  test    eax, eax
0x18003c731  jz      loc_18003C7C0
0x18003c737  mov     rdx, [rsi+10h]
0x18003c73b  mov     ecx, [r14+8]
0x18003c73f  call    ORConvertOffsetToAbsolute
0x18003c744  cmp     rax, r15
0x18003c747  jnz     short loc_18003C7C0
0x18003c749  mov     edx, 10h; Alignment
0x18003c74e  lea     ecx, [rdx+18h]; Size
0x18003c751  call    _o__aligned_malloc_0
0x18003c756  test    rax, rax
0x18003c759  jz      loc_18003C6A8
0x18003c75f  mov     qword ptr [rax], 0
0x18003c766  mov     qword ptr [rax+8], 0
0x18003c76e  mov     qword ptr [rax+18h], 0
0x18003c776  mov     qword ptr [rax+20h], 0
0x18003c77e  mov     [rax+10h], r14
0x18003c782  mov     rcx, [rbp+8]
0x18003c786  cmp     [rcx], rbp
0x18003c789  jnz     short loc_18003C7B9
0x18003c78b  mov     [rax], rbp
0x18003c78e  mov     r15, rbx
0x18003c791  mov     [rax+8], rcx
0x18003c795  mov     [rcx], rax
0x18003c798  mov     [rbp+8], rax
0x18003c79c  mov     ecx, [r14+4]
0x18003c7a0  mov     rdx, [rsi+10h]
0x18003c7a4  call    ORConvertOffsetToAbsolute
0x18003c7a9  mov     rbx, rax
0x18003c7ac  cmp     rax, rdi
0x18003c7af  jnz     loc_18003C6FF
0x18003c7b5  xor     ebx, ebx
0x18003c7b7  jmp     short loc_18003C7CD
0x18003c7b9  mov     ecx, 3
0x18003c7be  int     29h; Win8: RtlFailFast(ecx)
0x18003c7c0  mov     ebx, 3F1h
0x18003c7c5  mov     rcx, rsi
0x18003c7c8  call    ORFreeSecurityCellList
0x18003c7cd  mov     eax, ebx
0x18003c7cf  add     rsp, 20h
0x18003c7d3  pop     r15
0x18003c7d5  pop     r14
0x18003c7d7  pop     r13
0x18003c7d9  pop     rdi
0x18003c7da  pop     rsi
0x18003c7db  pop     rbp
0x18003c7dc  pop     rbx
0x18003c7dd  retn
```
