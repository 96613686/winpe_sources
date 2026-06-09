# UlInitializeParsing(void)

- ea: `0x1800280f4`
- end: `0x1800284a4`
- name: `?UlInitializeParsing@@YAJXZ`
- size: `944`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001fbd0`

## callees

- `0x1800280f4`
- `0x18002e52e`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x180028477`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180028477`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002815e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002815e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028282`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028282`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800281a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800281f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028250`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800281a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800281f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028250`

## string_xrefs

- `0x180028124`: `System\CurrentControlSet\Services\http\Parameters`

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
  dword_1800502AC |= 0x10u;
  dword_180050130 |= 0x20u;
  dword_1800500D4 |= 0x20u;
  do
    *((_DWORD *)&HttpChars + v5++) |= 0x40u;
  while ( v5 != 71 );
  do
    *((_DWORD *)&HttpChars + v7++) |= 0x40u;
  while ( v7 != 103 );
  dword_1800501A0 |= 0x80u;
  dword_1800501A8 |= 0x80u;
  dword_180050130 |= 0x80u;
  dword_1800500D4 |= 0x80u;
  dword_18005019C |= 0x280u;
  dword_180050148 |= 0x200u;
  dword_18005015C |= 0x200u;
  dword_180050140 |= 0x200u;
  dword_180050164 |= 0x200u;
  dword_18005022C |= 0x200u;
  dword_180050168 |= 0x200u;
  dword_180050134 |= 0x200u;
  dword_1800502A8 |= 0x200u;
  dword_180050158 |= 0x200u;
  dword_18005014C |= 0x200u;
  dword_1800502A0 |= 0x200u;
  dword_180050228 |= 0x200u;
  dword_180050230 |= 0x200u;
  dword_18005013C |= 0x200u;
  dword_180050144 |= 0x200u;
  dword_18005016C |= 0x280u;
  dword_180050220 |= 0x280u;
  dword_1800501AC |= 0x280u;
  dword_180050198 |= 0x280u;
  dword_1800501B0 |= 0x280u;
  dword_1800501A4 |= 0x280u;
  dword_180050160 |= 0x280u;
  dword_180050150 |= 0x280u;
  dword_180050154 |= 0x280u;
  dword_18005029C |= 0x280u;
  dword_1800502A4 |= 0x280u;
  dword_18005021C |= 0x280u;
  dword_180050224 |= 0x280u;
  dword_180050138 |= 0x280u;
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
  word_18004FF68 = 47;
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
0x1800280f4  push    rbp
0x1800280f6  push    rsi
0x1800280f7  push    rdi
0x1800280f8  push    r12
0x1800280fa  push    r14
0x1800280fc  mov     rbp, rsp
0x1800280ff  sub     rsp, 30h
0x180028103  lea     rax, [rbp+hKey]
0x180028107  mov     [rbp+hKey], 0
0x18002810f  mov     r9d, 20019h; samDesired
0x180028115  mov     [rsp+30h+phkResult], rax; phkResult
0x18002811a  xor     r8d, r8d; ulOptions
0x18002811d  mov     [rbp+Type], 0
0x180028124  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\ht"...
0x18002812b  mov     [rbp+Data], 0
0x180028132  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028139  mov     [rbp+cbData], 0
0x180028140  mov     cs:?g_UlEnableNonUTF8@@3HA, 1; int g_UlEnableNonUTF8
0x18002814a  mov     cs:?g_UlEnableDBCS@@3HA, 0; int g_UlEnableDBCS
0x180028154  mov     cs:?g_UlFavorDBCS@@3HA, 0; int g_UlFavorDBCS
0x18002815e  call    cs:__imp_RegOpenKeyExW
0x180028165  nop     dword ptr [rax+rax+00h]
0x18002816a  mov     r14d, 4
0x180028170  test    eax, eax
0x180028172  jnz     loc_18002828E
0x180028178  mov     rcx, [rbp+hKey]; hKey
0x18002817c  lea     rax, [rbp+cbData]
0x180028180  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180028185  lea     r9, [rbp+Type]; lpType
0x180028189  lea     rax, [rbp+Data]
0x18002818d  mov     [rbp+cbData], r14d
0x180028191  xor     r8d, r8d; lpReserved
0x180028194  mov     [rsp+30h+phkResult], rax; lpData
0x180028199  lea     rdx, aEnablenonutf8; "EnableNonUTF8"
0x1800281a0  call    cs:__imp_RegQueryValueExW
0x1800281a7  nop     dword ptr [rax+rax+00h]
0x1800281ac  test    eax, eax
0x1800281ae  jnz     short loc_1800281C4
0x1800281b0  cmp     [rbp+Type], r14d
0x1800281b4  jnz     short loc_1800281C4
0x1800281b6  cmp     [rbp+Data], eax
0x1800281b9  setnz   al
0x1800281bc  mov     cs:?g_UlEnableNonUTF8@@3HA, eax; int g_UlEnableNonUTF8
0x1800281c2  jmp     short loc_1800281CA
0x1800281c4  mov     eax, cs:?g_UlEnableNonUTF8@@3HA; int g_UlEnableNonUTF8
0x1800281ca  mov     [rbp+cbData], r14d
0x1800281ce  test    eax, eax
0x1800281d0  jz      short loc_18002821C
0x1800281d2  mov     rcx, [rbp+hKey]; hKey
0x1800281d6  lea     rax, [rbp+cbData]
0x1800281da  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800281df  lea     r9, [rbp+Type]; lpType
0x1800281e3  lea     rax, [rbp+Data]
0x1800281e7  xor     r8d, r8d; lpReserved
0x1800281ea  lea     rdx, aEnabledbcs; "EnableDBCS"
0x1800281f1  mov     [rsp+30h+phkResult], rax; lpData
0x1800281f6  call    cs:__imp_RegQueryValueExW
0x1800281fd  nop     dword ptr [rax+rax+00h]
0x180028202  test    eax, eax
0x180028204  jnz     short loc_180028214
0x180028206  cmp     [rbp+Type], r14d
0x18002820a  jnz     short loc_180028214
0x18002820c  cmp     [rbp+Data], eax
0x18002820f  setnz   al
0x180028212  jmp     short loc_18002821E
0x180028214  mov     eax, cs:?g_UlEnableDBCS@@3HA; int g_UlEnableDBCS
0x18002821a  jmp     short loc_180028224
0x18002821c  xor     eax, eax
0x18002821e  mov     cs:?g_UlEnableDBCS@@3HA, eax; int g_UlEnableDBCS
0x180028224  mov     [rbp+cbData], r14d
0x180028228  test    eax, eax
0x18002822a  jz      short loc_180028274
0x18002822c  mov     rcx, [rbp+hKey]; hKey
0x180028230  lea     rax, [rbp+cbData]
0x180028234  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180028239  lea     r9, [rbp+Type]; lpType
0x18002823d  lea     rax, [rbp+Data]
0x180028241  xor     r8d, r8d; lpReserved
0x180028244  lea     rdx, aFavordbcs; "FavorDBCS"
0x18002824b  mov     [rsp+30h+phkResult], rax; lpData
0x180028250  call    cs:__imp_RegQueryValueExW
0x180028257  nop     dword ptr [rax+rax+00h]
0x18002825c  test    eax, eax
0x18002825e  jnz     short loc_18002827E
0x180028260  cmp     [rbp+Type], r14d
0x180028264  jnz     short loc_18002827E
0x180028266  cmp     [rbp+Data], eax
0x180028269  setnz   al
0x18002826c  mov     cs:?g_UlFavorDBCS@@3HA, eax; int g_UlFavorDBCS
0x180028272  jmp     short loc_18002827E
0x180028274  mov     cs:?g_UlFavorDBCS@@3HA, 0; int g_UlFavorDBCS
0x18002827e  mov     rcx, [rbp+hKey]; hKey
0x180028282  call    cs:__imp_RegCloseKey
0x180028289  nop     dword ptr [rax+rax+00h]
0x18002828e  mov     eax, 1
0x180028293  lea     rsi, ?HttpChars@@3PAKA; ulong near * HttpChars
0x18002829a  mov     rdi, rsi
0x18002829d  lea     r8d, [rax+7Fh]
0x1800282a1  mov     ecx, r8d
0x1800282a4  lea     edx, [rax+40h]
0x1800282a7  rep stosd
0x1800282a9  mov     eax, edx
0x1800282ab  or      dword ptr [rsi+rax*4], 2
0x1800282af  inc     rax
0x1800282b2  cmp     rax, 5Bh ; '['
0x1800282b6  jnz     short loc_1800282AB
0x1800282b8  mov     eax, 61h ; 'a'
0x1800282bd  mov     ecx, eax
0x1800282bf  or      [rsi+rcx*4], r14d
0x1800282c3  inc     rcx
0x1800282c6  cmp     rcx, 7Bh ; '{'
0x1800282ca  jnz     short loc_1800282BF
0x1800282cc  mov     ecx, 30h ; '0'
0x1800282d1  or      dword ptr [rsi+rcx*4], 48h
0x1800282d5  inc     rcx
0x1800282d8  cmp     rcx, 3Ah ; ':'
0x1800282dc  jnz     short loc_1800282D1
0x1800282de  xor     ecx, ecx
0x1800282e0  movdqu  xmm0, xmmword ptr [rsi+rcx*4]
0x1800282e5  movdqa  xmm1, cs:__xmm@00000010000000100000001000000010
0x1800282ed  orps    xmm1, xmm0
0x1800282f0  movdqu  xmmword ptr [rsi+rcx*4], xmm1
0x1800282f5  add     rcx, r14
0x1800282f8  cmp     rcx, 20h ; ' '
0x1800282fc  jnz     short loc_1800282E0
0x1800282fe  or      cs:dword_1800502AC, 10h
0x180028305  or      cs:dword_180050130, ecx
0x18002830b  or      cs:dword_1800500D4, ecx
0x180028311  or      dword ptr [rsi+rdx*4], 40h
0x180028315  inc     rdx
0x180028318  cmp     rdx, 47h ; 'G'
0x18002831c  jnz     short loc_180028311
0x18002831e  or      dword ptr [rsi+rax*4], 40h
0x180028322  inc     rax
0x180028325  cmp     rax, 67h ; 'g'
0x180028329  jnz     short loc_18002831E
0x18002832b  or      cs:dword_1800501A0, r8d
0x180028332  mov     eax, 280h
0x180028337  or      cs:dword_1800501A8, r8d
0x18002833e  mov     r14d, 100h
0x180028344  or      cs:dword_180050130, r8d
0x18002834b  or      cs:dword_1800500D4, r8d
0x180028352  or      cs:dword_18005019C, eax
0x180028358  lea     edi, [rax-80h]
0x18002835b  or      cs:dword_180050148, edi
0x180028361  or      cs:dword_18005015C, edi
0x180028367  or      cs:dword_180050140, edi
0x18002836d  or      cs:dword_180050164, edi
0x180028373  or      cs:dword_18005022C, edi
0x180028379  or      cs:dword_180050168, edi
0x18002837f  or      cs:dword_180050134, edi
0x180028385  or      cs:dword_1800502A8, edi
0x18002838b  or      cs:dword_180050158, edi
0x180028391  or      cs:dword_18005014C, edi
0x180028397  or      cs:dword_1800502A0, edi
0x18002839d  or      cs:dword_180050228, edi
0x1800283a3  or      cs:dword_180050230, edi
0x1800283a9  or      cs:dword_18005013C, edi
0x1800283af  or      cs:dword_180050144, edi
0x1800283b5  or      cs:dword_18005016C, eax
0x1800283bb  or      cs:dword_180050220, eax
0x1800283c1  or      cs:dword_1800501AC, eax
0x1800283c7  or      cs:dword_180050198, eax
0x1800283cd  or      cs:dword_1800501B0, eax
0x1800283d3  or      cs:dword_1800501A4, eax
0x1800283d9  or      cs:dword_180050160, eax
0x1800283df  or      cs:dword_180050150, eax
0x1800283e5  or      cs:dword_180050154, eax
0x1800283eb  or      cs:dword_18005029C, eax
0x1800283f1  or      cs:dword_1800502A4, eax
0x1800283f7  or      cs:dword_18005021C, eax
0x1800283fd  or      cs:dword_180050224, eax
0x180028403  or      cs:dword_180050138, eax
0x180028409  xor     ecx, ecx
0x18002840b  movzx   eax, cl
0x18002840e  test    byte ptr [rsi+rax*4], 90h
0x180028412  jnz     short loc_180028418
0x180028414  or      [rsi+rcx*4], r14d
0x180028418  inc     ecx
0x18002841a  cmp     ecx, r8d
0x18002841d  jb      short loc_18002840B
0x18002841f  lea     r12, ?FastPopChars@@3PAGA; ushort near * FastPopChars
0x180028426  mov     r8, rdi; Size
0x180028429  mov     rcx, r12; void *
0x18002842c  xor     edx, edx; Val
0x18002842e  call    memset_0
0x180028433  mov     r8, rdi; Size
0x180028436  lea     rcx, ?DummyPopChars@@3PAGA; void *
0x18002843d  xor     edx, edx; Val
0x18002843f  call    memset_0
0x180028444  xor     edx, edx
0x180028446  movzx   eax, dl
0x180028449  test    dword ptr [rsi+rax*4], 20Eh
0x180028450  jz      short loc_18002845F
0x180028452  cmp     al, 25h ; '%'
0x180028454  jz      short loc_18002845F
0x180028456  test    al, al
0x180028458  js      short loc_18002845F
0x18002845a  mov     [r12+rdx*2], ax
0x18002845f  inc     edx
0x180028461  cmp     edx, r14d
0x180028464  jb      short loc_180028446
0x180028466  mov     eax, 2Fh ; '/'
0x18002846b  xor     edi, edi
0x18002846d  mov     cs:word_18004FF68, ax
0x180028474  movzx   ecx, di; Source
0x180028477  call    cs:__imp_RtlUpcaseUnicodeChar
0x18002847e  nop     dword ptr [rax+rax+00h]
0x180028483  lea     rdx, ?FastUpcaseChars@@3PAGA; ushort near * FastUpcaseChars
0x18002848a  mov     [rdx+rdi*2], ax
0x18002848e  inc     edi
0x180028490  cmp     edi, r14d
0x180028493  jb      short loc_180028474
0x180028495  xor     eax, eax
0x180028497  add     rsp, 30h
0x18002849b  pop     r14
0x18002849d  pop     r12
0x18002849f  pop     rdi
0x1800284a0  pop     rsi
0x1800284a1  pop     rbp
0x1800284a2  retn
```
