# SdppConnectCompletionRoutine

- ea: `0x14001b220`
- end: `0x14001b311`
- name: `SdppConnectCompletionRoutine`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14001b220`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001b2cc`
- `ntoskrnl!IoFreeIrp` at `0x14001b2cc`
- `ntoskrnl!ExFreePool` at `0x14001b2b8`
- `ntoskrnl!ExFreePool` at `0x14001b2b8`

## pseudocode

```c
__int64 __fastcall SdppConnectCompletionRoutine(__int64 a1, IRP *a2, __int64 a3)
{
  unsigned int Status; // esi
  int v6; // edx
  int v8; // [rsp+28h] [rbp-30h]

  Status = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      51,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  if ( a2 )
  {
    if ( a2->IoStatus.Status < 0 )
    {
      Status = a2->IoStatus.Status;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v8 = a2->IoStatus.Status;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          52,
          (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
          v8);
      }
    }
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(a3 + 32))(*(_QWORD *)(a3 + 24), *(_QWORD *)(a3 + 12), Status);
  ExFreePool((PVOID)a3);
  if ( a2 )
    IoFreeIrp(a2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      3,
      53,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001b220  push    rbx
0x14001b222  push    rbp
0x14001b223  push    rsi
0x14001b224  push    rdi
0x14001b225  push    r14
0x14001b227  sub     rsp, 30h
0x14001b22b  mov     rdi, r8
0x14001b22e  mov     rbx, rdx
0x14001b231  xor     esi, esi
0x14001b233  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001b23a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001b241  lea     r14, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001b248  jz      short loc_14001B267
0x14001b24a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b251  lea     r9d, [rsi+33h]
0x14001b255  lea     r8d, [rsi+3]
0x14001b259  mov     [rsp+58h+var_38], r14
0x14001b25e  mov     rcx, [rcx+40h]
0x14001b262  call    WPP_RECORDER_SF_
0x14001b267  test    rbx, rbx
0x14001b26a  jz      short loc_14001B2A1
0x14001b26c  mov     eax, [rbx+30h]
0x14001b26f  test    eax, eax
0x14001b271  jns     short loc_14001B2A1
0x14001b273  mov     esi, eax
0x14001b275  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001b27c  jz      short loc_14001B2A1
0x14001b27e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b285  mov     r9d, 34h ; '4'
0x14001b28b  mov     [rsp+58h+var_30], eax
0x14001b28f  mov     [rsp+58h+var_38], r14
0x14001b294  mov     rcx, [rcx+40h]
0x14001b298  lea     r8d, [r9-33h]
0x14001b29c  call    WPP_RECORDER_SF_d
0x14001b2a1  mov     rax, [rdi+20h]
0x14001b2a5  mov     r8d, esi
0x14001b2a8  mov     rdx, [rdi+0Ch]
0x14001b2ac  mov     rcx, [rdi+18h]
0x14001b2b0  call    _guard_dispatch_icall
0x14001b2b5  mov     rcx, rdi; P
0x14001b2b8  call    cs:__imp_ExFreePool
0x14001b2bf  nop     dword ptr [rax+rax+00h]
0x14001b2c4  test    rbx, rbx
0x14001b2c7  jz      short loc_14001B2D8
0x14001b2c9  mov     rcx, rbx; Irp
0x14001b2cc  call    cs:__imp_IoFreeIrp
0x14001b2d3  nop     dword ptr [rax+rax+00h]
0x14001b2d8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001b2df  jz      short loc_14001B300
0x14001b2e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b2e8  mov     r9d, 35h ; '5'
0x14001b2ee  mov     [rsp+58h+var_38], r14
0x14001b2f3  mov     rcx, [rcx+40h]
0x14001b2f7  lea     r8d, [r9-32h]
0x14001b2fb  call    WPP_RECORDER_SF_
0x14001b300  mov     eax, 0C0000016h
0x14001b305  add     rsp, 30h
0x14001b309  pop     r14
0x14001b30b  pop     rdi
0x14001b30c  pop     rsi
0x14001b30d  pop     rbp
0x14001b30e  pop     rbx
0x14001b30f  retn
```
