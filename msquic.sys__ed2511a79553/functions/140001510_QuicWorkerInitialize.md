# QuicWorkerInitialize

- ea: `0x140001510`
- end: `0x140001755`
- name: `QuicWorkerInitialize`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400013c4`

## callees

- `0x140001510`
- `0x1400230c0`
- `0x14002e124`
- `0x14003ed00`
- `0x14003fdf8`
- `0x1400453d0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140001560`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001560`
- `ntoskrnl!KeInitializeEvent` at `0x140001575`
- `ntoskrnl!KeInitializeEvent` at `0x14000158e`
- `ntoskrnl!KeInitializeEvent` at `0x140001575`
- `ntoskrnl!KeInitializeEvent` at `0x14000158e`
- `ntoskrnl!KeSetEvent` at `0x140001724`
- `ntoskrnl!KeSetEvent` at `0x140001724`
- `ntoskrnl!ExAllocatePool2` at `0x1400015e3`
- `ntoskrnl!ExAllocatePool2` at `0x1400015e3`

## string_xrefs

- `0x1400016fd`: `CxPlatThreadCreate`

## pseudocode

```c
__int64 __fastcall QuicWorkerInitialize(int a1, int a2, __int64 a3, __int64 a4)
{
  __int64 Pool2; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // edi
  unsigned int i; // ecx
  __int64 v12; // rax
  _QWORD *v13; // rax
  int v14; // edi
  int v15; // edi
  __int16 v16; // r8
  __int16 v17; // dx
  __int64 v18; // rcx
  _WORD v20[2]; // [rsp+30h] [rbp-38h] BYREF
  int v21; // [rsp+34h] [rbp-34h]
  const char *v22; // [rsp+38h] [rbp-30h]
  NTSTATUS (__fastcall *v23)(_QWORD *); // [rsp+40h] [rbp-28h]
  __int64 v24; // [rsp+48h] [rbp-20h]

  if ( Microsoft_QuicEnableBits < 0 )
    McTemplateU0php_EtwWriteTransfer(a1, a2, a4, *(unsigned __int16 *)(a3 + 2), a1);
  *(_QWORD *)(a4 + 48) = a3;
  *(_BYTE *)(a4 + 81) = 1;
  KeInitializeSpinLock((PKSPIN_LOCK)(a4 + 160));
  KeInitializeEvent((PRKEVENT)(a4 + 56), NotificationEvent, 0);
  KeInitializeEvent((PRKEVENT)(a4 + 128), SynchronizationEvent, 0);
  *(_QWORD *)(a4 + 88) = -1;
  *(_QWORD *)(a4 + 184) = a4 + 176;
  *(_QWORD *)(a4 + 176) = a4 + 176;
  *(_QWORD *)(a4 + 192) = a4 + 176;
  *(_QWORD *)(a4 + 96) = 0;
  *(_QWORD *)(a4 + 208) = a4 + 200;
  *(_QWORD *)(a4 + 200) = a4 + 200;
  *(_DWORD *)(a4 + 112) = 32;
  *(_QWORD *)(a4 + 104) = 0;
  Pool2 = ExAllocatePool2(66, 512, 875651921);
  *(_QWORD *)(a4 + 120) = Pool2;
  if ( !Pool2 )
  {
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(v9, v8, "timerwheel slots", 512);
    v10 = -1073741801;
LABEL_24:
    KeSetEvent((PRKEVENT)(a4 + 56), 0, 0);
    QuicWorkerUninitialize(a4);
    return (unsigned int)v10;
  }
  for ( i = 0; i < *(_DWORD *)(a4 + 112); *v13 = v13 )
  {
    v12 = i++;
    v13 = (_QWORD *)(*(_QWORD *)(a4 + 120) + 16 * v12);
    v13[1] = v13;
  }
  *(_QWORD *)(a4 + 32) = -1;
  *(_QWORD *)(a4 + 24) = QuicWorkerLoop;
  *(_QWORD *)(a4 + 8) = a4;
  *(_BYTE *)(a4 + 40) = 1;
  if ( a2 )
  {
    v14 = a2 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( !v15 )
      {
        v16 = 0;
        goto LABEL_16;
      }
      if ( v15 == 1 )
      {
        v16 = 6;
        goto LABEL_16;
      }
    }
  }
  v16 = 1;
LABEL_16:
  if ( P )
  {
    v17 = v16 | 4;
    if ( (*(_DWORD *)P & 0x10) == 0 )
      v17 = v16;
    v16 = v17;
    if ( (*(_DWORD *)P & 0x20) != 0 )
      v16 = v17 | 2;
  }
  v20[1] = *(_WORD *)(a3 + 2);
  v20[0] = v16;
  v21 = 0;
  v22 = "quic_worker";
  v23 = QuicWorkerThread;
  v24 = a4;
  v10 = CxPlatThreadCreate((__int64)v20, (PVOID *)(a4 + 152));
  if ( v10 < 0 )
  {
    if ( (byte_14005C489 & 2) != 0 )
      McTemplateU0pqs_EtwWriteTransfer(
        v18,
        (const EVENT_DESCRIPTOR *)QuicWorkerErrorStatus,
        a4,
        v10,
        "CxPlatThreadCreate");
    goto LABEL_24;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140001510  mov     r11, rsp
0x140001513  mov     [r11+8], rbx
0x140001517  mov     [r11+10h], rbp
0x14000151b  mov     [r11+18h], rsi
0x14000151f  push    rdi
0x140001520  push    r14
0x140001522  push    r15
0x140001524  sub     rsp, 50h
0x140001528  mov     al, cs:Microsoft_QuicEnableBits
0x14000152e  mov     rbx, r9
0x140001531  mov     rsi, r8
0x140001534  mov     edi, edx
0x140001536  test    al, al
0x140001538  jns     short loc_14000154B
0x14000153a  movzx   r9d, word ptr [r8+2]
0x14000153f  mov     r8, rbx
0x140001542  mov     [r11-48h], rcx
0x140001546  call    McTemplateU0php_EtwWriteTransfer
0x14000154b  mov     r15d, 1
0x140001551  mov     [rbx+30h], rsi
0x140001555  lea     rcx, [rbx+0A0h]; SpinLock
0x14000155c  mov     [rbx+51h], r15b
0x140001560  call    cs:__imp_KeInitializeSpinLock
0x140001567  nop     dword ptr [rax+rax+00h]
0x14000156c  xor     r8d, r8d; State
0x14000156f  lea     rcx, [rbx+38h]; Event
0x140001573  xor     edx, edx; Type
0x140001575  call    cs:__imp_KeInitializeEvent
0x14000157c  nop     dword ptr [rax+rax+00h]
0x140001581  lea     rcx, [rbx+80h]; Event
0x140001588  xor     r8d, r8d; State
0x14000158b  mov     edx, r15d; Type
0x14000158e  call    cs:__imp_KeInitializeEvent
0x140001595  nop     dword ptr [rax+rax+00h]
0x14000159a  or      qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x14000159f  lea     rax, [rbx+0B0h]
0x1400015a6  mov     [rax+8], rax
0x1400015aa  lea     ecx, [r15+41h]
0x1400015ae  mov     [rax], rax
0x1400015b1  xor     r14d, r14d
0x1400015b4  mov     [rbx+0C0h], rax
0x1400015bb  mov     edx, 200h
0x1400015c0  lea     rax, [rbx+0C8h]
0x1400015c7  mov     [rbx+60h], r14
0x1400015cb  mov     [rax+8], rax
0x1400015cf  mov     r8d, 34316351h
0x1400015d5  mov     [rax], rax
0x1400015d8  mov     dword ptr [rbx+70h], 20h ; ' '
0x1400015df  mov     [rbx+68h], r14
0x1400015e3  call    cs:__imp_ExAllocatePool2
0x1400015ea  nop     dword ptr [rax+rax+00h]
0x1400015ef  mov     [rbx+78h], rax
0x1400015f3  test    rax, rax
0x1400015f6  jnz     short loc_14000161D
0x1400015f8  test    cs:Microsoft_QuicEnableBits, 2
0x1400015ff  jz      short loc_140001613
0x140001601  mov     r9d, 200h
0x140001607  lea     r8, aTimerwheelSlot; "timerwheel slots"
0x14000160e  call    McTemplateU0sx_EtwWriteTransfer
0x140001613  mov     edi, 0C0000017h
0x140001618  jmp     loc_14000171B
0x14000161d  mov     ecx, r14d
0x140001620  cmp     [rbx+70h], r14d
0x140001624  jbe     short loc_14000163F
0x140001626  mov     eax, ecx
0x140001628  add     ecx, r15d
0x14000162b  shl     rax, 4
0x14000162f  add     rax, [rbx+78h]
0x140001633  mov     [rax+8], rax
0x140001637  mov     [rax], rax
0x14000163a  cmp     ecx, [rbx+70h]
0x14000163d  jb      short loc_140001626
0x14000163f  or      qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x140001644  lea     rax, QuicWorkerLoop
0x14000164b  mov     [rbx+18h], rax
0x14000164f  mov     [rbx+8], rbx
0x140001653  mov     [rbx+28h], r15b
0x140001657  test    edi, edi
0x140001659  jz      short loc_140001678
0x14000165b  sub     edi, r15d
0x14000165e  jz      short loc_140001678
0x140001660  sub     edi, r15d
0x140001663  jz      short loc_140001672
0x140001665  cmp     edi, r15d
0x140001668  jnz     short loc_140001678
0x14000166a  mov     r8d, 6
0x140001670  jmp     short loc_14000167C
0x140001672  movzx   r8d, r14w
0x140001676  jmp     short loc_14000167C
0x140001678  movzx   r8d, r15w
0x14000167c  mov     rcx, cs:P
0x140001683  test    rcx, rcx
0x140001686  jz      short loc_1400016AB
0x140001688  mov     ecx, [rcx]
0x14000168a  movzx   edx, r8w
0x14000168e  or      dx, 4
0x140001692  test    cl, 10h
0x140001695  cmovz   dx, r8w
0x14000169a  movzx   r8d, dx
0x14000169e  test    cl, 20h
0x1400016a1  jz      short loc_1400016AB
0x1400016a3  or      dx, 2
0x1400016a7  movzx   r8d, dx
0x1400016ab  movzx   eax, word ptr [rsi+2]
0x1400016af  lea     rdx, [rbx+98h]
0x1400016b6  mov     [rsp+68h+var_36], ax
0x1400016bb  lea     rcx, [rsp+68h+var_38]
0x1400016c0  xor     eax, eax
0x1400016c2  mov     [rsp+68h+var_38], r8w
0x1400016c8  mov     [rsp+68h+var_34], eax
0x1400016cc  lea     rax, aQuicWorker; "quic_worker"
0x1400016d3  mov     [rsp+68h+var_30], rax
0x1400016d8  lea     rax, QuicWorkerThread
0x1400016df  mov     [rsp+68h+var_28], rax
0x1400016e4  mov     [rsp+68h+var_20], rbx
0x1400016e9  call    CxPlatThreadCreate
0x1400016ee  mov     edi, eax
0x1400016f0  test    eax, eax
0x1400016f2  jns     short loc_140001738
0x1400016f4  test    cs:byte_14005C489, 2
0x1400016fb  jz      short loc_14000171B
0x1400016fd  lea     rax, aCxplatthreadcr; "CxPlatThreadCreate"
0x140001704  mov     r9d, edi
0x140001707  mov     r8, rbx
0x14000170a  mov     [rsp+68h+var_48], rax
0x14000170f  lea     rdx, QuicWorkerErrorStatus
0x140001716  call    McTemplateU0pqs_EtwWriteTransfer
0x14000171b  xor     r8d, r8d; Wait
0x14000171e  lea     rcx, [rbx+38h]; Event
0x140001722  xor     edx, edx; Increment
0x140001724  call    cs:__imp_KeSetEvent
0x14000172b  nop     dword ptr [rax+rax+00h]
0x140001730  mov     rcx, rbx
0x140001733  call    QuicWorkerUninitialize
0x140001738  lea     r11, [rsp+68h+var_18]
0x14000173d  mov     eax, edi
0x14000173f  mov     rbx, [r11+20h]
0x140001743  mov     rbp, [r11+28h]
0x140001747  mov     rsi, [r11+30h]
0x14000174b  mov     rsp, r11
0x14000174e  pop     r15
0x140001750  pop     r14
0x140001752  pop     rdi
0x140001753  retn
```
