# DfscCreateNameFromUnicodeString

- ea: `0x140022620`
- end: `0x140022709`
- name: `DfscCreateNameFromUnicodeString`
- size: `233`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400120f4`
- `0x140021c60`
- `0x140021e28`
- `0x1400221cc`
- `0x140022b60`
- `0x140024ff0`

## callees

- `0x140006080`
- `0x140022620`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400226f1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400226f1`
- `ntoskrnl!ExAllocatePool2` at `0x14002268a`
- `ntoskrnl!ExAllocatePool2` at `0x14002268a`

## pseudocode

```c
__int64 __fastcall DfscCreateNameFromUnicodeString(struct _UNICODE_STRING *a1, unsigned __int16 *a2, __int64 a3)
{
  size_t v3; // rbx
  unsigned __int16 v6; // di
  unsigned __int64 v7; // r14
  WCHAR *Pool2; // rax
  WCHAR *v9; // rbp
  __int64 result; // rax
  struct _UNICODE_STRING v11; // [rsp+20h] [rbp-28h]

  v3 = *a2;
  *(_DWORD *)(&v11.MaximumLength + 1) = 0;
  if ( (_WORD)v3 )
  {
    v6 = *a2;
    v11.MaximumLength = *a2;
    v11.Length = *a2;
    v7 = (unsigned __int64)*a2 >> 1;
    if ( *(_WORD *)(*((_QWORD *)a2 + 1) + v7 * 2 - 2) )
    {
      v6 = v3 + 2;
      v11.MaximumLength = v3 + 2;
      if ( (unsigned __int16)(v3 + 2) < (unsigned __int16)v3 )
        return 3221225626LL;
    }
    Pool2 = (WCHAR *)ExAllocatePool2(258, v6, a3);
    v11.Buffer = Pool2;
    v9 = Pool2;
    if ( !Pool2 )
    {
      return 3221225626LL;
    }
    else
    {
      memmove(Pool2, *((const void **)a2 + 1), v3);
      if ( (unsigned __int16)v3 < v6 )
        v9[v7] = 0;
      result = 0;
      *a1 = v11;
    }
  }
  else
  {
    RtlInitUnicodeString(a1, 0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140022620  mov     rax, rsp
0x140022623  push    rbx
0x140022624  push    rsi
0x140022625  push    r12
0x140022627  sub     rsp, 30h
0x14002262b  movzx   ebx, word ptr [rdx]
0x14002262e  xorps   xmm0, xmm0
0x140022631  mov     rsi, rdx
0x140022634  mov     r12, rcx
0x140022637  movups  xmmword ptr [rax-28h], xmm0
0x14002263b  test    bx, bx
0x14002263e  jz      loc_1400226EF
0x140022644  mov     [rax+8], rbp
0x140022648  mov     [rax+10h], rdi
0x14002264c  movzx   edi, bx
0x14002264f  mov     [rax+18h], r14
0x140022653  mov     [rax+20h], r15
0x140022657  mov     [rax-26h], bx
0x14002265b  mov     [rax-28h], bx
0x14002265f  mov     eax, ebx
0x140022661  shr     rax, 1
0x140022664  lea     r14, [rax+rax]
0x140022668  mov     rax, [rdx+8]
0x14002266c  cmp     word ptr [rax+r14-2], 0
0x140022673  jz      short loc_140022682
0x140022675  lea     edi, [rbx+2]
0x140022678  mov     [rsp+48h+var_26], di
0x14002267d  cmp     di, bx
0x140022680  jb      short loc_1400226E8
0x140022682  movzx   edx, di
0x140022685  mov     ecx, 102h
0x14002268a  call    cs:__imp_ExAllocatePool2
0x140022691  nop     dword ptr [rax+rax+00h]
0x140022696  mov     [rsp+48h+var_20], rax
0x14002269b  mov     rbp, rax
0x14002269e  test    rax, rax
0x1400226a1  jz      short loc_1400226E8
0x1400226a3  mov     rdx, [rsi+8]; Src
0x1400226a7  mov     r8, rbx; Size
0x1400226aa  mov     rcx, rax; void *
0x1400226ad  call    memmove
0x1400226b2  cmp     bx, di
0x1400226b5  jnb     short loc_1400226BE
0x1400226b7  xor     eax, eax
0x1400226b9  mov     [r14+rbp], ax
0x1400226be  movups  xmm0, xmmword ptr [rsp+20h]
0x1400226c3  xor     eax, eax
0x1400226c5  movups  xmmword ptr [r12], xmm0
0x1400226ca  mov     r14, [rsp+48h+arg_10]
0x1400226cf  mov     rdi, [rsp+48h+arg_8]
0x1400226d4  mov     rbp, [rsp+48h+arg_0]
0x1400226d9  mov     r15, [rsp+48h+arg_18]
0x1400226de  add     rsp, 30h
0x1400226e2  pop     r12
0x1400226e4  pop     rsi
0x1400226e5  pop     rbx
0x1400226e6  retn
0x1400226e8  mov     eax, 0C000009Ah
0x1400226ed  jmp     short loc_1400226CA
0x1400226ef  xor     edx, edx; SourceString
0x1400226f1  call    cs:__imp_RtlInitUnicodeString
0x1400226f8  nop     dword ptr [rax+rax+00h]
0x1400226fd  xor     eax, eax
0x1400226ff  add     rsp, 30h
0x140022703  pop     r12
0x140022705  pop     rsi
0x140022706  pop     rbx
0x140022707  retn
```
