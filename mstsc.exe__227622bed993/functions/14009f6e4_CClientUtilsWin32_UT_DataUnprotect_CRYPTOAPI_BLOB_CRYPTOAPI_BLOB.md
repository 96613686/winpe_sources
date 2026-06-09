# CClientUtilsWin32::UT_DataUnprotect(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *)

- ea: `0x14009f6e4`
- end: `0x14009f8eb`
- name: `?UT_DataUnprotect@CClientUtilsWin32@@SAHPEAU_CRYPTOAPI_BLOB@@0@Z`
- size: `519`
- prototype: `__int64 __fastcall(struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14003b898`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14009f6e4`
- `0x140112010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14009f726`
- `KERNEL32!LoadLibraryW` at `0x14009f726`
- `KERNEL32!FreeLibrary` at `0x14009f82e`
- `KERNEL32!FreeLibrary` at `0x14009f82e`
- `KERNEL32!GetProcAddress` at `0x14009f742`
- `KERNEL32!GetProcAddress` at `0x14009f742`
- `KERNEL32!GetLastError` at `0x14009f780`
- `KERNEL32!GetLastError` at `0x14009f7f9`
- `KERNEL32!GetLastError` at `0x14009f862`
- `KERNEL32!GetLastError` at `0x14009f780`
- `KERNEL32!GetLastError` at `0x14009f7f9`
- `KERNEL32!GetLastError` at `0x14009f862`

## string_xrefs

- `0x14009f71f`: `crypt32.dll`

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
0x14009f6e4  mov     [rsp+arg_0], rbx
0x14009f6e9  mov     [rsp+arg_8], rsi
0x14009f6ee  push    rdi
0x14009f6ef  sub     rsp, 40h
0x14009f6f3  mov     rbx, rdx
0x14009f6f6  mov     rdi, rcx
0x14009f6f9  test    rcx, rcx
0x14009f6fc  jz      loc_14009F894
0x14009f702  cmp     dword ptr [rcx], 0
0x14009f705  jz      loc_14009F894
0x14009f70b  cmp     qword ptr [rcx+8], 0
0x14009f710  jz      loc_14009F894
0x14009f716  test    rdx, rdx
0x14009f719  jz      loc_14009F894
0x14009f71f  lea     rcx, aCrypt32Dll_0; "crypt32.dll"
0x14009f726  call    cs:__imp_LoadLibraryW
0x14009f72c  mov     rsi, rax
0x14009f72f  test    rax, rax
0x14009f732  jz      loc_14009F83B
0x14009f738  lea     rdx, aCryptunprotect_1; "CryptUnprotectData"
0x14009f73f  mov     rcx, rax; hModule
0x14009f742  call    cs:__imp_GetProcAddress
0x14009f748  test    rax, rax
0x14009f74b  jz      loc_14009F7D6
0x14009f751  mov     [rsp+48h+var_18], rbx
0x14009f756  xor     r9d, r9d
0x14009f759  mov     ebx, 1
0x14009f75e  xor     r8d, r8d
0x14009f761  mov     [rsp+48h+var_20], ebx
0x14009f765  xor     edx, edx
0x14009f767  mov     rcx, rdi
0x14009f76a  mov     [rsp+48h+var_28], 0
0x14009f773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f778  test    eax, eax
0x14009f77a  jnz     loc_14009F82B
0x14009f780  call    cs:__imp_GetLastError
0x14009f786  mov     edi, eax
0x14009f788  mov     rdx, cs:WPP_GLOBAL_Control
0x14009f78f  lea     rcx, WPP_GLOBAL_Control
0x14009f796  cmp     rdx, rcx
0x14009f799  jz      loc_14009F829
0x14009f79f  test    [rdx+1Ch], bl
0x14009f7a2  jz      loc_14009F829
0x14009f7a8  cmp     byte ptr [rdx+19h], 2
0x14009f7ac  jb      short loc_14009F829
0x14009f7ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009f7b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f7ba  lea     edx, [rbx+36h]
0x14009f7bd  mov     r9d, eax
0x14009f7c0  mov     dword ptr [rsp+48h+var_28], edi
0x14009f7c4  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009f7cb  mov     rcx, [rcx+10h]
0x14009f7cf  call    WPP_SF_Dd
0x14009f7d4  jmp     short loc_14009F829
0x14009f7d6  mov     rax, cs:WPP_GLOBAL_Control
0x14009f7dd  lea     rcx, WPP_GLOBAL_Control
0x14009f7e4  cmp     rax, rcx
0x14009f7e7  jz      short loc_14009F829
0x14009f7e9  mov     ebx, 1
0x14009f7ee  test    [rax+1Ch], bl
0x14009f7f1  jz      short loc_14009F829
0x14009f7f3  cmp     byte ptr [rax+19h], 2
0x14009f7f7  jb      short loc_14009F829
0x14009f7f9  call    cs:__imp_GetLastError
0x14009f7ff  mov     ebx, eax
0x14009f801  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009f806  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f80d  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009f814  mov     edx, 38h ; '8'
0x14009f819  mov     dword ptr [rsp+48h+var_28], ebx
0x14009f81d  mov     r9d, eax
0x14009f820  mov     rcx, [rcx+10h]
0x14009f824  call    WPP_SF_Dd
0x14009f829  xor     ebx, ebx
0x14009f82b  mov     rcx, rsi; hLibModule
0x14009f82e  call    cs:__imp_FreeLibrary
0x14009f834  mov     eax, ebx
0x14009f836  jmp     loc_14009F8DB
0x14009f83b  mov     rax, cs:WPP_GLOBAL_Control
0x14009f842  lea     rcx, WPP_GLOBAL_Control
0x14009f849  cmp     rax, rcx
0x14009f84c  jz      loc_14009F8D9
0x14009f852  mov     ebx, 1
0x14009f857  test    [rax+1Ch], bl
0x14009f85a  jz      short loc_14009F8D9
0x14009f85c  cmp     byte ptr [rax+19h], 2
0x14009f860  jb      short loc_14009F8D9
0x14009f862  call    cs:__imp_GetLastError
0x14009f868  mov     ebx, eax
0x14009f86a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009f86f  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f876  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009f87d  mov     edx, 36h ; '6'
0x14009f882  mov     dword ptr [rsp+48h+var_28], ebx
0x14009f886  mov     r9d, eax
0x14009f889  mov     rcx, [rcx+10h]
0x14009f88d  call    WPP_SF_Dd
0x14009f892  jmp     short loc_14009F8D9
0x14009f894  mov     rax, cs:WPP_GLOBAL_Control
0x14009f89b  lea     rcx, WPP_GLOBAL_Control
0x14009f8a2  cmp     rax, rcx
0x14009f8a5  jz      short loc_14009F8D9
0x14009f8a7  mov     ebx, 1
0x14009f8ac  test    [rax+1Ch], bl
0x14009f8af  jz      short loc_14009F8D9
0x14009f8b1  cmp     byte ptr [rax+19h], 2
0x14009f8b5  jb      short loc_14009F8D9
0x14009f8b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009f8bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f8c3  lea     edx, [rbx+38h]
0x14009f8c6  mov     r9d, eax
0x14009f8c9  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009f8d0  mov     rcx, [rcx+10h]
0x14009f8d4  call    WPP_SF_d
0x14009f8d9  xor     eax, eax
0x14009f8db  mov     rbx, [rsp+48h+arg_0]
0x14009f8e0  mov     rsi, [rsp+48h+arg_8]
0x14009f8e5  add     rsp, 40h
0x14009f8e9  pop     rdi
0x14009f8ea  retn
```
