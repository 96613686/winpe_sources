# OneXUpdatePortProfile

- ea: `0x180003c80`
- end: `0x18000426e`
- name: `OneXUpdatePortProfile`
- size: `1518`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callees

- `0x180003a1c`
- `0x180003c80`
- `0x180004280`
- `0x180005440`
- `0x1800054f0`
- `0x180007f60`
- `0x180010ae0`
- `0x18001d838`
- `0x1800214f0`
- `0x180023640`
- `0x18002d9a8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800040eb`
- `MobileNetworking!ReleaseWriteLock` at `0x18000416a`
- `MobileNetworking!ReleaseWriteLock` at `0x1800040eb`
- `MobileNetworking!ReleaseWriteLock` at `0x18000416a`
- `MobileNetworking!AcquireWriteLock` at `0x180003e9c`
- `MobileNetworking!AcquireWriteLock` at `0x18000412b`
- `MobileNetworking!AcquireWriteLock` at `0x180003e9c`
- `MobileNetworking!AcquireWriteLock` at `0x18000412b`
- `MobileNetworking!FreeMemory` at `0x180004189`
- `MobileNetworking!FreeMemory` at `0x180004189`

## string_xrefs

- `0x180003d1d`: `OneXUpdatePortProfile`
- `0x1800041d6`: `OneXUpdatePortProfile`

## pseudocode

