# _CatDBRunOnceShouldOnlySyncPresentCatalogs(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18001b130`
- end: `0x18001b1be`
- name: `?_CatDBRunOnceShouldOnlySyncPresentCatalogs@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `142`
- prototype: `unsigned int __fastcall(union _RTL_RUN_ONCE *, void *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000be40`
- `0x18001b130`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b189`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b189`

## string_xrefs

- `0x18001b156`: `PresumeRemovedCatalogsDuringSync`

## pseudocode

```c
__int64 __fastcall _CatDBRunOnceShouldOnlySyncPresentCatalogs(union _RTL_RUN_ONCE *a1, void *a2, void **a3)
{
  int v3; // eax
  int v5; // [rsp+40h] [rbp-18h] BYREF
  DWORD v6; // [rsp+44h] [rbp-14h] BYREF

  v5 = 0;
  v6 = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Cryptography\\CatalogDB",
         L"PresumeRemovedCatalogsDuringSync",
         0x10u,
         0,
         &v5,
         &v6) )
  {
    v3 = 0;
  }
  else
  {
    v3 = v5;
  }
  if ( v3 )
    g_fFilterNonePresentCatalogs = 1;
  return 1;
}

```

## disassembly

```asm
0x18001b130  mov     r11, rsp
0x18001b133  sub     rsp, 58h
0x18001b137  mov     rax, cs:__security_cookie
0x18001b13e  xor     rax, rsp
0x18001b141  mov     [rsp+58h+var_10], rax
0x18001b146  lea     rax, [r11-14h]
0x18001b14a  mov     [rsp+58h+var_18], 0
0x18001b152  mov     [r11-28h], rax
0x18001b156  lea     r8, aPresumeremoved; "PresumeRemovedCatalogsDuringSync"
0x18001b15d  lea     rax, [r11-18h]
0x18001b161  mov     [rsp+58h+var_14], 4
0x18001b169  mov     [r11-30h], rax
0x18001b16d  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Cryptography\\Cata"...
0x18001b174  mov     r9d, 10h; dwFlags
0x18001b17a  mov     qword ptr [r11-38h], 0
0x18001b182  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001b189  call    cs:__imp_RegGetValueW
0x18001b18f  test    eax, eax
0x18001b191  jz      short loc_18001B197
0x18001b193  xor     eax, eax
0x18001b195  jmp     short loc_18001B19B
0x18001b197  mov     eax, [rsp+58h+var_18]
0x18001b19b  mov     ecx, 1
0x18001b1a0  test    eax, eax
0x18001b1a2  jz      short loc_18001B1AA
0x18001b1a4  mov     cs:?g_fFilterNonePresentCatalogs@@3HA, ecx; int g_fFilterNonePresentCatalogs
0x18001b1aa  mov     eax, ecx
0x18001b1ac  mov     rcx, [rsp+58h+var_10]
0x18001b1b1  xor     rcx, rsp; StackCookie
0x18001b1b4  call    __security_check_cookie
0x18001b1b9  add     rsp, 58h
0x18001b1bd  retn
```
