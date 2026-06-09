# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x18000ec38`
- end: `0x18000edc2`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000edc8`

## callees

- `0x1800024a0`
- `0x18000e33c`
- `0x18000e624`
- `0x18000ec38`
- `0x18000efac`
- `0x180015650`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ecd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ecd6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000eda7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000eda7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ecbd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ecbd`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, wchar_t *a2, int a3)
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
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (wchar_t **)&pv);
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
0x18000ec38  push    rbx
0x18000ec3a  push    rbp
0x18000ec3b  push    rsi
0x18000ec3c  push    rdi
0x18000ec3d  push    r13
0x18000ec3f  push    r14
0x18000ec41  push    r15
0x18000ec43  mov     eax, 2050h
0x18000ec48  call    _alloca_probe
0x18000ec4d  sub     rsp, rax
0x18000ec50  mov     rax, cs:__security_cookie
0x18000ec57  xor     rax, rsp
0x18000ec5a  mov     [rsp+2088h+var_48], rax
0x18000ec62  mov     r15d, r8d
0x18000ec65  mov     [rsp+2088h+pv], 0
0x18000ec6e  lea     r8, [rsp+2088h+pv]; wchar_t **
0x18000ec73  mov     rdi, rcx
0x18000ec76  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x18000ec7b  mov     ebx, eax
0x18000ec7d  test    eax, eax
0x18000ec7f  js      short loc_18000ECDE
0x18000ec81  mov     rbp, [rsp+2088h+pv]
0x18000ec86  xor     eax, eax
0x18000ec88  mov     [rdi], rbp
0x18000ec8b  cmp     ax, [rbp+0]
0x18000ec8f  jz      short loc_18000ECD3
0x18000ec91  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x18000ec98  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000ec9d  mov     rcx, rdi; this
0x18000eca0  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000eca5  mov     ebx, eax
0x18000eca7  test    eax, eax
0x18000eca9  js      short loc_18000ECD3
0x18000ecab  xor     ebx, ebx
0x18000ecad  movsxd  rsi, ebx
0x18000ecb0  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000ecb5  add     rsi, rsi
0x18000ecb8  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000ecbd  call    cs:__imp_lstrcmpiW
0x18000ecc3  test    eax, eax
0x18000ecc5  jz      short loc_18000ED00
0x18000ecc7  inc     ebx
0x18000ecc9  cmp     ebx, 0Eh
0x18000eccc  jb      short loc_18000ECAD
0x18000ecce  mov     ebx, 80020009h
0x18000ecd3  mov     rcx, rbp; pv
0x18000ecd6  call    cs:__imp_CoTaskMemFree
0x18000ecdc  mov     eax, ebx
0x18000ecde  mov     rcx, [rsp+2088h+var_48]
0x18000ece6  xor     rcx, rsp; StackCookie
0x18000ece9  call    __security_check_cookie
0x18000ecee  add     rsp, 2050h
0x18000ecf5  pop     r15
0x18000ecf7  pop     r14
0x18000ecf9  pop     r13
0x18000ecfb  pop     rdi
0x18000ecfc  pop     rsi
0x18000ecfd  pop     rbp
0x18000ecfe  pop     rbx
0x18000ecff  retn
0x18000ed00  mov     rsi, [r13+rsi*8+8]
0x18000ed05  test    rsi, rsi
0x18000ed08  jz      short loc_18000ECCE
0x18000ed0a  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000ed0f  mov     rcx, rdi; this
0x18000ed12  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000ed17  mov     ebx, eax
0x18000ed19  test    eax, eax
0x18000ed1b  js      short loc_18000ECD3
0x18000ed1d  mov     eax, 7Bh ; '{'
0x18000ed22  cmp     ax, [rsp+2088h+String1]
0x18000ed27  jnz     short loc_18000ECCE
0x18000ed29  mov     [rsp+2088h+var_2068], 0; int
0x18000ed31  mov     r8, rsi; HKEY
0x18000ed34  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000ed39  mov     rcx, rdi; this
0x18000ed3c  test    r15d, r15d
0x18000ed3f  jz      short loc_18000ED75
0x18000ed41  mov     r14, [rdi]
0x18000ed44  mov     r9d, r15d; int
0x18000ed47  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000ed4c  mov     ebx, eax
0x18000ed4e  test    eax, eax
0x18000ed50  jns     short loc_18000ED87
0x18000ed52  xor     r9d, r9d; int
0x18000ed55  mov     [rdi], r14
0x18000ed58  mov     r8, rsi; HKEY
0x18000ed5b  mov     [rsp+2088h+var_2068], 0; int
0x18000ed63  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000ed68  mov     rcx, rdi; this
0x18000ed6b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000ed70  jmp     loc_18000ECD3
0x18000ed75  xor     r9d, r9d; int
0x18000ed78  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000ed7d  mov     ebx, eax
0x18000ed7f  test    eax, eax
0x18000ed81  js      loc_18000ECD3
0x18000ed87  mov     r8, [rdi]
0x18000ed8a  movzx   edx, word ptr [r8]
0x18000ed8e  mov     ecx, edx
0x18000ed90  sub     ecx, 9
0x18000ed93  jz      short loc_18000EDA4
0x18000ed95  sub     ecx, 1
0x18000ed98  jz      short loc_18000EDA4
0x18000ed9a  sub     ecx, 3
0x18000ed9d  jz      short loc_18000EDA4
0x18000ed9f  cmp     ecx, 13h
0x18000eda2  jnz     short loc_18000EDB2
0x18000eda4  mov     rcx, r8; lpsz
0x18000eda7  call    cs:__imp_CharNextW
0x18000edad  mov     [rdi], rax
0x18000edb0  jmp     short loc_18000ED87
0x18000edb2  xor     eax, eax
0x18000edb4  cmp     ax, dx
0x18000edb7  jnz     loc_18000EC98
0x18000edbd  jmp     loc_18000ECD3
```
