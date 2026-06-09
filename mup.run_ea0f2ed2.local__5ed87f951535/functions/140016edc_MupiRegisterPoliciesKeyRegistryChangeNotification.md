# MupiRegisterPoliciesKeyRegistryChangeNotification

- ea: `0x140016edc`
- end: `0x140016f81`
- name: `MupiRegisterPoliciesKeyRegistryChangeNotification`
- size: `165`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004b40`
- `0x140004c30`
- `0x140004e60`

## callees

- `0x140002e74`
- `0x140016edc`

## import_xrefs

- `ntoskrnl!ZwNotifyChangeKey` at `0x140016f32`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140016f32`

## pseudocode

```c
__int64 __fastcall MupiRegisterPoliciesKeyRegistryChangeNotification(__int64 a1)
{
  NTSTATUS v1; // ebx

  *(_QWORD *)(a1 + 48) = MupRegistryPoliciesKeyChangeNotification;
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_4108bb1397623747c94676978a28aeb5_Traceguids, (unsigned int)v1);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140016edc  push    rbx
0x140016ede  sub     rsp, 50h
0x140016ee2  lea     r8, [rcx+20h]; ApcRoutine
0x140016ee6  mov     [rsp+58h+Asynchronous], 1; Asynchronous
0x140016eeb  mov     [rsp+58h+BufferSize], 0; BufferSize
0x140016ef3  lea     rax, MupRegistryPoliciesKeyChangeNotification
0x140016efa  mov     [r8+10h], rax
0x140016efe  xor     edx, edx; Event
0x140016f00  mov     [rsp+58h+Buffer], 0; Buffer
0x140016f09  lea     rax, [rcx+40h]
0x140016f0d  mov     [r8+18h], rcx
0x140016f11  mov     qword ptr [r8], 0
0x140016f18  mov     rcx, [rcx+18h]; KeyHandle
0x140016f1c  lea     r9d, [rdx+1]; ApcContext
0x140016f20  mov     [rsp+58h+WatchTree], 0; WatchTree
0x140016f25  mov     [rsp+58h+CompletionFilter], 4; CompletionFilter
0x140016f2d  mov     [rsp+58h+IoStatusBlock], rax; IoStatusBlock
0x140016f32  call    cs:__imp_ZwNotifyChangeKey
0x140016f39  nop     dword ptr [rax+rax+00h]
0x140016f3e  mov     ebx, eax
0x140016f40  test    eax, eax
0x140016f42  jns     short loc_140016F78
0x140016f44  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f4b  lea     rax, WPP_GLOBAL_Control
0x140016f52  cmp     rcx, rax
0x140016f55  jz      short loc_140016F78
0x140016f57  test    dword ptr [rcx+2Ch], 4000000h
0x140016f5e  jz      short loc_140016F78
0x140016f60  mov     rcx, [rcx+18h]
0x140016f64  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140016f6b  mov     edx, 17h
0x140016f70  mov     r9d, ebx
0x140016f73  call    WPP_SF_d
0x140016f78  mov     eax, ebx
0x140016f7a  add     rsp, 50h
0x140016f7e  pop     rbx
0x140016f7f  retn
```
