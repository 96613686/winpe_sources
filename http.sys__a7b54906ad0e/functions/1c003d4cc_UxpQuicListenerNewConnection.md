# UxpQuicListenerNewConnection

- ea: `0x1c003d4cc`
- end: `0x1c003de01`
- name: `UxpQuicListenerNewConnection`
- size: `2357`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting`

## callers

- `0x1c003d460`

## callees

- `0x1c0001ae0`
- `0x1c0003db0`
- `0x1c001a4b0`
- `0x1c001a548`
- `0x1c001b610`
- `0x1c001b640`
- `0x1c001b900`
- `0x1c00366c4`
- `0x1c0036a7c`
- `0x1c0036b84`
- `0x1c00381e4`
- `0x1c0038c30`
- `0x1c00398ec`
- `0x1c003b6ac`
- `0x1c003d4cc`
- `0x1c008f3ec`
- `0x1c008f570`
- `0x1c008f680`
- `0x1c0098e5c`
- `0x1c0098fb8`
- `0x1c00990e8`
- `0x1c00a3568`
- `0x1c00a96e0`
- `0x1c00d6070`
- `0x1c00d60c4`
- `0x1c012f794`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1c003d62a`
- `ntoskrnl!KeReadStateEvent` at `0x1c003d62a`
- `ntoskrnl!KeBugCheckEx` at `0x1c003dc7c`
- `ntoskrnl!KeBugCheckEx` at `0x1c003dce2`
- `ntoskrnl!KeBugCheckEx` at `0x1c003dd88`
- `ntoskrnl!KeBugCheckEx` at `0x1c003ddf4`
- `ntoskrnl!KeBugCheckEx` at `0x1c003dc7c`
- `ntoskrnl!KeBugCheckEx` at `0x1c003dce2`
- `ntoskrnl!KeBugCheckEx` at `0x1c003dd88`
- `ntoskrnl!KeBugCheckEx` at `0x1c003ddf4`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c003da9d`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c003daf3`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c003da9d`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c003daf3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c003dc00`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c003dd0f`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c003dc00`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c003dd0f`
- `HAL!KeQueryPerformanceCounter` at `0x1c003d6b1`
- `HAL!KeQueryPerformanceCounter` at `0x1c003d6b1`

## pseudocode

```c
__int64 __fastcall UxpQuicListenerNewConnection(_QWORD *a1, __int64 a2, LARGE_INTEGER a3, _QWORD *a4)
{
  unsigned int v7; // r12d
  __int64 v9; // rdx
  char v10; // r13
  __int16 v11; // si
  __int64 v12; // rcx
  unsigned __int16 v13; // ax
  int Connection; // edi
  LARGE_INTEGER *v15; // rbx
  char v16; // si
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER *v18; // rcx
  LARGE_INTEGER *v19; // r13
  LARGE_INTEGER v20; // r13
  ADDRESS_FAMILY *v21; // r10
  ADDRESS_FAMILY v22; // cx
  ADDRESS_FAMILY *v23; // r11
  UCHAR v24; // al
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  __int64 v28; // r10
  __int64 v29; // r11
  unsigned int v30; // ecx
  ADDRESS_FAMILY *v31; // rax
  ADDRESS_FAMILY v32; // cx
  __int16 v33; // dx
  ADDRESS_FAMILY *v34; // rax
  ADDRESS_FAMILY v35; // cx
  UCHAR v36; // al
  int v37; // ecx
  __int64 v39; // rax
  __int64 v40; // rax
  int v41; // ecx
  PVOID PoolWithTagPriority; // rax
  DWORD v43; // eax
  PVOID v44; // rax
  DWORD v45; // eax
  int ControlStreams; // eax
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v48; // r9
  __int64 v49; // rcx
  LARGE_INTEGER *v50; // rsi
  struct _KPROCESS *v51; // rax
  __int64 v52; // r9
  LARGE_INTEGER *v53; // rbx
  int BugCheckParameter4; // [rsp+20h] [rbp-E0h]
  ULONG_PTR BugCheckParameter4a; // [rsp+20h] [rbp-E0h]
  __int64 v56; // [rsp+28h] [rbp-D8h]
  __int64 v57; // [rsp+30h] [rbp-D0h]
  __int64 QuadPart; // [rsp+38h] [rbp-C8h]
  char v59[6]; // [rsp+72h] [rbp-8Eh] BYREF
  LARGE_INTEGER *v60; // [rsp+78h] [rbp-88h] BYREF
  __int64 v61; // [rsp+80h] [rbp-80h]
  LARGE_INTEGER v62; // [rsp+88h] [rbp-78h]
  int v63[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v64; // [rsp+A0h] [rbp-60h]
  __int128 v65; // [rsp+B0h] [rbp-50h]
  LARGE_INTEGER *v66; // [rsp+C0h] [rbp-40h]
  _QWORD *v67; // [rsp+C8h] [rbp-38h]
  __int128 v68; // [rsp+D0h] [rbp-30h]
  __int128 v69; // [rsp+E0h] [rbp-20h]
  __int128 v70; // [rsp+F0h] [rbp-10h]
  __int128 v71; // [rsp+100h] [rbp+0h] BYREF
  __int128 v72; // [rsp+110h] [rbp+10h] BYREF
  __int128 v73; // [rsp+120h] [rbp+20h] BYREF
  __int128 v74; // [rsp+130h] [rbp+30h] BYREF
  __int128 v75; // [rsp+140h] [rbp+40h] BYREF
  __int128 v76; // [rsp+150h] [rbp+50h] BYREF
  __int128 v77; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v78[3]; // [rsp+170h] [rbp+70h] BYREF
  char v79; // [rsp+188h] [rbp+88h]
  int v80; // [rsp+189h] [rbp+89h]
  __int16 v81; // [rsp+18Dh] [rbp+8Dh]
  char v82; // [rsp+18Fh] [rbp+8Fh]
  _QWORD v83[3]; // [rsp+190h] [rbp+90h] BYREF
  char v84; // [rsp+1A8h] [rbp+A8h]
  int v85; // [rsp+1A9h] [rbp+A9h]
  __int16 v86; // [rsp+1ADh] [rbp+ADh]
  char v87; // [rsp+1AFh] [rbp+AFh]
  __int128 v88; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v89[24]; // [rsp+1C0h] [rbp+C0h] BYREF

  v67 = a4;
  v60 = 0;
  v62 = a3;
  v59[0] = 0;
  v7 = 0;
  v88 = 0;
  memset(v89, 0, sizeof(v89));
  v61 = 0;
  v10 = 0;
  v11 = 8000;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x40000000) != 0 )
  {
    v12 = *(unsigned __int16 *)(a2 + 28);
    v13 = *(_WORD *)(a2 + 28);
    BugCheckParameter4 = v13;
    if ( (unsigned __int16)v12 > 0x1F40u )
      v13 = 8000;
    DWORD1(v64) = 0;
    LOWORD(v64) = v13;
    WORD1(v64) = v13;
    *((_QWORD *)&v64 + 1) = *(_QWORD *)(a2 + 48);
    v73 = v64;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))WPP_SF_q_CTDSTR_dq)(
      v12,
      v9,
      a1,
      &v73,
      BugCheckParameter4,
      (LARGE_INTEGER)a3.QuadPart);
  }
  *a4 = 0;
  if ( !a1[3] )
  {
    Connection = -1073741436;
LABEL_7:
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1[25] + 7336LL)) == 1 )
      UlEnablePeriodicScavenger(a1[25] + 7344LL);
    v15 = v60;
    v16 = 0;
    goto LABEL_26;
  }
  if ( !*(_QWORD *)(a2 + 48) )
  {
    if ( (WPP_MAIN_CB.DeviceType & 0x40000000) != 0 )
      WPP_SF_q(53, WPP_6c9563e425ff3808296af7352dd0dbf9_Traceguids, a1);
    Connection = -1073741811;
    v7 = 21;
    goto LABEL_7;
  }
  if ( *(_BYTE *)(a1[25] + 7264LL) && !KeReadStateEvent(UxHighNonPagedPoolEvent) )
  {
    Connection = -1073741258;
    v7 = 2;
    goto LABEL_7;
  }
  Connection = (*(__int64 (__fastcall **)(LARGE_INTEGER, __int64, __int64, __int64, char *))(UxQuicFuncTable + 32))(
                 a3,
                 3,
                 15,
                 1,
                 v59);
  if ( Connection < 0 )
    goto LABEL_7;
  v7 = 22;
  Connection = UxQuicCreateConnection(0, (_DWORD)a1, a1[25], a1[24], (__int64)&v60);
  if ( Connection < 0 )
    goto LABEL_7;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v18 = v60;
  v66 = v60;
  v60[167] = PerformanceCounter;
  _InterlockedIncrement(&v18->HighPart);
  v15 = v60;
  v19 = v60 + 138;
  Connection = UxAllocateOpaqueId(&v60[138], 7, v60);
  if ( Connection < 0 )
    goto LABEL_24;
  if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x40000000) != 0 )
    WPP_SF_qq(54, WPP_6c9563e425ff3808296af7352dd0dbf9_Traceguids, v15, v19->QuadPart);
  if ( *(_BYTE *)(a1[25] + 1568LL) )
  {
    v63[0] = 192;
    *(_OWORD *)&v15[136].LowPart = UlEtwBaseOpaqueIdActivityGuid;
    v15[136] = *v19;
    v88 = *(_OWORD *)&v15[136].LowPart;
    v20 = v62;
    Connection = (*(__int64 (__fastcall **)(LARGE_INTEGER, __int64, __int64, int *, _QWORD *))(UxQuicFuncTable + 40))(
                   v62,
                   3,
                   10,
                   v63,
                   v89);
    if ( Connection < 0 )
    {
LABEL_24:
      v16 = 0;
LABEL_25:
      v10 = 1;
      goto LABEL_26;
    }
  }
  else
  {
    v20 = v62;
  }
  v39 = *(_QWORD *)(a2 + 8);
  *(_OWORD *)&v15[6].LowPart = *(_OWORD *)v39;
  v15[8] = *(LARGE_INTEGER *)(v39 + 16);
  v15[9].LowPart = *(_DWORD *)(v39 + 24);
  v40 = *(_QWORD *)(a2 + 16);
  *(_OWORD *)((char *)&v15[9].QuadPart + 4) = *(_OWORD *)v40;
  *(LARGE_INTEGER *)((char *)v15 + 92) = *(LARGE_INTEGER *)(v40 + 16);
  v15[12].HighPart = *(_DWORD *)(v40 + 24);
  Connection = UxSslValidateSni(a1[25], *(_QWORD *)(a2 + 48), *(unsigned __int16 *)(a2 + 28), &v15[4]);
  if ( Connection < 0 )
    goto LABEL_24;
  if ( *(_BYTE *)(v15[172].QuadPart + 1568) )
  {
    v41 = *(unsigned __int16 *)(a2 + 28);
    v78[2] = v15[172].QuadPart;
    v80 = 0;
    v78[0] = v15 + 136;
    QuadPart = v15[5].QuadPart;
    v57 = *(_QWORD *)(a2 + 48);
    v81 = 0;
    v82 = 0;
    v78[1] = 0;
    v79 = 0;
    McTemplateK0pqqbr2z_UlEtwWriteEventWrapper(v41, 0, (unsigned int)v78, (_DWORD)v15, Connection, v41, v57, QuadPart);
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x40000000) != 0 )
  {
    if ( *(_WORD *)(a2 + 28) <= 0x1F40u )
      v11 = *(_WORD *)(a2 + 28);
    *((_QWORD *)&v65 + 1) = *(_QWORD *)(a2 + 48);
    DWORD1(v65) = 0;
    LOWORD(v65) = v11;
    WORD1(v65) = v11;
    v74 = v65;
    WPP_SF_qd_CTDSTR_Z(
      55,
      (unsigned int)WPP_6c9563e425ff3808296af7352dd0dbf9_Traceguids,
      (_DWORD)v15,
      Connection,
      (__int64)&v74,
      (__int64)&v15[4]);
  }
  PoolWithTagPriority = ExAllocatePoolWithTagPriority(
                          PagedPool,
                          *(unsigned __int16 *)(a2 + 24),
                          0x56537855u,
                          LowPoolPriority);
  v15[107].QuadPart = (LONGLONG)PoolWithTagPriority;
  if ( !PoolWithTagPriority
    || (v43 = *(unsigned __int16 *)(a2 + 24),
        v15[108].LowPart = v43,
        memmove((void *)v15[107].QuadPart, *(const void **)(a2 + 32), v43),
        v44 = ExAllocatePoolWithTagPriority(PagedPool, *(unsigned __int16 *)(a2 + 26), 0x56537855u, LowPoolPriority),
        (v15[109].QuadPart = (LONGLONG)v44) == 0) )
  {
    v16 = 0;
    Connection = -1073741670;
    goto LABEL_25;
  }
  v45 = *(unsigned __int16 *)(a2 + 26);
  v15[110].LowPart = v45;
  memmove((void *)v15[109].QuadPart, *(const void **)(a2 + 40), v45);
  v15[17] = v20;
  (*(void (__fastcall **)(LARGE_INTEGER, __int64 (__fastcall *)(), LARGE_INTEGER *))(UxQuicFuncTable + 24))(
    v20,
    UxpQuicConnectionCallbackHandler,
    v15);
  _InterlockedIncrement(&v66->HighPart);
  v15 = v60;
  v16 = 1;
  v10 = 0;
  ControlStreams = UxpQuicConnectionCreateControlStreams(v60);
  if ( ControlStreams < 0 )
  {
    if ( (WPP_MAIN_CB.DeviceType & 0x40000000) != 0 )
      WPP_SF_qD(56, WPP_6c9563e425ff3808296af7352dd0dbf9_Traceguids, v15, (unsigned int)ControlStreams);
    Connection = 259;
LABEL_26:
    if ( !v15 )
      goto LABEL_29;
    if ( v16 )
    {
      UxQuicAbortConnection(v15, v7);
      goto LABEL_29;
    }
    if ( v15[138].QuadPart )
    {
      UxFreeOpaqueId();
      v15[138].QuadPart = 0;
    }
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(&v15->HighPart, 0xFFFFFFFF) == 1 )
      {
        CurrentProcess = IoGetCurrentProcess();
        v15 = v60;
        v49 = v60[171].QuadPart;
        v50 = v60 + 112;
        if ( UxSystemProcess != CurrentProcess )
        {
          if ( v50->QuadPart || v60[114].QuadPart || v60[116].QuadPart )
            KeBugCheckEx(0xFAu, 1u, (ULONG_PTR)&v60[112], (ULONG_PTR)"minio\\http\\sys\\quicconn.h", 0x29Fu);
LABEL_63:
          LODWORD(v56) = -1;
          LOBYTE(v48) = 1;
          UlThreadPoolEnqueueWorkItem(0, &v60[112], UxQuicFreeConnection, v48, v49, v56);
          goto LABEL_72;
        }
        v71 = 0;
        if ( v50->QuadPart || v60[114].QuadPart || v60[116].QuadPart )
          KeBugCheckEx(0xFAu, 1u, (ULONG_PTR)&v60[112], (ULONG_PTR)"minio\\http\\sys\\quicconn.h", 0x2A6u);
        if ( KeGetCurrentIrql() )
          goto LABEL_63;
        UxPodAttachThread(v49, (__int64)&v71);
        UxQuicFreeConnection(v50);
        UxPodDetachThread((__int64)&v71);
      }
      else
      {
        v15 = v60;
      }
    }
