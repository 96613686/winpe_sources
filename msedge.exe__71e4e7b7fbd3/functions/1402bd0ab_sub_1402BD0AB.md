# sub_1402BD0AB

- ea: `0x1402bd0ab`
- end: `0x1402bd68a`
- name: `sub_1402BD0AB`
- size: `1503`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a2dbc`
- `0x1401fa3c5`

## callees

- `0x14003abe0`
- `0x14003f4d0`
- `0x140075e00`
- `0x140083b80`
- `0x140086c50`
- `0x1400dda90`
- `0x140101da0`
- `0x1401079e0`
- `0x140118620`
- `0x14011cb20`
- `0x14011fa70`
- `0x1401d2640`
- `0x1402bcc57`
- `0x1402bd0ab`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1402bd447`
- `KERNEL32!GetLastError` at `0x1402bd468`
- `KERNEL32!GetLastError` at `0x1402bd447`
- `KERNEL32!GetLastError` at `0x1402bd468`
- `KERNEL32!GetStartupInfoW` at `0x1402bd28d`
- `KERNEL32!GetStartupInfoW` at `0x1402bd28d`
- `KERNEL32!SetLastError` at `0x1402bd390`
- `KERNEL32!SetLastError` at `0x1402bd390`
- `USER32!AllowSetForegroundWindow` at `0x1402bd360`
- `USER32!AllowSetForegroundWindow` at `0x1402bd360`
- `USER32!GetWindowThreadProcessId` at `0x1402bd10b`
- `USER32!GetWindowThreadProcessId` at `0x1402bd10b`
- `USER32!IsHungAppWindow` at `0x1402bd459`
- `USER32!IsHungAppWindow` at `0x1402bd459`
- `USER32!IsWindow` at `0x1402bd49c`
- `USER32!IsWindow` at `0x1402bd49c`
- `USER32!SendMessageTimeoutW` at `0x1402bd3da`
- `USER32!SendMessageTimeoutW` at `0x1402bd3da`

## string_xrefs

- `0x1402bd546`: `AttemptToNotifyRunningChrome`
- `0x1402bd59d`: `AttemptToNotifyRunningChrome:GetWindowThreadProcessId failed`
- `0x1402bd623`: `AttemptToNotifyRunningChrome:SendMessage`
- `0x1402bd5ca`: `AttemptToNotifyRunningChrome:GetCurrentDirectory failed`
- `0x1402bd4ef`: `AttemptToNotifyRunningChrome:Error SendFailed`
- `0x1402bd4e3`: `AttemptToNotifyRunningChrome:Error RemoteDied`
- `0x1402bd660`: `AttemptToNotifyRunningChrome:Error RemoteHung`

## pseudocode

