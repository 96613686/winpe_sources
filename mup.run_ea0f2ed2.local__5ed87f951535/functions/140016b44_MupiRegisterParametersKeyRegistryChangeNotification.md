# MupiRegisterParametersKeyRegistryChangeNotification

- ea: `0x140016b44`
- end: `0x140016be9`
- name: `MupiRegisterParametersKeyRegistryChangeNotification`
- size: `165`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400045d0`
- `0x1400046c0`
- `0x1400048f0`

## callees

- `0x140002e74`
- `0x140016b44`

## import_xrefs

- `ntoskrnl!ZwNotifyChangeKey` at `0x140016b9a`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140016b9a`

## pseudocode

```c
__int64 __fastcall MupiRegisterParametersKeyRegistryChangeNotification(__int64 a1)
{
  NTSTATUS v1; // ebx

  *(_QWORD *)(a1 + 48) = MupRegistryParametersKeyChangeNotification;
  *(_QWORD *)(a1 + 56) = a1;
  *(_QWORD *)(a1 + 32) = 0;
  v1 = ZwNotifyChangeKey(
         *(HANDLE *)(a1 + 24),
         0,
         (PIO_APC_ROUTINE)(a1 + 32),
         (PVOID)1,
         (PIO_STATUS_BLOCK)(a1 + 64),
         4u,
         0,
         0,
         0,
         1u);
  if ( v1 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids, (unsigned int)v1);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140016b44  push    rbx
0x140016b46  sub     rsp, 50h
0x140016b4a  lea     r8, [rcx+20h]; ApcRoutine
0x140016b4e  mov     [rsp+58h+Asynchronous], 1; Asynchronous
0x140016b53  mov     [rsp+58h+BufferSize], 0; BufferSize
0x140016b5b  lea     rax, MupRegistryParametersKeyChangeNotification
0x140016b62  mov     [r8+10h], rax
0x140016b66  xor     edx, edx; Event
0x140016b68  mov     [rsp+58h+Buffer], 0; Buffer
0x140016b71  lea     rax, [rcx+40h]
0x140016b75  mov     [r8+18h], rcx
0x140016b79  mov     qword ptr [r8], 0
0x140016b80  mov     rcx, [rcx+18h]; KeyHandle
0x140016b84  lea     r9d, [rdx+1]; ApcContext
0x140016b88  mov     [rsp+58h+WatchTree], 0; WatchTree
0x140016b8d  mov     [rsp+58h+CompletionFilter], 4; CompletionFilter
0x140016b95  mov     [rsp+58h+IoStatusBlock], rax; IoStatusBlock
0x140016b9a  call    cs:__imp_ZwNotifyChangeKey
0x140016ba1  nop     dword ptr [rax+rax+00h]
0x140016ba6  mov     ebx, eax
0x140016ba8  test    eax, eax
0x140016baa  jns     short loc_140016BE0
0x140016bac  mov     rcx, cs:WPP_GLOBAL_Control
0x140016bb3  lea     rax, WPP_GLOBAL_Control
0x140016bba  cmp     rcx, rax
0x140016bbd  jz      short loc_140016BE0
0x140016bbf  test    dword ptr [rcx+2Ch], 4000000h
0x140016bc6  jz      short loc_140016BE0
0x140016bc8  mov     rcx, [rcx+18h]
0x140016bcc  lea     r8, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x140016bd3  mov     edx, 17h
0x140016bd8  mov     r9d, ebx
0x140016bdb  call    WPP_SF_d
0x140016be0  mov     eax, ebx
0x140016be2  add     rsp, 50h
0x140016be6  pop     rbx
0x140016be7  retn
```
