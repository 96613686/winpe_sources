# BrbpIndication

- ea: `0x14000e840`
- end: `0x14000eaae`
- name: `BrbpIndication`
- size: `622`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x14000e840`
- `0x14000f0c0`
- `0x140017ab8`
- `0x140017db4`
- `0x14001898c`
- `0x140018a6c`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000ea0c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000ea0c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000ea41`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000ea41`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e9c4`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e9c4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e864`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e864`
- `ntoskrnl!ObfReferenceObject` at `0x14000ea55`
- `ntoskrnl!ObfReferenceObject` at `0x14000ea55`

## string_xrefs

- `0x14000e9ae`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`
- `0x14000ea21`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`
- `0x14000ea6b`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`

## pseudocode

```c
void __fastcall BrbpIndication(__int64 a1, int a2, __int64 a3)
{
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // r9d
  __int64 v14; // r8
  __int64 v15; // r14
  int v16; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    KeGetCurrentIrql();
    WPP_RECORDER_SF_Lqd(WPP_GLOBAL_Control->DeviceExtension, v6, v7, v8);
  }
  if ( !a2 )
  {
    IoAcquireRemoveLockEx(
      (PIO_REMOVE_LOCK)(*(_QWORD *)(a1 + 72) + 40LL),
      (PVOID)0x54426652,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c",
      0xAFu,
      0x20u);
    ObfReferenceObject(*(PVOID *)(*(_QWORD *)(a1 + 72) + 80LL));
    RefObj_AddRefEx(a1 + 24, 1413637714, 177, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c");
    goto LABEL_29;
  }
  v9 = a2 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( !v10 )
      goto LABEL_29;
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( v12 )
      {
        if ( v12 == 6 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              a2,
              3,
              17,
              (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
          SessionReconfigInd(a1, *(_QWORD *)a3);
          goto LABEL_29;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        v13 = 18;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        v13 = 16;
      }
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        2,
        v13,
        (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
LABEL_29:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          3,
          19,
          (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
      return;
    }
    _InterlockedExchange64((volatile __int64 *)(a1 + 280), 0);
    if ( *(_DWORD *)(a3 + 16) != 1 )
    {
      if ( *(_DWORD *)(a3 + 16) != 4 )
      {
        v14 = 3221225648LL;
LABEL_22:
        SessionDisconnectInd(a1, 0, v14);
        *(_BYTE *)(a3 + 20) = 1;
        goto LABEL_29;
      }
      SessionReconfigNotSupported(a1);
    }
    v14 = 3221225788LL;
    goto LABEL_22;
  }
  v15 = *(_QWORD *)(a1 + 72);
  _InterlockedExchange64((volatile __int64 *)(a1 + 280), 0);
  if ( *(_DWORD *)(a1 + 48) != 6 )
    SessionDisconnect(a1);
  RefObj_ReleaseEx(a1 + 24, 1413637714, 201, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c");
  ObfDereferenceObject(*(PVOID *)(v15 + 80));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      3,
      15,
      (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v15 + 40), (PVOID)0x54426652, 0x20u);
}

```

## disassembly

```asm
0x14000e840  push    rbx
0x14000e842  push    rbp
0x14000e843  push    rdi
0x14000e844  push    r14
0x14000e846  push    r15
0x14000e848  sub     rsp, 40h
0x14000e84c  mov     r14, r8
0x14000e84f  mov     ebx, edx
0x14000e851  mov     rdi, rcx
0x14000e854  lea     r15, WPP_RECORDER_INITIALIZED
0x14000e85b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000e862  jz      short loc_14000E890
0x14000e864  call    cs:__imp_KeGetCurrentIrql
0x14000e86b  nop     dword ptr [rax+rax+00h]
0x14000e870  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e877  movzx   eax, al
0x14000e87a  mov     [rsp+68h+var_30], eax
0x14000e87e  mov     [rsp+68h+var_38], rdi
0x14000e883  mov     rcx, [rcx+40h]
0x14000e887  mov     [rsp+68h+var_40], ebx
0x14000e88b  call    WPP_RECORDER_SF_Lqd
0x14000e890  lea     rbp, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000e897  test    ebx, ebx
0x14000e899  jz      loc_14000EA1D
0x14000e89f  sub     ebx, 1
0x14000e8a2  jz      loc_14000E988
0x14000e8a8  sub     ebx, 1
0x14000e8ab  jz      loc_14000EA79
0x14000e8b1  sub     ebx, 1
0x14000e8b4  jz      loc_14000E944
0x14000e8ba  sub     ebx, 3
0x14000e8bd  jz      short loc_14000E92F
0x14000e8bf  cmp     ebx, 6
0x14000e8c2  jz      short loc_14000E8F7
0x14000e8c4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000e8cb  jz      loc_14000EAA1
0x14000e8d1  mov     r9d, 12h
0x14000e8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8de  mov     r8d, 2
0x14000e8e4  mov     qword ptr [rsp+68h+RemlockSize], rbp
0x14000e8e9  mov     rcx, [rcx+40h]
0x14000e8ed  call    WPP_RECORDER_SF_
0x14000e8f2  jmp     loc_14000EA79
0x14000e8f7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000e8fe  jz      short loc_14000E91F
0x14000e900  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e907  mov     r9d, 11h
0x14000e90d  mov     qword ptr [rsp+68h+RemlockSize], rbp
0x14000e912  mov     rcx, [rcx+40h]
0x14000e916  lea     r8d, [r9-0Eh]
0x14000e91a  call    WPP_RECORDER_SF_
0x14000e91f  mov     rdx, [r14]
0x14000e922  mov     rcx, rdi
0x14000e925  call    SessionReconfigInd
0x14000e92a  jmp     loc_14000EA79
0x14000e92f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000e936  jz      loc_14000EAA1
0x14000e93c  mov     r9d, 10h
0x14000e942  jmp     short loc_14000E8D7
0x14000e944  xor     eax, eax
0x14000e946  xchg    rax, [rdi+118h]
0x14000e94d  mov     ecx, [r14+10h]
0x14000e951  sub     ecx, 1
0x14000e954  jz      short loc_14000E96B
0x14000e956  cmp     ecx, 3
0x14000e959  jz      short loc_14000E963
0x14000e95b  mov     r8d, 0C00000B0h
0x14000e961  jmp     short loc_14000E971
0x14000e963  mov     rcx, rdi
0x14000e966  call    SessionReconfigNotSupported
0x14000e96b  mov     r8d, 0C000013Ch
0x14000e971  mov     r9b, 1
0x14000e974  xor     edx, edx
0x14000e976  mov     rcx, rdi
0x14000e979  call    SessionDisconnectInd
0x14000e97e  mov     byte ptr [r14+14h], 1
0x14000e983  jmp     loc_14000EA79
0x14000e988  mov     r14, [rdi+48h]
0x14000e98c  xor     eax, eax
0x14000e98e  xchg    rax, [rdi+118h]
0x14000e995  cmp     dword ptr [rdi+30h], 6
0x14000e999  jz      short loc_14000E9A3
0x14000e99b  mov     rcx, rdi
0x14000e99e  call    SessionDisconnect
0x14000e9a3  mov     ebx, 54426652h
0x14000e9a8  lea     rcx, [rdi+18h]
0x14000e9ac  mov     edx, ebx
0x14000e9ae  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000e9b5  mov     r8d, 0C9h
0x14000e9bb  call    RefObj_ReleaseEx
0x14000e9c0  mov     rcx, [r14+50h]; Object
0x14000e9c4  call    cs:__imp_ObfDereferenceObject
0x14000e9cb  nop     dword ptr [rax+rax+00h]
0x14000e9d0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000e9d7  jz      short loc_14000E9FF
0x14000e9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9e0  lea     rbp, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000e9e7  mov     r9d, 0Fh
0x14000e9ed  mov     qword ptr [rsp+68h+RemlockSize], rbp
0x14000e9f2  mov     rcx, [rcx+40h]
0x14000e9f6  lea     r8d, [r9-0Ch]
0x14000e9fa  call    WPP_RECORDER_SF_
0x14000e9ff  lea     rcx, [r14+28h]; RemoveLock
0x14000ea03  mov     r8d, 20h ; ' '; RemlockSize
0x14000ea09  mov     rdx, rbx; Tag
0x14000ea0c  call    cs:__imp_IoReleaseRemoveLockEx
0x14000ea13  nop     dword ptr [rax+rax+00h]
0x14000ea18  jmp     loc_14000EAA1
0x14000ea1d  mov     rcx, [rdi+48h]
0x14000ea21  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000ea28  mov     ebx, 54426652h
0x14000ea2d  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x14000ea35  add     rcx, 28h ; '('; RemoveLock
0x14000ea39  mov     edx, ebx; Tag
0x14000ea3b  mov     r9d, 0AFh; Line
0x14000ea41  call    cs:__imp_IoAcquireRemoveLockEx
0x14000ea48  nop     dword ptr [rax+rax+00h]
0x14000ea4d  mov     rcx, [rdi+48h]
0x14000ea51  mov     rcx, [rcx+50h]; Object
0x14000ea55  call    cs:__imp_ObfReferenceObject
0x14000ea5c  nop     dword ptr [rax+rax+00h]
0x14000ea61  lea     rcx, [rdi+18h]
0x14000ea65  mov     r8d, 0B1h
0x14000ea6b  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000ea72  mov     edx, ebx
0x14000ea74  call    RefObj_AddRefEx
0x14000ea79  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000ea80  jz      short loc_14000EAA1
0x14000ea82  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea89  mov     r9d, 13h
0x14000ea8f  mov     qword ptr [rsp+68h+RemlockSize], rbp
0x14000ea94  mov     rcx, [rcx+40h]
0x14000ea98  lea     r8d, [r9-10h]
0x14000ea9c  call    WPP_RECORDER_SF_
0x14000eaa1  add     rsp, 40h
0x14000eaa5  pop     r15
0x14000eaa7  pop     r14
0x14000eaa9  pop     rdi
0x14000eaaa  pop     rbp
0x14000eaab  pop     rbx
0x14000eaac  retn
```
