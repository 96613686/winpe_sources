# SuexParseIdLite(ushort const *,_SUEX_ID *)

- ea: `0x180037890`
- end: `0x180037b56`
- name: `?SuexParseIdLite@@YAKPEBGPEAU_SUEX_ID@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SUEX_ID *)`
- caller_count: `54`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001afd0`
- `0x18002e5d0`
- `0x18002e794`
- `0x18002ec80`
- `0x18002fc98`
- `0x180030324`
- `0x180030c50`
- `0x18003128c`
- `0x18003166c`
- `0x180031980`
- `0x180031e48`
- `0x180032310`
- `0x1800327b0`
- `0x1800329d0`
- `0x180032d84`
- `0x18003394c`
- `0x180034568`
- `0x180035820`
- `0x180037794`
- `0x18003e280`
- `0x180040a20`
- `0x180041ea8`
- `0x180042cd0`
- `0x180043504`
- `0x1800436a4`
- `0x180043ca8`
- `0x1800440cc`
- `0x180044400`
- `0x18004472c`
- `0x180053b10`
- `0x180058200`
- `0x180063294`
- `0x18007a404`
- `0x18007b76c`
- `0x18007bba8`
- `0x18009b724`
- `0x1800a027c`
- `0x1800a69c0`
- `0x1800a99c0`
- `0x1800aaa88`
- `0x1800c6950`
- `0x1800ccda4`
- `0x1800d2d68`
- `0x1800eb4c8`
- `0x1800ee8d0`
- `0x180100820`
- `0x18010cd68`
- `0x18010d0ec`
- `0x18010d69c`
- `0x18010d95c`

## callees

- `0x18000cd3c`
- `0x180037890`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800378a1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037a68`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037a7c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037ad1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037ae6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037afa`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037b13`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037b2c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800378a1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037a68`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037a7c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037ad1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037ae6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037afa`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037b13`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180037b2c`

## pseudocode

