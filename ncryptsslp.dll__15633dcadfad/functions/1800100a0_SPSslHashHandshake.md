# SPSslHashHandshake

- ea: `0x1800100a0`
- end: `0x180010278`
- name: `SPSslHashHandshake`
- size: `472`
- prototype: `__int64 __fastcall(_DWORD *, __int64, UCHAR *, ULONG, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x1800100a0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18001017b`
- `bcrypt!BCryptHashData` at `0x1800101e9`
- `bcrypt!BCryptHashData` at `0x18001017b`
- `bcrypt!BCryptHashData` at `0x1800101e9`

## string_xrefs

- `0x1800100f6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800101c7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800101fb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001023b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180010256`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslHashHandshake(_DWORD *a1, __int64 a2, UCHAR *a3, ULONG a4, int a5)
{
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  int v10; // edx
  int v11; // r8d
  void *v12; // rcx
  NTSTATUS v14; // eax
  char v15; // [rsp+30h] [rbp-38h]

  if ( a1 && *a1 >= 0x310u && a1[1] == 1936944177 )
  {
    if ( a2 && *(_DWORD *)a2 >= 0x30u && *(_DWORD *)(a2 + 4) == 1936944178 )
    {
      if ( a3 )
      {
        if ( a5 )
        {
          v8 = -2146893815;
          DebugTraceError(
            2148073481LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            3439);
          return v8;
        }
        if ( a4 )
        {
          v8 = BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a2 + 16), a3, a4, 0);
          if ( (v8 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v10,
                v11,
                (unsigned int)"Status",
                v8,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                124);
            return v8;
          }
          v12 = *(void **)(a2 + 32);
          if ( v12 )
          {
            v14 = BCryptHashData(v12, a3, a4, 0);
            v8 = v14;
            if ( v14 < 0 )
            {
              DebugTraceError(
                (unsigned int)v14,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                3465);
              return v8;
            }
          }
        }
        return 0;
      }
      v8 = -2146893785;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          0,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          104);
    }
    else
    {
      v8 = -2146893786;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 97;
        goto LABEL_7;
      }
    }
  }
  else
  {
    v8 = -2146893786;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 88;
LABEL_7:
      WPP_SF_sDsd(
        v9[2],
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v15);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800100a0  push    rbx
0x1800100a2  push    rbp
0x1800100a3  push    rsi
0x1800100a4  push    rdi
0x1800100a5  sub     rsp, 48h
0x1800100a9  mov     esi, r9d
0x1800100ac  mov     rbp, r8
0x1800100af  mov     rbx, rdx
0x1800100b2  test    rcx, rcx
0x1800100b5  jz      short loc_1800100C8
0x1800100b7  cmp     dword ptr [rcx], 310h
0x1800100bd  jb      short loc_1800100C8
0x1800100bf  cmp     dword ptr [rcx+4], 73736C31h
0x1800100c6  jz      short loc_18001011C
0x1800100c8  mov     edi, 80090026h
0x1800100cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100d4  lea     rax, WPP_GLOBAL_Control
0x1800100db  cmp     rcx, rax
0x1800100de  jz      loc_180010196
0x1800100e4  test    byte ptr [rcx+1Ch], 1
0x1800100e8  jz      loc_180010196
0x1800100ee  mov     dword ptr [rsp+68h+var_38], 0D58h
0x1800100f6  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800100fd  mov     [rsp+68h+var_40], rax
0x180010102  mov     [rsp+68h+var_48], 80090026h
0x18001010a  mov     rcx, [rcx+10h]
0x18001010e  lea     r9, aStatus; "Status"
0x180010115  call    WPP_SF_sDsd
0x18001011a  jmp     short loc_180010196
0x18001011c  test    rbx, rbx
0x18001011f  jz      short loc_18001012F
0x180010121  cmp     dword ptr [rdx], 30h ; '0'
0x180010124  jb      short loc_18001012F
0x180010126  cmp     dword ptr [rdx+4], 73736C32h
0x18001012d  jz      short loc_180010157
0x18001012f  mov     edi, 80090026h
0x180010134  mov     rcx, cs:WPP_GLOBAL_Control
0x18001013b  lea     rax, WPP_GLOBAL_Control
0x180010142  cmp     rcx, rax
0x180010145  jz      short loc_180010196
0x180010147  test    byte ptr [rcx+1Ch], 1
0x18001014b  jz      short loc_180010196
0x18001014d  mov     dword ptr [rsp+68h+var_38], 0D61h
0x180010155  jmp     short loc_1800100F6
0x180010157  test    rbp, rbp
0x18001015a  jz      short loc_1800101A1
0x18001015c  cmp     [rsp+68h+arg_20], 0
0x180010164  jnz     loc_180010250
0x18001016a  test    esi, esi
0x18001016c  jz      short loc_180010194
0x18001016e  mov     rcx, [rbx+10h]; hHash
0x180010172  xor     r9d, r9d; dwFlags
0x180010175  mov     r8d, esi; cbInput
0x180010178  mov     rdx, rbp; pbInput
0x18001017b  call    cs:__imp_BCryptHashData
0x180010181  mov     edi, eax
0x180010183  test    eax, eax
0x180010185  js      loc_180010212
0x18001018b  mov     rcx, [rbx+20h]; hHash
0x18001018f  test    rcx, rcx
0x180010192  jnz     short loc_1800101E0
0x180010194  xor     edi, edi
0x180010196  mov     eax, edi
0x180010198  add     rsp, 48h
0x18001019c  pop     rdi
0x18001019d  pop     rsi
0x18001019e  pop     rbp
0x18001019f  pop     rbx
0x1800101a0  retn
0x1800101a1  mov     edi, 80090027h
0x1800101a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101ad  lea     rax, WPP_GLOBAL_Control
0x1800101b4  cmp     rcx, rax
0x1800101b7  jz      short loc_180010196
0x1800101b9  test    byte ptr [rcx+1Ch], 1
0x1800101bd  jz      short loc_180010196
0x1800101bf  mov     dword ptr [rsp+68h+var_38], 0D68h
0x1800101c7  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800101ce  mov     [rsp+68h+var_40], rax
0x1800101d3  mov     [rsp+68h+var_48], 80090027h
0x1800101db  jmp     loc_18001010A
0x1800101e0  xor     r9d, r9d; dwFlags
0x1800101e3  mov     r8d, esi; cbInput
0x1800101e6  mov     rdx, rbp; pbInput
0x1800101e9  call    cs:__imp_BCryptHashData
0x1800101ef  mov     edi, eax
0x1800101f1  test    eax, eax
0x1800101f3  jns     short loc_180010194
0x1800101f5  mov     r9d, 0D89h
0x1800101fb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010202  lea     rdx, aStatus; "Status"
0x180010209  mov     ecx, eax
0x18001020b  call    DebugTraceError
0x180010210  jmp     short loc_180010196
0x180010212  mov     rcx, cs:WPP_GLOBAL_Control
0x180010219  lea     rax, WPP_GLOBAL_Control
0x180010220  cmp     rcx, rax
0x180010223  jz      loc_180010196
0x180010229  test    byte ptr [rcx+1Ch], 1
0x18001022d  jz      loc_180010196
0x180010233  mov     dword ptr [rsp+68h+var_38], 0D7Ch
0x18001023b  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010242  mov     [rsp+68h+var_40], rax
0x180010247  mov     [rsp+68h+var_48], edi
0x18001024b  jmp     loc_18001010A
0x180010250  mov     r9d, 0D6Fh
0x180010256  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001025d  lea     rdx, aStatus; "Status"
0x180010264  mov     ecx, 80090009h
0x180010269  mov     edi, 80090009h
0x18001026e  call    DebugTraceError
0x180010273  jmp     loc_180010196
```
