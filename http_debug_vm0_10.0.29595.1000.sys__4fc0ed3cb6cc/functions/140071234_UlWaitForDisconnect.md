# UlWaitForDisconnect

- ea: `0x140071234`
- end: `0x140071599`
- name: `UlWaitForDisconnect`
- size: `869`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140019730`

## callees

- `0x14000a350`
- `0x14003deb0`
- `0x140051188`
- `0x140051248`
- `0x1400705d0`
- `0x140071234`
- `0x1400715a0`
- `0x1401c64e4`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14007132c`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14007132c`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140071418`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140071418`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071407`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071424`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071441`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071407`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071424`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071441`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400713fb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140071435`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400713fb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140071435`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400712d7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071378`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400712d7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071378`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400712bf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071317`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071362`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400712bf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071317`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071362`

## pseudocode

```c
__int64 __fastcall UlWaitForDisconnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r13
  char v6; // r15
  int Grip; // ebx
  char *v10; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  volatile signed __int32 *v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  char *v20; // rdx
  int v21; // eax
  _QWORD v22[3]; // [rsp+40h] [rbp-18h] BYREF
  PVOID Entry; // [rsp+A0h] [rbp+48h] BYREF

  v4 = *(_QWORD *)(a1 + 8);
  v6 = a3;
  Entry = 0;
  v22[0] = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a2 )
      v18 = *(_QWORD *)(a2 + 48);
    else
      v18 = 0;
    WPP_SF_qqilq(v18, a2, a3, a1, a2, v18, (unsigned __int8)a3, a4);
  }
  Grip = UlAllocateGrip(v22, a4);
  if ( Grip >= 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a2 + 576, 0);
    v12 = *(_QWORD *)(a2 + 568);
    if ( v12 && *(_QWORD *)(v12 + 1744) == a1 )
    {
      if ( !v6 || (*(_BYTE *)(a2 + 632) & 0x50) != 0x50 )
      {
        if ( (*(_DWORD *)(a2 + 632) & 8) != 0 )
        {
          if ( v6 )
            Grip = -1073741300;
        }
        else
        {
          KeEnterCriticalRegion();
          v13 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v4 + 280), 0);
          if ( *(_BYTE *)(a1 + 5) )
          {
            Grip = -1073741436;
          }
          else
          {
            Grip = UlpOpenCoupling(a2, v4, &Entry);
            if ( Grip >= 0 )
            {
              KeEnterCriticalRegion();
              ExAcquirePushLockExclusiveEx((char *)Entry + 72, 0);
              v14 = (volatile signed __int32 *)Entry;
              if ( *((_BYTE *)Entry + 80) )
              {
                Grip = -1073741436;
              }
              else
              {
                *(_QWORD *)(a4 + 120) = Entry;
                v15 = _InterlockedIncrement(v14 + 5);
                if ( UxDebugCheckRefcount && v15 <= -1 )
                  UlBugCheckEx(3u, (ULONG_PTR)(v14 + 5), 5u, v15);
                v16 = v22[0];
                v22[0] = 0;
                *(_QWORD *)(*(_QWORD *)(v16 + 80) + 128LL) = v16;
                v17 = UlSiqEnqueueIrp((PKSPIN_LOCK)Entry + 16);
                v14 = (volatile signed __int32 *)Entry;
                Grip = v17;
                if ( v17 < 0 )
                {
                  *(_QWORD *)(a4 + 120) = 0;
                  v19 = _InterlockedDecrement(v14 + 5);
                  if ( UxDebugCheckRefcount && v19 <= -1 )
                    UlBugCheckEx(3u, (ULONG_PTR)(v14 + 5), 5u, v19);
                  if ( !v19 )
                    UlpFreeCoupling((char *)v14, 0);
                  v14 = (volatile signed __int32 *)Entry;
                  v22[0] = *(_QWORD *)(a4 + 128);
                  *(_QWORD *)(a4 + 128) = 0;
                }
                else
                {
                  *(_DWORD *)(a2 + 632) |= 0x20u;
                  Grip = 259;
                }
              }
              ExReleasePushLockExclusiveEx(v14 + 18, 0);
              KeLeaveCriticalRegion();
            }
          }
          ExReleaseCacheAwarePushLockSharedEx(v13, 0);
          KeLeaveCriticalRegion();
        }
      }
    }
    else
    {
      Grip = -1073741692;
    }
    ExReleasePushLockExclusiveEx(a2 + 576, 0);
    KeLeaveCriticalRegion();
  }
  v10 = (char *)Entry;
  if ( Entry )
  {
    v20 = (char *)Entry + 20;
    v21 = _InterlockedDecrement((volatile signed __int32 *)Entry + 5);
    if ( UxDebugCheckRefcount && v21 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v20, 0xAu, v21);
    if ( !v21 )
      UlpFreeCoupling(v10, 0);
    Entry = 0;
  }
  UlFreeGrip(v22);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 210, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, (unsigned int)Grip);
  return (unsigned int)Grip;
}

