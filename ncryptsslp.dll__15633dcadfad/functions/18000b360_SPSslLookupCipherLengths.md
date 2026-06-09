# SPSslLookupCipherLengths

- ea: `0x18000b360`
- end: `0x18000b58e`
- name: `SPSslLookupCipherLengths`
- size: `558`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, int, __int64, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b360`
- `0x18000b594`
- `0x18000b654`

## string_xrefs

- `0x18000b3a2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000b3dd`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000b51e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslLookupCipherLengths(
        _DWORD *a1,
        _DWORD *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  int v7; // r10d
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 i; // rcx
  int v13; // r11d
  __int64 j; // rax
  int v15; // eax
  unsigned int v16; // eax

  v7 = (int)a2;
  if ( (unsigned int)a2 < 0x302 )
  {
    v8 = -2146893783;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        87);
    return v8;
  }
  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
  {
    v8 = -2146893786;
    v9 = 4196;
    v10 = 2148073510LL;
LABEL_6:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v9);
    return v8;
  }
  if ( !a5 || a6 < 0x14 )
  {
    v8 = -2146893785;
    v9 = 4204;
    v10 = 2148073511LL;
    goto LABEL_6;
  }
  if ( a7 )
  {
    v8 = -2146893815;
    v9 = 4211;
    v10 = 2148073481LL;
    goto LABEL_6;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 7 )
      goto LABEL_7;
    a2 = (_DWORD *)(8 * i);
    if ( (unsigned __int16)ProtocolVersionList[4 * i] == v7 )
      break;
  }
  v13 = *(int *)((char *)&dword_180031A24 + (_QWORD)a2);
  if ( !v13 )
  {
LABEL_7:
    v8 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        124);
    return v8;
  }
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    if ( (unsigned int)j >= g_dwCipherSuiteInfoTotalCount )
      goto LABEL_7;
    a2 = (_DWORD *)g_pCipherSuiteInfo[j];
    if ( a2 )
    {
      if ( a2[1] == a3 && (v13 & *a2) != 0 )
        break;
    }
  }
  *(_QWORD *)(a5 + 4) = 0;
  *(_QWORD *)(a5 + 12) = 0;
  *(_DWORD *)a5 = 20;
  if ( (unsigned int)(a2[10] - 5) <= 1 )
  {
    v15 = 0;
    *(_DWORD *)(a5 + 8) = 16;
    if ( v7 != 772 )
      v15 = 8;
    *(_DWORD *)(a5 + 4) = v15;
    return 0;
  }
  *(_DWORD *)(a5 + 8) = a2[17];
  v16 = a2[9];
  if ( v16 <= 1 )
    return 0;
  *(_DWORD *)(a5 + 4) = v16;
  *(_DWORD *)(a5 + 12) = a2[9];
  *(_DWORD *)(a5 + 16) = 1;
  return 0;
}

```

## disassembly

