# lldpSendOidRequestAndWait

- ea: `0x1400123a0`
- end: `0x1400124f4`
- name: `lldpSendOidRequestAndWait`
- size: `340`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000edc0`
- `0x14000fa94`
- `0x14000fb2c`

## callees

- `0x140004b00`
- `0x140005d20`
- `0x1400123a0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140012420`
- `ntoskrnl!KeInitializeEvent` at `0x140012420`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012477`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012477`
- `NDIS!NdisOidRequest` at `0x14001244c`
- `NDIS!NdisOidRequest` at `0x14001244c`

## pseudocode

```c
__int64 __fastcall lldpSendOidRequestAndWait(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  unsigned int v5; // edi
  __int64 v6; // r8
  NTSTATUS v7; // eax
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xAu,
      (__int64)WPP_d30fab6896f93787189af96e4090c324_Traceguids,
      *(_DWORD *)(a2 + 32));
  *(_DWORD *)(a2 + 216) = 1919896652;
  *(_QWORD *)(a2 + 224) = &Event;
  *(_DWORD *)(a2 + 220) = 259;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  *(_DWORD *)a2 = 15466902;
  *(_DWORD *)(a2 + 12) = 5;
  *(_QWORD *)(a2 + 16) = a1;
  *(_QWORD *)(a2 + 24) = *(_QWORD *)(a1 + 8);
  v5 = NdisOidRequest(*(NDIS_HANDLE *)(a1 + 8), (PNDIS_OID_REQUEST)a2);
  if ( v5 == 259 )
  {
    v7 = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( v7 )
    {
      v5 = -1073741823;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v5;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0xBu,
          (__int64)WPP_d30fab6896f93787189af96e4090c324_Traceguids,
          v7);
    }
    else
    {
      v5 = *(_DWORD *)(a2 + 220);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, v4, v6, *(unsigned int *)(a2 + 32), v5);
  return v5;
}

```

## disassembly

```asm
0x1400123a0  mov     [rsp+arg_0], rbx
0x1400123a5  mov     [rsp+arg_8], rsi
0x1400123aa  push    rdi
0x1400123ab  sub     rsp, 50h
0x1400123af  xorps   xmm0, xmm0
0x1400123b2  xor     eax, eax
0x1400123b4  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x1400123b9  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x1400123be  mov     rbx, rdx
0x1400123c1  mov     rdi, rcx
0x1400123c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400123cb  lea     rsi, WPP_GLOBAL_Control
0x1400123d2  cmp     rcx, rsi
0x1400123d5  jz      short loc_1400123F6
0x1400123d7  cmp     byte ptr [rcx+29h], 4
0x1400123db  jb      short loc_1400123F6
0x1400123dd  mov     r9d, [rbx+20h]
0x1400123e1  lea     r8, WPP_d30fab6896f93787189af96e4090c324_Traceguids
0x1400123e8  mov     rcx, [rcx+18h]
0x1400123ec  mov     edx, 0Ah
0x1400123f1  call    WPP_SF_d
0x1400123f6  lea     rax, [rsp+58h+Event]
0x1400123fb  mov     dword ptr [rbx+0D8h], 726F4C4Ch
0x140012405  xor     r8d, r8d; State
0x140012408  mov     [rbx+0E0h], rax
0x14001240f  xor     edx, edx; Type
0x140012411  mov     dword ptr [rbx+0DCh], 103h
0x14001241b  lea     rcx, [rsp+58h+Event]; Event
0x140012420  call    cs:__imp_KeInitializeEvent
0x140012427  nop     dword ptr [rax+rax+00h]
0x14001242c  mov     dword ptr [rbx], 0EC0196h
0x140012432  mov     rdx, rbx; OidRequest
0x140012435  mov     dword ptr [rbx+0Ch], 5
0x14001243c  mov     [rbx+10h], rdi
0x140012440  mov     rax, [rdi+8]
0x140012444  mov     [rbx+18h], rax
0x140012448  mov     rcx, [rdi+8]; NdisBindingHandle
0x14001244c  call    cs:__imp_NdisOidRequest
0x140012453  nop     dword ptr [rax+rax+00h]
0x140012458  mov     edi, eax
0x14001245a  cmp     eax, 103h
0x14001245f  jnz     short loc_1400124BE
0x140012461  xor     r9d, r9d; Alertable
0x140012464  mov     [rsp+58h+Timeout], 0; Timeout
0x14001246d  xor     r8d, r8d; WaitMode
0x140012470  lea     rcx, [rsp+58h+Event]; Object
0x140012475  xor     edx, edx; WaitReason
0x140012477  call    cs:__imp_KeWaitForSingleObject
0x14001247e  nop     dword ptr [rax+rax+00h]
0x140012483  test    eax, eax
0x140012485  jnz     short loc_14001248F
0x140012487  mov     edi, [rbx+0DCh]
0x14001248d  jmp     short loc_1400124BE
0x14001248f  mov     edi, 0C0000001h
0x140012494  mov     rcx, cs:WPP_GLOBAL_Control
0x14001249b  cmp     rcx, rsi
0x14001249e  jz      short loc_1400124E1
0x1400124a0  cmp     byte ptr [rcx+29h], 2
0x1400124a4  jb      short loc_1400124BE
0x1400124a6  mov     rcx, [rcx+18h]
0x1400124aa  lea     r8, WPP_d30fab6896f93787189af96e4090c324_Traceguids
0x1400124b1  mov     edx, 0Bh
0x1400124b6  mov     r9d, eax
0x1400124b9  call    WPP_SF_d
0x1400124be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400124c5  cmp     rcx, rsi
0x1400124c8  jz      short loc_1400124E1
0x1400124ca  cmp     byte ptr [rcx+29h], 4
0x1400124ce  jb      short loc_1400124E1
0x1400124d0  mov     r9d, [rbx+20h]
0x1400124d4  mov     rcx, [rcx+18h]
0x1400124d8  mov     dword ptr [rsp+58h+Timeout], edi
0x1400124dc  call    WPP_SF_Dd
0x1400124e1  mov     rbx, [rsp+58h+arg_0]
0x1400124e6  mov     eax, edi
0x1400124e8  mov     rsi, [rsp+58h+arg_8]
0x1400124ed  add     rsp, 50h
0x1400124f1  pop     rdi
0x1400124f2  retn
```
