# WorkbookMakeValidSheetName(x,x,x,x,x)

- ea: `0x1001e2b0`
- end: `0x1001e4a6`
- name: `_WorkbookMakeValidSheetName@20`
- size: `502`
- prototype: `int __fastcall(int, const unsigned __int16 *, int, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1002db68`

## callees

- `0x10006400`
- `0x10018b80`
- `0x1001d4c0`
- `0x1001e2b0`
- `0x10035510`
- `0x10035530`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001e361`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001e361`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001e368`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001e368`

## pseudocode

```c
int __fastcall WorkbookMakeValidSheetName(int a1, const unsigned __int16 *a2, int a3, int a4, int a5)
{
  unsigned __int16 *v5; // ecx
  unsigned int v6; // edi
  int v7; // esi
  const unsigned __int16 *v8; // eax
  unsigned __int16 *v9; // eax
  unsigned int v10; // edi
  int v11; // ebx
  int i; // edi
  _DWORD *v13; // esi
  LCID UserDefaultLCID; // eax
  const unsigned __int16 *v16; // eax
  unsigned __int16 *v17; // ecx
  int v18; // esi
  unsigned __int16 *v19; // eax
  int v20; // ecx
  unsigned int v21; // edx
  unsigned __int16 *v22; // esi
  unsigned int v23; // ecx
  unsigned __int16 *v24; // esi
  unsigned __int16 v25; // ax
  unsigned int v26; // kr04_4
  unsigned int v27; // kr08_4
  int v29; // [esp+14h] [ebp-68h]
  unsigned __int16 v30[31]; // [esp+18h] [ebp-64h] BYREF
  unsigned __int16 v32[16]; // [esp+58h] [ebp-24h] BYREF

  v29 = a1;
  v5 = v30;
  v6 = wcslen(a2) + 1;
  v7 = 32;
  if ( v6 > 0x1F )
    v6 = 31;
  v8 = a2;
  do
  {
    if ( !*v8 )
      break;
    *v5++ = *v8++;
    --v7;
  }
  while ( v7 );
  v9 = v5 - 1;
  if ( v7 )
    v9 = v5;
  v10 = v6;
  *v9 = 0;
  if ( v10 >= 32 )
    __report_rangecheckfailure();
  v11 = 1;
  v30[v10] = 0;
  for ( i = 1; ; i = 2 )
  {
    v13 = *(_DWORD **)(v29 + 80);
    if ( !v13 )
      break;
    while ( 1 )
    {
      UserDefaultLCID = GetUserDefaultLCID();
      if ( DBCompareStringW(UserDefaultLCID, 196609, (char *)v13 + 14, -1, v30, -1) == 2 )
        break;
      v13 = (_DWORD *)*v13;
      if ( !v13 )
        goto LABEL_13;
    }
    v16 = a2;
    v17 = v30;
    v18 = 32;
    do
    {
      if ( !*v16 )
        break;
      *v17++ = *v16++;
      --v18;
    }
    while ( v18 );
    v19 = v17 - 1;
    if ( v18 )
      v19 = v17;
    *v19 = 0;
    if ( v11 >= 0 )
    {
      v20 = 0;
      v21 = v11;
      if ( v11 )
      {
        do
        {
          ++v20;
          v21 /= 0xAu;
        }
        while ( v21 );
        if ( v20 < 16 )
        {
          v22 = &v32[v20];
          v23 = v11;
          *v22 = 0;
          v24 = v22 - 1;
          do
          {
            --v24;
            v25 = byte_10004F00[v23 % 0xA];
            v23 /= 0xAu;
            v24[1] = v25;
          }
          while ( v23 );
        }
      }
      else
      {
        *(_DWORD *)v32 = 48;
      }
    }
    else
    {
      v32[0] = 45;
      DecodeUintW(-v11, 0);
    }
    v26 = wcslen(v30);
    v27 = wcslen(v32);
    if ( (int)(v27 + v26) > 31 )
      v32[-v27] = 0;
    WCSCAT2(32);
    ++v11;
  }
LABEL_13:
  WCSCPY2(32);
  return i;
}

```

## disassembly

