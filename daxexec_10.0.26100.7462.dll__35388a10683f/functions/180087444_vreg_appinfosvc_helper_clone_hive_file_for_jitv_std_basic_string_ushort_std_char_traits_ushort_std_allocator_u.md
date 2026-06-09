# vreg::appinfosvc::helper::clone_hive_file_for_jitv(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::filesystem::path const &,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x180087444`
- end: `0x18008766c`
- name: `?clone_hive_file_for_jitv@helper@appinfosvc@vreg@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@AEBVpath@filesystem@5@_N0PEAX@Z`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18008878c`

## callees

- `0x1800053a0`
- `0x1800116b0`
- `0x180011820`
- `0x180013100`
- `0x180013148`
- `0x18002031c`
- `0x18002b240`
- `0x18002cea4`
- `0x180034de0`
- `0x180087444`
- `0x180087cd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087554`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800875e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800875e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800875b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800875b5`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180087540`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180087540`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall vreg::appinfosvc::helper::clone_hive_file_for_jitv(__int64 a1, __int64 a2, const WCHAR *a3, char a4)
{
  __int64 v8; // rcx
  const WCHAR *v9; // rdx
  DWORD LastError; // eax
  const struct std::filesystem::path *v11; // rdx
  const WCHAR *v12; // rcx
  char *FileW; // rax
  const char *v14; // r9
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-99h]
  LPCWSTR lpNewFileName[3]; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v18; // [rsp+68h] [rbp-51h]
  __int128 v19; // [rsp+70h] [rbp-49h] BYREF
  __m128i si128; // [rsp+80h] [rbp-39h]
  _OWORD v21[2]; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v22[32]; // [rsp+B0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]

  vreg::appinfosvc::helper::get_destination_hives_location_path((struct std::error_code *)v22);
  v8 = *(_QWORD *)(a2 + 16);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v8) < 4 )
    std::_Xlen_string();
  std::wstring::wstring(&v19, v8, L".dat", 4);
  v21[0] = v19;
  v21[1] = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19) = 0;
  std::filesystem::operator/(lpNewFileName);
  std::wstring::~wstring(v21);
  std::wstring::~wstring(&v19);
  v9 = (const WCHAR *)lpNewFileName;
  if ( v18 > 7 )
    v9 = lpNewFileName[0];
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  if ( !CopyFileW(a3, v9, 0) )
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
      if ( !std::filesystem::exists((std::filesystem *)lpNewFileName, v11) )
      {
        v12 = (const WCHAR *)lpNewFileName;
        if ( v18 > 7 )
          v12 = lpNewFileName[0];
        FileW = (char *)CreateFileW(v12, 0x40000000u, 0, 0, 1u, 0x80u, 0);
        if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xC8,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\vreg.cpp",
            v14);
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(FileW);
      }
    }
  }
  std::wstring::wstring(a1, lpNewFileName);
  std::wstring::~wstring(lpNewFileName);
  std::wstring::~wstring(v22);
  return a1;
}

