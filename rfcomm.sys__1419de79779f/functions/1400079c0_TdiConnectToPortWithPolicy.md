# TdiConnectToPortWithPolicy

- ea: `0x1400079c0`
- end: `0x140007b54`
- name: `TdiConnectToPortWithPolicy`
- size: `404`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400074d0`
- `0x14000b090`

## callees

- `0x140007350`
- `0x1400077cc`
- `0x1400079c0`
- `0x14000a380`
- `0x14000ab70`
- `0x14001a4f8`
- `0x14001e74c`
- `0x14001ea34`
- `0x14001f2ac`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400079d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400079d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400079f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400079f8`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140007a6f`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140007a6f`
- `ntoskrnl!ExAllocatePool2` at `0x140007a31`
- `ntoskrnl!ExAllocatePool2` at `0x140007a31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007b07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007b07`

## string_xrefs

- `0x140007a61`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140007a8c`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140007b28`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiConnectToPortWithPolicy(__int64 a1)
{
  __int64 v2; // rbp
  NTSTATUS v3; // ebx
  __int64 v4; // r14
  _QWORD *Pool2; // rsi
  __int128 v6; // xmm1
  int v7; // eax
  __int64 result; // rax

  *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  v2 = TdiReferenceAddrLocked(a1, 1313754947);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 48), *(_BYTE *)(a1 + 56));
  if ( !v2 )
  {
    v3 = -1073741509;
    return TdiCompleteConnect(a1, (unsigned int)v3);
  }
  v4 = *(_QWORD *)(v2 + 80);
  if ( (unsigned __int8)BthServicePolicyEnabled() )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 64, 1835230802);
    if ( Pool2 )
    {
      v3 = IoAcquireRemoveLockEx(
             (PIO_REMOVE_LOCK)(v4 + 40),
             TdiPortToServiceClassIdCallback,
             "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c",
             0x492u,
             0x20u);
      if ( v3 < 0 )
      {
        ExFreePoolWithTag(Pool2, 0x6D636652u);
      }
      else
      {
        *Pool2 = v4;
        *(_OWORD *)(Pool2 + 1) = *(_OWORD *)(a1 + 116);
        v6 = *(_OWORD *)(a1 + 128);
        Pool2[7] = a1;
        *((_WORD *)Pool2 + 18) = 256;
        *(_OWORD *)((char *)Pool2 + 20) = v6;
        RefObj_AddRefEx(a1 + 24, 1145652818, 1179, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
        v7 = BthPortToServiceClassIdList(*(PDEVICE_OBJECT *)(v4 + 88), (__int64)Pool2);
        if ( v7 < 0 )
          TdiPortToServiceClassIdCallback((unsigned int)v7, Pool2, 0, 0);
      }
    }
    else
    {
      v3 = -1073741670;
    }
  }
  else
  {
    v3 = 0;
    TdiConnectToPort(a1);
  }
  result = RefObj_ReleaseEx(v2 + 24, 1313754947, 1211, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  if ( v3 < 0 )
    return TdiCompleteConnect(a1, (unsigned int)v3);
  return result;
}

