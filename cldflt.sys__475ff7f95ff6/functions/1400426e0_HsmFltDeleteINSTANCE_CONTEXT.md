# HsmFltDeleteINSTANCE_CONTEXT

- ea: `0x1400426e0`
- end: `0x140042806`
- name: `HsmFltDeleteINSTANCE_CONTEXT`
- size: `294`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001e2a0`
- `0x1400426e0`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14004277e`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400427c9`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14004277e`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400427c9`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x14004279f`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x1400427ea`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x14004279f`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x1400427ea`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140042790`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400427db`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140042790`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400427db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042730`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042730`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004274a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004275b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004274a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004275b`
- `FLTMGR!FltReleaseContext` at `0x140042701`
- `FLTMGR!FltReleaseContext` at `0x140042701`

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
0x1400426e0  mov     [rsp+arg_8], rbx
0x1400426e5  push    rdi
0x1400426e6  sub     rsp, 20h
0x1400426ea  mov     rbx, rcx
0x1400426ed  add     rcx, 8; Resource
0x1400426f1  cmp     dword ptr [rbx], 63497348h
0x1400426f7  jnz     short loc_14004275B
0x1400426f9  mov     rcx, [rcx]; Context
0x1400426fc  test    rcx, rcx
0x1400426ff  jz      short loc_14004270D
0x140042701  call    cs:__imp_FltReleaseContext
0x140042708  nop     dword ptr [rax+rax+00h]
0x14004270d  mov     rcx, [rbx+10h]
0x140042711  test    rcx, rcx
0x140042714  jz      short loc_140042722
0x140042716  mov     rax, cs:qword_1400296F0
0x14004271d  call    _guard_dispatch_icall
0x140042722  mov     rcx, [rbx+48h]; P
0x140042726  test    rcx, rcx
0x140042729  jz      short loc_140042743
0x14004272b  mov     edx, 73557348h; Tag
0x140042730  call    cs:__imp_ExFreePoolWithTag
0x140042737  nop     dword ptr [rax+rax+00h]
0x14004273c  xorps   xmm0, xmm0
0x14004273f  movups  xmmword ptr [rbx+40h], xmm0
0x140042743  lea     rcx, [rbx+138h]; Resource
0x14004274a  call    cs:__imp_ExDeleteResourceLite
0x140042751  nop     dword ptr [rax+rax+00h]
0x140042756  jmp     loc_1400427FA
0x14004275b  call    cs:__imp_ExDeleteResourceLite
0x140042762  nop     dword ptr [rax+rax+00h]
0x140042767  lea     rdi, [rbx+70h]
0x14004276b  jmp     short loc_14004279C
0x14004276d  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x140042772  mov     [rsp+28h+RestartKey], 0
0x14004277b  mov     rcx, rdi; Table
0x14004277e  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x140042785  nop     dword ptr [rax+rax+00h]
0x14004278a  mov     rdx, rax; Buffer
0x14004278d  mov     rcx, rdi; Table
0x140042790  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140042797  nop     dword ptr [rax+rax+00h]
0x14004279c  mov     rcx, rdi; Table
0x14004279f  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x1400427a6  nop     dword ptr [rax+rax+00h]
0x1400427ab  test    eax, eax
0x1400427ad  jnz     short loc_14004276D
0x1400427af  add     rbx, 0D8h
0x1400427b6  jmp     short loc_1400427E7
0x1400427b8  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x1400427bd  mov     [rsp+28h+RestartKey], 0
0x1400427c6  mov     rcx, rbx; Table
0x1400427c9  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1400427d0  nop     dword ptr [rax+rax+00h]
0x1400427d5  mov     rdx, rax; Buffer
0x1400427d8  mov     rcx, rbx; Table
0x1400427db  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400427e2  nop     dword ptr [rax+rax+00h]
0x1400427e7  mov     rcx, rbx; Table
0x1400427ea  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x1400427f1  nop     dword ptr [rax+rax+00h]
0x1400427f6  test    eax, eax
0x1400427f8  jnz     short loc_1400427B8
0x1400427fa  mov     rbx, [rsp+28h+arg_8]
0x1400427ff  add     rsp, 20h
0x140042803  pop     rdi
0x140042804  retn
```
