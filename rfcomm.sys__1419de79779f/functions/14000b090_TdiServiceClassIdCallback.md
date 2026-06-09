# TdiServiceClassIdCallback

- ea: `0x14000b090`
- end: `0x14000b22f`
- name: `TdiServiceClassIdCallback`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140007b60`

## callees

- `0x140003bf4`
- `0x140004a68`
- `0x140007350`
- `0x1400079c0`
- `0x14000b090`
- `0x14001ad08`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b0f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b0f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b11f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b137`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b11f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b137`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000b1da`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000b1da`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000b17e`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000b17e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b1eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b1eb`

## string_xrefs

- `0x14000b162`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x14000b1b6`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
void __fastcall TdiServiceClassIdCallback(unsigned int a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rbx
  struct _DEVICE_OBJECT *v8; // r14
  KIRQL v9; // al
  unsigned int v10; // edx
  KSPIN_LOCK *v11; // rcx
  __int64 v12; // rdx
  int v13; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      15,
      111,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      (char)a2);
  v7 = *a2;
  v8 = (struct _DEVICE_OBJECT *)a2[1];
  if ( a1 )
  {
    v12 = a1;
    goto LABEL_8;
  }
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 48));
  v10 = *(_DWORD *)(v7 + 148);
  v11 = (KSPIN_LOCK *)(v7 + 48);
  *(_BYTE *)(v7 + 56) = v9;
  if ( *(_DWORD *)(v7 + 112) >= v10 )
  {
    KeReleaseSpinLock(v11, v9);
    v12 = 3221225793LL;
LABEL_8:
    TdiCompleteConnect(v7, v12);
    goto LABEL_9;
  }
  *(_DWORD *)(v7 + 140) = *(_DWORD *)(v7 + 152);
  KeReleaseSpinLock(v11, v9);
  TdiConnectToPortWithPolicy(v7);
LABEL_9:
  if ( a4
    && IoAcquireRemoveLockEx(
         (PIO_REMOVE_LOCK)(a2[2] + 40),
         &TdiServiceClassIdCallback,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c",
         0xC52u,
         0x20u) >= 0 )
  {
    SdpDisconnect(v8, a2[2]);
  }
  RefObj_ReleaseEx(v7 + 24, 1145652818, 3160, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a2[2] + 40), TdiConnectToUuid, 0x20u);
  ExFreePoolWithTag(a2, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      15,
      112,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
}

