# ORCreateSecurityDescriptorsList

- ea: `0x140028e6c`
- end: `0x140029017`
- name: `ORCreateSecurityDescriptorsList`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140029848`

## callees

- `0x1400029d2`
- `0x140026cac`
- `0x140028e6c`
- `0x140029020`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140028eba`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140028f5b`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140028eba`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140028f5b`

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
0x140028e6c  push    rbx
0x140028e6e  push    rbp
0x140028e6f  push    rsi
0x140028e70  push    rdi
0x140028e71  push    r13
0x140028e73  push    r14
0x140028e75  push    r15
0x140028e77  sub     rsp, 20h
0x140028e7b  mov     rax, rdx
0x140028e7e  mov     rsi, rcx
0x140028e81  mov     rdx, [rcx+10h]
0x140028e85  mov     ecx, [rax+2Ch]
0x140028e88  call    ORConvertOffsetToAbsolute
0x140028e8d  mov     rdi, rax
0x140028e90  test    rax, rax
0x140028e93  jz      loc_140028FF8
0x140028e99  cmp     dword ptr [rax], 0
0x140028e9c  jg      loc_140028FF8
0x140028ea2  lea     rbx, [rax+4]
0x140028ea6  mov     r13d, 6B73h
0x140028eac  cmp     [rbx], r13w
0x140028eb0  jnz     loc_140028FF8
0x140028eb6  lea     rcx, [rbx+14h]; pSecurityDescriptor
0x140028eba  call    cs:__imp_IsValidSecurityDescriptor
0x140028ec1  nop     dword ptr [rax+rax+00h]
0x140028ec6  test    eax, eax
0x140028ec8  jz      loc_140028FF8
0x140028ece  mov     edx, 10h; Alignment
0x140028ed3  lea     ecx, [rdx+18h]; Size
0x140028ed6  call    _o__aligned_malloc_0
0x140028edb  test    rax, rax
0x140028ede  jnz     short loc_140028EEA
0x140028ee0  mov     ebx, 8
0x140028ee5  jmp     loc_140028FFD
0x140028eea  mov     qword ptr [rax], 0
0x140028ef1  lea     rbp, [rsi+40h]
0x140028ef5  mov     qword ptr [rax+8], 0
0x140028efd  mov     qword ptr [rax+18h], 0
0x140028f05  mov     qword ptr [rax+20h], 0
0x140028f0d  mov     [rax+10h], rbx
0x140028f11  mov     rcx, [rbp+8]
0x140028f15  cmp     [rcx], rbp
0x140028f18  jnz     loc_140028FF1
0x140028f1e  mov     [rax], rbp
0x140028f21  mov     r15, rdi
0x140028f24  mov     [rax+8], rcx
0x140028f28  mov     [rcx], rax
0x140028f2b  mov     [rbp+8], rax
0x140028f2f  mov     ecx, [rbx+4]
0x140028f32  jmp     loc_140028FD8
0x140028f37  test    rbx, rbx
0x140028f3a  jz      loc_140028FF8
0x140028f40  cmp     dword ptr [rbx], 0
0x140028f43  jg      loc_140028FF8
0x140028f49  lea     r14, [rbx+4]
0x140028f4d  cmp     [r14], r13w
0x140028f51  jnz     loc_140028FF8
0x140028f57  lea     rcx, [rbx+18h]; pSecurityDescriptor
0x140028f5b  call    cs:__imp_IsValidSecurityDescriptor
0x140028f62  nop     dword ptr [rax+rax+00h]
0x140028f67  test    eax, eax
0x140028f69  jz      loc_140028FF8
0x140028f6f  mov     rdx, [rsi+10h]
0x140028f73  mov     ecx, [r14+8]
0x140028f77  call    ORConvertOffsetToAbsolute
0x140028f7c  cmp     rax, r15
0x140028f7f  jnz     short loc_140028FF8
0x140028f81  mov     edx, 10h; Alignment
0x140028f86  lea     ecx, [rdx+18h]; Size
0x140028f89  call    _o__aligned_malloc_0
0x140028f8e  test    rax, rax
0x140028f91  jz      loc_140028EE0
0x140028f97  mov     qword ptr [rax], 0
0x140028f9e  mov     qword ptr [rax+8], 0
0x140028fa6  mov     qword ptr [rax+18h], 0
0x140028fae  mov     qword ptr [rax+20h], 0
0x140028fb6  mov     [rax+10h], r14
0x140028fba  mov     rcx, [rbp+8]
0x140028fbe  cmp     [rcx], rbp
0x140028fc1  jnz     short loc_140028FF1
0x140028fc3  mov     [rax], rbp
0x140028fc6  mov     r15, rbx
0x140028fc9  mov     [rax+8], rcx
0x140028fcd  mov     [rcx], rax
0x140028fd0  mov     [rbp+8], rax
0x140028fd4  mov     ecx, [r14+4]
0x140028fd8  mov     rdx, [rsi+10h]
0x140028fdc  call    ORConvertOffsetToAbsolute
0x140028fe1  mov     rbx, rax
0x140028fe4  cmp     rax, rdi
0x140028fe7  jnz     loc_140028F37
0x140028fed  xor     ebx, ebx
0x140028fef  jmp     short loc_140029005
0x140028ff1  mov     ecx, 3
0x140028ff6  int     29h; Win8: RtlFailFast(ecx)
0x140028ff8  mov     ebx, 3F1h
0x140028ffd  mov     rcx, rsi
0x140029000  call    ORFreeSecurityCellList
0x140029005  mov     eax, ebx
0x140029007  add     rsp, 20h
0x14002900b  pop     r15
0x14002900d  pop     r14
0x14002900f  pop     r13
0x140029011  pop     rdi
0x140029012  pop     rsi
0x140029013  pop     rbp
0x140029014  pop     rbx
0x140029015  retn
```
