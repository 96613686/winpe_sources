# OneXSetRuntimeState

- ea: `0x1800170c0`
- end: `0x18001744d`
- name: `OneXSetRuntimeState`
- size: `909`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800037d0`
- `0x180005440`
- `0x180010ae0`
- `0x180010b20`
- `0x1800170c0`
- `0x1800214f0`
- `0x180023640`
- `0x18002d9a8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800172d7`
- `MobileNetworking!ReleaseWriteLock` at `0x18001737c`
- `MobileNetworking!ReleaseWriteLock` at `0x1800172d7`
- `MobileNetworking!ReleaseWriteLock` at `0x18001737c`
- `MobileNetworking!AcquireWriteLock` at `0x180017335`
- `MobileNetworking!AcquireWriteLock` at `0x180017335`
- `MobileNetworking!FreeMemory` at `0x18001739b`
- `MobileNetworking!FreeMemory` at `0x18001739b`

## pseudocode

```c
__int64 __fastcall OneXSetRuntimeState(int a1, __int64 a2, __int64 a3)
{
  int v4; // edi
  _QWORD *v7; // rcx
  __int64 v8; // r9
  _QWORD *v9; // rcx
  unsigned int v10; // ebp
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  _QWORD *v15; // r8
  signed __int32 v16; // ebx
  _QWORD *v17; // rcx
  int v19; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v20[4]; // [rsp+38h] [rbp-20h] BYREF

  v4 = 0;
  v19 = 0;
  LODWORD(v20[0]) = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 215, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v7 + 17) & 0x100) != 0 )
      {
        WPP_SF_(v7[7], 216, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x400) != 0 )
        WPP_SF_sd(v7[7], 29, a3, (unsigned int)"OneXSetRuntimeState", 197);
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
      v11 = 217;
LABEL_20:
      WPP_SF_d(v9[7], v11, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v10);
