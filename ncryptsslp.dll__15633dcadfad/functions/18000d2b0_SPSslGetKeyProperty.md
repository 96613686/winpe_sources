# SPSslGetKeyProperty

- ea: `0x18000d2b0`
- end: `0x18000d6c6`
- name: `SPSslGetKeyProperty`
- size: `1046`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, BYTE **, DWORD *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x18000b594`
- `0x18000b654`
- `0x18000d2b0`
- `0x1800185e0`

## import_xrefs

- `ncrypt!NCryptGetProperty` at `0x18000d426`
- `ncrypt!NCryptGetProperty` at `0x18000d47e`
- `ncrypt!NCryptGetProperty` at `0x18000d426`
- `ncrypt!NCryptGetProperty` at `0x18000d47e`
- `ntdll!RtlAllocateHeap` at `0x18000d449`
- `ntdll!RtlAllocateHeap` at `0x18000d449`

## string_xrefs

- `0x18000d32d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000d396`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000d4cc`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000d50f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000d545`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000d5a4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000d5cb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000d5f3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000d620`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000d665`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslGetKeyProperty(__int64 a1, const wchar_t *a2, BYTE **a3, DWORD *a4, int a5)
{
  const wchar_t *v7; // rbx
  unsigned int Property; // edi
  __int64 v10; // r13
  unsigned __int64 v11; // rax
  NCRYPT_HANDLE v13; // rbp
  int v14; // edx
  int v15; // r8d
  int v16; // edx
  BYTE *Heap; // rsi
  int v18; // r8d
  int v19; // edx
  int v20; // r8d
  BYTE *v21; // rax
  DWORD cbOutput; // [rsp+90h] [rbp+8h] BYREF

  cbOutput = 0;
  v7 = a2;
  if ( !a1 )
  {
LABEL_6:
    Property = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        99);
    return Property;
  }
  LODWORD(a2) = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 >= 0x20u && *(_DWORD *)(a1 + 4) == 1936944180 )
  {
    v10 = 0;
  }
  else
  {
    if ( (unsigned int)a2 < 0x28 || *(_DWORD *)(a1 + 4) != 1936944182 )
      goto LABEL_6;
    v10 = a1;
  }
  if ( !v7 )
  {
    Property = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 3184);
    return Property;
  }
  v11 = -1;
  do
    ++v11;
  while ( v7[v11] );
  if ( v11 > 0x40 )
  {
    Property = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        118);
    return Property;
  }
  if ( a3 && a4 )
  {
    if ( a5 )
    {
      Property = -2146893815;
      DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 3204);
      return Property;
    }
    if ( !wcscmp(v7, L"KEYTYPE") )
    {
      if ( !v10 )
      {
        Property = -2146893786;
        DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 3213);
        return Property;
      }
      cbOutput = 4;
      v21 = (BYTE *)SafeAllocaAllocateFromHeap(4);
      Heap = v21;
      if ( !v21 )
      {
        Property = -2146893810;
        DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 3223);
        return Property;
      }
      switch ( *(_DWORD *)(v10 + 8) )
      {
        case 0x30007:
          *(_DWORD *)v21 = 23;
          break;
        case 0x30008:
          *(_DWORD *)v21 = 24;
          break;
        case 0x30009:
          *(_DWORD *)v21 = 25;
          break;
        default:
          *(_DWORD *)v21 = 0;
          break;
      }
      goto LABEL_25;
    }
    v13 = *(_QWORD *)(a1 + 24);
    Property = NCryptGetProperty(v13, v7, 0, 0, &cbOutput, 0);
    if ( (Property & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          v15,
          (unsigned int)"Status",
          Property,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          194);
    }
    else
    {
      Heap = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, cbOutput);
      if ( Heap )
      {
        Property = NCryptGetProperty(v13, v7, Heap, cbOutput, &cbOutput, 0);
        if ( (Property & 0x80000000) == 0 )
        {
LABEL_25:
          Property = 0;
          *a4 = cbOutput;
          *a3 = Heap;
          return Property;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v19,
            v20,
            (unsigned int)"Status",
            Property,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            217);
        MSCryptFree(Heap);
      }
      else
      {
        Property = -2146893810;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v16,
            v18,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            203);
      }
    }
  }
  else
  {
    Property = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        125);
  }
  return Property;
}

```