```

## disassembly

```asm
0x180087444  mov     [rsp-8+arg_18], rbx
0x180087449  push    rbp
0x18008744a  push    rsi
0x18008744b  push    rdi
0x18008744c  push    r14
0x18008744e  push    r15
0x180087450  lea     rbp, [rsp-27h]
0x180087455  sub     rsp, 0E0h
0x18008745c  mov     rax, cs:__security_cookie
0x180087463  xor     rax, rsp
0x180087466  mov     [rbp+47h+var_30], rax
0x18008746a  mov     r14b, r9b
0x18008746d  mov     rdi, r8
0x180087470  mov     rbx, rdx
0x180087473  mov     rsi, rcx
0x180087476  mov     [rbp+47h+var_B8], rcx
0x18008747a  mov     rdx, [rbp+47h+arg_20]
0x18008747e  mov     r8, [rbp+47h+arg_28]
0x180087482  xor     r15d, r15d
0x180087485  lea     rcx, [rbp+47h+var_50]; struct std::error_code *
0x180087489  call    ?get_destination_hives_location_path@helper@appinfosvc@vreg@@YA?AVpath@filesystem@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@PEAX@Z; vreg::appinfosvc::helper::get_destination_hives_location_path(std::wstring const &,void *)
0x18008748e  nop
0x18008748f  mov     rcx, [rbx+10h]
0x180087493  mov     rax, 7FFFFFFFFFFFFFFEh
0x18008749d  sub     rax, rcx
0x1800874a0  cmp     rax, 4
0x1800874a4  jb      loc_180087666
0x1800874aa  cmp     qword ptr [rbx+18h], 7
0x1800874af  jbe     short loc_1800874B4
0x1800874b1  mov     rbx, [rbx]
0x1800874b4  mov     [rsp+100h+hTemplateFile], 4; __int64
0x1800874bd  lea     rax, aDat_0; ".dat"
0x1800874c4  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rax; Src
0x1800874c9  mov     qword ptr [rsp+100h+dwCreationDisposition], rcx; unsigned int
0x1800874ce  mov     r9, rbx
0x1800874d1  lea     rcx, [rbp+47h+var_90]; void *
0x1800874d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800874da  nop
0x1800874db  movups  xmm0, [rbp+47h+var_90]
0x1800874df  movups  [rbp+47h+var_70], xmm0
0x1800874e3  movups  xmm1, [rbp+47h+var_80]
0x1800874e7  movups  [rbp+47h+var_60], xmm1
0x1800874eb  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800874f3  movdqu  [rbp+47h+var_80], xmm0
0x1800874f8  mov     word ptr [rbp+47h+var_90], r15w
0x1800874fd  lea     r8, [rbp+47h+var_70]
0x180087501  lea     rdx, [rbp+47h+var_50]
0x180087505  lea     rcx, [rbp+47h+lpNewFileName]; void *
0x180087509  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18008750e  nop
0x18008750f  lea     rcx, [rbp+47h+var_70]; void *
0x180087513  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180087518  nop
0x180087519  lea     rcx, [rbp+47h+var_90]; void *
0x18008751d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180087522  lea     rdx, [rbp+47h+lpNewFileName]
0x180087526  cmp     [rbp+47h+var_98], 7
0x18008752b  cmova   rdx, [rbp+47h+lpNewFileName]; lpNewFileName
0x180087530  cmp     qword ptr [rdi+18h], 7
0x180087535  jbe     short loc_18008753A
0x180087537  mov     rdi, [rdi]
0x18008753a  xor     r8d, r8d; bFailIfExists
0x18008753d  mov     rcx, rdi; lpExistingFileName
0x180087540  call    cs:__imp_CopyFileW
0x180087547  nop     dword ptr [rax+rax+00h]
0x18008754c  test    eax, eax
0x18008754e  jnz     loc_1800875F4
0x180087554  call    cs:__imp_GetLastError
0x18008755b  nop     dword ptr [rax+rax+00h]
0x180087560  test    eax, eax
0x180087562  jz      loc_1800875F4
0x180087568  test    r14b, r14b
0x18008756b  jz      loc_18008764D
0x180087571  cmp     eax, 20h ; ' '
0x180087574  jnz     loc_18008764D
0x18008757a  lea     rcx, [rbp+47h+lpNewFileName]; this
0x18008757e  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x180087583  test    al, al
0x180087585  jnz     short loc_1800875F4
0x180087587  lea     rcx, [rbp+47h+lpNewFileName]
0x18008758b  cmp     [rbp+47h+var_98], 7
0x180087590  cmova   rcx, [rbp+47h+lpNewFileName]; lpFileName
0x180087595  mov     [rsp+100h+hTemplateFile], r15; hTemplateFile
0x18008759a  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800875a2  mov     [rsp+100h+dwCreationDisposition], 1; dwCreationDisposition
0x1800875aa  xor     r9d, r9d; lpSecurityAttributes
0x1800875ad  xor     r8d, r8d; dwShareMode
0x1800875b0  mov     edx, 40000000h; dwDesiredAccess
0x1800875b5  call    cs:__imp_CreateFileW
0x1800875bc  nop     dword ptr [rax+rax+00h]
0x1800875c1  mov     [rbp+47h+var_B8], rax
0x1800875c5  lea     rcx, [rax+1]
0x1800875c9  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800875d0  setz    dl
0x1800875d3  mov     rcx, [rbp+4Fh]; this
0x1800875d7  test    dl, dl
0x1800875d9  jnz     short loc_18008763B
0x1800875db  lea     rcx, [rax-1]
0x1800875df  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800875e3  ja      short loc_1800875F4
0x1800875e5  mov     rcx, rax; hObject
0x1800875e8  call    cs:__imp_CloseHandle
0x1800875ef  nop     dword ptr [rax+rax+00h]
0x1800875f4  lea     rdx, [rbp+47h+lpNewFileName]
0x1800875f8  mov     rcx, rsi
0x1800875fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180087600  nop
0x180087601  lea     rcx, [rbp+47h+lpNewFileName]; void *
0x180087605  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008760a  nop
0x18008760b  lea     rcx, [rbp+47h+var_50]; void *
0x18008760f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180087614  mov     rax, rsi
0x180087617  mov     rcx, [rbp+47h+var_30]
0x18008761b  xor     rcx, rsp; StackCookie
0x18008761e  call    __security_check_cookie
0x180087623  mov     rbx, [rsp+100h+arg_18]
0x18008762b  add     rsp, 0E0h
0x180087632  pop     r15
0x180087634  pop     r14
0x180087636  pop     rdi
0x180087637  pop     rsi
0x180087638  pop     rbp
0x180087639  retn
0x18008763b  lea     r8, aOnecoreBaseApp_66; "onecore\\base\\appmodel\\execmodel\\des"...
0x180087642  mov     edx, 0C8h; void *
0x180087647  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18008764d  mov     rcx, [rbp+4Fh]; this
0x180087651  mov     r9d, eax; char *
0x180087654  lea     r8, aOnecoreBaseApp_66; "onecore\\base\\appmodel\\execmodel\\des"...
0x18008765b  mov     edx, 0CEh; void *
0x180087660  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180087666  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
