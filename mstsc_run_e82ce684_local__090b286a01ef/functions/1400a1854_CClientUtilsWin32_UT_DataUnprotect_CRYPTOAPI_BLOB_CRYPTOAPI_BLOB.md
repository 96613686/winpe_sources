# CClientUtilsWin32::UT_DataUnprotect(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *)

- ea: `0x1400a1854`
- end: `0x1400a1a5b`
- name: `?UT_DataUnprotect@CClientUtilsWin32@@SAHPEAU_CRYPTOAPI_BLOB@@0@Z`
- size: `519`
- prototype: `__int64 __fastcall(struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14003d188`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x1400a1854`
- `0x140114010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1400a1896`
- `KERNEL32!LoadLibraryW` at `0x1400a1896`
- `KERNEL32!FreeLibrary` at `0x1400a199e`
- `KERNEL32!FreeLibrary` at `0x1400a199e`
- `KERNEL32!GetProcAddress` at `0x1400a18b2`
- `KERNEL32!GetProcAddress` at `0x1400a18b2`
- `KERNEL32!GetLastError` at `0x1400a18f0`
- `KERNEL32!GetLastError` at `0x1400a1969`
- `KERNEL32!GetLastError` at `0x1400a19d2`
- `KERNEL32!GetLastError` at `0x1400a18f0`
- `KERNEL32!GetLastError` at `0x1400a1969`
- `KERNEL32!GetLastError` at `0x1400a19d2`

## string_xrefs

- `0x1400a188f`: `crypt32.dll`

## pseudocode

```c
__int64 __fastcall CClientUtilsWin32::UT_DataUnprotect(struct _CRYPTOAPI_BLOB *a1, struct _CRYPTOAPI_BLOB *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rsi
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  DWORD LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD v10; // ebx
  unsigned int v11; // eax
  DWORD v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // eax
  struct _CRYPTOAPI_BLOB *v16; // [rsp+30h] [rbp-18h]

  if ( a1 && a1->cbData && a1->pbData && a2 )
  {
    LibraryW = LoadLibraryW(L"crypt32.dll");
    v5 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "CryptUnprotectData");
      if ( ProcAddress )
      {
        v16 = a2;
        v7 = 1;
        if ( ((unsigned int (__fastcall *)(struct _CRYPTOAPI_BLOB *, _QWORD, _QWORD, _QWORD, _QWORD, int, struct _CRYPTOAPI_BLOB *))ProcAddress)(
               a1,
               0,
               0,
               0,
               0,
               1,
               v16) )
        {
LABEL_17:
          FreeLibrary(v5);
          return v7;
        }
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            55,
            &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
            CurrentThreadActivityIdPrefix,
            LastError);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = GetLastError();
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids, v11, v10);
      }
      v7 = 0;
      goto LABEL_17;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = GetLastError();
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids, v14, v13);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x1400a1854  mov     [rsp+arg_0], rbx
0x1400a1859  mov     [rsp+arg_8], rsi
0x1400a185e  push    rdi
0x1400a185f  sub     rsp, 40h
0x1400a1863  mov     rbx, rdx
0x1400a1866  mov     rdi, rcx
0x1400a1869  test    rcx, rcx
0x1400a186c  jz      loc_1400A1A04
0x1400a1872  cmp     dword ptr [rcx], 0
0x1400a1875  jz      loc_1400A1A04
0x1400a187b  cmp     qword ptr [rcx+8], 0
0x1400a1880  jz      loc_1400A1A04
0x1400a1886  test    rdx, rdx
0x1400a1889  jz      loc_1400A1A04
0x1400a188f  lea     rcx, aCrypt32Dll_0; "crypt32.dll"
0x1400a1896  call    cs:__imp_LoadLibraryW
0x1400a189c  mov     rsi, rax
0x1400a189f  test    rax, rax
0x1400a18a2  jz      loc_1400A19AB
0x1400a18a8  lea     rdx, aCryptunprotect_1; "CryptUnprotectData"
0x1400a18af  mov     rcx, rax; hModule
0x1400a18b2  call    cs:__imp_GetProcAddress
0x1400a18b8  test    rax, rax
0x1400a18bb  jz      loc_1400A1946
0x1400a18c1  mov     [rsp+48h+var_18], rbx
0x1400a18c6  xor     r9d, r9d
0x1400a18c9  mov     ebx, 1
0x1400a18ce  xor     r8d, r8d
0x1400a18d1  mov     [rsp+48h+var_20], ebx
0x1400a18d5  xor     edx, edx
0x1400a18d7  mov     rcx, rdi
0x1400a18da  mov     [rsp+48h+var_28], 0
0x1400a18e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a18e8  test    eax, eax
0x1400a18ea  jnz     loc_1400A199B
0x1400a18f0  call    cs:__imp_GetLastError
0x1400a18f6  mov     edi, eax
0x1400a18f8  mov     rdx, cs:WPP_GLOBAL_Control
0x1400a18ff  lea     rcx, WPP_GLOBAL_Control
0x1400a1906  cmp     rdx, rcx
0x1400a1909  jz      loc_1400A1999
0x1400a190f  test    [rdx+1Ch], bl
0x1400a1912  jz      loc_1400A1999
0x1400a1918  cmp     byte ptr [rdx+19h], 2
0x1400a191c  jb      short loc_1400A1999
0x1400a191e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1923  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a192a  lea     edx, [rbx+36h]
0x1400a192d  mov     r9d, eax
0x1400a1930  mov     dword ptr [rsp+48h+var_28], edi
0x1400a1934  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a193b  mov     rcx, [rcx+10h]
0x1400a193f  call    WPP_SF_Dd
0x1400a1944  jmp     short loc_1400A1999
0x1400a1946  mov     rax, cs:WPP_GLOBAL_Control
0x1400a194d  lea     rcx, WPP_GLOBAL_Control
0x1400a1954  cmp     rax, rcx
0x1400a1957  jz      short loc_1400A1999
0x1400a1959  mov     ebx, 1
0x1400a195e  test    [rax+1Ch], bl
0x1400a1961  jz      short loc_1400A1999
0x1400a1963  cmp     byte ptr [rax+19h], 2
0x1400a1967  jb      short loc_1400A1999
0x1400a1969  call    cs:__imp_GetLastError
0x1400a196f  mov     ebx, eax
0x1400a1971  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1976  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a197d  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a1984  mov     edx, 38h ; '8'
0x1400a1989  mov     dword ptr [rsp+48h+var_28], ebx
0x1400a198d  mov     r9d, eax
0x1400a1990  mov     rcx, [rcx+10h]
0x1400a1994  call    WPP_SF_Dd
0x1400a1999  xor     ebx, ebx
0x1400a199b  mov     rcx, rsi; hLibModule
0x1400a199e  call    cs:__imp_FreeLibrary
0x1400a19a4  mov     eax, ebx
0x1400a19a6  jmp     loc_1400A1A4B
0x1400a19ab  mov     rax, cs:WPP_GLOBAL_Control
0x1400a19b2  lea     rcx, WPP_GLOBAL_Control
0x1400a19b9  cmp     rax, rcx
0x1400a19bc  jz      loc_1400A1A49
0x1400a19c2  mov     ebx, 1
0x1400a19c7  test    [rax+1Ch], bl
0x1400a19ca  jz      short loc_1400A1A49
0x1400a19cc  cmp     byte ptr [rax+19h], 2
0x1400a19d0  jb      short loc_1400A1A49
0x1400a19d2  call    cs:__imp_GetLastError
0x1400a19d8  mov     ebx, eax
0x1400a19da  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a19df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a19e6  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a19ed  mov     edx, 36h ; '6'
0x1400a19f2  mov     dword ptr [rsp+48h+var_28], ebx
0x1400a19f6  mov     r9d, eax
0x1400a19f9  mov     rcx, [rcx+10h]
0x1400a19fd  call    WPP_SF_Dd
0x1400a1a02  jmp     short loc_1400A1A49
0x1400a1a04  mov     rax, cs:WPP_GLOBAL_Control
0x1400a1a0b  lea     rcx, WPP_GLOBAL_Control
0x1400a1a12  cmp     rax, rcx
0x1400a1a15  jz      short loc_1400A1A49
0x1400a1a17  mov     ebx, 1
0x1400a1a1c  test    [rax+1Ch], bl
0x1400a1a1f  jz      short loc_1400A1A49
0x1400a1a21  cmp     byte ptr [rax+19h], 2
0x1400a1a25  jb      short loc_1400A1A49
0x1400a1a27  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1a33  lea     edx, [rbx+38h]
0x1400a1a36  mov     r9d, eax
0x1400a1a39  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a1a40  mov     rcx, [rcx+10h]
0x1400a1a44  call    WPP_SF_d
0x1400a1a49  xor     eax, eax
0x1400a1a4b  mov     rbx, [rsp+48h+arg_0]
0x1400a1a50  mov     rsi, [rsp+48h+arg_8]
0x1400a1a55  add     rsp, 40h
0x1400a1a59  pop     rdi
0x1400a1a5a  retn
```
