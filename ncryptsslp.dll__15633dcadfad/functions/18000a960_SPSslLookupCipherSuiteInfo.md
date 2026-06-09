# SPSslLookupCipherSuiteInfo

- ea: `0x18000a960`
- end: `0x18000adf2`
- name: `SPSslLookupCipherSuiteInfo`
- size: `1170`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a960`
- `0x18000b594`
- `0x18000b654`

## string_xrefs

- `0x18000a9b9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000ab9a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000abf2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000adb1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000add0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslLookupCipherSuiteInfo(_DWORD *a1, __int64 a2, int a3, __int64 a4, _DWORD *a5, int a6)
{
  int v6; // r9d
  int v7; // r10d
  unsigned int v8; // ebx
  __int64 i; // rcx
  int v10; // r11d
  __int64 j; // rax
  __int64 v12; // r11
  _WORD *v13; // r10
  __int64 v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // r9
  __int64 v17; // r8
  _WORD *v18; // rcx
  _WORD *v19; // rcx
  _WORD *v20; // r9
  __int64 v21; // rax
  _WORD *v22; // rcx
  _WORD *v23; // r9
  __int64 v24; // rax
  _WORD *v25; // rcx
  _WORD *v26; // rcx
  _QWORD *v27; // rcx
  _WORD *v29; // r10
  __int64 v30; // rcx
  __int64 v31; // r9
  _WORD *v32; // rcx
  _WORD *v33; // rcx
  _WORD *v34; // rcx
  char v35; // [rsp+30h] [rbp-18h]

  v6 = a3;
  v7 = a2;
  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
  {
    v8 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        227);
    return v8;
  }
  if ( !a5 )
  {
    v8 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        234);
    return v8;
  }
  if ( a6 )
  {
    v8 = -2146893815;
    DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 4081);
    return v8;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 7 )
      goto LABEL_46;
    a2 = 8 * i;
    if ( (unsigned __int16)ProtocolVersionList[4 * i] == v7 )
      break;
  }
  v10 = *(int *)((char *)&dword_180031A24 + a2);
  if ( !v10 )
  {
LABEL_46:
    v8 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        251);
    return v8;
  }
  a3 = g_dwCipherSuiteInfoTotalCount;
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    if ( (unsigned int)j >= g_dwCipherSuiteInfoTotalCount )
      goto LABEL_46;
    a2 = g_pCipherSuiteInfo[j];
    if ( a2 )
    {
      if ( *(_DWORD *)(a2 + 4) == v6 && (v10 & *(_DWORD *)a2) != 0 )
        break;
    }
  }
  *a5 = v7;
  v12 = 2147483646;
  v13 = a5 + 3;
  a5[1] = *(_DWORD *)(a2 + 4);
  v14 = 64;
  v15 = 2147483646;
  a5[2] = *(_DWORD *)(a2 + 4);
  v16 = 64;
  v17 = *(_QWORD *)(a2 + 8);
  do
  {
    if ( !v15 )
      break;
    if ( !*(_WORD *)v17 )
      break;
    *v13 = *(_WORD *)v17;
    v17 += 2;
    ++v13;
    --v15;
    --v16;
  }
  while ( v16 );
  v18 = v13 - 1;
  v8 = -2147024774;
  if ( v16 )
  {
    v18 = v13;
    v8 = 0;
  }
  *v18 = 0;
  if ( !v16 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v35 = 9;
      goto LABEL_44;
    }
    return v8;
  }
  v19 = *(_WORD **)(a2 + 16);
  v20 = a5 + 35;
  v21 = 2147483646;
  v17 = 64;
  do
  {
    if ( !v21 )
      break;
    if ( !*v19 )
      break;
    *v20++ = *v19++;
    --v21;
    --v17;
  }
  while ( v17 );
  v22 = v20 - 1;
  v8 = -2147024774;
  if ( v17 )
  {
    v22 = v20;
    v8 = 0;
  }
  *v22 = 0;
  if ( !v17 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v35 = 18;
      goto LABEL_44;
    }
    return v8;
  }
  v23 = a5 + 69;
  a5[67] = *(_DWORD *)(a2 + 28);
  v17 = 64;
  a5[68] = *(_DWORD *)(a2 + 36);
  v24 = 2147483646;
  v25 = *(_WORD **)(a2 + 56);
  do
  {
    if ( !v24 )
      break;
    if ( !*v25 )
      break;
    *v23++ = *v25++;
    --v24;
    --v17;
  }
  while ( v17 );
  v26 = v23 - 1;
  v8 = -2147024774;
  if ( v17 )
  {
    v26 = v23;
    v8 = 0;
  }
  *v26 = 0;
  if ( !v17 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v35 = 30;
LABEL_44:
      WPP_SF_sDsd(
        v27[2],
        a2,
        v17,
        (unsigned int)"Status",
        v8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v35);
      return v8;
    }
    return v8;
  }
  v29 = a5 + 102;
  v30 = 2147483646;
  a5[101] = 8 * *(_DWORD *)(a2 + 68);
  v31 = 64;
  v17 = *(_QWORD *)(a2 + 80);
  do
  {
    if ( !v30 )
      break;
    if ( !*(_WORD *)v17 )
      break;
    *v29 = *(_WORD *)v17;
    v17 += 2;
    ++v29;
    --v30;
    --v31;
  }
  while ( v31 );
  v32 = v29 - 1;
  v8 = -2147024774;
  if ( v31 )
  {
    v32 = v29;
    v8 = 0;
  }
  *v32 = 0;
  if ( !v31 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v35 = 41;
      goto LABEL_44;
    }
    return v8;
  }
  a5[134] = *(_DWORD *)(a2 + 92);
  a5[135] = *(_DWORD *)(a2 + 96);
  v33 = *(_WORD **)(a2 + 120);
  a2 = (__int64)(a5 + 136);
  do
  {
    if ( !v12 )
      break;
    if ( !*v33 )
      break;
    *(_WORD *)a2 = *v33++;
    a2 += 2;
    --v12;
    --v14;
  }
  while ( v14 );
  v34 = (_WORD *)(a2 - 2);
  v8 = -2147024774;
  if ( v14 )
  {
    v34 = (_WORD *)a2;
    v8 = 0;
  }
  *v34 = 0;
  if ( !v14 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v35 = 53;
      goto LABEL_44;
    }
    return v8;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a960  mov     [rsp+arg_0], rbx
