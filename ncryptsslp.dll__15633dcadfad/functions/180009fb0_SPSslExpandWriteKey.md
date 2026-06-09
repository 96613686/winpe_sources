# SPSslExpandWriteKey

- ea: `0x180009fb0`
- end: `0x18000a111`
- name: `SPSslExpandWriteKey`
- size: `353`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003050`
- `0x180009fb0`
- `0x18000b594`
- `0x18000b654`

## string_xrefs

- `0x18000a02b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000a08c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000a0b3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000a0f8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExpandWriteKey(_DWORD *a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  int v5; // eax

  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
    a1 = 0;
  if ( !a2 || *(_DWORD *)a2 < 0x70u || *(_DWORD *)(a2 + 4) != 1936944179 )
    a2 = 0;
  if ( a1 && a2 && *(_QWORD *)(a2 + 16) )
  {
    if ( a3 )
    {
      if ( *(_DWORD *)(a2 + 8) == 772 && *(_DWORD *)(a2 + 108) == 4 )
      {
        v5 = TlsExpandWriteKey();
        v3 = v5;
        if ( v5 < 0 )
          DebugTraceError(
            (unsigned int)v5,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            6332);
      }
      else
      {
        v3 = -2146893783;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            a3,
            (unsigned int)"Status",
            41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            174);
      }
    }
    else
    {
      v3 = -2146893785;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          0,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          166);
    }
  }
  else
  {
    v3 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        159);
  }
  return v3;
}

```

## disassembly

```asm
0x180009fb0  push    rbx
0x180009fb2  sub     rsp, 40h
0x180009fb6  test    rcx, rcx
0x180009fb9  jz      short loc_180009FCC
0x180009fbb  cmp     dword ptr [rcx], 310h
0x180009fc1  jb      short loc_180009FCC
0x180009fc3  cmp     dword ptr [rcx+4], 73736C31h
0x180009fca  jz      short loc_180009FCE
0x180009fcc  xor     ecx, ecx
0x180009fce  test    rdx, rdx
0x180009fd1  jz      short loc_180009FE1
0x180009fd3  cmp     dword ptr [rdx], 70h ; 'p'
0x180009fd6  jb      short loc_180009FE1
0x180009fd8  cmp     dword ptr [rdx+4], 73736C33h
0x180009fdf  jz      short loc_180009FE3
0x180009fe1  xor     edx, edx
0x180009fe3  test    rcx, rcx
0x180009fe6  jz      loc_18000A0CA
0x180009fec  test    rdx, rdx
0x180009fef  jz      loc_18000A0CA
0x180009ff5  cmp     qword ptr [rdx+10h], 0
0x180009ffa  jz      loc_18000A0CA
0x18000a000  test    r8, r8
0x18000a003  jnz     short loc_18000A057
0x18000a005  mov     ebx, 80090027h
0x18000a00a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a011  lea     rax, WPP_GLOBAL_Control
0x18000a018  cmp     rcx, rax
0x18000a01b  jz      short loc_18000A04F
0x18000a01d  test    byte ptr [rcx+1Ch], 1
0x18000a021  jz      short loc_18000A04F
0x18000a023  mov     [rsp+48h+var_18], 18A6h
0x18000a02b  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a032  mov     [rsp+48h+var_20], rax
0x18000a037  mov     [rsp+48h+var_28], 80090027h
0x18000a03f  mov     rcx, [rcx+10h]
0x18000a043  lea     r9, aStatus; "Status"
0x18000a04a  call    WPP_SF_sDsd
0x18000a04f  mov     eax, ebx
0x18000a051  add     rsp, 40h
0x18000a055  pop     rbx
0x18000a056  retn
0x18000a057  cmp     dword ptr [rdx+8], 304h
0x18000a05e  jnz     short loc_18000A066
0x18000a060  cmp     dword ptr [rdx+6Ch], 4
0x18000a064  jz      short loc_18000A0A2
0x18000a066  mov     ebx, 80090029h
0x18000a06b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a072  lea     rax, WPP_GLOBAL_Control
0x18000a079  cmp     rcx, rax
0x18000a07c  jz      short loc_18000A04F
0x18000a07e  test    byte ptr [rcx+1Ch], 1
0x18000a082  jz      short loc_18000A04F
0x18000a084  mov     [rsp+48h+var_18], 18AEh
0x18000a08c  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a093  mov     [rsp+48h+var_20], rax
0x18000a098  mov     [rsp+48h+var_28], 80090029h
0x18000a0a0  jmp     short loc_18000A03F
0x18000a0a2  call    TlsExpandWriteKey
0x18000a0a7  mov     ebx, eax
0x18000a0a9  test    eax, eax
0x18000a0ab  jns     short loc_18000A04F
0x18000a0ad  mov     r9d, 18BCh
0x18000a0b3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a0ba  lea     rdx, aStatus; "Status"
0x18000a0c1  mov     ecx, eax
0x18000a0c3  call    DebugTraceError
0x18000a0c8  jmp     short loc_18000A04F
0x18000a0ca  mov     ebx, 80090026h
0x18000a0cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0d6  lea     rax, WPP_GLOBAL_Control
0x18000a0dd  cmp     rcx, rax
0x18000a0e0  jz      loc_18000A04F
0x18000a0e6  test    byte ptr [rcx+1Ch], 1
0x18000a0ea  jz      loc_18000A04F
0x18000a0f0  mov     [rsp+48h+var_18], 189Fh
0x18000a0f8  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a0ff  mov     [rsp+48h+var_20], rax
0x18000a104  mov     [rsp+48h+var_28], 80090026h
0x18000a10c  jmp     loc_18000A03F
```
