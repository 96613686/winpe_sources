# Utils::OpenFile(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,int,int)

- ea: `0x18000be70`
- end: `0x18000bfd3`
- name: `?OpenFile@Utils@@SA_JAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@HH@Z`
- size: `355`
- prototype: `__int64 __fastcall(const WCHAR *, __int16)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000cee0`
- `0x18000d340`

## callees

- `0x180001540`
- `0x180003648`
- `0x18000bcac`
- `0x18000be70`
- `0x180010124`
- `0x1800104d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bfa6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bfa6`

## pseudocode

```c
__int64 __fastcall Utils::OpenFile(const WCHAR *a1, __int16 a2)
{
  __int64 v3; // rax
  DWORD dwCreationDisposition; // esi
  DWORD v5; // ebx
  __int64 FileW; // rbx
  const WCHAR *v7; // rax
  const WCHAR *v8; // rcx
  LPCWSTR v10; // [rsp+40h] [rbp-49h] BYREF
  __int64 v11; // [rsp+48h] [rbp-41h]
  __int64 v12; // [rsp+50h] [rbp-39h]
  __int128 v13; // [rsp+58h] [rbp-31h] BYREF
  __m128i si128; // [rsp+68h] [rbp-21h]
  _OWORD v15[2]; // [rsp+78h] [rbp-11h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+98h] [rbp+Fh] BYREF

  v12 = -2;
  v3 = *((_QWORD *)a1 + 2);
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  v10 = a1;
  v11 = v3;
  GetCanonicalUNCPath((__int64)lpFileName, &v10);
  dwCreationDisposition = 2;
  v5 = -1073741824;
  if ( (a2 & 2) == 0 )
    v5 = (a2 & 1) != 0 ? 0x40000000 : 0x80000000;
  if ( (a2 & 0x100) != 0 )
  {
    v13 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v13) = 0;
    v15[0] = 0;
    v15[1] = si128;
    LOWORD(v15[0]) = 0;
    if ( (int)Utils::GetPathAndFilename((void **)lpFileName, (void **)&v13, (void **)v15) < 0 )
    {
      std::wstring::~wstring((char **)v15);
      std::wstring::~wstring((char **)&v13);
      FileW = -1;
      goto LABEL_15;
    }
    v7 = (const WCHAR *)&v13;
    if ( si128.m128i_i64[1] > 7uLL )
      v7 = (const WCHAR *)v13;
    v10 = v7;
    v11 = si128.m128i_i64[0];
    EnsureDirectoryExistsHr((__int64)&v10);
    std::wstring::~wstring((char **)v15);
    std::wstring::~wstring((char **)&v13);
  }
  else
  {
    dwCreationDisposition = 3;
  }
  v8 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v8 = lpFileName[0];
  FileW = (__int64)CreateFileW(v8, v5, 7u, 0, dwCreationDisposition, 0x2000080u, 0);
LABEL_15:
  std::wstring::~wstring((char **)lpFileName);
  return FileW;
}

```

## disassembly

