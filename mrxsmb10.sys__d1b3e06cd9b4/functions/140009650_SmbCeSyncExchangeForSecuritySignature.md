# SmbCeSyncExchangeForSecuritySignature

- ea: `0x140009650`
- end: `0x1400098c2`
- name: `SmbCeSyncExchangeForSecuritySignature`
- size: `626`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003e364`
- `0x14004dd50`

## callees

- `0x140009650`
- `0x1400098d0`
- `0x14000a440`
- `0x14000ebd8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140009857`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009857`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009748`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009748`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009701`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009701`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009839`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009839`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000982d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000982d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140009878`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140009878`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009863`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009863`
- `ntoskrnl!KeInitializeEvent` at `0x140009811`
- `ntoskrnl!KeInitializeEvent` at `0x140009811`

## pseudocode

```c
__int64 __fastcall SmbCeSyncExchangeForSecuritySignature(__int64 a1)
{
  __int64 v1; // rbp
  unsigned int v2; // edi
  __int64 v3; // rax
  __int64 v5; // rsi
  char v6; // al
  char v8; // al
  __int64 v9; // rbp
  KIRQL v10; // r8
  _QWORD *v11; // rdx
  char v12; // cl
  __int64 Object; // rax
  __int64 v14; // rsi
  struct _KEVENT Event; // [rsp+30h] [rbp-48h] BYREF

  v1 = *(_QWORD *)(a1 + 80);
  v2 = 0;
  v3 = *(_QWORD *)(a1 + 88);
  memset(&Event, 0, sizeof(Event));
  if ( v3 )
    v5 = *(_QWORD *)(v3 + 96);
  else
    v5 = 0;
  if ( *(_BYTE *)(v5 + 408) || (v6 = *(_BYTE *)(v1 + 672), (v6 & 0x10) != 0) && (v6 & 8) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_3c31e27de787349c1c5c86b5fe6691e5_Traceguids, a1);
    v8 = *(_BYTE *)(v5 + 408);
    if ( v8 )
    {
      if ( *(_BYTE *)a1 == 3 )
        return 0;
    }
    else
    {
      v12 = *(_BYTE *)(v1 + 672);
      if ( (v12 & 0x20) == 0 )
      {
        if ( *(_BYTE *)a1 == 3 )
          *(_BYTE *)(v1 + 672) = v12 | 0x20;
        return 0;
      }
    }
    if ( *(_DWORD *)(v5 + 12) != 4 && !v8 && (*(_DWORD *)(a1 + 72) & 0x10) == 0 )
      return 3221225996LL;
    Object = SmbMmAllocateObject(3);
    v14 = Object;
    if ( Object )
    {
      *(_QWORD *)(Object + 56) = a1;
      SmbCeIncrementPendingOperations(a1, 1);
      v9 = v1 + 744;
      s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
      v10 = s_SmbCeDbSpinLockSavedIrql;
      v11 = *(_QWORD **)(v9 + 8);
      if ( *v11 != v9 )
        __fastfail(3u);
      *(_QWORD *)(v14 + 40) = v11;
      *(_QWORD *)(v14 + 32) = v9;
      *v11 = v14 + 32;
      *(_QWORD *)(v9 + 8) = v14 + 32;
      KeReleaseSpinLock(&s_SmbCeDbSpinLock, v10);
      if ( *(_QWORD *)(a1 + 120) )
      {
        v2 = 259;
      }
      else
      {
        KeInitializeEvent(&Event, SynchronizationEvent, 0);
        *(_QWORD *)(a1 + 120) = &Event;
        ExReleaseResourceLite(&s_SmbCeDbResource);
        KeLeaveCriticalRegion();
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
        *(_QWORD *)(a1 + 120) = 0;
      }
    }
    else
    {
      v2 = -1073741670;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_3c31e27de787349c1c5c86b5fe6691e5_Traceguids, a1);
  }
  return v2;
}

```

## disassembly

