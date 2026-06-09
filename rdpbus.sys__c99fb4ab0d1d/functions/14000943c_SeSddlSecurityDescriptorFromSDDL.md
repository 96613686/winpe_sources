# SeSddlSecurityDescriptorFromSDDL

- ea: `0x14000943c`
- end: `0x1400094f8`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400091b0`

## callees

- `0x140002640`
- `0x140002940`
- `0x14000943c`
- `0x140009c14`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400094de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140009481`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140009481`

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
0x14000943c  push    rbx
0x14000943e  push    rbp
0x14000943f  push    rsi
0x140009440  push    rdi
0x140009441  push    r14
0x140009443  sub     rsp, 20h
0x140009447  movzx   edx, word ptr [rcx]
0x14000944a  xor     ebp, ebp
0x14000944c  movzx   eax, word ptr [rcx+2]
0x140009450  mov     rsi, r8
0x140009453  mov     rdi, rcx
0x140009456  lea     r9, [rdx+2]
0x14000945a  cmp     rax, r9
0x14000945d  jnz     short loc_140009473
0x14000945f  mov     rcx, [rcx+8]
0x140009463  shr     rdx, 1
0x140009466  cmp     [rcx+rdx*2], bp
0x14000946a  jnz     short loc_140009473
0x14000946c  call    SepSddlSecurityDescriptorFromSDDLString
0x140009471  jmp     short loc_1400094EC
0x140009473  mov     r8d, 73546553h; Tag
0x140009479  mov     rdx, r9; NumberOfBytes
0x14000947c  mov     ecx, 1; PoolType
0x140009481  call    cs:__imp_ExAllocatePoolWithTag
0x140009488  nop     dword ptr [rax+rax+00h]
0x14000948d  mov     r14, rax
0x140009490  test    rax, rax
0x140009493  jnz     short loc_14000949F
0x140009495  mov     [rsi], rbp
0x140009498  mov     eax, 0C000009Ah
0x14000949d  jmp     short loc_1400094EC
0x14000949f  movzx   r8d, word ptr [rdi]
0x1400094a3  xor     edx, edx; Val
0x1400094a5  add     r8, 2; Size
0x1400094a9  mov     rcx, r14; void *
0x1400094ac  call    memset
0x1400094b1  movzx   r8d, word ptr [rdi]; Size
0x1400094b5  mov     rcx, r14; void *
0x1400094b8  mov     rdx, [rdi+8]; Src
0x1400094bc  call    memmove
0x1400094c1  movzx   ecx, word ptr [rdi]
0x1400094c4  mov     r8, rsi
0x1400094c7  shr     rcx, 1
0x1400094ca  mov     [r14+rcx*2], bp
0x1400094cf  mov     rcx, r14
0x1400094d2  call    SepSddlSecurityDescriptorFromSDDLString
0x1400094d7  xor     edx, edx; Tag
0x1400094d9  mov     rcx, r14; P
0x1400094dc  mov     ebx, eax
0x1400094de  call    cs:__imp_ExFreePoolWithTag
0x1400094e5  nop     dword ptr [rax+rax+00h]
0x1400094ea  mov     eax, ebx
0x1400094ec  add     rsp, 20h
0x1400094f0  pop     r14
0x1400094f2  pop     rdi
0x1400094f3  pop     rsi
0x1400094f4  pop     rbp
0x1400094f5  pop     rbx
0x1400094f6  retn
```