```

## disassembly

```asm
0x14000b090  push    rbx
0x14000b092  push    rbp
0x14000b093  push    rsi
0x14000b094  push    rdi
0x14000b095  push    r12
0x14000b097  push    r13
0x14000b099  push    r14
0x14000b09b  sub     rsp, 30h
0x14000b09f  mov     rbp, r9
0x14000b0a2  mov     rdi, rdx
0x14000b0a5  mov     esi, ecx
0x14000b0a7  lea     r13, WPP_RECORDER_INITIALIZED
0x14000b0ae  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000b0b5  lea     r12, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000b0bc  jz      short loc_14000B0E2
0x14000b0be  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0c5  mov     r9d, 6Fh ; 'o'
0x14000b0cb  mov     [rsp+68h+var_40], rdx
0x14000b0d0  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14000b0d5  mov     rcx, [rcx+40h]
0x14000b0d9  lea     r8d, [r9-60h]
0x14000b0dd  call    WPP_RECORDER_SF_q
0x14000b0e2  mov     rbx, [rdi]
0x14000b0e5  mov     r14, [rdi+8]
0x14000b0e9  test    esi, esi
0x14000b0eb  jnz     short loc_14000B14A
0x14000b0ed  lea     rsi, [rbx+30h]
0x14000b0f1  mov     rcx, rsi; SpinLock
0x14000b0f4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b0fb  nop     dword ptr [rax+rax+00h]
0x14000b100  mov     edx, [rbx+94h]
0x14000b106  mov     rcx, rsi; SpinLock
0x14000b109  mov     [rbx+38h], al
0x14000b10c  cmp     [rbx+70h], edx
0x14000b10f  jnb     short loc_14000B135
0x14000b111  mov     edx, [rbx+98h]
0x14000b117  mov     [rbx+8Ch], edx
0x14000b11d  mov     dl, al; NewIrql
0x14000b11f  call    cs:__imp_KeReleaseSpinLock
0x14000b126  nop     dword ptr [rax+rax+00h]
0x14000b12b  mov     rcx, rbx
0x14000b12e  call    TdiConnectToPortWithPolicy
0x14000b133  jmp     short loc_14000B154
0x14000b135  mov     dl, al; NewIrql
0x14000b137  call    cs:__imp_KeReleaseSpinLock
0x14000b13e  nop     dword ptr [rax+rax+00h]
0x14000b143  mov     edx, 0C0000141h
0x14000b148  jmp     short loc_14000B14C
0x14000b14a  mov     edx, esi
0x14000b14c  mov     rcx, rbx
0x14000b14f  call    TdiCompleteConnect
0x14000b154  mov     esi, 20h ; ' '
0x14000b159  test    rbp, rbp
0x14000b15c  jz      short loc_14000B1AD
0x14000b15e  mov     rcx, [rdi+10h]
0x14000b162  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000b169  add     rcx, 28h ; '('; RemoveLock
0x14000b16d  mov     [rsp+68h+RemlockSize], esi; RemlockSize
0x14000b171  mov     r9d, 0C52h; Line
0x14000b177  lea     rdx, TdiServiceClassIdCallback; Tag
0x14000b17e  call    cs:__imp_IoAcquireRemoveLockEx
0x14000b185  nop     dword ptr [rax+rax+00h]
0x14000b18a  test    eax, eax
0x14000b18c  js      short loc_14000B1AD
0x14000b18e  mov     rdx, [rdi+10h]
0x14000b192  lea     r9, TdiSdpDisconnectCompletion
0x14000b199  mov     qword ptr [rsp+68h+RemlockSize], rdx; __int64
0x14000b19e  mov     r8, rbp
0x14000b1a1  mov     rcx, r14; DeviceObject
0x14000b1a4  mov     rdx, [rdx+50h]
0x14000b1a8  call    SdpDisconnect
0x14000b1ad  lea     rcx, [rbx+18h]
0x14000b1b1  mov     edx, 44494652h
0x14000b1b6  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000b1bd  mov     r8d, 0C58h
0x14000b1c3  call    RefObj_ReleaseEx
0x14000b1c8  mov     rcx, [rdi+10h]
0x14000b1cc  lea     rdx, TdiConnectToUuid; Tag
0x14000b1d3  add     rcx, 28h ; '('; RemoveLock
0x14000b1d7  mov     r8d, esi; RemlockSize
0x14000b1da  call    cs:__imp_IoReleaseRemoveLockEx
0x14000b1e1  nop     dword ptr [rax+rax+00h]
0x14000b1e6  xor     edx, edx; Tag
0x14000b1e8  mov     rcx, rdi; P
0x14000b1eb  call    cs:__imp_ExFreePoolWithTag
0x14000b1f2  nop     dword ptr [rax+rax+00h]
0x14000b1f7  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000b1fe  jz      short loc_14000B21F
0x14000b200  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b207  mov     r9d, 70h ; 'p'
0x14000b20d  mov     qword ptr [rsp+68h+RemlockSize], r12
0x14000b212  mov     rcx, [rcx+40h]
0x14000b216  lea     r8d, [r9-61h]
0x14000b21a  call    WPP_RECORDER_SF_
0x14000b21f  add     rsp, 30h
0x14000b223  pop     r14
0x14000b225  pop     r13
0x14000b227  pop     r12
0x14000b229  pop     rdi
0x14000b22a  pop     rsi
0x14000b22b  pop     rbp
0x14000b22c  pop     rbx
0x14000b22d  retn
```
