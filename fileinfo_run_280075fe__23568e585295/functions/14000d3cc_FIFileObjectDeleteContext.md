# FIFileObjectDeleteContext

- ea: `0x14000d3cc`
- end: `0x14000d4fe`
- name: `FIFileObjectDeleteContext`
- size: `306`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012850`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x14000d3cc`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14000d4c5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000d4c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d4e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d4e6`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14000d4d5`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14000d4d5`

## pseudocode

```c
void __fastcall FIFileObjectDeleteContext(struct _EX_RUNDOWN_REF *P)
{
  struct _EX_RUNDOWN_REF *i; // r8
  __int64 v3; // [rsp+30h] [rbp+8h]

  FILockExclusiveAcquire(&qword_140009648);
  v3 = P[1].Count & (-1LL << (qword_140009654 & 0x1F));
  for ( i = (struct _EX_RUNDOWN_REF *)(*(__int64 *)((char *)&qword_140009654 + 4)
                                     + 8LL
                                     * ((((unsigned int)qword_140009654 >> 5) - 1)
                                      & (HIBYTE(v3)
                                       + 37
                                       * (BYTE6(v3)
                                        + 37
                                        * (BYTE5(v3)
                                         + 37
                                         * (BYTE4(v3)
                                          + 37
                                          * (BYTE3(v3)
                                           + 37 * (BYTE2(v3) + 37 * (BYTE1(v3) + 37 * ((unsigned __int8)v3 + 11623883))))))))));
        (i->Count & 1) == 0;
        i = (struct _EX_RUNDOWN_REF *)i->Count )
  {
    if ( (struct _EX_RUNDOWN_REF *)i->Count == P )
    {
      i->Count = P->Count;
      --dword_140009650;
      P->Count |= 0x8000000000000002uLL;
      break;
    }
  }
  FILockExclusiveRelease(&qword_140009648);
  ExReleaseRundownProtection(P + 2);
  ExWaitForRundownProtectionRelease(P + 2);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000d3cc  mov     [rsp+arg_8], rbx
0x14000d3d1  push    rdi
0x14000d3d2  sub     rsp, 20h
0x14000d3d6  mov     rdi, rcx
0x14000d3d9  lea     rcx, qword_140009648
0x14000d3e0  call    FILockExclusiveAcquire
0x14000d3e5  mov     r8d, dword ptr cs:qword_140009654
0x14000d3ec  lea     r9, [rsp+28h+arg_0]
0x14000d3f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d3f5  mov     ecx, r8d
0x14000d3f8  and     ecx, 1Fh
0x14000d3fb  shr     r8d, 5
0x14000d3ff  shl     rax, cl
0x14000d402  and     rax, [rdi+8]
0x14000d406  mov     [rsp+28h+arg_0], rax
0x14000d40b  movzx   eax, byte ptr [r9]
0x14000d40f  add     eax, 0B15DCBh
0x14000d414  imul    ecx, eax, 25h ; '%'
0x14000d417  movzx   eax, byte ptr [r9+1]
0x14000d41c  add     ecx, eax
0x14000d41e  movzx   eax, byte ptr [r9+2]
0x14000d423  imul    edx, ecx, 25h ; '%'
0x14000d426  add     edx, eax
0x14000d428  movzx   eax, byte ptr [r9+3]
0x14000d42d  imul    ecx, edx, 25h ; '%'
0x14000d430  add     ecx, eax
0x14000d432  movzx   eax, byte ptr [r9+4]
0x14000d437  imul    edx, ecx, 25h ; '%'
0x14000d43a  add     edx, eax
0x14000d43c  movzx   eax, byte ptr [r9+5]
0x14000d441  imul    ecx, edx, 25h ; '%'
0x14000d444  add     ecx, eax
0x14000d446  movzx   eax, byte ptr [r9+6]
0x14000d44b  imul    edx, ecx, 25h ; '%'
0x14000d44e  add     edx, eax
0x14000d450  movzx   eax, byte ptr [r9+7]
0x14000d455  imul    edx, 25h ; '%'
0x14000d458  add     edx, eax
0x14000d45a  lea     eax, [r8-1]
0x14000d45e  and     rdx, rax
0x14000d461  mov     rax, cs:qword_140009654+4
0x14000d468  lea     r8, [rax+rdx*8]
0x14000d46c  mov     rax, [rdi]
0x14000d46f  mov     rdx, 8000000000000002h
0x14000d479  and     rax, rdx
0x14000d47c  cmp     rax, rdx
0x14000d47f  jnz     short loc_14000D486
0x14000d481  xor     eax, eax
0x14000d483  mov     rcx, [rax]
0x14000d486  mov     rax, [r8]
0x14000d489  test    al, 1
0x14000d48b  jnz     short loc_14000D4B0
0x14000d48d  cmp     rax, rdi
0x14000d490  jz      short loc_14000D497
0x14000d492  mov     r8, rax
0x14000d495  jmp     short loc_14000D486
0x14000d497  mov     rax, [rdi]
0x14000d49a  mov     [r8], rax
0x14000d49d  mov     eax, cs:dword_140009650
0x14000d4a3  dec     eax
0x14000d4a5  mov     cs:dword_140009650, eax
0x14000d4ab  or      [rdi], rdx
0x14000d4ae  jmp     short loc_14000D4B5
0x14000d4b0  xor     eax, eax
0x14000d4b2  mov     rdx, [rax]
0x14000d4b5  lea     rcx, qword_140009648
0x14000d4bc  call    FILockExclusiveRelease
0x14000d4c1  lea     rcx, [rdi+10h]; RunRef
0x14000d4c5  call    cs:__imp_ExReleaseRundownProtection
0x14000d4cc  nop     dword ptr [rax+rax+00h]
0x14000d4d1  lea     rcx, [rdi+10h]; RunRef
0x14000d4d5  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14000d4dc  nop     dword ptr [rax+rax+00h]
0x14000d4e1  xor     edx, edx; Tag
0x14000d4e3  mov     rcx, rdi; P
0x14000d4e6  call    cs:__imp_ExFreePoolWithTag
0x14000d4ed  nop     dword ptr [rax+rax+00h]
0x14000d4f2  mov     rbx, [rsp+28h+arg_8]
0x14000d4f7  add     rsp, 20h
0x14000d4fb  pop     rdi
0x14000d4fc  retn
```
