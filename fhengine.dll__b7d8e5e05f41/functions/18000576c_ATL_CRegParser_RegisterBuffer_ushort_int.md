# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000576c`
- end: `0x1800058d9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(const wchar_t **this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800058e0`

## callees

- `0x180005004`
- `0x1800051d4`
- `0x18000576c`
- `0x180005a90`
- `0x180006584`
- `0x180031680`
- `0x180031740`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180005808`
- `KERNEL32!lstrcmpiW` at `0x180005808`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058af`

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
0x18000576c  push    rbx
0x18000576e  push    rbp
0x18000576f  push    rsi
0x180005770  push    rdi
0x180005771  push    r13
0x180005773  push    r14
0x180005775  push    r15
0x180005777  mov     eax, 2050h
0x18000577c  call    _alloca_probe
0x180005781  sub     rsp, rax
0x180005784  mov     rax, cs:__security_cookie
0x18000578b  xor     rax, rsp
0x18000578e  mov     [rsp+2088h+var_48], rax
0x180005796  mov     r15d, r8d
0x180005799  mov     [rsp+2088h+pv], 0
0x1800057a2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800057a7  mov     rdi, rcx
0x1800057aa  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800057af  mov     ebx, eax
0x1800057b1  test    eax, eax
0x1800057b3  js      loc_1800058B7
0x1800057b9  mov     rbp, [rsp+2088h+pv]
0x1800057be  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800057c5  mov     [rdi], rbp
0x1800057c8  mov     rcx, [rdi]
0x1800057cb  xor     eax, eax
0x1800057cd  cmp     ax, [rcx]
0x1800057d0  jz      loc_1800058AC
0x1800057d6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800057db  mov     rcx, rdi; this
0x1800057de  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800057e3  mov     ebx, eax
0x1800057e5  test    eax, eax
0x1800057e7  js      loc_1800058AC
0x1800057ed  xor     ebx, ebx
0x1800057ef  cmp     ebx, 0Eh
0x1800057f2  jnb     loc_1800058A7
0x1800057f8  movsxd  rsi, ebx
0x1800057fb  lea     rcx, [rsp+2088h+String1]; lpString1
0x180005800  add     rsi, rsi
0x180005803  mov     rdx, [r13+rsi*8+0]; lpString2
0x180005808  call    cs:__imp_lstrcmpiW
0x18000580e  test    eax, eax
0x180005810  jz      short loc_180005816
0x180005812  inc     ebx
0x180005814  jmp     short loc_1800057EF
0x180005816  mov     rsi, [r13+rsi*8+8]
0x18000581b  test    rsi, rsi
0x18000581e  jz      loc_1800058A7
0x180005824  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005829  mov     rcx, rdi; this
0x18000582c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005831  mov     ebx, eax
0x180005833  test    eax, eax
0x180005835  js      short loc_1800058AC
0x180005837  mov     eax, 7Bh ; '{'
0x18000583c  cmp     ax, [rsp+2088h+String1]
0x180005841  jnz     short loc_1800058A7
0x180005843  mov     [rsp+2088h+var_2068], 0; int
0x18000584b  mov     r8, rsi; HKEY
0x18000584e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005853  mov     rcx, rdi; this
0x180005856  test    r15d, r15d
0x180005859  jz      short loc_18000588C
0x18000585b  mov     r14, [rdi]
0x18000585e  mov     r9d, r15d; int
0x180005861  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005866  mov     ebx, eax
0x180005868  test    eax, eax
0x18000586a  jns     short loc_18000589A
0x18000586c  xor     r9d, r9d; int
0x18000586f  mov     [rdi], r14
0x180005872  mov     r8, rsi; HKEY
0x180005875  mov     [rsp+2088h+var_2068], 0; int
0x18000587d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005882  mov     rcx, rdi; this
0x180005885  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000588a  jmp     short loc_1800058AC
0x18000588c  xor     r9d, r9d; int
0x18000588f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005894  mov     ebx, eax
0x180005896  test    eax, eax
0x180005898  js      short loc_1800058AC
0x18000589a  mov     rcx, rdi; this
0x18000589d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800058a2  jmp     loc_1800057C8
0x1800058a7  mov     ebx, 80020009h
0x1800058ac  mov     rcx, rbp; pv
0x1800058af  call    cs:__imp_CoTaskMemFree
0x1800058b5  mov     eax, ebx
0x1800058b7  mov     rcx, [rsp+2088h+var_48]
0x1800058bf  xor     rcx, rsp; StackCookie
0x1800058c2  call    __security_check_cookie
0x1800058c7  add     rsp, 2050h
0x1800058ce  pop     r15
0x1800058d0  pop     r14
0x1800058d2  pop     r13
0x1800058d4  pop     rdi
0x1800058d5  pop     rsi
0x1800058d6  pop     rbp
0x1800058d7  pop     rbx
0x1800058d8  retn
```
