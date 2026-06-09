# EapMsChapv2GetLogonCred

- ea: `0x180023900`
- end: `0x180023c29`
- name: `EapMsChapv2GetLogonCred`
- size: `809`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003200`

## callees

- `0x180003bd0`
- `0x180006a20`
- `0x18000ee48`
- `0x180013b20`
- `0x180023900`
- `0x180025efc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023afc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023afc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023b94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a69`
- `SspiCli!GetUserNameExW` at `0x180023a1a`
- `SspiCli!GetUserNameExW` at `0x180023a1a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180023a5f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180023a5f`

## pseudocode

```c
__int64 __fastcall EapMsChapv2GetLogonCred(char a1, __int64 a2, _QWORD *a3)
{
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  DWORD IdentityFromUserName; // eax
  DWORD LastError; // eax
  DWORD v12; // ecx
  WCHAR *v13; // r8
  __int64 v14; // rdx
  WCHAR *v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  wchar_t *v18; // rax
  __int64 v19; // rcx
  WCHAR *v20; // r8
  __int64 v21; // rdx
  WCHAR *v22; // rax
  WCHAR *v23; // rcx
  HLOCAL v24; // rax
  ULONG nSize; // [rsp+20h] [rbp-E0h] BYREF
  DWORD v27; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Buffer[8]; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v29; // [rsp+38h] [rbp-C8h]
  __int16 v30; // [rsp+48h] [rbp-B8h]
  WCHAR NameBuffer[520]; // [rsp+50h] [rbp-B0h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
  nSize = 512;
  *a3 = 0;
  v30 = 0;
  v27 = 17;
  *(_OWORD *)Buffer = 0;
  v29 = 0;
  if ( (a1 & 4) == 0 )
  {
    if ( !GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v6;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, LastError);
      goto LABEL_46;
    }
    if ( GetComputerNameW(Buffer, &v27) )
    {
      v12 = v27;
      if ( v27 && nSize > v27 )
      {
        v13 = Buffer;
        Buffer[v27] = 92;
        v27 = v12 + 1;
        v14 = v12 + 1;
        v15 = NameBuffer;
        while ( v14 )
        {
          if ( *v13 != *v15 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_41;
            v17 = 72;
            goto LABEL_40;
          }
          ++v13;
          ++v15;
          --v14;
        }
        v18 = wcschr(NameBuffer, 0x5Cu);
        if ( v18 )
        {
          nSize -= v27;
          v19 = nSize + 1;
          if ( (unsigned int)v19 <= 0x7FFFFFFE )
          {
            v20 = v18 + 1;
            v21 = 514;
            v22 = NameBuffer;
            do
            {
              if ( !v19 )
                break;
              if ( !*v20 )
                break;
              *v22++ = *v20++;
              --v19;
              --v21;
            }
            while ( v21 );
            v23 = v22 - 1;
            if ( v21 )
              v23 = v22;
            *v23 = 0;
          }
          else
          {
            NameBuffer[0] = 0;
          }
        }
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v17 = 71;
LABEL_40:
          WPP_SF_(v16[2], v17, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
        }
      }
LABEL_41:
      v24 = LocalAlloc(0x40u, 2LL * nSize + 2);
      *a3 = v24;
      if ( v24 )
      {
        v6 = 0;
        memcpy_0(v24, NameBuffer, 2LL * nSize);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
        v6 = 14;
      }
      goto LABEL_46;
    }
    IdentityFromUserName = GetLastError();
    v6 = IdentityFromUserName;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v6;
    v8 = 70;
    goto LABEL_12;
  }
  if ( (a1 & 1) != 0 )
  {
    v6 = 87;
  }
  else
  {
    if ( !*(_BYTE *)(a2 + 12) )
    {
      v6 = 805;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v6;
      v8 = 67;
      v9 = 805;
      goto LABEL_8;
    }
    IdentityFromUserName = GetIdentityFromUserName((LPCCH)(a2 + 12), (LPCCH)(a2 + 526));
    v6 = IdentityFromUserName;
    if ( IdentityFromUserName )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v6;
      v8 = 68;
LABEL_12:
      v9 = IdentityFromUserName;
LABEL_8:
      WPP_SF_d(v7[2], v8, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, v9);
    }
  }
