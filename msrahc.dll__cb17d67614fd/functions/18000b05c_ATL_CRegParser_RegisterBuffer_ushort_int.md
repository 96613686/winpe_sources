# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000b05c`
- end: `0x18000b1c9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(const wchar_t **this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b1f4`

## callees

- `0x18000aaa0`
- `0x18000ac58`
- `0x18000b05c`
- `0x18000b44c`
- `0x18000bc50`
- `0x18001a5e0`
- `0x18001a6a0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000b0f8`
- `KERNEL32!lstrcmpiW` at `0x18000b0f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b19f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b19f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000b05c  push    rbx
0x18000b05e  push    rbp
0x18000b05f  push    rsi
0x18000b060  push    rdi
0x18000b061  push    r13
0x18000b063  push    r14
0x18000b065  push    r15
0x18000b067  mov     eax, 2050h
0x18000b06c  call    _alloca_probe
0x18000b071  sub     rsp, rax
0x18000b074  mov     rax, cs:__security_cookie
0x18000b07b  xor     rax, rsp
0x18000b07e  mov     [rsp+2088h+var_48], rax
0x18000b086  mov     r15d, r8d
0x18000b089  mov     [rsp+2088h+pv], 0
0x18000b092  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000b097  mov     rdi, rcx
0x18000b09a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000b09f  mov     ebx, eax
0x18000b0a1  test    eax, eax
0x18000b0a3  js      loc_18000B1A7
0x18000b0a9  mov     rbp, [rsp+2088h+pv]
0x18000b0ae  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000b0b5  mov     [rdi], rbp
0x18000b0b8  mov     rcx, [rdi]
0x18000b0bb  xor     eax, eax
0x18000b0bd  cmp     ax, [rcx]
0x18000b0c0  jz      loc_18000B19C
0x18000b0c6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000b0cb  mov     rcx, rdi; this
0x18000b0ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b0d3  mov     ebx, eax
0x18000b0d5  test    eax, eax
0x18000b0d7  js      loc_18000B19C
0x18000b0dd  xor     ebx, ebx
0x18000b0df  cmp     ebx, 0Eh
0x18000b0e2  jnb     loc_18000B197
0x18000b0e8  movsxd  rsi, ebx
0x18000b0eb  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000b0f0  add     rsi, rsi
0x18000b0f3  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000b0f8  call    cs:__imp_lstrcmpiW
0x18000b0fe  test    eax, eax
0x18000b100  jz      short loc_18000B106
0x18000b102  inc     ebx
0x18000b104  jmp     short loc_18000B0DF
0x18000b106  mov     rsi, [r13+rsi*8+8]
0x18000b10b  test    rsi, rsi
0x18000b10e  jz      loc_18000B197
0x18000b114  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000b119  mov     rcx, rdi; this
0x18000b11c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b121  mov     ebx, eax
0x18000b123  test    eax, eax
0x18000b125  js      short loc_18000B19C
0x18000b127  mov     eax, 7Bh ; '{'
0x18000b12c  cmp     ax, [rsp+2088h+String1]
0x18000b131  jnz     short loc_18000B197
0x18000b133  mov     [rsp+2088h+var_2068], 0; int
0x18000b13b  mov     r8, rsi; HKEY
0x18000b13e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000b143  mov     rcx, rdi; this
0x18000b146  test    r15d, r15d
0x18000b149  jz      short loc_18000B17C
0x18000b14b  mov     r14, [rdi]
0x18000b14e  mov     r9d, r15d; int
0x18000b151  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b156  mov     ebx, eax
0x18000b158  test    eax, eax
0x18000b15a  jns     short loc_18000B18A
0x18000b15c  xor     r9d, r9d; int
0x18000b15f  mov     [rdi], r14
0x18000b162  mov     r8, rsi; HKEY
0x18000b165  mov     [rsp+2088h+var_2068], 0; int
0x18000b16d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000b172  mov     rcx, rdi; this
0x18000b175  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b17a  jmp     short loc_18000B19C
0x18000b17c  xor     r9d, r9d; int
0x18000b17f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b184  mov     ebx, eax
0x18000b186  test    eax, eax
0x18000b188  js      short loc_18000B19C
0x18000b18a  mov     rcx, rdi; this
0x18000b18d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000b192  jmp     loc_18000B0B8
0x18000b197  mov     ebx, 80020009h
0x18000b19c  mov     rcx, rbp; pv
0x18000b19f  call    cs:__imp_CoTaskMemFree
0x18000b1a5  mov     eax, ebx
0x18000b1a7  mov     rcx, [rsp+2088h+var_48]
0x18000b1af  xor     rcx, rsp; StackCookie
0x18000b1b2  call    __security_check_cookie
0x18000b1b7  add     rsp, 2050h
0x18000b1be  pop     r15
0x18000b1c0  pop     r14
0x18000b1c2  pop     r13
0x18000b1c4  pop     rdi
0x18000b1c5  pop     rsi
0x18000b1c6  pop     rbp
0x18000b1c7  pop     rbx
0x18000b1c8  retn
```
