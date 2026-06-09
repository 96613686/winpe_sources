# SimpleCbor::Encoder::EncodeTextWString(std::basic_string_view<ushort,std::char_traits<ushort>>,SimpleCbor::impl::slim_source_location)

- ea: `0x1800522f0`
- end: `0x1800525e9`
- name: `?EncodeTextWString@Encoder@SimpleCbor@@QEAAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@Uslim_source_location@impl@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180051810`
- `0x180051c44`
- `0x180053f70`

## callees

- `0x180003080`
- `0x180003bc8`
- `0x18000c95c`
- `0x18000ce74`
- `0x1800131dc`
- `0x18001361c`
- `0x180014d74`
- `0x180052240`
- `0x1800522f0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800523d3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800524d5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800523d3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800524d5`

## string_xrefs

- `0x180052558`: `onecore\ds\security\cbor\inc\simplecbor\SimpleCbor.h`
- `0x1800525c2`: `onecore\ds\security\cbor\inc\simplecbor\SimpleCbor.h`
- `0x1800525d3`: `onecore\ds\security\cbor\inc\simplecbor\SimpleCbor.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SimpleCbor::Encoder::EncodeTextWString(
        __int64 a1,
        _QWORD *a2,
        SimpleCbor::impl::slim_source_location *a3)
{
  CHAR *v4; // rcx
  unsigned __int64 v5; // rax
  const WCHAR *p_lpWideCharStr; // r8
  int v7; // eax
  const char *v8; // r9
  __int64 v9; // rdx
  unsigned __int64 v10; // rsi
  char *v11; // rbx
  CHAR *lpMultiByteStr; // rcx
  const WCHAR *v13; // r8
  const char *v14; // r9
  CHAR *v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  SimpleCbor::impl::slim_source_location *v19; // rcx
  const char *v20; // rax
  int v21; // edx
  _DWORD v23[2]; // [rsp+60h] [rbp-98h] BYREF
  const char *v24; // [rsp+68h] [rbp-90h]
  LPSTR Src[2]; // [rsp+70h] [rbp-88h] BYREF
  int cbMultiByte[4]; // [rsp+80h] [rbp-78h]
  __int128 lpWideCharStr; // [rsp+90h] [rbp-68h] BYREF
  int cchWideChar[2]; // [rsp+A0h] [rbp-58h]
  unsigned __int64 v29; // [rsp+A8h] [rbp-50h]
  __int128 v30; // [rsp+B0h] [rbp-48h] BYREF
  __int128 v31; // [rsp+C0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  try
  {
    lpWideCharStr = 0;
    *(_QWORD *)cchWideChar = 0;
    v29 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&lpWideCharStr, *a2, a2[1]);
    if ( *(_QWORD *)cchWideChar )
    {
      *(_OWORD *)Src = 0;
      *(_QWORD *)cbMultiByte = 0;
      *(_QWORD *)&cbMultiByte[2] = 15;
      LOBYTE(Src[0]) = 0;
      p_lpWideCharStr = (const WCHAR *)&lpWideCharStr;
      if ( v29 > 7 )
        p_lpWideCharStr = (const WCHAR *)lpWideCharStr;
      v7 = WideCharToMultiByte(0xFDE9u, 0x80u, p_lpWideCharStr, cchWideChar[0], 0, 0, 0, 0);
      if ( !v7 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecore\\ds\\security\\cbor\\inc\\simplecbor\\SimpleCbor.h",
          v8);
      v9 = *(_QWORD *)cbMultiByte;
      if ( (unsigned __int64)v7 > *(_QWORD *)cbMultiByte )
      {
        v10 = v7 - *(_QWORD *)cbMultiByte;
        if ( v10 > *(_QWORD *)&cbMultiByte[2] - *(_QWORD *)cbMultiByte )
        {
          std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(Src);
        }
        else
        {
          *(_QWORD *)cbMultiByte = v7;
          v11 = (char *)Src + v9;
          memset_0((char *)Src + v9, 0, v7 - v9);
          v11[v10] = 0;
        }
      }
      else
      {
        *(_QWORD *)cbMultiByte = v7;
        *((_BYTE *)Src + v7) = 0;
      }
      lpMultiByteStr = (CHAR *)Src;
      if ( *(_QWORD *)&cbMultiByte[2] > 0xFu )
        lpMultiByteStr = Src[0];
      v13 = (const WCHAR *)&lpWideCharStr;
      if ( v29 > 7 )
        v13 = (const WCHAR *)lpWideCharStr;
      if ( !WideCharToMultiByte(0xFDE9u, 0x80u, v13, cchWideChar[0], lpMultiByteStr, cbMultiByte[0], 0, 0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecore\\ds\\security\\cbor\\inc\\simplecbor\\SimpleCbor.h",
          v14);
      v30 = *(_OWORD *)Src;
      v31 = *(_OWORD *)cbMultiByte;
      *(_QWORD *)cbMultiByte = 0;
      *(_QWORD *)&cbMultiByte[2] = 15;
      LOBYTE(Src[0]) = 0;
      std::string::~string(Src);
      v5 = *((_QWORD *)&v31 + 1);
      v4 = (CHAR *)v31;
    }
    else
    {
      v30 = 0;
      v4 = 0;
      *(_QWORD *)&v31 = 0;
      v5 = 15;
      *((_QWORD *)&v31 + 1) = 15;
      LOBYTE(v30) = 0;
    }
  }
  catch ( ... )
  {
    SimpleCbor::impl::slim_source_location::line(a3);
    v20 = SimpleCbor::impl::slim_source_location::file_name(v19);
    wil::details::in1diag3::Throw_CaughtExceptionMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecore\\ds\\security\\cbor\\inc\\simplecbor\\SimpleCbor.h",
      "Caller: %hs:%u",
      v20,
      v21);
  }
  v15 = (CHAR *)&v30;
  if ( v5 > 0xF )
    v15 = (CHAR *)v30;
  v23[0] = 331;
  v23[1] = HIDWORD(Src[0]);
  v24 = "onecore\\ds\\security\\cbor\\inc\\simplecbor\\SimpleCbor.h";
  Src[0] = v15;
  Src[1] = v4;
  SimpleCbor::Encoder::EncodeTextString(a1, Src, v23);
  std::string::~string(&v30);
  return std::wstring::~wstring(&lpWideCharStr, v16, v17);
}

```

