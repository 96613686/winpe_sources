# ClIncomingCall

- ea: `0x14000a4b0`
- end: `0x14000a5ec`
- name: `ClIncomingCall`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000a4b0`
- `0x14000a648`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a582`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a582`
- `ntoskrnl!ExAllocatePool2` at `0x14000a50c`
- `ntoskrnl!ExAllocatePool2` at `0x14000a50c`
- `NDIS!NdisAllocateIoWorkItem` at `0x14000a567`
- `NDIS!NdisAllocateIoWorkItem` at `0x14000a567`
- `NDIS!NdisQueueIoWorkItem` at `0x14000a59d`
- `NDIS!NdisQueueIoWorkItem` at `0x14000a59d`

## pseudocode

```c
__int64 __fastcall ClIncomingCall(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *Pool2; // rax
  void *v7; // rdi
  unsigned int v8; // ebx
  NDIS_HANDLE IoWorkItem; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, a2);
  }
  Pool2 = (_QWORD *)ExAllocatePool2(64, 24, 1112432983);
  v7 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = a1;
    Pool2[1] = a2;
    Pool2[2] = a3;
    IoWorkItem = NdisAllocateIoWorkItem(NdisMiniportDriverHandle);
    if ( IoWorkItem )
    {
      NdisQueueIoWorkItem(IoWorkItem, (NDIS_IO_WORKITEM_ROUTINE)ClIncomingCallWork, v7);
      v8 = 259;
    }
    else
    {
      v8 = -1073741670;
      ExFreePoolWithTag(v7, 0);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
    }
    v8 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
  }
  return v8;
}

```

## disassembly

```asm
0x14000a4b0  push    rbx
0x14000a4b2  push    rbp
0x14000a4b3  push    rsi
0x14000a4b4  push    rdi
0x14000a4b5  push    r15
0x14000a4b7  sub     rsp, 20h
0x14000a4bb  mov     rsi, r8
0x14000a4be  mov     rbx, rdx
0x14000a4c1  mov     rbp, rcx
0x14000a4c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4cb  lea     r15, WPP_GLOBAL_Control
0x14000a4d2  cmp     rcx, r15
0x14000a4d5  jz      short loc_14000A4FE
0x14000a4d7  test    dword ptr [rcx+2Ch], 8000h
0x14000a4de  jz      short loc_14000A4FE
0x14000a4e0  cmp     byte ptr [rcx+29h], 5
0x14000a4e4  jb      short loc_14000A4FE
0x14000a4e6  mov     rcx, [rcx+18h]
0x14000a4ea  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14000a4f1  mov     edx, 1Fh
0x14000a4f6  mov     r9, rbx
0x14000a4f9  call    WPP_SF_q
0x14000a4fe  mov     edx, 18h
0x14000a503  mov     r8d, 424E6157h
0x14000a509  lea     ecx, [rdx+28h]
0x14000a50c  call    cs:__imp_ExAllocatePool2
0x14000a513  nop     dword ptr [rax+rax+00h]
0x14000a518  mov     rdi, rax
0x14000a51b  test    rax, rax
0x14000a51e  jnz     short loc_14000A555
0x14000a520  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a527  cmp     rcx, r15
0x14000a52a  jz      short loc_14000A54E
0x14000a52c  test    dword ptr [rcx+2Ch], 8000h
0x14000a533  jz      short loc_14000A54E
0x14000a535  cmp     byte ptr [rcx+29h], 3
0x14000a539  jb      short loc_14000A54E
0x14000a53b  mov     rcx, [rcx+18h]
0x14000a53f  lea     edx, [rax+20h]
0x14000a542  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14000a549  call    WPP_SF_
0x14000a54e  mov     ebx, 0C000009Ah
0x14000a553  jmp     short loc_14000A5AE
0x14000a555  mov     [rax], rbp
0x14000a558  mov     [rax+8], rbx
0x14000a55c  mov     [rax+10h], rsi
0x14000a560  mov     rcx, cs:NdisMiniportDriverHandle; NdisObjectHandle
0x14000a567  call    cs:__imp_NdisAllocateIoWorkItem
0x14000a56e  nop     dword ptr [rax+rax+00h]
0x14000a573  test    rax, rax
0x14000a576  jnz     short loc_14000A590
0x14000a578  xor     edx, edx; Tag
0x14000a57a  mov     rcx, rdi; P
0x14000a57d  mov     ebx, 0C000009Ah
0x14000a582  call    cs:__imp_ExFreePoolWithTag
0x14000a589  nop     dword ptr [rax+rax+00h]
0x14000a58e  jmp     short loc_14000A5AE
0x14000a590  mov     r8, rdi; WorkItemContext
0x14000a593  lea     rdx, ClIncomingCallWork; Routine
0x14000a59a  mov     rcx, rax; NdisIoWorkItemHandle
0x14000a59d  call    cs:__imp_NdisQueueIoWorkItem
0x14000a5a4  nop     dword ptr [rax+rax+00h]
0x14000a5a9  mov     ebx, 103h
0x14000a5ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5b5  cmp     rcx, r15
0x14000a5b8  jz      short loc_14000A5DE
0x14000a5ba  test    dword ptr [rcx+2Ch], 8000h
0x14000a5c1  jz      short loc_14000A5DE
0x14000a5c3  cmp     byte ptr [rcx+29h], 5
0x14000a5c7  jb      short loc_14000A5DE
0x14000a5c9  mov     rcx, [rcx+18h]
0x14000a5cd  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14000a5d4  mov     edx, 21h ; '!'
0x14000a5d9  call    WPP_SF_
0x14000a5de  mov     eax, ebx
0x14000a5e0  add     rsp, 20h
0x14000a5e4  pop     r15
0x14000a5e6  pop     rdi
0x14000a5e7  pop     rsi
0x14000a5e8  pop     rbp
0x14000a5e9  pop     rbx
0x14000a5ea  retn
```
