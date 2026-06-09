# ConnectCompleteRequest

- ea: `0x1800152c0`
- end: `0x180015620`
- name: `ConnectCompleteRequest`
- size: `864`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005f1c`
- `0x18000c00c`
- `0x1800152c0`
- `0x18001f424`
- `0x1800383c4`
- `0x18003c098`
- `0x18003f2e0`
- `0x180047714`
- `0x1800e7206`
- `0x1800e9010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180015373`
- `msvcrt!_stricmp` at `0x180015373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001547b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001547b`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180015471`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180015471`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800153f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800153f5`

## pseudocode

```c
double __fastcall ConnectCompleteRequest(const char *a1, __int64 a2, unsigned int *a3)
{
  struct _LIST_ENTRY *v5; // rcx
  double result; // xmm0_8
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rcx
  DWORD LastError; // eax
  unsigned int v13; // eax
  struct _LIST_ENTRY *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 498, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v17 = 0;
  if ( a1 )
  {
    if ( *((_DWORD *)a1 + 6) != 2 )
    {
      if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v5[1].Blink) & 0x2000) != 0
        && BYTE1(v5[1].Blink) >= 4u )
      {
        WPP_SF_q(v5[1].Flink, 503, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *(_QWORD *)a1);
      }
      if ( !_stricmp(a1 + 56, "NULL") )
      {
        SetPortConnState(v8, v7, a1, 2);
        *a3 = 0;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
        {
          return WPP_SF_(WPP_GLOBAL_Control[1].Flink, 504, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
        }
        return result;
      }
      FreeDeviceList(a1);
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(*((_QWORD *)a1 + 6) + 64LL))(
             *((_QWORD *)a1 + 27),
             0,
             &v17);
      if ( !v9 )
      {
        *((_DWORD *)a1 + 130) = GetTickCount();
        SetPortConnState(v11, v10, a1, 2);
        v9 = AllocBundle(a1);
        if ( !v9 )
        {
          MapCookieToEndpoint((__int64)a1, v17);
          memset_0((void *)(a1 + 732), 0, 0x9Cu);
          memset_0((void *)(a1 + 888), 0, 0x9Cu);
          if ( !*(_BYTE *)ReceiveBuffers && !PostQueuedCompletionStatus(hIoCompletionPort, 0, 0, &RO_PostRecvPkt) )
          {
            LastError = GetLastError();
            if ( LastError != 997
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              result = WPP_SF_d(
                         WPP_GLOBAL_Control[1].Flink,
                         505,
                         WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                         LastError);
            }
            v9 = 0;
          }
          if ( *(_WORD *)(*((_QWORD *)a1 + 154) + 96LL) == 9 )
          {
            v13 = DwSaveIpSecInfo((__int64)a1);
            if ( v13
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              result = WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 506, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v13);
            }
            v9 = 0;
          }
        }
      }
      *a3 = v9;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control[1].Flink,
            507,
            (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
            (_DWORD)a1 + 8,
            v9);
          v14 = WPP_GLOBAL_Control;
        }
        if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v14[1].Blink) & 0x2000) != 0
          && BYTE1(v14[1].Blink) >= 6u )
        {
          v15 = 508;
          v16 = v9;
          return WPP_SF_d(v14[1].Flink, v15, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v16);
        }
      }
      return result;
    }
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 2u )
    {
      WPP_SF_q(v5[1].Flink, 499, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *(_QWORD *)a1);
    }
  }
  else if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
         && (HIDWORD(v5[1].Blink) & 0x2000) != 0
         && BYTE1(v5[1].Blink) >= 2u )
  {
    result = WPP_SF_(v5[1].Flink, 500, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
  *a3 = 615;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 501, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      v14 = WPP_GLOBAL_Control;
    }
    if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v14[1].Blink) & 0x2000) != 0
      && BYTE1(v14[1].Blink) >= 6u )
    {
      v15 = 502;
      v16 = 615;
      return WPP_SF_d(v14[1].Flink, v15, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v16);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800152c0  mov     [rsp+arg_8], rbx
0x1800152c5  mov     [rsp+arg_10], rbp
0x1800152ca  push    rsi
0x1800152cb  push    rdi
0x1800152cc  push    r13
0x1800152ce  push    r14
0x1800152d0  push    r15
0x1800152d2  sub     rsp, 30h
0x1800152d6  mov     rsi, r8
0x1800152d9  mov     rbx, rcx
0x1800152dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152e3  lea     r15, WPP_GLOBAL_Control
0x1800152ea  lea     r13, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800152f1  mov     dil, 6
0x1800152f4  mov     r14d, 2000h
0x1800152fa  cmp     rcx, r15
0x1800152fd  jz      short loc_180015323
0x1800152ff  test    [rcx+1Ch], r14d
0x180015303  jz      short loc_180015323
0x180015305  cmp     [rcx+19h], dil
0x180015309  jb      short loc_180015323
0x18001530b  mov     rcx, [rcx+10h]
0x18001530f  mov     edx, 1F2h
0x180015314  mov     r8, r13
0x180015317  call    WPP_SF_
0x18001531c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015323  mov     [rsp+58h+arg_0], 0
0x18001532c  mov     ebp, 2
0x180015331  test    rbx, rbx
0x180015334  jz      loc_18001558D
0x18001533a  cmp     [rbx+18h], ebp
0x18001533d  jz      loc_180015566
0x180015343  cmp     rcx, r15
0x180015346  jz      short loc_180015368
0x180015348  test    [rcx+1Ch], r14d
0x18001534c  jz      short loc_180015368
0x18001534e  cmp     byte ptr [rcx+19h], 4
0x180015352  jb      short loc_180015368
0x180015354  mov     r9, [rbx]
0x180015357  mov     edx, 1F7h
0x18001535c  mov     rcx, [rcx+10h]
0x180015360  mov     r8, r13
0x180015363  call    WPP_SF_q
0x180015368  lea     rcx, [rbx+38h]; String1
0x18001536c  lea     rdx, aNull_2; "NULL"
0x180015373  call    cs:__imp__stricmp
0x180015379  test    eax, eax
0x18001537b  jnz     short loc_1800153C8
0x18001537d  mov     r9d, ebp
0x180015380  mov     r8, rbx
0x180015383  call    SetPortConnState
0x180015388  mov     dword ptr [rsi], 0
0x18001538e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015395  cmp     rcx, r15
0x180015398  jz      loc_180015609
0x18001539e  test    [rcx+1Ch], r14d
0x1800153a2  jz      loc_180015609
0x1800153a8  cmp     [rcx+19h], dil
0x1800153ac  jb      loc_180015609
0x1800153b2  mov     rcx, [rcx+10h]
0x1800153b6  mov     edx, 1F8h
0x1800153bb  mov     r8, r13
0x1800153be  call    WPP_SF_
0x1800153c3  jmp     loc_180015609
0x1800153c8  mov     rcx, rbx
0x1800153cb  call    FreeDeviceList
0x1800153d0  mov     rax, [rbx+30h]
0x1800153d4  lea     r8, [rsp+58h+arg_0]
0x1800153d9  mov     rcx, [rbx+0D8h]
0x1800153e0  xor     edx, edx
0x1800153e2  mov     rax, [rax+40h]
0x1800153e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153eb  mov     edi, eax
0x1800153ed  test    eax, eax
0x1800153ef  jnz     loc_1800154FE
0x1800153f5  call    cs:__imp_GetTickCount
0x1800153fb  mov     r9d, ebp
0x1800153fe  mov     r8, rbx
0x180015401  mov     [rbx+208h], eax
0x180015407  call    SetPortConnState
0x18001540c  mov     rcx, rbx
0x18001540f  call    AllocBundle
0x180015414  mov     edi, eax
0x180015416  test    eax, eax
0x180015418  jnz     loc_1800154FE
0x18001541e  mov     rdx, [rsp+58h+arg_0]
0x180015423  mov     rcx, rbx
0x180015426  call    MapCookieToEndpoint
0x18001542b  mov     ebp, 9Ch
0x180015430  lea     rcx, [rbx+2DCh]; void *
0x180015437  mov     r8d, ebp; Size
0x18001543a  xor     edx, edx; Val
0x18001543c  call    memset_0
0x180015441  lea     rcx, [rbx+378h]; void *
0x180015448  mov     r8d, ebp; Size
0x18001544b  xor     edx, edx; Val
0x18001544d  call    memset_0
0x180015452  mov     rax, cs:ReceiveBuffers
0x180015459  cmp     [rax], dil
0x18001545c  jnz     short loc_1800154B6
0x18001545e  mov     rcx, cs:hIoCompletionPort; CompletionPort
0x180015465  lea     r9, RO_PostRecvPkt; lpOverlapped
0x18001546c  xor     r8d, r8d; dwCompletionKey
0x18001546f  xor     edx, edx; dwNumberOfBytesTransferred
0x180015471  call    cs:__imp_PostQueuedCompletionStatus
0x180015477  test    eax, eax
0x180015479  jnz     short loc_1800154B6
0x18001547b  call    cs:__imp_GetLastError
0x180015481  cmp     eax, 3E5h
0x180015486  jz      short loc_1800154B4
0x180015488  mov     rcx, cs:WPP_GLOBAL_Control
0x18001548f  cmp     rcx, r15
0x180015492  jz      short loc_1800154B4
0x180015494  test    [rcx+1Ch], r14d
0x180015498  jz      short loc_1800154B4
0x18001549a  cmp     byte ptr [rcx+19h], 2
0x18001549e  jb      short loc_1800154B4
0x1800154a0  mov     rcx, [rcx+10h]
0x1800154a4  mov     edx, 1F9h
0x1800154a9  mov     r9d, eax
0x1800154ac  mov     r8, r13
0x1800154af  call    WPP_SF_d
0x1800154b4  xor     edi, edi
0x1800154b6  mov     rax, [rbx+4D0h]
0x1800154bd  cmp     word ptr [rax+60h], 9
0x1800154c2  jnz     short loc_1800154FE
0x1800154c4  mov     rcx, rbx
0x1800154c7  call    DwSaveIpSecInfo
0x1800154cc  test    eax, eax
0x1800154ce  jz      short loc_1800154FC
0x1800154d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154d7  cmp     rcx, r15
0x1800154da  jz      short loc_1800154FC
0x1800154dc  test    [rcx+1Ch], r14d
0x1800154e0  jz      short loc_1800154FC
0x1800154e2  cmp     byte ptr [rcx+19h], 2
0x1800154e6  jb      short loc_1800154FC
0x1800154e8  mov     rcx, [rcx+10h]
0x1800154ec  mov     edx, 1FAh
0x1800154f1  mov     r9d, eax
0x1800154f4  mov     r8, r13
0x1800154f7  call    WPP_SF_d
0x1800154fc  xor     edi, edi
0x1800154fe  mov     [rsi], edi
0x180015500  mov     rcx, cs:WPP_GLOBAL_Control
0x180015507  cmp     rcx, r15
0x18001550a  jz      loc_180015609
0x180015510  test    [rcx+1Ch], r14d
0x180015514  jz      short loc_18001553C
0x180015516  cmp     byte ptr [rcx+19h], 4
0x18001551a  jb      short loc_18001553C
0x18001551c  mov     rcx, [rcx+10h]
0x180015520  lea     r9, [rbx+8]
0x180015524  mov     edx, 1FBh
0x180015529  mov     [rsp+58h+var_38], edi
0x18001552d  mov     r8, r13
0x180015530  call    WPP_SF_sd
0x180015535  mov     rcx, cs:WPP_GLOBAL_Control
0x18001553c  cmp     rcx, r15
0x18001553f  jz      loc_180015609
0x180015545  test    [rcx+1Ch], r14d
0x180015549  jz      loc_180015609
0x18001554f  cmp     byte ptr [rcx+19h], 6
0x180015553  jb      loc_180015609
0x180015559  mov     edx, 1FCh
0x18001555e  mov     r9d, edi
0x180015561  jmp     loc_1800155FD
0x180015566  cmp     rcx, r15
0x180015569  jz      short loc_1800155AF
0x18001556b  test    [rcx+1Ch], r14d
0x18001556f  jz      short loc_1800155AF
0x180015571  cmp     [rcx+19h], bpl
0x180015575  jb      short loc_1800155AF
0x180015577  mov     r9, [rbx]
0x18001557a  mov     edx, 1F3h
0x18001557f  mov     rcx, [rcx+10h]
0x180015583  mov     r8, r13
0x180015586  call    WPP_SF_q
0x18001558b  jmp     short loc_1800155AF
0x18001558d  cmp     rcx, r15
0x180015590  jz      short loc_1800155AF
0x180015592  test    [rcx+1Ch], r14d
0x180015596  jz      short loc_1800155AF
0x180015598  cmp     [rcx+19h], bpl
0x18001559c  jb      short loc_1800155AF
0x18001559e  mov     rcx, [rcx+10h]
0x1800155a2  mov     edx, 1F4h
0x1800155a7  mov     r8, r13
0x1800155aa  call    WPP_SF_
0x1800155af  mov     ebx, 267h
0x1800155b4  mov     [rsi], ebx
0x1800155b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155bd  cmp     rcx, r15
0x1800155c0  jz      short loc_180015609
0x1800155c2  test    [rcx+1Ch], r14d
0x1800155c6  jz      short loc_1800155E4
0x1800155c8  cmp     [rcx+19h], bpl
0x1800155cc  jb      short loc_1800155E4
0x1800155ce  mov     rcx, [rcx+10h]
0x1800155d2  lea     edx, [rbx-72h]
0x1800155d5  mov     r8, r13
0x1800155d8  call    WPP_SF_
0x1800155dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155e4  cmp     rcx, r15
0x1800155e7  jz      short loc_180015609
0x1800155e9  test    [rcx+1Ch], r14d
0x1800155ed  jz      short loc_180015609
0x1800155ef  cmp     [rcx+19h], dil
0x1800155f3  jb      short loc_180015609
0x1800155f5  mov     edx, 1F6h
0x1800155fa  mov     r9d, ebx
0x1800155fd  mov     rcx, [rcx+10h]
0x180015601  mov     r8, r13
0x180015604  call    WPP_SF_d
0x180015609  mov     rbx, [rsp+58h+arg_8]
0x18001560e  mov     rbp, [rsp+58h+arg_10]
0x180015613  add     rsp, 30h
0x180015617  pop     r15
0x180015619  pop     r14
0x18001561b  pop     r13
0x18001561d  pop     rdi
0x18001561e  pop     rsi
0x18001561f  retn
```
