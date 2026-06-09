# SmbCeSendCompleteInd

- ea: `0x1400052f0`
- end: `0x1400054a7`
- name: `SmbCeSendCompleteInd`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140041468`
- `0x14004e5b0`

## callees

- `0x1400052f0`
- `0x1400054b0`
- `0x14000dfd8`
- `0x140016640`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005384`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005384`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000531f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000531f`
- `ntoskrnl!IoFreeMdl` at `0x14000544f`
- `ntoskrnl!IoFreeMdl` at `0x14000544f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000546b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000546b`

## pseudocode

```c
__int64 __fastcall SmbCeSendCompleteInd(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // rsi
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned int v11; // edi
  __int64 (__fastcall *v12)(__int64, __int64, _QWORD); // rax
  void *v13; // rcx

  if ( !a2 )
    return 0;
  v6 = 0;
  s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v7 = *(_QWORD *)(a1 + 368);
  v8 = 0;
  if ( v7 != a1 + 368 )
    v8 = v7 - 32;
  while ( v8 )
  {
    if ( *(_DWORD *)(v8 + 48) == 1 && *(_QWORD *)(v8 + 72) == a2 )
    {
      v6 = *(_QWORD *)(v8 + 56);
      *(_QWORD *)(v8 + 72) = 0;
      break;
    }
    v9 = *(_QWORD *)(v8 + 32);
    if ( v9 == a1 + 368 )
      v8 = 0;
    else
      v8 = v9 - 32;
  }
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
  if ( v6 )
  {
    v11 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids, a3);
    if ( *(_QWORD *)(v6 + 320) )
    {
      IoFreeMdl(*(PMDL *)(v6 + 328));
      v13 = *(void **)(v6 + 320);
      *(_QWORD *)(v6 + 328) = 0;
      ExFreePoolWithTag(v13, 0);
      *(_QWORD *)(v6 + 320) = 0;
    }
    v12 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(v6 + 152) + 24LL);
    if ( v12 )
      v11 = v12(v6, a2, a3);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids, v11);
    SmbCeDecrementPendingOperationsAndFinalize((PVOID)v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1400052f0  mov     [rsp+arg_10], rbx
0x1400052f5  mov     [rsp+arg_18], rbp
0x1400052fa  push    rdi
0x1400052fb  sub     rsp, 20h
0x1400052ff  mov     ebp, r8d
0x140005302  mov     rbx, rdx
0x140005305  mov     rdi, rcx
0x140005308  test    rdx, rdx
0x14000530b  jz      loc_1400054A0
0x140005311  mov     [rsp+28h+arg_0], rsi
0x140005316  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000531d  xor     esi, esi
0x14000531f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005326  nop     dword ptr [rax+rax+00h]
0x14000532b  lea     rdx, [rdi+170h]
0x140005332  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140005338  mov     r9, [rdx]
0x14000533b  xor     eax, eax
0x14000533d  cmp     r9, rdx
0x140005340  lea     rcx, [r9-20h]
0x140005344  cmovnz  rax, rcx
0x140005348  test    rax, rax
0x14000534b  jz      short loc_140005376
0x14000534d  cmp     dword ptr [rax+30h], 1
0x140005351  jnz     short loc_140005359
0x140005353  cmp     [rax+48h], rbx
0x140005357  jz      short loc_14000536A
0x140005359  mov     rax, [rax+20h]
0x14000535d  cmp     rax, rdx
0x140005360  jnz     loc_140005425
0x140005366  xor     eax, eax
0x140005368  jmp     short loc_140005348
0x14000536a  mov     rsi, [rax+38h]
0x14000536e  mov     qword ptr [rax+48h], 0
0x140005376  movzx   edx, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000537d  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140005384  call    cs:__imp_KeReleaseSpinLock
0x14000538b  nop     dword ptr [rax+rax+00h]
0x140005390  test    rsi, rsi
0x140005393  jnz     short loc_1400053AD
0x140005395  mov     rsi, [rsp+28h+arg_0]
0x14000539a  xor     eax, eax
0x14000539c  mov     rbx, [rsp+28h+arg_10]
0x1400053a1  mov     rbp, [rsp+28h+arg_18]
0x1400053a6  add     rsp, 20h
0x1400053aa  pop     rdi
0x1400053ab  retn
0x1400053ad  mov     [rsp+28h+arg_8], r15
0x1400053b2  xor     edi, edi
0x1400053b4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400053bb  lea     r15, WPP_GLOBAL_Control
0x1400053c2  cmp     rcx, r15
0x1400053c5  jz      short loc_1400053D0
0x1400053c7  test    dword ptr [rcx+2Ch], 400h
0x1400053ce  jnz     short loc_14000542E
0x1400053d0  cmp     [rsi+140h], rdi
0x1400053d7  jnz     short loc_140005448
0x1400053d9  mov     rax, [rsi+98h]
0x1400053e0  mov     rax, [rax+18h]
0x1400053e4  test    rax, rax
0x1400053e7  jz      short loc_1400053F9
0x1400053e9  mov     r8d, ebp
0x1400053ec  mov     rdx, rbx
0x1400053ef  mov     rcx, rsi
0x1400053f2  call    _guard_dispatch_icall
0x1400053f7  mov     edi, eax
0x1400053f9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140005400  cmp     rcx, r15
0x140005403  mov     r15, [rsp+28h+arg_8]
0x140005408  jz      short loc_140005413
0x14000540a  test    dword ptr [rcx+2Ch], 400h
0x140005411  jnz     short loc_140005483
0x140005413  mov     edx, 2
0x140005418  mov     rcx, rsi; pContext
0x14000541b  call    SmbCeDecrementPendingOperationsAndFinalize
0x140005420  jmp     loc_140005395
0x140005425  add     rax, 0FFFFFFFFFFFFFFE0h
0x140005429  jmp     loc_140005348
0x14000542e  mov     rcx, [rcx+18h]
0x140005432  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x140005439  mov     edx, 15h
0x14000543e  mov     r9d, ebp
0x140005441  call    WPP_SF_d
0x140005446  jmp     short loc_1400053D0
0x140005448  mov     rcx, [rsi+148h]; Mdl
0x14000544f  call    cs:__imp_IoFreeMdl
0x140005456  nop     dword ptr [rax+rax+00h]
0x14000545b  mov     rcx, [rsi+140h]; P
0x140005462  xor     edx, edx; Tag
0x140005464  mov     [rsi+148h], rdi
0x14000546b  call    cs:__imp_ExFreePoolWithTag
0x140005472  nop     dword ptr [rax+rax+00h]
0x140005477  mov     [rsi+140h], rdi
0x14000547e  jmp     loc_1400053D9
0x140005483  mov     rcx, [rcx+18h]
0x140005487  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x14000548e  mov     edx, 16h
0x140005493  mov     r9d, edi
0x140005496  call    WPP_SF_d
0x14000549b  jmp     loc_140005413
0x1400054a0  xor     eax, eax
0x1400054a2  jmp     loc_14000539C
```
