# SessionReconfigNotSupported

- ea: `0x140018a6c`
- end: `0x140018bca`
- name: `SessionReconfigNotSupported`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000e840`

## callees

- `0x140003bf4`
- `0x140018a6c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018a80`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018aa6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018b6c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018a80`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018aa6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018b6c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018ac4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018adf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018bae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018ac4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018adf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018bae`
- `ntoskrnl!ExAllocatePool2` at `0x140018b02`
- `ntoskrnl!ExAllocatePool2` at `0x140018b02`

## pseudocode

```c
__int64 __fastcall SessionReconfigNotSupported(__int64 a1)
{
  KIRQL v2; // al
  __int64 v3; // rbp
  KSPIN_LOCK *v4; // rdi
  KIRQL v5; // al
  int v6; // edx
  KIRQL v8; // al
  __int64 v9; // rdx

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v3 = *(_QWORD *)(a1 + 72);
  v4 = *(KSPIN_LOCK **)(a1 + 96);
  *(_BYTE *)(a1 + 64) = v2;
  while ( v4 != (KSPIN_LOCK *)(a1 + 96) )
  {
    v5 = KeAcquireSpinLockRaiseToDpc(v4 - 29);
    *((_BYTE *)v4 + 550) = 0;
    *((_BYTE *)v4 - 224) = v5;
    KeReleaseSpinLock(v4 - 29, v5);
    v4 = (KSPIN_LOCK *)*v4;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  if ( !v3 )
    return 0;
  if ( !ExAllocatePool2(64, 24, 1835230802) )
  {
    MEMORY[0x10] = *(_QWORD *)(a1 + 264);
    v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 400));
    v9 = *(_QWORD *)(v3 + 408);
    if ( *(_QWORD *)(v9 + 8) != v3 + 408 )
      __fastfail(3u);
    MEMORY[0] = *(_QWORD *)(v3 + 408);
    MEMORY[8] = v3 + 408;
    *(_QWORD *)(v9 + 8) = 0;
    *(_QWORD *)(v3 + 408) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 400), v8);
    return 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      25,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140018a6c  push    rbx
0x140018a6e  push    rbp
0x140018a6f  push    rsi
0x140018a70  push    rdi
0x140018a71  push    r14
0x140018a73  push    r15
0x140018a75  sub     rsp, 38h
0x140018a79  mov     rsi, rcx
0x140018a7c  add     rcx, 38h ; '8'; SpinLock
0x140018a80  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018a87  nop     dword ptr [rax+rax+00h]
0x140018a8c  mov     rbp, [rsi+48h]
0x140018a90  lea     r14, [rsi+60h]
0x140018a94  mov     rdi, [r14]
0x140018a97  mov     [rsi+40h], al
0x140018a9a  jmp     short loc_140018AD3
0x140018a9c  lea     rbx, [rdi-0E8h]
0x140018aa3  mov     rcx, rbx; SpinLock
0x140018aa6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018aad  nop     dword ptr [rax+rax+00h]
0x140018ab2  mov     rcx, rbx; SpinLock
0x140018ab5  mov     byte ptr [rdi+226h], 0
0x140018abc  mov     dl, al; NewIrql
0x140018abe  mov     [rdi-0E0h], al
0x140018ac4  call    cs:__imp_KeReleaseSpinLock
0x140018acb  nop     dword ptr [rax+rax+00h]
0x140018ad0  mov     rdi, [rdi]
0x140018ad3  cmp     rdi, r14
0x140018ad6  jnz     short loc_140018A9C
0x140018ad8  mov     dl, [rsi+40h]; NewIrql
0x140018adb  lea     rcx, [rsi+38h]; SpinLock
0x140018adf  call    cs:__imp_KeReleaseSpinLock
0x140018ae6  nop     dword ptr [rax+rax+00h]
0x140018aeb  test    rbp, rbp
0x140018aee  jz      loc_140018BBA
0x140018af4  mov     edx, 18h
0x140018af9  mov     r8d, 6D636652h
0x140018aff  lea     ecx, [rdx+28h]
0x140018b02  call    cs:__imp_ExAllocatePool2
0x140018b09  nop     dword ptr [rax+rax+00h]
0x140018b0e  mov     rbx, rax
0x140018b11  test    rax, rax
0x140018b14  jz      short loc_140018B53
0x140018b16  lea     rax, WPP_RECORDER_INITIALIZED
0x140018b1d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018b24  jz      short loc_140018B4C
0x140018b26  mov     rcx, cs:WPP_GLOBAL_Control
0x140018b2d  lea     rax, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x140018b34  mov     r9d, 19h
0x140018b3a  mov     [rsp+68h+var_48], rax
0x140018b3f  mov     rcx, [rcx+40h]
0x140018b43  lea     r8d, [r9-18h]
0x140018b47  call    WPP_RECORDER_SF_
0x140018b4c  mov     eax, 0C000009Ah
0x140018b51  jmp     short loc_140018BBC
0x140018b53  mov     rax, [rsi+108h]
0x140018b5a  lea     rdi, [rbp+190h]
0x140018b61  mov     rcx, rdi; SpinLock
0x140018b64  mov     ds:10h, rax
0x140018b6c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018b73  nop     dword ptr [rax+rax+00h]
0x140018b78  lea     rcx, [rbp+198h]
0x140018b7f  mov     rdx, [rcx]
0x140018b82  cmp     [rdx+8], rcx
0x140018b86  jz      short loc_140018B8F
0x140018b88  mov     ecx, 3
0x140018b8d  int     29h; Win8: RtlFailFast(ecx)
0x140018b8f  mov     [rbx], rdx
0x140018b92  mov     ds:8, rcx
0x140018b9a  mov     qword ptr [rdx+8], 0
0x140018ba2  mov     dl, al; NewIrql
0x140018ba4  mov     qword ptr [rcx], 0
0x140018bab  mov     rcx, rdi; SpinLock
0x140018bae  call    cs:__imp_KeReleaseSpinLock
0x140018bb5  nop     dword ptr [rax+rax+00h]
0x140018bba  xor     eax, eax
0x140018bbc  add     rsp, 38h
0x140018bc0  pop     r15
0x140018bc2  pop     r14
0x140018bc4  pop     rdi
0x140018bc5  pop     rsi
0x140018bc6  pop     rbp
0x140018bc7  pop     rbx
0x140018bc8  retn
```