LABEL_46:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180023900  mov     [rsp-8+arg_0], rbx
0x180023905  mov     [rsp-8+arg_18], rsi
0x18002390a  push    rbp
0x18002390b  push    rdi
0x18002390c  push    r12
0x18002390e  push    r14
0x180023910  push    r15
0x180023912  lea     rbp, [rsp-370h]
0x18002391a  sub     rsp, 470h
0x180023921  mov     rax, cs:__security_cookie
0x180023928  xor     rax, rsp
0x18002392b  mov     [rbp+390h+var_30], rax
0x180023932  mov     rsi, r8
0x180023935  mov     rdi, rdx
0x180023938  mov     ebx, ecx
0x18002393a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023941  lea     r15, WPP_GLOBAL_Control
0x180023948  lea     r12, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x18002394f  cmp     rcx, r15
0x180023952  jz      short loc_180023965
0x180023954  mov     rcx, [rcx+10h]
0x180023958  mov     edx, 42h ; 'B'
0x18002395d  mov     r8, r12
0x180023960  call    WPP_SF_
0x180023965  xor     r14d, r14d
0x180023968  mov     [rsp+490h+nSize], 200h
0x180023970  xor     eax, eax
0x180023972  mov     [rsi], r14
0x180023975  mov     [rsp+490h+var_448], ax
0x18002397a  xorps   xmm0, xmm0
0x18002397d  mov     [rsp+490h+var_46C], 11h
0x180023985  movups  xmmword ptr [rsp+490h+Buffer], xmm0
0x18002398a  movups  [rsp+490h+var_458], xmm0
0x18002398f  test    bl, 4
0x180023992  jz      short loc_180023A0B
0x180023994  test    bl, 1
0x180023997  jnz     short loc_180023A01
0x180023999  lea     rcx, [rdi+0Ch]; lpMultiByteStr
0x18002399d  cmp     [rcx], r14b
0x1800239a0  jnz     short loc_1800239CE
0x1800239a2  mov     ebx, 325h
0x1800239a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239ae  cmp     rcx, r15
0x1800239b1  jz      loc_180023BFC
0x1800239b7  lea     edx, [rax+43h]
0x1800239ba  mov     r9d, ebx
0x1800239bd  mov     rcx, [rcx+10h]
0x1800239c1  mov     r8, r12
0x1800239c4  call    WPP_SF_d
0x1800239c9  jmp     loc_180023BDC
0x1800239ce  lea     rdx, [rdi+20Eh]; LPCCH
0x1800239d5  mov     r8, rsi
0x1800239d8  call    GetIdentityFromUserName
0x1800239dd  mov     ebx, eax
0x1800239df  test    eax, eax
0x1800239e1  jz      loc_180023BDC
0x1800239e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239ee  cmp     rcx, r15
0x1800239f1  jz      loc_180023BFC
0x1800239f7  mov     edx, 44h ; 'D'
0x1800239fc  mov     r9d, eax
0x1800239ff  jmp     short loc_1800239BD
0x180023a01  mov     ebx, 57h ; 'W'
0x180023a06  jmp     loc_180023BDC
0x180023a0b  lea     r8, [rsp+490h+nSize]; nSize
0x180023a10  mov     ecx, 2; NameFormat
0x180023a15  lea     rdx, [rsp+490h+NameBuffer]; lpNameBuffer
0x180023a1a  call    cs:__imp_GetUserNameExW
0x180023a20  test    al, al
0x180023a22  jnz     short loc_180023A55
0x180023a24  call    cs:__imp_GetLastError
0x180023a2a  mov     ebx, eax
0x180023a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a33  cmp     rcx, r15
0x180023a36  jz      loc_180023BFC
0x180023a3c  mov     rcx, [rcx+10h]
0x180023a40  mov     edx, 45h ; 'E'
0x180023a45  mov     r9d, eax
0x180023a48  mov     r8, r12
0x180023a4b  call    WPP_SF_d
0x180023a50  jmp     loc_180023BDC
0x180023a55  lea     rdx, [rsp+490h+var_46C]; nSize
0x180023a5a  lea     rcx, [rsp+490h+Buffer]; lpBuffer
0x180023a5f  call    cs:__imp_GetComputerNameW
0x180023a65  test    eax, eax
0x180023a67  jnz     short loc_180023A8B
0x180023a69  call    cs:__imp_GetLastError
0x180023a6f  mov     ebx, eax
0x180023a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a78  cmp     rcx, r15
0x180023a7b  jz      loc_180023BFC
0x180023a81  mov     edx, 46h ; 'F'
0x180023a86  jmp     loc_1800239FC
0x180023a8b  mov     ecx, [rsp+490h+var_46C]
0x180023a8f  test    ecx, ecx
0x180023a91  jz      loc_180023B83
0x180023a97  cmp     [rsp+490h+nSize], ecx
0x180023a9b  jbe     loc_180023B83
0x180023aa1  mov     r9d, 5Ch ; '\'
0x180023aa7  lea     r8, [rsp+490h+Buffer]
0x180023aac  mov     [rsp+rcx*2+490h+Buffer], r9w
0x180023ab2  inc     ecx
0x180023ab4  mov     [rsp+490h+var_46C], ecx
0x180023ab8  mov     edx, ecx
0x180023aba  lea     rcx, [rsp+490h+NameBuffer]
0x180023abf  test    rdx, rdx
0x180023ac2  jz      short loc_180023AF4
0x180023ac4  movzx   eax, word ptr [rcx]
0x180023ac7  cmp     [r8], ax
0x180023acb  jnz     short loc_180023ADA
0x180023acd  add     r8, 2
0x180023ad1  add     rcx, 2
0x180023ad5  dec     rdx
0x180023ad8  jmp     short loc_180023ABF
0x180023ada  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ae1  cmp     rcx, r15
0x180023ae4  jz      loc_180023B83
0x180023aea  mov     edx, 48h ; 'H'
0x180023aef  jmp     loc_180023B77
0x180023af4  mov     edx, r9d; Ch
0x180023af7  lea     rcx, [rsp+490h+NameBuffer]; Str
0x180023afc  call    cs:__imp_wcschr
0x180023b02  test    rax, rax
0x180023b05  jz      short loc_180023B66
0x180023b07  mov     ecx, [rsp+490h+nSize]
0x180023b0b  sub     ecx, [rsp+490h+var_46C]
0x180023b0f  mov     [rsp+490h+nSize], ecx
0x180023b13  inc     ecx
0x180023b15  cmp     ecx, 7FFFFFFEh
0x180023b1b  jbe     short loc_180023B25
0x180023b1d  mov     [rsp+490h+NameBuffer], r14w
0x180023b23  jmp     short loc_180023B66
0x180023b25  lea     r8, [rax+2]
0x180023b29  mov     edx, 202h
0x180023b2e  lea     rax, [rsp+490h+NameBuffer]
0x180023b33  test    rcx, rcx
0x180023b36  jz      short loc_180023B57
0x180023b38  movzx   r9d, word ptr [r8]
0x180023b3c  test    r9w, r9w
0x180023b40  jz      short loc_180023B57
0x180023b42  mov     [rax], r9w
0x180023b46  add     r8, 2
0x180023b4a  add     rax, 2
0x180023b4e  dec     rcx
0x180023b51  sub     rdx, 1
0x180023b55  jnz     short loc_180023B33
0x180023b57  test    rdx, rdx
0x180023b5a  lea     rcx, [rax-2]
0x180023b5e  cmovnz  rcx, rax
0x180023b62  mov     [rcx], r14w
0x180023b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b6d  cmp     rcx, r15
0x180023b70  jz      short loc_180023B83
0x180023b72  mov     edx, 47h ; 'G'
0x180023b77  mov     rcx, [rcx+10h]
0x180023b7b  mov     r8, r12
0x180023b7e  call    WPP_SF_
0x180023b83  mov     edx, [rsp+490h+nSize]
0x180023b87  mov     ecx, 40h ; '@'; uFlags
0x180023b8c  lea     rdx, ds:2[rdx*2]; uBytes
0x180023b94  call    cs:__imp_LocalAlloc
0x180023b9a  mov     [rsi], rax
0x180023b9d  test    rax, rax
0x180023ba0  jnz     short loc_180023BC4
0x180023ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ba9  cmp     rcx, r15
0x180023bac  jz      short loc_180023BBD
0x180023bae  mov     rcx, [rcx+10h]
0x180023bb2  lea     edx, [rax+49h]
0x180023bb5  mov     r8, r12
0x180023bb8  call    WPP_SF_
0x180023bbd  mov     ebx, 0Eh
0x180023bc2  jmp     short loc_180023BDC
0x180023bc4  mov     r8d, [rsp+490h+nSize]
0x180023bc9  lea     rdx, [rsp+490h+NameBuffer]; Src
0x180023bce  add     r8, r8; Size
0x180023bd1  mov     rcx, rax; void *
0x180023bd4  mov     ebx, r14d
0x180023bd7  call    memcpy_0
0x180023bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180023be3  cmp     rcx, r15
0x180023be6  jz      short loc_180023BFC
0x180023be8  mov     rcx, [rcx+10h]
0x180023bec  mov     edx, 4Ah ; 'J'
0x180023bf1  mov     r9d, ebx
0x180023bf4  mov     r8, r12
0x180023bf7  call    WPP_SF_d
0x180023bfc  mov     eax, ebx
0x180023bfe  mov     rcx, [rbp+390h+var_30]
0x180023c05  xor     rcx, rsp; StackCookie
0x180023c08  call    __security_check_cookie
0x180023c0d  lea     r11, [rsp+490h+var_20]
0x180023c15  mov     rbx, [r11+30h]
0x180023c19  mov     rsi, [r11+48h]
0x180023c1d  mov     rsp, r11
0x180023c20  pop     r15
0x180023c22  pop     r14
0x180023c24  pop     r12
0x180023c26  pop     rdi
0x180023c27  pop     rbp
0x180023c28  retn
```
