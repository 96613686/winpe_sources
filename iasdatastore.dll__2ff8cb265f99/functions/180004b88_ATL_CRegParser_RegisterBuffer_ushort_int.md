# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180004b88`
- end: `0x180004d12`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180004d18`

## callees

- `0x1800044c0`
- `0x18000466c`
- `0x180004b88`
- `0x180004efc`
- `0x18000dd10`
- `0x18000ddd0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180004c0d`
- `KERNEL32!lstrcmpiW` at `0x180004c0d`
- `ole32!CoTaskMemFree` at `0x180004c26`
- `ole32!CoTaskMemFree` at `0x180004c26`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004cf7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004cf7`

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
0x180004b88  push    rbx
0x180004b8a  push    rbp
0x180004b8b  push    rsi
0x180004b8c  push    rdi
0x180004b8d  push    r13
0x180004b8f  push    r14
0x180004b91  push    r15
0x180004b93  mov     eax, 2050h
0x180004b98  call    _alloca_probe
0x180004b9d  sub     rsp, rax
0x180004ba0  mov     rax, cs:__security_cookie
0x180004ba7  xor     rax, rsp
0x180004baa  mov     [rsp+2088h+var_48], rax
0x180004bb2  mov     r15d, r8d
0x180004bb5  mov     [rsp+2088h+pv], 0
0x180004bbe  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180004bc3  mov     rdi, rcx
0x180004bc6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180004bcb  mov     ebx, eax
0x180004bcd  test    eax, eax
0x180004bcf  js      short loc_180004C2E
0x180004bd1  mov     rbp, [rsp+2088h+pv]
0x180004bd6  xor     eax, eax
0x180004bd8  mov     [rdi], rbp
0x180004bdb  cmp     ax, [rbp+0]
0x180004bdf  jz      short loc_180004C23
0x180004be1  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180004be8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004bed  mov     rcx, rdi; this
0x180004bf0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004bf5  mov     ebx, eax
0x180004bf7  test    eax, eax
0x180004bf9  js      short loc_180004C23
0x180004bfb  xor     ebx, ebx
0x180004bfd  movsxd  rsi, ebx
0x180004c00  lea     rcx, [rsp+2088h+String1]; lpString1
0x180004c05  add     rsi, rsi
0x180004c08  mov     rdx, [r13+rsi*8+0]; lpString2
0x180004c0d  call    cs:__imp_lstrcmpiW
0x180004c13  test    eax, eax
0x180004c15  jz      short loc_180004C50
0x180004c17  inc     ebx
0x180004c19  cmp     ebx, 0Eh
0x180004c1c  jb      short loc_180004BFD
0x180004c1e  mov     ebx, 80020009h
0x180004c23  mov     rcx, rbp; pv
0x180004c26  call    cs:__imp_CoTaskMemFree
0x180004c2c  mov     eax, ebx
0x180004c2e  mov     rcx, [rsp+2088h+var_48]
0x180004c36  xor     rcx, rsp; StackCookie
0x180004c39  call    __security_check_cookie
0x180004c3e  add     rsp, 2050h
0x180004c45  pop     r15
0x180004c47  pop     r14
0x180004c49  pop     r13
0x180004c4b  pop     rdi
0x180004c4c  pop     rsi
0x180004c4d  pop     rbp
0x180004c4e  pop     rbx
0x180004c4f  retn
0x180004c50  mov     rsi, [r13+rsi*8+8]
0x180004c55  test    rsi, rsi
0x180004c58  jz      short loc_180004C1E
0x180004c5a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004c5f  mov     rcx, rdi; this
0x180004c62  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004c67  mov     ebx, eax
0x180004c69  test    eax, eax
0x180004c6b  js      short loc_180004C23
0x180004c6d  mov     eax, 7Bh ; '{'
0x180004c72  cmp     ax, [rsp+2088h+String1]
0x180004c77  jnz     short loc_180004C1E
0x180004c79  mov     [rsp+2088h+var_2068], 0; int
0x180004c81  mov     r8, rsi; HKEY
0x180004c84  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004c89  mov     rcx, rdi; this
0x180004c8c  test    r15d, r15d
0x180004c8f  jz      short loc_180004CC5
0x180004c91  mov     r14, [rdi]
0x180004c94  mov     r9d, r15d; int
0x180004c97  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004c9c  mov     ebx, eax
0x180004c9e  test    eax, eax
0x180004ca0  jns     short loc_180004CD7
0x180004ca2  xor     r9d, r9d; int
0x180004ca5  mov     [rdi], r14
0x180004ca8  mov     r8, rsi; HKEY
0x180004cab  mov     [rsp+2088h+var_2068], 0; int
0x180004cb3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004cb8  mov     rcx, rdi; this
0x180004cbb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004cc0  jmp     loc_180004C23
0x180004cc5  xor     r9d, r9d; int
0x180004cc8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004ccd  mov     ebx, eax
0x180004ccf  test    eax, eax
0x180004cd1  js      loc_180004C23
0x180004cd7  mov     r8, [rdi]
0x180004cda  movzx   edx, word ptr [r8]
0x180004cde  mov     ecx, edx
0x180004ce0  sub     ecx, 9
0x180004ce3  jz      short loc_180004CF4
0x180004ce5  sub     ecx, 1
0x180004ce8  jz      short loc_180004CF4
0x180004cea  sub     ecx, 3
0x180004ced  jz      short loc_180004CF4
0x180004cef  cmp     ecx, 13h
0x180004cf2  jnz     short loc_180004D02
0x180004cf4  mov     rcx, r8; lpsz
0x180004cf7  call    cs:__imp_CharNextW
0x180004cfd  mov     [rdi], rax
0x180004d00  jmp     short loc_180004CD7
0x180004d02  xor     eax, eax
0x180004d04  cmp     ax, dx
0x180004d07  jnz     loc_180004BE8
0x180004d0d  jmp     loc_180004C23
```
