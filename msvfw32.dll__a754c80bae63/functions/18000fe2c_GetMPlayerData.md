# GetMPlayerData

- ea: `0x18000fe2c`
- end: `0x1800100db`
- name: `GetMPlayerData`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010578`

## callees

- `0x1800014b0`
- `0x18000222c`
- `0x180002280`
- `0x18000fe2c`
- `0x180010884`
- `0x1800127bc`
- `0x180012934`
- `0x180015234`
- `0x180015de0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ff30`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ff30`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000ffe5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000ffe5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ffd0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ffd0`
- `WINMM!mciSendCommandW` at `0x18000fea2`
- `WINMM!mciSendCommandW` at `0x18000fed5`
- `WINMM!mciSendCommandW` at `0x18000fea2`
- `WINMM!mciSendCommandW` at `0x18000fed5`

## string_xrefs

- `0x18000fe63`: `sysinfo installname`

## pseudocode

```c
HGLOBAL __fastcall GetMPlayerData(__int64 a1)
{
  MCIDEVICEID v2; // ecx
  __int64 v3; // rbx
  MCIDEVICEID v4; // ecx
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  SIZE_T v10; // r14
  HGLOBAL result; // rax
  HGLOBAL v12; // rsi
  char *v13; // r15
  int v14; // eax
  int v15; // ebx
  DWORD_PTR dwParam2[2]; // [rsp+B0h] [rbp-80h] BYREF
  __int128 v17; // [rsp+C0h] [rbp-70h] BYREF
  wchar_t String1[40]; // [rsp+D0h] [rbp-60h] BYREF
  wchar_t String2[40]; // [rsp+120h] [rbp-10h] BYREF
  wchar_t pszDest[264]; // [rsp+170h] [rbp+40h] BYREF

  v17 = 0;
  *(_OWORD *)dwParam2 = 0;
  MCIWndGet(a1, L"sysinfo installname", String1, 40);
  v2 = *(_DWORD *)(a1 + 20);
  HIDWORD(dwParam2[1]) = 6;
  v3 = -1;
  if ( mciSendCommandW(v2, 0x80Bu, 0x100u, (DWORD_PTR)dwParam2)
    || !LODWORD(dwParam2[1])
    || (v4 = *(_DWORD *)(a1 + 20), HIDWORD(dwParam2[1]) = 5, mciSendCommandW(v4, 0x80Bu, 0x100u, (DWORD_PTR)dwParam2))
    || !LODWORD(dwParam2[1]) )
  {
    pszDest[0] = 0;
  }
  else
  {
    StringCchCopyW(pszDest, 0x104u, (STRSAFE_LPCWSTR)(a1 + 244));
    v5 = -1;
    do
      ++v5;
    while ( String1[v5] );
    StringCchCopyNW(String2, 0x28u, pszDest, v5 + 1);
    if ( !lstrcmpiW(String1, String2) )
    {
      v6 = -1;
      do
        ++v6;
      while ( String1[v6] );
      if ( pszDest[v6] == 33 )
        StringCchCopyW(pszDest, 0x104u, (STRSAFE_LPCWSTR)(a1 + 2 * (v6 + 123)));
    }
    NetParseFile(pszDest);
  }
  v7 = -1;
  do
    ++v7;
  while ( pszDest[v7] );
  v8 = -1;
  do
    ++v8;
  while ( String1[v8] );
  v9 = -1;
  do
    ++v9;
  while ( aszMPlayerName[v9] );
  do
    ++v3;
  while ( pszDest[v3] );
  v10 = (int)v3 + (int)v8 + 44 + (int)v9 + (int)v7;
  result = GlobalAlloc(0x2040u, v10);
  v12 = result;
  if ( result )
  {
    v13 = (char *)GlobalLock(result);
    v14 = MCIWndStatus(a1, 6, 0);
    if ( v14 )
    {
      v15 = 48;
      if ( v14 == 3 )
        v15 = 49;
    }
    else
    {
      v15 = 50;
    }
    MCIWndRect(a1, &v17, 0);
    StringCchPrintfA(
      v13,
      v10,
      "%ls%c%ls%c%ls%c%d%c%d%c%d%c%d%c%d%c%ls%c",
      aszMPlayerName,
      0,
      pszDest,
      0,
      String1,
      44,
      v15,
      44,
      0,
      44,
      0,
      44,
      *(_DWORD *)(a1 + 228),
      59,
      HIDWORD(v17) - DWORD1(v17),
      44,
      pszDest,
      0);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18000fe2c  push    rbp
0x18000fe2e  push    rbx
0x18000fe2f  push    rsi
0x18000fe30  push    rdi
0x18000fe31  push    r12
0x18000fe33  push    r13
0x18000fe35  push    r14
0x18000fe37  push    r15
0x18000fe39  lea     rbp, [rsp-268h]
0x18000fe41  sub     rsp, 398h
0x18000fe48  mov     rax, cs:__security_cookie
0x18000fe4f  xor     rax, rsp
0x18000fe52  mov     [rbp+2A0h+var_50], rax
0x18000fe59  xorps   xmm0, xmm0
0x18000fe5c  lea     r8, [rbp+2A0h+String1]
0x18000fe60  xorps   xmm1, xmm1
0x18000fe63  lea     rdx, aSysinfoInstall; "sysinfo installname"
0x18000fe6a  mov     r15d, 28h ; '('
0x18000fe70  mov     rdi, rcx
0x18000fe73  mov     r9d, r15d
0x18000fe76  movups  [rbp+2A0h+var_310], xmm0
0x18000fe7a  movups  xmmword ptr [rbp+2A0h+dwParam2], xmm1
0x18000fe7e  call    MCIWndGet
0x18000fe83  mov     ecx, [rdi+14h]; mciId
0x18000fe86  lea     r9, [rbp+2A0h+dwParam2]; dwParam2
0x18000fe8a  mov     esi, 100h
0x18000fe8f  mov     dword ptr [rbp+2A0h+dwParam2+0Ch], 6
0x18000fe96  mov     r14d, 80Bh
0x18000fe9c  mov     r8d, esi; dwParam1
0x18000fe9f  mov     edx, r14d; uMsg
0x18000fea2  call    cs:__imp_mciSendCommandW
0x18000fea8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000feac  xor     r12d, r12d
0x18000feaf  test    eax, eax
0x18000feb1  jnz     loc_18000FF72
0x18000feb7  cmp     dword ptr [rbp+2A0h+dwParam2+8], r12d
0x18000febb  jz      loc_18000FF72
0x18000fec1  mov     ecx, [rdi+14h]; mciId
0x18000fec4  lea     r9, [rbp+2A0h+dwParam2]; dwParam2
0x18000fec8  mov     r8d, esi; dwParam1
0x18000fecb  mov     dword ptr [rbp+2A0h+dwParam2+0Ch], 5
0x18000fed2  mov     edx, r14d; uMsg
0x18000fed5  call    cs:__imp_mciSendCommandW
0x18000fedb  test    eax, eax
0x18000fedd  jnz     loc_18000FF72
0x18000fee3  cmp     dword ptr [rbp+2A0h+dwParam2+8], r12d
0x18000fee7  jz      loc_18000FF72
0x18000feed  mov     esi, 104h
0x18000fef2  lea     r8, [rdi+0F4h]; pszSrc
0x18000fef9  mov     edx, esi; cchDest
0x18000fefb  lea     rcx, [rbp+2A0h+pszDest]; pszDest
0x18000feff  call    StringCchCopyW
0x18000ff04  mov     r9, rbx
0x18000ff07  lea     r11, [rbp+2A0h+String1]
0x18000ff0b  inc     r9
0x18000ff0e  cmp     [r11+r9*2], r12w
0x18000ff13  jnz     short loc_18000FF0B
0x18000ff15  inc     r9; cchToCopy
0x18000ff18  lea     r8, [rbp+2A0h+pszDest]; pszSrc
0x18000ff1c  mov     rdx, r15; cchDest
0x18000ff1f  lea     rcx, [rbp+2A0h+String2]; pszDest
0x18000ff23  call    StringCchCopyNW
0x18000ff28  lea     rdx, [rbp+2A0h+String2]; lpString2
0x18000ff2c  lea     rcx, [rbp+2A0h+String1]; lpString1
0x18000ff30  call    cs:__imp_lstrcmpiW
0x18000ff36  test    eax, eax
0x18000ff38  jnz     short loc_18000FF67
0x18000ff3a  lea     rcx, [rbp+2A0h+String1]
0x18000ff3e  mov     rax, rbx
0x18000ff41  inc     rax
0x18000ff44  cmp     [rcx+rax*2], r12w
0x18000ff49  jnz     short loc_18000FF41
0x18000ff4b  cmp     [rbp+rax*2+2A0h+pszDest], 21h ; '!'
0x18000ff51  jnz     short loc_18000FF67
0x18000ff53  add     rax, 7Bh ; '{'
0x18000ff57  lea     rcx, [rbp+2A0h+pszDest]; pszDest
0x18000ff5b  mov     rdx, rsi; cchDest
0x18000ff5e  lea     r8, [rdi+rax*2]; pszSrc
0x18000ff62  call    StringCchCopyW
0x18000ff67  lea     rcx, [rbp+2A0h+pszDest]; pszDest
0x18000ff6b  call    NetParseFile
0x18000ff70  jmp     short loc_18000FF77
0x18000ff72  mov     [rbp+2A0h+pszDest], r12w
0x18000ff77  lea     rcx, [rbp+2A0h+pszDest]
0x18000ff7b  mov     rax, rbx
0x18000ff7e  inc     rax
0x18000ff81  cmp     [rcx+rax*2], r12w
0x18000ff86  jnz     short loc_18000FF7E
0x18000ff88  lea     rdx, [rbp+2A0h+String1]
0x18000ff8c  mov     rcx, rbx
0x18000ff8f  inc     rcx
0x18000ff92  cmp     [rdx+rcx*2], r12w
0x18000ff97  jnz     short loc_18000FF8F
0x18000ff99  lea     r13, aszMPlayerName; "MPlayer"
0x18000ffa0  mov     rdx, rbx
0x18000ffa3  inc     rdx
0x18000ffa6  cmp     [r13+rdx*2+0], r12w
0x18000ffac  jnz     short loc_18000FFA3
0x18000ffae  lea     r8, [rbp+2A0h+pszDest]
0x18000ffb2  inc     rbx
0x18000ffb5  cmp     [r8+rbx*2], r12w
0x18000ffba  jnz     short loc_18000FFB2
0x18000ffbc  add     eax, edx
0x18000ffbe  add     ecx, 2Ch ; ','
0x18000ffc1  add     eax, ecx
0x18000ffc3  mov     ecx, 2040h; uFlags
0x18000ffc8  add     eax, ebx
0x18000ffca  movsxd  r14, eax
0x18000ffcd  mov     rdx, r14; dwBytes
0x18000ffd0  call    cs:__imp_GlobalAlloc
0x18000ffd6  mov     rsi, rax
0x18000ffd9  test    rax, rax
0x18000ffdc  jz      loc_1800100B8
0x18000ffe2  mov     rcx, rsi; hMem
0x18000ffe5  call    cs:__imp_GlobalLock
0x18000ffeb  xor     r8d, r8d
0x18000ffee  mov     rcx, rdi
0x18000fff1  mov     r15, rax
0x18000fff4  lea     edx, [r8+6]
0x18000fff8  call    MCIWndStatus
0x18000fffd  test    eax, eax
0x18000ffff  jz      short loc_180010010
0x180010001  mov     ebx, 30h ; '0'
0x180010006  cmp     eax, 3
0x180010009  jnz     short loc_180010015
0x18001000b  lea     ebx, [rax+2Eh]
0x18001000e  jmp     short loc_180010015
0x180010010  mov     ebx, 32h ; '2'
0x180010015  xor     r8d, r8d
0x180010018  lea     rdx, [rbp+2A0h+var_310]
0x18001001c  mov     rcx, rdi
0x18001001f  call    MCIWndRect
0x180010024  mov     eax, dword ptr [rbp+2A0h+var_310+0Ch]
0x180010027  lea     rcx, [rbp+2A0h+pszDest]
0x18001002b  sub     eax, dword ptr [rbp+2A0h+var_310+4]
0x18001002e  lea     r8, aLsCLsCLsCDCDCD; "%ls%c%ls%c%ls%c%d%c%d%c%d%c%d%c%d%c%ls%"...
0x180010035  mov     [rsp+3D0h+var_330], r12
0x18001003d  mov     r9, r13
0x180010040  mov     [rsp+3D0h+var_338], rcx
0x180010048  mov     rdx, r14; cchDest
0x18001004b  mov     ecx, 2Ch ; ','
0x180010050  mov     [rsp+3D0h+var_340], ecx
0x180010057  mov     [rsp+3D0h+var_348], eax
0x18001005e  mov     eax, [rdi+0E4h]
0x180010064  mov     [rsp+3D0h+var_350], 3Bh ; ';'
0x18001006f  mov     [rsp+3D0h+var_358], eax
0x180010073  lea     rax, [rbp+2A0h+String1]
0x180010077  mov     [rsp+3D0h+var_360], ecx
0x18001007b  mov     [rsp+3D0h+var_368], r12
0x180010080  mov     [rsp+3D0h+var_370], ecx
0x180010084  mov     [rsp+3D0h+var_378], r12
0x180010089  mov     [rsp+3D0h+var_380], ecx
0x18001008d  mov     [rsp+3D0h+var_388], ebx
0x180010091  mov     [rsp+3D0h+var_390], ecx
0x180010095  mov     rcx, r15; pszDest
0x180010098  mov     [rsp+3D0h+var_398], rax
0x18001009d  lea     rax, [rbp+2A0h+pszDest]
0x1800100a1  mov     [rsp+3D0h+var_3A0], r12
0x1800100a6  mov     [rsp+3D0h+var_3A8], rax
0x1800100ab  mov     [rsp+3D0h+var_3B0], r12
0x1800100b0  call    StringCchPrintfA
0x1800100b5  mov     rax, rsi
0x1800100b8  mov     rcx, [rbp+2A0h+var_50]
0x1800100bf  xor     rcx, rsp; StackCookie
0x1800100c2  call    __security_check_cookie
0x1800100c7  add     rsp, 398h
0x1800100ce  pop     r15
0x1800100d0  pop     r14
0x1800100d2  pop     r13
0x1800100d4  pop     r12
0x1800100d6  pop     rdi
0x1800100d7  pop     rsi
0x1800100d8  pop     rbx
0x1800100d9  pop     rbp
0x1800100da  retn
```
