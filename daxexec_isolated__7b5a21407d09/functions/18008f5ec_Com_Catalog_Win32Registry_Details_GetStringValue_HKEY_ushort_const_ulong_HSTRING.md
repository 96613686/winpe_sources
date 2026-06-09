# Com::Catalog::Win32Registry::Details::GetStringValue(HKEY__ *,ushort const *,ulong,HSTRING__ * *)

- ea: `0x18008f5ec`
- end: `0x18008f802`
- name: `?GetStringValue@Details@Win32Registry@Catalog@Com@@YAJPEAUHKEY__@@PEBGKPEAPEAUHSTRING__@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(HKEY hkey, HKEY, const unsigned __int16 *, unsigned int, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008fe60`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18001eeb8`
- `0x18008f5ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008f750`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008f7cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008f750`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008f7cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008f67c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008f73c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008f7b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008f67c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008f73c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008f7b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008f693`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008f693`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008f65b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008f6d4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008f65b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008f6d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008f779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008f779`

## string_xrefs

- `0x18008f6ed`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008f721`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008f79a`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`

## pseudocode

```c
__int64 __fastcall Com::Catalog::Win32Registry::Details::GetStringValue(
        HKEY hkey,
        HKEY a2,
        const unsigned __int16 *a3,
        HSTRING *a4)
{
  unsigned int ValueW; // eax
  __int64 v7; // rsi
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rax
  const WCHAR *v10; // rdi
  WCHAR *v11; // rbx
  unsigned int v12; // edi
  HANDLE v14; // rax
  __int64 v15; // rdx
  HSTRING v16; // rax
  HANDLE v17; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-278h]
  DWORD pcbData; // [rsp+40h] [rbp-258h] BYREF
  HSTRING string; // [rsp+48h] [rbp-250h] BYREF
  _BYTE pvData[528]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  memset_0(pvData, 0, 0x208u);
  pcbData = 520;
  ValueW = RegGetValueW(hkey, 0, &String1, 6u, 0, pvData, &pcbData);
  if ( ValueW == 234 )
  {
    v7 = (pcbData + 1) & 0xFFFFFFFE;
    ProcessHeap = GetProcessHeap();
    v9 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v7 + 2);
    v10 = v9;
    if ( !v9 )
    {
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
        (const char *)0x8007000ELL,
        pdwType);
      return v12;
    }
    *v9 = 0;
    *(WCHAR *)((char *)v9 + v7) = 0;
    ValueW = RegGetValueW(hkey, 0, &String1, 6u, 0, v9, &pcbData);
    v11 = (WCHAR *)v10;
  }
  else
  {
    v11 = 0;
    v10 = (const WCHAR *)pvData;
  }
  if ( ValueW )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2D,
            (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
            (const char *)ValueW,
            pdwType);
    goto LABEL_9;
  }
  v15 = -1;
  do
    ++v15;
  while ( v10[v15] );
  string = 0;
  WindowsCreateString(v10, v15, &string);
  v16 = string;
  *a4 = string;
  if ( !v16 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
      (const char *)0x8007000ELL,
      pdwType);
LABEL_9:
    if ( v11 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v11);
    }
    return v12;
  }
  if ( v11 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x18008f5ec  mov     [rsp+arg_8], rbx
0x18008f5f1  push    rbp
0x18008f5f2  push    rsi
0x18008f5f3  push    rdi
0x18008f5f4  push    r14
0x18008f5f6  push    r15
0x18008f5f8  sub     rsp, 270h
0x18008f5ff  mov     rax, cs:__security_cookie
0x18008f606  xor     rax, rsp
0x18008f609  mov     [rsp+298h+var_38], rax
0x18008f611  mov     rbp, rcx
0x18008f614  mov     ebx, 208h
0x18008f619  mov     r8d, ebx; Size
0x18008f61c  lea     rcx, [rsp+298h+var_248]; void *
0x18008f621  xor     edx, edx; Val
0x18008f623  mov     r14, r9
0x18008f626  call    memset_0
0x18008f62b  lea     rax, [rsp+298h+var_258]
0x18008f630  mov     [rsp+298h+var_258], ebx
0x18008f634  mov     [rsp+298h+pcbData], rax; pcbData
0x18008f639  lea     r8, String1; lpValue
0x18008f640  xor     r15d, r15d
0x18008f643  lea     rax, [rsp+298h+var_248]
0x18008f648  mov     [rsp+298h+pvData], rax; pvData
0x18008f64d  xor     edx, edx; lpSubKey
0x18008f64f  mov     rcx, rbp; hkey
0x18008f652  mov     [rsp+298h+pdwType], r15; int
0x18008f657  lea     r9d, [r15+6]; dwFlags
0x18008f65b  call    cs:__imp_RegGetValueW
0x18008f662  nop     dword ptr [rax+rax+00h]
0x18008f667  cmp     eax, 0EAh
0x18008f66c  jnz     loc_18008F70D
0x18008f672  mov     esi, [rsp+298h+var_258]
0x18008f676  inc     esi
0x18008f678  and     rsi, 0FFFFFFFFFFFFFFFEh
0x18008f67c  call    cs:__imp_GetProcessHeap
0x18008f683  nop     dword ptr [rax+rax+00h]
0x18008f688  mov     rcx, rax; hHeap
0x18008f68b  lea     r8, [rsi+2]; dwBytes
0x18008f68f  lea     edx, [r15+8]; dwFlags
0x18008f693  call    cs:__imp_HeapAlloc
0x18008f69a  nop     dword ptr [rax+rax+00h]
0x18008f69f  mov     rdi, rax
0x18008f6a2  test    rax, rax
0x18008f6a5  jz      short loc_18008F6E5
0x18008f6a7  mov     [rax], r15w
0x18008f6ab  lea     r9d, [r15+6]; dwFlags
0x18008f6af  mov     [rsi+rax], r15w
0x18008f6b4  lea     r8, String1; lpValue
0x18008f6bb  lea     rax, [rsp+298h+var_258]
0x18008f6c0  xor     edx, edx; lpSubKey
0x18008f6c2  mov     [rsp+298h+pcbData], rax; pcbData
0x18008f6c7  mov     rcx, rbp; hkey
0x18008f6ca  mov     [rsp+298h+pvData], rdi; pvData
0x18008f6cf  mov     [rsp+298h+pdwType], r15; pdwType
0x18008f6d4  call    cs:__imp_RegGetValueW
0x18008f6db  nop     dword ptr [rax+rax+00h]
0x18008f6e0  mov     rbx, rdi
0x18008f6e3  jmp     short loc_18008F715
0x18008f6e5  mov     rcx, [rsp+298h]; this
0x18008f6ed  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008f6f4  mov     edi, 8007000Eh
0x18008f6f9  mov     edx, 27h ; '''; void *
0x18008f6fe  mov     r9d, edi; char *
0x18008f701  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f706  mov     eax, edi
0x18008f708  jmp     loc_18008F7DA
0x18008f70d  mov     rbx, r15
0x18008f710  lea     rdi, [rsp+298h+var_248]
0x18008f715  test    eax, eax
0x18008f717  jz      short loc_18008F75E
0x18008f719  mov     rcx, [rsp+298h]; this
0x18008f721  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008f728  mov     r9d, eax; char *
0x18008f72b  mov     edx, 2Dh ; '-'; void *
0x18008f730  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008f735  mov     edi, eax
0x18008f737  test    rbx, rbx
0x18008f73a  jz      short loc_18008F706
0x18008f73c  call    cs:__imp_GetProcessHeap
0x18008f743  nop     dword ptr [rax+rax+00h]
0x18008f748  mov     r8, rbx; lpMem
0x18008f74b  xor     edx, edx; dwFlags
0x18008f74d  mov     rcx, rax; hHeap
0x18008f750  call    cs:__imp_HeapFree
0x18008f757  nop     dword ptr [rax+rax+00h]
0x18008f75c  jmp     short loc_18008F706
0x18008f75e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008f762  inc     rdx; length
0x18008f765  cmp     [rdi+rdx*2], r15w
0x18008f76a  jnz     short loc_18008F762
0x18008f76c  lea     r8, [rsp+298h+string]; string
0x18008f771  mov     [rsp+298h+string], r15
0x18008f776  mov     rcx, rdi; sourceString
0x18008f779  call    cs:__imp_WindowsCreateString
0x18008f780  nop     dword ptr [rax+rax+00h]
0x18008f785  mov     rax, [rsp+298h+string]
0x18008f78a  mov     [r14], rax
0x18008f78d  test    rax, rax
0x18008f790  jnz     short loc_18008F7B3
0x18008f792  mov     rcx, [rsp+298h]; this
0x18008f79a  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008f7a1  mov     edi, 8007000Eh
0x18008f7a6  lea     edx, [rax+30h]; void *
0x18008f7a9  mov     r9d, edi; char *
0x18008f7ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f7b1  jmp     short loc_18008F737
0x18008f7b3  test    rbx, rbx
0x18008f7b6  jz      short loc_18008F7D8
0x18008f7b8  call    cs:__imp_GetProcessHeap
0x18008f7bf  nop     dword ptr [rax+rax+00h]
0x18008f7c4  mov     r8, rbx; lpMem
0x18008f7c7  xor     edx, edx; dwFlags
0x18008f7c9  mov     rcx, rax; hHeap
0x18008f7cc  call    cs:__imp_HeapFree
0x18008f7d3  nop     dword ptr [rax+rax+00h]
0x18008f7d8  xor     eax, eax
0x18008f7da  mov     rcx, [rsp+298h+var_38]
0x18008f7e2  xor     rcx, rsp; StackCookie
0x18008f7e5  call    __security_check_cookie
0x18008f7ea  mov     rbx, [rsp+298h+arg_8]
0x18008f7f2  add     rsp, 270h
0x18008f7f9  pop     r15
0x18008f7fb  pop     r14
0x18008f7fd  pop     rdi
0x18008f7fe  pop     rsi
0x18008f7ff  pop     rbp
0x18008f800  retn
```
