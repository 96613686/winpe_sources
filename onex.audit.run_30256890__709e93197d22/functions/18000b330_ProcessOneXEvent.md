# ProcessOneXEvent

- ea: `0x18000b330`
- end: `0x18000ba24`
- name: `ProcessOneXEvent`
- size: `1780`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x180004f40`
- `0x180005440`
- `0x18000ad00`
- `0x18000b330`
- `0x18000ba30`
- `0x18000c5a0`
- `0x180010ae0`
- `0x180019f7c`
- `0x18001a9c4`
- `0x1800214f0`
- `0x180022000`
- `0x180023640`
- `0x180024578`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b81c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b81c`
- `MobileNetworking!ReleaseWriteLock` at `0x18000b8e8`
- `MobileNetworking!ReleaseWriteLock` at `0x18000b973`
- `MobileNetworking!ReleaseWriteLock` at `0x18000b8e8`
- `MobileNetworking!ReleaseWriteLock` at `0x18000b973`
- `MobileNetworking!AcquireWriteLock` at `0x18000b3a7`
- `MobileNetworking!AcquireWriteLock` at `0x18000b92c`
- `MobileNetworking!AcquireWriteLock` at `0x18000b3a7`
- `MobileNetworking!AcquireWriteLock` at `0x18000b92c`
- `MobileNetworking!FreeMemory` at `0x18000b7e8`
- `MobileNetworking!FreeMemory` at `0x18000b804`
- `MobileNetworking!FreeMemory` at `0x18000b84a`
- `MobileNetworking!FreeMemory` at `0x18000b992`
- `MobileNetworking!FreeMemory` at `0x18000b7e8`
- `MobileNetworking!FreeMemory` at `0x18000b804`
- `MobileNetworking!FreeMemory` at `0x18000b84a`
- `MobileNetworking!FreeMemory` at `0x18000b992`

## string_xrefs

- `0x18000b7e1`: `OneXDeleteEvent`
- `0x18000b7fd`: `OneXDeleteEvent`
- `0x18000b83b`: `OneXDeleteEvent`
- `0x18000b48e`: `ConfigChanged`

## pseudocode

