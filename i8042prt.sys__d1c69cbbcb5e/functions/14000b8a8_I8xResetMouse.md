# I8xResetMouse

- ea: `0x14000b8a8`
- end: `0x14000ba91`
- name: `I8xResetMouse`
- size: `489`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001b924`
- `0x14001bdd0`
- `0x14001c4d0`
- `0x14001e950`

## callees

- `0x1400014e0`
- `0x140004530`
- `0x14000b8a8`
- `0x14000ba98`
- `0x14000bb00`
- `0x14000c0a4`

## import_xrefs

- `ntoskrnl!IoStartPacket` at `0x14000b9d7`
- `ntoskrnl!IoStartPacket` at `0x14000b9d7`
- `ntoskrnl!IoFreeIrp` at `0x14000ba23`
- `ntoskrnl!IoFreeIrp` at `0x14000ba36`
- `ntoskrnl!IoFreeIrp` at `0x14000ba23`
- `ntoskrnl!IoFreeIrp` at `0x14000ba36`
- `ntoskrnl!IoAllocateIrp` at `0x14000b924`
- `ntoskrnl!IoAllocateIrp` at `0x14000b924`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000b98c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000b98c`

## pseudocode

```c
__int64 __fastcall I8xResetMouse(__int64 a1, int a2)
{
  char *v3; // rdi
  struct _DEVICE_OBJECT *v4; // rbp
  PIRP Irp; // rax
  IRP *v6; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v9; // edx
  NTSTATUS v10; // esi
  IRP *v11; // rdi

  v3 = (char *)(a1 + 1012);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      14,
      90,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      *v3);
  ++*(_BYTE *)(a1 + 1013);
  if ( (unsigned __int8)++*v3 >= 3u || *(_BYTE *)(a1 + 1013) >= 3u )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        17,
        91,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
    I8xResetMouseFailed(a1);
    return 3221225629LL;
  }
  else
  {
    v4 = *(struct _DEVICE_OBJECT **)a1;
    Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)a1 + 76LL), 0);
    v6 = Irp;
    if ( Irp )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 600), (signed __int64)Irp, 0) )
      {
        v10 = 0;
        IoFreeIrp(Irp);
        I8xSendResetCommand(a1);
      }
      else
      {
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].MajorFunction = 15;
        CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 999423;
        --v6->CurrentLocation;
        --v6->Tail.Overlay.CurrentStackLocation;
        v10 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 40), v6, File, 1u, 0x20u);
        if ( v10 < 0 )
        {
          v11 = (IRP *)_InterlockedExchange64((volatile __int64 *)(a1 + 600), 0);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              v9,
              16,
              93,
              (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
              (char)v11);
          if ( v11 )
            IoFreeIrp(v11);
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              v9,
              16,
              92,
              (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
              (char)v6);
          IoStartPacket(v4, v6, 0, 0);
        }
      }
      return (unsigned int)v10;
    }
    else
    {
      return 3221225626LL;
    }
  }
}

```

## disassembly

