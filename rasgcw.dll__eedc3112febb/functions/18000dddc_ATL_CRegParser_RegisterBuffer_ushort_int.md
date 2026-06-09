# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000dddc`
- end: `0x18000df49`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000df50`

## callees

- `0x18000c5c0`
- `0x18000ca4c`
- `0x18000dddc`
- `0x18000e1a8`
- `0x18000f0e0`
- `0x18002f3b0`
- `0x18002f470`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000de78`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000de78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df1f`

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
0x18000dddc  push    rbx
0x18000ddde  push    rbp
0x18000dddf  push    rsi
0x18000dde0  push    rdi
0x18000dde1  push    r13
0x18000dde3  push    r14
0x18000dde5  push    r15
0x18000dde7  mov     eax, 2050h
0x18000ddec  call    _alloca_probe
0x18000ddf1  sub     rsp, rax
0x18000ddf4  mov     rax, cs:__security_cookie
0x18000ddfb  xor     rax, rsp
0x18000ddfe  mov     [rsp+2088h+var_48], rax
0x18000de06  mov     r15d, r8d
0x18000de09  mov     [rsp+2088h+pv], 0
0x18000de12  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000de17  mov     rdi, rcx
0x18000de1a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000de1f  mov     ebx, eax
0x18000de21  test    eax, eax
0x18000de23  js      loc_18000DF27
0x18000de29  mov     rbp, [rsp+2088h+pv]
0x18000de2e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000de35  mov     [rdi], rbp
0x18000de38  mov     rcx, [rdi]
0x18000de3b  xor     eax, eax
0x18000de3d  cmp     ax, [rcx]
0x18000de40  jz      loc_18000DF1C
0x18000de46  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000de4b  mov     rcx, rdi; this
0x18000de4e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000de53  mov     ebx, eax
0x18000de55  test    eax, eax
0x18000de57  js      loc_18000DF1C
0x18000de5d  xor     ebx, ebx
0x18000de5f  cmp     ebx, 0Eh
0x18000de62  jnb     loc_18000DF17
0x18000de68  movsxd  rsi, ebx
0x18000de6b  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000de70  add     rsi, rsi
0x18000de73  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000de78  call    cs:__imp_lstrcmpiW
0x18000de7e  test    eax, eax
0x18000de80  jz      short loc_18000DE86
0x18000de82  inc     ebx
0x18000de84  jmp     short loc_18000DE5F
0x18000de86  mov     rsi, [r13+rsi*8+8]
0x18000de8b  test    rsi, rsi
0x18000de8e  jz      loc_18000DF17
0x18000de94  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000de99  mov     rcx, rdi; this
0x18000de9c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000dea1  mov     ebx, eax
0x18000dea3  test    eax, eax
0x18000dea5  js      short loc_18000DF1C
0x18000dea7  mov     eax, 7Bh ; '{'
0x18000deac  cmp     ax, [rsp+2088h+String1]
0x18000deb1  jnz     short loc_18000DF17
0x18000deb3  mov     [rsp+2088h+var_2068], 0; int
0x18000debb  mov     r8, rsi; HKEY
0x18000debe  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000dec3  mov     rcx, rdi; this
0x18000dec6  test    r15d, r15d
0x18000dec9  jz      short loc_18000DEFC
0x18000decb  mov     r14, [rdi]
0x18000dece  mov     r9d, r15d; int
0x18000ded1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000ded6  mov     ebx, eax
0x18000ded8  test    eax, eax
0x18000deda  jns     short loc_18000DF0A
0x18000dedc  xor     r9d, r9d; int
0x18000dedf  mov     [rdi], r14
0x18000dee2  mov     r8, rsi; HKEY
0x18000dee5  mov     [rsp+2088h+var_2068], 0; int
0x18000deed  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000def2  mov     rcx, rdi; this
0x18000def5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000defa  jmp     short loc_18000DF1C
0x18000defc  xor     r9d, r9d; int
0x18000deff  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000df04  mov     ebx, eax
0x18000df06  test    eax, eax
0x18000df08  js      short loc_18000DF1C
0x18000df0a  mov     rcx, rdi; this
0x18000df0d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000df12  jmp     loc_18000DE38
0x18000df17  mov     ebx, 80020009h
0x18000df1c  mov     rcx, rbp; pv
0x18000df1f  call    cs:__imp_CoTaskMemFree
0x18000df25  mov     eax, ebx
0x18000df27  mov     rcx, [rsp+2088h+var_48]
0x18000df2f  xor     rcx, rsp; StackCookie
0x18000df32  call    __security_check_cookie
0x18000df37  add     rsp, 2050h
0x18000df3e  pop     r15
0x18000df40  pop     r14
0x18000df42  pop     r13
0x18000df44  pop     rdi
0x18000df45  pop     rsi
0x18000df46  pop     rbp
0x18000df47  pop     rbx
0x18000df48  retn
```
