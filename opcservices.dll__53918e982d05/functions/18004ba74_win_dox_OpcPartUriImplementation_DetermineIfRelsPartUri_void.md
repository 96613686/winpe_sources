# win_dox::OpcPartUriImplementation::DetermineIfRelsPartUri(void)

- ea: `0x18004ba74`
- end: `0x18004bcf1`
- name: `?DetermineIfRelsPartUri@OpcPartUriImplementation@win_dox@@AEAAXXZ`
- size: `637`
- prototype: `void __fastcall(win_dox::OpcPartUriImplementation *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18004b998`
- `0x18004b9f4`

## callees

- `0x18001631c`
- `0x180016d00`
- `0x1800175b0`
- `0x18002db70`
- `0x18004aa18`
- `0x18004ba74`
- `0x18004bcf8`
- `0x18004beb0`
- `0x180059fe0`
- `0x18006554c`
- `0x18007e7a4`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004bb28`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004bb28`

## string_xrefs

- `0x18004bbfa`: `::CompareString returned invalid return value`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall win_dox::OpcPartUriImplementation::DetermineIfRelsPartUri(win_dox::OpcPartUriImplementation *this)
{
  __int64 v2; // rbx
  const WCHAR *p_lpString1; // rcx
  bool v4; // di
  int v5; // eax
  win_musl::detail *v6; // rcx
  int v7; // eax
  const struct win_dox::OpcPartUri *PackageRelationshipUri; // rax
  int v9; // ebx
  const wchar_t *v10; // rcx
  unsigned int LastErrorAsFailHR; // [rsp+28h] [rbp-D8h]
  __int64 v12; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[8]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v15; // [rsp+68h] [rbp-98h] BYREF
  __int64 v16; // [rsp+78h] [rbp-88h]
  unsigned __int64 v17; // [rsp+80h] [rbp-80h]
  _BYTE v18[8]; // [rsp+88h] [rbp-78h] BYREF
  LPCWCH lpString1; // [rsp+90h] [rbp-70h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v21; // [rsp+A8h] [rbp-58h]
  _BYTE v22[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *Block; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v24; // [rsp+D0h] [rbp-30h]
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-20h] BYREF

  v13[1] = -2;
  v12 = 0;
  v2 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 8LL))(*(_QWORD *)this);
  v12 = v2;
  v13[2] = &v12;
  win_dox::to_interface<IByteReceiver>::resolve(v13);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  win_dox::Uri::GetExtension(v13, v18);
  if ( !v20 )
    goto LABEL_9;
  p_lpString1 = (const WCHAR *)&lpString1;
  if ( v21 >= 8 )
    p_lpString1 = lpString1;
  v4 = 1;
  v5 = CompareStringOrdinal(p_lpString1, -1, L".rels", -1, 1) - 1;
  if ( !v5 )
    goto LABEL_9;
  v7 = v5 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
    {
      LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v6);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x5B4u,
        LastErrorAsFailHR,
        (struct win_musl::TStringEllipseBase *)L"::CompareString returned invalid return value");
      throw (SplException::THResultException *)pExceptionObject;
    }
LABEL_9:
    v4 = 0;
    goto LABEL_10;
  }
  PackageRelationshipUri = (const struct win_dox::OpcPartUri *)GetPackageRelationshipUri(v14);
  v9 = win_dox::OpcPartUriImplementation::ComparePartUri(this, PackageRelationshipUri);
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v14);
  if ( v9 )
  {
    win_dox::Uri::GetPath(v13, v22);
    FindLastSegment(v14, v22);
    if ( v16 )
    {
      v10 = (const wchar_t *)&v15;
      if ( v17 >= 8 )
        v10 = v15;
      v4 = Compare(v10, L"_rels") == 0;
    }
    if ( v17 >= 8 )
      operator delete(v15);
    v17 = 7;
    v16 = 0;
    LOWORD(v15) = 0;
    if ( v24 >= 8 )
      operator delete(Block);
  }
