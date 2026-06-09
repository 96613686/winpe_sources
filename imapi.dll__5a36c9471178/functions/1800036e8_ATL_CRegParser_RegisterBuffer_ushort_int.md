# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800036e8`
- end: `0x180003872`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180003878`

## callees

- `0x1800030c0`
- `0x18000326c`
- `0x1800036e8`
- `0x180003a3c`
- `0x180018500`
- `0x1800185c0`

## import_xrefs

- `USER32!CharNextW` at `0x180003857`
- `USER32!CharNextW` at `0x180003857`
- `ole32!CoTaskMemFree` at `0x180003786`
- `ole32!CoTaskMemFree` at `0x180003786`
- `KERNEL32!lstrcmpiW` at `0x18000376d`
- `KERNEL32!lstrcmpiW` at `0x18000376d`

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
0x1800036e8  push    rbx
0x1800036ea  push    rbp
0x1800036eb  push    rsi
0x1800036ec  push    rdi
0x1800036ed  push    r13
0x1800036ef  push    r14
0x1800036f1  push    r15
0x1800036f3  mov     eax, 2050h
0x1800036f8  call    _alloca_probe
0x1800036fd  sub     rsp, rax
0x180003700  mov     rax, cs:__security_cookie
0x180003707  xor     rax, rsp
0x18000370a  mov     [rsp+2088h+var_48], rax
0x180003712  mov     r15d, r8d
0x180003715  mov     [rsp+2088h+pv], 0
0x18000371e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180003723  mov     rdi, rcx
0x180003726  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000372b  mov     ebx, eax
0x18000372d  test    eax, eax
0x18000372f  js      short loc_18000378E
0x180003731  mov     rbp, [rsp+2088h+pv]
0x180003736  xor     eax, eax
0x180003738  mov     [rdi], rbp
0x18000373b  cmp     ax, [rbp+0]
0x18000373f  jz      short loc_180003783
0x180003741  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180003748  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000374d  mov     rcx, rdi; this
0x180003750  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003755  mov     ebx, eax
0x180003757  test    eax, eax
0x180003759  js      short loc_180003783
0x18000375b  xor     ebx, ebx
0x18000375d  movsxd  rsi, ebx
0x180003760  lea     rcx, [rsp+2088h+String1]; lpString1
0x180003765  add     rsi, rsi
0x180003768  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000376d  call    cs:__imp_lstrcmpiW
0x180003773  test    eax, eax
0x180003775  jz      short loc_1800037B0
0x180003777  inc     ebx
0x180003779  cmp     ebx, 0Eh
0x18000377c  jb      short loc_18000375D
0x18000377e  mov     ebx, 80020009h
0x180003783  mov     rcx, rbp; pv
0x180003786  call    cs:__imp_CoTaskMemFree
0x18000378c  mov     eax, ebx
0x18000378e  mov     rcx, [rsp+2088h+var_48]
0x180003796  xor     rcx, rsp; StackCookie
0x180003799  call    __security_check_cookie
0x18000379e  add     rsp, 2050h
0x1800037a5  pop     r15
0x1800037a7  pop     r14
0x1800037a9  pop     r13
0x1800037ab  pop     rdi
0x1800037ac  pop     rsi
0x1800037ad  pop     rbp
0x1800037ae  pop     rbx
0x1800037af  retn
0x1800037b0  mov     rsi, [r13+rsi*8+8]
0x1800037b5  test    rsi, rsi
0x1800037b8  jz      short loc_18000377E
0x1800037ba  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800037bf  mov     rcx, rdi; this
0x1800037c2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800037c7  mov     ebx, eax
0x1800037c9  test    eax, eax
0x1800037cb  js      short loc_180003783
0x1800037cd  mov     eax, 7Bh ; '{'
0x1800037d2  cmp     ax, [rsp+2088h+String1]
0x1800037d7  jnz     short loc_18000377E
0x1800037d9  mov     [rsp+2088h+var_2068], 0; int
0x1800037e1  mov     r8, rsi; HKEY
0x1800037e4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800037e9  mov     rcx, rdi; this
0x1800037ec  test    r15d, r15d
0x1800037ef  jz      short loc_180003825
0x1800037f1  mov     r14, [rdi]
0x1800037f4  mov     r9d, r15d; int
0x1800037f7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800037fc  mov     ebx, eax
0x1800037fe  test    eax, eax
0x180003800  jns     short loc_180003837
0x180003802  xor     r9d, r9d; int
0x180003805  mov     [rdi], r14
0x180003808  mov     r8, rsi; HKEY
0x18000380b  mov     [rsp+2088h+var_2068], 0; int
0x180003813  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180003818  mov     rcx, rdi; this
0x18000381b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003820  jmp     loc_180003783
0x180003825  xor     r9d, r9d; int
0x180003828  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000382d  mov     ebx, eax
0x18000382f  test    eax, eax
0x180003831  js      loc_180003783
0x180003837  mov     r8, [rdi]
0x18000383a  movzx   edx, word ptr [r8]
0x18000383e  mov     ecx, edx
0x180003840  sub     ecx, 9
0x180003843  jz      short loc_180003854
0x180003845  sub     ecx, 1
0x180003848  jz      short loc_180003854
0x18000384a  sub     ecx, 3
0x18000384d  jz      short loc_180003854
0x18000384f  cmp     ecx, 13h
0x180003852  jnz     short loc_180003862
0x180003854  mov     rcx, r8; lpsz
0x180003857  call    cs:__imp_CharNextW
0x18000385d  mov     [rdi], rax
0x180003860  jmp     short loc_180003837
0x180003862  xor     eax, eax
0x180003864  cmp     ax, dx
0x180003867  jnz     loc_180003748
0x18000386d  jmp     loc_180003783
```
