# LoadLibraryAndFunction(wchar_t const * const,char const * const,HINSTANCE__ * *,__int64 (**)(void))

- ea: `0x180010b08`
- end: `0x180010bd8`
- name: `?LoadLibraryAndFunction@@YAJQEB_WQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z`
- size: `208`
- prototype: `__int64 __fastcall(const wchar_t *const, const char *const, HINSTANCE *, __int64 (**)(void))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010d4c`

## callees

- `0x180004700`
- `0x180005514`
- `0x18000553c`
- `0x180010b08`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180010b89`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180010b89`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180010b9b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180010b9b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180010b5f`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180010b5f`

## string_xrefs

- `0x180010b56`: `ntdll.dll`
- `0x180010b2c`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x180010bae`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c
__int64 __fastcall LoadLibraryAndFunction(
        const wchar_t *const a1,
        const char *const a2,
        HINSTANCE *a3,
        __int64 (**a4)(void))
{
  __int64 v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  HMODULE Library; // rax
  HMODULE v10; // rdi
  __int64 (*ProcAddress)(void); // rax
  const char *v12; // r9
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a3 )
  {
    v6 = 3272;
LABEL_3:
    LastErrorFailHr = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
      (const char *)0x80004003LL,
      v13);
    return LastErrorFailHr;
  }
  if ( !a4 )
  {
    v6 = 3273;
    goto LABEL_3;
  }
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v10 = Library;
  if ( (((unsigned __int64)Library + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr((wil::details *)((char *)Library + 1));
    if ( (unsigned __int64)v10 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return LastErrorFailHr;
LABEL_9:
    FreeLibrary(v10);
    return LastErrorFailHr;
  }
  ProcAddress = GetProcAddress(Library, "RtlPublishWnfStateData");
  *a4 = ProcAddress;
  if ( !ProcAddress )
  {
    LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xCCE,
                        (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                        v12);
    goto LABEL_9;
  }
  *a3 = v10;
  return 0;
}

```

## disassembly

```asm
0x180010b08  mov     [rsp+arg_0], rbx
0x180010b0d  mov     [rsp+arg_8], rsi
0x180010b12  push    rdi; int
0x180010b13  sub     rsp, 20h
0x180010b17  mov     rsi, r9
0x180010b1a  mov     rbx, r8
0x180010b1d  test    r8, r8
0x180010b20  jnz     short loc_180010B47
0x180010b22  mov     edx, 0CC8h; void *
0x180010b27  mov     rcx, [rsp+28h]; this
0x180010b2c  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x180010b33  mov     ebx, 80004003h
0x180010b38  mov     r9d, ebx; char *
0x180010b3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b40  mov     eax, ebx
0x180010b42  jmp     loc_180010BC8
0x180010b47  test    rsi, rsi
0x180010b4a  jnz     short loc_180010B53
0x180010b4c  mov     edx, 0CC9h
0x180010b51  jmp     short loc_180010B27
0x180010b53  xor     r8d, r8d; dwFlags
0x180010b56  lea     rcx, LibFileName; "ntdll.dll"
0x180010b5d  xor     edx, edx; hFile
0x180010b5f  call    cs:__imp_LoadLibraryExW
0x180010b65  mov     rdi, rax
0x180010b68  lea     rcx, [rax+1]; this
0x180010b6c  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180010b73  jnz     short loc_180010B91
0x180010b75  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010b7a  lea     rcx, [rdi-1]
0x180010b7e  mov     ebx, eax
0x180010b80  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180010b84  ja      short loc_180010B40
0x180010b86  mov     rcx, rdi; hLibModule
0x180010b89  call    cs:__imp_FreeLibrary
0x180010b8f  jmp     short loc_180010B40
0x180010b91  lea     rdx, aRtlpublishwnfs; "RtlPublishWnfStateData"
0x180010b98  mov     rcx, rdi; hModule
0x180010b9b  call    cs:__imp_GetProcAddress
0x180010ba1  mov     [rsi], rax
0x180010ba4  test    rax, rax
0x180010ba7  jnz     short loc_180010BC3
0x180010ba9  mov     rcx, [rsp+28h]; this
0x180010bae  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x180010bb5  mov     edx, 0CCEh; void *
0x180010bba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010bbf  mov     ebx, eax
0x180010bc1  jmp     short loc_180010B86
0x180010bc3  mov     [rbx], rdi
0x180010bc6  xor     eax, eax
0x180010bc8  mov     rbx, [rsp+28h+arg_0]
0x180010bcd  mov     rsi, [rsp+28h+arg_8]
0x180010bd2  add     rsp, 20h
0x180010bd6  pop     rdi
0x180010bd7  retn
```
