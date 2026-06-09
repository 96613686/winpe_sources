# ProtoOpenWanAdapterLegacy

- ea: `0x14000f9c0`
- end: `0x14000fb2a`
- name: `ProtoOpenWanAdapterLegacy`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f2d0`

## callees

- `0x14000a290`
- `0x14000cac8`
- `0x14000f9c0`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14000facf`
- `ntoskrnl!KeClearEvent` at `0x14000facf`
- `ntoskrnl!KeInitializeEvent` at `0x14000fa34`
- `ntoskrnl!KeInitializeEvent` at `0x14000fa34`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fab7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fab7`
- `NDIS!NdisOpenAdapter` at `0x14000fa8c`
- `NDIS!NdisOpenAdapter` at `0x14000fa8c`

## pseudocode

```c
__int64 __fastcall ProtoOpenWanAdapterLegacy(__int64 a1)
{
  unsigned int v2; // edx
  unsigned int v4; // [rsp+90h] [rbp+28h] BYREF
  int v5; // [rsp+98h] [rbp+30h] BYREF
  _DWORD v6[2]; // [rsp+A0h] [rbp+38h] BYREF
  int v7; // [rsp+A8h] [rbp+40h] BYREF

  v4 = 0;
  v7 = 0;
  v5 = 0;
  v6[0] = 3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_S(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_714410adb39534c9cec6a41078899c0f_Traceguids,
      *(_QWORD *)(a1 + 72));
  }
  KeInitializeEvent((PRKEVENT)(a1 + 136), NotificationEvent, 0);
  NdisOpenAdapter(&v4, &v7, a1 + 56, &v5, v6, 1, qword_14001E2E8, a1, a1 + 64, 0, 0);
  v2 = v4;
  if ( v4 == 259 )
  {
    KeWaitForSingleObject((PVOID)(a1 + 136), Executive, 0, 1u, 0);
    v4 = *(_DWORD *)(a1 + 160);
    KeClearEvent((PRKEVENT)(a1 + 136));
    v2 = v4;
  }
  if ( !v2 )
    *(_DWORD *)(a1 + 120) = v6[v5];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_714410adb39534c9cec6a41078899c0f_Traceguids);
    return v4;
  }
  return v2;
}

```

## disassembly

```asm
0x14000f9c0  push    rbp
0x14000f9c2  push    rbx
0x14000f9c3  push    rdi
0x14000f9c4  push    r14
0x14000f9c6  mov     rbp, rsp
0x14000f9c9  sub     rsp, 68h
0x14000f9cd  mov     rbx, rcx
0x14000f9d0  mov     [rbp+arg_0], 0
0x14000f9d7  mov     [rbp+arg_18], 0
0x14000f9de  mov     [rbp+arg_8], 0
0x14000f9e5  mov     [rbp+arg_10], 3
0x14000f9ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f9f3  lea     r14, WPP_GLOBAL_Control
0x14000f9fa  cmp     rcx, r14
0x14000f9fd  jz      short loc_14000FA25
0x14000f9ff  mov     eax, [rcx+2Ch]
0x14000fa02  test    al, 4
0x14000fa04  jz      short loc_14000FA25
0x14000fa06  cmp     byte ptr [rcx+29h], 5
0x14000fa0a  jb      short loc_14000FA25
0x14000fa0c  mov     r9, [rbx+48h]
0x14000fa10  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000fa17  mov     rcx, [rcx+18h]
0x14000fa1b  mov     edx, 0Ah
0x14000fa20  call    WPP_SF_S
0x14000fa25  lea     rdi, [rbx+88h]
0x14000fa2c  xor     r8d, r8d; State
0x14000fa2f  mov     rcx, rdi; Event
0x14000fa32  xor     edx, edx; Type
0x14000fa34  call    cs:__imp_KeInitializeEvent
0x14000fa3b  nop     dword ptr [rax+rax+00h]
0x14000fa40  mov     [rsp+68h+var_18], 0
0x14000fa49  lea     rax, [rbx+40h]
0x14000fa4d  mov     [rsp+68h+var_20], 0
0x14000fa55  lea     r8, [rbx+38h]
0x14000fa59  mov     [rsp+68h+var_28], rax
0x14000fa5e  lea     r9, [rbp+arg_8]
0x14000fa62  mov     rax, cs:qword_14001E2E8
0x14000fa69  lea     rdx, [rbp+arg_18]
0x14000fa6d  mov     [rsp+68h+var_30], rbx
0x14000fa72  lea     rcx, [rbp+arg_0]
0x14000fa76  mov     [rsp+68h+var_38], rax
0x14000fa7b  lea     rax, [rbp+arg_10]
0x14000fa7f  mov     [rsp+68h+var_40], 1
0x14000fa87  mov     [rsp+68h+Timeout], rax
0x14000fa8c  call    cs:__imp_NdisOpenAdapter
0x14000fa93  nop     dword ptr [rax+rax+00h]
0x14000fa98  mov     edx, [rbp+arg_0]
0x14000fa9b  cmp     edx, 103h
0x14000faa1  jnz     short loc_14000FADE
0x14000faa3  mov     r9b, 1; Alertable
0x14000faa6  mov     [rsp+68h+Timeout], 0; Timeout
0x14000faaf  xor     r8d, r8d; WaitMode
0x14000fab2  xor     edx, edx; WaitReason
0x14000fab4  mov     rcx, rdi; Object
0x14000fab7  call    cs:__imp_KeWaitForSingleObject
0x14000fabe  nop     dword ptr [rax+rax+00h]
0x14000fac3  mov     eax, [rbx+0A0h]
0x14000fac9  mov     rcx, rdi; Event
0x14000facc  mov     [rbp+arg_0], eax
0x14000facf  call    cs:__imp_KeClearEvent
0x14000fad6  nop     dword ptr [rax+rax+00h]
0x14000fadb  mov     edx, [rbp+arg_0]
0x14000fade  test    edx, edx
0x14000fae0  jnz     short loc_14000FAEC
0x14000fae2  mov     eax, [rbp+arg_8]
0x14000fae5  mov     ecx, [rbp+rax*4+arg_10]
0x14000fae9  mov     [rbx+78h], ecx
0x14000faec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000faf3  cmp     rcx, r14
0x14000faf6  jz      short loc_14000FB1D
0x14000faf8  mov     eax, [rcx+2Ch]
0x14000fafb  test    al, 4
0x14000fafd  jz      short loc_14000FB1D
0x14000faff  cmp     byte ptr [rcx+29h], 5
0x14000fb03  jb      short loc_14000FB1D
0x14000fb05  mov     rcx, [rcx+18h]
0x14000fb09  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000fb10  mov     edx, 0Bh
0x14000fb15  call    WPP_SF_
0x14000fb1a  mov     edx, [rbp+arg_0]
0x14000fb1d  mov     eax, edx
0x14000fb1f  add     rsp, 68h
0x14000fb23  pop     r14
0x14000fb25  pop     rdi
0x14000fb26  pop     rbx
0x14000fb27  pop     rbp
0x14000fb28  retn
```
