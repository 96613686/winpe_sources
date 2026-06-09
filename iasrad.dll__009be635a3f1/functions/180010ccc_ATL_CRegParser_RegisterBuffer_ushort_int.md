# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180010ccc`
- end: `0x180010e36`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010e3c`

## callees

- `0x1800106a0`
- `0x180010870`
- `0x180010ccc`
- `0x1800110f4`
- `0x180011a24`
- `0x18002e230`
- `0x18002e2f0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180010d51`
- `KERNEL32!lstrcmpiW` at `0x180010d51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010d6a`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
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
      while ( **(_WORD **)this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180010ccc  push    rbx
0x180010cce  push    rbp
0x180010ccf  push    rsi
0x180010cd0  push    rdi
0x180010cd1  push    r13
0x180010cd3  push    r14
0x180010cd5  push    r15
0x180010cd7  mov     eax, 2050h
0x180010cdc  call    _alloca_probe
0x180010ce1  sub     rsp, rax
0x180010ce4  mov     rax, cs:__security_cookie
0x180010ceb  xor     rax, rsp
0x180010cee  mov     [rsp+2088h+var_48], rax
0x180010cf6  mov     r15d, r8d
0x180010cf9  mov     [rsp+2088h+pv], 0
0x180010d02  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180010d07  mov     rdi, rcx
0x180010d0a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180010d0f  mov     ebx, eax
0x180010d11  test    eax, eax
0x180010d13  js      short loc_180010D72
0x180010d15  mov     rbp, [rsp+2088h+pv]
0x180010d1a  xor     eax, eax
0x180010d1c  mov     [rdi], rbp
0x180010d1f  cmp     ax, [rbp+0]
0x180010d23  jz      short loc_180010D67
0x180010d25  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180010d2c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180010d31  mov     rcx, rdi; this
0x180010d34  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010d39  mov     ebx, eax
0x180010d3b  test    eax, eax
0x180010d3d  js      short loc_180010D67
0x180010d3f  xor     ebx, ebx
0x180010d41  movsxd  rsi, ebx
0x180010d44  lea     rcx, [rsp+2088h+String1]; lpString1
0x180010d49  add     rsi, rsi
0x180010d4c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180010d51  call    cs:__imp_lstrcmpiW
0x180010d57  test    eax, eax
0x180010d59  jz      short loc_180010D94
0x180010d5b  inc     ebx
0x180010d5d  cmp     ebx, 0Eh
0x180010d60  jb      short loc_180010D41
0x180010d62  mov     ebx, 80020009h
0x180010d67  mov     rcx, rbp; pv
0x180010d6a  call    cs:__imp_CoTaskMemFree
0x180010d70  mov     eax, ebx
0x180010d72  mov     rcx, [rsp+2088h+var_48]
0x180010d7a  xor     rcx, rsp; StackCookie
0x180010d7d  call    __security_check_cookie
0x180010d82  add     rsp, 2050h
0x180010d89  pop     r15
0x180010d8b  pop     r14
0x180010d8d  pop     r13
0x180010d8f  pop     rdi
0x180010d90  pop     rsi
0x180010d91  pop     rbp
0x180010d92  pop     rbx
0x180010d93  retn
0x180010d94  mov     rsi, [r13+rsi*8+8]
0x180010d99  test    rsi, rsi
0x180010d9c  jz      short loc_180010D62
0x180010d9e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180010da3  mov     rcx, rdi; this
0x180010da6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010dab  mov     ebx, eax
0x180010dad  test    eax, eax
0x180010daf  js      short loc_180010D67
0x180010db1  mov     eax, 7Bh ; '{'
0x180010db6  cmp     ax, [rsp+2088h+String1]
0x180010dbb  jnz     short loc_180010D62
0x180010dbd  mov     [rsp+2088h+var_2068], 0; int
0x180010dc5  mov     r8, rsi; HKEY
0x180010dc8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180010dcd  mov     rcx, rdi; this
0x180010dd0  test    r15d, r15d
0x180010dd3  jz      short loc_180010E09
0x180010dd5  mov     r14, [rdi]
0x180010dd8  mov     r9d, r15d; int
0x180010ddb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180010de0  mov     ebx, eax
0x180010de2  test    eax, eax
0x180010de4  jns     short loc_180010E1B
0x180010de6  xor     r9d, r9d; int
0x180010de9  mov     [rdi], r14
0x180010dec  mov     r8, rsi; HKEY
0x180010def  mov     [rsp+2088h+var_2068], 0; int
0x180010df7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180010dfc  mov     rcx, rdi; this
0x180010dff  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180010e04  jmp     loc_180010D67
0x180010e09  xor     r9d, r9d; int
0x180010e0c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180010e11  mov     ebx, eax
0x180010e13  test    eax, eax
0x180010e15  js      loc_180010D67
0x180010e1b  mov     rcx, rdi; this
0x180010e1e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180010e23  mov     rcx, [rdi]
0x180010e26  xor     eax, eax
0x180010e28  cmp     ax, [rcx]
0x180010e2b  jnz     loc_180010D2C
0x180010e31  jmp     loc_180010D67
```
