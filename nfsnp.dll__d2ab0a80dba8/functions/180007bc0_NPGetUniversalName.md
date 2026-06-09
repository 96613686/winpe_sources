# NPGetUniversalName

- ea: `0x180007bc0`
- end: `0x180007f9f`
- name: `NPGetUniversalName`
- size: `991`
- prototype: `DWORD __stdcall(LPCWSTR lpLocalPath, DWORD dwInfoLevel, LPVOID lpBuffer, LPDWORD lpBufferSize)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800023f0`
- `0x180002418`
- `0x180006410`
- `0x180007bc0`
- `0x180008730`
- `0x18000895c`
- `0x180008aa0`
- `0x180008b00`
- `0x180008bac`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180007e03`
- `msvcrt!_snwprintf_s` at `0x180007e03`
- `msvcrt!wcschr` at `0x180007d2d`
- `msvcrt!wcschr` at `0x180007d2d`
- `msvcrt!wcsncpy_s` at `0x180007d1b`
- `msvcrt!wcsncpy_s` at `0x180007e16`
- `msvcrt!wcsncpy_s` at `0x180007d1b`
- `msvcrt!wcsncpy_s` at `0x180007e16`

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
            v21 = UniversalNameInfoStrings;
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
0x180007bc0  push    rbp
0x180007bc2  push    rbx
0x180007bc3  push    rsi
0x180007bc4  push    rdi
0x180007bc5  push    r12
0x180007bc7  push    r13
0x180007bc9  push    r14
0x180007bcb  push    r15
0x180007bcd  lea     rbp, [rsp-598h]
0x180007bd5  sub     rsp, 698h
0x180007bdc  mov     rax, cs:__security_cookie
0x180007be3  xor     rax, rsp
0x180007be6  mov     [rbp+5D0h+var_50], rax
0x180007bed  mov     r12, r8
0x180007bf0  mov     esi, edx
0x180007bf2  mov     rbx, rcx
0x180007bf5  mov     edi, 208h
0x180007bfa  mov     r8d, edi; Size
0x180007bfd  lea     rcx, [rsp+6D0h+RemoteName]; void *
0x180007c02  xor     edx, edx; Val
0x180007c04  mov     r15, r9
0x180007c07  call    memset_0
0x180007c0c  mov     r8d, edi; Size
0x180007c0f  lea     rcx, [rbp+5D0h+Destination]; void *
0x180007c16  xor     edx, edx; Val
0x180007c18  call    memset_0
0x180007c1d  mov     r8d, edi; Size
0x180007c20  lea     rcx, [rbp+5D0h+Buffer]; void *
0x180007c27  xor     edx, edx; Val
0x180007c29  call    memset_0
0x180007c2e  xorps   xmm0, xmm0
0x180007c31  mov     [rsp+6D0h+nBufferLen], 104h
0x180007c39  xor     r13d, r13d
0x180007c3c  movdqu  [rsp+6D0h+var_690], xmm0
0x180007c42  mov     [rsp+6D0h+var_6A0], r13d
0x180007c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c4e  lea     rdi, WPP_GLOBAL_Control
0x180007c55  cmp     rcx, rdi
0x180007c58  jz      short loc_180007C75
0x180007c5a  test    byte ptr [rcx+1Ch], 1
0x180007c5e  jz      short loc_180007C75
0x180007c60  mov     rcx, [rcx+10h]
0x180007c64  mov     edx, 0F2h
0x180007c69  mov     r9, rbx
0x180007c6c  mov     dword ptr [rsp+6D0h+var_6B0], esi
0x180007c70  call    WPP_SF_Sd
0x180007c75  lea     rcx, [rsp+6D0h+var_6A0]
0x180007c7a  call    NfsNpIsClientRunning
0x180007c7f  test    eax, eax
0x180007c81  js      loc_180007F50
0x180007c87  cmp     [rsp+6D0h+var_6A0], r13d
0x180007c8c  jz      loc_180007F50
0x180007c92  lea     eax, [rsi-1]
0x180007c95  cmp     eax, 1
0x180007c98  jbe     short loc_180007CCE
0x180007c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ca1  cmp     rcx, rdi
0x180007ca4  jz      short loc_180007CC4
0x180007ca6  test    byte ptr [rcx+1Ch], 2
0x180007caa  jz      short loc_180007CC4
0x180007cac  mov     rcx, [rcx+10h]
0x180007cb0  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007cb7  mov     edx, 0F4h
0x180007cbc  mov     r9d, esi
0x180007cbf  call    WPP_SF_d
0x180007cc4  mov     eax, 7Ch ; '|'
0x180007cc9  jmp     loc_180007F7C
0x180007cce  test    r15, r15
0x180007cd1  jnz     short loc_180007D04
0x180007cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cda  cmp     rcx, rdi
0x180007cdd  jz      short loc_180007CFA
0x180007cdf  test    byte ptr [rcx+1Ch], 2
0x180007ce3  jz      short loc_180007CFA
0x180007ce5  mov     rcx, [rcx+10h]
0x180007ce9  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007cf0  mov     edx, 0F5h
0x180007cf5  call    WPP_SF_
0x180007cfa  mov     eax, 1E7h
0x180007cff  jmp     loc_180007F7C
0x180007d04  mov     r9d, 103h; MaxCount
0x180007d0a  lea     rcx, [rbp+5D0h+Destination]; Destination
0x180007d11  mov     r8, rbx; Source
0x180007d14  mov     r14d, r13d
0x180007d17  lea     edx, [r9+1]; SizeInWords
0x180007d1b  call    cs:__imp_wcsncpy_s
0x180007d21  mov     edx, 3Ah ; ':'; Ch
0x180007d26  lea     rcx, [rbp+5D0h+Destination]; Str
0x180007d2d  call    cs:__imp_wcschr
0x180007d33  mov     rbx, rax
0x180007d36  test    rax, rax
0x180007d39  jz      short loc_180007D47
0x180007d3b  add     rbx, 2
0x180007d3f  movzx   r14d, word ptr [rbx]
0x180007d43  mov     [rbx], r13w
0x180007d47  lea     r8, [rsp+6D0h+nBufferLen]; lpnBufferLen
0x180007d4c  lea     rdx, [rsp+6D0h+RemoteName]; lpRemoteName
0x180007d51  lea     rcx, [rbp+5D0h+Destination]; lpLocalName
0x180007d58  call    NPGetConnection
0x180007d5d  mov     edi, eax
0x180007d5f  test    eax, eax
0x180007d61  jz      short loc_180007D9B
0x180007d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d6a  lea     r14, WPP_GLOBAL_Control
0x180007d71  cmp     rcx, r14
0x180007d74  jz      short loc_180007D94
0x180007d76  test    byte ptr [rcx+1Ch], 2
0x180007d7a  jz      short loc_180007D94
0x180007d7c  mov     rcx, [rcx+10h]
0x180007d80  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007d87  mov     edx, 0F6h
0x180007d8c  mov     r9d, eax
0x180007d8f  call    WPP_SF_d
0x180007d94  mov     eax, edi
0x180007d96  jmp     loc_180007F7C
0x180007d9b  test    rbx, rbx
0x180007d9e  jz      short loc_180007DA4
0x180007da0  mov     [rbx], r14w
0x180007da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dab  lea     r14, WPP_GLOBAL_Control
0x180007db2  cmp     rcx, r14
0x180007db5  jz      short loc_180007DD8
0x180007db7  test    byte ptr [rcx+1Ch], 8
0x180007dbb  jz      short loc_180007DD8
0x180007dbd  mov     rcx, [rcx+10h]
0x180007dc1  lea     rax, [rsp+6D0h+RemoteName]
0x180007dc6  mov     edx, 0F7h
0x180007dcb  mov     [rsp+6D0h+var_6B0], rax
0x180007dd0  mov     r9, rbx
0x180007dd3  call    WPP_SF_SS
0x180007dd8  lea     rcx, [rbp+5D0h+Buffer]; Destination
0x180007ddf  mov     edx, 104h; SizeInWords
0x180007de4  test    rbx, rbx
0x180007de7  jz      short loc_180007E0B
0x180007de9  lea     rax, [rsp+6D0h+RemoteName]
0x180007dee  mov     [rsp+6D0h+var_6A8], rbx
0x180007df3  lea     r9, aSS_0; "%s%s"
0x180007dfa  mov     [rsp+6D0h+var_6B0], rax
0x180007dff  lea     r8d, [rdx-1]; MaxCount
0x180007e03  call    cs:__imp__snwprintf_s
0x180007e09  jmp     short loc_180007E1C
0x180007e0b  mov     r9d, 103h; MaxCount
0x180007e11  lea     r8, [rsp+6D0h+RemoteName]; Source
0x180007e16  call    cs:__imp_wcsncpy_s
0x180007e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e23  cmp     rcx, r14
0x180007e26  jz      short loc_180007E51
0x180007e28  test    byte ptr [rcx+1Ch], 8
0x180007e2c  jz      short loc_180007E51
0x180007e2e  mov     rcx, [rcx+10h]
0x180007e32  lea     r9, [rbp+5D0h+Buffer]
0x180007e39  mov     edx, 0F8h
0x180007e3e  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007e45  call    WPP_SF_S
0x180007e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e51  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180007e55  lea     r8, [rbp+5D0h+Buffer]
0x180007e5c  mov     rax, rdx
0x180007e5f  inc     rax
0x180007e62  cmp     [r8+rax*2], r13w
0x180007e67  jnz     short loc_180007E5F
0x180007e69  cmp     esi, 1
0x180007e6c  jnz     short loc_180007E77
0x180007e6e  lea     edi, ds:0Ah[rax*2]
0x180007e75  jmp     short loc_180007EA8
0x180007e77  lea     r9, [rsp+6D0h+RemoteName]
0x180007e7c  mov     r8, rdx
0x180007e7f  inc     r8
0x180007e82  cmp     [r9+r8*2], r13w
0x180007e87  jnz     short loc_180007E7F
0x180007e89  add     eax, r8d
0x180007e8c  lea     edi, ds:1Ch[rax*2]
0x180007e93  test    rbx, rbx
0x180007e96  jz      short loc_180007EA8
0x180007e98  inc     rdx
0x180007e9b  cmp     [rbx+rdx*2], r13w
0x180007ea0  jnz     short loc_180007E98
0x180007ea2  lea     edi, [rdi+rdx*2]
0x180007ea5  add     edi, 2
0x180007ea8  cmp     [r15], edi
0x180007eab  jnb     short loc_180007EDD
0x180007ead  cmp     rcx, r14
0x180007eb0  jz      short loc_180007ED0
0x180007eb2  test    byte ptr [rcx+1Ch], 2
0x180007eb6  jz      short loc_180007ED0
0x180007eb8  mov     rcx, [rcx+10h]
0x180007ebc  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007ec3  mov     edx, 0F9h
0x180007ec8  mov     r9d, edi
0x180007ecb  call    WPP_SF_d
0x180007ed0  mov     [r15], edi
0x180007ed3  mov     eax, 0EAh
0x180007ed8  jmp     loc_180007F7C
0x180007edd  lea     rax, [rbp+5D0h+Buffer]
0x180007ee4  mov     [rsp+6D0h+var_698], rax
0x180007ee9  cmp     esi, 1
0x180007eec  jz      short loc_180007EFD
0x180007eee  lea     rax, [rsp+6D0h+RemoteName]
0x180007ef3  mov     qword ptr [rsp+6D0h+var_690+8], rbx
0x180007ef8  mov     qword ptr [rsp+6D0h+var_690], rax
0x180007efd  mov     r9d, [r15]
0x180007f00  lea     rax, RemoteNameInfoStrings
0x180007f07  add     r9, r12
0x180007f0a  lea     r8, UniversalNameInfoStrings
0x180007f11  cmp     esi, 1
0x180007f14  lea     rcx, [rsp+6D0h+var_698]
0x180007f19  mov     rdx, r12
0x180007f1c  cmovnz  r8, rax
0x180007f20  call    PackString
0x180007f25  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f2c  cmp     rcx, r14
0x180007f2f  jz      short loc_180007F4C
0x180007f31  test    byte ptr [rcx+1Ch], 1
0x180007f35  jz      short loc_180007F4C
0x180007f37  mov     rcx, [rcx+10h]
0x180007f3b  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007f42  mov     edx, 0FAh
0x180007f47  call    WPP_SF_
0x180007f4c  xor     eax, eax
0x180007f4e  jmp     short loc_180007F7C
0x180007f50  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f57  cmp     rcx, rdi
0x180007f5a  jz      short loc_180007F77
0x180007f5c  test    byte ptr [rcx+1Ch], 2
0x180007f60  jz      short loc_180007F77
0x180007f62  mov     rcx, [rcx+10h]
0x180007f66  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007f6d  mov     edx, 0F3h
0x180007f72  call    WPP_SF_
0x180007f77  mov     eax, 4C6h
0x180007f7c  mov     rcx, [rbp+5D0h+var_50]
0x180007f83  xor     rcx, rsp; StackCookie
0x180007f86  call    __security_check_cookie
0x180007f8b  add     rsp, 698h
0x180007f92  pop     r15
0x180007f94  pop     r14
0x180007f96  pop     r13
0x180007f98  pop     r12
0x180007f9a  pop     rdi
0x180007f9b  pop     rsi
0x180007f9c  pop     rbx
0x180007f9d  pop     rbp
0x180007f9e  retn
```
