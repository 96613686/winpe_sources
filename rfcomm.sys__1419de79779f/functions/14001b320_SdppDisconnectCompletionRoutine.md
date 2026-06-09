# SdppDisconnectCompletionRoutine

- ea: `0x14001b320`
- end: `0x14001b412`
- name: `SdppDisconnectCompletionRoutine`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14001b320`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001b3cd`
- `ntoskrnl!IoFreeIrp` at `0x14001b3cd`
- `ntoskrnl!ExFreePool` at `0x14001b3b9`
- `ntoskrnl!ExFreePool` at `0x14001b3b9`

## pseudocode

```c
__int64 __fastcall SdppDisconnectCompletionRoutine(__int64 a1, IRP *a2, _QWORD *a3)
{
  unsigned int v5; // esi
  void (__fastcall *v6)(_QWORD, _QWORD); // rax
  int v7; // edx
  int Status; // [rsp+28h] [rbp-30h]

  v5 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      56,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  if ( a2 && a2->IoStatus.Status < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Status = a2->IoStatus.Status;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        57,
        (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
        Status);
    }
    v5 = a2->IoStatus.Status;
  }
  v6 = (void (__fastcall *)(_QWORD, _QWORD))a3[4];
  if ( v6 )
    v6(a3[3], v5);
  ExFreePool(a3);
  if ( a2 )
    IoFreeIrp(a2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      3,
      58,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001b320  push    rbx
0x14001b322  push    rbp
0x14001b323  push    rsi
0x14001b324  push    rdi
0x14001b325  push    r14
0x14001b327  sub     rsp, 30h
0x14001b32b  mov     rdi, r8
0x14001b32e  mov     rbx, rdx
0x14001b331  xor     esi, esi
0x14001b333  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001b33a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001b341  lea     r14, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001b348  jz      short loc_14001B367
0x14001b34a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b351  lea     r9d, [rsi+38h]
0x14001b355  lea     r8d, [rsi+3]
0x14001b359  mov     [rsp+58h+var_38], r14
0x14001b35e  mov     rcx, [rcx+40h]
0x14001b362  call    WPP_RECORDER_SF_
0x14001b367  test    rbx, rbx
0x14001b36a  jz      short loc_14001B3A2
0x14001b36c  mov     eax, [rbx+30h]
0x14001b36f  test    eax, eax
0x14001b371  jns     short loc_14001B3A2
0x14001b373  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001b37a  jz      short loc_14001B39F
0x14001b37c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b383  mov     r9d, 39h ; '9'
0x14001b389  mov     [rsp+58h+var_30], eax
0x14001b38d  mov     [rsp+58h+var_38], r14
0x14001b392  mov     rcx, [rcx+40h]
0x14001b396  lea     r8d, [r9-38h]
0x14001b39a  call    WPP_RECORDER_SF_d
0x14001b39f  mov     esi, [rbx+30h]
0x14001b3a2  mov     rax, [rdi+20h]
0x14001b3a6  test    rax, rax
0x14001b3a9  jz      short loc_14001B3B6
0x14001b3ab  mov     rcx, [rdi+18h]
0x14001b3af  mov     edx, esi
0x14001b3b1  call    _guard_dispatch_icall
0x14001b3b6  mov     rcx, rdi; P
0x14001b3b9  call    cs:__imp_ExFreePool
0x14001b3c0  nop     dword ptr [rax+rax+00h]
0x14001b3c5  test    rbx, rbx
0x14001b3c8  jz      short loc_14001B3D9
0x14001b3ca  mov     rcx, rbx; Irp
0x14001b3cd  call    cs:__imp_IoFreeIrp
0x14001b3d4  nop     dword ptr [rax+rax+00h]
0x14001b3d9  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001b3e0  jz      short loc_14001B401
0x14001b3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b3e9  mov     r9d, 3Ah ; ':'
0x14001b3ef  mov     [rsp+58h+var_38], r14
0x14001b3f4  mov     rcx, [rcx+40h]
0x14001b3f8  lea     r8d, [r9-37h]
0x14001b3fc  call    WPP_RECORDER_SF_
0x14001b401  mov     eax, 0C0000016h
0x14001b406  add     rsp, 30h
0x14001b40a  pop     r14
0x14001b40c  pop     rdi
0x14001b40d  pop     rsi
0x14001b40e  pop     rbp
0x14001b40f  pop     rbx
0x14001b410  retn
```