0x18000a965  mov     [rsp+arg_8], rsi
0x18000a96a  push    rdi
0x18000a96b  sub     rsp, 40h
0x18000a96f  mov     r9d, r8d
0x18000a972  mov     r10d, edx
0x18000a975  test    rcx, rcx
0x18000a978  jz      short loc_18000A98B
0x18000a97a  cmp     dword ptr [rcx], 310h
0x18000a980  jb      short loc_18000A98B
0x18000a982  cmp     dword ptr [rcx+4], 73736C31h
0x18000a989  jz      short loc_18000A9D2
0x18000a98b  mov     ebx, 80090026h
0x18000a990  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a997  lea     rax, WPP_GLOBAL_Control
0x18000a99e  cmp     rcx, rax
0x18000a9a1  jz      loc_18000ABBA
0x18000a9a7  test    byte ptr [rcx+1Ch], 1
0x18000a9ab  jz      loc_18000ABBA
0x18000a9b1  mov     dword ptr [rsp+48h+var_18], 0FE3h
0x18000a9b9  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a9c0  mov     [rsp+48h+var_20], rax
0x18000a9c5  mov     [rsp+48h+var_28], 80090026h
0x18000a9cd  jmp     loc_18000ABAA
0x18000a9d2  mov     rsi, [rsp+48h+arg_20]
0x18000a9d7  test    rsi, rsi
0x18000a9da  jz      loc_18000AD83
0x18000a9e0  cmp     [rsp+48h+arg_28], 0
0x18000a9e5  jnz     loc_18000ADCA
0x18000a9eb  xor     ecx, ecx
0x18000a9ed  lea     rbx, __ImageBase
0x18000a9f4  cmp     ecx, 7
0x18000a9f7  jnb     loc_18000ABCC
0x18000a9fd  lea     rdx, ds:0[rcx*8]
0x18000aa05  movzx   eax, word ptr [rdx+rbx+31A20h]
0x18000aa0d  cmp     eax, r10d
0x18000aa10  jz      short loc_18000AA16
0x18000aa12  inc     ecx
0x18000aa14  jmp     short loc_18000A9F4
0x18000aa16  mov     r11d, [rdx+rbx+31A24h]
0x18000aa1e  test    r11d, r11d
0x18000aa21  jz      loc_18000ABCC
0x18000aa27  mov     r8d, cs:g_dwCipherSuiteInfoTotalCount
0x18000aa2e  xor     eax, eax
0x18000aa30  cmp     eax, r8d
0x18000aa33  jnb     loc_18000ABCC
0x18000aa39  mov     rdx, rva g_pCipherSuiteInfo[rbx+rax*8]
0x18000aa41  test    rdx, rdx
0x18000aa44  jz      short loc_18000AA4C
0x18000aa46  cmp     [rdx+4], r9d
0x18000aa4a  jz      short loc_18000AA50
0x18000aa4c  inc     eax
0x18000aa4e  jmp     short loc_18000AA30
0x18000aa50  test    [rdx], r11d
0x18000aa53  jz      short loc_18000AA4C
0x18000aa55  mov     [rsi], r10d
0x18000aa58  mov     r11d, 7FFFFFFEh
0x18000aa5e  mov     eax, [rdx+4]
0x18000aa61  lea     r10, [rsi+0Ch]
0x18000aa65  mov     [rsi+4], eax
0x18000aa68  mov     edi, 40h ; '@'
0x18000aa6d  mov     eax, [rdx+4]
0x18000aa70  mov     ecx, r11d
0x18000aa73  mov     [rsi+8], eax
0x18000aa76  mov     r9d, edi
0x18000aa79  mov     r8, [rdx+8]
0x18000aa7d  nop     dword ptr [rax]
0x18000aa80  test    rcx, rcx
0x18000aa83  jz      short loc_18000AAA3
0x18000aa85  movzx   eax, word ptr [r8]
0x18000aa89  test    ax, ax
0x18000aa8c  jz      short loc_18000AAA3
0x18000aa8e  mov     [r10], ax
0x18000aa92  add     r8, 2
0x18000aa96  add     r10, 2
0x18000aa9a  dec     rcx
0x18000aa9d  sub     r9, 1
0x18000aaa1  jnz     short loc_18000AA80
0x18000aaa3  xor     eax, eax
0x18000aaa5  lea     rcx, [r10-2]
0x18000aaa9  test    r9, r9
0x18000aaac  mov     ebx, 8007007Ah
0x18000aab1  cmovnz  rcx, r10
0x18000aab5  cmovnz  ebx, eax
0x18000aab8  mov     [rcx], ax
0x18000aabb  jz      loc_18000AC08
0x18000aac1  mov     rcx, [rdx+10h]
0x18000aac5  lea     r9, [rsi+8Ch]
0x18000aacc  mov     rax, r11
0x18000aacf  mov     r8, rdi
0x18000aad2  test    rax, rax
0x18000aad5  jz      short loc_18000AAF6
0x18000aad7  movzx   r10d, word ptr [rcx]
0x18000aadb  test    r10w, r10w
0x18000aadf  jz      short loc_18000AAF6
0x18000aae1  mov     [r9], r10w
0x18000aae5  add     rcx, 2
0x18000aae9  add     r9, 2
0x18000aaed  dec     rax
0x18000aaf0  sub     r8, 1
0x18000aaf4  jnz     short loc_18000AAD2
0x18000aaf6  xor     eax, eax
0x18000aaf8  lea     rcx, [r9-2]
0x18000aafc  test    r8, r8
0x18000aaff  mov     ebx, 8007007Ah
0x18000ab04  cmovnz  rcx, r9
0x18000ab08  cmovnz  ebx, eax
0x18000ab0b  mov     [rcx], ax
0x18000ab0e  jz      loc_18000AD55
0x18000ab14  mov     eax, [rdx+1Ch]
0x18000ab17  lea     r9, [rsi+114h]
0x18000ab1e  mov     [rsi+10Ch], eax
0x18000ab24  mov     r8, rdi
0x18000ab27  mov     eax, [rdx+24h]
0x18000ab2a  mov     [rsi+110h], eax
0x18000ab30  mov     rax, r11
0x18000ab33  mov     rcx, [rdx+38h]
0x18000ab37  test    rax, rax
0x18000ab3a  jz      short loc_18000AB5B
0x18000ab3c  movzx   r10d, word ptr [rcx]
0x18000ab40  test    r10w, r10w
0x18000ab44  jz      short loc_18000AB5B
0x18000ab46  mov     [r9], r10w
0x18000ab4a  add     rcx, 2
0x18000ab4e  add     r9, 2
0x18000ab52  dec     rax
0x18000ab55  sub     r8, 1
0x18000ab59  jnz     short loc_18000AB37
0x18000ab5b  xor     eax, eax
0x18000ab5d  lea     rcx, [r9-2]
0x18000ab61  test    r8, r8
0x18000ab64  mov     ebx, 8007007Ah
0x18000ab69  cmovnz  rcx, r9
0x18000ab6d  cmovnz  ebx, eax
0x18000ab70  mov     [rcx], ax
0x18000ab73  jnz     loc_18000AC2E
0x18000ab79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab80  lea     rax, WPP_GLOBAL_Control
0x18000ab87  cmp     rcx, rax
0x18000ab8a  jz      short loc_18000ABBA
0x18000ab8c  test    byte ptr [rcx+1Ch], 1
0x18000ab90  jz      short loc_18000ABBA
0x18000ab92  mov     dword ptr [rsp+48h+var_18], 101Eh
0x18000ab9a  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000aba1  mov     [rsp+48h+var_20], rax
0x18000aba6  mov     [rsp+48h+var_28], ebx
0x18000abaa  mov     rcx, [rcx+10h]
0x18000abae  lea     r9, aStatus; "Status"
0x18000abb5  call    WPP_SF_sDsd
0x18000abba  mov     eax, ebx
0x18000abbc  mov     rbx, [rsp+48h+arg_0]
0x18000abc1  mov     rsi, [rsp+48h+arg_8]
0x18000abc6  add     rsp, 40h
0x18000abca  pop     rdi
0x18000abcb  retn
0x18000abcc  mov     ebx, 80090027h
0x18000abd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abd8  lea     rax, WPP_GLOBAL_Control
0x18000abdf  cmp     rcx, rax
0x18000abe2  jz      short loc_18000ABBA
0x18000abe4  test    byte ptr [rcx+1Ch], 1
0x18000abe8  jz      short loc_18000ABBA
0x18000abea  mov     dword ptr [rsp+48h+var_18], 0FFBh
0x18000abf2  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000abf9  mov     [rsp+48h+var_20], rax
0x18000abfe  mov     [rsp+48h+var_28], 80090027h
0x18000ac06  jmp     short loc_18000ABAA
0x18000ac08  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac0f  lea     rax, WPP_GLOBAL_Control
0x18000ac16  cmp     rcx, rax
0x18000ac19  jz      short loc_18000ABBA
0x18000ac1b  test    byte ptr [rcx+1Ch], 1
0x18000ac1f  jz      short loc_18000ABBA
0x18000ac21  mov     dword ptr [rsp+48h+var_18], 1009h
0x18000ac29  jmp     loc_18000AB9A
0x18000ac2e  mov     eax, [rdx+44h]
0x18000ac31  lea     r10, [rsi+198h]
0x18000ac38  shl     eax, 3
0x18000ac3b  mov     rcx, r11
0x18000ac3e  mov     [rsi+194h], eax
0x18000ac44  mov     r9, rdi
0x18000ac47  mov     r8, [rdx+50h]
0x18000ac4b  nop     dword ptr [rax+rax+00h]
0x18000ac50  test    rcx, rcx
0x18000ac53  jz      short loc_18000AC73
0x18000ac55  movzx   eax, word ptr [r8]
0x18000ac59  test    ax, ax
0x18000ac5c  jz      short loc_18000AC73
0x18000ac5e  mov     [r10], ax
0x18000ac62  add     r8, 2
0x18000ac66  add     r10, 2
0x18000ac6a  dec     rcx
0x18000ac6d  sub     r9, 1
0x18000ac71  jnz     short loc_18000AC50
0x18000ac73  xor     eax, eax
0x18000ac75  lea     rcx, [r10-2]
0x18000ac79  test    r9, r9
0x18000ac7c  mov     ebx, 8007007Ah
0x18000ac81  cmovnz  rcx, r10
0x18000ac85  cmovnz  ebx, eax
0x18000ac88  mov     [rcx], ax
0x18000ac8b  jnz     short loc_18000ACBB
0x18000ac8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac94  lea     rax, WPP_GLOBAL_Control
0x18000ac9b  cmp     rcx, rax
0x18000ac9e  jz      loc_18000ABBA
0x18000aca4  test    byte ptr [rcx+1Ch], 1
0x18000aca8  jz      loc_18000ABBA
0x18000acae  mov     dword ptr [rsp+48h+var_18], 1029h
0x18000acb6  jmp     loc_18000AB9A
0x18000acbb  mov     eax, [rdx+5Ch]
0x18000acbe  mov     [rsi+218h], eax
0x18000acc4  mov     eax, [rdx+60h]
0x18000acc7  mov     [rsi+21Ch], eax
0x18000accd  mov     rcx, [rdx+78h]
0x18000acd1  lea     rdx, [rsi+220h]
0x18000acd8  test    r11, r11
0x18000acdb  jz      short loc_18000ACF9
0x18000acdd  movzx   eax, word ptr [rcx]
0x18000ace0  test    ax, ax
0x18000ace3  jz      short loc_18000ACF9
0x18000ace5  mov     [rdx], ax
0x18000ace8  add     rcx, 2
0x18000acec  add     rdx, 2
0x18000acf0  dec     r11
0x18000acf3  sub     rdi, 1
0x18000acf7  jnz     short loc_18000ACD8
0x18000acf9  xor     eax, eax
0x18000acfb  lea     rcx, [rdx-2]
0x18000acff  test    rdi, rdi
0x18000ad02  mov     ebx, 8007007Ah
0x18000ad07  cmovnz  rcx, rdx
0x18000ad0b  cmovnz  ebx, eax
0x18000ad0e  mov     [rcx], ax
0x18000ad11  jz      short loc_18000AD27
0x18000ad13  mov     rsi, [rsp+48h+arg_8]
0x18000ad18  xor     ebx, ebx
0x18000ad1a  mov     eax, ebx
0x18000ad1c  mov     rbx, [rsp+48h+arg_0]
0x18000ad21  add     rsp, 40h
0x18000ad25  pop     rdi
0x18000ad26  retn
0x18000ad27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad2e  lea     rax, WPP_GLOBAL_Control
0x18000ad35  cmp     rcx, rax
0x18000ad38  jz      loc_18000ABBA
0x18000ad3e  test    byte ptr [rcx+1Ch], 1
0x18000ad42  jz      loc_18000ABBA
0x18000ad48  mov     dword ptr [rsp+48h+var_18], 1035h
0x18000ad50  jmp     loc_18000AB9A
0x18000ad55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad5c  lea     rax, WPP_GLOBAL_Control
0x18000ad63  cmp     rcx, rax
0x18000ad66  jz      loc_18000ABBA
0x18000ad6c  test    byte ptr [rcx+1Ch], 1
0x18000ad70  jz      loc_18000ABBA
0x18000ad76  mov     dword ptr [rsp+48h+var_18], 1012h
0x18000ad7e  jmp     loc_18000AB9A
0x18000ad83  mov     ebx, 80090027h
0x18000ad88  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad8f  lea     rax, WPP_GLOBAL_Control
0x18000ad96  cmp     rcx, rax
0x18000ad99  jz      loc_18000ABBA
0x18000ad9f  test    byte ptr [rcx+1Ch], 1
0x18000ada3  jz      loc_18000ABBA
0x18000ada9  mov     dword ptr [rsp+48h+var_18], 0FEAh
0x18000adb1  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000adb8  mov     [rsp+48h+var_20], rax
0x18000adbd  mov     [rsp+48h+var_28], 80090027h
0x18000adc5  jmp     loc_18000ABAA
0x18000adca  mov     r9d, 0FF1h
0x18000add0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000add7  lea     rdx, aStatus; "Status"
0x18000adde  mov     ecx, 80090009h
0x18000ade3  mov     ebx, 80090009h
0x18000ade8  call    DebugTraceError
0x18000aded  jmp     loc_18000ABBA
```
