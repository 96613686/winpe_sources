# mciDriverEntry(_MCIGRAPHIC *,uint,uint,ulong,tagMCI_GENERIC_PARMS *)

- ea: `0x18000485c`
- end: `0x180004dd9`
- name: `?mciDriverEntry@@YA_KPEAU_MCIGRAPHIC@@IIKPEAUtagMCI_GENERIC_PARMS@@@Z`
- size: `1405`
- prototype: `__int64 __fastcall(HWND *, LPARAM lParam, unsigned __int64, unsigned int, struct MCI_DGV_UPDATE_PARMS *)`
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update`

## callers

- `0x1800044b0`

## callees

- `0x180001e7c`
- `0x180002b00`
- `0x180002b78`
- `0x180003074`
- `0x180003408`
- `0x180003604`
- `0x180003b5c`
- `0x18000443c`
- `0x180004614`
- `0x18000485c`
- `0x180004de0`
- `0x180004e58`
- `0x180004f9c`
- `0x180004fdc`
- `0x1800050c0`
- `0x180005268`
- `0x180005384`
- `0x180005634`
- `0x180005804`
- `0x180005934`
- `0x180006088`
- `0x18000617c`
- `0x180006230`
- `0x1800062f8`
- `0x180007010`

## import_xrefs

- `USER32!PostMessageW` at `0x180004da1`
- `USER32!PostMessageW` at `0x180004da1`
- `USER32!IsWindowVisible` at `0x180004c6b`
- `USER32!IsWindowVisible` at `0x180004c6b`
- `USER32!SetWindowPos` at `0x180004c96`
- `USER32!SetWindowPos` at `0x180004c96`
- `WINMM!mciSetDriverData` at `0x180004a65`
- `WINMM!mciSetDriverData` at `0x180004a65`

## pseudocode

```c
__int64 __fastcall mciDriverEntry(
        HWND *a1,
        LPARAM lParam,
        unsigned __int64 a3,
        unsigned int a4,
        struct MCI_DGV_UPDATE_PARMS *a5)
{
  struct tagMCI_GENERIC_PARMS *v5; // r14
  LPARAM v6; // r15
  HWND *v8; // rdi
  int v10; // r12d
  int v11; // r13d
  unsigned int DevCaps; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // ecx
  int dwCallback; // ebx
  unsigned int v17; // r8d
  unsigned __int64 v18; // r9
  unsigned int dwCallback_high; // ebx
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // eax
  int v23; // eax
  HWND v24; // rcx
  int v25; // ebx
  int v26; // eax
  BOOL v27; // eax
  unsigned int cy; // [rsp+28h] [rbp-60h]
  HWND *v29; // [rsp+90h] [rbp+8h] BYREF

