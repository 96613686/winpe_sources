# UlAuthInfoProcessing

- ea: `0x1400bb480`
- end: `0x1400bb631`
- name: `UlAuthInfoProcessing`
- size: `433`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1400c8dd0`
- `0x1400e65c4`

## callees

- `0x1400bb480`
- `0x1400fb848`
- `0x140145e28`
- `0x1401469cc`
- `0x1401c5068`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bb605`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bb605`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400bb557`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400bb557`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bb5bd`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bb5bd`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400bb57b`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400bb57b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bb587`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bb611`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bb587`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bb611`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bb542`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bb5aa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bb542`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bb5aa`

## pseudocode

```c
__int64 __fastcall UlAuthInfoProcessing(__int64 a1, __int64 a2, _DWORD *a3, unsigned __int8 a4, _BYTE *a5)
{
  __int64 v8; // r8
  int updated; // ebp
  __int64 v10; // rsi
  char v11; // r13
  __int64 v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx

  if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
  {
    if ( a2 )
      v8 = *(_QWORD *)(a2 + 64);
    else
      v8 = 0;
    WPP_SF_qqqL(1038, 10, WPP_bc9fc6652f5239547d16a26279776278_Traceguids, a2, v8, a3, a4);
  }
  if ( a5 )
    *a5 = 0;
  updated = UlVerifyInitializedAuthSchemes(a1, a3);
  if ( updated < 0 )
    return (unsigned int)updated;
  v10 = *(_QWORD *)(a2 + 1544);
  if ( v10 )
  {
    v11 = 1;
LABEL_14:
    v12 = v10 + 304;
    goto LABEL_15;
  }
  v11 = 0;
  if ( !*(_BYTE *)(a2 + 1537) )
  {
    v10 = *(_QWORD *)(a2 + 1328);
    goto LABEL_14;
  }
  v12 = *(_QWORD *)(a2 + 1320) + 296LL;
LABEL_15:
  KeEnterCriticalRegion();
  v13 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 1368), 0);
  updated = UlIsAuthChangeNeeded(v14, v12, a3, a5);
  ExReleaseCacheAwarePushLockSharedEx(v13, 0);
  KeLeaveCriticalRegion();
  if ( updated >= 0 && a5 && a4 )
  {
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 1368));
    if ( !v11 || (v15 = *(_QWORD *)(a2 + 1328), *(_QWORD *)(a2 + 1544) == v15) )
    {
      v16 = v12;
    }
    else
    {
      if ( (*a3 & 1) == 0 )
      {
LABEL_24:
        ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 1368));
        KeLeaveCriticalRegion();
        return (unsigned int)updated;
      }
      v16 = v15 + 304;
    }
    updated = UlUpdateAuthConfigNew(a1, v16, a3);
    goto LABEL_24;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1400bb480  mov     [rsp+arg_18], r9b
