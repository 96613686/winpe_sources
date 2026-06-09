# CRDPENCCONStreamWorker::InitializeInstance(void)

- ea: `0x1800f75b0`
- end: `0x1800f7ad1`
- name: `?InitializeInstance@CRDPENCCONStreamWorker@@UEAAJXZ`
- size: `1313`
- prototype: `__int64 __fastcall(CRDPENCCONStreamWorker *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18001e164`
- `0x180046a84`
- `0x1800711c8`
- `0x1800721d4`
- `0x1800bcaa0`
- `0x1800f75b0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f76ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f76ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f7654`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f76d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f7654`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f76d8`

## string_xrefs

- `0x1800f77d3`: `Failed to create the event source`
- `0x1800f7771`: `Failed to create the stream core events`
- `0x1800f786a`: `fUseAPIThread`
- `0x1800f7842`: `Failed to create the worker thread`
- `0x1800f797c`: `Failed to create the notification thread`
- `0x1800f7a89`: `Failed to start the network thread`
- `0x1800f7a40`: `Failed to start the notification thread`

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
0x1800f75b0  push    rbx
0x1800f75b2  push    rbp
0x1800f75b3  push    rsi
0x1800f75b4  push    rdi
0x1800f75b5  push    r12
0x1800f75b7  push    r14
0x1800f75b9  push    r15
0x1800f75bb  sub     rsp, 60h
0x1800f75bf  xor     eax, eax
0x1800f75c1  mov     rdi, rcx
0x1800f75c4  mov     [rsp+98h+var_48], rax
0x1800f75c9  xorps   xmm0, xmm0
0x1800f75cc  lea     rax, [rcx+220h]
0x1800f75d3  mov     [rcx+228h], rax
0x1800f75da  add     rcx, 270h; this
0x1800f75e1  movups  [rsp+98h+var_58], xmm0
0x1800f75e6  mov     [rax], rax
0x1800f75e9  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800f75ee  xor     r12d, r12d
0x1800f75f1  test    eax, eax
0x1800f75f3  jnz     short loc_1800F764A
0x1800f75f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f75fc  lea     rax, WPP_GLOBAL_Control
0x1800f7603  cmp     rcx, rax
0x1800f7606  jz      short loc_1800F7640
0x1800f7608  test    byte ptr [rcx+1Ch], 8
0x1800f760c  jz      short loc_1800F7640
0x1800f760e  cmp     byte ptr [rcx+19h], 2
0x1800f7612  jb      short loc_1800F7640
0x1800f7614  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f7619  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f7620  lea     edx, [r12+0Eh]
0x1800f7625  mov     r9d, eax
0x1800f7628  mov     dword ptr [rsp+98h+var_78], 8007000Eh
0x1800f7630  lea     r8, WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids
0x1800f7637  mov     rcx, [rcx+10h]
0x1800f763b  call    WPP_SF_Dd
0x1800f7640  mov     ebx, 8007000Eh
0x1800f7645  jmp     loc_1800F7AB3
0x1800f764a  xor     r9d, r9d; lpName
0x1800f764d  xor     r8d, r8d; bInitialState
0x1800f7650  xor     edx, edx; bManualReset
0x1800f7652  xor     ecx, ecx; lpEventAttributes
0x1800f7654  call    cs:__imp_CreateEventW
0x1800f765a  mov     [rdi+18h], rax
0x1800f765e  test    rax, rax
0x1800f7661  jnz     short loc_1800F76CE
0x1800f7663  call    cs:__imp_GetLastError
0x1800f7669  mov     ebx, eax
0x1800f766b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f7672  lea     rax, WPP_GLOBAL_Control
0x1800f7679  cmp     rcx, rax
0x1800f767c  jz      short loc_1800F76B2
0x1800f767e  test    byte ptr [rcx+1Ch], 8
0x1800f7682  jz      short loc_1800F76B2
0x1800f7684  cmp     byte ptr [rcx+19h], 2
0x1800f7688  jb      short loc_1800F76B2
0x1800f768a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f768f  mov     edx, 0Fh
0x1800f7694  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f769b  lea     r8, WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids
0x1800f76a2  mov     r9d, eax
0x1800f76a5  mov     dword ptr [rsp+98h+var_78], ebx
0x1800f76a9  mov     rcx, [rcx+10h]
0x1800f76ad  call    WPP_SF_Dd
0x1800f76b2  test    ebx, ebx
0x1800f76b4  jle     short loc_1800F76BF
0x1800f76b6  movzx   ebx, bx
0x1800f76b9  or      ebx, 80070000h
0x1800f76bf  test    ebx, ebx
0x1800f76c1  mov     eax, 80004005h
0x1800f76c6  cmovns  ebx, eax
0x1800f76c9  jmp     loc_1800F7AB3
0x1800f76ce  xor     r9d, r9d; lpName
0x1800f76d1  xor     r8d, r8d; bInitialState
0x1800f76d4  xor     edx, edx; bManualReset
0x1800f76d6  xor     ecx, ecx; lpEventAttributes
0x1800f76d8  call    cs:__imp_CreateEventW
0x1800f76de  mov     [rdi+248h], rax
0x1800f76e5  test    rax, rax
0x1800f76e8  jnz     short loc_1800F7720
0x1800f76ea  call    cs:__imp_GetLastError
0x1800f76f0  mov     ebx, eax
0x1800f76f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f76f9  lea     rax, WPP_GLOBAL_Control
0x1800f7700  cmp     rcx, rax
0x1800f7703  jz      short loc_1800F76B2
0x1800f7705  test    byte ptr [rcx+1Ch], 8
0x1800f7709  jz      short loc_1800F76B2
0x1800f770b  cmp     byte ptr [rcx+19h], 2
0x1800f770f  jb      short loc_1800F76B2
0x1800f7711  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f7716  mov     edx, 10h
0x1800f771b  jmp     loc_1800F7694
0x1800f7720  mov     rcx, [rdi+288h]; struct ITSPlatform *
0x1800f7727  lea     rsi, [rdi+2B8h]
0x1800f772e  mov     rdx, rsi
0x1800f7731  call    TSCreateCoreEvents
0x1800f7736  mov     ebx, eax
0x1800f7738  test    eax, eax
0x1800f773a  jns     short loc_1800F777D
0x1800f773c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f7743  lea     rax, WPP_GLOBAL_Control
0x1800f774a  cmp     rcx, rax
0x1800f774d  jz      loc_1800F7AB3
0x1800f7753  test    byte ptr [rcx+1Ch], 8
0x1800f7757  jz      loc_1800F7AB3
0x1800f775d  cmp     byte ptr [rcx+19h], 2
0x1800f7761  jb      loc_1800F7AB3
0x1800f7767  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f776c  mov     edx, 11h
0x1800f7771  lea     rcx, aFailedToCreate_48; "Failed to create the stream core events"
0x1800f7778  jmp     loc_1800F7A90
0x1800f777d  mov     rcx, [rsi]
0x1800f7780  lea     r8, [rdi+2C0h]
0x1800f7787  mov     edx, 20h ; ' '
0x1800f778c  mov     rax, [rcx]
0x1800f778f  mov     rax, [rax+38h]
0x1800f7793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7798  mov     ebx, eax
0x1800f779a  test    eax, eax
0x1800f779c  jns     short loc_1800F77DF
0x1800f779e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f77a5  lea     rax, WPP_GLOBAL_Control
0x1800f77ac  cmp     rcx, rax
0x1800f77af  jz      loc_1800F7AB3
0x1800f77b5  test    byte ptr [rcx+1Ch], 8
0x1800f77b9  jz      loc_1800F7AB3
0x1800f77bf  cmp     byte ptr [rcx+19h], 2
0x1800f77c3  jb      loc_1800F7AB3
0x1800f77c9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f77ce  mov     edx, 12h
0x1800f77d3  lea     rcx, aFailedToCreate_79; "Failed to create the event source"
0x1800f77da  jmp     loc_1800F7A90
0x1800f77df  mov     rcx, [rdi+288h]
0x1800f77e6  lea     r15, [rdi+290h]
0x1800f77ed  mov     r9, r15
0x1800f77f0  lea     r8, [rdi-30h]
0x1800f77f4  lea     rdx, ?STATIC_WorkerThreadProc@CRDPENCCONStreamWorker@@KAXPEAX@Z; CRDPENCCONStreamWorker::STATIC_WorkerThreadProc(void *)
0x1800f77fb  mov     rax, [rcx]
0x1800f77fe  mov     rax, [rax+38h]
0x1800f7802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7807  mov     ebx, eax
0x1800f7809  test    eax, eax
0x1800f780b  jns     short loc_1800F784E
0x1800f780d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f7814  lea     rax, WPP_GLOBAL_Control
0x1800f781b  cmp     rcx, rax
0x1800f781e  jz      loc_1800F7AB3
0x1800f7824  test    byte ptr [rcx+1Ch], 8
0x1800f7828  jz      loc_1800F7AB3
0x1800f782e  cmp     byte ptr [rcx+19h], 2
0x1800f7832  jb      loc_1800F7AB3
0x1800f7838  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f783d  mov     edx, 13h
0x1800f7842  lea     rcx, aFailedToCreate_6; "Failed to create the worker thread"
0x1800f7849  jmp     loc_1800F7A90
0x1800f784e  mov     rcx, [rdi+280h]
0x1800f7855  lea     r8, [rsp+98h+var_58]
0x1800f785a  mov     eax, 0Bh
0x1800f785f  mov     word ptr [rsp+98h+var_58+8], r12w
0x1800f7865  mov     word ptr [rsp+98h+var_58], ax
0x1800f786a  lea     rdx, aFuseapithread; "fUseAPIThread"
0x1800f7871  mov     rax, [rcx]
0x1800f7874  mov     rax, [rax+18h]
0x1800f7878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f787d  cmp     word ptr [rsp+98h+var_58+8], r12w
0x1800f7883  mov     eax, r12d
0x1800f7886  setnz   al
0x1800f7889  mov     [rdi+24h], eax
0x1800f788c  test    eax, eax
0x1800f788e  jz      short loc_1800F790F
0x1800f7890  mov     rcx, [rsi]
0x1800f7893  lea     r9, [rdi+2B0h]
0x1800f789a  mov     [rsp+98h+var_70], r9
0x1800f789f  lea     r8, [rdi+10h]
0x1800f78a3  mov     [rdi+244h], r12d
0x1800f78aa  mov     edx, 20h ; ' '
0x1800f78af  mov     [rsp+98h+var_78], r12
0x1800f78b4  mov     rax, [rcx]
0x1800f78b7  lea     r9d, [rdx-1Fh]
0x1800f78bb  mov     rax, [rax+50h]
0x1800f78bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f78c4  mov     ebx, eax
0x1800f78c6  test    eax, eax
0x1800f78c8  jns     loc_1800F7A49
0x1800f78ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f78d5  lea     rax, WPP_GLOBAL_Control
0x1800f78dc  cmp     rcx, rax
0x1800f78df  jz      loc_1800F7AB3
0x1800f78e5  test    byte ptr [rcx+1Ch], 8
0x1800f78e9  jz      loc_1800F7AB3
0x1800f78ef  cmp     byte ptr [rcx+19h], 2
0x1800f78f3  jb      loc_1800F7AB3
0x1800f78f9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f78fe  mov     edx, 14h
0x1800f7903  lea     rcx, aFailedToBindTh; "Failed to bind the network decoupler si"...
0x1800f790a  jmp     loc_1800F7A90
0x1800f790f  mov     rcx, [rdi+288h]
0x1800f7916  lea     r14, [rdi+298h]
0x1800f791d  mov     dword ptr [rdi+244h], 1
0x1800f7927  lea     r8, [rdi-30h]
0x1800f792b  mov     r9, r14
0x1800f792e  lea     rdx, ?STATIC_NotificationThreadProc@CRDPENCCONStreamWorker@@KAXPEAX@Z; CRDPENCCONStreamWorker::STATIC_NotificationThreadProc(void *)
0x1800f7935  mov     rax, [rcx]
0x1800f7938  mov     rax, [rax+38h]
0x1800f793c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7941  mov     ebx, eax
0x1800f7943  test    eax, eax
0x1800f7945  jns     short loc_1800F7988
0x1800f7947  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f794e  lea     rax, WPP_GLOBAL_Control
0x1800f7955  cmp     rcx, rax
0x1800f7958  jz      loc_1800F7AB3
0x1800f795e  test    byte ptr [rcx+1Ch], 8
0x1800f7962  jz      loc_1800F7AB3
0x1800f7968  cmp     byte ptr [rcx+19h], 2
0x1800f796c  jb      loc_1800F7AB3
0x1800f7972  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f7977  mov     edx, 15h
0x1800f797c  lea     rcx, aFailedToCreate_56; "Failed to create the notification threa"...
0x1800f7983  jmp     loc_1800F7A90
0x1800f7988  mov     rcx, [rsi]
0x1800f798b  lea     rdx, [rdi+2B0h]
0x1800f7992  mov     [rsp+98h+var_70], rdx
0x1800f7997  lea     r8, [rdi+10h]
0x1800f799b  mov     rdx, [r14]
0x1800f799e  mov     [rsp+98h+var_78], rdx
0x1800f79a3  mov     edx, 20h ; ' '
0x1800f79a8  mov     rax, [rcx]
0x1800f79ab  lea     r9d, [rdx-1Dh]
0x1800f79af  mov     rax, [rax+50h]
0x1800f79b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f79b8  mov     ebx, eax
0x1800f79ba  test    eax, eax
0x1800f79bc  jns     short loc_1800F79F8
0x1800f79be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f79c5  lea     rax, WPP_GLOBAL_Control
0x1800f79cc  cmp     rcx, rax
0x1800f79cf  jz      loc_1800F7AB3
0x1800f79d5  test    byte ptr [rcx+1Ch], 8
0x1800f79d9  jz      loc_1800F7AB3
0x1800f79df  cmp     byte ptr [rcx+19h], 2
0x1800f79e3  jb      loc_1800F7AB3
0x1800f79e9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f79ee  mov     edx, 16h
0x1800f79f3  jmp     loc_1800F7903
0x1800f79f8  mov     rcx, [r14]
0x1800f79fb  xor     edx, edx
0x1800f79fd  mov     rax, [rcx]
0x1800f7a00  mov     rax, [rax+20h]
0x1800f7a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7a09  mov     ebx, eax
0x1800f7a0b  test    eax, eax
0x1800f7a0d  jns     short loc_1800F7A49
0x1800f7a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f7a16  lea     rax, WPP_GLOBAL_Control
0x1800f7a1d  cmp     rcx, rax
0x1800f7a20  jz      loc_1800F7AB3
0x1800f7a26  test    byte ptr [rcx+1Ch], 8
0x1800f7a2a  jz      loc_1800F7AB3
0x1800f7a30  cmp     byte ptr [rcx+19h], 2
0x1800f7a34  jb      short loc_1800F7AB3
0x1800f7a36  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f7a3b  mov     edx, 17h
0x1800f7a40  lea     rcx, aFailedToStartT_9; "Failed to start the notification thread"
0x1800f7a47  jmp     short loc_1800F7A90
0x1800f7a49  mov     rcx, [r15]
0x1800f7a4c  xor     edx, edx
0x1800f7a4e  mov     rax, [rcx]
0x1800f7a51  mov     rax, [rax+20h]
0x1800f7a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7a5a  mov     ebx, eax
0x1800f7a5c  test    eax, eax
0x1800f7a5e  jns     short loc_1800F7AB9
0x1800f7a60  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f7a67  lea     rax, WPP_GLOBAL_Control
0x1800f7a6e  cmp     rcx, rax
0x1800f7a71  jz      short loc_1800F7AB3
0x1800f7a73  test    byte ptr [rcx+1Ch], 8
0x1800f7a77  jz      short loc_1800F7AB3
0x1800f7a79  cmp     byte ptr [rcx+19h], 2
0x1800f7a7d  jb      short loc_1800F7AB3
0x1800f7a7f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f7a84  mov     edx, 18h
0x1800f7a89  lea     rcx, aFailedToStartT_0; "Failed to start the network thread"
0x1800f7a90  mov     dword ptr [rsp+98h+var_70], ebx
0x1800f7a94  lea     r8, WPP_52931a3895c83eda767ef6813e03ebe8_Traceguids
0x1800f7a9b  mov     [rsp+98h+var_78], rcx
0x1800f7aa0  mov     r9d, eax
0x1800f7aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f7aaa  mov     rcx, [rcx+10h]
0x1800f7aae  call    WPP_SF_DsD
0x1800f7ab3  or      dword ptr [rdi-14h], 4
0x1800f7ab7  jmp     short loc_1800F7AC0
0x1800f7ab9  or      dword ptr [rdi-14h], 2
0x1800f7abd  mov     ebx, r12d
0x1800f7ac0  mov     eax, ebx
0x1800f7ac2  add     rsp, 60h
0x1800f7ac6  pop     r15
  ... truncated ...
```
