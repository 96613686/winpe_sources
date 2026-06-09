# SPSslDecryptPacket

- ea: `0x18000ec00`
- end: `0x18000ee8e`
- name: `SPSslDecryptPacket`
- size: `654`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, unsigned __int8 *, unsigned int, UCHAR *, ULONG, ULONG *, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x18000ec00`
- `0x18000eea0`
- `0x18000f2d0`

## string_xrefs

- `0x18000ec93`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000eda0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000ede2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000ee25`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000ee44`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000ee6c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslDecryptPacket(
        _DWORD *a1,
        _DWORD *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        UCHAR *a5,
        ULONG a6,
        ULONG *a7,
        __int64 a8,
        int a9)
{
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  int v11; // eax
  int v12; // edx
  int v13; // r8d
  _QWORD *v15; // rcx
  char v16; // [rsp+30h] [rbp-18h]
  char v17; // [rsp+30h] [rbp-18h]

  if ( a1 && *a1 >= 0x310u && a1[1] == 1936944177 )
  {
    if ( a2 && *a2 >= 0x70u && a2[1] == 1936944179 )
    {
      if ( a3 && a4 - 1 <= 0xFFFF )
      {
        if ( !a5 || !a7 )
        {
          v9 = -2146893785;
          DebugTraceError(
            2148073511LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            1743);
          return v9;
        }
        if ( !a9 )
        {
          v11 = a2[2];
          if ( v11 == 2 )
          {
            v9 = -2146893783;
            DebugTraceError(
              2148073513LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              1763);
            return v9;
          }
          if ( v11 == 772 )
          {
            v9 = Tls13DecryptPacket((int)a1, (int)a2, (int)a3, a4, a5, a6, (__int64)a7, a8);
            if ( (v9 & 0x80000000) == 0 )
              return v9;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return v9;
            v17 = -13;
          }
          else
          {
            v9 = TlsDecryptPacket((__int64)a1, (__int64)a2, a3, a4, a5, a6, a7, a8);
            if ( (v9 & 0x80000000) == 0 )
              return v9;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return v9;
            v17 = 4;
          }
          WPP_SF_sDsd(
            v15[2],
            v12,
            v13,
            (unsigned int)"Status",
            v9,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            v17);
          return v9;
        }
        v9 = -2146893815;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)a2,
            (_DWORD)a5,
            (unsigned int)"Status",
            9,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            214);
      }
      else
      {
        v9 = -2146893785;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)a2,
            (_DWORD)a3,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            200);
      }
    }
    else
    {
      v9 = -2146893786;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = -63;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v9 = -2146893786;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = -72;
LABEL_13:
      WPP_SF_sDsd(
        v10[2],
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v16);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000ec00  push    rbx
0x18000ec02  sub     rsp, 40h
0x18000ec06  mov     r11d, r9d
0x18000ec09  mov     r10, r8
0x18000ec0c  test    rcx, rcx
0x18000ec0f  jz      short loc_18000EC22
0x18000ec11  cmp     dword ptr [rcx], 310h
0x18000ec17  jb      short loc_18000EC22
0x18000ec19  cmp     dword ptr [rcx+4], 73736C31h
0x18000ec20  jz      short loc_18000EC52
0x18000ec22  mov     ebx, 80090026h
0x18000ec27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec2e  lea     rax, WPP_GLOBAL_Control
0x18000ec35  cmp     rcx, rax
0x18000ec38  jz      loc_18000ED44
0x18000ec3e  test    byte ptr [rcx+1Ch], 1
0x18000ec42  jz      loc_18000ED44
0x18000ec48  mov     dword ptr [rsp+48h+var_18], 6B8h
0x18000ec50  jmp     short loc_18000EC93
0x18000ec52  test    rdx, rdx
0x18000ec55  jz      short loc_18000EC65
0x18000ec57  cmp     dword ptr [rdx], 70h ; 'p'
0x18000ec5a  jb      short loc_18000EC65
0x18000ec5c  cmp     dword ptr [rdx+4], 73736C33h
0x18000ec63  jz      short loc_18000ECBC
0x18000ec65  mov     ebx, 80090026h
0x18000ec6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec71  lea     rax, WPP_GLOBAL_Control
0x18000ec78  cmp     rcx, rax
0x18000ec7b  jz      loc_18000ED44
0x18000ec81  test    byte ptr [rcx+1Ch], 1
0x18000ec85  jz      loc_18000ED44
0x18000ec8b  mov     dword ptr [rsp+48h+var_18], 6C1h
0x18000ec93  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ec9a  mov     qword ptr [rsp+48h+var_20], rax
0x18000ec9f  mov     dword ptr [rsp+48h+var_28], 80090026h
0x18000eca7  mov     rcx, [rcx+10h]
0x18000ecab  lea     r9, aStatus; "Status"
0x18000ecb2  call    WPP_SF_sDsd
0x18000ecb7  jmp     loc_18000ED44
0x18000ecbc  test    r10, r10
0x18000ecbf  jz      loc_18000ED7A
0x18000ecc5  lea     eax, [r9-1]
0x18000ecc9  cmp     eax, 0FFFFh
0x18000ecce  ja      loc_18000ED7A
0x18000ecd4  mov     r8, [rsp+48h+arg_20]
0x18000ecd9  test    r8, r8
0x18000ecdc  jz      loc_18000EE66
0x18000ece2  mov     r9, [rsp+48h+arg_30]
0x18000ecea  test    r9, r9
0x18000eced  jz      loc_18000EE66
0x18000ecf3  cmp     [rsp+48h+arg_40], 0
0x18000ecfb  jnz     loc_18000EDF7
0x18000ed01  mov     eax, [rdx+8]
0x18000ed04  cmp     eax, 2
0x18000ed07  jz      loc_18000EE3E
0x18000ed0d  cmp     eax, 304h
0x18000ed12  mov     rax, [rsp+48h+arg_38]
0x18000ed1a  mov     [rsp+48h+var_10], rax; __int64
0x18000ed1f  mov     eax, [rsp+48h+arg_28]
0x18000ed23  mov     [rsp+48h+var_18], r9; __int64
0x18000ed28  mov     r9d, r11d; int
0x18000ed2b  mov     [rsp+48h+var_20], eax; ULONG
0x18000ed2f  mov     [rsp+48h+var_28], r8; PUCHAR
0x18000ed34  mov     r8, r10; int
0x18000ed37  jnz     short loc_18000ED4C
0x18000ed39  call    Tls13DecryptPacket
0x18000ed3e  mov     ebx, eax
0x18000ed40  test    eax, eax
0x18000ed42  js      short loc_18000EDB9
0x18000ed44  mov     eax, ebx
0x18000ed46  add     rsp, 40h
0x18000ed4a  pop     rbx
0x18000ed4b  retn
0x18000ed4c  call    TlsDecryptPacket
0x18000ed51  mov     ebx, eax
0x18000ed53  test    eax, eax
0x18000ed55  jns     short loc_18000ED44
0x18000ed57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed5e  lea     rax, WPP_GLOBAL_Control
0x18000ed65  cmp     rcx, rax
0x18000ed68  jz      short loc_18000ED44
0x18000ed6a  test    byte ptr [rcx+1Ch], 1
0x18000ed6e  jz      short loc_18000ED44
0x18000ed70  mov     dword ptr [rsp+48h+var_18], 704h
0x18000ed78  jmp     short loc_18000EDE2
0x18000ed7a  mov     ebx, 80090027h
0x18000ed7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed86  lea     rax, WPP_GLOBAL_Control
0x18000ed8d  cmp     rcx, rax
0x18000ed90  jz      short loc_18000ED44
0x18000ed92  test    byte ptr [rcx+1Ch], 1
0x18000ed96  jz      short loc_18000ED44
0x18000ed98  mov     dword ptr [rsp+48h+var_18], 6C8h
0x18000eda0  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eda7  mov     qword ptr [rsp+48h+var_20], rax
0x18000edac  mov     dword ptr [rsp+48h+var_28], 80090027h
0x18000edb4  jmp     loc_18000ECA7
0x18000edb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edc0  lea     rax, WPP_GLOBAL_Control
0x18000edc7  cmp     rcx, rax
0x18000edca  jz      loc_18000ED44
0x18000edd0  test    byte ptr [rcx+1Ch], 1
0x18000edd4  jz      loc_18000ED44
0x18000edda  mov     dword ptr [rsp+48h+var_18], 6F3h
0x18000ede2  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ede9  mov     qword ptr [rsp+48h+var_20], rax
0x18000edee  mov     dword ptr [rsp+48h+var_28], ebx
0x18000edf2  jmp     loc_18000ECA7
0x18000edf7  mov     ebx, 80090009h
0x18000edfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee03  lea     rax, WPP_GLOBAL_Control
0x18000ee0a  cmp     rcx, rax
0x18000ee0d  jz      loc_18000ED44
0x18000ee13  test    byte ptr [rcx+1Ch], 1
0x18000ee17  jz      loc_18000ED44
0x18000ee1d  mov     dword ptr [rsp+48h+var_18], 6D6h
0x18000ee25  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ee2c  mov     qword ptr [rsp+48h+var_20], rax
0x18000ee31  mov     dword ptr [rsp+48h+var_28], 80090009h
0x18000ee39  jmp     loc_18000ECA7
0x18000ee3e  mov     r9d, 6E3h
0x18000ee44  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ee4b  lea     rdx, aStatus; "Status"
0x18000ee52  mov     ecx, 80090029h
0x18000ee57  mov     ebx, 80090029h
0x18000ee5c  call    DebugTraceError
0x18000ee61  jmp     loc_18000ED44
0x18000ee66  mov     r9d, 6CFh
0x18000ee6c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ee73  lea     rdx, aStatus; "Status"
0x18000ee7a  mov     ecx, 80090027h
0x18000ee7f  mov     ebx, 80090027h
0x18000ee84  call    DebugTraceError
0x18000ee89  jmp     loc_18000ED44
```