LABEL_72:
    v15[20].LowPart = v7;
    if ( _InterlockedExchangeAdd(&v15->HighPart, 0xFFFFFFFF) == 1 )
    {
      v51 = IoGetCurrentProcess();
      v52 = v60[171].QuadPart;
      v53 = v60 + 112;
      if ( UxSystemProcess == v51 )
      {
        v72 = 0;
        if ( v53->QuadPart || v60[114].QuadPart || v60[116].QuadPart )
          KeBugCheckEx(0xFAu, 1u, (ULONG_PTR)&v60[112], (ULONG_PTR)"minio\\http\\sys\\quicconn.h", 0x2A6u);
        if ( !KeGetCurrentIrql() )
        {
          UxPodAttachThread(v52, (__int64)&v72);
          UxQuicFreeConnection(v53);
          UxPodDetachThread((__int64)&v72);
          goto LABEL_29;
        }
      }
      else if ( v53->QuadPart || v60[114].QuadPart || v60[116].QuadPart )
      {
        KeBugCheckEx(0xFAu, 1u, (ULONG_PTR)&v60[112], (ULONG_PTR)"minio\\http\\sys\\quicconn.h", 0x29Fu);
      }
      LODWORD(v56) = -1;
      BugCheckParameter4a = v52;
      LOBYTE(v52) = 1;
      UlThreadPoolEnqueueWorkItem(0, &v60[112], UxQuicFreeConnection, v52, BugCheckParameter4a, v56);
    }
