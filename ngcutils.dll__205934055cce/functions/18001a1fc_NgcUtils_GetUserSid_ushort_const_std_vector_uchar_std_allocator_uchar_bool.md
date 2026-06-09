# NgcUtils::GetUserSid(ushort const *,std::vector<uchar,std::allocator<uchar>> *,bool *)

- ea: `0x18001a1fc`
- end: `0x18001a4c7`
- name: `?GetUserSid@NgcUtils@@YAJPEBGPEAV?$vector@EV?$allocator@E@std@@@std@@PEA_N@Z`
- size: `715`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180011190`

## callees

- `0x18000113c`
- `0x180003080`
- `0x18000a5b4`
- `0x18000c95c`
- `0x18000ce74`
- `0x18000cfcc`
- `0x18001558c`
- `0x18001565c`
- `0x1800163bc`
- `0x180018010`
- `0x1800185d0`
- `0x18001a1fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3ba`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18001a2dc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18001a3b0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18001a2dc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18001a3b0`

## string_xrefs

- `0x18001a23e`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::GetUserSid(NgcUtils::Detail *lpAccountName, __int64 a2, _BYTE *a3)
{
  int updated; // eax
  __int64 v7; // r8
  int UserSid; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  signed int LastError; // ebx
  WCHAR *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  int cchReferencedDomainName; // [rsp+20h] [rbp-69h]
  int v19; // [rsp+30h] [rbp-59h] BYREF
  DWORD v20; // [rsp+34h] [rbp-55h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-51h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+3Ch] [rbp-4Dh] BYREF
  PSID Sid[3]; // [rsp+40h] [rbp-49h] BYREF
  LPWSTR ReferencedDomainName[2]; // [rsp+58h] [rbp-31h] BYREF
  __m128i si128; // [rsp+68h] [rbp-21h]
  int *v26; // [rsp+78h] [rbp-11h]
  __int64 v27; // [rsp+80h] [rbp-9h]
  struct _EVENT_DATA_DESCRIPTOR v28[2]; // [rsp+88h] [rbp-1h] BYREF
  int *v29; // [rsp+A8h] [rbp+1Fh]
  __int64 v30; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  updated = NgcUtils::Detail::CacheUpdateVersion(lpAccountName);
  if ( updated < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)updated,
      cchReferencedDomainName);
  *(_OWORD *)ReferencedDomainName = 0;
  si128 = 0;
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)lpAccountName + v7) );
  std::wstring::_Construct<1,unsigned short const *>(ReferencedDomainName, lpAccountName, v7);
  UserSid = NgcUtils::Detail::CacheGetUserSid(ReferencedDomainName, a2);
  std::wstring::~wstring(ReferencedDomainName, v9, v10);
  if ( UserSid >= 0 )
  {
    if ( a3 )
      *a3 = 1;
    return 0;
  }
  if ( a3 )
    *a3 = 0;
  cbSid = 0;
  v20 = 0;
  peUse = SidTypeUnknown;
  if ( LookupAccountNameLocalW((LPCWSTR)lpAccountName, 0, &cbSid, 0, &v20, &peUse) )
  {
    if ( (unsigned int)dword_180075000 > 2 )
    {
      v19 = -2147418113;
      v29 = &v19;
      v30 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180075000, (unsigned __int8 *)byte_180068B0D, 0, 0, 3u, v28);
    }
    return 2147549183LL;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      std::vector<unsigned char>::vector<unsigned char>(Sid, cbSid);
      *(_OWORD *)ReferencedDomainName = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(ReferencedDomainName[0]) = 0;
      std::wstring::resize(ReferencedDomainName);
      v13 = (WCHAR *)ReferencedDomainName;
      if ( si128.m128i_i64[1] > 7uLL )
        v13 = ReferencedDomainName[0];
      if ( LookupAccountNameLocalW((LPCWSTR)lpAccountName, Sid[0], &cbSid, v13, &v20, &peUse) )
      {
        std::wstring::~wstring(ReferencedDomainName, v14, v15);
        std::vector<unsigned char>::operator=(a2, Sid);
        std::vector<unsigned char>::~vector<unsigned char>(Sid);
        return 0;
      }
      LastError = GetLastError();
      if ( (unsigned int)dword_180075000 > 2 )
      {
        v19 = LastError;
        v29 = &v19;
        v30 = 4;
        tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180075000, (unsigned __int8 *)&unk_180068AD8, 0, 0, 3u, v28);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      std::wstring::~wstring(ReferencedDomainName, v16, v17);
      std::vector<unsigned char>::~vector<unsigned char>(Sid);
    }
    else
    {
      if ( (unsigned int)dword_180075000 > 2 )
      {
        v19 = LastError;
        v26 = &v19;
        v27 = 4;
        tlgWriteTransfer_EventWriteTransfer(
          (__int64)&dword_180075000,
          (unsigned __int8 *)word_180068B5A,
          0,
          0,
          3u,
          (PEVENT_DATA_DESCRIPTOR)ReferencedDomainName);
      }
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    return (unsigned int)LastError;
  }
}

