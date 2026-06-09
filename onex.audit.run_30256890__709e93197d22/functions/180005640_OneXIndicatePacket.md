# OneXIndicatePacket

- ea: `0x180005640`
- end: `0x180005af3`
- name: `OneXIndicatePacket`
- size: `1203`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180005440`
- `0x1800054f0`
- `0x180005640`
- `0x180006160`
- `0x180007f60`
- `0x180010ae0`
- `0x18001d838`
- `0x1800214f0`
- `0x180023640`
- `0x18002d9a8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180005970`
- `MobileNetworking!ReleaseWriteLock` at `0x1800059ef`
- `MobileNetworking!ReleaseWriteLock` at `0x180005970`
- `MobileNetworking!ReleaseWriteLock` at `0x1800059ef`
- `MobileNetworking!AcquireWriteLock` at `0x180005855`
- `MobileNetworking!AcquireWriteLock` at `0x1800059b0`
- `MobileNetworking!AcquireWriteLock` at `0x180005855`
- `MobileNetworking!AcquireWriteLock` at `0x1800059b0`
- `MobileNetworking!FreeMemory` at `0x180005a0e`
- `MobileNetworking!FreeMemory` at `0x180005a0e`

## pseudocode

```c
__int64 __fastcall OneXIndicatePacket(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int16 v5; // r12
  _QWORD *v8; // rcx
  int v9; // ebp
  __int64 v10; // r9
  _BYTE *v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // r14d
  unsigned int v16; // eax
  __int64 v17; // r9
  _QWORD *v18; // r8
  signed __int32 v19; // edi
  _QWORD *v20; // rcx
  _QWORD *v22; // [rsp+30h] [rbp-38h] BYREF

  v5 = a3;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 117, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v8 + 17) & 0x100) != 0 )
      {
        WPP_SF_(v8[7], 118, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x400) != 0 )
        WPP_SF_sd(v8[7], 29, a3, (unsigned int)"OneXIndicatePacket", 94);
    }
  }
  v9 = 1;
  v10 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&qword_18003DD5C);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v10);
    v11 = WPP_GLOBAL_Control;
  }
  if ( HIDWORD(qword_18003DD5C) )
  {
    if ( a1 != 1 )
    {
      v12 = 50;
      if ( v11 == (_BYTE *)&WPP_GLOBAL_Control )
        goto LABEL_64;
      if ( (v11[68] & 1) == 0 )
        goto LABEL_61;
      v13 = 120;
      goto LABEL_20;
    }
    if ( !a4 || !v5 )
    {
      v12 = 87;
      if ( v11 == (_BYTE *)&WPP_GLOBAL_Control )
        goto LABEL_64;
      if ( (v11[68] & 1) == 0 )
        goto LABEL_61;
      WPP_SF_(*((_QWORD *)v11 + 7), 121, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      goto LABEL_60;
    }
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)v11 + 7), 57, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v14 = PortMgrValidateAndRefPort(a2, a2, a3, v10);
    v12 = v14;
    if ( v14 )
    {
      v9 = 0;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_51;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 7), 58, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v14, a2);
LABEL_38:
        v11 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      AcquireWriteLock(a2, a2 + 2896, "PortMgrValidateRefAndLockPort", 676);
      if ( *(int *)(a2 + 24) >= 0 )
        goto LABEL_38;
      v12 = 6;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_51;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          59,
          WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids,
          *(unsigned int *)(a2 + 20));
        goto LABEL_38;
      }
    }
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    {
      WPP_SF_D(*((_QWORD *)v11 + 7), 60, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v12);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v12 )
    {
      if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v11[68] & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v11 + 7), 122, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
        v11 = WPP_GLOBAL_Control;
      }