  v29 = a1;
  v5 = (struct tagMCI_GENERIC_PARMS *)a5;
  v6 = (unsigned int)lParam;
  v8 = a1;
  if ( !a5 && (a4 & 1) != 0 )
    return 273;
  if ( !a1 )
    return mciSpecial((unsigned int)lParam);
  v10 = 0;
  if ( *((_DWORD *)a1 + 4) )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    *((_DWORD *)a1 + 4) = a3;
  }
  if ( (unsigned int)a3 > 0x830 )
  {
    if ( (unsigned int)a3 > 0x870 )
    {
      switch ( (_DWORD)a3 )
      {
        case 0x871:
        case 0x872:
          goto LABEL_105;
        case 0x873:
          DevCaps = GraphicSetAudio((struct _MCIGRAPHIC *)a1, a4);
          goto LABEL_21;
        case 0x875:
          goto LABEL_38;
        case 0x876:
          DevCaps = GraphicSetVideo((struct _MCIGRAPHIC *)a1);
          goto LABEL_21;
      }
      v23 = a3 - 2167;
      if ( (_DWORD)a3 == 2167 )
        goto LABEL_105;
      goto LABEL_100;
    }
    if ( (_DWORD)a3 == 2160 )
      goto LABEL_105;
    if ( (unsigned int)a3 <= 0x850 )
    {
      if ( (_DWORD)a3 == 2128 )
        goto LABEL_105;
      if ( (_DWORD)a3 != 2112 )
      {
        if ( (_DWORD)a3 == 2113 )
        {
          DevCaps = GraphicWindow((struct _MCIGRAPHIC *)a1);
          goto LABEL_21;
        }
        if ( (_DWORD)a3 == 2114 )
        {
          DevCaps = GraphicPut((struct _MCIGRAPHIC *)a1);
          goto LABEL_21;
        }
        v23 = a3 - 2115;
        if ( (_DWORD)a3 == 2115 )
        {
          DevCaps = GraphicWhere(a1, a4, v5);
          goto LABEL_21;
        }
LABEL_100:
        v26 = v23 - 1;
        if ( !v26 )
          goto LABEL_105;
        goto LABEL_101;
      }
      DevCaps = 0;
      if ( (a4 & 0x20) != 0 )
        goto LABEL_21;
      v24 = a1[22];
      v25 = 0;
      LOBYTE(DevCaps) = (a4 & 0x20000) != 0;
      *((_DWORD *)v8 + 14) = DevCaps;
      if ( v24 )
      {
        v25 = (*(__int64 (__fastcall **)(HWND, _QWORD))(*(_QWORD *)v24 + 136LL))(
                v24,
                (unsigned int)-((a4 & 0x20000) != 0));
        (*(void (__fastcall **)(HWND, HWND, __int64, _QWORD, _QWORD))(*(_QWORD *)v8[22] + 304LL))(
          v8[22],
          v8[37],
          783,
          0,
          0);
      }
LABEL_91:
      DevCaps = CheckResult(v25);
      goto LABEL_21;
    }
    if ( (_DWORD)a3 == 2129 || (_DWORD)a3 == 2130 || (_DWORD)a3 == 2131 )
      goto LABEL_105;
    if ( (_DWORD)a3 == 2132 )
    {
      if ( (a4 & 0x20) == 0 )
      {
        DevCaps = DeviceUpdate((struct _MCIGRAPHIC *)a1, a4, (struct MCI_DGV_UPDATE_PARMS *)v5);
        goto LABEL_21;
      }
    }
    else
    {
      v26 = a3 - 2133;
      if ( (_DWORD)a3 != 2133 )
      {
LABEL_101:
        if ( v26 != 1 )
          goto LABEL_102;
        goto LABEL_105;
      }
      if ( (a4 & 0x20) == 0 )
      {
        v25 = 0;
        v27 = IsWindowVisible(a1[37]);
        SetWindowPos(v8[37], 0, 0, 0, 0, 0, v27 ? 83 : 67);
        if ( *((_DWORD *)v8 + 72) != 526 )
        {
          (*(void (__fastcall **)(HWND))(*(_QWORD *)v8[19] + 64LL))(v8[19]);
          v25 = (*(__int64 (__fastcall **)(HWND))(*(_QWORD *)v8[19] + 56LL))(v8[19]);
          *((_DWORD *)v8 + 72) = 526;
        }
        goto LABEL_91;
      }
    }
    DevCaps = 0;
    goto LABEL_21;
  }
  if ( (_DWORD)a3 == 2096 )
  {
    DevCaps = GraphicCue((struct _MCIGRAPHIC *)a1);
    goto LABEL_21;
  }
  if ( (unsigned int)a3 > 0x80A )
  {
    switch ( (_DWORD)a3 )
    {
      case 0x80B:
        DevCaps = GraphicGetDevCaps(2058, a4, v5);
        goto LABEL_21;
      case 0x80D:
        DevCaps = GraphicSet((struct _MCIGRAPHIC *)a1);
        goto LABEL_21;
      case 0x80E:
        DevCaps = GraphicStep((struct _MCIGRAPHIC *)a1);
        goto LABEL_21;
    }
    if ( (_DWORD)a3 != 2063 && (_DWORD)a3 != 2067 )
    {
      if ( (_DWORD)a3 == 2068 )
      {
        DevCaps = GraphicStatus((struct _MCIGRAPHIC *)a1);
        goto LABEL_21;
      }
      goto LABEL_102;
    }
LABEL_105:
    v13 = 274;
    goto LABEL_106;
  }
  switch ( (_DWORD)a3 )
  {
    case 0x80A:
      DevCaps = GraphicInfoI(
                  (struct _MCIGRAPHIC *)a1,
                  a4,
                  a3,
                  (unsigned __int16 *)v5[1].dwCallback,
                  v5[2].dwCallback,
                  cy);
      goto LABEL_21;
    case 0x801:
      v22 = GraphicOpen((HLOCAL *)&v29, a4, (__int64)v5, lParam);
      v8 = v29;
      v13 = v22;
      goto LABEL_106;
    case 0x802:
      mciSetDriverData(lParam, 0);
      v13 = GraphicClose((struct _MCIGRAPHIC *)v8);
      v8 = 0;
      goto LABEL_110;
  }
  if ( (_DWORD)a3 != 2054 )
  {
    if ( (_DWORD)a3 == 2055 )
    {
      v14 = a4 & 0xFFFFFFDF;
      if ( (a4 & 0x20) == 0 )
        v14 = a4;
      v15 = v14 & 0xFFFFFFFC;
      if ( (v14 & 0xFFFFFFFC) == 0 )
      {
        v13 = 273;
        goto LABEL_106;
      }
      switch ( v15 )
      {
        case 8u:
          dwCallback = v5[1].dwCallback;
          break;
        case 0x100u:
          dwCallback = 0;
          break;
        case 0x200u:
          dwCallback = Duration((struct _MCIGRAPHIC *)v8);
          break;
        default:
          v13 = (v14 & 0xFFFFFCF4) != 0 ? 259 : 284;
          goto LABEL_106;
      }
      if ( dwCallback > Duration((struct _MCIGRAPHIC *)v8) || dwCallback < 0 )
      {
        v13 = 282;
        goto LABEL_106;
      }
      if ( (a4 & 0x20) == 0 )
      {
        v13 = DeviceSeek((struct _MCIGRAPHIC *)v8, dwCallback, v17, v18);
        goto LABEL_106;
      }
      goto LABEL_38;
    }
    if ( (_DWORD)a3 != 2056 )
    {
      if ( (_DWORD)a3 == 2057 )
      {
        if ( (a4 & 0x20) == 0 )
        {
          DevCaps = DevicePause((struct _MCIGRAPHIC *)a1, a4, a3);
LABEL_21:
          v13 = DevCaps;
          goto LABEL_106;
        }
        goto LABEL_38;
      }
LABEL_102:
      v13 = 261;
      goto LABEL_106;
    }
    if ( (a4 & 0x10000) == 0 )
    {
      if ( (a4 & 0x20) == 0 )
      {
        DevCaps = DeviceStop((struct _MCIGRAPHIC *)a1, lParam);
        goto LABEL_21;
      }
LABEL_38:
      v13 = 0;
      goto LABEL_106;
    }
    goto LABEL_105;
  }
  if ( (a4 & 8) != 0
    && (dwCallback_high = HIDWORD(v5[1].dwCallback), dwCallback_high > Duration((struct _MCIGRAPHIC *)a1))
    || (a4 & 4) != 0 && (v20 = v5[1].dwCallback, v20 > Duration((struct _MCIGRAPHIC *)v8)) )
  {
    v13 = 282;
  }
  else if ( (a4 & 0x20) != 0 )
  {
    v13 = 0;
  }
  else
  {
    v13 = DevicePlay((struct _MCIGRAPHIC *)v8, a4, (struct tagMCI_PLAY_PARMS *)v5, v5->dwCallback);
    if ( *((_DWORD *)v8 + 148) )
    {
      v21 = UndisplayCachedFrame((struct _MCIGRAPHIC *)v8);
      if ( v21 < 0 )
        v13 = v21;
    }
  }
  v10 = 1;
  if ( (a4 & 0x20) == 0 )
    goto LABEL_114;
