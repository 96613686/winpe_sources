# MupiRegisterParametersKeyRegistryChangeNotification

- ea: `0x140016b94`
- end: `0x140016c39`
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
- `0x140016b94`

## import_xrefs

- `ntoskrnl!ZwNotifyChangeKey` at `0x140016bea`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140016bea`

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
0x140016b94  push    rbx
0x140016b96  sub     rsp, 50h
0x140016b9a  lea     r8, [rcx+20h]; ApcRoutine
0x140016b9e  mov     [rsp+58h+Asynchronous], 1; Asynchronous
0x140016ba3  mov     [rsp+58h+BufferSize], 0; BufferSize
0x140016bab  lea     rax, MupRegistryParametersKeyChangeNotification
0x140016bb2  mov     [r8+10h], rax
0x140016bb6  xor     edx, edx; Event
0x140016bb8  mov     [rsp+58h+Buffer], 0; Buffer
0x140016bc1  lea     rax, [rcx+40h]
0x140016bc5  mov     [r8+18h], rcx
0x140016bc9  mov     qword ptr [r8], 0
0x140016bd0  mov     rcx, [rcx+18h]; KeyHandle
0x140016bd4  lea     r9d, [rdx+1]; ApcContext
0x140016bd8  mov     [rsp+58h+WatchTree], 0; WatchTree
0x140016bdd  mov     [rsp+58h+CompletionFilter], 4; CompletionFilter
0x140016be5  mov     [rsp+58h+IoStatusBlock], rax; IoStatusBlock
0x140016bea  call    cs:__imp_ZwNotifyChangeKey
0x140016bf1  nop     dword ptr [rax+rax+00h]
0x140016bf6  mov     ebx, eax
0x140016bf8  test    eax, eax
0x140016bfa  jns     short loc_140016C30
0x140016bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c03  lea     rax, WPP_GLOBAL_Control
0x140016c0a  cmp     rcx, rax
0x140016c0d  jz      short loc_140016C30
0x140016c0f  test    dword ptr [rcx+2Ch], 4000000h
0x140016c16  jz      short loc_140016C30
0x140016c18  mov     rcx, [rcx+18h]
0x140016c1c  lea     r8, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x140016c23  mov     edx, 17h
0x140016c28  mov     r9d, ebx
0x140016c2b  call    WPP_SF_d
0x140016c30  mov     eax, ebx
0x140016c32  add     rsp, 50h
0x140016c36  pop     rbx
0x140016c37  retn
```
