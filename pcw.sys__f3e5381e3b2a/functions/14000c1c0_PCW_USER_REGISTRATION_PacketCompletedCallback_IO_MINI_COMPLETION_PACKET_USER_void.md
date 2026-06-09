# PCW_USER_REGISTRATION::PacketCompletedCallback(_IO_MINI_COMPLETION_PACKET_USER *,void *)

- ea: `0x14000c1c0`
- end: `0x14000c239`
- name: `?PacketCompletedCallback@PCW_USER_REGISTRATION@@CAXPEAU_IO_MINI_COMPLETION_PACKET_USER@@PEAX@Z`
- size: `121`
- prototype: `static void(struct _IO_MINI_COMPLETION_PACKET_USER *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000c1c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c1d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c1d2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c209`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c209`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c1e4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c1e4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c1fd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c1fd`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c21c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c21c`

## pseudocode

```c
void __fastcall PCW_USER_REGISTRATION::PacketCompletedCallback(struct _IO_MINI_COMPLETION_PACKET_USER *a1, _BYTE *a2)
{
  char v3; // bl

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a2 + 32, 0);
  v3 = a2[93];
  a2[92] = 0;
  ExReleasePushLockExclusiveEx(a2 + 32, 0);
  KeLeaveCriticalRegion();
  if ( v3 )
    ObfDereferenceObject(a2);
}

```

## disassembly

```asm
0x14000c1c0  mov     [rsp+arg_0], rbx
0x14000c1c5  mov     [rsp+arg_8], rsi
0x14000c1ca  push    rdi
0x14000c1cb  sub     rsp, 20h
0x14000c1cf  mov     rsi, rdx
0x14000c1d2  call    cs:__imp_KeEnterCriticalRegion
0x14000c1d9  nop     dword ptr [rax+rax+00h]
0x14000c1de  xor     edx, edx
0x14000c1e0  lea     rcx, [rsi+20h]
0x14000c1e4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c1eb  nop     dword ptr [rax+rax+00h]
0x14000c1f0  mov     bl, [rsi+5Dh]
0x14000c1f3  lea     rcx, [rsi+20h]
0x14000c1f7  xor     edx, edx
0x14000c1f9  mov     byte ptr [rsi+5Ch], 0
0x14000c1fd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c204  nop     dword ptr [rax+rax+00h]
0x14000c209  call    cs:__imp_KeLeaveCriticalRegion
0x14000c210  nop     dword ptr [rax+rax+00h]
0x14000c215  test    bl, bl
0x14000c217  jz      short loc_14000C228
0x14000c219  mov     rcx, rsi; Object
0x14000c21c  call    cs:__imp_ObfDereferenceObject
0x14000c223  nop     dword ptr [rax+rax+00h]
0x14000c228  mov     rbx, [rsp+28h+arg_0]
0x14000c22d  mov     rsi, [rsp+28h+arg_8]
0x14000c232  add     rsp, 20h
0x14000c236  pop     rdi
0x14000c237  retn
```
