# NgcUtils::GetCallingAppName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180042bc4`
- end: `0x180042cef`
- name: `?GetCallingAppName@NgcUtils@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037b40`

## callees

- `0x18000edb0`
- `0x18001bb24`
- `0x180028360`
- `0x180029aec`
- `0x18002b718`
- `0x18002e850`
- `0x180042bc4`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180042c40`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180042c77`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180042c40`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180042c77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042bf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042bf8`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x180042c0c`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x180042c0c`

## string_xrefs

- `0x180042c20`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::GetCallingAppName(__int64 a1)
{
  HANDLE CurrentProcess; // rax
  const char *v3; // r9
  __int64 v5; // rdx
  WCHAR *v6; // rdx
  __int64 v7; // r8
  wchar_t *v8; // rax
  __int64 v9; // r8
  _BYTE v10[32]; // [rsp+20h] [rbp-248h] BYREF
  wchar_t ImageFileName[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  memset_0(ImageFileName, 0, 0x208u);
  CurrentProcess = GetCurrentProcess();
  if ( !K32GetProcessImageFileNameW(CurrentProcess, ImageFileName, 0x104u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x11B,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
             v3);
  wcsrchr(ImageFileName, 0x5Cu);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v10);
  if ( v5 )
  {
    v6 = (WCHAR *)(v5 + 2);
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
  }
  else
  {
    v8 = wcsrchr(ImageFileName, 0x3Au);
    v9 = -1;
    if ( v8 )
    {
      v6 = v8 + 1;
      do
        ++v9;
      while ( v6[v9] );
    }
    else
    {
      do
        ++v9;
      while ( ImageFileName[v9] );
      v6 = ImageFileName;
    }
  }
  std::wstring::_Assign<unsigned short>(v10, v6);
  std::wstring::operator=(a1, v10);
  std::wstring::~wstring(v10);
  return 0;
}

```

## disassembly

```asm
0x180042bc4  mov     [rsp+arg_8], rbx
0x180042bc9  push    rdi
0x180042bca  sub     rsp, 260h
0x180042bd1  mov     rax, cs:__security_cookie
0x180042bd8  xor     rax, rsp
0x180042bdb  mov     [rsp+268h+var_18], rax
0x180042be3  mov     rbx, rcx
0x180042be6  xor     edx, edx; Val
0x180042be8  mov     r8d, 208h; Size
0x180042bee  lea     rcx, [rsp+268h+ImageFileName]; void *
0x180042bf3  call    memset_0
0x180042bf8  call    cs:__imp_GetCurrentProcess
0x180042bfe  mov     rcx, rax; hProcess
0x180042c01  mov     r8d, 104h; nSize
0x180042c07  lea     rdx, [rsp+268h+ImageFileName]; lpImageFileName
0x180042c0c  call    cs:__imp_K32GetProcessImageFileNameW
0x180042c12  xor     edi, edi
0x180042c14  test    eax, eax
0x180042c16  jnz     short loc_180042C36
0x180042c18  mov     rcx, [rsp+268h]; this
0x180042c20  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180042c27  mov     edx, 11Bh; void *
0x180042c2c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042c31  jmp     loc_180042CCE
0x180042c36  mov     edx, 5Ch ; '\'; Ch
0x180042c3b  lea     rcx, [rsp+268h+ImageFileName]; Str
0x180042c40  call    cs:__imp_wcsrchr
0x180042c46  mov     rdx, rax
0x180042c49  lea     rcx, [rsp+268h+var_248]
0x180042c4e  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180042c53  nop
0x180042c54  test    rdx, rdx
0x180042c57  jz      short loc_180042C6D
0x180042c59  add     rdx, 2
0x180042c5d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180042c61  inc     r8
0x180042c64  cmp     [rdx+r8*2], di
0x180042c69  jnz     short loc_180042C61
0x180042c6b  jmp     short loc_180042CAA
0x180042c6d  mov     edx, 3Ah ; ':'; Ch
0x180042c72  lea     rcx, [rsp+268h+ImageFileName]; Str
0x180042c77  call    cs:__imp_wcsrchr
0x180042c7d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180042c81  test    rax, rax
0x180042c84  jnz     short loc_180042C9C
0x180042c86  lea     rax, [rsp+268h+ImageFileName]
0x180042c8b  inc     r8
0x180042c8e  cmp     [rax+r8*2], di
0x180042c93  jnz     short loc_180042C8B
0x180042c95  lea     rdx, [rsp+268h+ImageFileName]
0x180042c9a  jmp     short loc_180042CAA
0x180042c9c  lea     rdx, [rax+2]
0x180042ca0  inc     r8
0x180042ca3  cmp     [rdx+r8*2], di
0x180042ca8  jnz     short loc_180042CA0
0x180042caa  lea     rcx, [rsp+268h+var_248]
0x180042caf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180042cb4  lea     rdx, [rsp+268h+var_248]
0x180042cb9  mov     rcx, rbx
0x180042cbc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180042cc1  nop
0x180042cc2  lea     rcx, [rsp+268h+var_248]
0x180042cc7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042ccc  xor     eax, eax
0x180042cce  mov     rcx, [rsp+268h+var_18]
0x180042cd6  xor     rcx, rsp; StackCookie
0x180042cd9  call    __security_check_cookie
0x180042cde  mov     rbx, [rsp+268h+arg_8]
0x180042ce6  add     rsp, 260h
0x180042ced  pop     rdi
0x180042cee  retn
```
