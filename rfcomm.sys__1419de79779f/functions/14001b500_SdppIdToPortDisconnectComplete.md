# SdppIdToPortDisconnectComplete

- ea: `0x14001b500`
- end: `0x14001b59c`
- name: `SdppIdToPortDisconnectComplete`
- size: `156`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x14001b500`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x14001b55d`
- `ntoskrnl!ExFreePool` at `0x14001b55d`

## pseudocode

```c
void __fastcall SdppIdToPortDisconnectComplete(_QWORD *P, unsigned int a2)
{
  int v4; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      31,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))*P)(a2, P[1], P[5], 0);
  ExFreePool(P);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      3,
      32,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
}

```

## disassembly

```asm
0x14001b500  push    rbx
0x14001b502  push    rbp
0x14001b503  push    rdi
0x14001b504  push    r14
0x14001b506  sub     rsp, 38h
0x14001b50a  mov     edi, edx
0x14001b50c  mov     rbx, rcx
0x14001b50f  lea     r14, WPP_RECORDER_INITIALIZED
0x14001b516  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001b51d  lea     rbp, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001b524  jz      short loc_14001B545
0x14001b526  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b52d  mov     r9d, 1Fh
0x14001b533  mov     [rsp+58h+var_38], rbp
0x14001b538  mov     rcx, [rcx+40h]
0x14001b53c  lea     r8d, [r9-1Ch]
0x14001b540  call    WPP_RECORDER_SF_
0x14001b545  mov     rax, [rbx]
0x14001b548  xor     r9d, r9d
0x14001b54b  mov     r8, [rbx+28h]
0x14001b54f  mov     ecx, edi
0x14001b551  mov     rdx, [rbx+8]
0x14001b555  call    _guard_dispatch_icall
0x14001b55a  mov     rcx, rbx; P
0x14001b55d  call    cs:__imp_ExFreePool
0x14001b564  nop     dword ptr [rax+rax+00h]
0x14001b569  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001b570  jz      short loc_14001B591
0x14001b572  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b579  mov     r9d, 20h ; ' '
0x14001b57f  mov     [rsp+58h+var_38], rbp
0x14001b584  mov     rcx, [rcx+40h]
0x14001b588  lea     r8d, [r9-1Dh]
0x14001b58c  call    WPP_RECORDER_SF_
0x14001b591  add     rsp, 38h
0x14001b595  pop     r14
0x14001b597  pop     rdi
0x14001b598  pop     rbp
0x14001b599  pop     rbx
0x14001b59a  retn
```
