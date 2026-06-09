# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180008d5c`
- end: `0x180008ef9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `413`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008f00`

## callees

- `0x180008514`
- `0x1800086fc`
- `0x180008d5c`
- `0x180009108`
- `0x1800136b0`
- `0x180013770`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180008de1`
- `KERNEL32!lstrcmpiW` at `0x180008de1`
- `USER32!CharNextW` at `0x180008ed8`
- `USER32!CharNextW` at `0x180008ed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e00`

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
0x180008d5c  push    rbx
0x180008d5e  push    rbp
0x180008d5f  push    rsi
0x180008d60  push    rdi
0x180008d61  push    r13
0x180008d63  push    r14
0x180008d65  push    r15
0x180008d67  mov     eax, 2050h
0x180008d6c  call    _alloca_probe
0x180008d71  sub     rsp, rax
0x180008d74  mov     rax, cs:__security_cookie
0x180008d7b  xor     rax, rsp
0x180008d7e  mov     [rsp+2088h+var_48], rax
0x180008d86  mov     r15d, r8d
0x180008d89  mov     [rsp+2088h+pv], 0
0x180008d92  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180008d97  mov     rdi, rcx
0x180008d9a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180008d9f  mov     ebx, eax
0x180008da1  test    eax, eax
0x180008da3  js      short loc_180008E0E
0x180008da5  mov     rbp, [rsp+2088h+pv]
0x180008daa  xor     eax, eax
0x180008dac  mov     [rdi], rbp
0x180008daf  cmp     ax, [rbp+0]
0x180008db3  jz      short loc_180008DFD
0x180008db5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180008dbc  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008dc1  mov     rcx, rdi; this
0x180008dc4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008dc9  mov     ebx, eax
0x180008dcb  test    eax, eax
0x180008dcd  js      short loc_180008DFD
0x180008dcf  xor     ebx, ebx
0x180008dd1  movsxd  rsi, ebx
0x180008dd4  lea     rcx, [rsp+2088h+String1]; lpString1
0x180008dd9  add     rsi, rsi
0x180008ddc  mov     rdx, [r13+rsi*8+0]; lpString2
0x180008de1  call    cs:__imp_lstrcmpiW
0x180008de8  nop     dword ptr [rax+rax+00h]
0x180008ded  test    eax, eax
0x180008def  jz      short loc_180008E31
0x180008df1  inc     ebx
0x180008df3  cmp     ebx, 0Eh
0x180008df6  jb      short loc_180008DD1
0x180008df8  mov     ebx, 80020009h
0x180008dfd  mov     rcx, rbp; pv
0x180008e00  call    cs:__imp_CoTaskMemFree
0x180008e07  nop     dword ptr [rax+rax+00h]
0x180008e0c  mov     eax, ebx
0x180008e0e  mov     rcx, [rsp+2088h+var_48]
0x180008e16  xor     rcx, rsp; StackCookie
0x180008e19  call    __security_check_cookie
0x180008e1e  add     rsp, 2050h
0x180008e25  pop     r15
0x180008e27  pop     r14
0x180008e29  pop     r13
0x180008e2b  pop     rdi
0x180008e2c  pop     rsi
0x180008e2d  pop     rbp
0x180008e2e  pop     rbx
0x180008e2f  retn
0x180008e31  mov     rsi, [r13+rsi*8+8]
0x180008e36  test    rsi, rsi
0x180008e39  jz      short loc_180008DF8
0x180008e3b  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008e40  mov     rcx, rdi; this
0x180008e43  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008e48  mov     ebx, eax
0x180008e4a  test    eax, eax
0x180008e4c  js      short loc_180008DFD
0x180008e4e  mov     eax, 7Bh ; '{'
0x180008e53  cmp     ax, [rsp+2088h+String1]
0x180008e58  jnz     short loc_180008DF8
0x180008e5a  mov     [rsp+2088h+var_2068], 0; int
0x180008e62  mov     r8, rsi; HKEY
0x180008e65  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008e6a  mov     rcx, rdi; this
0x180008e6d  test    r15d, r15d
0x180008e70  jz      short loc_180008EA6
0x180008e72  mov     r14, [rdi]
0x180008e75  mov     r9d, r15d; int
0x180008e78  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008e7d  mov     ebx, eax
0x180008e7f  test    eax, eax
0x180008e81  jns     short loc_180008EB8
0x180008e83  xor     r9d, r9d; int
0x180008e86  mov     [rdi], r14
0x180008e89  mov     r8, rsi; HKEY
0x180008e8c  mov     [rsp+2088h+var_2068], 0; int
0x180008e94  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008e99  mov     rcx, rdi; this
0x180008e9c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008ea1  jmp     loc_180008DFD
0x180008ea6  xor     r9d, r9d; int
0x180008ea9  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008eae  mov     ebx, eax
0x180008eb0  test    eax, eax
0x180008eb2  js      loc_180008DFD
0x180008eb8  mov     r8, [rdi]
0x180008ebb  movzx   edx, word ptr [r8]
0x180008ebf  mov     ecx, edx
0x180008ec1  sub     ecx, 9
0x180008ec4  jz      short loc_180008ED5
0x180008ec6  sub     ecx, 1
0x180008ec9  jz      short loc_180008ED5
0x180008ecb  sub     ecx, 3
0x180008ece  jz      short loc_180008ED5
0x180008ed0  cmp     ecx, 13h
0x180008ed3  jnz     short loc_180008EE9
0x180008ed5  mov     rcx, r8; lpsz
0x180008ed8  call    cs:__imp_CharNextW
0x180008edf  nop     dword ptr [rax+rax+00h]
0x180008ee4  mov     [rdi], rax
0x180008ee7  jmp     short loc_180008EB8
0x180008ee9  xor     eax, eax
0x180008eeb  cmp     ax, dx
0x180008eee  jnz     loc_180008DBC
0x180008ef4  jmp     loc_180008DFD
```
