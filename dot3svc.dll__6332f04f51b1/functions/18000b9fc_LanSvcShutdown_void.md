# LanSvcShutdown(void)

- ea: `0x18000b9fc`
- end: `0x18000c025`
- name: `?LanSvcShutdown@@YAXXZ`
- size: `1577`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x18000aac0`
- `0x18000b5e0`

## callees

- `0x180003be4`
- `0x18000a9c0`
- `0x18000b680`
- `0x18000b9fc`
- `0x18000c230`
- `0x18000c608`
- `0x18000fc34`
- `0x180012bf4`
- `0x18001346c`
- `0x180014040`
- `0x180014658`
- `0x18001c2b4`
- `0x18001ed50`
- `0x180027114`
- `0x18002807c`

## import_xrefs

- `dot3msm!Dot3MsmDeInit` at `0x18000bd25`
- `dot3msm!Dot3MsmDeInit` at `0x18000bd25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bf49`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bf49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bfa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bfa3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bbd8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bc1e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bbd8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bc1e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000bb49`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000bb49`
- `MobileNetworking!HtDestroyHandleTable` at `0x18000bf5b`
- `MobileNetworking!HtDestroyHandleTable` at `0x18000bf5b`
- `ext-ms-win-dot3-grouppolicy-l1-1-0!LANGPADeInit` at `0x18000bc7e`
- `ext-ms-win-dot3-grouppolicy-l1-1-0!LANGPADeInit` at `0x18000bc7e`

## pseudocode

```c
void LanSvcShutdown(void)
{
  unsigned int v0; // ebx
  __int16 v1; // ax
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  struct _LIST_ENTRY *v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // rdx
  unsigned int v9; // eax
  bool v10; // zf
  unsigned int v11; // eax
  unsigned int v12; // eax
  struct _LIST_ENTRY *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  struct _LIST_ENTRY *v21; // rcx
  DWORD v22; // eax

  v0 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 53, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
  }
  v1 = g_Deinit;
  if ( (g_Deinit & 0x800) != 0 )
  {
    v2 = LanNotifyDeInit();
    v0 = v2;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 54, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v2);
    }
    v1 = g_Deinit & 0xF7FF;
    g_Deinit &= ~0x800u;
  }
  if ( (v1 & 0x400) != 0 )
  {
    v3 = LanSvcStopRPCServer();
    v0 = v3;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 55, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v3);
    }
    g_Deinit &= ~0x400u;
  }
  NhDeregisterNSINotifications();
  v4 = g_Deinit;
  if ( (g_Deinit & 0x100) != 0 )
  {
    v5 = NhRegisterWmiNotification(0);
    v0 = v5;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 56, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v5);
      v6 = WPP_GLOBAL_Control;
    }
    v4 = g_Deinit & 0xFFFFFEFF;
    g_Deinit &= ~0x100u;
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
  }
  if ( g_hWaitObject )
  {
    if ( !UnregisterWait(g_hWaitObject) )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 4u
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_31;
      }
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 57, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, LastError);
    }
    v6 = WPP_GLOBAL_Control;
