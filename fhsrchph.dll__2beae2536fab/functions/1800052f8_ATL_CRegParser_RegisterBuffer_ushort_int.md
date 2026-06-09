# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800052f8`
- end: `0x180005482`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005488`

## callees

- `0x180004ba0`
- `0x180004d4c`
- `0x1800052f8`
- `0x18000566c`
- `0x18000ab60`
- `0x18000ac20`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000537d`
- `KERNEL32!lstrcmpiW` at `0x18000537d`
- `USER32!CharNextW` at `0x180005467`
- `USER32!CharNextW` at `0x180005467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005396`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005396`

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
0x1800052f8  push    rbx
0x1800052fa  push    rbp
0x1800052fb  push    rsi
0x1800052fc  push    rdi
0x1800052fd  push    r13
0x1800052ff  push    r14
0x180005301  push    r15
0x180005303  mov     eax, 2050h
0x180005308  call    _alloca_probe
0x18000530d  sub     rsp, rax
0x180005310  mov     rax, cs:__security_cookie
0x180005317  xor     rax, rsp
0x18000531a  mov     [rsp+2088h+var_48], rax
0x180005322  mov     r15d, r8d
0x180005325  mov     [rsp+2088h+pv], 0
0x18000532e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180005333  mov     rdi, rcx
0x180005336  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000533b  mov     ebx, eax
0x18000533d  test    eax, eax
0x18000533f  js      short loc_18000539E
0x180005341  mov     rbp, [rsp+2088h+pv]
0x180005346  xor     eax, eax
0x180005348  mov     [rdi], rbp
0x18000534b  cmp     ax, [rbp+0]
0x18000534f  jz      short loc_180005393
0x180005351  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180005358  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000535d  mov     rcx, rdi; this
0x180005360  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005365  mov     ebx, eax
0x180005367  test    eax, eax
0x180005369  js      short loc_180005393
0x18000536b  xor     ebx, ebx
0x18000536d  movsxd  rsi, ebx
0x180005370  lea     rcx, [rsp+2088h+String1]; lpString1
0x180005375  add     rsi, rsi
0x180005378  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000537d  call    cs:__imp_lstrcmpiW
0x180005383  test    eax, eax
0x180005385  jz      short loc_1800053C0
0x180005387  inc     ebx
0x180005389  cmp     ebx, 0Eh
0x18000538c  jb      short loc_18000536D
0x18000538e  mov     ebx, 80020009h
0x180005393  mov     rcx, rbp; pv
0x180005396  call    cs:__imp_CoTaskMemFree
0x18000539c  mov     eax, ebx
0x18000539e  mov     rcx, [rsp+2088h+var_48]
0x1800053a6  xor     rcx, rsp; StackCookie
0x1800053a9  call    __security_check_cookie
0x1800053ae  add     rsp, 2050h
0x1800053b5  pop     r15
0x1800053b7  pop     r14
0x1800053b9  pop     r13
0x1800053bb  pop     rdi
0x1800053bc  pop     rsi
0x1800053bd  pop     rbp
0x1800053be  pop     rbx
0x1800053bf  retn
0x1800053c0  mov     rsi, [r13+rsi*8+8]
0x1800053c5  test    rsi, rsi
0x1800053c8  jz      short loc_18000538E
0x1800053ca  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800053cf  mov     rcx, rdi; this
0x1800053d2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800053d7  mov     ebx, eax
0x1800053d9  test    eax, eax
0x1800053db  js      short loc_180005393
0x1800053dd  mov     eax, 7Bh ; '{'
0x1800053e2  cmp     ax, [rsp+2088h+String1]
0x1800053e7  jnz     short loc_18000538E
0x1800053e9  mov     [rsp+2088h+var_2068], 0; int
0x1800053f1  mov     r8, rsi; HKEY
0x1800053f4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800053f9  mov     rcx, rdi; this
0x1800053fc  test    r15d, r15d
0x1800053ff  jz      short loc_180005435
0x180005401  mov     r14, [rdi]
0x180005404  mov     r9d, r15d; int
0x180005407  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000540c  mov     ebx, eax
0x18000540e  test    eax, eax
0x180005410  jns     short loc_180005447
0x180005412  xor     r9d, r9d; int
0x180005415  mov     [rdi], r14
0x180005418  mov     r8, rsi; HKEY
0x18000541b  mov     [rsp+2088h+var_2068], 0; int
0x180005423  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005428  mov     rcx, rdi; this
0x18000542b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005430  jmp     loc_180005393
0x180005435  xor     r9d, r9d; int
0x180005438  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000543d  mov     ebx, eax
0x18000543f  test    eax, eax
0x180005441  js      loc_180005393
0x180005447  mov     r8, [rdi]
0x18000544a  movzx   edx, word ptr [r8]
0x18000544e  mov     ecx, edx
0x180005450  sub     ecx, 9
0x180005453  jz      short loc_180005464
0x180005455  sub     ecx, 1
0x180005458  jz      short loc_180005464
0x18000545a  sub     ecx, 3
0x18000545d  jz      short loc_180005464
0x18000545f  cmp     ecx, 13h
0x180005462  jnz     short loc_180005472
0x180005464  mov     rcx, r8; lpsz
0x180005467  call    cs:__imp_CharNextW
0x18000546d  mov     [rdi], rax
0x180005470  jmp     short loc_180005447
0x180005472  xor     eax, eax
0x180005474  cmp     ax, dx
0x180005477  jnz     loc_180005358
0x18000547d  jmp     loc_180005393
```
