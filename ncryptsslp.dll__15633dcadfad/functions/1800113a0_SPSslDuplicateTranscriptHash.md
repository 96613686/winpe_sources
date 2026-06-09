# SPSslDuplicateTranscriptHash

- ea: `0x1800113a0`
- end: `0x18001157a`
- name: `SPSslDuplicateTranscriptHash`
- size: `474`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003ef0`
- `0x1800068e0`
- `0x180007940`
- `0x18000b594`
- `0x18000b654`
- `0x1800113a0`
- `0x180011580`
- `0x180024fb0`

## import_xrefs

- `bcrypt!BCryptDuplicateHash` at `0x1800114a0`
- `bcrypt!BCryptDuplicateHash` at `0x1800114a0`
- `bcrypt!BCryptDestroyHash` at `0x1800114f6`
- `bcrypt!BCryptDestroyHash` at `0x1800114f6`

## string_xrefs

- `0x1800113ef`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001142d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800114c9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180011540`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslDuplicateTranscriptHash(__int64 a1, __int64 a2, _QWORD *a3)
{
  BCRYPT_HASH_HANDLE *v4; // rdi
  __int64 v5; // r10
  int v6; // edx
  __int64 v7; // r8
  int v8; // r9d
  unsigned int v9; // edi
  __int64 v10; // r9
  __int64 v11; // rcx
  _BYTE *v13; // rax
  _BYTE *v14; // rbx
  ULONG v15; // r9d
  int v16; // edx
  int v17; // r8d
  void *v18; // rcx
  __int64 v19; // rax
  _BYTE *v20; // rcx

  v4 = (BCRYPT_HASH_HANDLE *)SslpValidateHashHandle(a2, a2);
  if ( !SslpValidateProvHandle(v5) || !v4 )
  {
    v9 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v7,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        23);
    return v9;
  }
  if ( v7 )
  {
    if ( *((_DWORD *)v4 + 2) == 772 )
    {
      if ( v8 )
      {
        DebugTraceError(
          2148073481LL,
          "NTE_BAD_FLAGS",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          6699);
        return 2148073481LL;
      }
      v13 = (_BYTE *)SafeAllocaAllocateFromHeap(*(unsigned int *)v4);
      v14 = v13;
      if ( v13 )
      {
        memmove(v13, v4, *(unsigned int *)v4);
        v15 = *((_DWORD *)v14 + 6);
        *((_QWORD *)v14 + 2) = 0;
        v9 = BCryptDuplicateHash(v4[2], (BCRYPT_HASH_HANDLE *)v14 + 2, v14 + 48, v15, 0);
        if ( (v9 & 0x80000000) == 0 )
        {
          *a3 = v14;
          return 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v16,
              v17,
              (unsigned int)"Status",
              v9,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              69);
          v18 = (void *)*((_QWORD *)v14 + 2);
          if ( v18 )
            BCryptDestroyHash(v18);
          v19 = 48;
          v20 = v14;
          do
          {
            *v14++ = 0;
            --v19;
          }
          while ( v19 );
          MSCryptFree(v20);
        }
        return v9;
      }
      v9 = -2146893810;
      v10 = 6711;
      v11 = 2148073486LL;
    }
    else
    {
      v9 = -2146893783;
      v10 = 6693;
      v11 = 2148073513LL;
    }
  }
  else
  {
    v9 = -2146893785;
    v10 = 6686;
    v11 = 2148073511LL;
  }
  DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v10);
  return v9;
}

