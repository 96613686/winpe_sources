# UlInitializeParsing(void)

- ea: `0x1800264fc`
- end: `0x180026887`
- name: `?UlInitializeParsing@@YAJXZ`
- size: `907`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001ea00`

## callees

- `0x1800264fc`
- `0x18002c48e`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x180026861`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180026861`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026566`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026566`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026672`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026672`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800265a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800265f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026646`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800265a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800265f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026646`

## string_xrefs

- `0x18002652c`: `System\CurrentControlSet\Services\http\Parameters`

## pseudocode

```c
__int64 UlInitializeParsing(void)
{
  LSTATUS v0; // eax
  LSTATUS v1; // eax
  LSTATUS v2; // eax
  unsigned int near **v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 i; // rax
  __int64 v7; // rax
  __int64 j; // rcx
  __int64 k; // rcx
  __int64 m; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdi
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  int Data; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  g_UlEnableNonUTF8 = 1;
  g_UlEnableDBCS = 0;
  g_UlFavorDBCS = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\http\\Parameters", 0, 0x20019u, &hKey) )
    goto LABEL_19;
  cbData = 4;
  v0 = RegQueryValueExW(hKey, L"EnableNonUTF8", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v0 || Type != 4 )
  {
    v0 = g_UlEnableNonUTF8;
  }
  else
  {
    LOBYTE(v0) = Data != 0;
    g_UlEnableNonUTF8 = v0;
  }
  cbData = 4;
  if ( !v0 )
  {
    v1 = 0;
    goto LABEL_12;
  }
  v1 = RegQueryValueExW(hKey, L"EnableDBCS", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( !v1 && Type == 4 )
  {
    LOBYTE(v1) = Data != 0;
LABEL_12:
    g_UlEnableDBCS = v1;
    goto LABEL_13;
  }
  v1 = g_UlEnableDBCS;
LABEL_13:
  cbData = 4;
  if ( v1 )
  {
    v2 = RegQueryValueExW(hKey, L"FavorDBCS", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 && Type == 4 )
    {
      LOBYTE(v2) = Data != 0;
      g_UlFavorDBCS = v2;
    }
  }
  else
  {
    g_UlFavorDBCS = 0;
  }
  RegCloseKey(hKey);
LABEL_19:
  v3 = &HttpChars;
  v4 = 128;
  v5 = 65;
  while ( v4 )
  {
    *(_DWORD *)v3 = 1;
    v3 = (unsigned int near **)((char *)v3 + 4);
    --v4;
  }
  for ( i = 65; i != 91; ++i )
    *((_DWORD *)&HttpChars + i) |= 2u;
  v7 = 97;
  for ( j = 97; j != 123; ++j )
    *((_DWORD *)&HttpChars + j) |= 4u;
  for ( k = 48; k != 58; ++k )
    *((_DWORD *)&HttpChars + k) |= 0x48u;
  for ( m = 0; m != 16; m += 2 )
    *(__m128 *)&(&HttpChars)[m] = _mm_or_ps(
                                    (__m128)_mm_load_si128((const __m128i *)&_xmm),
                                    (__m128)_mm_loadu_si128((const __m128i *)&(&HttpChars)[m]));
  dword_18004E2AC |= 0x10u;
  dword_18004E130 |= 0x20u;
  dword_18004E0D4 |= 0x20u;
  do
    *((_DWORD *)&HttpChars + v5++) |= 0x40u;
  while ( v5 != 71 );
  do
    *((_DWORD *)&HttpChars + v7++) |= 0x40u;
  while ( v7 != 103 );
  dword_18004E1A0 |= 0x80u;
  dword_18004E1A8 |= 0x80u;
  dword_18004E130 |= 0x80u;
  dword_18004E0D4 |= 0x80u;
  dword_18004E19C |= 0x280u;
  dword_18004E148 |= 0x200u;
  dword_18004E15C |= 0x200u;
  dword_18004E140 |= 0x200u;
  dword_18004E164 |= 0x200u;
  dword_18004E22C |= 0x200u;
  dword_18004E168 |= 0x200u;
  dword_18004E134 |= 0x200u;
  dword_18004E2A8 |= 0x200u;
  dword_18004E158 |= 0x200u;
  dword_18004E14C |= 0x200u;
  dword_18004E2A0 |= 0x200u;
  dword_18004E228 |= 0x200u;
  dword_18004E230 |= 0x200u;
  dword_18004E13C |= 0x200u;
  dword_18004E144 |= 0x200u;
  dword_18004E16C |= 0x280u;
  dword_18004E220 |= 0x280u;
  dword_18004E1AC |= 0x280u;
  dword_18004E198 |= 0x280u;
  dword_18004E1B0 |= 0x280u;
  dword_18004E1A4 |= 0x280u;
  dword_18004E160 |= 0x280u;
  dword_18004E150 |= 0x280u;
  dword_18004E154 |= 0x280u;
  dword_18004E29C |= 0x280u;
  dword_18004E2A4 |= 0x280u;
  dword_18004E21C |= 0x280u;
  dword_18004E224 |= 0x280u;
  dword_18004E138 |= 0x280u;
  v11 = 0;
  do
  {
    if ( (*((_BYTE *)&HttpChars + 4 * (unsigned __int8)v11) & 0x90) == 0 )
      *((_DWORD *)&HttpChars + v11) |= 0x100u;
    v11 = (unsigned int)(v11 + 1);
  }
  while ( (unsigned int)v11 < 0x80 );
  memset_0(&FastPopChars, 0, 0x200u);
  memset_0(&DummyPopChars, 0, 0x200u);
  v12 = 0;
  do
  {
    if ( (*((_DWORD *)&HttpChars + (unsigned __int8)v12) & 0x20E) != 0 && (_BYTE)v12 != 37 && (v12 & 0x80u) == 0LL )
      *((_WORD *)&FastPopChars + v12) = (unsigned __int8)v12;
    v12 = (unsigned int)(v12 + 1);
  }
  while ( (unsigned int)v12 < 0x100 );
  v13 = 0;
  word_18004DF68 = 47;
  do
  {
    *((_WORD *)&FastUpcaseChars + v13) = RtlUpcaseUnicodeChar(v13);
    v13 = (unsigned int)(v13 + 1);
  }
  while ( (unsigned int)v13 < 0x100 );
  return 0;
}

```

## disassembly

```asm
0x1800264fc  push    rbp
0x1800264fe  push    rsi
0x1800264ff  push    rdi
0x180026500  push    r12
0x180026502  push    r14
0x180026504  mov     rbp, rsp
0x180026507  sub     rsp, 30h
0x18002650b  lea     rax, [rbp+hKey]
0x18002650f  mov     [rbp+hKey], 0
0x180026517  mov     r9d, 20019h; samDesired
0x18002651d  mov     [rsp+30h+phkResult], rax; phkResult
0x180026522  xor     r8d, r8d; ulOptions
0x180026525  mov     [rbp+Type], 0
0x18002652c  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\ht"...
0x180026533  mov     [rbp+Data], 0
0x18002653a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026541  mov     [rbp+cbData], 0
0x180026548  mov     cs:?g_UlEnableNonUTF8@@3HA, 1; int g_UlEnableNonUTF8
0x180026552  mov     cs:?g_UlEnableDBCS@@3HA, 0; int g_UlEnableDBCS
0x18002655c  mov     cs:?g_UlFavorDBCS@@3HA, 0; int g_UlFavorDBCS
0x180026566  call    cs:__imp_RegOpenKeyExW
0x18002656c  mov     r14d, 4
0x180026572  test    eax, eax
0x180026574  jnz     loc_180026678
0x18002657a  mov     rcx, [rbp+hKey]; hKey
0x18002657e  lea     rax, [rbp+cbData]
0x180026582  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180026587  lea     r9, [rbp+Type]; lpType
0x18002658b  lea     rax, [rbp+Data]
0x18002658f  mov     [rbp+cbData], r14d
0x180026593  xor     r8d, r8d; lpReserved
0x180026596  mov     [rsp+30h+phkResult], rax; lpData
0x18002659b  lea     rdx, aEnablenonutf8; "EnableNonUTF8"
0x1800265a2  call    cs:__imp_RegQueryValueExW
0x1800265a8  test    eax, eax
0x1800265aa  jnz     short loc_1800265C0
0x1800265ac  cmp     [rbp+Type], r14d
0x1800265b0  jnz     short loc_1800265C0
0x1800265b2  cmp     [rbp+Data], eax
0x1800265b5  setnz   al
0x1800265b8  mov     cs:?g_UlEnableNonUTF8@@3HA, eax; int g_UlEnableNonUTF8
0x1800265be  jmp     short loc_1800265C6
0x1800265c0  mov     eax, cs:?g_UlEnableNonUTF8@@3HA; int g_UlEnableNonUTF8
0x1800265c6  mov     [rbp+cbData], r14d
0x1800265ca  test    eax, eax
0x1800265cc  jz      short loc_180026612
0x1800265ce  mov     rcx, [rbp+hKey]; hKey
0x1800265d2  lea     rax, [rbp+cbData]
0x1800265d6  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800265db  lea     r9, [rbp+Type]; lpType
0x1800265df  lea     rax, [rbp+Data]
0x1800265e3  xor     r8d, r8d; lpReserved
0x1800265e6  lea     rdx, aEnabledbcs; "EnableDBCS"
0x1800265ed  mov     [rsp+30h+phkResult], rax; lpData
0x1800265f2  call    cs:__imp_RegQueryValueExW
0x1800265f8  test    eax, eax
0x1800265fa  jnz     short loc_18002660A
0x1800265fc  cmp     [rbp+Type], r14d
0x180026600  jnz     short loc_18002660A
0x180026602  cmp     [rbp+Data], eax
0x180026605  setnz   al
0x180026608  jmp     short loc_180026614
0x18002660a  mov     eax, cs:?g_UlEnableDBCS@@3HA; int g_UlEnableDBCS
0x180026610  jmp     short loc_18002661A
0x180026612  xor     eax, eax
0x180026614  mov     cs:?g_UlEnableDBCS@@3HA, eax; int g_UlEnableDBCS
0x18002661a  mov     [rbp+cbData], r14d
0x18002661e  test    eax, eax
0x180026620  jz      short loc_180026664
0x180026622  mov     rcx, [rbp+hKey]; hKey
0x180026626  lea     rax, [rbp+cbData]
0x18002662a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002662f  lea     r9, [rbp+Type]; lpType
0x180026633  lea     rax, [rbp+Data]
0x180026637  xor     r8d, r8d; lpReserved
0x18002663a  lea     rdx, aFavordbcs; "FavorDBCS"
0x180026641  mov     [rsp+30h+phkResult], rax; lpData
0x180026646  call    cs:__imp_RegQueryValueExW
0x18002664c  test    eax, eax
0x18002664e  jnz     short loc_18002666E
0x180026650  cmp     [rbp+Type], r14d
0x180026654  jnz     short loc_18002666E
0x180026656  cmp     [rbp+Data], eax
0x180026659  setnz   al
0x18002665c  mov     cs:?g_UlFavorDBCS@@3HA, eax; int g_UlFavorDBCS
0x180026662  jmp     short loc_18002666E
0x180026664  mov     cs:?g_UlFavorDBCS@@3HA, 0; int g_UlFavorDBCS
0x18002666e  mov     rcx, [rbp+hKey]; hKey
0x180026672  call    cs:__imp_RegCloseKey
0x180026678  mov     eax, 1
0x18002667d  lea     rsi, ?HttpChars@@3PAKA; ulong near * HttpChars
0x180026684  mov     rdi, rsi
0x180026687  lea     r8d, [rax+7Fh]
0x18002668b  mov     ecx, r8d
0x18002668e  lea     edx, [rax+40h]
0x180026691  rep stosd
0x180026693  mov     eax, edx
0x180026695  or      dword ptr [rsi+rax*4], 2
0x180026699  inc     rax
0x18002669c  cmp     rax, 5Bh ; '['
0x1800266a0  jnz     short loc_180026695
0x1800266a2  mov     eax, 61h ; 'a'
0x1800266a7  mov     ecx, eax
0x1800266a9  or      [rsi+rcx*4], r14d
0x1800266ad  inc     rcx
0x1800266b0  cmp     rcx, 7Bh ; '{'
0x1800266b4  jnz     short loc_1800266A9
0x1800266b6  mov     ecx, 30h ; '0'
0x1800266bb  or      dword ptr [rsi+rcx*4], 48h
0x1800266bf  inc     rcx
0x1800266c2  cmp     rcx, 3Ah ; ':'
0x1800266c6  jnz     short loc_1800266BB
0x1800266c8  xor     ecx, ecx
0x1800266ca  movdqu  xmm0, xmmword ptr [rsi+rcx*4]
0x1800266cf  movdqa  xmm1, cs:__xmm@00000010000000100000001000000010
0x1800266d7  orps    xmm1, xmm0
0x1800266da  movdqu  xmmword ptr [rsi+rcx*4], xmm1
0x1800266df  add     rcx, r14
0x1800266e2  cmp     rcx, 20h ; ' '
0x1800266e6  jnz     short loc_1800266CA
0x1800266e8  or      cs:dword_18004E2AC, 10h
0x1800266ef  or      cs:dword_18004E130, ecx
0x1800266f5  or      cs:dword_18004E0D4, ecx
0x1800266fb  or      dword ptr [rsi+rdx*4], 40h
0x1800266ff  inc     rdx
0x180026702  cmp     rdx, 47h ; 'G'
0x180026706  jnz     short loc_1800266FB
0x180026708  or      dword ptr [rsi+rax*4], 40h
0x18002670c  inc     rax
0x18002670f  cmp     rax, 67h ; 'g'
0x180026713  jnz     short loc_180026708
0x180026715  or      cs:dword_18004E1A0, r8d
0x18002671c  mov     eax, 280h
0x180026721  or      cs:dword_18004E1A8, r8d
0x180026728  mov     r14d, 100h
0x18002672e  or      cs:dword_18004E130, r8d
0x180026735  or      cs:dword_18004E0D4, r8d
0x18002673c  or      cs:dword_18004E19C, eax
0x180026742  lea     edi, [rax-80h]
0x180026745  or      cs:dword_18004E148, edi
0x18002674b  or      cs:dword_18004E15C, edi
0x180026751  or      cs:dword_18004E140, edi
0x180026757  or      cs:dword_18004E164, edi
0x18002675d  or      cs:dword_18004E22C, edi
0x180026763  or      cs:dword_18004E168, edi
0x180026769  or      cs:dword_18004E134, edi
0x18002676f  or      cs:dword_18004E2A8, edi
0x180026775  or      cs:dword_18004E158, edi
0x18002677b  or      cs:dword_18004E14C, edi
0x180026781  or      cs:dword_18004E2A0, edi
0x180026787  or      cs:dword_18004E228, edi
0x18002678d  or      cs:dword_18004E230, edi
0x180026793  or      cs:dword_18004E13C, edi
0x180026799  or      cs:dword_18004E144, edi
0x18002679f  or      cs:dword_18004E16C, eax
0x1800267a5  or      cs:dword_18004E220, eax
0x1800267ab  or      cs:dword_18004E1AC, eax
0x1800267b1  or      cs:dword_18004E198, eax
0x1800267b7  or      cs:dword_18004E1B0, eax
0x1800267bd  or      cs:dword_18004E1A4, eax
0x1800267c3  or      cs:dword_18004E160, eax
0x1800267c9  or      cs:dword_18004E150, eax
0x1800267cf  or      cs:dword_18004E154, eax
0x1800267d5  or      cs:dword_18004E29C, eax
0x1800267db  or      cs:dword_18004E2A4, eax
0x1800267e1  or      cs:dword_18004E21C, eax
0x1800267e7  or      cs:dword_18004E224, eax
0x1800267ed  or      cs:dword_18004E138, eax
0x1800267f3  xor     ecx, ecx
0x1800267f5  movzx   eax, cl
0x1800267f8  test    byte ptr [rsi+rax*4], 90h
0x1800267fc  jnz     short loc_180026802
0x1800267fe  or      [rsi+rcx*4], r14d
0x180026802  inc     ecx
0x180026804  cmp     ecx, r8d
0x180026807  jb      short loc_1800267F5
0x180026809  lea     r12, ?FastPopChars@@3PAGA; ushort near * FastPopChars
0x180026810  mov     r8, rdi; Size
0x180026813  mov     rcx, r12; void *
0x180026816  xor     edx, edx; Val
0x180026818  call    memset_0
0x18002681d  mov     r8, rdi; Size
0x180026820  lea     rcx, ?DummyPopChars@@3PAGA; void *
0x180026827  xor     edx, edx; Val
0x180026829  call    memset_0
0x18002682e  xor     edx, edx
0x180026830  movzx   eax, dl
0x180026833  test    dword ptr [rsi+rax*4], 20Eh
0x18002683a  jz      short loc_180026849
0x18002683c  cmp     al, 25h ; '%'
0x18002683e  jz      short loc_180026849
0x180026840  test    al, al
0x180026842  js      short loc_180026849
0x180026844  mov     [r12+rdx*2], ax
0x180026849  inc     edx
0x18002684b  cmp     edx, r14d
0x18002684e  jb      short loc_180026830
0x180026850  mov     eax, 2Fh ; '/'
0x180026855  xor     edi, edi
0x180026857  mov     cs:word_18004DF68, ax
0x18002685e  movzx   ecx, di; Source
0x180026861  call    cs:__imp_RtlUpcaseUnicodeChar
0x180026867  lea     rdx, ?FastUpcaseChars@@3PAGA; ushort near * FastUpcaseChars
0x18002686e  mov     [rdx+rdi*2], ax
0x180026872  inc     edi
0x180026874  cmp     edi, r14d
0x180026877  jb      short loc_18002685E
0x180026879  xor     eax, eax
0x18002687b  add     rsp, 30h
0x18002687f  pop     r14
0x180026881  pop     r12
0x180026883  pop     rdi
0x180026884  pop     rsi
0x180026885  pop     rbp
0x180026886  retn
```