```c
__int64 __fastcall sub_1402BD0AB(HWND hWnd, __int64 a2, char a3, __int64 a4)
{
  unsigned int v8; // edi
  unsigned __int64 v9; // rax
  __int128 *v11; // rbx
  int v12; // eax
  LRESULT v13; // rbx
  bool v14; // bp
  DWORD LastError; // eax
  DWORD v16; // eax
  __int64 v17; // rcx
  const char *v18; // rax
  _BYTE v19[32]; // [rsp+0h] [rbp-218h] BYREF
  ULONG_PTR dwResult; // [rsp+38h] [rbp-1E0h] BYREF
  LPARAM lParam[2]; // [rsp+40h] [rbp-1D8h] BYREF
  __int128 *v22; // [rsp+50h] [rbp-1C8h]
  _BYTE v23[24]; // [rsp+58h] [rbp-1C0h] BYREF
  __int128 v24; // [rsp+70h] [rbp-1A8h] BYREF
  __int64 v25; // [rsp+80h] [rbp-198h]
  const char *v26; // [rsp+90h] [rbp-188h]
  __int64 v27; // [rsp+98h] [rbp-180h]
  const char *v28; // [rsp+A0h] [rbp-178h]
  __int64 v29; // [rsp+A8h] [rbp-170h]
  LPWSTR lpTitle; // [rsp+B0h] [rbp-168h]
  __int64 v31; // [rsp+B8h] [rbp-160h]
  struct _STARTUPINFOW StartupInfo; // [rsp+C0h] [rbp-158h] BYREF
  const char *v33; // [rsp+130h] [rbp-E8h]
  __int64 v34; // [rsp+138h] [rbp-E0h]
  __int128 v35; // [rsp+140h] [rbp-D8h] BYREF
  __int64 v36; // [rsp+150h] [rbp-C8h]
  DWORD dwProcessId; // [rsp+15Ch] [rbp-BCh] BYREF
  __int64 v38; // [rsp+160h] [rbp-B8h] BYREF
  const char *v39; // [rsp+168h] [rbp-B0h] BYREF
  _QWORD v40[11]; // [rsp+170h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+1C8h] [rbp-50h]

  v40[0] = 205;
  if ( byte_14042F20D )
  {
    *(_QWORD *)&StartupInfo.cb = "AttemptToNotifyRunningChrome";
    sub_1401D2640((unsigned __int8)byte_14042F20D, v40, &StartupInfo, 1);
  }
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(hWnd, &dwProcessId) || !dwProcessId )
  {
    v40[0] = 205;
    if ( byte_14042F20D )
    {
      *(_QWORD *)&StartupInfo.cb = "AttemptToNotifyRunningChrome:GetWindowThreadProcessId failed";
      sub_1401D2640((unsigned __int8)byte_14042F20D, v40, &StartupInfo, 1);
    }
    v40[0] = 205;
    if ( byte_14042F20D )
    {
      *(_QWORD *)&StartupInfo.cb = 0;
      sub_1401D2640((unsigned __int8)byte_14042F20D, v40, &StartupInfo, 2);
    }
    v8 = 1;
    goto LABEL_15;
  }
  v35 = 0;
  v36 = 0;
  sub_14003F4D0(&v35);
  if ( (unsigned __int8)sub_1400DDA90(&v35) )
  {
    memset(v40, 0, sizeof(v40));
    sub_140101DA0(v40, a2);
    if ( a3 )
    {
      v33 = "fast-start";
      v34 = 10;
      sub_140118620(v40);
    }
    memset(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    GetStartupInfoW(&StartupInfo);
    if ( (StartupInfo.dwFlags & 0x800) != 0 )
    {
      lpTitle = StartupInfo.lpTitle;
      if ( !StartupInfo.lpTitle )
        BUG();
      v31 = sub_14011CB20(StartupInfo.lpTitle);
      v28 = "source-shortcut";
      v29 = 15;
      sub_140083B80(v40);
    }
    else if ( (StartupInfo.dwFlags & 0x1000) != 0 )
    {
      v26 = "source-app-id";
      v27 = 13;
      sub_140118620(v40);
    }
    v11 = &v24;
    v24 = 0;
    v25 = 0;
    sub_140075E00(v23, &v35);
    sub_1402BCC57(&v24, v40, v23, a4);
    AllowSetForegroundWindow(dwProcessId);
    v12 = SHIBYTE(v25);
    if ( v25 < 0 )
      v12 = DWORD2(v24);
    *(_OWORD *)lParam = 0;
    if ( v25 < 0 )
      v11 = (__int128 *)v24;
    LODWORD(lParam[1]) = 2 * v12 + 2;
    v22 = v11;
    dwResult = 0;
    SetLastError(0);
    v38 = 205;
    if ( byte_14042F20D )
    {
      v39 = "AttemptToNotifyRunningChrome:SendMessage";
      sub_1401D2640((unsigned __int8)byte_14042F20D, &v38, &v39, 1);
    }
    v13 = SendMessageTimeoutW(hWnd, 0x4Au, 0, (LPARAM)lParam, 2u, 0x4E20u, &dwResult);
    v8 = 0;
    v14 = dwResult == 0;
    v38 = 205;
    if ( byte_14042F20D )
    {
      v39 = 0;
      sub_1401D2640((unsigned __int8)byte_14042F20D, &v38, &v39, 2);
    }
    if ( v13 )
    {
      LOBYTE(v8) = v14;
      goto LABEL_36;
    }
    LastError = GetLastError();
    if ( LastError == 5 )
    {
      v8 = 3;
      goto LABEL_36;
    }
    if ( !LastError )
    {
      v8 = 2;
      if ( IsHungAppWindow(hWnd) )
        goto LABEL_36;
    }
    v16 = GetLastError();
    if ( !v16 || v16 == 1460 )
    {
      if ( IsWindow(hWnd) )
      {
        v38 = 205;
        LOBYTE(v9) = byte_14042F20D;
        if ( !byte_14042F20D )
          goto LABEL_49;
        goto LABEL_55;
      }
      v38 = 205;
      if ( !byte_14042F20D )
      {
LABEL_46:
        v8 = 1;
        goto LABEL_36;
      }
      v17 = (unsigned __int8)byte_14042F20D;
      v18 = "AttemptToNotifyRunningChrome:Error RemoteDied";
    }
    else
    {
      v38 = 205;
      if ( !byte_14042F20D )
        goto LABEL_46;
      v17 = (unsigned __int8)byte_14042F20D;
      v18 = "AttemptToNotifyRunningChrome:Error SendFailed";
    }
    v39 = v18;
    sub_1401D2640(v17, &v38, &v39, 3);
    goto LABEL_46;
  }
  v40[0] = 205;
  if ( byte_14042F20D )
  {
    *(_QWORD *)&StartupInfo.cb = "AttemptToNotifyRunningChrome:GetCurrentDirectory failed";
    sub_1401D2640((unsigned __int8)byte_14042F20D, v40, &StartupInfo, 3);
  }
  v8 = 1;
  while ( 1 )
  {
    sub_140086C50(&v35);
LABEL_15:
    v40[0] = 205;
    if ( byte_14042F20D )
    {
      *(_QWORD *)&StartupInfo.cb = 0;
      sub_1401D2640((unsigned __int8)byte_14042F20D, v40, &StartupInfo, 2);
    }
    v9 = (unsigned __int64)v19 ^ v41;
    if ( _security_cookie == ((unsigned __int64)v19 ^ v41) )
      break;
LABEL_55:
    v39 = "AttemptToNotifyRunningChrome:Error RemoteHung";
    sub_1401D2640((unsigned __int8)v9, &v38, &v39, 3);
LABEL_49:
    v8 = 2;
LABEL_36:
    if ( v25 < 0 )
      sub_14003ABE0(v24, 2 * v25);
    sub_1401079E0(v40);
  }
  return v8;
}

```

