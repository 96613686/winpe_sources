# EnsureDirectoryExistsHr(wil::basic_zstring_view<wchar_t> const &)

- ea: `0x180010124`
- end: `0x18001034f`
- name: `?EnsureDirectoryExistsHr@@YAJAEBV?$basic_zstring_view@_W@wil@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008fd8`
- `0x18000be70`

## callees

- `0x180001540`
- `0x180003648`
- `0x1800036b4`
- `0x180007b64`
- `0x180007fd0`
- `0x180008414`
- `0x18000c030`
- `0x18000ffa4`
- `0x180010124`
- `0x1800104d4`
- `0x18001084c`
- `0x180010c44`
- `0x180013394`
- `0x180013774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102ff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800101fb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800102f5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800101fb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800102f5`

## string_xrefs

- `0x1800102b9`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c
__int64 __fastcall EnsureDirectoryExistsHr(__int64 a1)
{
  bool *v2; // rdx
  void *v3; // rbx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v5; // rdx
  unsigned int v6; // r8d
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  const WCHAR *v10; // rcx
  DWORD LastError; // eax
  LPCWSTR *v12; // rax
  __int64 Directory; // rax
  __int64 v14; // rdx
  LPCWSTR *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rdi
  const WCHAR *v19; // rcx
  unsigned int v21; // [rsp+28h] [rbp-49h] BYREF
  _QWORD v22[3]; // [rsp+30h] [rbp-41h] BYREF
  char *v23[4]; // [rsp+48h] [rbp-29h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-9h] BYREF
  LPCWSTR lpPathName[2]; // [rsp+80h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+90h] [rbp+1Fh]
  unsigned __int64 v27; // [rsp+98h] [rbp+27h]
  __int128 v28; // [rsp+A0h] [rbp+2Fh] BYREF
  __int64 v29; // [rsp+B0h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v22[2] = -2;
  GetCanonicalUNCPath(lpPathName, a1);
  v28 = 0;
  v29 = 0;
  if ( !*(_QWORD *)(a1 + 8) || DirectoryExists(a1) )
  {
LABEL_37:
    v9 = 0;
    goto LABEL_38;
  }
  v3 = 0;
  v22[0] = 0;
  LOBYTE(v21) = 0;
  CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                        (Windows::WCP::Implementation::Rtl *)&v21,
                        v2);
  if ( CanSetSystemOwner >= 0 )
  {
    if ( (_BYTE)v21 )
    {
      CanSetSystemOwner = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                            (Windows::WCP::Implementation::Rtl *)v22,
                            v5);
      if ( CanSetSystemOwner < 0 )
      {
        v7 = 502;
        goto LABEL_8;
      }
      v3 = (void *)v22[0];
    }
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = v3;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    while ( 1 )
    {
      v10 = (const WCHAR *)lpPathName;
      if ( v27 > 7 )
        v10 = lpPathName[0];
      if ( CreateDirectoryW(v10, &SecurityAttributes) || (LastError = GetLastError(), LastError == 183) )
      {
        v17 = *((_QWORD *)&v28 + 1);
        v18 = v28;
        while ( v17 != v18 )
        {
          v17 -= 32;
          if ( *(_QWORD *)(v17 + 24) <= 7u )
            v19 = (const WCHAR *)v17;
          else
            v19 = *(const WCHAR **)v17;
          if ( !CreateDirectoryW(v19, &SecurityAttributes) )
          {
            LastError = GetLastError();
            if ( LastError != 183 && LastError )
            {
              v16 = 536;
              goto LABEL_27;
            }
            goto LABEL_37;
          }
        }
        goto LABEL_37;
      }
      if ( LastError != 3 )
        break;
      if ( *((_QWORD *)&v28 + 1) == v29 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(
          (__int64 *)&v28,
          *((__int64 *)&v28 + 1),
          (__int64)lpPathName);
      }
      else
      {
        std::wstring::wstring(*((__int64 *)&v28 + 1), (__int64)lpPathName);
        *((_QWORD *)&v28 + 1) += 32LL;
      }
      v12 = lpPathName;
      if ( v27 > 7 )
        v12 = (LPCWSTR *)lpPathName[0];
      v22[0] = v12;
      v22[1] = v26;
      Directory = GetDirectory(v23, v22);
      std::wstring::operator=((char **)lpPathName, Directory);
      std::wstring::~wstring(v23);
      v14 = --v26;
      v15 = lpPathName;
      if ( v27 > 7 )
        v15 = (LPCWSTR *)lpPathName[0];
      *((_WORD *)v15 + v14) = 0;
    }
    if ( !LastError )
      goto LABEL_37;
    v16 = 523;
