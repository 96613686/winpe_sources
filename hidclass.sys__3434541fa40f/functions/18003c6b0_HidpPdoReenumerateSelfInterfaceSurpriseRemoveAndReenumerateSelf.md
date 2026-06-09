# HidpPdoReenumerateSelfInterfaceSurpriseRemoveAndReenumerateSelf

- ea: `0x18003c6b0`
- end: `0x18003c7a5`
- name: `HidpPdoReenumerateSelfInterfaceSurpriseRemoveAndReenumerateSelf`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009a78`
- `0x18003c6b0`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceRelations` at `0x18003c78d`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x18003c78d`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18003c77c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18003c77c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x18003c765`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x18003c765`

## pseudocode

```c
void __fastcall HidpPdoReenumerateSelfInterfaceSurpriseRemoveAndReenumerateSelf(__int64 a1)
{
  struct _FAST_MUTEX *v2; // rbx
  bool v3; // dl

  if ( a1 && *(_BYTE *)(a1 + 24) == 1 )
  {
    v2 = *(struct _FAST_MUTEX **)(a1 + 96);
    v3 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qdq(
        WPP_GLOBAL_Control->AttachedDevice,
        v3,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        v2[12].Event.Header.WaitListHead.Flink,
        3,
        2,
        10,
        (__int64)WPP_15c9e22b41b136b74da9fe0f3a565e27_Traceguids,
        (char)v2->Event.Header.WaitListHead.Flink,
        *(_DWORD *)(a1 + 40),
        *(_QWORD *)(a1 + 80));
    KeAcquireGuardedMutex(v2 + 36);
    *(_BYTE *)(a1 + 104) = 1;
    KeReleaseGuardedMutex(v2 + 36);
    IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)a1, BusRelations);
  }
}

```

## disassembly

```asm
0x18003c6b0  test    rcx, rcx
0x18003c6b3  jz      locret_18003C7A3
0x18003c6b9  mov     [rsp+arg_0], rbx
0x18003c6be  push    rdi
0x18003c6bf  sub     rsp, 60h
0x18003c6c3  cmp     byte ptr [rcx+18h], 1
0x18003c6c7  mov     rdi, rcx
0x18003c6ca  jnz     loc_18003C799
0x18003c6d0  mov     rbx, [rcx+60h]
0x18003c6d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c6db  lea     rax, WPP_GLOBAL_Control
0x18003c6e2  cmp     rcx, rax
0x18003c6e5  jz      short loc_18003C6F8
0x18003c6e7  mov     eax, [rcx+2Ch]
0x18003c6ea  test    al, 2
0x18003c6ec  jz      short loc_18003C6F8
0x18003c6ee  cmp     byte ptr [rcx+29h], 3
0x18003c6f2  jb      short loc_18003C6F8
0x18003c6f4  mov     dl, 1
0x18003c6f6  jmp     short loc_18003C6FA
0x18003c6f8  xor     dl, dl
0x18003c6fa  lea     rax, WPP_RECORDER_INITIALIZED
0x18003c701  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003c708  setnz   r8b
0x18003c70c  test    dl, dl
0x18003c70e  jnz     short loc_18003C715
0x18003c710  test    r8b, r8b
0x18003c713  jz      short loc_18003C75E
0x18003c715  mov     rax, [rdi+50h]
0x18003c719  mov     r9, [rbx+2C0h]
0x18003c720  mov     rcx, [rcx+18h]
0x18003c724  mov     [rsp+68h+var_18], rax
0x18003c729  mov     eax, [rdi+28h]
0x18003c72c  mov     [rsp+68h+var_20], eax
0x18003c730  mov     rax, [rbx+20h]
0x18003c734  mov     [rsp+68h+var_28], rax
0x18003c739  lea     rax, WPP_15c9e22b41b136b74da9fe0f3a565e27_Traceguids
0x18003c740  mov     [rsp+68h+var_30], rax
0x18003c745  mov     [rsp+68h+var_38], 0Ah
0x18003c74c  mov     [rsp+68h+var_40], 2
0x18003c754  mov     [rsp+68h+var_48], 3
0x18003c759  call    WPP_RECORDER_AND_TRACE_SF_qdq
0x18003c75e  lea     rcx, [rbx+7E0h]; Mutex
0x18003c765  call    cs:__imp_KeAcquireGuardedMutex
0x18003c76c  nop     dword ptr [rax+rax+00h]
0x18003c771  lea     rcx, [rbx+7E0h]; Mutex
0x18003c778  mov     byte ptr [rdi+68h], 1
0x18003c77c  call    cs:__imp_KeReleaseGuardedMutex
0x18003c783  nop     dword ptr [rax+rax+00h]
0x18003c788  mov     rcx, [rdi]; DeviceObject
0x18003c78b  xor     edx, edx; Type
0x18003c78d  call    cs:__imp_IoInvalidateDeviceRelations
0x18003c794  nop     dword ptr [rax+rax+00h]
0x18003c799  mov     rbx, [rsp+68h+arg_0]
0x18003c79e  add     rsp, 60h
0x18003c7a2  pop     rdi
0x18003c7a3  retn
```
