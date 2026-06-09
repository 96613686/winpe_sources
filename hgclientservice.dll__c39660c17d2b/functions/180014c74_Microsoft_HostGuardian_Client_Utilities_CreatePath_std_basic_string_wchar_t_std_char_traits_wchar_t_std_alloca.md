# Microsoft::HostGuardian::Client::Utilities::CreatePath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180014c74`
- end: `0x180014e6e`
- name: `?CreatePath@Utilities@Client@HostGuardian@Microsoft@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `506`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180011848`

## callees

- `0x180001794`
- `0x180002ab0`
- `0x180002e55`
- `0x1800073c4`
- `0x180008760`
- `0x18000a7bc`
- `0x18000e7b4`
- `0x18001477c`
- `0x1800147f8`
- `0x180014c74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014df0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014df0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014dc2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014de6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014dc2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014de6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014dad`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014dad`

## string_xrefs

- `0x180014e23`: `servercommon\base\securehostingservice\common\service\lib\utilities.cpp`
- `0x180014e35`: `servercommon\base\securehostingservice\common\service\lib\utilities.cpp`
- `0x180014e5c`: `servercommon\base\securehostingservice\common\service\lib\utilities.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Utilities::CreatePath(_QWORD *a1)
{
  _BYTE **v1; // rdi
  bool v2; // cc
  _BYTE *v3; // rax
  _BYTE *v4; // rsi
  signed __int64 v5; // rbp
  unsigned __int64 v6; // rbx
  size_t v7; // rbx
  WCHAR *v8; // rax
  void *v9; // rax
  void *v10; // rcx
  const WCHAR *v11; // r14
  unsigned __int64 i; // rsi
  unsigned __int64 v13; // rax
  _BYTE **v14; // r15
  __int64 v15; // rbx
  __int64 trivial_2; // rax
  __int64 v17; // rsi
  DWORD FileAttributesW; // eax
  const char *v19; // r9
  const char *v20; // r9
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-58h] BYREF
  const WCHAR *v24; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v26; // [rsp+80h] [rbp+8h] BYREF

  v1 = (_BYTE **)a1;
  v2 = a1[3] <= 7u;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v3 = v1[2];
  if ( v2 )
    v4 = v1;
  else
    v4 = *v1;
  *(_OWORD *)lpFileName = 0;
  v24 = 0;
  v5 = (char *)a1 + 2 * (_QWORD)v3 - v4;
  v6 = v5 >> 1;
  if ( v5 >> 1 )
  {
    if ( v6 > 0x7FFFFFFFFFFFFFFFLL )
      std::vector<wchar_t>::_Xlength();
    v7 = 2 * v6;
    if ( v7 )
    {
      if ( v7 < 0x1000 )
      {
        v8 = (WCHAR *)operator new(v7);
      }
      else
      {
        if ( v7 + 39 < v7 )
          __scrt_throw_std_bad_array_new_length();
        v9 = operator new(v7 + 39);
        v10 = v9;
        if ( !v9 )
          __fastfail(5u);
        v8 = (WCHAR *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v8 - 1) = v10;
      }
    }
    else
    {
      v8 = 0;
    }
    lpFileName[0] = v8;
    v24 = &v8[v7 / 2];
    memmove_0(v8, v4, v5);
    lpFileName[1] = v24;
    v26 = 0;
    std::_Tidy_guard<std::vector<wchar_t>>::~_Tidy_guard<std::vector<wchar_t>>(&v26);
  }
  v11 = lpFileName[0];
  for ( i = 0; ; i = v17 + 1 )
  {
    v13 = (unsigned __int64)v1[2];
    v14 = (unsigned __int64)v1[3] <= 7 ? v1 : (_BYTE **)*v1;
    if ( i >= v13 )
      break;
    v15 = (__int64)v14 + 2 * v13;
    trivial_2 = _std_find_trivial_2((char *)v14 + 2 * i, v15, 92);
    if ( trivial_2 == v15 )
      break;
    v17 = (trivial_2 - (__int64)v14) >> 1;
    if ( v17 == -1 )
      break;
    v11[v17] = 0;
    FileAttributesW = GetFileAttributesW(v11);
    if ( FileAttributesW == -1 )
    {
      if ( !CreateDirectoryW(v11, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x86,
          (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\utilities.cpp",
          v19);
    }
    else if ( (FileAttributesW & 0x10) == 0 )
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\utilities.cpp",
        (const char *)0x8007139FLL,
        (int)lpFileName[0]);
    }
    v11[v17] = 92;
  }
  if ( !CreateDirectoryW(v11, 0) && GetLastError() != 183 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x75,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\utilities.cpp",
      v20);
  return std::vector<wchar_t>::~vector<wchar_t>(lpFileName);
}