```c
__int64 __fastcall ProcessOneXEvent(__int64 a1)
{
  unsigned int v1; // r14d
  __int64 v3; // rbx
  __int64 v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *v6; // r12
  _QWORD *v7; // rbx
  __int64 v8; // rax
  _QWORD *v9; // r10
  int v10; // eax
  const wchar_t *v11; // rax
  __int64 v12; // rsi
  unsigned int v13; // ebp
  int v14; // r15d
  __int64 i; // rdi
  unsigned int v16; // eax
  _QWORD *v17; // r10
  __int64 v18; // rax
  __int64 v19; // r10
  __int64 GlobalEventDescription; // rax
  __int64 v21; // r10
  int v22; // edx
  int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // rdi
  __int64 v26; // rdx
  void *v27; // rcx
  __int64 v28; // r9
  _QWORD *v29; // r8
  _QWORD *v31; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v32; // [rsp+80h] [rbp+18h] BYREF

  v1 = *(_DWORD *)(a1 + 20);
  LODWORD(v31) = v1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v3 = a1 + 2896;
  AcquireWriteLock(a1, a1 + 2896, "ProcessOneXEvent", 354);
  if ( *(int *)(a1 + 24) >= 0 )
  {
    v6 = (_QWORD *)(a1 + 176);
    while ( 1 )
    {
      while ( 1 )
      {
        v7 = (_QWORD *)*v6;
        if ( (_QWORD *)*v6 == v6 )
        {
          *(_DWORD *)(a1 + 24) &= ~0x10000000u;
          v3 = a1 + 2896;
          goto LABEL_92;
        }
        if ( (_QWORD *)v7[1] != v6 )
          goto LABEL_104;
        v8 = *v7;
        if ( *(_QWORD **)(*v7 + 8LL) != v7 )
          goto LABEL_104;
        *v6 = v8;
        *(_QWORD *)(v8 + 8) = v6;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0 )
        {
          v10 = *((_DWORD *)v7 + 4);
          if ( v10 == 1 )
          {
            v11 = L"StartAuth";
          }
          else if ( v10 == 6 )
          {
            v11 = L"EapPkt";
          }
          else
          {
            switch ( v10 )
            {
              case 0:
                v11 = L"StopAuth";
                break;
              case 2:
                v11 = L"SetAuthParams";
                break;
              case 3:
                v11 = L"ForceAuthenticated";
                break;
              case 4:
                v11 = L"SessionNotification";
                break;
              case 5:
                v11 = L"ConfigChanged";
                break;
              case 7:
                v11 = L"Timeout";
                break;
              case 8:
                v11 = L"UIResponse";
                break;
              case 9:
                v11 = L"SetEapAttributes";
                break;
              case 10:
                v11 = L"SetRuntimeState";
                break;
              case 11:
                v11 = L"SelfAuthRestarted";
                break;
              case 12:
                v11 = L"Max";
                break;
              default:
                v11 = L"OneXEventInvalid";
                break;
            }
          }
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            34,
            (unsigned int)WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids,
            v1,
            (__int64)v11);
          v9 = WPP_GLOBAL_Control;
        }
        if ( *((_DWORD *)v7 + 4) == 7 )
        {
          if ( byte_18003DF42 < 0 )
          {
            McTemplateU0q_EtwEventWriteTransfer(v4, OneXAuthTimeout, v1);
            v9 = WPP_GLOBAL_Control;
          }
          if ( a1 != -2496 )
          {
            *(_DWORD *)(a1 + 2724) = 1;
            v9 = WPP_GLOBAL_Control;
          }
        }
        v12 = v7[3];
        v13 = 0;
        v14 = *(_DWORD *)(v12 + 20);
        if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
          WPP_SF_(v9[7], 39, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
        for ( i = 0; ; i = 1 )
        {
          if ( (_DWORD)i )
            goto LABEL_50;
          v4 = 5 * i;
          if ( LODWORD(qword_18003A008[5 * i]) == *(_DWORD *)(v12 + 2376) )
          {
            v16 = ((__int64 (__fastcall *)(_QWORD *))*(&funcs_18000B5C8 + 5 * i))(v7);
            v13 = v16;
            if ( v16 )
              break;
          }
LABEL_46:
          ;
        }
        if ( v16 == 13 )
        {
          v13 = 0;
          goto LABEL_46;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_dSD(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              40,
              (unsigned int)WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids,
              v14,
              (__int64)(&g_StateMachinesTable)[5 * i],
              v16);
LABEL_50:
            v17 = WPP_GLOBAL_Control;
          }
          if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 17) & 0x800) != 0 )
          {
            WPP_SF_D(v17[7], 41, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v13);
            v17 = WPP_GLOBAL_Control;
          }
          if ( !v13 )
            goto LABEL_55;
        }
        if ( v17 == &WPP_GLOBAL_Control )
        {
          v1 = (unsigned int)v31;
          goto LABEL_63;
        }
        if ( (*((_BYTE *)v17 + 68) & 1) == 0 )
        {
LABEL_55:
          v1 = (unsigned int)v31;
          goto LABEL_56;
        }
        GlobalEventDescription = GetGlobalEventDescription(*((unsigned int *)v7 + 4));
        v1 = (unsigned int)v31;
        WPP_SF_dDS(*(_QWORD *)(v21 + 56), v22, v23, (_DWORD)v31, v13, GlobalEventDescription);
        v17 = WPP_GLOBAL_Control;
LABEL_56:
        if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 68) & 0x40) != 0 )
        {
          v18 = GetGlobalEventDescription(*((unsigned int *)v7 + 4));
          WPP_SF_dS(*(_QWORD *)(v19 + 56), 36, (unsigned int)WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v1, v18);
          v17 = WPP_GLOBAL_Control;
        }
LABEL_63:
        v32 = v7;
        if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 17) & 0x800) != 0 )
        {
          WPP_SF_(v17[7], 17, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
          v17 = WPP_GLOBAL_Control;
          v7 = v32;
        }
        if ( v7 )
          break;
        if ( v17 != &WPP_GLOBAL_Control )
        {
          v24 = 87;
          if ( (*((_BYTE *)v17 + 68) & 1) != 0 )
          {
            WPP_SF_d(v17[7], 18, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, 0);
            goto LABEL_87;
          }
          goto LABEL_88;
        }
      }
      v24 = 0;
      v25 = 0;
      if ( *((_DWORD *)v7 + 8) )
        break;
LABEL_86:
      FreeMemory(&v32, "OneXDeleteEvent", 190);
LABEL_87:
      v17 = WPP_GLOBAL_Control;
LABEL_88:
      if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 17) & 0x800) != 0 )
        WPP_SF_D(v17[7], 19, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v24);
    }
    while ( 1 )
    {
      v26 = 2LL * (unsigned int)v25;
      switch ( LODWORD(v7[v26 + 5]) )
      {
        case 3:
          v27 = (void *)v7[2 * v25 + 6];
          if ( v27 )
          {
            CloseHandle(v27);
            goto LABEL_84;
          }
          break;
        case 5:
          FreeMemory(&v7[v26 + 6], "OneXDeleteEvent", 158);
          goto LABEL_84;
        case 6:
          FreeMemory(&v7[v26 + 6], "OneXDeleteEvent", 162);
          goto LABEL_84;
        case 7:
          if ( v7[2 * v25 + 6] )
          {
            FreeEapAttributes();
LABEL_84:
            v7 = v32;
          }
          break;
        default:
          if ( LODWORD(v7[v26 + 5]) != 8 || !v7[2 * v25 + 6] )
            break;
          OneXFreeRuntimeState();
          goto LABEL_84;
      }
      v25 = (unsigned int)(v25 + 1);
      if ( (unsigned int)v25 >= *((_DWORD *)v7 + 8) )
        goto LABEL_86;
    }
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_96;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v1);
LABEL_92:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x800) != 0 )
    WPP_SF_d(v5[7], 37, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v1);
LABEL_96:
  ReleaseWriteLock(a1, v3, "ProcessOneXEvent", 431);
  v31 = (_QWORD *)a1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
  {
    PortMgrDeInitPort(v31);
    AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 595);
    v28 = *v31;
    if ( *(_QWORD **)(*v31 + 8LL) == v31 )
    {
      v29 = (_QWORD *)v31[1];
      if ( (_QWORD *)*v29 == v31 )
      {
        *v29 = v28;
        *(_QWORD *)(v28 + 8) = v29;
        ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 597);
        _InterlockedDecrement((_DWORD *)&qword_18003DD8C + 1);
        FreeMemory(&v31, "PortMgrDereferencePort", 601);
        goto LABEL_100;
      }
    }
LABEL_104:
    __fastfail(3u);
  }
LABEL_100:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 38, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18000b330  push    rbx
0x18000b332  push    r13
0x18000b334  push    r14
0x18000b336  push    r15
0x18000b338  sub     rsp, 48h
0x18000b33c  mov     r14d, [rcx+14h]
0x18000b340  mov     r13, rcx
0x18000b343  mov     dword ptr [rsp+68h+arg_0], r14d
0x18000b348  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b34f  lea     r15, WPP_GLOBAL_Control
0x18000b356  cmp     rcx, r15
0x18000b359  jz      short loc_18000B379
0x18000b35b  test    dword ptr [rcx+44h], 800h
0x18000b362  jz      short loc_18000B379
0x18000b364  mov     rcx, [rcx+38h]
0x18000b368  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b36f  mov     edx, 20h ; ' '
0x18000b374  call    WPP_SF_
0x18000b379  mov     [rsp+68h+arg_8], rbp
0x18000b37e  lea     rbx, [r13+0B50h]
0x18000b385  mov     [rsp+68h+var_28], rsi
0x18000b38a  lea     r8, aProcessonexeve; "ProcessOneXEvent"
0x18000b391  mov     [rsp+68h+var_30], rdi
0x18000b396  mov     rdx, rbx
0x18000b399  mov     r9d, 162h
0x18000b39f  mov     [rsp+68h+var_38], r12
0x18000b3a4  mov     rcx, r13
0x18000b3a7  call    cs:__imp_AcquireWriteLock
0x18000b3ad  cmp     dword ptr [r13+18h], 0
0x18000b3b2  jge     short loc_18000B3EB
0x18000b3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3bb  cmp     rcx, r15
0x18000b3be  jz      loc_18000B8D5
0x18000b3c4  test    byte ptr [rcx+44h], 1
0x18000b3c8  jz      loc_18000B8AF
0x18000b3ce  mov     rcx, [rcx+38h]
0x18000b3d2  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b3d9  mov     edx, 21h ; '!'
0x18000b3de  mov     r9d, r14d
0x18000b3e1  call    WPP_SF_d
0x18000b3e6  jmp     loc_18000B8A8
0x18000b3eb  lea     r12, [r13+0B0h]
0x18000b3f2  lea     rdx, __ImageBase
0x18000b3f9  nop     dword ptr [rax+00000000h]
0x18000b400  mov     rbx, [r12]
0x18000b404  cmp     rbx, r12
0x18000b407  jz      loc_18000B899
0x18000b40d  cmp     [rbx+8], r12
0x18000b411  jnz     loc_18000B9E7
0x18000b417  mov     rax, [rbx]
0x18000b41a  cmp     [rax+8], rbx
0x18000b41e  jnz     loc_18000B9E7
0x18000b424  mov     [r12], rax
0x18000b428  mov     [rax+8], r12
0x18000b42c  mov     r10, cs:WPP_GLOBAL_Control
0x18000b433  cmp     r10, r15
0x18000b436  jz      loc_18000B511
0x18000b43c  test    byte ptr [r10+44h], 40h
0x18000b441  jz      loc_18000B511
0x18000b447  movsxd  rax, dword ptr [rbx+10h]
0x18000b44b  cmp     eax, 1
0x18000b44e  jz      loc_18000B4DF
0x18000b454  cmp     eax, 6
0x18000b457  jz      short loc_18000B4D6
0x18000b459  cmp     eax, 0Ch; switch 13 cases
0x18000b45c  ja      short def_18000B468; jumptable 000000018000B468 default case, cases 1,6
0x18000b45e  mov     ecx, ds:(jpt_18000B468 - 180000000h)[rdx+rax*4]
0x18000b465  add     rcx, rdx
0x18000b468  jmp     rcx; switch jump
0x18000b46a  lea     rax, aStopauth; jumptable 000000018000B468 case 0
0x18000b471  jmp     short loc_18000B4E6
0x18000b473  lea     rax, aSetauthparams; jumptable 000000018000B468 case 2
0x18000b47a  jmp     short loc_18000B4E6
0x18000b47c  lea     rax, aForceauthentic; jumptable 000000018000B468 case 3
0x18000b483  jmp     short loc_18000B4E6
0x18000b485  lea     rax, aSessionnotific; jumptable 000000018000B468 case 4
0x18000b48c  jmp     short loc_18000B4E6
0x18000b48e  lea     rax, aConfigchanged; jumptable 000000018000B468 case 5
0x18000b495  jmp     short loc_18000B4E6
0x18000b497  lea     rax, aTimeout; jumptable 000000018000B468 case 7
0x18000b49e  jmp     short loc_18000B4E6
0x18000b4a0  lea     rax, aUiresponse; jumptable 000000018000B468 case 8
0x18000b4a7  jmp     short loc_18000B4E6
0x18000b4a9  lea     rax, aSeteapattribut; jumptable 000000018000B468 case 9
0x18000b4b0  jmp     short loc_18000B4E6
0x18000b4b2  lea     rax, aSetruntimestat; jumptable 000000018000B468 case 10
0x18000b4b9  jmp     short loc_18000B4E6
0x18000b4bb  lea     rax, aSelfauthrestar; jumptable 000000018000B468 case 11
0x18000b4c2  jmp     short loc_18000B4E6
0x18000b4c4  lea     rax, aMax; jumptable 000000018000B468 case 12
0x18000b4cb  jmp     short loc_18000B4E6
0x18000b4cd  lea     rax, aOnexeventinval; jumptable 000000018000B468 default case, cases 1,6
0x18000b4d4  jmp     short loc_18000B4E6
0x18000b4d6  lea     rax, aEappkt; "EapPkt"
0x18000b4dd  jmp     short loc_18000B4E6
0x18000b4df  lea     rax, aStartauth; "StartAuth"
0x18000b4e6  mov     rcx, [r10+38h]
0x18000b4ea  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b4f1  mov     edx, 22h ; '"'
0x18000b4f6  mov     [rsp+68h+var_48], rax
0x18000b4fb  mov     r9d, r14d
0x18000b4fe  call    WPP_SF_dS
0x18000b503  mov     r10, cs:WPP_GLOBAL_Control
0x18000b50a  lea     rdx, __ImageBase
0x18000b511  cmp     dword ptr [rbx+10h], 7
0x18000b515  jnz     short loc_18000B55A
0x18000b517  cmp     cs:byte_18003DF42, 0
0x18000b51e  lea     rdi, [r13+9C0h]
0x18000b525  jge     short loc_18000B544
0x18000b527  mov     r8d, r14d
0x18000b52a  lea     rdx, OneXAuthTimeout
0x18000b531  call    McTemplateU0q_EtwEventWriteTransfer
0x18000b536  mov     r10, cs:WPP_GLOBAL_Control
0x18000b53d  lea     rdx, __ImageBase
0x18000b544  test    rdi, rdi
0x18000b547  jz      short loc_18000B55A
0x18000b549  mov     dword ptr [rdi+0E4h], 1
0x18000b553  mov     r10, cs:WPP_GLOBAL_Control
0x18000b55a  mov     rsi, [rbx+18h]
0x18000b55e  xor     ebp, ebp
0x18000b560  mov     r15d, [rsi+14h]
0x18000b564  lea     rax, WPP_GLOBAL_Control
0x18000b56b  cmp     r10, rax
0x18000b56e  jz      short loc_18000B596
0x18000b570  test    dword ptr [r10+44h], 800h
0x18000b578  jz      short loc_18000B596
0x18000b57a  mov     rcx, [r10+38h]
0x18000b57e  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b585  mov     edx, 27h ; '''
0x18000b58a  call    WPP_SF_
0x18000b58f  lea     rdx, __ImageBase
0x18000b596  xor     edi, edi
0x18000b598  cmp     edi, 1
0x18000b59b  jnb     loc_18000B633
0x18000b5a1  mov     eax, [rsi+948h]
0x18000b5a7  lea     rcx, [rdi+rdi*4]
0x18000b5ab  lea     r14, ds:0[rcx*8]
0x18000b5b3  cmp     [r14+rdx+3A008h], eax
0x18000b5bb  jnz     short loc_18000B5E1
0x18000b5bd  mov     rax, (funcs_18000B5C8 - 180000000h)[r14+rdx]
0x18000b5c5  mov     rcx, rbx
0x18000b5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5cd  mov     ebp, eax
0x18000b5cf  test    eax, eax
0x18000b5d1  jz      short loc_18000B5DA
0x18000b5d3  cmp     eax, 0Dh
0x18000b5d6  jnz     short loc_18000B5E5
0x18000b5d8  xor     ebp, ebp
0x18000b5da  lea     rdx, __ImageBase
0x18000b5e1  inc     edi
0x18000b5e3  jmp     short loc_18000B598
0x18000b5e5  mov     r10, cs:WPP_GLOBAL_Control
0x18000b5ec  lea     rax, WPP_GLOBAL_Control
0x18000b5f3  cmp     r10, rax
0x18000b5f6  jz      loc_18000B6B2
0x18000b5fc  test    byte ptr [r10+44h], 1
0x18000b601  jz      short loc_18000B63A
0x18000b603  mov     rcx, [r10+38h]
0x18000b607  lea     rax, __ImageBase
0x18000b60e  mov     rax, [r14+rax+3A000h]
0x18000b616  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b61d  mov     edx, 28h ; '('
0x18000b622  mov     dword ptr [rsp+68h+var_40], ebp
0x18000b626  mov     r9d, r15d
0x18000b629  mov     [rsp+68h+var_48], rax
0x18000b62e  call    WPP_SF_dSD
0x18000b633  mov     r10, cs:WPP_GLOBAL_Control
0x18000b63a  lea     r15, WPP_GLOBAL_Control
0x18000b641  cmp     r10, r15
0x18000b644  jz      short loc_18000B66F
0x18000b646  test    dword ptr [r10+44h], 800h
0x18000b64e  jz      short loc_18000B66F
0x18000b650  mov     rcx, [r10+38h]
0x18000b654  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b65b  mov     edx, 29h ; ')'
0x18000b660  mov     r9d, ebp
0x18000b663  call    WPP_SF_D
0x18000b668  mov     r10, cs:WPP_GLOBAL_Control
0x18000b66f  test    ebp, ebp
0x18000b671  jnz     short loc_18000B6B9
0x18000b673  mov     r14d, dword ptr [rsp+68h+arg_0]
0x18000b678  cmp     r10, r15
0x18000b67b  jz      short loc_18000B6F5
0x18000b67d  test    byte ptr [r10+44h], 40h
0x18000b682  jz      short loc_18000B6F5
0x18000b684  mov     ecx, [rbx+10h]
0x18000b687  call    GetGlobalEventDescription
0x18000b68c  mov     rcx, [r10+38h]
0x18000b690  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b697  mov     edx, 24h ; '$'
0x18000b69c  mov     [rsp+68h+var_48], rax
0x18000b6a1  mov     r9d, r14d
0x18000b6a4  call    WPP_SF_dS
0x18000b6a9  mov     r10, cs:WPP_GLOBAL_Control
0x18000b6b0  jmp     short loc_18000B6F5
0x18000b6b2  lea     r15, WPP_GLOBAL_Control
0x18000b6b9  cmp     r10, r15
0x18000b6bc  jz      short loc_18000B6F0
0x18000b6be  test    byte ptr [r10+44h], 1
0x18000b6c3  jz      short loc_18000B673
0x18000b6c5  mov     ecx, [rbx+10h]
0x18000b6c8  call    GetGlobalEventDescription
0x18000b6cd  mov     r14d, dword ptr [rsp+68h+arg_0]
0x18000b6d2  mov     r9d, r14d
0x18000b6d5  mov     rcx, [r10+38h]
0x18000b6d9  mov     [rsp+68h+var_40], rax
0x18000b6de  mov     dword ptr [rsp+68h+var_48], ebp
0x18000b6e2  call    WPP_SF_dDS
0x18000b6e7  mov     r10, cs:WPP_GLOBAL_Control
0x18000b6ee  jmp     short loc_18000B678
0x18000b6f0  mov     r14d, dword ptr [rsp+68h+arg_0]
0x18000b6f5  mov     [rsp+68h+arg_10], rbx
0x18000b6fd  cmp     r10, r15
0x18000b700  jz      short loc_18000B730
0x18000b702  test    dword ptr [r10+44h], 800h
0x18000b70a  jz      short loc_18000B730
0x18000b70c  mov     rcx, [r10+38h]
0x18000b710  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b717  mov     edx, 11h
0x18000b71c  call    WPP_SF_
0x18000b721  mov     r10, cs:WPP_GLOBAL_Control
0x18000b728  mov     rbx, [rsp+68h+arg_10]
0x18000b730  test    rbx, rbx
0x18000b733  jnz     short loc_18000B772
0x18000b735  lea     rdx, __ImageBase
0x18000b73c  cmp     r10, r15
0x18000b73f  jz      loc_18000B400
0x18000b745  test    byte ptr [r10+44h], 1
0x18000b74a  mov     esi, 57h ; 'W'
0x18000b74f  jz      loc_18000B857
0x18000b755  mov     rcx, [r10+38h]
0x18000b759  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b760  mov     edx, 12h
0x18000b765  xor     r9d, r9d
0x18000b768  call    WPP_SF_d
0x18000b76d  jmp     loc_18000B850
0x18000b772  xor     esi, esi
0x18000b774  xor     edi, edi
0x18000b776  cmp     [rbx+20h], esi
0x18000b779  jbe     loc_18000B835
0x18000b77f  mov     edx, edi
0x18000b781  shl     rdx, 4
0x18000b785  mov     ecx, [rdx+rbx+28h]
0x18000b789  sub     ecx, 3
0x18000b78c  jz      short loc_18000B80C
0x18000b78e  sub     ecx, 2
0x18000b791  jz      short loc_18000B7F0
0x18000b793  sub     ecx, 1
0x18000b796  jz      short loc_18000B7D4
0x18000b798  sub     ecx, 1
0x18000b79b  jz      short loc_18000B7BD
0x18000b79d  cmp     ecx, 1
0x18000b7a0  jnz     loc_18000B82A
0x18000b7a6  lea     rax, [rdi+3]
0x18000b7aa  add     rax, rax
0x18000b7ad  mov     rcx, [rbx+rax*8]
0x18000b7b1  test    rcx, rcx
0x18000b7b4  jz      short loc_18000B82A
0x18000b7b6  call    OneXFreeRuntimeState
0x18000b7bb  jmp     short loc_18000B822
0x18000b7bd  lea     rax, [rdi+3]
0x18000b7c1  add     rax, rax
0x18000b7c4  mov     rcx, [rbx+rax*8]
0x18000b7c8  test    rcx, rcx
0x18000b7cb  jz      short loc_18000B82A
0x18000b7cd  call    FreeEapAttributes
0x18000b7d2  jmp     short loc_18000B822
0x18000b7d4  lea     rcx, [rbx+30h]
0x18000b7d8  mov     r8d, 0A2h
0x18000b7de  add     rcx, rdx
0x18000b7e1  lea     rdx, aOnexdeleteeven; "OneXDeleteEvent"
0x18000b7e8  call    cs:__imp_FreeMemory
0x18000b7ee  jmp     short loc_18000B822
0x18000b7f0  lea     rcx, [rbx+30h]
0x18000b7f4  mov     r8d, 9Eh
0x18000b7fa  add     rcx, rdx
0x18000b7fd  lea     rdx, aOnexdeleteeven; "OneXDeleteEvent"
0x18000b804  call    cs:__imp_FreeMemory
0x18000b80a  jmp     short loc_18000B822
0x18000b80c  lea     rax, [rdi+3]
0x18000b810  add     rax, rax
0x18000b813  mov     rcx, [rbx+rax*8]; hObject
0x18000b817  test    rcx, rcx
0x18000b81a  jz      short loc_18000B82A
0x18000b81c  call    cs:__imp_CloseHandle
0x18000b822  mov     rbx, [rsp+68h+arg_10]
0x18000b82a  inc     edi
0x18000b82c  cmp     edi, [rbx+20h]
0x18000b82f  jb      loc_18000B77F
0x18000b835  mov     r8d, 0BEh
0x18000b83b  lea     rdx, aOnexdeleteeven; "OneXDeleteEvent"
0x18000b842  lea     rcx, [rsp+68h+arg_10]
0x18000b84a  call    cs:__imp_FreeMemory
0x18000b850  mov     r10, cs:WPP_GLOBAL_Control
0x18000b857  lea     rdx, __ImageBase
0x18000b85e  cmp     r10, r15
0x18000b861  jz      loc_18000B400
0x18000b867  test    dword ptr [r10+44h], 800h
0x18000b86f  lea     rdx, __ImageBase
0x18000b876  jz      loc_18000B400
  ... truncated ...
```
