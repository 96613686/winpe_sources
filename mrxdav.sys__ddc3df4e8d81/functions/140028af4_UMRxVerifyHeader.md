# UMRxVerifyHeader

- ea: `0x140028af4`
- end: `0x140028e1c`
- name: `UMRxVerifyHeader`
- size: `808`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140026f54`
- `0x140027f1c`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140027658`
- `0x140028af4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140028b3a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028b76`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028c60`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028cf9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028da0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028de1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028b3a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028b76`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028c60`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028cf9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028da0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028de1`
- `ntoskrnl!KeSetEvent` at `0x140028d5e`
- `ntoskrnl!KeSetEvent` at `0x140028d5e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140028bad`
- `ntoskrnl!ExAcquireFastMutex` at `0x140028bad`
- `ntoskrnl!ExReleaseFastMutex` at `0x140028ca3`
- `ntoskrnl!ExReleaseFastMutex` at `0x140028d3e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140028d76`
- `ntoskrnl!ExReleaseFastMutex` at `0x140028ca3`
- `ntoskrnl!ExReleaseFastMutex` at `0x140028d3e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140028d76`
- `rdbss!RxMapMidToContext` at `0x140028bc4`
- `rdbss!RxMapMidToContext` at `0x140028bc4`
- `rdbss!RxMapAndDissociateMidFromContext` at `0x140028c94`
- `rdbss!RxMapAndDissociateMidFromContext` at `0x140028c94`
- `rdbss!RxReassociateMid` at `0x140028d2f`
- `rdbss!RxReassociateMid` at `0x140028d2f`

## pseudocode

```c
__int64 __fastcall UMRxVerifyHeader(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  PVOID v4; // rsi
  int v6; // r15d
  int v8; // r14d
  __int64 v10; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax
  PVOID v14; // rax
  unsigned int v15; // esi
  _QWORD *v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rbx
  HANDLE v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // r15
  __int64 v22; // rdi
  HANDLE v23; // rax
  __int64 v24; // rbx
  HANDLE v25; // rax
  __int64 v26; // rbx
  HANDLE v27; // rax
  PVOID ContextPointer; // [rsp+80h] [rbp+8h] BYREF

  v4 = *(PVOID *)a2;
  v6 = *(_DWORD *)(a2 + 8);
  v8 = *(unsigned __int16 *)(a2 + 12);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v10, 63, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      WPP_SF_qqq(v12, 64, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v13, a1, a2);
    }
  }
  ExAcquireFastMutex((PFAST_MUTEX)(a1 + 1320));
  v14 = RxMapMidToContext(*(PRX_MID_ATLAS *)(a1 + 1312), v8);
  ContextPointer = v14;
  if ( v14
    && v14 == v4
    && *((_WORD *)v14 + 210) == (_WORD)v8
    && *((_DWORD *)v14 + 104) == v6
    && a1 == *(_QWORD *)(*((_QWORD *)v14 + 10) + 80LL) )
  {
    *a4 = v14;
    v15 = 0;
    UMRxFinalizeAsyncEngineContext(&ContextPointer);
    v16 = (_QWORD *)(a1 + 1376);
    v17 = *(_QWORD **)(a1 + 1376);
    if ( v17 == (_QWORD *)(a1 + 1376) )
    {
      ContextPointer = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
      {
        v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v19 = PsGetCurrentThreadId();
        WPP_SF_q(v18, 66, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v19);
      }
      RxMapAndDissociateMidFromContext(*(PRX_MID_ATLAS *)(a1 + 1312), v8, &ContextPointer);
      ExReleaseFastMutex((PFAST_MUTEX)(a1 + 1320));
    }
    else
    {
      if ( (_QWORD *)v17[1] != v16 || (v20 = *v17, *(_QWORD **)(*v17 + 8LL) != v17) )
        __fastfail(3u);
      *v16 = v20;
      v21 = v17 - 45;
      *(_QWORD *)(v20 + 8) = v16;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
      {
        v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v23 = PsGetCurrentThreadId();
        WPP_SF_qD(v22, 67, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v23, v8);
      }
      RxReassociateMid(*(PRX_MID_ATLAS *)(a1 + 1312), v8, v21);
      ExReleaseFastMutex((PFAST_MUTEX)(a1 + 1320));
      *((_WORD *)v21 + 210) = v8;
      KeSetEvent((PRKEVENT)(v21 + 49), 0, 0);
    }
  }
  else
  {
    ExReleaseFastMutex((PFAST_MUTEX)(a1 + 1320));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v25 = PsGetCurrentThreadId();
      WPP_SF_q(v24, 65, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v25);
    }
    v15 = -1073741811;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
  {
    v26 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v27 = PsGetCurrentThreadId();
    WPP_SF_qD(v26, 68, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v27, v15);
  }
  return v15;
}

```

## disassembly

