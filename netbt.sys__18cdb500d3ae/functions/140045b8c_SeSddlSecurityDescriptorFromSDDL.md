# SeSddlSecurityDescriptorFromSDDL

- ea: `0x140045b8c`
- end: `0x140045c48`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140045900`

## callees

- `0x140031140`
- `0x140031440`
- `0x140045b8c`
- `0x140046364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140045c2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045c2e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045bd1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045bd1`

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
0x140045b8c  push    rbx
0x140045b8e  push    rbp
0x140045b8f  push    rsi
0x140045b90  push    rdi
0x140045b91  push    r14
0x140045b93  sub     rsp, 20h
0x140045b97  movzx   edx, word ptr [rcx]
0x140045b9a  xor     ebp, ebp
0x140045b9c  movzx   eax, word ptr [rcx+2]
0x140045ba0  mov     rsi, r8
0x140045ba3  mov     rdi, rcx
0x140045ba6  lea     r9, [rdx+2]
0x140045baa  cmp     rax, r9
0x140045bad  jnz     short loc_140045BC3
0x140045baf  mov     rcx, [rcx+8]
0x140045bb3  shr     rdx, 1
0x140045bb6  cmp     [rcx+rdx*2], bp
0x140045bba  jnz     short loc_140045BC3
0x140045bbc  call    SepSddlSecurityDescriptorFromSDDLString
0x140045bc1  jmp     short loc_140045C3C
0x140045bc3  mov     r8d, 73546553h; Tag
0x140045bc9  mov     rdx, r9; NumberOfBytes
0x140045bcc  mov     ecx, 1; PoolType
0x140045bd1  call    cs:__imp_ExAllocatePoolWithTag
0x140045bd8  nop     dword ptr [rax+rax+00h]
0x140045bdd  mov     r14, rax
0x140045be0  test    rax, rax
0x140045be3  jnz     short loc_140045BEF
0x140045be5  mov     [rsi], rbp
0x140045be8  mov     eax, 0C000009Ah
0x140045bed  jmp     short loc_140045C3C
0x140045bef  movzx   r8d, word ptr [rdi]
0x140045bf3  xor     edx, edx; Val
0x140045bf5  add     r8, 2; Size
0x140045bf9  mov     rcx, r14; void *
0x140045bfc  call    memset
0x140045c01  movzx   r8d, word ptr [rdi]; Size
0x140045c05  mov     rcx, r14; void *
0x140045c08  mov     rdx, [rdi+8]; Src
0x140045c0c  call    memmove
0x140045c11  movzx   ecx, word ptr [rdi]
0x140045c14  mov     r8, rsi
0x140045c17  shr     rcx, 1
0x140045c1a  mov     [r14+rcx*2], bp
0x140045c1f  mov     rcx, r14
0x140045c22  call    SepSddlSecurityDescriptorFromSDDLString
0x140045c27  xor     edx, edx; Tag
0x140045c29  mov     rcx, r14; P
0x140045c2c  mov     ebx, eax
0x140045c2e  call    cs:__imp_ExFreePoolWithTag
0x140045c35  nop     dword ptr [rax+rax+00h]
0x140045c3a  mov     eax, ebx
0x140045c3c  add     rsp, 20h
0x140045c40  pop     r14
0x140045c42  pop     rdi
0x140045c43  pop     rsi
0x140045c44  pop     rbp
0x140045c45  pop     rbx
0x140045c46  retn
```
