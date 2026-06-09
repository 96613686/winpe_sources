# PcpCreateFileHandle

- ea: `0x14000d8b8`
- end: `0x14000db80`
- name: `PcpCreateFileHandle`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140020a90`

## callees

- `0x140001884`
- `0x1400020f0`
- `0x140002c1c`
- `0x14000a910`
- `0x14000bc08`
- `0x14000d8b8`
- `0x14000eb54`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14000d9ae`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000d9ae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000db3c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000db3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db59`
- `ntoskrnl!ExAllocatePool2` at `0x14000d918`
- `ntoskrnl!ExAllocatePool2` at `0x14000d918`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000d9a2`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000d9a2`
- `NETIO!HfCreateFactory` at `0x14000da82`
- `NETIO!HfCreateFactory` at `0x14000da82`
- `NETIO!HfDestroyFactory` at `0x14000daf1`
- `NETIO!HfDestroyFactory` at `0x14000daf1`

## pseudocode

```c
__int64 __fastcall PcpCreateFileHandle(__int64 a1)
{
  __int64 Pool2; // rax
  _QWORD *v3; // rbx
  int v4; // edi
  int v5; // r8d
  PVOID v6; // rsi
  _QWORD *v7; // rax
  int v9; // [rsp+38h] [rbp-21h]
  __int64 v10; // [rsp+40h] [rbp-19h]
  UNICODE_STRING v11; // [rsp+60h] [rbp+7h] BYREF
  UNICODE_STRING v12; // [rsp+70h] [rbp+17h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp+27h] BYREF
  PVOID P; // [rsp+C8h] [rbp+6Fh] BYREF

  *(_QWORD *)&v12.Length = 4325440;
  P = 0;
  *(_QWORD *)&v11.Length = 5111884;
  v12.Buffer = (PWSTR)L"Traffic Control Global Interface";
  v11.Buffer = L"{6A5FEDA9-9BCE-4da1-94BF-E67D08946119}";
  memset(&LockHandle, 0, sizeof(LockHandle));
  Pool2 = ExAllocatePool2(64, 56, 1667786320);
  v3 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v4 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids, 3221225626LL);
    }
    return (unsigned int)v4;
  }
  *(_OWORD *)Pool2 = 0;
  v4 = 0;
  *(_OWORD *)(Pool2 + 16) = 0;
  *(_OWORD *)(Pool2 + 32) = 0;
  *(_QWORD *)(Pool2 + 48) = 0;
  *(_QWORD *)(Pool2 + 24) = Pool2 + 16;
  *(_QWORD *)(Pool2 + 16) = Pool2 + 16;
  KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 32));
  v3[5] = PsGetCurrentProcessId();
  if ( !PcgGlobalTcLine )
  {
    LOBYTE(v5) = 1;
    v4 = PcpLineCreate((unsigned int)&P, 0, v5, v12.MaximumLength, v11.MaximumLength, 0, 0x1FFFFFFF, 0, 0);
    if ( v4 < 0 )
    {
LABEL_22:
      ExFreePoolWithTag(v3, 0);
      return (unsigned int)v4;
    }
    v6 = P;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&PcgGlobalTcLine, (signed __int64)P, 0) )
    {
      PcpLineDestroy(P);
    }
    else
    {
      PcpLineUpdate((__int64)P, &v12, &v11, 0, 0, 0, 0, v9, v10, -1, -1);
      PcpLineStart(v6);
    }
  }
  if ( !*(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement )
  {
    P = 0;
    v4 = HfCreateFactory(0, &P);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids,
          (unsigned int)v4);
      }
      goto LABEL_22;
    }
    if ( _InterlockedCompareExchange64(
           (volatile signed __int64 *)&WPP_MAIN_CB.AlignmentRequirement,
           (signed __int64)P,
           0) )
    {
      HfDestroyFactory(&P);
    }
  }
  RtlAcquireWriteLock(&WPP_MAIN_CB.Queue.Wcb.DeviceObject, &LockHandle);
  v7 = *(_QWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
  if ( **(struct _DEVICE_OBJECT ***)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext )
    __fastfail(3u);
  *v3 = &WPP_MAIN_CB.Queue.Wcb.DeviceContext;
  v3[1] = v7;
  *v7 = v3;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = v3;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  *(_QWORD *)(*(_QWORD *)(a1 + 48) + 24LL) = v3;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000d8b8  mov     [rsp-8+arg_0], rbx
0x14000d8bd  mov     [rsp-8+arg_10], rsi
0x14000d8c2  push    rbp
0x14000d8c3  push    rdi
0x14000d8c4  push    r14
0x14000d8c6  lea     rbp, [rsp-47h]
0x14000d8cb  sub     rsp, 0A0h
0x14000d8d2  xor     eax, eax
0x14000d8d4  mov     [rbp+57h+var_40], 420040h
0x14000d8dc  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000d8e0  mov     r14, rcx
0x14000d8e3  mov     [rbp+57h+P], rax
0x14000d8e7  xorps   xmm0, xmm0
0x14000d8ea  mov     r8d, 63686650h
0x14000d8f0  mov     [rbp+57h+var_50], 4E004Ch
0x14000d8f8  lea     ecx, [rax+40h]
0x14000d8fb  lea     rax, SourceString; "Traffic Control Global Interface"
0x14000d902  mov     [rbp+57h+var_38], rax
0x14000d906  lea     edx, [rcx-8]
0x14000d909  lea     rax, a6a5feda99bce4d; "{6A5FEDA9-9BCE-4da1-94BF-E67D08946119}"
0x14000d910  mov     [rbp+57h+var_48], rax
0x14000d914  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000d918  call    cs:__imp_ExAllocatePool2
0x14000d91f  nop     dword ptr [rax+rax+00h]
0x14000d924  mov     rbx, rax
0x14000d927  test    rax, rax
0x14000d92a  jnz     short loc_14000D97D
0x14000d92c  mov     edi, 0C000009Ah
0x14000d931  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d938  lea     rax, WPP_GLOBAL_Control
0x14000d93f  cmp     rcx, rax
0x14000d942  jz      loc_14000DB65
0x14000d948  cmp     byte ptr [rcx+29h], 2
0x14000d94c  jb      loc_14000DB65
0x14000d952  test    dword ptr [rcx+2Ch], 800h
0x14000d959  jz      loc_14000DB65
0x14000d95f  mov     rcx, [rcx+18h]
0x14000d963  lea     edx, [rbx+0Fh]
0x14000d966  mov     r9d, 0C000009Ah
0x14000d96c  lea     r8, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids
0x14000d973  call    WPP_SF_D
0x14000d978  jmp     loc_14000DB65
0x14000d97d  xorps   xmm0, xmm0
0x14000d980  lea     rcx, [rbx+20h]; SpinLock
0x14000d984  movups  xmmword ptr [rbx], xmm0
0x14000d987  xor     eax, eax
0x14000d989  xor     edi, edi
0x14000d98b  movups  xmmword ptr [rbx+10h], xmm0
0x14000d98f  movups  xmmword ptr [rbx+20h], xmm0
0x14000d993  mov     [rbx+30h], rax
0x14000d997  lea     rax, [rbx+10h]
0x14000d99b  mov     [rax+8], rax
0x14000d99f  mov     [rax], rax
0x14000d9a2  call    cs:__imp_KeInitializeSpinLock
0x14000d9a9  nop     dword ptr [rax+rax+00h]
0x14000d9ae  call    cs:__imp_PsGetCurrentProcessId
0x14000d9b5  nop     dword ptr [rax+rax+00h]
0x14000d9ba  mov     [rbx+28h], rax
0x14000d9be  cmp     cs:PcgGlobalTcLine, rdi
0x14000d9c5  jnz     loc_14000DA66
0x14000d9cb  movzx   r9d, word ptr [rbp+57h+var_40+2]
0x14000d9d0  lea     rcx, [rbp+57h+P]
0x14000d9d4  xor     eax, eax
0x14000d9d6  mov     r8b, 1
0x14000d9d9  mov     dword ptr [rsp+0B0h+var_70], eax
0x14000d9dd  xor     edx, edx
0x14000d9df  mov     [rsp+0B0h+var_78], eax
0x14000d9e3  mov     [rsp+0B0h+var_80], 1FFFFFFFh
0x14000d9ec  mov     [rsp+0B0h+var_88], rax
0x14000d9f1  movzx   eax, word ptr [rbp+57h+var_50+2]
0x14000d9f5  mov     word ptr [rsp+0B0h+var_90], ax
0x14000d9fa  call    PcpLineCreate
0x14000d9ff  mov     edi, eax
0x14000da01  test    eax, eax
0x14000da03  js      loc_14000DB54
0x14000da09  mov     rsi, [rbp+57h+P]
0x14000da0d  xor     eax, eax
0x14000da0f  lock cmpxchg cs:PcgGlobalTcLine, rsi
0x14000da18  mov     rcx, rsi; P
0x14000da1b  jz      short loc_14000DA24
0x14000da1d  call    PcpLineDestroy
0x14000da22  jmp     short loc_14000DA66
0x14000da24  mov     [rsp+0B0h+var_60], 0FFFFFFFFh
0x14000da2c  lea     r8, [rbp+57h+var_50]
0x14000da30  mov     [rsp+0B0h+var_68], 0FFFFFFFFFFFFFFFFh
0x14000da39  lea     rdx, [rbp+57h+var_40]
0x14000da3d  mov     dword ptr [rsp+0B0h+var_80], 0
0x14000da45  xor     r9d, r9d
0x14000da48  mov     dword ptr [rsp+0B0h+var_88], 0
0x14000da50  mov     [rsp+0B0h+var_90], 0
0x14000da59  call    PcpLineUpdate
0x14000da5e  mov     rcx, rsi
0x14000da61  call    PcpLineStart
0x14000da66  cmp     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, 0
0x14000da6e  jnz     loc_14000DAFD
0x14000da74  lea     rdx, [rbp+57h+P]
0x14000da78  mov     [rbp+57h+P], 0
0x14000da80  xor     ecx, ecx
0x14000da82  call    cs:__imp_HfCreateFactory
0x14000da89  nop     dword ptr [rax+rax+00h]
0x14000da8e  mov     edi, eax
0x14000da90  test    eax, eax
0x14000da92  jns     short loc_14000DADC
0x14000da94  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da9b  lea     rax, WPP_GLOBAL_Control
0x14000daa2  cmp     rcx, rax
0x14000daa5  jz      loc_14000DB54
0x14000daab  cmp     byte ptr [rcx+29h], 2
0x14000daaf  jb      loc_14000DB54
0x14000dab5  test    dword ptr [rcx+2Ch], 800h
0x14000dabc  jz      loc_14000DB54
0x14000dac2  mov     rcx, [rcx+18h]
0x14000dac6  lea     r8, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids
0x14000dacd  mov     edx, 10h
0x14000dad2  mov     r9d, edi
0x14000dad5  call    WPP_SF_D
0x14000dada  jmp     short loc_14000DB54
0x14000dadc  mov     rcx, [rbp+57h+P]
0x14000dae0  xor     eax, eax
0x14000dae2  lock cmpxchg qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, rcx
0x14000daeb  jz      short loc_14000DAFD
0x14000daed  lea     rcx, [rbp+57h+P]
0x14000daf1  call    cs:__imp_HfDestroyFactory
0x14000daf8  nop     dword ptr [rax+rax+00h]
0x14000dafd  lea     rdx, [rbp+57h+LockHandle]
0x14000db01  lea     rcx, WPP_MAIN_CB.Queue+30h
0x14000db08  call    RtlAcquireWriteLock
0x14000db0d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x14000db14  lea     rcx, WPP_MAIN_CB.Queue+20h
0x14000db1b  cmp     [rax], rcx
0x14000db1e  jz      short loc_14000DB27
0x14000db20  mov     ecx, 3
0x14000db25  int     29h; Win8: RtlFailFast(ecx)
0x14000db27  mov     [rbx], rcx
0x14000db2a  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000db2e  mov     [rbx+8], rax
0x14000db32  mov     [rax], rbx
0x14000db35  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rbx
0x14000db3c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000db43  nop     dword ptr [rax+rax+00h]
0x14000db48  mov     rax, [r14+30h]
0x14000db4c  mov     [rax+18h], rbx
0x14000db50  test    edi, edi
0x14000db52  jns     short loc_14000DB65
0x14000db54  xor     edx, edx; Tag
0x14000db56  mov     rcx, rbx; P
0x14000db59  call    cs:__imp_ExFreePoolWithTag
0x14000db60  nop     dword ptr [rax+rax+00h]
0x14000db65  lea     r11, [rsp+0B0h+var_10]
0x14000db6d  mov     eax, edi
0x14000db6f  mov     rbx, [r11+20h]
0x14000db73  mov     rsi, [r11+30h]
0x14000db77  mov     rsp, r11
0x14000db7a  pop     r14
0x14000db7c  pop     rdi
0x14000db7d  pop     rbp
0x14000db7e  retn
```
