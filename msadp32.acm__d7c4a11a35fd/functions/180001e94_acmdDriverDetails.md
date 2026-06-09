# acmdDriverDetails

- ea: `0x180001e94`
- end: `0x180001fde`
- name: `acmdDriverDetails`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001cd0`

## callees

- `0x180001400`
- `0x180001c9e`
- `0x180001e94`
- `0x180005355`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001f30`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001f48`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001f6b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001f86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001fa2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001f30`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001f48`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001f6b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001f86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001fa2`

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
  v9 = 2162689;
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
    LoadStringW(*(HINSTANCE *)(a1 + 24), 1u, Buffer, 32);
    LoadStringW(*(HINSTANCE *)(a1 + 24), 2u, v16, 128);
    if ( v4 > 364 )
    {
      LoadStringW(*(HINSTANCE *)(a1 + 24), 3u, v17, 80);
      LoadStringW(*(HINSTANCE *)(a1 + 24), 4u, v18, 128);
      LoadStringW(*(HINSTANCE *)(a1 + 24), 5u, v19, 512);
    }
  }
  memcpy_0(a2, &Src, Src);
  return 0;
}

```

## disassembly

```asm
0x180001e94  mov     [rsp-8+arg_10], rbx
0x180001e99  push    rbp
0x180001e9a  push    rsi
0x180001e9b  push    rdi
0x180001e9c  lea     rbp, [rsp-640h]
0x180001ea4  sub     rsp, 740h
0x180001eab  mov     rax, cs:__security_cookie
0x180001eb2  xor     rax, rsp
0x180001eb5  mov     [rbp+650h+var_20], rax
0x180001ebc  mov     rsi, rdx
0x180001ebf  mov     rbx, rcx
0x180001ec2  xor     edx, edx; Val
0x180001ec4  lea     rcx, [rsp+750h+var_70C]; void *
0x180001ec9  mov     r8d, 6E8h; Size
0x180001ecf  call    memset_0
0x180001ed4  mov     edi, 70Ch
0x180001ed9  mov     [rsp+750h+var_72C], 63647561h
0x180001ee2  cmp     [rsi], edi
0x180001ee4  mov     [rsp+750h+var_724], 210001h
0x180001eec  cmovb   edi, [rsi]
0x180001eef  xor     ecx, ecx
0x180001ef1  mov     [rsp+750h+Src], edi
0x180001ef5  mov     [rsp+750h+var_720], 3320000h
0x180001efd  mov     [rsp+750h+var_71C], 4000000h
0x180001f05  mov     [rsp+750h+var_714], 2
0x180001f0e  lea     edx, [rcx+1]; uID
0x180001f11  mov     [rsp+750h+var_718], edx
0x180001f15  cmp     edi, 24h ; '$'
0x180001f18  jle     loc_180001FA8
0x180001f1e  mov     [rsp+750h+var_70C], rcx
0x180001f23  lea     r9d, [rcx+20h]; cchBufferMax
0x180001f27  mov     rcx, [rbx+18h]; hInstance
0x180001f2b  lea     r8, [rsp+750h+Buffer]; lpBuffer
0x180001f30  call    cs:__imp_LoadStringW
0x180001f36  mov     rcx, [rbx+18h]; hInstance
0x180001f3a  lea     r8, [rbp+650h+var_6C4]; lpBuffer
0x180001f3e  mov     r9d, 80h; cchBufferMax
0x180001f44  lea     edx, [r9-7Eh]; uID
0x180001f48  call    cs:__imp_LoadStringW
0x180001f4e  cmp     edi, 16Ch
0x180001f54  jle     short loc_180001FA8
0x180001f56  mov     rcx, [rbx+18h]; hInstance
0x180001f5a  lea     r8, [rbp+650h+var_5C4]; lpBuffer
0x180001f61  mov     r9d, 50h ; 'P'; cchBufferMax
0x180001f67  lea     edx, [r9-4Dh]; uID
0x180001f6b  call    cs:__imp_LoadStringW
0x180001f71  mov     rcx, [rbx+18h]; hInstance
0x180001f75  lea     r8, [rbp+650h+var_524]; lpBuffer
0x180001f7c  mov     r9d, 80h; cchBufferMax
0x180001f82  lea     edx, [r9-7Ch]; uID
0x180001f86  call    cs:__imp_LoadStringW
0x180001f8c  mov     rcx, [rbx+18h]; hInstance
0x180001f90  lea     r8, [rbp+650h+var_424]; lpBuffer
0x180001f97  mov     r9d, 200h; cchBufferMax
0x180001f9d  mov     edx, 5; uID
0x180001fa2  call    cs:__imp_LoadStringW
0x180001fa8  mov     r8d, [rsp+750h+Src]; Size
0x180001fad  lea     rdx, [rsp+750h+Src]; Src
0x180001fb2  mov     rcx, rsi; void *
0x180001fb5  call    memcpy_0
0x180001fba  xor     eax, eax
0x180001fbc  mov     rcx, [rbp+650h+var_20]
0x180001fc3  xor     rcx, rsp; StackCookie
0x180001fc6  call    __security_check_cookie
0x180001fcb  mov     rbx, [rsp+750h+arg_10]
0x180001fd3  add     rsp, 740h
0x180001fda  pop     rdi
0x180001fdb  pop     rsi
0x180001fdc  pop     rbp
0x180001fdd  retn
```