```asm
0x14000b8a8  push    rbx
0x14000b8aa  push    rbp
0x14000b8ab  push    rsi
0x14000b8ac  push    rdi
0x14000b8ad  push    r14
0x14000b8af  push    r15
0x14000b8b1  sub     rsp, 38h
0x14000b8b5  mov     rbx, rcx
0x14000b8b8  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b8bf  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b8c6  lea     rdi, [rcx+3F4h]
0x14000b8cd  lea     r15, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14000b8d4  jz      short loc_14000B8FC
0x14000b8d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b8dd  mov     r9d, 5Ah ; 'Z'
0x14000b8e3  movzx   eax, byte ptr [rdi]
0x14000b8e6  mov     dword ptr [rsp+68h+var_40], eax
0x14000b8ea  mov     qword ptr [rsp+68h+RemlockSize], r15
0x14000b8ef  mov     rcx, [rcx+40h]
0x14000b8f3  lea     r8d, [r9-4Ch]
0x14000b8f7  call    WPP_RECORDER_SF_d
0x14000b8fc  inc     byte ptr [rbx+3F5h]
0x14000b902  inc     byte ptr [rdi]
0x14000b904  cmp     byte ptr [rdi], 3
0x14000b907  mov     cl, [rbx+3F5h]
0x14000b90d  jnb     loc_14000BA4E
0x14000b913  cmp     cl, 3
0x14000b916  jnb     loc_14000BA4E
0x14000b91c  mov     rbp, [rbx]
0x14000b91f  xor     edx, edx; ChargeQuota
0x14000b921  mov     cl, [rbp+4Ch]; StackSize
0x14000b924  call    cs:__imp_IoAllocateIrp
0x14000b92b  nop     dword ptr [rax+rax+00h]
0x14000b930  mov     rdi, rax
0x14000b933  test    rax, rax
0x14000b936  jnz     short loc_14000B942
0x14000b938  mov     eax, 0C000009Ah
0x14000b93d  jmp     loc_14000BA83
0x14000b942  xor     eax, eax
0x14000b944  lock cmpxchg [rbx+258h], rdi
0x14000b94d  jnz     loc_14000BA31
0x14000b953  mov     rax, [rdi+0B8h]
0x14000b95a  lea     rcx, [rbx+28h]; RemoveLock
0x14000b95e  mov     r9d, 1; Line
0x14000b964  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x14000b96c  lea     r8, File; File
0x14000b973  mov     rdx, rdi; Tag
0x14000b976  mov     byte ptr [rax-48h], 0Fh
0x14000b97a  mov     dword ptr [rax-30h], 0F3FFFh
0x14000b981  dec     byte ptr [rdi+43h]
0x14000b984  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000b98c  call    cs:__imp_IoAcquireRemoveLockEx
0x14000b993  nop     dword ptr [rax+rax+00h]
0x14000b998  mov     esi, eax
0x14000b99a  test    eax, eax
0x14000b99c  js      short loc_14000B9E5
0x14000b99e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b9a5  jz      short loc_14000B9CB
0x14000b9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b9ae  mov     r9d, 5Ch ; '\'
0x14000b9b4  mov     [rsp+68h+var_40], rdi
0x14000b9b9  mov     qword ptr [rsp+68h+RemlockSize], r15
0x14000b9be  mov     rcx, [rcx+40h]
0x14000b9c2  lea     r8d, [r9-4Ch]
0x14000b9c6  call    WPP_RECORDER_SF_q
0x14000b9cb  xor     r9d, r9d; CancelFunction
0x14000b9ce  xor     r8d, r8d; Key
0x14000b9d1  mov     rdx, rdi; Irp
0x14000b9d4  mov     rcx, rbp; DeviceObject
0x14000b9d7  call    cs:__imp_IoStartPacket
0x14000b9de  nop     dword ptr [rax+rax+00h]
0x14000b9e3  jmp     short loc_14000BA4A
0x14000b9e5  xor     edi, edi
0x14000b9e7  xchg    rdi, [rbx+258h]
0x14000b9ee  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b9f5  jz      short loc_14000BA1B
0x14000b9f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b9fe  mov     r9d, 5Dh ; ']'
0x14000ba04  mov     [rsp+68h+var_40], rdi
0x14000ba09  mov     qword ptr [rsp+68h+RemlockSize], r15
0x14000ba0e  mov     rcx, [rcx+40h]
0x14000ba12  lea     r8d, [r9-4Dh]
0x14000ba16  call    WPP_RECORDER_SF_q
0x14000ba1b  test    rdi, rdi
0x14000ba1e  jz      short loc_14000BA4A
0x14000ba20  mov     rcx, rdi; Irp
0x14000ba23  call    cs:__imp_IoFreeIrp
0x14000ba2a  nop     dword ptr [rax+rax+00h]
0x14000ba2f  jmp     short loc_14000BA4A
0x14000ba31  mov     rcx, rdi; Irp
0x14000ba34  xor     esi, esi
0x14000ba36  call    cs:__imp_IoFreeIrp
0x14000ba3d  nop     dword ptr [rax+rax+00h]
0x14000ba42  mov     rcx, rbx
0x14000ba45  call    I8xSendResetCommand
0x14000ba4a  mov     eax, esi
0x14000ba4c  jmp     short loc_14000BA83
0x14000ba4e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000ba55  jz      short loc_14000BA76
0x14000ba57  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ba5e  mov     r9d, 5Bh ; '['
0x14000ba64  mov     qword ptr [rsp+68h+RemlockSize], r15
0x14000ba69  mov     rcx, [rcx+40h]
0x14000ba6d  lea     r8d, [r9-4Ah]
0x14000ba71  call    WPP_RECORDER_SF_
0x14000ba76  mov     rcx, rbx
0x14000ba79  call    I8xResetMouseFailed
0x14000ba7e  mov     eax, 0C000009Dh
0x14000ba83  add     rsp, 38h
0x14000ba87  pop     r15
0x14000ba89  pop     r14
0x14000ba8b  pop     rdi
0x14000ba8c  pop     rsi
0x14000ba8d  pop     rbp
0x14000ba8e  pop     rbx
0x14000ba8f  retn
```
