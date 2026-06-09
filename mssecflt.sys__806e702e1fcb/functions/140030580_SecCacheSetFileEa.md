# SecCacheSetFileEa

- ea: `0x140030580`
- end: `0x140030665`
- name: `SecCacheSetFileEa`
- size: `229`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140023224`
- `0x140030550`
- `0x140030900`
- `0x1400309d8`

## callees

- `0x140009b80`
- `0x140011610`
- `0x140011700`
- `0x1400119c0`
- `0x140030580`
- `0x1400308a0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400305d3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400305d3`

## pseudocode

```c
__int64 __fastcall SecCacheSetFileEa(__int64 a1, const void **a2, const void *a3, unsigned int a4, char a5)
{
  SIZE_T v6; // rbx
  size_t v7; // rbp
  char *PoolWithTag; // rax
  char *v11; // rdi
  __int64 v13; // rbx
  __int64 v14; // r8

  v6 = a4 + *(unsigned __int16 *)a2 + 9;
  v7 = a4;
  if ( qword_140020008 )
    PoolWithTag = (char *)qword_140020008(256, v6, 1366123859);
  else
    PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v6, 0x516D6553u);
  v11 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, v6);
  v13 = *(unsigned __int16 *)a2;
  v11[5] = *(_BYTE *)a2;
  *((_WORD *)v11 + 3) = v7;
  memmove(v11 + 8, a2[1], *(unsigned __int16 *)a2);
  memmove(&v11[v13 + 9], a3, v7);
  LOBYTE(v14) = a5;
  LODWORD(v13) = SecCacheSetFileKernelEa(a1, v11, v14);
  SecFreePool(v11, 0x516D6553u);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140030580  mov     [rsp+arg_0], rbx
0x140030585  mov     [rsp+arg_8], rbp
0x14003058a  mov     [rsp+arg_10], rsi
0x14003058f  push    rdi
0x140030590  push    r14
0x140030592  push    r15
0x140030594  sub     rsp, 20h
0x140030598  movzx   ebx, word ptr [rdx]
0x14003059b  mov     r14, r8
0x14003059e  mov     rax, cs:qword_140020008
0x1400305a5  add     ebx, 9
0x1400305a8  add     ebx, r9d
0x1400305ab  mov     ebp, r9d
0x1400305ae  mov     rsi, rdx
0x1400305b1  mov     r15, rcx
0x1400305b4  mov     r8d, 516D6553h; Tag
0x1400305ba  mov     edx, ebx; NumberOfBytes
0x1400305bc  test    rax, rax
0x1400305bf  jz      short loc_1400305CE
0x1400305c1  mov     ecx, 100h
0x1400305c6  call    cs:__guard_dispatch_icall_fptr
0x1400305cc  jmp     short loc_1400305DF
0x1400305ce  mov     ecx, 1; PoolType
0x1400305d3  call    cs:__imp_ExAllocatePoolWithTag
0x1400305da  nop     dword ptr [rax+rax+00h]
0x1400305df  mov     rdi, rax
0x1400305e2  test    rax, rax
0x1400305e5  jnz     short loc_1400305EE
0x1400305e7  mov     eax, 0C000009Ah
0x1400305ec  jmp     short loc_14003064B
0x1400305ee  mov     r8, rbx; Size
0x1400305f1  xor     edx, edx; Val
0x1400305f3  mov     rcx, rdi; void *
0x1400305f6  call    memset
0x1400305fb  mov     al, [rsi]
0x1400305fd  lea     rcx, [rdi+8]; void *
0x140030601  movzx   ebx, word ptr [rsi]
0x140030604  mov     [rdi+5], al
0x140030607  mov     [rdi+6], bp
0x14003060b  movzx   r8d, word ptr [rsi]; Size
0x14003060f  mov     rdx, [rsi+8]; Src
0x140030613  call    memmove
0x140030618  lea     rcx, [rbx+9]
0x14003061c  mov     r8, rbp; Size
0x14003061f  add     rcx, rdi; void *
0x140030622  mov     rdx, r14; Src
0x140030625  call    memmove
0x14003062a  mov     r8b, [rsp+38h+arg_20]
0x14003062f  mov     rdx, rdi
0x140030632  mov     rcx, r15
0x140030635  call    SecCacheSetFileKernelEa
0x14003063a  mov     edx, 516D6553h; Tag
0x14003063f  mov     rcx, rdi; P
0x140030642  mov     ebx, eax
0x140030644  call    SecFreePool
0x140030649  mov     eax, ebx
0x14003064b  mov     rbx, [rsp+38h+arg_0]
0x140030650  mov     rbp, [rsp+38h+arg_8]
0x140030655  mov     rsi, [rsp+38h+arg_10]
0x14003065a  add     rsp, 20h
0x14003065e  pop     r15
0x140030660  pop     r14
0x140030662  pop     rdi
0x140030663  retn
```
