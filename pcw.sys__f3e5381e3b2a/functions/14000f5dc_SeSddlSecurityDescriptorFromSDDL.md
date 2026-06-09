# SeSddlSecurityDescriptorFromSDDL

- ea: `0x14000f5dc`
- end: `0x14000f698`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f350`

## callees

- `0x1400014c0`
- `0x1400017c0`
- `0x14000f5dc`
- `0x14000fdc4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f67e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f67e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f621`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f621`

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
0x14000f5dc  push    rbx
0x14000f5de  push    rbp
0x14000f5df  push    rsi
0x14000f5e0  push    rdi
0x14000f5e1  push    r14
0x14000f5e3  sub     rsp, 20h
0x14000f5e7  movzx   edx, word ptr [rcx]
0x14000f5ea  xor     ebp, ebp
0x14000f5ec  movzx   eax, word ptr [rcx+2]
0x14000f5f0  mov     rsi, r8
0x14000f5f3  mov     rdi, rcx
0x14000f5f6  lea     r9, [rdx+2]
0x14000f5fa  cmp     rax, r9
0x14000f5fd  jnz     short loc_14000F613
0x14000f5ff  mov     rcx, [rcx+8]
0x14000f603  shr     rdx, 1
0x14000f606  cmp     [rcx+rdx*2], bp
0x14000f60a  jnz     short loc_14000F613
0x14000f60c  call    SepSddlSecurityDescriptorFromSDDLString
0x14000f611  jmp     short loc_14000F68C
0x14000f613  mov     r8d, 73546553h; Tag
0x14000f619  mov     rdx, r9; NumberOfBytes
0x14000f61c  mov     ecx, 1; PoolType
0x14000f621  call    cs:__imp_ExAllocatePoolWithTag
0x14000f628  nop     dword ptr [rax+rax+00h]
0x14000f62d  mov     r14, rax
0x14000f630  test    rax, rax
0x14000f633  jnz     short loc_14000F63F
0x14000f635  mov     [rsi], rbp
0x14000f638  mov     eax, 0C000009Ah
0x14000f63d  jmp     short loc_14000F68C
0x14000f63f  movzx   r8d, word ptr [rdi]
0x14000f643  xor     edx, edx; Val
0x14000f645  add     r8, 2; Size
0x14000f649  mov     rcx, r14; void *
0x14000f64c  call    memset
0x14000f651  movzx   r8d, word ptr [rdi]; Size
0x14000f655  mov     rcx, r14; void *
0x14000f658  mov     rdx, [rdi+8]; Src
0x14000f65c  call    memmove
0x14000f661  movzx   ecx, word ptr [rdi]
0x14000f664  mov     r8, rsi
0x14000f667  shr     rcx, 1
0x14000f66a  mov     [r14+rcx*2], bp
0x14000f66f  mov     rcx, r14
0x14000f672  call    SepSddlSecurityDescriptorFromSDDLString
0x14000f677  xor     edx, edx; Tag
0x14000f679  mov     rcx, r14; P
0x14000f67c  mov     ebx, eax
0x14000f67e  call    cs:__imp_ExFreePoolWithTag
0x14000f685  nop     dword ptr [rax+rax+00h]
0x14000f68a  mov     eax, ebx
0x14000f68c  add     rsp, 20h
0x14000f690  pop     r14
0x14000f692  pop     rdi
0x14000f693  pop     rsi
0x14000f694  pop     rbp
0x14000f695  pop     rbx
0x14000f696  retn
```
