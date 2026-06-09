# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180008a7c`
- end: `0x180008c06`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180008c0c`

## callees

- `0x180007038`
- `0x180007310`
- `0x180008a7c`
- `0x180008dd0`
- `0x180018500`
- `0x180018590`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180008b01`
- `KERNEL32!lstrcmpiW` at `0x180008b01`
- `USER32!CharNextW` at `0x180008beb`
- `USER32!CharNextW` at `0x180008beb`
- `ole32!CoTaskMemFree` at `0x180008b1a`
- `ole32!CoTaskMemFree` at `0x180008b1a`

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
0x180008a7c  push    rbx
0x180008a7e  push    rbp
0x180008a7f  push    rsi
0x180008a80  push    rdi
0x180008a81  push    r13
0x180008a83  push    r14
0x180008a85  push    r15
0x180008a87  mov     eax, 2050h
0x180008a8c  call    _alloca_probe
0x180008a91  sub     rsp, rax
0x180008a94  mov     rax, cs:__security_cookie
0x180008a9b  xor     rax, rsp
0x180008a9e  mov     [rsp+2088h+var_48], rax
0x180008aa6  mov     r15d, r8d
0x180008aa9  mov     [rsp+2088h+pv], 0
0x180008ab2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180008ab7  mov     rdi, rcx
0x180008aba  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180008abf  mov     ebx, eax
0x180008ac1  test    eax, eax
0x180008ac3  js      short loc_180008B22
0x180008ac5  mov     rbp, [rsp+2088h+pv]
0x180008aca  xor     eax, eax
0x180008acc  mov     [rdi], rbp
0x180008acf  cmp     ax, [rbp+0]
0x180008ad3  jz      short loc_180008B17
0x180008ad5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180008adc  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008ae1  mov     rcx, rdi; this
0x180008ae4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008ae9  mov     ebx, eax
0x180008aeb  test    eax, eax
0x180008aed  js      short loc_180008B17
0x180008aef  xor     ebx, ebx
0x180008af1  movsxd  rsi, ebx
0x180008af4  lea     rcx, [rsp+2088h+String1]; lpString1
0x180008af9  add     rsi, rsi
0x180008afc  mov     rdx, [r13+rsi*8+0]; lpString2
0x180008b01  call    cs:__imp_lstrcmpiW
0x180008b07  test    eax, eax
0x180008b09  jz      short loc_180008B44
0x180008b0b  inc     ebx
0x180008b0d  cmp     ebx, 0Eh
0x180008b10  jb      short loc_180008AF1
0x180008b12  mov     ebx, 80020009h
0x180008b17  mov     rcx, rbp; pv
0x180008b1a  call    cs:__imp_CoTaskMemFree
0x180008b20  mov     eax, ebx
0x180008b22  mov     rcx, [rsp+2088h+var_48]
0x180008b2a  xor     rcx, rsp; StackCookie
0x180008b2d  call    __security_check_cookie
0x180008b32  add     rsp, 2050h
0x180008b39  pop     r15
0x180008b3b  pop     r14
0x180008b3d  pop     r13
0x180008b3f  pop     rdi
0x180008b40  pop     rsi
0x180008b41  pop     rbp
0x180008b42  pop     rbx
0x180008b43  retn
0x180008b44  mov     rsi, [r13+rsi*8+8]
0x180008b49  test    rsi, rsi
0x180008b4c  jz      short loc_180008B12
0x180008b4e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008b53  mov     rcx, rdi; this
0x180008b56  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008b5b  mov     ebx, eax
0x180008b5d  test    eax, eax
0x180008b5f  js      short loc_180008B17
0x180008b61  mov     eax, 7Bh ; '{'
0x180008b66  cmp     ax, [rsp+2088h+String1]
0x180008b6b  jnz     short loc_180008B12
0x180008b6d  mov     [rsp+2088h+var_2068], 0; int
0x180008b75  mov     r8, rsi; HKEY
0x180008b78  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008b7d  mov     rcx, rdi; this
0x180008b80  test    r15d, r15d
0x180008b83  jz      short loc_180008BB9
0x180008b85  mov     r14, [rdi]
0x180008b88  mov     r9d, r15d; int
0x180008b8b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008b90  mov     ebx, eax
0x180008b92  test    eax, eax
0x180008b94  jns     short loc_180008BCB
0x180008b96  xor     r9d, r9d; int
0x180008b99  mov     [rdi], r14
0x180008b9c  mov     r8, rsi; HKEY
0x180008b9f  mov     [rsp+2088h+var_2068], 0; int
0x180008ba7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008bac  mov     rcx, rdi; this
0x180008baf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008bb4  jmp     loc_180008B17
0x180008bb9  xor     r9d, r9d; int
0x180008bbc  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008bc1  mov     ebx, eax
0x180008bc3  test    eax, eax
0x180008bc5  js      loc_180008B17
0x180008bcb  mov     r8, [rdi]
0x180008bce  movzx   edx, word ptr [r8]
0x180008bd2  mov     ecx, edx
0x180008bd4  sub     ecx, 9
0x180008bd7  jz      short loc_180008BE8
0x180008bd9  sub     ecx, 1
0x180008bdc  jz      short loc_180008BE8
0x180008bde  sub     ecx, 3
0x180008be1  jz      short loc_180008BE8
0x180008be3  cmp     ecx, 13h
0x180008be6  jnz     short loc_180008BF6
0x180008be8  mov     rcx, r8; lpsz
0x180008beb  call    cs:__imp_CharNextW
0x180008bf1  mov     [rdi], rax
0x180008bf4  jmp     short loc_180008BCB
0x180008bf6  xor     eax, eax
0x180008bf8  cmp     ax, dx
0x180008bfb  jnz     loc_180008ADC
0x180008c01  jmp     loc_180008B17
```
