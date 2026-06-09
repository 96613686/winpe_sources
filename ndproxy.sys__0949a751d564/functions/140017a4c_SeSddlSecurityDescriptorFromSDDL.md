# SeSddlSecurityDescriptorFromSDDL

- ea: `0x140017a4c`
- end: `0x140017b08`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400177c0`

## callees

- `0x1400081c0`
- `0x1400084c0`
- `0x140017a4c`
- `0x140018214`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140017aee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017aee`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017a91`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017a91`

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
0x140017a4c  push    rbx
0x140017a4e  push    rbp
0x140017a4f  push    rsi
0x140017a50  push    rdi
0x140017a51  push    r14
0x140017a53  sub     rsp, 20h
0x140017a57  movzx   edx, word ptr [rcx]
0x140017a5a  xor     ebp, ebp
0x140017a5c  movzx   eax, word ptr [rcx+2]
0x140017a60  mov     rsi, r8
0x140017a63  mov     rdi, rcx
0x140017a66  lea     r9, [rdx+2]
0x140017a6a  cmp     rax, r9
0x140017a6d  jnz     short loc_140017A83
0x140017a6f  mov     rcx, [rcx+8]
0x140017a73  shr     rdx, 1
0x140017a76  cmp     [rcx+rdx*2], bp
0x140017a7a  jnz     short loc_140017A83
0x140017a7c  call    SepSddlSecurityDescriptorFromSDDLString
0x140017a81  jmp     short loc_140017AFC
0x140017a83  mov     r8d, 73546553h; Tag
0x140017a89  mov     rdx, r9; NumberOfBytes
0x140017a8c  mov     ecx, 1; PoolType
0x140017a91  call    cs:__imp_ExAllocatePoolWithTag
0x140017a98  nop     dword ptr [rax+rax+00h]
0x140017a9d  mov     r14, rax
0x140017aa0  test    rax, rax
0x140017aa3  jnz     short loc_140017AAF
0x140017aa5  mov     [rsi], rbp
0x140017aa8  mov     eax, 0C000009Ah
0x140017aad  jmp     short loc_140017AFC
0x140017aaf  movzx   r8d, word ptr [rdi]
0x140017ab3  xor     edx, edx; Val
0x140017ab5  add     r8, 2; Size
0x140017ab9  mov     rcx, r14; void *
0x140017abc  call    memset
0x140017ac1  movzx   r8d, word ptr [rdi]; Size
0x140017ac5  mov     rcx, r14; void *
0x140017ac8  mov     rdx, [rdi+8]; Src
0x140017acc  call    memmove
0x140017ad1  movzx   ecx, word ptr [rdi]
0x140017ad4  mov     r8, rsi
0x140017ad7  shr     rcx, 1
0x140017ada  mov     [r14+rcx*2], bp
0x140017adf  mov     rcx, r14
0x140017ae2  call    SepSddlSecurityDescriptorFromSDDLString
0x140017ae7  xor     edx, edx; Tag
0x140017ae9  mov     rcx, r14; P
0x140017aec  mov     ebx, eax
0x140017aee  call    cs:__imp_ExFreePoolWithTag
0x140017af5  nop     dword ptr [rax+rax+00h]
0x140017afa  mov     eax, ebx
0x140017afc  add     rsp, 20h
0x140017b00  pop     r14
0x140017b02  pop     rdi
0x140017b03  pop     rsi
0x140017b04  pop     rbp
0x140017b05  pop     rbx
0x140017b06  retn
```
