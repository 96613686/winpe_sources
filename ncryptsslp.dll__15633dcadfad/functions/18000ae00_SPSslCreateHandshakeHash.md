# SPSslCreateHandshakeHash

- ea: `0x18000ae00`
- end: `0x18000b350`
- name: `SPSslCreateHandshakeHash`
- size: `1360`
- prototype: `__int64 __fastcall(_DWORD *, __int64, int, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001acc`
- `0x180003ef0`
- `0x18000ae00`
- `0x18000b594`
- `0x18000b654`
- `0x1800183d0`
- `0x180025660`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000b0a5`
- `bcrypt!BCryptCreateHash` at `0x18000b298`
- `bcrypt!BCryptCreateHash` at `0x18000b0a5`
- `bcrypt!BCryptCreateHash` at `0x18000b298`
- `bcrypt!BCryptDestroyHash` at `0x18000b2c4`
- `bcrypt!BCryptDestroyHash` at `0x18000b2c4`
- `ntdll!RtlAllocateHeap` at `0x18000b036`
- `ntdll!RtlAllocateHeap` at `0x18000b036`

## string_xrefs

- `0x18000af3d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000af85`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000b0e7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000b250`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000b2dc`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslCreateHandshakeHash(_DWORD *a1, __int64 a2, int a3, int a4, int a5)
{
  unsigned int v6; // r9d
  _QWORD *v7; // r11
  __int64 i; // rcx
  int v10; // r10d
  __int64 j; // rax
  const wchar_t *v12; // rsi
  __int64 k; // rdi
  __int64 *v14; // rcx
  unsigned int v15; // edi
  char v17; // bp
  int v18; // r14d
  _QWORD *v19; // rcx
  BCRYPT_ALG_HANDLE *v20; // r15
  unsigned int v21; // r14d
  BCRYPT_ALG_HANDLE *v22; // r13
  char *Heap; // rax
  char *v24; // rdi
  NTSTATUS Hash; // eax
  int v26; // edx
  int v27; // r8d
  int HashEntry; // eax
  UCHAR *v29; // r8
  NTSTATUS v30; // eax
  _QWORD *v31; // [rsp+88h] [rbp+10h]
  int v32; // [rsp+90h] [rbp+18h]

  v32 = a3;
  v31 = (_QWORD *)a2;
  v6 = a3;
  v7 = (_QWORD *)a2;
  if ( a5 )
  {
    v15 = -2146893815;
    DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 1466);
    return v15;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 7 )
      goto LABEL_23;
    a2 = 8 * i;
    if ( (unsigned __int16)ProtocolVersionList[4 * i] == a3 )
      break;
  }
  v10 = *(int *)((char *)&dword_180031A24 + a2);
  if ( !v10 )
  {
LABEL_23:
    v15 = -2146893783;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        195);
    return v15;
  }
  a3 = g_dwCipherSuiteInfoTotalCount;
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    if ( (unsigned int)j >= g_dwCipherSuiteInfoTotalCount )
      goto LABEL_23;
    a2 = g_pCipherSuiteInfo[j];
    if ( a2 )
    {
      if ( *(_DWORD *)(a2 + 4) == a4 && (v10 & *(_DWORD *)a2) != 0 )
        break;
    }
  }
  if ( v6 < 0x303 || v6 == 65279 )
  {
    LODWORD(k) = 2;
    v17 = 1;
    goto LABEL_29;
  }
  v12 = *(const wchar_t **)(a2 + 136);
  if ( !v12 || !*v12 )
  {
    LODWORD(k) = 4;
LABEL_28:
    v17 = 0;
LABEL_29:
    if ( a1 && *a1 >= 0x310u && a1[1] == 1936944177 )
    {
      if ( !v7 )
      {
        v15 = -2146893785;
        LOBYTE(v18) = 39;
        DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 1337);
        v19 = WPP_GLOBAL_Control;
        goto LABEL_51;
      }
      v20 = (BCRYPT_ALG_HANDLE *)&a1[8 * (unsigned int)k + 68];
      if ( *((_DWORD *)v20 + 7)
        || (HashEntry = I_GetHashEntry((unsigned int)k, (unsigned int)a1[3], &a1[8 * (unsigned int)k + 68]),
            v18 = HashEntry,
            HashEntry >= 0) )
      {
        v21 = *((_DWORD *)v20 + 4) + 48;
        if ( v17 )
        {
          v22 = (BCRYPT_ALG_HANDLE *)(a1 + 76);
          v21 += *((_DWORD *)v22 + 4);
        }
        else
        {
          v22 = 0;
        }
        Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
        v24 = Heap;
        if ( !Heap )
        {
          v15 = -2146893810;
          LOBYTE(v18) = 14;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v15;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_51;
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            a3,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            92);
          goto LABEL_46;
        }
        memset(Heap, 0, v21);
        *((_DWORD *)v24 + 2) = v32;
        *(_DWORD *)v24 = v21;
        *((_DWORD *)v24 + 1) = 1936944178;
        *((_DWORD *)v24 + 3) = a4;
        *((_DWORD *)v24 + 6) = *((_DWORD *)v20 + 4);
        *((_DWORD *)v24 + 7) = *((_DWORD *)v20 + 6);
        Hash = BCryptCreateHash(*v20, (BCRYPT_HASH_HANDLE *)v24 + 2, (PUCHAR)v24 + 48, *((_DWORD *)v20 + 4), 0, 0, 0);
        v18 = Hash;
        if ( Hash < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v26,
              v27,
              (unsigned int)"Status",
              Hash,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              115);
        }
        else
        {
          if ( !v17
            || (v29 = (UCHAR *)&v24[*((unsigned int *)v20 + 4) + 48],
                *((_DWORD *)v24 + 10) = *((_DWORD *)v22 + 4),
                v30 = BCryptCreateHash(*v22, (BCRYPT_HASH_HANDLE *)v24 + 4, v29, *((_DWORD *)v22 + 4), 0, 0, 0),
                v18 = v30,
                v30 >= 0) )
          {
            *v31 = v24;
            return 0;
          }
          DebugTraceError(
            (unsigned int)v30,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            1415);
          BCryptDestroyHash(*((BCRYPT_HASH_HANDLE *)v24 + 2));
        }
        MSCryptFree(v24);
        v19 = WPP_GLOBAL_Control;
      }
      else
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            a3,
            (unsigned int)"Status",
            HashEntry,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            71);
          v19 = WPP_GLOBAL_Control;
          v15 = v18;
          goto LABEL_51;
        }
      }
    }
    else
    {
      v15 = -2146893786;
      v18 = -2146893786;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          a3,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          50);
LABEL_46:
        v19 = WPP_GLOBAL_Control;
LABEL_51:
        if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 )
          WPP_SF_sDsd(
            v19[2],
            a2,
            a3,
            (unsigned int)"Status",
            v18,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            241);
        return v15;
      }
    }
    v15 = v18;
    if ( v18 >= 0 )
      return v15;
    goto LABEL_51;
  }
  for ( k = 0; (unsigned int)k < g_dwHashInfoTotalCount; k = (unsigned int)(k + 1) )
  {
    v14 = (__int64 *)g_pHashInfo[k];
    if ( v14 )
    {
      a2 = *v14;
      if ( *v14 )
      {
        if ( !wcsnicmp(v12, (const wchar_t *)a2, 0x40u) )
        {
          v7 = v31;
          goto LABEL_28;
        }
      }
    }
  }
  v15 = -2146893783;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (unsigned int)"Status",
      41,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      215);
  return v15;
}

```

