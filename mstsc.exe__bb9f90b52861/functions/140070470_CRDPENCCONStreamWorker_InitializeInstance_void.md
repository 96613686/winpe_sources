# CRDPENCCONStreamWorker::InitializeInstance(void)

- ea: `0x140070470`
- end: `0x140070991`
- name: `?InitializeInstance@CRDPENCCONStreamWorker@@UEAAJXZ`
- size: `1313`
- prototype: `__int64 __fastcall(CRDPENCCONStreamWorker *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14005bc3c`
- `0x140070470`
- `0x1401075c8`
- `0x140114010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x140070514`
- `KERNEL32!CreateEventW` at `0x140070598`
- `KERNEL32!CreateEventW` at `0x140070514`
- `KERNEL32!CreateEventW` at `0x140070598`
- `KERNEL32!GetLastError` at `0x140070523`
- `KERNEL32!GetLastError` at `0x1400705aa`
- `KERNEL32!GetLastError` at `0x140070523`
- `KERNEL32!GetLastError` at `0x1400705aa`

## string_xrefs

- `0x140070631`: `Failed to create the stream core events`
- `0x140070693`: `Failed to create the event source`
- `0x140070702`: `Failed to create the worker thread`
- `0x140070949`: `Failed to start the network thread`
- `0x14007072a`: `fUseAPIThread`
- `0x14007083c`: `Failed to create the notification thread`
- `0x140070900`: `Failed to start the notification thread`

## pseudocode

