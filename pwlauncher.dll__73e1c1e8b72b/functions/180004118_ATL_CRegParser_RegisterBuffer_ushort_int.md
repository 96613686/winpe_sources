# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180004118`
- end: `0x1800042a2`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800042a8`

## callees

- `0x180003b24`
- `0x180003cc4`
- `0x180004118`
- `0x18000448c`
- `0x18000fe10`
- `0x18000fed0`

## import_xrefs

- `USER32!CharNextW` at `0x180004287`
- `USER32!CharNextW` at `0x180004287`
- `KERNEL32!lstrcmpiW` at `0x18000419d`
- `KERNEL32!lstrcmpiW` at `0x18000419d`
- `ole32!CoTaskMemFree` at `0x1800041b6`
- `ole32!CoTaskMemFree` at `0x1800041b6`

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
        Token = ATL::CRegParser::NextToken(this, String1);
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
        Token = ATL::CRegParser::NextToken(this, String1);
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
0x180004118  push    rbx
0x18000411a  push    rbp
0x18000411b  push    rsi
0x18000411c  push    rdi
0x18000411d  push    r13
0x18000411f  push    r14
0x180004121  push    r15
0x180004123  mov     eax, 2050h
0x180004128  call    _alloca_probe
0x18000412d  sub     rsp, rax
0x180004130  mov     rax, cs:__security_cookie
0x180004137  xor     rax, rsp
0x18000413a  mov     [rsp+2088h+var_48], rax
0x180004142  mov     r15d, r8d
0x180004145  mov     [rsp+2088h+pv], 0
0x18000414e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180004153  mov     rdi, rcx
0x180004156  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000415b  mov     ebx, eax
0x18000415d  test    eax, eax
0x18000415f  js      short loc_1800041BE
0x180004161  mov     rbp, [rsp+2088h+pv]
0x180004166  xor     eax, eax
0x180004168  mov     [rdi], rbp
0x18000416b  cmp     ax, [rbp+0]
0x18000416f  jz      short loc_1800041B3
0x180004171  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180004178  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000417d  mov     rcx, rdi; this
0x180004180  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004185  mov     ebx, eax
0x180004187  test    eax, eax
0x180004189  js      short loc_1800041B3
0x18000418b  xor     ebx, ebx
0x18000418d  movsxd  rsi, ebx
0x180004190  lea     rcx, [rsp+2088h+String1]; lpString1
0x180004195  add     rsi, rsi
0x180004198  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000419d  call    cs:__imp_lstrcmpiW
0x1800041a3  test    eax, eax
0x1800041a5  jz      short loc_1800041E0
0x1800041a7  inc     ebx
0x1800041a9  cmp     ebx, 0Eh
0x1800041ac  jb      short loc_18000418D
0x1800041ae  mov     ebx, 80020009h
0x1800041b3  mov     rcx, rbp; pv
0x1800041b6  call    cs:__imp_CoTaskMemFree
0x1800041bc  mov     eax, ebx
0x1800041be  mov     rcx, [rsp+2088h+var_48]
0x1800041c6  xor     rcx, rsp; StackCookie
0x1800041c9  call    __security_check_cookie
0x1800041ce  add     rsp, 2050h
0x1800041d5  pop     r15
0x1800041d7  pop     r14
0x1800041d9  pop     r13
0x1800041db  pop     rdi
0x1800041dc  pop     rsi
0x1800041dd  pop     rbp
0x1800041de  pop     rbx
0x1800041df  retn
0x1800041e0  mov     rsi, [r13+rsi*8+8]
0x1800041e5  test    rsi, rsi
0x1800041e8  jz      short loc_1800041AE
0x1800041ea  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800041ef  mov     rcx, rdi; this
0x1800041f2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800041f7  mov     ebx, eax
0x1800041f9  test    eax, eax
0x1800041fb  js      short loc_1800041B3
0x1800041fd  mov     eax, 7Bh ; '{'
0x180004202  cmp     ax, [rsp+2088h+String1]
0x180004207  jnz     short loc_1800041AE
0x180004209  mov     [rsp+2088h+var_2068], 0; int
0x180004211  mov     r8, rsi; HKEY
0x180004214  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004219  mov     rcx, rdi; this
0x18000421c  test    r15d, r15d
0x18000421f  jz      short loc_180004255
0x180004221  mov     r14, [rdi]
0x180004224  mov     r9d, r15d; int
0x180004227  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000422c  mov     ebx, eax
0x18000422e  test    eax, eax
0x180004230  jns     short loc_180004267
0x180004232  xor     r9d, r9d; int
0x180004235  mov     [rdi], r14
0x180004238  mov     r8, rsi; HKEY
0x18000423b  mov     [rsp+2088h+var_2068], 0; int
0x180004243  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004248  mov     rcx, rdi; this
0x18000424b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004250  jmp     loc_1800041B3
0x180004255  xor     r9d, r9d; int
0x180004258  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000425d  mov     ebx, eax
0x18000425f  test    eax, eax
0x180004261  js      loc_1800041B3
0x180004267  mov     r8, [rdi]
0x18000426a  movzx   edx, word ptr [r8]
0x18000426e  mov     ecx, edx
0x180004270  sub     ecx, 9
0x180004273  jz      short loc_180004284
0x180004275  sub     ecx, 1
0x180004278  jz      short loc_180004284
0x18000427a  sub     ecx, 3
0x18000427d  jz      short loc_180004284
0x18000427f  cmp     ecx, 13h
0x180004282  jnz     short loc_180004292
0x180004284  mov     rcx, r8; lpsz
0x180004287  call    cs:__imp_CharNextW
0x18000428d  mov     [rdi], rax
0x180004290  jmp     short loc_180004267
0x180004292  xor     eax, eax
0x180004294  cmp     ax, dx
0x180004297  jnz     loc_180004178
0x18000429d  jmp     loc_1800041B3
```
