# DeviceLinkFill

- ea: `0x18001e1ec`
- end: `0x18001e558`
- name: `DeviceLinkFill`
- size: `876`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int **, int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18001d680`

## callees

- `0x1800042e0`
- `0x180017cf4`
- `0x180017e74`
- `0x180017efc`
- `0x180018b28`
- `0x18001e1ec`
- `0x18001e6ac`
- `0x18001e708`
- `0x18001e818`
- `0x18001e97c`
- `0x18001edd4`
- `0x18003cff6`
- `0x18003d002`
- `0x18003d040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4d7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001e4c0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001e4c0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001e2e0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001e2e0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001e2ce`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001e2ce`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001e2c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001e2d7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001e2c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001e2d7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001e4c9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001e4c9`

## pseudocode

```c
__int64 __fastcall DeviceLinkFill(__int64 a1, __int64 a2, unsigned int **a3, int a4)
{
  __int64 v8; // rdi
  unsigned int *v9; // rsi
  DWORD ColorSpaces; // ebx
  HGLOBAL v11; // rax
  HGLOBAL v12; // rax
  __int64 result; // rax
  __int64 v14; // rax
  unsigned int v15; // r8d
  int v16; // edx
  signed int v17; // ebx
  unsigned int Sizes; // eax
  unsigned int v19; // r14d
  HGLOBAL v20; // rax
  unsigned int *v21; // rax
  size_t v22; // r12
  char *v23; // rdx
  DWORD v24; // eax
  __int16 v25[2]; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v26; // [rsp+34h] [rbp-65h] BYREF
  int v27; // [rsp+38h] [rbp-61h] BYREF
  int v28; // [rsp+3Ch] [rbp-5Dh] BYREF
  unsigned int v29; // [rsp+40h] [rbp-59h] BYREF
  _DWORD v30[4]; // [rsp+48h] [rbp-51h] BYREF
  char v31; // [rsp+58h] [rbp-41h] BYREF
  char v32[32]; // [rsp+59h] [rbp-40h] BYREF
  __int64 Src; // [rsp+79h] [rbp-20h] BYREF
  __int128 v34; // [rsp+81h] [rbp-18h]
  char v35[31]; // [rsp+91h] [rbp-8h] BYREF

  strcpy(v32, "DeviceLink profile     ");
  v25[0] = -4;
  Src = 0x622036393931A9C2LL;
  v31 = 24;
  v34 = *(_OWORD *)"y Heidelberger Druckmaschinen AG  U.J.K.";
  v32[31] = 48;
  v8 = 0;
  *a3 = 0;
  v9 = 0;
  strcpy(v35, "ruckmaschinen AG  U.J.K.");
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v30[0] = 63189;
  v30[1] = 0x10000;
  v30[2] = 54060;
  if ( *(_DWORD *)(a1 + 328) )
  {
    ColorSpaces = 2011;
  }
  else
  {
    ColorSpaces = MyGetColorSpaces(a2, &v28, &v27);
    if ( !ColorSpaces )
    {
      v14 = SmartNewPtrClear(3000, v25);
      ColorSpaces = v25[0];
      v8 = v14;
      if ( !v25[0] )
      {
        ColorSpaces = MyAdd_NL_Header(0, v14, a4, 1818848875, v28, v27);
        if ( !ColorSpaces )
        {
          *(_DWORD *)(v8 + 128) = 83886080;
          *(_DWORD *)(v8 + 132) = 1668506980;
          *(_DWORD *)(v8 + 136) = -1073741824;
          *(_DWORD *)(v8 + 140) = 1912602624;
          ColorSpaces = MyAdd_NL_DescriptionTag(v8 + 192, &v31);
          if ( !ColorSpaces )
          {
            *(_DWORD *)(v8 + 144) = 1953526903;
            *(_DWORD *)(v8 + 148) = 872480768;
            *(_DWORD *)(v8 + 152) = 335544320;
            MyAdd_NL_ColorantTag(v8 + 308, v30);
            *(_DWORD *)(v8 + 156) = 1953656931;
            *(_DWORD *)(v8 + 160) = 1208025088;
            *(_DWORD *)(v8 + 164) = 939524096;
            v35[23] = 0;
            *(_QWORD *)(v8 + 328) = 1954047348;
            memcpy_0((void *)(v8 + 336), &Src, 0x30u);
            MyAdd_NL_SequenceDescTag(a2, v8 + 384, 2616, &v29);
            v15 = v29;
            v16 = v29 & 0xFF0000;
            *(_DWORD *)(v8 + 168) = 1902474096;
            *(_DWORD *)(v8 + 172) = -2147418112;
            v17 = (v15 + 387) & 0xFFFFFFFC;
            *(_DWORD *)(v8 + 176) = ((v15 & 0xFF00 | (v15 << 16)) << 8) | ((unsigned int)(HIWORD(v15) | v16) >> 8);
            Sizes = GetSizes(a1, &v26);
            *(_DWORD *)(v8 + 180) = 809644609;
            *(_DWORD *)(v8 + 184) = _byteswap_ulong(v17);
            v19 = v17 + Sizes;
            *(_DWORD *)(v8 + 188) = _byteswap_ulong(Sizes);
            v20 = GlobalAlloc(0x42u, (int)(v17 + Sizes));
            v21 = (unsigned int *)GlobalLock(v20);
            v9 = v21;
            if ( v21 )
            {
              v22 = v17;
              v23 = (char *)v21 + v17;
              if ( *(_DWORD *)(a1 + 60) == 8 )
                v24 = MyAdd_NL_AToB0Tag_mft1(a1, v23, v26);
              else
                v24 = MyAdd_NL_AToB0Tag_mft2(a1, v23, v26);
              ColorSpaces = v24;
              if ( !v24 )
              {
                memmove_0(v9, (const void *)v8, v22);
                DisposeIfPtr(v8);
                *v9 = (v19 << 24) | (v19 << 8) & 0xFF0000 | ((HIWORD(v19) | v19 & 0xFF0000) >> 8);
                result = 0;
                *a3 = v9;
                return result;
              }
            }
            else
            {
              ColorSpaces = GetLastError();
            }
          }
        }
      }
    }
  }
  *a3 = (unsigned int *)DisposeIfPtr(v8);
  if ( v9 )
  {
    v11 = GlobalHandle(v9);
    GlobalUnlock(v11);
    v12 = GlobalHandle(v9);
    GlobalFree(v12);
  }
  return ColorSpaces;
}