```c
__int64 __fastcall SuexParseIdLite(const unsigned __int16 *a1, struct _SUEX_ID *a2)
{
  unsigned __int16 v4; // ax
  const unsigned __int16 *v5; // r14
  unsigned int v6; // ecx
  unsigned int v7; // esi
  const OLECHAR *v8; // r14
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  const OLECHAR *v15; // rcx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  __int128 v21; // xmm0

  CLSIDFromString(a1, (LPCLSID)a2);
  *((_DWORD *)a2 + 4) = 2;
  v4 = a1[39];
  switch ( v4 )
  {
    case 'C':
      v5 = a1 + 40;
      if ( *v5 == 72 )
      {
        v6 = 40;
LABEL_39:
        *((_DWORD *)a2 + 5) = v6;
        goto LABEL_43;
      }
      return 50;
    case 'I':
      v5 = a1 + 40;
      if ( *v5 == 73 )
      {
        v6 = 1;
        goto LABEL_39;
      }
      return 50;
    case 'M':
      v5 = a1 + 40;
      if ( *v5 == 83 )
      {
        *((_DWORD *)a2 + 5) = 2;
        v6 = 2;
        goto LABEL_43;
      }
      return 50;
    case 'P':
      v5 = a1 + 40;
      if ( *v5 == 68 )
      {
        v6 = 4;
        goto LABEL_39;
      }
      if ( *v5 == 82 )
      {
        v6 = 34;
        goto LABEL_39;
      }
      return 50;
    case 'R':
      v5 = a1 + 40;
      switch ( *v5 )
      {
        case 'A':
          v6 = 41;
          goto LABEL_39;
        case 'C':
          v6 = 6;
          goto LABEL_39;
        case 'S':
          v6 = 7;
          goto LABEL_39;
      }
      return 50;
    case 'S':
      v5 = a1 + 40;
      switch ( *v5 )
      {
        case 'E':
          v6 = 8;
          goto LABEL_39;
        case 'I':
          v6 = 42;
          goto LABEL_39;
        case 'J':
          v6 = 9;
          goto LABEL_39;
        case 'N':
          *((_DWORD *)a2 + 5) = 10;
          v6 = 10;
          goto LABEL_43;
        case 'P':
          *((_DWORD *)a2 + 5) = 11;
          v6 = 11;
          goto LABEL_43;
        case 'S':
          v6 = 13;
          goto LABEL_39;
        case 'T':
          v6 = 12;
          goto LABEL_39;
        case 'U':
          v6 = 39;
          goto LABEL_39;
      }
      return 50;
  }
  if ( v4 != 86 )
    return 50;
  v5 = a1 + 40;
  if ( *v5 != 68 )
    return 50;
  *((_DWORD *)a2 + 5) = 16;
  v6 = 16;
LABEL_43:
  v7 = 0;
  v8 = v5 + 2;
  if ( v6 > 0xA )
  {
    v16 = v6 - 11;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( !v17 )
        goto LABEL_63;
      v18 = v17 - 4;
      if ( v18 )
      {
        v19 = v18 - 23;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( v20 )
          {
            if ( v20 - 1 > 1 )
              return v7;
          }
        }
LABEL_60:
        v15 = v8;
        goto LABEL_61;
      }
      CLSIDFromString(v8, (LPCLSID)((char *)a2 + 40));
      CLSIDFromString(v8 + 38, (LPCLSID)((char *)a2 + 56));
      v21 = *(_OWORD *)((char *)a2 + 56);
    }
    else
    {
      CLSIDFromString(v8, (LPCLSID)((char *)a2 + 40));
      v21 = *(_OWORD *)((char *)a2 + 40);
    }
    *(_OWORD *)((char *)a2 + 24) = v21;
    return v7;
  }
  if ( v6 == 10 )
    return (unsigned int)StringCchCopyW((unsigned __int16 *)a2 + 12, 0x10u, v8);
  v9 = v6 - 1;
  if ( !v9 )
    return (unsigned int)StringCchCopyW((unsigned __int16 *)a2 + 12, 0x10u, v8);
  v10 = v9 - 1;
  if ( !v10 )
    return (unsigned int)StringCchCopyW((unsigned __int16 *)a2 + 12, 0x10u, v8);
  v11 = v10 - 2;
  if ( !v11 )
    goto LABEL_60;
  v12 = v11 - 2;
  if ( !v12 )
    goto LABEL_60;
  v13 = v12 - 1;
  if ( !v13 )
  {
LABEL_63:
    CLSIDFromString(v8, (LPCLSID)((char *)a2 + 40));
    v15 = v8 + 38;
    goto LABEL_61;
  }
  v14 = v13 - 1;
  if ( !v14 )
    goto LABEL_60;
  if ( v14 == 1 )
  {
    CLSIDFromString(v8, (LPCLSID)((char *)a2 + 40));
    CLSIDFromString(v8 + 38, (LPCLSID)((char *)a2 + 56));
    v15 = v8 + 76;
LABEL_61:
    CLSIDFromString(v15, (LPCLSID)((char *)a2 + 24));
  }
  return v7;
}

```

## disassembly