```

## disassembly

```asm
0x180014c74  push    rbx
0x180014c76  push    rbp
0x180014c77  push    rsi
0x180014c78  push    rdi
0x180014c79  push    r14
0x180014c7b  push    r15
0x180014c7d  sub     rsp, 48h
0x180014c81  mov     rdi, rcx
0x180014c84  cmp     qword ptr [rcx+18h], 7
0x180014c89  jbe     short loc_180014C8E
0x180014c8b  mov     rcx, [rcx]
0x180014c8e  mov     rax, [rdi+10h]
0x180014c92  lea     rbp, [rcx+rax*2]
0x180014c96  jbe     short loc_180014C9D
0x180014c98  mov     rsi, [rdi]
0x180014c9b  jmp     short loc_180014CA0
0x180014c9d  mov     rsi, rdi
0x180014ca0  xorps   xmm0, xmm0
0x180014ca3  movdqu  xmmword ptr [rsp+78h+lpFileName], xmm0
0x180014ca9  mov     [rsp+78h+var_48], 0
0x180014cb2  sub     rbp, rsi
0x180014cb5  mov     rbx, rbp
0x180014cb8  sar     rbx, 1
0x180014cbb  jz      loc_180014D5A
0x180014cc1  mov     rax, 7FFFFFFFFFFFFFFFh
0x180014ccb  cmp     rbx, rax
0x180014cce  ja      loc_180014E4A
0x180014cd4  add     rbx, rbx
0x180014cd7  jnz     short loc_180014CDD
0x180014cd9  xor     eax, eax
0x180014cdb  jmp     short loc_180014D1B
0x180014cdd  cmp     rbx, 1000h
0x180014ce4  jb      short loc_180014D13
0x180014ce6  lea     rcx, [rbx+27h]; Size
0x180014cea  cmp     rcx, rbx
0x180014ced  jbe     loc_180014E50
0x180014cf3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014cf8  mov     rcx, rax
0x180014cfb  test    rax, rax
0x180014cfe  jnz     short loc_180014D05
0x180014d00  lea     ecx, [rax+5]
0x180014d03  int     29h; Win8: RtlFailFast(ecx)
0x180014d05  add     rax, 27h ; '''
0x180014d09  and     rax, 0FFFFFFFFFFFFFFE0h
0x180014d0d  mov     [rax-8], rcx
0x180014d11  jmp     short loc_180014D1B
0x180014d13  mov     rcx, rbx; Size
0x180014d16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014d1b  mov     [rsp+78h+lpFileName], rax; int
0x180014d20  mov     [rsp+78h+lpFileName+8], rax
0x180014d25  add     rbx, rax
0x180014d28  mov     [rsp+78h+var_48], rbx
0x180014d2d  mov     r8, rbp; Size
0x180014d30  mov     rdx, rsi; Src
0x180014d33  mov     rcx, rax; void *
0x180014d36  call    memmove_0
0x180014d3b  mov     [rsp+78h+lpFileName+8], rbx
0x180014d40  mov     [rsp+78h+arg_0], 0
0x180014d4c  lea     rcx, [rsp+78h+arg_0]
0x180014d54  call    ??1?$_Tidy_guard@V?$vector@_WV?$allocator@_W@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<wchar_t>>::~_Tidy_guard<std::vector<wchar_t>>(void)
0x180014d59  nop
0x180014d5a  mov     r14, [rsp+78h+lpFileName]
0x180014d5f  xor     esi, esi
0x180014d61  lea     ebp, [rsi+5Ch]
0x180014d64  mov     rax, [rdi+10h]
0x180014d68  cmp     qword ptr [rdi+18h], 7
0x180014d6d  jbe     short loc_180014D74
0x180014d6f  mov     r15, [rdi]
0x180014d72  jmp     short loc_180014D77
0x180014d74  mov     r15, rdi
0x180014d77  cmp     rsi, rax
0x180014d7a  jnb     short loc_180014DE1
0x180014d7c  lea     rbx, [r15+rax*2]
0x180014d80  mov     r8d, ebp
0x180014d83  lea     rcx, [r15+rsi*2]
0x180014d87  mov     rdx, rbx
0x180014d8a  call    __std_find_trivial_2
0x180014d8f  mov     rsi, rax
0x180014d92  cmp     rax, rbx
0x180014d95  jz      short loc_180014DE1
0x180014d97  sub     rsi, r15
0x180014d9a  sar     rsi, 1
0x180014d9d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180014da1  jz      short loc_180014DE1
0x180014da3  xor     ecx, ecx
0x180014da5  mov     [r14+rsi*2], cx
0x180014daa  mov     rcx, r14; lpFileName
0x180014dad  call    cs:__imp_GetFileAttributesW
0x180014db3  cmp     eax, 0FFFFFFFFh
0x180014db6  jnz     short loc_180014DCE
0x180014db8  mov     rbx, [rsp+78h]
0x180014dbd  xor     edx, edx; lpSecurityAttributes
0x180014dbf  mov     rcx, r14; lpPathName
0x180014dc2  call    cs:__imp_CreateDirectoryW
0x180014dc8  test    eax, eax
0x180014dca  jz      short loc_180014E35
0x180014dcc  jmp     short loc_180014DD7
0x180014dce  mov     rcx, [rsp+78h]; this
0x180014dd3  test    al, 10h
0x180014dd5  jz      short loc_180014E56
0x180014dd7  mov     [r14+rsi*2], bp
0x180014ddc  inc     rsi
0x180014ddf  jmp     short loc_180014D64
0x180014de1  xor     edx, edx; lpSecurityAttributes
0x180014de3  mov     rcx, r14; lpPathName
0x180014de6  call    cs:__imp_CreateDirectoryW
0x180014dec  test    eax, eax
0x180014dee  jnz     short loc_180014E01
0x180014df0  call    cs:__imp_GetLastError
0x180014df6  cmp     eax, 0B7h
0x180014dfb  jz      short loc_180014E01
0x180014dfd  mov     al, 1
0x180014dff  jmp     short loc_180014E03
0x180014e01  xor     al, al
0x180014e03  mov     rcx, [rsp+78h]; this
0x180014e08  test    al, al
0x180014e0a  jnz     short loc_180014E23
0x180014e0c  lea     rcx, [rsp+78h+lpFileName]
0x180014e11  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x180014e16  add     rsp, 48h
0x180014e1a  pop     r15
0x180014e1c  pop     r14
0x180014e1e  pop     rdi
0x180014e1f  pop     rsi
0x180014e20  pop     rbp
0x180014e21  pop     rbx
0x180014e22  retn
0x180014e23  lea     r8, aServercommonBa_2; "servercommon\\base\\securehostingservic"...
0x180014e2a  mov     edx, 75h ; 'u'; void *
0x180014e2f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180014e35  lea     r8, aServercommonBa_2; "servercommon\\base\\securehostingservic"...
0x180014e3c  mov     edx, 86h; void *
0x180014e41  mov     rcx, rbx; this
0x180014e44  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180014e4a  call    ?_Xlength@?$vector@_WV?$allocator@_W@std@@@std@@CAXXZ; std::vector<wchar_t>::_Xlength(void)
0x180014e50  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180014e56  mov     r9d, 8007139Fh; char *
0x180014e5c  lea     r8, aServercommonBa_2; "servercommon\\base\\securehostingservic"...
0x180014e63  mov     edx, 8Bh; void *
0x180014e68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