LABEL_29:
    LODWORD(v15) = v61;
    goto LABEL_30;
  }
  Connection = UxQuicListenerEndpointLookup(v15, 0, 0, v67);
  if ( Connection < 0 )
  {
    Connection = 259;
    v7 = 32;
    goto LABEL_26;
  }
  LOBYTE(v7) = 0;
LABEL_30:
  if ( *(_BYTE *)(a1[25] + 1568LL) )
  {
    v21 = *(ADDRESS_FAMILY **)(a2 + 16);
    v83[2] = a1[25];
    v22 = *v21;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v83[0] = &v88;
    v83[1] = 0;
    v84 = 0;
    SOCKADDR_SIZE(v22);
    v24 = SOCKADDR_SIZE(*v23);
    McTemplateK0xpqbr2qbr4qbr6qq_UlEtwWriteEventWrapper(
      v25,
      v24,
      (unsigned int)v83,
      v89[0],
      (char)v15,
      v24,
      v29,
      v26,
      v28,
      v27,
      *(_QWORD *)(a2 + 48),
      v7,
      Connection);
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x40000000) != 0 )
  {
    v30 = *(unsigned __int16 *)(a2 + 28);
    v68 = *(unsigned __int64 *)(a2 + 48);
    v31 = *(ADDRESS_FAMILY **)(a2 + 16);
    if ( v30 > 0xF800 )
      LOWORD(v30) = -2048;
    WORD4(v68) = v30;
    v75 = v68;
    v32 = *v31;
    v69 = (unsigned __int64)v31;
    v33 = SOCKADDR_SIZE(v32);
    v34 = *(ADDRESS_FAMILY **)(a2 + 8);
    v70 = 0;
    WORD4(v69) = v33;
    v76 = v69;
    v35 = *v34;
    *(_QWORD *)&v70 = v34;
    v36 = SOCKADDR_SIZE(v35);
    WORD4(v70) = v36;
    v77 = v70;
    WPP_SF_qi_SOCKADDR__SOCKADDR__HEX_Ld(
      v37,
      v36,
      (_DWORD)v15,
      v89[0],
      (__int64)&v77,
      (__int64)&v76,
      (__int64)&v75,
      v7,
      Connection);
  }
  return (unsigned int)Connection;
}

