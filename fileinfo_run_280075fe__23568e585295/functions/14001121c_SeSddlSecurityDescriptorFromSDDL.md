# SeSddlSecurityDescriptorFromSDDL

- ea: `0x14001121c`
- end: `0x1400112d8`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010f90`

## callees

- `0x140003a80`
- `0x140003d80`
- `0x14001121c`
- `0x1400119f4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140011261`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140011261`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400112be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400112be`

## pseudocode

```c
__int64 __fastcall SeSddlSecurityDescriptorFromSDDL(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  unsigned __int64 v3; // rdx
  SIZE_T v6; // r9
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  PVOID PoolWithTag; // rax
  void *v11; // r14
  ULONG v12; // edx
  unsigned int v13; // ebx

  v3 = *a1;
  v6 = v3 + 2;
  if ( a1[1] == v3 + 2 )
  {
    v7 = *((_QWORD *)a1 + 1);
    v8 = v3 >> 1;
    if ( !*(_WORD *)(v7 + 2 * v8) )
      return SepSddlSecurityDescriptorFromSDDLString(v7, v8, (__int64)a3);
  }
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, v6, 0x73546553u);
  v11 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, *a1 + 2LL);
    memmove(v11, *((const void **)a1 + 1), *a1);
    *((_WORD *)v11 + ((unsigned __int64)*a1 >> 1)) = 0;
    v13 = SepSddlSecurityDescriptorFromSDDLString((__int64)v11, v12, (__int64)a3);
    ExFreePoolWithTag(v11, 0);
    return v13;
  }
  else
  {
    *a3 = 0;
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14001121c  push    rbx
0x14001121e  push    rbp
0x14001121f  push    rsi
0x140011220  push    rdi
0x140011221  push    r14
0x140011223  sub     rsp, 20h
0x140011227  movzx   edx, word ptr [rcx]
0x14001122a  xor     ebp, ebp
0x14001122c  movzx   eax, word ptr [rcx+2]
0x140011230  mov     rsi, r8
0x140011233  mov     rdi, rcx
0x140011236  lea     r9, [rdx+2]
0x14001123a  cmp     rax, r9
0x14001123d  jnz     short loc_140011253
0x14001123f  mov     rcx, [rcx+8]
0x140011243  shr     rdx, 1
0x140011246  cmp     [rcx+rdx*2], bp
0x14001124a  jnz     short loc_140011253
0x14001124c  call    SepSddlSecurityDescriptorFromSDDLString
0x140011251  jmp     short loc_1400112CC
0x140011253  mov     r8d, 73546553h; Tag
0x140011259  mov     rdx, r9; NumberOfBytes
0x14001125c  mov     ecx, 1; PoolType
0x140011261  call    cs:__imp_ExAllocatePoolWithTag
0x140011268  nop     dword ptr [rax+rax+00h]
0x14001126d  mov     r14, rax
0x140011270  test    rax, rax
0x140011273  jnz     short loc_14001127F
0x140011275  mov     [rsi], rbp
0x140011278  mov     eax, 0C000009Ah
0x14001127d  jmp     short loc_1400112CC
0x14001127f  movzx   r8d, word ptr [rdi]
0x140011283  xor     edx, edx; Val
0x140011285  add     r8, 2; Size
0x140011289  mov     rcx, r14; void *
0x14001128c  call    memset
0x140011291  movzx   r8d, word ptr [rdi]; Size
0x140011295  mov     rcx, r14; void *
0x140011298  mov     rdx, [rdi+8]; Src
0x14001129c  call    memmove
0x1400112a1  movzx   ecx, word ptr [rdi]
0x1400112a4  mov     r8, rsi
0x1400112a7  shr     rcx, 1
0x1400112aa  mov     [r14+rcx*2], bp
0x1400112af  mov     rcx, r14
0x1400112b2  call    SepSddlSecurityDescriptorFromSDDLString
0x1400112b7  xor     edx, edx; Tag
0x1400112b9  mov     rcx, r14; P
0x1400112bc  mov     ebx, eax
0x1400112be  call    cs:__imp_ExFreePoolWithTag
0x1400112c5  nop     dword ptr [rax+rax+00h]
0x1400112ca  mov     eax, ebx
0x1400112cc  add     rsp, 20h
0x1400112d0  pop     r14
0x1400112d2  pop     rdi
0x1400112d3  pop     rsi
0x1400112d4  pop     rbp
0x1400112d5  pop     rbx
0x1400112d6  retn
```
