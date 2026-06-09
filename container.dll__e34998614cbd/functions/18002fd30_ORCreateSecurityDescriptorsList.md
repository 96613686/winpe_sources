# ORCreateSecurityDescriptorsList

- ea: `0x18002fd30`
- end: `0x18002fedb`
- name: `ORCreateSecurityDescriptorsList`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e6d0`

## callees

- `0x18000354e`
- `0x18002f7f8`
- `0x18002fd30`
- `0x18002fee4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002fd7e`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002fe1f`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002fd7e`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002fe1f`

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
0x18002fd30  push    rbx
0x18002fd32  push    rbp
0x18002fd33  push    rsi
0x18002fd34  push    rdi
0x18002fd35  push    r13
0x18002fd37  push    r14
0x18002fd39  push    r15
0x18002fd3b  sub     rsp, 20h
0x18002fd3f  mov     rax, rdx
0x18002fd42  mov     rsi, rcx
0x18002fd45  mov     rdx, [rcx+10h]
0x18002fd49  mov     ecx, [rax+2Ch]
0x18002fd4c  call    ORConvertOffsetToAbsolute
0x18002fd51  mov     rdi, rax
0x18002fd54  test    rax, rax
0x18002fd57  jz      loc_18002FEBC
0x18002fd5d  cmp     dword ptr [rax], 0
0x18002fd60  jg      loc_18002FEBC
0x18002fd66  lea     rbx, [rax+4]
0x18002fd6a  mov     r13d, 6B73h
0x18002fd70  cmp     [rbx], r13w
0x18002fd74  jnz     loc_18002FEBC
0x18002fd7a  lea     rcx, [rbx+14h]; pSecurityDescriptor
0x18002fd7e  call    cs:__imp_IsValidSecurityDescriptor
0x18002fd85  nop     dword ptr [rax+rax+00h]
0x18002fd8a  test    eax, eax
0x18002fd8c  jz      loc_18002FEBC
0x18002fd92  mov     edx, 10h; Alignment
0x18002fd97  lea     ecx, [rdx+18h]; Size
0x18002fd9a  call    _o__aligned_malloc_0
0x18002fd9f  test    rax, rax
0x18002fda2  jnz     short loc_18002FDAE
0x18002fda4  mov     ebx, 8
0x18002fda9  jmp     loc_18002FEC1
0x18002fdae  mov     qword ptr [rax], 0
0x18002fdb5  lea     rbp, [rsi+40h]
0x18002fdb9  mov     qword ptr [rax+8], 0
0x18002fdc1  mov     qword ptr [rax+18h], 0
0x18002fdc9  mov     qword ptr [rax+20h], 0
0x18002fdd1  mov     [rax+10h], rbx
0x18002fdd5  mov     rcx, [rbp+8]
0x18002fdd9  cmp     [rcx], rbp
0x18002fddc  jnz     loc_18002FEB5
0x18002fde2  mov     [rax], rbp
0x18002fde5  mov     r15, rdi
0x18002fde8  mov     [rax+8], rcx
0x18002fdec  mov     [rcx], rax
0x18002fdef  mov     [rbp+8], rax
0x18002fdf3  mov     ecx, [rbx+4]
0x18002fdf6  jmp     loc_18002FE9C
0x18002fdfb  test    rbx, rbx
0x18002fdfe  jz      loc_18002FEBC
0x18002fe04  cmp     dword ptr [rbx], 0
0x18002fe07  jg      loc_18002FEBC
0x18002fe0d  lea     r14, [rbx+4]
0x18002fe11  cmp     [r14], r13w
0x18002fe15  jnz     loc_18002FEBC
0x18002fe1b  lea     rcx, [rbx+18h]; pSecurityDescriptor
0x18002fe1f  call    cs:__imp_IsValidSecurityDescriptor
0x18002fe26  nop     dword ptr [rax+rax+00h]
0x18002fe2b  test    eax, eax
0x18002fe2d  jz      loc_18002FEBC
0x18002fe33  mov     rdx, [rsi+10h]
0x18002fe37  mov     ecx, [r14+8]
0x18002fe3b  call    ORConvertOffsetToAbsolute
0x18002fe40  cmp     rax, r15
0x18002fe43  jnz     short loc_18002FEBC
0x18002fe45  mov     edx, 10h; Alignment
0x18002fe4a  lea     ecx, [rdx+18h]; Size
0x18002fe4d  call    _o__aligned_malloc_0
0x18002fe52  test    rax, rax
0x18002fe55  jz      loc_18002FDA4
0x18002fe5b  mov     qword ptr [rax], 0
0x18002fe62  mov     qword ptr [rax+8], 0
0x18002fe6a  mov     qword ptr [rax+18h], 0
0x18002fe72  mov     qword ptr [rax+20h], 0
0x18002fe7a  mov     [rax+10h], r14
0x18002fe7e  mov     rcx, [rbp+8]
0x18002fe82  cmp     [rcx], rbp
0x18002fe85  jnz     short loc_18002FEB5
0x18002fe87  mov     [rax], rbp
0x18002fe8a  mov     r15, rbx
0x18002fe8d  mov     [rax+8], rcx
0x18002fe91  mov     [rcx], rax
0x18002fe94  mov     [rbp+8], rax
0x18002fe98  mov     ecx, [r14+4]
0x18002fe9c  mov     rdx, [rsi+10h]
0x18002fea0  call    ORConvertOffsetToAbsolute
0x18002fea5  mov     rbx, rax
0x18002fea8  cmp     rax, rdi
0x18002feab  jnz     loc_18002FDFB
0x18002feb1  xor     ebx, ebx
0x18002feb3  jmp     short loc_18002FEC9
0x18002feb5  mov     ecx, 3
0x18002feba  int     29h; Win8: RtlFailFast(ecx)
0x18002febc  mov     ebx, 3F1h
0x18002fec1  mov     rcx, rsi
0x18002fec4  call    ORFreeSecurityCellList
0x18002fec9  mov     eax, ebx
0x18002fecb  add     rsp, 20h
0x18002fecf  pop     r15
0x18002fed1  pop     r14
0x18002fed3  pop     r13
0x18002fed5  pop     rdi
0x18002fed6  pop     rsi
0x18002fed7  pop     rbp
0x18002fed8  pop     rbx
0x18002fed9  retn
```
