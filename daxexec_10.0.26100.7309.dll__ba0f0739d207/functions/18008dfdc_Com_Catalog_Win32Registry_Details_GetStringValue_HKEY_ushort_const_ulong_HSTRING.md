# Com::Catalog::Win32Registry::Details::GetStringValue(HKEY__ *,ushort const *,ulong,HSTRING__ * *)

- ea: `0x18008dfdc`
- end: `0x18008e1f7`
- name: `?GetStringValue@Details@Win32Registry@Catalog@Com@@YAJPEAUHKEY__@@PEBGKPEAPEAUHSTRING__@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(HKEY hkey, HKEY, const unsigned __int16 *, unsigned int, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008e820`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x18001e32c`
- `0x18008dfdc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e11b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e1bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e11b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e1bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e075`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e107`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e1ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e075`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e107`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e1ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008e08c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008e08c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008e058`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008e0d4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008e058`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008e0d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008e169`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008e169`

## string_xrefs

- `0x18008e0ec`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008e131`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008e18a`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`

## pseudocode

```c
__int64 __fastcall Com::Catalog::Win32Registry::Details::GetStringValue(
        HKEY hkey,
        HKEY a2,
        const unsigned __int16 *a3,
        HSTRING *a4)
{
  WCHAR *v6; // rdi
  void *v7; // rbx
  unsigned int ValueW; // eax
  __int64 v9; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *pvData; // rax
  unsigned int v12; // edi
  HANDLE v13; // rax
  __int64 v15; // rdx
  HSTRING v16; // rax
  HANDLE v17; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-268h]
  DWORD pcbData; // [rsp+40h] [rbp-248h] BYREF
  HSTRING string; // [rsp+48h] [rbp-240h] BYREF
  WCHAR sourceString[264]; // [rsp+50h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  memset_0(sourceString, 0, 0x208u);
  pcbData = 520;
  v6 = sourceString;
  v7 = 0;
  ValueW = RegGetValueW(hkey, 0, &String1, 6u, 0, sourceString, &pcbData);
  if ( ValueW == 234 )
  {
    v9 = (pcbData + 1) & 0xFFFFFFFE;
    ProcessHeap = GetProcessHeap();
    pvData = HeapAlloc(ProcessHeap, 8u, v9 + 2);
    v7 = pvData;
    if ( !pvData )
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
    *pvData = 0;
    *(_WORD *)((char *)pvData + v9) = 0;
    v6 = pvData;
    ValueW = RegGetValueW(hkey, 0, &String1, 6u, 0, pvData, &pcbData);
  }
  if ( ValueW )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2D,
            (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
            (const char *)ValueW,
            pdwType);
    goto LABEL_6;
  }
  v15 = -1;
  do
    ++v15;
  while ( v6[v15] );
  string = 0;
  WindowsCreateString(v6, v15, &string);
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
LABEL_6:
    if ( v7 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v7);
    }
    return v12;
  }
  if ( v7 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18008dfdc  mov     [rsp+arg_8], rbx
0x18008dfe1  mov     [rsp+arg_10], rsi
0x18008dfe6  push    rdi
0x18008dfe7  push    r14
0x18008dfe9  push    r15
0x18008dfeb  sub     rsp, 270h
0x18008dff2  mov     rax, cs:__security_cookie
0x18008dff9  xor     rax, rsp
0x18008dffc  mov     [rsp+288h+var_28], rax
0x18008e004  mov     rsi, rcx
0x18008e007  xor     edx, edx; Val
0x18008e009  lea     rcx, [rsp+288h+sourceString]; void *
0x18008e00e  mov     r8d, 208h; Size
0x18008e014  mov     r14, r9
0x18008e017  call    memset_0
0x18008e01c  xor     r15d, r15d
0x18008e01f  mov     [rsp+288h+var_248], 208h
0x18008e027  lea     rax, [rsp+288h+var_248]
0x18008e02c  xor     edx, edx; lpSubKey
0x18008e02e  mov     [rsp+288h+pcbData], rax; pcbData
0x18008e033  lea     r8, String1; lpValue
0x18008e03a  lea     rax, [rsp+288h+sourceString]
0x18008e03f  mov     rcx, rsi; hkey
0x18008e042  mov     [rsp+288h+pvData], rax; pvData
0x18008e047  lea     r9d, [r15+6]; dwFlags
0x18008e04b  mov     [rsp+288h+pdwType], r15; int
0x18008e050  lea     rdi, [rsp+288h+sourceString]
0x18008e055  mov     ebx, r15d
0x18008e058  call    cs:__imp_RegGetValueW
0x18008e05f  nop     dword ptr [rax+rax+00h]
0x18008e064  cmp     eax, 0EAh
0x18008e069  jnz     short loc_18008E0E0
0x18008e06b  mov     edi, [rsp+288h+var_248]
0x18008e06f  inc     edi
0x18008e071  and     rdi, 0FFFFFFFFFFFFFFFEh
0x18008e075  call    cs:__imp_GetProcessHeap
0x18008e07c  nop     dword ptr [rax+rax+00h]
0x18008e081  mov     rcx, rax; hHeap
0x18008e084  lea     r8, [rdi+2]; dwBytes
0x18008e088  lea     edx, [r15+8]; dwFlags
0x18008e08c  call    cs:__imp_HeapAlloc
0x18008e093  nop     dword ptr [rax+rax+00h]
0x18008e098  mov     rbx, rax
0x18008e09b  test    rax, rax
0x18008e09e  jz      loc_18008E129
0x18008e0a4  mov     [rax], r15w
0x18008e0a8  lea     r9d, [r15+6]; dwFlags
0x18008e0ac  mov     [rdi+rax], r15w
0x18008e0b1  lea     r8, String1; lpValue
0x18008e0b8  mov     rdi, rax
0x18008e0bb  xor     edx, edx; lpSubKey
0x18008e0bd  lea     rax, [rsp+288h+var_248]
0x18008e0c2  mov     rcx, rsi; hkey
0x18008e0c5  mov     [rsp+288h+pcbData], rax; pcbData
0x18008e0ca  mov     [rsp+288h+pvData], rbx; pvData
0x18008e0cf  mov     [rsp+288h+pdwType], r15; int
0x18008e0d4  call    cs:__imp_RegGetValueW
0x18008e0db  nop     dword ptr [rax+rax+00h]
0x18008e0e0  test    eax, eax
0x18008e0e2  jz      short loc_18008E14E
0x18008e0e4  mov     rcx, [rsp+288h]; this
0x18008e0ec  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008e0f3  mov     r9d, eax; char *
0x18008e0f6  mov     edx, 2Dh ; '-'; void *
0x18008e0fb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008e100  mov     edi, eax
0x18008e102  test    rbx, rbx
0x18008e105  jz      short loc_18008E14A
0x18008e107  call    cs:__imp_GetProcessHeap
0x18008e10e  nop     dword ptr [rax+rax+00h]
0x18008e113  mov     r8, rbx; lpMem
0x18008e116  xor     edx, edx; dwFlags
0x18008e118  mov     rcx, rax; hHeap
0x18008e11b  call    cs:__imp_HeapFree
0x18008e122  nop     dword ptr [rax+rax+00h]
0x18008e127  jmp     short loc_18008E14A
0x18008e129  mov     rcx, [rsp+288h]; this
0x18008e131  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008e138  mov     edi, 8007000Eh
0x18008e13d  mov     edx, 27h ; '''; void *
0x18008e142  mov     r9d, edi; char *
0x18008e145  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e14a  mov     eax, edi
0x18008e14c  jmp     short loc_18008E1CD
0x18008e14e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008e152  inc     rdx; length
0x18008e155  cmp     [rdi+rdx*2], r15w
0x18008e15a  jnz     short loc_18008E152
0x18008e15c  lea     r8, [rsp+288h+string]; string
0x18008e161  mov     [rsp+288h+string], r15
0x18008e166  mov     rcx, rdi; sourceString
0x18008e169  call    cs:__imp_WindowsCreateString
0x18008e170  nop     dword ptr [rax+rax+00h]
0x18008e175  mov     rax, [rsp+288h+string]
0x18008e17a  mov     [r14], rax
0x18008e17d  test    rax, rax
0x18008e180  jnz     short loc_18008E1A6
0x18008e182  mov     rcx, [rsp+288h]; this
0x18008e18a  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008e191  mov     edi, 8007000Eh
0x18008e196  lea     edx, [rax+30h]; void *
0x18008e199  mov     r9d, edi; char *
0x18008e19c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e1a1  jmp     loc_18008E102
0x18008e1a6  test    rbx, rbx
0x18008e1a9  jz      short loc_18008E1CB
0x18008e1ab  call    cs:__imp_GetProcessHeap
0x18008e1b2  nop     dword ptr [rax+rax+00h]
0x18008e1b7  mov     r8, rbx; lpMem
0x18008e1ba  xor     edx, edx; dwFlags
0x18008e1bc  mov     rcx, rax; hHeap
0x18008e1bf  call    cs:__imp_HeapFree
0x18008e1c6  nop     dword ptr [rax+rax+00h]
0x18008e1cb  xor     eax, eax
0x18008e1cd  mov     rcx, [rsp+288h+var_28]
0x18008e1d5  xor     rcx, rsp; StackCookie
0x18008e1d8  call    __security_check_cookie
0x18008e1dd  lea     r11, [rsp+288h+var_18]
0x18008e1e5  mov     rbx, [r11+28h]
0x18008e1e9  mov     rsi, [r11+30h]
0x18008e1ed  mov     rsp, r11
0x18008e1f0  pop     r15
0x18008e1f2  pop     r14
0x18008e1f4  pop     rdi
0x18008e1f5  retn
```