```asm
0x18000be70  push    rbp
0x18000be72  push    rbx
0x18000be73  push    rsi
0x18000be74  push    rdi
0x18000be75  lea     rbp, [rsp-3Fh]
0x18000be7a  sub     rsp, 0C8h
0x18000be81  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x18000be89  mov     rax, cs:__security_cookie
0x18000be90  xor     rax, rsp
0x18000be93  mov     [rbp+57h+var_28], rax
0x18000be97  mov     edi, edx
0x18000be99  mov     rax, [rcx+10h]
0x18000be9d  cmp     qword ptr [rcx+18h], 7
0x18000bea2  jbe     short loc_18000BEA7
0x18000bea4  mov     rcx, [rcx]
0x18000bea7  mov     [rbp+57h+var_A0], rcx
0x18000beab  mov     [rbp+57h+var_98], rax
0x18000beaf  lea     rdx, [rbp+57h+var_A0]
0x18000beb3  lea     rcx, [rbp+57h+lpFileName]
0x18000beb7  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x18000bebc  nop
0x18000bebd  mov     esi, 2
0x18000bec2  mov     ebx, 0C0000000h
0x18000bec7  test    sil, dil
0x18000beca  jnz     short loc_18000BEDD
0x18000becc  mov     al, dil
0x18000becf  and     al, 1
0x18000bed1  neg     al
0x18000bed3  sbb     ecx, ecx
0x18000bed5  and     ebx, ecx
0x18000bed7  add     ebx, 80000000h
0x18000bedd  bt      edi, 8
0x18000bee1  jnb     loc_18000BF75
0x18000bee7  xorps   xmm0, xmm0
0x18000beea  movups  [rbp+57h+var_88], xmm0
0x18000beee  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000bef6  movdqu  [rbp+57h+var_78], xmm1
0x18000befb  xor     eax, eax
0x18000befd  mov     word ptr [rbp+57h+var_88], ax
0x18000bf01  movups  [rbp+57h+var_68], xmm0
0x18000bf05  movdqu  [rbp+57h+var_58], xmm1
0x18000bf0a  mov     word ptr [rbp+57h+var_68], ax
0x18000bf0e  lea     r8, [rbp+57h+var_68]
0x18000bf12  lea     rdx, [rbp+57h+var_88]
0x18000bf16  lea     rcx, [rbp+57h+lpFileName]
0x18000bf1a  call    ?GetPathAndFilename@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV23@1@Z; Utils::GetPathAndFilename(std::wstring const &,std::wstring *,std::wstring *)
0x18000bf1f  test    eax, eax
0x18000bf21  jns     short loc_18000BF3C
0x18000bf23  lea     rcx, [rbp+57h+var_68]
0x18000bf27  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bf2c  nop
0x18000bf2d  lea     rcx, [rbp+57h+var_88]
0x18000bf31  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bf36  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000bf3a  jmp     short loc_18000BFAF
0x18000bf3c  mov     rcx, qword ptr [rbp+57h+var_78]
0x18000bf40  lea     rax, [rbp+57h+var_88]
0x18000bf44  cmp     qword ptr [rbp+57h+var_78+8], 7
0x18000bf49  cmova   rax, qword ptr [rbp+57h+var_88]
0x18000bf4e  mov     [rbp+57h+var_A0], rax
0x18000bf52  mov     [rbp+57h+var_98], rcx
0x18000bf56  lea     rcx, [rbp+57h+var_A0]
0x18000bf5a  call    ?EnsureDirectoryExistsHr@@YAJAEBV?$basic_zstring_view@_W@wil@@@Z; EnsureDirectoryExistsHr(wil::basic_zstring_view<wchar_t> const &)
0x18000bf5f  nop
0x18000bf60  lea     rcx, [rbp+57h+var_68]
0x18000bf64  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bf69  nop
0x18000bf6a  lea     rcx, [rbp+57h+var_88]
0x18000bf6e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bf73  jmp     short loc_18000BF7A
0x18000bf75  mov     esi, 3
0x18000bf7a  lea     rcx, [rbp+57h+lpFileName]
0x18000bf7e  cmp     [rbp+57h+var_30], 7
0x18000bf83  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18000bf88  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18000bf91  mov     [rsp+0E0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18000bf99  mov     [rsp+0E0h+dwCreationDisposition], esi; dwCreationDisposition
0x18000bf9d  xor     r9d, r9d; lpSecurityAttributes
0x18000bfa0  lea     r8d, [r9+7]; dwShareMode
0x18000bfa4  mov     edx, ebx; dwDesiredAccess
0x18000bfa6  call    cs:__imp_CreateFileW
0x18000bfac  mov     rbx, rax
0x18000bfaf  lea     rcx, [rbp+57h+lpFileName]
0x18000bfb3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bfb8  mov     rax, rbx
0x18000bfbb  mov     rcx, [rbp+57h+var_28]
0x18000bfbf  xor     rcx, rsp; StackCookie
0x18000bfc2  call    __security_check_cookie
0x18000bfc7  add     rsp, 0C8h
0x18000bfce  pop     rdi
0x18000bfcf  pop     rsi
0x18000bfd0  pop     rbx
0x18000bfd1  pop     rbp
0x18000bfd2  retn
```
