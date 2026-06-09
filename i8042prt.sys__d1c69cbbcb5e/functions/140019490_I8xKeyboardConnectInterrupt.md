# I8xKeyboardConnectInterrupt

- ea: `0x140019490`
- end: `0x14001970d`
- name: `I8xKeyboardConnectInterrupt`
- size: `637`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x140019714`
- `0x14001bce0`

## callees

- `0x140004530`
- `0x140009840`
- `0x1400098f0`
- `0x14000b2b8`
- `0x14000b334`
- `0x14000da60`
- `0x140019490`
- `0x14001ce6c`

## import_xrefs

- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140019624`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140019624`
- `ntoskrnl!IoConnectInterrupt` at `0x1400195fe`
- `ntoskrnl!IoConnectInterrupt` at `0x1400195fe`
- `ntoskrnl!ObfDereferenceObject` at `0x140019667`
- `ntoskrnl!ObfDereferenceObject` at `0x140019667`

## pseudocode

```c
__int64 __fastcall I8xKeyboardConnectInterrupt(__int64 a1)
{
  PKINTERRUPT *v1; // rdi
  struct _DEVICE_OBJECT *v4; // r12
  BOOLEAN *v5; // r14
  char *v6; // r15
  _BYTE *v7; // rsi
  const char *v8; // r10
  const char *v9; // r8
  const char *v10; // rdx
  BOOLEAN ShareVector; // zf
  __int64 v12; // rdx
  NTSTATUS v13; // esi
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rax
  struct _DEVICE_OBJECT *v15; // rbx
  int v16; // edx
  int v17; // [rsp+70h] [rbp-29h] BYREF
  __int128 InputBuffer; // [rsp+78h] [rbp-21h] BYREF
  _OWORD v19[2]; // [rsp+88h] [rbp-11h] BYREF

  v1 = (PKINTERRUPT *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 8) )
    return 0;
  v4 = *(struct _DEVICE_OBJECT **)a1;
  v5 = (BOOLEAN *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 80LL);
  v6 = (char *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 68LL);
  v7 = (_BYTE *)(a1 + 537);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = "yes";
    if ( !*v5 )
      v8 = "no";
    v9 = "true";
    v10 = "Latched";
    if ( *v7 != 3 )
      v9 = "false";
    if ( *(_WORD *)(a1 + 538) != 1 )
      v10 = "LevelSensitive";
    WPP_RECORDER_SF_qDDDssDs(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v10,
      (_DWORD)v9,
      10,
      (__int64)WPP_b71d3786c0783d031954a21c92de3f01_Traceguids,
      (char)v4,
      *(_DWORD *)(a1 + 544),
      *(_DWORD *)(a1 + 540),
      *v6,
      (__int64)v10,
      (__int64)v9,
      *(_DWORD *)(a1 + 548),
      (__int64)v8);
  }
  ShareVector = *v7 == 3;
  *(_BYTE *)(a1 + 564) = 1;
  v13 = IoConnectInterrupt(
          v1,
          (PKSERVICE_ROUTINE)I8042KeyboardInterruptService,
          v4,
          (PKSPIN_LOCK)(a1 + 16),
          *(_DWORD *)(a1 + 544),
          *(_BYTE *)(a1 + 540),
          *v6,
          (KINTERRUPT_MODE)(*(_WORD *)(a1 + 538) == 1),
          ShareVector,
          *(_QWORD *)(a1 + 548),
          *v5);
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v12,
        0x11u,
        0xBu,
        (__int64)WPP_b71d3786c0783d031954a21c92de3f01_Traceguids);
    v17 = *(_DWORD *)(a1 + 540);
    I8xLogError(v4, -1073414135, 1080, -1073741670, (__int64)&v17, 1u);
    TraceLoggingConnectInterruptFailed((unsigned int)v13);
    I8xManuallyRemoveDevice(a1, v16);
  }
  else
  {
    memset(v19, 0, 28);
    InputBuffer = 0;
    AttachedDeviceReference = IoGetAttachedDeviceReference(v4);
    *((_QWORD *)&InputBuffer + 1) = *v1;
    *(_QWORD *)&InputBuffer = 48;
    v15 = AttachedDeviceReference;
    memset(v19, 0, sizeof(v19));
    I8xSendIoctl(AttachedDeviceReference, 0xB3FCFu, &InputBuffer, 0x30u);
    ObfDereferenceObject(v15);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140019490  push    rbp
0x140019492  push    rbx
0x140019493  push    rsi
0x140019494  push    rdi
0x140019495  push    r12
0x140019497  push    r13
0x140019499  push    r14
0x14001949b  push    r15
0x14001949d  lea     rbp, [rsp-1Fh]
0x1400194a2  sub     rsp, 0B8h
0x1400194a9  mov     rax, cs:__security_cookie
0x1400194b0  xor     rax, rsp
0x1400194b3  mov     [rbp+57h+var_48], rax
0x1400194b7  lea     rdi, [rcx+8]
0x1400194bb  mov     rbx, rcx
0x1400194be  cmp     qword ptr [rdi], 0
0x1400194c2  jz      short loc_1400194CB
0x1400194c4  xor     eax, eax
0x1400194c6  jmp     loc_1400196EC
0x1400194cb  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400194d2  mov     r12, [rcx]
0x1400194d5  lea     r14, [rax+50h]
0x1400194d9  mov     r13d, 1
0x1400194df  lea     r15, [rax+44h]
0x1400194e3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400194ea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400194f1  lea     rsi, [rcx+219h]
0x1400194f8  lea     r11, WPP_b71d3786c0783d031954a21c92de3f01_Traceguids
0x1400194ff  jz      loc_14001959D
0x140019505  cmp     byte ptr [r14], 0
0x140019509  lea     rcx, aNo; "no"
0x140019510  mov     eax, [rbx+224h]
0x140019516  lea     r10, aYes; "yes"
0x14001951d  cmovz   r10, rcx
0x140019521  lea     r8, aTrue; "true"
0x140019528  cmp     byte ptr [rsi], 3
0x14001952b  lea     rcx, aFalse; "false"
0x140019532  mov     [rsp+0F0h+var_90], r10
0x140019537  lea     rdx, aLatched; "Latched"
0x14001953e  mov     [rsp+0F0h+var_98], eax
0x140019542  lea     r9d, [r13+9]
0x140019546  mov     eax, [rbx+21Ch]
0x14001954c  cmovnz  r8, rcx
0x140019550  cmp     [rbx+21Ah], r13w
0x140019558  lea     rcx, aLevelsensitive; "LevelSensitive"
0x14001955f  mov     qword ptr [rsp+0F0h+FloatingSave], r8
0x140019564  cmovnz  rdx, rcx
0x140019568  movzx   ecx, byte ptr [r15]
0x14001956c  mov     [rsp+0F0h+ProcessorEnableMask], rdx
0x140019571  mov     dword ptr [rsp+0F0h+ShareVector], ecx
0x140019575  mov     rcx, cs:WPP_GLOBAL_Control
0x14001957c  mov     [rsp+0F0h+InterruptMode], eax
0x140019580  mov     eax, [rbx+220h]
0x140019586  mov     dword ptr [rsp+0F0h+SynchronizeIrql], eax
0x14001958a  mov     rcx, [rcx+40h]
0x14001958e  mov     qword ptr [rsp+0F0h+Irql], r12
0x140019593  mov     qword ptr [rsp+0F0h+Vector], r11
0x140019598  call    WPP_RECORDER_SF_qDDDssDs
0x14001959d  cmp     byte ptr [rsi], 3
0x1400195a0  lea     r9, [rbx+10h]; SpinLock
0x1400195a4  mov     [rbx+234h], r13b
0x1400195ab  mov     r8, r12; ServiceContext
0x1400195ae  mov     al, [r14]
0x1400195b1  setz    cl
0x1400195b4  mov     [rsp+0F0h+FloatingSave], al; FloatingSave
0x1400195b8  xor     edx, edx
0x1400195ba  mov     rax, [rbx+224h]
0x1400195c1  cmp     [rbx+21Ah], r13w
0x1400195c9  mov     [rsp+0F0h+ProcessorEnableMask], rax; ProcessorEnableMask
0x1400195ce  mov     al, [r15]
0x1400195d1  setz    dl
0x1400195d4  mov     [rsp+0F0h+ShareVector], cl; ShareVector
0x1400195d8  mov     rcx, rdi; InterruptObject
0x1400195db  mov     [rsp+0F0h+InterruptMode], edx; InterruptMode
0x1400195df  lea     rdx, I8042KeyboardInterruptService; ServiceRoutine
0x1400195e6  mov     [rsp+0F0h+SynchronizeIrql], al; SynchronizeIrql
0x1400195ea  mov     al, [rbx+21Ch]
0x1400195f0  mov     [rsp+0F0h+Irql], al; Irql
0x1400195f4  mov     eax, [rbx+220h]
0x1400195fa  mov     [rsp+0F0h+Vector], eax; Vector
0x1400195fe  call    cs:__imp_IoConnectInterrupt
0x140019605  nop     dword ptr [rax+rax+00h]
0x14001960a  mov     esi, eax
0x14001960c  test    eax, eax
0x14001960e  js      short loc_140019675
0x140019610  xorps   xmm0, xmm0
0x140019613  xor     eax, eax
0x140019615  movups  [rbp+57h+var_68], xmm0
0x140019619  mov     rcx, r12; DeviceObject
0x14001961c  movups  [rbp+57h+var_68+0Ch], xmm0
0x140019620  movups  [rbp+57h+InputBuffer], xmm0
0x140019624  call    cs:__imp_IoGetAttachedDeviceReference
0x14001962b  nop     dword ptr [rax+rax+00h]
0x140019630  mov     rcx, [rdi]
0x140019633  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x140019637  xorps   xmm0, xmm0
0x14001963a  mov     r9d, 30h ; '0'; InputBufferLength
0x140019640  movups  [rbp+57h+InputBuffer], xmm0
0x140019644  mov     qword ptr [rbp+57h+InputBuffer+8], rcx
0x140019648  mov     edx, 0B3FCFh; IoControlCode
0x14001964d  mov     rcx, rax; DeviceObject
0x140019650  mov     dword ptr [rbp+57h+InputBuffer], r9d
0x140019654  mov     rbx, rax
0x140019657  movups  [rbp+57h+var_68], xmm0
0x14001965b  movups  [rbp+57h+var_58], xmm0
0x14001965f  call    I8xSendIoctl
0x140019664  mov     rcx, rbx; Object
0x140019667  call    cs:__imp_ObfDereferenceObject
0x14001966e  nop     dword ptr [rax+rax+00h]
0x140019673  jmp     short loc_1400196EA
0x140019675  lea     rax, WPP_RECORDER_INITIALIZED
0x14001967c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019683  jz      short loc_1400196AB
0x140019685  mov     rcx, cs:WPP_GLOBAL_Control
0x14001968c  lea     rax, WPP_b71d3786c0783d031954a21c92de3f01_Traceguids
0x140019693  mov     r9d, 0Bh
0x140019699  mov     qword ptr [rsp+0F0h+Vector], rax
0x14001969e  mov     rcx, [rcx+40h]
0x1400196a2  lea     r8d, [r9+6]
0x1400196a6  call    WPP_RECORDER_SF_
0x1400196ab  mov     eax, [rbx+21Ch]
0x1400196b1  mov     edx, 0C0050009h
0x1400196b6  mov     [rbp+57h+var_80], eax
0x1400196b9  mov     r9d, 0C000009Ah
0x1400196bf  lea     rax, [rbp+57h+var_80]
0x1400196c3  mov     dword ptr [rsp+0F0h+Irql], r13d
0x1400196c8  mov     r8d, 438h
0x1400196ce  mov     qword ptr [rsp+0F0h+Vector], rax
0x1400196d3  mov     rcx, r12
0x1400196d6  call    I8xLogError
0x1400196db  mov     ecx, esi
0x1400196dd  call    TraceLoggingConnectInterruptFailed
0x1400196e2  mov     rcx, rbx
0x1400196e5  call    I8xManuallyRemoveDevice
0x1400196ea  mov     eax, esi
0x1400196ec  mov     rcx, [rbp+57h+var_48]
0x1400196f0  xor     rcx, rsp; StackCookie
0x1400196f3  call    __security_check_cookie
0x1400196f8  add     rsp, 0B8h
0x1400196ff  pop     r15
0x140019701  pop     r14
0x140019703  pop     r13
0x140019705  pop     r12
0x140019707  pop     rdi
0x140019708  pop     rsi
0x140019709  pop     rbx
0x14001970a  pop     rbp
0x14001970b  retn
```
