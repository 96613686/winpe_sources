# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180004ea8`
- end: `0x180005032`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005038`

## callees

- `0x180001f90`
- `0x1800047e0`
- `0x18000498c`
- `0x180004ea8`
- `0x18000521c`
- `0x180012350`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f46`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005017`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005017`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004f2d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004f2d`

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
0x180004ea8  push    rbx
0x180004eaa  push    rbp
0x180004eab  push    rsi
0x180004eac  push    rdi
0x180004ead  push    r13
0x180004eaf  push    r14
0x180004eb1  push    r15
0x180004eb3  mov     eax, 2050h
0x180004eb8  call    _alloca_probe
0x180004ebd  sub     rsp, rax
0x180004ec0  mov     rax, cs:__security_cookie
0x180004ec7  xor     rax, rsp
0x180004eca  mov     [rsp+2088h+var_48], rax
0x180004ed2  mov     r15d, r8d
0x180004ed5  mov     [rsp+2088h+pv], 0
0x180004ede  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180004ee3  mov     rdi, rcx
0x180004ee6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180004eeb  mov     ebx, eax
0x180004eed  test    eax, eax
0x180004eef  js      short loc_180004F4E
0x180004ef1  mov     rbp, [rsp+2088h+pv]
0x180004ef6  xor     eax, eax
0x180004ef8  mov     [rdi], rbp
0x180004efb  cmp     ax, [rbp+0]
0x180004eff  jz      short loc_180004F43
0x180004f01  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180004f08  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004f0d  mov     rcx, rdi; this
0x180004f10  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004f15  mov     ebx, eax
0x180004f17  test    eax, eax
0x180004f19  js      short loc_180004F43
0x180004f1b  xor     ebx, ebx
0x180004f1d  movsxd  rsi, ebx
0x180004f20  lea     rcx, [rsp+2088h+String1]; lpString1
0x180004f25  add     rsi, rsi
0x180004f28  mov     rdx, [r13+rsi*8+0]; lpString2
0x180004f2d  call    cs:__imp_lstrcmpiW
0x180004f33  test    eax, eax
0x180004f35  jz      short loc_180004F70
0x180004f37  inc     ebx
0x180004f39  cmp     ebx, 0Eh
0x180004f3c  jb      short loc_180004F1D
0x180004f3e  mov     ebx, 80020009h
0x180004f43  mov     rcx, rbp; pv
0x180004f46  call    cs:__imp_CoTaskMemFree
0x180004f4c  mov     eax, ebx
0x180004f4e  mov     rcx, [rsp+2088h+var_48]
0x180004f56  xor     rcx, rsp; StackCookie
0x180004f59  call    __security_check_cookie
0x180004f5e  add     rsp, 2050h
0x180004f65  pop     r15
0x180004f67  pop     r14
0x180004f69  pop     r13
0x180004f6b  pop     rdi
0x180004f6c  pop     rsi
0x180004f6d  pop     rbp
0x180004f6e  pop     rbx
0x180004f6f  retn
0x180004f70  mov     rsi, [r13+rsi*8+8]
0x180004f75  test    rsi, rsi
0x180004f78  jz      short loc_180004F3E
0x180004f7a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004f7f  mov     rcx, rdi; this
0x180004f82  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004f87  mov     ebx, eax
0x180004f89  test    eax, eax
0x180004f8b  js      short loc_180004F43
0x180004f8d  mov     eax, 7Bh ; '{'
0x180004f92  cmp     ax, [rsp+2088h+String1]
0x180004f97  jnz     short loc_180004F3E
0x180004f99  mov     [rsp+2088h+var_2068], 0; int
0x180004fa1  mov     r8, rsi; HKEY
0x180004fa4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004fa9  mov     rcx, rdi; this
0x180004fac  test    r15d, r15d
0x180004faf  jz      short loc_180004FE5
0x180004fb1  mov     r14, [rdi]
0x180004fb4  mov     r9d, r15d; int
0x180004fb7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004fbc  mov     ebx, eax
0x180004fbe  test    eax, eax
0x180004fc0  jns     short loc_180004FF7
0x180004fc2  xor     r9d, r9d; int
0x180004fc5  mov     [rdi], r14
0x180004fc8  mov     r8, rsi; HKEY
0x180004fcb  mov     [rsp+2088h+var_2068], 0; int
0x180004fd3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004fd8  mov     rcx, rdi; this
0x180004fdb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004fe0  jmp     loc_180004F43
0x180004fe5  xor     r9d, r9d; int
0x180004fe8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004fed  mov     ebx, eax
0x180004fef  test    eax, eax
0x180004ff1  js      loc_180004F43
0x180004ff7  mov     r8, [rdi]
0x180004ffa  movzx   edx, word ptr [r8]
0x180004ffe  mov     ecx, edx
0x180005000  sub     ecx, 9
0x180005003  jz      short loc_180005014
0x180005005  sub     ecx, 1
0x180005008  jz      short loc_180005014
0x18000500a  sub     ecx, 3
0x18000500d  jz      short loc_180005014
0x18000500f  cmp     ecx, 13h
0x180005012  jnz     short loc_180005022
0x180005014  mov     rcx, r8; lpsz
0x180005017  call    cs:__imp_CharNextW
0x18000501d  mov     [rdi], rax
0x180005020  jmp     short loc_180004FF7
0x180005022  xor     eax, eax
0x180005024  cmp     ax, dx
0x180005027  jnz     loc_180004F08
0x18000502d  jmp     loc_180004F43
```