```

## disassembly

```asm
0x18001a1fc  mov     [rsp-8+arg_18], rbx
0x18001a201  push    rbp
0x18001a202  push    rsi
0x18001a203  push    rdi
0x18001a204  push    r14
0x18001a206  push    r15
0x18001a208  lea     rbp, [rsp-37h]
0x18001a20d  sub     rsp, 0C0h
0x18001a214  mov     rax, cs:__security_cookie
0x18001a21b  xor     rax, rsp
0x18001a21e  mov     [rbp+57h+var_28], rax
0x18001a222  mov     rdi, r8
0x18001a225  mov     r14, rdx
0x18001a228  mov     rsi, rcx
0x18001a22b  call    ?CacheUpdateVersion@Detail@NgcUtils@@YAJXZ; NgcUtils::Detail::CacheUpdateVersion(void)
0x18001a230  xor     r15d, r15d
0x18001a233  test    eax, eax
0x18001a235  jns     short loc_18001A24F
0x18001a237  mov     rcx, [rbp+5Fh]; this
0x18001a23b  mov     r9d, eax; char *
0x18001a23e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001a245  mov     edx, 0AAh; void *
0x18001a24a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a24f  xorps   xmm0, xmm0
0x18001a252  movups  xmmword ptr [rbp+57h+ReferencedDomainName], xmm0
0x18001a256  xorps   xmm1, xmm1
0x18001a259  movdqu  [rbp+57h+var_78], xmm1
0x18001a25e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a262  inc     r8
0x18001a265  cmp     [rsi+r8*2], r15w
0x18001a26a  jnz     short loc_18001A262
0x18001a26c  mov     rdx, rsi
0x18001a26f  lea     rcx, [rbp+57h+ReferencedDomainName]
0x18001a273  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a278  nop
0x18001a279  mov     rdx, r14
0x18001a27c  lea     rcx, [rbp+57h+ReferencedDomainName]
0x18001a280  call    ?CacheGetUserSid@Detail@NgcUtils@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$vector@EV?$allocator@E@std@@@4@@Z; NgcUtils::Detail::CacheGetUserSid(std::wstring const &,std::vector<uchar> *)
0x18001a285  mov     ebx, eax
0x18001a287  lea     rcx, [rbp+57h+ReferencedDomainName]
0x18001a28b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a290  shr     ebx, 1Fh
0x18001a293  xor     bl, 1
0x18001a296  jz      short loc_18001A2A7
0x18001a298  test    rdi, rdi
0x18001a29b  jz      short loc_18001A2A0
0x18001a29d  mov     byte ptr [rdi], 1
0x18001a2a0  xor     eax, eax
0x18001a2a2  jmp     loc_18001A4A4
0x18001a2a7  test    rdi, rdi
0x18001a2aa  jz      short loc_18001A2AF
0x18001a2ac  mov     [rdi], r15b
0x18001a2af  mov     [rbp+57h+cbSid], r15d
0x18001a2b3  mov     [rbp+57h+var_AC], r15d
0x18001a2b7  mov     [rbp+57h+var_A4], 8
0x18001a2be  lea     rax, [rbp+57h+var_A4]
0x18001a2c2  mov     [rsp+0E0h+peUse], rax; peUse
0x18001a2c7  lea     rax, [rbp+57h+var_AC]
0x18001a2cb  mov     [rsp+0E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001a2d0  xor     r9d, r9d; ReferencedDomainName
0x18001a2d3  lea     r8, [rbp+57h+cbSid]; cbSid
0x18001a2d7  xor     edx, edx; Sid
0x18001a2d9  mov     rcx, rsi; lpAccountName
0x18001a2dc  call    cs:__imp_LookupAccountNameLocalW
0x18001a2e2  test    eax, eax
0x18001a2e4  jnz     loc_18001A453
0x18001a2ea  call    cs:__imp_GetLastError
0x18001a2f0  mov     ebx, eax
0x18001a2f2  cmp     eax, 7Ah ; 'z'
0x18001a2f5  jz      short loc_18001A353
0x18001a2f7  mov     eax, cs:dword_180075000
0x18001a2fd  cmp     eax, 2
0x18001a300  jbe     short loc_18001A33F
0x18001a302  mov     [rbp+57h+var_B0], ebx
0x18001a305  lea     rax, [rbp+57h+var_B0]
0x18001a309  mov     [rbp+57h+var_68], rax
0x18001a30d  mov     [rbp+57h+var_60], 4
0x18001a315  lea     rax, [rbp+57h+ReferencedDomainName]
0x18001a319  mov     [rsp+0E0h+peUse], rax
0x18001a31e  mov     dword ptr [rsp+0E0h+cchReferencedDomainName], 3
0x18001a326  xor     r9d, r9d
0x18001a329  xor     r8d, r8d
0x18001a32c  lea     rdx, word_180068B5A
0x18001a333  lea     rcx, dword_180075000
0x18001a33a  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a33f  test    ebx, ebx
0x18001a341  jle     short loc_18001A34C
0x18001a343  movzx   ebx, bx
0x18001a346  or      ebx, 80070000h
0x18001a34c  mov     eax, ebx
0x18001a34e  jmp     loc_18001A4A4
0x18001a353  mov     edx, [rbp+57h+cbSid]
0x18001a356  lea     rcx, [rbp+57h+Sid]
0x18001a35a  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18001a35f  nop
0x18001a360  xorps   xmm0, xmm0
0x18001a363  movups  xmmword ptr [rbp+57h+ReferencedDomainName], xmm0
0x18001a367  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001a36f  movdqu  [rbp+57h+var_78], xmm1
0x18001a374  mov     word ptr [rbp+57h+ReferencedDomainName], r15w
0x18001a379  mov     edx, [rbp+57h+var_AC]
0x18001a37c  lea     rcx, [rbp+57h+ReferencedDomainName]; Src
0x18001a380  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001a385  lea     r9, [rbp+57h+ReferencedDomainName]
0x18001a389  cmp     qword ptr [rbp+57h+var_78+8], 7
0x18001a38e  cmova   r9, [rbp+57h+ReferencedDomainName]; ReferencedDomainName
0x18001a393  lea     rax, [rbp+57h+var_A4]
0x18001a397  mov     [rsp+0E0h+peUse], rax; peUse
0x18001a39c  lea     rax, [rbp+57h+var_AC]
0x18001a3a0  mov     [rsp+0E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001a3a5  lea     r8, [rbp+57h+cbSid]; cbSid
0x18001a3a9  mov     rdx, [rbp+57h+Sid]; Sid
0x18001a3ad  mov     rcx, rsi; lpAccountName
0x18001a3b0  call    cs:__imp_LookupAccountNameLocalW
0x18001a3b6  test    eax, eax
0x18001a3b8  jnz     short loc_18001A42F
0x18001a3ba  call    cs:__imp_GetLastError
0x18001a3c0  mov     ebx, eax
0x18001a3c2  mov     eax, cs:dword_180075000
0x18001a3c8  cmp     eax, 2
0x18001a3cb  jbe     short loc_18001A40A
0x18001a3cd  mov     [rbp+57h+var_B0], ebx
0x18001a3d0  lea     rax, [rbp+57h+var_B0]
0x18001a3d4  mov     [rbp+57h+var_38], rax
0x18001a3d8  mov     [rbp+57h+var_30], 4
0x18001a3e0  lea     rax, [rbp+57h+var_58]
0x18001a3e4  mov     [rsp+0E0h+peUse], rax
0x18001a3e9  mov     dword ptr [rsp+0E0h+cchReferencedDomainName], 3
0x18001a3f1  xor     r9d, r9d
0x18001a3f4  xor     r8d, r8d
0x18001a3f7  lea     rdx, unk_180068AD8
0x18001a3fe  lea     rcx, dword_180075000
0x18001a405  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a40a  test    ebx, ebx
0x18001a40c  jle     short loc_18001A417
0x18001a40e  movzx   ebx, bx
0x18001a411  or      ebx, 80070000h
0x18001a417  lea     rcx, [rbp+57h+ReferencedDomainName]
0x18001a41b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a420  nop
0x18001a421  lea     rcx, [rbp+57h+Sid]
0x18001a425  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001a42a  jmp     loc_18001A34C
0x18001a42f  lea     rcx, [rbp+57h+ReferencedDomainName]
0x18001a433  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a438  lea     rdx, [rbp+57h+Sid]
0x18001a43c  mov     rcx, r14
0x18001a43f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x18001a444  nop
0x18001a445  lea     rcx, [rbp+57h+Sid]
0x18001a449  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001a44e  jmp     loc_18001A2A0
0x18001a453  mov     eax, cs:dword_180075000
0x18001a459  cmp     eax, 2
0x18001a45c  jbe     short loc_18001A49F
0x18001a45e  mov     [rbp+57h+var_B0], 8000FFFFh
0x18001a465  lea     rax, [rbp+57h+var_B0]
0x18001a469  mov     [rbp+57h+var_38], rax
0x18001a46d  mov     [rbp+57h+var_30], 4
0x18001a475  lea     rax, [rbp+57h+var_58]
0x18001a479  mov     [rsp+0E0h+peUse], rax
0x18001a47e  mov     dword ptr [rsp+0E0h+cchReferencedDomainName], 3
0x18001a486  xor     r9d, r9d
0x18001a489  xor     r8d, r8d
0x18001a48c  lea     rdx, byte_180068B0D
0x18001a493  lea     rcx, dword_180075000
0x18001a49a  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a49f  mov     eax, 8000FFFFh
0x18001a4a4  mov     rcx, [rbp+57h+var_28]
0x18001a4a8  xor     rcx, rsp; StackCookie
0x18001a4ab  call    __security_check_cookie
0x18001a4b0  mov     rbx, [rsp+0E0h+arg_18]
0x18001a4b8  add     rsp, 0C0h
0x18001a4bf  pop     r15
0x18001a4c1  pop     r14
0x18001a4c3  pop     rdi
0x18001a4c4  pop     rsi
0x18001a4c5  pop     rbp
0x18001a4c6  retn
```
