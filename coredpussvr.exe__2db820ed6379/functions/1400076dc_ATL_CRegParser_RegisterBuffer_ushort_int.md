# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1400076dc`
- end: `0x140007879`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `413`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140007880`

## callees

- `0x140001500`
- `0x140006f40`
- `0x140007110`
- `0x1400076dc`
- `0x140007a88`
- `0x140009030`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007780`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007858`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007858`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007761`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007761`

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
0x1400076dc  push    rbx
0x1400076de  push    rbp
0x1400076df  push    rsi
0x1400076e0  push    rdi
0x1400076e1  push    r13
0x1400076e3  push    r14
0x1400076e5  push    r15
0x1400076e7  mov     eax, 2050h
0x1400076ec  call    _alloca_probe
0x1400076f1  sub     rsp, rax
0x1400076f4  mov     rax, cs:__security_cookie
0x1400076fb  xor     rax, rsp
0x1400076fe  mov     [rsp+2088h+var_48], rax
0x140007706  mov     r15d, r8d
0x140007709  mov     [rsp+2088h+pv], 0
0x140007712  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x140007717  mov     rdi, rcx
0x14000771a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x14000771f  mov     ebx, eax
0x140007721  test    eax, eax
0x140007723  js      short loc_14000778E
0x140007725  mov     rbp, [rsp+2088h+pv]
0x14000772a  xor     eax, eax
0x14000772c  mov     [rdi], rbp
0x14000772f  cmp     ax, [rbp+0]
0x140007733  jz      short loc_14000777D
0x140007735  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x14000773c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140007741  mov     rcx, rdi; this
0x140007744  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140007749  mov     ebx, eax
0x14000774b  test    eax, eax
0x14000774d  js      short loc_14000777D
0x14000774f  xor     ebx, ebx
0x140007751  movsxd  rsi, ebx
0x140007754  lea     rcx, [rsp+2088h+String1]; lpString1
0x140007759  add     rsi, rsi
0x14000775c  mov     rdx, [r13+rsi*8+0]; lpString2
0x140007761  call    cs:__imp_lstrcmpiW
0x140007768  nop     dword ptr [rax+rax+00h]
0x14000776d  test    eax, eax
0x14000776f  jz      short loc_1400077B1
0x140007771  inc     ebx
0x140007773  cmp     ebx, 0Eh
0x140007776  jb      short loc_140007751
0x140007778  mov     ebx, 80020009h
0x14000777d  mov     rcx, rbp; pv
0x140007780  call    cs:__imp_CoTaskMemFree
0x140007787  nop     dword ptr [rax+rax+00h]
0x14000778c  mov     eax, ebx
0x14000778e  mov     rcx, [rsp+2088h+var_48]
0x140007796  xor     rcx, rsp; StackCookie
0x140007799  call    __security_check_cookie
0x14000779e  add     rsp, 2050h
0x1400077a5  pop     r15
0x1400077a7  pop     r14
0x1400077a9  pop     r13
0x1400077ab  pop     rdi
0x1400077ac  pop     rsi
0x1400077ad  pop     rbp
0x1400077ae  pop     rbx
0x1400077af  retn
0x1400077b1  mov     rsi, [r13+rsi*8+8]
0x1400077b6  test    rsi, rsi
0x1400077b9  jz      short loc_140007778
0x1400077bb  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1400077c0  mov     rcx, rdi; this
0x1400077c3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400077c8  mov     ebx, eax
0x1400077ca  test    eax, eax
0x1400077cc  js      short loc_14000777D
0x1400077ce  mov     eax, 7Bh ; '{'
0x1400077d3  cmp     ax, [rsp+2088h+String1]
0x1400077d8  jnz     short loc_140007778
0x1400077da  mov     [rsp+2088h+var_2068], 0; int
0x1400077e2  mov     r8, rsi; HKEY
0x1400077e5  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1400077ea  mov     rcx, rdi; this
0x1400077ed  test    r15d, r15d
0x1400077f0  jz      short loc_140007826
0x1400077f2  mov     r14, [rdi]
0x1400077f5  mov     r9d, r15d; int
0x1400077f8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1400077fd  mov     ebx, eax
0x1400077ff  test    eax, eax
0x140007801  jns     short loc_140007838
0x140007803  xor     r9d, r9d; int
0x140007806  mov     [rdi], r14
0x140007809  mov     r8, rsi; HKEY
0x14000780c  mov     [rsp+2088h+var_2068], 0; int
0x140007814  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140007819  mov     rcx, rdi; this
0x14000781c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140007821  jmp     loc_14000777D
0x140007826  xor     r9d, r9d; int
0x140007829  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000782e  mov     ebx, eax
0x140007830  test    eax, eax
0x140007832  js      loc_14000777D
0x140007838  mov     r8, [rdi]
0x14000783b  movzx   edx, word ptr [r8]
0x14000783f  mov     ecx, edx
0x140007841  sub     ecx, 9
0x140007844  jz      short loc_140007855
0x140007846  sub     ecx, 1
0x140007849  jz      short loc_140007855
0x14000784b  sub     ecx, 3
0x14000784e  jz      short loc_140007855
0x140007850  cmp     ecx, 13h
0x140007853  jnz     short loc_140007869
0x140007855  mov     rcx, r8; lpsz
0x140007858  call    cs:__imp_CharNextW
0x14000785f  nop     dword ptr [rax+rax+00h]
0x140007864  mov     [rdi], rax
0x140007867  jmp     short loc_140007838
0x140007869  xor     eax, eax
0x14000786b  cmp     ax, dx
0x14000786e  jnz     loc_14000773C
0x140007874  jmp     loc_14000777D
```
