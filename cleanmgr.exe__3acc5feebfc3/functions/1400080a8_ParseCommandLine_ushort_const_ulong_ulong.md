# ParseCommandLine(ushort const *,ulong *,ulong *)

- ea: `0x1400080a8`
- end: `0x1400083c0`
- name: `?ParseCommandLine@@YAHPEBGPEAK1@Z`
- size: `792`
- prototype: `__int64 __fastcall(PCWSTR pszFirst, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009d34`

## callees

- `0x1400029a0`
- `0x140007b00`
- `0x1400080a8`

## import_xrefs

- `SHLWAPI!StrToIntW` at `0x140008128`
- `SHLWAPI!StrToIntW` at `0x140008190`
- `SHLWAPI!StrToIntW` at `0x140008222`
- `SHLWAPI!StrToIntW` at `0x140008128`
- `SHLWAPI!StrToIntW` at `0x140008190`
- `SHLWAPI!StrToIntW` at `0x140008222`
- `SHLWAPI!StrStrIW` at `0x1400080dc`
- `SHLWAPI!StrStrIW` at `0x140008142`
- `SHLWAPI!StrStrIW` at `0x1400081a9`
- `SHLWAPI!StrStrIW` at `0x1400081d4`
- `SHLWAPI!StrStrIW` at `0x140008240`
- `SHLWAPI!StrStrIW` at `0x140008260`
- `SHLWAPI!StrStrIW` at `0x14000827d`
- `SHLWAPI!StrStrIW` at `0x14000829a`
- `SHLWAPI!StrStrIW` at `0x1400082b7`
- `SHLWAPI!StrStrIW` at `0x1400082d4`
- `SHLWAPI!StrStrIW` at `0x1400082f9`
- `SHLWAPI!StrStrIW` at `0x140008312`
- `SHLWAPI!StrStrIW` at `0x14000832b`
- `SHLWAPI!StrStrIW` at `0x140008340`
- `SHLWAPI!StrStrIW` at `0x140008355`
- `SHLWAPI!StrStrIW` at `0x14000836a`
- `SHLWAPI!StrStrIW` at `0x14000837f`
- `SHLWAPI!StrStrIW` at `0x140008394`
- `SHLWAPI!StrStrIW` at `0x1400080dc`
- `SHLWAPI!StrStrIW` at `0x140008142`
- `SHLWAPI!StrStrIW` at `0x1400081a9`
- `SHLWAPI!StrStrIW` at `0x1400081d4`
- `SHLWAPI!StrStrIW` at `0x140008240`
- `SHLWAPI!StrStrIW` at `0x140008260`
- `SHLWAPI!StrStrIW` at `0x14000827d`
- `SHLWAPI!StrStrIW` at `0x14000829a`
- `SHLWAPI!StrStrIW` at `0x1400082b7`
- `SHLWAPI!StrStrIW` at `0x1400082d4`
- `SHLWAPI!StrStrIW` at `0x1400082f9`
- `SHLWAPI!StrStrIW` at `0x140008312`
- `SHLWAPI!StrStrIW` at `0x14000832b`
- `SHLWAPI!StrStrIW` at `0x140008340`
- `SHLWAPI!StrStrIW` at `0x140008355`
- `SHLWAPI!StrStrIW` at `0x14000836a`
- `SHLWAPI!StrStrIW` at `0x14000837f`
- `SHLWAPI!StrStrIW` at `0x140008394`

## pseudocode