LABEL_31:
    v4 = g_Deinit;
    g_hWaitObject = 0;
  }
  if ( (v4 & 0x10) != 0 )
  {
    g_fLanTimerStarted = 0;
    g_Deinit = v4 & 0xFFFFFFEF;
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v6[1].Blink) >= 4u && (BYTE4(v6[1].Blink) & 1) != 0 )
  {
    v8 = 58;
LABEL_42:
    WPP_SF_d(v6[1].Flink, v8, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, g_nThreads - 1);
  }
  while ( g_nThreads > 1 )
  {
    Sleep(0x3E8u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v8 = 59;
      goto LABEL_42;
    }
  }
  Sleep(0x64u);
  if ( (g_Deinit & 0x200) != 0 )
  {
    v9 = LanSvcDeinitRPCServer();
    v0 = v9;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 60, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v9);
    }
    g_Deinit &= ~0x200u;
  }
  v10 = (unsigned __int8)IsLANGPADeInitPresent() == 0;
  v11 = g_Deinit;
  if ( v10 || g_Deinit >= 0 )
  {
    v13 = WPP_GLOBAL_Control;
  }
  else
  {
    v12 = LANGPADeInit();
    v0 = v12;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 61, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v12);
      v13 = WPP_GLOBAL_Control;
    }
    v11 = g_Deinit & 0xFFFFFF7F;
    g_Deinit &= ~0x80u;
  }
  if ( (v11 & 0x40) != 0 )
  {
    v14 = WimDeinit();
    v0 = v14;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 62, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v14);
      v13 = WPP_GLOBAL_Control;
    }
    v11 = g_Deinit & 0xFFFFFFBF;
    g_Deinit &= ~0x40u;
  }
  if ( (v11 & 0x1000) != 0 )
  {
    v15 = Dot3MsmDeInit();
    v0 = v15;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 63, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v15);
      v13 = WPP_GLOBAL_Control;
    }
    v11 = g_Deinit & 0xFFFFEFFF;
    g_Deinit &= ~0x1000u;
  }
  if ( (v11 & 0x20) != 0 )
  {
    v16 = PmDeinit();
    v0 = v16;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 64, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v16);
      v13 = WPP_GLOBAL_Control;
    }
    v11 = g_Deinit & 0xFFFFFFDF;
    g_Deinit &= ~0x20u;
  }
  if ( (v11 & 8) != 0 )
  {
    v17 = TmDeinit();
    v0 = v17;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 65, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v17);
      v13 = WPP_GLOBAL_Control;
    }
    v11 = g_Deinit & 0xFFFFFFF7;
    g_Deinit &= ~8u;
  }
  if ( (v11 & 4) != 0 )
  {
    if ( v13 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v13[1].Blink) >= 4u && (BYTE4(v13[1].Blink) & 1) != 0 )
    {
      WPP_SF_(v13[1].Flink, 12, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids);
      v13 = WPP_GLOBAL_Control;
      v11 = g_Deinit;
    }
    v0 = 0;
    if ( v13 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v13[1].Blink) >= 4u && (BYTE4(v13[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(v13[1].Flink, 66, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, 0);
      v11 = g_Deinit;
    }
    v11 &= ~4u;
    g_Deinit = v11;
  }
  if ( (v11 & 2) != 0 )
  {
    v18 = LanSvcContextDeinit();
    v0 = v18;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 67, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v18);
    }
    LOWORD(v11) = g_Deinit & 0xFFFD;
    g_Deinit &= ~2u;
  }
  if ( (v11 & 1) != 0 )
  {
    v19 = StDeinit();
    v0 = v19;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 68, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v19);
    }
    LOWORD(v11) = g_Deinit & 0xFFFE;
    g_Deinit &= ~1u;
  }
  if ( (v11 & 0x2000) != 0 )
  {
    IntfHlpDeinit();
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 69, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v0);
    }
    g_Deinit &= ~0x2000u;
  }
  DeleteCriticalSection(&g_csDot3Migration);
  if ( !g_hHandleTable )
    goto LABEL_115;
  v20 = HtDestroyHandleTable();
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 70, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v20);
LABEL_115:
    v21 = WPP_GLOBAL_Control;
  }
  if ( g_hStopServiceEvent )
  {
    if ( !CloseHandle(g_hStopServiceEvent) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 4u
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_123;
      }
      v22 = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 71, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v22);
    }
    v21 = WPP_GLOBAL_Control;
LABEL_123:
    g_hStopServiceEvent = 0;
  }
  if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v21[1].Blink) >= 4u && (BYTE4(v21[1].Blink) & 1) != 0 )
    WPP_SF_(v21[1].Flink, 72, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
}

