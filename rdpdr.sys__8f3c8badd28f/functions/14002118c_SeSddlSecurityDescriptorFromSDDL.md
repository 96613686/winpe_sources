# SeSddlSecurityDescriptorFromSDDL

- ea: `0x14002118c`
- end: `0x140021248`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020f00`

## callees

- `0x1400065c0`
- `0x1400068c0`
- `0x14002118c`
- `0x14002194c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002122e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002122e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400211d1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400211d1`

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
0x14002118c  push    rbx
0x14002118e  push    rbp
0x14002118f  push    rsi
0x140021190  push    rdi
0x140021191  push    r14
0x140021193  sub     rsp, 20h
0x140021197  movzx   edx, word ptr [rcx]
0x14002119a  xor     ebp, ebp
0x14002119c  movzx   eax, word ptr [rcx+2]
0x1400211a0  mov     rsi, r8
0x1400211a3  mov     rdi, rcx
0x1400211a6  lea     r9, [rdx+2]
0x1400211aa  cmp     rax, r9
0x1400211ad  jnz     short loc_1400211C3
0x1400211af  mov     rcx, [rcx+8]
0x1400211b3  shr     rdx, 1
0x1400211b6  cmp     [rcx+rdx*2], bp
0x1400211ba  jnz     short loc_1400211C3
0x1400211bc  call    SepSddlSecurityDescriptorFromSDDLString
0x1400211c1  jmp     short loc_14002123C
0x1400211c3  mov     r8d, 73546553h; Tag
0x1400211c9  mov     rdx, r9; NumberOfBytes
0x1400211cc  mov     ecx, 1; PoolType
0x1400211d1  call    cs:__imp_ExAllocatePoolWithTag
0x1400211d8  nop     dword ptr [rax+rax+00h]
0x1400211dd  mov     r14, rax
0x1400211e0  test    rax, rax
0x1400211e3  jnz     short loc_1400211EF
0x1400211e5  mov     [rsi], rbp
0x1400211e8  mov     eax, 0C000009Ah
0x1400211ed  jmp     short loc_14002123C
0x1400211ef  movzx   r8d, word ptr [rdi]
0x1400211f3  xor     edx, edx; Val
0x1400211f5  add     r8, 2; Size
0x1400211f9  mov     rcx, r14; void *
0x1400211fc  call    memset
0x140021201  movzx   r8d, word ptr [rdi]; Size
0x140021205  mov     rcx, r14; void *
0x140021208  mov     rdx, [rdi+8]; Src
0x14002120c  call    memmove
0x140021211  movzx   ecx, word ptr [rdi]
0x140021214  mov     r8, rsi
0x140021217  shr     rcx, 1
0x14002121a  mov     [r14+rcx*2], bp
0x14002121f  mov     rcx, r14
0x140021222  call    SepSddlSecurityDescriptorFromSDDLString
0x140021227  xor     edx, edx; Tag
0x140021229  mov     rcx, r14; P
0x14002122c  mov     ebx, eax
0x14002122e  call    cs:__imp_ExFreePoolWithTag
0x140021235  nop     dword ptr [rax+rax+00h]
0x14002123a  mov     eax, ebx
0x14002123c  add     rsp, 20h
0x140021240  pop     r14
0x140021242  pop     rdi
0x140021243  pop     rsi
0x140021244  pop     rbp
0x140021245  pop     rbx
0x140021246  retn
```