## disassembly

```asm
0x1800522f0  mov     r11, rsp
0x1800522f3  mov     [r11+20h], rbx
0x1800522f7  push    rsi
0x1800522f8  push    r14
0x1800522fa  push    r15
0x1800522fc  sub     rsp, 0E0h
0x180052303  mov     rax, cs:__security_cookie
0x18005230a  xor     rax, rsp
0x18005230d  mov     [rsp+0F8h+var_28], rax
0x180052315  mov     r14, rcx
0x180052318  mov     [rsp+0F8h+var_A8], r8
0x18005231d  xor     r15d, r15d
0x180052320  xorps   xmm0, xmm0
0x180052323  movups  xmmword ptr [r11-68h], xmm0
0x180052328  mov     [r11-58h], r15
0x18005232c  mov     [r11-50h], r15
0x180052330  mov     r8, [rdx+8]
0x180052334  mov     rdx, [rdx]
0x180052337  lea     rcx, [r11-68h]
0x18005233b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180052340  nop
0x180052341  mov     r9, qword ptr [rsp+0F8h+cchWideChar]; cchWideChar
0x180052349  xorps   xmm0, xmm0
0x18005234c  test    r9, r9
0x18005234f  jnz     short loc_18005237D
0x180052351  movups  [rsp+0F8h+var_48], xmm0
0x180052359  mov     ecx, r15d
0x18005235c  mov     qword ptr [rsp+0F8h+var_38], rcx
0x180052364  lea     eax, [r15+0Fh]
0x180052368  mov     qword ptr [rsp+0F8h+var_38+8], rax
0x180052370  mov     byte ptr [rsp+0F8h+var_48], r15b
0x180052378  jmp     loc_180052533
0x18005237d  movups  xmmword ptr [rsp+0F8h+Src], xmm0
0x180052382  mov     qword ptr [rsp+0F8h+var_78], r15
0x18005238a  mov     qword ptr [rsp+0F8h+var_78+8], 0Fh
0x180052396  mov     byte ptr [rsp+0F8h+Src], r15b
0x18005239b  lea     r8, [rsp+0F8h+lpWideCharStr]
0x1800523a3  cmp     [rsp+0F8h+var_50], 7
0x1800523ac  cmova   r8, qword ptr [rsp+0F8h+lpWideCharStr]; lpWideCharStr
0x1800523b5  mov     [rsp+0F8h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800523ba  mov     [rsp+0F8h+lpDefaultChar], r15; lpDefaultChar
0x1800523bf  mov     [rsp+0F8h+cbMultiByte], r15d; cbMultiByte
0x1800523c4  mov     [rsp+0F8h+lpMultiByteStr], r15; lpMultiByteStr
0x1800523c9  mov     edx, 80h; dwFlags
0x1800523ce  mov     ecx, 0FDE9h; CodePage
0x1800523d3  call    cs:__imp_WideCharToMultiByte
0x1800523d9  mov     rcx, [rsp+0F8h]; this
0x1800523e1  test    eax, eax
0x1800523e3  jz      loc_1800525C2
0x1800523e9  mov     rdx, qword ptr [rsp+0F8h+var_78]
0x1800523f1  movsxd  rcx, eax
0x1800523f4  cmp     rcx, rdx
0x1800523f7  ja      short loc_18005241B
0x1800523f9  mov     qword ptr [rsp+0F8h+var_78], rcx
0x180052401  lea     rax, [rsp+0F8h+Src]
0x180052406  cmp     qword ptr [rsp+0F8h+var_78+8], 0Fh
0x18005240f  cmova   rax, [rsp+0F8h+Src]
0x180052415  mov     [rcx+rax], r15b
0x180052419  jmp     short loc_180052473
0x18005241b  mov     rsi, rcx
0x18005241e  sub     rsi, rdx
0x180052421  mov     rax, qword ptr [rsp+0F8h+var_78+8]
0x180052429  sub     rax, rdx
0x18005242c  cmp     rsi, rax
0x18005242f  ja      short loc_180052463
0x180052431  mov     qword ptr [rsp+0F8h+var_78], rcx
0x180052439  lea     rbx, [rsp+0F8h+Src]
0x18005243e  cmp     qword ptr [rsp+0F8h+var_78+8], 0Fh
0x180052447  cmova   rbx, [rsp+0F8h+Src]
0x18005244d  add     rbx, rdx
0x180052450  mov     r8, rsi; Size
0x180052453  xor     edx, edx; Val
0x180052455  mov     rcx, rbx; void *
0x180052458  call    memset_0
0x18005245d  mov     [rsi+rbx], r15b
0x180052461  jmp     short loc_180052473
0x180052463  mov     r9, rsi
0x180052466  mov     rdx, rsi
0x180052469  lea     rcx, [rsp+0F8h+Src]; Src
0x18005246e  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x180052473  mov     eax, [rsp+0F8h+var_78]
0x18005247a  lea     rcx, [rsp+0F8h+Src]
0x18005247f  cmp     qword ptr [rsp+0F8h+var_78+8], 0Fh
0x180052488  cmova   rcx, [rsp+0F8h+Src]
0x18005248e  lea     r8, [rsp+0F8h+lpWideCharStr]
0x180052496  cmp     [rsp+0F8h+var_50], 7
0x18005249f  cmova   r8, qword ptr [rsp+0F8h+lpWideCharStr]; lpWideCharStr
0x1800524a8  mov     rbx, [rsp+0F8h]
0x1800524b0  mov     [rsp+0F8h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800524b5  mov     [rsp+0F8h+lpDefaultChar], r15; lpDefaultChar
0x1800524ba  mov     [rsp+0F8h+cbMultiByte], eax; cbMultiByte
0x1800524be  mov     [rsp+0F8h+lpMultiByteStr], rcx; lpMultiByteStr
0x1800524c3  mov     r9d, [rsp+0F8h+cchWideChar]; cchWideChar
0x1800524cb  mov     edx, 80h; dwFlags
0x1800524d0  mov     ecx, 0FDE9h; CodePage
0x1800524d5  call    cs:__imp_WideCharToMultiByte
0x1800524db  test    eax, eax
0x1800524dd  jz      loc_1800525D3
0x1800524e3  movups  xmm0, xmmword ptr [rsp+0F8h+Src]
0x1800524e8  movups  [rsp+0F8h+var_48], xmm0
0x1800524f0  movups  xmm1, xmmword ptr [rsp+0F8h+var_78]
0x1800524f8  movups  [rsp+0F8h+var_38], xmm1
0x180052500  mov     qword ptr [rsp+0F8h+var_78], r15
0x180052508  mov     qword ptr [rsp+0F8h+var_78+8], 0Fh
0x180052514  mov     byte ptr [rsp+0F8h+Src], r15b
0x180052519  lea     rcx, [rsp+0F8h+Src]
0x18005251e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180052523  mov     rax, qword ptr [rsp+0F8h+var_38+8]
0x18005252b  mov     rcx, qword ptr [rsp+0F8h+var_38]
0x180052533  lea     rdx, [rsp+0F8h+var_48]
0x18005253b  cmp     rax, 0Fh
0x18005253f  cmova   rdx, qword ptr [rsp+0F8h+var_48]
0x180052548  mov     [rsp+0F8h+var_98], 14Bh
0x180052550  mov     eax, dword ptr [rsp+0F8h+Src+4]
0x180052554  mov     [rsp+0F8h+var_94], eax
0x180052558  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cbor\\inc\\simpl"...
0x18005255f  mov     [rsp+0F8h+var_90], rax
0x180052564  mov     [rsp+0F8h+Src], rdx
0x180052569  mov     [rsp+0F8h+Src+8], rcx
0x18005256e  lea     r8, [rsp+0F8h+var_98]
0x180052573  lea     rdx, [rsp+0F8h+Src]
0x180052578  mov     rcx, r14
0x18005257b  call    ?EncodeTextString@Encoder@SimpleCbor@@QEAAXV?$basic_string_view@DU?$char_traits@D@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Encoder::EncodeTextString(std::string_view,SimpleCbor::impl::slim_source_location)
0x180052580  nop
0x180052581  lea     rcx, [rsp+0F8h+var_48]
0x180052589  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18005258e  nop
0x18005258f  lea     rcx, [rsp+0F8h+lpWideCharStr]
0x180052597  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005259c  nop
0x18005259d  mov     rcx, [rsp+0F8h+var_28]
0x1800525a5  xor     rcx, rsp; StackCookie
0x1800525a8  call    __security_check_cookie
0x1800525ad  mov     rbx, [rsp+0F8h+arg_18]
0x1800525b5  add     rsp, 0E0h
0x1800525bc  pop     r15
0x1800525be  pop     r14
0x1800525c0  pop     rsi
0x1800525c1  retn
0x1800525c2  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cbor\\inc\\simpl"...
0x1800525c9  mov     edx, 80h; void *
0x1800525ce  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800525d3  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cbor\\inc\\simpl"...
0x1800525da  mov     edx, 8Dh; void *
0x1800525df  mov     rcx, rbx; this
0x1800525e2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
