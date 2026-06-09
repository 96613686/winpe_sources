# OpenSystemPreferredAlgorithmProvider

- ea: `0x180001770`
- end: `0x180001881`
- name: `OpenSystemPreferredAlgorithmProvider`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800016b0`
- `0x1800040e4`

## callees

- `0x180001770`
- `0x1800023e0`
- `0x18000743c`
- `0x1800082b0`
- `0x180028b40`
- `0x1800414e0`
- `0x1800449b0`

## string_xrefs

- `0x180001808`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x18009e2e1`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 __fastcall OpenSystemPreferredAlgorithmProvider(BCRYPT_ALG_HANDLE *a1)
{
  NTSTATUS v2; // ebx
  int v3; // edx
  const WCHAR *v5; // rdx
  NTSTATUS v6; // eax
  PVOID pvBuffer; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+70h] [rbp+20h] BYREF
  ULONG v9; // [rsp+78h] [rbp+28h] BYREF

  hAlgorithm = 0;
  pvBuffer = 0;
  v9 = 0;
  if ( !g_fLoadCNGDone )
    goto LABEL_13;
  v2 = BCryptResolveProviders(0, 6u, 0, 0, 2u, 0, &v9, (PCRYPT_PROVIDER_REFS *)&pvBuffer);
  if ( v2 >= 0 )
  {
    if ( !*(_DWORD *)pvBuffer )
    {
      v2 = -1073741595;
      goto LABEL_6;
    }
    if ( g_fLoadCNGDone )
    {
      v5 = *(const WCHAR **)(**((_QWORD **)pvBuffer + 1) + 8LL);
LABEL_16:
      v6 = BCryptOpenAlgorithmProvider(&hAlgorithm, v5, 0, 0);
      v2 = v6;
      if ( v6 >= 0 )
      {
        v2 = 0;
        *a1 = hAlgorithm;
        hAlgorithm = 0;
      }
      else
      {
        DebugTraceError((unsigned int)v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c", 392);
      }
      goto LABEL_6;
    }
LABEL_13:
    v5 = L"RNG";
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v3 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v3 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v3,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
        (unsigned int)"Status",
        v2,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
        109);
  }
LABEL_6:
  if ( hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  if ( pvBuffer )
    BCryptFreeBuffer(pvBuffer);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180001770  mov     r11, rsp
0x180001773  mov     [r11+8], rbx
0x180001777  mov     [r11+10h], rdi
0x18000177b  mov     [r11+20h], r9d
0x18000177f  mov     [r11+18h], r8
0x180001783  push    rbp
0x180001784  mov     rbp, rsp
0x180001787  sub     rsp, 50h
0x18000178b  cmp     cs:g_fLoadCNGDone, 0
0x180001792  mov     rdi, rcx
0x180001795  mov     [rbp+hAlgorithm], 0
0x18000179d  mov     [rbp+pvBuffer], 0
0x1800017a5  mov     [rbp+arg_18], 0
0x1800017ac  jz      loc_180001865
0x1800017b2  lea     rax, [rbp+pvBuffer]
0x1800017b6  xor     r9d, r9d; pszProvider
0x1800017b9  mov     [r11-20h], rax
0x1800017bd  xor     r8d, r8d; pszFunction
0x1800017c0  lea     rax, [rbp+arg_18]
0x1800017c4  xor     ecx, ecx; pszContext
0x1800017c6  mov     [r11-28h], rax
0x1800017ca  mov     [rsp+50h+dwFlags], 0; dwFlags
0x1800017d2  lea     edx, [r9+6]; dwInterface
0x1800017d6  mov     [rsp+50h+dwMode], 2; dwMode
0x1800017de  call    BCryptResolveProviders
0x1800017e3  mov     ebx, eax
0x1800017e5  test    eax, eax
0x1800017e7  jns     short loc_180001851
0x1800017e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017f0  lea     rax, WPP_GLOBAL_Control
0x1800017f7  cmp     rcx, rax
0x1800017fa  jz      short loc_18000182C
0x1800017fc  mov     edx, [rcx+2Ch]
0x1800017ff  test    dl, 1
0x180001802  jz      short loc_18000182C
0x180001804  mov     rcx, [rcx+18h]
0x180001808  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000180f  mov     [rsp+50h+var_20], 16Dh
0x180001817  lea     r9, aStatus; "Status"
0x18000181e  mov     qword ptr [rsp+50h+dwFlags], r8
0x180001823  mov     [rsp+50h+dwMode], ebx
0x180001827  call    WPP_SF_sDsd
0x18000182c  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x180001830  test    rcx, rcx
0x180001833  jnz     short loc_180001871
0x180001835  mov     rcx, [rbp+pvBuffer]; pvBuffer
0x180001839  test    rcx, rcx
0x18000183c  jnz     short loc_18000187A
0x18000183e  mov     rdi, [rsp+50h+arg_8]
0x180001843  mov     eax, ebx
0x180001845  mov     rbx, [rsp+50h+arg_0]
0x18000184a  add     rsp, 50h
0x18000184e  pop     rbp
0x18000184f  retn
0x180001851  mov     rax, [rbp+pvBuffer]
0x180001855  cmp     dword ptr [rax], 1
0x180001858  jnb     loc_18009E2AA
0x18000185e  mov     ebx, 0C00000E5h
0x180001863  jmp     short loc_18000182C
0x180001865  lea     rdx, aRng; "RNG"
0x18000186c  jmp     loc_18009E2C6
0x180001871  xor     edx, edx; dwFlags
0x180001873  call    BCryptCloseAlgorithmProvider
0x180001878  jmp     short loc_180001835
0x18000187a  call    BCryptFreeBuffer
0x18000187f  jmp     short loc_18000183E
0x18009e2aa  cmp     cs:g_fLoadCNGDone, 0
0x18009e2b1  jz      loc_180001865
0x18009e2b7  mov     rax, [rbp+pvBuffer]
0x18009e2bb  mov     rcx, [rax+8]
0x18009e2bf  mov     rax, [rcx]
0x18009e2c2  mov     rdx, [rax+8]; pszAlgId
0x18009e2c6  xor     r9d, r9d; dwFlags
0x18009e2c9  lea     rcx, [rbp+hAlgorithm]; phAlgorithm
0x18009e2cd  xor     r8d, r8d; pszImplementation
0x18009e2d0  call    BCryptOpenAlgorithmProvider
0x18009e2d5  mov     ebx, eax
0x18009e2d7  test    eax, eax
0x18009e2d9  jns     short loc_18009E2FC
0x18009e2db  mov     r9d, 188h
0x18009e2e1  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009e2e8  lea     rdx, aStatus; "Status"
0x18009e2ef  mov     ecx, eax
0x18009e2f1  call    DebugTraceError
0x18009e2f6  nop
0x18009e2f7  jmp     loc_18000182C
0x18009e2fc  mov     rax, [rbp+hAlgorithm]
0x18009e300  xor     ebx, ebx
0x18009e302  mov     [rdi], rax
0x18009e305  mov     [rbp+hAlgorithm], 0
0x18009e30d  jmp     loc_18000182C
```