0x1400bb485  push    rbx
0x1400bb486  push    rbp
0x1400bb487  push    rsi
0x1400bb488  push    rdi
0x1400bb489  push    r12
0x1400bb48b  push    r13
0x1400bb48d  push    r14
0x1400bb48f  push    r15
0x1400bb491  sub     rsp, 48h
0x1400bb495  mov     r15, r8
0x1400bb498  mov     rdi, rdx
0x1400bb49b  mov     r14, rcx
0x1400bb49e  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x1400bb4a5  jz      short loc_1400BB4E0
0x1400bb4a7  test    rdx, rdx
0x1400bb4aa  jz      short loc_1400BB4B2
0x1400bb4ac  mov     r8, [rdx+40h]
0x1400bb4b0  jmp     short loc_1400BB4B5
0x1400bb4b2  xor     r8d, r8d
0x1400bb4b5  movzx   eax, r9b
0x1400bb4b9  mov     edx, 0Ah
0x1400bb4be  mov     [rsp+88h+var_58], eax
0x1400bb4c2  mov     ecx, 40Eh
0x1400bb4c7  mov     [rsp+88h+var_60], r15
0x1400bb4cc  mov     r9, rdi
0x1400bb4cf  mov     [rsp+88h+var_68], r8
0x1400bb4d4  lea     r8, WPP_bc9fc6652f5239547d16a26279776278_Traceguids
0x1400bb4db  call    WPP_SF_qqqL
0x1400bb4e0  mov     r12, [rsp+88h+arg_20]
0x1400bb4e8  test    r12, r12
0x1400bb4eb  jz      short loc_1400BB4F2
0x1400bb4ed  mov     byte ptr [r12], 0
0x1400bb4f2  mov     rdx, r15
0x1400bb4f5  mov     rcx, r14
0x1400bb4f8  call    UlVerifyInitializedAuthSchemes
0x1400bb4fd  mov     ebp, eax
0x1400bb4ff  test    eax, eax
0x1400bb501  js      loc_1400BB61D
0x1400bb507  mov     rsi, [rdi+608h]
0x1400bb50e  test    rsi, rsi
0x1400bb511  jz      short loc_1400BB518
0x1400bb513  mov     r13b, 1
0x1400bb516  jmp     short loc_1400BB53B
0x1400bb518  xor     r13b, r13b
0x1400bb51b  cmp     [rdi+601h], r13b
0x1400bb522  jz      short loc_1400BB534
0x1400bb524  mov     rsi, [rdi+528h]
0x1400bb52b  add     rsi, 128h
0x1400bb532  jmp     short loc_1400BB542
0x1400bb534  mov     rsi, [rdi+530h]
0x1400bb53b  add     rsi, 130h
0x1400bb542  call    cs:__imp_KeEnterCriticalRegion
0x1400bb549  nop     dword ptr [rax+rax+00h]
0x1400bb54e  mov     rcx, [r14+558h]
0x1400bb555  xor     edx, edx
0x1400bb557  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400bb55e  nop     dword ptr [rax+rax+00h]
0x1400bb563  mov     r9, r12
0x1400bb566  mov     r8, r15
0x1400bb569  mov     rdx, rsi
0x1400bb56c  mov     rbx, rax
0x1400bb56f  call    UlIsAuthChangeNeeded
0x1400bb574  xor     edx, edx
0x1400bb576  mov     rcx, rbx
0x1400bb579  mov     ebp, eax
0x1400bb57b  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400bb582  nop     dword ptr [rax+rax+00h]
0x1400bb587  call    cs:__imp_KeLeaveCriticalRegion
0x1400bb58e  nop     dword ptr [rax+rax+00h]
0x1400bb593  test    ebp, ebp
0x1400bb595  js      loc_1400BB61D
0x1400bb59b  test    r12, r12
0x1400bb59e  jz      short loc_1400BB61D
0x1400bb5a0  cmp     [rsp+88h+arg_18], 0
0x1400bb5a8  jz      short loc_1400BB61D
0x1400bb5aa  call    cs:__imp_KeEnterCriticalRegion
0x1400bb5b1  nop     dword ptr [rax+rax+00h]
0x1400bb5b6  mov     rcx, [r14+558h]
0x1400bb5bd  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400bb5c4  nop     dword ptr [rax+rax+00h]
0x1400bb5c9  test    r13b, r13b
0x1400bb5cc  jz      short loc_1400BB5EE
0x1400bb5ce  mov     rdx, [rdi+530h]
0x1400bb5d5  cmp     [rdi+608h], rdx
0x1400bb5dc  jz      short loc_1400BB5EE
0x1400bb5de  mov     eax, [r15]
0x1400bb5e1  test    al, 1
0x1400bb5e3  jz      short loc_1400BB5FE
0x1400bb5e5  add     rdx, 130h
0x1400bb5ec  jmp     short loc_1400BB5F1
0x1400bb5ee  mov     rdx, rsi
0x1400bb5f1  mov     r8, r15
0x1400bb5f4  mov     rcx, r14
0x1400bb5f7  call    UlUpdateAuthConfigNew
0x1400bb5fc  mov     ebp, eax
0x1400bb5fe  mov     rcx, [r14+558h]
0x1400bb605  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400bb60c  nop     dword ptr [rax+rax+00h]
0x1400bb611  call    cs:__imp_KeLeaveCriticalRegion
0x1400bb618  nop     dword ptr [rax+rax+00h]
0x1400bb61d  mov     eax, ebp
0x1400bb61f  add     rsp, 48h
0x1400bb623  pop     r15
0x1400bb625  pop     r14
0x1400bb627  pop     r13
0x1400bb629  pop     r12
0x1400bb62b  pop     rdi
0x1400bb62c  pop     rsi
0x1400bb62d  pop     rbp
0x1400bb62e  pop     rbx
0x1400bb62f  retn
```
