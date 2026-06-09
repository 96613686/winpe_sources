# CreateSiufLocFolder(void)

- ea: `0x140010acc`
- end: `0x140010c3a`
- name: `?CreateSiufLocFolder@@YAJXZ`
- size: `366`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c928`

## callees

- `0x140001418`
- `0x1400101fc`
- `0x140010acc`
- `0x1400195e2`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010bee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010bee`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140010bde`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140010bde`

## string_xrefs

- `0x140010b55`: `CreateSiufLocFolder`
- `0x140010b85`: `BuildSiufLocFolderPath failed to build loc folder string.`

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
  else if ( (unsigned int)dword_140028000 > 2
         && (qword_140028010 & 0x400000000000LL) != 0
         && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
  {
    v7 = 0x1000000;
    v8 = "CreateSiufLocFolder";
    v5 = 314;
    v9 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
    v10 = "BuildSiufLocFolderPath failed to build loc folder string.";
    v6 = v1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      qword_140028010,
      (unsigned int)byte_140022FEB,
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
0x140010acc  mov     [rsp-8+arg_0], rbx
0x140010ad1  push    rbp
0x140010ad2  lea     rbp, [rsp-1A0h]
0x140010ada  sub     rsp, 2A0h
0x140010ae1  mov     rax, cs:__security_cookie
0x140010ae8  xor     rax, rsp
0x140010aeb  mov     [rbp+1A0h+var_10], rax
0x140010af2  xor     edx, edx; Val
0x140010af4  lea     rcx, [rbp+1A0h+PathName]; void *
0x140010af8  mov     r8d, 208h; Size
0x140010afe  call    memset_0
0x140010b03  lea     rcx, [rbp+1A0h+PathName]; unsigned __int16 *
0x140010b07  call    ?BuildSiufLocFolderPath@@YAJPEAGI@Z; BuildSiufLocFolderPath(ushort *,uint)
0x140010b0c  mov     ebx, eax
0x140010b0e  test    eax, eax
0x140010b10  jns     loc_140010BD8
0x140010b16  mov     ecx, cs:dword_140028000
0x140010b1c  cmp     ecx, 2
0x140010b1f  jbe     loc_140010C17
0x140010b25  mov     rdx, cs:qword_140028018
0x140010b2c  mov     r8, 400000000000h
0x140010b36  mov     rcx, cs:qword_140028010
0x140010b3d  test    r8, rcx
0x140010b40  jz      loc_140010C17
0x140010b46  mov     rax, rdx
0x140010b49  and     rax, r8
0x140010b4c  cmp     rax, rdx
0x140010b4f  jnz     loc_140010C17
0x140010b55  lea     rax, aCreatesiuflocf; "CreateSiufLocFolder"
0x140010b5c  mov     [rsp+2A0h+var_248], 1000000h
0x140010b65  mov     [rsp+2A0h+var_240], rax
0x140010b6a  lea     rdx, byte_140022FEB
0x140010b71  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010b78  mov     [rsp+2A0h+var_250], 13Ah
0x140010b80  mov     [rsp+2A0h+var_238], rax
0x140010b85  lea     rax, aBuildsiuflocfo_0; "BuildSiufLocFolderPath failed to build "...
0x140010b8c  mov     [rsp+2A0h+var_230], rax
0x140010b91  lea     rax, [rsp+2A0h+var_248]
0x140010b96  mov     [rsp+2A0h+var_258], rax
0x140010b9b  lea     rax, [rsp+2A0h+var_250]
0x140010ba0  mov     [rsp+2A0h+var_260], rax
0x140010ba5  lea     rax, [rsp+2A0h+var_240]
0x140010baa  mov     [rsp+2A0h+var_268], rax
0x140010baf  lea     rax, [rsp+2A0h+var_238]
0x140010bb4  mov     [rsp+2A0h+var_270], rax
0x140010bb9  lea     rax, [rsp+2A0h+var_24C]
0x140010bbe  mov     [rsp+2A0h+var_278], rax
0x140010bc3  lea     rax, [rsp+2A0h+var_230]
0x140010bc8  mov     [rsp+2A0h+var_280], rax
0x140010bcd  mov     [rsp+2A0h+var_24C], ebx
0x140010bd1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140010bd6  jmp     short loc_140010C17
0x140010bd8  xor     edx, edx; lpSecurityAttributes
0x140010bda  lea     rcx, [rbp+1A0h+PathName]; lpPathName
0x140010bde  call    cs:__imp_CreateDirectoryW
0x140010be5  nop     dword ptr [rax+rax+00h]
0x140010bea  test    eax, eax
0x140010bec  jnz     short loc_140010C17
0x140010bee  call    cs:__imp_GetLastError
0x140010bf5  nop     dword ptr [rax+rax+00h]
0x140010bfa  mov     ebx, eax
0x140010bfc  cmp     eax, 0B7h
0x140010c01  jnz     short loc_140010C0A
0x140010c03  mov     ebx, 700B7h
0x140010c08  jmp     short loc_140010C17
0x140010c0a  test    eax, eax
0x140010c0c  jle     short loc_140010C17
0x140010c0e  movzx   ebx, ax
0x140010c11  or      ebx, 80070000h
0x140010c17  mov     eax, ebx
0x140010c19  mov     rcx, [rbp+1A0h+var_10]
0x140010c20  xor     rcx, rsp; StackCookie
0x140010c23  call    __security_check_cookie
0x140010c28  mov     rbx, [rsp+2A0h+arg_0]
0x140010c30  add     rsp, 2A0h
0x140010c37  pop     rbp
0x140010c38  retn
```
