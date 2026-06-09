# EventManParser::DocumentRoot<0,ETW_PROVIDER_LIST>(ETW_PROVIDER_LIST &,wchar_t const *,long)

- ea: `0x18002c2fc`
- end: `0x18002c488`
- name: `??$DocumentRoot@$0A@VETW_PROVIDER_LIST@@@EventManParser@@AEAAXAEAVETW_PROVIDER_LIST@@PEB_WJ@Z`
- size: `396`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18003a680`
- `0x18003a720`

## callees

- `0x18001bf3c`
- `0x18001bf7c`
- `0x18001df64`
- `0x1800207c0`
- `0x18002c2fc`
- `0x18002c650`
- `0x180035858`
- `0x180037e80`
- `0x18003a638`
- `0x18004c010`

## string_xrefs

- `0x18002c3a5`: `instrumentationManifest`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EventManParser::DocumentRoot<0,ETW_PROVIDER_LIST>(
        XmlReader *this,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int128 *v5; // rcx
  __int128 v6; // xmm6
  __int128 v7; // xmm0
  enum XmlNodeType v8[3]; // [rsp+3Ch] [rbp-25h] BYREF
  __int128 v9; // [rsp+48h] [rbp-19h] BYREF
  __int128 v10; // [rsp+58h] [rbp-9h] BYREF
  __int128 v11; // [rsp+68h] [rbp+7h] BYREF
  unsigned __int64 v12; // [rsp+80h] [rbp+1Fh]

  *((_DWORD *)this + 17) = 0;
  *((_QWORD *)this + 9) = a3;
  if ( a4 && *((_QWORD *)this + 7) )
  {
    FormatErrorMessage(&v11, 1074261821, a4);
    v5 = &v11;
    if ( v12 > 0xF )
      v5 = (__int128 *)v11;
    (*((void (__fastcall **)(__int128 *, __int64, _QWORD))this + 7))(v5, 1074261821, *((_QWORD *)this + 9));
    std::string::_Tidy_deallocate(&v11);
  }
  XmlReader::GetLocalName(this);
  v6 = v9;
  v10 = v9;
  v11 = *(_OWORD *)&off_18004F7F0;
  *(_QWORD *)&v9 = L"instrumentationManifest";
  *((_QWORD *)&v9 + 1) = 23;
  if ( EventManParser::ElementMatches(this, &v9, &v11, &v10) )
  {
    v7 = *(_OWORD *)&off_18004F7F0;
  }
  else
  {
    v11 = v6;
    v10 = *(_OWORD *)&off_18004E0B0;
    *(_QWORD *)&v9 = L"assembly";
    *((_QWORD *)&v9 + 1) = 8;
    if ( !EventManParser::ElementMatches(this, &v9, &v10, &v11) )
      goto LABEL_12;
    v7 = *(_OWORD *)&off_18004E0B0;
  }
  v11 = v7;
  EventManParser::InstrumentationManifestType<0,ETW_PROVIDER_LIST>(this);
  v8[0] = XmlNodeType_None;
  while ( XmlReader::Read(this, v8) )
    ;
LABEL_12:
  EventManParser::ErrorWithFormatMessage(this, -1073221796);
}

```

## disassembly