```

## disassembly

```asm
0x18000b9fc  push    rbx
0x18000b9fe  push    rbp
0x18000b9ff  push    rsi
0x18000ba00  push    rdi
0x18000ba01  push    r14
0x18000ba03  sub     rsp, 20h
0x18000ba07  xor     ebx, ebx
0x18000ba09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba10  lea     rbp, WPP_GLOBAL_Control
0x18000ba17  lea     edi, [rbx+1]
0x18000ba1a  mov     sil, 4
0x18000ba1d  lea     r14, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids
0x18000ba24  cmp     rcx, rbp
0x18000ba27  jz      short loc_18000BA44
0x18000ba29  cmp     [rcx+19h], sil
0x18000ba2d  jb      short loc_18000BA44
0x18000ba2f  test    [rcx+1Ch], dil
0x18000ba33  jz      short loc_18000BA44
0x18000ba35  mov     rcx, [rcx+10h]
0x18000ba39  lea     edx, [rbx+35h]
0x18000ba3c  mov     r8, r14
0x18000ba3f  call    WPP_SF_
0x18000ba44  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000ba4a  bt      eax, 0Bh
0x18000ba4e  jnb     short loc_18000BA93
0x18000ba50  call    LanNotifyDeInit
0x18000ba55  mov     ebx, eax
0x18000ba57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba5e  cmp     rcx, rbp
0x18000ba61  jz      short loc_18000BA83
0x18000ba63  cmp     [rcx+19h], sil
0x18000ba67  jb      short loc_18000BA83
0x18000ba69  test    [rcx+1Ch], dil
0x18000ba6d  jz      short loc_18000BA83
0x18000ba6f  mov     rcx, [rcx+10h]
0x18000ba73  mov     edx, 36h ; '6'
0x18000ba78  mov     r9d, eax
0x18000ba7b  mov     r8, r14
0x18000ba7e  call    WPP_SF_d
0x18000ba83  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000ba89  btr     eax, 0Bh
0x18000ba8d  mov     cs:?g_Deinit@@3W4DeinitFlags@@A, eax; DeinitFlags g_Deinit
0x18000ba93  bt      eax, 0Ah
0x18000ba97  jnb     short loc_18000BAD4
0x18000ba99  call    ?LanSvcStopRPCServer@@YAKXZ; LanSvcStopRPCServer(void)
0x18000ba9e  mov     ebx, eax
0x18000baa0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000baa7  cmp     rcx, rbp
0x18000baaa  jz      short loc_18000BACC
0x18000baac  cmp     [rcx+19h], sil
0x18000bab0  jb      short loc_18000BACC
0x18000bab2  test    [rcx+1Ch], dil
0x18000bab6  jz      short loc_18000BACC
0x18000bab8  mov     rcx, [rcx+10h]
0x18000babc  mov     edx, 37h ; '7'
0x18000bac1  mov     r9d, eax
0x18000bac4  mov     r8, r14
0x18000bac7  call    WPP_SF_d
0x18000bacc  btr     cs:?g_Deinit@@3W4DeinitFlags@@A, 0Ah; DeinitFlags g_Deinit
0x18000bad4  call    ?NhDeregisterNSINotifications@@YAXXZ; NhDeregisterNSINotifications(void)
0x18000bad9  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000badf  bt      eax, 8
0x18000bae3  jnb     short loc_18000BB33
0x18000bae5  xor     ecx, ecx; unsigned __int8
0x18000bae7  call    ?NhRegisterWmiNotification@@YAKE@Z; NhRegisterWmiNotification(uchar)
0x18000baec  mov     ebx, eax
0x18000baee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000baf5  cmp     rcx, rbp
0x18000baf8  jz      short loc_18000BB21
0x18000bafa  cmp     [rcx+19h], sil
0x18000bafe  jb      short loc_18000BB21
0x18000bb00  test    [rcx+1Ch], dil
0x18000bb04  jz      short loc_18000BB21
0x18000bb06  mov     rcx, [rcx+10h]
0x18000bb0a  mov     edx, 38h ; '8'
0x18000bb0f  mov     r9d, eax
0x18000bb12  mov     r8, r14
0x18000bb15  call    WPP_SF_d
0x18000bb1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb21  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000bb27  btr     eax, 8
0x18000bb2b  mov     cs:?g_Deinit@@3W4DeinitFlags@@A, eax; DeinitFlags g_Deinit
0x18000bb31  jmp     short loc_18000BB3A
0x18000bb33  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb3a  mov     rdx, cs:?g_hWaitObject@@3PEAXEA; void * g_hWaitObject
0x18000bb41  test    rdx, rdx
0x18000bb44  jz      short loc_18000BBA4
0x18000bb46  mov     rcx, rdx; WaitHandle
0x18000bb49  call    cs:__imp_UnregisterWait
0x18000bb4f  test    eax, eax
0x18000bb51  jnz     short loc_18000BB8C
0x18000bb53  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb5a  cmp     rcx, rbp
0x18000bb5d  jz      short loc_18000BB93
0x18000bb5f  cmp     [rcx+19h], sil
0x18000bb63  jb      short loc_18000BB93
0x18000bb65  test    [rcx+1Ch], dil
0x18000bb69  jz      short loc_18000BB93
0x18000bb6b  call    cs:__imp_GetLastError
0x18000bb71  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb78  mov     edx, 39h ; '9'
0x18000bb7d  mov     r9d, eax
0x18000bb80  mov     r8, r14
0x18000bb83  mov     rcx, [rcx+10h]
0x18000bb87  call    WPP_SF_d
0x18000bb8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb93  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000bb99  mov     cs:?g_hWaitObject@@3PEAXEA, 0; void * g_hWaitObject
0x18000bba4  test    al, 10h
0x18000bba6  jz      short loc_18000BBBB
0x18000bba8  and     eax, 0FFFFFFEFh
0x18000bbab  mov     cs:?g_fLanTimerStarted@@3HA, 0; int g_fLanTimerStarted
0x18000bbb5  mov     cs:?g_Deinit@@3W4DeinitFlags@@A, eax; DeinitFlags g_Deinit
0x18000bbbb  cmp     rcx, rbp
0x18000bbbe  jz      short loc_18000BC11
0x18000bbc0  cmp     [rcx+19h], sil
0x18000bbc4  jb      short loc_18000BC11
0x18000bbc6  test    [rcx+1Ch], dil
0x18000bbca  jz      short loc_18000BC11
0x18000bbcc  mov     edx, 3Ah ; ':'
0x18000bbd1  jmp     short loc_18000BBFB
0x18000bbd3  mov     ecx, 3E8h; dwMilliseconds
0x18000bbd8  call    cs:__imp_Sleep
0x18000bbde  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbe5  cmp     rcx, rbp
0x18000bbe8  jz      short loc_18000BC11
0x18000bbea  cmp     [rcx+19h], sil
0x18000bbee  jb      short loc_18000BC11
0x18000bbf0  test    [rcx+1Ch], dil
0x18000bbf4  jz      short loc_18000BC11
0x18000bbf6  mov     edx, 3Bh ; ';'
0x18000bbfb  mov     r9d, cs:?g_nThreads@@3KA; ulong g_nThreads
0x18000bc02  mov     r8, r14
0x18000bc05  mov     rcx, [rcx+10h]
0x18000bc09  dec     r9d
0x18000bc0c  call    WPP_SF_d
0x18000bc11  cmp     cs:?g_nThreads@@3KA, edi; ulong g_nThreads
0x18000bc17  ja      short loc_18000BBD3
0x18000bc19  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000bc1e  call    cs:__imp_Sleep
0x18000bc24  test    cs:?g_Deinit@@3W4DeinitFlags@@A, 200h; DeinitFlags g_Deinit
0x18000bc2e  jz      short loc_18000BC6B
0x18000bc30  call    ?LanSvcDeinitRPCServer@@YAKXZ; LanSvcDeinitRPCServer(void)
0x18000bc35  mov     ebx, eax
0x18000bc37  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc3e  cmp     rcx, rbp
0x18000bc41  jz      short loc_18000BC63
0x18000bc43  cmp     [rcx+19h], sil
0x18000bc47  jb      short loc_18000BC63
0x18000bc49  test    [rcx+1Ch], dil
0x18000bc4d  jz      short loc_18000BC63
0x18000bc4f  mov     rcx, [rcx+10h]
0x18000bc53  mov     edx, 3Ch ; '<'
0x18000bc58  mov     r9d, eax
0x18000bc5b  mov     r8, r14
0x18000bc5e  call    WPP_SF_d
0x18000bc63  btr     cs:?g_Deinit@@3W4DeinitFlags@@A, 9; DeinitFlags g_Deinit
0x18000bc6b  call    IsLANGPADeInitPresent
0x18000bc70  test    al, al
0x18000bc72  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000bc78  jz      short loc_18000BCCB
0x18000bc7a  test    al, al
0x18000bc7c  jns     short loc_18000BCCB
0x18000bc7e  call    cs:__imp_LANGPADeInit
0x18000bc84  mov     ebx, eax
0x18000bc86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc8d  cmp     rcx, rbp
0x18000bc90  jz      short loc_18000BCB9
0x18000bc92  cmp     [rcx+19h], sil
0x18000bc96  jb      short loc_18000BCB9
0x18000bc98  test    [rcx+1Ch], dil
0x18000bc9c  jz      short loc_18000BCB9
0x18000bc9e  mov     rcx, [rcx+10h]
0x18000bca2  mov     edx, 3Dh ; '='
0x18000bca7  mov     r9d, eax
0x18000bcaa  mov     r8, r14
0x18000bcad  call    WPP_SF_d
0x18000bcb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcb9  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000bcbf  btr     eax, 7
0x18000bcc3  mov     cs:?g_Deinit@@3W4DeinitFlags@@A, eax; DeinitFlags g_Deinit
0x18000bcc9  jmp     short loc_18000BCD2
0x18000bccb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcd2  test    al, 40h
0x18000bcd4  jz      short loc_18000BD1F
0x18000bcd6  call    ?WimDeinit@@YAKXZ; WimDeinit(void)
0x18000bcdb  mov     ebx, eax
0x18000bcdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bce4  cmp     rcx, rbp
0x18000bce7  jz      short loc_18000BD10
0x18000bce9  cmp     [rcx+19h], sil
0x18000bced  jb      short loc_18000BD10
0x18000bcef  test    [rcx+1Ch], dil
0x18000bcf3  jz      short loc_18000BD10
0x18000bcf5  mov     rcx, [rcx+10h]
0x18000bcf9  mov     edx, 3Eh ; '>'
0x18000bcfe  mov     r9d, eax
0x18000bd01  mov     r8, r14
0x18000bd04  call    WPP_SF_d
0x18000bd09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd10  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000bd16  and     eax, 0FFFFFFBFh
0x18000bd19  mov     cs:?g_Deinit@@3W4DeinitFlags@@A, eax; DeinitFlags g_Deinit
0x18000bd1f  bt      eax, 0Ch
0x18000bd23  jnb     short loc_18000BD70
0x18000bd25  call    cs:__imp_Dot3MsmDeInit
0x18000bd2b  mov     ebx, eax
0x18000bd2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd34  cmp     rcx, rbp
0x18000bd37  jz      short loc_18000BD60
0x18000bd39  cmp     [rcx+19h], sil
0x18000bd3d  jb      short loc_18000BD60
0x18000bd3f  test    [rcx+1Ch], dil
0x18000bd43  jz      short loc_18000BD60
0x18000bd45  mov     rcx, [rcx+10h]
0x18000bd49  mov     edx, 3Fh ; '?'
0x18000bd4e  mov     r9d, eax
0x18000bd51  mov     r8, r14
0x18000bd54  call    WPP_SF_d
0x18000bd59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd60  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000bd66  btr     eax, 0Ch
0x18000bd6a  mov     cs:?g_Deinit@@3W4DeinitFlags@@A, eax; DeinitFlags g_Deinit
0x18000bd70  test    al, 20h
0x18000bd72  jz      short loc_18000BDBD
0x18000bd74  call    ?PmDeinit@@YAKXZ; PmDeinit(void)
0x18000bd79  mov     ebx, eax
0x18000bd7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd82  cmp     rcx, rbp
0x18000bd85  jz      short loc_18000BDAE
0x18000bd87  cmp     [rcx+19h], sil
0x18000bd8b  jb      short loc_18000BDAE
0x18000bd8d  test    [rcx+1Ch], dil
0x18000bd91  jz      short loc_18000BDAE
0x18000bd93  mov     rcx, [rcx+10h]
0x18000bd97  mov     edx, 40h ; '@'
0x18000bd9c  mov     r9d, eax
0x18000bd9f  mov     r8, r14
0x18000bda2  call    WPP_SF_d
0x18000bda7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdae  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000bdb4  and     eax, 0FFFFFFDFh
0x18000bdb7  mov     cs:?g_Deinit@@3W4DeinitFlags@@A, eax; DeinitFlags g_Deinit
0x18000bdbd  test    al, 8
0x18000bdbf  jz      short loc_18000BE0A
0x18000bdc1  call    ?TmDeinit@@YAKXZ; TmDeinit(void)
0x18000bdc6  mov     ebx, eax
0x18000bdc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdcf  cmp     rcx, rbp
0x18000bdd2  jz      short loc_18000BDFB
0x18000bdd4  cmp     [rcx+19h], sil
0x18000bdd8  jb      short loc_18000BDFB
0x18000bdda  test    [rcx+1Ch], dil
0x18000bdde  jz      short loc_18000BDFB
0x18000bde0  mov     rcx, [rcx+10h]
0x18000bde4  mov     edx, 41h ; 'A'
0x18000bde9  mov     r9d, eax
0x18000bdec  mov     r8, r14
0x18000bdef  call    WPP_SF_d
0x18000bdf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdfb  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000be01  and     eax, 0FFFFFFF7h
0x18000be04  mov     cs:?g_Deinit@@3W4DeinitFlags@@A, eax; DeinitFlags g_Deinit
0x18000be0a  test    sil, al
0x18000be0d  jz      short loc_18000BE76
0x18000be0f  cmp     rcx, rbp
0x18000be12  jz      short loc_18000BE42
0x18000be14  cmp     [rcx+19h], sil
0x18000be18  jb      short loc_18000BE42
0x18000be1a  test    [rcx+1Ch], dil
0x18000be1e  jz      short loc_18000BE42
0x18000be20  mov     rcx, [rcx+10h]
0x18000be24  lea     r8, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids
0x18000be2b  mov     edx, 0Ch
0x18000be30  call    WPP_SF_
0x18000be35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be3c  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000be42  xor     ebx, ebx
0x18000be44  cmp     rcx, rbp
0x18000be47  jz      short loc_18000BE6D
0x18000be49  cmp     [rcx+19h], sil
0x18000be4d  jb      short loc_18000BE6D
0x18000be4f  test    [rcx+1Ch], dil
0x18000be53  jz      short loc_18000BE6D
0x18000be55  mov     rcx, [rcx+10h]
0x18000be59  lea     edx, [rbx+42h]
0x18000be5c  xor     r9d, r9d
0x18000be5f  mov     r8, r14
0x18000be62  call    WPP_SF_d
0x18000be67  mov     eax, cs:?g_Deinit@@3W4DeinitFlags@@A; DeinitFlags g_Deinit
0x18000be6d  and     eax, 0FFFFFFFBh
0x18000be70  mov     cs:?g_Deinit@@3W4DeinitFlags@@A, eax; DeinitFlags g_Deinit
0x18000be76  test    al, 2
0x18000be78  jz      short loc_18000BEBC
0x18000be7a  call    ?LanSvcContextDeinit@@YAKXZ; LanSvcContextDeinit(void)
0x18000be7f  mov     ebx, eax
0x18000be81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be88  cmp     rcx, rbp
0x18000be8b  jz      short loc_18000BEAD
0x18000be8d  cmp     [rcx+19h], sil
  ... truncated ...
```