```

## disassembly

```asm
0x1800113a0  mov     [rsp+arg_0], rbx
0x1800113a5  mov     [rsp+arg_8], rsi
0x1800113aa  push    rdi
0x1800113ab  sub     rsp, 40h
0x1800113af  mov     r10, rcx
0x1800113b2  mov     rsi, r8
0x1800113b5  mov     rcx, rdx
0x1800113b8  call    SslpValidateHashHandle
0x1800113bd  mov     rcx, r10
0x1800113c0  mov     rdi, rax
0x1800113c3  call    SslpValidateProvHandle
0x1800113c8  test    rax, rax
0x1800113cb  jz      loc_18001151E
0x1800113d1  test    rdi, rdi
0x1800113d4  jz      loc_18001151E
0x1800113da  test    r8, r8
0x1800113dd  jnz     short loc_180011407
0x1800113df  mov     edi, 80090027h
0x1800113e4  mov     r9d, 1A1Eh
0x1800113ea  mov     ecx, 80090027h
0x1800113ef  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800113f6  lea     rdx, aStatus; "Status"
0x1800113fd  call    DebugTraceError
0x180011402  jmp     loc_180011568
0x180011407  cmp     dword ptr [rdi+8], 304h
0x18001140e  jz      short loc_180011422
0x180011410  mov     edi, 80090029h
0x180011415  mov     r9d, 1A25h
0x18001141b  mov     ecx, 80090029h
0x180011420  jmp     short loc_1800113EF
0x180011422  test    r9d, r9d
0x180011425  jz      short loc_18001144F
0x180011427  mov     r9d, 1A2Bh
0x18001142d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011434  lea     rdx, aNteBadFlags; "NTE_BAD_FLAGS"
0x18001143b  mov     ecx, 80090009h
0x180011440  call    DebugTraceError
0x180011445  mov     eax, 80090009h
0x18001144a  jmp     loc_18001156A
0x18001144f  mov     ecx, [rdi]
0x180011451  call    SafeAllocaAllocateFromHeap
0x180011456  mov     rbx, rax
0x180011459  test    rax, rax
0x18001145c  jnz     short loc_180011473
0x18001145e  mov     edi, 8009000Eh
0x180011463  mov     r9d, 1A37h
0x180011469  mov     ecx, 8009000Eh
0x18001146e  jmp     loc_1800113EF
0x180011473  mov     r8d, [rdi]; Size
0x180011476  mov     rdx, rdi; Src
0x180011479  mov     rcx, rbx; void *
0x18001147c  call    memmove
0x180011481  mov     r9d, [rbx+18h]; cbHashObject
0x180011485  lea     rdx, [rbx+10h]; phNewHash
0x180011489  mov     qword ptr [rdx], 0
0x180011490  lea     r8, [rbx+30h]; pbHashObject
0x180011494  mov     rcx, [rdi+10h]; hHash
0x180011498  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1800114a0  call    cs:__imp_BCryptDuplicateHash
0x1800114a6  mov     edi, eax
0x1800114a8  test    eax, eax
0x1800114aa  jns     short loc_180011517
0x1800114ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114b3  lea     rax, WPP_GLOBAL_Control
0x1800114ba  cmp     rcx, rax
0x1800114bd  jz      short loc_1800114ED
0x1800114bf  test    byte ptr [rcx+1Ch], 1
0x1800114c3  jz      short loc_1800114ED
0x1800114c5  mov     rcx, [rcx+10h]
0x1800114c9  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800114d0  mov     [rsp+48h+var_18], 1A45h
0x1800114d8  lea     r9, aStatus; "Status"
0x1800114df  mov     [rsp+48h+var_20], rax
0x1800114e4  mov     [rsp+48h+dwFlags], edi
0x1800114e8  call    WPP_SF_sDsd
0x1800114ed  mov     rcx, [rbx+10h]; hHash
0x1800114f1  test    rcx, rcx
0x1800114f4  jz      short loc_1800114FC
0x1800114f6  call    cs:__imp_BCryptDestroyHash
0x1800114fc  mov     eax, 30h ; '0'
0x180011501  mov     rcx, rbx
0x180011504  mov     byte ptr [rbx], 0
0x180011507  inc     rbx
0x18001150a  sub     rax, 1
0x18001150e  jnz     short loc_180011504
0x180011510  call    MSCryptFree
0x180011515  jmp     short loc_180011568
0x180011517  mov     [rsi], rbx
0x18001151a  xor     edi, edi
0x18001151c  jmp     short loc_180011568
0x18001151e  mov     edi, 80090026h
0x180011523  mov     rcx, cs:WPP_GLOBAL_Control
0x18001152a  lea     rax, WPP_GLOBAL_Control
0x180011531  cmp     rcx, rax
0x180011534  jz      short loc_180011568
0x180011536  test    byte ptr [rcx+1Ch], 1
0x18001153a  jz      short loc_180011568
0x18001153c  mov     rcx, [rcx+10h]
0x180011540  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011547  mov     [rsp+48h+var_18], 1A17h
0x18001154f  lea     r9, aStatus; "Status"
0x180011556  mov     [rsp+48h+var_20], rax
0x18001155b  mov     [rsp+48h+dwFlags], 80090026h
0x180011563  call    WPP_SF_sDsd
0x180011568  mov     eax, edi
0x18001156a  mov     rbx, [rsp+48h+arg_0]
0x18001156f  mov     rsi, [rsp+48h+arg_8]
0x180011574  add     rsp, 40h
0x180011578  pop     rdi
0x180011579  retn
```
