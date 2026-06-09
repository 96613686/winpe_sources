# acmdDriverDetails

- ea: `0x180002310`
- end: `0x18000245a`
- name: `acmdDriverDetails`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800020b0`

## callees

- `0x180001400`
- `0x180001caa`
- `0x180002310`
- `0x180005019`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800023ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800023c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800023e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002402`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000241e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800023ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800023c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800023e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002402`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000241e`

## pseudocode

```c
__int64 __fastcall acmdDriverDetails(__int64 a1, int *a2)
{
  int v4; // edi
  bool v5; // cf
  unsigned int Src; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+24h] [rbp-DCh]
  int v9; // [rsp+2Ch] [rbp-D4h]
  int v10; // [rsp+30h] [rbp-D0h]
  int v11; // [rsp+34h] [rbp-CCh]
  int v12; // [rsp+38h] [rbp-C8h]
  __int64 v13; // [rsp+3Ch] [rbp-C4h]
  __int64 v14; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR Buffer[32]; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR v16[128]; // [rsp+8Ch] [rbp-74h] BYREF
  WCHAR v17[80]; // [rsp+18Ch] [rbp+8Ch] BYREF
  WCHAR v18[128]; // [rsp+22Ch] [rbp+12Ch] BYREF
  WCHAR v19[514]; // [rsp+32Ch] [rbp+22Ch] BYREF

  memset_0(&v14, 0, 0x6E8u);
  v4 = 1804;
  v8 = 1667528033;
  v5 = (unsigned int)*a2 < 0x70C;
  v9 = 2228225;
  if ( v5 )
    v4 = *a2;
  Src = v4;
  v10 = 53608448;
  v11 = 0x4000000;
  v13 = 2;
  v12 = 1;
  if ( v4 > 36 )
  {
    v14 = 0;
    LoadStringW(*(HINSTANCE *)(a1 + 20), 1u, Buffer, 32);
    LoadStringW(*(HINSTANCE *)(a1 + 20), 2u, v16, 128);
    if ( v4 > 364 )
    {
      LoadStringW(*(HINSTANCE *)(a1 + 20), 3u, v17, 80);
      LoadStringW(*(HINSTANCE *)(a1 + 20), 4u, v18, 128);
      LoadStringW(*(HINSTANCE *)(a1 + 20), 5u, v19, 512);
    }
  }
  memcpy_0(a2, &Src, Src);
  return 0;
}

```

## disassembly

```asm
0x180002310  mov     [rsp-8+arg_10], rbx
0x180002315  push    rbp
0x180002316  push    rsi
0x180002317  push    rdi
0x180002318  lea     rbp, [rsp-640h]
0x180002320  sub     rsp, 740h
0x180002327  mov     rax, cs:__security_cookie
0x18000232e  xor     rax, rsp
0x180002331  mov     [rbp+650h+var_20], rax
0x180002338  mov     rsi, rdx
0x18000233b  mov     rbx, rcx
0x18000233e  xor     edx, edx; Val
0x180002340  lea     rcx, [rsp+750h+var_70C]; void *
0x180002345  mov     r8d, 6E8h; Size
0x18000234b  call    memset_0
0x180002350  mov     edi, 70Ch
0x180002355  mov     [rsp+750h+var_72C], 63647561h
0x18000235e  cmp     [rsi], edi
0x180002360  mov     [rsp+750h+var_724], 220001h
0x180002368  cmovb   edi, [rsi]
0x18000236b  xor     ecx, ecx
0x18000236d  mov     [rsp+750h+Src], edi
0x180002371  mov     [rsp+750h+var_720], 3320000h
0x180002379  mov     [rsp+750h+var_71C], 4000000h
0x180002381  mov     [rsp+750h+var_714], 2
0x18000238a  lea     edx, [rcx+1]; uID
0x18000238d  mov     [rsp+750h+var_718], edx
0x180002391  cmp     edi, 24h ; '$'
0x180002394  jle     loc_180002424
0x18000239a  mov     [rsp+750h+var_70C], rcx
0x18000239f  lea     r9d, [rcx+20h]; cchBufferMax
0x1800023a3  mov     rcx, [rbx+14h]; hInstance
0x1800023a7  lea     r8, [rsp+750h+Buffer]; lpBuffer
0x1800023ac  call    cs:__imp_LoadStringW
0x1800023b2  mov     rcx, [rbx+14h]; hInstance
0x1800023b6  lea     r8, [rbp+650h+var_6C4]; lpBuffer
0x1800023ba  mov     r9d, 80h; cchBufferMax
0x1800023c0  lea     edx, [r9-7Eh]; uID
0x1800023c4  call    cs:__imp_LoadStringW
0x1800023ca  cmp     edi, 16Ch
0x1800023d0  jle     short loc_180002424
0x1800023d2  mov     rcx, [rbx+14h]; hInstance
0x1800023d6  lea     r8, [rbp+650h+var_5C4]; lpBuffer
0x1800023dd  mov     r9d, 50h ; 'P'; cchBufferMax
0x1800023e3  lea     edx, [r9-4Dh]; uID
0x1800023e7  call    cs:__imp_LoadStringW
0x1800023ed  mov     rcx, [rbx+14h]; hInstance
0x1800023f1  lea     r8, [rbp+650h+var_524]; lpBuffer
0x1800023f8  mov     r9d, 80h; cchBufferMax
0x1800023fe  lea     edx, [r9-7Ch]; uID
0x180002402  call    cs:__imp_LoadStringW
0x180002408  mov     rcx, [rbx+14h]; hInstance
0x18000240c  lea     r8, [rbp+650h+var_424]; lpBuffer
0x180002413  mov     r9d, 200h; cchBufferMax
0x180002419  mov     edx, 5; uID
0x18000241e  call    cs:__imp_LoadStringW
0x180002424  mov     r8d, [rsp+750h+Src]; Size
0x180002429  lea     rdx, [rsp+750h+Src]; Src
0x18000242e  mov     rcx, rsi; void *
0x180002431  call    memcpy_0
0x180002436  xor     eax, eax
0x180002438  mov     rcx, [rbp+650h+var_20]
0x18000243f  xor     rcx, rsp; StackCookie
0x180002442  call    __security_check_cookie
0x180002447  mov     rbx, [rsp+750h+arg_10]
0x18000244f  add     rsp, 740h
0x180002456  pop     rdi
0x180002457  pop     rsi
0x180002458  pop     rbp
0x180002459  retn
```
