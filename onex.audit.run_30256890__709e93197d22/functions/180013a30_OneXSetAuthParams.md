# OneXSetAuthParams

- ea: `0x180013a30`
- end: `0x180013e3c`
- name: `OneXSetAuthParams`
- size: `1036`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180003120`
- `0x1800037d0`
- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x180013a30`
- `0x1800214f0`
- `0x180023640`
- `0x18002bbf8`
- `0x18002d9a8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180013caa`
- `MobileNetworking!ReleaseWriteLock` at `0x180013d6c`
- `MobileNetworking!ReleaseWriteLock` at `0x180013caa`
- `MobileNetworking!ReleaseWriteLock` at `0x180013d6c`
- `MobileNetworking!AcquireWriteLock` at `0x180013d25`
- `MobileNetworking!AcquireWriteLock` at `0x180013d25`
- `MobileNetworking!FreeMemory` at `0x180013d8b`
- `MobileNetworking!FreeMemory` at `0x180013d8b`

## pseudocode

```c
__int64 __fastcall OneXSetAuthParams(int a1, __int64 a2, unsigned int a3, __int64 a4)
{
  int v4; // esi
  _QWORD *v9; // rcx
  __int64 v10; // r9
  _QWORD *v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // esi
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  _QWORD *v19; // r8
  signed __int32 v20; // edi
  _QWORD *v21; // rcx
  int v23; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v24[8]; // [rsp+38h] [rbp-40h] BYREF

  v4 = 0;
  v23 = 0;
  LODWORD(v24[0]) = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 141, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v9 + 17) & 0x100) != 0 )
      {
        WPP_SF_(v9[7], 142, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x400) != 0 )
        WPP_SF_sd(v9[7], 29, a3, (unsigned int)"OneXSetAuthParams", 47);
    }
  }
  v10 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&qword_18003DD5C);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v10);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !HIDWORD(qword_18003DD5C) )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 1) != 0 )
    {
      WPP_SF_(v11[7], 31, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    v12 = 21;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 1) != 0 )
    {
      v13 = 143;
LABEL_20:
      WPP_SF_d(v11[7], v13, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
LABEL_46:
      v11 = WPP_GLOBAL_Control;
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  if ( a1 == 1 )
  {
    if ( !a4 || a3 < 0x48 )
    {
      v12 = 87;
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 1) != 0 )
      {
        WPP_SF_(v11[7], 145, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    v14 = PortMgrValidateRefAndLockPort(a2, a2, &v23, v24);
    v12 = v14;
    if ( v14 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_41;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 146, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v14);
LABEL_40:
      v11 = WPP_GLOBAL_Control;
LABEL_41:
      v4 = v23;
      if ( !LODWORD(v24[0]) )
        goto LABEL_47;
      ReleaseWriteLock(a2, a2 + 2896, "PortMgrUnlockAndDeRefPort", 694);
      goto LABEL_46;
    }
    v15 = *(_DWORD *)(a2 + 20);
    v16 = ValidateAuthParams(a2, *(unsigned int *)(a2 + 200), a3, a4);
    v12 = v16;
    if ( v16 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_41;
      v17 = 147;
    }
    else
    {
      v16 = OneXSetAuthParamsHelper(a2, a3, a4);
      v12 = v16;
      if ( !v16 )
        goto LABEL_40;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_41;
      v17 = 148;
    }
    WPP_SF_dd(v11[7], v17, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v15, v16);
    goto LABEL_40;
  }
  v12 = 50;
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 1) != 0 )
  {
    v13 = 144;
    goto LABEL_20;
  }
LABEL_47:
  if ( v4 )
  {
    v24[0] = a2;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 16), 0xFFFFFFFF) == 1 )
    {
      PortMgrDeInitPort(v24[0]);
      AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 595);
      v18 = *(_QWORD *)v24[0];
      if ( *(_QWORD *)(*(_QWORD *)v24[0] + 8LL) != v24[0] || (v19 = *(_QWORD **)(v24[0] + 8LL), *v19 != v24[0]) )
        __fastfail(3u);
      *v19 = v18;
      *(_QWORD *)(v18 + 8) = v19;
      ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 597);
      _InterlockedDecrement((_DWORD *)&qword_18003DD8C + 1);
      FreeMemory(v24, "PortMgrDereferencePort", 601);
    }
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x400) != 0 )
    WPP_SF_sd(v11[7], 32, a3, (unsigned int)"OneXSetAuthParams", 77);
  v20 = _InterlockedExchangeAdd((volatile signed __int32 *)&qword_18003DD5C, 0xFFFFFFFF);
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        33,
        WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids,
        (unsigned int)(v20 - 1));
      v21 = WPP_GLOBAL_Control;
    }
    if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 17) & 0x800) != 0 )
      WPP_SF_D(v21[7], 149, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180013a30  push    rbx
0x180013a32  push    rbp
0x180013a33  push    rsi
0x180013a34  push    rdi
0x180013a35  push    r14
0x180013a37  push    r15
0x180013a39  sub     rsp, 48h
0x180013a3d  xor     esi, esi
0x180013a3f  mov     rdi, r9
0x180013a42  mov     [rsp+78h+var_48], esi
0x180013a46  mov     r14d, r8d
0x180013a49  mov     dword ptr [rsp+78h+var_40], esi
0x180013a4d  mov     rbp, rdx
0x180013a50  mov     ebx, ecx
0x180013a52  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a59  lea     r15, WPP_GLOBAL_Control
0x180013a60  cmp     rcx, r15
0x180013a63  jz      short loc_180013ADF
0x180013a65  test    dword ptr [rcx+44h], 800h
0x180013a6c  jz      short loc_180013A8A
0x180013a6e  mov     rcx, [rcx+38h]
0x180013a72  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180013a79  mov     edx, 8Dh
0x180013a7e  call    WPP_SF_
0x180013a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a8a  cmp     rcx, r15
0x180013a8d  jz      short loc_180013ADF
0x180013a8f  test    dword ptr [rcx+44h], 100h
0x180013a96  jz      short loc_180013AB4
0x180013a98  mov     rcx, [rcx+38h]
0x180013a9c  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180013aa3  mov     edx, 8Eh
0x180013aa8  call    WPP_SF_
0x180013aad  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ab4  cmp     rcx, r15
0x180013ab7  jz      short loc_180013ADF
0x180013ab9  test    dword ptr [rcx+44h], 400h
0x180013ac0  jz      short loc_180013ADF
0x180013ac2  mov     rcx, [rcx+38h]
0x180013ac6  lea     r9, aOnexsetauthpar_0; "OneXSetAuthParams"
0x180013acd  mov     edx, 1Dh
0x180013ad2  mov     [rsp+78h+var_58], 52Fh
0x180013ada  call    WPP_SF_sd
0x180013adf  mov     r9d, 1
0x180013ae5  lock xadd dword ptr cs:qword_18003DD5C, r9d
0x180013aee  inc     r9d
0x180013af1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013af8  cmp     rcx, r15
0x180013afb  jz      short loc_180013B22
0x180013afd  test    dword ptr [rcx+44h], 400h
0x180013b04  jz      short loc_180013B22
0x180013b06  mov     rcx, [rcx+38h]
0x180013b0a  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180013b11  mov     edx, 1Eh
0x180013b16  call    WPP_SF_d
0x180013b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b22  cmp     dword ptr cs:qword_18003DD5C+4, esi
0x180013b28  jnz     short loc_180013B86
0x180013b2a  cmp     rcx, r15
0x180013b2d  jz      short loc_180013B51
0x180013b2f  test    byte ptr [rcx+44h], 1
0x180013b33  jz      short loc_180013B51
0x180013b35  mov     rcx, [rcx+38h]
0x180013b39  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180013b40  mov     edx, 1Fh
0x180013b45  call    WPP_SF_
0x180013b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b51  mov     ebx, 15h
0x180013b56  cmp     rcx, r15
0x180013b59  jz      loc_180013CDE
0x180013b5f  test    byte ptr [rcx+44h], 1
0x180013b63  jz      loc_180013CDE
0x180013b69  mov     edx, 8Fh
0x180013b6e  mov     rcx, [rcx+38h]
0x180013b72  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180013b79  mov     r9d, ebx
0x180013b7c  call    WPP_SF_d
0x180013b81  jmp     loc_180013CD7
0x180013b86  cmp     ebx, 1
0x180013b89  jz      short loc_180013BAA
0x180013b8b  mov     ebx, 32h ; '2'
0x180013b90  cmp     rcx, r15
0x180013b93  jz      loc_180013CDE
0x180013b99  test    byte ptr [rcx+44h], 1
0x180013b9d  jz      loc_180013CDE
0x180013ba3  mov     edx, 90h
0x180013ba8  jmp     short loc_180013B6E
0x180013baa  test    rdi, rdi
0x180013bad  jz      loc_180013CB2
0x180013bb3  cmp     r14d, 48h ; 'H'
0x180013bb7  jb      loc_180013CB2
0x180013bbd  lea     r9, [rsp+78h+var_40]
0x180013bc2  mov     rcx, rbp
0x180013bc5  lea     r8, [rsp+78h+var_48]
0x180013bca  call    PortMgrValidateRefAndLockPort
0x180013bcf  mov     ebx, eax
0x180013bd1  test    eax, eax
0x180013bd3  jz      short loc_180013C09
0x180013bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bdc  cmp     rcx, r15
0x180013bdf  jz      loc_180013C88
0x180013be5  test    byte ptr [rcx+44h], 1
0x180013be9  jz      loc_180013C88
0x180013bef  mov     rcx, [rcx+38h]
0x180013bf3  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180013bfa  mov     edx, 92h
0x180013bff  mov     r9d, eax
0x180013c02  call    WPP_SF_d
0x180013c07  jmp     short loc_180013C81
0x180013c09  mov     edx, [rbp+0C8h]
0x180013c0f  mov     r9, rdi
0x180013c12  mov     esi, [rbp+14h]
0x180013c15  mov     r8d, r14d
0x180013c18  mov     rcx, rbp
0x180013c1b  call    ValidateAuthParams
0x180013c20  mov     ebx, eax
0x180013c22  test    eax, eax
0x180013c24  jz      short loc_180013C3F
0x180013c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c2d  cmp     rcx, r15
0x180013c30  jz      short loc_180013C88
0x180013c32  test    byte ptr [rcx+44h], 1
0x180013c36  jz      short loc_180013C88
0x180013c38  mov     edx, 93h
0x180013c3d  jmp     short loc_180013C6A
0x180013c3f  mov     r8, rdi
0x180013c42  mov     edx, r14d
0x180013c45  mov     rcx, rbp
0x180013c48  call    OneXSetAuthParamsHelper
0x180013c4d  mov     ebx, eax
0x180013c4f  test    eax, eax
0x180013c51  jz      short loc_180013C81
0x180013c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c5a  cmp     rcx, r15
0x180013c5d  jz      short loc_180013C88
0x180013c5f  test    byte ptr [rcx+44h], 1
0x180013c63  jz      short loc_180013C88
0x180013c65  mov     edx, 94h
0x180013c6a  mov     rcx, [rcx+38h]
0x180013c6e  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180013c75  mov     r9d, esi
0x180013c78  mov     [rsp+78h+var_58], eax
0x180013c7c  call    WPP_SF_dd
0x180013c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c88  cmp     dword ptr [rsp+78h+var_40], 0
0x180013c8d  mov     esi, [rsp+78h+var_48]
0x180013c91  jz      short loc_180013CDE
0x180013c93  lea     rdx, [rbp+0B50h]
0x180013c9a  mov     r9d, 2B6h
0x180013ca0  lea     r8, aPortmgrunlocka; "PortMgrUnlockAndDeRefPort"
0x180013ca7  mov     rcx, rbp
0x180013caa  call    cs:__imp_ReleaseWriteLock
0x180013cb0  jmp     short loc_180013CD7
0x180013cb2  mov     ebx, 57h ; 'W'
0x180013cb7  cmp     rcx, r15
0x180013cba  jz      short loc_180013CDE
0x180013cbc  test    byte ptr [rcx+44h], 1
0x180013cc0  jz      short loc_180013CDE
0x180013cc2  mov     rcx, [rcx+38h]
0x180013cc6  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180013ccd  mov     edx, 91h
0x180013cd2  call    WPP_SF_
0x180013cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cde  mov     edi, 0FFFFFFFFh
0x180013ce3  test    esi, esi
0x180013ce5  jz      loc_180013D98
0x180013ceb  mov     [rsp+78h+var_40], rbp
0x180013cf0  mov     eax, edi
0x180013cf2  lock xadd [rbp+10h], eax
0x180013cf7  cmp     eax, 1
0x180013cfa  jnz     loc_180013D91
0x180013d00  mov     rcx, [rsp+78h+var_40]
0x180013d05  call    PortMgrDeInitPort
0x180013d0a  mov     r9d, 253h
0x180013d10  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x180013d17  lea     rdx, qword_18003DD98
0x180013d1e  lea     rcx, g_OneXInfo
0x180013d25  call    cs:__imp_AcquireWriteLock
0x180013d2b  mov     rax, [rsp+78h+var_40]
0x180013d30  mov     r9, [rax]
0x180013d33  cmp     [r9+8], rax
0x180013d37  jnz     loc_180013E35
0x180013d3d  mov     r8, [rax+8]
0x180013d41  cmp     [r8], rax
0x180013d44  jnz     loc_180013E35
0x180013d4a  mov     [r8], r9
0x180013d4d  lea     rdx, qword_18003DD98
0x180013d54  mov     [r9+8], r8
0x180013d58  lea     rcx, g_OneXInfo
0x180013d5f  mov     r9d, 255h
0x180013d65  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x180013d6c  call    cs:__imp_ReleaseWriteLock
0x180013d72  lock dec dword ptr cs:qword_18003DD8C+4
0x180013d79  lea     rdx, aPortmgrderefer; "PortMgrDereferencePort"
0x180013d80  mov     r8d, 259h
0x180013d86  lea     rcx, [rsp+78h+var_40]
0x180013d8b  call    cs:__imp_FreeMemory
0x180013d91  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d98  cmp     rcx, r15
0x180013d9b  jz      short loc_180013DC3
0x180013d9d  test    dword ptr [rcx+44h], 400h
0x180013da4  jz      short loc_180013DC3
0x180013da6  mov     rcx, [rcx+38h]
0x180013daa  lea     r9, aOnexsetauthpar_0; "OneXSetAuthParams"
0x180013db1  mov     edx, 20h ; ' '
0x180013db6  mov     [rsp+78h+var_58], 54Dh
0x180013dbe  call    WPP_SF_sd
0x180013dc3  lock xadd dword ptr cs:qword_18003DD5C, edi
0x180013dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180013dd2  cmp     rcx, r15
0x180013dd5  jz      short loc_180013E26
0x180013dd7  test    dword ptr [rcx+44h], 400h
0x180013dde  jz      short loc_180013E00
0x180013de0  mov     rcx, [rcx+38h]
0x180013de4  lea     r9d, [rdi-1]
0x180013de8  mov     edx, 21h ; '!'
0x180013ded  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180013df4  call    WPP_SF_d
0x180013df9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e00  cmp     rcx, r15
0x180013e03  jz      short loc_180013E26
0x180013e05  test    dword ptr [rcx+44h], 800h
0x180013e0c  jz      short loc_180013E26
0x180013e0e  mov     rcx, [rcx+38h]
0x180013e12  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180013e19  mov     edx, 95h
0x180013e1e  mov     r9d, ebx
0x180013e21  call    WPP_SF_D
0x180013e26  mov     eax, ebx
0x180013e28  add     rsp, 48h
0x180013e2c  pop     r15
0x180013e2e  pop     r14
0x180013e30  pop     rdi
0x180013e31  pop     rsi
0x180013e32  pop     rbp
0x180013e33  pop     rbx
0x180013e34  retn
0x180013e35  mov     ecx, 3
0x180013e3a  int     29h; Win8: RtlFailFast(ecx)
```