```asm
0x1001e2b0  mov     edi, edi
0x1001e2b2  push    ebp
0x1001e2b3  mov     ebp, esp
0x1001e2b5  sub     esp, 70h
0x1001e2b8  mov     eax, ___security_cookie
0x1001e2bd  xor     eax, ebp
0x1001e2bf  mov     [ebp+var_4], eax
0x1001e2c2  mov     eax, [ebp+arg_0]
0x1001e2c5  push    ebx
0x1001e2c6  push    esi
0x1001e2c7  mov     esi, edx
0x1001e2c9  mov     [ebp+var_68], ecx
0x1001e2cc  push    edi
0x1001e2cd  mov     [ebp+var_6C], edx
0x1001e2d0  mov     [ebp+var_70], eax
0x1001e2d3  lea     ecx, [esi+2]
0x1001e2d6  mov     ax, [esi]
0x1001e2d9  add     esi, 2
0x1001e2dc  test    ax, ax
0x1001e2df  jnz     short loc_1001E2D6
0x1001e2e1  sub     esi, ecx
0x1001e2e3  mov     eax, 1Fh
0x1001e2e8  sar     esi, 1
0x1001e2ea  lea     ecx, [ebp+var_64]
0x1001e2ed  lea     edi, [esi+1]
0x1001e2f0  mov     esi, 20h ; ' '
0x1001e2f5  cmp     edi, eax
0x1001e2f7  cmova   edi, eax
0x1001e2fa  mov     eax, edx
0x1001e2fc  nop     dword ptr [eax+00h]
0x1001e300  movzx   edx, word ptr [eax]
0x1001e303  test    dx, dx
0x1001e306  jz      short loc_1001E316
0x1001e308  mov     [ecx], dx
0x1001e30b  add     eax, 2
0x1001e30e  add     ecx, 2
0x1001e311  sub     esi, 1
0x1001e314  jnz     short loc_1001E300
0x1001e316  test    esi, esi
0x1001e318  lea     eax, [ecx-2]
0x1001e31b  cmovnz  eax, ecx
0x1001e31e  xor     ecx, ecx
0x1001e320  add     edi, edi
0x1001e322  mov     [eax], cx
0x1001e325  cmp     edi, 40h ; '@'
0x1001e328  jnb     loc_1001E4A1
0x1001e32e  xor     eax, eax
0x1001e330  mov     ebx, 1
0x1001e335  mov     [ebp+edi+var_64], ax
0x1001e33a  mov     edi, ebx
0x1001e33c  nop     dword ptr [eax+00h]
0x1001e340  mov     eax, [ebp+var_68]
0x1001e343  mov     esi, [eax+50h]
0x1001e346  test    esi, esi
0x1001e348  jz      short loc_1001E379
0x1001e34a  nop     word ptr [eax+eax+00h]
0x1001e350  push    0FFFFFFFFh
0x1001e352  lea     eax, [ebp+var_64]
0x1001e355  push    eax
0x1001e356  push    0FFFFFFFFh
0x1001e358  lea     eax, [esi+0Eh]
0x1001e35b  push    eax
0x1001e35c  push    30001h
0x1001e361  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x1001e367  push    eax
0x1001e368  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x1001e36e  sub     eax, 2
0x1001e371  jz      short loc_1001E39B
0x1001e373  mov     esi, [esi]
0x1001e375  test    esi, esi
0x1001e377  jnz     short loc_1001E350
0x1001e379  mov     ecx, [ebp+var_70]
0x1001e37c  lea     edx, [ebp+var_64]
0x1001e37f  push    20h ; ' '
0x1001e381  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001e386  mov     ecx, [ebp+var_4]
0x1001e389  mov     eax, edi
0x1001e38b  pop     edi
0x1001e38c  pop     esi
0x1001e38d  xor     ecx, ebp; StackCookie
0x1001e38f  pop     ebx
0x1001e390  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001e395  mov     esp, ebp
0x1001e397  pop     ebp
0x1001e398  retn    0Ch
0x1001e39b  mov     eax, [ebp+var_6C]
0x1001e39e  lea     ecx, [ebp+var_64]
0x1001e3a1  mov     esi, 20h ; ' '
0x1001e3a6  movzx   edx, word ptr [eax]
0x1001e3a9  test    dx, dx
0x1001e3ac  jz      short loc_1001E3BC
0x1001e3ae  mov     [ecx], dx
0x1001e3b1  add     eax, 2
0x1001e3b4  add     ecx, 2
0x1001e3b7  sub     esi, 1
0x1001e3ba  jnz     short loc_1001E3A6
0x1001e3bc  test    esi, esi
0x1001e3be  lea     eax, [ecx-2]
0x1001e3c1  cmovnz  eax, ecx
0x1001e3c4  xor     ecx, ecx
0x1001e3c6  mov     [eax], cx
0x1001e3c9  test    ebx, ebx
0x1001e3cb  jns     short loc_1001E3E9
0x1001e3cd  mov     eax, 2Dh ; '-'
0x1001e3d2  lea     edx, [ecx+0Fh]
0x1001e3d5  mov     [ebp+var_24], ax
0x1001e3d9  mov     eax, ebx
0x1001e3db  push    ecx
0x1001e3dc  neg     eax
0x1001e3de  lea     ecx, [ebp+var_24+2]
0x1001e3e1  push    eax
0x1001e3e2  call    _DecodeUintW@16; DecodeUintW(x,x,x,x)
0x1001e3e7  jmp     short loc_1001E44A
0x1001e3e9  xor     ecx, ecx
0x1001e3eb  mov     edx, ebx
0x1001e3ed  test    ebx, ebx
0x1001e3ef  jnz     short loc_1001E400
0x1001e3f1  mov     dword ptr [ebp+var_24], 30h ; '0'
0x1001e3f8  jmp     short loc_1001E44A
0x1001e400  mov     eax, 0CCCCCCCDh
0x1001e405  inc     ecx
0x1001e406  mul     edx
0x1001e408  shr     edx, 3
0x1001e40b  test    edx, edx
0x1001e40d  jnz     short loc_1001E400
0x1001e40f  cmp     ecx, 10h
0x1001e412  jge     short loc_1001E44A
0x1001e414  lea     esi, [ebp+var_24]
0x1001e417  xor     eax, eax
0x1001e419  lea     esi, [esi+ecx*2]
0x1001e41c  mov     ecx, ebx
0x1001e41e  mov     [esi], ax
0x1001e421  sub     esi, 2
0x1001e424  mov     eax, 0CCCCCCCDh
0x1001e429  lea     esi, [esi-2]
0x1001e42c  mul     ecx
0x1001e42e  shr     edx, 3
0x1001e431  lea     eax, [edx+edx*4]
0x1001e434  add     eax, eax
0x1001e436  sub     ecx, eax
0x1001e438  movsx   ax, ds:byte_10004F00[ecx]
0x1001e440  mov     ecx, edx
0x1001e442  mov     [esi+2], ax
0x1001e446  test    ecx, ecx
0x1001e448  jnz     short loc_1001E424
0x1001e44a  lea     edx, [ebp+var_64]
0x1001e44d  lea     ecx, [edx+2]
0x1001e450  mov     ax, [edx]
0x1001e453  add     edx, 2
0x1001e456  test    ax, ax
0x1001e459  jnz     short loc_1001E450
0x1001e45b  sub     edx, ecx
0x1001e45d  lea     ecx, [ebp+var_24]
0x1001e460  sar     edx, 1
0x1001e462  lea     esi, [ecx+2]
0x1001e465  mov     ax, [ecx]
0x1001e468  add     ecx, 2
0x1001e46b  test    ax, ax
0x1001e46e  jnz     short loc_1001E465
0x1001e470  sub     ecx, esi
0x1001e472  sar     ecx, 1
0x1001e474  lea     eax, [ecx+edx]
0x1001e477  cmp     eax, 1Fh
0x1001e47a  jle     short loc_1001E489
0x1001e47c  lea     eax, [ecx+ecx]
0x1001e47f  lea     ecx, [ebp+var_26]
0x1001e482  sub     ecx, eax
0x1001e484  xor     eax, eax
0x1001e486  mov     [ecx], ax
0x1001e489  push    20h ; ' '
0x1001e48b  lea     edx, [ebp+var_24]
0x1001e48e  lea     ecx, [ebp+var_64]
0x1001e491  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1001e496  inc     ebx
0x1001e497  mov     edi, 2
0x1001e49c  jmp     loc_1001E340
0x1001e4a1  call    ___report_rangecheckfailure
```