## disassembly

```asm
0x18000d2b0  push    rbx
0x18000d2b2  push    rbp
0x18000d2b3  push    rsi
0x18000d2b4  push    rdi
0x18000d2b5  push    r12
0x18000d2b7  push    r13
0x18000d2b9  push    r14
0x18000d2bb  push    r15
0x18000d2bd  sub     rsp, 48h
0x18000d2c1  xor     r12d, r12d
0x18000d2c4  mov     r14, r9
0x18000d2c7  mov     [rsp+88h+cbOutput], r12d
0x18000d2cf  mov     r15, r8
0x18000d2d2  mov     rbx, rdx
0x18000d2d5  mov     rdi, rcx
0x18000d2d8  test    rcx, rcx
0x18000d2db  jz      short loc_18000D2FF
0x18000d2dd  mov     edx, [rcx]
0x18000d2df  cmp     edx, 20h ; ' '
0x18000d2e2  jb      short loc_18000D2F1
0x18000d2e4  cmp     dword ptr [rcx+4], 73736C34h
0x18000d2eb  jz      loc_18000D5BD
0x18000d2f1  cmp     edx, 28h ; '('
0x18000d2f4  jb      short loc_18000D2FF
0x18000d2f6  cmp     dword ptr [rcx+4], 73736C36h
0x18000d2fd  jz      short loc_18000D343
0x18000d2ff  mov     edi, 80090026h
0x18000d304  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d30b  lea     rax, WPP_GLOBAL_Control
0x18000d312  cmp     rcx, rax
0x18000d315  jz      loc_18000D3BA
0x18000d31b  test    byte ptr [rcx+1Ch], 1
0x18000d31f  jz      loc_18000D3BA
0x18000d325  mov     [rsp+88h+var_58], 0C63h
0x18000d32d  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d334  mov     qword ptr [rsp+88h+dwFlags], rax
0x18000d339  mov     dword ptr [rsp+88h+pcbResult], 80090026h
0x18000d341  jmp     short loc_18000D3AA
0x18000d343  mov     r13, rdi
0x18000d346  mov     ebp, 18h
0x18000d34b  test    rbx, rbx
0x18000d34e  jz      loc_18000D5C5
0x18000d354  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d35b  nop     dword ptr [rax+rax+00h]
0x18000d360  inc     rax
0x18000d363  cmp     [rbx+rax*2], r12w
0x18000d368  jnz     short loc_18000D360
0x18000d36a  cmp     rax, 40h ; '@'
0x18000d36e  jbe     short loc_18000D3CD
0x18000d370  mov     edi, 80090027h
0x18000d375  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d37c  lea     rax, WPP_GLOBAL_Control
0x18000d383  cmp     rcx, rax
0x18000d386  jz      short loc_18000D3BA
0x18000d388  test    byte ptr [rcx+1Ch], 1
0x18000d38c  jz      short loc_18000D3BA
0x18000d38e  mov     [rsp+88h+var_58], 0C76h
0x18000d396  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d39d  mov     qword ptr [rsp+88h+dwFlags], rax
0x18000d3a2  mov     dword ptr [rsp+88h+pcbResult], 80090027h
0x18000d3aa  mov     rcx, [rcx+10h]
0x18000d3ae  lea     r9, aStatus; "Status"
0x18000d3b5  call    WPP_SF_sDsd
0x18000d3ba  mov     eax, edi
0x18000d3bc  add     rsp, 48h
0x18000d3c0  pop     r15
0x18000d3c2  pop     r14
0x18000d3c4  pop     r13
0x18000d3c6  pop     r12
0x18000d3c8  pop     rdi
0x18000d3c9  pop     rsi
0x18000d3ca  pop     rbp
0x18000d3cb  pop     rbx
0x18000d3cc  retn
0x18000d3cd  test    r15, r15
0x18000d3d0  jz      loc_18000D576
0x18000d3d6  test    r14, r14
0x18000d3d9  jz      loc_18000D576
0x18000d3df  cmp     [rsp+88h+arg_20], r12d
0x18000d3e7  jnz     loc_18000D5ED
0x18000d3ed  lea     rdx, aKeytype; "KEYTYPE"
0x18000d3f4  mov     rcx, rbx; String1
0x18000d3f7  call    wcscmp
0x18000d3fc  test    eax, eax
0x18000d3fe  jz      loc_18000D615
0x18000d404  mov     rbp, [rdi+rbp]
0x18000d408  lea     rax, [rsp+88h+cbOutput]
0x18000d410  mov     rcx, rbp; hObject
0x18000d413  mov     [rsp+88h+dwFlags], r12d; dwFlags
0x18000d418  xor     r9d, r9d; cbOutput
0x18000d41b  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18000d420  xor     r8d, r8d; pbOutput
0x18000d423  mov     rdx, rbx; pszProperty
0x18000d426  call    cs:__imp_NCryptGetProperty
0x18000d42c  mov     edi, eax
0x18000d42e  test    eax, eax
0x18000d430  js      short loc_18000D4A3
0x18000d432  mov     rcx, gs:60h
0x18000d43b  xor     edx, edx; Flags
0x18000d43d  mov     r8d, [rsp+88h+cbOutput]; Size
0x18000d445  mov     rcx, [rcx+30h]; HeapHandle
0x18000d449  call    cs:__imp_RtlAllocateHeap
0x18000d44f  mov     rsi, rax
0x18000d452  test    rax, rax
0x18000d455  jz      loc_18000D4E1
0x18000d45b  mov     r9d, [rsp+88h+cbOutput]; cbOutput
0x18000d463  lea     rax, [rsp+88h+cbOutput]
0x18000d46b  mov     [rsp+88h+dwFlags], r12d; dwFlags
0x18000d470  mov     r8, rsi; pbOutput
0x18000d473  mov     rdx, rbx; pszProperty
0x18000d476  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18000d47b  mov     rcx, rbp; hObject
0x18000d47e  call    cs:__imp_NCryptGetProperty
0x18000d484  mov     edi, eax
0x18000d486  test    eax, eax
0x18000d488  js      loc_18000D528
0x18000d48e  mov     eax, [rsp+88h+cbOutput]
0x18000d495  mov     edi, r12d
0x18000d498  mov     [r14], eax
0x18000d49b  mov     [r15], rsi
0x18000d49e  jmp     loc_18000D3BA
0x18000d4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4aa  lea     rax, WPP_GLOBAL_Control
0x18000d4b1  cmp     rcx, rax
0x18000d4b4  jz      loc_18000D3BA
0x18000d4ba  test    byte ptr [rcx+1Ch], 1
0x18000d4be  jz      loc_18000D3BA
0x18000d4c4  mov     [rsp+88h+var_58], 0CC2h
0x18000d4cc  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d4d3  mov     qword ptr [rsp+88h+dwFlags], rax
0x18000d4d8  mov     dword ptr [rsp+88h+pcbResult], edi
0x18000d4dc  jmp     loc_18000D3AA
0x18000d4e1  mov     edi, 8009000Eh
0x18000d4e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4ed  lea     rax, WPP_GLOBAL_Control
0x18000d4f4  cmp     rcx, rax
0x18000d4f7  jz      loc_18000D3BA
0x18000d4fd  test    byte ptr [rcx+1Ch], 1
0x18000d501  jz      loc_18000D3BA
0x18000d507  mov     [rsp+88h+var_58], 0CCBh
0x18000d50f  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d516  mov     qword ptr [rsp+88h+dwFlags], rax
0x18000d51b  mov     dword ptr [rsp+88h+pcbResult], 8009000Eh
0x18000d523  jmp     loc_18000D3AA
0x18000d528  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d52f  lea     rax, WPP_GLOBAL_Control
0x18000d536  cmp     rcx, rax
0x18000d539  jz      short loc_18000D569
0x18000d53b  test    byte ptr [rcx+1Ch], 1
0x18000d53f  jz      short loc_18000D569
0x18000d541  mov     rcx, [rcx+10h]
0x18000d545  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d54c  mov     [rsp+88h+var_58], 0CD9h
0x18000d554  lea     r9, aStatus; "Status"
0x18000d55b  mov     qword ptr [rsp+88h+dwFlags], rax
0x18000d560  mov     dword ptr [rsp+88h+pcbResult], edi
0x18000d564  call    WPP_SF_sDsd
0x18000d569  mov     rcx, rsi
0x18000d56c  call    MSCryptFree
0x18000d571  jmp     loc_18000D3BA
0x18000d576  mov     edi, 80090027h
0x18000d57b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d582  lea     rax, WPP_GLOBAL_Control
0x18000d589  cmp     rcx, rax
0x18000d58c  jz      loc_18000D3BA
0x18000d592  test    byte ptr [rcx+1Ch], 1
0x18000d596  jz      loc_18000D3BA
0x18000d59c  mov     [rsp+88h+var_58], 0C7Dh
0x18000d5a4  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d5ab  mov     qword ptr [rsp+88h+dwFlags], rax
0x18000d5b0  mov     dword ptr [rsp+88h+pcbResult], 80090027h
0x18000d5b8  jmp     loc_18000D3AA
0x18000d5bd  mov     r13, r12
0x18000d5c0  jmp     loc_18000D346
0x18000d5c5  mov     r9d, 0C70h
0x18000d5cb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d5d2  lea     rdx, aStatus; "Status"
0x18000d5d9  mov     ecx, 80090027h
0x18000d5de  mov     edi, 80090027h
0x18000d5e3  call    DebugTraceError
0x18000d5e8  jmp     loc_18000D3BA
0x18000d5ed  mov     r9d, 0C84h
0x18000d5f3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d5fa  lea     rdx, aStatus; "Status"
0x18000d601  mov     ecx, 80090009h
0x18000d606  mov     edi, 80090009h
0x18000d60b  call    DebugTraceError
0x18000d610  jmp     loc_18000D3BA
0x18000d615  test    r13, r13
0x18000d618  jnz     short loc_18000D642
0x18000d61a  mov     r9d, 0C8Dh
0x18000d620  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d627  lea     rdx, aStatus; "Status"
0x18000d62e  mov     ecx, 80090026h
0x18000d633  mov     edi, 80090026h
0x18000d638  call    DebugTraceError
0x18000d63d  jmp     loc_18000D3BA
0x18000d642  mov     ecx, 4
0x18000d647  mov     [rsp+88h+cbOutput], 4
0x18000d652  call    SafeAllocaAllocateFromHeap
0x18000d657  mov     rsi, rax
0x18000d65a  test    rax, rax
0x18000d65d  jnz     short loc_18000D687
0x18000d65f  mov     r9d, 0C97h
0x18000d665  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d66c  lea     rdx, aStatus; "Status"
0x18000d673  mov     ecx, 8009000Eh
0x18000d678  mov     edi, 8009000Eh
0x18000d67d  call    DebugTraceError
0x18000d682  jmp     loc_18000D3BA
0x18000d687  mov     ecx, [r13+8]
0x18000d68b  sub     ecx, 30007h
0x18000d691  jz      short loc_18000D6BB
0x18000d693  sub     ecx, 1
0x18000d696  jz      short loc_18000D6B0
0x18000d698  cmp     ecx, 1
0x18000d69b  jz      short loc_18000D6A5
0x18000d69d  mov     [rax], r12d
0x18000d6a0  jmp     loc_18000D48E
0x18000d6a5  mov     dword ptr [rax], 19h
0x18000d6ab  jmp     loc_18000D48E
0x18000d6b0  mov     dword ptr [rax], 18h
0x18000d6b6  jmp     loc_18000D48E
0x18000d6bb  mov     dword ptr [rax], 17h
0x18000d6c1  jmp     loc_18000D48E
```
