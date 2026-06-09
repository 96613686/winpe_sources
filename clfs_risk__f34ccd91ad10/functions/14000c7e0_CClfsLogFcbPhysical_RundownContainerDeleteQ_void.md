# CClfsLogFcbPhysical::RundownContainerDeleteQ(void)

- ea: `0x14000c7e0`
- end: `0x14000c86e`
- name: `?RundownContainerDeleteQ@CClfsLogFcbPhysical@@UEAAJXZ`
- size: `142`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140016410`

## callees

- `0x14000c7e0`
- `0x14000c874`
- `0x140015ff0`
- `0x140017f20`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000c82f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000c82f`
- `ntoskrnl!ExQueryDepthSList` at `0x14000c7fc`
- `ntoskrnl!ExQueryDepthSList` at `0x14000c7fc`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::RundownContainerDeleteQ(union _SLIST_HEADER *Context)
{
  union _SLIST_HEADER *v1; // rdi
  PSLIST_ENTRY v4; // rax
  struct _SLIST_ENTRY *Next; // rbx

  v1 = Context + 61;
  if ( !ExQueryDepthSList(Context + 61) )
    return 0;
  if ( !CClfsLogFcbCommon::IsMainLocked((CClfsLogFcbCommon *)Context) )
  {
    while ( 1 )
    {
      v4 = ExpInterlockedPopEntrySList(v1);
      if ( !v4 )
        break;
      Next = v4[1].Next;
      (*((void (__fastcall **)(struct _SLIST_ENTRY *))&Next->Next[1].Next + 1))(Next);
      (*((void (__fastcall **)(struct _SLIST_ENTRY *))&Next->Next->Next + 1))(Next);
    }
    return 0;
  }
  return CClfsLogFcbCommon::QueueRundownContainerDeleteQ(Context);
}

```

## disassembly

```asm
0x14000c7e0  mov     [rsp+arg_0], rbx
0x14000c7e5  mov     [rsp+arg_8], rsi
0x14000c7ea  push    rdi
0x14000c7eb  sub     rsp, 20h
0x14000c7ef  lea     rdi, [rcx+3D0h]
0x14000c7f6  mov     rbx, rcx
0x14000c7f9  mov     rcx, rdi; SListHead
0x14000c7fc  call    cs:__imp_ExQueryDepthSList
0x14000c803  nop     dword ptr [rax+rax+00h]
0x14000c808  test    ax, ax
0x14000c80b  jnz     short loc_14000C820
0x14000c80d  xor     eax, eax
0x14000c80f  mov     rbx, [rsp+28h+arg_0]
0x14000c814  mov     rsi, [rsp+28h+arg_8]
0x14000c819  add     rsp, 20h
0x14000c81d  pop     rdi
0x14000c81e  retn
0x14000c820  mov     rcx, rbx; this
0x14000c823  call    ?IsMainLocked@CClfsLogFcbCommon@@QEAAEXZ; CClfsLogFcbCommon::IsMainLocked(void)
0x14000c828  test    al, al
0x14000c82a  jnz     short loc_14000C864
0x14000c82c  mov     rcx, rdi; ListHead
0x14000c82f  call    cs:__imp_ExpInterlockedPopEntrySList
0x14000c836  nop     dword ptr [rax+rax+00h]
0x14000c83b  test    rax, rax
0x14000c83e  jz      short loc_14000C80D
0x14000c840  mov     rbx, [rax+10h]
0x14000c844  mov     rcx, rbx
0x14000c847  mov     rax, [rbx]
0x14000c84a  mov     rax, [rax+18h]
0x14000c84e  call    _guard_dispatch_icall
0x14000c853  mov     rax, [rbx]
0x14000c856  mov     rcx, rbx
0x14000c859  mov     rax, [rax+8]
0x14000c85d  call    _guard_dispatch_icall
0x14000c862  jmp     short loc_14000C82C
0x14000c864  mov     rcx, rbx; Context
0x14000c867  call    ?QueueRundownContainerDeleteQ@CClfsLogFcbCommon@@QEAAJXZ; CClfsLogFcbCommon::QueueRundownContainerDeleteQ(void)
0x14000c86c  jmp     short loc_14000C80F
```
