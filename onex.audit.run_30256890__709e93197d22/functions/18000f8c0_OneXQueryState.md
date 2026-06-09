# OneXQueryState

- ea: `0x18000f8c0`
- end: `0x18000fd17`
- name: `OneXQueryState`
- size: `1111`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180005440`
- `0x1800054f0`
- `0x180007f60`
- `0x18000f8c0`
- `0x18000fd20`
- `0x180010ae0`
- `0x18001d838`
- `0x1800214f0`
- `0x180023640`
- `0x18002d9a8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18000fbc1`
- `MobileNetworking!ReleaseWriteLock` at `0x18000fc40`
- `MobileNetworking!ReleaseWriteLock` at `0x18000fbc1`
- `MobileNetworking!ReleaseWriteLock` at `0x18000fc40`
- `MobileNetworking!AcquireWriteLock` at `0x18000faa7`
- `MobileNetworking!AcquireWriteLock` at `0x18000fc01`
- `MobileNetworking!AcquireWriteLock` at `0x18000faa7`
- `MobileNetworking!AcquireWriteLock` at `0x18000fc01`
- `MobileNetworking!FreeMemory` at `0x18000fc5f`
- `MobileNetworking!FreeMemory` at `0x18000fc5f`

## pseudocode

```c
__int64 __fastcall OneXQueryState(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v8; // rcx
  int v9; // esi
  __int64 v10; // r9
  _BYTE *v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // r12d
  unsigned int v16; // eax
  __int64 v17; // r9
  _QWORD *v18; // r8
  signed __int32 v19; // edi
  _QWORD *v21; // [rsp+30h] [rbp-38h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 70, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x400) != 0 )
      WPP_SF_sd(v8[7], 29, a3, (unsigned int)"OneXQueryState", 133);
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
        goto LABEL_61;
      if ( (v11[68] & 1) == 0 )
        goto LABEL_58;
      v13 = 72;
      goto LABEL_17;
    }
    if ( !a4 || !a3 )
    {
      v12 = 87;
      if ( v11 == (_BYTE *)&WPP_GLOBAL_Control )
        goto LABEL_61;
      if ( (v11[68] & 1) == 0 )
        goto LABEL_58;
      WPP_SF_(*((_QWORD *)v11 + 7), 73, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      goto LABEL_57;
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
        goto LABEL_48;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 7), 58, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v14, a2);
LABEL_35:
        v11 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      AcquireWriteLock(a2, a2 + 2896, "PortMgrValidateRefAndLockPort", 676);
      if ( *(int *)(a2 + 24) >= 0 )
        goto LABEL_35;
      v12 = 6;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_48;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          59,
          WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids,
          *(unsigned int *)(a2 + 20));
        goto LABEL_35;
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
        WPP_SF_d(*((_QWORD *)v11 + 7), 74, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
        v11 = WPP_GLOBAL_Control;
      }
LABEL_48:
      if ( v9 )
      {
        ReleaseWriteLock(a2, a2 + 2896, "PortMgrUnlockAndDeRefPort", 694);
        v21 = (_QWORD *)a2;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 16), 0xFFFFFFFF) == 1 )
        {
          PortMgrDeInitPort(v21);
          AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 595);
          v17 = *v21;
          if ( *(_QWORD **)(*v21 + 8LL) != v21 || (v18 = (_QWORD *)v21[1], (_QWORD *)*v18 != v21) )
            __fastfail(3u);
          *v18 = v17;
          *(_QWORD *)(v17 + 8) = v18;
          ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 597);
          _InterlockedDecrement((_DWORD *)&qword_18003DD8C + 1);
          FreeMemory(&v21, "PortMgrDereferencePort", 601);
        }
        goto LABEL_57;
      }
      goto LABEL_58;
    }
    v15 = *(_DWORD *)(a2 + 20);
    v16 = OneXQueryStateHelper(a2, a3, a4);
    v12 = v16;
    if ( v16 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_48;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 75, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v15, v16);
    }
    v11 = WPP_GLOBAL_Control;
    goto LABEL_48;
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
      v13 = 71;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v11 + 7), v13, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
LABEL_57:
      v11 = WPP_GLOBAL_Control;
    }
LABEL_58:
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x400) != 0 )
      WPP_SF_sd(*((_QWORD *)v11 + 7), 32, a3, (unsigned int)"OneXQueryState", 159);
  }
