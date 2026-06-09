# SeSddlSecurityDescriptorFromSDDL

- ea: `0x140042f4c`
- end: `0x140043008`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140042cc0`

## callees

- `0x14002c8c0`
- `0x14002cbc0`
- `0x140042f4c`
- `0x140043734`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140042f91`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140042f91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042fee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042fee`

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
0x140042f4c  push    rbx
0x140042f4e  push    rbp
0x140042f4f  push    rsi
0x140042f50  push    rdi
0x140042f51  push    r14
0x140042f53  sub     rsp, 20h
0x140042f57  movzx   edx, word ptr [rcx]
0x140042f5a  xor     ebp, ebp
0x140042f5c  movzx   eax, word ptr [rcx+2]
0x140042f60  mov     rsi, r8
0x140042f63  mov     rdi, rcx
0x140042f66  lea     r9, [rdx+2]
0x140042f6a  cmp     rax, r9
0x140042f6d  jnz     short loc_140042F83
0x140042f6f  mov     rcx, [rcx+8]
0x140042f73  shr     rdx, 1
0x140042f76  cmp     [rcx+rdx*2], bp
0x140042f7a  jnz     short loc_140042F83
0x140042f7c  call    SepSddlSecurityDescriptorFromSDDLString
0x140042f81  jmp     short loc_140042FFC
0x140042f83  mov     r8d, 73546553h; Tag
0x140042f89  mov     rdx, r9; NumberOfBytes
0x140042f8c  mov     ecx, 1; PoolType
0x140042f91  call    cs:__imp_ExAllocatePoolWithTag
0x140042f98  nop     dword ptr [rax+rax+00h]
0x140042f9d  mov     r14, rax
0x140042fa0  test    rax, rax
0x140042fa3  jnz     short loc_140042FAF
0x140042fa5  mov     [rsi], rbp
0x140042fa8  mov     eax, 0C000009Ah
0x140042fad  jmp     short loc_140042FFC
0x140042faf  movzx   r8d, word ptr [rdi]
0x140042fb3  xor     edx, edx; Val
0x140042fb5  add     r8, 2; Size
0x140042fb9  mov     rcx, r14; void *
0x140042fbc  call    memset
0x140042fc1  movzx   r8d, word ptr [rdi]; Size
0x140042fc5  mov     rcx, r14; void *
0x140042fc8  mov     rdx, [rdi+8]; Src
0x140042fcc  call    memmove
0x140042fd1  movzx   ecx, word ptr [rdi]
0x140042fd4  mov     r8, rsi
0x140042fd7  shr     rcx, 1
0x140042fda  mov     [r14+rcx*2], bp
0x140042fdf  mov     rcx, r14
0x140042fe2  call    SepSddlSecurityDescriptorFromSDDLString
0x140042fe7  xor     edx, edx; Tag
0x140042fe9  mov     rcx, r14; P
0x140042fec  mov     ebx, eax
0x140042fee  call    cs:__imp_ExFreePoolWithTag
0x140042ff5  nop     dword ptr [rax+rax+00h]
0x140042ffa  mov     eax, ebx
0x140042ffc  add     rsp, 20h
0x140043000  pop     r14
0x140043002  pop     rdi
0x140043003  pop     rsi
0x140043004  pop     rbp
0x140043005  pop     rbx
0x140043006  retn
```
