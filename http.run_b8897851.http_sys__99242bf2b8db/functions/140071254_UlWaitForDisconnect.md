# UlWaitForDisconnect

- ea: `0x140071254`
- end: `0x1400715b9`
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
- `0x14003ded0`
- `0x1400511a8`
- `0x140051268`
- `0x1400705f0`
- `0x140071254`
- `0x1400715c0`
- `0x1401c64e4`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14007134c`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14007134c`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140071438`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140071438`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071427`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071444`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071461`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071427`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071444`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071461`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007141b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140071455`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007141b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140071455`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400712f7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071398`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400712f7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071398`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400712df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071337`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071382`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400712df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071337`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071382`

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
0x140071254  push    rbp
0x140071256  push    rbx
0x140071257  push    rsi
0x140071258  push    rdi
0x140071259  push    r12
0x14007125b  push    r13
0x14007125d  push    r14
0x14007125f  push    r15
0x140071261  mov     rbp, rsp
0x140071264  sub     rsp, 58h
0x140071268  mov     r13, [rcx+8]
0x14007126c  mov     rsi, r9
0x14007126f  movzx   r15d, r8b
0x140071273  mov     rdi, rdx
0x140071276  mov     r14, rcx
0x140071279  mov     [rbp+Entry], 0
0x140071281  mov     [rbp+var_18], 0
0x140071289  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140071290  jnz     loc_140071494
0x140071296  mov     rdx, rsi
0x140071299  lea     rcx, [rbp+var_18]
0x14007129d  call    UlAllocateGrip
0x1400712a2  mov     ebx, eax
0x1400712a4  test    eax, eax
0x1400712a6  jns     short loc_1400712DF
0x1400712a8  mov     rcx, [rbp+Entry]; Entry
0x1400712ac  test    rcx, rcx
0x1400712af  jnz     loc_140071519
0x1400712b5  lea     rcx, [rbp+var_18]
0x1400712b9  call    UlFreeGrip
0x1400712be  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400712c5  jnz     loc_14007159B
0x1400712cb  mov     eax, ebx
0x1400712cd  add     rsp, 58h
0x1400712d1  pop     r15
0x1400712d3  pop     r14
0x1400712d5  pop     r13
0x1400712d7  pop     r12
0x1400712d9  pop     rdi
0x1400712da  pop     rsi
0x1400712db  pop     rbx
0x1400712dc  pop     rbp
0x1400712dd  retn
0x1400712df  call    cs:__imp_KeEnterCriticalRegion
0x1400712e6  nop     dword ptr [rax+rax+00h]
0x1400712eb  lea     r12, [rdi+240h]
0x1400712f2  xor     edx, edx
0x1400712f4  mov     rcx, r12
0x1400712f7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400712fe  nop     dword ptr [rax+rax+00h]
0x140071303  mov     rax, [rdi+238h]
0x14007130a  test    rax, rax
0x14007130d  jz      loc_140071472
0x140071313  cmp     [rax+6D0h], r14
0x14007131a  jnz     loc_140071472
0x140071320  test    r15b, r15b
0x140071323  jnz     loc_14007155E
0x140071329  mov     eax, [rdi+278h]
0x14007132f  test    al, 8
0x140071331  jnz     loc_140071574
0x140071337  call    cs:__imp_KeEnterCriticalRegion
0x14007133e  nop     dword ptr [rax+rax+00h]
0x140071343  mov     rcx, [r13+118h]
0x14007134a  xor     edx, edx
0x14007134c  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x140071353  nop     dword ptr [rax+rax+00h]
0x140071358  cmp     byte ptr [r14+5], 0
0x14007135d  mov     r15, rax
0x140071360  jnz     loc_140071587
0x140071366  lea     r8, [rbp+Entry]
0x14007136a  mov     rdx, r13
0x14007136d  mov     rcx, rdi
0x140071370  call    UlpOpenCoupling
0x140071375  xor     r14d, r14d
0x140071378  mov     ebx, eax
0x14007137a  test    eax, eax
0x14007137c  js      loc_140071433
0x140071382  call    cs:__imp_KeEnterCriticalRegion
0x140071389  nop     dword ptr [rax+rax+00h]
0x14007138e  mov     rcx, [rbp+Entry]
0x140071392  xor     edx, edx
0x140071394  add     rcx, 48h ; 'H'
0x140071398  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14007139f  nop     dword ptr [rax+rax+00h]
0x1400713a4  mov     rcx, [rbp+Entry]
0x1400713a8  cmp     [rcx+50h], r14b
0x1400713ac  jnz     loc_140071591
0x1400713b2  mov     [rsi+78h], rcx
0x1400713b6  lea     rdx, [rcx+14h]; BugCheckParameter2
0x1400713ba  lea     eax, [r14+1]
0x1400713be  lock xadd [rdx], eax
0x1400713c2  inc     eax
0x1400713c4  cmp     cs:UxDebugCheckRefcount, r14b
0x1400713cb  jnz     loc_140071479
0x1400713d1  mov     rcx, [rbp+var_18]
0x1400713d5  lea     r8, UlpCancelWaitForDisconnectIrp
0x1400713dc  mov     rdx, rsi
0x1400713df  mov     [rbp+var_18], r14
0x1400713e3  mov     rax, [rcx+50h]
0x1400713e7  mov     [rax+80h], rcx
0x1400713ee  mov     rcx, [rbp+Entry]
0x1400713f2  sub     rcx, 0FFFFFFFFFFFFFF80h; SpinLock
0x1400713f6  call    UlSiqEnqueueIrp
0x1400713fb  mov     rcx, [rbp+Entry]; Entry
0x1400713ff  mov     ebx, eax
0x140071401  test    eax, eax
0x140071403  js      loc_1400714C2
0x140071409  or      dword ptr [rdi+278h], 20h
0x140071410  mov     ebx, 103h
0x140071415  add     rcx, 48h ; 'H'
0x140071419  xor     edx, edx
0x14007141b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140071422  nop     dword ptr [rax+rax+00h]
0x140071427  call    cs:__imp_KeLeaveCriticalRegion
0x14007142e  nop     dword ptr [rax+rax+00h]
0x140071433  xor     edx, edx
0x140071435  mov     rcx, r15
0x140071438  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14007143f  nop     dword ptr [rax+rax+00h]
0x140071444  call    cs:__imp_KeLeaveCriticalRegion
0x14007144b  nop     dword ptr [rax+rax+00h]
0x140071450  xor     edx, edx
0x140071452  mov     rcx, r12
0x140071455  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14007145c  nop     dword ptr [rax+rax+00h]
0x140071461  call    cs:__imp_KeLeaveCriticalRegion
0x140071468  nop     dword ptr [rax+rax+00h]
0x14007146d  jmp     loc_1400712A8
0x140071472  mov     ebx, 0C0000084h
0x140071477  jmp     short loc_140071450
0x140071479  cmp     eax, 0FFFFFFFFh
0x14007147c  jg      loc_1400713D1
0x140071482  mov     ecx, 3; BugCheckParameter1
0x140071487  movsxd  r9, eax; BugCheckParameter4
0x14007148a  lea     r8d, [rcx+2]; BugCheckParameter3
0x14007148e  call    UlBugCheckEx
0x140071494  test    rdi, rdi
0x140071497  jz      short loc_1400714BE
0x140071499  mov     rcx, [rdx+30h]
0x14007149d  mov     [rsp+58h+var_20], rsi
0x1400714a2  mov     r9, r14
0x1400714a5  mov     [rsp+58h+var_28], r15d
0x1400714aa  mov     [rsp+58h+var_30], rcx
0x1400714af  mov     [rsp+58h+var_38], rdi
0x1400714b4  call    WPP_SF_qqilq
0x1400714b9  jmp     loc_140071296
0x1400714be  xor     ecx, ecx
0x1400714c0  jmp     short loc_14007149D
0x1400714c2  mov     [rsi+78h], r14
0x1400714c6  lea     rdx, [rcx+14h]; BugCheckParameter2
0x1400714ca  or      eax, 0FFFFFFFFh
0x1400714cd  lock xadd [rdx], eax
0x1400714d1  dec     eax
0x1400714d3  cmp     cs:UxDebugCheckRefcount, r14b
0x1400714da  jnz     short loc_140071502
0x1400714dc  test    eax, eax
0x1400714de  jnz     short loc_1400714E7
0x1400714e0  xor     edx, edx
0x1400714e2  call    UlpFreeCoupling
0x1400714e7  mov     rax, [rsi+80h]
0x1400714ee  mov     rcx, [rbp+Entry]
0x1400714f2  mov     [rbp+var_18], rax
0x1400714f6  mov     [rsi+80h], r14
0x1400714fd  jmp     loc_140071415
0x140071502  cmp     eax, 0FFFFFFFFh
0x140071505  jg      short loc_1400714DC
0x140071507  mov     ecx, 3; BugCheckParameter1
0x14007150c  movsxd  r9, eax; BugCheckParameter4
0x14007150f  lea     r8d, [rcx+2]; BugCheckParameter3
0x140071513  call    UlBugCheckEx
0x140071519  lea     rdx, [rcx+14h]; BugCheckParameter2
0x14007151d  or      eax, 0FFFFFFFFh
0x140071520  lock xadd [rdx], eax
0x140071524  dec     eax
0x140071526  cmp     cs:UxDebugCheckRefcount, 0
0x14007152d  jnz     short loc_140071547
0x14007152f  test    eax, eax
0x140071531  jnz     short loc_14007153A
0x140071533  xor     edx, edx
0x140071535  call    UlpFreeCoupling
0x14007153a  mov     [rbp+Entry], 0
0x140071542  jmp     loc_1400712B5
0x140071547  cmp     eax, 0FFFFFFFFh
0x14007154a  jg      short loc_14007152F
0x14007154c  mov     ecx, 3; BugCheckParameter1
0x140071551  movsxd  r9, eax; BugCheckParameter4
0x140071554  lea     r8d, [rcx+7]; BugCheckParameter3
0x140071558  call    UlBugCheckEx
0x14007155e  mov     eax, [rdi+278h]
0x140071564  and     eax, 50h
0x140071567  cmp     al, 50h ; 'P'
0x140071569  jz      loc_140071450
0x14007156f  jmp     loc_140071329
0x140071574  test    r15b, r15b
0x140071577  jz      loc_140071450
0x14007157d  mov     ebx, 0C000020Ch
0x140071582  jmp     loc_140071450
0x140071587  mov     ebx, 0C0000184h
0x14007158c  jmp     loc_140071433
0x140071591  mov     ebx, 0C0000184h
0x140071596  jmp     loc_140071415
0x14007159b  mov     edx, 0D2h
0x1400715a0  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400715a7  mov     ecx, 408h
0x1400715ac  mov     r9d, ebx
0x1400715af  call    WPP_SF_d
0x1400715b4  jmp     loc_1400712CB
```
