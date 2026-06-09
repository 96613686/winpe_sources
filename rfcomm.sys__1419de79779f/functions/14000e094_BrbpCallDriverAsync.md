# BrbpCallDriverAsync

- ea: `0x14000e094`
- end: `0x14000e295`
- name: `BrbpCallDriverAsync`
- size: `513`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d970`
- `0x14000dd28`
- `0x14000df68`
- `0x14000e4e0`
- `0x14000e700`
- `0x14000ecd0`

## callees

- `0x140004a68`
- `0x140004e58`
- `0x14000e094`
- `0x14001a2f8`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e1bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e1bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e1f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e1f8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e18e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e18e`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000e0d7`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000e0d7`
- `ntoskrnl!IofCallDriver` at `0x14000e23b`
- `ntoskrnl!IofCallDriver` at `0x14000e23b`

## string_xrefs

- `0x14000e0c3`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`

## pseudocode

```c
void __fastcall BrbpCallDriverAsync(
        __int64 a1,
        _DWORD *a2,
        void (__fastcall *a3)(__int64, _DWORD *, __int64),
        __int64 a4,
        __int64 a5)
{
  NTSTATUS v9; // eax
  int v10; // r8d
  IRP *v11; // rbx
  int v12; // edx
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // edx
  _QWORD *v16; // rdi
  __int64 v17; // rax
  _QWORD *v18; // rdx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v20; // rax
  _QWORD *v21; // [rsp+70h] [rbp+8h] BYREF

  v21 = 0;
  v9 = IoAcquireRemoveLockEx(
         (PIO_REMOVE_LOCK)(a1 + 40),
         a2,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c",
         0x1C1u,
         0x20u);
  if ( v9 >= 0 )
  {
    v13 = *(_QWORD *)(a1 + 88);
    LOBYTE(v13) = *(_BYTE *)(v13 + 76);
    v14 = IrpAllocateWithContextEx(0, v13, v10, (unsigned int)&v21, 64);
    v11 = (IRP *)v14;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        3,
        25,
        (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids,
        (char)a2,
        v14);
    if ( v11 )
    {
      v16 = v21;
      v21[2] = a1;
      v16[3] = v11;
      v16[4] = a2;
      v16[5] = a4;
      v16[6] = a3;
      *(_BYTE *)(a1 + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 24));
      v17 = a5;
      v18 = *(_QWORD **)(a5 + 8);
      if ( *v18 != a5 )
        __fastfail(3u);
      *v16 = a5;
      v16[1] = v18;
      *v18 = v16;
      *(_QWORD *)(v17 + 8) = v16;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 24), *(_BYTE *)(a1 + 32));
      CurrentStackLocation = v11->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation[-1].MajorFunction = 15;
      CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)a2;
      CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4259843;
      v20 = v11->Tail.Overlay.CurrentStackLocation;
      v20[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&BrbpIrpCompletionRoutine;
      v20[-1].Context = v16;
      v20[-1].Control = -32;
      IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 88), v11);
    }
    else
    {
      a2[7] = -1073741670;
      a3(a1, a2, a4);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 40), a2, 0x20u);
    }
  }
  else
  {
    a2[7] = v9;
    LOBYTE(v11) = 0;
    ((void (__fastcall *)(__int64, _DWORD *, __int64, _QWORD))a3)(a1, a2, a4, (unsigned int)v9);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      3,
      26,
      (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids,
      (char)v11);
}

