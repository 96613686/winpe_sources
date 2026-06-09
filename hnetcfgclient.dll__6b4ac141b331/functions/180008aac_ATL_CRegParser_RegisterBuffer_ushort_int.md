# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180008aac`
- end: `0x180008c19`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008c20`

## callees

- `0x180008410`
- `0x1800085c8`
- `0x180008aac`
- `0x180008e68`
- `0x180009760`
- `0x18002d200`
- `0x18002d2c0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008b48`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008b48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bef`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(const wchar_t **this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  const wchar_t *v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (const wchar_t *)pv;
    while ( **this )
    {
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
      if ( Token < 0 )
        break;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xE )
          goto LABEL_17;
        if ( !lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * (int)i]) )
          break;
      }
      v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * (int)i + 1);
      if ( !v9 )
        goto LABEL_17;
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
      if ( Token < 0 )
        break;
      if ( String1[0] != 123 )
      {
LABEL_17:
        Token = -2147352567;
        break;
      }
      if ( a3 )
      {
        v10 = *this;
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, a3, 0);
        if ( Token < 0 )
        {
          *this = v10;
          ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
        if ( Token < 0 )
          break;
      }
      ATL::CRegParser::SkipWhiteSpace((ATL::CRegParser *)this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180008aac  push    rbx
0x180008aae  push    rbp
0x180008aaf  push    rsi
0x180008ab0  push    rdi
0x180008ab1  push    r13
0x180008ab3  push    r14
0x180008ab5  push    r15
0x180008ab7  mov     eax, 2050h
0x180008abc  call    _alloca_probe
0x180008ac1  sub     rsp, rax
0x180008ac4  mov     rax, cs:__security_cookie
0x180008acb  xor     rax, rsp
0x180008ace  mov     [rsp+2088h+var_48], rax
0x180008ad6  mov     r15d, r8d
0x180008ad9  mov     [rsp+2088h+pv], 0
0x180008ae2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180008ae7  mov     rdi, rcx
0x180008aea  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180008aef  mov     ebx, eax
0x180008af1  test    eax, eax
0x180008af3  js      loc_180008BF7
0x180008af9  mov     rbp, [rsp+2088h+pv]
0x180008afe  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180008b05  mov     [rdi], rbp
0x180008b08  mov     rcx, [rdi]
0x180008b0b  xor     eax, eax
0x180008b0d  cmp     ax, [rcx]
0x180008b10  jz      loc_180008BEC
0x180008b16  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008b1b  mov     rcx, rdi; this
0x180008b1e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008b23  mov     ebx, eax
0x180008b25  test    eax, eax
0x180008b27  js      loc_180008BEC
0x180008b2d  xor     ebx, ebx
0x180008b2f  cmp     ebx, 0Eh
0x180008b32  jnb     loc_180008BE7
0x180008b38  movsxd  rsi, ebx
0x180008b3b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180008b40  add     rsi, rsi
0x180008b43  mov     rdx, [r13+rsi*8+0]; lpString2
0x180008b48  call    cs:__imp_lstrcmpiW
0x180008b4e  test    eax, eax
0x180008b50  jz      short loc_180008B56
0x180008b52  inc     ebx
0x180008b54  jmp     short loc_180008B2F
0x180008b56  mov     rsi, [r13+rsi*8+8]
0x180008b5b  test    rsi, rsi
0x180008b5e  jz      loc_180008BE7
0x180008b64  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008b69  mov     rcx, rdi; this
0x180008b6c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008b71  mov     ebx, eax
0x180008b73  test    eax, eax
0x180008b75  js      short loc_180008BEC
0x180008b77  mov     eax, 7Bh ; '{'
0x180008b7c  cmp     ax, [rsp+2088h+String1]
0x180008b81  jnz     short loc_180008BE7
0x180008b83  mov     [rsp+2088h+var_2068], 0; int
0x180008b8b  mov     r8, rsi; HKEY
0x180008b8e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008b93  mov     rcx, rdi; this
0x180008b96  test    r15d, r15d
0x180008b99  jz      short loc_180008BCC
0x180008b9b  mov     r14, [rdi]
0x180008b9e  mov     r9d, r15d; int
0x180008ba1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008ba6  mov     ebx, eax
0x180008ba8  test    eax, eax
0x180008baa  jns     short loc_180008BDA
0x180008bac  xor     r9d, r9d; int
0x180008baf  mov     [rdi], r14
0x180008bb2  mov     r8, rsi; HKEY
0x180008bb5  mov     [rsp+2088h+var_2068], 0; int
0x180008bbd  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008bc2  mov     rcx, rdi; this
0x180008bc5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008bca  jmp     short loc_180008BEC
0x180008bcc  xor     r9d, r9d; int
0x180008bcf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008bd4  mov     ebx, eax
0x180008bd6  test    eax, eax
0x180008bd8  js      short loc_180008BEC
0x180008bda  mov     rcx, rdi; this
0x180008bdd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180008be2  jmp     loc_180008B08
0x180008be7  mov     ebx, 80020009h
0x180008bec  mov     rcx, rbp; pv
0x180008bef  call    cs:__imp_CoTaskMemFree
0x180008bf5  mov     eax, ebx
0x180008bf7  mov     rcx, [rsp+2088h+var_48]
0x180008bff  xor     rcx, rsp; StackCookie
0x180008c02  call    __security_check_cookie
0x180008c07  add     rsp, 2050h
0x180008c0e  pop     r15
0x180008c10  pop     r14
0x180008c12  pop     r13
0x180008c14  pop     rdi
0x180008c15  pop     rsi
0x180008c16  pop     rbp
0x180008c17  pop     rbx
0x180008c18  retn
```
