# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180004688`
- end: `0x180004812`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004818`

## callees

- `0x180004060`
- `0x18000420c`
- `0x180004688`
- `0x1800049dc`
- `0x180006030`
- `0x1800060c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004726`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004726`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800047f7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800047f7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000470d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000470d`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  LPCWSTR v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCWSTR)pv;
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
0x180004688  push    rbx
0x18000468a  push    rbp
0x18000468b  push    rsi
0x18000468c  push    rdi
0x18000468d  push    r13
0x18000468f  push    r14
0x180004691  push    r15
0x180004693  mov     eax, 2050h
0x180004698  call    _alloca_probe
0x18000469d  sub     rsp, rax
0x1800046a0  mov     rax, cs:__security_cookie
0x1800046a7  xor     rax, rsp
0x1800046aa  mov     [rsp+2088h+var_48], rax
0x1800046b2  mov     r15d, r8d
0x1800046b5  mov     [rsp+2088h+pv], 0
0x1800046be  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800046c3  mov     rdi, rcx
0x1800046c6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800046cb  mov     ebx, eax
0x1800046cd  test    eax, eax
0x1800046cf  js      short loc_18000472E
0x1800046d1  mov     rbp, [rsp+2088h+pv]
0x1800046d6  xor     eax, eax
0x1800046d8  mov     [rdi], rbp
0x1800046db  cmp     ax, [rbp+0]
0x1800046df  jz      short loc_180004723
0x1800046e1  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800046e8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800046ed  mov     rcx, rdi; this
0x1800046f0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800046f5  mov     ebx, eax
0x1800046f7  test    eax, eax
0x1800046f9  js      short loc_180004723
0x1800046fb  xor     ebx, ebx
0x1800046fd  movsxd  rsi, ebx
0x180004700  lea     rcx, [rsp+2088h+String1]; lpString1
0x180004705  add     rsi, rsi
0x180004708  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000470d  call    cs:__imp_lstrcmpiW
0x180004713  test    eax, eax
0x180004715  jz      short loc_180004750
0x180004717  inc     ebx
0x180004719  cmp     ebx, 0Eh
0x18000471c  jb      short loc_1800046FD
0x18000471e  mov     ebx, 80020009h
0x180004723  mov     rcx, rbp; pv
0x180004726  call    cs:__imp_CoTaskMemFree
0x18000472c  mov     eax, ebx
0x18000472e  mov     rcx, [rsp+2088h+var_48]
0x180004736  xor     rcx, rsp; StackCookie
0x180004739  call    __security_check_cookie
0x18000473e  add     rsp, 2050h
0x180004745  pop     r15
0x180004747  pop     r14
0x180004749  pop     r13
0x18000474b  pop     rdi
0x18000474c  pop     rsi
0x18000474d  pop     rbp
0x18000474e  pop     rbx
0x18000474f  retn
0x180004750  mov     rsi, [r13+rsi*8+8]
0x180004755  test    rsi, rsi
0x180004758  jz      short loc_18000471E
0x18000475a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000475f  mov     rcx, rdi; this
0x180004762  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004767  mov     ebx, eax
0x180004769  test    eax, eax
0x18000476b  js      short loc_180004723
0x18000476d  mov     eax, 7Bh ; '{'
0x180004772  cmp     ax, [rsp+2088h+String1]
0x180004777  jnz     short loc_18000471E
0x180004779  mov     [rsp+2088h+var_2068], 0; int
0x180004781  mov     r8, rsi; HKEY
0x180004784  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004789  mov     rcx, rdi; this
0x18000478c  test    r15d, r15d
0x18000478f  jz      short loc_1800047C5
0x180004791  mov     r14, [rdi]
0x180004794  mov     r9d, r15d; int
0x180004797  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000479c  mov     ebx, eax
0x18000479e  test    eax, eax
0x1800047a0  jns     short loc_1800047D7
0x1800047a2  xor     r9d, r9d; int
0x1800047a5  mov     [rdi], r14
0x1800047a8  mov     r8, rsi; HKEY
0x1800047ab  mov     [rsp+2088h+var_2068], 0; int
0x1800047b3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800047b8  mov     rcx, rdi; this
0x1800047bb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800047c0  jmp     loc_180004723
0x1800047c5  xor     r9d, r9d; int
0x1800047c8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800047cd  mov     ebx, eax
0x1800047cf  test    eax, eax
0x1800047d1  js      loc_180004723
0x1800047d7  mov     r8, [rdi]
0x1800047da  movzx   edx, word ptr [r8]
0x1800047de  mov     ecx, edx
0x1800047e0  sub     ecx, 9
0x1800047e3  jz      short loc_1800047F4
0x1800047e5  sub     ecx, 1
0x1800047e8  jz      short loc_1800047F4
0x1800047ea  sub     ecx, 3
0x1800047ed  jz      short loc_1800047F4
0x1800047ef  cmp     ecx, 13h
0x1800047f2  jnz     short loc_180004802
0x1800047f4  mov     rcx, r8; lpsz
0x1800047f7  call    cs:__imp_CharNextW
0x1800047fd  mov     [rdi], rax
0x180004800  jmp     short loc_1800047D7
0x180004802  xor     eax, eax
0x180004804  cmp     ax, dx
0x180004807  jnz     loc_1800046E8
0x18000480d  jmp     loc_180004723
```
