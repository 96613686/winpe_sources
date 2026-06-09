# HidpSubmitInterruptRead

- ea: `0x180003190`
- end: `0x1800038ed`
- name: `HidpSubmitInterruptRead`
- size: `1885`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001430`
- `0x1800017d0`
- `0x18000f8a8`

## callees

- `0x180003190`
- `0x180003b70`
- `0x180003f40`
- `0x18000a15c`
- `0x1800163bc`
- `0x180018978`
- `0x180027c80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x180003337`
- `ntoskrnl!KeSetEvent` at `0x1800034cd`
- `ntoskrnl!KeSetEvent` at `0x1800034e2`
- `ntoskrnl!KeSetEvent` at `0x180003885`
- `ntoskrnl!KeSetEvent` at `0x18000389a`
- `ntoskrnl!KeSetEvent` at `0x180003337`
- `ntoskrnl!KeSetEvent` at `0x1800034cd`
- `ntoskrnl!KeSetEvent` at `0x1800034e2`
- `ntoskrnl!KeSetEvent` at `0x180003885`
- `ntoskrnl!KeSetEvent` at `0x18000389a`
- `ntoskrnl!KeBugCheckEx` at `0x1800036f0`
- `ntoskrnl!KeBugCheckEx` at `0x1800036f0`
- `ntoskrnl!KeSetTimer` at `0x18000354b`
- `ntoskrnl!KeSetTimer` at `0x18000354b`
- `ntoskrnl!KeResetEvent` at `0x180003236`
- `ntoskrnl!KeResetEvent` at `0x180003236`

## pseudocode

```c
__int64 __fastcall HidpSubmitInterruptRead(__int64 a1, __int64 a2, _BYTE *a3)
{
  ULONG_PTR v3; // rsi
  _BYTE *v4; // r13
  unsigned int v5; // ebp
  __int64 v6; // rdi
  __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rcx
  unsigned __int8 *v13; // rax
  __int64 v14; // r12
  __int64 v15; // r15
  int v16; // edx
  int v17; // r8d

  v3 = *(_QWORD *)(a2 + 8);
  v4 = a3;
  v5 = 0;
  v6 = a2;
  *a3 = 0;
  while ( (v5 & 0x80000000) == 0 )
  {
    if ( (unsigned int)(_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 1808), 0, 0) - 12) > 2
      && ((*(_DWORD *)(a1 + 1768) & 4) == 0 || *(int *)(a1 + 344) > 1) )
    {
      HidpFdoAcquirePoFxPowerReferenceWithTag(a1, 4u);
      HidpFdoReleasePoFxPowerReferenceWithTag(a1, 4);
    }
    _InterlockedExchange((volatile __int32 *)(v6 + 4), 1);
    v8 = *(_QWORD *)(v3 + 184);
    *(_BYTE *)(v3 + 68) = 0;
    *(_DWORD *)(v3 + 48) = -1073741637;
    *(_BYTE *)(v8 - 72) = 15;
    *(_DWORD *)(v8 - 48) = 720907;
    *(_DWORD *)(v8 - 64) = *(_DWORD *)(a1 + 228);
    *(_DWORD *)(v8 - 56) = 0;
    v9 = *(_QWORD *)(v3 + 184);
    *(_QWORD *)(v9 - 16) = HidpInterruptReadComplete;
    *(_QWORD *)(v9 - 8) = a1;
    *(_BYTE *)(v9 - 69) = -32;
    KeResetEvent((PRKEVENT)(v6 + 32));
    if ( *(_DWORD *)(v6 + 24) )
    {
      LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                 && LOWORD(WPP_GLOBAL_Control->DeviceType);
      if ( (_BYTE)v10 || (_BYTE)v11 )
        WPP_RECORDER_AND_TRACE_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          v10,
          v11,
          *(_QWORD *)(a1 + 688),
          5,
          5,
          12,
          (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
          *(_QWORD *)a1,
          v3);
      KeSetEvent((PRKEVENT)(v6 + 32), 0, 0);
      KeSetEvent((PRKEVENT)(v6 + 56), 0, 0);
      return (unsigned int)-1073741536;
    }
    LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
               && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)v10 || (_BYTE)v11 )
      WPP_RECORDER_AND_TRACE_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        v11,
        *(_QWORD *)(a1 + 688),
        5,
        5,
        13,
        (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
        *(_QWORD *)a1,
        v3);
    v12 = *(_QWORD *)a1;
    if ( (char)--*(_BYTE *)(v3 + 67) <= 0 )
      KeBugCheckEx(0x35u, v3, 0, 0, 0);
    *(_QWORD *)(v3 + 184) -= 72LL;
    v13 = *(unsigned __int8 **)(v3 + 184);
    v14 = *v13;
    *((_QWORD *)v13 + 5) = v12;
    v15 = *(_QWORD *)(v12 + 64);
    v5 = (*(__int64 (__fastcall **)(__int64, ULONG_PTR))(*(_QWORD *)(v15 + 40) + 8 * v14 + 32))(v12, v3);
    if ( *(_BYTE *)(v15 + 24) )
      v15 = *(_QWORD *)(v15 + 96);
    LOBYTE(v16) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
               && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)v16 || (_BYTE)v17 )
      WPP_RECORDER_AND_TRACE_SF_qqcd(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        v17,
        *(_QWORD *)(v15 + 704),
        5,
        4,
        10,
        (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
        *(_QWORD *)(v15 + 32),
        v3,
        v14,
        v5);
    KeSetEvent((PRKEVENT)(v6 + 32), 0, 0);
    *v4 = 1;
    if ( _InterlockedExchange((volatile __int32 *)(v6 + 4), 2) != 3 )
    {
      LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                && LOWORD(WPP_GLOBAL_Control->DeviceType);
      if ( (_BYTE)a2 || (_BYTE)a3 )
        WPP_RECORDER_AND_TRACE_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          a2,
          (_DWORD)a3,
          *(_QWORD *)(a1 + 688),
          5,
          5,
          14,
          (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
          *(_QWORD *)a1,
          v3);
      return v5;
    }
    v5 = *(_DWORD *)(v3 + 48);
    LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)a2 || (_BYTE)a3 )
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        a2,
        (_DWORD)a3,
        *(_QWORD *)(a1 + 688),
        5,
        5,
        15,
        (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
        *(_QWORD *)a1,
        v3,
        *(_DWORD *)(v3 + 48));
  }
  if ( *(_DWORD *)(v6 + 24) )
  {
    LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)a2 || (_BYTE)a3 )
      WPP_RECORDER_AND_TRACE_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        a2,
        (_DWORD)a3,
        *(_QWORD *)(a1 + 688),
        5,
        5,
        16,
        (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
        *(_QWORD *)a1,
        v3);
    goto LABEL_112;
  }
  if ( v5 == -1073741438 && (*(_DWORD *)(a1 + 1756) & 0x100) != 0 )
  {
    LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        a2,
        (_DWORD)a3,
        *(_QWORD *)(a1 + 688),
        3,
        5,
        17,
        (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
        *(_QWORD *)a1,
        v3,
        130);
    }
    KeSetEvent((PRKEVENT)(v6 + 32), 0, 0);
