# PxTerminateDigitDetection

- ea: `0x140010a14`
- end: `0x140010b51`
- name: `PxTerminateDigitDetection`
- size: `317`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400104f0`
- `0x140010600`
- `0x140012210`
- `0x140015290`

## callees

- `0x140001b54`
- `0x140001b84`
- `0x1400105b0`
- `0x140010924`
- `0x140010a14`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010ade`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010ade`
- `ntoskrnl!IofCompleteRequest` at `0x140010aa9`
- `ntoskrnl!IofCompleteRequest` at `0x140010aa9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010ac5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010ac5`

## pseudocode

```c
KIRQL __fastcall PxTerminateDigitDetection(__int64 a1, __int64 a2, int a3)
{
  IRP *v6; // rdi
  int MillisecondTickCount; // eax
  __int64 v8; // rdx
  _DWORD *v9; // r8
  __int64 v10; // rax
  unsigned int v11; // edi
  KIRQL result; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids);
  v6 = *(IRP **)(a2 + 16);
  MillisecondTickCount = PxGetMillisecondTickCount();
  v8 = *(unsigned int *)(a2 + 88);
  v9 = (_DWORD *)(a2 + 40);
  *(_DWORD *)(a2 + 92) = MillisecondTickCount;
  v10 = *(unsigned int *)(a2 + 80);
  *(_DWORD *)(a2 + 96) = a3;
  if ( (int)v8 + (int)v10 < (unsigned int)v10 || *v9 <= (unsigned int)(v8 + v10) || (unsigned int)v10 < 0x40 )
  {
    v6->IoStatus.Status = -1073668071;
  }
  else
  {
    *(_WORD *)(a2 + v10 + 2 * v8 + 48) = 0;
    v6->IoStatus.Status = 0;
  }
  v6->IoStatus.Information = (unsigned int)(*v9 - 1) + 56LL;
  IofCompleteRequest(v6, 0);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 512), *(_BYTE *)(a1 + 520));
  v11 = PxStopDigitReporting(a1);
  result = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 512));
  *(_BYTE *)(a1 + 520) = result;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return result;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      result = WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids, v11);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140010a14  push    rbx
0x140010a16  push    rbp
0x140010a17  push    rsi
0x140010a18  push    rdi
0x140010a19  push    r14
0x140010a1b  sub     rsp, 20h
0x140010a1f  mov     esi, r8d
0x140010a22  mov     rbx, rdx
0x140010a25  mov     rbp, rcx
0x140010a28  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a2f  lea     r14, WPP_GLOBAL_Control
0x140010a36  cmp     rcx, r14
0x140010a39  jz      short loc_140010A56
0x140010a3b  cmp     byte ptr [rcx+29h], 5
0x140010a3f  jb      short loc_140010A56
0x140010a41  mov     rcx, [rcx+18h]
0x140010a45  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x140010a4c  mov     edx, 29h ; ')'
0x140010a51  call    WPP_SF_
0x140010a56  mov     rdi, [rbx+10h]
0x140010a5a  call    PxGetMillisecondTickCount
0x140010a5f  mov     edx, [rbx+58h]
0x140010a62  lea     r8, [rbx+28h]
0x140010a66  mov     [rbx+5Ch], eax
0x140010a69  mov     eax, [rbx+50h]
0x140010a6c  mov     [rbx+60h], esi
0x140010a6f  lea     ecx, [rdx+rax]
0x140010a72  cmp     ecx, eax
0x140010a74  jb      short loc_140010A90
0x140010a76  cmp     [r8], ecx
0x140010a79  jbe     short loc_140010A90
0x140010a7b  cmp     eax, 40h ; '@'
0x140010a7e  jb      short loc_140010A90
0x140010a80  lea     rcx, [rbx+rax]
0x140010a84  xor     eax, eax
0x140010a86  mov     [rcx+rdx*2+30h], ax
0x140010a8b  mov     [rdi+30h], eax
0x140010a8e  jmp     short loc_140010A97
0x140010a90  mov     dword ptr [rdi+30h], 0C0012019h
0x140010a97  mov     eax, [r8]
0x140010a9a  xor     edx, edx; PriorityBoost
0x140010a9c  dec     eax
0x140010a9e  mov     rcx, rdi; Irp
0x140010aa1  add     rax, 38h ; '8'
0x140010aa5  mov     [rdi+38h], rax
0x140010aa9  call    cs:__imp_IofCompleteRequest
0x140010ab0  nop     dword ptr [rax+rax+00h]
0x140010ab5  mov     dl, [rbp+208h]; NewIrql
0x140010abb  lea     rbx, [rbp+200h]
0x140010ac2  mov     rcx, rbx; SpinLock
0x140010ac5  call    cs:__imp_KeReleaseSpinLock
0x140010acc  nop     dword ptr [rax+rax+00h]
0x140010ad1  mov     rcx, rbp
0x140010ad4  call    PxStopDigitReporting
0x140010ad9  mov     rcx, rbx; SpinLock
0x140010adc  mov     edi, eax
0x140010ade  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010ae5  nop     dword ptr [rax+rax+00h]
0x140010aea  mov     [rbp+208h], al
0x140010af0  test    edi, edi
0x140010af2  jz      short loc_140010B1E
0x140010af4  mov     rcx, cs:WPP_GLOBAL_Control
0x140010afb  cmp     rcx, r14
0x140010afe  jz      short loc_140010B45
0x140010b00  cmp     byte ptr [rcx+29h], 2
0x140010b04  jb      short loc_140010B1E
0x140010b06  mov     rcx, [rcx+18h]
0x140010b0a  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x140010b11  mov     edx, 2Ah ; '*'
0x140010b16  mov     r9d, edi
0x140010b19  call    WPP_SF_d
0x140010b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b25  cmp     rcx, r14
0x140010b28  jz      short loc_140010B45
0x140010b2a  cmp     byte ptr [rcx+29h], 5
0x140010b2e  jb      short loc_140010B45
0x140010b30  mov     rcx, [rcx+18h]
0x140010b34  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x140010b3b  mov     edx, 2Bh ; '+'
0x140010b40  call    WPP_SF_
0x140010b45  add     rsp, 20h
0x140010b49  pop     r14
0x140010b4b  pop     rdi
0x140010b4c  pop     rsi
0x140010b4d  pop     rbp
0x140010b4e  pop     rbx
0x140010b4f  retn
```