LABEL_10:
  *((_DWORD *)this + 14) = v4;
  if ( v21 >= 8 )
    operator delete((void *)lpString1);
  v21 = 7;
  v20 = 0;
  LOWORD(lpString1) = 0;
  if ( v13[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
}

```

## disassembly

```asm
0x18004ba74  push    rbp
0x18004ba76  push    rbx
0x18004ba77  push    rsi
0x18004ba78  push    rdi
0x18004ba79  lea     rbp, [rsp-98h]
0x18004ba81  sub     rsp, 198h
0x18004ba88  mov     [rsp+1B0h+var_160], 0FFFFFFFFFFFFFFFEh
0x18004ba91  mov     rax, cs:__security_cookie
0x18004ba98  xor     rax, rsp
0x18004ba9b  mov     [rbp+0B0h+var_30], rax
0x18004baa2  mov     rsi, rcx
0x18004baa5  xor     ecx, ecx
0x18004baa7  mov     [rsp+1B0h+var_170], rcx
0x18004baac  mov     rbx, [rsi]
0x18004baaf  test    rbx, rbx
0x18004bab2  jnz     loc_18004BBB1
0x18004bab8  mov     [rsp+1B0h+var_170], rbx
0x18004babd  test    rcx, rcx
0x18004bac0  jnz     loc_18004BBCA
0x18004bac6  lea     rax, [rsp+1B0h+var_170]
0x18004bacb  mov     [rsp+1B0h+var_158], rax
0x18004bad0  lea     rdx, [rsp+1B0h+var_170]
0x18004bad5  lea     rcx, [rsp+1B0h+var_168]
0x18004bada  call    ?resolve@?$to_interface@UIByteReceiver@@@win_dox@@SA?AV?$scope@PEAUIByteReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBV34@@Z; win_dox::to_interface<IByteReceiver>::resolve(win_scope::scope<IByteReceiver *,win_scope::const_policies<win_scope::com_policies>> const &)
0x18004badf  nop
0x18004bae0  mov     rcx, [rsp+1B0h+var_170]
0x18004bae5  test    rcx, rcx
0x18004bae8  jnz     loc_18004BB97
0x18004baee  lea     rdx, [rbp+0B0h+var_128]
0x18004baf2  lea     rcx, [rsp+1B0h+var_168]
0x18004baf7  call    ?GetExtension@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetExtension(void)
0x18004bafc  nop
0x18004bafd  cmp     [rbp+0B0h+var_110], 0
0x18004bb02  jz      short loc_18004BB36
0x18004bb04  lea     rcx, [rbp+0B0h+lpString1]
0x18004bb08  cmp     [rbp+0B0h+var_108], 8
0x18004bb0d  cmovnb  rcx, [rbp+0B0h+lpString1]; lpString1
0x18004bb12  mov     edi, 1
0x18004bb17  mov     [rsp+1B0h+bIgnoreCase], edi; bIgnoreCase
0x18004bb1b  or      edx, 0FFFFFFFFh; cchCount1
0x18004bb1e  mov     r9d, edx; cchCount2
0x18004bb21  lea     r8, ?g_relationshipsExtension@win_musl@@3QB_WB; ".rels"
0x18004bb28  call    cs:__imp_CompareStringOrdinal
0x18004bb2e  sub     eax, edi
0x18004bb30  jnz     loc_18004BBE9
0x18004bb36  xor     dil, dil
0x18004bb39  xor     eax, eax
0x18004bb3b  test    dil, dil
0x18004bb3e  setnz   al
0x18004bb41  mov     [rsi+38h], eax
0x18004bb44  cmp     [rbp+0B0h+var_108], 8
0x18004bb49  jnb     loc_18004BBDB
0x18004bb4f  mov     [rbp+0B0h+var_108], 7
0x18004bb57  mov     [rbp+0B0h+var_110], 0
0x18004bb5f  xor     eax, eax
0x18004bb61  mov     word ptr [rbp+0B0h+lpString1], ax
0x18004bb65  mov     rcx, [rsp+1B0h+var_168]
0x18004bb6a  test    rcx, rcx
0x18004bb6d  jz      short loc_18004BB7C
0x18004bb6f  mov     rax, [rcx]
0x18004bb72  mov     rax, [rax+10h]
0x18004bb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb7b  nop
0x18004bb7c  mov     rcx, [rbp+0B0h+var_30]
0x18004bb83  xor     rcx, rsp; StackCookie
0x18004bb86  call    __security_check_cookie
0x18004bb8b  add     rsp, 198h
0x18004bb92  pop     rdi
0x18004bb93  pop     rsi
0x18004bb94  pop     rbx
0x18004bb95  pop     rbp
0x18004bb96  retn
0x18004bb97  mov     rax, [rcx]
0x18004bb9a  mov     rax, [rax+10h]
0x18004bb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bba3  mov     [rsp+1B0h+var_170], 0
0x18004bbac  jmp     loc_18004BAEE
0x18004bbb1  mov     rax, [rbx]
0x18004bbb4  mov     rcx, rbx
0x18004bbb7  mov     rax, [rax+8]
0x18004bbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbc0  mov     rcx, [rsp+1B0h+var_170]
0x18004bbc5  jmp     loc_18004BAB8
0x18004bbca  mov     rax, [rcx]
0x18004bbcd  mov     rax, [rax+10h]
0x18004bbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbd6  jmp     loc_18004BAC6
0x18004bbdb  mov     rcx, [rbp+0B0h+lpString1]; Block
0x18004bbdf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004bbe4  jmp     loc_18004BB4F
0x18004bbe9  sub     eax, edi
0x18004bbeb  jz      short loc_18004BC3A
0x18004bbed  cmp     eax, edi
0x18004bbef  jz      loc_18004BB36
0x18004bbf5  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18004bbfa  lea     rcx, aComparestringR; "::CompareString returned invalid return"...
0x18004bc01  mov     [rsp+1B0h+var_180], rcx; struct win_musl::TStringEllipseBase *
0x18004bc06  mov     [rsp+1B0h+var_188], eax; unsigned int
0x18004bc0a  mov     [rsp+1B0h+bIgnoreCase], 5B4h; unsigned int
0x18004bc12  lea     r9, word_180139126
0x18004bc19  lea     r8, aNoFilename; "(no filename)"
0x18004bc20  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x18004bc24  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004bc29  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004bc30  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x18004bc34  call    _CxxThrowException_0
0x18004bc3a  lea     rcx, [rsp+1B0h+var_150]
0x18004bc3f  call    ?GetPackageRelationshipUri@@YA?AVOpcPartUri@win_dox@@XZ; GetPackageRelationshipUri(void)
0x18004bc44  nop
0x18004bc45  mov     rdx, rax; struct win_dox::OpcPartUri *
0x18004bc48  mov     rcx, rsi; this
0x18004bc4b  call    ?ComparePartUri@OpcPartUriImplementation@win_dox@@QEBAHAEBVOpcPartUri@2@@Z; win_dox::OpcPartUriImplementation::ComparePartUri(win_dox::OpcPartUri const &)
0x18004bc50  mov     ebx, eax
0x18004bc52  lea     rcx, [rsp+1B0h+var_150]; this
0x18004bc57  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x18004bc5c  test    ebx, ebx
0x18004bc5e  jz      loc_18004BB39
0x18004bc64  lea     rdx, [rbp+0B0h+var_100]
0x18004bc68  lea     rcx, [rsp+1B0h+var_168]
0x18004bc6d  call    ?GetPath@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetPath(void)
0x18004bc72  nop
0x18004bc73  lea     rdx, [rbp+0B0h+var_100]
0x18004bc77  lea     rcx, [rsp+1B0h+var_150]
0x18004bc7c  call    ?FindLastSegment@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV12@@Z; FindLastSegment(std::wstring const &)
0x18004bc81  nop
0x18004bc82  cmp     [rsp+1B0h+var_138], 0
0x18004bc88  jz      short loc_18004BCAC
0x18004bc8a  lea     rcx, [rsp+1B0h+var_148]
0x18004bc8f  cmp     [rbp+0B0h+var_130], 8
0x18004bc94  cmovnb  rcx, [rsp+1B0h+var_148]; wchar_t *
0x18004bc9a  lea     rdx, ?g_relationshipsSegment@win_musl@@3QB_WB; "_rels"
0x18004bca1  call    ?Compare@@YAHPEB_W0@Z; Compare(wchar_t const *,wchar_t const *)
0x18004bca6  test    eax, eax
0x18004bca8  setz    dil
0x18004bcac  cmp     [rbp+0B0h+var_130], 8
0x18004bcb1  jnb     short loc_18004BCE4
0x18004bcb3  mov     [rbp+0B0h+var_130], 7
0x18004bcbb  mov     [rsp+1B0h+var_138], 0
0x18004bcc4  xor     eax, eax
0x18004bcc6  mov     word ptr [rsp+1B0h+var_148], ax
0x18004bccb  cmp     [rbp+0B0h+var_E0], 8
0x18004bcd0  jb      loc_18004BB39
0x18004bcd6  mov     rcx, [rbp+0B0h+Block]; Block
0x18004bcda  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004bcdf  jmp     loc_18004BB39
0x18004bce4  mov     rcx, [rsp+1B0h+var_148]; Block
0x18004bce9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004bcee  jmp     short loc_18004BCB3
```
