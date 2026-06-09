# BuildShowMountList

- ea: `0x180002a90`
- end: `0x180002f96`
- name: `BuildShowMountList`
- size: `1286`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180008570`

## callees

- `0x180002a90`
- `0x1800089e4`
- `0x18000937c`
- `0x1800093e0`
- `0x1800094f4`
- `0x1800095a4`
- `0x180009758`
- `0x180009c78`
- `0x18000c450`
- `0x180012e70`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180002dab`
- `msvcrt!_wcsnicmp` at `0x180002dab`
- `msvcrt!mbstowcs` at `0x180002c84`
- `msvcrt!mbstowcs` at `0x180002d26`
- `msvcrt!mbstowcs` at `0x180002c84`
- `msvcrt!mbstowcs` at `0x180002d26`
- `msvcrt!strpbrk` at `0x180002be9`
- `msvcrt!strpbrk` at `0x180002be9`
- `msvcrt!wcstombs` at `0x180002b82`
- `msvcrt!wcstombs` at `0x180002b82`
- `KERNEL32!GetLastError` at `0x180002f36`
- `KERNEL32!GetLastError` at `0x180002f36`

## string_xrefs

- `0x180002abd`: `BuildShowMountList`

## pseudocode

```c
__int64 __fastcall BuildShowMountList(__int64 a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rdx
  char *i; // rbx
  char *v6; // rdi
  HGLOBAL v7; // rsi
  const char *v8; // rdi
  int v10; // r14d
  __int64 *v11; // rbx
  _QWORD *v12; // rcx
  unsigned int v13; // edi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  DWORD LastError; // eax
  DWORD v19; // ebx
  HGLOBAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  char v21[24]; // [rsp+48h] [rbp-B8h] BYREF
  char Dest[272]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String1[264]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t String2[264]; // [rsp+380h] [rbp+280h] BYREF

  hMem = 0;
  strcpy(v21, "BuildShowMountList");
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_sS(
        v2[2],
        39,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v21,
        *(_QWORD *)(*(_QWORD *)(a1 + 104) + 24LL));
  }
  v3 = -1;
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 24LL);
  do
    ++v3;
  while ( *(_WORD *)(v4 + 2 * v3) );
  if ( *(_WORD *)(v4 + 2 * v3 - 2) == 58 )
    *(_WORD *)(v4 + 2 * v3 - 2) = 0;
  if ( (unsigned int)wcstombs(Dest, *(const wchar_t **)(*(_QWORD *)(a1 + 104) + 24LL), 0x104u) - 1 > 0xFFFFFFFD )
  {
    LastError = GetLastError();
    v19 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v21,
        LastError);
    return v19;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v21,
        (__int64)Dest);
    for ( i = Dest; *i == 92; ++i )
      ;
    v6 = strpbrk(i, "\\/");
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
      *v6 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
          (unsigned int)v21,
          (__int64)i);
      NfsNpCallRpc((__int64)i, (__int64)&hMem);
      v7 = hMem;
      if ( hMem )
      {
        v8 = v6 + 1;
        if ( (unsigned int)mbstowcs(String1, v8, 0x104u) == -1 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_ss(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              44,
              (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
              (unsigned int)v21,
              (__int64)v8);
          FreeExportList(v7);
          return 67;
        }
        v10 = 0;
        v11 = (__int64 *)v7;
        if ( !v7 )
          goto LABEL_51;
        v12 = WPP_GLOBAL_Control;
        while ( 1 )
        {
          if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
            WPP_SF_ss(
              v12[2],
              45,
              (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
              (unsigned int)v21,
              *v11);
          v13 = mbstowcs(String2, (const char *)(*v11 + 1), 0x104u);
          if ( v13 == -1 )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_45;
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_sSdS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)String2, v13, (__int64)String1);
            if ( !_wcsnicmp(String1, String2, v13) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)String2, (__int64)String1);
              }
              v10 = 1;
LABEL_51:
              FreeExportList(v7);
              if ( v10 )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v15 = 49;
                  goto LABEL_55;
                }
                return 0;
              }
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v17 = 50;
                goto LABEL_63;
              }
              return 67;
            }
          }
          v12 = WPP_GLOBAL_Control;
LABEL_45:
          v11 = (__int64 *)v11[3];
          if ( !v11 )
            goto LABEL_51;
        }
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 51;
LABEL_63:
        WPP_SF_s(v16[2], v17, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
      }
      return 67;
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
          (unsigned int)v21,
          (__int64)i);
        v14 = WPP_GLOBAL_Control;
      }
      if ( (*(_BYTE *)(a1 + 4) & 1) != 0 )
      {
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
          WPP_SF_s(v14[2], 53, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
        if ( (unsigned int)NfsNpCallRpc((__int64)i, a1 + 88) )
          return 67;
        v14 = WPP_GLOBAL_Control;
      }
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
      {
        v15 = 54;
LABEL_55:
        WPP_SF_s(v14[2], v15, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180002a90  push    rbp
0x180002a92  push    rbx
0x180002a93  push    rsi
0x180002a94  push    rdi
0x180002a95  push    r12
0x180002a97  push    r13
0x180002a99  push    r14
0x180002a9b  push    r15
0x180002a9d  lea     rbp, [rsp-4A8h]
0x180002aa5  sub     rsp, 5A8h
0x180002aac  mov     rax, cs:__security_cookie
0x180002ab3  xor     rax, rsp
0x180002ab6  mov     [rbp+4E0h+var_50], rax
0x180002abd  movups  xmm0, xmmword ptr cs:aBuildshowmount; "BuildShowMountList"
0x180002ac4  mov     eax, dword ptr cs:aBuildshowmount+0Fh; "ist"
0x180002aca  xor     r13d, r13d
0x180002acd  mov     rsi, rcx
0x180002ad0  mov     [rsp+5E0h+hMem], r13
0x180002ad5  movups  xmmword ptr [rsp+5E0h+var_598], xmm0
0x180002ada  mov     dword ptr [rsp+5E0h+var_598+0Fh], eax
0x180002ade  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ae5  lea     r15, WPP_GLOBAL_Control
0x180002aec  lea     r12, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180002af3  mov     r14b, 8
0x180002af6  cmp     rcx, r15
0x180002af9  jz      short loc_180002B4B
0x180002afb  test    byte ptr [rcx+1Ch], 1
0x180002aff  jz      short loc_180002B1D
0x180002b01  mov     rcx, [rcx+10h]
0x180002b05  lea     edx, [r13+26h]
0x180002b09  lea     r9, [rsp+5E0h+var_598]
0x180002b0e  mov     r8, r12
0x180002b11  call    WPP_SF_s
0x180002b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b1d  cmp     rcx, r15
0x180002b20  jz      short loc_180002B4B
0x180002b22  test    [rcx+1Ch], r14b
0x180002b26  jz      short loc_180002B4B
0x180002b28  mov     rax, [rsi+68h]
0x180002b2c  lea     r9, [rsp+5E0h+var_598]
0x180002b31  mov     rcx, [rcx+10h]
0x180002b35  mov     edx, 27h ; '''
0x180002b3a  mov     r8, r12
0x180002b3d  mov     rax, [rax+18h]
0x180002b41  mov     [rsp+5E0h+var_5C0], rax
0x180002b46  call    WPP_SF_sS
0x180002b4b  mov     rax, [rsi+68h]
0x180002b4f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002b53  mov     rdx, [rax+18h]
0x180002b57  inc     rcx
0x180002b5a  cmp     [rdx+rcx*2], r13w
0x180002b5f  jnz     short loc_180002B57
0x180002b61  cmp     word ptr [rdx+rcx*2-2], 3Ah ; ':'
0x180002b67  jnz     short loc_180002B6F
0x180002b69  mov     [rdx+rcx*2-2], r13w
0x180002b6f  mov     rdx, [rsi+68h]
0x180002b73  lea     rcx, [rsp+5E0h+Dest]; Dest
0x180002b78  mov     r8d, 104h; MaxCount
0x180002b7e  mov     rdx, [rdx+18h]; Source
0x180002b82  call    cs:__imp_wcstombs
0x180002b89  nop     dword ptr [rax+rax+00h]
0x180002b8e  dec     eax
0x180002b90  cmp     eax, 0FFFFFFFDh
0x180002b93  ja      loc_180002F36
0x180002b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ba0  cmp     rcx, r15
0x180002ba3  jz      short loc_180002BCB
0x180002ba5  test    [rcx+1Ch], r14b
0x180002ba9  jz      short loc_180002BCB
0x180002bab  mov     rcx, [rcx+10h]
0x180002baf  lea     rax, [rsp+5E0h+Dest]
0x180002bb4  mov     edx, 29h ; ')'
0x180002bb9  mov     [rsp+5E0h+var_5C0], rax
0x180002bbe  lea     r9, [rsp+5E0h+var_598]
0x180002bc3  mov     r8, r12
0x180002bc6  call    WPP_SF_ss
0x180002bcb  cmp     [rsp+5E0h+Dest], 5Ch ; '\'
0x180002bd0  lea     rbx, [rsp+5E0h+Dest]
0x180002bd5  jnz     short loc_180002BDF
0x180002bd7  inc     rbx
0x180002bda  cmp     byte ptr [rbx], 5Ch ; '\'
0x180002bdd  jz      short loc_180002BD7
0x180002bdf  lea     rdx, Control; "\\/"
0x180002be6  mov     rcx, rbx; Str
0x180002be9  call    cs:__imp_strpbrk
0x180002bf0  nop     dword ptr [rax+rax+00h]
0x180002bf5  mov     rdi, rax
0x180002bf8  test    rax, rax
0x180002bfb  jz      loc_180002EA3
0x180002c01  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c08  cmp     rcx, r15
0x180002c0b  jz      short loc_180002C29
0x180002c0d  test    [rcx+1Ch], r14b
0x180002c11  jz      short loc_180002C29
0x180002c13  mov     rcx, [rcx+10h]
0x180002c17  lea     r9, [rsp+5E0h+var_598]
0x180002c1c  mov     edx, 2Ah ; '*'
0x180002c21  mov     r8, r12
0x180002c24  call    WPP_SF_s
0x180002c29  mov     [rdi], r13b
0x180002c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c33  cmp     rcx, r15
0x180002c36  jz      short loc_180002C59
0x180002c38  test    [rcx+1Ch], r14b
0x180002c3c  jz      short loc_180002C59
0x180002c3e  mov     rcx, [rcx+10h]
0x180002c42  lea     r9, [rsp+5E0h+var_598]
0x180002c47  mov     edx, 2Bh ; '+'
0x180002c4c  mov     [rsp+5E0h+var_5C0], rbx
0x180002c51  mov     r8, r12
0x180002c54  call    WPP_SF_ss
0x180002c59  lea     rdx, [rsp+5E0h+hMem]
0x180002c5e  mov     rcx, rbx
0x180002c61  call    NfsNpCallRpc
0x180002c66  mov     rsi, [rsp+5E0h+hMem]
0x180002c6b  test    rsi, rsi
0x180002c6e  jz      loc_180002E6E
0x180002c74  inc     rdi
0x180002c77  lea     rcx, [rbp+4E0h+String1]; Dest
0x180002c7b  mov     rdx, rdi; Source
0x180002c7e  mov     r8d, 104h; MaxCount
0x180002c84  call    cs:__imp_mbstowcs
0x180002c8b  nop     dword ptr [rax+rax+00h]
0x180002c90  cmp     eax, 0FFFFFFFFh
0x180002c93  jnz     short loc_180002CD4
0x180002c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c9c  cmp     rcx, r15
0x180002c9f  jz      short loc_180002CC2
0x180002ca1  test    byte ptr [rcx+1Ch], 2
0x180002ca5  jz      short loc_180002CC2
0x180002ca7  mov     rcx, [rcx+10h]
0x180002cab  lea     r9, [rsp+5E0h+var_598]
0x180002cb0  mov     edx, 2Ch ; ','
0x180002cb5  mov     [rsp+5E0h+var_5C0], rdi
0x180002cba  mov     r8, r12
0x180002cbd  call    WPP_SF_ss
0x180002cc2  mov     rcx, rsi; hMem
0x180002cc5  call    FreeExportList
0x180002cca  mov     eax, 43h ; 'C'
0x180002ccf  jmp     loc_180002F72
0x180002cd4  mov     r14d, r13d
0x180002cd7  mov     rbx, rsi
0x180002cda  test    rsi, rsi
0x180002cdd  jz      loc_180002E11
0x180002ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cea  cmp     rcx, r15
0x180002ced  jz      short loc_180002D13
0x180002cef  test    byte ptr [rcx+1Ch], 8
0x180002cf3  jz      short loc_180002D13
0x180002cf5  mov     rax, [rbx]
0x180002cf8  lea     r9, [rsp+5E0h+var_598]
0x180002cfd  mov     rcx, [rcx+10h]
0x180002d01  mov     edx, 2Dh ; '-'
0x180002d06  mov     r8, r12
0x180002d09  mov     [rsp+5E0h+var_5C0], rax
0x180002d0e  call    WPP_SF_ss
0x180002d13  mov     rdx, [rbx]
0x180002d16  lea     rcx, [rbp+4E0h+String2]; Dest
0x180002d1d  inc     rdx; Source
0x180002d20  mov     r8d, 104h; MaxCount
0x180002d26  call    cs:__imp_mbstowcs
0x180002d2d  nop     dword ptr [rax+rax+00h]
0x180002d32  mov     rdi, rax
0x180002d35  cmp     eax, 0FFFFFFFFh
0x180002d38  jnz     short loc_180002D64
0x180002d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d41  cmp     rcx, r15
0x180002d44  jz      short loc_180002DC2
0x180002d46  test    byte ptr [rcx+1Ch], 2
0x180002d4a  jz      short loc_180002DC2
0x180002d4c  mov     rcx, [rcx+10h]
0x180002d50  lea     r9, [rsp+5E0h+var_598]
0x180002d55  mov     edx, 2Eh ; '.'
0x180002d5a  mov     r8, r12
0x180002d5d  call    WPP_SF_s
0x180002d62  jmp     short loc_180002DBB
0x180002d64  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d6b  cmp     rcx, r15
0x180002d6e  jz      short loc_180002D9D
0x180002d70  test    byte ptr [rcx+1Ch], 8
0x180002d74  jz      short loc_180002D9D
0x180002d76  mov     rcx, [rcx+10h]; LoggerHandle
0x180002d7a  lea     rax, [rbp+4E0h+String1]
0x180002d7e  mov     [rsp+5E0h+var_5B0], rax; __int64
0x180002d83  lea     r9, [rsp+5E0h+var_598]
0x180002d88  lea     rax, [rbp+4E0h+String2]
0x180002d8f  mov     dword ptr [rsp+5E0h+var_5B8], edi; char
0x180002d93  mov     [rsp+5E0h+var_5C0], rax; __int64
0x180002d98  call    WPP_SF_sSdS
0x180002d9d  mov     r8d, edi; MaxCount
0x180002da0  lea     rdx, [rbp+4E0h+String2]; String2
0x180002da7  lea     rcx, [rbp+4E0h+String1]; String1
0x180002dab  call    cs:__imp__wcsnicmp
0x180002db2  nop     dword ptr [rax+rax+00h]
0x180002db7  test    eax, eax
0x180002db9  jz      short loc_180002DD1
0x180002dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dc2  mov     rbx, [rbx+18h]
0x180002dc6  test    rbx, rbx
0x180002dc9  jnz     loc_180002CEA
0x180002dcf  jmp     short loc_180002E11
0x180002dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dd8  cmp     rcx, r15
0x180002ddb  jz      short loc_180002E0B
0x180002ddd  test    byte ptr [rcx+1Ch], 8
0x180002de1  jz      short loc_180002E0B
0x180002de3  mov     rcx, [rcx+10h]; LoggerHandle
0x180002de7  lea     rax, [rbp+4E0h+String1]
0x180002deb  mov     qword ptr [rsp+5E0h+var_5B8], rax; __int64
0x180002df0  lea     r9, [rsp+5E0h+var_598]
0x180002df5  lea     rax, [rbp+4E0h+String2]
0x180002dfc  mov     edx, 30h ; '0'
0x180002e01  mov     [rsp+5E0h+var_5C0], rax; __int64
0x180002e06  call    WPP_SF_sSS
0x180002e0b  mov     r14d, 1
0x180002e11  mov     rcx, rsi; hMem
0x180002e14  call    FreeExportList
0x180002e19  test    r14d, r14d
0x180002e1c  jz      short loc_180002E4D
0x180002e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e25  cmp     rcx, r15
0x180002e28  jz      short loc_180002E46
0x180002e2a  test    byte ptr [rcx+1Ch], 2
0x180002e2e  jz      short loc_180002E46
0x180002e30  mov     edx, 31h ; '1'
0x180002e35  mov     rcx, [rcx+10h]
0x180002e39  lea     r9, [rsp+5E0h+var_598]
0x180002e3e  mov     r8, r12
0x180002e41  call    WPP_SF_s
0x180002e46  xor     eax, eax
0x180002e48  jmp     loc_180002F72
0x180002e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e54  cmp     rcx, r15
0x180002e57  jz      loc_180002CCA
0x180002e5d  test    byte ptr [rcx+1Ch], 2
0x180002e61  jz      loc_180002CCA
0x180002e67  mov     edx, 32h ; '2'
0x180002e6c  jmp     short loc_180002E8D
0x180002e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e75  cmp     rcx, r15
0x180002e78  jz      loc_180002CCA
0x180002e7e  test    byte ptr [rcx+1Ch], 2
0x180002e82  jz      loc_180002CCA
0x180002e88  mov     edx, 33h ; '3'
0x180002e8d  mov     rcx, [rcx+10h]
0x180002e91  lea     r9, [rsp+5E0h+var_598]
0x180002e96  mov     r8, r12
0x180002e99  call    WPP_SF_s
0x180002e9e  jmp     loc_180002CCA
0x180002ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eaa  cmp     rcx, r15
0x180002ead  jz      short loc_180002ED7
0x180002eaf  test    [rcx+1Ch], r14b
0x180002eb3  jz      short loc_180002ED7
0x180002eb5  mov     rcx, [rcx+10h]
0x180002eb9  lea     r9, [rsp+5E0h+var_598]
0x180002ebe  mov     edx, 34h ; '4'
0x180002ec3  mov     [rsp+5E0h+var_5C0], rbx
0x180002ec8  mov     r8, r12
0x180002ecb  call    WPP_SF_ss
0x180002ed0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ed7  test    byte ptr [rsi+4], 1
0x180002edb  jz      short loc_180002F19
0x180002edd  cmp     rcx, r15
0x180002ee0  jz      short loc_180002EFE
0x180002ee2  test    [rcx+1Ch], r14b
0x180002ee6  jz      short loc_180002EFE
0x180002ee8  mov     rcx, [rcx+10h]
0x180002eec  lea     r9, [rsp+5E0h+var_598]
0x180002ef1  mov     edx, 35h ; '5'
0x180002ef6  mov     r8, r12
0x180002ef9  call    WPP_SF_s
0x180002efe  lea     rdx, [rsi+58h]
0x180002f02  mov     rcx, rbx
0x180002f05  call    NfsNpCallRpc
0x180002f0a  test    eax, eax
0x180002f0c  jnz     loc_180002CCA
0x180002f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f19  cmp     rcx, r15
0x180002f1c  jz      loc_180002E46
0x180002f22  test    byte ptr [rcx+1Ch], 1
0x180002f26  jz      loc_180002E46
0x180002f2c  mov     edx, 36h ; '6'
0x180002f31  jmp     loc_180002E35
0x180002f36  call    cs:__imp_GetLastError
0x180002f3d  nop     dword ptr [rax+rax+00h]
0x180002f42  mov     ebx, eax
0x180002f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f4b  cmp     rcx, r15
0x180002f4e  jz      short loc_180002F70
0x180002f50  test    byte ptr [rcx+1Ch], 2
0x180002f54  jz      short loc_180002F70
0x180002f56  mov     rcx, [rcx+10h]
0x180002f5a  lea     r9, [rsp+5E0h+var_598]
0x180002f5f  mov     edx, 28h ; '('
0x180002f64  mov     dword ptr [rsp+5E0h+var_5C0], eax
0x180002f68  mov     r8, r12
0x180002f6b  call    WPP_SF_sd
0x180002f70  mov     eax, ebx
0x180002f72  mov     rcx, [rbp+4E0h+var_50]
  ... truncated ...
```
