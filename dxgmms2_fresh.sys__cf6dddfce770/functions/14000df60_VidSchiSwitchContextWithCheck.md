# VidSchiSwitchContextWithCheck

- ea: `0x14000df60`
- end: `0x14000e39a`
- name: `VidSchiSwitchContextWithCheck`
- size: `1082`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000f040`

## callees

- `0x14000d298`
- `0x14000d5c0`
- `0x14000df60`
- `0x14000e840`
- `0x140011c60`
- `0x140059030`

## import_xrefs

- `ntoskrnl!RtlClearBitEx` at `0x14000e053`
- `ntoskrnl!RtlClearBitEx` at `0x14000e053`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000e073`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000e073`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x14000e085`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x14000e085`
- `ntoskrnl!RtlAreBitsClearEx` at `0x14000e099`
- `ntoskrnl!RtlAreBitsClearEx` at `0x14000e099`
- `watchdog!WdLogSingleEntry2` at `0x14000e219`
- `watchdog!WdLogSingleEntry2` at `0x14000e302`
- `watchdog!WdLogSingleEntry2` at `0x14000e219`
- `watchdog!WdLogSingleEntry2` at `0x14000e302`
- `HAL!KeQueryPerformanceCounter` at `0x14000e1cd`
- `HAL!KeQueryPerformanceCounter` at `0x14000e2bc`
- `HAL!KeQueryPerformanceCounter` at `0x14000e1cd`
- `HAL!KeQueryPerformanceCounter` at `0x14000e2bc`

## pseudocode

```c
__int64 __fastcall VidSchiSwitchContextWithCheck(__int64 a1)
{
  __int64 v1; // rbp
  unsigned int v3; // r15d
  __int64 v4; // r14
  int v5; // eax
  __int64 v6; // rdx
  int v7; // r12d
  union _LARGE_INTEGER v8; // rbx
  __int64 v9; // rdi
  void (__fastcall *v11)(_QWORD); // rax
  LARGE_INTEGER v12; // r9
  unsigned __int64 v13; // rcx
  __int64 v14; // r8
  void (__fastcall *v15)(_QWORD); // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  LARGE_INTEGER v18; // r9
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rdx
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 96);
  v3 = 1;
  v4 = *(_QWORD *)(v1 + 24);
  if ( *(_DWORD *)(v4 + 3340) || (*(_BYTE *)(v4 + 3364) & 1) != 0 )
    goto LABEL_23;
  if ( (unsigned __int8)VidSchiBlockContextOnPendingFlips(*(_QWORD *)(a1 + 656)) )
  {
    if ( !*(_QWORD *)(a1 + 48) )
    {
      v22 = *(_QWORD *)(a1 + 96);
      v23 = *(_QWORD *)(v22 + 24) + 3848LL;
      v24 = *(_QWORD **)(*(_QWORD *)(v22 + 24) + 3856LL);
      if ( *v24 != v23 )
        __fastfail(3u);
      *(_QWORD *)(a1 + 40) = v23;
      *(_QWORD *)(a1 + 48) = v24;
      *v24 = a1 + 40;
      *(_QWORD *)(v23 + 8) = a1 + 40;
    }
    v16 = 3;
    v17 = 16757;
    goto LABEL_41;
  }
  v5 = *(_DWORD *)(a1 + 652);
  PerformanceFrequency.QuadPart = 0;
  if ( (v5 & 0xF) != 0
    || (*(_DWORD *)(a1 + 112) & 0x10) == 0
    || (v6 = *(_QWORD *)(a1 + 104), *(_BYTE *)(v6 + 212))
    || (v7 = *(_DWORD *)(v1 + 16520), _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 208), 0, 0)) )
  {
LABEL_23:
    VidSchiSwitchContext(a1);
    return v3;
  }
  if ( (unsigned int)VidSchiCheckPreemptionPolicy(a1, &PerformanceFrequency) )
  {
    v3 = 4;
LABEL_18:
    if ( v7 == -1 )
      goto LABEL_23;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 656) + 80LL) & 0x10) == 0 )
    {
      if ( *(_DWORD *)(v1 + 16520) != -1 )
      {
        v11 = *(void (__fastcall **)(_QWORD))(v4 + 3408);
        if ( v11 )
          v11(*(_QWORD *)(v4 + 3448));
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 656) + 80LL) |= 0x10u;
    }
    if ( *(_BYTE *)(v1 + 16524) )
      goto LABEL_23;
    v16 = 8;
    v17 = 16925;
