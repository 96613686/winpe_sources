# SeSddlSecurityDescriptorFromSDDL

- ea: `0x1400438cc`
- end: `0x140043988`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140043640`

## callees

- `0x140037340`
- `0x140037640`
- `0x1400438cc`
- `0x1400440a4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043911`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043911`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004396e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004396e`

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
0x1400438cc  push    rbx
0x1400438ce  push    rbp
0x1400438cf  push    rsi
0x1400438d0  push    rdi
0x1400438d1  push    r14
0x1400438d3  sub     rsp, 20h
0x1400438d7  movzx   edx, word ptr [rcx]
0x1400438da  xor     ebp, ebp
0x1400438dc  movzx   eax, word ptr [rcx+2]
0x1400438e0  mov     rsi, r8
0x1400438e3  mov     rdi, rcx
0x1400438e6  lea     r9, [rdx+2]
0x1400438ea  cmp     rax, r9
0x1400438ed  jnz     short loc_140043903
0x1400438ef  mov     rcx, [rcx+8]
0x1400438f3  shr     rdx, 1
0x1400438f6  cmp     [rcx+rdx*2], bp
0x1400438fa  jnz     short loc_140043903
0x1400438fc  call    SepSddlSecurityDescriptorFromSDDLString
0x140043901  jmp     short loc_14004397C
0x140043903  mov     r8d, 73546553h; Tag
0x140043909  mov     rdx, r9; NumberOfBytes
0x14004390c  mov     ecx, 1; PoolType
0x140043911  call    cs:__imp_ExAllocatePoolWithTag
0x140043918  nop     dword ptr [rax+rax+00h]
0x14004391d  mov     r14, rax
0x140043920  test    rax, rax
0x140043923  jnz     short loc_14004392F
0x140043925  mov     [rsi], rbp
0x140043928  mov     eax, 0C000009Ah
0x14004392d  jmp     short loc_14004397C
0x14004392f  movzx   r8d, word ptr [rdi]
0x140043933  xor     edx, edx; Val
0x140043935  add     r8, 2; Size
0x140043939  mov     rcx, r14; void *
0x14004393c  call    memset
0x140043941  movzx   r8d, word ptr [rdi]; Size
0x140043945  mov     rcx, r14; void *
0x140043948  mov     rdx, [rdi+8]; Src
0x14004394c  call    memmove
0x140043951  movzx   ecx, word ptr [rdi]
0x140043954  mov     r8, rsi
0x140043957  shr     rcx, 1
0x14004395a  mov     [r14+rcx*2], bp
0x14004395f  mov     rcx, r14
0x140043962  call    SepSddlSecurityDescriptorFromSDDLString
0x140043967  xor     edx, edx; Tag
0x140043969  mov     rcx, r14; P
0x14004396c  mov     ebx, eax
0x14004396e  call    cs:__imp_ExFreePoolWithTag
0x140043975  nop     dword ptr [rax+rax+00h]
0x14004397a  mov     eax, ebx
0x14004397c  add     rsp, 20h
0x140043980  pop     r14
0x140043982  pop     rdi
0x140043983  pop     rsi
0x140043984  pop     rbp
0x140043985  pop     rbx
0x140043986  retn
```
