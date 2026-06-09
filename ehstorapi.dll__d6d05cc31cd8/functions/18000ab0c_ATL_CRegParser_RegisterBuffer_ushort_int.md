# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000ab0c`
- end: `0x18000ac79`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ac80`

## callees

- `0x18000a570`
- `0x18000a728`
- `0x18000ab0c`
- `0x18000ae30`
- `0x18000b5b8`
- `0x18000c4f0`
- `0x18000c5b0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000aba8`
- `KERNEL32!lstrcmpiW` at `0x18000aba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac4f`

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
0x18000ab0c  push    rbx
0x18000ab0e  push    rbp
0x18000ab0f  push    rsi
0x18000ab10  push    rdi
0x18000ab11  push    r13
0x18000ab13  push    r14
0x18000ab15  push    r15
0x18000ab17  mov     eax, 2050h
0x18000ab1c  call    _alloca_probe
0x18000ab21  sub     rsp, rax
0x18000ab24  mov     rax, cs:__security_cookie
0x18000ab2b  xor     rax, rsp
0x18000ab2e  mov     [rsp+2088h+var_48], rax
0x18000ab36  mov     r15d, r8d
0x18000ab39  mov     [rsp+2088h+pv], 0
0x18000ab42  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000ab47  mov     rdi, rcx
0x18000ab4a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000ab4f  mov     ebx, eax
0x18000ab51  test    eax, eax
0x18000ab53  js      loc_18000AC57
0x18000ab59  mov     rbp, [rsp+2088h+pv]
0x18000ab5e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000ab65  mov     [rdi], rbp
0x18000ab68  mov     rcx, [rdi]
0x18000ab6b  xor     eax, eax
0x18000ab6d  cmp     ax, [rcx]
0x18000ab70  jz      loc_18000AC4C
0x18000ab76  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000ab7b  mov     rcx, rdi; this
0x18000ab7e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ab83  mov     ebx, eax
0x18000ab85  test    eax, eax
0x18000ab87  js      loc_18000AC4C
0x18000ab8d  xor     ebx, ebx
0x18000ab8f  cmp     ebx, 0Eh
0x18000ab92  jnb     loc_18000AC47
0x18000ab98  movsxd  rsi, ebx
0x18000ab9b  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000aba0  add     rsi, rsi
0x18000aba3  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000aba8  call    cs:__imp_lstrcmpiW
0x18000abae  test    eax, eax
0x18000abb0  jz      short loc_18000ABB6
0x18000abb2  inc     ebx
0x18000abb4  jmp     short loc_18000AB8F
0x18000abb6  mov     rsi, [r13+rsi*8+8]
0x18000abbb  test    rsi, rsi
0x18000abbe  jz      loc_18000AC47
0x18000abc4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000abc9  mov     rcx, rdi; this
0x18000abcc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000abd1  mov     ebx, eax
0x18000abd3  test    eax, eax
0x18000abd5  js      short loc_18000AC4C
0x18000abd7  mov     eax, 7Bh ; '{'
0x18000abdc  cmp     ax, [rsp+2088h+String1]
0x18000abe1  jnz     short loc_18000AC47
0x18000abe3  mov     [rsp+2088h+var_2068], 0; int
0x18000abeb  mov     r8, rsi; HKEY
0x18000abee  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000abf3  mov     rcx, rdi; this
0x18000abf6  test    r15d, r15d
0x18000abf9  jz      short loc_18000AC2C
0x18000abfb  mov     r14, [rdi]
0x18000abfe  mov     r9d, r15d; int
0x18000ac01  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000ac06  mov     ebx, eax
0x18000ac08  test    eax, eax
0x18000ac0a  jns     short loc_18000AC3A
0x18000ac0c  xor     r9d, r9d; int
0x18000ac0f  mov     [rdi], r14
0x18000ac12  mov     r8, rsi; HKEY
0x18000ac15  mov     [rsp+2088h+var_2068], 0; int
0x18000ac1d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000ac22  mov     rcx, rdi; this
0x18000ac25  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000ac2a  jmp     short loc_18000AC4C
0x18000ac2c  xor     r9d, r9d; int
0x18000ac2f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000ac34  mov     ebx, eax
0x18000ac36  test    eax, eax
0x18000ac38  js      short loc_18000AC4C
0x18000ac3a  mov     rcx, rdi; this
0x18000ac3d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000ac42  jmp     loc_18000AB68
0x18000ac47  mov     ebx, 80020009h
0x18000ac4c  mov     rcx, rbp; pv
0x18000ac4f  call    cs:__imp_CoTaskMemFree
0x18000ac55  mov     eax, ebx
0x18000ac57  mov     rcx, [rsp+2088h+var_48]
0x18000ac5f  xor     rcx, rsp; StackCookie
0x18000ac62  call    __security_check_cookie
0x18000ac67  add     rsp, 2050h
0x18000ac6e  pop     r15
0x18000ac70  pop     r14
0x18000ac72  pop     r13
0x18000ac74  pop     rdi
0x18000ac75  pop     rsi
0x18000ac76  pop     rbp
0x18000ac77  pop     rbx
0x18000ac78  retn
```