## disassembly

```asm
0x18000ae00  mov     [rsp+arg_10], r8d
0x18000ae05  mov     [rsp+arg_8], rdx
0x18000ae0a  push    rbx
0x18000ae0b  push    rbp
0x18000ae0c  push    rsi
0x18000ae0d  push    rdi
0x18000ae0e  push    r12
0x18000ae10  push    r13
0x18000ae12  push    r15
0x18000ae14  sub     rsp, 40h
0x18000ae18  cmp     [rsp+78h+arg_20], 0
0x18000ae20  mov     ebx, r9d
0x18000ae23  mov     r9d, r8d
0x18000ae26  mov     r11, rdx
0x18000ae29  mov     r13, rcx
0x18000ae2c  jnz     loc_18000B2D6
0x18000ae32  mov     [rsp+78h+arg_0], r14
0x18000ae3a  xor     ecx, ecx
0x18000ae3c  lea     r14, __ImageBase
0x18000ae43  cmp     ecx, 7
0x18000ae46  jnb     loc_18000AF17
0x18000ae4c  lea     rdx, ds:0[rcx*8]
0x18000ae54  movzx   eax, word ptr [rdx+r14+31A20h]
0x18000ae5d  cmp     eax, r9d
0x18000ae60  jz      short loc_18000AE66
0x18000ae62  inc     ecx
0x18000ae64  jmp     short loc_18000AE43
0x18000ae66  mov     r10d, [rdx+r14+31A24h]
0x18000ae6e  test    r10d, r10d
0x18000ae71  jz      loc_18000AF17
0x18000ae77  mov     r8d, cs:g_dwCipherSuiteInfoTotalCount
0x18000ae7e  xor     eax, eax
0x18000ae80  cmp     eax, r8d
0x18000ae83  jnb     loc_18000AF17
0x18000ae89  mov     rdx, rva g_pCipherSuiteInfo[r14+rax*8]
0x18000ae91  test    rdx, rdx
0x18000ae94  jz      short loc_18000AE9B
0x18000ae96  cmp     [rdx+4], ebx
0x18000ae99  jz      short loc_18000AE9F
0x18000ae9b  inc     eax
0x18000ae9d  jmp     short loc_18000AE80
0x18000ae9f  test    [rdx], r10d
0x18000aea2  jz      short loc_18000AE9B
0x18000aea4  cmp     r9d, 303h
0x18000aeab  jb      loc_18000B2FE
0x18000aeb1  cmp     r9d, 0FEFFh
0x18000aeb8  jz      loc_18000B2FE
0x18000aebe  mov     rsi, [rdx+88h]
0x18000aec5  test    rsi, rsi
0x18000aec8  jz      loc_18000B1BE
0x18000aece  cmp     word ptr [rsi], 0
0x18000aed2  jz      loc_18000B1BE
0x18000aed8  xor     edi, edi
0x18000aeda  nop     word ptr [rax+rax+00h]
0x18000aee0  cmp     edi, cs:g_dwHashInfoTotalCount
0x18000aee6  jnb     loc_18000B222
0x18000aeec  mov     rcx, rva g_pHashInfo[r14+rdi*8]
0x18000aef4  test    rcx, rcx
0x18000aef7  jz      short loc_18000AF13
0x18000aef9  mov     rdx, [rcx]; String2
0x18000aefc  test    rdx, rdx
0x18000aeff  jz      short loc_18000AF13
0x18000af01  mov     r8d, 40h ; '@'; MaxCount
0x18000af07  mov     rcx, rsi; String1
0x18000af0a  call    _wcsnicmp
0x18000af0f  test    eax, eax
0x18000af11  jz      short loc_18000AF7A
0x18000af13  inc     edi
0x18000af15  jmp     short loc_18000AEE0
0x18000af17  mov     edi, 80090029h
0x18000af1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af23  lea     rbx, WPP_GLOBAL_Control
0x18000af2a  cmp     rcx, rbx
0x18000af2d  jz      short loc_18000AF61
0x18000af2f  test    byte ptr [rcx+1Ch], 1
0x18000af33  jz      short loc_18000AF61
0x18000af35  mov     [rsp+78h+dwFlags], 5C3h
0x18000af3d  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000af44  mov     qword ptr [rsp+78h+cbSecret], rsi
0x18000af49  mov     dword ptr [rsp+78h+pbSecret], 80090029h
0x18000af51  mov     rcx, [rcx+10h]
0x18000af55  lea     r9, aStatus; "Status"
0x18000af5c  call    WPP_SF_sDsd
0x18000af61  mov     r14, [rsp+78h+arg_0]
0x18000af69  mov     eax, edi
0x18000af6b  add     rsp, 40h
0x18000af6f  pop     r15
0x18000af71  pop     r13
0x18000af73  pop     r12
0x18000af75  pop     rdi
0x18000af76  pop     rsi
0x18000af77  pop     rbp
0x18000af78  pop     rbx
0x18000af79  retn
0x18000af7a  mov     r11, [rsp+78h+arg_8]
0x18000af82  xor     bpl, bpl
0x18000af85  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000af8c  test    r13, r13
0x18000af8f  jz      short loc_18000AFA5
0x18000af91  cmp     dword ptr [r13+0], 310h
0x18000af99  jb      short loc_18000AFA5
0x18000af9b  cmp     dword ptr [r13+4], 73736C31h
0x18000afa3  jz      short loc_18000AFE8
0x18000afa5  mov     edi, 80090026h
0x18000afaa  mov     r14d, edi
0x18000afad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afb4  lea     rbx, WPP_GLOBAL_Control
0x18000afbb  cmp     rcx, rbx
0x18000afbe  jz      loc_18000B211
0x18000afc4  test    byte ptr [rcx+1Ch], 1
0x18000afc8  jz      loc_18000B211
0x18000afce  mov     [rsp+78h+dwFlags], 532h
0x18000afd6  mov     qword ptr [rsp+78h+cbSecret], rsi
0x18000afdb  mov     dword ptr [rsp+78h+pbSecret], 80090026h
0x18000afe3  jmp     loc_18000B116
0x18000afe8  test    r11, r11
0x18000afeb  jz      loc_18000B30B
0x18000aff1  mov     r15d, edi
0x18000aff4  shl     r15, 5
0x18000aff8  add     r15, 110h
0x18000afff  add     r15, r13
0x18000b002  cmp     dword ptr [r15+1Ch], 0
0x18000b007  jz      loc_18000B12F
0x18000b00d  mov     r14d, [r15+10h]
0x18000b011  add     r14d, 30h ; '0'
0x18000b015  test    bpl, bpl
0x18000b018  jnz     loc_18000B340
0x18000b01e  xor     r13d, r13d
0x18000b021  mov     rcx, gs:60h
0x18000b02a  xor     edx, edx; Flags
0x18000b02c  mov     r8d, r14d; Size
0x18000b02f  mov     r12d, r14d
0x18000b032  mov     rcx, [rcx+30h]; HeapHandle
0x18000b036  call    cs:__imp_RtlAllocateHeap
0x18000b03c  mov     rdi, rax
0x18000b03f  test    rax, rax
0x18000b042  jz      loc_18000B0D1
0x18000b048  mov     r8d, r12d; Size
0x18000b04b  xor     edx, edx; Val
0x18000b04d  mov     rcx, rax; void *
0x18000b050  call    memset
0x18000b055  mov     eax, [rsp+78h+arg_10]
0x18000b05c  lea     r12, [rdi+30h]
0x18000b060  mov     [rdi+8], eax
0x18000b063  lea     rdx, [rdi+10h]; phHash
0x18000b067  mov     [rdi], r14d
0x18000b06a  mov     r8, r12; pbHashObject
0x18000b06d  mov     dword ptr [rdi+4], 73736C32h
0x18000b074  mov     [rdi+0Ch], ebx
0x18000b077  mov     eax, [r15+10h]
0x18000b07b  mov     [rdi+18h], eax
0x18000b07e  mov     eax, [r15+18h]
0x18000b082  mov     [rdi+1Ch], eax
0x18000b085  mov     r9d, [r15+10h]; cbHashObject
0x18000b089  mov     rcx, [r15]; hAlgorithm
0x18000b08c  mov     [rsp+78h+dwFlags], 0; dwFlags
0x18000b094  mov     [rsp+78h+cbSecret], 0; cbSecret
0x18000b09c  mov     [rsp+78h+pbSecret], 0; pbSecret
0x18000b0a5  call    cs:__imp_BCryptCreateHash
0x18000b0ab  mov     r14d, eax
0x18000b0ae  test    eax, eax
0x18000b0b0  js      loc_18000B1C8
0x18000b0b6  test    bpl, bpl
0x18000b0b9  jnz     loc_18000B265
0x18000b0bf  mov     rax, [rsp+78h+arg_8]
0x18000b0c7  mov     [rax], rdi
0x18000b0ca  xor     edi, edi
0x18000b0cc  jmp     loc_18000AF61
0x18000b0d1  mov     edi, 8009000Eh
0x18000b0d6  mov     r14d, edi
0x18000b0d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0e0  lea     rbx, WPP_GLOBAL_Control
0x18000b0e7  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b0ee  cmp     rcx, rbx
0x18000b0f1  jz      loc_18000AF61
0x18000b0f7  test    byte ptr [rcx+1Ch], 1
0x18000b0fb  jz      loc_18000B194
0x18000b101  mov     [rsp+78h+dwFlags], 55Ch
0x18000b109  mov     qword ptr [rsp+78h+cbSecret], rsi
0x18000b10e  mov     dword ptr [rsp+78h+pbSecret], 8009000Eh
0x18000b116  mov     rcx, [rcx+10h]
0x18000b11a  lea     r9, aStatus; "Status"
0x18000b121  call    WPP_SF_sDsd
0x18000b126  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b12d  jmp     short loc_18000B194
0x18000b12f  mov     edx, [r13+0Ch]
0x18000b133  mov     r8, r15
0x18000b136  mov     ecx, edi
0x18000b138  call    I_GetHashEntry
0x18000b13d  mov     r14d, eax
0x18000b140  test    eax, eax
0x18000b142  jns     loc_18000B00D
0x18000b148  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b14f  lea     rbx, WPP_GLOBAL_Control
0x18000b156  cmp     rcx, rbx
0x18000b159  jz      loc_18000B211
0x18000b15f  test    byte ptr [rcx+1Ch], 1
0x18000b163  jz      loc_18000B211
0x18000b169  mov     rcx, [rcx+10h]
0x18000b16d  lea     r9, aStatus; "Status"
0x18000b174  mov     [rsp+78h+dwFlags], 547h
0x18000b17c  mov     qword ptr [rsp+78h+cbSecret], rsi
0x18000b181  mov     dword ptr [rsp+78h+pbSecret], eax
0x18000b185  call    WPP_SF_sDsd
0x18000b18a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b191  mov     edi, r14d
0x18000b194  cmp     rcx, rbx
0x18000b197  jz      loc_18000AF61
0x18000b19d  test    byte ptr [rcx+1Ch], 1
0x18000b1a1  jz      loc_18000AF61
0x18000b1a7  mov     [rsp+78h+dwFlags], 5F1h
0x18000b1af  mov     qword ptr [rsp+78h+cbSecret], rsi
0x18000b1b4  mov     dword ptr [rsp+78h+pbSecret], r14d
0x18000b1b9  jmp     loc_18000AF51
0x18000b1be  mov     edi, 4
0x18000b1c3  jmp     loc_18000AF82
0x18000b1c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1cf  lea     rbx, WPP_GLOBAL_Control
0x18000b1d6  cmp     rcx, rbx
0x18000b1d9  jz      short loc_18000B202
0x18000b1db  test    byte ptr [rcx+1Ch], 1
0x18000b1df  jz      short loc_18000B202
0x18000b1e1  mov     rcx, [rcx+10h]
0x18000b1e5  lea     r9, aStatus; "Status"
0x18000b1ec  mov     [rsp+78h+dwFlags], 573h
0x18000b1f4  mov     qword ptr [rsp+78h+cbSecret], rsi
0x18000b1f9  mov     dword ptr [rsp+78h+pbSecret], eax
0x18000b1fd  call    WPP_SF_sDsd
0x18000b202  mov     rcx, rdi
0x18000b205  call    MSCryptFree
0x18000b20a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b211  mov     edi, r14d
0x18000b214  test    r14d, r14d
0x18000b217  jns     loc_18000AF61
0x18000b21d  jmp     loc_18000B194
0x18000b222  mov     edi, 80090029h
0x18000b227  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b22e  lea     rbx, WPP_GLOBAL_Control
0x18000b235  cmp     rcx, rbx
0x18000b238  jz      loc_18000AF61
0x18000b23e  test    byte ptr [rcx+1Ch], 1
0x18000b242  jz      loc_18000AF61
0x18000b248  mov     [rsp+78h+dwFlags], 5D7h
0x18000b250  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b257  mov     qword ptr [rsp+78h+cbSecret], rsi
0x18000b25c  mov     dword ptr [rsp+78h+pbSecret], edi
0x18000b260  jmp     loc_18000AF51
0x18000b265  mov     r8d, [r15+10h]
0x18000b269  lea     rdx, [rdi+20h]; phHash
0x18000b26d  mov     eax, [r13+10h]
0x18000b271  add     r8, r12; pbHashObject
0x18000b274  mov     [rdi+28h], eax
0x18000b277  mov     r9d, [r13+10h]; cbHashObject
0x18000b27b  mov     rcx, [r13+0]; hAlgorithm
0x18000b27f  mov     [rsp+78h+dwFlags], 0; dwFlags
0x18000b287  mov     [rsp+78h+cbSecret], 0; cbSecret
0x18000b28f  mov     [rsp+78h+pbSecret], 0; pbSecret
0x18000b298  call    cs:__imp_BCryptCreateHash
0x18000b29e  mov     r14d, eax
0x18000b2a1  test    eax, eax
0x18000b2a3  jns     loc_18000B0BF
0x18000b2a9  mov     r9d, 587h
0x18000b2af  lea     rdx, aStatus; "Status"
0x18000b2b6  mov     r8, rsi
0x18000b2b9  mov     ecx, eax
0x18000b2bb  call    DebugTraceError
0x18000b2c0  mov     rcx, [rdi+10h]; hHash
0x18000b2c4  call    cs:__imp_BCryptDestroyHash
0x18000b2ca  lea     rbx, WPP_GLOBAL_Control
0x18000b2d1  jmp     loc_18000B202
0x18000b2d6  mov     r9d, 5BAh
0x18000b2dc  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b2e3  lea     rdx, aStatus; "Status"
0x18000b2ea  mov     ecx, 80090009h
0x18000b2ef  mov     edi, 80090009h
0x18000b2f4  call    DebugTraceError
0x18000b2f9  jmp     loc_18000AF69
0x18000b2fe  mov     edi, 2
0x18000b303  mov     bpl, 1
0x18000b306  jmp     loc_18000AF85
0x18000b30b  mov     edi, 80090027h
0x18000b310  lea     rdx, aStatus; "Status"
0x18000b317  mov     r9d, 539h
0x18000b31d  mov     r8, rsi
0x18000b320  mov     ecx, 80090027h
0x18000b325  mov     r14d, edi
0x18000b328  call    DebugTraceError
0x18000b32d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b334  lea     rbx, WPP_GLOBAL_Control
0x18000b33b  jmp     loc_18000B194
0x18000b340  add     r13, 130h
0x18000b347  add     r14d, [r13+10h]
0x18000b34b  jmp     loc_18000B021
```
