# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x140003f98`
- end: `0x140004122`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140004128`

## callees

- `0x140003910`
- `0x140003abc`
- `0x140003f98`
- `0x1400042ec`
- `0x1400065f0`
- `0x140006680`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x14000401d`
- `KERNEL32!lstrcmpiW` at `0x14000401d`
- `USER32!CharNextW` at `0x140004107`
- `USER32!CharNextW` at `0x140004107`
- `ole32!CoTaskMemFree` at `0x140004036`
- `ole32!CoTaskMemFree` at `0x140004036`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(const wchar_t **this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
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
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        while ( lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8]) )
        {
          if ( (unsigned int)++v8 >= 0xE )
            goto LABEL_7;
        }
        v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v8 + 1);
        if ( !v9 )
          goto LABEL_7;
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        if ( String1[0] != 123 )
        {
LABEL_7:
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
        while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
          *this = CharNextW(*this);
      }
      while ( **this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x140003f98  push    rbx
0x140003f9a  push    rbp
0x140003f9b  push    rsi
0x140003f9c  push    rdi
0x140003f9d  push    r13
0x140003f9f  push    r14
0x140003fa1  push    r15
0x140003fa3  mov     eax, 2050h
0x140003fa8  call    _alloca_probe
0x140003fad  sub     rsp, rax
0x140003fb0  mov     rax, cs:__security_cookie
0x140003fb7  xor     rax, rsp
0x140003fba  mov     [rsp+2088h+var_48], rax
0x140003fc2  mov     r15d, r8d
0x140003fc5  mov     [rsp+2088h+pv], 0
0x140003fce  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x140003fd3  mov     rdi, rcx
0x140003fd6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x140003fdb  mov     ebx, eax
0x140003fdd  test    eax, eax
0x140003fdf  js      short loc_14000403E
0x140003fe1  mov     rbp, [rsp+2088h+pv]
0x140003fe6  xor     eax, eax
0x140003fe8  mov     [rdi], rbp
0x140003feb  cmp     ax, [rbp+0]
0x140003fef  jz      short loc_140004033
0x140003ff1  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x140003ff8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140003ffd  mov     rcx, rdi; this
0x140004000  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004005  mov     ebx, eax
0x140004007  test    eax, eax
0x140004009  js      short loc_140004033
0x14000400b  xor     ebx, ebx
0x14000400d  movsxd  rsi, ebx
0x140004010  lea     rcx, [rsp+2088h+String1]; lpString1
0x140004015  add     rsi, rsi
0x140004018  mov     rdx, [r13+rsi*8+0]; lpString2
0x14000401d  call    cs:__imp_lstrcmpiW
0x140004023  test    eax, eax
0x140004025  jz      short loc_140004060
0x140004027  inc     ebx
0x140004029  cmp     ebx, 0Eh
0x14000402c  jb      short loc_14000400D
0x14000402e  mov     ebx, 80020009h
0x140004033  mov     rcx, rbp; pv
0x140004036  call    cs:__imp_CoTaskMemFree
0x14000403c  mov     eax, ebx
0x14000403e  mov     rcx, [rsp+2088h+var_48]
0x140004046  xor     rcx, rsp; StackCookie
0x140004049  call    __security_check_cookie
0x14000404e  add     rsp, 2050h
0x140004055  pop     r15
0x140004057  pop     r14
0x140004059  pop     r13
0x14000405b  pop     rdi
0x14000405c  pop     rsi
0x14000405d  pop     rbp
0x14000405e  pop     rbx
0x14000405f  retn
0x140004060  mov     rsi, [r13+rsi*8+8]
0x140004065  test    rsi, rsi
0x140004068  jz      short loc_14000402E
0x14000406a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14000406f  mov     rcx, rdi; this
0x140004072  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004077  mov     ebx, eax
0x140004079  test    eax, eax
0x14000407b  js      short loc_140004033
0x14000407d  mov     eax, 7Bh ; '{'
0x140004082  cmp     ax, [rsp+2088h+String1]
0x140004087  jnz     short loc_14000402E
0x140004089  mov     [rsp+2088h+var_2068], 0; int
0x140004091  mov     r8, rsi; HKEY
0x140004094  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140004099  mov     rcx, rdi; this
0x14000409c  test    r15d, r15d
0x14000409f  jz      short loc_1400040D5
0x1400040a1  mov     r14, [rdi]
0x1400040a4  mov     r9d, r15d; int
0x1400040a7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1400040ac  mov     ebx, eax
0x1400040ae  test    eax, eax
0x1400040b0  jns     short loc_1400040E7
0x1400040b2  xor     r9d, r9d; int
0x1400040b5  mov     [rdi], r14
0x1400040b8  mov     r8, rsi; HKEY
0x1400040bb  mov     [rsp+2088h+var_2068], 0; int
0x1400040c3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1400040c8  mov     rcx, rdi; this
0x1400040cb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1400040d0  jmp     loc_140004033
0x1400040d5  xor     r9d, r9d; int
0x1400040d8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1400040dd  mov     ebx, eax
0x1400040df  test    eax, eax
0x1400040e1  js      loc_140004033
0x1400040e7  mov     r8, [rdi]
0x1400040ea  movzx   edx, word ptr [r8]
0x1400040ee  mov     ecx, edx
0x1400040f0  sub     ecx, 9
0x1400040f3  jz      short loc_140004104
0x1400040f5  sub     ecx, 1
0x1400040f8  jz      short loc_140004104
0x1400040fa  sub     ecx, 3
0x1400040fd  jz      short loc_140004104
0x1400040ff  cmp     ecx, 13h
0x140004102  jnz     short loc_140004112
0x140004104  mov     rcx, r8; lpsz
0x140004107  call    cs:__imp_CharNextW
0x14000410d  mov     [rdi], rax
0x140004110  jmp     short loc_1400040E7
0x140004112  xor     eax, eax
0x140004114  cmp     ax, dx
0x140004117  jnz     loc_140003FF8
0x14000411d  jmp     loc_140004033
```
