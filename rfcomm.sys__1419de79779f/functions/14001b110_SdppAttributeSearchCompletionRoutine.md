# SdppAttributeSearchCompletionRoutine

- ea: `0x14001b110`
- end: `0x14001b21a`
- name: `SdppAttributeSearchCompletionRoutine`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14001b110`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001b1d5`
- `ntoskrnl!IoFreeIrp` at `0x14001b1d5`
- `ntoskrnl!ExFreePool` at `0x14001b1c1`
- `ntoskrnl!ExFreePool` at `0x14001b1c1`

## pseudocode

```c
__int64 __fastcall SdppAttributeSearchCompletionRoutine(__int64 a1, IRP *a2, __int64 a3)
{
  unsigned int Status; // esi
  __int64 v6; // r8
  unsigned int v7; // eax
  int v8; // edx
  int v10; // [rsp+28h] [rbp-30h]

  Status = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      68,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  if ( a2 )
  {
    if ( a2->IoStatus.Status < 0 )
    {
      Status = a2->IoStatus.Status;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v10 = a2->IoStatus.Status;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          69,
          (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
          v10);
      }
    }
  }
  v6 = *(unsigned int *)(a3 + 36);
  if ( a2 )
  {
    if ( a2->IoStatus.Status >= 0 )
    {
      v7 = *(_DWORD *)(a3 + 32);
      if ( v7 < (unsigned int)v6 )
        v6 = v7;
    }
  }
  (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(a3 + 24))(*(_QWORD *)(a3 + 16), a3 + 44, v6, Status);
  ExFreePool((PVOID)a3);
  if ( a2 )
    IoFreeIrp(a2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      3,
      70,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001b110  push    rbx
0x14001b112  push    rbp
0x14001b113  push    rsi
0x14001b114  push    rdi
0x14001b115  push    r14
0x14001b117  sub     rsp, 30h
0x14001b11b  mov     rdi, r8
0x14001b11e  mov     rbx, rdx
0x14001b121  xor     esi, esi
0x14001b123  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001b12a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001b131  lea     r14, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001b138  jz      short loc_14001B157
0x14001b13a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b141  lea     r9d, [rsi+44h]
0x14001b145  lea     r8d, [rsi+3]
0x14001b149  mov     [rsp+58h+var_38], r14
0x14001b14e  mov     rcx, [rcx+40h]
0x14001b152  call    WPP_RECORDER_SF_
0x14001b157  test    rbx, rbx
0x14001b15a  jz      short loc_14001B191
0x14001b15c  mov     eax, [rbx+30h]
0x14001b15f  test    eax, eax
0x14001b161  jns     short loc_14001B191
0x14001b163  mov     esi, eax
0x14001b165  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001b16c  jz      short loc_14001B191
0x14001b16e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b175  mov     r9d, 45h ; 'E'
0x14001b17b  mov     [rsp+58h+var_30], eax
0x14001b17f  mov     [rsp+58h+var_38], r14
0x14001b184  mov     rcx, [rcx+40h]
0x14001b188  lea     r8d, [r9-44h]
0x14001b18c  call    WPP_RECORDER_SF_d
0x14001b191  mov     r8d, [rdi+24h]
0x14001b195  test    rbx, rbx
0x14001b198  jz      short loc_14001B1AA
0x14001b19a  cmp     dword ptr [rbx+30h], 0
0x14001b19e  jl      short loc_14001B1AA
0x14001b1a0  mov     eax, [rdi+20h]
0x14001b1a3  cmp     eax, r8d
0x14001b1a6  cmovb   r8d, eax
0x14001b1aa  mov     rax, [rdi+18h]
0x14001b1ae  lea     rdx, [rdi+2Ch]
0x14001b1b2  mov     rcx, [rdi+10h]
0x14001b1b6  mov     r9d, esi
0x14001b1b9  call    _guard_dispatch_icall
0x14001b1be  mov     rcx, rdi; P
0x14001b1c1  call    cs:__imp_ExFreePool
0x14001b1c8  nop     dword ptr [rax+rax+00h]
0x14001b1cd  test    rbx, rbx
0x14001b1d0  jz      short loc_14001B1E1
0x14001b1d2  mov     rcx, rbx; Irp
0x14001b1d5  call    cs:__imp_IoFreeIrp
0x14001b1dc  nop     dword ptr [rax+rax+00h]
0x14001b1e1  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001b1e8  jz      short loc_14001B209
0x14001b1ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b1f1  mov     r9d, 46h ; 'F'
0x14001b1f7  mov     [rsp+58h+var_38], r14
0x14001b1fc  mov     rcx, [rcx+40h]
0x14001b200  lea     r8d, [r9-43h]
0x14001b204  call    WPP_RECORDER_SF_
0x14001b209  mov     eax, 0C0000016h
0x14001b20e  add     rsp, 30h
0x14001b212  pop     r14
0x14001b214  pop     rdi
0x14001b215  pop     rsi
0x14001b216  pop     rbp
0x14001b217  pop     rbx
0x14001b218  retn
```