```asm
0x18000b360  mov     [rsp+arg_0], rbx
0x18000b365  push    rdi
0x18000b366  sub     rsp, 40h
0x18000b36a  mov     r9d, r8d
0x18000b36d  mov     r10d, edx
0x18000b370  cmp     edx, 302h
0x18000b376  jb      loc_18000B4F0
0x18000b37c  test    rcx, rcx
0x18000b37f  jz      short loc_18000B392
0x18000b381  cmp     dword ptr [rcx], 310h
0x18000b387  jb      short loc_18000B392
0x18000b389  cmp     dword ptr [rcx+4], 73736C31h
0x18000b390  jz      short loc_18000B40E
0x18000b392  mov     ebx, 80090026h
0x18000b397  mov     r9d, 1064h
0x18000b39d  mov     ecx, 80090026h
0x18000b3a2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b3a9  lea     rdx, aStatus; "Status"
0x18000b3b0  call    DebugTraceError
0x18000b3b5  jmp     short loc_18000B401
0x18000b3b7  mov     ebx, 80090027h
0x18000b3bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3c3  lea     rax, WPP_GLOBAL_Control
0x18000b3ca  cmp     rcx, rax
0x18000b3cd  jz      short loc_18000B401
0x18000b3cf  test    byte ptr [rcx+1Ch], 1
0x18000b3d3  jz      short loc_18000B401
0x18000b3d5  mov     [rsp+48h+var_18], 107Ch
0x18000b3dd  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b3e4  mov     [rsp+48h+var_20], r8
0x18000b3e9  mov     [rsp+48h+var_28], 80090027h
0x18000b3f1  mov     rcx, [rcx+10h]
0x18000b3f5  lea     r9, aStatus; "Status"
0x18000b3fc  call    WPP_SF_sDsd
0x18000b401  mov     eax, ebx
0x18000b403  mov     rbx, [rsp+48h+arg_0]
0x18000b408  add     rsp, 40h
0x18000b40c  pop     rdi
0x18000b40d  retn
0x18000b40e  mov     rbx, [rsp+48h+arg_20]
0x18000b413  test    rbx, rbx
0x18000b416  jz      loc_18000B579
0x18000b41c  cmp     [rsp+48h+arg_28], 14h
0x18000b421  jb      loc_18000B579
0x18000b427  cmp     [rsp+48h+arg_30], 0
0x18000b42f  jnz     loc_18000B564
0x18000b435  xor     ecx, ecx
0x18000b437  lea     rdi, __ImageBase
0x18000b43e  cmp     ecx, 7
0x18000b441  jnb     loc_18000B3B7
0x18000b447  lea     rdx, ds:0[rcx*8]
0x18000b44f  movzx   eax, word ptr [rdx+rdi+31A20h]
0x18000b457  cmp     eax, r10d
0x18000b45a  jz      short loc_18000B460
0x18000b45c  inc     ecx
0x18000b45e  jmp     short loc_18000B43E
0x18000b460  mov     r11d, [rdx+rdi+31A24h]
0x18000b468  test    r11d, r11d
0x18000b46b  jz      loc_18000B3B7
0x18000b471  mov     r8d, cs:g_dwCipherSuiteInfoTotalCount
0x18000b478  xor     eax, eax
0x18000b47a  nop     word ptr [rax+rax+00h]
0x18000b480  cmp     eax, r8d
0x18000b483  jnb     loc_18000B3B7
0x18000b489  mov     rdx, rva g_pCipherSuiteInfo[rdi+rax*8]
0x18000b491  test    rdx, rdx
0x18000b494  jz      short loc_18000B49C
0x18000b496  cmp     [rdx+4], r9d
0x18000b49a  jz      short loc_18000B4A0
0x18000b49c  inc     eax
0x18000b49e  jmp     short loc_18000B480
0x18000b4a0  test    [rdx], r11d
0x18000b4a3  jz      short loc_18000B49C
0x18000b4a5  mov     qword ptr [rbx+4], 0
0x18000b4ad  mov     qword ptr [rbx+0Ch], 0
0x18000b4b5  mov     dword ptr [rbx], 14h
0x18000b4bb  mov     eax, [rdx+28h]
0x18000b4be  sub     eax, 5
0x18000b4c1  cmp     eax, 1
0x18000b4c4  ja      short loc_18000B537
0x18000b4c6  xor     eax, eax
0x18000b4c8  mov     dword ptr [rbx+8], 10h
0x18000b4cf  cmp     r10d, 304h
0x18000b4d6  mov     ecx, 8
0x18000b4db  cmovnz  eax, ecx
0x18000b4de  mov     [rbx+4], eax
0x18000b4e1  xor     ebx, ebx
0x18000b4e3  mov     eax, ebx
0x18000b4e5  mov     rbx, [rsp+48h+arg_0]
0x18000b4ea  add     rsp, 40h
0x18000b4ee  pop     rdi
0x18000b4ef  retn
0x18000b4f0  mov     ebx, 80090029h
0x18000b4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4fc  lea     rax, WPP_GLOBAL_Control
0x18000b503  cmp     rcx, rax
0x18000b506  jz      loc_18000B401
0x18000b50c  test    byte ptr [rcx+1Ch], 1
0x18000b510  jz      loc_18000B401
0x18000b516  mov     [rsp+48h+var_18], 1057h
0x18000b51e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b525  mov     [rsp+48h+var_20], r8
0x18000b52a  mov     [rsp+48h+var_28], 80090029h
0x18000b532  jmp     loc_18000B3F1
0x18000b537  mov     eax, [rdx+44h]
0x18000b53a  mov     [rbx+8], eax
0x18000b53d  mov     eax, [rdx+24h]
0x18000b540  cmp     eax, 1
0x18000b543  jbe     short loc_18000B4E1
0x18000b545  mov     [rbx+4], eax
0x18000b548  mov     eax, [rdx+24h]
0x18000b54b  mov     [rbx+0Ch], eax
0x18000b54e  mov     dword ptr [rbx+10h], 1
0x18000b555  xor     ebx, ebx
0x18000b557  mov     eax, ebx
0x18000b559  mov     rbx, [rsp+48h+arg_0]
0x18000b55e  add     rsp, 40h
0x18000b562  pop     rdi
0x18000b563  retn
0x18000b564  mov     ebx, 80090009h
0x18000b569  mov     r9d, 1073h
0x18000b56f  mov     ecx, 80090009h
0x18000b574  jmp     loc_18000B3A2
0x18000b579  mov     ebx, 80090027h
0x18000b57e  mov     r9d, 106Ch
0x18000b584  mov     ecx, 80090027h
0x18000b589  jmp     loc_18000B3A2
```
