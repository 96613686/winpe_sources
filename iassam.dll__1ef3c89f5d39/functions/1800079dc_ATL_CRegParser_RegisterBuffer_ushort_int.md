# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800079dc`
- end: `0x180007b46`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007b4c`

## callees

- `0x1800072f0`
- `0x1800074d4`
- `0x1800079dc`
- `0x180007e04`
- `0x1800087c4`
- `0x18002b4a0`
- `0x18002b560`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180007a61`
- `KERNEL32!lstrcmpiW` at `0x180007a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a7a`

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
0x1800079dc  push    rbx
0x1800079de  push    rbp
0x1800079df  push    rsi
0x1800079e0  push    rdi
0x1800079e1  push    r13
0x1800079e3  push    r14
0x1800079e5  push    r15
0x1800079e7  mov     eax, 2050h
0x1800079ec  call    _alloca_probe
0x1800079f1  sub     rsp, rax
0x1800079f4  mov     rax, cs:__security_cookie
0x1800079fb  xor     rax, rsp
0x1800079fe  mov     [rsp+2088h+var_48], rax
0x180007a06  mov     r15d, r8d
0x180007a09  mov     [rsp+2088h+pv], 0
0x180007a12  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180007a17  mov     rdi, rcx
0x180007a1a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180007a1f  mov     ebx, eax
0x180007a21  test    eax, eax
0x180007a23  js      short loc_180007A82
0x180007a25  mov     rbp, [rsp+2088h+pv]
0x180007a2a  xor     eax, eax
0x180007a2c  mov     [rdi], rbp
0x180007a2f  cmp     ax, [rbp+0]
0x180007a33  jz      short loc_180007A77
0x180007a35  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180007a3c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007a41  mov     rcx, rdi; this
0x180007a44  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007a49  mov     ebx, eax
0x180007a4b  test    eax, eax
0x180007a4d  js      short loc_180007A77
0x180007a4f  xor     ebx, ebx
0x180007a51  movsxd  rsi, ebx
0x180007a54  lea     rcx, [rsp+2088h+String1]; lpString1
0x180007a59  add     rsi, rsi
0x180007a5c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180007a61  call    cs:__imp_lstrcmpiW
0x180007a67  test    eax, eax
0x180007a69  jz      short loc_180007AA4
0x180007a6b  inc     ebx
0x180007a6d  cmp     ebx, 0Eh
0x180007a70  jb      short loc_180007A51
0x180007a72  mov     ebx, 80020009h
0x180007a77  mov     rcx, rbp; pv
0x180007a7a  call    cs:__imp_CoTaskMemFree
0x180007a80  mov     eax, ebx
0x180007a82  mov     rcx, [rsp+2088h+var_48]
0x180007a8a  xor     rcx, rsp; StackCookie
0x180007a8d  call    __security_check_cookie
0x180007a92  add     rsp, 2050h
0x180007a99  pop     r15
0x180007a9b  pop     r14
0x180007a9d  pop     r13
0x180007a9f  pop     rdi
0x180007aa0  pop     rsi
0x180007aa1  pop     rbp
0x180007aa2  pop     rbx
0x180007aa3  retn
0x180007aa4  mov     rsi, [r13+rsi*8+8]
0x180007aa9  test    rsi, rsi
0x180007aac  jz      short loc_180007A72
0x180007aae  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007ab3  mov     rcx, rdi; this
0x180007ab6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007abb  mov     ebx, eax
0x180007abd  test    eax, eax
0x180007abf  js      short loc_180007A77
0x180007ac1  mov     eax, 7Bh ; '{'
0x180007ac6  cmp     ax, [rsp+2088h+String1]
0x180007acb  jnz     short loc_180007A72
0x180007acd  mov     [rsp+2088h+var_2068], 0; int
0x180007ad5  mov     r8, rsi; HKEY
0x180007ad8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007add  mov     rcx, rdi; this
0x180007ae0  test    r15d, r15d
0x180007ae3  jz      short loc_180007B19
0x180007ae5  mov     r14, [rdi]
0x180007ae8  mov     r9d, r15d; int
0x180007aeb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007af0  mov     ebx, eax
0x180007af2  test    eax, eax
0x180007af4  jns     short loc_180007B2B
0x180007af6  xor     r9d, r9d; int
0x180007af9  mov     [rdi], r14
0x180007afc  mov     r8, rsi; HKEY
0x180007aff  mov     [rsp+2088h+var_2068], 0; int
0x180007b07  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007b0c  mov     rcx, rdi; this
0x180007b0f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007b14  jmp     loc_180007A77
0x180007b19  xor     r9d, r9d; int
0x180007b1c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007b21  mov     ebx, eax
0x180007b23  test    eax, eax
0x180007b25  js      loc_180007A77
0x180007b2b  mov     rcx, rdi; this
0x180007b2e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180007b33  mov     rcx, [rdi]
0x180007b36  xor     eax, eax
0x180007b38  cmp     ax, [rcx]
0x180007b3b  jnz     loc_180007A3C
0x180007b41  jmp     loc_180007A77
```