LABEL_61:
  v19 = _InterlockedExchangeAdd((volatile signed __int32 *)&qword_18003DD5C, 0xFFFFFFFF);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      33,
      WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids,
      (unsigned int)(v19 - 1));
  return v12;
}

```

## disassembly

```asm
0x18000f8c0  mov     [rsp+arg_8], rbx
0x18000f8c5  mov     [rsp+arg_10], rbp
0x18000f8ca  push    rsi
0x18000f8cb  push    rdi
0x18000f8cc  push    r13
0x18000f8ce  push    r14
0x18000f8d0  push    r15
0x18000f8d2  sub     rsp, 40h
0x18000f8d6  mov     r14, r9
0x18000f8d9  mov     r15, r8
0x18000f8dc  mov     rbp, rdx
0x18000f8df  mov     ebx, ecx
0x18000f8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8e8  lea     r13, WPP_GLOBAL_Control
0x18000f8ef  cmp     rcx, r13
0x18000f8f2  jz      short loc_18000F944
0x18000f8f4  test    dword ptr [rcx+44h], 800h
0x18000f8fb  jz      short loc_18000F919
0x18000f8fd  mov     rcx, [rcx+38h]
0x18000f901  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000f908  mov     edx, 46h ; 'F'
0x18000f90d  call    WPP_SF_
0x18000f912  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f919  cmp     rcx, r13
0x18000f91c  jz      short loc_18000F944
0x18000f91e  test    dword ptr [rcx+44h], 400h
0x18000f925  jz      short loc_18000F944
0x18000f927  mov     rcx, [rcx+38h]
0x18000f92b  lea     r9, aOnexquerystate_0; "OneXQueryState"
0x18000f932  mov     edx, 1Dh
0x18000f937  mov     dword ptr [rsp+68h+var_48], 285h
0x18000f93f  call    WPP_SF_sd
0x18000f944  mov     esi, 1
0x18000f949  mov     r9d, esi
0x18000f94c  lock xadd dword ptr cs:qword_18003DD5C, r9d
0x18000f955  inc     r9d
0x18000f958  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f95f  cmp     rcx, r13
0x18000f962  jz      short loc_18000F989
0x18000f964  test    dword ptr [rcx+44h], 400h
0x18000f96b  jz      short loc_18000F989
0x18000f96d  mov     rcx, [rcx+38h]
0x18000f971  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18000f978  mov     edx, 1Eh
0x18000f97d  call    WPP_SF_d
0x18000f982  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f989  cmp     dword ptr cs:qword_18003DD5C+4, 0
0x18000f990  mov     edi, 0FFFFFFFFh
0x18000f995  jnz     short loc_18000F9F3
0x18000f997  cmp     rcx, r13
0x18000f99a  jz      short loc_18000F9BE
0x18000f99c  test    [rcx+44h], sil
0x18000f9a0  jz      short loc_18000F9BE
0x18000f9a2  mov     rcx, [rcx+38h]
0x18000f9a6  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18000f9ad  mov     edx, 1Fh
0x18000f9b2  call    WPP_SF_
0x18000f9b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9be  mov     ebx, 15h
0x18000f9c3  cmp     rcx, r13
0x18000f9c6  jz      loc_18000FCC5
0x18000f9cc  test    [rcx+44h], sil
0x18000f9d0  jz      loc_18000FC9A
0x18000f9d6  mov     edx, 47h ; 'G'
0x18000f9db  mov     rcx, [rcx+38h]
0x18000f9df  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000f9e6  mov     r9d, ebx
0x18000f9e9  call    WPP_SF_d
0x18000f9ee  jmp     loc_18000FC93
0x18000f9f3  cmp     ebx, esi
0x18000f9f5  jz      short loc_18000FA16
0x18000f9f7  mov     ebx, 32h ; '2'
0x18000f9fc  cmp     rcx, r13
0x18000f9ff  jz      loc_18000FCC5
0x18000fa05  test    [rcx+44h], sil
0x18000fa09  jz      loc_18000FC9A
0x18000fa0f  mov     edx, 48h ; 'H'
0x18000fa14  jmp     short loc_18000F9DB
0x18000fa16  test    r14, r14
0x18000fa19  jz      loc_18000FC6E
0x18000fa1f  test    r15, r15
0x18000fa22  jz      loc_18000FC6E
0x18000fa28  cmp     rcx, r13
0x18000fa2b  jz      short loc_18000FA4B
0x18000fa2d  test    dword ptr [rcx+44h], 800h
0x18000fa34  jz      short loc_18000FA4B
0x18000fa36  mov     rcx, [rcx+38h]
0x18000fa3a  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000fa41  mov     edx, 39h ; '9'
0x18000fa46  call    WPP_SF_
0x18000fa4b  mov     rcx, rbp
0x18000fa4e  call    PortMgrValidateAndRefPort
0x18000fa53  mov     ebx, eax
0x18000fa55  test    eax, eax
0x18000fa57  jz      short loc_18000FA90
0x18000fa59  xor     esi, esi
0x18000fa5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa62  cmp     rcx, r13
0x18000fa65  jz      loc_18000FBA2
0x18000fa6b  test    byte ptr [rcx+44h], 1
0x18000fa6f  jz      short loc_18000FAEE
0x18000fa71  mov     rcx, [rcx+38h]
0x18000fa75  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000fa7c  mov     edx, 3Ah ; ':'
0x18000fa81  mov     [rsp+68h+var_48], rbp
0x18000fa86  mov     r9d, eax
0x18000fa89  call    WPP_SF_dq
0x18000fa8e  jmp     short loc_18000FAE7
0x18000fa90  lea     rdx, [rbp+0B50h]
0x18000fa97  mov     r9d, 2A4h
0x18000fa9d  lea     r8, aPortmgrvalidat; "PortMgrValidateRefAndLockPort"
0x18000faa4  mov     rcx, rbp
0x18000faa7  call    cs:__imp_AcquireWriteLock
0x18000faad  cmp     dword ptr [rbp+18h], 0
0x18000fab1  jge     short loc_18000FAE7
0x18000fab3  mov     ebx, 6
0x18000fab8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fabf  cmp     rcx, r13
0x18000fac2  jz      loc_18000FBA2
0x18000fac8  test    [rcx+44h], sil
0x18000facc  jz      short loc_18000FAEE
0x18000face  mov     r9d, [rbp+14h]
0x18000fad2  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000fad9  mov     rcx, [rcx+38h]
0x18000fadd  mov     edx, 3Bh ; ';'
0x18000fae2  call    WPP_SF_d
0x18000fae7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000faee  cmp     rcx, r13
0x18000faf1  jz      short loc_18000FB1B
0x18000faf3  test    dword ptr [rcx+44h], 800h
0x18000fafa  jz      short loc_18000FB1B
0x18000fafc  mov     rcx, [rcx+38h]
0x18000fb00  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000fb07  mov     edx, 3Ch ; '<'
0x18000fb0c  mov     r9d, ebx
0x18000fb0f  call    WPP_SF_D
0x18000fb14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb1b  test    ebx, ebx
0x18000fb1d  jz      short loc_18000FB4B
0x18000fb1f  cmp     rcx, r13
0x18000fb22  jz      short loc_18000FBA2
0x18000fb24  test    byte ptr [rcx+44h], 1
0x18000fb28  jz      short loc_18000FBA2
0x18000fb2a  mov     rcx, [rcx+38h]
0x18000fb2e  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000fb35  mov     edx, 4Ah ; 'J'
0x18000fb3a  mov     r9d, ebx
0x18000fb3d  call    WPP_SF_d
0x18000fb42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb49  jmp     short loc_18000FBA2
0x18000fb4b  mov     [rsp+68h+arg_0], r12
0x18000fb50  mov     r8, r14
0x18000fb53  mov     r12d, [rbp+14h]
0x18000fb57  mov     rdx, r15
0x18000fb5a  mov     rcx, rbp
0x18000fb5d  call    OneXQueryStateHelper
0x18000fb62  mov     ebx, eax
0x18000fb64  test    eax, eax
0x18000fb66  jz      short loc_18000FB96
0x18000fb68  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb6f  cmp     rcx, r13
0x18000fb72  jz      short loc_18000FB9D
0x18000fb74  test    byte ptr [rcx+44h], 1
0x18000fb78  jz      short loc_18000FB9D
0x18000fb7a  mov     rcx, [rcx+38h]
0x18000fb7e  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000fb85  mov     edx, 4Bh ; 'K'
0x18000fb8a  mov     dword ptr [rsp+68h+var_48], eax
0x18000fb8e  mov     r9d, r12d
0x18000fb91  call    WPP_SF_dd
0x18000fb96  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb9d  mov     r12, [rsp+68h+arg_0]
0x18000fba2  test    esi, esi
0x18000fba4  jz      loc_18000FC9A
0x18000fbaa  lea     rdx, [rbp+0B50h]
0x18000fbb1  mov     r9d, 2B6h
0x18000fbb7  lea     r8, aPortmgrunlocka; "PortMgrUnlockAndDeRefPort"
0x18000fbbe  mov     rcx, rbp
0x18000fbc1  call    cs:__imp_ReleaseWriteLock
0x18000fbc7  mov     eax, edi
0x18000fbc9  mov     [rsp+68h+var_38], rbp
0x18000fbce  lock xadd [rbp+10h], eax
0x18000fbd3  cmp     eax, 1
0x18000fbd6  jnz     loc_18000FC93
0x18000fbdc  mov     rcx, [rsp+68h+var_38]
0x18000fbe1  call    PortMgrDeInitPort
0x18000fbe6  mov     r9d, 253h
0x18000fbec  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x18000fbf3  lea     rdx, qword_18003DD98
0x18000fbfa  lea     rcx, g_OneXInfo
0x18000fc01  call    cs:__imp_AcquireWriteLock
0x18000fc07  mov     rax, [rsp+68h+var_38]
0x18000fc0c  mov     r9, [rax]
0x18000fc0f  cmp     [r9+8], rax
0x18000fc13  jnz     short loc_18000FC67
0x18000fc15  mov     r8, [rax+8]
0x18000fc19  cmp     [r8], rax
0x18000fc1c  jnz     short loc_18000FC67
0x18000fc1e  mov     [r8], r9
0x18000fc21  lea     rdx, qword_18003DD98
0x18000fc28  mov     [r9+8], r8
0x18000fc2c  lea     rcx, g_OneXInfo
0x18000fc33  mov     r9d, 255h
0x18000fc39  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x18000fc40  call    cs:__imp_ReleaseWriteLock
0x18000fc46  lock dec dword ptr cs:qword_18003DD8C+4
0x18000fc4d  lea     rdx, aPortmgrderefer; "PortMgrDereferencePort"
0x18000fc54  mov     r8d, 259h
0x18000fc5a  lea     rcx, [rsp+68h+var_38]
0x18000fc5f  call    cs:__imp_FreeMemory
0x18000fc65  jmp     short loc_18000FC93
0x18000fc67  mov     ecx, 3
0x18000fc6c  int     29h; Win8: RtlFailFast(ecx)
0x18000fc6e  mov     ebx, 57h ; 'W'
0x18000fc73  cmp     rcx, r13
0x18000fc76  jz      short loc_18000FCC5
0x18000fc78  test    [rcx+44h], sil
0x18000fc7c  jz      short loc_18000FC9A
0x18000fc7e  mov     rcx, [rcx+38h]
0x18000fc82  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000fc89  mov     edx, 49h ; 'I'
0x18000fc8e  call    WPP_SF_
0x18000fc93  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc9a  cmp     rcx, r13
0x18000fc9d  jz      short loc_18000FCC5
0x18000fc9f  test    dword ptr [rcx+44h], 400h
0x18000fca6  jz      short loc_18000FCC5
0x18000fca8  mov     rcx, [rcx+38h]
0x18000fcac  lea     r9, aOnexquerystate_0; "OneXQueryState"
0x18000fcb3  mov     edx, 20h ; ' '
0x18000fcb8  mov     dword ptr [rsp+68h+var_48], 29Fh
0x18000fcc0  call    WPP_SF_sd
0x18000fcc5  lock xadd dword ptr cs:qword_18003DD5C, edi
0x18000fccd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcd4  cmp     rcx, r13
0x18000fcd7  jz      short loc_18000FCFB
0x18000fcd9  test    dword ptr [rcx+44h], 400h
0x18000fce0  jz      short loc_18000FCFB
0x18000fce2  mov     rcx, [rcx+38h]
0x18000fce6  lea     r9d, [rdi-1]
0x18000fcea  mov     edx, 21h ; '!'
0x18000fcef  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18000fcf6  call    WPP_SF_d
0x18000fcfb  mov     rbp, [rsp+68h+arg_10]
0x18000fd03  mov     eax, ebx
0x18000fd05  mov     rbx, [rsp+68h+arg_8]
0x18000fd0a  add     rsp, 40h
0x18000fd0e  pop     r15
0x18000fd10  pop     r14
0x18000fd12  pop     r13
0x18000fd14  pop     rdi
0x18000fd15  pop     rsi
0x18000fd16  retn
```