```

## disassembly

```asm
0x140071234  push    rbp
0x140071236  push    rbx
0x140071237  push    rsi
0x140071238  push    rdi
0x140071239  push    r12
0x14007123b  push    r13
0x14007123d  push    r14
0x14007123f  push    r15
0x140071241  mov     rbp, rsp
0x140071244  sub     rsp, 58h
0x140071248  mov     r13, [rcx+8]
0x14007124c  mov     rsi, r9
0x14007124f  movzx   r15d, r8b
0x140071253  mov     rdi, rdx
0x140071256  mov     r14, rcx
0x140071259  mov     [rbp+Entry], 0
0x140071261  mov     [rbp+var_18], 0
0x140071269  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140071270  jnz     loc_140071474
0x140071276  mov     rdx, rsi
0x140071279  lea     rcx, [rbp+var_18]
0x14007127d  call    UlAllocateGrip
0x140071282  mov     ebx, eax
0x140071284  test    eax, eax
0x140071286  jns     short loc_1400712BF
0x140071288  mov     rcx, [rbp+Entry]; Entry
0x14007128c  test    rcx, rcx
0x14007128f  jnz     loc_1400714F9
0x140071295  lea     rcx, [rbp+var_18]
0x140071299  call    UlFreeGrip
0x14007129e  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400712a5  jnz     loc_14007157B
0x1400712ab  mov     eax, ebx
0x1400712ad  add     rsp, 58h
0x1400712b1  pop     r15
0x1400712b3  pop     r14
0x1400712b5  pop     r13
0x1400712b7  pop     r12
0x1400712b9  pop     rdi
0x1400712ba  pop     rsi
0x1400712bb  pop     rbx
0x1400712bc  pop     rbp
0x1400712bd  retn
0x1400712bf  call    cs:__imp_KeEnterCriticalRegion
0x1400712c6  nop     dword ptr [rax+rax+00h]
0x1400712cb  lea     r12, [rdi+240h]
0x1400712d2  xor     edx, edx
0x1400712d4  mov     rcx, r12
0x1400712d7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400712de  nop     dword ptr [rax+rax+00h]
0x1400712e3  mov     rax, [rdi+238h]
0x1400712ea  test    rax, rax
0x1400712ed  jz      loc_140071452
0x1400712f3  cmp     [rax+6D0h], r14
0x1400712fa  jnz     loc_140071452
0x140071300  test    r15b, r15b
0x140071303  jnz     loc_14007153E
0x140071309  mov     eax, [rdi+278h]
0x14007130f  test    al, 8
0x140071311  jnz     loc_140071554
0x140071317  call    cs:__imp_KeEnterCriticalRegion
0x14007131e  nop     dword ptr [rax+rax+00h]
0x140071323  mov     rcx, [r13+118h]
0x14007132a  xor     edx, edx
0x14007132c  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x140071333  nop     dword ptr [rax+rax+00h]
0x140071338  cmp     byte ptr [r14+5], 0
0x14007133d  mov     r15, rax
0x140071340  jnz     loc_140071567
0x140071346  lea     r8, [rbp+Entry]
0x14007134a  mov     rdx, r13
0x14007134d  mov     rcx, rdi
0x140071350  call    UlpOpenCoupling
0x140071355  xor     r14d, r14d
0x140071358  mov     ebx, eax
0x14007135a  test    eax, eax
0x14007135c  js      loc_140071413
0x140071362  call    cs:__imp_KeEnterCriticalRegion
0x140071369  nop     dword ptr [rax+rax+00h]
0x14007136e  mov     rcx, [rbp+Entry]
0x140071372  xor     edx, edx
0x140071374  add     rcx, 48h ; 'H'
0x140071378  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14007137f  nop     dword ptr [rax+rax+00h]
0x140071384  mov     rcx, [rbp+Entry]
0x140071388  cmp     [rcx+50h], r14b
0x14007138c  jnz     loc_140071571
0x140071392  mov     [rsi+78h], rcx
0x140071396  lea     rdx, [rcx+14h]; BugCheckParameter2
0x14007139a  lea     eax, [r14+1]
0x14007139e  lock xadd [rdx], eax
0x1400713a2  inc     eax
0x1400713a4  cmp     cs:UxDebugCheckRefcount, r14b
0x1400713ab  jnz     loc_140071459
0x1400713b1  mov     rcx, [rbp+var_18]
0x1400713b5  lea     r8, UlpCancelWaitForDisconnectIrp
0x1400713bc  mov     rdx, rsi
0x1400713bf  mov     [rbp+var_18], r14
0x1400713c3  mov     rax, [rcx+50h]
0x1400713c7  mov     [rax+80h], rcx
0x1400713ce  mov     rcx, [rbp+Entry]
0x1400713d2  sub     rcx, 0FFFFFFFFFFFFFF80h; SpinLock
0x1400713d6  call    UlSiqEnqueueIrp
0x1400713db  mov     rcx, [rbp+Entry]; Entry
0x1400713df  mov     ebx, eax
0x1400713e1  test    eax, eax
0x1400713e3  js      loc_1400714A2
0x1400713e9  or      dword ptr [rdi+278h], 20h
0x1400713f0  mov     ebx, 103h
0x1400713f5  add     rcx, 48h ; 'H'
0x1400713f9  xor     edx, edx
0x1400713fb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140071402  nop     dword ptr [rax+rax+00h]
0x140071407  call    cs:__imp_KeLeaveCriticalRegion
0x14007140e  nop     dword ptr [rax+rax+00h]
0x140071413  xor     edx, edx
0x140071415  mov     rcx, r15
0x140071418  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14007141f  nop     dword ptr [rax+rax+00h]
0x140071424  call    cs:__imp_KeLeaveCriticalRegion
0x14007142b  nop     dword ptr [rax+rax+00h]
0x140071430  xor     edx, edx
0x140071432  mov     rcx, r12
0x140071435  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14007143c  nop     dword ptr [rax+rax+00h]
0x140071441  call    cs:__imp_KeLeaveCriticalRegion
0x140071448  nop     dword ptr [rax+rax+00h]
0x14007144d  jmp     loc_140071288
0x140071452  mov     ebx, 0C0000084h
0x140071457  jmp     short loc_140071430
0x140071459  cmp     eax, 0FFFFFFFFh
0x14007145c  jg      loc_1400713B1
0x140071462  mov     ecx, 3; BugCheckParameter1
0x140071467  movsxd  r9, eax; BugCheckParameter4
0x14007146a  lea     r8d, [rcx+2]; BugCheckParameter3
0x14007146e  call    UlBugCheckEx
0x140071474  test    rdi, rdi
0x140071477  jz      short loc_14007149E
0x140071479  mov     rcx, [rdx+30h]
0x14007147d  mov     [rsp+58h+var_20], rsi
0x140071482  mov     r9, r14
0x140071485  mov     [rsp+58h+var_28], r15d
0x14007148a  mov     [rsp+58h+var_30], rcx
0x14007148f  mov     [rsp+58h+var_38], rdi
0x140071494  call    WPP_SF_qqilq
0x140071499  jmp     loc_140071276
0x14007149e  xor     ecx, ecx
0x1400714a0  jmp     short loc_14007147D
0x1400714a2  mov     [rsi+78h], r14
0x1400714a6  lea     rdx, [rcx+14h]; BugCheckParameter2
0x1400714aa  or      eax, 0FFFFFFFFh
0x1400714ad  lock xadd [rdx], eax
0x1400714b1  dec     eax
0x1400714b3  cmp     cs:UxDebugCheckRefcount, r14b
0x1400714ba  jnz     short loc_1400714E2
0x1400714bc  test    eax, eax
0x1400714be  jnz     short loc_1400714C7
0x1400714c0  xor     edx, edx
0x1400714c2  call    UlpFreeCoupling
0x1400714c7  mov     rax, [rsi+80h]
0x1400714ce  mov     rcx, [rbp+Entry]
0x1400714d2  mov     [rbp+var_18], rax
0x1400714d6  mov     [rsi+80h], r14
0x1400714dd  jmp     loc_1400713F5
0x1400714e2  cmp     eax, 0FFFFFFFFh
0x1400714e5  jg      short loc_1400714BC
0x1400714e7  mov     ecx, 3; BugCheckParameter1
0x1400714ec  movsxd  r9, eax; BugCheckParameter4
0x1400714ef  lea     r8d, [rcx+2]; BugCheckParameter3
0x1400714f3  call    UlBugCheckEx
0x1400714f9  lea     rdx, [rcx+14h]; BugCheckParameter2
0x1400714fd  or      eax, 0FFFFFFFFh
0x140071500  lock xadd [rdx], eax
0x140071504  dec     eax
0x140071506  cmp     cs:UxDebugCheckRefcount, 0
0x14007150d  jnz     short loc_140071527
0x14007150f  test    eax, eax
0x140071511  jnz     short loc_14007151A
0x140071513  xor     edx, edx
0x140071515  call    UlpFreeCoupling
0x14007151a  mov     [rbp+Entry], 0
0x140071522  jmp     loc_140071295
0x140071527  cmp     eax, 0FFFFFFFFh
0x14007152a  jg      short loc_14007150F
0x14007152c  mov     ecx, 3; BugCheckParameter1
0x140071531  movsxd  r9, eax; BugCheckParameter4
0x140071534  lea     r8d, [rcx+7]; BugCheckParameter3
0x140071538  call    UlBugCheckEx
0x14007153e  mov     eax, [rdi+278h]
0x140071544  and     eax, 50h
0x140071547  cmp     al, 50h ; 'P'
0x140071549  jz      loc_140071430
0x14007154f  jmp     loc_140071309
0x140071554  test    r15b, r15b
0x140071557  jz      loc_140071430
0x14007155d  mov     ebx, 0C000020Ch
0x140071562  jmp     loc_140071430
0x140071567  mov     ebx, 0C0000184h
0x14007156c  jmp     loc_140071413
0x140071571  mov     ebx, 0C0000184h
0x140071576  jmp     loc_1400713F5
0x14007157b  mov     edx, 0D2h
0x140071580  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140071587  mov     ecx, 408h
0x14007158c  mov     r9d, ebx
0x14007158f  call    WPP_SF_d
0x140071594  jmp     loc_1400712AB
```
