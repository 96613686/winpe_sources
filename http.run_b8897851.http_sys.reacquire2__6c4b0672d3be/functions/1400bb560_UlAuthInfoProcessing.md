# UlAuthInfoProcessing

- ea: `0x1400bb560`
- end: `0x1400bb711`
- name: `UlAuthInfoProcessing`
- size: `433`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1400c8eb0`
- `0x1400e6584`

## callees

- `0x1400bb560`
- `0x1400fb818`
- `0x140145d38`
- `0x1401468dc`
- `0x1401c5068`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bb6e5`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bb6e5`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400bb637`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400bb637`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bb69d`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bb69d`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400bb65b`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400bb65b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bb667`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bb6f1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bb667`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bb6f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bb622`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bb68a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bb622`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bb68a`

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
0x1400bb560  mov     [rsp+arg_18], r9b
0x1400bb565  push    rbx
0x1400bb566  push    rbp
0x1400bb567  push    rsi
0x1400bb568  push    rdi
0x1400bb569  push    r12
0x1400bb56b  push    r13
0x1400bb56d  push    r14
0x1400bb56f  push    r15
0x1400bb571  sub     rsp, 48h
0x1400bb575  mov     r15, r8
0x1400bb578  mov     rdi, rdx
0x1400bb57b  mov     r14, rcx
0x1400bb57e  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x1400bb585  jz      short loc_1400BB5C0
0x1400bb587  test    rdx, rdx
0x1400bb58a  jz      short loc_1400BB592
0x1400bb58c  mov     r8, [rdx+40h]
0x1400bb590  jmp     short loc_1400BB595
0x1400bb592  xor     r8d, r8d
0x1400bb595  movzx   eax, r9b
0x1400bb599  mov     edx, 0Ah
0x1400bb59e  mov     [rsp+88h+var_58], eax
0x1400bb5a2  mov     ecx, 40Eh
0x1400bb5a7  mov     [rsp+88h+var_60], r15
0x1400bb5ac  mov     r9, rdi
0x1400bb5af  mov     [rsp+88h+var_68], r8
0x1400bb5b4  lea     r8, WPP_bc9fc6652f5239547d16a26279776278_Traceguids
0x1400bb5bb  call    WPP_SF_qqqL
0x1400bb5c0  mov     r12, [rsp+88h+arg_20]
0x1400bb5c8  test    r12, r12
0x1400bb5cb  jz      short loc_1400BB5D2
0x1400bb5cd  mov     byte ptr [r12], 0
0x1400bb5d2  mov     rdx, r15
0x1400bb5d5  mov     rcx, r14
0x1400bb5d8  call    UlVerifyInitializedAuthSchemes
0x1400bb5dd  mov     ebp, eax
0x1400bb5df  test    eax, eax
0x1400bb5e1  js      loc_1400BB6FD
0x1400bb5e7  mov     rsi, [rdi+608h]
0x1400bb5ee  test    rsi, rsi
0x1400bb5f1  jz      short loc_1400BB5F8
0x1400bb5f3  mov     r13b, 1
0x1400bb5f6  jmp     short loc_1400BB61B
0x1400bb5f8  xor     r13b, r13b
0x1400bb5fb  cmp     [rdi+601h], r13b
0x1400bb602  jz      short loc_1400BB614
0x1400bb604  mov     rsi, [rdi+528h]
0x1400bb60b  add     rsi, 128h
0x1400bb612  jmp     short loc_1400BB622
0x1400bb614  mov     rsi, [rdi+530h]
0x1400bb61b  add     rsi, 130h
0x1400bb622  call    cs:__imp_KeEnterCriticalRegion
0x1400bb629  nop     dword ptr [rax+rax+00h]
0x1400bb62e  mov     rcx, [r14+558h]
0x1400bb635  xor     edx, edx
0x1400bb637  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400bb63e  nop     dword ptr [rax+rax+00h]
0x1400bb643  mov     r9, r12
0x1400bb646  mov     r8, r15
0x1400bb649  mov     rdx, rsi
0x1400bb64c  mov     rbx, rax
0x1400bb64f  call    UlIsAuthChangeNeeded
0x1400bb654  xor     edx, edx
0x1400bb656  mov     rcx, rbx
0x1400bb659  mov     ebp, eax
0x1400bb65b  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400bb662  nop     dword ptr [rax+rax+00h]
0x1400bb667  call    cs:__imp_KeLeaveCriticalRegion
0x1400bb66e  nop     dword ptr [rax+rax+00h]
0x1400bb673  test    ebp, ebp
0x1400bb675  js      loc_1400BB6FD
0x1400bb67b  test    r12, r12
0x1400bb67e  jz      short loc_1400BB6FD
0x1400bb680  cmp     [rsp+88h+arg_18], 0
0x1400bb688  jz      short loc_1400BB6FD
0x1400bb68a  call    cs:__imp_KeEnterCriticalRegion
0x1400bb691  nop     dword ptr [rax+rax+00h]
0x1400bb696  mov     rcx, [r14+558h]
0x1400bb69d  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400bb6a4  nop     dword ptr [rax+rax+00h]
0x1400bb6a9  test    r13b, r13b
0x1400bb6ac  jz      short loc_1400BB6CE
0x1400bb6ae  mov     rdx, [rdi+530h]
0x1400bb6b5  cmp     [rdi+608h], rdx
0x1400bb6bc  jz      short loc_1400BB6CE
0x1400bb6be  mov     eax, [r15]
0x1400bb6c1  test    al, 1
0x1400bb6c3  jz      short loc_1400BB6DE
0x1400bb6c5  add     rdx, 130h
0x1400bb6cc  jmp     short loc_1400BB6D1
0x1400bb6ce  mov     rdx, rsi
0x1400bb6d1  mov     r8, r15
0x1400bb6d4  mov     rcx, r14
0x1400bb6d7  call    UlUpdateAuthConfigNew
0x1400bb6dc  mov     ebp, eax
0x1400bb6de  mov     rcx, [r14+558h]
0x1400bb6e5  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400bb6ec  nop     dword ptr [rax+rax+00h]
0x1400bb6f1  call    cs:__imp_KeLeaveCriticalRegion
0x1400bb6f8  nop     dword ptr [rax+rax+00h]
0x1400bb6fd  mov     eax, ebp
0x1400bb6ff  add     rsp, 48h
0x1400bb703  pop     r15
0x1400bb705  pop     r14
0x1400bb707  pop     r13
0x1400bb709  pop     r12
0x1400bb70b  pop     rdi
0x1400bb70c  pop     rsi
0x1400bb70d  pop     rbp
0x1400bb70e  pop     rbx
0x1400bb70f  retn
```