```c
__int64 __fastcall OneXUpdatePortProfile(int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v6; // r14d
  _QWORD *v9; // rcx
  int v10; // r12d
  __int64 v11; // r9
  _BYTE *v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // r13d
  unsigned int v17; // eax
  _QWORD *v18; // rcx
  unsigned int v19; // ebp
  __int64 v20; // r9
  _QWORD *v21; // r8
  signed __int32 v22; // esi
  _QWORD *v23; // rcx
  _QWORD v25[7]; // [rsp+30h] [rbp-38h] BYREF

  LODWORD(v25[0]) = 0;
  v6 = a3;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 60, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v9 + 17) & 0x100) != 0 )
      {
        WPP_SF_(v9[7], 61, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x400) != 0 )
        WPP_SF_sd(v9[7], 29, a3, (unsigned int)"OneXUpdatePortProfile", 53);
    }
  }
  v10 = 1;
  v11 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&qword_18003DD5C);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v11);
    v12 = WPP_GLOBAL_Control;
  }
  if ( HIDWORD(qword_18003DD5C) )
  {
    if ( a1 != 1 )
    {
      v13 = 50;
      if ( v12 == (_BYTE *)&WPP_GLOBAL_Control )
        goto LABEL_82;
      if ( (v12[68] & 1) == 0 )
        goto LABEL_79;
      v14 = 63;
      goto LABEL_20;
    }
    if ( !a4 || !v6 )
    {
      v13 = 87;
      if ( v12 == (_BYTE *)&WPP_GLOBAL_Control )
        goto LABEL_82;
      if ( (v12[68] & 1) == 0 )
        goto LABEL_79;
      WPP_SF_(*((_QWORD *)v12 + 7), 64, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      goto LABEL_78;
    }
    if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)v12 + 7), 57, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v15 = PortMgrValidateAndRefPort(a2, a2, a3, v11);
    v13 = v15;
    if ( v15 )
    {
      v10 = 0;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 7), 58, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v15, a2);
LABEL_38:
        v12 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      AcquireWriteLock(a2, a2 + 2896, "PortMgrValidateRefAndLockPort", 676);
      if ( *(int *)(a2 + 24) >= 0 )
        goto LABEL_38;
      v13 = 6;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_69;
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
    if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
    {
      WPP_SF_D(*((_QWORD *)v12 + 7), 60, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v13);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v13 )
    {
      if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (v12[68] & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v12 + 7), 65, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v13);
        v12 = WPP_GLOBAL_Control;
      }
LABEL_69:
      if ( v10 )
      {
        ReleaseWriteLock(a2, a2 + 2896, "PortMgrUnlockAndDeRefPort", 694);
        v25[0] = a2;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 16), 0xFFFFFFFF) == 1 )
        {
          PortMgrDeInitPort(v25[0]);
          AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 595);
          v20 = *(_QWORD *)v25[0];
          if ( *(_QWORD *)(*(_QWORD *)v25[0] + 8LL) != v25[0] || (v21 = *(_QWORD **)(v25[0] + 8LL), *v21 != v25[0]) )
            __fastfail(3u);
          *v21 = v20;
          *(_QWORD *)(v20 + 8) = v21;
          ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 597);
          _InterlockedDecrement((_DWORD *)&qword_18003DD8C + 1);
          FreeMemory(v25, "PortMgrDereferencePort", 601);
        }
        goto LABEL_78;
      }
      goto LABEL_79;
    }
    v16 = *(_DWORD *)(a2 + 20);
    v17 = OneXValidateProfile(v6, a4, *(unsigned int *)(a2 + 200), v25);
    v13 = v17;
    if ( v17 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_69;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v16, v17);
      goto LABEL_68;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 67, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v16, v6);
      v18 = WPP_GLOBAL_Control;
    }
    v19 = *(_DWORD *)(a2 + 20);
    if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 17) & 0x800) != 0 )
      WPP_SF_(v18[7], 39, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
    v13 = OneXGenerateConfigChangedEvent(a2, v6, a4, a5);
    if ( v13 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
LABEL_64:
        if ( !v13 || v12 == (_BYTE *)&WPP_GLOBAL_Control || (v12[68] & 1) == 0 )
          goto LABEL_69;
        WPP_SF_dd(*((_QWORD *)v12 + 7), 68, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v16, v13);
LABEL_68:
        v12 = WPP_GLOBAL_Control;
        goto LABEL_69;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_61:
        if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
        {
          WPP_SF_D(*((_QWORD *)v12 + 7), 41, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v13);
          v12 = WPP_GLOBAL_Control;
        }
        goto LABEL_64;
      }
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 40, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v19, v13);
    }
    v12 = WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (v12[68] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)v12 + 7), 31, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  v13 = 21;
  if ( v12 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( (v12[68] & 1) != 0 )
    {
      v14 = 62;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v12 + 7), v14, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v13);
LABEL_78:
      v12 = WPP_GLOBAL_Control;
    }
LABEL_79:
    if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x400) != 0 )
      WPP_SF_sd(*((_QWORD *)v12 + 7), 32, a3, (unsigned int)"OneXUpdatePortProfile", 87);
  }
LABEL_82:
  v22 = _InterlockedExchangeAdd((volatile signed __int32 *)&qword_18003DD5C, 0xFFFFFFFF);
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        33,
        WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids,
        (unsigned int)(v22 - 1));
      v23 = WPP_GLOBAL_Control;
    }
    if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 17) & 0x800) != 0 )
      WPP_SF_D(v23[7], 69, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x180003c80  mov     [rsp+arg_8], rbx
0x180003c85  mov     [rsp+arg_10], rbp
0x180003c8a  push    rsi
0x180003c8b  push    rdi
0x180003c8c  push    r12
0x180003c8e  push    r14
0x180003c90  push    r15
0x180003c92  sub     rsp, 40h
0x180003c96  mov     r15, r9
0x180003c99  mov     dword ptr [rsp+68h+var_38], 0
0x180003ca1  mov     r14d, r8d
0x180003ca4  mov     rdi, rdx
0x180003ca7  mov     ebx, ecx
0x180003ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cb0  lea     rbp, WPP_GLOBAL_Control
0x180003cb7  cmp     rcx, rbp
0x180003cba  jz      short loc_180003D36
0x180003cbc  test    dword ptr [rcx+44h], 800h
0x180003cc3  jz      short loc_180003CE1
0x180003cc5  mov     rcx, [rcx+38h]
0x180003cc9  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180003cd0  mov     edx, 3Ch ; '<'
0x180003cd5  call    WPP_SF_
0x180003cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ce1  cmp     rcx, rbp
0x180003ce4  jz      short loc_180003D36
0x180003ce6  test    dword ptr [rcx+44h], 100h
0x180003ced  jz      short loc_180003D0B
0x180003cef  mov     rcx, [rcx+38h]
0x180003cf3  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180003cfa  mov     edx, 3Dh ; '='
0x180003cff  call    WPP_SF_
0x180003d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d0b  cmp     rcx, rbp
0x180003d0e  jz      short loc_180003D36
0x180003d10  test    dword ptr [rcx+44h], 400h
0x180003d17  jz      short loc_180003D36
0x180003d19  mov     rcx, [rcx+38h]
0x180003d1d  lea     r9, aOnexupdateport_0; "OneXUpdatePortProfile"
0x180003d24  mov     edx, 1Dh
0x180003d29  mov     dword ptr [rsp+68h+var_48], 235h
0x180003d31  call    WPP_SF_sd
0x180003d36  mov     r12d, 1
0x180003d3c  mov     r9d, r12d
0x180003d3f  lock xadd dword ptr cs:qword_18003DD5C, r9d
0x180003d48  inc     r9d
0x180003d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d52  cmp     rcx, rbp
0x180003d55  jz      short loc_180003D7C
0x180003d57  test    dword ptr [rcx+44h], 400h
0x180003d5e  jz      short loc_180003D7C
0x180003d60  mov     rcx, [rcx+38h]
0x180003d64  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180003d6b  mov     edx, 1Eh
0x180003d70  call    WPP_SF_d
0x180003d75  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d7c  cmp     dword ptr cs:qword_18003DD5C+4, 0
0x180003d83  mov     esi, 0FFFFFFFFh
0x180003d88  jnz     short loc_180003DE6
0x180003d8a  cmp     rcx, rbp
0x180003d8d  jz      short loc_180003DB1
0x180003d8f  test    [rcx+44h], r12b
0x180003d93  jz      short loc_180003DB1
0x180003d95  mov     rcx, [rcx+38h]
0x180003d99  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180003da0  mov     edx, 1Fh
0x180003da5  call    WPP_SF_
0x180003daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180003db1  mov     ebx, 15h
0x180003db6  cmp     rcx, rbp
0x180003db9  jz      loc_1800041EF
0x180003dbf  test    [rcx+44h], r12b
0x180003dc3  jz      loc_1800041C4
0x180003dc9  mov     edx, 3Eh ; '>'
0x180003dce  mov     rcx, [rcx+38h]
0x180003dd2  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180003dd9  mov     r9d, ebx
0x180003ddc  call    WPP_SF_d
0x180003de1  jmp     loc_1800041BD
0x180003de6  cmp     ebx, r12d
0x180003de9  jz      short loc_180003E0A
0x180003deb  mov     ebx, 32h ; '2'
0x180003df0  cmp     rcx, rbp
0x180003df3  jz      loc_1800041EF
0x180003df9  test    [rcx+44h], r12b
0x180003dfd  jz      loc_1800041C4
0x180003e03  mov     edx, 3Fh ; '?'
0x180003e08  jmp     short loc_180003DCE
0x180003e0a  test    r15, r15
0x180003e0d  jz      loc_180004198
0x180003e13  test    r14d, r14d
0x180003e16  jz      loc_180004198
0x180003e1c  cmp     rcx, rbp
0x180003e1f  jz      short loc_180003E3F
0x180003e21  test    dword ptr [rcx+44h], 800h
0x180003e28  jz      short loc_180003E3F
0x180003e2a  mov     rcx, [rcx+38h]
0x180003e2e  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180003e35  mov     edx, 39h ; '9'
0x180003e3a  call    WPP_SF_
0x180003e3f  mov     rcx, rdi
0x180003e42  call    PortMgrValidateAndRefPort
0x180003e47  mov     ebx, eax
0x180003e49  test    eax, eax
0x180003e4b  jz      short loc_180003E85
0x180003e4d  xor     r12d, r12d
0x180003e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e57  cmp     rcx, rbp
0x180003e5a  jz      loc_1800040CB
0x180003e60  test    byte ptr [rcx+44h], 1
0x180003e64  jz      short loc_180003EE3
0x180003e66  mov     rcx, [rcx+38h]
0x180003e6a  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180003e71  mov     edx, 3Ah ; ':'
0x180003e76  mov     [rsp+68h+var_48], rdi
0x180003e7b  mov     r9d, eax
0x180003e7e  call    WPP_SF_dq
0x180003e83  jmp     short loc_180003EDC
0x180003e85  lea     rdx, [rdi+0B50h]
0x180003e8c  mov     r9d, 2A4h
0x180003e92  lea     r8, aPortmgrvalidat; "PortMgrValidateRefAndLockPort"
0x180003e99  mov     rcx, rdi
0x180003e9c  call    cs:__imp_AcquireWriteLock
0x180003ea2  cmp     dword ptr [rdi+18h], 0
0x180003ea6  jge     short loc_180003EDC
0x180003ea8  mov     ebx, 6
0x180003ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eb4  cmp     rcx, rbp
0x180003eb7  jz      loc_1800040CB
0x180003ebd  test    [rcx+44h], r12b
0x180003ec1  jz      short loc_180003EE3
0x180003ec3  mov     r9d, [rdi+14h]
0x180003ec7  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180003ece  mov     rcx, [rcx+38h]
0x180003ed2  mov     edx, 3Bh ; ';'
0x180003ed7  call    WPP_SF_d
0x180003edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ee3  cmp     rcx, rbp
0x180003ee6  jz      short loc_180003F10
0x180003ee8  test    dword ptr [rcx+44h], 800h
0x180003eef  jz      short loc_180003F10
0x180003ef1  mov     rcx, [rcx+38h]
0x180003ef5  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180003efc  mov     edx, 3Ch ; '<'
0x180003f01  mov     r9d, ebx
0x180003f04  call    WPP_SF_D
0x180003f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f10  test    ebx, ebx
0x180003f12  jz      short loc_180003F4B
0x180003f14  cmp     rcx, rbp
0x180003f17  jz      loc_1800040CB
0x180003f1d  test    byte ptr [rcx+44h], 1
0x180003f21  jz      loc_1800040CB
0x180003f27  mov     rcx, [rcx+38h]
0x180003f2b  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180003f32  mov     edx, 41h ; 'A'
0x180003f37  mov     r9d, ebx
0x180003f3a  call    WPP_SF_d
0x180003f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f46  jmp     loc_1800040CB
0x180003f4b  mov     r8d, [rdi+0C8h]
0x180003f52  lea     r9, [rsp+68h+var_38]
0x180003f57  mov     [rsp+68h+arg_0], r13
0x180003f5c  mov     rdx, r15
0x180003f5f  mov     r13d, [rdi+14h]
0x180003f63  mov     ecx, r14d
0x180003f66  call    OneXValidateProfile
0x180003f6b  mov     ebx, eax
0x180003f6d  test    eax, eax
0x180003f6f  jz      short loc_180003F99
0x180003f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f78  cmp     rcx, rbp
0x180003f7b  jz      loc_1800040C6
0x180003f81  test    byte ptr [rcx+44h], 1
0x180003f85  jz      loc_1800040C6
0x180003f8b  mov     edx, 42h ; 'B'
0x180003f90  mov     dword ptr [rsp+68h+var_48], eax
0x180003f94  jmp     loc_1800040AC
0x180003f99  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fa0  cmp     rcx, rbp
0x180003fa3  jz      short loc_180003FD2
0x180003fa5  test    dword ptr [rcx+44h], 100h
0x180003fac  jz      short loc_180003FD2
0x180003fae  mov     rcx, [rcx+38h]
0x180003fb2  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180003fb9  mov     edx, 43h ; 'C'
0x180003fbe  mov     dword ptr [rsp+68h+var_48], r14d
0x180003fc3  mov     r9d, r13d
0x180003fc6  call    WPP_SF_dd
0x180003fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fd2  mov     ebp, [rdi+14h]
0x180003fd5  lea     rax, WPP_GLOBAL_Control
0x180003fdc  cmp     rcx, rax
0x180003fdf  jz      short loc_180003FFF
0x180003fe1  test    dword ptr [rcx+44h], 800h
0x180003fe8  jz      short loc_180003FFF
0x180003fea  mov     rcx, [rcx+38h]
0x180003fee  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x180003ff5  mov     edx, 27h ; '''
0x180003ffa  call    WPP_SF_
0x180003fff  mov     r9, [rsp+68h+arg_20]
0x180004007  mov     r8, r15
0x18000400a  mov     edx, r14d
0x18000400d  mov     rcx, rdi
0x180004010  call    OneXGenerateConfigChangedEvent
0x180004015  mov     ebx, eax
0x180004017  test    eax, eax
0x180004019  jz      short loc_180004050
0x18000401b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004022  lea     rax, WPP_GLOBAL_Control
0x180004029  cmp     rcx, rax
0x18000402c  jz      short loc_18000408D
0x18000402e  test    byte ptr [rcx+44h], 1
0x180004032  jz      short loc_180004057
0x180004034  mov     rcx, [rcx+38h]
0x180004038  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18000403f  mov     edx, 28h ; '('
0x180004044  mov     dword ptr [rsp+68h+var_48], ebx
0x180004048  mov     r9d, ebp
0x18000404b  call    WPP_SF_dd
0x180004050  mov     rcx, cs:WPP_GLOBAL_Control
0x180004057  lea     rbp, WPP_GLOBAL_Control
0x18000405e  cmp     rcx, rbp
0x180004061  jz      short loc_180004094
0x180004063  test    dword ptr [rcx+44h], 800h
0x18000406a  jz      short loc_180004094
0x18000406c  mov     rcx, [rcx+38h]
0x180004070  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x180004077  mov     edx, 29h ; ')'
0x18000407c  mov     r9d, ebx
0x18000407f  call    WPP_SF_D
0x180004084  mov     rcx, cs:WPP_GLOBAL_Control
0x18000408b  jmp     short loc_180004094
0x18000408d  lea     rbp, WPP_GLOBAL_Control
0x180004094  test    ebx, ebx
0x180004096  jz      short loc_1800040C6
0x180004098  cmp     rcx, rbp
0x18000409b  jz      short loc_1800040C6
0x18000409d  test    byte ptr [rcx+44h], 1
0x1800040a1  jz      short loc_1800040C6
0x1800040a3  mov     edx, 44h ; 'D'
0x1800040a8  mov     dword ptr [rsp+68h+var_48], ebx
0x1800040ac  mov     rcx, [rcx+38h]
0x1800040b0  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x1800040b7  mov     r9d, r13d
0x1800040ba  call    WPP_SF_dd
0x1800040bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040c6  mov     r13, [rsp+68h+arg_0]
0x1800040cb  test    r12d, r12d
0x1800040ce  jz      loc_1800041C4
0x1800040d4  lea     rdx, [rdi+0B50h]
0x1800040db  mov     r9d, 2B6h
0x1800040e1  lea     r8, aPortmgrunlocka; "PortMgrUnlockAndDeRefPort"
0x1800040e8  mov     rcx, rdi
0x1800040eb  call    cs:__imp_ReleaseWriteLock
0x1800040f1  mov     eax, esi
0x1800040f3  mov     [rsp+68h+var_38], rdi
0x1800040f8  lock xadd [rdi+10h], eax
0x1800040fd  cmp     eax, 1
0x180004100  jnz     loc_1800041BD
0x180004106  mov     rcx, [rsp+68h+var_38]
0x18000410b  call    PortMgrDeInitPort
0x180004110  mov     r9d, 253h
0x180004116  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x18000411d  lea     rdx, qword_18003DD98
0x180004124  lea     rcx, g_OneXInfo
0x18000412b  call    cs:__imp_AcquireWriteLock
0x180004131  mov     rax, [rsp+68h+var_38]
0x180004136  mov     r9, [rax]
0x180004139  cmp     [r9+8], rax
0x18000413d  jnz     short loc_180004191
0x18000413f  mov     r8, [rax+8]
0x180004143  cmp     [r8], rax
0x180004146  jnz     short loc_180004191
0x180004148  mov     [r8], r9
0x18000414b  lea     rdx, qword_18003DD98
0x180004152  mov     [r9+8], r8
0x180004156  lea     rcx, g_OneXInfo
0x18000415d  mov     r9d, 255h
0x180004163  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x18000416a  call    cs:__imp_ReleaseWriteLock
0x180004170  lock dec dword ptr cs:qword_18003DD8C+4
0x180004177  lea     rdx, aPortmgrderefer; "PortMgrDereferencePort"
0x18000417e  mov     r8d, 259h
0x180004184  lea     rcx, [rsp+68h+var_38]
0x180004189  call    cs:__imp_FreeMemory
0x18000418f  jmp     short loc_1800041BD
0x180004191  mov     ecx, 3
0x180004196  int     29h; Win8: RtlFailFast(ecx)
0x180004198  mov     ebx, 57h ; 'W'
0x18000419d  cmp     rcx, rbp
0x1800041a0  jz      short loc_1800041EF
0x1800041a2  test    [rcx+44h], r12b
0x1800041a6  jz      short loc_1800041C4
0x1800041a8  mov     rcx, [rcx+38h]
0x1800041ac  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x1800041b3  mov     edx, 40h ; '@'
0x1800041b8  call    WPP_SF_
0x1800041bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041c4  cmp     rcx, rbp
  ... truncated ...
```
