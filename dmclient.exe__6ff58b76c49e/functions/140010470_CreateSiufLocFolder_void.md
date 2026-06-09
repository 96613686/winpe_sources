# CreateSiufLocFolder(void)

- ea: `0x140010470`
- end: `0x1400105d1`
- name: `?CreateSiufLocFolder@@YAJXZ`
- size: `353`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c47c`

## callees

- `0x140001414`
- `0x14000fc30`
- `0x140010470`
- `0x1400187b2`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001058c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001058c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140010582`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140010582`

## string_xrefs

- `0x1400104f9`: `CreateSiufLocFolder`
- `0x140010529`: `BuildSiufLocFolderPath failed to build loc folder string.`

## pseudocode

```c
__int64 CreateSiufLocFolder(void)
{
  unsigned int v0; // edx
  int v1; // ebx
  int v2; // r9d
  signed int LastError; // eax
  int v5; // [rsp+50h] [rbp-B0h] BYREF
  int v6; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v7; // [rsp+58h] [rbp-A8h] BYREF
  const char *v8; // [rsp+60h] [rbp-A0h] BYREF
  const char *v9; // [rsp+68h] [rbp-98h] BYREF
  const char *v10; // [rsp+70h] [rbp-90h] BYREF
  WCHAR PathName[264]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(PathName, 0, 0x208u);
  v1 = BuildSiufLocFolderPath(PathName, v0);
  if ( v1 >= 0 )
  {
    if ( !CreateDirectoryW(PathName, 0) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError == 183 )
      {
        return 458935;
      }
      else if ( LastError > 0 )
      {
        return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else if ( (unsigned int)dword_140027000 > 2
         && (qword_140027010 & 0x400000000000LL) != 0
         && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
  {
    v7 = 0x1000000;
    v8 = "CreateSiufLocFolder";
    v5 = 314;
    v9 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
    v10 = "BuildSiufLocFolderPath failed to build loc folder string.";
    v6 = v1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      qword_140027010,
      (unsigned int)byte_140021FE3,
      0,
      v2,
      (__int64)&v10,
      (__int64)&v6,
      (__int64)&v9,
      (__int64)&v8,
      (__int64)&v5,
      (__int64)&v7);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140010470  mov     [rsp-8+arg_0], rbx
0x140010475  push    rbp
0x140010476  lea     rbp, [rsp-1A0h]
0x14001047e  sub     rsp, 2A0h
0x140010485  mov     rax, cs:__security_cookie
0x14001048c  xor     rax, rsp
0x14001048f  mov     [rbp+1A0h+var_10], rax
0x140010496  xor     edx, edx; Val
0x140010498  lea     rcx, [rbp+1A0h+PathName]; void *
0x14001049c  mov     r8d, 208h; Size
0x1400104a2  call    memset_0
0x1400104a7  lea     rcx, [rbp+1A0h+PathName]; unsigned __int16 *
0x1400104ab  call    ?BuildSiufLocFolderPath@@YAJPEAGI@Z; BuildSiufLocFolderPath(ushort *,uint)
0x1400104b0  mov     ebx, eax
0x1400104b2  test    eax, eax
0x1400104b4  jns     loc_14001057C
0x1400104ba  mov     ecx, cs:dword_140027000
0x1400104c0  cmp     ecx, 2
0x1400104c3  jbe     loc_1400105AF
0x1400104c9  mov     rdx, cs:qword_140027018
0x1400104d0  mov     r8, 400000000000h
0x1400104da  mov     rcx, cs:qword_140027010
0x1400104e1  test    r8, rcx
0x1400104e4  jz      loc_1400105AF
0x1400104ea  mov     rax, rdx
0x1400104ed  and     rax, r8
0x1400104f0  cmp     rax, rdx
0x1400104f3  jnz     loc_1400105AF
0x1400104f9  lea     rax, aCreatesiuflocf; "CreateSiufLocFolder"
0x140010500  mov     [rsp+2A0h+var_248], 1000000h
0x140010509  mov     [rsp+2A0h+var_240], rax
0x14001050e  lea     rdx, byte_140021FE3
0x140010515  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14001051c  mov     [rsp+2A0h+var_250], 13Ah
0x140010524  mov     [rsp+2A0h+var_238], rax
0x140010529  lea     rax, aBuildsiuflocfo_0; "BuildSiufLocFolderPath failed to build "...
0x140010530  mov     [rsp+2A0h+var_230], rax
0x140010535  lea     rax, [rsp+2A0h+var_248]
0x14001053a  mov     [rsp+2A0h+var_258], rax
0x14001053f  lea     rax, [rsp+2A0h+var_250]
0x140010544  mov     [rsp+2A0h+var_260], rax
0x140010549  lea     rax, [rsp+2A0h+var_240]
0x14001054e  mov     [rsp+2A0h+var_268], rax
0x140010553  lea     rax, [rsp+2A0h+var_238]
0x140010558  mov     [rsp+2A0h+var_270], rax
0x14001055d  lea     rax, [rsp+2A0h+var_24C]
0x140010562  mov     [rsp+2A0h+var_278], rax
0x140010567  lea     rax, [rsp+2A0h+var_230]
0x14001056c  mov     [rsp+2A0h+var_280], rax
0x140010571  mov     [rsp+2A0h+var_24C], ebx
0x140010575  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14001057a  jmp     short loc_1400105AF
0x14001057c  xor     edx, edx; lpSecurityAttributes
0x14001057e  lea     rcx, [rbp+1A0h+PathName]; lpPathName
0x140010582  call    cs:__imp_CreateDirectoryW
0x140010588  test    eax, eax
0x14001058a  jnz     short loc_1400105AF
0x14001058c  call    cs:__imp_GetLastError
0x140010592  mov     ebx, eax
0x140010594  cmp     eax, 0B7h
0x140010599  jnz     short loc_1400105A2
0x14001059b  mov     ebx, 700B7h
0x1400105a0  jmp     short loc_1400105AF
0x1400105a2  test    eax, eax
0x1400105a4  jle     short loc_1400105AF
0x1400105a6  movzx   ebx, ax
0x1400105a9  or      ebx, 80070000h
0x1400105af  mov     eax, ebx
0x1400105b1  mov     rcx, [rbp+1A0h+var_10]
0x1400105b8  xor     rcx, rsp; StackCookie
0x1400105bb  call    __security_check_cookie
0x1400105c0  mov     rbx, [rsp+2A0h+arg_0]
0x1400105c8  add     rsp, 2A0h
0x1400105cf  pop     rbp
0x1400105d0  retn
```
