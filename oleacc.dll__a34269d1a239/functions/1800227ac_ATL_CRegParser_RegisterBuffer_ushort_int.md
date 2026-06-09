# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800227ac`
- end: `0x180022919`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022920`

## callees

- `0x18001e4c0`
- `0x180022200`
- `0x1800223b8`
- `0x1800227ac`
- `0x180022ad0`
- `0x18002321c`
- `0x180047f80`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022848`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800228ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800228ef`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
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
0x1800227ac  push    rbx
0x1800227ae  push    rbp
0x1800227af  push    rsi
0x1800227b0  push    rdi
0x1800227b1  push    r13
0x1800227b3  push    r14
0x1800227b5  push    r15
0x1800227b7  mov     eax, 2050h
0x1800227bc  call    _alloca_probe
0x1800227c1  sub     rsp, rax
0x1800227c4  mov     rax, cs:__security_cookie
0x1800227cb  xor     rax, rsp
0x1800227ce  mov     [rsp+2088h+var_48], rax
0x1800227d6  mov     r15d, r8d
0x1800227d9  mov     [rsp+2088h+pv], 0
0x1800227e2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800227e7  mov     rdi, rcx
0x1800227ea  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800227ef  mov     ebx, eax
0x1800227f1  test    eax, eax
0x1800227f3  js      loc_1800228F7
0x1800227f9  mov     rbp, [rsp+2088h+pv]
0x1800227fe  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180022805  mov     [rdi], rbp
0x180022808  mov     rcx, [rdi]
0x18002280b  xor     eax, eax
0x18002280d  cmp     ax, [rcx]
0x180022810  jz      loc_1800228EC
0x180022816  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18002281b  mov     rcx, rdi; this
0x18002281e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022823  mov     ebx, eax
0x180022825  test    eax, eax
0x180022827  js      loc_1800228EC
0x18002282d  xor     ebx, ebx
0x18002282f  cmp     ebx, 0Eh
0x180022832  jnb     loc_1800228E7
0x180022838  movsxd  rsi, ebx
0x18002283b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180022840  add     rsi, rsi
0x180022843  mov     rdx, [r13+rsi*8+0]; lpString2
0x180022848  call    cs:__imp_lstrcmpiW
0x18002284e  test    eax, eax
0x180022850  jz      short loc_180022856
0x180022852  inc     ebx
0x180022854  jmp     short loc_18002282F
0x180022856  mov     rsi, [r13+rsi*8+8]
0x18002285b  test    rsi, rsi
0x18002285e  jz      loc_1800228E7
0x180022864  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180022869  mov     rcx, rdi; this
0x18002286c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022871  mov     ebx, eax
0x180022873  test    eax, eax
0x180022875  js      short loc_1800228EC
0x180022877  mov     eax, 7Bh ; '{'
0x18002287c  cmp     ax, [rsp+2088h+String1]
0x180022881  jnz     short loc_1800228E7
0x180022883  mov     [rsp+2088h+var_2068], 0; int
0x18002288b  mov     r8, rsi; HKEY
0x18002288e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180022893  mov     rcx, rdi; this
0x180022896  test    r15d, r15d
0x180022899  jz      short loc_1800228CC
0x18002289b  mov     r14, [rdi]
0x18002289e  mov     r9d, r15d; int
0x1800228a1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800228a6  mov     ebx, eax
0x1800228a8  test    eax, eax
0x1800228aa  jns     short loc_1800228DA
0x1800228ac  xor     r9d, r9d; int
0x1800228af  mov     [rdi], r14
0x1800228b2  mov     r8, rsi; HKEY
0x1800228b5  mov     [rsp+2088h+var_2068], 0; int
0x1800228bd  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800228c2  mov     rcx, rdi; this
0x1800228c5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800228ca  jmp     short loc_1800228EC
0x1800228cc  xor     r9d, r9d; int
0x1800228cf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800228d4  mov     ebx, eax
0x1800228d6  test    eax, eax
0x1800228d8  js      short loc_1800228EC
0x1800228da  mov     rcx, rdi; this
0x1800228dd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800228e2  jmp     loc_180022808
0x1800228e7  mov     ebx, 80020009h
0x1800228ec  mov     rcx, rbp; pv
0x1800228ef  call    cs:__imp_CoTaskMemFree
0x1800228f5  mov     eax, ebx
0x1800228f7  mov     rcx, [rsp+2088h+var_48]
0x1800228ff  xor     rcx, rsp; StackCookie
0x180022902  call    __security_check_cookie
0x180022907  add     rsp, 2050h
0x18002290e  pop     r15
0x180022910  pop     r14
0x180022912  pop     r13
0x180022914  pop     rdi
0x180022915  pop     rsi
0x180022916  pop     rbp
0x180022917  pop     rbx
0x180022918  retn
```
