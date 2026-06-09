# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180010f18`
- end: `0x1800110a2`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800110a8`

## callees

- `0x1800107e0`
- `0x18001098c`
- `0x180010f18`
- `0x180011384`
- `0x1800181e0`
- `0x1800182a0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180010f9d`
- `KERNEL32!lstrcmpiW` at `0x180010f9d`
- `USER32!CharNextW` at `0x180011087`
- `USER32!CharNextW` at `0x180011087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010fb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010fb6`

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
0x180010f18  push    rbx
0x180010f1a  push    rbp
0x180010f1b  push    rsi
0x180010f1c  push    rdi
0x180010f1d  push    r13
0x180010f1f  push    r14
0x180010f21  push    r15
0x180010f23  mov     eax, 2050h
0x180010f28  call    _alloca_probe
0x180010f2d  sub     rsp, rax
0x180010f30  mov     rax, cs:__security_cookie
0x180010f37  xor     rax, rsp
0x180010f3a  mov     [rsp+2088h+var_48], rax
0x180010f42  mov     r15d, r8d
0x180010f45  mov     [rsp+2088h+pv], 0
0x180010f4e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180010f53  mov     rdi, rcx
0x180010f56  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180010f5b  mov     ebx, eax
0x180010f5d  test    eax, eax
0x180010f5f  js      short loc_180010FBE
0x180010f61  mov     rbp, [rsp+2088h+pv]
0x180010f66  xor     eax, eax
0x180010f68  mov     [rdi], rbp
0x180010f6b  cmp     ax, [rbp+0]
0x180010f6f  jz      short loc_180010FB3
0x180010f71  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180010f78  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180010f7d  mov     rcx, rdi; this
0x180010f80  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010f85  mov     ebx, eax
0x180010f87  test    eax, eax
0x180010f89  js      short loc_180010FB3
0x180010f8b  xor     ebx, ebx
0x180010f8d  movsxd  rsi, ebx
0x180010f90  lea     rcx, [rsp+2088h+String1]; lpString1
0x180010f95  add     rsi, rsi
0x180010f98  mov     rdx, [r13+rsi*8+0]; lpString2
0x180010f9d  call    cs:__imp_lstrcmpiW
0x180010fa3  test    eax, eax
0x180010fa5  jz      short loc_180010FE0
0x180010fa7  inc     ebx
0x180010fa9  cmp     ebx, 0Eh
0x180010fac  jb      short loc_180010F8D
0x180010fae  mov     ebx, 80020009h
0x180010fb3  mov     rcx, rbp; pv
0x180010fb6  call    cs:__imp_CoTaskMemFree
0x180010fbc  mov     eax, ebx
0x180010fbe  mov     rcx, [rsp+2088h+var_48]
0x180010fc6  xor     rcx, rsp; StackCookie
0x180010fc9  call    __security_check_cookie
0x180010fce  add     rsp, 2050h
0x180010fd5  pop     r15
0x180010fd7  pop     r14
0x180010fd9  pop     r13
0x180010fdb  pop     rdi
0x180010fdc  pop     rsi
0x180010fdd  pop     rbp
0x180010fde  pop     rbx
0x180010fdf  retn
0x180010fe0  mov     rsi, [r13+rsi*8+8]
0x180010fe5  test    rsi, rsi
0x180010fe8  jz      short loc_180010FAE
0x180010fea  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180010fef  mov     rcx, rdi; this
0x180010ff2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010ff7  mov     ebx, eax
0x180010ff9  test    eax, eax
0x180010ffb  js      short loc_180010FB3
0x180010ffd  mov     eax, 7Bh ; '{'
0x180011002  cmp     ax, [rsp+2088h+String1]
0x180011007  jnz     short loc_180010FAE
0x180011009  mov     [rsp+2088h+var_2068], 0; int
0x180011011  mov     r8, rsi; HKEY
0x180011014  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180011019  mov     rcx, rdi; this
0x18001101c  test    r15d, r15d
0x18001101f  jz      short loc_180011055
0x180011021  mov     r14, [rdi]
0x180011024  mov     r9d, r15d; int
0x180011027  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001102c  mov     ebx, eax
0x18001102e  test    eax, eax
0x180011030  jns     short loc_180011067
0x180011032  xor     r9d, r9d; int
0x180011035  mov     [rdi], r14
0x180011038  mov     r8, rsi; HKEY
0x18001103b  mov     [rsp+2088h+var_2068], 0; int
0x180011043  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180011048  mov     rcx, rdi; this
0x18001104b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180011050  jmp     loc_180010FB3
0x180011055  xor     r9d, r9d; int
0x180011058  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001105d  mov     ebx, eax
0x18001105f  test    eax, eax
0x180011061  js      loc_180010FB3
0x180011067  mov     r8, [rdi]
0x18001106a  movzx   edx, word ptr [r8]
0x18001106e  mov     ecx, edx
0x180011070  sub     ecx, 9
0x180011073  jz      short loc_180011084
0x180011075  sub     ecx, 1
0x180011078  jz      short loc_180011084
0x18001107a  sub     ecx, 3
0x18001107d  jz      short loc_180011084
0x18001107f  cmp     ecx, 13h
0x180011082  jnz     short loc_180011092
0x180011084  mov     rcx, r8; lpsz
0x180011087  call    cs:__imp_CharNextW
0x18001108d  mov     [rdi], rax
0x180011090  jmp     short loc_180011067
0x180011092  xor     eax, eax
0x180011094  cmp     ax, dx
0x180011097  jnz     loc_180010F78
0x18001109d  jmp     loc_180010FB3
```
