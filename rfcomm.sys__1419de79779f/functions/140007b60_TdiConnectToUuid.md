# TdiConnectToUuid

- ea: `0x140007b60`
- end: `0x140007d39`
- name: `TdiConnectToUuid`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400074d0`

## callees

- `0x140003cb4`
- `0x140007350`
- `0x140007b60`
- `0x14000ab70`
- `0x14000b090`
- `0x14000bb4c`
- `0x14001a654`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007c16`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007c16`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007c3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007c3c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140007c8c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140007c8c`
- `ntoskrnl!ExAllocatePool2` at `0x140007bec`
- `ntoskrnl!ExAllocatePool2` at `0x140007bec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007c52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007cab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007c52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007cab`

## string_xrefs

- `0x140007c69`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
void __fastcall TdiConnectToUuid(__int64 a1, int a2, int a3)
{
  _QWORD *Pool2; // rsi
  __int64 v5; // rdx
  __int64 v6; // rbp
  NTSTATUS v7; // eax
  __int64 v8; // rdi
  signed int v9; // eax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF__guid_(WPP_GLOBAL_Control->DeviceExtension, a2, a3, 113);
  if ( !a1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        15,
        114,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        13);
    return;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(64, 24, 1129539154);
  if ( !Pool2 )
  {
    v5 = 3221225626LL;
LABEL_8:
    TdiCompleteConnect(a1, v5);
    return;
  }
  *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  v6 = TdiReferenceAddrLocked(a1, 1313754947);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 48), *(_BYTE *)(a1 + 56));
  if ( !v6 )
  {
    ExFreePoolWithTag(Pool2, 0);
    v5 = 3221225787LL;
    goto LABEL_8;
  }
  v7 = IoAcquireRemoveLockEx(
         (PIO_REMOVE_LOCK)(*(_QWORD *)(v6 + 80) + 40LL),
         TdiConnectToUuid,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c",
         0xC8Eu,
         0x20u);
  if ( v7 >= 0 )
  {
    *Pool2 = a1;
    Pool2[1] = *(_QWORD *)(*(_QWORD *)(v6 + 80) + 88LL);
    Pool2[2] = *(_QWORD *)(v6 + 80);
    RefObj_AddRefEx(a1 + 24, 1145652818, 3227, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    v8 = a1 + 116;
    v9 = BthServiceClassIdToPort((PDEVICE_OBJECT)Pool2[1], v8);
    if ( v9 < 0 )
      TdiServiceClassIdCallback(v9, Pool2, v8, 0);
  }
  else
  {
    TdiCompleteConnect(a1, (unsigned int)v7);
    ExFreePoolWithTag(Pool2, 0);
  }
  RefObj_ReleaseEx(v6 + 24, 1313754947, 3249, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
}

```

## disassembly

```asm
0x140007b60  push    rbx
0x140007b62  push    rbp
0x140007b63  push    rsi
0x140007b64  push    rdi
0x140007b65  sub     rsp, 38h
0x140007b69  mov     rdi, rcx
0x140007b6c  lea     rbx, WPP_RECORDER_INITIALIZED
0x140007b73  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140007b7a  jz      short loc_140007B9B
0x140007b7c  lea     rax, [rcx+7Ch]
0x140007b80  mov     r9d, 71h ; 'q'
0x140007b86  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b8d  mov     [rsp+58h+var_30], rax
0x140007b92  mov     rcx, [rcx+40h]
0x140007b96  call    WPP_RECORDER_SF__guid_
0x140007b9b  test    rdi, rdi
0x140007b9e  jnz     short loc_140007BDE
0x140007ba0  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140007ba7  jz      loc_140007D2F
0x140007bad  mov     rcx, cs:WPP_GLOBAL_Control
0x140007bb4  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140007bbb  lea     r9d, [rdi+72h]
0x140007bbf  mov     dword ptr [rsp+58h+var_30], 0C000000Dh
0x140007bc7  lea     r8d, [rdi+0Fh]
0x140007bcb  mov     qword ptr [rsp+58h+RemlockSize], rax
0x140007bd0  mov     rcx, [rcx+40h]
0x140007bd4  call    WPP_RECORDER_SF_d
0x140007bd9  jmp     loc_140007D2F
0x140007bde  mov     edx, 18h
0x140007be3  mov     r8d, 43536652h
0x140007be9  lea     ecx, [rdx+28h]
0x140007bec  call    cs:__imp_ExAllocatePool2
0x140007bf3  nop     dword ptr [rax+rax+00h]
0x140007bf8  mov     rsi, rax
0x140007bfb  test    rax, rax
0x140007bfe  jnz     short loc_140007C12
0x140007c00  mov     edx, 0C000009Ah
0x140007c05  mov     rcx, rdi
0x140007c08  call    TdiCompleteConnect
0x140007c0d  jmp     loc_140007D2F
0x140007c12  lea     rcx, [rdi+30h]; SpinLock
0x140007c16  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007c1d  nop     dword ptr [rax+rax+00h]
0x140007c22  mov     edx, 4E4E4F43h
0x140007c27  mov     rcx, rdi
0x140007c2a  mov     [rdi+38h], al
0x140007c2d  call    TdiReferenceAddrLocked
0x140007c32  mov     dl, [rdi+38h]; NewIrql
0x140007c35  lea     rcx, [rdi+30h]; SpinLock
0x140007c39  mov     rbp, rax
0x140007c3c  call    cs:__imp_KeReleaseSpinLock
0x140007c43  nop     dword ptr [rax+rax+00h]
0x140007c48  test    rbp, rbp
0x140007c4b  jnz     short loc_140007C65
0x140007c4d  xor     edx, edx; Tag
0x140007c4f  mov     rcx, rsi; P
0x140007c52  call    cs:__imp_ExFreePoolWithTag
0x140007c59  nop     dword ptr [rax+rax+00h]
0x140007c5e  mov     edx, 0C000013Bh
0x140007c63  jmp     short loc_140007C05
0x140007c65  mov     rcx, [rbp+50h]
0x140007c69  lea     rbx, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140007c70  add     rcx, 28h ; '('; RemoveLock
0x140007c74  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x140007c7c  mov     r8, rbx; File
0x140007c7f  lea     rdx, TdiConnectToUuid; Tag
0x140007c86  mov     r9d, 0C8Eh; Line
0x140007c8c  call    cs:__imp_IoAcquireRemoveLockEx
0x140007c93  nop     dword ptr [rax+rax+00h]
0x140007c98  test    eax, eax
0x140007c9a  jns     short loc_140007CB9
0x140007c9c  mov     edx, eax
0x140007c9e  mov     rcx, rdi
0x140007ca1  call    TdiCompleteConnect
0x140007ca6  xor     edx, edx; Tag
0x140007ca8  mov     rcx, rsi; P
0x140007cab  call    cs:__imp_ExFreePoolWithTag
0x140007cb2  nop     dword ptr [rax+rax+00h]
0x140007cb7  jmp     short loc_140007D18
0x140007cb9  mov     [rsi], rdi
0x140007cbc  mov     r9, rbx
0x140007cbf  mov     rax, [rbp+50h]
0x140007cc3  mov     edx, 44494652h
0x140007cc8  mov     r8d, 0C9Bh
0x140007cce  mov     rcx, [rax+58h]
0x140007cd2  mov     [rsi+8], rcx
0x140007cd6  lea     rcx, [rdi+18h]
0x140007cda  mov     rax, [rbp+50h]
0x140007cde  mov     [rsi+10h], rax
0x140007ce2  call    RefObj_AddRefEx
0x140007ce7  mov     rdx, [rsi+10h]
0x140007ceb  add     rdi, 74h ; 't'
0x140007cef  mov     rcx, [rsi+8]; DeviceObject
0x140007cf3  mov     r8, rsi
0x140007cf6  mov     qword ptr [rsp+58h+RemlockSize], rdi; __int64
0x140007cfb  mov     rdx, [rdx+50h]
0x140007cff  call    BthServiceClassIdToPort
0x140007d04  test    eax, eax
0x140007d06  jns     short loc_140007D18
0x140007d08  xor     r9d, r9d
0x140007d0b  mov     r8, rdi
0x140007d0e  mov     rdx, rsi
0x140007d11  mov     ecx, eax
0x140007d13  call    TdiServiceClassIdCallback
0x140007d18  lea     rcx, [rbp+18h]
0x140007d1c  mov     r9, rbx
0x140007d1f  mov     edx, 4E4E4F43h
0x140007d24  mov     r8d, 0CB1h
0x140007d2a  call    RefObj_ReleaseEx
0x140007d2f  add     rsp, 38h
0x140007d33  pop     rdi
0x140007d34  pop     rsi
0x140007d35  pop     rbp
0x140007d36  pop     rbx
0x140007d37  retn
```
