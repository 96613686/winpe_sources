# MupiUncProviderCompletion

- ea: `0x140001b30`
- end: `0x140001c05`
- name: `MupiUncProviderCompletion`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001b30`
- `0x140002614`
- `0x140019f50`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140001b8e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001b8e`
- `ntoskrnl!ExQueueWorkItem` at `0x140001bc4`
- `ntoskrnl!ExQueueWorkItem` at `0x140001bc4`

## pseudocode

```c
__int64 __fastcall MupiUncProviderCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v6; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      42,
      WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      a2,
      *(_DWORD *)(a2 + 48));
  }
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  *(_DWORD *)(a3 + 32) = *(_DWORD *)(a2 + 48);
  if ( !*(_BYTE *)(a2 + 65) )
    return 3221225494LL;
  if ( KeGetCurrentIrql() < 2u )
  {
    MupStateMachineWorker((_QWORD *)a3, v6);
    return 3221225494LL;
  }
  *(_QWORD *)(a3 + 104) = 0;
  *(_QWORD *)(a3 + 120) = MupStateMachineWorker;
  *(_QWORD *)(a3 + 128) = a3;
  ExQueueWorkItem((PWORK_QUEUE_ITEM)(a3 + 104), CriticalWorkQueue);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001b30  mov     [rsp+arg_0], rbx
0x140001b35  push    rdi
0x140001b36  sub     rsp, 30h
0x140001b3a  mov     rdi, r8
0x140001b3d  mov     rbx, rdx
0x140001b40  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b47  lea     rax, WPP_GLOBAL_Control
0x140001b4e  cmp     rcx, rax
0x140001b51  jz      short loc_140001B60
0x140001b53  test    dword ptr [rcx+2Ch], 4000000h
0x140001b5a  jnz     loc_140001BE1
0x140001b60  cmp     byte ptr [rbx+41h], 0
0x140001b64  jz      short loc_140001B71
0x140001b66  mov     rax, [rbx+0B8h]
0x140001b6d  or      byte ptr [rax+3], 1
0x140001b71  mov     eax, [rbx+30h]
0x140001b74  mov     [rdi+20h], eax
0x140001b77  cmp     byte ptr [rbx+41h], 0
0x140001b7b  jnz     short loc_140001B8E
0x140001b7d  mov     eax, 0C0000016h
0x140001b82  mov     rbx, [rsp+38h+arg_0]
0x140001b87  add     rsp, 30h
0x140001b8b  pop     rdi
0x140001b8c  retn
0x140001b8e  call    cs:__imp_KeGetCurrentIrql
0x140001b95  nop     dword ptr [rax+rax+00h]
0x140001b9a  cmp     al, 2
0x140001b9c  jnb     short loc_140001BA8
0x140001b9e  mov     rcx, rdi; P
0x140001ba1  call    MupStateMachineWorker
0x140001ba6  jmp     short loc_140001B7D
0x140001ba8  lea     rcx, [rdi+68h]; WorkItem
0x140001bac  xor     edx, edx; QueueType
0x140001bae  lea     rax, MupStateMachineWorker
0x140001bb5  mov     qword ptr [rcx], 0
0x140001bbc  mov     [rcx+10h], rax
0x140001bc0  mov     [rcx+18h], rdi
0x140001bc4  call    cs:__imp_ExQueueWorkItem
0x140001bcb  nop     dword ptr [rax+rax+00h]
0x140001bd0  mov     rbx, [rsp+38h+arg_0]
0x140001bd5  mov     eax, 0C0000016h
0x140001bda  add     rsp, 30h
0x140001bde  pop     rdi
0x140001bdf  retn
0x140001be1  mov     eax, [rbx+30h]
0x140001be4  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x140001beb  mov     rcx, [rcx+18h]
0x140001bef  mov     edx, 2Ah ; '*'
0x140001bf4  mov     r9, rbx
0x140001bf7  mov     [rsp+38h+var_18], eax
0x140001bfb  call    WPP_SF_qD
0x140001c00  jmp     loc_140001B60
```
