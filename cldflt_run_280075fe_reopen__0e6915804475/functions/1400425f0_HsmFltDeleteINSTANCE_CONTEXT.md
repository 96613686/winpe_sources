# HsmFltDeleteINSTANCE_CONTEXT

- ea: `0x1400425f0`
- end: `0x140042716`
- name: `HsmFltDeleteINSTANCE_CONTEXT`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001e220`
- `0x1400425f0`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14004268e`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400426d9`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14004268e`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400426d9`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x1400426af`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x1400426fa`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x1400426af`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x1400426fa`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400426a0`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400426eb`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400426a0`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400426eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042640`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042640`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004265a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004266b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004265a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004266b`
- `FLTMGR!FltReleaseContext` at `0x140042611`
- `FLTMGR!FltReleaseContext` at `0x140042611`

## pseudocode

```c
NTSTATUS __fastcall HsmFltDeleteINSTANCE_CONTEXT(__int64 a1)
{
  struct _ERESOURCE *v2; // rcx
  struct _LIST_ENTRY *Flink; // rcx
  void *v4; // rcx
  NTSTATUS result; // eax
  PVOID v6; // rax
  struct _RTL_AVL_TABLE *i; // rbx
  PVOID v8; // rax
  PVOID RestartKey; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _ERESOURCE *)(a1 + 8);
  if ( *(_DWORD *)a1 == 1665758024 )
  {
    Flink = v2->SystemResourcesList.Flink;
    if ( Flink )
      FltReleaseContext(Flink);
    if ( *(_QWORD *)(a1 + 16) )
      ((void (*)(void))qword_1400296F0)();
    v4 = *(void **)(a1 + 72);
    if ( v4 )
    {
      ExFreePoolWithTag(v4, 0x73557348u);
      *(_OWORD *)(a1 + 64) = 0;
    }
    return ExDeleteResourceLite((PERESOURCE)(a1 + 312));
  }
  else
  {
    ExDeleteResourceLite(v2);
    while ( RtlNumberGenericTableElementsAvl((PRTL_AVL_TABLE)(a1 + 112)) )
    {
      RestartKey = 0;
      v6 = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)(a1 + 112), &RestartKey);
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 112), v6);
    }
    for ( i = (struct _RTL_AVL_TABLE *)(a1 + 216); ; RtlDeleteElementGenericTableAvl(i, v8) )
    {
      result = RtlNumberGenericTableElementsAvl(i);
      if ( !result )
        break;
      RestartKey = 0;
      v8 = RtlEnumerateGenericTableWithoutSplayingAvl(i, &RestartKey);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400425f0  mov     [rsp+arg_8], rbx
0x1400425f5  push    rdi
0x1400425f6  sub     rsp, 20h
0x1400425fa  mov     rbx, rcx
0x1400425fd  add     rcx, 8; Resource
0x140042601  cmp     dword ptr [rbx], 63497348h
0x140042607  jnz     short loc_14004266B
0x140042609  mov     rcx, [rcx]; Context
0x14004260c  test    rcx, rcx
0x14004260f  jz      short loc_14004261D
0x140042611  call    cs:__imp_FltReleaseContext
0x140042618  nop     dword ptr [rax+rax+00h]
0x14004261d  mov     rcx, [rbx+10h]
0x140042621  test    rcx, rcx
0x140042624  jz      short loc_140042632
0x140042626  mov     rax, cs:qword_1400296F0
0x14004262d  call    _guard_dispatch_icall
0x140042632  mov     rcx, [rbx+48h]; P
0x140042636  test    rcx, rcx
0x140042639  jz      short loc_140042653
0x14004263b  mov     edx, 73557348h; Tag
0x140042640  call    cs:__imp_ExFreePoolWithTag
0x140042647  nop     dword ptr [rax+rax+00h]
0x14004264c  xorps   xmm0, xmm0
0x14004264f  movups  xmmword ptr [rbx+40h], xmm0
0x140042653  lea     rcx, [rbx+138h]; Resource
0x14004265a  call    cs:__imp_ExDeleteResourceLite
0x140042661  nop     dword ptr [rax+rax+00h]
0x140042666  jmp     loc_14004270A
0x14004266b  call    cs:__imp_ExDeleteResourceLite
0x140042672  nop     dword ptr [rax+rax+00h]
0x140042677  lea     rdi, [rbx+70h]
0x14004267b  jmp     short loc_1400426AC
0x14004267d  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x140042682  mov     [rsp+28h+RestartKey], 0
0x14004268b  mov     rcx, rdi; Table
0x14004268e  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x140042695  nop     dword ptr [rax+rax+00h]
0x14004269a  mov     rdx, rax; Buffer
0x14004269d  mov     rcx, rdi; Table
0x1400426a0  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400426a7  nop     dword ptr [rax+rax+00h]
0x1400426ac  mov     rcx, rdi; Table
0x1400426af  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x1400426b6  nop     dword ptr [rax+rax+00h]
0x1400426bb  test    eax, eax
0x1400426bd  jnz     short loc_14004267D
0x1400426bf  add     rbx, 0D8h
0x1400426c6  jmp     short loc_1400426F7
0x1400426c8  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x1400426cd  mov     [rsp+28h+RestartKey], 0
0x1400426d6  mov     rcx, rbx; Table
0x1400426d9  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1400426e0  nop     dword ptr [rax+rax+00h]
0x1400426e5  mov     rdx, rax; Buffer
0x1400426e8  mov     rcx, rbx; Table
0x1400426eb  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400426f2  nop     dword ptr [rax+rax+00h]
0x1400426f7  mov     rcx, rbx; Table
0x1400426fa  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x140042701  nop     dword ptr [rax+rax+00h]
0x140042706  test    eax, eax
0x140042708  jnz     short loc_1400426C8
0x14004270a  mov     rbx, [rsp+28h+arg_8]
0x14004270f  add     rsp, 20h
0x140042713  pop     rdi
0x140042714  retn
```