```

## disassembly

```asm
0x14000e094  mov     rax, rsp
0x14000e097  mov     [rax+10h], rbx
0x14000e09b  mov     [rax+18h], rbp
0x14000e09f  push    rsi
0x14000e0a0  push    rdi
0x14000e0a1  push    r13
0x14000e0a3  push    r14
0x14000e0a5  push    r15
0x14000e0a7  sub     rsp, 40h
0x14000e0ab  mov     r14, r9
0x14000e0ae  mov     qword ptr [rax+8], 0
0x14000e0b6  mov     r15, r8
0x14000e0b9  mov     dword ptr [rax-48h], 20h ; ' '
0x14000e0c0  mov     rsi, rcx
0x14000e0c3  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000e0ca  mov     r9d, 1C1h; Line
0x14000e0d0  add     rcx, 28h ; '('; RemoveLock
0x14000e0d4  mov     rbp, rdx
0x14000e0d7  call    cs:__imp_IoAcquireRemoveLockEx
0x14000e0de  nop     dword ptr [rax+rax+00h]
0x14000e0e3  lea     r13, WPP_RECORDER_INITIALIZED
0x14000e0ea  test    eax, eax
0x14000e0ec  jns     short loc_14000E10C
0x14000e0ee  mov     [rbp+1Ch], eax
0x14000e0f1  mov     r9d, eax
0x14000e0f4  mov     rax, r15
0x14000e0f7  xor     ebx, ebx
0x14000e0f9  mov     r8, r14
0x14000e0fc  mov     rdx, rbp
0x14000e0ff  mov     rcx, rsi
0x14000e102  call    _guard_dispatch_icall
0x14000e107  jmp     loc_14000E247
0x14000e10c  mov     rdx, [rsi+58h]
0x14000e110  lea     r9, [rsp+68h+arg_0]
0x14000e115  xor     ecx, ecx
0x14000e117  mov     dword ptr [rsp+68h+var_48], 40h ; '@'
0x14000e11f  mov     dl, [rdx+4Ch]
0x14000e122  call    IrpAllocateWithContextEx
0x14000e127  mov     rbx, rax
0x14000e12a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000e131  jz      short loc_14000E163
0x14000e133  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e13a  mov     r9d, 19h
0x14000e140  mov     [rsp+68h+var_38], rax
0x14000e145  lea     rax, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000e14c  mov     [rsp+68h+var_40], rbp
0x14000e151  mov     [rsp+68h+var_48], rax
0x14000e156  mov     rcx, [rcx+40h]
0x14000e15a  lea     r8d, [r9-16h]
0x14000e15e  call    WPP_RECORDER_SF_qq
0x14000e163  test    rbx, rbx
0x14000e166  jnz     short loc_14000E19F
0x14000e168  mov     r9d, 0C000009Ah
0x14000e16e  mov     r8, r14
0x14000e171  mov     rdx, rbp
0x14000e174  mov     [rbp+1Ch], r9d
0x14000e178  mov     rcx, rsi
0x14000e17b  mov     rax, r15
0x14000e17e  call    _guard_dispatch_icall
0x14000e183  lea     r8d, [rbx+20h]; RemlockSize
0x14000e187  mov     rdx, rbp; Tag
0x14000e18a  lea     rcx, [rsi+28h]; RemoveLock
0x14000e18e  call    cs:__imp_IoReleaseRemoveLockEx
0x14000e195  nop     dword ptr [rax+rax+00h]
0x14000e19a  jmp     loc_14000E247
0x14000e19f  mov     rdi, [rsp+68h+arg_0]
0x14000e1a4  lea     rcx, [rsi+18h]; SpinLock
0x14000e1a8  mov     [rdi+10h], rsi
0x14000e1ac  mov     [rdi+18h], rbx
0x14000e1b0  mov     [rdi+20h], rbp
0x14000e1b4  mov     [rdi+28h], r14
0x14000e1b8  mov     [rdi+30h], r15
0x14000e1bc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e1c3  nop     dword ptr [rax+rax+00h]
0x14000e1c8  mov     [rsi+20h], al
0x14000e1cb  mov     rax, [rsp+68h+arg_20]
0x14000e1d3  mov     rdx, [rax+8]
0x14000e1d7  cmp     [rdx], rax
0x14000e1da  jz      short loc_14000E1E3
0x14000e1dc  mov     ecx, 3
0x14000e1e1  int     29h; Win8: RtlFailFast(ecx)
0x14000e1e3  mov     [rdi], rax
0x14000e1e6  lea     rcx, [rsi+18h]; SpinLock
0x14000e1ea  mov     [rdi+8], rdx
0x14000e1ee  mov     [rdx], rdi
0x14000e1f1  mov     [rax+8], rdi
0x14000e1f5  mov     dl, [rsi+20h]; NewIrql
0x14000e1f8  call    cs:__imp_KeReleaseSpinLock
0x14000e1ff  nop     dword ptr [rax+rax+00h]
0x14000e204  mov     rax, [rbx+0B8h]
0x14000e20b  lea     rcx, BrbpIrpCompletionRoutine
0x14000e212  mov     rdx, rbx; Irp
0x14000e215  mov     byte ptr [rax-48h], 0Fh
0x14000e219  mov     [rax-40h], rbp
0x14000e21d  mov     dword ptr [rax-30h], 410003h
0x14000e224  mov     rax, [rbx+0B8h]
0x14000e22b  mov     [rax-10h], rcx
0x14000e22f  mov     [rax-8], rdi
0x14000e233  mov     byte ptr [rax-45h], 0E0h
0x14000e237  mov     rcx, [rsi+58h]; DeviceObject
0x14000e23b  call    cs:__imp_IofCallDriver
0x14000e242  nop     dword ptr [rax+rax+00h]
0x14000e247  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000e24e  jz      short loc_14000E27B
0x14000e250  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e257  lea     rax, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000e25e  mov     r9d, 1Ah
0x14000e264  mov     [rsp+68h+var_40], rbx
0x14000e269  mov     [rsp+68h+var_48], rax
0x14000e26e  mov     rcx, [rcx+40h]
0x14000e272  lea     r8d, [r9-17h]
0x14000e276  call    WPP_RECORDER_SF_q
0x14000e27b  lea     r11, [rsp+68h+var_28]
0x14000e280  mov     rbx, [r11+38h]
0x14000e284  mov     rbp, [r11+40h]
0x14000e288  mov     rsp, r11
0x14000e28b  pop     r15
0x14000e28d  pop     r14
0x14000e28f  pop     r13
0x14000e291  pop     rdi
0x14000e292  pop     rsi
0x14000e293  retn
```