```

## disassembly

```asm
0x18001e1ec  mov     [rsp-8+arg_18], rbx
0x18001e1f1  push    rbp
0x18001e1f2  push    rsi
0x18001e1f3  push    rdi
0x18001e1f4  push    r12
0x18001e1f6  push    r13
0x18001e1f8  push    r14
0x18001e1fa  push    r15
0x18001e1fc  lea     rbp, [rsp-27h]
0x18001e201  sub     rsp, 0C0h
0x18001e208  mov     rax, cs:__security_cookie
0x18001e20f  xor     rax, rsp
0x18001e212  mov     [rbp+57h+var_40], rax
0x18001e216  movups  xmm0, cs:xmmword_18003F819
0x18001e21d  mov     eax, 0FFFFFFFCh
0x18001e222  mov     r12d, r9d
0x18001e225  movsd   xmm1, cs:qword_18003F829
0x18001e22d  mov     r13, r8
0x18001e230  movups  xmmword ptr [rbp+57h+var_97], xmm0
0x18001e234  mov     [rbp+57h+var_C0], ax
0x18001e238  mov     rax, 622036393931A9C2h
0x18001e242  movups  xmm0, xmmword ptr cs:a01996ByHeidelb+9; "y Heidelberger Druckmaschinen AG  U.J.K"...
0x18001e249  mov     r14, rdx
0x18001e24c  mov     [rbp+57h+Src], rax
0x18001e250  xor     eax, eax
0x18001e252  movsd   qword ptr [rbp+57h+var_97+10h], xmm1
0x18001e257  movups  xmm1, xmmword ptr cs:a01996ByHeidelb+19h; "ruckmaschinen AG  U.J.K."
0x18001e25e  mov     r15, rcx
0x18001e261  mov     [rbp+57h+var_98], 18h
0x18001e265  movups  [rbp+57h+var_6F], xmm0
0x18001e269  mov     [rbp+57h+var_78], 30h ; '0'
0x18001e26d  mov     edi, eax
0x18001e26f  movups  xmm0, xmmword ptr cs:a01996ByHeidelb+22h; "inen AG  U.J.K."
0x18001e276  mov     [r8], rax
0x18001e279  mov     esi, eax
0x18001e27b  movups  xmmword ptr [rbp+57h+var_5F], xmm1
0x18001e27f  mov     [rbp+57h+var_B0], eax
0x18001e282  movups  xmmword ptr [rbp+57h+var_5F+9], xmm0
0x18001e286  mov     [rbp+57h+var_B4], eax
0x18001e289  mov     [rbp+57h+var_B8], eax
0x18001e28c  mov     [rbp+57h+var_BC], eax
0x18001e28f  mov     [rbp+57h+var_A8], 0F6D5h
0x18001e296  mov     [rbp+57h+var_A4], 10000h
0x18001e29d  mov     [rbp+57h+var_A0], 0D32Ch
0x18001e2a4  cmp     [rcx+148h], eax
0x18001e2aa  jz      short loc_18001E30F
0x18001e2ac  mov     ebx, 7DBh
0x18001e2b1  mov     rcx, rdi
0x18001e2b4  call    DisposeIfPtr
0x18001e2b9  mov     [r13+0], rax
0x18001e2bd  test    rsi, rsi
0x18001e2c0  jz      short loc_18001E2E6
0x18001e2c2  mov     rcx, rsi; pMem
0x18001e2c5  call    cs:__imp_GlobalHandle
0x18001e2cb  mov     rcx, rax; hMem
0x18001e2ce  call    cs:__imp_GlobalUnlock
0x18001e2d4  mov     rcx, rsi; pMem
0x18001e2d7  call    cs:__imp_GlobalHandle
0x18001e2dd  mov     rcx, rax; hMem
0x18001e2e0  call    cs:__imp_GlobalFree
0x18001e2e6  mov     eax, ebx
0x18001e2e8  mov     rcx, [rbp+57h+var_40]
0x18001e2ec  xor     rcx, rsp; StackCookie
0x18001e2ef  call    __security_check_cookie
0x18001e2f4  mov     rbx, [rsp+0F0h+arg_18]
0x18001e2fc  add     rsp, 0C0h
0x18001e303  pop     r15
0x18001e305  pop     r14
0x18001e307  pop     r13
0x18001e309  pop     r12
0x18001e30b  pop     rdi
0x18001e30c  pop     rsi
0x18001e30d  pop     rbp
0x18001e30e  retn
0x18001e30f  lea     r8, [rbp+57h+var_B8]
0x18001e313  mov     rcx, r14
0x18001e316  lea     rdx, [rbp+57h+var_B4]
0x18001e31a  call    MyGetColorSpaces
0x18001e31f  mov     ebx, eax
0x18001e321  test    eax, eax
0x18001e323  jnz     short loc_18001E2B1
0x18001e325  lea     rdx, [rbp+57h+var_C0]
0x18001e329  mov     ecx, 0BB8h
0x18001e32e  call    SmartNewPtrClear
0x18001e333  movsx   ebx, [rbp+57h+var_C0]
0x18001e337  mov     rdi, rax
0x18001e33a  test    ebx, ebx
0x18001e33c  jnz     loc_18001E2B1
0x18001e342  mov     ecx, [rbp+57h+var_B8]
0x18001e345  mov     r9d, 6C696E6Bh
0x18001e34b  mov     [rsp+0F0h+var_C8], ecx
0x18001e34f  mov     r8d, r12d
0x18001e352  mov     ecx, [rbp+57h+var_B4]
0x18001e355  mov     rdx, rax
0x18001e358  mov     [rsp+0F0h+var_D0], ecx
0x18001e35c  xor     ecx, ecx
0x18001e35e  call    MyAdd_NL_Header
0x18001e363  mov     ebx, eax
0x18001e365  test    eax, eax
0x18001e367  jnz     loc_18001E2B1
0x18001e36d  mov     dword ptr [rdi+80h], 5000000h
0x18001e377  lea     rcx, [rdi+0C0h]
0x18001e37e  mov     dword ptr [rdi+84h], 63736564h
0x18001e388  lea     rdx, [rbp+57h+var_98]
0x18001e38c  mov     dword ptr [rdi+88h], 0C0000000h
0x18001e396  mov     dword ptr [rdi+8Ch], 72000000h
0x18001e3a0  call    MyAdd_NL_DescriptionTag
0x18001e3a5  mov     ebx, eax
0x18001e3a7  test    eax, eax
0x18001e3a9  jnz     loc_18001E2B1
0x18001e3af  mov     dword ptr [rdi+90h], 74707477h
0x18001e3b9  lea     rcx, [rdi+134h]
0x18001e3c0  mov     dword ptr [rdi+94h], 34010000h
0x18001e3ca  lea     rdx, [rbp+57h+var_A8]
0x18001e3ce  mov     dword ptr [rdi+98h], 14000000h
0x18001e3d8  call    MyAdd_NL_ColorantTag
0x18001e3dd  mov     dword ptr [rdi+9Ch], 74727063h
0x18001e3e7  lea     rcx, [rdi+150h]; void *
0x18001e3ee  mov     dword ptr [rdi+0A0h], 48010000h
0x18001e3f8  lea     rdx, [rbp+57h+Src]; Src
0x18001e3fc  mov     dword ptr [rdi+0A4h], 38000000h
0x18001e406  mov     al, 30h ; '0'
0x18001e408  movzx   r8d, al; Size
0x18001e40c  mov     [rbp+57h+var_5F+17h], sil
0x18001e410  mov     qword ptr [rdi+148h], 74786574h
0x18001e41b  call    memcpy_0
0x18001e420  lea     rdx, [rdi+180h]
0x18001e427  mov     r8d, 0A38h
0x18001e42d  lea     r9, [rbp+57h+var_B0]
0x18001e431  mov     rcx, r14
0x18001e434  call    MyAdd_NL_SequenceDescTag
0x18001e439  mov     r8d, [rbp+57h+var_B0]
0x18001e43d  mov     edx, r8d
0x18001e440  and     edx, 0FF0000h
0x18001e446  mov     dword ptr [rdi+0A8h], 71657370h
0x18001e450  mov     ecx, r8d
0x18001e453  mov     dword ptr [rdi+0ACh], 80010000h
0x18001e45d  shl     ecx, 10h
0x18001e460  mov     eax, r8d
0x18001e463  shr     eax, 10h
0x18001e466  lea     ebx, [r8+183h]
0x18001e46d  or      edx, eax
0x18001e46f  and     ebx, 0FFFFFFFCh
0x18001e472  mov     eax, r8d
0x18001e475  shr     edx, 8
0x18001e478  and     eax, 0FF00h
0x18001e47d  or      ecx, eax
0x18001e47f  shl     ecx, 8
0x18001e482  or      edx, ecx
0x18001e484  mov     rcx, r15
0x18001e487  mov     [rdi+0B0h], edx
0x18001e48d  lea     rdx, [rbp+57h+var_BC]
0x18001e491  call    GetSizes
0x18001e496  mov     dword ptr [rdi+0B4h], 30423241h
0x18001e4a0  mov     ecx, ebx
0x18001e4a2  bswap   ecx
0x18001e4a4  mov     [rdi+0B8h], ecx
0x18001e4aa  mov     ecx, eax
0x18001e4ac  bswap   ecx
0x18001e4ae  lea     r14d, [rbx+rax]
0x18001e4b2  mov     [rdi+0BCh], ecx
0x18001e4b8  mov     ecx, 42h ; 'B'; uFlags
0x18001e4bd  movsxd  rdx, r14d; dwBytes
0x18001e4c0  call    cs:__imp_GlobalAlloc
0x18001e4c6  mov     rcx, rax; hMem
0x18001e4c9  call    cs:__imp_GlobalLock
0x18001e4cf  mov     rsi, rax
0x18001e4d2  test    rax, rax
0x18001e4d5  jnz     short loc_18001E4E4
0x18001e4d7  call    cs:__imp_GetLastError
0x18001e4dd  mov     ebx, eax
0x18001e4df  jmp     loc_18001E2B1
0x18001e4e4  cmp     dword ptr [r15+3Ch], 8
0x18001e4e9  mov     rcx, r15
0x18001e4ec  mov     r8d, [rbp+57h+var_BC]
0x18001e4f0  movsxd  r12, ebx
0x18001e4f3  lea     rdx, [r12+rax]
0x18001e4f7  jnz     short loc_18001E500
0x18001e4f9  call    MyAdd_NL_AToB0Tag_mft1
0x18001e4fe  jmp     short loc_18001E505
0x18001e500  call    MyAdd_NL_AToB0Tag_mft2
0x18001e505  mov     ebx, eax
0x18001e507  test    eax, eax
0x18001e509  jnz     loc_18001E2B1
0x18001e50f  mov     r8, r12; Size
0x18001e512  mov     rdx, rdi; Src
0x18001e515  mov     rcx, rsi; void *
0x18001e518  call    memmove_0
0x18001e51d  mov     rcx, rdi
0x18001e520  call    DisposeIfPtr
0x18001e525  mov     ecx, r14d
0x18001e528  mov     edx, 0FF0000h
0x18001e52d  and     ecx, edx
0x18001e52f  mov     eax, r14d
0x18001e532  shr     eax, 10h
0x18001e535  or      ecx, eax
0x18001e537  mov     eax, r14d
0x18001e53a  shr     ecx, 8
0x18001e53d  shl     eax, 8
0x18001e540  and     eax, edx
0x18001e542  shl     r14d, 18h
0x18001e546  or      ecx, eax
0x18001e548  or      ecx, r14d
0x18001e54b  mov     [rsi], ecx
0x18001e54d  xor     eax, eax
0x18001e54f  mov     [r13+0], rsi
0x18001e553  jmp     loc_18001E2E8
```
