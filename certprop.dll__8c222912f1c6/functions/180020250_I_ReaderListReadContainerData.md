# I_ReaderListReadContainerData

- ea: `0x180020250`
- end: `0x1800205bb`
- name: `I_ReaderListReadContainerData`
- size: `875`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001fdfc`

## callees

- `0x180004600`
- `0x18000a980`
- `0x18000b010`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x180020250`
- `0x1800205c4`
- `0x180024380`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020432`
- `ADVAPI32!CryptAcquireContextW` at `0x180020427`
- `ADVAPI32!CryptAcquireContextW` at `0x180020427`
- `ADVAPI32!CryptReleaseContext` at `0x180020506`
- `ADVAPI32!CryptReleaseContext` at `0x180020506`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadContainerData(__int64 a1, __int64 *a2, __int64 a3, _DWORD *a4)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdx
  wchar_t *p_phProv; // rbx
  size_t v13; // r15
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  unsigned __int64 v19; // rcx
  wchar_t *v20; // rax
  DWORD LastError; // edi
  __int64 v22; // rcx
  STRSAFE_LPSTR v23; // rcx
  int v24; // edx
  DWORD ContainerDataPerKeyType; // eax
  __int64 v26; // rcx
  HCRYPTPROV v27; // rcx
  __int64 v29; // [rsp+0h] [rbp-30h] BYREF
  DWORD dwFlags[4]; // [rsp+20h] [rbp-10h]
  HCRYPTPROV phProv; // [rsp+30h] [rbp+0h] BYREF
  __int64 v32; // [rsp+38h] [rbp+8h] BYREF

  phProv = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  v8 = -1;
  v9 = -1;
  v10 = 0;
  do
    ++v9;
  while ( *(_WORD *)(a3 + 2 * v9) );
  v11 = *a2;
  do
    ++v8;
  while ( *(_WORD *)(v11 + 2 * v8) );
  p_phProv = 0;
  v13 = v8 + v9 + 6;
  v14 = 2 * v13;
  if ( 2 * v13 )
  {
    if ( v14 <= g_ulMaxStackAllocSize )
    {
      v15 = v14 + g_ulAdditionalProbeSize + 8;
      if ( v15 >= v14 )
      {
        if ( (unsigned int)VerifyStackAvailable(v15, v11, 0) )
        {
          v16 = v14 + 23;
          if ( v14 + 23 <= v14 + 8 )
            v16 = 0xFFFFFFFFFFFFFF0LL;
          v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
          v18 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
          p_phProv = (wchar_t *)&phProv;
          if ( &v29 != (__int64 *)-48LL )
          {
            LODWORD(phProv) = 1801679955;
            p_phProv = (wchar_t *)&v32;
            if ( &v32 )
              goto LABEL_25;
          }
        }
      }
    }
  }
  v19 = v14 + 8;
  if ( v14 + 8 < v14 )
  {
LABEL_20:
    if ( !p_phProv )
      goto LABEL_21;
LABEL_25:
    if ( StringCchPrintfW(p_phProv, v13, L"\\\\.\\%s\\%s", *a2, a3) < 0 )
    {
      LastError = 122;
      goto LABEL_38;
    }
    if ( !CryptAcquireContextW(&phProv, p_phProv, (LPCWSTR)a2[10], *((_DWORD *)a2 + 30), 0x40u) )
    {
      LastError = GetLastError();
      WppTraceIndent(v22, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_38;
      }
      v24 = 83;
      dwFlags[0] = LastError;
      goto LABEL_32;
    }
    if ( *(_DWORD *)(a1 + 16) )
    {
      ContainerDataPerKeyType = I_ReaderListReadContainerDataPerKeyType(a1, a2, phProv, a3, 2);
      LastError = ContainerDataPerKeyType;
      if ( ContainerDataPerKeyType )
      {
        if ( ContainerDataPerKeyType == 8 )
        {
          WppTraceIndent(v26, 2);
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[28] & 1) == 0
            || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
          {
            goto LABEL_38;
          }
          v24 = 84;
          dwFlags[0] = 8;
LABEL_32:
          WPP_SF_sD(
            *((_QWORD *)v23 + 2),
            v24,
            (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent,
            dwFlags[0]);
          goto LABEL_38;
        }
      }
      else
      {
        ++*a4;
      }
    }
    LastError = I_ReaderListReadContainerDataPerKeyType(a1, a2, phProv, a3, 1);
    if ( !LastError )
      ++*a4;
    goto LABEL_38;
  }
  v20 = (wchar_t *)((__int64 (__fastcall *)(unsigned __int64, __int64, __int64))g_pfnAllocate)(v19, v11, v10);
  p_phProv = v20;
  if ( v20 )
  {
    *(_DWORD *)v20 = 1885431112;
    p_phProv = v20 + 4;
    goto LABEL_20;
  }
LABEL_21:
  WppTraceIndent(v19, 2);
  LastError = 8;
  if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control )
    goto LABEL_41;
  if ( (WPP_GLOBAL_Control[28] & 1) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
LABEL_38:
  if ( p_phProv && *((_DWORD *)p_phProv - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_41:
  v27 = phProv;
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  WppTraceIndent(v27, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180020250  push    rbp
0x180020252  push    rbx
0x180020253  push    rsi
0x180020254  push    rdi
0x180020255  push    r12
0x180020257  push    r13
0x180020259  push    r14
0x18002025b  push    r15
0x18002025d  sub     rsp, 58h
0x180020261  lea     rbp, [rsp+30h]
0x180020266  mov     rax, cs:__security_cookie
0x18002026d  xor     rax, rbp
0x180020270  mov     [rbp+60h+var_50], rax
0x180020274  mov     r14, rdx
0x180020277  xor     r15d, r15d
0x18002027a  xor     edx, edx
0x18002027c  mov     [rbp+60h+phProv], r15
0x180020280  mov     rsi, r9
0x180020283  mov     r12, r8
0x180020286  mov     r13, rcx
0x180020289  call    WppTraceIndent
0x18002028e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020295  lea     rax, WPP_GLOBAL_Control
0x18002029c  cmp     rcx, rax
0x18002029f  jz      short loc_1800202C8
0x1800202a1  test    byte ptr [rcx+1Ch], 2
0x1800202a5  jz      short loc_1800202C8
0x1800202a7  cmp     byte ptr [rcx+19h], 5
0x1800202ab  jb      short loc_1800202C8
0x1800202ad  mov     r9, cs:WPP_pszIndent
0x1800202b4  lea     edx, [r15+51h]
0x1800202b8  mov     rcx, [rcx+10h]
0x1800202bc  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800202c3  call    WPP_SF_s
0x1800202c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800202cc  mov     rcx, rax
0x1800202cf  xor     r8d, r8d
0x1800202d2  inc     rcx
0x1800202d5  cmp     [r12+rcx*2], r8w
0x1800202da  jnz     short loc_1800202D2
0x1800202dc  mov     rdx, [r14]
0x1800202df  inc     rax
0x1800202e2  cmp     [rdx+rax*2], r8w
0x1800202e7  jnz     short loc_1800202DF
0x1800202e9  lea     r15, [rcx+6]
0x1800202ed  mov     rbx, r8
0x1800202f0  add     r15, rax
0x1800202f3  lea     rdi, [r15+r15]
0x1800202f7  test    rdi, rdi
0x1800202fa  jz      short loc_180020361
0x1800202fc  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180020303  ja      short loc_180020361
0x180020305  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002030c  add     rcx, 8
0x180020310  add     rcx, rdi
0x180020313  cmp     rcx, rdi
0x180020316  jb      short loc_180020361
0x180020318  call    VerifyStackAvailable
0x18002031d  test    eax, eax
0x18002031f  jz      short loc_180020361
0x180020321  lea     rax, [rdi+8]
0x180020325  lea     rcx, [rax+0Fh]
0x180020329  cmp     rcx, rax
0x18002032c  ja      short loc_180020338
0x18002032e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180020338  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002033c  mov     rax, rcx
0x18002033f  call    _alloca_probe
0x180020344  sub     rsp, rcx
0x180020347  lea     rbx, [rsp+90h+phProv]
0x18002034c  test    rbx, rbx
0x18002034f  jz      short loc_180020361
0x180020351  mov     dword ptr [rbx], 6B637453h
0x180020357  add     rbx, 8
0x18002035b  jnz     loc_1800203E6
0x180020361  lea     rcx, [rdi+8]
0x180020365  cmp     rcx, rdi
0x180020368  jb      short loc_180020388
0x18002036a  mov     rax, cs:g_pfnAllocate
0x180020371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020376  mov     rbx, rax
0x180020379  test    rax, rax
0x18002037c  jz      short loc_18002038D
0x18002037e  mov     dword ptr [rax], 70616548h
0x180020384  add     rbx, 8
0x180020388  test    rbx, rbx
0x18002038b  jnz     short loc_1800203E6
0x18002038d  mov     edx, 2
0x180020392  call    WppTraceIndent
0x180020397  mov     edi, 8
0x18002039c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203a3  lea     rsi, WPP_GLOBAL_Control
0x1800203aa  cmp     rcx, rsi
0x1800203ad  jz      loc_1800204FB
0x1800203b3  test    byte ptr [rcx+1Ch], 1
0x1800203b7  jz      loc_1800204DE
0x1800203bd  cmp     byte ptr [rcx+19h], 2
0x1800203c1  jb      loc_1800204DE
0x1800203c7  mov     r9, cs:WPP_pszIndent
0x1800203ce  lea     edx, [rdi+4Ah]
0x1800203d1  mov     rcx, [rcx+10h]
0x1800203d5  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800203dc  call    WPP_SF_s
0x1800203e1  jmp     loc_1800204DE
0x1800203e6  mov     r9, [r14]
0x1800203e9  lea     r8, aSS_0; "\\\\.\\%s\\%s"
0x1800203f0  mov     rdx, r15; cchDest
0x1800203f3  mov     qword ptr [rsp+90h+dwFlags], r12
0x1800203f8  mov     rcx, rbx; pszDest
0x1800203fb  call    StringCchPrintfW
0x180020400  xor     r15d, r15d
0x180020403  test    eax, eax
0x180020405  jns     short loc_180020410
0x180020407  lea     edi, [r15+7Ah]
0x18002040b  jmp     loc_1800204D7
0x180020410  mov     r9d, [r14+78h]; dwProvType
0x180020414  lea     rcx, [rbp+60h+phProv]; phProv
0x180020418  mov     r8, [r14+50h]; szProvider
0x18002041c  mov     rdx, rbx; szContainer
0x18002041f  mov     [rsp+90h+dwFlags], 40h ; '@'; dwFlags
0x180020427  call    cs:__imp_CryptAcquireContextW
0x18002042d  cmp     eax, 1
0x180020430  jz      short loc_180020489
0x180020432  call    cs:__imp_GetLastError
0x180020438  mov     edx, 2
0x18002043d  mov     edi, eax
0x18002043f  call    WppTraceIndent
0x180020444  mov     rcx, cs:WPP_GLOBAL_Control
0x18002044b  lea     rsi, WPP_GLOBAL_Control
0x180020452  cmp     rcx, rsi
0x180020455  jz      loc_1800204DE
0x18002045b  test    byte ptr [rcx+1Ch], 1
0x18002045f  jz      short loc_1800204DE
0x180020461  cmp     byte ptr [rcx+19h], 2
0x180020465  jb      short loc_1800204DE
0x180020467  mov     edx, 53h ; 'S'
0x18002046c  mov     [rsp+90h+dwFlags], edi
0x180020470  mov     r9, cs:WPP_pszIndent
0x180020477  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18002047e  mov     rcx, [rcx+10h]
0x180020482  call    WPP_SF_sD
0x180020487  jmp     short loc_1800204DE
0x180020489  cmp     [r13+10h], r15d
0x18002048d  jz      short loc_1800204B5
0x18002048f  mov     r8, [rbp+60h+phProv]
0x180020493  mov     r9, r12
0x180020496  mov     rdx, r14
0x180020499  mov     [rsp+90h+dwFlags], 2
0x1800204a1  mov     rcx, r13
0x1800204a4  call    I_ReaderListReadContainerDataPerKeyType
0x1800204a9  mov     edi, eax
0x1800204ab  test    eax, eax
0x1800204ad  jnz     loc_18002056D
0x1800204b3  inc     dword ptr [rsi]
0x1800204b5  mov     r8, [rbp+60h+phProv]
0x1800204b9  mov     r9, r12
0x1800204bc  mov     rdx, r14
0x1800204bf  mov     [rsp+90h+dwFlags], 1
0x1800204c7  mov     rcx, r13
0x1800204ca  call    I_ReaderListReadContainerDataPerKeyType
0x1800204cf  mov     edi, eax
0x1800204d1  test    eax, eax
0x1800204d3  jnz     short loc_1800204D7
0x1800204d5  inc     dword ptr [rsi]
0x1800204d7  lea     rsi, WPP_GLOBAL_Control
0x1800204de  test    rbx, rbx
0x1800204e1  jz      short loc_1800204FB
0x1800204e3  lea     rcx, [rbx-8]
0x1800204e7  cmp     dword ptr [rcx], 70616548h
0x1800204ed  jnz     short loc_1800204FB
0x1800204ef  mov     rax, cs:g_pfnFree
0x1800204f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204fb  mov     rcx, [rbp+60h+phProv]; hProv
0x1800204ff  test    rcx, rcx
0x180020502  jz      short loc_18002050C
0x180020504  xor     edx, edx; dwFlags
0x180020506  call    cs:__imp_CryptReleaseContext
0x18002050c  mov     edx, 1
0x180020511  call    WppTraceIndent
0x180020516  mov     rcx, cs:WPP_GLOBAL_Control
0x18002051d  cmp     rcx, rsi
0x180020520  jz      short loc_18002054E
0x180020522  test    byte ptr [rcx+1Ch], 2
0x180020526  jz      short loc_18002054E
0x180020528  cmp     byte ptr [rcx+19h], 5
0x18002052c  jb      short loc_18002054E
0x18002052e  mov     r9, cs:WPP_pszIndent
0x180020535  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18002053c  mov     rcx, [rcx+10h]
0x180020540  mov     edx, 55h ; 'U'
0x180020545  mov     [rsp+90h+dwFlags], edi
0x180020549  call    WPP_SF_sD
0x18002054e  mov     eax, edi
0x180020550  mov     rcx, [rbp+60h+var_50]
0x180020554  xor     rcx, rbp; StackCookie
0x180020557  call    __security_check_cookie
0x18002055c  lea     rsp, [rbp+28h]
0x180020560  pop     r15
0x180020562  pop     r14
0x180020564  pop     r13
0x180020566  pop     r12
0x180020568  pop     rdi
0x180020569  pop     rsi
0x18002056a  pop     rbx
0x18002056b  pop     rbp
0x18002056c  retn
0x18002056d  cmp     eax, 8
0x180020570  jnz     loc_1800204B5
0x180020576  lea     edx, [rax-6]
0x180020579  call    WppTraceIndent
0x18002057e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020585  lea     rsi, WPP_GLOBAL_Control
0x18002058c  cmp     rcx, rsi
0x18002058f  jz      loc_1800204DE
0x180020595  test    byte ptr [rcx+1Ch], 1
0x180020599  jz      loc_1800204DE
0x18002059f  cmp     byte ptr [rcx+19h], 2
0x1800205a3  jb      loc_1800204DE
0x1800205a9  mov     edx, 54h ; 'T'
0x1800205ae  mov     [rsp+90h+dwFlags], 8
0x1800205b6  jmp     loc_180020470
```