LABEL_51:
      if ( v9 )
      {
        ReleaseWriteLock(a2, a2 + 2896, "PortMgrUnlockAndDeRefPort", 694);
        v22 = (_QWORD *)a2;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 16), 0xFFFFFFFF) == 1 )
        {
          PortMgrDeInitPort(v22);
          AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 595);
          v17 = *v22;
          if ( *(_QWORD **)(*v22 + 8LL) != v22 || (v18 = (_QWORD *)v22[1], (_QWORD *)*v18 != v22) )
            __fastfail(3u);
          *v18 = v17;
          *(_QWORD *)(v17 + 8) = v18;
          ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 597);
          _InterlockedDecrement((_DWORD *)&qword_18003DD8C + 1);
          FreeMemory(&v22, "PortMgrDereferencePort", 601);
        }
        goto LABEL_60;
      }
      goto LABEL_61;
    }
    v15 = *(_DWORD *)(a2 + 20);
    v16 = OneXIndicatePacketHelper(a2, v5, a4);
    v12 = v16;
    if ( v16 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_51;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 123, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v15, v16);
    }
    v11 = WPP_GLOBAL_Control;
    goto LABEL_51;
  }
  if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v11[68] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)v11 + 7), 31, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  v12 = 21;
  if ( v11 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( (v11[68] & 1) != 0 )
    {
      v13 = 119;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v11 + 7), v13, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
LABEL_60:
      v11 = WPP_GLOBAL_Control;
    }
LABEL_61:
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x400) != 0 )
      WPP_SF_sd(*((_QWORD *)v11 + 7), 32, a3, (unsigned int)"OneXIndicatePacket", 120);
  }
