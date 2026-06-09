# SPSslEncryptPacket

- ea: `0x18000bb90`
- end: `0x18000be45`
- name: `SPSslEncryptPacket`
- size: `693`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, __int64, unsigned int, __int64, int, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x18000bb90`
- `0x18000be50`
- `0x18000c1c0`

## string_xrefs

- `0x18000bc23`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000bd1b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000bd56`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000bd9d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000bde4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000be03`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000be2b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslEncryptPacket(
        _DWORD *a1,
        _DWORD *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10)
{
  int v10; // ebx
  _QWORD *v11; // rcx
  int v12; // eax
  int v13; // eax
  int v15; // edx
  int v16; // r8d
  char v17; // [rsp+30h] [rbp-28h]

  if ( a1 && *a1 >= 0x310u && a1[1] == 1936944177 )
  {
    if ( a2 && *a2 >= 0x70u && a2[1] == 1936944179 )
    {
      if ( a3 && a4 <= 0x8000 )
      {
        if ( a5 && a7 )
        {
          if ( a10 )
          {
            v10 = -2146893815;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                (_DWORD)a2,
                a5,
                (unsigned int)"Status",
                9,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                82);
          }
          else
          {
            v12 = a2[2];
            if ( v12 == 2 )
            {
              v10 = -2146893783;
              DebugTraceError(
                2148073513LL,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                1887);
            }
            else if ( v12 == 772 )
            {
              v13 = Tls13EncryptPacket(a1, a2, a3, a4, a5, a6, a7, a8, a9);
              v10 = v13;
              if ( v13 < 0 )
                DebugTraceError(
                  (unsigned int)v13,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                  1904);
            }
            else
            {
              v10 = TlsEncryptPacket(a1, a2, a3, a4, a5, a6, a7, a8, a9);
              if ( v10 < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v15,
                  v16,
                  (unsigned int)"Status",
                  v10,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                  130);
              }
            }
          }
        }
        else
        {
          v10 = -2146893785;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              a5,
              (unsigned int)"Status",
              39,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              75);
        }
      }
      else
      {
        v10 = -2146893785;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)a2,
            a3,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            68);
      }
    }
    else
    {
      v10 = -2146893786;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 61;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v10 = -2146893786;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 52;
LABEL_13:
      WPP_SF_sDsd(
        v11[2],
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v17);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000bb90  push    rbx
0x18000bb92  sub     rsp, 50h
0x18000bb96  mov     r10d, r9d
0x18000bb99  mov     r11, r8
0x18000bb9c  test    rcx, rcx
0x18000bb9f  jz      short loc_18000BBB2
0x18000bba1  cmp     dword ptr [rcx], 310h
0x18000bba7  jb      short loc_18000BBB2
0x18000bba9  cmp     dword ptr [rcx+4], 73736C31h
0x18000bbb0  jz      short loc_18000BBE2
0x18000bbb2  mov     ebx, 80090026h
0x18000bbb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbbe  lea     rax, WPP_GLOBAL_Control
0x18000bbc5  cmp     rcx, rax
0x18000bbc8  jz      loc_18000BCE7
0x18000bbce  test    byte ptr [rcx+1Ch], 1
0x18000bbd2  jz      loc_18000BCE7
0x18000bbd8  mov     dword ptr [rsp+58h+var_28], 734h
0x18000bbe0  jmp     short loc_18000BC23
0x18000bbe2  test    rdx, rdx
0x18000bbe5  jz      short loc_18000BBF5
0x18000bbe7  cmp     dword ptr [rdx], 70h ; 'p'
0x18000bbea  jb      short loc_18000BBF5
0x18000bbec  cmp     dword ptr [rdx+4], 73736C33h
0x18000bbf3  jz      short loc_18000BC4C
0x18000bbf5  mov     ebx, 80090026h
0x18000bbfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc01  lea     rax, WPP_GLOBAL_Control
0x18000bc08  cmp     rcx, rax
0x18000bc0b  jz      loc_18000BCE7
0x18000bc11  test    byte ptr [rcx+1Ch], 1
0x18000bc15  jz      loc_18000BCE7
0x18000bc1b  mov     dword ptr [rsp+58h+var_28], 73Dh
0x18000bc23  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bc2a  mov     [rsp+58h+var_30], rax
0x18000bc2f  mov     dword ptr [rsp+58h+var_38], 80090026h
0x18000bc37  mov     rcx, [rcx+10h]
0x18000bc3b  lea     r9, aStatus; "Status"
0x18000bc42  call    WPP_SF_sDsd
0x18000bc47  jmp     loc_18000BCE7
0x18000bc4c  test    r11, r11
0x18000bc4f  jz      loc_18000BDB6
0x18000bc55  cmp     r10d, 8000h
0x18000bc5c  ja      loc_18000BDB6
0x18000bc62  mov     r8, [rsp+58h+arg_20]
0x18000bc6a  test    r8, r8
0x18000bc6d  jz      loc_18000BD30
0x18000bc73  mov     r9, [rsp+58h+arg_30]
0x18000bc7b  test    r9, r9
0x18000bc7e  jz      loc_18000BD30
0x18000bc84  cmp     [rsp+58h+arg_48], 0
0x18000bc8c  jnz     loc_18000BD6F
0x18000bc92  mov     eax, [rdx+8]
0x18000bc95  cmp     eax, 2
0x18000bc98  jz      loc_18000BDFD
0x18000bc9e  cmp     eax, 304h
0x18000bca3  mov     eax, [rsp+58h+arg_40]
0x18000bcaa  mov     [rsp+58h+var_18], eax
0x18000bcae  mov     rax, [rsp+58h+arg_38]
0x18000bcb6  mov     [rsp+58h+var_20], rax
0x18000bcbb  mov     eax, [rsp+58h+arg_28]
0x18000bcc2  mov     [rsp+58h+var_28], r9
0x18000bcc7  mov     r9d, r10d
0x18000bcca  mov     dword ptr [rsp+58h+var_30], eax
0x18000bcce  mov     [rsp+58h+var_38], r8
0x18000bcd3  mov     r8, r11
0x18000bcd6  jnz     short loc_18000BCEF
0x18000bcd8  call    Tls13EncryptPacket
0x18000bcdd  mov     ebx, eax
0x18000bcdf  test    eax, eax
0x18000bce1  js      loc_18000BE25
0x18000bce7  mov     eax, ebx
0x18000bce9  add     rsp, 50h
0x18000bced  pop     rbx
0x18000bcee  retn
0x18000bcef  call    TlsEncryptPacket
0x18000bcf4  mov     ebx, eax
0x18000bcf6  test    eax, eax
0x18000bcf8  jns     short loc_18000BCE7
0x18000bcfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd01  lea     rax, WPP_GLOBAL_Control
0x18000bd08  cmp     rcx, rax
0x18000bd0b  jz      short loc_18000BCE7
0x18000bd0d  test    byte ptr [rcx+1Ch], 1
0x18000bd11  jz      short loc_18000BCE7
0x18000bd13  mov     dword ptr [rsp+58h+var_28], 782h
0x18000bd1b  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bd22  mov     [rsp+58h+var_30], rax
0x18000bd27  mov     dword ptr [rsp+58h+var_38], ebx
0x18000bd2b  jmp     loc_18000BC37
0x18000bd30  mov     ebx, 80090027h
0x18000bd35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd3c  lea     rax, WPP_GLOBAL_Control
0x18000bd43  cmp     rcx, rax
0x18000bd46  jz      short loc_18000BCE7
0x18000bd48  test    byte ptr [rcx+1Ch], 1
0x18000bd4c  jz      short loc_18000BCE7
0x18000bd4e  mov     dword ptr [rsp+58h+var_28], 74Bh
0x18000bd56  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bd5d  mov     [rsp+58h+var_30], rax
0x18000bd62  mov     dword ptr [rsp+58h+var_38], 80090027h
0x18000bd6a  jmp     loc_18000BC37
0x18000bd6f  mov     ebx, 80090009h
0x18000bd74  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd7b  lea     rax, WPP_GLOBAL_Control
0x18000bd82  cmp     rcx, rax
0x18000bd85  jz      loc_18000BCE7
0x18000bd8b  test    byte ptr [rcx+1Ch], 1
0x18000bd8f  jz      loc_18000BCE7
0x18000bd95  mov     dword ptr [rsp+58h+var_28], 752h
0x18000bd9d  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bda4  mov     [rsp+58h+var_30], rax
0x18000bda9  mov     dword ptr [rsp+58h+var_38], 80090009h
0x18000bdb1  jmp     loc_18000BC37
0x18000bdb6  mov     ebx, 80090027h
0x18000bdbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdc2  lea     rax, WPP_GLOBAL_Control
0x18000bdc9  cmp     rcx, rax
0x18000bdcc  jz      loc_18000BCE7
0x18000bdd2  test    byte ptr [rcx+1Ch], 1
0x18000bdd6  jz      loc_18000BCE7
0x18000bddc  mov     dword ptr [rsp+58h+var_28], 744h
0x18000bde4  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bdeb  mov     [rsp+58h+var_30], rax
0x18000bdf0  mov     dword ptr [rsp+58h+var_38], 80090027h
0x18000bdf8  jmp     loc_18000BC37
0x18000bdfd  mov     r9d, 75Fh
0x18000be03  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000be0a  lea     rdx, aStatus; "Status"
0x18000be11  mov     ecx, 80090029h
0x18000be16  mov     ebx, 80090029h
0x18000be1b  call    DebugTraceError
0x18000be20  jmp     loc_18000BCE7
0x18000be25  mov     r9d, 770h
0x18000be2b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000be32  lea     rdx, aStatus; "Status"
0x18000be39  mov     ecx, eax
0x18000be3b  call    DebugTraceError
0x18000be40  jmp     loc_18000BCE7
```
