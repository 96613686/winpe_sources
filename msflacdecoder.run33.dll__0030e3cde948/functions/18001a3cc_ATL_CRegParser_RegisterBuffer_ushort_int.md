# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18001a3cc`
- end: `0x18001a539`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a668`

## callees

- `0x180001e80`
- `0x180016aa0`
- `0x180019970`
- `0x180019b28`
- `0x18001a3cc`
- `0x18001a8b0`
- `0x18001b5c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a50f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a50f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a468`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a468`

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
0x18001a3cc  push    rbx
0x18001a3ce  push    rbp
0x18001a3cf  push    rsi
0x18001a3d0  push    rdi
0x18001a3d1  push    r13
0x18001a3d3  push    r14
0x18001a3d5  push    r15
0x18001a3d7  mov     eax, 2050h
0x18001a3dc  call    _alloca_probe
0x18001a3e1  sub     rsp, rax
0x18001a3e4  mov     rax, cs:__security_cookie
0x18001a3eb  xor     rax, rsp
0x18001a3ee  mov     [rsp+2088h+var_48], rax
0x18001a3f6  mov     r15d, r8d
0x18001a3f9  mov     [rsp+2088h+pv], 0
0x18001a402  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18001a407  mov     rdi, rcx
0x18001a40a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18001a40f  mov     ebx, eax
0x18001a411  test    eax, eax
0x18001a413  js      loc_18001A517
0x18001a419  mov     rbp, [rsp+2088h+pv]
0x18001a41e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18001a425  mov     [rdi], rbp
0x18001a428  mov     rcx, [rdi]
0x18001a42b  xor     eax, eax
0x18001a42d  cmp     ax, [rcx]
0x18001a430  jz      loc_18001A50C
0x18001a436  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001a43b  mov     rcx, rdi; this
0x18001a43e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a443  mov     ebx, eax
0x18001a445  test    eax, eax
0x18001a447  js      loc_18001A50C
0x18001a44d  xor     ebx, ebx
0x18001a44f  cmp     ebx, 0Eh
0x18001a452  jnb     loc_18001A507
0x18001a458  movsxd  rsi, ebx
0x18001a45b  lea     rcx, [rsp+2088h+String1]; lpString1
0x18001a460  add     rsi, rsi
0x18001a463  mov     rdx, [r13+rsi*8+0]; lpString2
0x18001a468  call    cs:__imp_lstrcmpiW
0x18001a46e  test    eax, eax
0x18001a470  jz      short loc_18001A476
0x18001a472  inc     ebx
0x18001a474  jmp     short loc_18001A44F
0x18001a476  mov     rsi, [r13+rsi*8+8]
0x18001a47b  test    rsi, rsi
0x18001a47e  jz      loc_18001A507
0x18001a484  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001a489  mov     rcx, rdi; this
0x18001a48c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a491  mov     ebx, eax
0x18001a493  test    eax, eax
0x18001a495  js      short loc_18001A50C
0x18001a497  mov     eax, 7Bh ; '{'
0x18001a49c  cmp     ax, [rsp+2088h+String1]
0x18001a4a1  jnz     short loc_18001A507
0x18001a4a3  mov     [rsp+2088h+var_2068], 0; int
0x18001a4ab  mov     r8, rsi; HKEY
0x18001a4ae  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001a4b3  mov     rcx, rdi; this
0x18001a4b6  test    r15d, r15d
0x18001a4b9  jz      short loc_18001A4EC
0x18001a4bb  mov     r14, [rdi]
0x18001a4be  mov     r9d, r15d; int
0x18001a4c1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001a4c6  mov     ebx, eax
0x18001a4c8  test    eax, eax
0x18001a4ca  jns     short loc_18001A4FA
0x18001a4cc  xor     r9d, r9d; int
0x18001a4cf  mov     [rdi], r14
0x18001a4d2  mov     r8, rsi; HKEY
0x18001a4d5  mov     [rsp+2088h+var_2068], 0; int
0x18001a4dd  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001a4e2  mov     rcx, rdi; this
0x18001a4e5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001a4ea  jmp     short loc_18001A50C
0x18001a4ec  xor     r9d, r9d; int
0x18001a4ef  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001a4f4  mov     ebx, eax
0x18001a4f6  test    eax, eax
0x18001a4f8  js      short loc_18001A50C
0x18001a4fa  mov     rcx, rdi; this
0x18001a4fd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001a502  jmp     loc_18001A428
0x18001a507  mov     ebx, 80020009h
0x18001a50c  mov     rcx, rbp; pv
0x18001a50f  call    cs:__imp_CoTaskMemFree
0x18001a515  mov     eax, ebx
0x18001a517  mov     rcx, [rsp+2088h+var_48]
0x18001a51f  xor     rcx, rsp; StackCookie
0x18001a522  call    __security_check_cookie
0x18001a527  add     rsp, 2050h
0x18001a52e  pop     r15
0x18001a530  pop     r14
0x18001a532  pop     r13
0x18001a534  pop     rdi
0x18001a535  pop     rsi
0x18001a536  pop     rbp
0x18001a537  pop     rbx
0x18001a538  retn
```
