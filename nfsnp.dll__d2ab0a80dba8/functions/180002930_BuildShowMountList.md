# BuildShowMountList

- ea: `0x180002930`
- end: `0x180002e11`
- name: `BuildShowMountList`
- size: `1249`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007fd0`

## callees

- `0x180002930`
- `0x180008420`
- `0x180008d20`
- `0x180008d7c`
- `0x180008e80`
- `0x180008f28`
- `0x1800090d4`
- `0x1800095c4`
- `0x18000bba4`
- `0x180011ba0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180002c33`
- `msvcrt!_wcsnicmp` at `0x180002c33`
- `msvcrt!mbstowcs` at `0x180002b18`
- `msvcrt!mbstowcs` at `0x180002bb4`
- `msvcrt!mbstowcs` at `0x180002b18`
- `msvcrt!mbstowcs` at `0x180002bb4`
- `msvcrt!strpbrk` at `0x180002a83`
- `msvcrt!strpbrk` at `0x180002a83`
- `msvcrt!wcstombs` at `0x180002a22`
- `msvcrt!wcstombs` at `0x180002a22`
- `KERNEL32!GetLastError` at `0x180002db8`
- `KERNEL32!GetLastError` at `0x180002db8`

## string_xrefs

- `0x18000295d`: `BuildShowMountList`

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
0x180002930  push    rbp
0x180002932  push    rbx
0x180002933  push    rsi
0x180002934  push    rdi
0x180002935  push    r12
0x180002937  push    r13
0x180002939  push    r14
0x18000293b  push    r15
0x18000293d  lea     rbp, [rsp-4A8h]
0x180002945  sub     rsp, 5A8h
0x18000294c  mov     rax, cs:__security_cookie
0x180002953  xor     rax, rsp
0x180002956  mov     [rbp+4E0h+var_50], rax
0x18000295d  movups  xmm0, xmmword ptr cs:aBuildshowmount; "BuildShowMountList"
0x180002964  mov     eax, dword ptr cs:aBuildshowmount+0Fh; "ist"
0x18000296a  xor     r13d, r13d
0x18000296d  mov     rsi, rcx
0x180002970  mov     [rsp+5E0h+hMem], r13
0x180002975  movups  xmmword ptr [rsp+5E0h+var_598], xmm0
0x18000297a  mov     dword ptr [rsp+5E0h+var_598+0Fh], eax
0x18000297e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002985  lea     r15, WPP_GLOBAL_Control
0x18000298c  lea     r12, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180002993  mov     r14b, 8
0x180002996  cmp     rcx, r15
0x180002999  jz      short loc_1800029EB
0x18000299b  test    byte ptr [rcx+1Ch], 1
0x18000299f  jz      short loc_1800029BD
0x1800029a1  mov     rcx, [rcx+10h]
0x1800029a5  lea     edx, [r13+26h]
0x1800029a9  lea     r9, [rsp+5E0h+var_598]
0x1800029ae  mov     r8, r12
0x1800029b1  call    WPP_SF_s
0x1800029b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029bd  cmp     rcx, r15
0x1800029c0  jz      short loc_1800029EB
0x1800029c2  test    [rcx+1Ch], r14b
0x1800029c6  jz      short loc_1800029EB
0x1800029c8  mov     rax, [rsi+68h]
0x1800029cc  lea     r9, [rsp+5E0h+var_598]
0x1800029d1  mov     rcx, [rcx+10h]
0x1800029d5  mov     edx, 27h ; '''
0x1800029da  mov     r8, r12
0x1800029dd  mov     rax, [rax+18h]
0x1800029e1  mov     [rsp+5E0h+var_5C0], rax
0x1800029e6  call    WPP_SF_sS
0x1800029eb  mov     rax, [rsi+68h]
0x1800029ef  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800029f3  mov     rdx, [rax+18h]
0x1800029f7  inc     rcx
0x1800029fa  cmp     [rdx+rcx*2], r13w
0x1800029ff  jnz     short loc_1800029F7
0x180002a01  cmp     word ptr [rdx+rcx*2-2], 3Ah ; ':'
0x180002a07  jnz     short loc_180002A0F
0x180002a09  mov     [rdx+rcx*2-2], r13w
0x180002a0f  mov     rdx, [rsi+68h]
0x180002a13  lea     rcx, [rsp+5E0h+Dest]; Dest
0x180002a18  mov     r8d, 104h; MaxCount
0x180002a1e  mov     rdx, [rdx+18h]; Source
0x180002a22  call    cs:__imp_wcstombs
0x180002a28  dec     eax
0x180002a2a  cmp     eax, 0FFFFFFFDh
0x180002a2d  ja      loc_180002DB8
0x180002a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a3a  cmp     rcx, r15
0x180002a3d  jz      short loc_180002A65
0x180002a3f  test    [rcx+1Ch], r14b
0x180002a43  jz      short loc_180002A65
0x180002a45  mov     rcx, [rcx+10h]
0x180002a49  lea     rax, [rsp+5E0h+Dest]
0x180002a4e  mov     edx, 29h ; ')'
0x180002a53  mov     [rsp+5E0h+var_5C0], rax
0x180002a58  lea     r9, [rsp+5E0h+var_598]
0x180002a5d  mov     r8, r12
0x180002a60  call    WPP_SF_ss
0x180002a65  cmp     [rsp+5E0h+Dest], 5Ch ; '\'
0x180002a6a  lea     rbx, [rsp+5E0h+Dest]
0x180002a6f  jnz     short loc_180002A79
0x180002a71  inc     rbx
0x180002a74  cmp     byte ptr [rbx], 5Ch ; '\'
0x180002a77  jz      short loc_180002A71
0x180002a79  lea     rdx, Control; "\\/"
0x180002a80  mov     rcx, rbx; Str
0x180002a83  call    cs:__imp_strpbrk
0x180002a89  mov     rdi, rax
0x180002a8c  test    rax, rax
0x180002a8f  jz      loc_180002D25
0x180002a95  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a9c  cmp     rcx, r15
0x180002a9f  jz      short loc_180002ABD
0x180002aa1  test    [rcx+1Ch], r14b
0x180002aa5  jz      short loc_180002ABD
0x180002aa7  mov     rcx, [rcx+10h]
0x180002aab  lea     r9, [rsp+5E0h+var_598]
0x180002ab0  mov     edx, 2Ah ; '*'
0x180002ab5  mov     r8, r12
0x180002ab8  call    WPP_SF_s
0x180002abd  mov     [rdi], r13b
0x180002ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ac7  cmp     rcx, r15
0x180002aca  jz      short loc_180002AED
0x180002acc  test    [rcx+1Ch], r14b
0x180002ad0  jz      short loc_180002AED
0x180002ad2  mov     rcx, [rcx+10h]
0x180002ad6  lea     r9, [rsp+5E0h+var_598]
0x180002adb  mov     edx, 2Bh ; '+'
0x180002ae0  mov     [rsp+5E0h+var_5C0], rbx
0x180002ae5  mov     r8, r12
0x180002ae8  call    WPP_SF_ss
0x180002aed  lea     rdx, [rsp+5E0h+hMem]
0x180002af2  mov     rcx, rbx
0x180002af5  call    NfsNpCallRpc
0x180002afa  mov     rsi, [rsp+5E0h+hMem]
0x180002aff  test    rsi, rsi
0x180002b02  jz      loc_180002CF0
0x180002b08  inc     rdi
0x180002b0b  lea     rcx, [rbp+4E0h+String1]; Dest
0x180002b0f  mov     rdx, rdi; Source
0x180002b12  mov     r8d, 104h; MaxCount
0x180002b18  call    cs:__imp_mbstowcs
0x180002b1e  cmp     eax, 0FFFFFFFFh
0x180002b21  jnz     short loc_180002B62
0x180002b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b2a  cmp     rcx, r15
0x180002b2d  jz      short loc_180002B50
0x180002b2f  test    byte ptr [rcx+1Ch], 2
0x180002b33  jz      short loc_180002B50
0x180002b35  mov     rcx, [rcx+10h]
0x180002b39  lea     r9, [rsp+5E0h+var_598]
0x180002b3e  mov     edx, 2Ch ; ','
0x180002b43  mov     [rsp+5E0h+var_5C0], rdi
0x180002b48  mov     r8, r12
0x180002b4b  call    WPP_SF_ss
0x180002b50  mov     rcx, rsi; hMem
0x180002b53  call    FreeExportList
0x180002b58  mov     eax, 43h ; 'C'
0x180002b5d  jmp     loc_180002DEE
0x180002b62  mov     r14d, r13d
0x180002b65  mov     rbx, rsi
0x180002b68  test    rsi, rsi
0x180002b6b  jz      loc_180002C93
0x180002b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b78  cmp     rcx, r15
0x180002b7b  jz      short loc_180002BA1
0x180002b7d  test    byte ptr [rcx+1Ch], 8
0x180002b81  jz      short loc_180002BA1
0x180002b83  mov     rax, [rbx]
0x180002b86  lea     r9, [rsp+5E0h+var_598]
0x180002b8b  mov     rcx, [rcx+10h]
0x180002b8f  mov     edx, 2Dh ; '-'
0x180002b94  mov     r8, r12
0x180002b97  mov     [rsp+5E0h+var_5C0], rax
0x180002b9c  call    WPP_SF_ss
0x180002ba1  mov     rdx, [rbx]
0x180002ba4  lea     rcx, [rbp+4E0h+String2]; Dest
0x180002bab  inc     rdx; Source
0x180002bae  mov     r8d, 104h; MaxCount
0x180002bb4  call    cs:__imp_mbstowcs
0x180002bba  mov     rdi, rax
0x180002bbd  cmp     eax, 0FFFFFFFFh
0x180002bc0  jnz     short loc_180002BEC
0x180002bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bc9  cmp     rcx, r15
0x180002bcc  jz      short loc_180002C44
0x180002bce  test    byte ptr [rcx+1Ch], 2
0x180002bd2  jz      short loc_180002C44
0x180002bd4  mov     rcx, [rcx+10h]
0x180002bd8  lea     r9, [rsp+5E0h+var_598]
0x180002bdd  mov     edx, 2Eh ; '.'
0x180002be2  mov     r8, r12
0x180002be5  call    WPP_SF_s
0x180002bea  jmp     short loc_180002C3D
0x180002bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bf3  cmp     rcx, r15
0x180002bf6  jz      short loc_180002C25
0x180002bf8  test    byte ptr [rcx+1Ch], 8
0x180002bfc  jz      short loc_180002C25
0x180002bfe  mov     rcx, [rcx+10h]; LoggerHandle
0x180002c02  lea     rax, [rbp+4E0h+String1]
0x180002c06  mov     [rsp+5E0h+var_5B0], rax; __int64
0x180002c0b  lea     r9, [rsp+5E0h+var_598]
0x180002c10  lea     rax, [rbp+4E0h+String2]
0x180002c17  mov     dword ptr [rsp+5E0h+var_5B8], edi; char
0x180002c1b  mov     [rsp+5E0h+var_5C0], rax; __int64
0x180002c20  call    WPP_SF_sSdS
0x180002c25  mov     r8d, edi; MaxCount
0x180002c28  lea     rdx, [rbp+4E0h+String2]; String2
0x180002c2f  lea     rcx, [rbp+4E0h+String1]; String1
0x180002c33  call    cs:__imp__wcsnicmp
0x180002c39  test    eax, eax
0x180002c3b  jz      short loc_180002C53
0x180002c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c44  mov     rbx, [rbx+18h]
0x180002c48  test    rbx, rbx
0x180002c4b  jnz     loc_180002B78
0x180002c51  jmp     short loc_180002C93
0x180002c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c5a  cmp     rcx, r15
0x180002c5d  jz      short loc_180002C8D
0x180002c5f  test    byte ptr [rcx+1Ch], 8
0x180002c63  jz      short loc_180002C8D
0x180002c65  mov     rcx, [rcx+10h]; LoggerHandle
0x180002c69  lea     rax, [rbp+4E0h+String1]
0x180002c6d  mov     qword ptr [rsp+5E0h+var_5B8], rax; __int64
0x180002c72  lea     r9, [rsp+5E0h+var_598]
0x180002c77  lea     rax, [rbp+4E0h+String2]
0x180002c7e  mov     edx, 30h ; '0'
0x180002c83  mov     [rsp+5E0h+var_5C0], rax; __int64
0x180002c88  call    WPP_SF_sSS
0x180002c8d  mov     r14d, 1
0x180002c93  mov     rcx, rsi; hMem
0x180002c96  call    FreeExportList
0x180002c9b  test    r14d, r14d
0x180002c9e  jz      short loc_180002CCF
0x180002ca0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ca7  cmp     rcx, r15
0x180002caa  jz      short loc_180002CC8
0x180002cac  test    byte ptr [rcx+1Ch], 2
0x180002cb0  jz      short loc_180002CC8
0x180002cb2  mov     edx, 31h ; '1'
0x180002cb7  mov     rcx, [rcx+10h]
0x180002cbb  lea     r9, [rsp+5E0h+var_598]
0x180002cc0  mov     r8, r12
0x180002cc3  call    WPP_SF_s
0x180002cc8  xor     eax, eax
0x180002cca  jmp     loc_180002DEE
0x180002ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cd6  cmp     rcx, r15
0x180002cd9  jz      loc_180002B58
0x180002cdf  test    byte ptr [rcx+1Ch], 2
0x180002ce3  jz      loc_180002B58
0x180002ce9  mov     edx, 32h ; '2'
0x180002cee  jmp     short loc_180002D0F
0x180002cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cf7  cmp     rcx, r15
0x180002cfa  jz      loc_180002B58
0x180002d00  test    byte ptr [rcx+1Ch], 2
0x180002d04  jz      loc_180002B58
0x180002d0a  mov     edx, 33h ; '3'
0x180002d0f  mov     rcx, [rcx+10h]
0x180002d13  lea     r9, [rsp+5E0h+var_598]
0x180002d18  mov     r8, r12
0x180002d1b  call    WPP_SF_s
0x180002d20  jmp     loc_180002B58
0x180002d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d2c  cmp     rcx, r15
0x180002d2f  jz      short loc_180002D59
0x180002d31  test    [rcx+1Ch], r14b
0x180002d35  jz      short loc_180002D59
0x180002d37  mov     rcx, [rcx+10h]
0x180002d3b  lea     r9, [rsp+5E0h+var_598]
0x180002d40  mov     edx, 34h ; '4'
0x180002d45  mov     [rsp+5E0h+var_5C0], rbx
0x180002d4a  mov     r8, r12
0x180002d4d  call    WPP_SF_ss
0x180002d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d59  test    byte ptr [rsi+4], 1
0x180002d5d  jz      short loc_180002D9B
0x180002d5f  cmp     rcx, r15
0x180002d62  jz      short loc_180002D80
0x180002d64  test    [rcx+1Ch], r14b
0x180002d68  jz      short loc_180002D80
0x180002d6a  mov     rcx, [rcx+10h]
0x180002d6e  lea     r9, [rsp+5E0h+var_598]
0x180002d73  mov     edx, 35h ; '5'
0x180002d78  mov     r8, r12
0x180002d7b  call    WPP_SF_s
0x180002d80  lea     rdx, [rsi+58h]
0x180002d84  mov     rcx, rbx
0x180002d87  call    NfsNpCallRpc
0x180002d8c  test    eax, eax
0x180002d8e  jnz     loc_180002B58
0x180002d94  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d9b  cmp     rcx, r15
0x180002d9e  jz      loc_180002CC8
0x180002da4  test    byte ptr [rcx+1Ch], 1
0x180002da8  jz      loc_180002CC8
0x180002dae  mov     edx, 36h ; '6'
0x180002db3  jmp     loc_180002CB7
0x180002db8  call    cs:__imp_GetLastError
0x180002dbe  mov     ebx, eax
0x180002dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dc7  cmp     rcx, r15
0x180002dca  jz      short loc_180002DEC
0x180002dcc  test    byte ptr [rcx+1Ch], 2
0x180002dd0  jz      short loc_180002DEC
0x180002dd2  mov     rcx, [rcx+10h]
0x180002dd6  lea     r9, [rsp+5E0h+var_598]
0x180002ddb  mov     edx, 28h ; '('
0x180002de0  mov     dword ptr [rsp+5E0h+var_5C0], eax
0x180002de4  mov     r8, r12
0x180002de7  call    WPP_SF_sd
0x180002dec  mov     eax, ebx
0x180002dee  mov     rcx, [rbp+4E0h+var_50]
0x180002df5  xor     rcx, rsp; StackCookie
0x180002df8  call    __security_check_cookie
0x180002dfd  add     rsp, 5A8h
0x180002e04  pop     r15
0x180002e06  pop     r14
0x180002e08  pop     r13
  ... truncated ...
```