```asm
0x18002c2fc  mov     rax, rsp
0x18002c2ff  push    rbp
0x18002c300  push    rbx
0x18002c301  push    rdi
0x18002c302  lea     rbp, [rax-5Fh]
0x18002c306  sub     rsp, 0A0h
0x18002c30d  movaps  xmmword ptr [rax-28h], xmm6
0x18002c311  mov     rax, cs:__security_cookie
0x18002c318  xor     rax, rsp
0x18002c31b  mov     [rbp+57h+var_30], rax
0x18002c31f  mov     rdi, rdx
0x18002c322  mov     rbx, rcx
0x18002c325  xor     eax, eax
0x18002c327  mov     [rbp+57h+var_80], ax
0x18002c32b  mov     [rcx+44h], eax
0x18002c32e  mov     [rcx+48h], r8
0x18002c332  test    r9d, r9d
0x18002c335  jz      short loc_18002C384
0x18002c337  cmp     [rcx+38h], rax
0x18002c33b  jz      short loc_18002C384
0x18002c33d  mov     r8d, r9d
0x18002c340  mov     edx, 4007EF3Dh
0x18002c345  lea     rcx, [rbp+57h+var_50]
0x18002c349  call    ?FormatErrorMessage@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@JZZ; FormatErrorMessage(long,...)
0x18002c34e  nop
0x18002c34f  lea     rcx, [rbp+57h+var_50]
0x18002c353  cmp     [rbp+57h+var_38], 0Fh
0x18002c358  cmova   rcx, qword ptr [rbp+57h+var_50]
0x18002c35d  mov     r9d, 1
0x18002c363  mov     [rsp+20h], r9d
0x18002c368  mov     r8, [rbx+48h]
0x18002c36c  mov     edx, 4007EF3Dh
0x18002c371  mov     rax, [rbx+38h]
0x18002c375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c37a  nop
0x18002c37b  lea     rcx, [rbp+57h+var_50]
0x18002c37f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002c384  lea     rdx, [rbp+57h+var_70]
0x18002c388  mov     rcx, rbx; this
0x18002c38b  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x18002c390  movaps  xmm6, [rbp+57h+var_70]
0x18002c394  movdqa  [rbp+57h+var_60], xmm6
0x18002c399  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18002c3a0  movdqu  [rbp+57h+var_50], xmm0
0x18002c3a5  lea     rax, aInstrumentatio_0; "instrumentationManifest"
0x18002c3ac  mov     qword ptr [rbp+57h+var_70], rax
0x18002c3b0  mov     qword ptr [rbp+57h+var_70+8], 17h
0x18002c3b8  lea     r9, [rbp+57h+var_60]
0x18002c3bc  lea     r8, [rbp+57h+var_50]
0x18002c3c0  lea     rdx, [rbp+57h+var_70]
0x18002c3c4  mov     rcx, rbx; this
0x18002c3c7  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18002c3cc  test    al, al
0x18002c3ce  jz      short loc_18002C3D9
0x18002c3d0  movups  xmm0, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x18002c3d7  jmp     short loc_18002C41C
0x18002c3d9  movdqa  [rbp+57h+var_50], xmm6
0x18002c3de  movups  xmm0, xmmword ptr cs:off_18004E0B0; "urn:schemas-microsoft-com:asm.v3"
0x18002c3e5  movdqu  [rbp+57h+var_60], xmm0
0x18002c3ea  lea     rax, aAssembly; "assembly"
0x18002c3f1  mov     qword ptr [rbp+57h+var_70], rax
0x18002c3f5  mov     qword ptr [rbp+57h+var_70+8], 8
0x18002c3fd  lea     r9, [rbp+57h+var_50]
0x18002c401  lea     r8, [rbp+57h+var_60]
0x18002c405  lea     rdx, [rbp+57h+var_70]
0x18002c409  mov     rcx, rbx; this
0x18002c40c  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x18002c411  test    al, al
0x18002c413  jz      short loc_18002C45C
0x18002c415  movups  xmm0, xmmword ptr cs:off_18004E0B0; "urn:schemas-microsoft-com:asm.v3"
0x18002c41c  movdqa  [rbp+57h+var_50], xmm0
0x18002c421  lea     r9, [rbp+57h+var_80]
0x18002c425  lea     r8, [rbp+57h+var_50]
0x18002c429  mov     rdx, rdi
0x18002c42c  mov     rcx, rbx; this
0x18002c42f  call    ??$InstrumentationManifestType@$0A@VETW_PROVIDER_LIST@@@EventManParser@@AEAAXAEAVETW_PROVIDER_LIST@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAUElementsFound@0@@Z; EventManParser::InstrumentationManifestType<0,ETW_PROVIDER_LIST>(ETW_PROVIDER_LIST &,std::wstring_view,EventManParser::ElementsFound *)
0x18002c434  mov     [rbp+57h+var_7C], 0
0x18002c43b  lea     rdx, [rbp+57h+var_7C]; enum XmlNodeType *
0x18002c43f  mov     rcx, rbx; this
0x18002c442  call    ?Read@XmlReader@@QEAA_NPEAW4XmlNodeType@@@Z; XmlReader::Read(XmlNodeType *)
0x18002c447  test    al, al
0x18002c449  jnz     short loc_18002C43B
0x18002c44b  cmp     byte ptr [rbp+57h+var_80], al
0x18002c44e  jz      short loc_18002C45C
0x18002c450  cmp     byte ptr [rbp+57h+var_80+1], al
0x18002c453  jnz     short loc_18002C469
0x18002c455  mov     edx, 0C007EF6Dh
0x18002c45a  jmp     short loc_18002C461
0x18002c45c  mov     edx, 0C007EF5Ch; int
0x18002c461  mov     rcx, rbx; this
0x18002c464  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18002c469  mov     rcx, [rbp+57h+var_30]
0x18002c46d  xor     rcx, rsp; StackCookie
0x18002c470  call    __security_check_cookie
0x18002c475  movaps  xmm6, [rsp+0B0h+var_28+8]
0x18002c47d  add     rsp, 0A0h
0x18002c484  pop     rdi
0x18002c485  pop     rbx
0x18002c486  pop     rbp
0x18002c487  retn
```
