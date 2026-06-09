# CRDPENCCONStreamWorker::InitializeInstance(void)

- ea: `0x14006e300`
- end: `0x14006e821`
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
- `0x140059acc`
- `0x14006e300`
- `0x140105458`
- `0x140112010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14006e3a4`
- `KERNEL32!CreateEventW` at `0x14006e428`
- `KERNEL32!CreateEventW` at `0x14006e3a4`
- `KERNEL32!CreateEventW` at `0x14006e428`
- `KERNEL32!GetLastError` at `0x14006e3b3`
- `KERNEL32!GetLastError` at `0x14006e43a`
- `KERNEL32!GetLastError` at `0x14006e3b3`
- `KERNEL32!GetLastError` at `0x14006e43a`

## string_xrefs

- `0x14006e4c1`: `Failed to create the stream core events`
- `0x14006e523`: `Failed to create the event source`
- `0x14006e790`: `Failed to start the notification thread`
- `0x14006e7d9`: `Failed to start the network thread`
- `0x14006e592`: `Failed to create the worker thread`
- `0x14006e5ba`: `fUseAPIThread`
- `0x14006e6cc`: `Failed to create the notification thread`

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
  __int128 v18; // [rsp+40h] [rbp-58h] BYREF
  __int64 v19; // [rsp+50h] [rbp-48h]

  v19 = 0;
  *((_QWORD *)this + 69) = (char *)this + 544;
  v18 = 0;
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
  WORD4(v18) = 0;
  LOWORD(v18) = 11;
  (*(void (__fastcall **)(__int64, const wchar_t *, __int128 *))(*(_QWORD *)v12 + 24LL))(v12, L"fUseAPIThread", &v18);
  v13 = WORD4(v18) != 0;
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
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids,
        v9,
        (__int64)v11,
        LastError);
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
0x14006e300  push    rbx
0x14006e302  push    rbp
0x14006e303  push    rsi
0x14006e304  push    rdi
0x14006e305  push    r12
0x14006e307  push    r14
0x14006e309  push    r15
0x14006e30b  sub     rsp, 60h
0x14006e30f  xor     eax, eax
0x14006e311  mov     rdi, rcx
0x14006e314  mov     [rsp+98h+var_48], rax
0x14006e319  xorps   xmm0, xmm0
0x14006e31c  lea     rax, [rcx+220h]
0x14006e323  mov     [rcx+228h], rax
0x14006e32a  add     rcx, 270h; this
0x14006e331  movups  [rsp+98h+var_58], xmm0
0x14006e336  mov     [rax], rax
0x14006e339  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x14006e33e  xor     r12d, r12d
0x14006e341  test    eax, eax
0x14006e343  jnz     short loc_14006E39A
0x14006e345  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e34c  lea     rax, WPP_GLOBAL_Control
0x14006e353  cmp     rcx, rax
0x14006e356  jz      short loc_14006E390
0x14006e358  test    byte ptr [rcx+1Ch], 8
0x14006e35c  jz      short loc_14006E390
0x14006e35e  cmp     byte ptr [rcx+19h], 2
0x14006e362  jb      short loc_14006E390
0x14006e364  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e369  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e370  lea     edx, [r12+0Eh]
0x14006e375  mov     r9d, eax
0x14006e378  mov     dword ptr [rsp+98h+var_78], 8007000Eh
0x14006e380  lea     r8, WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids
0x14006e387  mov     rcx, [rcx+10h]
0x14006e38b  call    WPP_SF_Dd
0x14006e390  mov     ebx, 8007000Eh
0x14006e395  jmp     loc_14006E803
0x14006e39a  xor     r9d, r9d; lpName
0x14006e39d  xor     r8d, r8d; bInitialState
0x14006e3a0  xor     edx, edx; bManualReset
0x14006e3a2  xor     ecx, ecx; lpEventAttributes
0x14006e3a4  call    cs:__imp_CreateEventW
0x14006e3aa  mov     [rdi+18h], rax
0x14006e3ae  test    rax, rax
0x14006e3b1  jnz     short loc_14006E41E
0x14006e3b3  call    cs:__imp_GetLastError
0x14006e3b9  mov     ebx, eax
0x14006e3bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e3c2  lea     rax, WPP_GLOBAL_Control
0x14006e3c9  cmp     rcx, rax
0x14006e3cc  jz      short loc_14006E402
0x14006e3ce  test    byte ptr [rcx+1Ch], 8
0x14006e3d2  jz      short loc_14006E402
0x14006e3d4  cmp     byte ptr [rcx+19h], 2
0x14006e3d8  jb      short loc_14006E402
0x14006e3da  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e3df  mov     edx, 0Fh
0x14006e3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e3eb  lea     r8, WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids
0x14006e3f2  mov     r9d, eax
0x14006e3f5  mov     dword ptr [rsp+98h+var_78], ebx
0x14006e3f9  mov     rcx, [rcx+10h]
0x14006e3fd  call    WPP_SF_Dd
0x14006e402  test    ebx, ebx
0x14006e404  jle     short loc_14006E40F
0x14006e406  movzx   ebx, bx
0x14006e409  or      ebx, 80070000h
0x14006e40f  test    ebx, ebx
0x14006e411  mov     eax, 80004005h
0x14006e416  cmovns  ebx, eax
0x14006e419  jmp     loc_14006E803
0x14006e41e  xor     r9d, r9d; lpName
0x14006e421  xor     r8d, r8d; bInitialState
0x14006e424  xor     edx, edx; bManualReset
0x14006e426  xor     ecx, ecx; lpEventAttributes
0x14006e428  call    cs:__imp_CreateEventW
0x14006e42e  mov     [rdi+248h], rax
0x14006e435  test    rax, rax
0x14006e438  jnz     short loc_14006E470
0x14006e43a  call    cs:__imp_GetLastError
0x14006e440  mov     ebx, eax
0x14006e442  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e449  lea     rax, WPP_GLOBAL_Control
0x14006e450  cmp     rcx, rax
0x14006e453  jz      short loc_14006E402
0x14006e455  test    byte ptr [rcx+1Ch], 8
0x14006e459  jz      short loc_14006E402
0x14006e45b  cmp     byte ptr [rcx+19h], 2
0x14006e45f  jb      short loc_14006E402
0x14006e461  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e466  mov     edx, 10h
0x14006e46b  jmp     loc_14006E3E4
0x14006e470  mov     rcx, [rdi+288h]; struct ITSPlatform *
0x14006e477  lea     rsi, [rdi+2B8h]
0x14006e47e  mov     rdx, rsi
0x14006e481  call    TSCreateCoreEvents
0x14006e486  mov     ebx, eax
0x14006e488  test    eax, eax
0x14006e48a  jns     short loc_14006E4CD
0x14006e48c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e493  lea     rax, WPP_GLOBAL_Control
0x14006e49a  cmp     rcx, rax
0x14006e49d  jz      loc_14006E803
0x14006e4a3  test    byte ptr [rcx+1Ch], 8
0x14006e4a7  jz      loc_14006E803
0x14006e4ad  cmp     byte ptr [rcx+19h], 2
0x14006e4b1  jb      loc_14006E803
0x14006e4b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e4bc  mov     edx, 11h
0x14006e4c1  lea     rcx, aFailedToCreate_28; "Failed to create the stream core events"
0x14006e4c8  jmp     loc_14006E7E0
0x14006e4cd  mov     rcx, [rsi]
0x14006e4d0  lea     r8, [rdi+2C0h]
0x14006e4d7  mov     edx, 20h ; ' '
0x14006e4dc  mov     rax, [rcx]
0x14006e4df  mov     rax, [rax+38h]
0x14006e4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e4e8  mov     ebx, eax
0x14006e4ea  test    eax, eax
0x14006e4ec  jns     short loc_14006E52F
0x14006e4ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e4f5  lea     rax, WPP_GLOBAL_Control
0x14006e4fc  cmp     rcx, rax
0x14006e4ff  jz      loc_14006E803
0x14006e505  test    byte ptr [rcx+1Ch], 8
0x14006e509  jz      loc_14006E803
0x14006e50f  cmp     byte ptr [rcx+19h], 2
0x14006e513  jb      loc_14006E803
0x14006e519  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e51e  mov     edx, 12h
0x14006e523  lea     rcx, aFailedToCreate_46; "Failed to create the event source"
0x14006e52a  jmp     loc_14006E7E0
0x14006e52f  mov     rcx, [rdi+288h]
0x14006e536  lea     r15, [rdi+290h]
0x14006e53d  mov     r9, r15
0x14006e540  lea     r8, [rdi-30h]
0x14006e544  lea     rdx, ?STATIC_WorkerThreadProc@CRDPENCCONStreamWorker@@KAXPEAX@Z; CRDPENCCONStreamWorker::STATIC_WorkerThreadProc(void *)
0x14006e54b  mov     rax, [rcx]
0x14006e54e  mov     rax, [rax+38h]
0x14006e552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e557  mov     ebx, eax
0x14006e559  test    eax, eax
0x14006e55b  jns     short loc_14006E59E
0x14006e55d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e564  lea     rax, WPP_GLOBAL_Control
0x14006e56b  cmp     rcx, rax
0x14006e56e  jz      loc_14006E803
0x14006e574  test    byte ptr [rcx+1Ch], 8
0x14006e578  jz      loc_14006E803
0x14006e57e  cmp     byte ptr [rcx+19h], 2
0x14006e582  jb      loc_14006E803
0x14006e588  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e58d  mov     edx, 13h
0x14006e592  lea     rcx, aFailedToCreate_5; "Failed to create the worker thread"
0x14006e599  jmp     loc_14006E7E0
0x14006e59e  mov     rcx, [rdi+280h]
0x14006e5a5  lea     r8, [rsp+98h+var_58]
0x14006e5aa  mov     eax, 0Bh
0x14006e5af  mov     word ptr [rsp+98h+var_58+8], r12w
0x14006e5b5  mov     word ptr [rsp+98h+var_58], ax
0x14006e5ba  lea     rdx, aFuseapithread; "fUseAPIThread"
0x14006e5c1  mov     rax, [rcx]
0x14006e5c4  mov     rax, [rax+18h]
0x14006e5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e5cd  cmp     word ptr [rsp+98h+var_58+8], r12w
0x14006e5d3  mov     eax, r12d
0x14006e5d6  setnz   al
0x14006e5d9  mov     [rdi+24h], eax
0x14006e5dc  test    eax, eax
0x14006e5de  jz      short loc_14006E65F
0x14006e5e0  mov     rcx, [rsi]
0x14006e5e3  lea     r9, [rdi+2B0h]
0x14006e5ea  mov     [rsp+98h+var_70], r9
0x14006e5ef  lea     r8, [rdi+10h]
0x14006e5f3  mov     [rdi+244h], r12d
0x14006e5fa  mov     edx, 20h ; ' '
0x14006e5ff  mov     [rsp+98h+var_78], r12
0x14006e604  mov     rax, [rcx]
0x14006e607  lea     r9d, [rdx-1Fh]
0x14006e60b  mov     rax, [rax+50h]
0x14006e60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e614  mov     ebx, eax
0x14006e616  test    eax, eax
0x14006e618  jns     loc_14006E799
0x14006e61e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e625  lea     rax, WPP_GLOBAL_Control
0x14006e62c  cmp     rcx, rax
0x14006e62f  jz      loc_14006E803
0x14006e635  test    byte ptr [rcx+1Ch], 8
0x14006e639  jz      loc_14006E803
0x14006e63f  cmp     byte ptr [rcx+19h], 2
0x14006e643  jb      loc_14006E803
0x14006e649  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e64e  mov     edx, 14h
0x14006e653  lea     rcx, aFailedToBindTh; "Failed to bind the network decoupler si"...
0x14006e65a  jmp     loc_14006E7E0
0x14006e65f  mov     rcx, [rdi+288h]
0x14006e666  lea     r14, [rdi+298h]
0x14006e66d  mov     dword ptr [rdi+244h], 1
0x14006e677  lea     r8, [rdi-30h]
0x14006e67b  mov     r9, r14
0x14006e67e  lea     rdx, ?STATIC_NotificationThreadProc@CRDPENCCONStreamWorker@@KAXPEAX@Z; CRDPENCCONStreamWorker::STATIC_NotificationThreadProc(void *)
0x14006e685  mov     rax, [rcx]
0x14006e688  mov     rax, [rax+38h]
0x14006e68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e691  mov     ebx, eax
0x14006e693  test    eax, eax
0x14006e695  jns     short loc_14006E6D8
0x14006e697  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e69e  lea     rax, WPP_GLOBAL_Control
0x14006e6a5  cmp     rcx, rax
0x14006e6a8  jz      loc_14006E803
0x14006e6ae  test    byte ptr [rcx+1Ch], 8
0x14006e6b2  jz      loc_14006E803
0x14006e6b8  cmp     byte ptr [rcx+19h], 2
0x14006e6bc  jb      loc_14006E803
0x14006e6c2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e6c7  mov     edx, 15h
0x14006e6cc  lea     rcx, aFailedToCreate_32; "Failed to create the notification threa"...
0x14006e6d3  jmp     loc_14006E7E0
0x14006e6d8  mov     rcx, [rsi]
0x14006e6db  lea     rdx, [rdi+2B0h]
0x14006e6e2  mov     [rsp+98h+var_70], rdx
0x14006e6e7  lea     r8, [rdi+10h]
0x14006e6eb  mov     rdx, [r14]
0x14006e6ee  mov     [rsp+98h+var_78], rdx
0x14006e6f3  mov     edx, 20h ; ' '
0x14006e6f8  mov     rax, [rcx]
0x14006e6fb  lea     r9d, [rdx-1Dh]
0x14006e6ff  mov     rax, [rax+50h]
0x14006e703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e708  mov     ebx, eax
0x14006e70a  test    eax, eax
0x14006e70c  jns     short loc_14006E748
0x14006e70e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e715  lea     rax, WPP_GLOBAL_Control
0x14006e71c  cmp     rcx, rax
0x14006e71f  jz      loc_14006E803
0x14006e725  test    byte ptr [rcx+1Ch], 8
0x14006e729  jz      loc_14006E803
0x14006e72f  cmp     byte ptr [rcx+19h], 2
0x14006e733  jb      loc_14006E803
0x14006e739  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e73e  mov     edx, 16h
0x14006e743  jmp     loc_14006E653
0x14006e748  mov     rcx, [r14]
0x14006e74b  xor     edx, edx
0x14006e74d  mov     rax, [rcx]
0x14006e750  mov     rax, [rax+20h]
0x14006e754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e759  mov     ebx, eax
0x14006e75b  test    eax, eax
0x14006e75d  jns     short loc_14006E799
0x14006e75f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e766  lea     rax, WPP_GLOBAL_Control
0x14006e76d  cmp     rcx, rax
0x14006e770  jz      loc_14006E803
0x14006e776  test    byte ptr [rcx+1Ch], 8
0x14006e77a  jz      loc_14006E803
0x14006e780  cmp     byte ptr [rcx+19h], 2
0x14006e784  jb      short loc_14006E803
0x14006e786  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e78b  mov     edx, 17h
0x14006e790  lea     rcx, aFailedToStartT_4; "Failed to start the notification thread"
0x14006e797  jmp     short loc_14006E7E0
0x14006e799  mov     rcx, [r15]
0x14006e79c  xor     edx, edx
0x14006e79e  mov     rax, [rcx]
0x14006e7a1  mov     rax, [rax+20h]
0x14006e7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e7aa  mov     ebx, eax
0x14006e7ac  test    eax, eax
0x14006e7ae  jns     short loc_14006E809
0x14006e7b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e7b7  lea     rax, WPP_GLOBAL_Control
0x14006e7be  cmp     rcx, rax
0x14006e7c1  jz      short loc_14006E803
0x14006e7c3  test    byte ptr [rcx+1Ch], 8
0x14006e7c7  jz      short loc_14006E803
0x14006e7c9  cmp     byte ptr [rcx+19h], 2
0x14006e7cd  jb      short loc_14006E803
0x14006e7cf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006e7d4  mov     edx, 18h
0x14006e7d9  lea     rcx, aFailedToStartT; "Failed to start the network thread"
0x14006e7e0  mov     dword ptr [rsp+98h+var_70], ebx
0x14006e7e4  lea     r8, WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids
0x14006e7eb  mov     [rsp+98h+var_78], rcx
0x14006e7f0  mov     r9d, eax
0x14006e7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e7fa  mov     rcx, [rcx+10h]
0x14006e7fe  call    WPP_SF_DsD
0x14006e803  or      dword ptr [rdi-14h], 4
0x14006e807  jmp     short loc_14006E810
0x14006e809  or      dword ptr [rdi-14h], 2
0x14006e80d  mov     ebx, r12d
0x14006e810  mov     eax, ebx
0x14006e812  add     rsp, 60h
0x14006e816  pop     r15
  ... truncated ...
```
