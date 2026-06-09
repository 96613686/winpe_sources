# _anonymous_namespace_::DeleteAllSubkeys

- ea: `0x1800a42ac`
- end: `0x1800a441d`
- name: `_anonymous_namespace_::DeleteAllSubkeys`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800a3df8`

## callees

- `0x180003220`
- `0x18000949c`
- `0x180015af4`
- `0x180019704`
- `0x180019800`
- `0x1800a3970`
- `0x1800a42ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a43a1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a43a1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a437d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a437d`

## string_xrefs

- `0x1800a4409`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::DeleteAllSubkeys(HKEY *a1)
{
  int v2; // ebx
  DWORD v3; // edx
  HKEY i; // rcx
  __int128 j; // rdi
  const WCHAR *v6; // rax
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  int lpReserved; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v12; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+58h] [rbp-A8h]
  WCHAR Name[256]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v12 = 0;
  v13 = 0;
  v2 = 0;
  v3 = 0;
  for ( i = *a1; ; i = *a1 )
  {
    cchName = 256;
    if ( RegEnumKeyExW(i, v3, Name, &cchName, 0, 0, 0, 0) )
      break;
    if ( *((_QWORD *)&v12 + 1) == v13 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<unsigned short (&)[256]>(&v12, *((_QWORD *)&v12 + 1), Name);
    }
    else
    {
      std::wstring::wstring(*((_QWORD *)&v12 + 1));
      *((_QWORD *)&v12 + 1) += 32LL;
    }
    v3 = ++v2;
  }
  for ( j = v12; ; *(_QWORD *)&j = j + 32 )
  {
    if ( (_QWORD)j == *((_QWORD *)&j + 1) )
    {
      v8 = 0;
      goto LABEL_15;
    }
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(j);
    v7 = RegDeleteTreeW(*a1, v6);
    v8 = v7;
    if ( (v7 & 0xFFFFFFFD) != 0 )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      if ( (v8 & 0x80000000) != 0 )
        break;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72,
    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
    (const char *)v8,
    lpReserved);
LABEL_15:
  std::vector<std::wstring>::_Tidy(&v12);
  return v8;
}

```

## disassembly

```asm
0x1800a42ac  mov     [rsp-8+arg_8], rbx
0x1800a42b1  mov     [rsp-8+arg_10], rsi
0x1800a42b6  push    rbp
0x1800a42b7  push    rdi
0x1800a42b8  push    r14
0x1800a42ba  lea     rbp, [rsp-170h]
0x1800a42c2  sub     rsp, 270h
0x1800a42c9  mov     rax, cs:__security_cookie
0x1800a42d0  xor     rax, rsp
0x1800a42d3  mov     [rbp+180h+var_20], rax
0x1800a42da  mov     r14, rcx
0x1800a42dd  xorps   xmm0, xmm0
0x1800a42e0  movdqu  [rsp+280h+var_238], xmm0
0x1800a42e6  mov     [rsp+280h+var_228], 0
0x1800a42ef  xor     ebx, ebx
0x1800a42f1  mov     edi, 100h
0x1800a42f6  mov     [rsp+280h+lpftLastWriteTime], rbx
0x1800a42fb  mov     [rsp+280h+lpcchClass], rbx
0x1800a4300  mov     [rsp+280h+lpClass], rbx
0x1800a4305  mov     [rsp+280h+lpReserved], rbx
0x1800a430a  xor     edx, edx
0x1800a430c  mov     rcx, [rcx]
0x1800a430f  jmp     short loc_1800A436F
0x1800a4311  mov     rax, qword ptr [rsp+280h+var_238+8]
0x1800a4316  cmp     rax, [rsp+280h+var_228]
0x1800a431b  jz      short loc_1800A4332
0x1800a431d  lea     rdx, [rsp+280h+Name]
0x1800a4322  mov     rcx, rax
0x1800a4325  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a432a  add     qword ptr [rsp+280h+var_238+8], 20h ; ' '
0x1800a4330  jmp     short loc_1800A4344
0x1800a4332  lea     r8, [rsp+280h+Name]
0x1800a4337  mov     rdx, rax
0x1800a433a  lea     rcx, [rsp+280h+var_238]
0x1800a433f  call    ??$_Emplace_reallocate@AEAY0BAA@G@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEAY0BAA@G@Z; std::vector<std::wstring>::_Emplace_reallocate<ushort (&)[256]>(std::wstring * const,ushort (&)[256])
0x1800a4344  inc     ebx
0x1800a4346  mov     [rsp+280h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800a434f  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x1800a4358  mov     [rsp+280h+lpClass], 0; lpClass
0x1800a4361  mov     [rsp+280h+lpReserved], 0; lpReserved
0x1800a436a  mov     edx, ebx; dwIndex
0x1800a436c  mov     rcx, [r14]; hKey
0x1800a436f  mov     [rsp+280h+cchName], edi
0x1800a4373  lea     r9, [rsp+280h+cchName]; lpcchName
0x1800a4378  lea     r8, [rsp+280h+Name]; lpName
0x1800a437d  call    cs:__imp_RegEnumKeyExW
0x1800a4383  test    eax, eax
0x1800a4385  jz      short loc_1800A4311
0x1800a4387  mov     rdi, qword ptr [rsp+280h+var_238]
0x1800a438c  mov     rsi, qword ptr [rsp+280h+var_238+8]
0x1800a4391  jmp     short loc_1800A43C5
0x1800a4393  mov     rcx, rdi
0x1800a4396  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a439b  mov     rdx, rax; lpSubKey
0x1800a439e  mov     rcx, [r14]; hKey
0x1800a43a1  call    cs:__imp_RegDeleteTreeW
0x1800a43a7  mov     ebx, eax
0x1800a43a9  test    eax, 0FFFFFFFDh
0x1800a43ae  jz      short loc_1800A43C1
0x1800a43b0  test    eax, eax
0x1800a43b2  jle     short loc_1800A43BD
0x1800a43b4  movzx   ebx, ax
0x1800a43b7  or      ebx, 80070000h
0x1800a43bd  test    ebx, ebx
0x1800a43bf  js      short loc_1800A43FF
0x1800a43c1  add     rdi, 20h ; ' '
0x1800a43c5  cmp     rdi, rsi
0x1800a43c8  jnz     short loc_1800A4393
0x1800a43ca  xor     ebx, ebx
0x1800a43cc  lea     rcx, [rsp+280h+var_238]
0x1800a43d1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800a43d6  mov     eax, ebx
0x1800a43d8  mov     rcx, [rbp+180h+var_20]
0x1800a43df  xor     rcx, rsp; StackCookie
0x1800a43e2  call    __security_check_cookie
0x1800a43e7  lea     r11, [rsp+280h+var_10]
0x1800a43ef  mov     rbx, [r11+28h]
0x1800a43f3  mov     rsi, [r11+30h]
0x1800a43f7  mov     rsp, r11
0x1800a43fa  pop     r14
0x1800a43fc  pop     rdi
0x1800a43fd  pop     rbp
0x1800a43fe  retn
0x1800a43ff  mov     rcx, [rbp+188h]; this
0x1800a4406  mov     r9d, ebx; char *
0x1800a4409  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a4410  mov     edx, 72h ; 'r'; void *
0x1800a4415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a441a  jmp     short loc_1800A43CC
```
