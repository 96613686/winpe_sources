# UlReceiveHttpRequest

- ea: `0x14003f1b0`
- end: `0x14003fa7e`
- name: `UlReceiveHttpRequest`
- size: `2254`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: ``

## callers

- `0x14003a870`
- `0x140081dc0`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x14001a6d0`
- `0x14001a750`
- `0x14003c144`
- `0x14003ec40`
- `0x14003f1b0`
- `0x140041340`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4e4c`
- `0x1401c4eb4`
- `0x1401c5068`
- `0x1401c53b0`
- `0x1401c5480`
- `0x1401cfa20`
- `0x1401da310`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14003f21e`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14003f21e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003f267`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003f649`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003f267`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003f649`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f273`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f41c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f613`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f638`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f655`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f826`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f84b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f273`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f41c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f613`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f638`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f655`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f826`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f84b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f410`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f607`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f62c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f81a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f83f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f410`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f607`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f62c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f81a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f83f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f3b4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f4dd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f506`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f3b4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f4dd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f506`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f209`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f39f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f4c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f4e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f209`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f39f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f4c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f4e9`

## pseudocode

```c
__int64 __fastcall UlReceiveHttpRequest(unsigned __int64 a1, __int64 a2, ULONG_PTR a3, IRP *a4)
{
  int v6; // esi
  unsigned __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // r15
  unsigned int v10; // eax
  unsigned int v11; // edi
  __int64 v13; // rsi
  __int64 v14; // r9
  unsigned __int64 v15; // r8
  unsigned __int8 v16; // r15
  __int64 v17; // r15
  __int64 v18; // r12
  __int64 v19; // r15
  ULONG_PTR v20; // rdx
  int v21; // r12d
  int v22; // r8d
  __int64 v23; // rdi
  __int64 v24; // rdx
  int v25; // r8d
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // r8
  int v29; // eax
  unsigned __int8 v30; // di
  ULONG_PTR v31; // rdx
  int v32; // r13d
  ULONG_PTR v33; // rdx
  int v34; // r12d
  int v35; // eax
  __int64 v36; // rax
  ULONG_PTR v37; // rdx
  int v38; // eax
  int v39; // [rsp+20h] [rbp-40h]
  int v40; // [rsp+28h] [rbp-38h]
  int v41; // [rsp+30h] [rbp-30h]
  unsigned int v42; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v43; // [rsp+54h] [rbp-Ch] BYREF
  __int64 v44; // [rsp+58h] [rbp-8h] BYREF
  __int64 v45; // [rsp+A0h] [rbp+40h] BYREF

  v44 = 0;
  v6 = a2;
  v7 = a1;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    v41 = (int)a4;
    v40 = a3;
    v39 = a2;
    WPP_SF_iLqq(a1, a2, a3, a1);
  }
  if ( *(_DWORD *)(a3 + 40) == 4 && v6 )
  {
    v11 = -1073741811;
    goto LABEL_8;
  }
  if ( v7 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qq(1033, 10, WPP_3bf590e843a03617467a72dc4e459b29_Traceguids, v7, a3);
    v13 = 0;
    LODWORD(v45) = 0;
    v43 = 0;
    v42 = 0;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_iLLqqq(a1, a2, a3, v7, v39, v40, v41);
    v14 = (unsigned int)v7 >> 28;
    if ( (_DWORD)v14 != 4 )
    {
      if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
        WPP_SF_d(521, 14, WPP_02f89a7cef4b3153cc79135fcb4f2711_Traceguids, v14);
      goto LABEL_32;
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_iqqq(a1, a2, a3, v7, &v43, &v45, &v42);
    LODWORD(v45) = 0;
    v15 = HIDWORD(v7);
    v42 = 0;
    v43 = WORD2(v7) & 0xFFF;
    if ( v43 >= UxMaximumNumberOfProcessors )
    {
      if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
        WPP_SF_(521, 11, WPP_6218f2abddb13899518e42ce65335ae2_Traceguids);
    }
    else
    {
      a2 = (HIDWORD(v7) >> 12) & 0xFFF;
      a1 = (unsigned __int64)(WORD2(v7) & 0xFFF) << 6;
      LODWORD(v45) = a2;
      if ( (unsigned int)a2 < *(_DWORD *)((char *)UxOpaqueIdTable + a1 + 40) )
      {
        v15 = HIBYTE(HIDWORD(v7));
        v16 = 1;
        v42 = HIBYTE(HIDWORD(v7));
LABEL_23:
        if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
          WPP_SF_lLLL(a1, a2, v15, v16, v43, v45, v42);
        if ( v16 )
        {
          v17 = 48LL * v42
              + *(_QWORD *)(*((_QWORD *)UxOpaqueIdTable + 8 * (unsigned __int64)v43 + 2) + 8LL * (unsigned int)v45);
          KeEnterCriticalRegion();
          v18 = v17 + 32;
          ExAcquirePushLockExclusiveEx(v17 + 32, 0);
          if ( (*(_DWORD *)(v17 + 40) & 0xF0000000) == 0x30000000 )
          {
            v19 = *(_QWORD *)v17;
            if ( (*(_DWORD *)(v19 + 32) & 0xF0000000) == 0x40000000
              && (((unsigned int)v7 ^ *(_DWORD *)(v19 + 32)) & 0xFFFFFFF) == 0
              && (unsigned __int8)UlValidateHttpRequestFromId(*(_QWORD *)(v19 + 24), a3) )
            {
              v13 = *(_QWORD *)(v19 + 24);
              UlReferenceHttpRequestFromId(v13);
            }
          }
          ExReleasePushLockExclusiveEx(v18, 0);
          KeLeaveCriticalRegion();
        }
LABEL_32:
        if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
        {
          WPP_SF_q(1033, 15, WPP_02f89a7cef4b3153cc79135fcb4f2711_Traceguids, v13);
          if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
          {
            if ( v13 )
              v36 = *(_QWORD *)(v13 + 64);
            else
              v36 = 0;
            WPP_SF_qq(1033, 11, WPP_3bf590e843a03617467a72dc4e459b29_Traceguids, v13, v36);
          }
        }
        v44 = v13;
        if ( v13 )
        {
          UlStopRequestQueueTimer(v13);
          a4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
          UlCopyRequestToIrp(v44, a4, a3, 0, 0);
          v20 = v44 + 48;
          v21 = _InterlockedDecrement((volatile signed __int32 *)(v44 + 48));
          if ( UxDebugCheckRefcount && v21 <= -1 )
            UlBugCheckEx(3u, v20, 0xBu, v21);
          if ( !v21 )
            UlpQueueFreeHttpRequest(v44);
          v44 = 0;
          v11 = 259;
        }
        else
        {
          v11 = -1073741254;
        }
        goto LABEL_8;
      }
      if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
      {
        WPP_SF_(521, 12, WPP_6218f2abddb13899518e42ce65335ae2_Traceguids);
        v16 = 0;
        goto LABEL_23;
      }
    }
    v16 = 0;
    goto LABEL_23;
  }
  v8 = *(_QWORD *)(a3 + 8);
  KeEnterCriticalRegion();
  v9 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v8 + 280), 0);
  if ( *(_BYTE *)(a3 + 4) )
  {
    v11 = -1073741816;
  }
  else
  {
    while ( 1 )
    {
      v10 = UlpRetrieveRequest(v8, a3, a4, &v44);
      v11 = v10;
      if ( v10 == 259 )
        break;
      if ( v10 == -1073741738 )
      {
        v11 = 259;
        break;
      }
      if ( v10 == -1073741536 )
        break;
      if ( v10 )
      {
        v11 = -1073741823;
        break;
      }
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v44 + 1704, 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(*(_QWORD *)(v44 + 1712) + 72LL, 0);
      v23 = v44;
      v24 = *(_QWORD *)(v44 + 1712);
      v45 = v24;
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      {
        WPP_SF_qqqL(1032, 183, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v44, *(_QWORD *)(v44 + 64), a3, 1);
        v24 = v45;
      }
      if ( *(_BYTE *)(v24 + 80) && (BYTE10(xmmword_1401A2C90) & 0x40) != 0 )
      {
        WPP_SF_qLLqqZq(
          *(_QWORD *)(a3 + 8),
          v24,
          v22,
          v23,
          *(_DWORD *)(v23 + 1736),
          *(_DWORD *)(v23 + 1740),
          a3,
          *(_QWORD *)(a3 + 8),
          *(_QWORD *)(a3 + 8) + 160LL,
          v24);
        LODWORD(v24) = v45;
      }
      v25 = *(_DWORD *)(v23 + 1736);
      if ( v25 == 1 )
      {
        UlStopRequestQueueTimer(v23);
        v26 = v45;
        v27 = v45 + 96;
        *(_DWORD *)(v23 + 1736) = 2;
        v28 = *(_QWORD **)(v27 + 8);
        if ( *v28 != v27 )
          __fastfail(3u);
        *(_QWORD *)(v23 + 1720) = v27;
        *(_QWORD *)(v23 + 1728) = v28;
        *v28 = v23 + 1720;
        *(_QWORD *)(v27 + 8) = v23 + 1720;
        if ( *(_DWORD *)(a3 + 40) == 1 && !*(_QWORD *)(v26 + 88) )
        {
          *(_QWORD *)(v26 + 88) = a3;
          v35 = _InterlockedIncrement((volatile signed __int32 *)a3);
          if ( UxDebugCheckRefcount )
          {
            if ( v35 <= -1 )
              UlBugCheckEx(3u, a3, 0xEu, v35);
          }
        }
        if ( *(_DWORD *)(a3 + 40) == 4 )
          *(_BYTE *)(v23 + 1853) = 1;
        *(_QWORD *)(v23 + 1744) = a3;
        v29 = _InterlockedIncrement((volatile signed __int32 *)a3);
        if ( UxDebugCheckRefcount && v29 <= -1 )
          UlBugCheckEx(3u, a3, 9u, v29);
        v30 = 1;
      }
      else
      {
        LOBYTE(v45) = 0;
        if ( (BYTE10(xmmword_1401A2C90) & 0x40) != 0 )
        {
          WPP_SF_qqqZqL(
            *(_QWORD *)(a3 + 8),
            v24,
            v25,
            v23,
            a3,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a3 + 8) + 160LL,
            v24,
            v25);
          v30 = v45;
        }
        else
        {
          v30 = 0;
        }
      }
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_d(1032, 186, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v30);
      if ( v30 )
      {
        v31 = v44 + 48;
        v32 = _InterlockedIncrement((volatile signed __int32 *)(v44 + 48));
        if ( UxDebugCheckRefcount && v32 <= -1 )
          UlBugCheckEx(3u, v31, 0x27u, v32);
        ExReleasePushLockExclusiveEx(*(_QWORD *)(v44 + 1712) + 72LL, 0);
        KeLeaveCriticalRegion();
        ExReleasePushLockExclusiveEx(v44 + 1704, 0);
        KeLeaveCriticalRegion();
        ExReleaseCacheAwarePushLockSharedEx(v9, 0);
        KeLeaveCriticalRegion();
        a4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        UlCopyRequestToIrp(v44, a4, a3, 0, 0);
        v33 = v44 + 48;
        v34 = _InterlockedDecrement((volatile signed __int32 *)(v44 + 48));
        if ( UxDebugCheckRefcount && v34 <= -1 )
          UlBugCheckEx(3u, v33, 0x27u, v34);
        v11 = 259;
        if ( !v34 )
          UlpQueueFreeHttpRequest(v44);
        goto LABEL_8;
      }
      ExReleasePushLockExclusiveEx(*(_QWORD *)(v44 + 1712) + 72LL, 0);
      KeLeaveCriticalRegion();
      ExReleasePushLockExclusiveEx(v44 + 1704, 0);
      KeLeaveCriticalRegion();
      v37 = v44 + 48;
      v38 = _InterlockedDecrement((volatile signed __int32 *)(v44 + 48));
      if ( UxDebugCheckRefcount && v38 <= -1 )
        UlBugCheckEx(3u, v37, 0xCu, v38);
      if ( !v38 )
        UlpQueueFreeHttpRequest(v44);
    }
  }
  ExReleaseCacheAwarePushLockSharedEx(v9, 0);
  KeLeaveCriticalRegion();
LABEL_8:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 196, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x14003f1b0  mov     [rsp-28h+arg_18], rbx
0x14003f1b5  push    rbp
0x14003f1b6  push    rsi
0x14003f1b7  push    rdi
0x14003f1b8  push    r13
0x14003f1ba  push    r14
0x14003f1bc  mov     rbp, rsp
0x14003f1bf  sub     rsp, 60h
0x14003f1c3  xor     r13d, r13d
0x14003f1c6  mov     r14, r9
0x14003f1c9  mov     [rbp+var_8], r13
0x14003f1cd  mov     rbx, r8
0x14003f1d0  mov     esi, edx
0x14003f1d2  mov     rdi, rcx
0x14003f1d5  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003f1dc  jnz     loc_14003F8A0
0x14003f1e2  cmp     dword ptr [rbx+28h], 4
0x14003f1e6  mov     [rsp+60h+arg_0], r12
0x14003f1ee  mov     [rsp+60h+arg_8], r15
0x14003f1f6  jz      loc_14003F2B3
0x14003f1fc  test    rdi, rdi
0x14003f1ff  jnz     loc_14003F2C2
0x14003f205  mov     rsi, [rbx+8]
0x14003f209  call    cs:__imp_KeEnterCriticalRegion
0x14003f210  nop     dword ptr [rax+rax+00h]
0x14003f215  mov     rcx, [rsi+118h]
0x14003f21c  xor     edx, edx
0x14003f21e  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14003f225  nop     dword ptr [rax+rax+00h]
0x14003f22a  mov     r15, rax
0x14003f22d  cmp     [rbx+4], r13b
0x14003f231  jnz     loc_14003F784
0x14003f237  mov     r12d, 0FFFFFFFFh
0x14003f23d  mov     r13d, 1
0x14003f243  lea     r9, [rbp+var_8]
0x14003f247  mov     r8, r14
0x14003f24a  mov     rdx, rbx
0x14003f24d  mov     rcx, rsi
0x14003f250  call    UlpRetrieveRequest
0x14003f255  mov     edi, eax
0x14003f257  cmp     eax, 103h
0x14003f25c  jnz     loc_14003F4A6
0x14003f262  xor     edx, edx
0x14003f264  mov     rcx, r15
0x14003f267  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14003f26e  nop     dword ptr [rax+rax+00h]
0x14003f273  call    cs:__imp_KeLeaveCriticalRegion
0x14003f27a  nop     dword ptr [rax+rax+00h]
0x14003f27f  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003f286  jnz     loc_14003FA60
0x14003f28c  mov     r15, [rsp+60h+arg_8]
0x14003f294  mov     eax, edi
0x14003f296  mov     r12, [rsp+60h+arg_0]
0x14003f29e  mov     rbx, [rsp+60h+arg_18]
0x14003f2a6  add     rsp, 60h
0x14003f2aa  pop     r14
0x14003f2ac  pop     r13
0x14003f2ae  pop     rdi
0x14003f2af  pop     rsi
0x14003f2b0  pop     rbp
0x14003f2b1  retn
0x14003f2b3  test    esi, esi
0x14003f2b5  jz      loc_14003F1FC
0x14003f2bb  mov     edi, 0C000000Dh
0x14003f2c0  jmp     short loc_14003F27F
0x14003f2c2  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003f2c9  jnz     loc_14003F8BB
0x14003f2cf  mov     rsi, r13
0x14003f2d2  mov     dword ptr [rbp+arg_10], r13d
0x14003f2d6  mov     [rbp+var_C], r13d
0x14003f2da  mov     [rbp+var_10], r13d
0x14003f2de  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003f2e5  jnz     loc_14003F8DE
0x14003f2eb  mov     r9d, edi
0x14003f2ee  shr     r9d, 1Ch
0x14003f2f2  cmp     r9d, 4
0x14003f2f6  jnz     loc_14003F8F0
0x14003f2fc  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003f303  jnz     loc_14003F918
0x14003f309  mov     r8, rdi
0x14003f30c  mov     dword ptr [rbp+arg_10], r13d
0x14003f310  shr     r8, 20h
0x14003f314  mov     eax, r8d
0x14003f317  mov     [rbp+var_10], r13d
0x14003f31b  and     eax, 0FFFh
0x14003f320  cmp     eax, cs:UxMaximumNumberOfProcessors
0x14003f326  mov     [rbp+var_C], eax
0x14003f329  jnb     loc_14003F78E
0x14003f32f  mov     ecx, eax
0x14003f331  mov     edx, r8d
0x14003f334  mov     rax, cs:UxOpaqueIdTable
0x14003f33b  shr     edx, 0Ch
0x14003f33e  and     edx, 0FFFh
0x14003f344  shl     rcx, 6
0x14003f348  mov     dword ptr [rbp+arg_10], edx
0x14003f34b  cmp     edx, [rcx+rax+28h]
0x14003f34f  jnb     loc_14003F95B
0x14003f355  shr     r8d, 18h
0x14003f359  mov     r15b, 1
0x14003f35c  mov     [rbp+var_10], r8d
0x14003f360  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003f367  jnz     loc_14003F986
0x14003f36d  test    r15b, r15b
0x14003f370  jz      loc_14003F428
0x14003f376  mov     rax, cs:UxOpaqueIdTable
0x14003f37d  mov     ecx, [rbp+var_C]
0x14003f380  mov     r8d, dword ptr [rbp+arg_10]
0x14003f384  shl     rcx, 6
0x14003f388  mov     rdx, [rcx+rax+10h]
0x14003f38d  mov     eax, [rbp+var_10]
0x14003f390  mov     r15, [rdx+r8*8]
0x14003f394  lea     rcx, [rax+rax*2]
0x14003f398  shl     rcx, 4
0x14003f39c  add     r15, rcx
0x14003f39f  call    cs:__imp_KeEnterCriticalRegion
0x14003f3a6  nop     dword ptr [rax+rax+00h]
0x14003f3ab  lea     r12, [r15+20h]
0x14003f3af  xor     edx, edx
0x14003f3b1  mov     rcx, r12
0x14003f3b4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003f3bb  nop     dword ptr [rax+rax+00h]
0x14003f3c0  mov     eax, [r15+28h]
0x14003f3c4  and     eax, 0F0000000h
0x14003f3c9  cmp     eax, 30000000h
0x14003f3ce  jnz     short loc_14003F40B
0x14003f3d0  mov     r15, [r15]
0x14003f3d3  mov     ecx, [r15+20h]
0x14003f3d7  mov     eax, ecx
0x14003f3d9  and     eax, 0F0000000h
0x14003f3de  cmp     eax, 40000000h
0x14003f3e3  jnz     short loc_14003F40B
0x14003f3e5  xor     ecx, edi
0x14003f3e7  test    ecx, 0FFFFFFFh
0x14003f3ed  jnz     short loc_14003F40B
0x14003f3ef  mov     rcx, [r15+18h]
0x14003f3f3  mov     rdx, rbx
0x14003f3f6  call    UlValidateHttpRequestFromId
0x14003f3fb  test    al, al
0x14003f3fd  jz      short loc_14003F40B
0x14003f3ff  mov     rsi, [r15+18h]
0x14003f403  mov     rcx, rsi
0x14003f406  call    UlReferenceHttpRequestFromId
0x14003f40b  xor     edx, edx
0x14003f40d  mov     rcx, r12
0x14003f410  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003f417  nop     dword ptr [rax+rax+00h]
0x14003f41c  call    cs:__imp_KeLeaveCriticalRegion
0x14003f423  nop     dword ptr [rax+rax+00h]
0x14003f428  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003f42f  jnz     loc_14003F9A9
0x14003f435  mov     [rbp+var_8], rsi
0x14003f439  test    rsi, rsi
0x14003f43c  jz      loc_14003F9D4
0x14003f442  mov     rcx, rsi
0x14003f445  call    UlStopRequestQueueTimer
0x14003f44a  mov     rax, [r14+0B8h]
0x14003f451  xor     r9d, r9d
0x14003f454  mov     r8, rbx
0x14003f457  mov     byte ptr [rsp+60h+var_40], r13b
0x14003f45c  mov     rdx, r14
0x14003f45f  or      byte ptr [rax+3], 1
0x14003f463  mov     rcx, [rbp+var_8]
0x14003f467  call    UlCopyRequestToIrp
0x14003f46c  mov     rdx, [rbp+var_8]
0x14003f470  mov     r12d, 0FFFFFFFFh
0x14003f476  add     rdx, 30h ; '0'; BugCheckParameter2
0x14003f47a  lock xadd [rdx], r12d
0x14003f47f  dec     r12d
0x14003f482  cmp     cs:UxDebugCheckRefcount, r13b
0x14003f489  jnz     loc_14003F733
0x14003f48f  test    r12d, r12d
0x14003f492  jz      loc_14003F9DE
0x14003f498  mov     [rbp+var_8], r13
0x14003f49c  mov     edi, 103h
0x14003f4a1  jmp     loc_14003F27F
0x14003f4a6  cmp     eax, 0C0000056h
0x14003f4ab  jz      loc_14003FA56
0x14003f4b1  cmp     eax, 0C0000120h
0x14003f4b6  jz      loc_14003F262
0x14003f4bc  test    eax, eax
0x14003f4be  jnz     loc_14003FA4C
0x14003f4c4  call    cs:__imp_KeEnterCriticalRegion
0x14003f4cb  nop     dword ptr [rax+rax+00h]
0x14003f4d0  mov     rcx, [rbp+var_8]
0x14003f4d4  xor     edx, edx
0x14003f4d6  add     rcx, 6A8h
0x14003f4dd  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003f4e4  nop     dword ptr [rax+rax+00h]
0x14003f4e9  call    cs:__imp_KeEnterCriticalRegion
0x14003f4f0  nop     dword ptr [rax+rax+00h]
0x14003f4f5  mov     rax, [rbp+var_8]
0x14003f4f9  xor     edx, edx
0x14003f4fb  mov     rcx, [rax+6B0h]
0x14003f502  add     rcx, 48h ; 'H'
0x14003f506  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003f50d  nop     dword ptr [rax+rax+00h]
0x14003f512  mov     rdi, [rbp+var_8]
0x14003f516  mov     rdx, [rdi+6B0h]
0x14003f51d  mov     [rbp+arg_10], rdx
0x14003f521  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x14003f528  jnz     loc_14003F9EC
0x14003f52e  cmp     byte ptr [rdx+50h], 0
0x14003f532  jnz     loc_140175A18
0x14003f538  mov     r8d, [rdi+6C8h]
0x14003f53f  cmp     r8d, r13d
0x14003f542  jnz     loc_14003F76F
0x14003f548  mov     rcx, rdi
0x14003f54b  call    UlStopRequestQueueTimer
0x14003f550  mov     rdx, [rbp+arg_10]
0x14003f554  lea     rcx, [rdx+60h]
0x14003f558  mov     dword ptr [rdi+6C8h], 2
0x14003f562  mov     r8, [rcx+8]
0x14003f566  cmp     [r8], rcx
0x14003f569  jz      short loc_14003F572
0x14003f56b  mov     ecx, 3
0x14003f570  int     29h; Win8: RtlFailFast(ecx)
0x14003f572  lea     rax, [rdi+6B8h]
0x14003f579  mov     [rax], rcx
0x14003f57c  mov     [rax+8], r8
0x14003f580  mov     [r8], rax
0x14003f583  mov     [rcx+8], rax
0x14003f587  cmp     [rbx+28h], r13d
0x14003f58b  jnz     short loc_14003F598
0x14003f58d  cmp     qword ptr [rdx+58h], 0
0x14003f592  jz      loc_14003F6F9
0x14003f598  cmp     dword ptr [rbx+28h], 4
0x14003f59c  jz      loc_14003FA21
0x14003f5a2  mov     [rdi+6D0h], rbx
0x14003f5a9  mov     eax, r13d
0x14003f5ac  lock xadd [rbx], eax
0x14003f5b0  inc     eax
0x14003f5b2  cmp     cs:UxDebugCheckRefcount, 0
0x14003f5b9  jnz     loc_14003F6D9
0x14003f5bf  movzx   edi, r13b
0x14003f5c3  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x14003f5ca  jnz     loc_14003FA2D
0x14003f5d0  test    dil, dil
0x14003f5d3  jz      loc_14003F809
0x14003f5d9  mov     rdx, [rbp+var_8]
0x14003f5dd  add     rdx, 30h ; '0'; BugCheckParameter2
0x14003f5e1  lock xadd [rdx], r13d
0x14003f5e6  inc     r13d
0x14003f5e9  cmp     cs:UxDebugCheckRefcount, 0
0x14003f5f0  jnz     loc_14003F6BC
0x14003f5f6  mov     rax, [rbp+var_8]
0x14003f5fa  xor     edx, edx
0x14003f5fc  mov     rcx, [rax+6B0h]
0x14003f603  add     rcx, 48h ; 'H'
0x14003f607  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003f60e  nop     dword ptr [rax+rax+00h]
0x14003f613  call    cs:__imp_KeLeaveCriticalRegion
0x14003f61a  nop     dword ptr [rax+rax+00h]
0x14003f61f  mov     rcx, [rbp+var_8]
0x14003f623  xor     edx, edx
0x14003f625  add     rcx, 6A8h
0x14003f62c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003f633  nop     dword ptr [rax+rax+00h]
0x14003f638  call    cs:__imp_KeLeaveCriticalRegion
0x14003f63f  nop     dword ptr [rax+rax+00h]
0x14003f644  xor     edx, edx
0x14003f646  mov     rcx, r15
0x14003f649  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14003f650  nop     dword ptr [rax+rax+00h]
0x14003f655  call    cs:__imp_KeLeaveCriticalRegion
0x14003f65c  nop     dword ptr [rax+rax+00h]
0x14003f661  mov     rax, [r14+0B8h]
0x14003f668  xor     r9d, r9d
0x14003f66b  mov     r8, rbx
0x14003f66e  mov     byte ptr [rsp+60h+var_40], 0
0x14003f673  mov     rdx, r14
0x14003f676  or      byte ptr [rax+3], 1
0x14003f67a  mov     rcx, [rbp+var_8]
0x14003f67e  call    UlCopyRequestToIrp
0x14003f683  mov     rdx, [rbp+var_8]
0x14003f687  add     rdx, 30h ; '0'; BugCheckParameter2
0x14003f68b  lock xadd [rdx], r12d
0x14003f690  dec     r12d
0x14003f693  cmp     cs:UxDebugCheckRefcount, 0
0x14003f69a  jnz     loc_14003F751
0x14003f6a0  mov     edi, 103h
0x14003f6a5  test    r12d, r12d
0x14003f6a8  jnz     loc_14003F27F
0x14003f6ae  mov     rcx, [rbp+var_8]
0x14003f6b2  call    UlpQueueFreeHttpRequest
0x14003f6b7  jmp     loc_14003F27F
0x14003f6bc  cmp     r13d, r12d
0x14003f6bf  jg      loc_14003F5F6
0x14003f6c5  movsxd  r9, r13d; BugCheckParameter4
0x14003f6c8  mov     ecx, 3; BugCheckParameter1
0x14003f6cd  mov     r8d, 27h ; '''; BugCheckParameter3
0x14003f6d3  call    UlBugCheckEx
0x14003f6d9  cmp     eax, r12d
0x14003f6dc  jg      loc_14003F5BF
0x14003f6e2  movsxd  r9, eax; BugCheckParameter4
0x14003f6e5  mov     r8d, 9; BugCheckParameter3
0x14003f6eb  mov     rdx, rbx; BugCheckParameter2
0x14003f6ee  mov     ecx, 3; BugCheckParameter1
0x14003f6f3  call    UlBugCheckEx
0x14003f6f9  mov     [rdx+58h], rbx
0x14003f6fd  mov     eax, r13d
  ... truncated ...
```
