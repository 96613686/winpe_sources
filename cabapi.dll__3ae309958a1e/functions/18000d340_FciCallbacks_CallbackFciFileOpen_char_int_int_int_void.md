# FciCallbacks::CallbackFciFileOpen(char *,int,int,int *,void *)

- ea: `0x18000d340`
- end: `0x18000d453`
- name: `?CallbackFciFileOpen@FciCallbacks@@SA_JPEADHHPEAHPEAX@Z`
- size: `275`
- prototype: `INT_PTR __fastcall(LPSTR pszFile, unsigned int oflag, int pmode, DWORD *err)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001540`
- `0x180002e54`
- `0x180003648`
- `0x1800082b8`
- `0x18000b34c`
- `0x18000b5ac`
- `0x18000be70`
- `0x18000c7a4`
- `0x18000d340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d418`

## pseudocode

```c
INT_PTR __fastcall FciCallbacks::CallbackFciFileOpen(LPSTR pszFile, unsigned int oflag, int pmode, DWORD *err)
{
  size_t v6; // r8
  int v7; // eax
  _QWORD *v8; // rdx
  __int64 v9; // rbx
  _QWORD v11[2]; // [rsp+20h] [rbp-60h] BYREF
  _OWORD v12[2]; // [rsp+30h] [rbp-50h] BYREF
  CHAR MultiByteStr[16]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v14; // [rsp+60h] [rbp-20h]

  v11[1] = -2;
  *(_OWORD *)MultiByteStr = 0;
  v14 = 0;
  v6 = -1;
  do
    ++v6;
  while ( pszFile[v6] );
  std::string::_Construct<1,char const *>(MultiByteStr, pszFile, v6);
  v12[0] = 0;
  v12[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v12[0]) = 0;
  v11[0] = 0;
  v7 = Utils::ConvertStringToPointer(MultiByteStr, v11);
  if ( v7 < 0 )
  {
    if ( v7 != -2147024883 || (int)Utils::ConvertMultiByteToUnicode(MultiByteStr) < 0 )
    {
      v9 = -1;
      goto LABEL_13;
    }
  }
  else
  {
    v8 = (_QWORD *)(v11[0] + 128LL);
    if ( v12 != (_OWORD *)(v11[0] + 128LL) )
    {
      if ( *(_QWORD *)(v11[0] + 152LL) > 7u )
        v8 = (_QWORD *)*v8;
      std::wstring::_Assign<wchar_t>((void **)v12, v8, *(_QWORD *)(v11[0] + 144LL));
    }
  }
  v9 = Utils::OpenFile(v12, oflag);
  if ( v9 == -1 )
    *err = GetLastError();
LABEL_13:
  std::wstring::~wstring((char **)v12);
  std::string::~string((char **)MultiByteStr);
  return v9;
}

```

## disassembly

```asm
0x18000d340  push    rbp
0x18000d342  push    rbx
0x18000d343  push    rdi
0x18000d344  mov     rbp, rsp
0x18000d347  sub     rsp, 80h
0x18000d34e  mov     [rbp+var_58], 0FFFFFFFFFFFFFFFEh
0x18000d356  mov     rax, cs:__security_cookie
0x18000d35d  xor     rax, rsp
0x18000d360  mov     [rbp+var_10], rax
0x18000d364  mov     rdi, r9
0x18000d367  mov     ebx, edx
0x18000d369  xorps   xmm0, xmm0
0x18000d36c  movups  xmmword ptr [rbp+MultiByteStr], xmm0
0x18000d370  xorps   xmm1, xmm1
0x18000d373  movdqu  [rbp+var_20], xmm1
0x18000d378  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000d37c  inc     r8
0x18000d37f  cmp     byte ptr [rcx+r8], 0
0x18000d384  jnz     short loc_18000D37C
0x18000d386  mov     rdx, rcx
0x18000d389  lea     rcx, [rbp+MultiByteStr]
0x18000d38d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000d392  nop
0x18000d393  xorps   xmm0, xmm0
0x18000d396  movups  [rbp+var_50], xmm0
0x18000d39a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000d3a2  movdqu  [rbp+var_40], xmm1
0x18000d3a7  xor     eax, eax
0x18000d3a9  mov     word ptr [rbp+var_50], ax
0x18000d3ad  mov     [rbp+var_60], rax
0x18000d3b1  lea     rdx, [rbp+var_60]
0x18000d3b5  lea     rcx, [rbp+MultiByteStr]
0x18000d3b9  call    ?ConvertStringToPointer@Utils@@SAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAX@Z; Utils::ConvertStringToPointer(std::string &,void * *)
0x18000d3be  test    eax, eax
0x18000d3c0  js      short loc_18000D3EC
0x18000d3c2  mov     rdx, [rbp+var_60]
0x18000d3c6  sub     rdx, 0FFFFFFFFFFFFFF80h
0x18000d3ca  lea     rax, [rbp+var_50]
0x18000d3ce  cmp     rax, rdx
0x18000d3d1  jz      short loc_18000D404
0x18000d3d3  mov     r8, [rdx+10h]
0x18000d3d7  cmp     qword ptr [rdx+18h], 7
0x18000d3dc  jbe     short loc_18000D3E1
0x18000d3de  mov     rdx, [rdx]
0x18000d3e1  lea     rcx, [rbp+var_50]
0x18000d3e5  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000d3ea  jmp     short loc_18000D404
0x18000d3ec  cmp     eax, 8007000Dh
0x18000d3f1  jnz     short loc_18000D422
0x18000d3f3  lea     rdx, [rbp+var_50]
0x18000d3f7  lea     rcx, [rbp+MultiByteStr]; lpMultiByteStr
0x18000d3fb  call    ?ConvertMultiByteToUnicode@Utils@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Utils::ConvertMultiByteToUnicode(std::string const &,std::wstring *)
0x18000d400  test    eax, eax
0x18000d402  js      short loc_18000D422
0x18000d404  mov     edx, ebx
0x18000d406  lea     rcx, [rbp+var_50]
0x18000d40a  call    ?OpenFile@Utils@@SA_JAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@HH@Z; Utils::OpenFile(std::wstring const &,int,int)
0x18000d40f  mov     rbx, rax
0x18000d412  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d416  jnz     short loc_18000D426
0x18000d418  call    cs:__imp_GetLastError
0x18000d41e  mov     [rdi], eax
0x18000d420  jmp     short loc_18000D426
0x18000d422  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d426  lea     rcx, [rbp+var_50]
0x18000d42a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d42f  nop
0x18000d430  lea     rcx, [rbp+MultiByteStr]
0x18000d434  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000d439  mov     rax, rbx
0x18000d43c  mov     rcx, [rbp+var_10]
0x18000d440  xor     rcx, rsp; StackCookie
0x18000d443  call    __security_check_cookie
0x18000d448  add     rsp, 80h
0x18000d44f  pop     rdi
0x18000d450  pop     rbx
0x18000d451  pop     rbp
0x18000d452  retn
```
