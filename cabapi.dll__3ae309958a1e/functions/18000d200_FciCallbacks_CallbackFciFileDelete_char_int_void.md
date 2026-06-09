# FciCallbacks::CallbackFciFileDelete(char *,int *,void *)

- ea: `0x18000d200`
- end: `0x18000d336`
- name: `?CallbackFciFileDelete@FciCallbacks@@SAHPEADPEAHPEAX@Z`
- size: `310`
- prototype: `__int64 __fastcall(LPSTR pszFile, DWORD *err, void *pv)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180001540`
- `0x180002e54`
- `0x180003648`
- `0x1800082b8`
- `0x18000b34c`
- `0x18000b5ac`
- `0x18000c7a4`
- `0x18000d200`
- `0x180010c74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2f4`

## pseudocode

```c
__int64 __fastcall FciCallbacks::CallbackFciFileDelete(LPSTR pszFile, DWORD *err, void *pv)
{
  unsigned int v4; // ebx
  __int64 v5; // r8
  int v6; // eax
  LPCWSTR v7; // rdx
  const WCHAR *v8; // rax
  LPCWSTR v10[3]; // [rsp+20h] [rbp-60h] BYREF
  __int128 v11; // [rsp+38h] [rbp-48h] BYREF
  __m128i si128; // [rsp+48h] [rbp-38h]
  CHAR MultiByteStr[16]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v14; // [rsp+68h] [rbp-18h]

  v10[2] = (LPCWSTR)-2LL;
  *(_OWORD *)MultiByteStr = 0;
  v14 = 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( pszFile[v5] );
  std::string::_Construct<1,char const *>(MultiByteStr, pszFile);
  v11 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v11) = 0;
  v10[0] = 0;
  v6 = Utils::ConvertStringToPointer(MultiByteStr, v10);
  if ( v6 < 0 )
  {
    if ( v6 != -2147024883 || (int)Utils::ConvertMultiByteToUnicode(MultiByteStr) < 0 )
      goto LABEL_15;
  }
  else
  {
    v7 = v10[0] + 64;
    if ( &v11 != (__int128 *)v10[0] + 8 )
    {
      if ( *((_QWORD *)v10[0] + 19) > 7u )
        v7 = *(LPCWSTR *)v7;
      std::wstring::_Assign<wchar_t>(&v11, v7, *((_QWORD *)v10[0] + 18));
    }
  }
  v8 = (const WCHAR *)&v11;
  if ( si128.m128i_i64[1] > 7uLL )
    v8 = (const WCHAR *)v11;
  v10[0] = v8;
  v10[1] = (LPCWSTR)si128.m128i_i64[0];
  if ( SetAttrAndDeleteFile(v10) )
    v4 = 0;
  else
    *err = GetLastError();
LABEL_15:
  std::wstring::~wstring(&v11);
  std::string::~string(MultiByteStr);
  return v4;
}

```

## disassembly

```asm
0x18000d200  mov     rax, rsp
0x18000d203  push    rbp
0x18000d204  mov     rbp, rsp
0x18000d207  sub     rsp, 80h
0x18000d20e  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18000d216  mov     [rax+18h], rbx
0x18000d21a  mov     [rax+20h], rdi
0x18000d21e  mov     rax, cs:__security_cookie
0x18000d225  xor     rax, rsp
0x18000d228  mov     [rbp+var_8], rax
0x18000d22c  mov     rdi, rdx
0x18000d22f  xorps   xmm0, xmm0
0x18000d232  movups  xmmword ptr [rbp+MultiByteStr], xmm0
0x18000d236  xorps   xmm1, xmm1
0x18000d239  movdqu  [rbp+var_18], xmm1
0x18000d23e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d242  mov     r8, rbx
0x18000d245  inc     r8
0x18000d248  cmp     byte ptr [rcx+r8], 0
0x18000d24d  jnz     short loc_18000D245
0x18000d24f  mov     rdx, rcx
0x18000d252  lea     rcx, [rbp+MultiByteStr]
0x18000d256  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000d25b  nop
0x18000d25c  xorps   xmm0, xmm0
0x18000d25f  movups  [rbp+var_48], xmm0
0x18000d263  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000d26b  movdqu  [rbp+var_38], xmm1
0x18000d270  xor     eax, eax
0x18000d272  mov     word ptr [rbp+var_48], ax
0x18000d276  mov     [rbp+var_60], rax
0x18000d27a  lea     rdx, [rbp+var_60]
0x18000d27e  lea     rcx, [rbp+MultiByteStr]
0x18000d282  call    ?ConvertStringToPointer@Utils@@SAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAX@Z; Utils::ConvertStringToPointer(std::string &,void * *)
0x18000d287  test    eax, eax
0x18000d289  js      short loc_18000D2B5
0x18000d28b  mov     rdx, [rbp+var_60]
0x18000d28f  sub     rdx, 0FFFFFFFFFFFFFF80h
0x18000d293  lea     rax, [rbp+var_48]
0x18000d297  cmp     rax, rdx
0x18000d29a  jz      short loc_18000D2CD
0x18000d29c  mov     r8, [rdx+10h]
0x18000d2a0  cmp     qword ptr [rdx+18h], 7
0x18000d2a5  jbe     short loc_18000D2AA
0x18000d2a7  mov     rdx, [rdx]
0x18000d2aa  lea     rcx, [rbp+var_48]
0x18000d2ae  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000d2b3  jmp     short loc_18000D2CD
0x18000d2b5  cmp     eax, 8007000Dh
0x18000d2ba  jnz     short loc_18000D300
0x18000d2bc  lea     rdx, [rbp+var_48]
0x18000d2c0  lea     rcx, [rbp+MultiByteStr]; lpMultiByteStr
0x18000d2c4  call    ?ConvertMultiByteToUnicode@Utils@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Utils::ConvertMultiByteToUnicode(std::string const &,std::wstring *)
0x18000d2c9  test    eax, eax
0x18000d2cb  js      short loc_18000D300
0x18000d2cd  mov     rcx, qword ptr [rbp+var_38]
0x18000d2d1  lea     rax, [rbp+var_48]
0x18000d2d5  cmp     qword ptr [rbp+var_38+8], 7
0x18000d2da  cmova   rax, qword ptr [rbp+var_48]
0x18000d2df  mov     [rbp+var_60], rax
0x18000d2e3  mov     [rbp+var_58], rcx
0x18000d2e7  lea     rcx, [rbp+var_60]
0x18000d2eb  call    ?SetAttrAndDeleteFile@@YAHAEBV?$basic_zstring_view@_W@wil@@@Z; SetAttrAndDeleteFile(wil::basic_zstring_view<wchar_t> const &)
0x18000d2f0  test    eax, eax
0x18000d2f2  jnz     short loc_18000D2FE
0x18000d2f4  call    cs:__imp_GetLastError
0x18000d2fa  mov     [rdi], eax
0x18000d2fc  jmp     short loc_18000D300
0x18000d2fe  xor     ebx, ebx
0x18000d300  lea     rcx, [rbp+var_48]
0x18000d304  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d309  nop
0x18000d30a  lea     rcx, [rbp+MultiByteStr]
0x18000d30e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000d313  mov     eax, ebx
0x18000d315  mov     rcx, [rbp+var_8]
0x18000d319  xor     rcx, rsp; StackCookie
0x18000d31c  call    __security_check_cookie
0x18000d321  lea     r11, [rsp+80h+var_s0]
0x18000d329  mov     rbx, [r11+20h]
0x18000d32d  mov     rdi, [r11+28h]
0x18000d331  mov     rsp, r11
0x18000d334  pop     rbp
0x18000d335  retn
```
