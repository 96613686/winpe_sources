# CRasGcwLUA::CreateRASEntry(_RASNCWINFO * const)

- ea: `0x180012280`
- end: `0x18001255e`
- name: `?CreateRASEntry@CRasGcwLUA@@UEAAJQEAU_RASNCWINFO@@@Z`
- size: `734`
- prototype: `signed int __fastcall(CRasGcwLUA *this, struct _RASNCWINFO *const)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180010c38`
- `0x180012280`
- `0x18002f382`
- `0x18002f3b0`
- `0x18002f470`

## import_xrefs

- `RASAPI32!RasSetEntryPropertiesW` at `0x18001252c`
- `RASAPI32!RasSetEntryPropertiesW` at `0x18001252c`

## pseudocode

```c
signed int __fastcall CRasGcwLUA::CreateRASEntry(CRasGcwLUA *this, struct _RASNCWINFO *const a2)
{
  signed int result; // eax
  DWORD v4; // r11d
  DWORD v5; // ecx
  DWORD dwfOptions; // eax
  bool v7; // zf
  int v8; // edx
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  DWORD v12; // ecx
  DWORD v13; // eax
  DWORD v14; // ecx
  tagRASENTRYW v15; // [rsp+30h] [rbp-D0h] BYREF

  memset_0(&v15.dwfOptions, 0, 0x1A40u);
  if ( !a2 )
    return 87;
  v15.dwSize = 6724;
  StringCchCopyW(v15.szLocalPhoneNumber, 0x81u, (const unsigned __int16 *)a2 + 776);
  v4 = 3;
  switch ( *(_DWORD *)a2 )
  {
    case 1:
      StringCchCopyW(v15.szDeviceType, 0x11u, L"modem");
      v15.dwType = 1;
      break;
    case 2:
      StringCchCopyW(v15.szDeviceType, 0x11u, L"vpn");
      v15.dwType = 2;
      v15.dwVpnStrategy = 0;
      break;
    case 5:
      StringCchCopyW(v15.szDeviceType, 0x11u, L"PPPoE");
      v15.dwType = 5;
      break;
  }
  v15.dwfNetProtocols = 12;
  v15.dwDialExtraSampleSeconds = 120;
  v15.dwHangUpExtraSampleSeconds = 120;
  v5 = 10240;
  dwfOptions = v15.dwfOptions | 0x5000110;
  v15.dwEncryptionType = v4;
  v7 = *((_DWORD *)a2 + 722) == 1;
  v15.dwRedialCount = v4;
  if ( v7 )
    v5 = 33564672;
  v15.dwRedialPause = 60;
  v8 = *(_DWORD *)a2;
  v9 = *(_DWORD *)a2;
  v15.dwDialExtraPercent = 75;
  v15.dwHangUpExtraPercent = 10;
  v15.dwfOptions |= 0x5000110u;
  v15.dwfOptions2 = v5;
  v10 = v9 - 1;
  if ( !v10 )
  {
    v13 = dwfOptions | 0xA00208;
    v14 = v5 | 0x205;
    v7 = (*((_BYTE *)a2 + 4) & 2) == 0;
    v15.dwfOptions = v13;
    v15.dwfOptions2 = v14;
    if ( v7 )
    {
      v15.dwfOptions = v13 | 0x2000000;
    }
    else
    {
      v15.dwIdleDisconnectSeconds = 1200;
      v15.dwfOptions2 = v14 | 0x6B;
    }
    StringCchCopyW(v15.szDeviceName, 0x81u, (const unsigned __int16 *)a2 + 2218);
    v8 = *(_DWORD *)a2;
    dwfOptions = v15.dwfOptions;
    goto LABEL_23;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    dwfOptions |= 0x2001000u;
    v7 = *((_DWORD *)a2 + 454) == 0;
    v15.dwfOptions = dwfOptions;
    if ( v7 )
    {
      dwfOptions |= 0x20800u;
      v15.dwCustomAuthKey = 0;
      v15.dwfOptions = dwfOptions;
    }
    v12 = v5 | 0x104;
    goto LABEL_18;
  }
  if ( v11 == v4 )
  {
    v12 = v5 | 0x16F;
LABEL_18:
    v15.dwfOptions2 = v12;
  }
LABEL_23:
  if ( *((_DWORD *)a2 + 454) )
  {
    v15.dwCustomAuthKey = 13;
    v15.dwfOptions = dwfOptions | 0x20000;
    v15.dwEncryptionType = 1;
  }
  if ( v8 == 2 && (*((_DWORD *)a2 + 1108) || !*((_DWORD *)a2 + 453)) )
  {
    StringCchCopyW(v15.szPrerequisitePbk, 0x104u, (const unsigned __int16 *)a2 + 1446);
    StringCchCopyW(v15.szPrerequisiteEntry, 0x101u, (const unsigned __int16 *)a2 + 1958);
  }
  result = RasSetEntryPropertiesW(
             (LPCWSTR)(((unsigned __int64)a2 + 12) & -(__int64)(*((_WORD *)a2 + 6) != 0)),
             (LPCWSTR)a2 + 519,
             &v15,
             0x1A44u,
             0,
             0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180012280  mov     [rsp-8+arg_0], rbx
0x180012285  push    rbp
0x180012286  lea     rbp, [rsp-1990h]
0x18001228e  mov     eax, 1A90h
0x180012293  call    _alloca_probe
0x180012298  sub     rsp, rax
0x18001229b  mov     rax, cs:__security_cookie
0x1800122a2  xor     rax, rsp
0x1800122a5  mov     [rbp+1990h+var_10], rax
0x1800122ac  mov     rbx, rdx
0x1800122af  lea     rcx, [rsp+1A90h+var_1A60.dwfOptions]; void *
0x1800122b4  xor     edx, edx; Val
0x1800122b6  mov     r8d, 1A40h; Size
0x1800122bc  call    memset_0
0x1800122c1  test    rbx, rbx
0x1800122c4  jnz     short loc_1800122CE
0x1800122c6  lea     eax, [rbx+57h]
0x1800122c9  jmp     loc_18001253E
0x1800122ce  lea     r8, [rbx+610h]; unsigned __int16 *
0x1800122d5  mov     [rsp+1A90h+var_1A60.dwSize], 1A44h
0x1800122dd  mov     edx, 81h; unsigned __int64
0x1800122e2  lea     rcx, [rsp+1A90h+var_1A60.szLocalPhoneNumber]; unsigned __int16 *
0x1800122e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800122ec  mov     eax, [rbx]
0x1800122ee  mov     r11d, 3
0x1800122f4  sub     eax, 1
0x1800122f7  jz      short loc_180012354
0x1800122f9  sub     eax, 1
0x1800122fc  jz      short loc_180012326
0x1800122fe  cmp     eax, r11d
0x180012301  jnz     short loc_180012376
0x180012303  lea     r8, aPppoe; "PPPoE"
0x18001230a  lea     edx, [r11+0Eh]; unsigned __int64
0x18001230e  lea     rcx, [rbp+1990h+var_1A60.szDeviceType]; unsigned __int16 *
0x180012315  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001231a  mov     [rbp+1990h+var_1A60.dwType], 5
0x180012324  jmp     short loc_180012376
0x180012326  lea     r8, aVpn; "vpn"
0x18001232d  mov     edx, 11h; unsigned __int64
0x180012332  lea     rcx, [rbp+1990h+var_1A60.szDeviceType]; unsigned __int16 *
0x180012339  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001233e  mov     [rbp+1990h+var_1A60.dwType], 2
0x180012348  mov     [rbp+1990h+var_1A60.dwVpnStrategy], 0
0x180012352  jmp     short loc_180012376
0x180012354  lea     r8, String1; "modem"
0x18001235b  mov     edx, 11h; unsigned __int64
0x180012360  lea     rcx, [rbp+1990h+var_1A60.szDeviceType]; unsigned __int16 *
0x180012367  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001236c  mov     [rbp+1990h+var_1A60.dwType], 1
0x180012376  mov     eax, 78h ; 'x'
0x18001237b  mov     [rbp+1990h+var_1A60.dwfNetProtocols], 0Ch
0x180012382  mov     [rbp+1990h+var_1A60.dwDialExtraSampleSeconds], eax
0x180012388  mov     edx, 2002800h
0x18001238d  mov     [rbp+1990h+var_1A60.dwHangUpExtraSampleSeconds], eax
0x180012393  mov     ecx, 2800h
0x180012398  mov     eax, [rsp+1A90h+var_1A60.dwfOptions]
0x18001239c  or      eax, 5000110h
0x1800123a1  mov     [rbp+1990h+var_1A60.dwEncryptionType], r11d
0x1800123a8  cmp     dword ptr [rbx+0B48h], 1
0x1800123af  mov     [rbp+1990h+var_1A60.dwRedialCount], r11d
0x1800123b6  cmovz   ecx, edx
0x1800123b9  mov     [rbp+1990h+var_1A60.dwRedialPause], 3Ch ; '<'
0x1800123c3  mov     edx, [rbx]
0x1800123c5  mov     r8d, edx
0x1800123c8  mov     [rbp+1990h+var_1A60.dwDialExtraPercent], 4Bh ; 'K'
0x1800123d2  mov     [rbp+1990h+var_1A60.dwHangUpExtraPercent], 0Ah
0x1800123dc  mov     [rsp+1A90h+var_1A60.dwfOptions], eax
0x1800123e0  mov     [rbp+1990h+var_1A60.dwfOptions2], ecx
0x1800123e6  sub     r8d, 1
0x1800123ea  jz      short loc_180012436
0x1800123ec  sub     r8d, 1
0x1800123f0  jz      short loc_180012403
0x1800123f2  cmp     r8d, r11d
0x1800123f5  jnz     loc_18001248C
0x1800123fb  or      ecx, 16Fh
0x180012401  jmp     short loc_18001242E
0x180012403  or      eax, 2001000h
0x180012408  cmp     dword ptr [rbx+718h], 0
0x18001240f  mov     [rsp+1A90h+var_1A60.dwfOptions], eax
0x180012413  jnz     short loc_180012428
0x180012415  or      eax, 20800h
0x18001241a  mov     [rbp+1990h+var_1A60.dwCustomAuthKey], 0
0x180012424  mov     [rsp+1A90h+var_1A60.dwfOptions], eax
0x180012428  or      ecx, 104h
0x18001242e  mov     [rbp+1990h+var_1A60.dwfOptions2], ecx
0x180012434  jmp     short loc_18001248C
0x180012436  or      eax, 0A00208h
0x18001243b  or      ecx, 205h
0x180012441  test    byte ptr [rbx+4], 2
0x180012445  mov     [rsp+1A90h+var_1A60.dwfOptions], eax
0x180012449  mov     [rbp+1990h+var_1A60.dwfOptions2], ecx
0x18001244f  jz      short loc_180012466
0x180012451  or      ecx, 6Bh
0x180012454  mov     [rbp+1990h+var_1A60.dwIdleDisconnectSeconds], 4B0h
0x18001245e  mov     [rbp+1990h+var_1A60.dwfOptions2], ecx
0x180012464  jmp     short loc_18001246E
0x180012466  bts     eax, 19h
0x18001246a  mov     [rsp+1A90h+var_1A60.dwfOptions], eax
0x18001246e  lea     r8, [rbx+1154h]; unsigned __int16 *
0x180012475  mov     edx, 81h; unsigned __int64
0x18001247a  lea     rcx, [rbp+1990h+var_1A60.szDeviceName]; unsigned __int16 *
0x180012481  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012486  mov     edx, [rbx]
0x180012488  mov     eax, [rsp+1A90h+var_1A60.dwfOptions]
0x18001248c  cmp     dword ptr [rbx+718h], 0
0x180012493  jz      short loc_1800124B1
0x180012495  bts     eax, 11h
0x180012499  mov     [rbp+1990h+var_1A60.dwCustomAuthKey], 0Dh
0x1800124a3  mov     [rsp+1A90h+var_1A60.dwfOptions], eax
0x1800124a7  mov     [rbp+1990h+var_1A60.dwEncryptionType], 1
0x1800124b1  cmp     edx, 2
0x1800124b4  jnz     short loc_1800124F8
0x1800124b6  cmp     dword ptr [rbx+1150h], 0
0x1800124bd  jnz     short loc_1800124C8
0x1800124bf  cmp     dword ptr [rbx+714h], 0
0x1800124c6  jnz     short loc_1800124F8
0x1800124c8  lea     r8, [rbx+0B4Ch]; unsigned __int16 *
0x1800124cf  mov     edx, 104h; unsigned __int64
0x1800124d4  lea     rcx, [rbp+1990h+var_1A60.szPrerequisitePbk]; unsigned __int16 *
0x1800124db  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800124e0  lea     r8, [rbx+0F4Ch]; unsigned __int16 *
0x1800124e7  mov     edx, 101h; unsigned __int64
0x1800124ec  lea     rcx, [rbp+1990h+var_1A60.szPrerequisiteEntry]; unsigned __int16 *
0x1800124f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800124f8  lea     r8, [rbx+0Ch]
0x1800124fc  mov     [rsp+1A90h+var_1A68], 0; DWORD
0x180012504  movzx   eax, word ptr [r8]
0x180012508  lea     rdx, [rbx+40Eh]; LPCWSTR
0x18001250f  neg     ax
0x180012512  mov     [rsp+1A90h+var_1A70], 0; LPBYTE
0x18001251b  mov     r9d, 1A44h; DWORD
0x180012521  sbb     rcx, rcx
0x180012524  and     rcx, r8; LPCWSTR
0x180012527  lea     r8, [rsp+1A90h+var_1A60]; struct tagRASENTRYW *
0x18001252c  call    cs:__imp_RasSetEntryPropertiesW
0x180012532  test    eax, eax
0x180012534  jle     short loc_18001253E
0x180012536  movzx   eax, ax
0x180012539  or      eax, 80070000h
0x18001253e  mov     rcx, [rbp+1990h+var_10]
0x180012545  xor     rcx, rsp; StackCookie
0x180012548  call    __security_check_cookie
0x18001254d  mov     rbx, [rsp+1A90h+arg_0]
0x180012555  add     rsp, 1A90h
0x18001255c  pop     rbp
0x18001255d  retn
```
