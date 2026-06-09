# OpenSystemPreferredAlgorithmProvider

- ea: `0x18000b898`
- end: `0x18000b9a9`
- name: `OpenSystemPreferredAlgorithmProvider`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000b7d8`
- `0x18000e204`

## callees

- `0x18000b898`
- `0x18000c500`
- `0x18001155c`
- `0x1800123d0`
- `0x180032c70`
- `0x18004b4c0`
- `0x18004eaa0`

## string_xrefs

- `0x18000b930`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x1800a507f`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

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
0x18000b898  mov     r11, rsp
0x18000b89b  mov     [r11+8], rbx
0x18000b89f  mov     [r11+10h], rdi
0x18000b8a3  mov     [r11+20h], r9d
0x18000b8a7  mov     [r11+18h], r8
0x18000b8ab  push    rbp
0x18000b8ac  mov     rbp, rsp
0x18000b8af  sub     rsp, 50h
0x18000b8b3  cmp     cs:g_fLoadCNGDone, 0
0x18000b8ba  mov     rdi, rcx
0x18000b8bd  mov     [rbp+hAlgorithm], 0
0x18000b8c5  mov     [rbp+pvBuffer], 0
0x18000b8cd  mov     [rbp+arg_18], 0
0x18000b8d4  jz      loc_18000B98D
0x18000b8da  lea     rax, [rbp+pvBuffer]
0x18000b8de  xor     r9d, r9d; pszProvider
0x18000b8e1  mov     [r11-20h], rax
0x18000b8e5  xor     r8d, r8d; pszFunction
0x18000b8e8  lea     rax, [rbp+arg_18]
0x18000b8ec  xor     ecx, ecx; pszContext
0x18000b8ee  mov     [r11-28h], rax
0x18000b8f2  mov     [rsp+50h+dwFlags], 0; dwFlags
0x18000b8fa  lea     edx, [r9+6]; dwInterface
0x18000b8fe  mov     [rsp+50h+dwMode], 2; dwMode
0x18000b906  call    BCryptResolveProviders
0x18000b90b  mov     ebx, eax
0x18000b90d  test    eax, eax
0x18000b90f  jns     short loc_18000B979
0x18000b911  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b918  lea     rax, WPP_GLOBAL_Control
0x18000b91f  cmp     rcx, rax
0x18000b922  jz      short loc_18000B954
0x18000b924  mov     edx, [rcx+2Ch]
0x18000b927  test    dl, 1
0x18000b92a  jz      short loc_18000B954
0x18000b92c  mov     rcx, [rcx+18h]
0x18000b930  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b937  mov     [rsp+50h+var_20], 16Dh
0x18000b93f  lea     r9, aStatus; "Status"
0x18000b946  mov     qword ptr [rsp+50h+dwFlags], r8
0x18000b94b  mov     [rsp+50h+dwMode], ebx
0x18000b94f  call    WPP_SF_sDsd
0x18000b954  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18000b958  test    rcx, rcx
0x18000b95b  jnz     short loc_18000B999
0x18000b95d  mov     rcx, [rbp+pvBuffer]; pvBuffer
0x18000b961  test    rcx, rcx
0x18000b964  jnz     short loc_18000B9A2
0x18000b966  mov     rdi, [rsp+50h+arg_8]
0x18000b96b  mov     eax, ebx
0x18000b96d  mov     rbx, [rsp+50h+arg_0]
0x18000b972  add     rsp, 50h
0x18000b976  pop     rbp
0x18000b977  retn
0x18000b979  mov     rax, [rbp+pvBuffer]
0x18000b97d  cmp     dword ptr [rax], 1
0x18000b980  jnb     loc_1800A5048
0x18000b986  mov     ebx, 0C00000E5h
0x18000b98b  jmp     short loc_18000B954
0x18000b98d  lea     rdx, aRng; "RNG"
0x18000b994  jmp     loc_1800A5064
0x18000b999  xor     edx, edx; dwFlags
0x18000b99b  call    BCryptCloseAlgorithmProvider
0x18000b9a0  jmp     short loc_18000B95D
0x18000b9a2  call    BCryptFreeBuffer
0x18000b9a7  jmp     short loc_18000B966
0x1800a5048  cmp     cs:g_fLoadCNGDone, 0
0x1800a504f  jz      loc_18000B98D
0x1800a5055  mov     rax, [rbp+pvBuffer]
0x1800a5059  mov     rcx, [rax+8]
0x1800a505d  mov     rax, [rcx]
0x1800a5060  mov     rdx, [rax+8]; pszAlgId
0x1800a5064  xor     r9d, r9d; dwFlags
0x1800a5067  lea     rcx, [rbp+hAlgorithm]; phAlgorithm
0x1800a506b  xor     r8d, r8d; pszImplementation
0x1800a506e  call    BCryptOpenAlgorithmProvider
0x1800a5073  mov     ebx, eax
0x1800a5075  test    eax, eax
0x1800a5077  jns     short loc_1800A509A
0x1800a5079  mov     r9d, 188h
0x1800a507f  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a5086  lea     rdx, aStatus; "Status"
0x1800a508d  mov     ecx, eax
0x1800a508f  call    DebugTraceError
0x1800a5094  nop
0x1800a5095  jmp     loc_18000B954
0x1800a509a  mov     rax, [rbp+hAlgorithm]
0x1800a509e  xor     ebx, ebx
0x1800a50a0  mov     [rdi], rax
0x1800a50a3  mov     [rbp+hAlgorithm], 0
0x1800a50ab  jmp     loc_18000B954
```
