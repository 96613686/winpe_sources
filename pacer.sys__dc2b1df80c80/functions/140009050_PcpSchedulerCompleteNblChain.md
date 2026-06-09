# PcpSchedulerCompleteNblChain

- ea: `0x140009050`
- end: `0x1400090f9`
- name: `PcpSchedulerCompleteNblChain`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b9d4`

## callees

- `0x140003770`
- `0x140009050`
- `0x140009100`

## import_xrefs

- `NDIS!NdisFreeNetBufferListContext` at `0x1400090e8`
- `NDIS!NdisFreeNetBufferListContext` at `0x1400090e8`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000909b`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000909b`

## pseudocode

```c
void __fastcall PcpSchedulerCompleteNblChain(__int64 a1, _QWORD *a2, struct _NET_BUFFER_LIST *a3, ULONG a4)
{
  __int64 v4; // rax
  PVOID v8; // rcx

  v4 = a2[32];
  if ( *(_DWORD *)(v4 + 16) == 3 && *(_WORD *)(v4 + 212) == 2048 )
  {
    PcpLineDereference(a2);
    NdisFreeNetBufferListContext(a3, 8u);
  }
  v8 = a3->NetBufferListInfo[3];
  if ( v8 && v8 == *(PVOID *)&WPP_MAIN_CB.DeviceLock.Header.Lock )
  {
    PcpDereferenceFlow(v8);
    a3->NetBufferListInfo[3] = 0;
  }
  NdisFSendNetBufferListsComplete(*(NDIS_HANDLE *)(a2[32] + 40LL), a3, a4);
}

```

## disassembly

```asm
0x140009050  mov     [rsp+arg_0], rbx
0x140009055  mov     [rsp+arg_8], rsi
0x14000905a  push    rdi
0x14000905b  sub     rsp, 20h
0x14000905f  mov     rax, [rdx+100h]
0x140009066  mov     esi, r9d
0x140009069  mov     rbx, r8
0x14000906c  mov     rdi, rdx
0x14000906f  cmp     dword ptr [rax+10h], 3
0x140009073  jz      short loc_1400090CA
0x140009075  mov     rcx, [rbx+0A8h]
0x14000907c  test    rcx, rcx
0x14000907f  jz      short loc_14000908A
0x140009081  cmp     rcx, qword ptr cs:WPP_MAIN_CB.DeviceLock.Header
0x140009088  jz      short loc_1400090B8
0x14000908a  mov     rcx, [rdi+100h]
0x140009091  mov     r8d, esi; SendCompleteFlags
0x140009094  mov     rdx, rbx; NetBufferList
0x140009097  mov     rcx, [rcx+28h]; NdisFilterHandle
0x14000909b  call    cs:__imp_NdisFSendNetBufferListsComplete
0x1400090a2  nop     dword ptr [rax+rax+00h]
0x1400090a7  mov     rbx, [rsp+28h+arg_0]
0x1400090ac  mov     rsi, [rsp+28h+arg_8]
0x1400090b1  add     rsp, 20h
0x1400090b5  pop     rdi
0x1400090b6  retn
0x1400090b8  call    PcpDereferenceFlow
0x1400090bd  mov     qword ptr [rbx+0A8h], 0
0x1400090c8  jmp     short loc_14000908A
0x1400090ca  mov     ecx, 800h
0x1400090cf  cmp     [rax+0D4h], cx
0x1400090d6  jnz     short loc_140009075
0x1400090d8  mov     rcx, rdi; P
0x1400090db  call    PcpLineDereference
0x1400090e0  mov     edx, 8; ContextSize
0x1400090e5  mov     rcx, rbx; NetBufferList
0x1400090e8  call    cs:__imp_NdisFreeNetBufferListContext
0x1400090ef  nop     dword ptr [rax+rax+00h]
0x1400090f4  jmp     loc_140009075
```
