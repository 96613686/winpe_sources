# OneXForceAuthenticatedState

- ea: `0x180004780`
- end: `0x180004b2c`
- name: `OneXForceAuthenticatedState`
- size: `940`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800037d0`
- `0x180004780`
- `0x180005440`
- `0x180007f60`
- `0x18000d8d0`
- `0x180010ae0`
- `0x1800214f0`
- `0x180023640`
- `0x18002d9a8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800049b6`
- `MobileNetworking!ReleaseWriteLock` at `0x180004a5b`
- `MobileNetworking!ReleaseWriteLock` at `0x1800049b6`
- `MobileNetworking!ReleaseWriteLock` at `0x180004a5b`
- `MobileNetworking!AcquireWriteLock` at `0x180004a14`
- `MobileNetworking!AcquireWriteLock` at `0x180004a14`
- `MobileNetworking!FreeMemory` at `0x180004a7a`
- `MobileNetworking!FreeMemory` at `0x180004a7a`

## pseudocode

```c
__int64 __fastcall OneXForceAuthenticatedState(int a1, __int64 a2, __int64 a3)
{
  int v4; // esi
  _QWORD *v7; // rcx
  __int64 v8; // r9
  _QWORD *v9; // rcx
  unsigned int v10; // edi
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  __int64 v15; // r9
  _QWORD *v16; // r8
  signed __int32 v17; // ebx
  _QWORD *v18; // rcx
  int v20; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v21[4]; // [rsp+38h] [rbp-20h] BYREF

  v4 = 0;
  v20 = 0;
  LODWORD(v21[0]) = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 150, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v7 + 17) & 0x100) != 0 )
      {
        WPP_SF_(v7[7], 151, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x400) != 0 )
        WPP_SF_sd(v7[7], 29, a3, (unsigned int)"OneXForceAuthenticatedState", 120);
    }
  }
  v8 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&qword_18003DD5C);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v8);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !HIDWORD(qword_18003DD5C) )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
    {
      WPP_SF_(v9[7], 31, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    v10 = 21;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
    {
      v11 = 152;
LABEL_20:
      WPP_SF_d(v9[7], v11, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v10);
LABEL_36:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  if ( a1 == 1 )
  {
    v12 = PortMgrValidateRefAndLockPort(a3, a2, &v20, v21);
    v10 = v12;
    if ( v12 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_34;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 154, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
    }
    else
    {
      v13 = *(_DWORD *)(a3 + 20);
      v14 = OneXGeneratePortCookieEvent(a3, 3, a2);
      v10 = v14;
      if ( v14 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_34;
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 155, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v13, v14);
      }
    }
    v9 = WPP_GLOBAL_Control;
LABEL_34:
    v4 = v20;
    if ( !LODWORD(v21[0]) )
      goto LABEL_37;
    ReleaseWriteLock(a3, a3 + 2896, "PortMgrUnlockAndDeRefPort", 694);
    goto LABEL_36;
  }
  v10 = 50;
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
  {
    v11 = 153;
    goto LABEL_20;
  }
LABEL_37:
  if ( v4 )
  {
    v21[0] = a3;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 16), 0xFFFFFFFF) == 1 )
    {
      PortMgrDeInitPort(v21[0]);
      AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 595);
      v15 = *(_QWORD *)v21[0];
      if ( *(_QWORD *)(*(_QWORD *)v21[0] + 8LL) != v21[0] || (v16 = *(_QWORD **)(v21[0] + 8LL), *v16 != v21[0]) )
        __fastfail(3u);
      *v16 = v15;
      *(_QWORD *)(v15 + 8) = v16;
      ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 597);
      _InterlockedDecrement((_DWORD *)&qword_18003DD8C + 1);
      FreeMemory(v21, "PortMgrDereferencePort", 601);
    }
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x400) != 0 )
    WPP_SF_sd(v9[7], 32, a3, (unsigned int)"OneXForceAuthenticatedState", 143);
  v17 = _InterlockedExchangeAdd((volatile signed __int32 *)&qword_18003DD5C, 0xFFFFFFFF);
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        33,
        WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids,
        (unsigned int)(v17 - 1));
      v18 = WPP_GLOBAL_Control;
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 17) & 0x800) != 0 )
      WPP_SF_D(v18[7], 156, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180004780  push    rbx
0x180004782  push    rbp
0x180004783  push    r15
0x180004785  sub     rsp, 40h
0x180004789  mov     [rsp+58h+arg_0], rsi
0x18000478e  mov     rbp, r8
0x180004791  xor     esi, esi
0x180004793  mov     [rsp+58h+arg_10], r14
0x180004798  mov     [rsp+58h+var_28], esi
0x18000479c  mov     r14, rdx
0x18000479f  mov     dword ptr [rsp+58h+var_20], esi
0x1800047a3  mov     ebx, ecx
0x1800047a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047ac  lea     r15, WPP_GLOBAL_Control
0x1800047b3  cmp     rcx, r15
0x1800047b6  jz      short loc_180004832
0x1800047b8  test    dword ptr [rcx+44h], 800h
0x1800047bf  jz      short loc_1800047DD
0x1800047c1  mov     rcx, [rcx+38h]
0x1800047c5  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x1800047cc  mov     edx, 96h
0x1800047d1  call    WPP_SF_
0x1800047d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047dd  cmp     rcx, r15
0x1800047e0  jz      short loc_180004832
0x1800047e2  test    dword ptr [rcx+44h], 100h
0x1800047e9  jz      short loc_180004807
0x1800047eb  mov     rcx, [rcx+38h]
0x1800047ef  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x1800047f6  mov     edx, 97h
0x1800047fb  call    WPP_SF_
0x180004800  mov     rcx, cs:WPP_GLOBAL_Control
0x180004807  cmp     rcx, r15
0x18000480a  jz      short loc_180004832
0x18000480c  test    dword ptr [rcx+44h], 400h
0x180004813  jz      short loc_180004832
0x180004815  mov     rcx, [rcx+38h]
0x180004819  lea     r9, aOnexforceauthe_0; "OneXForceAuthenticatedState"
0x180004820  mov     edx, 1Dh
0x180004825  mov     [rsp+58h+var_38], 578h
0x18000482d  call    WPP_SF_sd
0x180004832  mov     r9d, 1
0x180004838  lock xadd dword ptr cs:qword_18003DD5C, r9d
0x180004841  inc     r9d
0x180004844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000484b  cmp     rcx, r15
0x18000484e  jz      short loc_180004875
0x180004850  test    dword ptr [rcx+44h], 400h
0x180004857  jz      short loc_180004875
0x180004859  mov     rcx, [rcx+38h]
0x18000485d  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180004864  mov     edx, 1Eh
0x180004869  call    WPP_SF_d
0x18000486e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004875  cmp     dword ptr cs:qword_18003DD5C+4, esi
0x18000487b  mov     [rsp+58h+arg_8], rdi
0x180004880  jnz     short loc_1800048DE
0x180004882  cmp     rcx, r15
0x180004885  jz      short loc_1800048A9
0x180004887  test    byte ptr [rcx+44h], 1
0x18000488b  jz      short loc_1800048A9
0x18000488d  mov     rcx, [rcx+38h]
0x180004891  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180004898  mov     edx, 1Fh
0x18000489d  call    WPP_SF_
0x1800048a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048a9  mov     edi, 15h
0x1800048ae  cmp     rcx, r15
0x1800048b1  jz      loc_1800049C3
0x1800048b7  test    byte ptr [rcx+44h], 1
0x1800048bb  jz      loc_1800049C3
0x1800048c1  mov     edx, 98h
0x1800048c6  mov     rcx, [rcx+38h]
0x1800048ca  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x1800048d1  mov     r9d, edi
0x1800048d4  call    WPP_SF_d
0x1800048d9  jmp     loc_1800049BC
0x1800048de  cmp     ebx, 1
0x1800048e1  jz      short loc_180004902
0x1800048e3  mov     edi, 32h ; '2'
0x1800048e8  cmp     rcx, r15
0x1800048eb  jz      loc_1800049C3
0x1800048f1  test    byte ptr [rcx+44h], 1
0x1800048f5  jz      loc_1800049C3
0x1800048fb  mov     edx, 99h
0x180004900  jmp     short loc_1800048C6
0x180004902  lea     r9, [rsp+58h+var_20]
0x180004907  mov     rcx, rbp
0x18000490a  lea     r8, [rsp+58h+var_28]
0x18000490f  call    PortMgrValidateRefAndLockPort
0x180004914  mov     edi, eax
0x180004916  test    eax, eax
0x180004918  jz      short loc_180004946
0x18000491a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004921  cmp     rcx, r15
0x180004924  jz      short loc_180004994
0x180004926  test    byte ptr [rcx+44h], 1
0x18000492a  jz      short loc_180004994
0x18000492c  mov     rcx, [rcx+38h]
0x180004930  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180004937  mov     edx, 9Ah
0x18000493c  mov     r9d, eax
0x18000493f  call    WPP_SF_d
0x180004944  jmp     short loc_18000498D
0x180004946  mov     ebx, [rbp+14h]
0x180004949  mov     r8, r14
0x18000494c  mov     edx, 3
0x180004951  mov     rcx, rbp
0x180004954  call    OneXGeneratePortCookieEvent
0x180004959  mov     edi, eax
0x18000495b  test    eax, eax
0x18000495d  jz      short loc_18000498D
0x18000495f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004966  cmp     rcx, r15
0x180004969  jz      short loc_180004994
0x18000496b  test    byte ptr [rcx+44h], 1
0x18000496f  jz      short loc_180004994
0x180004971  mov     rcx, [rcx+38h]
0x180004975  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18000497c  mov     edx, 9Bh
0x180004981  mov     [rsp+58h+var_38], eax
0x180004985  mov     r9d, ebx
0x180004988  call    WPP_SF_dd
0x18000498d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004994  cmp     dword ptr [rsp+58h+var_20], 0
0x180004999  mov     esi, [rsp+58h+var_28]
0x18000499d  jz      short loc_1800049C3
0x18000499f  lea     rdx, [rbp+0B50h]
0x1800049a6  mov     r9d, 2B6h
0x1800049ac  lea     r8, aPortmgrunlocka; "PortMgrUnlockAndDeRefPort"
0x1800049b3  mov     rcx, rbp
0x1800049b6  call    cs:__imp_ReleaseWriteLock
0x1800049bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049c3  mov     r14, [rsp+58h+arg_10]
0x1800049c8  test    esi, esi
0x1800049ca  mov     rsi, [rsp+58h+arg_0]
0x1800049cf  mov     ebx, 0FFFFFFFFh
0x1800049d4  jz      loc_180004A87
0x1800049da  mov     [rsp+58h+var_20], rbp
0x1800049df  mov     eax, ebx
0x1800049e1  lock xadd [rbp+10h], eax
0x1800049e6  cmp     eax, 1
0x1800049e9  jnz     loc_180004A80
0x1800049ef  mov     rcx, [rsp+58h+var_20]
0x1800049f4  call    PortMgrDeInitPort
0x1800049f9  mov     r9d, 253h
0x1800049ff  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x180004a06  lea     rdx, qword_18003DD98
0x180004a0d  lea     rcx, g_OneXInfo
0x180004a14  call    cs:__imp_AcquireWriteLock
0x180004a1a  mov     rax, [rsp+58h+var_20]
0x180004a1f  mov     r9, [rax]
0x180004a22  cmp     [r9+8], rax
0x180004a26  jnz     loc_180004B25
0x180004a2c  mov     r8, [rax+8]
0x180004a30  cmp     [r8], rax
0x180004a33  jnz     loc_180004B25
0x180004a39  mov     [r8], r9
0x180004a3c  lea     rdx, qword_18003DD98
0x180004a43  mov     [r9+8], r8
0x180004a47  lea     rcx, g_OneXInfo
0x180004a4e  mov     r9d, 255h
0x180004a54  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x180004a5b  call    cs:__imp_ReleaseWriteLock
0x180004a61  lock dec dword ptr cs:qword_18003DD8C+4
0x180004a68  lea     rdx, aPortmgrderefer; "PortMgrDereferencePort"
0x180004a6f  mov     r8d, 259h
0x180004a75  lea     rcx, [rsp+58h+var_20]
0x180004a7a  call    cs:__imp_FreeMemory
0x180004a80  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a87  cmp     rcx, r15
0x180004a8a  jz      short loc_180004AB2
0x180004a8c  test    dword ptr [rcx+44h], 400h
0x180004a93  jz      short loc_180004AB2
0x180004a95  mov     rcx, [rcx+38h]
0x180004a99  lea     r9, aOnexforceauthe_0; "OneXForceAuthenticatedState"
0x180004aa0  mov     edx, 20h ; ' '
0x180004aa5  mov     [rsp+58h+var_38], 58Fh
0x180004aad  call    WPP_SF_sd
0x180004ab2  lock xadd dword ptr cs:qword_18003DD5C, ebx
0x180004aba  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ac1  cmp     rcx, r15
0x180004ac4  jz      short loc_180004B15
0x180004ac6  test    dword ptr [rcx+44h], 400h
0x180004acd  jz      short loc_180004AEF
0x180004acf  mov     rcx, [rcx+38h]
0x180004ad3  lea     r9d, [rbx-1]
0x180004ad7  mov     edx, 21h ; '!'
0x180004adc  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180004ae3  call    WPP_SF_d
0x180004ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180004aef  cmp     rcx, r15
0x180004af2  jz      short loc_180004B15
0x180004af4  test    dword ptr [rcx+44h], 800h
0x180004afb  jz      short loc_180004B15
0x180004afd  mov     rcx, [rcx+38h]
0x180004b01  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180004b08  mov     edx, 9Ch
0x180004b0d  mov     r9d, edi
0x180004b10  call    WPP_SF_D
0x180004b15  mov     eax, edi
0x180004b17  mov     rdi, [rsp+58h+arg_8]
0x180004b1c  add     rsp, 40h
0x180004b20  pop     r15
0x180004b22  pop     rbp
0x180004b23  pop     rbx
0x180004b24  retn
0x180004b25  mov     ecx, 3
0x180004b2a  int     29h; Win8: RtlFailFast(ecx)
```
