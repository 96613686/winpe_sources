# GetLongPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18005fb14`
- end: `0x18005fcf8`
- name: `?GetLongPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180060594`

## callees

- `0x1800053a0`
- `0x180010a84`
- `0x180011820`
- `0x1800149a4`
- `0x18002031c`
- `0x18002b240`
- `0x1800345b8`
- `0x18005fb14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb65`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005fb54`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005fb54`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18005fbe4`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18005fc27`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18005fbe4`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18005fc27`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall GetLongPath(_OWORD *a1, const WCHAR *a2)
{
  const WCHAR *v2; // rbx
  char v4; // si
  const WCHAR *v5; // rcx
  DWORD LastError; // eax
  const char *v7; // r9
  __int64 v8; // rcx
  const WCHAR *v9; // rcx
  DWORD LongPathNameW; // eax
  __int64 v11; // r8
  const char *v12; // r9
  WCHAR *v13; // rdx
  unsigned __int64 v14; // rdx
  LPWSTR *v15; // rax
  int v17; // [rsp+20h] [rbp-40h]
  LPWSTR lpszLongPath[2]; // [rsp+30h] [rbp-30h] BYREF
  DWORD cchBuffer[4]; // [rsp+40h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v2 = a2;
  v4 = 0;
  v5 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v5 = *(const WCHAR **)a2;
  if ( GetFileAttributesW(v5) != -1 )
  {
    v4 = 1;
LABEL_11:
    v7 = 0;
    goto LABEL_12;
  }
  LastError = GetLastError();
  v7 = (const char *)LastError;
  if ( LastError <= 0x35 )
  {
    v8 = 0x2000000000800CLL;
    if ( _bittest64(&v8, LastError) )
      goto LABEL_11;
  }
  if ( LastError == 67 || LastError == 1203 )
    goto LABEL_11;
  if ( (int)LastError > 0 )
    v7 = (const char *)((unsigned __int16)LastError | 0x80070000);
LABEL_12:
  if ( (int)v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\FileUtils.h",
      v7,
      v17);
  if ( v4 )
  {
    v9 = v2;
    if ( *((_QWORD *)v2 + 3) > 7u )
      v9 = *(const WCHAR **)v2;
    LongPathNameW = GetLongPathNameW(v9, 0, 0);
    if ( !LongPathNameW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\FileUtils.h",
        v12);
    std::wstring::wstring(lpszLongPath, LongPathNameW, v11, v12);
    v13 = (WCHAR *)lpszLongPath;
    if ( *(_QWORD *)&cchBuffer[2] > 7u )
      v13 = lpszLongPath[0];
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(const WCHAR **)v2;
    v14 = GetLongPathNameW(v2, v13, cchBuffer[0]);
    if ( v14 > *(_QWORD *)cchBuffer )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\FileUtils.h",
        *(const char **)cchBuffer);
    v15 = lpszLongPath;
    if ( *(_QWORD *)&cchBuffer[2] > 7u )
      v15 = (LPWSTR *)lpszLongPath[0];
    *(_QWORD *)cchBuffer = v14;
    *((_WORD *)v15 + v14) = 0;
    *a1 = *(_OWORD *)lpszLongPath;
    a1[1] = *(_OWORD *)cchBuffer;
    *(_QWORD *)cchBuffer = 0;
    *(_QWORD *)&cchBuffer[2] = 7;
    LOWORD(lpszLongPath[0]) = 0;
    std::wstring::~wstring(lpszLongPath);
  }
  else
  {
    std::wstring::wstring(a1, v2);
  }
  return a1;
}

