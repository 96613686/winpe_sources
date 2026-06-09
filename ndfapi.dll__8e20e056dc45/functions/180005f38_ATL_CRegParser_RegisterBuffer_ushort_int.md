# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180005f38`
- end: `0x1800060c2`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800060c8`

## callees

- `0x180005944`
- `0x180005ae4`
- `0x180005f38`
- `0x1800062ac`
- `0x18001f690`
- `0x18001f750`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180005fbd`
- `KERNEL32!lstrcmpiW` at `0x180005fbd`
- `USER32!CharNextW` at `0x1800060a7`
- `USER32!CharNextW` at `0x1800060a7`
- `ole32!CoTaskMemFree` at `0x180005fd6`
- `ole32!CoTaskMemFree` at `0x180005fd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180005f38  push    rbx
0x180005f3a  push    rbp
0x180005f3b  push    rsi
0x180005f3c  push    rdi
0x180005f3d  push    r13
0x180005f3f  push    r14
0x180005f41  push    r15
0x180005f43  mov     eax, 2050h
0x180005f48  call    _alloca_probe
0x180005f4d  sub     rsp, rax
0x180005f50  mov     rax, cs:__security_cookie
0x180005f57  xor     rax, rsp
0x180005f5a  mov     [rsp+2088h+var_48], rax
0x180005f62  mov     r15d, r8d
0x180005f65  mov     [rsp+2088h+pv], 0
0x180005f6e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180005f73  mov     rdi, rcx
0x180005f76  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180005f7b  mov     ebx, eax
0x180005f7d  test    eax, eax
0x180005f7f  js      short loc_180005FDE
0x180005f81  mov     rbp, [rsp+2088h+pv]
0x180005f86  xor     eax, eax
0x180005f88  mov     [rdi], rbp
0x180005f8b  cmp     ax, [rbp+0]
0x180005f8f  jz      short loc_180005FD3
0x180005f91  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180005f98  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005f9d  mov     rcx, rdi; this
0x180005fa0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005fa5  mov     ebx, eax
0x180005fa7  test    eax, eax
0x180005fa9  js      short loc_180005FD3
0x180005fab  xor     ebx, ebx
0x180005fad  movsxd  rsi, ebx
0x180005fb0  lea     rcx, [rsp+2088h+String1]; lpString1
0x180005fb5  add     rsi, rsi
0x180005fb8  mov     rdx, [r13+rsi*8+0]; lpString2
0x180005fbd  call    cs:__imp_lstrcmpiW
0x180005fc3  test    eax, eax
0x180005fc5  jz      short loc_180006000
0x180005fc7  inc     ebx
0x180005fc9  cmp     ebx, 0Eh
0x180005fcc  jb      short loc_180005FAD
0x180005fce  mov     ebx, 80020009h
0x180005fd3  mov     rcx, rbp; pv
0x180005fd6  call    cs:__imp_CoTaskMemFree
0x180005fdc  mov     eax, ebx
0x180005fde  mov     rcx, [rsp+2088h+var_48]
0x180005fe6  xor     rcx, rsp; StackCookie
0x180005fe9  call    __security_check_cookie
0x180005fee  add     rsp, 2050h
0x180005ff5  pop     r15
0x180005ff7  pop     r14
0x180005ff9  pop     r13
0x180005ffb  pop     rdi
0x180005ffc  pop     rsi
0x180005ffd  pop     rbp
0x180005ffe  pop     rbx
0x180005fff  retn
0x180006000  mov     rsi, [r13+rsi*8+8]
0x180006005  test    rsi, rsi
0x180006008  jz      short loc_180005FCE
0x18000600a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000600f  mov     rcx, rdi; this
0x180006012  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006017  mov     ebx, eax
0x180006019  test    eax, eax
0x18000601b  js      short loc_180005FD3
0x18000601d  mov     eax, 7Bh ; '{'
0x180006022  cmp     ax, [rsp+2088h+String1]
0x180006027  jnz     short loc_180005FCE
0x180006029  mov     [rsp+2088h+var_2068], 0; int
0x180006031  mov     r8, rsi; HKEY
0x180006034  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180006039  mov     rcx, rdi; this
0x18000603c  test    r15d, r15d
0x18000603f  jz      short loc_180006075
0x180006041  mov     r14, [rdi]
0x180006044  mov     r9d, r15d; int
0x180006047  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000604c  mov     ebx, eax
0x18000604e  test    eax, eax
0x180006050  jns     short loc_180006087
0x180006052  xor     r9d, r9d; int
0x180006055  mov     [rdi], r14
0x180006058  mov     r8, rsi; HKEY
0x18000605b  mov     [rsp+2088h+var_2068], 0; int
0x180006063  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180006068  mov     rcx, rdi; this
0x18000606b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180006070  jmp     loc_180005FD3
0x180006075  xor     r9d, r9d; int
0x180006078  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000607d  mov     ebx, eax
0x18000607f  test    eax, eax
0x180006081  js      loc_180005FD3
0x180006087  mov     r8, [rdi]
0x18000608a  movzx   edx, word ptr [r8]
0x18000608e  mov     ecx, edx
0x180006090  sub     ecx, 9
0x180006093  jz      short loc_1800060A4
0x180006095  sub     ecx, 1
0x180006098  jz      short loc_1800060A4
0x18000609a  sub     ecx, 3
0x18000609d  jz      short loc_1800060A4
0x18000609f  cmp     ecx, 13h
0x1800060a2  jnz     short loc_1800060B2
0x1800060a4  mov     rcx, r8; lpsz
0x1800060a7  call    cs:__imp_CharNextW
0x1800060ad  mov     [rdi], rax
0x1800060b0  jmp     short loc_180006087
0x1800060b2  xor     eax, eax
0x1800060b4  cmp     ax, dx
0x1800060b7  jnz     loc_180005F98
0x1800060bd  jmp     loc_180005FD3
```
