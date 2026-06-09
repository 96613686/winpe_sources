# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180024a2c`
- end: `0x180024b99`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024ba0`

## callees

- `0x18001d8e0`
- `0x1800244d4`
- `0x18002468c`
- `0x180024a2c`
- `0x180024d50`
- `0x18002541c`
- `0x180032090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b6f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024ac8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024ac8`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  __int64 v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *(_QWORD *)this = pv;
    while ( **(_WORD **)this )
    {
      Token = ATL::CRegParser::NextToken(this, String1);
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
      Token = ATL::CRegParser::NextToken(this, String1);
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
        v10 = *(_QWORD *)this;
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, a3, 0);
        if ( Token < 0 )
        {
          *(_QWORD *)this = v10;
          ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
        if ( Token < 0 )
          break;
      }
      ATL::CRegParser::SkipWhiteSpace(this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180024a2c  push    rbx
0x180024a2e  push    rbp
0x180024a2f  push    rsi
0x180024a30  push    rdi
0x180024a31  push    r13
0x180024a33  push    r14
0x180024a35  push    r15
0x180024a37  mov     eax, 2050h
0x180024a3c  call    _alloca_probe
0x180024a41  sub     rsp, rax
0x180024a44  mov     rax, cs:__security_cookie
0x180024a4b  xor     rax, rsp
0x180024a4e  mov     [rsp+2088h+var_48], rax
0x180024a56  mov     r15d, r8d
0x180024a59  mov     [rsp+2088h+pv], 0
0x180024a62  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180024a67  mov     rdi, rcx
0x180024a6a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180024a6f  mov     ebx, eax
0x180024a71  test    eax, eax
0x180024a73  js      loc_180024B77
0x180024a79  mov     rbp, [rsp+2088h+pv]
0x180024a7e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180024a85  mov     [rdi], rbp
0x180024a88  mov     rcx, [rdi]
0x180024a8b  xor     eax, eax
0x180024a8d  cmp     ax, [rcx]
0x180024a90  jz      loc_180024B6C
0x180024a96  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180024a9b  mov     rcx, rdi; this
0x180024a9e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180024aa3  mov     ebx, eax
0x180024aa5  test    eax, eax
0x180024aa7  js      loc_180024B6C
0x180024aad  xor     ebx, ebx
0x180024aaf  cmp     ebx, 0Eh
0x180024ab2  jnb     loc_180024B67
0x180024ab8  movsxd  rsi, ebx
0x180024abb  lea     rcx, [rsp+2088h+String1]; lpString1
0x180024ac0  add     rsi, rsi
0x180024ac3  mov     rdx, [r13+rsi*8+0]; lpString2
0x180024ac8  call    cs:__imp_lstrcmpiW
0x180024ace  test    eax, eax
0x180024ad0  jz      short loc_180024AD6
0x180024ad2  inc     ebx
0x180024ad4  jmp     short loc_180024AAF
0x180024ad6  mov     rsi, [r13+rsi*8+8]
0x180024adb  test    rsi, rsi
0x180024ade  jz      loc_180024B67
0x180024ae4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180024ae9  mov     rcx, rdi; this
0x180024aec  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180024af1  mov     ebx, eax
0x180024af3  test    eax, eax
0x180024af5  js      short loc_180024B6C
0x180024af7  mov     eax, 7Bh ; '{'
0x180024afc  cmp     ax, [rsp+2088h+String1]
0x180024b01  jnz     short loc_180024B67
0x180024b03  mov     [rsp+2088h+var_2068], 0; int
0x180024b0b  mov     r8, rsi; HKEY
0x180024b0e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180024b13  mov     rcx, rdi; this
0x180024b16  test    r15d, r15d
0x180024b19  jz      short loc_180024B4C
0x180024b1b  mov     r14, [rdi]
0x180024b1e  mov     r9d, r15d; int
0x180024b21  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180024b26  mov     ebx, eax
0x180024b28  test    eax, eax
0x180024b2a  jns     short loc_180024B5A
0x180024b2c  xor     r9d, r9d; int
0x180024b2f  mov     [rdi], r14
0x180024b32  mov     r8, rsi; HKEY
0x180024b35  mov     [rsp+2088h+var_2068], 0; int
0x180024b3d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180024b42  mov     rcx, rdi; this
0x180024b45  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180024b4a  jmp     short loc_180024B6C
0x180024b4c  xor     r9d, r9d; int
0x180024b4f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180024b54  mov     ebx, eax
0x180024b56  test    eax, eax
0x180024b58  js      short loc_180024B6C
0x180024b5a  mov     rcx, rdi; this
0x180024b5d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180024b62  jmp     loc_180024A88
0x180024b67  mov     ebx, 80020009h
0x180024b6c  mov     rcx, rbp; pv
0x180024b6f  call    cs:__imp_CoTaskMemFree
0x180024b75  mov     eax, ebx
0x180024b77  mov     rcx, [rsp+2088h+var_48]
0x180024b7f  xor     rcx, rsp; StackCookie
0x180024b82  call    __security_check_cookie
0x180024b87  add     rsp, 2050h
0x180024b8e  pop     r15
0x180024b90  pop     r14
0x180024b92  pop     r13
0x180024b94  pop     rdi
0x180024b95  pop     rsi
0x180024b96  pop     rbp
0x180024b97  pop     rbx
0x180024b98  retn
```
