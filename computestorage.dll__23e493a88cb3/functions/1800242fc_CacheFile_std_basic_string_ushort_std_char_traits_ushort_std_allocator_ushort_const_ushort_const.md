# CacheFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *)

- ea: `0x1800242fc`
- end: `0x1800244c3`
- name: `?CacheFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `455`
- prototype: `__int64 __fastcall(__int64 *, const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800244d0`

## callees

- `0x180002690`
- `0x1800242fc`
- `0x180024e70`
- `0x180024ed0`
- `0x180024f28`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024348`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024348`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002449c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002449c`
- `ntdll!NtSetCachedSigningLevel2` at `0x1800243f4`
- `ntdll!NtSetCachedSigningLevel2` at `0x1800243f4`

## string_xrefs

- `0x18002436d`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180024457`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180024486`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CacheFile(__int64 *a1, const WCHAR *a2)
{
  char *FileW; // rbx
  unsigned int LastErrorMsg; // edi
  bool v6; // cc
  __int64 *v7; // rcx
  __int16 v8; // ax
  int v9; // eax
  __int64 v10; // rdx
  char *v12; // [rsp+50h] [rbp+7h] BYREF
  __int64 v13; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v14; // [rsp+60h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  FileW = (char *)CreateFileW(a2, 1u, 5u, 0, 3u, 0x80u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v6 = (unsigned __int64)a1[3] <= 7;
    v14 = 0;
    v12 = FileW;
    v13 = 24;
    if ( v6 )
      v7 = a1;
    else
      v7 = (__int64 *)*a1;
    v8 = 2 * *((_WORD *)a1 + 8);
    *((_QWORD *)&v14 + 1) = v7;
    LOWORD(v14) = v8;
    WORD1(v14) = v8;
    DWORD1(v14) = 0;
    v9 = NtSetCachedSigningLevel2(4, 0, &v12, 1, FileW, &v13);
    if ( (v9 & 0xFFF0000) == 0xE90000 )
    {
      v10 = 201;
LABEL_16:
      wil::details::in1diag3::Log_NtStatusMsg(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        (const char *)(unsigned int)v9,
        (int)"%ls",
        (const char *)a2);
      goto LABEL_17;
    }
    if ( v9 != -1073741701 && v9 != -1073741279 )
    {
      if ( v9 == -1073740760 )
        goto LABEL_17;
      if ( ((v9 + 1073740285) & 0xFFFFFFFD) != 0 )
      {
        if ( v9 <= -1 )
        {
          LastErrorMsg = wil::details::in1diag3::Return_NtStatusMsg(
                           retaddr,
                           (void *)0xDB,
                           (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
                           (const char *)(unsigned int)v9,
                           (int)"%ls",
                           (const char *)a2);
LABEL_18:
          CloseHandle(FileW);
          return LastErrorMsg;
        }
LABEL_17:
        LastErrorMsg = 0;
        goto LABEL_18;
      }
    }
    v10 = 215;
    goto LABEL_16;
  }
  LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                   retaddr,
                   (void *)0xB5,
                   (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
                   "%ls",
                   (const char *)a2);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_18;
  return LastErrorMsg;
}

```

## disassembly

```asm
0x1800242fc  push    rbp
0x1800242fe  push    rbx
0x1800242ff  push    rsi
0x180024300  push    rdi
0x180024301  lea     rbp, [rsp-3Fh]
0x180024306  sub     rsp, 88h
0x18002430d  mov     rax, cs:__security_cookie
0x180024314  xor     rax, rsp
0x180024317  mov     [rbp+57h+var_30], rax
0x18002431b  xor     r9d, r9d; lpSecurityAttributes
0x18002431e  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x180024327  mov     rsi, rdx
0x18002432a  mov     [rsp+0A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180024332  mov     rdi, rcx
0x180024335  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002433d  mov     rcx, rsi; lpFileName
0x180024340  lea     edx, [r9+1]; dwDesiredAccess
0x180024344  lea     r8d, [r9+5]; dwShareMode
0x180024348  call    cs:__imp_CreateFileW
0x18002434f  nop     dword ptr [rax+rax+00h]
0x180024354  mov     rbx, rax
0x180024357  inc     rax
0x18002435a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180024360  jnz     short loc_180024398
0x180024362  mov     rcx, [rbp+5Fh]; this
0x180024366  lea     r9, aLs; "%ls"
0x18002436d  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180024374  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rsi; char *
0x180024379  mov     edx, 0B5h; void *
0x18002437e  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180024383  lea     rcx, [rbx-1]
0x180024387  mov     edi, eax
0x180024389  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002438d  ja      loc_1800244A8
0x180024393  jmp     loc_180024499
0x180024398  cmp     qword ptr [rdi+18h], 7
0x18002439d  xorps   xmm0, xmm0
0x1800243a0  movups  [rbp+57h+var_40], xmm0
0x1800243a4  mov     [rbp+57h+var_50], rbx
0x1800243a8  mov     [rbp+57h+var_48], 18h
0x1800243b0  jbe     short loc_1800243B7
0x1800243b2  mov     rcx, [rdi]
0x1800243b5  jmp     short loc_1800243BA
0x1800243b7  mov     rcx, rdi
0x1800243ba  movzx   eax, word ptr [rdi+10h]
0x1800243be  lea     r8, [rbp+57h+var_50]
0x1800243c2  add     ax, ax
0x1800243c5  mov     qword ptr [rbp+57h+var_40+8], rcx
0x1800243c9  mov     word ptr [rbp+57h+var_40], ax
0x1800243cd  xor     edx, edx
0x1800243cf  mov     word ptr [rbp+57h+var_40+2], ax
0x1800243d3  mov     r9d, 1
0x1800243d9  movups  [rbp+57h+var_60], xmm0
0x1800243dd  mov     eax, dword ptr [rbp+57h+var_60+4]
0x1800243e0  mov     dword ptr [rbp+57h+var_40+4], eax
0x1800243e3  lea     ecx, [rdx+4]
0x1800243e6  lea     rax, [rbp+57h+var_48]
0x1800243ea  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rax
0x1800243ef  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rbx
0x1800243f4  call    cs:__imp_NtSetCachedSigningLevel2
0x1800243fb  nop     dword ptr [rax+rax+00h]
0x180024400  mov     ecx, eax
0x180024402  mov     r9d, eax; char *
0x180024405  and     ecx, 0FFF0000h
0x18002440b  cmp     ecx, 0E90000h
0x180024411  jnz     short loc_18002441A
0x180024413  mov     edx, 0C9h
0x180024418  jmp     short loc_180024476
0x18002441a  cmp     r9d, 0C000007Bh
0x180024421  jz      short loc_180024471
0x180024423  cmp     r9d, 0C0000221h
0x18002442a  jz      short loc_180024471
0x18002442c  cmp     r9d, 0C0000428h
0x180024433  jz      short loc_180024497
0x180024435  add     eax, 3FFFF9FDh
0x18002443a  test    eax, 0FFFFFFFDh
0x18002443f  jz      short loc_180024471
0x180024441  cmp     r9d, 0FFFFFFFFh
0x180024445  jg      short loc_180024497
0x180024447  mov     rcx, [rbp+5Fh]; this
0x18002444b  lea     rax, aLs; "%ls"
0x180024452  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rsi; char *
0x180024457  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18002445e  mov     edx, 0DBh; void *
0x180024463  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax; int
0x180024468  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18002446d  mov     edi, eax
0x18002446f  jmp     short loc_180024499
0x180024471  mov     edx, 0D7h; void *
0x180024476  mov     rcx, [rbp+5Fh]; this
0x18002447a  lea     rax, aLs; "%ls"
0x180024481  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rsi; char *
0x180024486  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18002448d  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax; int
0x180024492  call    ?Log_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180024497  xor     edi, edi
0x180024499  mov     rcx, rbx; hObject
0x18002449c  call    cs:__imp_CloseHandle
0x1800244a3  nop     dword ptr [rax+rax+00h]
0x1800244a8  mov     eax, edi
0x1800244aa  mov     rcx, [rbp+57h+var_30]
0x1800244ae  xor     rcx, rsp; StackCookie
0x1800244b1  call    __security_check_cookie
0x1800244b6  add     rsp, 88h
0x1800244bd  pop     rdi
0x1800244be  pop     rsi
0x1800244bf  pop     rbx
0x1800244c0  pop     rbp
0x1800244c1  retn
```