LABEL_41:
    VidSchiUpdateContextStatus(a1, v16, v17);
    return 3;
  }
  v8 = PerformanceFrequency;
  if ( PerformanceFrequency.QuadPart != -1 )
  {
    PerformanceFrequency.QuadPart = 0;
    v18 = KeQueryPerformanceCounter(&PerformanceFrequency);
    if ( is_mul_ok(v18.QuadPart, 0x989680u) )
      v19 = (unsigned __int64)v18.QuadPart
          * (unsigned __int128)0x989680uLL
          / (unsigned __int64)PerformanceFrequency.QuadPart;
    else
      v19 = 10000000 * (v18.QuadPart / (unsigned __int64)PerformanceFrequency.QuadPart)
          + 10000000 * (v18.QuadPart % (unsigned __int64)PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart;
    v20 = v19 + v8.QuadPart;
    v21 = *(_QWORD *)(v1 + 96);
    *(_QWORD *)(v1 + 136) = v21;
    *(_QWORD *)(v1 + 128) = v20;
    WdLogSingleEntry2(4, *(unsigned __int16 *)(v1 + 4), v21);
    WdLogGlobalForLineNumber = 16807;
  }
  v9 = *(_QWORD *)(v1 + 8LL * *(unsigned int *)(v1 + 1584) + 1592);
  if ( v8.QuadPart == -1 && !*(_DWORD *)(v1 + 3032) && (*(_DWORD *)(v1 + 3012) > 1u || v9 && a1 != v9) )
  {
    PerformanceFrequency.QuadPart = 0;
    v12 = KeQueryPerformanceCounter(&PerformanceFrequency);
    if ( is_mul_ok(v12.QuadPart, 0x989680u) )
      v13 = (unsigned __int64)v12.QuadPart
          * (unsigned __int128)0x989680uLL
          / (unsigned __int64)PerformanceFrequency.QuadPart;
    else
      v13 = 10000000 * (v12.QuadPart / (unsigned __int64)PerformanceFrequency.QuadPart)
          + 10000000 * (v12.QuadPart % (unsigned __int64)PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart;
    v14 = *(_QWORD *)(v1 + 96);
    *(_QWORD *)(v1 + 128) = v13 + *(_QWORD *)(a1 + 488);
    *(_QWORD *)(v1 + 144) = v14;
    WdLogSingleEntry2(4, *(unsigned __int16 *)(v1 + 4), v14);
    WdLogGlobalForLineNumber = 16834;
  }
  if ( *(int *)(v1 + 3008) > 0
    && *(_DWORD *)(v1 + 3024) < *(_DWORD *)(v4 + 252)
    && !*(_DWORD *)(v1 + 3032)
    && (!v9
     || !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v9 + 96) + 24LL) + 7942LL)
     || *(_DWORD *)(v9 + 412) <= *(_DWORD *)(a1 + 412)) )
  {
    goto LABEL_18;
  }
  RtlClearBitEx(v4 + 632, *(unsigned __int16 *)(v1 + 4));
  RtlCopyBitMapEx(v4 + 584, v4 + 680, 0);
  RtlIntersectBitMapsEx(v4 + 680, v4 + 632);
  if ( !(unsigned __int8)RtlAreBitsClearEx(v4 + 680, 0, *(_QWORD *)(v4 + 680)) )
    return 3;
  if ( v7 != -1 && (*(_DWORD *)(*(_QWORD *)(a1 + 656) + 80LL) & 0x10) == 0 )
  {
    if ( *(_DWORD *)(v1 + 16520) != -1 )
    {
      v15 = *(void (__fastcall **)(_QWORD))(v4 + 3408);
      if ( v15 )
        v15(*(_QWORD *)(v4 + 3448));
    }
    *(_DWORD *)(*(_QWORD *)(a1 + 656) + 80LL) |= 0x10u;
  }
  return 2;
}

