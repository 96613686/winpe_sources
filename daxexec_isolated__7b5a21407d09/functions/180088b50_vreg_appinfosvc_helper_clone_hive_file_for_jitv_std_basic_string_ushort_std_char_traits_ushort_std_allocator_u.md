# vreg::appinfosvc::helper::clone_hive_file_for_jitv(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::filesystem::path const &,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x180088b50`
- end: `0x180088db9`
- name: `?clone_hive_file_for_jitv@helper@appinfosvc@vreg@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@AEBVpath@filesystem@5@_N0PEAX@Z`
- size: `617`
- prototype: `char *__fastcall(char *, _QWORD *, const WCHAR *, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180089dd0`

## callees

- `0x180004f70`
- `0x180013320`
- `0x180013510`
- `0x180014e74`
- `0x180014ebc`
- `0x1800210fc`
- `0x18002bab4`
- `0x18002d978`
- `0x1800355c0`
- `0x180035e50`
- `0x180088b50`
- `0x1800893f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088c59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088d1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088d1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180088ceb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180088ceb`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180088c45`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180088c45`

## pseudocode

```c
char *__fastcall vreg::appinfosvc::helper::clone_hive_file_for_jitv(char *a1, _QWORD *a2, const WCHAR *a3, char a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  const WCHAR *v11; // rdx
  DWORD LastError; // eax
  _DWORD *any_status; // rcx
  const struct std::filesystem::path *v14; // r9
  int v15; // edx
  bool v16; // al
  const WCHAR *v17; // rcx
  char *FileW; // rax
  const char *v19; // r9
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-99h]
  char *v22; // [rsp+48h] [rbp-71h] BYREF
  char v23[16]; // [rsp+58h] [rbp-61h] BYREF
  __m128i si128; // [rsp+68h] [rbp-51h]
  LPCWSTR lpNewFileName[3]; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int64 v26; // [rsp+90h] [rbp-29h]
  _OWORD v27[2]; // [rsp+98h] [rbp-21h] BYREF
  _BYTE v28[32]; // [rsp+B8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]

  v22 = a1;
  vreg::appinfosvc::helper::get_destination_hives_location_path((struct std::error_code *)v28);
  v10 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v10) < 4 )
    std::_Xlen_string();
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::wstring(v23, v8, v9, a2, v10, L".dat", 4);
  v27[0] = *(_OWORD *)v23;
  v27[1] = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(_WORD *)v23 = 0;
  std::filesystem::operator/(lpNewFileName, v28, (std::filesystem *)v27);
  std::wstring::~wstring(v27);
  std::wstring::~wstring(v23);
  v11 = (const WCHAR *)lpNewFileName;
  if ( v26 > 7 )
    v11 = lpNewFileName[0];
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  if ( !CopyFileW(a3, v11, 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( !a4 || LastError != 32 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xCE,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\vreg.cpp",
          (const char *)LastError,
          dwCreationDisposition);
      any_status = (_DWORD *)std::filesystem::_Get_any_status(&v22, lpNewFileName);
      v15 = any_status[2];
      *(_DWORD *)v23 = v15;
      *(_QWORD *)&v23[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
      if ( *any_status )
      {
        v16 = *any_status != 1;
      }
      else
      {
        v16 = 0;
        if ( v15 )
          std::filesystem::_Throw_fs_error(
            (std::filesystem *)"exists",
            v23,
            (const struct std::error_code *)lpNewFileName,
            v14);
      }
      if ( !v16 )
      {
        v17 = (const WCHAR *)lpNewFileName;
        if ( v26 > 7 )
          v17 = lpNewFileName[0];
        FileW = (char *)CreateFileW(v17, 0x40000000u, 0, 0, 1u, 0x80u, 0);
        v22 = FileW;
        if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xC8,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\vreg.cpp",
            v19);
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(FileW);
      }
    }
  }
  std::wstring::wstring(a1, lpNewFileName);
  std::wstring::~wstring(lpNewFileName);
  std::wstring::~wstring(v28);
  return a1;
}

```

## disassembly

