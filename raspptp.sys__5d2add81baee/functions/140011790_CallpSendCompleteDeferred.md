# CallpSendCompleteDeferred

- ea: `0x140011790`
- end: `0x14001182f`
- name: `CallpSendCompleteDeferred`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001a70`
- `0x140004308`
- `0x140011790`

## import_xrefs

- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400117f0`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400117f0`

## pseudocode

```c
__int64 __fastcall CallpSendCompleteDeferred(__int64 a1)
{
  __int64 v1; // rbx
  struct _NET_BUFFER_LIST *v2; // rdi

  v1 = *(_QWORD *)(a1 + 24);
  v2 = *(struct _NET_BUFFER_LIST **)(a1 + 32);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 94, a1, v1, v2, *(_DWORD *)(a1 + 40));
  }
  NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(v1 + 224), v2, 0);
  _InterlockedIncrement(&dword_14000B3F4);
  _InterlockedIncrement((volatile signed __int32 *)(v1 + 664));
  DereferenceRefCount(*(_QWORD *)(v1 + 56) + 192LL);
  return DereferenceRefCount(v1 + 32);
}

```

## disassembly

```asm
0x140011790  mov     [rsp+arg_0], rbx
0x140011795  push    rdi
0x140011796  sub     rsp, 30h
0x14001179a  mov     rbx, [rcx+18h]
0x14001179e  mov     r8, rcx
0x1400117a1  mov     rdi, [rcx+20h]
0x1400117a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400117ac  lea     rax, WPP_GLOBAL_Control
0x1400117b3  cmp     rcx, rax
0x1400117b6  jz      short loc_1400117E3
0x1400117b8  mov     eax, [rcx+2Ch]
0x1400117bb  test    al, 20h
0x1400117bd  jz      short loc_1400117E3
0x1400117bf  cmp     byte ptr [rcx+29h], 2
0x1400117c3  jb      short loc_1400117E3
0x1400117c5  mov     eax, [r8+28h]
0x1400117c9  mov     edx, 5Eh ; '^'
0x1400117ce  mov     rcx, [rcx+18h]
0x1400117d2  mov     r9, rbx
0x1400117d5  mov     [rsp+38h+var_10], eax
0x1400117d9  mov     [rsp+38h+var_18], rdi
0x1400117de  call    WPP_SF_qqD
0x1400117e3  mov     rcx, [rbx+0E0h]; NdisVcHandle
0x1400117ea  xor     r8d, r8d; SendCompleteFlags
0x1400117ed  mov     rdx, rdi; NetBufferLists
0x1400117f0  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x1400117f7  nop     dword ptr [rax+rax+00h]
0x1400117fc  lock inc cs:dword_14000B3F4
0x140011803  lock inc dword ptr [rbx+298h]
0x14001180a  mov     rcx, [rbx+38h]
0x14001180e  add     rcx, 0C0h
0x140011815  call    DereferenceRefCount
0x14001181a  lea     rcx, [rbx+20h]
0x14001181e  call    DereferenceRefCount
0x140011823  mov     rbx, [rsp+38h+arg_0]
0x140011828  add     rsp, 30h
0x14001182c  pop     rdi
0x14001182d  retn
```
