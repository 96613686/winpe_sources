# OneXStopAuthentication

- ea: `0x18000e230`
- end: `0x18000e6b9`
- name: `OneXStopAuthentication`
- size: `1161`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180004f40`
- `0x180005440`
- `0x1800054f0`
- `0x180007f60`
- `0x18000e230`
- `0x18000e6c0`
- `0x18000e888`
- `0x180010ae0`
- `0x18001d838`
- `0x1800214f0`
- `0x180023640`
- `0x18002d9a8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18000e609`
- `MobileNetworking!ReleaseWriteLock` at `0x18000e688`
- `MobileNetworking!ReleaseWriteLock` at `0x18000e609`
- `MobileNetworking!ReleaseWriteLock` at `0x18000e688`
- `MobileNetworking!AcquireWriteLock` at `0x18000e4c9`
- `MobileNetworking!AcquireWriteLock` at `0x18000e649`
- `MobileNetworking!AcquireWriteLock` at `0x18000e4c9`
- `MobileNetworking!AcquireWriteLock` at `0x18000e649`
- `MobileNetworking!FreeMemory` at `0x18000e6a7`
- `MobileNetworking!FreeMemory` at `0x18000e6a7`

## pseudocode

```c
__int64 __fastcall OneXStopAuthentication(int a1, __int64 a2, __int64 a3)
{
  _QWORD *v5; // rcx
  int v6; // ebp
  __int64 v7; // r9
  _BYTE *v8; // rcx
  unsigned int v9; // esi
  __int64 v10; // rdx
  signed __int32 v11; // edi
  _QWORD *v12; // rcx
  unsigned int v14; // eax
  unsigned int v15; // r14d
  unsigned int GlobalEvent; // eax
  __int64 v17; // r9
  _QWORD *v18; // r8
  _QWORD *v19; // [rsp+68h] [rbp+20h] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 53, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v5 + 17) & 0x100) != 0 )
      {
        WPP_SF_(v5[7], 54, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
        v5 = WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x400) != 0 )
        WPP_SF_sd(v5[7], 29, a3, (unsigned int)"OneXStopAuthentication", 233);
    }
  }
  v6 = 1;
  v7 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&qword_18003DD5C);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v7);
    v8 = WPP_GLOBAL_Control;
  }
  if ( HIDWORD(qword_18003DD5C) )
  {
    if ( a1 != 1 )
    {
      v9 = 50;
      if ( v8 == (_BYTE *)&WPP_GLOBAL_Control )
        goto LABEL_25;
      if ( (v8[68] & 1) == 0 )
        goto LABEL_22;
      v10 = 56;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v8 + 7), v10, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v9);
LABEL_21:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_22;
    }
    if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)v8 + 7), 57, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v14 = PortMgrValidateAndRefPort(a2, a2, a3, v7);
    v9 = v14;
    if ( v14 )
    {
      v6 = 0;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_63;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_48:
        if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
        {
          WPP_SF_D(*((_QWORD *)v8 + 7), 60, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v9);
          v8 = WPP_GLOBAL_Control;
        }
        if ( v9 )
        {
          if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (v8[68] & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)v8 + 7), 57, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v9);
            v8 = WPP_GLOBAL_Control;
          }
          goto LABEL_63;
        }
        v15 = *(_DWORD *)(a2 + 20);
        if ( (Microsoft_Windows_OneXEnableBits & 2) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(v8, AuthenticationStop, v15);
        GlobalEvent = GenerateGlobalEvent(a2);
        v9 = GlobalEvent;
        if ( GlobalEvent )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_63;
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            58,
            WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids,
            v15,
            GlobalEvent);
        }
        else
        {
          WriteOneXStopAuthenticationTelemetry(a2, 0);
        }
        v8 = WPP_GLOBAL_Control;
LABEL_63:
        if ( !v6 )
          goto LABEL_22;
        ReleaseWriteLock(a2, a2 + 2896, "PortMgrUnlockAndDeRefPort", 694);
        v19 = (_QWORD *)a2;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 16), 0xFFFFFFFF) == 1 )
        {
          PortMgrDeInitPort(v19);
          AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 595);
          v17 = *v19;
          if ( *(_QWORD **)(*v19 + 8LL) != v19 || (v18 = (_QWORD *)v19[1], (_QWORD *)*v18 != v19) )
            __fastfail(3u);
          *v18 = v17;
          *(_QWORD *)(v17 + 8) = v18;
          ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 597);
          _InterlockedDecrement((_DWORD *)&qword_18003DD8C + 1);
          FreeMemory(&v19, "PortMgrDereferencePort", 601);
        }
        goto LABEL_21;
      }
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 7), 58, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v14, a2);
    }
    else
    {
      AcquireWriteLock(a2, a2 + 2896, "PortMgrValidateRefAndLockPort", 676);
      if ( *(int *)(a2 + 24) < 0 )
      {
        v9 = 6;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_63;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_48;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          59,
          WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids,
          *(unsigned int *)(a2 + 20));
      }
    }
    v8 = WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (v8[68] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)v8 + 7), 31, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = 21;
  if ( v8 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( (v8[68] & 1) == 0 )
    {
LABEL_22:
      if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x400) != 0 )
        WPP_SF_sd(*((_QWORD *)v8 + 7), 32, a3, (unsigned int)"OneXStopAuthentication", 3);
      goto LABEL_25;
    }
    v10 = 55;
    goto LABEL_20;
  }