```asm
0x180037890  push    rbx
0x180037892  push    rbp
0x180037893  push    rsi
0x180037894  push    rdi
0x180037895  push    r14
0x180037897  sub     rsp, 20h
0x18003789b  mov     rbp, rdx
0x18003789e  mov     r14, rcx
0x1800378a1  call    cs:__imp_CLSIDFromString
0x1800378a8  nop     dword ptr [rax+rax+00h]
0x1800378ad  mov     edx, 2
0x1800378b2  mov     [rbp+10h], edx
0x1800378b5  movzx   eax, word ptr [r14+4Eh]
0x1800378ba  lea     r10d, [rdx+0Eh]
0x1800378be  lea     r9d, [rdx+9]
0x1800378c2  lea     r8d, [rdx+8]
0x1800378c6  cmp     ax, 43h ; 'C'
0x1800378ca  jnz     short loc_1800378E3
0x1800378cc  add     r14, 50h ; 'P'
0x1800378d0  cmp     word ptr [r14], 48h ; 'H'
0x1800378d5  jnz     loc_180037B43
0x1800378db  lea     ecx, [rdx+26h]
0x1800378de  jmp     loc_1800379FE
0x1800378e3  cmp     ax, 49h ; 'I'
0x1800378e7  jnz     short loc_180037901
0x1800378e9  add     r14, 50h ; 'P'
0x1800378ed  cmp     [r14], ax
0x1800378f1  jnz     loc_180037B43
0x1800378f7  mov     ecx, 1
0x1800378fc  jmp     loc_1800379FE
0x180037901  cmp     ax, 4Dh ; 'M'
0x180037905  jnz     short loc_180037920
0x180037907  add     r14, 50h ; 'P'
0x18003790b  cmp     word ptr [r14], 53h ; 'S'
0x180037910  jnz     loc_180037B43
0x180037916  mov     [rbp+14h], edx
0x180037919  mov     ecx, edx
0x18003791b  jmp     loc_180037A23
0x180037920  cmp     ax, 50h ; 'P'
0x180037924  jnz     short loc_180037950
0x180037926  add     r14, 50h ; 'P'
0x18003792a  cmp     word ptr [r14], 44h ; 'D'
0x18003792f  jz      short loc_180037946
0x180037931  cmp     word ptr [r14], 52h ; 'R'
0x180037936  jnz     loc_180037B43
0x18003793c  mov     ecx, 22h ; '"'
0x180037941  jmp     loc_1800379FE
0x180037946  mov     ecx, 4
0x18003794b  jmp     loc_1800379FE
0x180037950  cmp     ax, 52h ; 'R'
0x180037954  jnz     short loc_18003798B
0x180037956  add     r14, 50h ; 'P'
0x18003795a  cmp     word ptr [r14], 41h ; 'A'
0x18003795f  jz      short loc_180037984
0x180037961  cmp     word ptr [r14], 43h ; 'C'
0x180037966  jz      short loc_18003797D
0x180037968  cmp     word ptr [r14], 53h ; 'S'
0x18003796d  jnz     loc_180037B43
0x180037973  mov     ecx, 7
0x180037978  jmp     loc_1800379FE
0x18003797d  mov     ecx, 6
0x180037982  jmp     short loc_1800379FE
0x180037984  mov     ecx, 29h ; ')'
0x180037989  jmp     short loc_1800379FE
0x18003798b  cmp     ax, 53h ; 'S'
0x18003798f  jnz     short loc_180037A03
0x180037991  add     r14, 50h ; 'P'
0x180037995  movzx   ecx, word ptr [r14]
0x180037999  sub     ecx, 45h ; 'E'
0x18003799c  jz      short loc_1800379F9
0x18003799e  sub     ecx, 4
0x1800379a1  jz      short loc_1800379F2
0x1800379a3  sub     ecx, 1
0x1800379a6  jz      short loc_1800379EB
0x1800379a8  sub     ecx, 4
0x1800379ab  jz      short loc_1800379E2
0x1800379ad  sub     ecx, edx
0x1800379af  jz      short loc_1800379D9
0x1800379b1  sub     ecx, 3
0x1800379b4  jz      short loc_1800379D2
0x1800379b6  sub     ecx, 1
0x1800379b9  jz      short loc_1800379CB
0x1800379bb  cmp     ecx, 1
0x1800379be  jnz     loc_180037B43
0x1800379c4  mov     ecx, 27h ; '''
0x1800379c9  jmp     short loc_1800379FE
0x1800379cb  mov     ecx, 0Ch
0x1800379d0  jmp     short loc_1800379FE
0x1800379d2  mov     ecx, 0Dh
0x1800379d7  jmp     short loc_1800379FE
0x1800379d9  mov     [rbp+14h], r9d
0x1800379dd  mov     ecx, r9d
0x1800379e0  jmp     short loc_180037A23
0x1800379e2  mov     [rbp+14h], r8d
0x1800379e6  mov     ecx, r8d
0x1800379e9  jmp     short loc_180037A23
0x1800379eb  mov     ecx, 9
0x1800379f0  jmp     short loc_1800379FE
0x1800379f2  mov     ecx, 2Ah ; '*'
0x1800379f7  jmp     short loc_1800379FE
0x1800379f9  mov     ecx, 8
0x1800379fe  mov     [rbp+14h], ecx
0x180037a01  jmp     short loc_180037A23
0x180037a03  cmp     ax, 56h ; 'V'
0x180037a07  jnz     loc_180037B43
0x180037a0d  add     r14, 50h ; 'P'
0x180037a11  cmp     word ptr [r14], 44h ; 'D'
0x180037a16  jnz     loc_180037B43
0x180037a1c  mov     [rbp+14h], r10d
0x180037a20  mov     ecx, r10d
0x180037a23  xor     esi, esi
0x180037a25  add     r14, 4
0x180037a29  cmp     ecx, r8d
0x180037a2c  ja      short loc_180037AA7
0x180037a2e  jz      short loc_180037A91
0x180037a30  sub     ecx, 1
0x180037a33  jz      short loc_180037A91
0x180037a35  sub     ecx, 1
0x180037a38  jz      short loc_180037A91
0x180037a3a  sub     ecx, edx
0x180037a3c  jz      loc_180037ACA
0x180037a42  sub     ecx, edx
0x180037a44  jz      loc_180037ACA
0x180037a4a  sub     ecx, 1
0x180037a4d  jz      loc_180037B0C
0x180037a53  sub     ecx, 1
0x180037a56  jz      short loc_180037ACA
0x180037a58  cmp     ecx, 1
0x180037a5b  jnz     loc_180037B48
0x180037a61  lea     rdx, [rbp+28h]; pclsid
0x180037a65  mov     rcx, r14; lpsz
0x180037a68  call    cs:__imp_CLSIDFromString
0x180037a6f  nop     dword ptr [rax+rax+00h]
0x180037a74  lea     rdx, [rbp+38h]; pclsid
0x180037a78  lea     rcx, [r14+4Ch]; lpsz
0x180037a7c  call    cs:__imp_CLSIDFromString
0x180037a83  nop     dword ptr [rax+rax+00h]
0x180037a88  lea     rcx, [r14+98h]
0x180037a8f  jmp     short loc_180037ACD
0x180037a91  lea     rcx, [rbp+18h]; unsigned __int16 *
0x180037a95  mov     r8, r14; unsigned __int16 *
0x180037a98  mov     rdx, r10; unsigned __int64
0x180037a9b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037aa0  mov     esi, eax
0x180037aa2  jmp     loc_180037B48
0x180037aa7  sub     ecx, r9d
0x180037aaa  jz      short loc_180037B25
0x180037aac  sub     ecx, 1
0x180037aaf  jz      short loc_180037B0C
0x180037ab1  sub     ecx, 4
0x180037ab4  jz      short loc_180037ADF
0x180037ab6  sub     ecx, 17h
0x180037ab9  jz      short loc_180037ACA
0x180037abb  sub     ecx, 1
0x180037abe  jz      short loc_180037ACA
0x180037ac0  sub     ecx, 1
0x180037ac3  jz      short loc_180037ACA
0x180037ac5  cmp     ecx, 1
0x180037ac8  jnz     short loc_180037B48
0x180037aca  mov     rcx, r14; lpsz
0x180037acd  lea     rdx, [rbp+18h]; pclsid
0x180037ad1  call    cs:__imp_CLSIDFromString
0x180037ad8  nop     dword ptr [rax+rax+00h]
0x180037add  jmp     short loc_180037B48
0x180037adf  lea     rdx, [rbp+28h]; pclsid
0x180037ae3  mov     rcx, r14; lpsz
0x180037ae6  call    cs:__imp_CLSIDFromString
0x180037aed  nop     dword ptr [rax+rax+00h]
0x180037af2  lea     rcx, [r14+4Ch]; lpsz
0x180037af6  lea     rdx, [rbp+38h]; pclsid
0x180037afa  call    cs:__imp_CLSIDFromString
0x180037b01  nop     dword ptr [rax+rax+00h]
0x180037b06  movups  xmm0, xmmword ptr [rbp+38h]
0x180037b0a  jmp     short loc_180037B3C
0x180037b0c  lea     rdx, [rbp+28h]; pclsid
0x180037b10  mov     rcx, r14; lpsz
0x180037b13  call    cs:__imp_CLSIDFromString
0x180037b1a  nop     dword ptr [rax+rax+00h]
0x180037b1f  lea     rcx, [r14+4Ch]
0x180037b23  jmp     short loc_180037ACD
0x180037b25  lea     rdx, [rbp+28h]; pclsid
0x180037b29  mov     rcx, r14; lpsz
0x180037b2c  call    cs:__imp_CLSIDFromString
0x180037b33  nop     dword ptr [rax+rax+00h]
0x180037b38  movups  xmm0, xmmword ptr [rbp+28h]
0x180037b3c  movdqu  xmmword ptr [rbp+18h], xmm0
0x180037b41  jmp     short loc_180037B48
0x180037b43  mov     esi, 32h ; '2'
0x180037b48  mov     eax, esi
0x180037b4a  add     rsp, 20h
0x180037b4e  pop     r14
0x180037b50  pop     rdi
0x180037b51  pop     rsi
0x180037b52  pop     rbp
0x180037b53  pop     rbx
0x180037b54  retn
```
