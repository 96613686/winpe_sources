# NPGetUniversalName

- ea: `0x180008150`
- end: `0x180008548`
- name: `NPGetUniversalName`
- size: `1016`
- prototype: `DWORD __stdcall(LPCWSTR lpLocalPath, DWORD dwInfoLevel, LPVOID lpBuffer, LPDWORD lpBufferSize)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180002508`
- `0x180002538`
- `0x180006890`
- `0x180008150`
- `0x180008d00`
- `0x180008f88`
- `0x1800090dc`
- `0x180009144`
- `0x1800091f4`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000839f`
- `msvcrt!_snwprintf_s` at `0x18000839f`
- `msvcrt!wcschr` at `0x1800082c3`
- `msvcrt!wcschr` at `0x1800082c3`
- `msvcrt!wcsncpy_s` at `0x1800082ab`
- `msvcrt!wcsncpy_s` at `0x1800083b8`
- `msvcrt!wcsncpy_s` at `0x1800082ab`
- `msvcrt!wcsncpy_s` at `0x1800083b8`

## pseudocode

```c
DWORD __stdcall NPGetUniversalName(LPCWSTR lpLocalPath, DWORD dwInfoLevel, LPVOID lpBuffer, LPDWORD lpBufferSize)
{
  int v8; // r8d
  wchar_t v10; // r14
  wchar_t *v11; // rax
  wchar_t *v12; // rbx
  DWORD v13; // eax
  int v14; // r8d
  DWORD v15; // edi
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  DWORD v19; // edi
  __int64 v20; // r8
  __int64 *v21; // r8
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  DWORD nBufferLen; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t *v24; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+40h] [rbp-C0h]
  wchar_t RemoteName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Buffer[264]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t Destination[264]; // [rsp+470h] [rbp+370h] BYREF

  memset_0(RemoteName, 0, 0x208u);
  memset_0(Destination, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  nBufferLen = 260;
  v25 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, v8, (_DWORD)lpLocalPath, dwInfoLevel);
  if ( (int)NfsNpIsClientRunning(&v22) >= 0 && v22 )
  {
    if ( dwInfoLevel - 1 <= 1 )
    {
      if ( lpBufferSize )
      {
        v10 = 0;
        wcsncpy_s(Destination, 0x104u, lpLocalPath, 0x103u);
        v11 = wcschr(Destination, 0x3Au);
        v12 = v11;
        if ( v11 )
        {
          v12 = v11 + 1;
          v10 = v11[1];
          v11[1] = 0;
        }
        v13 = NPGetConnection(Destination, RemoteName, &nBufferLen);
        v15 = v13;
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 246, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v13);
          return v15;
        }
        else
        {
          if ( v12 )
            *v12 = v10;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, v14, (_DWORD)v12, (__int64)RemoteName);
          if ( v12 )
            _snwprintf_s(Buffer, 0x104u, 0x103u, L"%s%s", RemoteName, v12);
          else
            wcsncpy_s(Buffer, 0x104u, RemoteName, 0x103u);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, Buffer);
            v16 = WPP_GLOBAL_Control;
          }
          v17 = -1;
          v18 = -1;
          do
            ++v18;
          while ( Buffer[v18] );
          if ( dwInfoLevel == 1 )
          {
            v19 = 2 * v18 + 10;
          }
          else
          {
            v20 = -1;
            do
              ++v20;
            while ( RemoteName[v20] );
            v19 = 2 * (v20 + v18) + 28;
            if ( v12 )
            {
              do
                ++v17;
              while ( v12[v17] );
              v19 += 2 * v17 + 2;
            }
          }
          if ( *lpBufferSize >= v19 )
          {
            v24 = Buffer;
            if ( dwInfoLevel != 1 )
            {
              *((_QWORD *)&v25 + 1) = v12;
              *(_QWORD *)&v25 = RemoteName;
            }
            v21 = &UniversalNameInfoStrings;
            if ( dwInfoLevel != 1 )
              v21 = RemoteNameInfoStrings;
            PackString(&v24, lpBuffer, v21, (char *)lpBuffer + *lpBufferSize);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
            return 0;
          }
          else
          {
            if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
              WPP_SF_d(v16[2], 249, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v19);
            *lpBufferSize = v19;
            return 234;
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
        return 487;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          244,
          &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
          dwInfoLevel);
      return 124;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 243, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    return 1222;
  }
}