```c
__int64 __fastcall ParseCommandLine(PCWSTR pszFirst, unsigned int *a2, unsigned int *a3)
{
  PWSTR v6; // rax
  unsigned int v7; // ebx
  WCHAR *v8; // rdx
  WCHAR v9; // cx
  int v10; // r8d
  __int64 v11; // rax
  PWSTR v12; // rax
  WCHAR *v13; // rdx
  WCHAR v14; // cx
  int v15; // r8d
  __int64 v16; // rax
  PWSTR v17; // rax
  WCHAR *v18; // rdx
  WCHAR v19; // cx
  int v20; // r8d
  __int64 v21; // rax
  WCHAR pszSrc[4]; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)pszSrc = 0;
  *a3 = 0;
  v6 = StrStrIW(pszFirst, L"SAGESET");
  if ( v6 )
  {
    v7 = 1;
    if ( v6[7] == 58 )
    {
      v8 = v6 + 8;
      v9 = v6[8];
      if ( v9 )
      {
        v10 = 0;
        do
        {
          if ( v9 == 32 )
            break;
          if ( v10 >= 4 )
            break;
          v11 = v10;
          ++v8;
          ++v10;
          pszSrc[v11] = v9;
          v9 = *v8;
        }
        while ( *v8 );
      }
      *a3 = StrToIntW(pszSrc);
    }
    *a2 = 1;
    return v7;
  }
  v12 = StrStrIW(pszFirst, L"SAGERUN");
  if ( v12 )
  {
    v7 = 1;
    if ( v12[7] == 58 )
    {
      v13 = v12 + 8;
      v14 = v12[8];
      if ( v14 )
      {
        v15 = 0;
        do
        {
          if ( v14 == 32 )
            break;
          if ( v15 >= 4 )
            break;
          v16 = v15;
          ++v13;
          ++v15;
          pszSrc[v16] = v14;
          v14 = *v13;
        }
        while ( *v13 );
      }
      *a3 = StrToIntW(pszSrc);
    }
    *a2 = 2;
    if ( StrStrIW(pszFirst, L"NOWINDOW") || !(unsigned int)IsInteractiveSession() )
      *a2 |= 0x1000u;
    return v7;
  }
  v17 = StrStrIW(pszFirst, L"TUNEUP");
  if ( v17 )
  {
    v7 = 1;
    if ( v17[6] == 58 )
    {
      v18 = v17 + 7;
      v19 = v17[7];
      if ( v19 )
      {
        v20 = 0;
        do
        {
          if ( v19 == 32 )
            break;
          if ( v20 >= 4 )
            break;
          v21 = v20;
          ++v18;
          ++v20;
          pszSrc[v21] = v19;
          v19 = *v18;
        }
        while ( *v18 );
      }
      *a3 = StrToIntW(pszSrc);
    }
    *a2 = 5;
    return v7;
  }
  if ( StrStrIW(pszFirst, L"VERYLOWDISK") )
  {
    *a2 = 18;
    return 1;
  }
  if ( StrStrIW(pszFirst, L"LOWDISK") )
  {
    *a2 = 8;
    return 1;
  }
  if ( StrStrIW(pszFirst, L"SETUP") )
  {
    *a2 = 34;
    return 1;
  }
  if ( StrStrIW(pszFirst, L"AUTOCLEANSTORAGESENSE") )
  {
    *a2 = 2560;
    return 1;
  }
  if ( StrStrIW(pszFirst, L"AUTOCLEAN") )
  {
    *a2 = 512;
    return 1;
  }
  if ( StrStrIW(pszFirst, L"AUTORUNALL") )
  {
    *a2 = 1536;
    return 1;
  }
  if ( StrStrIW(pszFirst, L"/HELP") )
    return 0;
  if ( StrStrIW(pszFirst, L"/H") )
    return 0;
  if ( StrStrIW(pszFirst, L"/h") )
    return 0;
  if ( StrStrIW(pszFirst, L"/?") )
    return 0;
  if ( StrStrIW(pszFirst, L"-?") )
    return 0;
  if ( StrStrIW(pszFirst, L"/USAGE") )
    return 0;
  if ( StrStrIW(pszFirst, L"-H") )
    return 0;
  v7 = 1;
  if ( StrStrIW(pszFirst, L"-h") )
    return 0;
  return v7;
}

```

## disassembly