LABEL_27:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v16,
           (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
           (const char *)LastError,
           v21);
    goto LABEL_9;
  }
  v7 = 497;
LABEL_8:
  v8 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)v7,
         v6,
         (const char *)(unsigned int)CanSetSystemOwner,
         v21);
LABEL_9:
  v9 = v8;
LABEL_38:
  std::vector<std::wstring>::~vector<std::wstring>((__int64)&v28);
  std::wstring::~wstring((char **)lpPathName);
  return v9;
}

```

## disassembly

```asm
0x180010124  mov     rax, rsp
0x180010127  push    rbp
0x180010128  lea     rbp, [rax-5Fh]
0x18001012c  sub     rsp, 0C0h
0x180010133  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18001013b  mov     [rax+10h], rbx
0x18001013f  mov     [rax+18h], rdi
0x180010143  mov     rax, cs:__security_cookie
0x18001014a  xor     rax, rsp
0x18001014d  mov     [rbp+57h+var_10], rax
0x180010151  mov     rbx, rcx
0x180010154  mov     rdx, rcx
0x180010157  lea     rcx, [rbp+57h+lpPathName]
0x18001015b  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x180010160  nop
0x180010161  xorps   xmm0, xmm0
0x180010164  movdqu  [rbp+57h+var_28], xmm0
0x180010169  mov     [rbp+57h+var_18], 0
0x180010171  cmp     qword ptr [rbx+8], 0
0x180010176  jz      loc_180010317
0x18001017c  mov     rcx, rbx
0x18001017f  call    ?DirectoryExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; DirectoryExists(wil::basic_zstring_view<wchar_t> const &)
0x180010184  test    al, al
0x180010186  jnz     loc_180010317
0x18001018c  xor     ebx, ebx
0x18001018e  mov     [rbp+57h+var_98], rbx
0x180010192  mov     byte ptr [rbp+57h+var_A0], bl
0x180010195  lea     rcx, [rbp+57h+var_A0]; this
0x180010199  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x18001019e  test    eax, eax
0x1800101a0  jns     short loc_1800101A9
0x1800101a2  mov     edx, 1F1h
0x1800101a7  jmp     short loc_1800101C0
0x1800101a9  cmp     byte ptr [rbp+57h+var_A0], bl
0x1800101ac  jz      short loc_1800101D7
0x1800101ae  lea     rcx, [rbp+57h+var_98]; this
0x1800101b2  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x1800101b7  test    eax, eax
0x1800101b9  jns     short loc_1800101D3
0x1800101bb  mov     edx, 1F6h; void *
0x1800101c0  mov     r9d, eax; char *
0x1800101c3  mov     rcx, [rbp+5Fh]; this
0x1800101c7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800101cc  mov     ebx, eax
0x1800101ce  jmp     loc_180010319
0x1800101d3  mov     rbx, [rbp+57h+var_98]
0x1800101d7  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x1800101df  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rbx
0x1800101e3  xor     eax, eax
0x1800101e5  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x1800101e9  lea     rcx, [rbp+57h+lpPathName]
0x1800101ed  cmp     [rbp+57h+var_30], 7
0x1800101f2  cmova   rcx, [rbp+57h+lpPathName]; lpPathName
0x1800101f7  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x1800101fb  call    cs:__imp_CreateDirectoryW
0x180010201  test    eax, eax
0x180010203  jnz     loc_1800102D1
0x180010209  call    cs:__imp_GetLastError
0x18001020f  cmp     eax, 0B7h
0x180010214  jz      loc_1800102D1
0x18001021a  cmp     eax, 3
0x18001021d  jnz     loc_1800102B0
0x180010223  mov     rax, qword ptr [rbp+57h+var_28+8]
0x180010227  cmp     rax, [rbp+57h+var_18]
0x18001022b  jz      short loc_180010240
0x18001022d  lea     rdx, [rbp+57h+lpPathName]
0x180010231  mov     rcx, rax
0x180010234  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010239  add     qword ptr [rbp+57h+var_28+8], 20h ; ' '
0x18001023e  jmp     short loc_180010250
0x180010240  lea     r8, [rbp+57h+lpPathName]
0x180010244  mov     rdx, rax
0x180010247  lea     rcx, [rbp+57h+var_28]
0x18001024b  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180010250  mov     rcx, [rbp+57h+var_38]
0x180010254  lea     rax, [rbp+57h+lpPathName]
0x180010258  cmp     [rbp+57h+var_30], 7
0x18001025d  cmova   rax, [rbp+57h+lpPathName]
0x180010262  mov     [rbp+57h+var_98], rax
0x180010266  mov     [rbp+57h+var_90], rcx
0x18001026a  lea     rdx, [rbp+57h+var_98]
0x18001026e  lea     rcx, [rbp+57h+var_80]
0x180010272  call    ?GetDirectory@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetDirectory(wil::basic_zstring_view<wchar_t> const &)
0x180010277  mov     rdx, rax
0x18001027a  lea     rcx, [rbp+57h+lpPathName]
0x18001027e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180010283  lea     rcx, [rbp+57h+var_80]
0x180010287  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001028c  mov     rdx, [rbp+57h+var_38]
0x180010290  dec     rdx
0x180010293  mov     [rbp+57h+var_38], rdx
0x180010297  lea     rcx, [rbp+57h+lpPathName]
0x18001029b  cmp     [rbp+57h+var_30], 7
0x1800102a0  cmova   rcx, [rbp+57h+lpPathName]
0x1800102a5  xor     eax, eax
0x1800102a7  mov     [rcx+rdx*2], ax
0x1800102ab  jmp     loc_1800101E9
0x1800102b0  test    eax, eax
0x1800102b2  jz      short loc_180010317
0x1800102b4  mov     edx, 20Bh; void *
0x1800102b9  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1800102c0  mov     r9d, eax; char *
0x1800102c3  mov     rcx, [rbp+5Fh]; this
0x1800102c7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800102cc  jmp     loc_1800101CC
0x1800102d1  mov     rbx, qword ptr [rbp+57h+var_28+8]
0x1800102d5  mov     rdi, qword ptr [rbp+57h+var_28]
0x1800102d9  cmp     rbx, rdi
0x1800102dc  jz      short loc_180010317
0x1800102de  add     rbx, 0FFFFFFFFFFFFFFE0h
0x1800102e2  cmp     qword ptr [rbx+18h], 7
0x1800102e7  jbe     short loc_1800102EE
0x1800102e9  mov     rcx, [rbx]
0x1800102ec  jmp     short loc_1800102F1
0x1800102ee  mov     rcx, rbx; lpPathName
0x1800102f1  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x1800102f5  call    cs:__imp_CreateDirectoryW
0x1800102fb  test    eax, eax
0x1800102fd  jnz     short loc_1800102D9
0x1800102ff  call    cs:__imp_GetLastError
0x180010305  cmp     eax, 0B7h
0x18001030a  jz      short loc_180010317
0x18001030c  test    eax, eax
0x18001030e  jz      short loc_180010317
0x180010310  mov     edx, 218h
0x180010315  jmp     short loc_1800102B9
0x180010317  xor     ebx, ebx
0x180010319  lea     rcx, [rbp+57h+var_28]
0x18001031d  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180010322  nop
0x180010323  lea     rcx, [rbp+57h+lpPathName]
0x180010327  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001032c  mov     eax, ebx
0x18001032e  mov     rcx, [rbp+57h+var_10]
0x180010332  xor     rcx, rsp; StackCookie
0x180010335  call    __security_check_cookie
0x18001033a  lea     r11, [rsp+0C0h+var_s0]
0x180010342  mov     rbx, [r11+18h]
0x180010346  mov     rdi, [r11+20h]
0x18001034a  mov     rsp, r11
0x18001034d  pop     rbp
0x18001034e  retn
```