## disassembly

```asm
0x1402bd0ab  push    r15
0x1402bd0ad  push    r14
0x1402bd0af  push    rsi
0x1402bd0b0  push    rdi
0x1402bd0b1  push    rbp
0x1402bd0b2  push    rbx
0x1402bd0b3  sub     rsp, 1E8h
0x1402bd0ba  movaps  [rsp+218h+var_48], xmm6
0x1402bd0c2  mov     rdi, r9
0x1402bd0c5  mov     ebx, r8d
0x1402bd0c8  mov     r14, rdx
0x1402bd0cb  mov     rsi, rcx
0x1402bd0ce  mov     rax, cs:__security_cookie
0x1402bd0d5  xor     rax, rsp
0x1402bd0d8  mov     [rsp+218h+var_50], rax
0x1402bd0e0  mov     [rsp+218h+var_A8], 0CDh
0x1402bd0ec  mov     al, cs:byte_14042F20D
0x1402bd0f2  test    al, al
0x1402bd0f4  jnz     loc_1402BD543
0x1402bd0fa  lea     rdx, [rsp+218h+dwProcessId]; lpdwProcessId
0x1402bd102  mov     dword ptr [rdx], 0
0x1402bd108  mov     rcx, rsi; hWnd
0x1402bd10b  call    cs:GetWindowThreadProcessId
0x1402bd111  test    eax, eax
0x1402bd113  jz      short loc_1402BD17C
0x1402bd115  cmp     [rsp+218h+dwProcessId], 0
0x1402bd11d  jz      short loc_1402BD17C
0x1402bd11f  xorps   xmm6, xmm6
0x1402bd122  lea     r15, [rsp+218h+var_D8]
0x1402bd12a  movaps  xmmword ptr [r15], xmm6
0x1402bd12e  mov     qword ptr [r15+10h], 0
0x1402bd136  mov     rcx, r15
0x1402bd139  call    sub_14003F4D0
0x1402bd13e  mov     rcx, r15
0x1402bd141  call    sub_1400DDA90
0x1402bd146  test    al, al
0x1402bd148  jnz     loc_1402BD204
0x1402bd14e  mov     [rsp+218h+var_A8], 0CDh
0x1402bd15a  mov     al, cs:byte_14042F20D
0x1402bd160  test    al, al
0x1402bd162  jnz     loc_1402BD5C7
0x1402bd168  mov     edi, 1
0x1402bd16d  lea     rcx, [rsp+218h+var_D8]
0x1402bd175  call    sub_140086C50
0x1402bd17a  jmp     short loc_1402BD1B5
0x1402bd17c  mov     [rsp+218h+var_A8], 0CDh
0x1402bd188  mov     al, cs:byte_14042F20D
0x1402bd18e  test    al, al
0x1402bd190  jnz     loc_1402BD59A
0x1402bd196  mov     [rsp+218h+var_A8], 0CDh
0x1402bd1a2  mov     al, cs:byte_14042F20D
0x1402bd1a8  test    al, al
0x1402bd1aa  jnz     loc_1402BD570
0x1402bd1b0  mov     edi, 1
0x1402bd1b5  mov     [rsp+218h+var_A8], 0CDh
0x1402bd1c1  mov     al, cs:byte_14042F20D
0x1402bd1c7  test    al, al
0x1402bd1c9  jnz     loc_1402BD519
0x1402bd1cf  mov     rax, [rsp+218h+var_50]
0x1402bd1d7  xor     rax, rsp
0x1402bd1da  mov     rcx, cs:__security_cookie
0x1402bd1e1  cmp     rcx, rax
0x1402bd1e4  jnz     loc_1402BD64D
0x1402bd1ea  mov     eax, edi
0x1402bd1ec  movaps  xmm6, [rsp+218h+var_48]
0x1402bd1f4  add     rsp, 1E8h
0x1402bd1fb  pop     rbx
0x1402bd1fc  pop     rbp
0x1402bd1fd  pop     rdi
0x1402bd1fe  pop     rsi
0x1402bd1ff  pop     r14
0x1402bd201  pop     r15
0x1402bd203  retn
0x1402bd204  lea     rcx, [rsp+218h+var_A8]
0x1402bd20c  movaps  xmmword ptr [rcx+40h], xmm6
0x1402bd210  movaps  xmmword ptr [rcx+30h], xmm6
0x1402bd214  movaps  xmmword ptr [rcx+20h], xmm6
0x1402bd218  movaps  xmmword ptr [rcx+10h], xmm6
0x1402bd21c  movaps  xmmword ptr [rcx], xmm6
0x1402bd21f  mov     qword ptr [rcx+50h], 0
0x1402bd227  mov     rdx, r14
0x1402bd22a  call    sub_140101DA0
0x1402bd22f  test    bl, bl
0x1402bd231  jz      short loc_1402BD25A
0x1402bd233  lea     rax, aFastStart; "fast-start"
0x1402bd23a  lea     rdx, [rsp+218h+var_E8]
0x1402bd242  mov     [rdx], rax
0x1402bd245  mov     qword ptr [rdx+8], 0Ah
0x1402bd24d  lea     rcx, [rsp+218h+var_A8]
0x1402bd255  call    sub_140118620
0x1402bd25a  xorps   xmm0, xmm0
0x1402bd25d  lea     rbx, [rsp+218h+StartupInfo]
0x1402bd265  movaps  xmmword ptr [rbx], xmm0
0x1402bd268  movaps  xmmword ptr [rbx+50h], xmm0
0x1402bd26c  movaps  xmmword ptr [rbx+40h], xmm0
0x1402bd270  movaps  xmmword ptr [rbx+30h], xmm0
0x1402bd274  movaps  xmmword ptr [rbx+20h], xmm0
0x1402bd278  movaps  xmmword ptr [rbx+10h], xmm0
0x1402bd27c  mov     qword ptr [rbx+60h], 0
0x1402bd284  mov     dword ptr [rbx], 68h ; 'h'
0x1402bd28a  mov     rcx, rbx; lpStartupInfo
0x1402bd28d  call    cs:GetStartupInfoW
0x1402bd293  mov     eax, [rbx+3Ch]
0x1402bd296  bt      eax, 0Bh
0x1402bd29a  jb      short loc_1402BD2CB
0x1402bd29c  bt      eax, 0Ch
0x1402bd2a0  jnb     short loc_1402BD31C
0x1402bd2a2  lea     rax, aSourceAppId; "source-app-id"
0x1402bd2a9  lea     rdx, [rsp+218h+var_188]
0x1402bd2b1  mov     [rdx], rax
0x1402bd2b4  mov     qword ptr [rdx+8], 0Dh
0x1402bd2bc  lea     rcx, [rsp+218h+var_A8]
0x1402bd2c4  call    sub_140118620
0x1402bd2c9  jmp     short loc_1402BD31C
0x1402bd2cb  mov     rcx, [rsp+218h+StartupInfo.lpTitle]
0x1402bd2d3  mov     [rsp+218h+var_168], rcx
0x1402bd2db  test    rcx, rcx
0x1402bd2de  jz      loc_1402BD5F4
0x1402bd2e4  call    sub_14011CB20
0x1402bd2e9  lea     r8, [rsp+218h+var_168]
0x1402bd2f1  mov     [r8+8], rax
0x1402bd2f5  lea     rax, aSourceShortcut; "source-shortcut"
0x1402bd2fc  lea     rdx, [rsp+218h+var_178]
0x1402bd304  mov     [rdx], rax
0x1402bd307  mov     qword ptr [rdx+8], 0Fh
0x1402bd30f  lea     rcx, [rsp+218h+var_A8]
0x1402bd317  call    sub_140083B80
0x1402bd31c  xorps   xmm6, xmm6
0x1402bd31f  lea     rbx, [rsp+218h+var_1A8]
0x1402bd324  movaps  xmmword ptr [rbx], xmm6
0x1402bd327  xor     r15d, r15d
0x1402bd32a  mov     [rbx+10h], r15
0x1402bd32e  lea     r14, [rsp+218h+var_1C0]
0x1402bd333  lea     rdx, [rsp+218h+var_D8]
0x1402bd33b  mov     rcx, r14
0x1402bd33e  call    sub_140075E00
0x1402bd343  lea     rdx, [rsp+218h+var_A8]
0x1402bd34b  mov     rcx, rbx
0x1402bd34e  mov     r8, r14
0x1402bd351  mov     r9, rdi
0x1402bd354  call    sub_1402BCC57
0x1402bd359  mov     ecx, [rsp+218h+dwProcessId]; dwProcessId
0x1402bd360  call    cs:AllowSetForegroundWindow
0x1402bd366  movsx   eax, byte ptr [rbx+17h]
0x1402bd36a  test    eax, eax
0x1402bd36c  cmovs   eax, [rbx+8]
0x1402bd370  movaps  xmmword ptr [rsp+218h+lParam], xmm6
0x1402bd375  cmovs   rbx, [rbx]
0x1402bd379  lea     eax, ds:2[rax*2]
0x1402bd380  mov     dword ptr [rsp+218h+lParam+8], eax
0x1402bd384  mov     [rsp+218h+var_1C8], rbx
0x1402bd389  mov     [rsp+218h+dwResult], r15
0x1402bd38e  xor     ecx, ecx; dwErrCode
0x1402bd390  call    cs:SetLastError
0x1402bd396  mov     [rsp+218h+var_B8], 0CDh
0x1402bd3a2  mov     al, cs:byte_14042F20D
0x1402bd3a8  test    al, al
0x1402bd3aa  jnz     loc_1402BD620
0x1402bd3b0  lea     r14, [rsp+218h+dwResult]
0x1402bd3b5  mov     [rsp+218h+lpdwResult], r14; lpdwResult
0x1402bd3ba  mov     [rsp+218h+uTimeout], 4E20h; uTimeout
0x1402bd3c2  mov     [rsp+218h+fuFlags], 2; fuFlags
0x1402bd3ca  lea     r9, [rsp+218h+lParam]; lParam
0x1402bd3cf  mov     rcx, rsi; hWnd
0x1402bd3d2  mov     edx, 4Ah ; 'J'; Msg
0x1402bd3d7  xor     r8d, r8d; wParam
0x1402bd3da  call    cs:SendMessageTimeoutW
0x1402bd3e0  mov     rbx, rax
0x1402bd3e3  xor     edi, edi
0x1402bd3e5  cmp     qword ptr [r14], 0
0x1402bd3e9  setz    bpl
0x1402bd3ed  mov     [rsp+218h+var_B8], 0CDh
0x1402bd3f9  mov     al, cs:byte_14042F20D
0x1402bd3ff  test    al, al
0x1402bd401  jnz     loc_1402BD5F6
0x1402bd407  test    rbx, rbx
0x1402bd40a  jz      short loc_1402BD447
0x1402bd40c  mov     dil, bpl
0x1402bd40f  cmp     [rsp+218h+var_191], 0
0x1402bd417  jns     short loc_1402BD42E
0x1402bd419  mov     rcx, qword ptr [rsp+218h+var_1A8]
0x1402bd41e  mov     rdx, [rsp+80h]
0x1402bd426  add     rdx, rdx
0x1402bd429  call    sub_14003ABE0
0x1402bd42e  lea     rcx, [rsp+218h+var_A8]
0x1402bd436  call    sub_1401079E0
0x1402bd43b  jmp     loc_1402BD16D
0x1402bd440  mov     edi, 3
0x1402bd445  jmp     short loc_1402BD40F
0x1402bd447  call    cs:__imp_GetLastError
0x1402bd44d  cmp     eax, 5
0x1402bd450  jz      short loc_1402BD440
0x1402bd452  test    eax, eax
0x1402bd454  jnz     short loc_1402BD468
0x1402bd456  mov     rcx, rsi; hwnd
0x1402bd459  call    cs:IsHungAppWindow
0x1402bd45f  mov     edi, 2
0x1402bd464  test    eax, eax
0x1402bd466  jnz     short loc_1402BD40F
0x1402bd468  call    cs:__imp_GetLastError
0x1402bd46e  test    eax, eax
0x1402bd470  jz      short loc_1402BD499
0x1402bd472  cmp     eax, 5B4h
0x1402bd477  jz      short loc_1402BD499
0x1402bd479  mov     [rsp+218h+var_B8], 0CDh
0x1402bd485  mov     al, cs:byte_14042F20D
0x1402bd48b  test    al, al
0x1402bd48d  jnz     short loc_1402BD4EC
0x1402bd48f  mov     edi, 1
0x1402bd494  jmp     loc_1402BD40F
0x1402bd499  mov     rcx, rsi; hWnd
0x1402bd49c  call    cs:IsWindow
0x1402bd4a2  test    eax, eax
0x1402bd4a4  jz      short loc_1402BD4CA
0x1402bd4a6  mov     [rsp+218h+var_B8], 0CDh
0x1402bd4b2  mov     al, cs:byte_14042F20D
0x1402bd4b8  test    al, al
0x1402bd4ba  jnz     loc_1402BD65D
0x1402bd4c0  mov     edi, 2
0x1402bd4c5  jmp     loc_1402BD40F
0x1402bd4ca  mov     [rsp+218h+var_B8], 0CDh
0x1402bd4d6  mov     al, cs:byte_14042F20D
0x1402bd4dc  test    al, al
0x1402bd4de  jz      short loc_1402BD48F
0x1402bd4e0  movzx   ecx, al
0x1402bd4e3  lea     rax, aAttempttonotif; "AttemptToNotifyRunningChrome:Error Remo"...
0x1402bd4ea  jmp     short loc_1402BD4F6
0x1402bd4ec  movzx   ecx, al
0x1402bd4ef  lea     rax, aAttempttonotif_0; "AttemptToNotifyRunningChrome:Error Send"...
0x1402bd4f6  lea     r8, [rsp+218h+var_B0]
0x1402bd4fe  mov     [r8], rax
0x1402bd501  lea     rdx, [rsp+218h+var_B8]
0x1402bd509  mov     r9d, 3
0x1402bd50f  call    sub_1401D2640
0x1402bd514  jmp     loc_1402BD48F
0x1402bd519  movzx   ecx, al
0x1402bd51c  lea     r8, [rsp+218h+StartupInfo]
0x1402bd524  mov     qword ptr [r8], 0
0x1402bd52b  lea     rdx, [rsp+218h+var_A8]
0x1402bd533  mov     r9d, 2
0x1402bd539  call    sub_1401D2640
0x1402bd53e  jmp     loc_1402BD1CF
0x1402bd543  movzx   ecx, al
0x1402bd546  lea     rax, aAttempttonotif_1; "AttemptToNotifyRunningChrome"
0x1402bd54d  lea     r8, [rsp+218h+StartupInfo]
0x1402bd555  mov     [r8], rax
0x1402bd558  lea     rdx, [rsp+218h+var_A8]
0x1402bd560  mov     r9d, 1
0x1402bd566  call    sub_1401D2640
0x1402bd56b  jmp     loc_1402BD0FA
0x1402bd570  movzx   ecx, al
0x1402bd573  lea     r8, [rsp+218h+StartupInfo]
0x1402bd57b  mov     qword ptr [r8], 0
0x1402bd582  lea     rdx, [rsp+218h+var_A8]
0x1402bd58a  mov     r9d, 2
0x1402bd590  call    sub_1401D2640
0x1402bd595  jmp     loc_1402BD1B0
0x1402bd59a  movzx   ecx, al
0x1402bd59d  lea     rax, aAttempttonotif_2; "AttemptToNotifyRunningChrome:GetWindowT"...
0x1402bd5a4  lea     r8, [rsp+218h+StartupInfo]
0x1402bd5ac  mov     [r8], rax
0x1402bd5af  lea     rdx, [rsp+218h+var_A8]
0x1402bd5b7  mov     r9d, 1
0x1402bd5bd  call    sub_1401D2640
0x1402bd5c2  jmp     loc_1402BD196
0x1402bd5c7  movzx   ecx, al
0x1402bd5ca  lea     rax, aAttempttonotif_3; "AttemptToNotifyRunningChrome:GetCurrent"...
0x1402bd5d1  lea     r8, [rsp+218h+StartupInfo]
0x1402bd5d9  mov     [r8], rax
0x1402bd5dc  lea     rdx, [rsp+218h+var_A8]
0x1402bd5e4  mov     r9d, 3
0x1402bd5ea  call    sub_1401D2640
0x1402bd5ef  jmp     loc_1402BD168
0x1402bd5f4  ud2
0x1402bd5f6  movzx   ecx, al
0x1402bd5f9  lea     r8, [rsp+218h+var_B0]
0x1402bd601  mov     qword ptr [r8], 0
0x1402bd608  lea     rdx, [rsp+218h+var_B8]
0x1402bd610  mov     r9d, 2
0x1402bd616  call    sub_1401D2640
0x1402bd61b  jmp     loc_1402BD407
0x1402bd620  movzx   ecx, al
0x1402bd623  lea     rax, aAttempttonotif_4; "AttemptToNotifyRunningChrome:SendMessag"...
0x1402bd62a  lea     r8, [rsp+218h+var_B0]
0x1402bd632  mov     [r8], rax
0x1402bd635  lea     rdx, [rsp+218h+var_B8]
0x1402bd63d  mov     r9d, 1
0x1402bd643  call    sub_1401D2640
0x1402bd648  jmp     loc_1402BD3B0
0x1402bd64d  mov     rcx, [rsp+218h+var_50]
0x1402bd655  xor     rcx, rsp; StackCookie
0x1402bd658  call    __security_check_cookie
0x1402bd65d  movzx   ecx, al
0x1402bd660  lea     rax, aAttempttonotif_5; "AttemptToNotifyRunningChrome:Error Remo"...
0x1402bd667  lea     r8, [rsp+218h+var_B0]
0x1402bd66f  mov     [r8], rax
0x1402bd672  lea     rdx, [rsp+218h+var_B8]
0x1402bd67a  mov     r9d, 3
0x1402bd680  call    sub_1401D2640
0x1402bd685  jmp     loc_1402BD4C0
  ... truncated ...
```