```

## disassembly

```asm
0x1400079c0  push    rbx
0x1400079c2  push    rbp
0x1400079c3  push    rsi
0x1400079c4  push    rdi
0x1400079c5  push    r14
0x1400079c7  sub     rsp, 50h
0x1400079cb  mov     rdi, rcx
0x1400079ce  add     rcx, 30h ; '0'; SpinLock
0x1400079d2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400079d9  nop     dword ptr [rax+rax+00h]
0x1400079de  mov     edx, 4E4E4F43h
0x1400079e3  mov     rcx, rdi
0x1400079e6  mov     [rdi+38h], al
0x1400079e9  call    TdiReferenceAddrLocked
0x1400079ee  mov     dl, [rdi+38h]; NewIrql
0x1400079f1  lea     rcx, [rdi+30h]; SpinLock
0x1400079f5  mov     rbp, rax
0x1400079f8  call    cs:__imp_KeReleaseSpinLock
0x1400079ff  nop     dword ptr [rax+rax+00h]
0x140007a04  test    rbp, rbp
0x140007a07  jnz     short loc_140007A13
0x140007a09  mov     ebx, 0C000013Bh
0x140007a0e  jmp     loc_140007B3E
0x140007a13  mov     r14, [rbp+50h]
0x140007a17  call    BthServicePolicyEnabled
0x140007a1c  test    al, al
0x140007a1e  jz      loc_140007B15
0x140007a24  mov     ecx, 40h ; '@'
0x140007a29  mov     r8d, 6D636652h
0x140007a2f  mov     edx, ecx
0x140007a31  call    cs:__imp_ExAllocatePool2
0x140007a38  nop     dword ptr [rax+rax+00h]
0x140007a3d  mov     rsi, rax
0x140007a40  test    rax, rax
0x140007a43  jnz     short loc_140007A4F
0x140007a45  mov     ebx, 0C000009Ah
0x140007a4a  jmp     loc_140007B1F
0x140007a4f  lea     rcx, [r14+28h]; RemoveLock
0x140007a53  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x140007a5b  mov     r9d, 492h; Line
0x140007a61  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140007a68  lea     rdx, TdiPortToServiceClassIdCallback; Tag
0x140007a6f  call    cs:__imp_IoAcquireRemoveLockEx
0x140007a76  nop     dword ptr [rax+rax+00h]
0x140007a7b  mov     ebx, eax
0x140007a7d  test    eax, eax
0x140007a7f  js      short loc_140007AFF
0x140007a81  mov     [rsi], r14
0x140007a84  lea     rcx, [rdi+18h]
0x140007a88  movups  xmm0, xmmword ptr [rdi+74h]
0x140007a8c  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140007a93  mov     edx, 44494652h
0x140007a98  mov     r8d, 49Bh
0x140007a9e  movups  xmmword ptr [rsi+8], xmm0
0x140007aa2  movups  xmm1, xmmword ptr [rdi+80h]
0x140007aa9  mov     [rsi+38h], rdi
0x140007aad  mov     word ptr [rsi+24h], 100h
0x140007ab3  movups  xmmword ptr [rsi+14h], xmm1
0x140007ab7  call    RefObj_AddRefEx
0x140007abc  movups  xmm0, xmmword ptr [rsi+8]
0x140007ac0  mov     r9b, [rsi+25h]
0x140007ac4  lea     r8, [rsp+78h+var_48]
0x140007ac9  movups  xmm1, xmmword ptr [rsi+14h]
0x140007acd  mov     rdx, [r14+50h]
0x140007ad1  mov     rcx, [r14+58h]; DeviceObject
0x140007ad5  movaps  [rsp+78h+var_48], xmm0
0x140007ada  movups  [rsp+78h+var_48+0Ch], xmm1
0x140007adf  mov     qword ptr [rsp+78h+RemlockSize], rsi; __int64
0x140007ae4  call    BthPortToServiceClassIdList
0x140007ae9  test    eax, eax
0x140007aeb  jns     short loc_140007B1F
0x140007aed  xor     r9d, r9d
0x140007af0  xor     r8d, r8d
0x140007af3  mov     rdx, rsi
0x140007af6  mov     ecx, eax
0x140007af8  call    TdiPortToServiceClassIdCallback
0x140007afd  jmp     short loc_140007B1F
0x140007aff  mov     edx, 6D636652h; Tag
0x140007b04  mov     rcx, rsi; P
0x140007b07  call    cs:__imp_ExFreePoolWithTag
0x140007b0e  nop     dword ptr [rax+rax+00h]
0x140007b13  jmp     short loc_140007B1F
0x140007b15  xor     ebx, ebx
0x140007b17  mov     rcx, rdi
0x140007b1a  call    TdiConnectToPort
0x140007b1f  lea     rcx, [rbp+18h]
0x140007b23  mov     edx, 4E4E4F43h
0x140007b28  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140007b2f  mov     r8d, 4BBh
0x140007b35  call    RefObj_ReleaseEx
0x140007b3a  test    ebx, ebx
0x140007b3c  jns     short loc_140007B48
0x140007b3e  mov     edx, ebx
0x140007b40  mov     rcx, rdi
0x140007b43  call    TdiCompleteConnect
0x140007b48  add     rsp, 50h
0x140007b4c  pop     r14
0x140007b4e  pop     rdi
0x140007b4f  pop     rsi
0x140007b50  pop     rbp
0x140007b51  pop     rbx
0x140007b52  retn
```