```asm
0x140028af4  push    rbx
0x140028af6  push    rbp
0x140028af7  push    rsi
0x140028af8  push    rdi
0x140028af9  push    r12
0x140028afb  push    r13
0x140028afd  push    r14
0x140028aff  push    r15
0x140028b01  sub     rsp, 38h
0x140028b05  mov     rsi, [rdx]
0x140028b08  mov     r13, r9
0x140028b0b  mov     r15d, [rdx+8]
0x140028b0f  mov     rdi, rdx
0x140028b12  movzx   r14d, word ptr [rdx+0Ch]
0x140028b17  mov     rbp, rcx
0x140028b1a  mov     rbx, cs:WPP_GLOBAL_Control
0x140028b21  lea     r12, WPP_GLOBAL_Control
0x140028b28  cmp     rbx, r12
0x140028b2b  jz      short loc_140028BA3
0x140028b2d  test    dword ptr [rbx+2Ch], 800h
0x140028b34  jz      short loc_140028B5D
0x140028b36  mov     rbx, [rbx+18h]
0x140028b3a  call    cs:__imp_PsGetCurrentThreadId
0x140028b41  nop     dword ptr [rax+rax+00h]
0x140028b46  mov     edx, 3Fh ; '?'
0x140028b4b  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028b52  mov     r9, rax
0x140028b55  mov     rcx, rbx
0x140028b58  call    WPP_SF_q
0x140028b5d  mov     rbx, cs:WPP_GLOBAL_Control
0x140028b64  cmp     rbx, r12
0x140028b67  jz      short loc_140028BA3
0x140028b69  test    dword ptr [rbx+2Ch], 200h
0x140028b70  jz      short loc_140028BA3
0x140028b72  mov     rbx, [rbx+18h]
0x140028b76  call    cs:__imp_PsGetCurrentThreadId
0x140028b7d  nop     dword ptr [rax+rax+00h]
0x140028b82  mov     edx, 40h ; '@'
0x140028b87  mov     [rsp+78h+var_50], rdi
0x140028b8c  mov     r9, rax
0x140028b8f  mov     [rsp+78h+var_58], rbp
0x140028b94  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028b9b  mov     rcx, rbx
0x140028b9e  call    WPP_SF_qqq
0x140028ba3  lea     r12, [rbp+528h]
0x140028baa  mov     rcx, r12; FastMutex
0x140028bad  call    cs:__imp_ExAcquireFastMutex
0x140028bb4  nop     dword ptr [rax+rax+00h]
0x140028bb9  mov     rcx, [rbp+520h]; MidAtlas
0x140028bc0  movzx   edx, r14w; Mid
0x140028bc4  call    cs:__imp_RxMapMidToContext
0x140028bcb  nop     dword ptr [rax+rax+00h]
0x140028bd0  mov     [rsp+78h+ContextPointer], rax
0x140028bd8  mov     rcx, rax
0x140028bdb  test    rax, rax
0x140028bde  jz      loc_140028D73
0x140028be4  cmp     rax, rsi
0x140028be7  jnz     loc_140028D73
0x140028bed  cmp     [rax+1A4h], r14w
0x140028bf5  jnz     loc_140028D73
0x140028bfb  cmp     [rax+1A0h], r15d
0x140028c02  jnz     loc_140028D73
0x140028c08  mov     rax, [rax+50h]
0x140028c0c  cmp     rbp, [rax+50h]
0x140028c10  jnz     loc_140028D73
0x140028c16  mov     [r13+0], rcx
0x140028c1a  xor     esi, esi
0x140028c1c  lea     rcx, [rsp+78h+ContextPointer]
0x140028c24  call    UMRxFinalizeAsyncEngineContext
0x140028c29  lea     rcx, [rbp+560h]
0x140028c30  mov     rax, [rcx]
0x140028c33  cmp     rax, rcx
0x140028c36  jnz     short loc_140028CB4
0x140028c38  mov     [rsp+78h+ContextPointer], rsi
0x140028c40  mov     rbx, cs:WPP_GLOBAL_Control
0x140028c47  lea     r13, WPP_GLOBAL_Control
0x140028c4e  cmp     rbx, r13
0x140028c51  jz      short loc_140028C81
0x140028c53  test    dword ptr [rbx+2Ch], 400h
0x140028c5a  jz      short loc_140028C81
0x140028c5c  mov     rbx, [rbx+18h]
0x140028c60  call    cs:__imp_PsGetCurrentThreadId
0x140028c67  nop     dword ptr [rax+rax+00h]
0x140028c6c  lea     edx, [rsi+42h]
0x140028c6f  mov     rcx, rbx
0x140028c72  mov     r9, rax
0x140028c75  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028c7c  call    WPP_SF_q
0x140028c81  mov     rcx, [rbp+520h]; MidAtlas
0x140028c88  lea     r8, [rsp+78h+ContextPointer]; ContextPointer
0x140028c90  movzx   edx, r14w; Mid
0x140028c94  call    cs:__imp_RxMapAndDissociateMidFromContext
0x140028c9b  nop     dword ptr [rax+rax+00h]
0x140028ca0  mov     rcx, r12; FastMutex
0x140028ca3  call    cs:__imp_ExReleaseFastMutex
0x140028caa  nop     dword ptr [rax+rax+00h]
0x140028caf  jmp     loc_140028DC8
0x140028cb4  cmp     [rax+8], rcx
0x140028cb8  jnz     loc_140028D6C
0x140028cbe  mov     rdx, [rax]
0x140028cc1  cmp     [rdx+8], rax
0x140028cc5  jnz     loc_140028D6C
0x140028ccb  mov     [rcx], rdx
0x140028cce  lea     r15, [rax-168h]
0x140028cd5  mov     [rdx+8], rcx
0x140028cd9  mov     rdi, cs:WPP_GLOBAL_Control
0x140028ce0  lea     r13, WPP_GLOBAL_Control
0x140028ce7  cmp     rdi, r13
0x140028cea  jz      short loc_140028D21
0x140028cec  test    dword ptr [rdi+2Ch], 400h
0x140028cf3  jz      short loc_140028D21
0x140028cf5  mov     rdi, [rdi+18h]
0x140028cf9  call    cs:__imp_PsGetCurrentThreadId
0x140028d00  nop     dword ptr [rax+rax+00h]
0x140028d05  mov     edx, 43h ; 'C'
0x140028d0a  mov     dword ptr [rsp+78h+var_58], r14d
0x140028d0f  mov     r9, rax
0x140028d12  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028d19  mov     rcx, rdi
0x140028d1c  call    WPP_SF_qD
0x140028d21  mov     rcx, [rbp+520h]; MidAtlas
0x140028d28  mov     r8, r15; NewContext
0x140028d2b  movzx   edx, r14w; Mid
0x140028d2f  call    cs:__imp_RxReassociateMid
0x140028d36  nop     dword ptr [rax+rax+00h]
0x140028d3b  mov     rcx, r12; FastMutex
0x140028d3e  call    cs:__imp_ExReleaseFastMutex
0x140028d45  nop     dword ptr [rax+rax+00h]
0x140028d4a  lea     rcx, [r15+188h]; Event
0x140028d51  mov     [r15+1A4h], r14w
0x140028d59  xor     r8d, r8d; Wait
0x140028d5c  xor     edx, edx; Increment
0x140028d5e  call    cs:__imp_KeSetEvent
0x140028d65  nop     dword ptr [rax+rax+00h]
0x140028d6a  jmp     short loc_140028DC8
0x140028d6c  mov     ecx, 3
0x140028d71  int     29h; Win8: RtlFailFast(ecx)
0x140028d73  mov     rcx, r12; FastMutex
0x140028d76  call    cs:__imp_ExReleaseFastMutex
0x140028d7d  nop     dword ptr [rax+rax+00h]
0x140028d82  mov     rbx, cs:WPP_GLOBAL_Control
0x140028d89  lea     r13, WPP_GLOBAL_Control
0x140028d90  cmp     rbx, r13
0x140028d93  jz      short loc_140028DC3
0x140028d95  mov     eax, [rbx+2Ch]
0x140028d98  test    al, al
0x140028d9a  jns     short loc_140028DC3
0x140028d9c  mov     rbx, [rbx+18h]
0x140028da0  call    cs:__imp_PsGetCurrentThreadId
0x140028da7  nop     dword ptr [rax+rax+00h]
0x140028dac  mov     edx, 41h ; 'A'
0x140028db1  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028db8  mov     r9, rax
0x140028dbb  mov     rcx, rbx
0x140028dbe  call    WPP_SF_q
0x140028dc3  mov     esi, 0C000000Dh
0x140028dc8  mov     rbx, cs:WPP_GLOBAL_Control
0x140028dcf  cmp     rbx, r13
0x140028dd2  jz      short loc_140028E08
0x140028dd4  test    dword ptr [rbx+2Ch], 800h
0x140028ddb  jz      short loc_140028E08
0x140028ddd  mov     rbx, [rbx+18h]
0x140028de1  call    cs:__imp_PsGetCurrentThreadId
0x140028de8  nop     dword ptr [rax+rax+00h]
0x140028ded  mov     edx, 44h ; 'D'
0x140028df2  mov     dword ptr [rsp+78h+var_58], esi
0x140028df6  mov     r9, rax
0x140028df9  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028e00  mov     rcx, rbx
0x140028e03  call    WPP_SF_qD
0x140028e08  mov     eax, esi
0x140028e0a  add     rsp, 38h
0x140028e0e  pop     r15
0x140028e10  pop     r14
0x140028e12  pop     r13
0x140028e14  pop     r12
0x140028e16  pop     rdi
0x140028e17  pop     rsi
0x140028e18  pop     rbp
0x140028e19  pop     rbx
0x140028e1a  retn
```