```

## disassembly

```asm
0x18005fb14  mov     [rsp-18h+arg_10], rbx
0x18005fb19  mov     [rsp-18h+arg_18], rsi
0x18005fb1e  push    rbp
0x18005fb1f  push    rdi
0x18005fb20  push    r14
0x18005fb22  mov     rbp, rsp
0x18005fb25  sub     rsp, 60h
0x18005fb29  mov     rax, cs:__security_cookie
0x18005fb30  xor     rax, rsp
0x18005fb33  mov     [rbp+var_10], rax
0x18005fb37  mov     rbx, rdx
0x18005fb3a  mov     rdi, rcx
0x18005fb3d  mov     [rbp+var_38], rcx
0x18005fb41  xor     r14d, r14d
0x18005fb44  mov     sil, r14b
0x18005fb47  mov     rcx, rdx
0x18005fb4a  cmp     qword ptr [rdx+18h], 7
0x18005fb4f  jbe     short loc_18005FB54
0x18005fb51  mov     rcx, [rdx]; lpFileName
0x18005fb54  call    cs:__imp_GetFileAttributesW
0x18005fb5b  nop     dword ptr [rax+rax+00h]
0x18005fb60  cmp     eax, 0FFFFFFFFh
0x18005fb63  jnz     short loc_18005FBAA
0x18005fb65  call    cs:__imp_GetLastError
0x18005fb6c  nop     dword ptr [rax+rax+00h]
0x18005fb71  mov     r9d, eax
0x18005fb74  cmp     eax, 35h ; '5'
0x18005fb77  ja      short loc_18005FB89
0x18005fb79  mov     rcx, 2000000000800Ch
0x18005fb83  bt      rcx, r9
0x18005fb87  jb      short loc_18005FBAD
0x18005fb89  cmp     r9d, 43h ; 'C'
0x18005fb8d  jz      short loc_18005FBAD
0x18005fb8f  cmp     r9d, 4B3h
0x18005fb96  jz      short loc_18005FBAD
0x18005fb98  test    r9d, r9d
0x18005fb9b  jle     short loc_18005FBB0
0x18005fb9d  movzx   r9d, r9w
0x18005fba1  or      r9d, 80070000h
0x18005fba8  jmp     short loc_18005FBB0
0x18005fbaa  mov     sil, 1
0x18005fbad  mov     r9d, r14d; char *
0x18005fbb0  mov     rcx, [rbp+18h]; this
0x18005fbb4  test    r9d, r9d
0x18005fbb7  js      loc_18005FCD4
0x18005fbbd  test    sil, sil
0x18005fbc0  jnz     short loc_18005FBD2
0x18005fbc2  mov     rdx, rbx
0x18005fbc5  mov     rcx, rdi
0x18005fbc8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005fbcd  jmp     loc_18005FC9D
0x18005fbd2  mov     rcx, rbx
0x18005fbd5  cmp     qword ptr [rbx+18h], 7
0x18005fbda  jbe     short loc_18005FBDF
0x18005fbdc  mov     rcx, [rbx]; lpszShortPath
0x18005fbdf  xor     r8d, r8d; cchBuffer
0x18005fbe2  xor     edx, edx; lpszLongPath
0x18005fbe4  call    cs:__imp_GetLongPathNameW
0x18005fbeb  nop     dword ptr [rax+rax+00h]
0x18005fbf0  mov     rcx, [rbp+18h]; this
0x18005fbf4  test    eax, eax
0x18005fbf6  jz      loc_18005FCE6
0x18005fbfc  mov     edx, eax
0x18005fbfe  lea     rcx, [rbp+lpszLongPath]
0x18005fc02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18005fc07  nop
0x18005fc08  lea     rdx, [rbp+lpszLongPath]
0x18005fc0c  cmp     qword ptr [rbp+cchBuffer+8], 7
0x18005fc11  cmova   rdx, [rbp+lpszLongPath]; lpszLongPath
0x18005fc16  cmp     qword ptr [rbx+18h], 7
0x18005fc1b  jbe     short loc_18005FC20
0x18005fc1d  mov     rbx, [rbx]
0x18005fc20  mov     r8d, [rbp+cchBuffer]; cchBuffer
0x18005fc24  mov     rcx, rbx; lpszShortPath
0x18005fc27  call    cs:__imp_GetLongPathNameW
0x18005fc2e  nop     dword ptr [rax+rax+00h]
0x18005fc33  mov     edx, eax
0x18005fc35  mov     r9, qword ptr [rbp+cchBuffer]; char *
0x18005fc39  cmp     rdx, r9
0x18005fc3c  setnbe  al
0x18005fc3f  mov     rcx, [rbp+18h]; this
0x18005fc43  test    al, al
0x18005fc45  jnz     short loc_18005FCC2
0x18005fc47  cmp     rdx, r9
0x18005fc4a  ja      short loc_18005FC65
0x18005fc4c  lea     rax, [rbp+lpszLongPath]
0x18005fc50  cmp     qword ptr [rbp+cchBuffer+8], 7
0x18005fc55  cmova   rax, [rbp+lpszLongPath]
0x18005fc5a  mov     qword ptr [rbp+cchBuffer], rdx
0x18005fc5e  mov     [rax+rdx*2], r14w
0x18005fc63  jmp     short loc_18005FC74
0x18005fc65  xor     r8d, r8d
0x18005fc68  sub     rdx, r9
0x18005fc6b  lea     rcx, [rbp+lpszLongPath]; Src
0x18005fc6f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x18005fc74  movups  xmm0, xmmword ptr [rbp+lpszLongPath]
0x18005fc78  movups  xmmword ptr [rdi], xmm0
0x18005fc7b  movups  xmm1, xmmword ptr [rbp+cchBuffer]
0x18005fc7f  movups  xmmword ptr [rdi+10h], xmm1
0x18005fc83  mov     qword ptr [rbp+cchBuffer], r14
0x18005fc87  mov     qword ptr [rbp+cchBuffer+8], 7
0x18005fc8f  mov     word ptr [rbp+lpszLongPath], r14w
0x18005fc94  lea     rcx, [rbp+lpszLongPath]; void *
0x18005fc98  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005fc9d  mov     rax, rdi
0x18005fca0  mov     rcx, [rbp+var_10]
0x18005fca4  xor     rcx, rsp; StackCookie
0x18005fca7  call    __security_check_cookie
0x18005fcac  lea     r11, [rsp+60h+var_s0]
0x18005fcb1  mov     rbx, [r11+30h]
0x18005fcb5  mov     rsi, [r11+38h]
0x18005fcb9  mov     rsp, r11
0x18005fcbc  pop     r14
0x18005fcbe  pop     rdi
0x18005fcbf  pop     rbp
0x18005fcc0  retn
0x18005fcc2  lea     r8, aOnecoreBaseApp_37; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005fcc9  mov     edx, 63h ; 'c'; void *
0x18005fcce  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005fcd4  lea     r8, aOnecoreBaseApp_37; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005fcdb  mov     edx, 54h ; 'T'; void *
0x18005fce0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005fce6  lea     r8, aOnecoreBaseApp_37; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005fced  mov     edx, 5Fh ; '_'; void *
0x18005fcf2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