```

## disassembly

```asm
0x1c003d4cc  push    rbp
0x1c003d4ce  push    rbx
0x1c003d4cf  push    rsi
0x1c003d4d0  push    rdi
0x1c003d4d1  push    r12
0x1c003d4d3  push    r13
0x1c003d4d5  push    r14
0x1c003d4d7  push    r15
0x1c003d4d9  lea     rbp, [rsp-198h]
0x1c003d4e1  sub     rsp, 298h
0x1c003d4e8  mov     rax, cs:__security_cookie
0x1c003d4ef  xor     rax, rsp
0x1c003d4f2  mov     [rbp+1D0h+var_50], rax
0x1c003d4f9  xor     esi, esi
0x1c003d4fb  mov     [rbp+1D0h+var_208], r9
0x1c003d4ff  mov     rbx, r8
0x1c003d502  mov     [rsp+2D0h+var_258], rsi
0x1c003d507  mov     r14, rdx
0x1c003d50a  mov     [rbp+1D0h+var_248], rbx
0x1c003d50e  mov     r15, rcx
0x1c003d511  mov     [rsp+2D0h+var_260], sil
0x1c003d516  xorps   xmm0, xmm0
0x1c003d519  mov     [rsp+2D0h+var_25E], sil
0x1c003d51e  xor     edx, edx; Val
0x1c003d520  lea     rcx, [rbp+1D0h+var_110]; void *
0x1c003d527  mov     r8d, 0C0h; Size
0x1c003d52d  mov     r12d, esi
0x1c003d530  movups  [rbp+1D0h+var_120], xmm0
0x1c003d537  mov     rdi, r9
0x1c003d53a  call    memset
0x1c003d53f  mov     [rbp+1D0h+var_250], rsi
0x1c003d543  mov     r13b, sil
0x1c003d546  test    dword ptr cs:WPP_MAIN_CB.Queue, 40000000h
0x1c003d550  mov     esi, 1F40h
0x1c003d555  jz      short loc_1C003D596
0x1c003d557  movzx   ecx, word ptr [r14+1Ch]
0x1c003d55c  lea     r9, [rbp+1D0h+var_1B0]
0x1c003d560  mov     eax, ecx
0x1c003d562  mov     [rsp+2D0h+var_2A8], rbx
0x1c003d567  cmp     cx, si
0x1c003d56a  mov     dword ptr [rsp+2D0h+BugCheckParameter4], ecx
0x1c003d56e  mov     r8, r15
0x1c003d571  cmova   eax, esi
0x1c003d574  and     dword ptr [rbp+1D0h+var_230+4], r12d
0x1c003d578  mov     word ptr [rbp+1D0h+var_230], ax
0x1c003d57c  mov     word ptr [rbp+1D0h+var_230+2], ax
0x1c003d580  mov     rax, [r14+30h]
0x1c003d584  mov     qword ptr [rbp+1D0h+var_230+8], rax
0x1c003d588  movaps  xmm0, [rbp+1D0h+var_230]
0x1c003d58c  movdqa  [rbp+1D0h+var_1B0], xmm0
0x1c003d591  call    WPP_SF_q_CTDSTR_dq
0x1c003d596  xor     ecx, ecx
0x1c003d598  mov     [rdi], rcx
0x1c003d59b  cmp     [r15+18h], rcx
0x1c003d59f  jnz     short loc_1C003D5E1
0x1c003d5a1  mov     edi, 0C0000184h
0x1c003d5a6  mov     rcx, [r15+0C8h]
0x1c003d5ad  mov     eax, 1
0x1c003d5b2  lock xadd [rcx+1CA8h], eax
0x1c003d5ba  inc     eax
0x1c003d5bc  cmp     eax, 1
0x1c003d5bf  jnz     short loc_1C003D5D4
0x1c003d5c1  mov     rcx, [r15+0C8h]
0x1c003d5c8  add     rcx, 1CB0h
0x1c003d5cf  call    UlEnablePeriodicScavenger
0x1c003d5d4  mov     rbx, [rsp+2D0h+var_258]
0x1c003d5d9  mov     sil, r13b
0x1c003d5dc  jmp     loc_1C003D7AA
0x1c003d5e1  cmp     [r14+30h], rcx
0x1c003d5e5  jnz     short loc_1C003D614
0x1c003d5e7  test    cs:WPP_MAIN_CB.DeviceType, 40000000h
0x1c003d5f1  jz      short loc_1C003D607
0x1c003d5f3  mov     ecx, 35h ; '5'
0x1c003d5f8  lea     rdx, WPP_6c9563e425ff3808296af7352dd0dbf9_Traceguids
0x1c003d5ff  mov     r8, r15
0x1c003d602  call    WPP_SF_q
0x1c003d607  mov     edi, 0C000000Dh
0x1c003d60c  mov     r12d, 15h
0x1c003d612  jmp     short loc_1C003D5A6
0x1c003d614  mov     rax, [r15+0C8h]
0x1c003d61b  cmp     [rax+1C60h], cl
0x1c003d621  jz      short loc_1C003D648
0x1c003d623  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x1c003d62a  call    cs:__imp_KeReadStateEvent
0x1c003d631  nop     dword ptr [rax+rax+00h]
0x1c003d636  test    eax, eax
0x1c003d638  jnz     short loc_1C003D648
0x1c003d63a  mov     edi, 0C0000236h
0x1c003d63f  lea     r12d, [rax+2]
0x1c003d643  jmp     loc_1C003D5A6
0x1c003d648  mov     rax, cs:UxQuicFuncTable
0x1c003d64f  lea     rcx, [rsp+2D0h+var_25E]
0x1c003d654  mov     edx, 3
0x1c003d659  mov     [rsp+2D0h+BugCheckParameter4], rcx
0x1c003d65e  mov     rcx, rbx
0x1c003d661  mov     rax, [rax+20h]
0x1c003d665  lea     r9d, [rdx-2]
0x1c003d669  lea     r8d, [rdx+0Ch]
0x1c003d66d  call    cs:__guard_dispatch_icall_fptr
0x1c003d673  mov     edi, eax
0x1c003d675  test    eax, eax
0x1c003d677  js      loc_1C003D5A6
0x1c003d67d  mov     r9, [r15+0C0h]
0x1c003d684  lea     rax, [rsp+2D0h+var_258]
0x1c003d689  mov     r8, [r15+0C8h]
0x1c003d690  mov     rdx, r15
0x1c003d693  xor     ecx, ecx
0x1c003d695  mov     [rsp+2D0h+BugCheckParameter4], rax
0x1c003d69a  mov     r12d, 16h
0x1c003d6a0  call    UxQuicCreateConnection
0x1c003d6a5  mov     edi, eax
0x1c003d6a7  test    eax, eax
0x1c003d6a9  js      loc_1C003D5A6
0x1c003d6af  xor     ecx, ecx; PerformanceFrequency
0x1c003d6b1  call    cs:__imp_KeQueryPerformanceCounter
0x1c003d6b8  nop     dword ptr [rax+rax+00h]
0x1c003d6bd  mov     rcx, [rsp+2D0h+var_258]
0x1c003d6c2  mov     [rbp+1D0h+var_210], rcx
0x1c003d6c6  mov     [rcx+538h], rax
0x1c003d6cd  lock inc dword ptr [rcx+4]
0x1c003d6d1  mov     rbx, [rsp+2D0h+var_258]
0x1c003d6d6  lea     edx, [r12-0Fh]
0x1c003d6db  mov     r8, rbx
0x1c003d6de  mov     [rsp+2D0h+var_25F], 1
0x1c003d6e3  lea     r13, [rbx+450h]
0x1c003d6ea  mov     rcx, r13
0x1c003d6ed  call    UxAllocateOpaqueId
0x1c003d6f2  xor     edx, edx
0x1c003d6f4  mov     edi, eax
0x1c003d6f6  test    eax, eax
0x1c003d6f8  js      loc_1C003D7A2
0x1c003d6fe  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 40000000h
0x1c003d708  jz      short loc_1C003D722
0x1c003d70a  mov     r9, [r13+0]
0x1c003d70e  lea     ecx, [rdx+36h]
0x1c003d711  lea     rdx, WPP_6c9563e425ff3808296af7352dd0dbf9_Traceguids
0x1c003d718  mov     r8, rbx
0x1c003d71b  call    WPP_SF_qq
0x1c003d720  xor     edx, edx
0x1c003d722  mov     rax, [r15+0C8h]
0x1c003d729  cmp     [rax+620h], dl
0x1c003d72f  jz      loc_1C003D961
0x1c003d735  movups  xmm0, cs:UlEtwBaseOpaqueIdActivityGuid
0x1c003d73c  mov     [rbp+1D0h+var_240], 0C0h
0x1c003d743  movdqu  xmmword ptr [rbx+440h], xmm0
0x1c003d74b  mov     rax, [r13+0]
0x1c003d74f  mov     [rbx+440h], rax
0x1c003d756  movups  xmm0, xmmword ptr [rbx+440h]
0x1c003d75d  movdqu  [rbp+1D0h+var_120], xmm0
0x1c003d765  mov     rax, cs:UxQuicFuncTable
0x1c003d76c  lea     rcx, [rbp+1D0h+var_110]
0x1c003d773  mov     r13, [rbp+1D0h+var_248]
0x1c003d777  lea     r9, [rbp+1D0h+var_240]
0x1c003d77b  mov     edx, 3
0x1c003d780  mov     [rsp+2D0h+BugCheckParameter4], rcx
0x1c003d785  mov     rcx, r13
0x1c003d788  mov     rax, [rax+28h]
0x1c003d78c  lea     r8d, [rdx+7]
0x1c003d790  call    cs:__guard_dispatch_icall_fptr
0x1c003d796  xor     edx, edx
0x1c003d798  mov     edi, eax
0x1c003d79a  test    eax, eax
0x1c003d79c  jns     loc_1C003D965
0x1c003d7a2  mov     sil, dl
0x1c003d7a5  mov     r13b, [rsp+2D0h+var_25F]
0x1c003d7aa  test    rbx, rbx
0x1c003d7ad  jz      short loc_1C003D7C3
0x1c003d7af  test    sil, sil
0x1c003d7b2  jz      loc_1C003DBCC
0x1c003d7b8  mov     edx, r12d
0x1c003d7bb  mov     rcx, rbx
0x1c003d7be  call    UxQuicAbortConnection
0x1c003d7c3  xor     r13d, r13d
0x1c003d7c6  mov     rbx, [rbp+1D0h+var_250]
0x1c003d7ca  mov     rax, [r15+0C8h]
0x1c003d7d1  cmp     [rax+620h], r13b
0x1c003d7d8  jz      loc_1C003D87F
0x1c003d7de  mov     r10, [r14+10h]
0x1c003d7e2  mov     r11, [r14+8]
0x1c003d7e6  movzx   r9d, word ptr [r14+1Ch]
0x1c003d7eb  mov     [rbp+1D0h+var_130], rax
0x1c003d7f2  lea     rax, [rbp+1D0h+var_120]
0x1c003d7f9  movzx   ecx, word ptr [r10]; af
0x1c003d7fd  mov     [rbp+1D0h+var_127], r13d
0x1c003d804  mov     [rbp+1D0h+var_123], r13w
0x1c003d80c  mov     [rbp+1D0h+var_121], r13b
0x1c003d813  mov     [rbp+1D0h+var_140], rax
0x1c003d81a  mov     [rbp+1D0h+var_138], r13
0x1c003d821  mov     [rbp+1D0h+var_128], r13b
0x1c003d828  call    SOCKADDR_SIZE
0x1c003d82d  movzx   ecx, word ptr [r11]; af
0x1c003d831  movzx   r8d, al
0x1c003d835  call    SOCKADDR_SIZE
0x1c003d83a  mov     [rsp+2D0h+var_270], edi
0x1c003d83e  mov     [rsp+2D0h+var_278], r12d
0x1c003d843  movzx   edx, al
0x1c003d846  mov     rax, [r14+30h]
0x1c003d84a  mov     [rsp+2D0h+var_280], rax
0x1c003d84f  mov     [rsp+2D0h+var_288], r9d
0x1c003d854  mov     r9, [rbp+1D0h+var_110]
0x1c003d85b  mov     [rsp+2D0h+var_290], r10
0x1c003d860  mov     dword ptr [rsp+2D0h+var_298], r8d
0x1c003d865  lea     r8, [rbp+1D0h+var_140]
0x1c003d86c  mov     [rsp+2D0h+var_2A0], r11
0x1c003d871  mov     dword ptr [rsp+2D0h+var_2A8], edx
0x1c003d875  mov     [rsp+2D0h+BugCheckParameter4], rbx
0x1c003d87a  call    McTemplateK0xpqbr2qbr4qbr6qq_UlEtwWriteEventWrapper
0x1c003d87f  test    dword ptr cs:WPP_MAIN_CB.Queue, 40000000h
0x1c003d889  jz      loc_1C003D93B
0x1c003d88f  movzx   ecx, word ptr [r14+1Ch]
0x1c003d894  xorps   xmm0, xmm0
0x1c003d897  mov     rax, [r14+30h]
0x1c003d89b  mov     edx, 0F800h
0x1c003d8a0  movups  [rbp+1D0h+var_200], xmm0
0x1c003d8a4  cmp     ecx, edx
0x1c003d8a6  mov     qword ptr [rbp+1D0h+var_200], rax
0x1c003d8aa  mov     rax, [r14+10h]
0x1c003d8ae  xorps   xmm1, xmm1
0x1c003d8b1  cmova   ecx, edx
0x1c003d8b4  mov     word ptr [rbp+1D0h+var_200+8], cx
0x1c003d8b8  movaps  xmm0, [rbp+1D0h+var_200]
0x1c003d8bc  movdqa  [rbp+1D0h+var_190], xmm0
0x1c003d8c1  movzx   ecx, word ptr [rax]; af
0x1c003d8c4  movups  [rbp+1D0h+var_1F0], xmm1
0x1c003d8c8  mov     qword ptr [rbp+1D0h+var_1F0], rax
0x1c003d8cc  call    SOCKADDR_SIZE
0x1c003d8d1  movzx   edx, al
0x1c003d8d4  xorps   xmm1, xmm1
0x1c003d8d7  mov     rax, [r14+8]
0x1c003d8db  movups  [rbp+1D0h+var_1E0], xmm1
0x1c003d8df  mov     word ptr [rbp+1D0h+var_1F0+8], dx
0x1c003d8e3  movaps  xmm0, [rbp+1D0h+var_1F0]
0x1c003d8e7  movdqa  [rbp+1D0h+var_180], xmm0
0x1c003d8ec  movzx   ecx, word ptr [rax]; af
0x1c003d8ef  mov     qword ptr [rbp+1D0h+var_1E0], rax
0x1c003d8f3  call    SOCKADDR_SIZE
0x1c003d8f8  mov     r9, [rbp+1D0h+var_110]
0x1c003d8ff  mov     r8, rbx
0x1c003d902  movzx   edx, al
0x1c003d905  lea     rax, [rbp+1D0h+var_190]
0x1c003d909  mov     dword ptr [rsp+2D0h+var_290], edi
0x1c003d90d  mov     dword ptr [rsp+2D0h+var_298], r12d
0x1c003d912  mov     [rsp+2D0h+var_2A0], rax
0x1c003d917  lea     rax, [rbp+1D0h+var_180]
0x1c003d91b  mov     [rsp+2D0h+var_2A8], rax
0x1c003d920  lea     rax, [rbp+1D0h+var_170]
0x1c003d924  mov     word ptr [rbp+1D0h+var_1E0+8], dx
0x1c003d928  movaps  xmm0, [rbp+1D0h+var_1E0]
0x1c003d92c  mov     [rsp+2D0h+BugCheckParameter4], rax
0x1c003d931  movdqa  [rbp+1D0h+var_170], xmm0
0x1c003d936  call    WPP_SF_qi_SOCKADDR__SOCKADDR__HEX_Ld
0x1c003d93b  mov     eax, edi
0x1c003d93d  mov     rcx, [rbp+1D0h+var_50]
0x1c003d944  xor     rcx, rsp; StackCookie
0x1c003d947  call    __security_check_cookie
0x1c003d94c  add     rsp, 298h
0x1c003d953  pop     r15
0x1c003d955  pop     r14
0x1c003d957  pop     r13
0x1c003d959  pop     r12
0x1c003d95b  pop     rdi
0x1c003d95c  pop     rsi
0x1c003d95d  pop     rbx
0x1c003d95e  pop     rbp
0x1c003d95f  retn
0x1c003d961  mov     r13, [rbp+1D0h+var_248]
0x1c003d965  mov     rax, [r14+8]
0x1c003d969  lea     r9, [rbx+20h]
0x1c003d96d  movups  xmm0, xmmword ptr [rax]
0x1c003d970  movups  xmmword ptr [rbx+30h], xmm0
0x1c003d974  movsd   xmm1, qword ptr [rax+10h]
0x1c003d979  movsd   qword ptr [rbx+40h], xmm1
0x1c003d97e  mov     eax, [rax+18h]
0x1c003d981  mov     [rbx+48h], eax
0x1c003d984  mov     rax, [r14+10h]
0x1c003d988  movups  xmm0, xmmword ptr [rax]
0x1c003d98b  movups  xmmword ptr [rbx+4Ch], xmm0
0x1c003d98f  movsd   xmm1, qword ptr [rax+10h]
0x1c003d994  movsd   qword ptr [rbx+5Ch], xmm1
0x1c003d999  mov     eax, [rax+18h]
0x1c003d99c  mov     [rbx+64h], eax
0x1c003d99f  movzx   r8d, word ptr [r14+1Ch]
0x1c003d9a4  mov     rdx, [r14+30h]
0x1c003d9a8  mov     rcx, [r15+0C8h]
0x1c003d9af  call    UxSslValidateSni
0x1c003d9b4  xor     edx, edx
0x1c003d9b6  mov     edi, eax
0x1c003d9b8  test    eax, eax
0x1c003d9ba  js      loc_1C003D7A2
0x1c003d9c0  mov     rax, [rbx+560h]
0x1c003d9c7  cmp     [rax+620h], dl
0x1c003d9cd  jz      short loc_1C003DA2B
0x1c003d9cf  movzx   ecx, word ptr [r14+1Ch]
0x1c003d9d4  lea     r8, [rbp+1D0h+var_160]
0x1c003d9d8  mov     [rbp+1D0h+var_150], rax
0x1c003d9df  mov     r9, rbx
0x1c003d9e2  lea     rax, [rbx+440h]
0x1c003d9e9  mov     [rbp+1D0h+var_147], edx
0x1c003d9ef  mov     [rbp+1D0h+var_160], rax
0x1c003d9f3  mov     rax, [rbx+28h]
  ... truncated ...
```
