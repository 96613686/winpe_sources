# SeSddlSecurityDescriptorFromSDDL

- ea: `0x14000d4cc`
- end: `0x14000d588`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d240`

## callees

- `0x140006680`
- `0x140006980`
- `0x14000d4cc`
- `0x14000dca4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d56e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d56e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d511`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d511`

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
0x14000d4cc  push    rbx
0x14000d4ce  push    rbp
0x14000d4cf  push    rsi
0x14000d4d0  push    rdi
0x14000d4d1  push    r14
0x14000d4d3  sub     rsp, 20h
0x14000d4d7  movzx   edx, word ptr [rcx]
0x14000d4da  xor     ebp, ebp
0x14000d4dc  movzx   eax, word ptr [rcx+2]
0x14000d4e0  mov     rsi, r8
0x14000d4e3  mov     rdi, rcx
0x14000d4e6  lea     r9, [rdx+2]
0x14000d4ea  cmp     rax, r9
0x14000d4ed  jnz     short loc_14000D503
0x14000d4ef  mov     rcx, [rcx+8]
0x14000d4f3  shr     rdx, 1
0x14000d4f6  cmp     [rcx+rdx*2], bp
0x14000d4fa  jnz     short loc_14000D503
0x14000d4fc  call    SepSddlSecurityDescriptorFromSDDLString
0x14000d501  jmp     short loc_14000D57C
0x14000d503  mov     r8d, 73546553h; Tag
0x14000d509  mov     rdx, r9; NumberOfBytes
0x14000d50c  mov     ecx, 1; PoolType
0x14000d511  call    cs:__imp_ExAllocatePoolWithTag
0x14000d518  nop     dword ptr [rax+rax+00h]
0x14000d51d  mov     r14, rax
0x14000d520  test    rax, rax
0x14000d523  jnz     short loc_14000D52F
0x14000d525  mov     [rsi], rbp
0x14000d528  mov     eax, 0C000009Ah
0x14000d52d  jmp     short loc_14000D57C
0x14000d52f  movzx   r8d, word ptr [rdi]
0x14000d533  xor     edx, edx; Val
0x14000d535  add     r8, 2; Size
0x14000d539  mov     rcx, r14; void *
0x14000d53c  call    memset
0x14000d541  movzx   r8d, word ptr [rdi]; Size
0x14000d545  mov     rcx, r14; void *
0x14000d548  mov     rdx, [rdi+8]; Src
0x14000d54c  call    memmove
0x14000d551  movzx   ecx, word ptr [rdi]
0x14000d554  mov     r8, rsi
0x14000d557  shr     rcx, 1
0x14000d55a  mov     [r14+rcx*2], bp
0x14000d55f  mov     rcx, r14
0x14000d562  call    SepSddlSecurityDescriptorFromSDDLString
0x14000d567  xor     edx, edx; Tag
0x14000d569  mov     rcx, r14; P
0x14000d56c  mov     ebx, eax
0x14000d56e  call    cs:__imp_ExFreePoolWithTag
0x14000d575  nop     dword ptr [rax+rax+00h]
0x14000d57a  mov     eax, ebx
0x14000d57c  add     rsp, 20h
0x14000d580  pop     r14
0x14000d582  pop     rdi
0x14000d583  pop     rsi
0x14000d584  pop     rbp
0x14000d585  pop     rbx
0x14000d586  retn
```