LABEL_37:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  if ( a1 == 1 )
  {
    v12 = PortMgrValidateRefAndLockPort(a2, a2, &v19, v20);
    v10 = v12;
    if ( v12 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_35;
      v13 = 219;
    }
    else
    {
      v12 = OneXSetRuntimeStateHelper(a2, a3);
      v10 = v12;
      if ( !v12 )
      {
LABEL_34:
        v9 = WPP_GLOBAL_Control;
LABEL_35:
        v4 = v19;
        if ( !LODWORD(v20[0]) )
          goto LABEL_38;
        ReleaseWriteLock(a2, a2 + 2896, "PortMgrUnlockAndDeRefPort", 694);
        goto LABEL_37;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_35;
      v13 = 220;
    }
    WPP_SF_d(v9[7], v13, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
    goto LABEL_34;
  }
  v10 = 50;
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
  {
    v11 = 218;
    goto LABEL_20;
  }
LABEL_38:
  if ( v4 )
  {
    v20[0] = a2;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 16), 0xFFFFFFFF) == 1 )
    {
      PortMgrDeInitPort(v20[0]);
      AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 595);
      v14 = *(_QWORD *)v20[0];
      if ( *(_QWORD *)(*(_QWORD *)v20[0] + 8LL) != v20[0] || (v15 = *(_QWORD **)(v20[0] + 8LL), *v15 != v20[0]) )
        __fastfail(3u);
      *v15 = v14;
      *(_QWORD *)(v14 + 8) = v15;
      ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 597);
      _InterlockedDecrement((_DWORD *)&qword_18003DD8C + 1);
      FreeMemory(v20, "PortMgrDereferencePort", 601);
    }
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x400) != 0 )
    WPP_SF_sd(v9[7], 32, a3, (unsigned int)"OneXSetRuntimeState", 216);
  v16 = _InterlockedExchangeAdd((volatile signed __int32 *)&qword_18003DD5C, 0xFFFFFFFF);
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        33,
        WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids,
        (unsigned int)(v16 - 1));
      v17 = WPP_GLOBAL_Control;
    }
    if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 17) & 0x800) != 0 )
      WPP_SF_D(v17[7], 221, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x1800170c0  push    rbx
0x1800170c2  push    rsi
0x1800170c3  push    r15
0x1800170c5  sub     rsp, 40h
0x1800170c9  mov     [rsp+58h+arg_8], rdi
0x1800170ce  mov     rsi, rdx
0x1800170d1  xor     edi, edi
0x1800170d3  mov     [rsp+58h+arg_10], r14
0x1800170d8  mov     [rsp+58h+var_28], edi
0x1800170dc  mov     r14, r8
0x1800170df  mov     dword ptr [rsp+58h+var_20], edi
0x1800170e3  mov     ebx, ecx
0x1800170e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170ec  lea     r15, WPP_GLOBAL_Control
0x1800170f3  cmp     rcx, r15
0x1800170f6  jz      short loc_180017172
0x1800170f8  test    dword ptr [rcx+44h], 800h
0x1800170ff  jz      short loc_18001711D
0x180017101  mov     rcx, [rcx+38h]
0x180017105  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001710c  mov     edx, 0D7h
0x180017111  call    WPP_SF_
0x180017116  mov     rcx, cs:WPP_GLOBAL_Control
0x18001711d  cmp     rcx, r15
0x180017120  jz      short loc_180017172
0x180017122  test    dword ptr [rcx+44h], 100h
0x180017129  jz      short loc_180017147
0x18001712b  mov     rcx, [rcx+38h]
0x18001712f  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180017136  mov     edx, 0D8h
0x18001713b  call    WPP_SF_
0x180017140  mov     rcx, cs:WPP_GLOBAL_Control
0x180017147  cmp     rcx, r15
0x18001714a  jz      short loc_180017172
0x18001714c  test    dword ptr [rcx+44h], 400h
0x180017153  jz      short loc_180017172
0x180017155  mov     rcx, [rcx+38h]
0x180017159  lea     r9, aOnexsetruntime_0; "OneXSetRuntimeState"
0x180017160  mov     edx, 1Dh
0x180017165  mov     [rsp+58h+var_38], 8C5h
0x18001716d  call    WPP_SF_sd
0x180017172  mov     r9d, 1
0x180017178  lock xadd dword ptr cs:qword_18003DD5C, r9d
0x180017181  inc     r9d
0x180017184  mov     rcx, cs:WPP_GLOBAL_Control
0x18001718b  cmp     rcx, r15
0x18001718e  jz      short loc_1800171B5
0x180017190  test    dword ptr [rcx+44h], 400h
0x180017197  jz      short loc_1800171B5
0x180017199  mov     rcx, [rcx+38h]
0x18001719d  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x1800171a4  mov     edx, 1Eh
0x1800171a9  call    WPP_SF_d
0x1800171ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171b5  cmp     dword ptr cs:qword_18003DD5C+4, edi
0x1800171bb  mov     [rsp+58h+arg_0], rbp
0x1800171c0  jnz     short loc_18001721E
0x1800171c2  cmp     rcx, r15
0x1800171c5  jz      short loc_1800171E9
0x1800171c7  test    byte ptr [rcx+44h], 1
0x1800171cb  jz      short loc_1800171E9
0x1800171cd  mov     rcx, [rcx+38h]
0x1800171d1  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x1800171d8  mov     edx, 1Fh
0x1800171dd  call    WPP_SF_
0x1800171e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171e9  mov     ebp, 15h
0x1800171ee  cmp     rcx, r15
0x1800171f1  jz      loc_1800172E4
0x1800171f7  test    byte ptr [rcx+44h], 1
0x1800171fb  jz      loc_1800172E4
0x180017201  mov     edx, 0D9h
0x180017206  mov     rcx, [rcx+38h]
0x18001720a  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180017211  mov     r9d, ebp
0x180017214  call    WPP_SF_d
0x180017219  jmp     loc_1800172DD
0x18001721e  cmp     ebx, 1
0x180017221  jz      short loc_180017242
0x180017223  mov     ebp, 32h ; '2'
0x180017228  cmp     rcx, r15
0x18001722b  jz      loc_1800172E4
0x180017231  test    byte ptr [rcx+44h], 1
0x180017235  jz      loc_1800172E4
0x18001723b  mov     edx, 0DAh
0x180017240  jmp     short loc_180017206
0x180017242  lea     r9, [rsp+58h+var_20]
0x180017247  mov     rcx, rsi
0x18001724a  lea     r8, [rsp+58h+var_28]
0x18001724f  call    PortMgrValidateRefAndLockPort
0x180017254  mov     ebp, eax
0x180017256  test    eax, eax
0x180017258  jz      short loc_180017273
0x18001725a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017261  cmp     rcx, r15
0x180017264  jz      short loc_1800172B5
0x180017266  test    byte ptr [rcx+44h], 1
0x18001726a  jz      short loc_1800172B5
0x18001726c  mov     edx, 0DBh
0x180017271  jmp     short loc_18001729B
0x180017273  mov     rdx, r14
0x180017276  mov     rcx, rsi
0x180017279  call    OneXSetRuntimeStateHelper
0x18001727e  mov     ebp, eax
0x180017280  test    eax, eax
0x180017282  jz      short loc_1800172AE
0x180017284  mov     rcx, cs:WPP_GLOBAL_Control
0x18001728b  cmp     rcx, r15
0x18001728e  jz      short loc_1800172B5
0x180017290  test    byte ptr [rcx+44h], 1
0x180017294  jz      short loc_1800172B5
0x180017296  mov     edx, 0DCh
0x18001729b  mov     rcx, [rcx+38h]
0x18001729f  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x1800172a6  mov     r9d, eax
0x1800172a9  call    WPP_SF_d
0x1800172ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172b5  cmp     dword ptr [rsp+58h+var_20], 0
0x1800172ba  mov     edi, [rsp+58h+var_28]
0x1800172be  jz      short loc_1800172E4
0x1800172c0  lea     rdx, [rsi+0B50h]
0x1800172c7  mov     r9d, 2B6h
0x1800172cd  lea     r8, aPortmgrunlocka; "PortMgrUnlockAndDeRefPort"
0x1800172d4  mov     rcx, rsi
0x1800172d7  call    cs:__imp_ReleaseWriteLock
0x1800172dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172e4  mov     r14, [rsp+58h+arg_10]
0x1800172e9  test    edi, edi
0x1800172eb  mov     rdi, [rsp+58h+arg_8]
0x1800172f0  mov     ebx, 0FFFFFFFFh
0x1800172f5  jz      loc_1800173A8
0x1800172fb  mov     [rsp+58h+var_20], rsi
0x180017300  mov     eax, ebx
0x180017302  lock xadd [rsi+10h], eax
0x180017307  cmp     eax, 1
0x18001730a  jnz     loc_1800173A1
0x180017310  mov     rcx, [rsp+58h+var_20]
0x180017315  call    PortMgrDeInitPort
0x18001731a  mov     r9d, 253h
0x180017320  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x180017327  lea     rdx, qword_18003DD98
0x18001732e  lea     rcx, g_OneXInfo
0x180017335  call    cs:__imp_AcquireWriteLock
0x18001733b  mov     rax, [rsp+58h+var_20]
0x180017340  mov     r9, [rax]
0x180017343  cmp     [r9+8], rax
0x180017347  jnz     loc_180017446
0x18001734d  mov     r8, [rax+8]
0x180017351  cmp     [r8], rax
0x180017354  jnz     loc_180017446
0x18001735a  mov     [r8], r9
0x18001735d  lea     rdx, qword_18003DD98
0x180017364  mov     [r9+8], r8
0x180017368  lea     rcx, g_OneXInfo
0x18001736f  mov     r9d, 255h
0x180017375  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x18001737c  call    cs:__imp_ReleaseWriteLock
0x180017382  lock dec dword ptr cs:qword_18003DD8C+4
0x180017389  lea     rdx, aPortmgrderefer; "PortMgrDereferencePort"
0x180017390  mov     r8d, 259h
0x180017396  lea     rcx, [rsp+58h+var_20]
0x18001739b  call    cs:__imp_FreeMemory
0x1800173a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173a8  cmp     rcx, r15
0x1800173ab  jz      short loc_1800173D3
0x1800173ad  test    dword ptr [rcx+44h], 400h
0x1800173b4  jz      short loc_1800173D3
0x1800173b6  mov     rcx, [rcx+38h]
0x1800173ba  lea     r9, aOnexsetruntime_0; "OneXSetRuntimeState"
0x1800173c1  mov     edx, 20h ; ' '
0x1800173c6  mov     [rsp+58h+var_38], 8D8h
0x1800173ce  call    WPP_SF_sd
0x1800173d3  lock xadd dword ptr cs:qword_18003DD5C, ebx
0x1800173db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173e2  cmp     rcx, r15
0x1800173e5  jz      short loc_180017436
0x1800173e7  test    dword ptr [rcx+44h], 400h
0x1800173ee  jz      short loc_180017410
0x1800173f0  mov     rcx, [rcx+38h]
0x1800173f4  lea     r9d, [rbx-1]
0x1800173f8  mov     edx, 21h ; '!'
0x1800173fd  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180017404  call    WPP_SF_d
0x180017409  mov     rcx, cs:WPP_GLOBAL_Control
0x180017410  cmp     rcx, r15
0x180017413  jz      short loc_180017436
0x180017415  test    dword ptr [rcx+44h], 800h
0x18001741c  jz      short loc_180017436
0x18001741e  mov     rcx, [rcx+38h]
0x180017422  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180017429  mov     edx, 0DDh
0x18001742e  mov     r9d, ebp
0x180017431  call    WPP_SF_D
0x180017436  mov     eax, ebp
0x180017438  mov     rbp, [rsp+58h+arg_0]
0x18001743d  add     rsp, 40h
0x180017441  pop     r15
0x180017443  pop     rsi
0x180017444  pop     rbx
0x180017445  retn
0x180017446  mov     ecx, 3
0x18001744b  int     29h; Win8: RtlFailFast(ecx)
```
