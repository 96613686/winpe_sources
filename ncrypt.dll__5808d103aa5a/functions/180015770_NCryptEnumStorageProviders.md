# NCryptEnumStorageProviders

- ea: `0x180015770`
- end: `0x1800159e3`
- name: `NCryptEnumStorageProviders`
- size: `627`
- prototype: `SECURITY_STATUS __stdcall(DWORD *pdwProviderCount, NCryptProviderName **ppProviderList, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cd0`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180015770`
- `0x18001f15d`

## import_xrefs

- `bcrypt!BCryptResolveProviders` at `0x1800157ee`
- `bcrypt!BCryptResolveProviders` at `0x1800157ee`
- `bcrypt!BCryptFreeBuffer` at `0x1800159a6`
- `bcrypt!BCryptFreeBuffer` at `0x1800159a6`

## string_xrefs

- `0x18001593c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180015990`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800159d2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
SECURITY_STATUS __stdcall NCryptEnumStorageProviders(
        DWORD *pdwProviderCount,
        NCryptProviderName **ppProviderList,
        DWORD dwFlags)
{
  NCryptAlgorithmName **v3; // r9
  unsigned int v6; // eax
  unsigned int v7; // ebx
  int v8; // r8d
  DWORD v9; // ebx
  DWORD v10; // edx
  __int64 v11; // rax
  unsigned int v12; // ebx
  __int64 v13; // rax
  NCryptProviderName *v14; // rdi
  unsigned int v15; // r15d
  WCHAR *v16; // rbp
  DWORD i; // ecx
  __int64 v18; // rax
  __int64 v19; // rdx
  size_t v20; // rbx
  __int64 v22; // r9
  __int64 v23; // rcx
  ULONG v24; // [rsp+70h] [rbp+8h] BYREF
  PVOID pvBuffer; // [rsp+88h] [rbp+20h] BYREF
  PBYTE v26; // [rsp+90h] [rbp+28h]
  DWORD v27; // [rsp+98h] [rbp+30h]
  DWORD *v28; // [rsp+A0h] [rbp+38h]

  pvBuffer = 0;
  v24 = 0;
  if ( pdwProviderCount && ppProviderList )
  {
    if ( (dwFlags & 0xFFFFFFBF) != 0 )
    {
      v7 = -2146893815;
      v22 = 729;
      v23 = 2148073481LL;
    }
    else
    {
      *pdwProviderCount = 0;
      *ppProviderList = 0;
      v6 = BCryptResolveProviders(0, 0x10001u, L"KEY_STORAGE", 0, 1u, 2u, &v24, (PCRYPT_PROVIDER_REFS *)&pvBuffer);
      v7 = v6;
      if ( !v6 )
      {
        v8 = 0;
        v9 = *(_DWORD *)pvBuffer;
        if ( *(_DWORD *)pvBuffer )
        {
          v10 = 0;
          do
          {
            v11 = -1;
            do
              ++v11;
            while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8LL * v10) + 16LL) + 2 * v11) );
            ++v10;
            v8 += 2 * v11 + 2;
          }
          while ( v10 < v9 );
        }
        v12 = 16 * v9;
        v13 = SafeAllocaAllocateFromHeap(v12 + v8);
        v14 = (NCryptProviderName *)v13;
        if ( v13 )
        {
          v15 = 0;
          v16 = (WCHAR *)(v13 + v12);
          for ( i = *(_DWORD *)pvBuffer; v15 < *(_DWORD *)pvBuffer; i = *(_DWORD *)pvBuffer )
          {
            v18 = -1;
            do
              ++v18;
            while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8LL * v15) + 16LL) + 2 * v18) );
            v19 = v15;
            v20 = 2LL * (unsigned int)(v18 + 1);
            v14[v19].pszName = v16;
            v14[v19].pszComment = 0;
            memcpy_0(v16, *(const void **)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8LL * v15) + 16LL), v20);
            v16 = (WCHAR *)((char *)v16 + v20);
            ++v15;
          }
          *pdwProviderCount = i;
          v7 = 0;
          *ppProviderList = v14;
        }
        else
        {
          v7 = -2146893810;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)ppProviderList,
              dwFlags,
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
              10);
        }
        goto LABEL_16;
      }
      v22 = 753;
      v23 = v6;
    }
    DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v22);
  }
  else
  {
    v7 = -2146893785;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return NormalizeNteStatus(
               v7,
               (NCRYPT_KEY_HANDLE *)ppProviderList,
               *(NCryptKeyName ***)&dwFlags,
               v3,
               v26,
               v27,
               v28);
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)ppProviderList,
      dwFlags,
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
      210);
  }
LABEL_16:
  if ( pvBuffer )
    BCryptFreeBuffer(pvBuffer);
  return NormalizeNteStatus(v7, (NCRYPT_KEY_HANDLE *)ppProviderList, *(NCryptKeyName ***)&dwFlags, v3, v26, v27, v28);
}

```