```asm
0x180088b50  push    rbp
0x180088b52  push    rbx
0x180088b53  push    rsi
0x180088b54  push    rdi
0x180088b55  push    r14
0x180088b57  lea     rbp, [rsp-27h]
0x180088b5c  sub     rsp, 0E0h
0x180088b63  mov     rax, cs:__security_cookie
0x180088b6a  xor     rax, rsp
0x180088b6d  mov     [rbp+47h+var_28], rax
0x180088b71  mov     r14b, r9b
0x180088b74  mov     rdi, r8
0x180088b77  mov     rbx, rdx
0x180088b7a  mov     rsi, rcx
0x180088b7d  mov     [rbp+47h+var_B8], rcx
0x180088b81  mov     rdx, [rbp+47h+arg_20]
0x180088b85  mov     r8, [rbp+47h+arg_28]
0x180088b89  lea     rcx, [rbp+47h+var_48]; struct std::error_code *
0x180088b8d  call    ?get_destination_hives_location_path@helper@appinfosvc@vreg@@YA?AVpath@filesystem@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@PEAX@Z; vreg::appinfosvc::helper::get_destination_hives_location_path(std::wstring const &,void *)
0x180088b92  nop
0x180088b93  mov     rcx, [rbx+10h]
0x180088b97  mov     rax, 7FFFFFFFFFFFFFFEh
0x180088ba1  sub     rax, rcx
0x180088ba4  cmp     rax, 4
0x180088ba8  jb      loc_180088DB3
0x180088bae  cmp     qword ptr [rbx+18h], 7
0x180088bb3  jbe     short loc_180088BB8
0x180088bb5  mov     rbx, [rbx]
0x180088bb8  mov     [rsp+100h+hTemplateFile], 4
0x180088bc1  lea     rax, aDat_0; ".dat"
0x180088bc8  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rax
0x180088bcd  mov     qword ptr [rsp+100h+dwCreationDisposition], rcx; unsigned int
0x180088bd2  mov     r9, rbx
0x180088bd5  lea     rcx, [rbp+47h+var_A8]
0x180088bd9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180088bde  nop
0x180088bdf  movups  xmm0, xmmword ptr [rbp+47h+var_A8]
0x180088be3  movups  [rbp+47h+var_68], xmm0
0x180088be7  movups  xmm1, [rbp+47h+var_98]
0x180088beb  movups  [rbp+47h+var_58], xmm1
0x180088bef  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180088bf7  movdqu  [rbp+47h+var_98], xmm0
0x180088bfc  xor     eax, eax
0x180088bfe  mov     word ptr [rbp+47h+var_A8], ax
0x180088c02  lea     r8, [rbp+47h+var_68]; this
0x180088c06  lea     rdx, [rbp+47h+var_48]; void *
0x180088c0a  lea     rcx, [rbp+47h+lpNewFileName]; Src
0x180088c0e  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180088c13  nop
0x180088c14  lea     rcx, [rbp+47h+var_68]; void *
0x180088c18  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088c1d  nop
0x180088c1e  lea     rcx, [rbp+47h+var_A8]; void *
0x180088c22  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088c27  lea     rdx, [rbp+47h+lpNewFileName]
0x180088c2b  cmp     [rbp+47h+var_70], 7
0x180088c30  cmova   rdx, [rbp+47h+lpNewFileName]; lpNewFileName
0x180088c35  cmp     qword ptr [rdi+18h], 7
0x180088c3a  jbe     short loc_180088C3F
0x180088c3c  mov     rdi, [rdi]
0x180088c3f  xor     r8d, r8d; bFailIfExists
0x180088c42  mov     rcx, rdi; lpExistingFileName
0x180088c45  call    cs:__imp_CopyFileW
0x180088c4c  nop     dword ptr [rax+rax+00h]
0x180088c51  test    eax, eax
0x180088c53  jnz     loc_180088D2A
0x180088c59  call    cs:__imp_GetLastError
0x180088c60  nop     dword ptr [rax+rax+00h]
0x180088c65  test    eax, eax
0x180088c67  jz      loc_180088D2A
0x180088c6d  test    r14b, r14b
0x180088c70  jz      loc_180088D9A
0x180088c76  cmp     eax, 20h ; ' '
0x180088c79  jnz     loc_180088D9A
0x180088c7f  lea     rdx, [rbp+47h+lpNewFileName]
0x180088c83  lea     rcx, [rbp+47h+var_B8]
0x180088c87  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x180088c8c  mov     rcx, rax
0x180088c8f  mov     edx, [rax+8]
0x180088c92  mov     dword ptr [rbp+47h+var_A8], edx
0x180088c95  mov     eax, dword ptr [rbp+47h+var_A8+4]
0x180088c98  mov     dword ptr [rbp+47h+var_A8+4], eax
0x180088c9b  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180088ca2  mov     qword ptr [rbp+47h+var_A8+8], rax
0x180088ca6  cmp     dword ptr [rcx], 0
0x180088ca9  jz      loc_180088D68
0x180088caf  cmp     dword ptr [rcx], 1
0x180088cb2  setnz   al
0x180088cb5  test    al, al
0x180088cb7  jnz     short loc_180088D2A
0x180088cb9  lea     rcx, [rbp+47h+lpNewFileName]
0x180088cbd  cmp     [rbp+47h+var_70], 7
0x180088cc2  cmova   rcx, [rbp+47h+lpNewFileName]; lpFileName
0x180088cc7  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x180088cd0  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180088cd8  mov     [rsp+100h+dwCreationDisposition], 1; dwCreationDisposition
0x180088ce0  xor     r9d, r9d; lpSecurityAttributes
0x180088ce3  xor     r8d, r8d; dwShareMode
0x180088ce6  mov     edx, 40000000h; dwDesiredAccess
0x180088ceb  call    cs:__imp_CreateFileW
0x180088cf2  nop     dword ptr [rax+rax+00h]
0x180088cf7  mov     [rbp+47h+var_B8], rax
0x180088cfb  lea     rcx, [rax+1]
0x180088cff  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180088d06  setz    dl
0x180088d09  mov     rcx, [rbp+4Fh]; this
0x180088d0d  test    dl, dl
0x180088d0f  jnz     short loc_180088D73
0x180088d11  lea     rcx, [rax-1]
0x180088d15  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180088d19  ja      short loc_180088D2A
0x180088d1b  mov     rcx, rax; hObject
0x180088d1e  call    cs:__imp_CloseHandle
0x180088d25  nop     dword ptr [rax+rax+00h]
0x180088d2a  lea     rdx, [rbp+47h+lpNewFileName]
0x180088d2e  mov     rcx, rsi
0x180088d31  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180088d36  nop
0x180088d37  lea     rcx, [rbp+47h+lpNewFileName]; void *
0x180088d3b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088d40  nop
0x180088d41  lea     rcx, [rbp+47h+var_48]; void *
0x180088d45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088d4a  mov     rax, rsi
0x180088d4d  mov     rcx, [rbp+47h+var_28]
0x180088d51  xor     rcx, rsp; StackCookie
0x180088d54  call    __security_check_cookie
0x180088d59  add     rsp, 0E0h
0x180088d60  pop     r14
0x180088d62  pop     rdi
0x180088d63  pop     rsi
0x180088d64  pop     rbx
0x180088d65  pop     rbp
0x180088d66  retn
0x180088d68  xor     al, al
0x180088d6a  test    edx, edx
0x180088d6c  jnz     short loc_180088D85
0x180088d6e  jmp     loc_180088CB5
0x180088d73  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\execmodel\\des"...
0x180088d7a  mov     edx, 0C8h; void *
0x180088d7f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180088d85  lea     r8, [rbp+47h+lpNewFileName]; struct std::error_code *
0x180088d89  lea     rdx, [rbp+47h+var_A8]; char *
0x180088d8d  lea     rcx, aExists; "exists"
0x180088d94  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x180088d9a  mov     rcx, [rbp+4Fh]; this
0x180088d9e  mov     r9d, eax; char *
0x180088da1  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\execmodel\\des"...
0x180088da8  mov     edx, 0CEh; void *
0x180088dad  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180088db3  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