```asm
0x1400080a8  push    rbx
0x1400080aa  push    rbp
0x1400080ab  push    rsi
0x1400080ac  push    rdi
0x1400080ad  push    r14
0x1400080af  sub     rsp, 30h
0x1400080b3  mov     rax, cs:__security_cookie
0x1400080ba  xor     rax, rsp
0x1400080bd  mov     [rsp+58h+var_30], rax
0x1400080c2  mov     rsi, rdx
0x1400080c5  xor     ebp, ebp
0x1400080c7  lea     rdx, pszSrch; "SAGESET"
0x1400080ce  mov     qword ptr [rsp+58h+pszSrc], rbp
0x1400080d3  mov     [r8], ebp
0x1400080d6  mov     r14, r8
0x1400080d9  mov     rdi, rcx
0x1400080dc  call    cs:__imp_StrStrIW
0x1400080e2  test    rax, rax
0x1400080e5  jz      short loc_140008138
0x1400080e7  cmp     word ptr [rax+0Eh], 3Ah ; ':'
0x1400080ec  lea     ebx, [rbp+1]
0x1400080ef  jnz     short loc_140008131
0x1400080f1  lea     rdx, [rax+10h]
0x1400080f5  movzx   ecx, word ptr [rdx]
0x1400080f8  test    cx, cx
0x1400080fb  jz      short loc_140008123
0x1400080fd  mov     r8d, ebp
0x140008100  cmp     cx, 20h ; ' '
0x140008104  jz      short loc_140008123
0x140008106  cmp     r8d, 4
0x14000810a  jge     short loc_140008123
0x14000810c  movsxd  rax, r8d
0x14000810f  add     rdx, 2
0x140008113  add     r8d, ebx
0x140008116  mov     [rsp+rax*2+58h+pszSrc], cx
0x14000811b  movzx   ecx, word ptr [rdx]
0x14000811e  test    cx, cx
0x140008121  jnz     short loc_140008100
0x140008123  lea     rcx, [rsp+58h+pszSrc]; pszSrc
0x140008128  call    cs:__imp_StrToIntW
0x14000812e  mov     [r14], eax
0x140008131  mov     [rsi], ebx
0x140008133  jmp     loc_1400083A6
0x140008138  lea     rdx, aSagerun; "SAGERUN"
0x14000813f  mov     rcx, rdi; pszFirst
0x140008142  call    cs:__imp_StrStrIW
0x140008148  test    rax, rax
0x14000814b  jz      short loc_1400081CA
0x14000814d  cmp     word ptr [rax+0Eh], 3Ah ; ':'
0x140008152  mov     ebx, 1
0x140008157  jnz     short loc_140008199
0x140008159  lea     rdx, [rax+10h]
0x14000815d  movzx   ecx, word ptr [rdx]
0x140008160  test    cx, cx
0x140008163  jz      short loc_14000818B
0x140008165  mov     r8d, ebp
0x140008168  cmp     cx, 20h ; ' '
0x14000816c  jz      short loc_14000818B
0x14000816e  cmp     r8d, 4
0x140008172  jge     short loc_14000818B
0x140008174  movsxd  rax, r8d
0x140008177  add     rdx, 2
0x14000817b  add     r8d, ebx
0x14000817e  mov     [rsp+rax*2+58h+pszSrc], cx
0x140008183  movzx   ecx, word ptr [rdx]
0x140008186  test    cx, cx
0x140008189  jnz     short loc_140008168
0x14000818b  lea     rcx, [rsp+58h+pszSrc]; pszSrc
0x140008190  call    cs:__imp_StrToIntW
0x140008196  mov     [r14], eax
0x140008199  lea     rdx, aNowindow; "NOWINDOW"
0x1400081a0  mov     dword ptr [rsi], 2
0x1400081a6  mov     rcx, rdi; pszFirst
0x1400081a9  call    cs:__imp_StrStrIW
0x1400081af  test    rax, rax
0x1400081b2  jnz     short loc_1400081C1
0x1400081b4  call    ?IsInteractiveSession@@YAHXZ; IsInteractiveSession(void)
0x1400081b9  test    eax, eax
0x1400081bb  jnz     loc_1400083A6
0x1400081c1  bts     dword ptr [rsi], 0Ch
0x1400081c5  jmp     loc_1400083A6
0x1400081ca  lea     rdx, aTuneup; "TUNEUP"
0x1400081d1  mov     rcx, rdi; pszFirst
0x1400081d4  call    cs:__imp_StrStrIW
0x1400081da  test    rax, rax
0x1400081dd  jz      short loc_140008236
0x1400081df  cmp     word ptr [rax+0Ch], 3Ah ; ':'
0x1400081e4  mov     ebx, 1
0x1400081e9  jnz     short loc_14000822B
0x1400081eb  lea     rdx, [rax+0Eh]
0x1400081ef  movzx   ecx, word ptr [rdx]
0x1400081f2  test    cx, cx
0x1400081f5  jz      short loc_14000821D
0x1400081f7  mov     r8d, ebp
0x1400081fa  cmp     cx, 20h ; ' '
0x1400081fe  jz      short loc_14000821D
0x140008200  cmp     r8d, 4
0x140008204  jge     short loc_14000821D
0x140008206  movsxd  rax, r8d
0x140008209  add     rdx, 2
0x14000820d  add     r8d, ebx
0x140008210  mov     [rsp+rax*2+58h+pszSrc], cx
0x140008215  movzx   ecx, word ptr [rdx]
0x140008218  test    cx, cx
0x14000821b  jnz     short loc_1400081FA
0x14000821d  lea     rcx, [rsp+58h+pszSrc]; pszSrc
0x140008222  call    cs:__imp_StrToIntW
0x140008228  mov     [r14], eax
0x14000822b  mov     dword ptr [rsi], 5
0x140008231  jmp     loc_1400083A6
0x140008236  lea     rdx, aVerylowdisk; "VERYLOWDISK"
0x14000823d  mov     rcx, rdi; pszFirst
0x140008240  call    cs:__imp_StrStrIW
0x140008246  test    rax, rax
0x140008249  jz      short loc_140008256
0x14000824b  mov     dword ptr [rsi], 12h
0x140008251  jmp     loc_1400082E5
0x140008256  lea     rdx, aLowdisk; "LOWDISK"
0x14000825d  mov     rcx, rdi; pszFirst
0x140008260  call    cs:__imp_StrStrIW
0x140008266  test    rax, rax
0x140008269  jz      short loc_140008273
0x14000826b  mov     dword ptr [rsi], 8
0x140008271  jmp     short loc_1400082E5
0x140008273  lea     rdx, aSetup; "SETUP"
0x14000827a  mov     rcx, rdi; pszFirst
0x14000827d  call    cs:__imp_StrStrIW
0x140008283  test    rax, rax
0x140008286  jz      short loc_140008290
0x140008288  mov     dword ptr [rsi], 22h ; '"'
0x14000828e  jmp     short loc_1400082E5
0x140008290  lea     rdx, aAutocleanstora; "AUTOCLEANSTORAGESENSE"
0x140008297  mov     rcx, rdi; pszFirst
0x14000829a  call    cs:__imp_StrStrIW
0x1400082a0  test    rax, rax
0x1400082a3  jz      short loc_1400082AD
0x1400082a5  mov     dword ptr [rsi], 0A00h
0x1400082ab  jmp     short loc_1400082E5
0x1400082ad  lea     rdx, aAutoclean; "AUTOCLEAN"
0x1400082b4  mov     rcx, rdi; pszFirst
0x1400082b7  call    cs:__imp_StrStrIW
0x1400082bd  test    rax, rax
0x1400082c0  jz      short loc_1400082CA
0x1400082c2  mov     dword ptr [rsi], 200h
0x1400082c8  jmp     short loc_1400082E5
0x1400082ca  lea     rdx, aAutorunall; "AUTORUNALL"
0x1400082d1  mov     rcx, rdi; pszFirst
0x1400082d4  call    cs:__imp_StrStrIW
0x1400082da  test    rax, rax
0x1400082dd  jz      short loc_1400082EF
0x1400082df  mov     dword ptr [rsi], 600h
0x1400082e5  mov     ebx, 1
0x1400082ea  jmp     loc_1400083A6
0x1400082ef  lea     rdx, aHelp; "/HELP"
0x1400082f6  mov     rcx, rdi; pszFirst
0x1400082f9  call    cs:__imp_StrStrIW
0x1400082ff  test    rax, rax
0x140008302  jnz     loc_1400083A4
0x140008308  lea     rdx, asc_14001A3C4; "/H"
0x14000830f  mov     rcx, rdi; pszFirst
0x140008312  call    cs:__imp_StrStrIW
0x140008318  test    rax, rax
0x14000831b  jnz     loc_1400083A4
0x140008321  lea     rdx, asc_14001A3CC; "/h"
0x140008328  mov     rcx, rdi; pszFirst
0x14000832b  call    cs:__imp_StrStrIW
0x140008331  test    rax, rax
0x140008334  jnz     short loc_1400083A4
0x140008336  lea     rdx, asc_14001A3D4; "/?"
0x14000833d  mov     rcx, rdi; pszFirst
0x140008340  call    cs:__imp_StrStrIW
0x140008346  test    rax, rax
0x140008349  jnz     short loc_1400083A4
0x14000834b  lea     rdx, asc_14001A3DC; "-?"
0x140008352  mov     rcx, rdi; pszFirst
0x140008355  call    cs:__imp_StrStrIW
0x14000835b  test    rax, rax
0x14000835e  jnz     short loc_1400083A4
0x140008360  lea     rdx, aUsage_0; "/USAGE"
0x140008367  mov     rcx, rdi; pszFirst
0x14000836a  call    cs:__imp_StrStrIW
0x140008370  test    rax, rax
0x140008373  jnz     short loc_1400083A4
0x140008375  lea     rdx, asc_14001A3F8; "-H"
0x14000837c  mov     rcx, rdi; pszFirst
0x14000837f  call    cs:__imp_StrStrIW
0x140008385  test    rax, rax
0x140008388  jnz     short loc_1400083A4
0x14000838a  lea     rdx, asc_14001A400; "-h"
0x140008391  mov     rcx, rdi; pszFirst
0x140008394  call    cs:__imp_StrStrIW
0x14000839a  mov     ebx, 1
0x14000839f  test    rax, rax
0x1400083a2  jz      short loc_1400083A6
0x1400083a4  mov     ebx, ebp
0x1400083a6  mov     eax, ebx
0x1400083a8  mov     rcx, [rsp+58h+var_30]
0x1400083ad  xor     rcx, rsp; StackCookie
0x1400083b0  call    __security_check_cookie
0x1400083b5  add     rsp, 30h
0x1400083b9  pop     r14
0x1400083bb  pop     rdi
0x1400083bc  pop     rsi
0x1400083bd  pop     rbp
0x1400083be  pop     rbx
0x1400083bf  retn
```