```asm
0x140009650  push    rbx
0x140009652  push    rbp
0x140009653  push    rsi
0x140009654  push    rdi
0x140009655  sub     rsp, 58h
0x140009659  mov     rbp, [rcx+50h]
0x14000965d  xor     eax, eax
0x14000965f  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x140009664  xor     edi, edi
0x140009666  mov     rax, [rcx+58h]
0x14000966a  xorps   xmm0, xmm0
0x14000966d  mov     rbx, rcx
0x140009670  movups  xmmword ptr [rsp+78h+Event.Header], xmm0
0x140009675  test    rax, rax
0x140009678  jz      short loc_1400096E5
0x14000967a  mov     rsi, [rax+60h]
0x14000967e  mov     [rsp+78h+arg_0], r14
0x140009686  cmp     [rsi+198h], dil
0x14000968d  jnz     short loc_1400096B2
0x14000968f  movzx   eax, byte ptr [rbp+2A0h]
0x140009696  test    al, 10h
0x140009698  jnz     loc_140009768
0x14000969e  mov     eax, edi
0x1400096a0  mov     r14, [rsp+78h+arg_0]
0x1400096a8  add     rsp, 58h
0x1400096ac  pop     rdi
0x1400096ad  pop     rsi
0x1400096ae  pop     rbp
0x1400096af  pop     rbx
0x1400096b0  retn
0x1400096b2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400096b9  lea     r14, WPP_GLOBAL_Control
0x1400096c0  cmp     rcx, r14
0x1400096c3  jnz     loc_140009775
0x1400096c9  movzx   eax, byte ptr [rsi+198h]
0x1400096d0  test    al, al
0x1400096d2  jz      loc_14000979F
0x1400096d8  cmp     byte ptr [rbx], 3
0x1400096db  jnz     loc_1400097C2
0x1400096e1  xor     eax, eax
0x1400096e3  jmp     short loc_1400096A0
0x1400096e5  xor     esi, esi
0x1400096e7  jmp     short loc_14000967E
0x1400096e9  mov     edx, 1
0x1400096ee  mov     [rax+38h], rbx
0x1400096f2  mov     rcx, rbx
0x1400096f5  call    SmbCeIncrementPendingOperations
0x1400096fa  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140009701  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009708  nop     dword ptr [rax+rax+00h]
0x14000970d  add     rbp, 2E8h
0x140009714  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x14000971a  movzx   r8d, al
0x14000971e  mov     rdx, [rbp+8]
0x140009722  cmp     [rdx], rbp
0x140009725  jnz     loc_1400097FD
0x14000972b  lea     rax, [rsi+20h]
0x14000972f  mov     [rax+8], rdx
0x140009733  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000973a  mov     [rax], rbp
0x14000973d  mov     [rdx], rax
0x140009740  movzx   edx, r8b; NewIrql
0x140009744  mov     [rbp+8], rax
0x140009748  call    cs:__imp_KeReleaseSpinLock
0x14000974f  nop     dword ptr [rax+rax+00h]
0x140009754  cmp     [rbx+78h], rdi
0x140009758  jz      loc_140009804
0x14000975e  mov     edi, 103h
0x140009763  jmp     loc_140009888
0x140009768  test    al, 8
0x14000976a  jnz     loc_14000969E
0x140009770  jmp     loc_1400096B2
0x140009775  test    dword ptr [rcx+2Ch], 200h
0x14000977c  jz      loc_1400096C9
0x140009782  mov     rcx, [rcx+18h]
0x140009786  lea     r8, WPP_3c31e27de787349c1c5c86b5fe6691e5_Traceguids
0x14000978d  mov     edx, 0Ah
0x140009792  mov     r9, rbx
0x140009795  call    WPP_SF_q
0x14000979a  jmp     loc_1400096C9
0x14000979f  movzx   ecx, byte ptr [rbp+2A0h]
0x1400097a6  test    cl, 20h
0x1400097a9  jnz     short loc_1400097C2
0x1400097ab  cmp     byte ptr [rbx], 3
0x1400097ae  jnz     loc_1400096E1
0x1400097b4  or      cl, 20h
0x1400097b7  mov     [rbp+2A0h], cl
0x1400097bd  jmp     loc_1400096E1
0x1400097c2  cmp     dword ptr [rsi+0Ch], 4
0x1400097c6  jz      short loc_1400097DD
0x1400097c8  test    al, al
0x1400097ca  jnz     short loc_1400097DD
0x1400097cc  mov     eax, [rbx+48h]
0x1400097cf  test    al, 10h
0x1400097d1  jnz     short loc_1400097DD
0x1400097d3  mov     eax, 0C000020Ch
0x1400097d8  jmp     loc_1400096A0
0x1400097dd  mov     ecx, 3
0x1400097e2  call    SmbMmAllocateObject
0x1400097e7  mov     rsi, rax
0x1400097ea  test    rax, rax
0x1400097ed  jnz     loc_1400096E9
0x1400097f3  mov     edi, 0C000009Ah
0x1400097f8  jmp     loc_140009888
0x1400097fd  mov     ecx, 3
0x140009802  int     29h; Win8: RtlFailFast(ecx)
0x140009804  xor     r8d, r8d; State
0x140009807  lea     rcx, [rsp+78h+Event]; Event
0x14000980c  mov     edx, 1; Type
0x140009811  call    cs:__imp_KeInitializeEvent
0x140009818  nop     dword ptr [rax+rax+00h]
0x14000981d  lea     rax, [rsp+78h+Event]
0x140009822  lea     rcx, s_SmbCeDbResource; Resource
0x140009829  mov     [rbx+78h], rax
0x14000982d  call    cs:__imp_ExReleaseResourceLite
0x140009834  nop     dword ptr [rax+rax+00h]
0x140009839  call    cs:__imp_KeLeaveCriticalRegion
0x140009840  nop     dword ptr [rax+rax+00h]
0x140009845  xor     r9d, r9d; Alertable
0x140009848  mov     [rsp+78h+Timeout], rdi; Timeout
0x14000984d  xor     r8d, r8d; WaitMode
0x140009850  lea     rcx, [rsp+78h+Event]; Object
0x140009855  xor     edx, edx; WaitReason
0x140009857  call    cs:__imp_KeWaitForSingleObject
0x14000985e  nop     dword ptr [rax+rax+00h]
0x140009863  call    cs:__imp_KeEnterCriticalRegion
0x14000986a  nop     dword ptr [rax+rax+00h]
0x14000986f  mov     dl, 1; Wait
0x140009871  lea     rcx, s_SmbCeDbResource; Resource
0x140009878  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000987f  nop     dword ptr [rax+rax+00h]
0x140009884  mov     [rbx+78h], rdi
0x140009888  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000988f  cmp     rcx, r14
0x140009892  jz      loc_14000969E
0x140009898  test    dword ptr [rcx+2Ch], 200h
0x14000989f  jz      loc_14000969E
0x1400098a5  mov     rcx, [rcx+18h]
0x1400098a9  lea     r8, WPP_3c31e27de787349c1c5c86b5fe6691e5_Traceguids
0x1400098b0  mov     edx, 0Bh
0x1400098b5  mov     r9, rbx
0x1400098b8  call    WPP_SF_q
0x1400098bd  jmp     loc_14000969E
```
