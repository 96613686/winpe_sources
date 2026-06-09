# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x14000d578`
- end: `0x14000d702`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d708`

## callees

- `0x140001fa0`
- `0x14000cf98`
- `0x14000d138`
- `0x14000d578`
- `0x14000d8cc`
- `0x14000f6e0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x14000d5fd`
- `KERNEL32!lstrcmpiW` at `0x14000d5fd`
- `USER32!CharNextW` at `0x14000d6e7`
- `USER32!CharNextW` at `0x14000d6e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d616`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d616`

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
0x14000d578  push    rbx
0x14000d57a  push    rbp
0x14000d57b  push    rsi
0x14000d57c  push    rdi
0x14000d57d  push    r13
0x14000d57f  push    r14
0x14000d581  push    r15
0x14000d583  mov     eax, 2050h
0x14000d588  call    _alloca_probe
0x14000d58d  sub     rsp, rax
0x14000d590  mov     rax, cs:__security_cookie
0x14000d597  xor     rax, rsp
0x14000d59a  mov     [rsp+2088h+var_48], rax
0x14000d5a2  mov     r15d, r8d
0x14000d5a5  mov     [rsp+2088h+pv], 0
0x14000d5ae  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x14000d5b3  mov     rdi, rcx
0x14000d5b6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x14000d5bb  mov     ebx, eax
0x14000d5bd  test    eax, eax
0x14000d5bf  js      short loc_14000D61E
0x14000d5c1  mov     rbp, [rsp+2088h+pv]
0x14000d5c6  xor     eax, eax
0x14000d5c8  mov     [rdi], rbp
0x14000d5cb  cmp     ax, [rbp+0]
0x14000d5cf  jz      short loc_14000D613
0x14000d5d1  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x14000d5d8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14000d5dd  mov     rcx, rdi; this
0x14000d5e0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000d5e5  mov     ebx, eax
0x14000d5e7  test    eax, eax
0x14000d5e9  js      short loc_14000D613
0x14000d5eb  xor     ebx, ebx
0x14000d5ed  movsxd  rsi, ebx
0x14000d5f0  lea     rcx, [rsp+2088h+String1]; lpString1
0x14000d5f5  add     rsi, rsi
0x14000d5f8  mov     rdx, [r13+rsi*8+0]; lpString2
0x14000d5fd  call    cs:__imp_lstrcmpiW
0x14000d603  test    eax, eax
0x14000d605  jz      short loc_14000D640
0x14000d607  inc     ebx
0x14000d609  cmp     ebx, 0Eh
0x14000d60c  jb      short loc_14000D5ED
0x14000d60e  mov     ebx, 80020009h
0x14000d613  mov     rcx, rbp; pv
0x14000d616  call    cs:__imp_CoTaskMemFree
0x14000d61c  mov     eax, ebx
0x14000d61e  mov     rcx, [rsp+2088h+var_48]
0x14000d626  xor     rcx, rsp; StackCookie
0x14000d629  call    __security_check_cookie
0x14000d62e  add     rsp, 2050h
0x14000d635  pop     r15
0x14000d637  pop     r14
0x14000d639  pop     r13
0x14000d63b  pop     rdi
0x14000d63c  pop     rsi
0x14000d63d  pop     rbp
0x14000d63e  pop     rbx
0x14000d63f  retn
0x14000d640  mov     rsi, [r13+rsi*8+8]
0x14000d645  test    rsi, rsi
0x14000d648  jz      short loc_14000D60E
0x14000d64a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14000d64f  mov     rcx, rdi; this
0x14000d652  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000d657  mov     ebx, eax
0x14000d659  test    eax, eax
0x14000d65b  js      short loc_14000D613
0x14000d65d  mov     eax, 7Bh ; '{'
0x14000d662  cmp     ax, [rsp+2088h+String1]
0x14000d667  jnz     short loc_14000D60E
0x14000d669  mov     [rsp+2088h+var_2068], 0; int
0x14000d671  mov     r8, rsi; HKEY
0x14000d674  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14000d679  mov     rcx, rdi; this
0x14000d67c  test    r15d, r15d
0x14000d67f  jz      short loc_14000D6B5
0x14000d681  mov     r14, [rdi]
0x14000d684  mov     r9d, r15d; int
0x14000d687  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000d68c  mov     ebx, eax
0x14000d68e  test    eax, eax
0x14000d690  jns     short loc_14000D6C7
0x14000d692  xor     r9d, r9d; int
0x14000d695  mov     [rdi], r14
0x14000d698  mov     r8, rsi; HKEY
0x14000d69b  mov     [rsp+2088h+var_2068], 0; int
0x14000d6a3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14000d6a8  mov     rcx, rdi; this
0x14000d6ab  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000d6b0  jmp     loc_14000D613
0x14000d6b5  xor     r9d, r9d; int
0x14000d6b8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000d6bd  mov     ebx, eax
0x14000d6bf  test    eax, eax
0x14000d6c1  js      loc_14000D613
0x14000d6c7  mov     r8, [rdi]
0x14000d6ca  movzx   edx, word ptr [r8]
0x14000d6ce  mov     ecx, edx
0x14000d6d0  sub     ecx, 9
0x14000d6d3  jz      short loc_14000D6E4
0x14000d6d5  sub     ecx, 1
0x14000d6d8  jz      short loc_14000D6E4
0x14000d6da  sub     ecx, 3
0x14000d6dd  jz      short loc_14000D6E4
0x14000d6df  cmp     ecx, 13h
0x14000d6e2  jnz     short loc_14000D6F2
0x14000d6e4  mov     rcx, r8; lpsz
0x14000d6e7  call    cs:__imp_CharNextW
0x14000d6ed  mov     [rdi], rax
0x14000d6f0  jmp     short loc_14000D6C7
0x14000d6f2  xor     eax, eax
0x14000d6f4  cmp     ax, dx
0x14000d6f7  jnz     loc_14000D5D8
0x14000d6fd  jmp     loc_14000D613
```
