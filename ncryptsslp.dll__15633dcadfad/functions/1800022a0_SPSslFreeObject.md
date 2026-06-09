# SPSslFreeObject

- ea: `0x1800022a0`
- end: `0x1800024fc`
- name: `SPSslFreeObject`
- size: `604`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001670`
- `0x1800022a0`
- `0x180003ef0`
- `0x18000b594`
- `0x18000b654`
- `0x180013e6c`
- `0x180022164`
- `0x180023234`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18000233e`
- `bcrypt!BCryptDestroyKey` at `0x1800024f1`
- `bcrypt!BCryptDestroyKey` at `0x18000233e`
- `bcrypt!BCryptDestroyKey` at `0x1800024f1`
- `bcrypt!BCryptDestroyHash` at `0x180002424`
- `bcrypt!BCryptDestroyHash` at `0x18000242f`
- `bcrypt!BCryptDestroyHash` at `0x180002424`
- `bcrypt!BCryptDestroyHash` at `0x18000242f`
- `ncrypt!NCryptFreeObject` at `0x18000241c`
- `ncrypt!NCryptFreeObject` at `0x18000241c`

## string_xrefs

- `0x1800023a0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000248e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800024b6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslFreeObject(unsigned int *a1)
{
  unsigned int *v1; // rbx
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  void *v6; // rcx
  __int64 v7; // rax
  _BYTE *v8; // rcx
  void *v10; // rcx
  void *v11; // rcx
  __int64 v12; // rax
  _BYTE *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rax
  int v17; // edx
  int v18; // ebx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  __int64 v21; // rax
  _BYTE *v22; // rcx
  NCRYPT_HANDLE v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // r9
  void *v29; // rcx

  v1 = a1;
  if ( !a1 )
    return 2148073511LL;
  v2 = a1[1];
  if ( v2 <= 0x73736C37 )
  {
    if ( v2 == 1936944183 )
      goto LABEL_22;
    v3 = v2 - 1936944177;
    if ( !v3 )
    {
      FreeProviderObject(a1);
      return 0;
    }
    v4 = v3 - 1;
    if ( !v4 )
    {
      v10 = (void *)*((_QWORD *)a1 + 2);
      if ( v10 )
        BCryptDestroyHash(v10);
      v11 = (void *)*((_QWORD *)v1 + 4);
      if ( v11 )
        BCryptDestroyHash(v11);
      v12 = *v1;
      v13 = v1;
      if ( *v1 )
      {
        do
        {
          *v13++ = 0;
          --v12;
        }
        while ( v12 );
      }
      goto LABEL_11;
    }
    v5 = v4 - 1;
    if ( !v5 )
    {
      v6 = (void *)*((_QWORD *)a1 + 4);
      if ( v6 )
        BCryptDestroyKey(v6);
      v7 = *v1;
      v8 = v1;
      if ( *v1 )
      {
        do
        {
          *v8++ = 0;
          --v7;
        }
        while ( v7 );
      }
LABEL_11:
      MSCryptFree(v1);
      return 0;
    }
    v14 = v5 - 1;
    if ( !v14 )
    {
      v23 = *((_QWORD *)a1 + 3);
      if ( v23 )
        NCryptFreeObject(v23);
      v19 = *v1;
      v20 = v1;
      if ( *v1 )
      {
        do
        {
          *v20++ = 0;
          --v19;
        }
        while ( v19 );
      }
      goto LABEL_11;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
LABEL_22:
      v16 = *a1;
      if ( *a1 )
      {
        do
        {
          *(_BYTE *)a1 = 0;
          a1 = (unsigned int *)((char *)a1 + 1);
          --v16;
        }
        while ( v16 );
      }
      goto LABEL_11;
    }
    if ( v15 == 1 )
    {
      v18 = SslpFreeEphemeralKey(a1);
      if ( v18 >= 0 )
        return 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v17,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          (unsigned int)"Status",
          v18,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          237);
      return (unsigned int)v18;
    }
    goto LABEL_48;
  }
  v24 = v2 - 1936944184;
  if ( !v24 )
    goto LABEL_22;
  v25 = v24 - 1;
  if ( !v25 )
  {
    v29 = (void *)*((_QWORD *)a1 + 2);
    if ( v29 )
      BCryptDestroyKey(v29);
    v21 = *v1;
    v22 = v1;
    if ( *v1 )
    {
      do
      {
        *v22++ = 0;
        --v21;
      }
      while ( v21 );
    }
    goto LABEL_11;
  }
  v26 = v25 - 1;
  if ( !v26 )
    goto LABEL_22;
  v27 = v26 - 1;
  if ( !v27 )
  {
    v18 = SslpFreeHybridKey(a1);
    if ( v18 >= 0 )
      return 0;
    v28 = 2565;
LABEL_49:
    DebugTraceError((unsigned int)v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v28);
    return (unsigned int)v18;
  }
  if ( v27 == 1 )
  {
    v18 = SslpFreeKemKey(a1);
    if ( v18 >= 0 )
      return 0;
    v28 = 2553;
    goto LABEL_49;
  }
LABEL_48:
  DebugTraceError(3221225474LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 2604);
  return 3221225474LL;
}

```

