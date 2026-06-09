# CNG_Decrypt

- ea: `0x180002280`
- end: `0x1800023f0`
- name: `CNG_Decrypt`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002c34`

## callees

- `0x180002280`
- `0x18000d02c`
- `0x18000e120`

## import_xrefs

- `bcrypt!BCryptDecrypt` at `0x18000231a`
- `bcrypt!BCryptDecrypt` at `0x18000231a`

## string_xrefs

- `0x180002371`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x1800023c8`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`

## pseudocode

```c
__int64 __fastcall CNG_Decrypt(__int64 a1, UCHAR *a2, ULONG a3, UCHAR *a4, ULONG cbOutput, ULONG *pcbResult, int a7)
{
  ULONG dwFlags; // r11d
  __int64 v11; // rcx
  UCHAR *pbIV; // rdx
  ULONG cbIV; // r9d
  unsigned int v14; // eax
  unsigned int v15; // ebx
  __int64 v17; // r9
  __int64 v18; // rcx

  dwFlags = 0;
  if ( (*(_DWORD *)(a1 + 112) & 0x10000000) == 0 )
  {
    pbIV = 0;
    cbIV = 0;
    if ( a7 )
      dwFlags = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 72LL);
    goto LABEL_6;
  }
  if ( *(_DWORD *)(a1 + 64) >= 0x98u )
  {
    v11 = *(_QWORD *)(a1 + 72);
    *(_DWORD *)(v11 + 64) = 16;
    *(_QWORD *)(v11 + 56) = v11 + 116;
    if ( a7 )
    {
      if ( !*(_QWORD *)(v11 + 40) )
      {
        if ( a3 < *(_DWORD *)(v11 + 48) )
        {
          v15 = -2146893819;
          v17 = 1238;
          v18 = 2148073477LL;
          goto LABEL_17;
        }
        a3 -= *(_DWORD *)(v11 + 48);
        *(_QWORD *)(v11 + 40) = &a2[a3];
      }
      *(_DWORD *)(v11 + 80) &= ~1u;
    }
    else
    {
      *(_DWORD *)(v11 + 80) |= 1u;
    }
    pbIV = *(UCHAR **)(v11 + 136);
    cbIV = *(_DWORD *)(v11 + 144);
LABEL_6:
    v14 = BCryptDecrypt(
            *(BCRYPT_KEY_HANDLE *)(a1 + 16),
            a2,
            a3,
            *(void **)(a1 + 72),
            pbIV,
            cbIV,
            a4,
            cbOutput,
            pcbResult,
            dwFlags);
    v15 = v14;
    if ( !v14 )
      return v15;
    v17 = 1275;
    v18 = v14;
LABEL_17:
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c", v17);
    return v15;
  }
  v15 = -2146893779;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
      (unsigned int)"Status",
      45,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
      189);
  return v15;
}

```

## disassembly

```asm
0x180002280  mov     [rsp+arg_0], rbx
0x180002285  push    rdi
0x180002286  sub     rsp, 50h
0x18000228a  xor     r11d, r11d
0x18000228d  mov     rdi, r9
0x180002290  test    dword ptr [rcx+70h], 10000000h
0x180002297  mov     rbx, rdx
0x18000229a  mov     r10, rcx
0x18000229d  jz      loc_180002337
0x1800022a3  cmp     dword ptr [rcx+40h], 98h
0x1800022aa  jb      loc_18000234F
0x1800022b0  mov     rcx, [rcx+48h]
0x1800022b4  lea     rax, [rcx+74h]
0x1800022b8  mov     dword ptr [rcx+40h], 10h
0x1800022bf  mov     [rcx+38h], rax
0x1800022c3  cmp     [rsp+58h+arg_30], r11d
0x1800022cb  jnz     loc_18000239B
0x1800022d1  or      dword ptr [rcx+50h], 1
0x1800022d5  mov     rdx, [rcx+88h]
0x1800022dc  mov     r9d, [rcx+90h]
0x1800022e3  mov     rax, [rsp+58h+arg_28]
0x1800022eb  mov     rcx, [r10+10h]; hKey
0x1800022ef  mov     [rsp+58h+dwFlags], r11d; dwFlags
0x1800022f4  mov     [rsp+58h+pcbResult], rax; pcbResult
0x1800022f9  mov     eax, [rsp+58h+arg_20]
0x180002300  mov     [rsp+58h+cbOutput], eax; cbOutput
0x180002304  mov     [rsp+58h+pbOutput], rdi; pbOutput
0x180002309  mov     [rsp+58h+cbIV], r9d; cbIV
0x18000230e  mov     r9, [r10+48h]; pPaddingInfo
0x180002312  mov     [rsp+58h+pbIV], rdx; pbIV
0x180002317  mov     rdx, rbx; pbInput
0x18000231a  call    cs:__imp_BCryptDecrypt
0x180002320  mov     ebx, eax
0x180002322  test    eax, eax
0x180002324  jnz     loc_1800023B9
0x18000232a  mov     eax, ebx
0x18000232c  mov     rbx, [rsp+58h+arg_0]
0x180002331  add     rsp, 50h
0x180002335  pop     rdi
0x180002336  retn
0x180002337  xor     edx, edx
0x180002339  xor     r9d, r9d
0x18000233c  cmp     [rsp+58h+arg_30], edx
0x180002343  jz      short loc_1800022E3
0x180002345  mov     rax, [rcx+18h]
0x180002349  mov     r11d, [rax+48h]
0x18000234d  jmp     short loc_1800022E3
0x18000234f  mov     ebx, 8009002Dh
0x180002354  mov     rcx, cs:WPP_GLOBAL_Control
0x18000235b  lea     rax, WPP_GLOBAL_Control
0x180002362  cmp     rcx, rax
0x180002365  jz      short loc_18000232A
0x180002367  test    byte ptr [rcx+1Ch], 1
0x18000236b  jz      short loc_18000232A
0x18000236d  mov     rcx, [rcx+10h]
0x180002371  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002378  mov     dword ptr [rsp+58h+pbOutput], 4BDh
0x180002380  lea     r9, aStatus; "Status"
0x180002387  mov     qword ptr [rsp+58h+cbIV], r8
0x18000238c  mov     dword ptr [rsp+58h+pbIV], 8009002Dh
0x180002394  call    WPP_SF_sDsd
0x180002399  jmp     short loc_18000232A
0x18000239b  cmp     [rcx+28h], r11
0x18000239f  jnz     short loc_1800023E7
0x1800023a1  cmp     r8d, [rcx+30h]
0x1800023a5  jnb     short loc_1800023D9
0x1800023a7  mov     ebx, 80090005h
0x1800023ac  mov     r9d, 4D6h
0x1800023b2  mov     ecx, 80090005h
0x1800023b7  jmp     short loc_1800023C1
0x1800023b9  mov     r9d, 4FBh
0x1800023bf  mov     ecx, eax
0x1800023c1  lea     rdx, aStatus; "Status"
0x1800023c8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800023cf  call    DebugTraceError
0x1800023d4  jmp     loc_18000232A
0x1800023d9  sub     r8d, [rcx+30h]
0x1800023dd  mov     eax, r8d
0x1800023e0  add     rax, rbx
0x1800023e3  mov     [rcx+28h], rax
0x1800023e7  and     dword ptr [rcx+50h], 0FFFFFFFEh
0x1800023eb  jmp     loc_1800022D5
```
