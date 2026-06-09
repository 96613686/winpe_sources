# NdisWanFreeLinkCB

- ea: `0x1400059d4`
- end: `0x140005a6c`
- name: `NdisWanFreeLinkCB`
- size: `152`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000550c`
- `0x14000a310`
- `0x140024008`

## callees

- `0x1400059d4`
- `0x14000a648`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005a30`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005a30`
- `NDIS!NdisSetEvent` at `0x140005a54`
- `NDIS!NdisSetEvent` at `0x140005a54`

## pseudocode

```c
void __fastcall NdisWanFreeLinkCB(_QWORD *Entry)
{
  __int64 v1; // rbx

  v1 = Entry[9];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids, Entry);
  }
  *((_DWORD *)Entry + 5) = 0;
  ExFreeToNPagedLookasideList(&LinkProtoCBList, Entry);
  _InterlockedDecrement((volatile signed __int32 *)(v1 + 48));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 16), 0xFFFFFFFF) == 1 )
    NdisSetEvent((PNDIS_EVENT)(v1 + 552));
}

```

## disassembly

```asm
0x1400059d4  mov     [rsp+arg_0], rbx
0x1400059d9  push    rdi
0x1400059da  sub     rsp, 20h
0x1400059de  mov     rbx, [rcx+48h]
0x1400059e2  mov     rdi, rcx
0x1400059e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059ec  lea     rax, WPP_GLOBAL_Control
0x1400059f3  cmp     rcx, rax
0x1400059f6  jz      short loc_140005A1F
0x1400059f8  test    dword ptr [rcx+2Ch], 8000h
0x1400059ff  jz      short loc_140005A1F
0x140005a01  cmp     byte ptr [rcx+29h], 5
0x140005a05  jb      short loc_140005A1F
0x140005a07  mov     rcx, [rcx+18h]
0x140005a0b  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x140005a12  mov     edx, 1Eh
0x140005a17  mov     r9, rdi
0x140005a1a  call    WPP_SF_q
0x140005a1f  mov     rdx, rdi; Entry
0x140005a22  mov     dword ptr [rdi+14h], 0
0x140005a29  lea     rcx, LinkProtoCBList; Lookaside
0x140005a30  call    cs:__imp_ExFreeToNPagedLookasideList
0x140005a37  nop     dword ptr [rax+rax+00h]
0x140005a3c  lock dec dword ptr [rbx+30h]
0x140005a40  or      eax, 0FFFFFFFFh
0x140005a43  lock xadd [rbx+10h], eax
0x140005a48  cmp     eax, 1
0x140005a4b  jnz     short loc_140005A60
0x140005a4d  lea     rcx, [rbx+228h]; Event
0x140005a54  call    cs:__imp_NdisSetEvent
0x140005a5b  nop     dword ptr [rax+rax+00h]
0x140005a60  mov     rbx, [rsp+28h+arg_0]
0x140005a65  add     rsp, 20h
0x140005a69  pop     rdi
0x140005a6a  retn
```