## disassembly

```asm
0x1800022a0  push    rbx
0x1800022a2  sub     rsp, 40h
0x1800022a6  mov     rbx, rcx
0x1800022a9  test    rcx, rcx
0x1800022ac  jz      loc_180002409
0x1800022b2  mov     eax, [rcx+4]
0x1800022b5  mov     ecx, 73736C37h
0x1800022ba  cmp     eax, ecx
0x1800022bc  ja      loc_180002447
0x1800022c2  jz      loc_180002354
0x1800022c8  sub     eax, 73736C31h
0x1800022cd  jz      loc_18000243A
0x1800022d3  sub     eax, 1
0x1800022d6  jz      short loc_18000230C
0x1800022d8  sub     eax, 1
0x1800022db  jnz     short loc_180002346
0x1800022dd  mov     rcx, [rbx+20h]; hKey
0x1800022e1  test    rcx, rcx
0x1800022e4  jnz     short loc_18000233E
0x1800022e6  mov     eax, [rbx]
0x1800022e8  mov     rcx, rbx
0x1800022eb  test    rax, rax
0x1800022ee  jz      short loc_1800022FC
0x1800022f0  mov     byte ptr [rcx], 0
0x1800022f3  inc     rcx
0x1800022f6  sub     rax, 1
0x1800022fa  jnz     short loc_1800022F0
0x1800022fc  mov     rcx, rbx
0x1800022ff  call    MSCryptFree
0x180002304  xor     eax, eax
0x180002306  add     rsp, 40h
0x18000230a  pop     rbx
0x18000230b  retn
0x18000230c  mov     rcx, [rbx+10h]; hHash
0x180002310  test    rcx, rcx
0x180002313  jnz     loc_180002424
0x180002319  mov     rcx, [rbx+20h]; hHash
0x18000231d  test    rcx, rcx
0x180002320  jnz     loc_18000242F
0x180002326  mov     eax, [rbx]
0x180002328  mov     rcx, rbx
0x18000232b  test    rax, rax
0x18000232e  jz      short loc_1800022FC
0x180002330  mov     byte ptr [rcx], 0
0x180002333  inc     rcx
0x180002336  sub     rax, 1
0x18000233a  jnz     short loc_180002330
0x18000233c  jmp     short loc_1800022FC
0x18000233e  call    cs:__imp_BCryptDestroyKey
0x180002344  jmp     short loc_1800022E6
0x180002346  sub     eax, 1
0x180002349  jz      loc_180002413
0x18000234f  sub     eax, 1
0x180002352  jnz     short loc_18000236C
0x180002354  mov     eax, [rbx]
0x180002356  mov     rcx, rbx
0x180002359  test    rax, rax
0x18000235c  jz      short loc_1800022FC
0x18000235e  mov     byte ptr [rcx], 0
0x180002361  inc     rcx
0x180002364  sub     rax, 1
0x180002368  jnz     short loc_18000235E
0x18000236a  jmp     short loc_1800022FC
0x18000236c  cmp     eax, 1
0x18000236f  jnz     loc_180002488
0x180002375  mov     rcx, rbx
0x180002378  call    SslpFreeEphemeralKey
0x18000237d  mov     ebx, eax
0x18000237f  test    eax, eax
0x180002381  jns     short loc_180002304
0x180002383  mov     rcx, cs:WPP_GLOBAL_Control
0x18000238a  lea     rax, WPP_GLOBAL_Control
0x180002391  cmp     rcx, rax
0x180002394  jz      short loc_1800023C4
0x180002396  test    byte ptr [rcx+1Ch], 1
0x18000239a  jz      short loc_1800023C4
0x18000239c  mov     rcx, [rcx+10h]
0x1800023a0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800023a7  mov     [rsp+48h+var_18], 9EDh
0x1800023af  lea     r9, aStatus; "Status"
0x1800023b6  mov     [rsp+48h+var_20], r8
0x1800023bb  mov     [rsp+48h+var_28], ebx
0x1800023bf  call    WPP_SF_sDsd
0x1800023c4  mov     eax, ebx
0x1800023c6  jmp     loc_180002306
0x1800023cb  mov     eax, [rbx]
0x1800023cd  mov     rcx, rbx
0x1800023d0  test    rax, rax
0x1800023d3  jz      loc_1800022FC
0x1800023d9  mov     byte ptr [rcx], 0
0x1800023dc  inc     rcx
0x1800023df  sub     rax, 1
0x1800023e3  jnz     short loc_1800023D9
0x1800023e5  jmp     loc_1800022FC
0x1800023ea  mov     eax, [rbx]
0x1800023ec  mov     rcx, rbx
0x1800023ef  test    rax, rax
0x1800023f2  jz      loc_1800022FC
0x1800023f8  mov     byte ptr [rcx], 0
0x1800023fb  inc     rcx
0x1800023fe  sub     rax, 1
0x180002402  jnz     short loc_1800023F8
0x180002404  jmp     loc_1800022FC
0x180002409  mov     eax, 80090027h
0x18000240e  jmp     loc_180002306
0x180002413  mov     rcx, [rbx+18h]; hObject
0x180002417  test    rcx, rcx
0x18000241a  jz      short loc_1800023CB
0x18000241c  call    cs:__imp_NCryptFreeObject
0x180002422  jmp     short loc_1800023CB
0x180002424  call    cs:__imp_BCryptDestroyHash
0x18000242a  jmp     loc_180002319
0x18000242f  call    cs:__imp_BCryptDestroyHash
0x180002435  jmp     loc_180002326
0x18000243a  mov     rcx, rbx
0x18000243d  call    FreeProviderObject
0x180002442  jmp     loc_180002304
0x180002447  sub     eax, 73736C38h
0x18000244c  jz      loc_180002354
0x180002452  sub     eax, 1
0x180002455  jz      loc_1800024E4
0x18000245b  sub     eax, 1
0x18000245e  jz      loc_180002354
0x180002464  sub     eax, 1
0x180002467  jz      short loc_1800024D0
0x180002469  cmp     eax, 1
0x18000246c  jnz     short loc_180002488
0x18000246e  mov     rcx, rbx
0x180002471  call    SslpFreeKemKey
0x180002476  mov     ebx, eax
0x180002478  test    eax, eax
0x18000247a  jns     loc_180002304
0x180002480  mov     r9d, 9F9h
0x180002486  jmp     short loc_1800024B6
0x180002488  mov     r9d, 0A2Ch
0x18000248e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002495  lea     rdx, aStatus; "Status"
0x18000249c  mov     ecx, 0C0000002h
0x1800024a1  call    DebugTraceError
0x1800024a6  mov     eax, 0C0000002h
0x1800024ab  jmp     loc_180002306
0x1800024b0  mov     r9d, 0A05h
0x1800024b6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800024bd  mov     ecx, ebx
0x1800024bf  lea     rdx, aStatus; "Status"
0x1800024c6  call    DebugTraceError
0x1800024cb  jmp     loc_1800023C4
0x1800024d0  mov     rcx, rbx
0x1800024d3  call    SslpFreeHybridKey
0x1800024d8  mov     ebx, eax
0x1800024da  test    eax, eax
0x1800024dc  jns     loc_180002304
0x1800024e2  jmp     short loc_1800024B0
0x1800024e4  mov     rcx, [rbx+10h]; hKey
0x1800024e8  test    rcx, rcx
0x1800024eb  jz      loc_1800023EA
0x1800024f1  call    cs:__imp_BCryptDestroyKey
0x1800024f7  jmp     loc_1800023EA
```
