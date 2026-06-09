# TrueTypeFontList::s_Initialize(void)

- ea: `0x1800188c0`
- end: `0x180018acb`
- name: `?s_Initialize@TrueTypeFontList@@SAJXZ`
- size: `523`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006f18`

## callees

- `0x1800015b0`
- `0x180005e60`
- `0x180008714`
- `0x1800186bc`
- `0x18001886c`
- `0x1800188c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800189ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800189ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018991`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018991`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018aa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018aa1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180018971`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180018971`

## string_xrefs

- `0x1800188fc`: `onecore\windows\core\console\open\src\propslib\truetypefontlist.cpp`

## pseudocode

```c
__int64 TrueTypeFontList::s_Initialize(void)
{
  int v0; // eax
  DWORD i; // edi
  LSTATUS v2; // eax
  bool v3; // sf
  HANDLE ProcessHeap; // rax
  wchar_t *v5; // rax
  wchar_t *v6; // r11
  WCHAR *v7; // r8
  WCHAR v8; // dx
  unsigned __int16 v9; // cx
  const wchar_t *v10; // rbx
  int v11; // eax
  void *v12; // r11
  __int64 v13; // rax
  const wchar_t *v14; // r8
  int lpReserved; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v21; // [rsp+52h] [rbp-AEh] BYREF
  WCHAR ValueName[512]; // [rsp+450h] [rbp+350h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+888h] [rbp+788h]

  hKey = 0;
  v0 = TrueTypeFontList::s_Destroy();
  if ( v0 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propslib\\truetypefontlist.cpp",
      (const char *)(unsigned int)v0,
      lpReserved);
  if ( RegistrySerialization::s_OpenKey(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Console\\TrueTypeFont",
         &hKey) >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      cchValueName = 512;
      cbData = 1024;
      v2 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, Data, &cbData);
      v3 = v2 < 0;
      if ( v2 > 0 )
        v3 = 1;
      if ( v3 )
        break;
      ProcessHeap = GetProcessHeap();
      v5 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 0x90u);
      v6 = v5;
      if ( !v5 )
        break;
      *(_QWORD *)v5 = 0;
      v7 = ValueName;
      v8 = ValueName[0];
      v9 = 0;
      while ( v8 && (unsigned __int16)(v8 - 48) <= 9u )
      {
        v9 = v8 - 48 + 10 * v9;
        v8 = *++v7;
      }
      *((_DWORD *)v5 + 2) = v9;
      if ( *(_WORD *)Data == 42 )
      {
        v10 = &v21;
        v11 = 1;
      }
      else
      {
        v10 = (const wchar_t *)Data;
        v11 = 0;
      }
      *((_DWORD *)v6 + 3) = v11;
      StringCchCopyW(v6 + 8, 0x20u, v10);
      v13 = -1;
      do
        ++v13;
      while ( v10[v13] );
      v14 = &v10[v13 + 1];
      if ( v14 >= (const wchar_t *)Data && v14 < ValueName )
      {
        if ( *v14 == 42 )
        {
          *((_DWORD *)v12 + 3) = 1;
          ++v14;
        }
        StringCchCopyW((wchar_t *)v12 + 40, 0x20u, v14);
      }
      *(_QWORD *)v12 = TrueTypeFontList::s_ttFontList;
      TrueTypeFontList::s_ttFontList = v12;
    }
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x1800188c0  push    rbp
0x1800188c2  push    rbx
0x1800188c3  push    rsi
0x1800188c4  push    rdi
0x1800188c5  lea     rbp, [rsp-768h]
0x1800188cd  sub     rsp, 868h
0x1800188d4  mov     rax, cs:__security_cookie
0x1800188db  xor     rax, rsp
0x1800188de  mov     [rbp+780h+var_30], rax
0x1800188e5  xor     esi, esi
0x1800188e7  mov     [rsp+880h+hKey], rsi
0x1800188ec  call    ?s_Destroy@TrueTypeFontList@@SAJXZ; TrueTypeFontList::s_Destroy(void)
0x1800188f1  test    eax, eax
0x1800188f3  jns     short loc_18001890E
0x1800188f5  mov     rcx, [rbp+788h]; this
0x1800188fc  lea     r8, aOnecoreWindows_5; "onecore\\windows\\core\\console\\open\\"...
0x180018903  mov     r9d, eax; char *
0x180018906  lea     edx, [rsi+2Ch]; void *
0x180018909  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001890e  lea     r8, [rsp+880h+hKey]; HKEY *
0x180018913  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001891a  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180018921  call    ?s_OpenKey@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WQEAPEAU2@@Z; RegistrySerialization::s_OpenKey(HKEY__ * const,wchar_t const * const,HKEY__ * * const)
0x180018926  test    eax, eax
0x180018928  js      loc_180018AAD
0x18001892e  mov     edi, esi
0x180018930  mov     rcx, [rsp+880h+hKey]; hKey
0x180018935  lea     rax, [rsp+880h+cbData]
0x18001893a  mov     [rsp+880h+lpcbData], rax; lpcbData
0x18001893f  lea     r9, [rsp+880h+cchValueName]; lpcchValueName
0x180018944  lea     rax, [rsp+880h+Data]
0x180018949  mov     [rsp+880h+cchValueName], 200h
0x180018951  mov     [rsp+880h+lpData], rax; lpData
0x180018956  lea     r8, [rbp+780h+ValueName]; lpValueName
0x18001895d  mov     [rsp+880h+lpType], rsi; lpType
0x180018962  mov     edx, edi; dwIndex
0x180018964  mov     [rsp+880h+lpReserved], rsi; lpReserved
0x180018969  mov     [rsp+880h+cbData], 400h
0x180018971  call    cs:__imp_RegEnumValueW
0x180018978  nop     dword ptr [rax+rax+00h]
0x18001897d  test    eax, eax
0x18001897f  jle     short loc_18001898B
0x180018981  movzx   eax, ax
0x180018984  or      eax, 0C0070000h
0x180018989  test    eax, eax
0x18001898b  js      loc_180018A9C
0x180018991  call    cs:__imp_GetProcessHeap
0x180018998  nop     dword ptr [rax+rax+00h]
0x18001899d  mov     edx, 8; dwFlags
0x1800189a2  mov     r8d, 90h; dwBytes
0x1800189a8  mov     rcx, rax; hHeap
0x1800189ab  call    cs:__imp_HeapAlloc
0x1800189b2  nop     dword ptr [rax+rax+00h]
0x1800189b7  mov     r11, rax
0x1800189ba  test    rax, rax
0x1800189bd  jz      loc_180018A9C
0x1800189c3  mov     [rax], rsi
0x1800189c6  lea     r8, [rbp+780h+ValueName]
0x1800189cd  movzx   edx, [rbp+780h+ValueName]
0x1800189d4  mov     ecx, esi
0x1800189d6  jmp     short loc_1800189FD
0x1800189d8  lea     eax, [rdx-30h]
0x1800189db  cmp     ax, 9
0x1800189df  ja      short loc_180018A02
0x1800189e1  movzx   eax, cx
0x1800189e4  sub     dx, 30h ; '0'
0x1800189e8  shl     ax, 2
0x1800189ec  add     cx, ax
0x1800189ef  add     cx, cx
0x1800189f2  add     cx, dx
0x1800189f5  add     r8, 2
0x1800189f9  movzx   edx, word ptr [r8]
0x1800189fd  test    dx, dx
0x180018a00  jnz     short loc_1800189D8
0x180018a02  movzx   eax, cx
0x180018a05  mov     [r11+8], eax
0x180018a09  cmp     word ptr [rsp+880h+Data], 2Ah ; '*'
0x180018a0f  jnz     short loc_180018A1D
0x180018a11  lea     rbx, [rsp+880h+var_82E]
0x180018a16  mov     eax, 1
0x180018a1b  jmp     short loc_180018A24
0x180018a1d  lea     rbx, [rsp+880h+Data]
0x180018a22  mov     eax, esi
0x180018a24  lea     rcx, [r11+10h]; wchar_t *
0x180018a28  mov     [r11+0Ch], eax
0x180018a2c  mov     r8, rbx; wchar_t *
0x180018a2f  mov     edx, 20h ; ' '; unsigned __int64
0x180018a34  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180018a39  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018a3d  inc     rax
0x180018a40  cmp     [rbx+rax*2], si
0x180018a44  jnz     short loc_180018A3D
0x180018a46  inc     rax
0x180018a49  lea     r8, [rbx+rax*2]
0x180018a4d  lea     rax, [rsp+880h+Data]
0x180018a52  cmp     r8, rax
0x180018a55  jb      short loc_180018A84
0x180018a57  lea     rax, [rbp+780h+ValueName]
0x180018a5e  cmp     r8, rax
0x180018a61  jnb     short loc_180018A84
0x180018a63  cmp     word ptr [r8], 2Ah ; '*'
0x180018a68  jnz     short loc_180018A76
0x180018a6a  mov     dword ptr [r11+0Ch], 1
0x180018a72  add     r8, 2; wchar_t *
0x180018a76  lea     rcx, [r11+50h]; wchar_t *
0x180018a7a  mov     edx, 20h ; ' '; unsigned __int64
0x180018a7f  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180018a84  mov     rax, cs:?s_ttFontList@TrueTypeFontList@@2U_SINGLE_LIST_ENTRY@@A; _SINGLE_LIST_ENTRY TrueTypeFontList::s_ttFontList
0x180018a8b  inc     edi
0x180018a8d  mov     [r11], rax
0x180018a90  mov     cs:?s_ttFontList@TrueTypeFontList@@2U_SINGLE_LIST_ENTRY@@A, r11; _SINGLE_LIST_ENTRY TrueTypeFontList::s_ttFontList
0x180018a97  jmp     loc_180018930
0x180018a9c  mov     rcx, [rsp+880h+hKey]; hKey
0x180018aa1  call    cs:__imp_RegCloseKey
0x180018aa8  nop     dword ptr [rax+rax+00h]
0x180018aad  xor     eax, eax
0x180018aaf  mov     rcx, [rbp+780h+var_30]
0x180018ab6  xor     rcx, rsp; StackCookie
0x180018ab9  call    __security_check_cookie
0x180018abe  add     rsp, 868h
0x180018ac5  pop     rdi
0x180018ac6  pop     rsi
0x180018ac7  pop     rbx
0x180018ac8  pop     rbp
0x180018ac9  retn
```
