# SslEncryptPacket

- ea: `0x18000d940`
- end: `0x18000dd4a`
- name: `SslEncryptPacket`
- size: `1034`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000d02c`
- `0x18000d940`
- `0x18000e120`
- `0x180020010`

## string_xrefs

- `0x18000d98f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000d9d5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000da6c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslEncryptPacket(__int64 a1, __int64 a2, int a3)
{
  unsigned int v3; // ebx
  __int64 result; // rax
  int v5; // eax

  if ( !a1 || *(_DWORD *)a1 < 0x1B0u || *(_DWORD *)(a1 + 4) != 1145324609 || *(_DWORD *)(a1 + 12) )
  {
    v3 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        78);
    return v3;
  }
  if ( !a2 || *(_DWORD *)a2 < 0x20u || *(_DWORD *)(a2 + 4) != 1145324610 )
  {
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 1110);
    return 2148073510LL;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 88))(*(_QWORD *)(a1 + 424), *(_QWORD *)(a2 + 16));
  v3 = v5;
  if ( v5 >= 0 )
    return 0;
  DebugTraceError((unsigned int)v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 1132);
  if ( (v3 & 0x1FFF0000) == 0x90000 || (v3 & 0x1FFF0000) == 0x100000 )
    return v3;
  if ( !v3 )
    return 0;
  if ( v3 > 0x216 )
  {
    if ( v3 > 0xC000007B )
    {
      if ( v3 <= 0xC0000135 )
      {
        if ( v3 == -1073741515 )
          return 2148073502LL;
        if ( v3 == -1073741637 )
          return 2148073513LL;
        if ( v3 != -1073741670 )
        {
          if ( v3 != -1073741595 )
            return v3;
          return 2148073517LL;
        }
        return 2148073486LL;
      }
      if ( v3 != -1073741502 && v3 != -1073741511 )
      {
        if ( v3 == -1073700864 )
          return 2148073478LL;
        return v3;
      }
    }
    else if ( v3 != -1073741701 )
    {
      if ( v3 == -1073741816 )
        return 2148073510LL;
      if ( v3 <= 0xC0000008 )
      {
        if ( v3 == -2147023680 )
          return 2147943616LL;
        if ( v3 != 1359 )
        {
          if ( v3 == -2147023673 )
            return 2147943623LL;
          if ( v3 == -2147023496 )
            return 2147943800LL;
          return v3;
        }
        return 2148073517LL;
      }
      if ( v3 == -1073741811 )
        return 2148073511LL;
      if ( v3 != -1073741801 )
      {
        if ( v3 == -1073741789 )
          return 2148073512LL;
        return v3;
      }
      return 2148073486LL;
    }
    return 2148073501LL;
  }
  if ( v3 == 534 )
    return 2147942934LL;
  switch ( v3 )
  {
    case 2u:
    case 3u:
      result = 2148073489LL;
      break;
    case 5u:
      result = 2148073488LL;
      break;
    case 8u:
    case 0xEu:
      return 2148073486LL;
    case 0x57u:
      return 2148073511LL;
    case 0x70u:
      result = 2147942512LL;
      break;
    case 0x7Au:
      return 2148073512LL;
    case 0xB7u:
      result = 2148073487LL;
      break;
    default:
      return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18000d940  push    rbx
0x18000d942  sub     rsp, 60h
0x18000d946  mov     r10, rcx
0x18000d949  test    rcx, rcx
0x18000d94c  jz      short loc_18000D965
0x18000d94e  cmp     dword ptr [rcx], 1B0h
0x18000d954  jb      short loc_18000D965
0x18000d956  cmp     dword ptr [rcx+4], 44444441h
0x18000d95d  jnz     short loc_18000D965
0x18000d95f  cmp     dword ptr [rcx+0Ch], 0
0x18000d963  jz      short loc_18000D9BC
0x18000d965  mov     ebx, 80090026h
0x18000d96a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d971  lea     rax, WPP_GLOBAL_Control
0x18000d978  cmp     rcx, rax
0x18000d97b  jz      def_18000DACB; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000d981  test    byte ptr [rcx+1Ch], 1
0x18000d985  jz      def_18000DACB; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000d98b  mov     rcx, [rcx+10h]
0x18000d98f  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d996  mov     dword ptr [rsp+68h+var_38], 44Eh
0x18000d99e  lea     r9, aStatus; "Status"
0x18000d9a5  mov     [rsp+68h+var_40], rax
0x18000d9aa  mov     dword ptr [rsp+68h+var_48], 80090026h
0x18000d9b2  call    WPP_SF_sDsd
0x18000d9b7  jmp     def_18000DACB; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000d9bc  test    rdx, rdx
0x18000d9bf  jz      short loc_18000D9CF
0x18000d9c1  cmp     dword ptr [rdx], 20h ; ' '
0x18000d9c4  jb      short loc_18000D9CF
0x18000d9c6  cmp     dword ptr [rdx+4], 44444442h
0x18000d9cd  jz      short loc_18000D9FA
0x18000d9cf  mov     r9d, 456h
0x18000d9d5  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d9dc  lea     rdx, aStatus; "Status"
0x18000d9e3  mov     ecx, 80090026h
0x18000d9e8  mov     ebx, 80090026h
0x18000d9ed  call    DebugTraceError
0x18000d9f2  mov     eax, ebx
0x18000d9f4  add     rsp, 60h
0x18000d9f8  pop     rbx
0x18000d9f9  retn
0x18000d9fa  mov     eax, [rsp+68h+arg_48]
0x18000da01  mov     ecx, [rsp+68h+arg_40]
0x18000da08  mov     rdx, [rdx+10h]
0x18000da0c  mov     [rsp+68h+var_20], eax
0x18000da10  mov     rax, [r10+58h]
0x18000da14  mov     [rsp+68h+var_28], ecx
0x18000da18  mov     rcx, [rsp+68h+arg_38]
0x18000da20  mov     [rsp+68h+var_30], rcx
0x18000da25  mov     rcx, [rsp+68h+arg_30]
0x18000da2d  mov     [rsp+68h+var_38], rcx
0x18000da32  mov     ecx, [rsp+68h+arg_28]
0x18000da39  mov     dword ptr [rsp+68h+var_40], ecx
0x18000da3d  mov     rcx, [rsp+68h+arg_20]
0x18000da45  mov     [rsp+68h+var_48], rcx
0x18000da4a  mov     rcx, [r10+1A8h]
0x18000da51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da56  mov     ebx, eax
0x18000da58  test    eax, eax
0x18000da5a  js      short loc_18000DA66
0x18000da5c  xor     ebx, ebx
0x18000da5e  mov     eax, ebx; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000da60  add     rsp, 60h
0x18000da64  pop     rbx
0x18000da65  retn
0x18000da66  mov     r9d, 46Ch
0x18000da6c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da73  lea     rdx, aStatus; "Status"
0x18000da7a  mov     ecx, ebx
0x18000da7c  call    DebugTraceError
0x18000da81  mov     eax, ebx
0x18000da83  and     eax, 1FFF0000h
0x18000da88  cmp     eax, 90000h
0x18000da8d  jz      short def_18000DACB; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000da8f  cmp     eax, 100000h
0x18000da94  jz      short def_18000DACB; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000da96  test    ebx, ebx
0x18000da98  jz      short loc_18000DA5C
0x18000da9a  cmp     ebx, 216h
0x18000daa0  ja      short loc_18000DADA
0x18000daa2  jz      loc_18000DBEA
0x18000daa8  lea     eax, [rbx-2]; switch 182 cases
0x18000daab  cmp     eax, 0B5h
0x18000dab0  ja      short def_18000DACB; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000dab2  lea     rdx, __ImageBase
0x18000dab9  movzx   eax, ds:(byte_18000DC94 - 180000000h)[rdx+rax]
0x18000dac1  mov     ecx, ds:(jpt_18000DACB - 180000000h)[rdx+rax*4]
0x18000dac8  add     rcx, rdx
0x18000dacb  jmp     rcx; switch jump
0x18000dacd  mov     ebx, 80090027h; jumptable 000000018000DACB case 87
0x18000dad2  mov     eax, ebx
0x18000dad4  add     rsp, 60h
0x18000dad8  pop     rbx
0x18000dad9  retn
0x18000dada  cmp     ebx, 0C000007Bh
0x18000dae0  ja      short loc_18000DB37
0x18000dae2  jz      loc_18000DC2B
0x18000dae8  cmp     ebx, 0C0000008h
0x18000daee  jz      loc_18000DB9C
0x18000daf4  ja      loc_18000DC38
0x18000dafa  cmp     ebx, 800704C0h
0x18000db00  jz      loc_18000DB8F
0x18000db06  cmp     ebx, 54Fh
0x18000db0c  jz      loc_18000DBF7
0x18000db12  cmp     ebx, 800704C7h
0x18000db18  jz      loc_18000DC04
0x18000db1e  cmp     ebx, 80070578h
0x18000db24  jnz     def_18000DACB; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000db2a  mov     ebx, 80070578h
0x18000db2f  mov     eax, ebx
0x18000db31  add     rsp, 60h
0x18000db35  pop     rbx
0x18000db36  retn
0x18000db37  cmp     ebx, 0C0000135h
0x18000db3d  ja      short loc_18000DB5E
0x18000db3f  jz      loc_18000DC1E
0x18000db45  cmp     ebx, 0C00000BBh
0x18000db4b  jnz     loc_18000DC5D
0x18000db51  mov     ebx, 80090029h
0x18000db56  mov     eax, ebx
0x18000db58  add     rsp, 60h
0x18000db5c  pop     rbx
0x18000db5d  retn
0x18000db5e  cmp     ebx, 0C0000142h
0x18000db64  jz      loc_18000DC2B
0x18000db6a  cmp     ebx, 0C0000139h
0x18000db70  jz      loc_18000DC2B
0x18000db76  cmp     ebx, 0C000A000h
0x18000db7c  jnz     def_18000DACB; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000db82  mov     ebx, 80090006h
0x18000db87  mov     eax, ebx
0x18000db89  add     rsp, 60h
0x18000db8d  pop     rbx
0x18000db8e  retn
0x18000db8f  mov     ebx, 800704C0h
0x18000db94  mov     eax, ebx
0x18000db96  add     rsp, 60h
0x18000db9a  pop     rbx
0x18000db9b  retn
0x18000db9c  mov     ebx, 80090026h
0x18000dba1  mov     eax, ebx
0x18000dba3  add     rsp, 60h
0x18000dba7  pop     rbx
0x18000dba8  retn
0x18000dba9  mov     ebx, 80090028h; jumptable 000000018000DACB case 122
0x18000dbae  mov     eax, ebx
0x18000dbb0  add     rsp, 60h
0x18000dbb4  pop     rbx
0x18000dbb5  retn
0x18000dbb6  mov     ebx, 80090011h; jumptable 000000018000DACB cases 2,3
0x18000dbbb  mov     eax, ebx
0x18000dbbd  add     rsp, 60h
0x18000dbc1  pop     rbx
0x18000dbc2  retn
0x18000dbc3  mov     ebx, 80090010h; jumptable 000000018000DACB case 5
0x18000dbc8  mov     eax, ebx
0x18000dbca  add     rsp, 60h
0x18000dbce  pop     rbx
0x18000dbcf  retn
0x18000dbd0  mov     ebx, 80070070h; jumptable 000000018000DACB case 112
0x18000dbd5  mov     eax, ebx
0x18000dbd7  add     rsp, 60h
0x18000dbdb  pop     rbx
0x18000dbdc  retn
0x18000dbdd  mov     ebx, 8009000Fh; jumptable 000000018000DACB case 183
0x18000dbe2  mov     eax, ebx
0x18000dbe4  add     rsp, 60h
0x18000dbe8  pop     rbx
0x18000dbe9  retn
0x18000dbea  mov     ebx, 80070216h
0x18000dbef  mov     eax, ebx
0x18000dbf1  add     rsp, 60h
0x18000dbf5  pop     rbx
0x18000dbf6  retn
0x18000dbf7  mov     ebx, 8009002Dh
0x18000dbfc  mov     eax, ebx
0x18000dbfe  add     rsp, 60h
0x18000dc02  pop     rbx
0x18000dc03  retn
0x18000dc04  mov     ebx, 800704C7h
0x18000dc09  mov     eax, ebx
0x18000dc0b  add     rsp, 60h
0x18000dc0f  pop     rbx
0x18000dc10  retn
0x18000dc11  mov     ebx, 8009000Eh; jumptable 000000018000DACB cases 8,14
0x18000dc16  mov     eax, ebx
0x18000dc18  add     rsp, 60h
0x18000dc1c  pop     rbx
0x18000dc1d  retn
0x18000dc1e  mov     ebx, 8009001Eh
0x18000dc23  mov     eax, ebx
0x18000dc25  add     rsp, 60h
0x18000dc29  pop     rbx
0x18000dc2a  retn
0x18000dc2b  mov     ebx, 8009001Dh
0x18000dc30  mov     eax, ebx
0x18000dc32  add     rsp, 60h
0x18000dc36  pop     rbx
0x18000dc37  retn
0x18000dc38  cmp     ebx, 0C000000Dh
0x18000dc3e  jz      loc_18000DACD; jumptable 000000018000DACB case 87
0x18000dc44  cmp     ebx, 0C0000017h
0x18000dc4a  jz      short loc_18000DC11; jumptable 000000018000DACB cases 8,14
0x18000dc4c  cmp     ebx, 0C0000023h
0x18000dc52  jnz     def_18000DACB; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000dc58  jmp     loc_18000DBA9; jumptable 000000018000DACB case 122
0x18000dc5d  cmp     ebx, 0C000009Ah
0x18000dc63  jz      short loc_18000DC11; jumptable 000000018000DACB cases 8,14
0x18000dc65  cmp     ebx, 0C00000E5h
0x18000dc6b  jnz     def_18000DACB; jumptable 000000018000DACB default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000dc71  jmp     short loc_18000DBF7
```