LABEL_64:
  v19 = _InterlockedExchangeAdd((volatile signed __int32 *)&qword_18003DD5C, 0xFFFFFFFF);
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        33,
        WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids,
        (unsigned int)(v19 - 1));
      v20 = WPP_GLOBAL_Control;
    }
    if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 17) & 0x800) != 0 )
      WPP_SF_D(v20[7], 124, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180005640  mov     [rsp+arg_8], rbx
0x180005645  mov     [rsp+arg_10], rbp
0x18000564a  push    rsi
0x18000564b  push    rdi
0x18000564c  push    r12
0x18000564e  push    r13
0x180005650  push    r15
0x180005652  sub     rsp, 40h
0x180005656  mov     r15, r9
0x180005659  movzx   r12d, r8w
0x18000565d  mov     rsi, rdx
0x180005660  mov     ebx, ecx
0x180005662  mov     rcx, cs:WPP_GLOBAL_Control
0x180005669  lea     r13, WPP_GLOBAL_Control
0x180005670  cmp     rcx, r13
0x180005673  jz      short loc_1800056EF
0x180005675  test    dword ptr [rcx+44h], 800h
0x18000567c  jz      short loc_18000569A
0x18000567e  mov     rcx, [rcx+38h]
0x180005682  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180005689  mov     edx, 75h ; 'u'
0x18000568e  call    WPP_SF_
0x180005693  mov     rcx, cs:WPP_GLOBAL_Control
0x18000569a  cmp     rcx, r13
0x18000569d  jz      short loc_1800056EF
0x18000569f  test    dword ptr [rcx+44h], 100h
0x1800056a6  jz      short loc_1800056C4
0x1800056a8  mov     rcx, [rcx+38h]
0x1800056ac  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x1800056b3  mov     edx, 76h ; 'v'
0x1800056b8  call    WPP_SF_
0x1800056bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056c4  cmp     rcx, r13
0x1800056c7  jz      short loc_1800056EF
0x1800056c9  test    dword ptr [rcx+44h], 400h
0x1800056d0  jz      short loc_1800056EF
0x1800056d2  mov     rcx, [rcx+38h]
0x1800056d6  lea     r9, aOnexindicatepa_0; "OneXIndicatePacket"
0x1800056dd  mov     edx, 1Dh
0x1800056e2  mov     dword ptr [rsp+68h+var_48], 45Eh
0x1800056ea  call    WPP_SF_sd
0x1800056ef  mov     ebp, 1
0x1800056f4  mov     r9d, ebp
0x1800056f7  lock xadd dword ptr cs:qword_18003DD5C, r9d
0x180005700  inc     r9d
0x180005703  mov     rcx, cs:WPP_GLOBAL_Control
0x18000570a  cmp     rcx, r13
0x18000570d  jz      short loc_180005734
0x18000570f  test    dword ptr [rcx+44h], 400h
0x180005716  jz      short loc_180005734
0x180005718  mov     rcx, [rcx+38h]
0x18000571c  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180005723  mov     edx, 1Eh
0x180005728  call    WPP_SF_d
0x18000572d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005734  cmp     dword ptr cs:qword_18003DD5C+4, 0
0x18000573b  mov     edi, 0FFFFFFFFh
0x180005740  jnz     short loc_18000579E
0x180005742  cmp     rcx, r13
0x180005745  jz      short loc_180005769
0x180005747  test    [rcx+44h], bpl
0x18000574b  jz      short loc_180005769
0x18000574d  mov     rcx, [rcx+38h]
0x180005751  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180005758  mov     edx, 1Fh
0x18000575d  call    WPP_SF_
0x180005762  mov     rcx, cs:WPP_GLOBAL_Control
0x180005769  mov     ebx, 15h
0x18000576e  cmp     rcx, r13
0x180005771  jz      loc_180005A74
0x180005777  test    [rcx+44h], bpl
0x18000577b  jz      loc_180005A49
0x180005781  mov     edx, 77h ; 'w'
0x180005786  mov     rcx, [rcx+38h]
0x18000578a  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180005791  mov     r9d, ebx
0x180005794  call    WPP_SF_d
0x180005799  jmp     loc_180005A42
0x18000579e  cmp     ebx, ebp
0x1800057a0  jz      short loc_1800057C1
0x1800057a2  mov     ebx, 32h ; '2'
0x1800057a7  cmp     rcx, r13
0x1800057aa  jz      loc_180005A74
0x1800057b0  test    [rcx+44h], bpl
0x1800057b4  jz      loc_180005A49
0x1800057ba  mov     edx, 78h ; 'x'
0x1800057bf  jmp     short loc_180005786
0x1800057c1  test    r15, r15
0x1800057c4  jz      loc_180005A1D
0x1800057ca  xor     eax, eax
0x1800057cc  cmp     ax, r12w
0x1800057d0  jz      loc_180005A1D
0x1800057d6  cmp     rcx, r13
0x1800057d9  jz      short loc_1800057F9
0x1800057db  test    dword ptr [rcx+44h], 800h
0x1800057e2  jz      short loc_1800057F9
0x1800057e4  mov     rcx, [rcx+38h]
0x1800057e8  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800057ef  mov     edx, 39h ; '9'
0x1800057f4  call    WPP_SF_
0x1800057f9  mov     rcx, rsi
0x1800057fc  call    PortMgrValidateAndRefPort
0x180005801  mov     ebx, eax
0x180005803  test    eax, eax
0x180005805  jz      short loc_18000583E
0x180005807  xor     ebp, ebp
0x180005809  mov     rcx, cs:WPP_GLOBAL_Control
0x180005810  cmp     rcx, r13
0x180005813  jz      loc_180005951
0x180005819  test    byte ptr [rcx+44h], 1
0x18000581d  jz      short loc_18000589C
0x18000581f  mov     rcx, [rcx+38h]
0x180005823  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000582a  mov     edx, 3Ah ; ':'
0x18000582f  mov     [rsp+68h+var_48], rsi
0x180005834  mov     r9d, eax
0x180005837  call    WPP_SF_dq
0x18000583c  jmp     short loc_180005895
0x18000583e  lea     rdx, [rsi+0B50h]
0x180005845  mov     r9d, 2A4h
0x18000584b  lea     r8, aPortmgrvalidat; "PortMgrValidateRefAndLockPort"
0x180005852  mov     rcx, rsi
0x180005855  call    cs:__imp_AcquireWriteLock
0x18000585b  cmp     dword ptr [rsi+18h], 0
0x18000585f  jge     short loc_180005895
0x180005861  mov     ebx, 6
0x180005866  mov     rcx, cs:WPP_GLOBAL_Control
0x18000586d  cmp     rcx, r13
0x180005870  jz      loc_180005951
0x180005876  test    [rcx+44h], bpl
0x18000587a  jz      short loc_18000589C
0x18000587c  mov     r9d, [rsi+14h]
0x180005880  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180005887  mov     rcx, [rcx+38h]
0x18000588b  mov     edx, 3Bh ; ';'
0x180005890  call    WPP_SF_d
0x180005895  mov     rcx, cs:WPP_GLOBAL_Control
0x18000589c  cmp     rcx, r13
0x18000589f  jz      short loc_1800058C9
0x1800058a1  test    dword ptr [rcx+44h], 800h
0x1800058a8  jz      short loc_1800058C9
0x1800058aa  mov     rcx, [rcx+38h]
0x1800058ae  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800058b5  mov     edx, 3Ch ; '<'
0x1800058ba  mov     r9d, ebx
0x1800058bd  call    WPP_SF_D
0x1800058c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058c9  test    ebx, ebx
0x1800058cb  jz      short loc_1800058F9
0x1800058cd  cmp     rcx, r13
0x1800058d0  jz      short loc_180005951
0x1800058d2  test    byte ptr [rcx+44h], 1
0x1800058d6  jz      short loc_180005951
0x1800058d8  mov     rcx, [rcx+38h]
0x1800058dc  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x1800058e3  mov     edx, 7Ah ; 'z'
0x1800058e8  mov     r9d, ebx
0x1800058eb  call    WPP_SF_d
0x1800058f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058f7  jmp     short loc_180005951
0x1800058f9  mov     [rsp+68h+arg_0], r14
0x1800058fe  mov     r8, r15
0x180005901  mov     r14d, [rsi+14h]
0x180005905  movzx   edx, r12w
0x180005909  mov     rcx, rsi
0x18000590c  call    OneXIndicatePacketHelper
0x180005911  mov     ebx, eax
0x180005913  test    eax, eax
0x180005915  jz      short loc_180005945
0x180005917  mov     rcx, cs:WPP_GLOBAL_Control
0x18000591e  cmp     rcx, r13
0x180005921  jz      short loc_18000594C
0x180005923  test    byte ptr [rcx+44h], 1
0x180005927  jz      short loc_18000594C
0x180005929  mov     rcx, [rcx+38h]
0x18000592d  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180005934  mov     edx, 7Bh ; '{'
0x180005939  mov     dword ptr [rsp+68h+var_48], eax
0x18000593d  mov     r9d, r14d
0x180005940  call    WPP_SF_dd
0x180005945  mov     rcx, cs:WPP_GLOBAL_Control
0x18000594c  mov     r14, [rsp+68h+arg_0]
0x180005951  test    ebp, ebp
0x180005953  jz      loc_180005A49
0x180005959  lea     rdx, [rsi+0B50h]
0x180005960  mov     r9d, 2B6h
0x180005966  lea     r8, aPortmgrunlocka; "PortMgrUnlockAndDeRefPort"
0x18000596d  mov     rcx, rsi
0x180005970  call    cs:__imp_ReleaseWriteLock
0x180005976  mov     eax, edi
0x180005978  mov     [rsp+68h+var_38], rsi
0x18000597d  lock xadd [rsi+10h], eax
0x180005982  cmp     eax, 1
0x180005985  jnz     loc_180005A42
0x18000598b  mov     rcx, [rsp+68h+var_38]
0x180005990  call    PortMgrDeInitPort
0x180005995  mov     r9d, 253h
0x18000599b  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x1800059a2  lea     rdx, qword_18003DD98
0x1800059a9  lea     rcx, g_OneXInfo
0x1800059b0  call    cs:__imp_AcquireWriteLock
0x1800059b6  mov     rax, [rsp+68h+var_38]
0x1800059bb  mov     r9, [rax]
0x1800059be  cmp     [r9+8], rax
0x1800059c2  jnz     short loc_180005A16
0x1800059c4  mov     r8, [rax+8]
0x1800059c8  cmp     [r8], rax
0x1800059cb  jnz     short loc_180005A16
0x1800059cd  mov     [r8], r9
0x1800059d0  lea     rdx, qword_18003DD98
0x1800059d7  mov     [r9+8], r8
0x1800059db  lea     rcx, g_OneXInfo
0x1800059e2  mov     r9d, 255h
0x1800059e8  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x1800059ef  call    cs:__imp_ReleaseWriteLock
0x1800059f5  lock dec dword ptr cs:qword_18003DD8C+4
0x1800059fc  lea     rdx, aPortmgrderefer; "PortMgrDereferencePort"
0x180005a03  mov     r8d, 259h
0x180005a09  lea     rcx, [rsp+68h+var_38]
0x180005a0e  call    cs:__imp_FreeMemory
0x180005a14  jmp     short loc_180005A42
0x180005a16  mov     ecx, 3
0x180005a1b  int     29h; Win8: RtlFailFast(ecx)
0x180005a1d  mov     ebx, 57h ; 'W'
0x180005a22  cmp     rcx, r13
0x180005a25  jz      short loc_180005A74
0x180005a27  test    [rcx+44h], bpl
0x180005a2b  jz      short loc_180005A49
0x180005a2d  mov     rcx, [rcx+38h]
0x180005a31  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180005a38  mov     edx, 79h ; 'y'
0x180005a3d  call    WPP_SF_
0x180005a42  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a49  cmp     rcx, r13
0x180005a4c  jz      short loc_180005A74
0x180005a4e  test    dword ptr [rcx+44h], 400h
0x180005a55  jz      short loc_180005A74
0x180005a57  mov     rcx, [rcx+38h]
0x180005a5b  lea     r9, aOnexindicatepa_0; "OneXIndicatePacket"
0x180005a62  mov     edx, 20h ; ' '
0x180005a67  mov     dword ptr [rsp+68h+var_48], 478h
0x180005a6f  call    WPP_SF_sd
0x180005a74  lock xadd dword ptr cs:qword_18003DD5C, edi
0x180005a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a83  cmp     rcx, r13
0x180005a86  jz      short loc_180005AD7
0x180005a88  test    dword ptr [rcx+44h], 400h
0x180005a8f  jz      short loc_180005AB1
0x180005a91  mov     rcx, [rcx+38h]
0x180005a95  lea     r9d, [rdi-1]
0x180005a99  mov     edx, 21h ; '!'
0x180005a9e  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180005aa5  call    WPP_SF_d
0x180005aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ab1  cmp     rcx, r13
0x180005ab4  jz      short loc_180005AD7
0x180005ab6  test    dword ptr [rcx+44h], 800h
0x180005abd  jz      short loc_180005AD7
0x180005abf  mov     rcx, [rcx+38h]
0x180005ac3  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180005aca  mov     edx, 7Ch ; '|'
0x180005acf  mov     r9d, ebx
0x180005ad2  call    WPP_SF_D
0x180005ad7  mov     rbp, [rsp+68h+arg_10]
0x180005adf  mov     eax, ebx
0x180005ae1  mov     rbx, [rsp+68h+arg_8]
0x180005ae6  add     rsp, 40h
0x180005aea  pop     r15
0x180005aec  pop     r13
0x180005aee  pop     r12
0x180005af0  pop     rdi
0x180005af1  pop     rsi
0x180005af2  retn
```
