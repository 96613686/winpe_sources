# PcwpIoctlRemoveQueryItem(PCW_IOCTL_INPUT *,void *,ulong *)

- ea: `0x14000a920`
- end: `0x14000a99d`
- name: `?PcwpIoctlRemoveQueryItem@@YAJPEATPCW_IOCTL_INPUT@@PEAXPEAK@Z`
- size: `125`
- prototype: `__int64 __fastcall(union PCW_IOCTL_INPUT *, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000947c`
- `0x140009828`
- `0x14000a920`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000a95a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a983`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a95a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a983`

## pseudocode

```c
__int64 __fastcall PcwpIoctlRemoveQueryItem(union PCW_IOCTL_INPUT *a1, void *a2, unsigned int *a3)
{
  __int64 v3; // rdx
  int v5; // ebx
  PVOID v7; // rbx
  unsigned int Item; // edi
  PVOID Object; // [rsp+30h] [rbp+8h] BYREF

  v3 = *((_QWORD *)a1 + 1);
  Object = 0;
  v5 = PcwpReferenceObjectByHandle_PCW_QUERY_(&Object, v3, 2);
  if ( v5 >= 0 )
  {
    v7 = Object;
    Item = PCW_QUERY::CloseQueryItem((PCW_QUERY *)Object, *(_DWORD *)a1);
    if ( v7 )
      ObfDereferenceObject(v7);
    return Item;
  }
  else
  {
    if ( Object )
      ObfDereferenceObject(Object);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x14000a920  mov     [rsp+arg_8], rbx
0x14000a925  push    rdi
0x14000a926  sub     rsp, 20h
0x14000a92a  mov     rdx, [rcx+8]
0x14000a92e  mov     rdi, rcx
0x14000a931  lea     rcx, [rsp+28h+Object]
0x14000a936  mov     [rsp+28h+Object], 0
0x14000a93f  mov     r8d, 2
0x14000a945  call    PcwpReferenceObjectByHandle_PCW_QUERY_
0x14000a94a  mov     ebx, eax
0x14000a94c  test    eax, eax
0x14000a94e  jns     short loc_14000A96A
0x14000a950  mov     rcx, [rsp+28h+Object]; Object
0x14000a955  test    rcx, rcx
0x14000a958  jz      short loc_14000A966
0x14000a95a  call    cs:__imp_ObfDereferenceObject
0x14000a961  nop     dword ptr [rax+rax+00h]
0x14000a966  mov     eax, ebx
0x14000a968  jmp     short loc_14000A991
0x14000a96a  mov     rbx, [rsp+28h+Object]
0x14000a96f  mov     edx, [rdi]; unsigned int
0x14000a971  mov     rcx, rbx; this
0x14000a974  call    ?CloseQueryItem@PCW_QUERY@@QEAAJK@Z; PCW_QUERY::CloseQueryItem(ulong)
0x14000a979  mov     edi, eax
0x14000a97b  test    rbx, rbx
0x14000a97e  jz      short loc_14000A98F
0x14000a980  mov     rcx, rbx; Object
0x14000a983  call    cs:__imp_ObfDereferenceObject
0x14000a98a  nop     dword ptr [rax+rax+00h]
0x14000a98f  mov     eax, edi
0x14000a991  mov     rbx, [rsp+28h+arg_8]
0x14000a996  add     rsp, 20h
0x14000a99a  pop     rdi
0x14000a99b  retn
```
