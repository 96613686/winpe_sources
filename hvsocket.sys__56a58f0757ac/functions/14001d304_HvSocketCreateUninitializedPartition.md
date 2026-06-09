# HvSocketCreateUninitializedPartition

- ea: `0x14001d304`
- end: `0x14001d52a`
- name: `HvSocketCreateUninitializedPartition`
- size: `550`
- prototype: `__int64 __fastcall(__int64, _OWORD *, char)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140018350`
- `0x140018e20`
- `0x140020124`

## callees

- `0x140001350`
- `0x1400017ec`
- `0x140009df0`
- `0x140009fa4`
- `0x14000a048`
- `0x14000bfe0`
- `0x14001d304`
- `0x14001df1c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001d430`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d430`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001d417`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001d417`

## string_xrefs

- `0x14001d32a`: `HvSocketCreateUninitializedPartition`
- `0x14001d378`: `HvSocketCreateUninitializedPartition`
- `0x14001d3bd`: `HvSocketCreateUninitializedPartition`
- `0x14001d4c2`: `HvSocketCreateUninitializedPartition`

## pseudocode

```c
__int64 __fastcall HvSocketCreateUninitializedPartition(__int64 a1, _OWORD *a2, char a3)
{
  int v7; // ebx
  PVOID v8; // rdi
  signed __int64 v9; // rax
  bool v10; // cc
  signed __int64 v11; // rax
  void (__fastcall *v12)(PVOID); // rax
  char *v13; // rbx
  __int64 v14; // rdi
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  PVOID Entry; // [rsp+78h] [rbp+20h] BYREF

  Entry = 0;
  if ( (unsigned int)dword_140013058 > 4 )
    HvsocketTraceMessage("HvSocketCreateUninitializedPartition", a2);
  if ( (unsigned __int8)HvSocketPartitionExists(a1, a2) )
    return 0;
  v7 = VmbusTlCreateObject(4, 512, &Entry);
  if ( v7 >= 0 )
  {
    v13 = (char *)Entry;
    *((_QWORD *)Entry + 10) = VmbusTlPartitionDestructor;
    *(_OWORD *)(v13 + 232) = *a2;
    VmbusTlInitializeObjectTable((PVOID)0x6E6F4350, (PRTL_AVL_TABLE)(v13 + 256));
    *((_QWORD *)v13 + 46) = v13 + 360;
    *((_QWORD *)v13 + 45) = v13 + 360;
    *((_QWORD *)v13 + 47) = 0;
    *((_QWORD *)v13 + 48) = 0;
    v13[472] = 0;
    v13[248] = a3;
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketCreateUninitializedPartition",
        190,
        a1,
        *(_QWORD *)(a1 + 8),
        (__int64)"Reference object");
    if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 8)) <= 1 )
      __fastfail(0xEu);
    *((_QWORD *)v13 + 25) = a1;
    v14 = a1 + 144;
    v15 = *(_QWORD **)(v14 + 8);
    if ( *v15 != v14 )
      __fastfail(3u);
    v16 = v13 + 216;
    v7 = 0;
    *v16 = v14;
    v16[1] = v15;
    *v15 = v16;
    *(_QWORD *)(v14 + 8) = v16;
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError("HvSocketCreateUninitializedPartition", 167, (unsigned int)v7, a2);
    v8 = Entry;
    if ( Entry )
    {
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"HvSocketCreateUninitializedPartition",
          203,
          (_DWORD)Entry,
          *((_QWORD *)Entry + 1),
          (__int64)"Dereference object");
      v9 = _InterlockedExchangeAdd64((volatile signed __int64 *)v8 + 1, 0xFFFFFFFFFFFFFFFFuLL);
      v10 = v9 <= 1;
      v11 = v9 - 1;
      if ( v10 )
      {
        if ( v11 )
          __fastfail(0xEu);
        v12 = (void (__fastcall *)(PVOID))*((_QWORD *)v8 + 10);
        if ( v12 )
          v12(v8);
        if ( *((_DWORD *)v8 + 22) == 1 )
        {
          ExFreePoolWithTag(v8, 0x69706E56u);
        }
        else if ( *((_DWORD *)v8 + 22) == 2 )
        {
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v8 + 12), v8);
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001d304  push    rbx
0x14001d306  push    rbp
0x14001d307  push    rsi
0x14001d308  push    rdi
0x14001d309  sub     rsp, 38h
0x14001d30d  mov     eax, cs:dword_140013058
0x14001d313  mov     bpl, r8b
0x14001d316  mov     [rsp+58h+Entry], 0
0x14001d31f  mov     rsi, rdx
0x14001d322  mov     rdi, rcx
0x14001d325  cmp     eax, 4
0x14001d328  jbe     short loc_14001D336
0x14001d32a  lea     rcx, aHvsocketcreate_1; "HvSocketCreateUninitializedPartition"
0x14001d331  call    HvsocketTraceMessage
0x14001d336  mov     rdx, rsi
0x14001d339  mov     rcx, rdi
0x14001d33c  call    HvSocketPartitionExists
0x14001d341  test    al, al
0x14001d343  jz      short loc_14001D34C
0x14001d345  xor     eax, eax
0x14001d347  jmp     loc_14001D520
0x14001d34c  lea     r8, [rsp+58h+Entry]
0x14001d351  mov     edx, 200h
0x14001d356  mov     ecx, 4
0x14001d35b  call    VmbusTlCreateObject
0x14001d360  mov     ebx, eax
0x14001d362  test    eax, eax
0x14001d364  jns     loc_14001D441
0x14001d36a  mov     eax, cs:dword_140013058
0x14001d370  cmp     eax, 2
0x14001d373  jbe     short loc_14001D38C
0x14001d375  mov     r9, rsi
0x14001d378  lea     rcx, aHvsocketcreate_1; "HvSocketCreateUninitializedPartition"
0x14001d37f  mov     r8d, ebx
0x14001d382  mov     edx, 0A7h
0x14001d387  call    HvsocketTraceGuidError
0x14001d38c  mov     rdi, [rsp+58h+Entry]
0x14001d391  test    rdi, rdi
0x14001d394  jz      loc_14001D51E
0x14001d39a  mov     eax, cs:dword_140013058
0x14001d3a0  cmp     eax, 5
0x14001d3a3  jbe     short loc_14001D3C9
0x14001d3a5  mov     r9, [rdi+8]
0x14001d3a9  lea     rax, aDereferenceObj; "Dereference object"
0x14001d3b0  mov     r8, rdi
0x14001d3b3  mov     [rsp+58h+var_38], rax
0x14001d3b8  mov     edx, 0CBh
0x14001d3bd  lea     rcx, aHvsocketcreate_1; "HvSocketCreateUninitializedPartition"
0x14001d3c4  call    HvsocketTraceReferenceCount
0x14001d3c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d3cd  lock xadd [rdi+8], rax
0x14001d3d3  sub     rax, 1
0x14001d3d7  jg      loc_14001D51E
0x14001d3dd  test    rax, rax
0x14001d3e0  jz      short loc_14001D3EE
0x14001d3e2  mov     ecx, 0Eh
0x14001d3e7  int     29h; Win8: RtlFailFast(ecx)
0x14001d3e9  jmp     loc_14001D51E
0x14001d3ee  mov     rax, [rdi+50h]
0x14001d3f2  test    rax, rax
0x14001d3f5  jz      short loc_14001D3FF
0x14001d3f7  mov     rcx, rdi
0x14001d3fa  call    _guard_dispatch_icall
0x14001d3ff  mov     ecx, [rdi+58h]
0x14001d402  sub     ecx, 1
0x14001d405  jz      short loc_14001D428
0x14001d407  cmp     ecx, 1
0x14001d40a  jnz     loc_14001D51E
0x14001d410  mov     rcx, [rdi+60h]; Lookaside
0x14001d414  mov     rdx, rdi; Entry
0x14001d417  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001d41e  nop     dword ptr [rax+rax+00h]
0x14001d423  jmp     loc_14001D51E
0x14001d428  mov     edx, 69706E56h; Tag
0x14001d42d  mov     rcx, rdi; P
0x14001d430  call    cs:__imp_ExFreePoolWithTag
0x14001d437  nop     dword ptr [rax+rax+00h]
0x14001d43c  jmp     loc_14001D51E
0x14001d441  mov     rbx, [rsp+58h+Entry]
0x14001d446  lea     rax, VmbusTlPartitionDestructor
0x14001d44d  mov     ecx, 6E6F4350h; TableContext
0x14001d452  mov     [rbx+50h], rax
0x14001d456  lea     rdx, [rbx+100h]; Table
0x14001d45d  movups  xmm0, xmmword ptr [rsi]
0x14001d460  movdqu  xmmword ptr [rbx+0E8h], xmm0
0x14001d468  call    VmbusTlInitializeObjectTable
0x14001d46d  lea     rax, [rbx+168h]
0x14001d474  mov     [rax+8], rax
0x14001d478  mov     [rax], rax
0x14001d47b  mov     qword ptr [rbx+178h], 0
0x14001d486  mov     qword ptr [rbx+180h], 0
0x14001d491  mov     byte ptr [rbx+1D8h], 0
0x14001d498  mov     [rbx+0F8h], bpl
0x14001d49f  mov     eax, cs:dword_140013058
0x14001d4a5  cmp     eax, 5
0x14001d4a8  jbe     short loc_14001D4CE
0x14001d4aa  mov     r9, [rdi+8]
0x14001d4ae  lea     rax, aReferenceObjec; "Reference object"
0x14001d4b5  mov     r8, rdi
0x14001d4b8  mov     [rsp+58h+var_38], rax
0x14001d4bd  mov     edx, 0BEh
0x14001d4c2  lea     rcx, aHvsocketcreate_1; "HvSocketCreateUninitializedPartition"
0x14001d4c9  call    HvsocketTraceReferenceCount
0x14001d4ce  mov     eax, 1
0x14001d4d3  lock xadd [rdi+8], rax
0x14001d4d9  inc     rax
0x14001d4dc  cmp     rax, 1
0x14001d4e0  jg      short loc_14001D4E9
0x14001d4e2  mov     ecx, 0Eh
0x14001d4e7  int     29h; Win8: RtlFailFast(ecx)
0x14001d4e9  mov     [rbx+0C8h], rdi
0x14001d4f0  add     rdi, 90h
0x14001d4f7  mov     rcx, [rdi+8]
0x14001d4fb  cmp     [rcx], rdi
0x14001d4fe  jz      short loc_14001D507
0x14001d500  mov     ecx, 3
0x14001d505  int     29h; Win8: RtlFailFast(ecx)
0x14001d507  lea     rax, [rbx+0D8h]
0x14001d50e  xor     ebx, ebx
0x14001d510  mov     [rax], rdi
0x14001d513  mov     [rax+8], rcx
0x14001d517  mov     [rcx], rax
0x14001d51a  mov     [rdi+8], rax
0x14001d51e  mov     eax, ebx
0x14001d520  add     rsp, 38h
0x14001d524  pop     rdi
0x14001d525  pop     rsi
0x14001d526  pop     rbp
0x14001d527  pop     rbx
0x14001d528  retn
```