```c
__int64 __fastcall CRDPENCCONStreamWorker::InitializeInstance(CRDPENCCONStreamWorker *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int LastError; // ebx
  HANDLE EventW; // rax
  unsigned int v5; // eax
  __int64 v6; // rdx
  HANDLE v7; // rax
  _QWORD *v8; // rsi
  unsigned int v9; // eax
  int v10; // edx
  const char *v11; // rcx
  __int64 v12; // rcx
  BOOL v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  _QWORD *v16; // r14
  __int64 v18; // [rsp+28h] [rbp-70h]
  __int128 v19; // [rsp+40h] [rbp-58h] BYREF
  __int64 v20; // [rsp+50h] [rbp-48h]

  v20 = 0;
  *((_QWORD *)this + 69) = (char *)this + 544;
  v19 = 0;
  *((_QWORD *)this + 68) = (char *)this + 544;
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRDPENCCONStreamWorker *)((char *)this + 624)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024882);
    }
    LastError = -2147024882;
    goto LABEL_66;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 3) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 15;
LABEL_12:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids, v5, LastError);
LABEL_13:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_66;
  }
  v7 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 73) = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 16;
    goto LABEL_12;
  }
  v8 = (_QWORD *)((char *)this + 696);
  LastError = TSCreateCoreEvents(*((struct ITSPlatform **)this + 81));
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 17;
    v11 = "Failed to create the stream core events";
    goto LABEL_65;
  }
  LastError = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v8 + 56LL))(*v8, 32, (char *)this + 704);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 18;
    v11 = "Failed to create the event source";
    goto LABEL_65;
  }
  LastError = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(void *), char *, char *))(**((_QWORD **)this + 81)
                                                                                             + 56LL))(
                *((_QWORD *)this + 81),
                CRDPENCCONStreamWorker::STATIC_WorkerThreadProc,
                (char *)this - 48,
                (char *)this + 656);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 19;
    v11 = "Failed to create the worker thread";
    goto LABEL_65;
  }
  v12 = *((_QWORD *)this + 80);
  WORD4(v19) = 0;
  LOWORD(v19) = 11;
  (*(void (__fastcall **)(__int64, const wchar_t *, __int128 *))(*(_QWORD *)v12 + 24LL))(v12, L"fUseAPIThread", &v19);
  v13 = WORD4(v19) != 0;
  *((_DWORD *)this + 9) = v13;
  if ( v13 )
  {
    v14 = *v8;
    *((_DWORD *)this + 145) = 0;
    LastError = (*(__int64 (__fastcall **)(__int64, __int64, char *, __int64, _QWORD, char *))(*(_QWORD *)v14 + 80LL))(
                  v14,
                  32,
                  (char *)this + 16,
                  1,
                  0,
                  (char *)this + 688);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_66;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 20;
      goto LABEL_44;
    }
  }
  else
  {
    v15 = *((_QWORD *)this + 81);
    v16 = (_QWORD *)((char *)this + 664);
    *((_DWORD *)this + 145) = 1;
    LastError = (*(__int64 (__fastcall **)(__int64, void (__fastcall *)(void *), char *, char *))(*(_QWORD *)v15 + 56LL))(
                  v15,
                  CRDPENCCONStreamWorker::STATIC_NotificationThreadProc,
                  (char *)this - 48,
                  (char *)this + 664);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_66;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 21;
      v11 = "Failed to create the notification thread";
      goto LABEL_65;
    }
    LastError = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, __int64, _QWORD, char *))(*(_QWORD *)*v8 + 80LL))(
                  *v8,
                  32,
                  (char *)this + 16,
                  3,
                  *v16,
                  (char *)this + 688);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_66;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 22;
LABEL_44:
      v11 = "Failed to bind the network decoupler sink";
LABEL_65:
      LODWORD(v18) = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids,
        v9,
        (__int64)v11,
        v18);
      goto LABEL_66;
    }
    LastError = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v16 + 32LL))(*v16, 0);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_66;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 23;
      v11 = "Failed to start the notification thread";
      goto LABEL_65;
    }
  }
  LastError = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 82) + 32LL))(*((_QWORD *)this + 82), 0);
  if ( LastError >= 0 )
  {
    *((_DWORD *)this - 5) |= 2u;
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 24;
    v11 = "Failed to start the network thread";
    goto LABEL_65;
  }
LABEL_66:
  *((_DWORD *)this - 5) |= 4u;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140070470  push    rbx
0x140070472  push    rbp
0x140070473  push    rsi
0x140070474  push    rdi
0x140070475  push    r12
0x140070477  push    r14
0x140070479  push    r15
0x14007047b  sub     rsp, 60h
0x14007047f  xor     eax, eax
0x140070481  mov     rdi, rcx
0x140070484  mov     [rsp+98h+var_48], rax
0x140070489  xorps   xmm0, xmm0
0x14007048c  lea     rax, [rcx+220h]
0x140070493  mov     [rcx+228h], rax
0x14007049a  add     rcx, 270h; this
0x1400704a1  movups  [rsp+98h+var_58], xmm0
0x1400704a6  mov     [rax], rax
0x1400704a9  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1400704ae  xor     r12d, r12d
0x1400704b1  test    eax, eax
0x1400704b3  jnz     short loc_14007050A
0x1400704b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400704bc  lea     rax, WPP_GLOBAL_Control
0x1400704c3  cmp     rcx, rax
0x1400704c6  jz      short loc_140070500
0x1400704c8  test    byte ptr [rcx+1Ch], 8
0x1400704cc  jz      short loc_140070500
0x1400704ce  cmp     byte ptr [rcx+19h], 2
0x1400704d2  jb      short loc_140070500
0x1400704d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400704d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400704e0  lea     edx, [r12+0Eh]
0x1400704e5  mov     r9d, eax
0x1400704e8  mov     dword ptr [rsp+98h+var_78], 8007000Eh
0x1400704f0  lea     r8, WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids
0x1400704f7  mov     rcx, [rcx+10h]
0x1400704fb  call    WPP_SF_Dd
0x140070500  mov     ebx, 8007000Eh
0x140070505  jmp     loc_140070973
0x14007050a  xor     r9d, r9d; lpName
0x14007050d  xor     r8d, r8d; bInitialState
0x140070510  xor     edx, edx; bManualReset
0x140070512  xor     ecx, ecx; lpEventAttributes
0x140070514  call    cs:__imp_CreateEventW
0x14007051a  mov     [rdi+18h], rax
0x14007051e  test    rax, rax
0x140070521  jnz     short loc_14007058E
0x140070523  call    cs:__imp_GetLastError
0x140070529  mov     ebx, eax
0x14007052b  mov     rcx, cs:WPP_GLOBAL_Control
0x140070532  lea     rax, WPP_GLOBAL_Control
0x140070539  cmp     rcx, rax
0x14007053c  jz      short loc_140070572
0x14007053e  test    byte ptr [rcx+1Ch], 8
0x140070542  jz      short loc_140070572
0x140070544  cmp     byte ptr [rcx+19h], 2
0x140070548  jb      short loc_140070572
0x14007054a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007054f  mov     edx, 0Fh
0x140070554  mov     rcx, cs:WPP_GLOBAL_Control
0x14007055b  lea     r8, WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids
0x140070562  mov     r9d, eax
0x140070565  mov     dword ptr [rsp+98h+var_78], ebx
0x140070569  mov     rcx, [rcx+10h]
0x14007056d  call    WPP_SF_Dd
0x140070572  test    ebx, ebx
0x140070574  jle     short loc_14007057F
0x140070576  movzx   ebx, bx
0x140070579  or      ebx, 80070000h
0x14007057f  test    ebx, ebx
0x140070581  mov     eax, 80004005h
0x140070586  cmovns  ebx, eax
0x140070589  jmp     loc_140070973
0x14007058e  xor     r9d, r9d; lpName
0x140070591  xor     r8d, r8d; bInitialState
0x140070594  xor     edx, edx; bManualReset
0x140070596  xor     ecx, ecx; lpEventAttributes
0x140070598  call    cs:__imp_CreateEventW
0x14007059e  mov     [rdi+248h], rax
0x1400705a5  test    rax, rax
0x1400705a8  jnz     short loc_1400705E0
0x1400705aa  call    cs:__imp_GetLastError
0x1400705b0  mov     ebx, eax
0x1400705b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400705b9  lea     rax, WPP_GLOBAL_Control
0x1400705c0  cmp     rcx, rax
0x1400705c3  jz      short loc_140070572
0x1400705c5  test    byte ptr [rcx+1Ch], 8
0x1400705c9  jz      short loc_140070572
0x1400705cb  cmp     byte ptr [rcx+19h], 2
0x1400705cf  jb      short loc_140070572
0x1400705d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400705d6  mov     edx, 10h
0x1400705db  jmp     loc_140070554
0x1400705e0  mov     rcx, [rdi+288h]; struct ITSPlatform *
0x1400705e7  lea     rsi, [rdi+2B8h]
0x1400705ee  mov     rdx, rsi
0x1400705f1  call    TSCreateCoreEvents
0x1400705f6  mov     ebx, eax
0x1400705f8  test    eax, eax
0x1400705fa  jns     short loc_14007063D
0x1400705fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140070603  lea     rax, WPP_GLOBAL_Control
0x14007060a  cmp     rcx, rax
0x14007060d  jz      loc_140070973
0x140070613  test    byte ptr [rcx+1Ch], 8
0x140070617  jz      loc_140070973
0x14007061d  cmp     byte ptr [rcx+19h], 2
0x140070621  jb      loc_140070973
0x140070627  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007062c  mov     edx, 11h
0x140070631  lea     rcx, aFailedToCreate_28; "Failed to create the stream core events"
0x140070638  jmp     loc_140070950
0x14007063d  mov     rcx, [rsi]
0x140070640  lea     r8, [rdi+2C0h]
0x140070647  mov     edx, 20h ; ' '
0x14007064c  mov     rax, [rcx]
0x14007064f  mov     rax, [rax+38h]
0x140070653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070658  mov     ebx, eax
0x14007065a  test    eax, eax
0x14007065c  jns     short loc_14007069F
0x14007065e  mov     rcx, cs:WPP_GLOBAL_Control
0x140070665  lea     rax, WPP_GLOBAL_Control
0x14007066c  cmp     rcx, rax
0x14007066f  jz      loc_140070973
0x140070675  test    byte ptr [rcx+1Ch], 8
0x140070679  jz      loc_140070973
0x14007067f  cmp     byte ptr [rcx+19h], 2
0x140070683  jb      loc_140070973
0x140070689  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007068e  mov     edx, 12h
0x140070693  lea     rcx, aFailedToCreate_46; "Failed to create the event source"
0x14007069a  jmp     loc_140070950
0x14007069f  mov     rcx, [rdi+288h]
0x1400706a6  lea     r15, [rdi+290h]
0x1400706ad  mov     r9, r15
0x1400706b0  lea     r8, [rdi-30h]
0x1400706b4  lea     rdx, ?STATIC_WorkerThreadProc@CRDPENCCONStreamWorker@@KAXPEAX@Z; CRDPENCCONStreamWorker::STATIC_WorkerThreadProc(void *)
0x1400706bb  mov     rax, [rcx]
0x1400706be  mov     rax, [rax+38h]
0x1400706c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400706c7  mov     ebx, eax
0x1400706c9  test    eax, eax
0x1400706cb  jns     short loc_14007070E
0x1400706cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400706d4  lea     rax, WPP_GLOBAL_Control
0x1400706db  cmp     rcx, rax
0x1400706de  jz      loc_140070973
0x1400706e4  test    byte ptr [rcx+1Ch], 8
0x1400706e8  jz      loc_140070973
0x1400706ee  cmp     byte ptr [rcx+19h], 2
0x1400706f2  jb      loc_140070973
0x1400706f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400706fd  mov     edx, 13h
0x140070702  lea     rcx, aFailedToCreate_5; "Failed to create the worker thread"
0x140070709  jmp     loc_140070950
0x14007070e  mov     rcx, [rdi+280h]
0x140070715  lea     r8, [rsp+98h+var_58]
0x14007071a  mov     eax, 0Bh
0x14007071f  mov     word ptr [rsp+98h+var_58+8], r12w
0x140070725  mov     word ptr [rsp+98h+var_58], ax
0x14007072a  lea     rdx, aFuseapithread; "fUseAPIThread"
0x140070731  mov     rax, [rcx]
0x140070734  mov     rax, [rax+18h]
0x140070738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007073d  cmp     word ptr [rsp+98h+var_58+8], r12w
0x140070743  mov     eax, r12d
0x140070746  setnz   al
0x140070749  mov     [rdi+24h], eax
0x14007074c  test    eax, eax
0x14007074e  jz      short loc_1400707CF
0x140070750  mov     rcx, [rsi]
0x140070753  lea     r9, [rdi+2B0h]
0x14007075a  mov     [rsp+98h+var_70], r9
0x14007075f  lea     r8, [rdi+10h]
0x140070763  mov     [rdi+244h], r12d
0x14007076a  mov     edx, 20h ; ' '
0x14007076f  mov     [rsp+98h+var_78], r12
0x140070774  mov     rax, [rcx]
0x140070777  lea     r9d, [rdx-1Fh]
0x14007077b  mov     rax, [rax+50h]
0x14007077f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070784  mov     ebx, eax
0x140070786  test    eax, eax
0x140070788  jns     loc_140070909
0x14007078e  mov     rcx, cs:WPP_GLOBAL_Control
0x140070795  lea     rax, WPP_GLOBAL_Control
0x14007079c  cmp     rcx, rax
0x14007079f  jz      loc_140070973
0x1400707a5  test    byte ptr [rcx+1Ch], 8
0x1400707a9  jz      loc_140070973
0x1400707af  cmp     byte ptr [rcx+19h], 2
0x1400707b3  jb      loc_140070973
0x1400707b9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400707be  mov     edx, 14h
0x1400707c3  lea     rcx, aFailedToBindTh; "Failed to bind the network decoupler si"...
0x1400707ca  jmp     loc_140070950
0x1400707cf  mov     rcx, [rdi+288h]
0x1400707d6  lea     r14, [rdi+298h]
0x1400707dd  mov     dword ptr [rdi+244h], 1
0x1400707e7  lea     r8, [rdi-30h]
0x1400707eb  mov     r9, r14
0x1400707ee  lea     rdx, ?STATIC_NotificationThreadProc@CRDPENCCONStreamWorker@@KAXPEAX@Z; CRDPENCCONStreamWorker::STATIC_NotificationThreadProc(void *)
0x1400707f5  mov     rax, [rcx]
0x1400707f8  mov     rax, [rax+38h]
0x1400707fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070801  mov     ebx, eax
0x140070803  test    eax, eax
0x140070805  jns     short loc_140070848
0x140070807  mov     rcx, cs:WPP_GLOBAL_Control
0x14007080e  lea     rax, WPP_GLOBAL_Control
0x140070815  cmp     rcx, rax
0x140070818  jz      loc_140070973
0x14007081e  test    byte ptr [rcx+1Ch], 8
0x140070822  jz      loc_140070973
0x140070828  cmp     byte ptr [rcx+19h], 2
0x14007082c  jb      loc_140070973
0x140070832  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140070837  mov     edx, 15h
0x14007083c  lea     rcx, aFailedToCreate_32; "Failed to create the notification threa"...
0x140070843  jmp     loc_140070950
0x140070848  mov     rcx, [rsi]
0x14007084b  lea     rdx, [rdi+2B0h]
0x140070852  mov     [rsp+98h+var_70], rdx
0x140070857  lea     r8, [rdi+10h]
0x14007085b  mov     rdx, [r14]
0x14007085e  mov     [rsp+98h+var_78], rdx
0x140070863  mov     edx, 20h ; ' '
0x140070868  mov     rax, [rcx]
0x14007086b  lea     r9d, [rdx-1Dh]
0x14007086f  mov     rax, [rax+50h]
0x140070873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070878  mov     ebx, eax
0x14007087a  test    eax, eax
0x14007087c  jns     short loc_1400708B8
0x14007087e  mov     rcx, cs:WPP_GLOBAL_Control
0x140070885  lea     rax, WPP_GLOBAL_Control
0x14007088c  cmp     rcx, rax
0x14007088f  jz      loc_140070973
0x140070895  test    byte ptr [rcx+1Ch], 8
0x140070899  jz      loc_140070973
0x14007089f  cmp     byte ptr [rcx+19h], 2
0x1400708a3  jb      loc_140070973
0x1400708a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400708ae  mov     edx, 16h
0x1400708b3  jmp     loc_1400707C3
0x1400708b8  mov     rcx, [r14]
0x1400708bb  xor     edx, edx
0x1400708bd  mov     rax, [rcx]
0x1400708c0  mov     rax, [rax+20h]
0x1400708c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400708c9  mov     ebx, eax
0x1400708cb  test    eax, eax
0x1400708cd  jns     short loc_140070909
0x1400708cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400708d6  lea     rax, WPP_GLOBAL_Control
0x1400708dd  cmp     rcx, rax
0x1400708e0  jz      loc_140070973
0x1400708e6  test    byte ptr [rcx+1Ch], 8
0x1400708ea  jz      loc_140070973
0x1400708f0  cmp     byte ptr [rcx+19h], 2
0x1400708f4  jb      short loc_140070973
0x1400708f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400708fb  mov     edx, 17h
0x140070900  lea     rcx, aFailedToStartT_4; "Failed to start the notification thread"
0x140070907  jmp     short loc_140070950
0x140070909  mov     rcx, [r15]
0x14007090c  xor     edx, edx
0x14007090e  mov     rax, [rcx]
0x140070911  mov     rax, [rax+20h]
0x140070915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007091a  mov     ebx, eax
0x14007091c  test    eax, eax
0x14007091e  jns     short loc_140070979
0x140070920  mov     rcx, cs:WPP_GLOBAL_Control
0x140070927  lea     rax, WPP_GLOBAL_Control
0x14007092e  cmp     rcx, rax
0x140070931  jz      short loc_140070973
0x140070933  test    byte ptr [rcx+1Ch], 8
0x140070937  jz      short loc_140070973
0x140070939  cmp     byte ptr [rcx+19h], 2
0x14007093d  jb      short loc_140070973
0x14007093f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140070944  mov     edx, 18h
0x140070949  lea     rcx, aFailedToStartT; "Failed to start the network thread"
0x140070950  mov     dword ptr [rsp+98h+var_70], ebx
0x140070954  lea     r8, WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids
0x14007095b  mov     [rsp+98h+var_78], rcx
0x140070960  mov     r9d, eax
0x140070963  mov     rcx, cs:WPP_GLOBAL_Control
0x14007096a  mov     rcx, [rcx+10h]
0x14007096e  call    WPP_SF_DsD
0x140070973  or      dword ptr [rdi-14h], 4
0x140070977  jmp     short loc_140070980
0x140070979  or      dword ptr [rdi-14h], 2
0x14007097d  mov     ebx, r12d
0x140070980  mov     eax, ebx
0x140070982  add     rsp, 60h
0x140070986  pop     r15
  ... truncated ...
```