```

## disassembly

```asm
0x180008150  push    rbp
0x180008152  push    rbx
0x180008153  push    rsi
0x180008154  push    rdi
0x180008155  push    r12
0x180008157  push    r13
0x180008159  push    r14
0x18000815b  push    r15
0x18000815d  lea     rbp, [rsp-598h]
0x180008165  sub     rsp, 698h
0x18000816c  mov     rax, cs:__security_cookie
0x180008173  xor     rax, rsp
0x180008176  mov     [rbp+5D0h+var_50], rax
0x18000817d  mov     r12, r8
0x180008180  mov     esi, edx
0x180008182  mov     rbx, rcx
0x180008185  mov     edi, 208h
0x18000818a  mov     r8d, edi; Size
0x18000818d  lea     rcx, [rsp+6D0h+RemoteName]; void *
0x180008192  xor     edx, edx; Val
0x180008194  mov     r15, r9
0x180008197  call    memset_0
0x18000819c  mov     r8d, edi; Size
0x18000819f  lea     rcx, [rbp+5D0h+Destination]; void *
0x1800081a6  xor     edx, edx; Val
0x1800081a8  call    memset_0
0x1800081ad  mov     r8d, edi; Size
0x1800081b0  lea     rcx, [rbp+5D0h+Buffer]; void *
0x1800081b7  xor     edx, edx; Val
0x1800081b9  call    memset_0
0x1800081be  xorps   xmm0, xmm0
0x1800081c1  mov     [rsp+6D0h+nBufferLen], 104h
0x1800081c9  xor     r13d, r13d
0x1800081cc  movdqu  [rsp+6D0h+var_690], xmm0
0x1800081d2  mov     [rsp+6D0h+var_6A0], r13d
0x1800081d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081de  lea     rdi, WPP_GLOBAL_Control
0x1800081e5  cmp     rcx, rdi
0x1800081e8  jz      short loc_180008205
0x1800081ea  test    byte ptr [rcx+1Ch], 1
0x1800081ee  jz      short loc_180008205
0x1800081f0  mov     rcx, [rcx+10h]
0x1800081f4  mov     edx, 0F2h
0x1800081f9  mov     r9, rbx
0x1800081fc  mov     dword ptr [rsp+6D0h+var_6B0], esi
0x180008200  call    WPP_SF_Sd
0x180008205  lea     rcx, [rsp+6D0h+var_6A0]
0x18000820a  call    NfsNpIsClientRunning
0x18000820f  test    eax, eax
0x180008211  js      loc_1800084F8
0x180008217  cmp     [rsp+6D0h+var_6A0], r13d
0x18000821c  jz      loc_1800084F8
0x180008222  lea     eax, [rsi-1]
0x180008225  cmp     eax, 1
0x180008228  jbe     short loc_18000825E
0x18000822a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008231  cmp     rcx, rdi
0x180008234  jz      short loc_180008254
0x180008236  test    byte ptr [rcx+1Ch], 2
0x18000823a  jz      short loc_180008254
0x18000823c  mov     rcx, [rcx+10h]
0x180008240  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008247  mov     edx, 0F4h
0x18000824c  mov     r9d, esi
0x18000824f  call    WPP_SF_d
0x180008254  mov     eax, 7Ch ; '|'
0x180008259  jmp     loc_180008524
0x18000825e  test    r15, r15
0x180008261  jnz     short loc_180008294
0x180008263  mov     rcx, cs:WPP_GLOBAL_Control
0x18000826a  cmp     rcx, rdi
0x18000826d  jz      short loc_18000828A
0x18000826f  test    byte ptr [rcx+1Ch], 2
0x180008273  jz      short loc_18000828A
0x180008275  mov     rcx, [rcx+10h]
0x180008279  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008280  mov     edx, 0F5h
0x180008285  call    WPP_SF_
0x18000828a  mov     eax, 1E7h
0x18000828f  jmp     loc_180008524
0x180008294  mov     r9d, 103h; MaxCount
0x18000829a  lea     rcx, [rbp+5D0h+Destination]; Destination
0x1800082a1  mov     r8, rbx; Source
0x1800082a4  mov     r14d, r13d
0x1800082a7  lea     edx, [r9+1]; SizeInWords
0x1800082ab  call    cs:__imp_wcsncpy_s
0x1800082b2  nop     dword ptr [rax+rax+00h]
0x1800082b7  mov     edx, 3Ah ; ':'; Ch
0x1800082bc  lea     rcx, [rbp+5D0h+Destination]; Str
0x1800082c3  call    cs:__imp_wcschr
0x1800082ca  nop     dword ptr [rax+rax+00h]
0x1800082cf  mov     rbx, rax
0x1800082d2  test    rax, rax
0x1800082d5  jz      short loc_1800082E3
0x1800082d7  add     rbx, 2
0x1800082db  movzx   r14d, word ptr [rbx]
0x1800082df  mov     [rbx], r13w
0x1800082e3  lea     r8, [rsp+6D0h+nBufferLen]; lpnBufferLen
0x1800082e8  lea     rdx, [rsp+6D0h+RemoteName]; lpRemoteName
0x1800082ed  lea     rcx, [rbp+5D0h+Destination]; lpLocalName
0x1800082f4  call    NPGetConnection
0x1800082f9  mov     edi, eax
0x1800082fb  test    eax, eax
0x1800082fd  jz      short loc_180008337
0x1800082ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180008306  lea     r14, WPP_GLOBAL_Control
0x18000830d  cmp     rcx, r14
0x180008310  jz      short loc_180008330
0x180008312  test    byte ptr [rcx+1Ch], 2
0x180008316  jz      short loc_180008330
0x180008318  mov     rcx, [rcx+10h]
0x18000831c  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008323  mov     edx, 0F6h
0x180008328  mov     r9d, eax
0x18000832b  call    WPP_SF_d
0x180008330  mov     eax, edi
0x180008332  jmp     loc_180008524
0x180008337  test    rbx, rbx
0x18000833a  jz      short loc_180008340
0x18000833c  mov     [rbx], r14w
0x180008340  mov     rcx, cs:WPP_GLOBAL_Control
0x180008347  lea     r14, WPP_GLOBAL_Control
0x18000834e  cmp     rcx, r14
0x180008351  jz      short loc_180008374
0x180008353  test    byte ptr [rcx+1Ch], 8
0x180008357  jz      short loc_180008374
0x180008359  mov     rcx, [rcx+10h]
0x18000835d  lea     rax, [rsp+6D0h+RemoteName]
0x180008362  mov     edx, 0F7h
0x180008367  mov     [rsp+6D0h+var_6B0], rax
0x18000836c  mov     r9, rbx
0x18000836f  call    WPP_SF_SS
0x180008374  lea     rcx, [rbp+5D0h+Buffer]; Destination
0x18000837b  mov     edx, 104h; SizeInWords
0x180008380  test    rbx, rbx
0x180008383  jz      short loc_1800083AD
0x180008385  lea     rax, [rsp+6D0h+RemoteName]
0x18000838a  mov     [rsp+6D0h+var_6A8], rbx
0x18000838f  lea     r9, aSS_0; "%s%s"
0x180008396  mov     [rsp+6D0h+var_6B0], rax
0x18000839b  lea     r8d, [rdx-1]; MaxCount
0x18000839f  call    cs:__imp__snwprintf_s
0x1800083a6  nop     dword ptr [rax+rax+00h]
0x1800083ab  jmp     short loc_1800083C4
0x1800083ad  mov     r9d, 103h; MaxCount
0x1800083b3  lea     r8, [rsp+6D0h+RemoteName]; Source
0x1800083b8  call    cs:__imp_wcsncpy_s
0x1800083bf  nop     dword ptr [rax+rax+00h]
0x1800083c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083cb  cmp     rcx, r14
0x1800083ce  jz      short loc_1800083F9
0x1800083d0  test    byte ptr [rcx+1Ch], 8
0x1800083d4  jz      short loc_1800083F9
0x1800083d6  mov     rcx, [rcx+10h]
0x1800083da  lea     r9, [rbp+5D0h+Buffer]
0x1800083e1  mov     edx, 0F8h
0x1800083e6  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800083ed  call    WPP_SF_S
0x1800083f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083f9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800083fd  lea     r8, [rbp+5D0h+Buffer]
0x180008404  mov     rax, rdx
0x180008407  inc     rax
0x18000840a  cmp     [r8+rax*2], r13w
0x18000840f  jnz     short loc_180008407
0x180008411  cmp     esi, 1
0x180008414  jnz     short loc_18000841F
0x180008416  lea     edi, ds:0Ah[rax*2]
0x18000841d  jmp     short loc_180008450
0x18000841f  lea     r9, [rsp+6D0h+RemoteName]
0x180008424  mov     r8, rdx
0x180008427  inc     r8
0x18000842a  cmp     [r9+r8*2], r13w
0x18000842f  jnz     short loc_180008427
0x180008431  add     eax, r8d
0x180008434  lea     edi, ds:1Ch[rax*2]
0x18000843b  test    rbx, rbx
0x18000843e  jz      short loc_180008450
0x180008440  inc     rdx
0x180008443  cmp     [rbx+rdx*2], r13w
0x180008448  jnz     short loc_180008440
0x18000844a  lea     edi, [rdi+rdx*2]
0x18000844d  add     edi, 2
0x180008450  cmp     [r15], edi
0x180008453  jnb     short loc_180008485
0x180008455  cmp     rcx, r14
0x180008458  jz      short loc_180008478
0x18000845a  test    byte ptr [rcx+1Ch], 2
0x18000845e  jz      short loc_180008478
0x180008460  mov     rcx, [rcx+10h]
0x180008464  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000846b  mov     edx, 0F9h
0x180008470  mov     r9d, edi
0x180008473  call    WPP_SF_d
0x180008478  mov     [r15], edi
0x18000847b  mov     eax, 0EAh
0x180008480  jmp     loc_180008524
0x180008485  lea     rax, [rbp+5D0h+Buffer]
0x18000848c  mov     [rsp+6D0h+var_698], rax
0x180008491  cmp     esi, 1
0x180008494  jz      short loc_1800084A5
0x180008496  lea     rax, [rsp+6D0h+RemoteName]
0x18000849b  mov     qword ptr [rsp+6D0h+var_690+8], rbx
0x1800084a0  mov     qword ptr [rsp+6D0h+var_690], rax
0x1800084a5  mov     r9d, [r15]
0x1800084a8  lea     rax, RemoteNameInfoStrings
0x1800084af  add     r9, r12
0x1800084b2  lea     r8, UniversalNameInfoStrings
0x1800084b9  cmp     esi, 1
0x1800084bc  lea     rcx, [rsp+6D0h+var_698]
0x1800084c1  mov     rdx, r12
0x1800084c4  cmovnz  r8, rax
0x1800084c8  call    PackString
0x1800084cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084d4  cmp     rcx, r14
0x1800084d7  jz      short loc_1800084F4
0x1800084d9  test    byte ptr [rcx+1Ch], 1
0x1800084dd  jz      short loc_1800084F4
0x1800084df  mov     rcx, [rcx+10h]
0x1800084e3  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800084ea  mov     edx, 0FAh
0x1800084ef  call    WPP_SF_
0x1800084f4  xor     eax, eax
0x1800084f6  jmp     short loc_180008524
0x1800084f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084ff  cmp     rcx, rdi
0x180008502  jz      short loc_18000851F
0x180008504  test    byte ptr [rcx+1Ch], 2
0x180008508  jz      short loc_18000851F
0x18000850a  mov     rcx, [rcx+10h]
0x18000850e  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008515  mov     edx, 0F3h
0x18000851a  call    WPP_SF_
0x18000851f  mov     eax, 4C6h
0x180008524  mov     rcx, [rbp+5D0h+var_50]
0x18000852b  xor     rcx, rsp; StackCookie
0x18000852e  call    __security_check_cookie
0x180008533  add     rsp, 698h
0x18000853a  pop     r15
0x18000853c  pop     r14
0x18000853e  pop     r13
0x180008540  pop     r12
0x180008542  pop     rdi
0x180008543  pop     rsi
0x180008544  pop     rbx
0x180008545  pop     rbp
0x180008546  retn
```