LABEL_112:
    KeSetEvent((PRKEVENT)(v6 + 56), 0, 0);
    return v5;
  }
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType);
  if ( (_BYTE)a2 || (_BYTE)a3 )
    WPP_RECORDER_AND_TRACE_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      (_DWORD)a3,
      *(_QWORD *)(a1 + 688),
      5,
      5,
      18,
      (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
      *(_QWORD *)a1,
      v3);
  KeSetTimer((PKTIMER)(v6 + 88), *(LARGE_INTEGER *)(v6 + 216), (PKDPC)(v6 + 152));
  return v5;
}

```

## disassembly

```asm
0x180003190  push    rbx
0x180003192  push    rbp
0x180003193  push    rsi
0x180003194  push    rdi
0x180003195  push    r12
0x180003197  push    r13
0x180003199  push    r14
0x18000319b  push    r15
0x18000319d  sub     rsp, 68h
0x1800031a1  mov     rsi, [rdx+8]
0x1800031a5  lea     r12, WPP_GLOBAL_Control
0x1800031ac  xor     r15d, r15d
0x1800031af  mov     r13, r8
0x1800031b2  mov     ebp, r15d
0x1800031b5  mov     rdi, rdx
0x1800031b8  mov     [r8], bpl
0x1800031bb  mov     rbx, rcx
0x1800031be  lea     r9, WPP_RECORDER_INITIALIZED
0x1800031c5  lea     r14, HidpInterruptReadComplete
0x1800031cc  test    ebp, ebp
0x1800031ce  js      loc_1800034F8
0x1800031d4  mov     ecx, r15d
0x1800031d7  xor     eax, eax
0x1800031d9  lock cmpxchg [rbx+710h], ecx
0x1800031e1  add     eax, 0FFFFFFF4h
0x1800031e4  cmp     eax, 2
0x1800031e7  ja      loc_18000344E
0x1800031ed  mov     eax, 1
0x1800031f2  xchg    eax, [rdi+4]
0x1800031f5  mov     rcx, [rsi+0B8h]
0x1800031fc  mov     byte ptr [rsi+44h], 0
0x180003200  mov     dword ptr [rsi+30h], 0C00000BBh
0x180003207  mov     byte ptr [rcx-48h], 0Fh
0x18000320b  mov     dword ptr [rcx-30h], 0B000Bh
0x180003212  mov     eax, [rbx+0E4h]
0x180003218  mov     [rcx-40h], eax
0x18000321b  mov     [rcx-38h], r15d
0x18000321f  lea     rcx, [rdi+20h]; Event
0x180003223  mov     rax, [rsi+0B8h]
0x18000322a  mov     [rax-10h], r14
0x18000322e  mov     [rax-8], rbx
0x180003232  mov     byte ptr [rax-45h], 0E0h
0x180003236  call    cs:__imp_KeResetEvent
0x18000323d  nop     dword ptr [rax+rax+00h]
0x180003242  cmp     dword ptr [rdi+18h], 0
0x180003246  jnz     loc_18000348A
0x18000324c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003253  cmp     rcx, r12
0x180003256  jz      short loc_180003263
0x180003258  mov     eax, [rcx+2Ch]
0x18000325b  test    al, 10h
0x18000325d  jnz     loc_1800035C5
0x180003263  xor     dl, dl
0x180003265  lea     rax, WPP_RECORDER_INITIALIZED
0x18000326c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180003273  jz      short loc_180003280
0x180003275  cmp     word ptr [rcx+48h], 0
0x18000327a  jnz     loc_1800035D6
0x180003280  xor     r8b, r8b
0x180003283  test    dl, dl
0x180003285  jnz     loc_1800035DE
0x18000328b  test    r8b, r8b
0x18000328e  jnz     loc_1800035DE
0x180003294  mov     rcx, [rbx]
0x180003297  mov     rdx, rsi; BugCheckParameter1
0x18000329a  dec     byte ptr [rsi+43h]
0x18000329d  movzx   eax, byte ptr [rsi+43h]
0x1800032a1  test    al, al
0x1800032a3  jle     loc_1800036E0
0x1800032a9  add     qword ptr [rsi+0B8h], 0FFFFFFFFFFFFFFB8h
0x1800032b1  mov     rax, [rsi+0B8h]
0x1800032b8  movzx   r12d, byte ptr [rax]
0x1800032bc  mov     [rax+28h], rcx
0x1800032c0  mov     r15, [rcx+40h]
0x1800032c4  mov     rax, [r15+28h]
0x1800032c8  mov     rax, [rax+r12*8+20h]
0x1800032cd  call    _guard_dispatch_icall
0x1800032d2  cmp     byte ptr [r15+18h], 0
0x1800032d7  mov     ebp, eax
0x1800032d9  jnz     loc_180003481
0x1800032df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032e6  lea     rax, WPP_GLOBAL_Control
0x1800032ed  cmp     rcx, rax
0x1800032f0  jz      short loc_1800032FD
0x1800032f2  mov     eax, [rcx+2Ch]
0x1800032f5  test    al, 8
0x1800032f7  jnz     loc_180003620
0x1800032fd  xor     dl, dl
0x1800032ff  lea     rax, WPP_RECORDER_INITIALIZED
0x180003306  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000330d  jz      short loc_18000331A
0x18000330f  cmp     word ptr [rcx+48h], 0
0x180003314  jnz     loc_180003631
0x18000331a  xor     r8b, r8b
0x18000331d  test    dl, dl
0x18000331f  jnz     loc_180003639
0x180003325  test    r8b, r8b
0x180003328  jnz     loc_180003639
0x18000332e  xor     r8d, r8d; Wait
0x180003331  lea     rcx, [rdi+20h]; Event
0x180003335  xor     edx, edx; Increment
0x180003337  call    cs:__imp_KeSetEvent
0x18000333e  nop     dword ptr [rax+rax+00h]
0x180003343  mov     eax, 2
0x180003348  mov     byte ptr [r13+0], 1
0x18000334d  xchg    eax, [rdi+4]
0x180003350  cmp     eax, 3
0x180003353  jz      short loc_1800033B8
0x180003355  mov     rcx, cs:WPP_GLOBAL_Control
0x18000335c  lea     rax, WPP_GLOBAL_Control
0x180003363  cmp     rcx, rax
0x180003366  jz      short loc_180003373
0x180003368  mov     eax, [rcx+2Ch]
0x18000336b  test    al, 10h
0x18000336d  jnz     loc_180003685
0x180003373  xor     dl, dl
0x180003375  lea     rax, WPP_RECORDER_INITIALIZED
0x18000337c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180003383  jz      short loc_180003390
0x180003385  cmp     word ptr [rcx+48h], 0
0x18000338a  jnz     loc_180003696
0x180003390  xor     r8b, r8b
0x180003393  test    dl, dl
0x180003395  jnz     loc_18000369E
0x18000339b  test    r8b, r8b
0x18000339e  jnz     loc_18000369E
0x1800033a4  mov     eax, ebp
0x1800033a6  add     rsp, 68h
0x1800033aa  pop     r15
0x1800033ac  pop     r14
0x1800033ae  pop     r13
0x1800033b0  pop     r12
0x1800033b2  pop     rdi
0x1800033b3  pop     rsi
0x1800033b4  pop     rbp
0x1800033b5  pop     rbx
0x1800033b6  retn
0x1800033b8  mov     ebp, [rsi+30h]
0x1800033bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033c2  lea     r12, WPP_GLOBAL_Control
0x1800033c9  cmp     rcx, r12
0x1800033cc  jnz     loc_18000355C
0x1800033d2  xor     dl, dl
0x1800033d4  lea     r9, WPP_RECORDER_INITIALIZED
0x1800033db  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x1800033e2  jnz     loc_180003578
0x1800033e8  xor     r8b, r8b
0x1800033eb  test    dl, dl
0x1800033ed  jnz     short loc_180003405
0x1800033ef  lea     r14, HidpInterruptReadComplete
0x1800033f6  mov     r15d, 0
0x1800033fc  test    r8b, r8b
0x1800033ff  jz      loc_1800031CC
0x180003405  mov     rax, [rbx]
0x180003408  mov     r9, [rbx+2B0h]
0x18000340f  mov     rcx, [rcx+18h]
0x180003413  mov     [rsp+0A8h+var_58], ebp
0x180003417  mov     [rsp+0A8h+var_60], rsi
0x18000341c  mov     [rsp+0A8h+var_68], rax
0x180003421  lea     rax, WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids
0x180003428  mov     [rsp+0A8h+var_70], rax
0x18000342d  mov     [rsp+0A8h+var_78], 0Fh
0x180003434  mov     [rsp+0A8h+var_80], 5
0x18000343c  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 5
0x180003441  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x180003446  xor     r15d, r15d
0x180003449  jmp     loc_1800031BE
0x18000344e  mov     eax, [rbx+6E8h]
0x180003454  test    al, 4
0x180003456  jnz     loc_1800035B3
0x18000345c  xor     r8d, r8d
0x18000345f  mov     edx, 4
0x180003464  mov     rcx, rbx
0x180003467  call    HidpFdoAcquirePoFxPowerReferenceWithTag
0x18000346c  xor     r8d, r8d
0x18000346f  mov     edx, 4
0x180003474  mov     rcx, rbx
0x180003477  call    HidpFdoReleasePoFxPowerReferenceWithTag
0x18000347c  jmp     loc_1800031ED
0x180003481  mov     r15, [r15+60h]
0x180003485  jmp     loc_1800032DF
0x18000348a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003491  cmp     rcx, r12
0x180003494  jnz     loc_1800036FD
0x18000349a  xor     dl, dl
0x18000349c  lea     rax, WPP_RECORDER_INITIALIZED
0x1800034a3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800034aa  jnz     loc_180003719
0x1800034b0  xor     r8b, r8b
0x1800034b3  test    dl, dl
0x1800034b5  jnz     loc_18000372C
0x1800034bb  test    r8b, r8b
0x1800034be  jnz     loc_18000372C
0x1800034c4  xor     r8d, r8d; Wait
0x1800034c7  lea     rcx, [rdi+20h]; Event
0x1800034cb  xor     edx, edx; Increment
0x1800034cd  call    cs:__imp_KeSetEvent
0x1800034d4  nop     dword ptr [rax+rax+00h]
0x1800034d9  lea     rcx, [rdi+38h]; Event
0x1800034dd  xor     r8d, r8d; Wait
0x1800034e0  xor     edx, edx; Increment
0x1800034e2  call    cs:__imp_KeSetEvent
0x1800034e9  nop     dword ptr [rax+rax+00h]
0x1800034ee  mov     ebp, 0C0000120h
0x1800034f3  jmp     loc_1800033A4
0x1800034f8  cmp     dword ptr [rdi+18h], 0
0x1800034fc  jnz     loc_18000376E
0x180003502  cmp     ebp, 0C0000182h
0x180003508  jz      loc_1800037F4
0x18000350e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003515  cmp     rcx, r12
0x180003518  jnz     short loc_180003597
0x18000351a  xor     dl, dl
0x18000351c  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x180003523  jnz     short loc_18000358B
0x180003525  xor     r8b, r8b
0x180003528  test    dl, dl
0x18000352a  jnz     loc_1800038AB
0x180003530  test    r8b, r8b
0x180003533  jnz     loc_1800038AB
0x180003539  mov     rdx, [rdi+0D8h]; DueTime
0x180003540  lea     r8, [rdi+98h]; Dpc
0x180003547  lea     rcx, [rdi+58h]; Timer
0x18000354b  call    cs:__imp_KeSetTimer
0x180003552  nop     dword ptr [rax+rax+00h]
0x180003557  jmp     loc_1800033A4
0x18000355c  mov     eax, [rcx+2Ch]
0x18000355f  test    al, 10h
0x180003561  jz      loc_1800033D2
0x180003567  cmp     byte ptr [rcx+29h], 5
0x18000356b  jb      loc_1800033D2
0x180003571  mov     dl, 1
0x180003573  jmp     loc_1800033D4
0x180003578  cmp     word ptr [rcx+48h], 0
0x18000357d  jz      loc_1800033E8
0x180003583  mov     r8b, 1
0x180003586  jmp     loc_1800033EB
0x18000358b  cmp     word ptr [rcx+48h], 0
0x180003590  jz      short loc_180003525
0x180003592  mov     r8b, 1
0x180003595  jmp     short loc_180003528
0x180003597  mov     eax, [rcx+2Ch]
0x18000359a  test    al, 10h
0x18000359c  jz      loc_18000351A
0x1800035a2  cmp     byte ptr [rcx+29h], 5
0x1800035a6  jb      loc_18000351A
0x1800035ac  mov     dl, 1
0x1800035ae  jmp     loc_18000351C
0x1800035b3  cmp     dword ptr [rbx+158h], 1
0x1800035ba  jle     loc_1800031ED
0x1800035c0  jmp     loc_18000345C
0x1800035c5  cmp     byte ptr [rcx+29h], 5
0x1800035c9  jb      loc_180003263
0x1800035cf  mov     dl, 1
0x1800035d1  jmp     loc_180003265
0x1800035d6  mov     r8b, 1
0x1800035d9  jmp     loc_180003283
0x1800035de  mov     rax, [rbx]
0x1800035e1  mov     r9, [rbx+2B0h]
0x1800035e8  mov     rcx, [rcx+18h]
0x1800035ec  mov     [rsp+0A8h+var_60], rsi
0x1800035f1  mov     [rsp+0A8h+var_68], rax
0x1800035f6  lea     rax, WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids
0x1800035fd  mov     [rsp+0A8h+var_70], rax
0x180003602  mov     [rsp+0A8h+var_78], 0Dh
0x180003609  mov     [rsp+0A8h+var_80], 5
0x180003611  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 5
0x180003616  call    WPP_RECORDER_AND_TRACE_SF_qq
0x18000361b  jmp     loc_180003294
0x180003620  cmp     byte ptr [rcx+29h], 5
0x180003624  jb      loc_1800032FD
0x18000362a  mov     dl, 1
0x18000362c  jmp     loc_1800032FF
0x180003631  mov     r8b, 1
0x180003634  jmp     loc_18000331D
0x180003639  mov     rax, [r15+20h]
0x18000363d  mov     r9, [r15+2C0h]
0x180003644  mov     rcx, [rcx+18h]
0x180003648  mov     [rsp+0A8h+var_50], ebp
0x18000364c  mov     byte ptr [rsp+0A8h+var_58], r12b
0x180003651  mov     [rsp+0A8h+var_60], rsi
0x180003656  mov     [rsp+0A8h+var_68], rax
0x18000365b  lea     rax, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x180003662  mov     [rsp+0A8h+var_70], rax
0x180003667  mov     [rsp+0A8h+var_78], 0Ah
0x18000366e  mov     [rsp+0A8h+var_80], 4
0x180003676  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 5
0x18000367b  call    WPP_RECORDER_AND_TRACE_SF_qqcd
0x180003680  jmp     loc_18000332E
0x180003685  cmp     byte ptr [rcx+29h], 5
0x180003689  jb      loc_180003373
0x18000368f  mov     dl, 1
0x180003691  jmp     loc_180003375
0x180003696  mov     r8b, 1
0x180003699  jmp     loc_180003393
0x18000369e  mov     rax, [rbx]
0x1800036a1  mov     r9, [rbx+2B0h]
0x1800036a8  mov     rcx, [rcx+18h]
0x1800036ac  mov     [rsp+0A8h+var_60], rsi
0x1800036b1  mov     [rsp+0A8h+var_68], rax
  ... truncated ...
```