## disassembly

```asm
0x180015770  mov     r11, rsp
0x180015773  mov     [r11+10h], rbx
0x180015777  mov     [r11+18h], rbp
0x18001577b  push    rsi
0x18001577c  push    rdi
0x18001577d  push    r12
0x18001577f  push    r14
0x180015781  push    r15
0x180015783  sub     rsp, 40h
0x180015787  xor     r12d, r12d
0x18001578a  mov     rsi, rdx
0x18001578d  mov     [r11+20h], r12
0x180015791  mov     r14, rcx
0x180015794  mov     [r11+8], r12d
0x180015798  test    rcx, rcx
0x18001579b  jz      loc_180015962
0x1800157a1  test    rdx, rdx
0x1800157a4  jz      loc_180015962
0x1800157aa  test    r8d, 0FFFFFFBFh
0x1800157b1  jnz     loc_1800159B1
0x1800157b7  lea     rax, [r11+20h]
0x1800157bb  mov     [rcx], r12d
0x1800157be  mov     [r11-30h], rax
0x1800157c2  lea     r8, pszFunction; "KEY_STORAGE"
0x1800157c9  lea     rax, [r11+8]
0x1800157cd  mov     [rdx], r12
0x1800157d0  mov     [r11-38h], rax
0x1800157d4  xor     r9d, r9d; pszProvider
0x1800157d7  mov     [rsp+68h+dwFlags], 2; dwFlags
0x1800157df  mov     edx, 10001h; dwInterface
0x1800157e4  xor     ecx, ecx; pszContext
0x1800157e6  mov     [rsp+68h+dwMode], 1; dwMode
0x1800157ee  call    cs:__imp_BCryptResolveProviders
0x1800157f4  mov     ebx, eax
0x1800157f6  test    eax, eax
0x1800157f8  jnz     loc_1800159C3
0x1800157fe  mov     rax, [rsp+68h+pvBuffer]
0x180015806  mov     r8d, r12d
0x180015809  mov     ebx, [rax]
0x18001580b  test    ebx, ebx
0x18001580d  jz      short loc_18001583C
0x18001580f  mov     r10, [rax+8]
0x180015813  mov     edx, r12d
0x180015816  mov     eax, edx
0x180015818  mov     rcx, [r10+rax*8]
0x18001581c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015820  mov     r9, [rcx+10h]
0x180015824  inc     rax
0x180015827  cmp     [r9+rax*2], r12w
0x18001582c  jnz     short loc_180015824
0x18001582e  lea     r8d, [r8+rax*2]
0x180015832  inc     edx
0x180015834  add     r8d, 2
0x180015838  cmp     edx, ebx
0x18001583a  jb      short loc_180015816
0x18001583c  shl     ebx, 4
0x18001583f  lea     ecx, [rbx+r8]
0x180015843  call    SafeAllocaAllocateFromHeap
0x180015848  mov     rdi, rax
0x18001584b  test    rax, rax
0x18001584e  jz      loc_180015916
0x180015854  mov     ebp, ebx
0x180015856  mov     r15d, r12d
0x180015859  add     rbp, rax
0x18001585c  mov     rax, [rsp+68h+pvBuffer]
0x180015864  mov     ecx, [rax]
0x180015866  test    ecx, ecx
0x180015868  jz      short loc_1800158DD
0x18001586a  mov     rax, [rsp+68h+pvBuffer]
0x180015872  mov     edx, r15d
0x180015875  mov     rcx, [rax+8]
0x180015879  lea     r8, ds:0[rdx*8]
0x180015881  mov     rax, [rcx+r8]
0x180015885  mov     rcx, [rax+10h]
0x180015889  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001588d  inc     rax
0x180015890  cmp     [rcx+rax*2], r12w
0x180015895  jnz     short loc_18001588D
0x180015897  add     rdx, rdx
0x18001589a  lea     ebx, [rax+1]
0x18001589d  add     rbx, rbx
0x1800158a0  mov     [rdi+rdx*8], rbp
0x1800158a4  mov     [rdi+rdx*8+8], r12
0x1800158a9  mov     rax, [rsp+68h+pvBuffer]
0x1800158b1  mov     rcx, [rax+8]
0x1800158b5  mov     rdx, [rcx+r8]
0x1800158b9  mov     r8, rbx; Size
0x1800158bc  mov     rcx, rbp; void *
0x1800158bf  mov     rdx, [rdx+10h]; Src
0x1800158c3  call    memcpy_0
0x1800158c8  mov     rax, [rsp+68h+pvBuffer]
0x1800158d0  add     rbp, rbx
0x1800158d3  inc     r15d
0x1800158d6  mov     ecx, [rax]
0x1800158d8  cmp     r15d, ecx
0x1800158db  jb      short loc_18001586A
0x1800158dd  mov     [r14], ecx
0x1800158e0  mov     ebx, r12d
0x1800158e3  mov     [rsi], rdi
0x1800158e6  mov     rcx, [rsp+68h+pvBuffer]; pvBuffer
0x1800158ee  test    rcx, rcx
0x1800158f1  jnz     loc_1800159A6
0x1800158f7  mov     ecx, ebx
0x1800158f9  lea     r11, [rsp+68h+var_28]
0x1800158fe  mov     rbx, [r11+38h]
0x180015902  mov     rbp, [r11+40h]
0x180015906  mov     rsp, r11
0x180015909  pop     r15
0x18001590b  pop     r14
0x18001590d  pop     r12
0x18001590f  pop     rdi
0x180015910  pop     rsi
0x180015911  jmp     NormalizeNteStatus
0x180015916  mov     ebx, 8009000Eh
0x18001591b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015922  lea     rax, WPP_GLOBAL_Control
0x180015929  cmp     rcx, rax
0x18001592c  jz      short loc_1800158E6
0x18001592e  test    byte ptr [rcx+1Ch], 1
0x180015932  jz      short loc_1800158E6
0x180015934  mov     [rsp+68h+var_38], 30Ah
0x18001593c  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015943  mov     qword ptr [rsp+68h+dwFlags], rax
0x180015948  mov     [rsp+68h+dwMode], 8009000Eh
0x180015950  mov     rcx, [rcx+10h]
0x180015954  lea     r9, aStatus; "Status"
0x18001595b  call    WPP_SF_sDsd
0x180015960  jmp     short loc_1800158E6
0x180015962  mov     ebx, 80090027h
0x180015967  mov     rcx, cs:WPP_GLOBAL_Control
0x18001596e  lea     rax, WPP_GLOBAL_Control
0x180015975  cmp     rcx, rax
0x180015978  jz      loc_1800158F7
0x18001597e  test    byte ptr [rcx+1Ch], 1
0x180015982  jz      loc_1800158F7
0x180015988  mov     [rsp+68h+var_38], 2D2h
0x180015990  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015997  mov     qword ptr [rsp+68h+dwFlags], rax
0x18001599c  mov     [rsp+68h+dwMode], 80090027h
0x1800159a4  jmp     short loc_180015950
0x1800159a6  call    cs:__imp_BCryptFreeBuffer
0x1800159ac  jmp     loc_1800158F7
0x1800159b1  mov     ebx, 80090009h
0x1800159b6  mov     r9d, 2D9h
0x1800159bc  mov     ecx, 80090009h
0x1800159c1  jmp     short loc_1800159CB
0x1800159c3  mov     r9d, 2F1h
0x1800159c9  mov     ecx, eax
0x1800159cb  lea     rdx, aStatus; "Status"
0x1800159d2  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800159d9  call    DebugTraceError
0x1800159de  jmp     loc_1800158E6
```