LABEL_25:
  v11 = _InterlockedExchangeAdd((volatile signed __int32 *)&qword_18003DD5C, 0xFFFFFFFF);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        33,
        WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids,
        (unsigned int)(v11 - 1));
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
      WPP_SF_D(v12[7], 59, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18000e230  mov     [rsp+arg_8], rbx
0x18000e235  mov     [rsp+arg_10], rbp
0x18000e23a  push    rsi
0x18000e23b  push    rdi
0x18000e23c  push    r15
0x18000e23e  sub     rsp, 30h
0x18000e242  mov     rbx, rdx
0x18000e245  mov     esi, ecx
0x18000e247  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e24e  lea     r15, WPP_GLOBAL_Control
0x18000e255  cmp     rcx, r15
0x18000e258  jz      short loc_18000E2D4
0x18000e25a  test    dword ptr [rcx+44h], 800h
0x18000e261  jz      short loc_18000E27F
0x18000e263  mov     rcx, [rcx+38h]
0x18000e267  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000e26e  mov     edx, 35h ; '5'
0x18000e273  call    WPP_SF_
0x18000e278  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e27f  cmp     rcx, r15
0x18000e282  jz      short loc_18000E2D4
0x18000e284  test    dword ptr [rcx+44h], 100h
0x18000e28b  jz      short loc_18000E2A9
0x18000e28d  mov     rcx, [rcx+38h]
0x18000e291  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000e298  mov     edx, 36h ; '6'
0x18000e29d  call    WPP_SF_
0x18000e2a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2a9  cmp     rcx, r15
0x18000e2ac  jz      short loc_18000E2D4
0x18000e2ae  test    dword ptr [rcx+44h], 400h
0x18000e2b5  jz      short loc_18000E2D4
0x18000e2b7  mov     rcx, [rcx+38h]
0x18000e2bb  lea     r9, aOnexstopauthen_0; "OneXStopAuthentication"
0x18000e2c2  mov     edx, 1Dh
0x18000e2c7  mov     dword ptr [rsp+48h+var_28], 1E9h
0x18000e2cf  call    WPP_SF_sd
0x18000e2d4  mov     ebp, 1
0x18000e2d9  mov     r9d, ebp
0x18000e2dc  lock xadd dword ptr cs:qword_18003DD5C, r9d
0x18000e2e5  inc     r9d
0x18000e2e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2ef  cmp     rcx, r15
0x18000e2f2  jz      short loc_18000E319
0x18000e2f4  test    dword ptr [rcx+44h], 400h
0x18000e2fb  jz      short loc_18000E319
0x18000e2fd  mov     rcx, [rcx+38h]
0x18000e301  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18000e308  mov     edx, 1Eh
0x18000e30d  call    WPP_SF_d
0x18000e312  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e319  cmp     dword ptr cs:qword_18003DD5C+4, 0
0x18000e320  mov     edi, 0FFFFFFFFh
0x18000e325  jnz     loc_18000E424
0x18000e32b  cmp     rcx, r15
0x18000e32e  jz      short loc_18000E352
0x18000e330  test    [rcx+44h], bpl
0x18000e334  jz      short loc_18000E352
0x18000e336  mov     rcx, [rcx+38h]
0x18000e33a  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18000e341  mov     edx, 1Fh
0x18000e346  call    WPP_SF_
0x18000e34b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e352  mov     esi, 15h
0x18000e357  cmp     rcx, r15
0x18000e35a  jz      short loc_18000E3AC
0x18000e35c  test    [rcx+44h], bpl
0x18000e360  jz      short loc_18000E381
0x18000e362  mov     edx, 37h ; '7'
0x18000e367  mov     rcx, [rcx+38h]
0x18000e36b  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000e372  mov     r9d, esi
0x18000e375  call    WPP_SF_d
0x18000e37a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e381  cmp     rcx, r15
0x18000e384  jz      short loc_18000E3AC
0x18000e386  test    dword ptr [rcx+44h], 400h
0x18000e38d  jz      short loc_18000E3AC
0x18000e38f  mov     rcx, [rcx+38h]
0x18000e393  lea     r9, aOnexstopauthen_0; "OneXStopAuthentication"
0x18000e39a  mov     edx, 20h ; ' '
0x18000e39f  mov     dword ptr [rsp+48h+var_28], 203h
0x18000e3a7  call    WPP_SF_sd
0x18000e3ac  lock xadd dword ptr cs:qword_18003DD5C, edi
0x18000e3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3bb  cmp     rcx, r15
0x18000e3be  jz      short loc_18000E40F
0x18000e3c0  test    dword ptr [rcx+44h], 400h
0x18000e3c7  jz      short loc_18000E3E9
0x18000e3c9  mov     rcx, [rcx+38h]
0x18000e3cd  lea     r9d, [rdi-1]
0x18000e3d1  mov     edx, 21h ; '!'
0x18000e3d6  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18000e3dd  call    WPP_SF_d
0x18000e3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3e9  cmp     rcx, r15
0x18000e3ec  jz      short loc_18000E40F
0x18000e3ee  test    dword ptr [rcx+44h], 800h
0x18000e3f5  jz      short loc_18000E40F
0x18000e3f7  mov     rcx, [rcx+38h]
0x18000e3fb  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000e402  mov     edx, 3Bh ; ';'
0x18000e407  mov     r9d, esi
0x18000e40a  call    WPP_SF_D
0x18000e40f  mov     rbx, [rsp+48h+arg_8]
0x18000e414  mov     eax, esi
0x18000e416  mov     rbp, [rsp+48h+arg_10]
0x18000e41b  add     rsp, 30h
0x18000e41f  pop     r15
0x18000e421  pop     rdi
0x18000e422  pop     rsi
0x18000e423  retn
0x18000e424  cmp     esi, ebp
0x18000e426  jz      short loc_18000E44A
0x18000e428  mov     esi, 32h ; '2'
0x18000e42d  cmp     rcx, r15
0x18000e430  jz      loc_18000E3AC
0x18000e436  test    [rcx+44h], bpl
0x18000e43a  jz      loc_18000E381
0x18000e440  mov     edx, 38h ; '8'
0x18000e445  jmp     loc_18000E367
0x18000e44a  cmp     rcx, r15
0x18000e44d  jz      short loc_18000E46D
0x18000e44f  test    dword ptr [rcx+44h], 800h
0x18000e456  jz      short loc_18000E46D
0x18000e458  mov     rcx, [rcx+38h]
0x18000e45c  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000e463  mov     edx, 39h ; '9'
0x18000e468  call    WPP_SF_
0x18000e46d  mov     rcx, rbx
0x18000e470  call    PortMgrValidateAndRefPort
0x18000e475  mov     esi, eax
0x18000e477  test    eax, eax
0x18000e479  jz      short loc_18000E4B2
0x18000e47b  xor     ebp, ebp
0x18000e47d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e484  cmp     rcx, r15
0x18000e487  jz      loc_18000E5EA
0x18000e48d  test    byte ptr [rcx+44h], 1
0x18000e491  jz      short loc_18000E510
0x18000e493  mov     rcx, [rcx+38h]
0x18000e497  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000e49e  mov     edx, 3Ah ; ':'
0x18000e4a3  mov     [rsp+48h+var_28], rbx
0x18000e4a8  mov     r9d, eax
0x18000e4ab  call    WPP_SF_dq
0x18000e4b0  jmp     short loc_18000E509
0x18000e4b2  lea     rdx, [rbx+0B50h]
0x18000e4b9  mov     r9d, 2A4h
0x18000e4bf  lea     r8, aPortmgrvalidat; "PortMgrValidateRefAndLockPort"
0x18000e4c6  mov     rcx, rbx
0x18000e4c9  call    cs:__imp_AcquireWriteLock
0x18000e4cf  cmp     dword ptr [rbx+18h], 0
0x18000e4d3  jge     short loc_18000E509
0x18000e4d5  mov     esi, 6
0x18000e4da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4e1  cmp     rcx, r15
0x18000e4e4  jz      loc_18000E5EA
0x18000e4ea  test    [rcx+44h], bpl
0x18000e4ee  jz      short loc_18000E510
0x18000e4f0  mov     r9d, [rbx+14h]
0x18000e4f4  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000e4fb  mov     rcx, [rcx+38h]
0x18000e4ff  mov     edx, 3Bh ; ';'
0x18000e504  call    WPP_SF_d
0x18000e509  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e510  cmp     rcx, r15
0x18000e513  jz      short loc_18000E53D
0x18000e515  test    dword ptr [rcx+44h], 800h
0x18000e51c  jz      short loc_18000E53D
0x18000e51e  mov     rcx, [rcx+38h]
0x18000e522  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000e529  mov     edx, 3Ch ; '<'
0x18000e52e  mov     r9d, esi
0x18000e531  call    WPP_SF_D
0x18000e536  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e53d  test    esi, esi
0x18000e53f  jz      short loc_18000E575
0x18000e541  cmp     rcx, r15
0x18000e544  jz      loc_18000E5EA
0x18000e54a  test    byte ptr [rcx+44h], 1
0x18000e54e  jz      loc_18000E5EA
0x18000e554  mov     rcx, [rcx+38h]
0x18000e558  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000e55f  mov     edx, 39h ; '9'
0x18000e564  mov     r9d, esi
0x18000e567  call    WPP_SF_d
0x18000e56c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e573  jmp     short loc_18000E5EA
0x18000e575  test    cs:Microsoft_Windows_OneXEnableBits, 2
0x18000e57c  mov     [rsp+48h+arg_0], r14
0x18000e581  mov     r14d, [rbx+14h]
0x18000e585  jz      short loc_18000E596
0x18000e587  mov     r8d, r14d
0x18000e58a  lea     rdx, AuthenticationStop
0x18000e591  call    McTemplateU0q_EtwEventWriteTransfer
0x18000e596  mov     rcx, rbx
0x18000e599  call    GenerateGlobalEvent
0x18000e59e  mov     esi, eax
0x18000e5a0  test    eax, eax
0x18000e5a2  jz      short loc_18000E5D4
0x18000e5a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5ab  cmp     rcx, r15
0x18000e5ae  jz      short loc_18000E5E5
0x18000e5b0  test    byte ptr [rcx+44h], 1
0x18000e5b4  jz      short loc_18000E5E5
0x18000e5b6  mov     rcx, [rcx+38h]
0x18000e5ba  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000e5c1  mov     edx, 3Ah ; ':'
0x18000e5c6  mov     dword ptr [rsp+48h+var_28], eax
0x18000e5ca  mov     r9d, r14d
0x18000e5cd  call    WPP_SF_dd
0x18000e5d2  jmp     short loc_18000E5DE
0x18000e5d4  xor     edx, edx
0x18000e5d6  mov     rcx, rbx
0x18000e5d9  call    WriteOneXStopAuthenticationTelemetry
0x18000e5de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5e5  mov     r14, [rsp+48h+arg_0]
0x18000e5ea  test    ebp, ebp
0x18000e5ec  jz      loc_18000E381
0x18000e5f2  lea     rdx, [rbx+0B50h]
0x18000e5f9  mov     r9d, 2B6h
0x18000e5ff  lea     r8, aPortmgrunlocka; "PortMgrUnlockAndDeRefPort"
0x18000e606  mov     rcx, rbx
0x18000e609  call    cs:__imp_ReleaseWriteLock
0x18000e60f  mov     eax, edi
0x18000e611  mov     [rsp+48h+arg_18], rbx
0x18000e616  lock xadd [rbx+10h], eax
0x18000e61b  cmp     eax, 1
0x18000e61e  jnz     loc_18000E37A
0x18000e624  mov     rcx, [rsp+48h+arg_18]
0x18000e629  call    PortMgrDeInitPort
0x18000e62e  mov     r9d, 253h
0x18000e634  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x18000e63b  lea     rdx, qword_18003DD98
0x18000e642  lea     rcx, g_OneXInfo
0x18000e649  call    cs:__imp_AcquireWriteLock
0x18000e64f  mov     rax, [rsp+48h+arg_18]
0x18000e654  mov     r9, [rax]
0x18000e657  cmp     [r9+8], rax
0x18000e65b  jnz     short loc_18000E6B2
0x18000e65d  mov     r8, [rax+8]
0x18000e661  cmp     [r8], rax
0x18000e664  jnz     short loc_18000E6B2
0x18000e666  mov     [r8], r9
0x18000e669  lea     rdx, qword_18003DD98
0x18000e670  mov     [r9+8], r8
0x18000e674  lea     rcx, g_OneXInfo
0x18000e67b  mov     r9d, 255h
0x18000e681  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x18000e688  call    cs:__imp_ReleaseWriteLock
0x18000e68e  lock dec dword ptr cs:qword_18003DD8C+4
0x18000e695  lea     rdx, aPortmgrderefer; "PortMgrDereferencePort"
0x18000e69c  mov     r8d, 259h
0x18000e6a2  lea     rcx, [rsp+48h+arg_18]
0x18000e6a7  call    cs:__imp_FreeMemory
0x18000e6ad  jmp     loc_18000E37A
0x18000e6b2  mov     ecx, 3
0x18000e6b7  int     29h; Win8: RtlFailFast(ecx)
```
