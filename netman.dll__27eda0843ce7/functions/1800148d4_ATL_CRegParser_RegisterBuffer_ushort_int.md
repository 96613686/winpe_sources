# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800148d4`
- end: `0x180014a41`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014b7c`

## callees

- `0x180001710`
- `0x180012408`
- `0x180012918`
- `0x1800148d4`
- `0x180014d38`
- `0x1800174d4`
- `0x180034d90`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180014970`
- `KERNEL32!lstrcmpiW` at `0x180014970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a17`

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
0x1800148d4  push    rbx
0x1800148d6  push    rbp
0x1800148d7  push    rsi
0x1800148d8  push    rdi
0x1800148d9  push    r13
0x1800148db  push    r14
0x1800148dd  push    r15
0x1800148df  mov     eax, 2050h
0x1800148e4  call    _alloca_probe
0x1800148e9  sub     rsp, rax
0x1800148ec  mov     rax, cs:__security_cookie
0x1800148f3  xor     rax, rsp
0x1800148f6  mov     [rsp+2088h+var_48], rax
0x1800148fe  mov     r15d, r8d
0x180014901  mov     [rsp+2088h+pv], 0
0x18001490a  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18001490f  mov     rdi, rcx
0x180014912  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180014917  mov     ebx, eax
0x180014919  test    eax, eax
0x18001491b  js      loc_180014A1F
0x180014921  mov     rbp, [rsp+2088h+pv]
0x180014926  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18001492d  mov     [rdi], rbp
0x180014930  mov     rcx, [rdi]
0x180014933  xor     eax, eax
0x180014935  cmp     ax, [rcx]
0x180014938  jz      loc_180014A14
0x18001493e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180014943  mov     rcx, rdi; this
0x180014946  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001494b  mov     ebx, eax
0x18001494d  test    eax, eax
0x18001494f  js      loc_180014A14
0x180014955  xor     ebx, ebx
0x180014957  cmp     ebx, 0Eh
0x18001495a  jnb     loc_180014A0F
0x180014960  movsxd  rsi, ebx
0x180014963  lea     rcx, [rsp+2088h+String1]; lpString1
0x180014968  add     rsi, rsi
0x18001496b  mov     rdx, [r13+rsi*8+0]; lpString2
0x180014970  call    cs:__imp_lstrcmpiW
0x180014976  test    eax, eax
0x180014978  jz      short loc_18001497E
0x18001497a  inc     ebx
0x18001497c  jmp     short loc_180014957
0x18001497e  mov     rsi, [r13+rsi*8+8]
0x180014983  test    rsi, rsi
0x180014986  jz      loc_180014A0F
0x18001498c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180014991  mov     rcx, rdi; this
0x180014994  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014999  mov     ebx, eax
0x18001499b  test    eax, eax
0x18001499d  js      short loc_180014A14
0x18001499f  mov     eax, 7Bh ; '{'
0x1800149a4  cmp     ax, [rsp+2088h+String1]
0x1800149a9  jnz     short loc_180014A0F
0x1800149ab  mov     [rsp+2088h+var_2068], 0; int
0x1800149b3  mov     r8, rsi; HKEY
0x1800149b6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800149bb  mov     rcx, rdi; this
0x1800149be  test    r15d, r15d
0x1800149c1  jz      short loc_1800149F4
0x1800149c3  mov     r14, [rdi]
0x1800149c6  mov     r9d, r15d; int
0x1800149c9  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800149ce  mov     ebx, eax
0x1800149d0  test    eax, eax
0x1800149d2  jns     short loc_180014A02
0x1800149d4  xor     r9d, r9d; int
0x1800149d7  mov     [rdi], r14
0x1800149da  mov     r8, rsi; HKEY
0x1800149dd  mov     [rsp+2088h+var_2068], 0; int
0x1800149e5  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800149ea  mov     rcx, rdi; this
0x1800149ed  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800149f2  jmp     short loc_180014A14
0x1800149f4  xor     r9d, r9d; int
0x1800149f7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800149fc  mov     ebx, eax
0x1800149fe  test    eax, eax
0x180014a00  js      short loc_180014A14
0x180014a02  mov     rcx, rdi; this
0x180014a05  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180014a0a  jmp     loc_180014930
0x180014a0f  mov     ebx, 80020009h
0x180014a14  mov     rcx, rbp; pv
0x180014a17  call    cs:__imp_CoTaskMemFree
0x180014a1d  mov     eax, ebx
0x180014a1f  mov     rcx, [rsp+2088h+var_48]
0x180014a27  xor     rcx, rsp; StackCookie
0x180014a2a  call    __security_check_cookie
0x180014a2f  add     rsp, 2050h
0x180014a36  pop     r15
0x180014a38  pop     r14
0x180014a3a  pop     r13
0x180014a3c  pop     rdi
0x180014a3d  pop     rsi
0x180014a3e  pop     rbp
0x180014a3f  pop     rbx
0x180014a40  retn
```
