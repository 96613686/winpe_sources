# acmdDriverDetails

- ea: `0x180002334`
- end: `0x180002480`
- name: `acmdDriverDetails`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800020d0`

## callees

- `0x180001400`
- `0x180001cca`
- `0x180002334`
- `0x180006479`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800023d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800023ea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000240d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002428`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002444`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800023d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800023ea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000240d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002428`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002444`

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
  v9 = 2359297;
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
0x180002334  mov     [rsp-8+arg_10], rbx
0x180002339  push    rbp
0x18000233a  push    rsi
0x18000233b  push    rdi
0x18000233c  lea     rbp, [rsp-640h]
0x180002344  sub     rsp, 740h
0x18000234b  mov     rax, cs:__security_cookie
0x180002352  xor     rax, rsp
0x180002355  mov     [rbp+650h+var_20], rax
0x18000235c  mov     rsi, rdx
0x18000235f  mov     rbx, rcx
0x180002362  xor     edx, edx; Val
0x180002364  lea     rcx, [rsp+750h+var_70C]; void *
0x180002369  mov     r8d, 6E8h; Size
0x18000236f  call    memset_0
0x180002374  mov     edi, 70Ch
0x180002379  mov     [rsp+750h+var_72C], 63647561h
0x180002382  cmp     [rsi], edi
0x180002384  mov     [rsp+750h+var_724], 240001h
0x18000238c  cmovb   edi, [rsi]
0x18000238f  xor     ecx, ecx
0x180002391  mov     [rsp+750h+Src], edi
0x180002395  mov     [rsp+750h+var_720], 3320000h
0x18000239d  mov     [rsp+750h+var_71C], 4000000h
0x1800023a5  lea     eax, [rcx+24h]
0x1800023a8  mov     [rsp+750h+var_714], 2
0x1800023b1  lea     edx, [rcx+1]; uID
0x1800023b4  mov     [rsp+750h+var_718], edx
0x1800023b8  cmp     edi, eax
0x1800023ba  jle     loc_18000244A
0x1800023c0  mov     [rsp+750h+var_70C], rcx
0x1800023c5  lea     r9d, [rcx+20h]; cchBufferMax
0x1800023c9  mov     rcx, [rbx+14h]; hInstance
0x1800023cd  lea     r8, [rsp+750h+Buffer]; lpBuffer
0x1800023d2  call    cs:__imp_LoadStringW
0x1800023d8  mov     rcx, [rbx+14h]; hInstance
0x1800023dc  lea     r8, [rbp+650h+var_6C4]; lpBuffer
0x1800023e0  mov     r9d, 80h; cchBufferMax
0x1800023e6  lea     edx, [r9-7Eh]; uID
0x1800023ea  call    cs:__imp_LoadStringW
0x1800023f0  cmp     edi, 16Ch
0x1800023f6  jle     short loc_18000244A
0x1800023f8  mov     rcx, [rbx+14h]; hInstance
0x1800023fc  lea     r8, [rbp+650h+var_5C4]; lpBuffer
0x180002403  mov     r9d, 50h ; 'P'; cchBufferMax
0x180002409  lea     edx, [r9-4Dh]; uID
0x18000240d  call    cs:__imp_LoadStringW
0x180002413  mov     rcx, [rbx+14h]; hInstance
0x180002417  lea     r8, [rbp+650h+var_524]; lpBuffer
0x18000241e  mov     r9d, 80h; cchBufferMax
0x180002424  lea     edx, [r9-7Ch]; uID
0x180002428  call    cs:__imp_LoadStringW
0x18000242e  mov     rcx, [rbx+14h]; hInstance
0x180002432  lea     r8, [rbp+650h+var_424]; lpBuffer
0x180002439  mov     r9d, 200h; cchBufferMax
0x18000243f  mov     edx, 5; uID
0x180002444  call    cs:__imp_LoadStringW
0x18000244a  mov     r8d, [rsp+750h+Src]; Size
0x18000244f  lea     rdx, [rsp+750h+Src]; Src
0x180002454  mov     rcx, rsi; void *
0x180002457  call    memcpy_0
0x18000245c  xor     eax, eax
0x18000245e  mov     rcx, [rbp+650h+var_20]
0x180002465  xor     rcx, rsp; StackCookie
0x180002468  call    __security_check_cookie
0x18000246d  mov     rbx, [rsp+750h+arg_10]
0x180002475  add     rsp, 740h
0x18000247c  pop     rdi
0x18000247d  pop     rsi
0x18000247e  pop     rbp
0x18000247f  retn
```
