# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800082ac`
- end: `0x180008419`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800086f0`

## callees

- `0x180007c40`
- `0x180007df8`
- `0x1800082ac`
- `0x18000893c`
- `0x1800093e4`
- `0x180039740`
- `0x180039800`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008348`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800083ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800083ef`

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
0x1800082ac  push    rbx
0x1800082ae  push    rbp
0x1800082af  push    rsi
0x1800082b0  push    rdi
0x1800082b1  push    r13
0x1800082b3  push    r14
0x1800082b5  push    r15
0x1800082b7  mov     eax, 2050h
0x1800082bc  call    _alloca_probe
0x1800082c1  sub     rsp, rax
0x1800082c4  mov     rax, cs:__security_cookie
0x1800082cb  xor     rax, rsp
0x1800082ce  mov     [rsp+2088h+var_48], rax
0x1800082d6  mov     r15d, r8d
0x1800082d9  mov     [rsp+2088h+pv], 0
0x1800082e2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800082e7  mov     rdi, rcx
0x1800082ea  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800082ef  mov     ebx, eax
0x1800082f1  test    eax, eax
0x1800082f3  js      loc_1800083F7
0x1800082f9  mov     rbp, [rsp+2088h+pv]
0x1800082fe  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180008305  mov     [rdi], rbp
0x180008308  mov     rcx, [rdi]
0x18000830b  xor     eax, eax
0x18000830d  cmp     ax, [rcx]
0x180008310  jz      loc_1800083EC
0x180008316  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000831b  mov     rcx, rdi; this
0x18000831e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008323  mov     ebx, eax
0x180008325  test    eax, eax
0x180008327  js      loc_1800083EC
0x18000832d  xor     ebx, ebx
0x18000832f  cmp     ebx, 0Eh
0x180008332  jnb     loc_1800083E7
0x180008338  movsxd  rsi, ebx
0x18000833b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180008340  add     rsi, rsi
0x180008343  mov     rdx, [r13+rsi*8+0]; lpString2
0x180008348  call    cs:__imp_lstrcmpiW
0x18000834e  test    eax, eax
0x180008350  jz      short loc_180008356
0x180008352  inc     ebx
0x180008354  jmp     short loc_18000832F
0x180008356  mov     rsi, [r13+rsi*8+8]
0x18000835b  test    rsi, rsi
0x18000835e  jz      loc_1800083E7
0x180008364  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008369  mov     rcx, rdi; this
0x18000836c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008371  mov     ebx, eax
0x180008373  test    eax, eax
0x180008375  js      short loc_1800083EC
0x180008377  mov     eax, 7Bh ; '{'
0x18000837c  cmp     ax, [rsp+2088h+String1]
0x180008381  jnz     short loc_1800083E7
0x180008383  mov     [rsp+2088h+var_2068], 0; int
0x18000838b  mov     r8, rsi; HKEY
0x18000838e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008393  mov     rcx, rdi; this
0x180008396  test    r15d, r15d
0x180008399  jz      short loc_1800083CC
0x18000839b  mov     r14, [rdi]
0x18000839e  mov     r9d, r15d; int
0x1800083a1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800083a6  mov     ebx, eax
0x1800083a8  test    eax, eax
0x1800083aa  jns     short loc_1800083DA
0x1800083ac  xor     r9d, r9d; int
0x1800083af  mov     [rdi], r14
0x1800083b2  mov     r8, rsi; HKEY
0x1800083b5  mov     [rsp+2088h+var_2068], 0; int
0x1800083bd  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800083c2  mov     rcx, rdi; this
0x1800083c5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800083ca  jmp     short loc_1800083EC
0x1800083cc  xor     r9d, r9d; int
0x1800083cf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800083d4  mov     ebx, eax
0x1800083d6  test    eax, eax
0x1800083d8  js      short loc_1800083EC
0x1800083da  mov     rcx, rdi; this
0x1800083dd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800083e2  jmp     loc_180008308
0x1800083e7  mov     ebx, 80020009h
0x1800083ec  mov     rcx, rbp; pv
0x1800083ef  call    cs:__imp_CoTaskMemFree
0x1800083f5  mov     eax, ebx
0x1800083f7  mov     rcx, [rsp+2088h+var_48]
0x1800083ff  xor     rcx, rsp; StackCookie
0x180008402  call    __security_check_cookie
0x180008407  add     rsp, 2050h
0x18000840e  pop     r15
0x180008410  pop     r14
0x180008412  pop     r13
0x180008414  pop     rdi
0x180008415  pop     rsi
0x180008416  pop     rbp
0x180008417  pop     rbx
0x180008418  retn
```