```

## disassembly

```asm
0x14000df60  mov     [rsp+arg_10], rbx
0x14000df65  push    rbp
0x14000df66  push    rsi
0x14000df67  push    rdi
0x14000df68  push    r12
0x14000df6a  push    r13
0x14000df6c  push    r14
0x14000df6e  push    r15
0x14000df70  sub     rsp, 20h
0x14000df74  mov     rbp, [rcx+60h]
0x14000df78  xor     r13d, r13d
0x14000df7b  mov     rsi, rcx
0x14000df7e  mov     r15d, 1
0x14000df84  mov     r14, [rbp+18h]
0x14000df88  cmp     [r14+0D0Ch], r13d
0x14000df8f  jnz     loc_14000E127
0x14000df95  test    [r14+0D24h], r15b
0x14000df9c  jnz     loc_14000E127
0x14000dfa2  mov     rcx, [rcx+290h]
0x14000dfa9  call    VidSchiBlockContextOnPendingFlips
0x14000dfae  test    al, al
0x14000dfb0  jnz     loc_14000E348
0x14000dfb6  mov     eax, [rsi+28Ch]
0x14000dfbc  mov     qword ptr [rsp+58h+PerformanceFrequency], r13
0x14000dfc1  test    al, 0Fh
0x14000dfc3  jnz     loc_14000E127
0x14000dfc9  mov     eax, [rsi+70h]
0x14000dfcc  test    al, 10h
0x14000dfce  jz      loc_14000E127
0x14000dfd4  mov     rdx, [rsi+68h]
0x14000dfd8  cmp     [rdx+0D4h], r13b
0x14000dfdf  jnz     loc_14000E127
0x14000dfe5  mov     r12d, [rbp+4088h]
0x14000dfec  mov     ecx, r13d
0x14000dfef  xor     eax, eax
0x14000dff1  lock cmpxchg [rdx+0D0h], ecx
0x14000dff9  jnz     loc_14000E127
0x14000dfff  lea     rdx, [rsp+58h+PerformanceFrequency]
0x14000e004  mov     rcx, rsi
0x14000e007  call    VidSchiCheckPreemptionPolicy
0x14000e00c  test    eax, eax
0x14000e00e  jnz     loc_14000E38F
0x14000e014  mov     rbx, qword ptr [rsp+58h+PerformanceFrequency]
0x14000e019  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000e01d  jnz     loc_14000E2B2
0x14000e023  mov     eax, [rbp+630h]
0x14000e029  mov     rdi, [rbp+rax*8+638h]
0x14000e031  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000e035  jz      loc_14000E19B
0x14000e03b  mov     eax, [rbp+0BC0h]
0x14000e041  test    eax, eax
0x14000e043  jg      short loc_14000E0B4
0x14000e045  movzx   edx, word ptr [rbp+4]
0x14000e049  lea     rbx, [r14+278h]
0x14000e050  mov     rcx, rbx
0x14000e053  call    cs:__imp_RtlClearBitEx
0x14000e05a  nop     dword ptr [rax+rax+00h]
0x14000e05f  lea     rdi, [r14+2A8h]
0x14000e066  xor     r8d, r8d
0x14000e069  mov     rdx, rdi
0x14000e06c  lea     rcx, [r14+248h]
0x14000e073  call    cs:__imp_RtlCopyBitMapEx
0x14000e07a  nop     dword ptr [rax+rax+00h]
0x14000e07f  mov     rdx, rbx
0x14000e082  mov     rcx, rdi
0x14000e085  call    cs:__imp_RtlIntersectBitMapsEx
0x14000e08c  nop     dword ptr [rax+rax+00h]
0x14000e091  mov     r8, [rdi]
0x14000e094  xor     edx, edx
0x14000e096  mov     rcx, rdi
0x14000e099  call    cs:__imp_RtlAreBitsClearEx
0x14000e0a0  nop     dword ptr [rax+rax+00h]
0x14000e0a5  test    al, al
0x14000e0a7  jnz     loc_14000E162
0x14000e0ad  mov     eax, 3
0x14000e0b2  jmp     short loc_14000E132
0x14000e0b4  mov     ecx, [r14+0FCh]
0x14000e0bb  mov     eax, [rbp+0BD0h]
0x14000e0c1  cmp     eax, ecx
0x14000e0c3  jnb     short loc_14000E045
0x14000e0c5  cmp     [rbp+0BD8h], r13d
0x14000e0cc  jnz     loc_14000E045
0x14000e0d2  test    rdi, rdi
0x14000e0d5  jz      short loc_14000E0EC
0x14000e0d7  mov     rax, [rdi+60h]
0x14000e0db  mov     rcx, [rax+18h]
0x14000e0df  cmp     [rcx+1F06h], r13b
0x14000e0e6  jnz     loc_14000E29B
0x14000e0ec  or      r8d, 0FFFFFFFFh
0x14000e0f0  cmp     r12d, r8d
0x14000e0f3  jz      short loc_14000E127
0x14000e0f5  mov     rax, [rsi+290h]
0x14000e0fc  mov     edx, [rax+50h]
0x14000e0ff  test    dl, 10h
0x14000e102  jnz     short loc_14000E11A
0x14000e104  mov     edx, [rbp+4088h]
0x14000e10a  cmp     edx, r8d
0x14000e10d  jnz     short loc_14000E148
0x14000e10f  mov     rax, [rsi+290h]
0x14000e116  or      dword ptr [rax+50h], 10h
0x14000e11a  cmp     [rbp+408Ch], r13b
0x14000e121  jz      loc_14000E255
0x14000e127  mov     rcx, rsi
0x14000e12a  call    VidSchiSwitchContext
0x14000e12f  mov     eax, r15d
0x14000e132  mov     rbx, [rsp+58h+arg_10]
0x14000e137  add     rsp, 20h
0x14000e13b  pop     r15
0x14000e13d  pop     r14
0x14000e13f  pop     r13
0x14000e141  pop     r12
0x14000e143  pop     rdi
0x14000e144  pop     rsi
0x14000e145  pop     rbp
0x14000e146  retn
0x14000e148  mov     rax, [r14+0D50h]
0x14000e14f  test    rax, rax
0x14000e152  jz      short loc_14000E10F
0x14000e154  mov     rcx, [r14+0D78h]
0x14000e15b  call    _guard_dispatch_icall
0x14000e160  jmp     short loc_14000E10F
0x14000e162  or      r8d, 0FFFFFFFFh
0x14000e166  cmp     r12d, r8d
0x14000e169  jz      short loc_14000E194
0x14000e16b  mov     rax, [rsi+290h]
0x14000e172  mov     ecx, [rax+50h]
0x14000e175  test    cl, 10h
0x14000e178  jnz     short loc_14000E194
0x14000e17a  mov     edx, [rbp+4088h]
0x14000e180  cmp     edx, r8d
0x14000e183  jnz     loc_14000E234
0x14000e189  mov     rax, [rsi+290h]
0x14000e190  or      dword ptr [rax+50h], 10h
0x14000e194  mov     eax, 2
0x14000e199  jmp     short loc_14000E132
0x14000e19b  cmp     [rbp+0BD8h], r13d
0x14000e1a2  jnz     loc_14000E03B
0x14000e1a8  cmp     [rbp+0BC4h], r15d
0x14000e1af  ja      short loc_14000E1C3
0x14000e1b1  test    rdi, rdi
0x14000e1b4  jz      loc_14000E03B
0x14000e1ba  cmp     rsi, rdi
0x14000e1bd  jz      loc_14000E03B
0x14000e1c3  lea     rcx, [rsp+58h+PerformanceFrequency]; PerformanceFrequency
0x14000e1c8  mov     qword ptr [rsp+58h+PerformanceFrequency], r13
0x14000e1cd  call    cs:__imp_KeQueryPerformanceCounter
0x14000e1d4  nop     dword ptr [rax+rax+00h]
0x14000e1d9  mov     r8, qword ptr [rsp+58h+PerformanceFrequency]
0x14000e1de  mov     r9, rax
0x14000e1e1  mov     eax, 989680h
0x14000e1e6  mul     r9
0x14000e1e9  test    rdx, rdx
0x14000e1ec  jnz     short loc_14000E26D
0x14000e1ee  div     r8
0x14000e1f1  mov     rcx, rax
0x14000e1f4  mov     rdx, [rsi+1E8h]
0x14000e1fb  mov     r8, [rbp+60h]
0x14000e1ff  add     rdx, rcx
0x14000e202  mov     [rbp+80h], rdx
0x14000e209  mov     [rbp+90h], r8
0x14000e210  movzx   edx, word ptr [rbp+4]
0x14000e214  mov     ecx, 4
0x14000e219  call    cs:__imp_WdLogSingleEntry2
0x14000e220  nop     dword ptr [rax+rax+00h]
0x14000e225  mov     cs:WdLogGlobalForLineNumber, 41C2h
0x14000e22f  jmp     loc_14000E03B
0x14000e234  mov     rax, [r14+0D50h]
0x14000e23b  test    rax, rax
0x14000e23e  jz      loc_14000E189
0x14000e244  mov     rcx, [r14+0D78h]
0x14000e24b  call    _guard_dispatch_icall
0x14000e250  jmp     loc_14000E189
0x14000e255  mov     edx, 8
0x14000e25a  mov     r8d, 421Dh
0x14000e260  mov     rcx, rsi
0x14000e263  call    VidSchiUpdateContextStatus
0x14000e268  jmp     loc_14000E0AD
0x14000e26d  xor     edx, edx
0x14000e26f  mov     rax, r9
0x14000e272  div     r8
0x14000e275  imul    rax, rdx, 989680h
0x14000e27c  xor     edx, edx
0x14000e27e  div     r8
0x14000e281  xor     edx, edx
0x14000e283  mov     rcx, rax
0x14000e286  mov     rax, r9
0x14000e289  div     r8
0x14000e28c  imul    rdx, rax, 989680h
0x14000e293  add     rcx, rdx
0x14000e296  jmp     loc_14000E1F4
0x14000e29b  mov     eax, [rsi+19Ch]
0x14000e2a1  cmp     [rdi+19Ch], eax
0x14000e2a7  jbe     loc_14000E0EC
0x14000e2ad  jmp     loc_14000E045
0x14000e2b2  lea     rcx, [rsp+58h+PerformanceFrequency]; PerformanceFrequency
0x14000e2b7  mov     qword ptr [rsp+58h+PerformanceFrequency], r13
0x14000e2bc  call    cs:__imp_KeQueryPerformanceCounter
0x14000e2c3  nop     dword ptr [rax+rax+00h]
0x14000e2c8  mov     rcx, qword ptr [rsp+58h+PerformanceFrequency]
0x14000e2cd  mov     r9, rax
0x14000e2d0  mov     eax, 989680h
0x14000e2d5  mul     r9
0x14000e2d8  test    rdx, rdx
0x14000e2db  jnz     short loc_14000E31D
0x14000e2dd  div     rcx
0x14000e2e0  mov     r8, rax
0x14000e2e3  lea     rax, [r8+rbx]
0x14000e2e7  mov     r8, [rbp+60h]
0x14000e2eb  mov     [rbp+88h], r8
0x14000e2f2  mov     [rbp+80h], rax
0x14000e2f9  movzx   edx, word ptr [rbp+4]
0x14000e2fd  mov     ecx, 4
0x14000e302  call    cs:__imp_WdLogSingleEntry2
0x14000e309  nop     dword ptr [rax+rax+00h]
0x14000e30e  mov     cs:WdLogGlobalForLineNumber, 41A7h
0x14000e318  jmp     loc_14000E023
0x14000e31d  xor     edx, edx
0x14000e31f  mov     rax, r9
0x14000e322  div     rcx
0x14000e325  imul    rax, rdx, 989680h
0x14000e32c  xor     edx, edx
0x14000e32e  div     rcx
0x14000e331  xor     edx, edx
0x14000e333  mov     r8, rax
0x14000e336  mov     rax, r9
0x14000e339  div     rcx
0x14000e33c  imul    rcx, rax, 989680h
0x14000e343  add     r8, rcx
0x14000e346  jmp     short loc_14000E2E3
0x14000e348  cmp     [rsi+30h], r13
0x14000e34c  jnz     short loc_14000E378
0x14000e34e  mov     rax, [rsi+60h]
0x14000e352  mov     rcx, [rax+18h]
0x14000e356  add     rcx, 0F08h
0x14000e35d  mov     rdx, [rcx+8]
0x14000e361  cmp     [rdx], rcx
0x14000e364  jnz     short loc_14000E388
0x14000e366  lea     rax, [rsi+28h]
0x14000e36a  mov     [rax], rcx
0x14000e36d  mov     [rax+8], rdx
0x14000e371  mov     [rdx], rax
0x14000e374  mov     [rcx+8], rax
0x14000e378  mov     edx, 3
0x14000e37d  mov     r8d, 4175h
0x14000e383  jmp     loc_14000E260
0x14000e388  mov     ecx, 3
0x14000e38d  int     29h; Win8: RtlFailFast(ecx)
0x14000e38f  mov     r15d, 4
0x14000e395  jmp     loc_14000E0EC
```
