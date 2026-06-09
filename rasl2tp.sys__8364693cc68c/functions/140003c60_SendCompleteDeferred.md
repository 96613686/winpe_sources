# SendCompleteDeferred

- ea: `0x140003c60`
- end: `0x140003cf2`
- name: `SendCompleteDeferred`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001870`
- `0x140003050`
- `0x140003c60`
- `0x14001b830`

## import_xrefs

- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140003c94`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140003c94`
- `NDIS!NdisFreeIoWorkItem` at `0x140003c77`
- `NDIS!NdisFreeIoWorkItem` at `0x140003c77`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall SendCompleteDeferred(__int64 a1, void *a2)
{
  __int64 v2; // rdi
  PDEVICE_OBJECT *result; // rax

  v2 = *(_QWORD *)(a1 + 144);
  NdisFreeIoWorkItem(a2);
  NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(v2 + 304), *(PNET_BUFFER_LIST *)(a1 + 128), 0);
  DereferenceAdapter(*(_QWORD *)(v2 + 24));
  DereferenceCall(v2);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return (PDEVICE_OBJECT *)WPP_SF_(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 42,
                                 WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140003c60  mov     [rsp+arg_0], rbx
0x140003c65  push    rdi
0x140003c66  sub     rsp, 20h
0x140003c6a  mov     rdi, [rcx+90h]
0x140003c71  mov     rbx, rcx
0x140003c74  mov     rcx, rdx; NdisIoWorkItemHandle
0x140003c77  call    cs:__imp_NdisFreeIoWorkItem
0x140003c7e  nop     dword ptr [rax+rax+00h]
0x140003c83  mov     rdx, [rbx+80h]; NetBufferLists
0x140003c8a  xor     r8d, r8d; SendCompleteFlags
0x140003c8d  mov     rcx, [rdi+130h]; NdisVcHandle
0x140003c94  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x140003c9b  nop     dword ptr [rax+rax+00h]
0x140003ca0  mov     rcx, [rdi+18h]
0x140003ca4  call    DereferenceAdapter
0x140003ca9  mov     rcx, rdi
0x140003cac  call    DereferenceCall
0x140003cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cb8  lea     rax, WPP_GLOBAL_Control
0x140003cbf  cmp     rcx, rax
0x140003cc2  jz      short loc_140003CE6
0x140003cc4  mov     eax, [rcx+2Ch]
0x140003cc7  test    al, 10h
0x140003cc9  jz      short loc_140003CE6
0x140003ccb  cmp     byte ptr [rcx+29h], 4
0x140003ccf  jb      short loc_140003CE6
0x140003cd1  mov     rcx, [rcx+18h]
0x140003cd5  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140003cdc  mov     edx, 2Ah ; '*'
0x140003ce1  call    WPP_SF_
0x140003ce6  mov     rbx, [rsp+28h+arg_0]
0x140003ceb  add     rsp, 20h
0x140003cef  pop     rdi
0x140003cf0  retn
```
