# GetLongPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180061618`
- end: `0x1800617e3`
- name: `?GetLongPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180061fd8`

## callees

- `0x180004f70`
- `0x1800125f4`
- `0x180013510`
- `0x1800165bc`
- `0x1800210fc`
- `0x18002bab4`
- `0x1800371c8`
- `0x180061618`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061662`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180061651`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180061651`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800616e7`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18006172a`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800616e7`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18006172a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetLongPath(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v2; // rbx
  const WCHAR *v4; // rcx
  DWORD LastError; // eax
  const char *v6; // r9
  __int64 v7; // rcx
  char v8; // al
  const WCHAR *v9; // rcx
  DWORD LongPathNameW; // eax
  __int64 v11; // r8
  const char *v12; // r9
  WCHAR *v13; // rdx
  DWORD v14; // eax
  const char *v15; // r9
  int v17; // [rsp+20h] [rbp-40h]
  LPWSTR lpszLongPath[2]; // [rsp+30h] [rbp-30h] BYREF
  DWORD cchBuffer[4]; // [rsp+40h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v2 = a2;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v4 = a2;
  else
    v4 = *(const WCHAR **)a2;
  if ( GetFileAttributesW(v4) != -1 )
  {
    v8 = 1;
    goto LABEL_13;
  }
  LastError = GetLastError();
  v6 = (const char *)LastError;
  if ( LastError <= 0x35 && (v7 = 0x2000000000800CLL, _bittest64(&v7, LastError))
    || LastError == 67
    || LastError == 1203 )
  {
    v8 = 0;
LABEL_13:
    v6 = 0;
    goto LABEL_14;
  }
  v8 = 0;
  if ( (int)v6 > 0 )
    v6 = (const char *)((unsigned __int16)v6 | 0x80070000);
LABEL_14:
  if ( (int)v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\FileUtils.h",
      v6,
      v17);
  if ( v8 )
  {
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v9 = v2;
    else
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
    if ( (unsigned __int64)v14 > *(_QWORD *)cchBuffer )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\FileUtils.h",
        v15);
    std::wstring::resize(lpszLongPath);
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)lpszLongPath;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)cchBuffer;
    *(__m128i *)cchBuffer = _mm_load_si128((const __m128i *)&_xmm);
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
0x180061618  mov     [rsp-8+arg_10], rbx
0x18006161d  mov     [rsp-8+arg_18], rdi
0x180061622  push    rbp
0x180061623  mov     rbp, rsp
0x180061626  sub     rsp, 60h
0x18006162a  mov     rax, cs:__security_cookie
0x180061631  xor     rax, rsp
0x180061634  mov     [rbp+var_10], rax
0x180061638  mov     rbx, rdx
0x18006163b  mov     rdi, rcx
0x18006163e  mov     [rbp+var_38], rcx
0x180061642  cmp     qword ptr [rdx+18h], 7
0x180061647  jbe     short loc_18006164E
0x180061649  mov     rcx, [rdx]
0x18006164c  jmp     short loc_180061651
0x18006164e  mov     rcx, rbx; lpFileName
0x180061651  call    cs:__imp_GetFileAttributesW
0x180061658  nop     dword ptr [rax+rax+00h]
0x18006165d  cmp     eax, 0FFFFFFFFh
0x180061660  jnz     short loc_1800616AD
0x180061662  call    cs:__imp_GetLastError
0x180061669  nop     dword ptr [rax+rax+00h]
0x18006166e  mov     r9d, eax
0x180061671  cmp     eax, 35h ; '5'
0x180061674  ja      short loc_180061686
0x180061676  mov     rcx, 2000000000800Ch
0x180061680  bt      rcx, r9
0x180061684  jb      short loc_1800616A9
0x180061686  cmp     r9d, 43h ; 'C'
0x18006168a  jz      short loc_1800616A9
0x18006168c  cmp     r9d, 4B3h
0x180061693  jz      short loc_1800616A9
0x180061695  xor     al, al
0x180061697  test    r9d, r9d
0x18006169a  jle     short loc_1800616B2
0x18006169c  movzx   r9d, r9w
0x1800616a0  or      r9d, 80070000h
0x1800616a7  jmp     short loc_1800616B2
0x1800616a9  xor     al, al
0x1800616ab  jmp     short loc_1800616AF
0x1800616ad  mov     al, 1
0x1800616af  xor     r9d, r9d; char *
0x1800616b2  mov     rcx, [rbp+8]; this
0x1800616b6  test    r9d, r9d
0x1800616b9  js      loc_1800617BF
0x1800616bf  test    al, al
0x1800616c1  jnz     short loc_1800616D3
0x1800616c3  mov     rdx, rbx
0x1800616c6  mov     rcx, rdi
0x1800616c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800616ce  jmp     loc_18006178B
0x1800616d3  cmp     qword ptr [rbx+18h], 7
0x1800616d8  jbe     short loc_1800616DF
0x1800616da  mov     rcx, [rbx]
0x1800616dd  jmp     short loc_1800616E2
0x1800616df  mov     rcx, rbx; lpszShortPath
0x1800616e2  xor     r8d, r8d; cchBuffer
0x1800616e5  xor     edx, edx; lpszLongPath
0x1800616e7  call    cs:__imp_GetLongPathNameW
0x1800616ee  nop     dword ptr [rax+rax+00h]
0x1800616f3  mov     rcx, [rbp+8]; this
0x1800616f7  test    eax, eax
0x1800616f9  jz      loc_1800617D1
0x1800616ff  mov     edx, eax
0x180061701  lea     rcx, [rbp+lpszLongPath]
0x180061705  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18006170a  nop
0x18006170b  lea     rdx, [rbp+lpszLongPath]
0x18006170f  cmp     qword ptr [rbp+cchBuffer+8], 7
0x180061714  cmova   rdx, [rbp+lpszLongPath]; lpszLongPath
0x180061719  cmp     qword ptr [rbx+18h], 7
0x18006171e  jbe     short loc_180061723
0x180061720  mov     rbx, [rbx]
0x180061723  mov     r8d, [rbp+cchBuffer]; cchBuffer
0x180061727  mov     rcx, rbx; lpszShortPath
0x18006172a  call    cs:__imp_GetLongPathNameW
0x180061731  nop     dword ptr [rax+rax+00h]
0x180061736  mov     edx, eax
0x180061738  cmp     rdx, qword ptr [rbp+cchBuffer]
0x18006173c  setnbe  al
0x18006173f  mov     rcx, [rbp+8]; this
0x180061743  test    al, al
0x180061745  jnz     short loc_1800617AD
0x180061747  lea     rcx, [rbp+lpszLongPath]; Src
0x18006174b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180061750  mov     qword ptr [rdi+10h], 0
0x180061758  mov     qword ptr [rdi+18h], 0
0x180061760  movups  xmm0, xmmword ptr [rbp+lpszLongPath]
0x180061764  movups  xmmword ptr [rdi], xmm0
0x180061767  movups  xmm1, xmmword ptr [rbp+cchBuffer]
0x18006176b  movups  xmmword ptr [rdi+10h], xmm1
0x18006176f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180061777  movdqu  xmmword ptr [rbp+cchBuffer], xmm0
0x18006177c  xor     eax, eax
0x18006177e  mov     word ptr [rbp+lpszLongPath], ax
0x180061782  lea     rcx, [rbp+lpszLongPath]; void *
0x180061786  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006178b  mov     rax, rdi
0x18006178e  mov     rcx, [rbp+var_10]
0x180061792  xor     rcx, rsp; StackCookie
0x180061795  call    __security_check_cookie
0x18006179a  lea     r11, [rsp+60h+var_s0]
0x18006179f  mov     rbx, [r11+20h]
0x1800617a3  mov     rdi, [r11+28h]
0x1800617a7  mov     rsp, r11
0x1800617aa  pop     rbp
0x1800617ab  retn
0x1800617ad  lea     r8, aOnecoreBaseApp_38; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800617b4  mov     edx, 63h ; 'c'; void *
0x1800617b9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800617bf  lea     r8, aOnecoreBaseApp_38; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800617c6  mov     edx, 54h ; 'T'; void *
0x1800617cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800617d1  lea     r8, aOnecoreBaseApp_38; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800617d8  mov     edx, 5Fh ; '_'; void *
0x1800617dd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