LABEL_106:
  if ( !v8 || (a4 & 1) == 0 )
  {
LABEL_110:
    if ( !(_WORD)v13 && (a4 & 1) != 0 && !gfEvil )
      PostMessageW((HWND)SLODWORD(v5->dwCallback), 0x3B9u, 1u, v6);
    goto LABEL_114;
  }
  if ( !(_WORD)v13 )
  {
    GraphicDelayedNotify(v8, 2);
    goto LABEL_110;
  }
LABEL_114:
  if ( v8 )
  {
    if ( v10 && v13 && (a4 & 1) != 0 )
      *v8 = 0;
    if ( !v11 )
      *((_DWORD *)v8 + 4) = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x18000485c  mov     [rsp+arg_0], rcx
0x180004861  push    rbx
0x180004862  push    rbp
0x180004863  push    rsi
0x180004864  push    rdi
0x180004865  push    r12
0x180004867  push    r13
0x180004869  push    r14
0x18000486b  push    r15
0x18000486d  sub     rsp, 48h
0x180004871  mov     r14, [rsp+88h+arg_20]
0x180004879  xor     ebp, ebp
0x18000487b  mov     r15d, edx
0x18000487e  mov     esi, r9d
0x180004881  mov     eax, r8d
0x180004884  mov     rdi, rcx
0x180004887  test    r14, r14
0x18000488a  jnz     short loc_18000489C
0x18000488c  test    sil, 1
0x180004890  jz      short loc_18000489C
0x180004892  mov     eax, 111h
0x180004897  jmp     loc_180004DC8
0x18000489c  test    rdi, rdi
0x18000489f  jnz     short loc_1800048B6
0x1800048a1  mov     r9, r14
0x1800048a4  mov     r8d, esi
0x1800048a7  mov     edx, eax
0x1800048a9  mov     ecx, r15d; lParam
0x1800048ac  call    mciSpecial
0x1800048b1  jmp     loc_180004DC8
0x1800048b6  mov     r12d, ebp
0x1800048b9  cmp     [rcx+10h], ebp
0x1800048bc  jz      short loc_1800048C6
0x1800048be  mov     r13d, 1
0x1800048c4  jmp     short loc_1800048CC
0x1800048c6  mov     r13d, ebp
0x1800048c9  mov     [rcx+10h], eax
0x1800048cc  mov     ecx, 830h
0x1800048d1  cmp     eax, ecx
0x1800048d3  ja      loc_180004B3F
0x1800048d9  jz      loc_180004B2D
0x1800048df  mov     ecx, 80Ah
0x1800048e4  cmp     eax, ecx
0x1800048e6  ja      loc_180004ABC
0x1800048ec  jz      loc_180004AA1
0x1800048f2  sub     eax, 801h
0x1800048f7  jz      loc_180004A7D
0x1800048fd  sub     eax, 1
0x180004900  jz      loc_180004A60
0x180004906  sub     eax, 4
0x180004909  jz      loc_1800049E6
0x18000490f  sub     eax, 1
0x180004912  jz      short loc_180004957
0x180004914  sub     eax, 1
0x180004917  jz      short loc_18000493D
0x180004919  cmp     eax, 1
0x18000491c  jnz     loc_180004D30
0x180004922  test    sil, 20h
0x180004926  jnz     loc_1800049BE
0x18000492c  mov     edx, esi; unsigned int
0x18000492e  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004931  call    ?DevicePause@@YAKPEAU_MCIGRAPHIC@@K_K@Z; DevicePause(_MCIGRAPHIC *,ulong,unsigned __int64)
0x180004936  mov     ebx, eax
0x180004938  jmp     loc_180004D60
0x18000493d  bt      esi, 10h
0x180004941  jb      loc_180004D5B
0x180004947  test    sil, 20h
0x18000494b  jnz     short loc_1800049BE
0x18000494d  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004950  call    ?DeviceStop@@YAKPEAU_MCIGRAPHIC@@K@Z; DeviceStop(_MCIGRAPHIC *,ulong)
0x180004955  jmp     short loc_180004936
0x180004957  mov     eax, esi
0x180004959  mov     ebp, esi
0x18000495b  and     eax, 0FFFFFFDFh
0x18000495e  and     ebp, 20h
0x180004961  cmovz   eax, esi
0x180004964  mov     ecx, eax
0x180004966  and     ecx, 0FFFFFFFCh
0x180004969  jz      short loc_1800049DA
0x18000496b  cmp     ecx, 8
0x18000496e  jz      short loc_1800049A4
0x180004970  cmp     ecx, 100h
0x180004976  jz      short loc_1800049A0
0x180004978  cmp     ecx, 200h
0x18000497e  jz      short loc_180004994
0x180004980  and     eax, 0FFFFFCF4h
0x180004985  neg     eax
0x180004987  sbb     ebx, ebx
0x180004989  and     ebx, 0FFFFFFE7h
0x18000498c  add     ebx, 11Ch
0x180004992  jmp     short loc_1800049DF
0x180004994  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004997  call    ?Duration@@YAKPEAU_MCIGRAPHIC@@@Z; Duration(_MCIGRAPHIC *)
0x18000499c  mov     ebx, eax
0x18000499e  jmp     short loc_1800049A8
0x1800049a0  xor     ebx, ebx
0x1800049a2  jmp     short loc_1800049A8
0x1800049a4  mov     ebx, [r14+8]
0x1800049a8  mov     rcx, rdi; struct _MCIGRAPHIC *
0x1800049ab  call    ?Duration@@YAKPEAU_MCIGRAPHIC@@@Z; Duration(_MCIGRAPHIC *)
0x1800049b0  cmp     ebx, eax
0x1800049b2  ja      short loc_1800049D3
0x1800049b4  test    ebx, ebx
0x1800049b6  js      short loc_1800049D3
0x1800049b8  test    ebp, ebp
0x1800049ba  jz      short loc_1800049C5
0x1800049bc  xor     ebp, ebp
0x1800049be  mov     ebx, ebp
0x1800049c0  jmp     loc_180004D60
0x1800049c5  mov     edx, ebx; int
0x1800049c7  mov     rcx, rdi; struct _MCIGRAPHIC *
0x1800049ca  call    ?DeviceSeek@@YAKPEAU_MCIGRAPHIC@@JK_K@Z; DeviceSeek(_MCIGRAPHIC *,long,ulong,unsigned __int64)
0x1800049cf  mov     ebx, eax
0x1800049d1  jmp     short loc_1800049DF
0x1800049d3  mov     ebx, 11Ah
0x1800049d8  jmp     short loc_1800049DF
0x1800049da  mov     ebx, 111h
0x1800049df  xor     ebp, ebp
0x1800049e1  jmp     loc_180004D60
0x1800049e6  test    sil, 8
0x1800049ea  jz      short loc_180004A03
0x1800049ec  mov     ebx, [r14+0Ch]
0x1800049f0  mov     rcx, rdi; struct _MCIGRAPHIC *
0x1800049f3  call    ?Duration@@YAKPEAU_MCIGRAPHIC@@@Z; Duration(_MCIGRAPHIC *)
0x1800049f8  cmp     ebx, eax
0x1800049fa  jbe     short loc_180004A03
0x1800049fc  mov     ebx, 11Ah
0x180004a01  jmp     short loc_180004A4B
0x180004a03  test    sil, 4
0x180004a07  jz      short loc_180004A19
0x180004a09  mov     ebx, [r14+8]
0x180004a0d  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004a10  call    ?Duration@@YAKPEAU_MCIGRAPHIC@@@Z; Duration(_MCIGRAPHIC *)
0x180004a15  cmp     ebx, eax
0x180004a17  ja      short loc_1800049FC
0x180004a19  test    sil, 20h
0x180004a1d  jz      short loc_180004A23
0x180004a1f  mov     ebx, ebp
0x180004a21  jmp     short loc_180004A4B
0x180004a23  mov     r9, [r14]; unsigned __int64
0x180004a26  mov     r8, r14; struct tagMCI_PLAY_PARMS *
0x180004a29  mov     edx, esi; unsigned int
0x180004a2b  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004a2e  call    ?DevicePlay@@YAKPEAU_MCIGRAPHIC@@KPEAUtagMCI_PLAY_PARMS@@_K@Z; DevicePlay(_MCIGRAPHIC *,ulong,tagMCI_PLAY_PARMS *,unsigned __int64)
0x180004a33  mov     ebx, eax
0x180004a35  cmp     [rdi+250h], ebp
0x180004a3b  jz      short loc_180004A4B
0x180004a3d  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004a40  call    ?UndisplayCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z; UndisplayCachedFrame(_MCIGRAPHIC *)
0x180004a45  test    eax, eax
0x180004a47  jns     short loc_180004A4B
0x180004a49  mov     ebx, eax
0x180004a4b  mov     r12d, 1
0x180004a51  test    sil, 20h
0x180004a55  jz      loc_180004DA7
0x180004a5b  jmp     loc_180004D60
0x180004a60  xor     edx, edx; dwData
0x180004a62  mov     ecx, r15d; wDeviceID
0x180004a65  call    cs:__imp_mciSetDriverData
0x180004a6b  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004a6e  call    GraphicClose
0x180004a73  mov     ebx, eax
0x180004a75  mov     rdi, rbp
0x180004a78  jmp     loc_180004D7D
0x180004a7d  mov     r9d, r15d
0x180004a80  lea     rcx, [rsp+88h+arg_0]
0x180004a88  mov     r8, r14
0x180004a8b  mov     edx, esi
0x180004a8d  call    GraphicOpen
0x180004a92  mov     rdi, [rsp+88h+arg_0]
0x180004a9a  mov     ebx, eax
0x180004a9c  jmp     loc_180004D60
0x180004aa1  mov     eax, [r14+10h]
0x180004aa5  mov     edx, esi; unsigned int
0x180004aa7  mov     r9, [r14+8]; unsigned __int16 *
0x180004aab  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004aae  mov     [rsp+88h+var_68], eax; unsigned int
0x180004ab2  call    ?GraphicInfoI@@YAKPEAU_MCIGRAPHIC@@K_KPEAGKK@Z; GraphicInfoI(_MCIGRAPHIC *,ulong,unsigned __int64,ushort *,ulong,ulong)
0x180004ab7  jmp     loc_180004936
0x180004abc  sub     eax, 80Bh
0x180004ac1  jz      short loc_180004B1E
0x180004ac3  sub     eax, 2
0x180004ac6  jz      short loc_180004B0C
0x180004ac8  sub     eax, 1
0x180004acb  jz      short loc_180004AFA
0x180004acd  sub     eax, 1
0x180004ad0  jz      loc_180004D5B
0x180004ad6  sub     eax, 4
0x180004ad9  jz      loc_180004D5B
0x180004adf  cmp     eax, 1
0x180004ae2  jnz     loc_180004D30
0x180004ae8  mov     r8, r14
0x180004aeb  mov     edx, esi
0x180004aed  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004af0  call    GraphicStatus
0x180004af5  jmp     loc_180004936
0x180004afa  mov     r8, r14
0x180004afd  mov     edx, esi
0x180004aff  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004b02  call    GraphicStep
0x180004b07  jmp     loc_180004936
0x180004b0c  mov     r8, r14
0x180004b0f  mov     edx, esi
0x180004b11  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004b14  call    GraphicSet
0x180004b19  jmp     loc_180004936
0x180004b1e  mov     r8, r14
0x180004b21  mov     edx, esi
0x180004b23  call    GraphicGetDevCaps
0x180004b28  jmp     loc_180004936
0x180004b2d  mov     r8, r14
0x180004b30  mov     edx, esi
0x180004b32  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004b35  call    GraphicCue
0x180004b3a  jmp     loc_180004936
0x180004b3f  mov     ecx, 870h
0x180004b44  cmp     eax, ecx
0x180004b46  ja      loc_180004D02
0x180004b4c  jz      loc_180004D5B
0x180004b52  mov     ecx, 850h
0x180004b57  cmp     eax, ecx
0x180004b59  ja      loc_180004C26
0x180004b5f  jz      loc_180004D5B
0x180004b65  sub     eax, 840h
0x180004b6a  jz      short loc_180004BB5
0x180004b6c  sub     eax, 1
0x180004b6f  jz      short loc_180004BA3
0x180004b71  sub     eax, 1
0x180004b74  jz      short loc_180004B91
0x180004b76  sub     eax, 1
0x180004b79  jnz     loc_180004D26
0x180004b7f  mov     r8, r14
0x180004b82  mov     edx, esi
0x180004b84  mov     rcx, rdi
0x180004b87  call    GraphicWhere
0x180004b8c  jmp     loc_180004936
0x180004b91  mov     r8, r14
0x180004b94  mov     edx, esi
0x180004b96  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004b99  call    GraphicPut
0x180004b9e  jmp     loc_180004936
0x180004ba3  mov     r8, r14
0x180004ba6  mov     edx, esi
0x180004ba8  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180004bab  call    GraphicWindow
0x180004bb0  jmp     loc_180004936
0x180004bb5  mov     eax, ebp
0x180004bb7  test    sil, 20h
0x180004bbb  jnz     loc_180004936
0x180004bc1  mov     rcx, [rdi+0B0h]
0x180004bc8  mov     edx, esi
0x180004bca  and     edx, 20000h
0x180004bd0  mov     ebx, ebp
0x180004bd2  setnz   al
0x180004bd5  mov     [rdi+38h], eax
0x180004bd8  test    rcx, rcx
0x180004bdb  jz      loc_180004CDA
0x180004be1  mov     rax, [rcx]
0x180004be4  neg     edx
0x180004be6  sbb     edx, edx
0x180004be8  mov     rax, [rax+88h]
0x180004bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf4  mov     rcx, [rdi+0B0h]
0x180004bfb  mov     ebx, eax
0x180004bfd  xor     r9d, r9d
0x180004c00  mov     qword ptr [rsp+88h+var_68], rbp
0x180004c05  mov     r8d, 30Fh
0x180004c0b  mov     rdx, [rcx]
0x180004c0e  mov     rax, [rdx+130h]
0x180004c15  mov     rdx, [rdi+128h]
0x180004c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c21  jmp     loc_180004CDA
0x180004c26  sub     eax, 851h
0x180004c2b  jz      loc_180004D5B
0x180004c31  sub     eax, 1
0x180004c34  jz      loc_180004D5B
0x180004c3a  sub     eax, 1
0x180004c3d  jz      loc_180004D5B
0x180004c43  sub     eax, 1
0x180004c46  jz      loc_180004CE6
0x180004c4c  sub     eax, 1
0x180004c4f  jnz     loc_180004D2B
0x180004c55  test    sil, 20h
0x180004c59  jz      short loc_180004C62
0x180004c5b  mov     eax, ebp
0x180004c5d  jmp     loc_180004936
0x180004c62  mov     rcx, [rdi+128h]; hWnd
0x180004c69  mov     ebx, ebp
0x180004c6b  call    cs:__imp_IsWindowVisible
0x180004c71  neg     eax
0x180004c73  sbb     ecx, ecx
0x180004c75  xor     r9d, r9d; Y
0x180004c78  and     ecx, 10h
0x180004c7b  xor     r8d, r8d; X
0x180004c7e  add     ecx, 43h ; 'C'
0x180004c81  xor     edx, edx; hWndInsertAfter
0x180004c83  mov     [rsp+88h+uFlags], ecx; uFlags
0x180004c87  mov     rcx, [rdi+128h]; hWnd
0x180004c8e  mov     [rsp+88h+cy], ebp; cy
0x180004c92  mov     [rsp+88h+var_68], ebp; cx
  ... truncated ...
```
