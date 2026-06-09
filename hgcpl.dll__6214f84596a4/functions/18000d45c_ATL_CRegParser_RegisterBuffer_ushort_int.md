# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000d45c`
- end: `0x18000d5c9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d5d0`

## callees

- `0x18000cf14`
- `0x18000d0cc`
- `0x18000d45c`
- `0x18000d764`
- `0x18000de50`
- `0x180018a80`
- `0x180018b10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d59f`
- `KERNEL32!lstrcmpiW` at `0x18000d4f8`
- `KERNEL32!lstrcmpiW` at `0x18000d4f8`

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
  result = ATL::CRegParser::PreProcessBuffer(this, a2, &pv);
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
0x18000d45c  push    rbx
0x18000d45e  push    rbp
0x18000d45f  push    rsi
0x18000d460  push    rdi
0x18000d461  push    r13
0x18000d463  push    r14
0x18000d465  push    r15
0x18000d467  mov     eax, 2050h
0x18000d46c  call    _alloca_probe
0x18000d471  sub     rsp, rax
0x18000d474  mov     rax, cs:__security_cookie
0x18000d47b  xor     rax, rsp
0x18000d47e  mov     [rsp+2088h+var_48], rax
0x18000d486  mov     r15d, r8d
0x18000d489  mov     [rsp+2088h+pv], 0
0x18000d492  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000d497  mov     rdi, rcx
0x18000d49a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000d49f  mov     ebx, eax
0x18000d4a1  test    eax, eax
0x18000d4a3  js      loc_18000D5A7
0x18000d4a9  mov     rbp, [rsp+2088h+pv]
0x18000d4ae  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000d4b5  mov     [rdi], rbp
0x18000d4b8  mov     rcx, [rdi]
0x18000d4bb  xor     eax, eax
0x18000d4bd  cmp     ax, [rcx]
0x18000d4c0  jz      loc_18000D59C
0x18000d4c6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000d4cb  mov     rcx, rdi; this
0x18000d4ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d4d3  mov     ebx, eax
0x18000d4d5  test    eax, eax
0x18000d4d7  js      loc_18000D59C
0x18000d4dd  xor     ebx, ebx
0x18000d4df  cmp     ebx, 0Eh
0x18000d4e2  jnb     loc_18000D597
0x18000d4e8  movsxd  rsi, ebx
0x18000d4eb  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000d4f0  add     rsi, rsi
0x18000d4f3  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000d4f8  call    cs:__imp_lstrcmpiW
0x18000d4fe  test    eax, eax
0x18000d500  jz      short loc_18000D506
0x18000d502  inc     ebx
0x18000d504  jmp     short loc_18000D4DF
0x18000d506  mov     rsi, [r13+rsi*8+8]
0x18000d50b  test    rsi, rsi
0x18000d50e  jz      loc_18000D597
0x18000d514  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000d519  mov     rcx, rdi; this
0x18000d51c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d521  mov     ebx, eax
0x18000d523  test    eax, eax
0x18000d525  js      short loc_18000D59C
0x18000d527  mov     eax, 7Bh ; '{'
0x18000d52c  cmp     ax, [rsp+2088h+String1]
0x18000d531  jnz     short loc_18000D597
0x18000d533  mov     [rsp+2088h+var_2068], 0; int
0x18000d53b  mov     r8, rsi; HKEY
0x18000d53e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000d543  mov     rcx, rdi; this
0x18000d546  test    r15d, r15d
0x18000d549  jz      short loc_18000D57C
0x18000d54b  mov     r14, [rdi]
0x18000d54e  mov     r9d, r15d; int
0x18000d551  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000d556  mov     ebx, eax
0x18000d558  test    eax, eax
0x18000d55a  jns     short loc_18000D58A
0x18000d55c  xor     r9d, r9d; int
0x18000d55f  mov     [rdi], r14
0x18000d562  mov     r8, rsi; HKEY
0x18000d565  mov     [rsp+2088h+var_2068], 0; int
0x18000d56d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000d572  mov     rcx, rdi; this
0x18000d575  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000d57a  jmp     short loc_18000D59C
0x18000d57c  xor     r9d, r9d; int
0x18000d57f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000d584  mov     ebx, eax
0x18000d586  test    eax, eax
0x18000d588  js      short loc_18000D59C
0x18000d58a  mov     rcx, rdi; this
0x18000d58d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000d592  jmp     loc_18000D4B8
0x18000d597  mov     ebx, 80020009h
0x18000d59c  mov     rcx, rbp; pv
0x18000d59f  call    cs:__imp_CoTaskMemFree
0x18000d5a5  mov     eax, ebx
0x18000d5a7  mov     rcx, [rsp+2088h+var_48]
0x18000d5af  xor     rcx, rsp; StackCookie
0x18000d5b2  call    __security_check_cookie
0x18000d5b7  add     rsp, 2050h
0x18000d5be  pop     r15
0x18000d5c0  pop     r14
0x18000d5c2  pop     r13
0x18000d5c4  pop     rdi
0x18000d5c5  pop     rsi
0x18000d5c6  pop     rbp
0x18000d5c7  pop     rbx
0x18000d5c8  retn
```
