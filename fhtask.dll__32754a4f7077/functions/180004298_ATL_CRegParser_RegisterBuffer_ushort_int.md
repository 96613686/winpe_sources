# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180004298`
- end: `0x180004422`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180004428`

## callees

- `0x180003b30`
- `0x180003cec`
- `0x180004298`
- `0x18000460c`
- `0x180009a00`
- `0x180009ac0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000431d`
- `KERNEL32!lstrcmpiW` at `0x18000431d`
- `USER32!CharNextW` at `0x180004407`
- `USER32!CharNextW` at `0x180004407`
- `ole32!CoTaskMemFree` at `0x180004336`
- `ole32!CoTaskMemFree` at `0x180004336`

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
0x180004298  push    rbx
0x18000429a  push    rbp
0x18000429b  push    rsi
0x18000429c  push    rdi
0x18000429d  push    r13
0x18000429f  push    r14
0x1800042a1  push    r15
0x1800042a3  mov     eax, 2050h
0x1800042a8  call    _alloca_probe
0x1800042ad  sub     rsp, rax
0x1800042b0  mov     rax, cs:__security_cookie
0x1800042b7  xor     rax, rsp
0x1800042ba  mov     [rsp+2088h+var_48], rax
0x1800042c2  mov     r15d, r8d
0x1800042c5  mov     [rsp+2088h+pv], 0
0x1800042ce  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800042d3  mov     rdi, rcx
0x1800042d6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800042db  mov     ebx, eax
0x1800042dd  test    eax, eax
0x1800042df  js      short loc_18000433E
0x1800042e1  mov     rbp, [rsp+2088h+pv]
0x1800042e6  xor     eax, eax
0x1800042e8  mov     [rdi], rbp
0x1800042eb  cmp     ax, [rbp+0]
0x1800042ef  jz      short loc_180004333
0x1800042f1  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800042f8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800042fd  mov     rcx, rdi; this
0x180004300  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004305  mov     ebx, eax
0x180004307  test    eax, eax
0x180004309  js      short loc_180004333
0x18000430b  xor     ebx, ebx
0x18000430d  movsxd  rsi, ebx
0x180004310  lea     rcx, [rsp+2088h+String1]; lpString1
0x180004315  add     rsi, rsi
0x180004318  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000431d  call    cs:__imp_lstrcmpiW
0x180004323  test    eax, eax
0x180004325  jz      short loc_180004360
0x180004327  inc     ebx
0x180004329  cmp     ebx, 0Eh
0x18000432c  jb      short loc_18000430D
0x18000432e  mov     ebx, 80020009h
0x180004333  mov     rcx, rbp; pv
0x180004336  call    cs:__imp_CoTaskMemFree
0x18000433c  mov     eax, ebx
0x18000433e  mov     rcx, [rsp+2088h+var_48]
0x180004346  xor     rcx, rsp; StackCookie
0x180004349  call    __security_check_cookie
0x18000434e  add     rsp, 2050h
0x180004355  pop     r15
0x180004357  pop     r14
0x180004359  pop     r13
0x18000435b  pop     rdi
0x18000435c  pop     rsi
0x18000435d  pop     rbp
0x18000435e  pop     rbx
0x18000435f  retn
0x180004360  mov     rsi, [r13+rsi*8+8]
0x180004365  test    rsi, rsi
0x180004368  jz      short loc_18000432E
0x18000436a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000436f  mov     rcx, rdi; this
0x180004372  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004377  mov     ebx, eax
0x180004379  test    eax, eax
0x18000437b  js      short loc_180004333
0x18000437d  mov     eax, 7Bh ; '{'
0x180004382  cmp     ax, [rsp+2088h+String1]
0x180004387  jnz     short loc_18000432E
0x180004389  mov     [rsp+2088h+var_2068], 0; int
0x180004391  mov     r8, rsi; HKEY
0x180004394  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004399  mov     rcx, rdi; this
0x18000439c  test    r15d, r15d
0x18000439f  jz      short loc_1800043D5
0x1800043a1  mov     r14, [rdi]
0x1800043a4  mov     r9d, r15d; int
0x1800043a7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800043ac  mov     ebx, eax
0x1800043ae  test    eax, eax
0x1800043b0  jns     short loc_1800043E7
0x1800043b2  xor     r9d, r9d; int
0x1800043b5  mov     [rdi], r14
0x1800043b8  mov     r8, rsi; HKEY
0x1800043bb  mov     [rsp+2088h+var_2068], 0; int
0x1800043c3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800043c8  mov     rcx, rdi; this
0x1800043cb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800043d0  jmp     loc_180004333
0x1800043d5  xor     r9d, r9d; int
0x1800043d8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800043dd  mov     ebx, eax
0x1800043df  test    eax, eax
0x1800043e1  js      loc_180004333
0x1800043e7  mov     r8, [rdi]
0x1800043ea  movzx   edx, word ptr [r8]
0x1800043ee  mov     ecx, edx
0x1800043f0  sub     ecx, 9
0x1800043f3  jz      short loc_180004404
0x1800043f5  sub     ecx, 1
0x1800043f8  jz      short loc_180004404
0x1800043fa  sub     ecx, 3
0x1800043fd  jz      short loc_180004404
0x1800043ff  cmp     ecx, 13h
0x180004402  jnz     short loc_180004412
0x180004404  mov     rcx, r8; lpsz
0x180004407  call    cs:__imp_CharNextW
0x18000440d  mov     [rdi], rax
0x180004410  jmp     short loc_1800043E7
0x180004412  xor     eax, eax
0x180004414  cmp     ax, dx
0x180004417  jnz     loc_1800042F8
0x18000441d  jmp     loc_180004333
```
