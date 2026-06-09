# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x140015830`
- end: `0x1400159cd`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `413`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400159d4`

## callees

- `0x140011b60`
- `0x140013c50`
- `0x140015830`
- `0x140015bdc`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1400158b5`
- `KERNEL32!lstrcmpiW` at `0x1400158b5`
- `USER32!CharNextW` at `0x1400159ac`
- `USER32!CharNextW` at `0x1400159ac`
- `ole32!CoTaskMemFree` at `0x1400158d4`
- `ole32!CoTaskMemFree` at `0x1400158d4`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(const wchar_t **this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  const wchar_t *v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (const wchar_t *)pv;
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
0x140015830  push    rbx
0x140015832  push    rbp
0x140015833  push    rsi
0x140015834  push    rdi
0x140015835  push    r13
0x140015837  push    r14
0x140015839  push    r15
0x14001583b  mov     eax, 2050h
0x140015840  call    _alloca_probe
0x140015845  sub     rsp, rax
0x140015848  mov     rax, cs:__security_cookie
0x14001584f  xor     rax, rsp
0x140015852  mov     [rsp+2088h+var_48], rax
0x14001585a  mov     r15d, r8d
0x14001585d  mov     [rsp+2088h+pv], 0
0x140015866  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x14001586b  mov     rdi, rcx
0x14001586e  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x140015873  mov     ebx, eax
0x140015875  test    eax, eax
0x140015877  js      short loc_1400158E2
0x140015879  mov     rbp, [rsp+2088h+pv]
0x14001587e  xor     eax, eax
0x140015880  mov     [rdi], rbp
0x140015883  cmp     ax, [rbp+0]
0x140015887  jz      short loc_1400158D1
0x140015889  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x140015890  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140015895  mov     rcx, rdi; this
0x140015898  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14001589d  mov     ebx, eax
0x14001589f  test    eax, eax
0x1400158a1  js      short loc_1400158D1
0x1400158a3  xor     ebx, ebx
0x1400158a5  movsxd  rsi, ebx
0x1400158a8  lea     rcx, [rsp+2088h+String1]; lpString1
0x1400158ad  add     rsi, rsi
0x1400158b0  mov     rdx, [r13+rsi*8+0]; lpString2
0x1400158b5  call    cs:__imp_lstrcmpiW
0x1400158bc  nop     dword ptr [rax+rax+00h]
0x1400158c1  test    eax, eax
0x1400158c3  jz      short loc_140015905
0x1400158c5  inc     ebx
0x1400158c7  cmp     ebx, 0Eh
0x1400158ca  jb      short loc_1400158A5
0x1400158cc  mov     ebx, 80020009h
0x1400158d1  mov     rcx, rbp; pv
0x1400158d4  call    cs:__imp_CoTaskMemFree
0x1400158db  nop     dword ptr [rax+rax+00h]
0x1400158e0  mov     eax, ebx
0x1400158e2  mov     rcx, [rsp+2088h+var_48]
0x1400158ea  xor     rcx, rsp; StackCookie
0x1400158ed  call    __security_check_cookie
0x1400158f2  add     rsp, 2050h
0x1400158f9  pop     r15
0x1400158fb  pop     r14
0x1400158fd  pop     r13
0x1400158ff  pop     rdi
0x140015900  pop     rsi
0x140015901  pop     rbp
0x140015902  pop     rbx
0x140015903  retn
0x140015905  mov     rsi, [r13+rsi*8+8]
0x14001590a  test    rsi, rsi
0x14001590d  jz      short loc_1400158CC
0x14001590f  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140015914  mov     rcx, rdi; this
0x140015917  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14001591c  mov     ebx, eax
0x14001591e  test    eax, eax
0x140015920  js      short loc_1400158D1
0x140015922  mov     eax, 7Bh ; '{'
0x140015927  cmp     ax, [rsp+2088h+String1]
0x14001592c  jnz     short loc_1400158CC
0x14001592e  mov     [rsp+2088h+var_2068], 0; int
0x140015936  mov     r8, rsi; HKEY
0x140015939  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14001593e  mov     rcx, rdi; this
0x140015941  test    r15d, r15d
0x140015944  jz      short loc_14001597A
0x140015946  mov     r14, [rdi]
0x140015949  mov     r9d, r15d; int
0x14001594c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140015951  mov     ebx, eax
0x140015953  test    eax, eax
0x140015955  jns     short loc_14001598C
0x140015957  xor     r9d, r9d; int
0x14001595a  mov     [rdi], r14
0x14001595d  mov     r8, rsi; HKEY
0x140015960  mov     [rsp+2088h+var_2068], 0; int
0x140015968  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14001596d  mov     rcx, rdi; this
0x140015970  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140015975  jmp     loc_1400158D1
0x14001597a  xor     r9d, r9d; int
0x14001597d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140015982  mov     ebx, eax
0x140015984  test    eax, eax
0x140015986  js      loc_1400158D1
0x14001598c  mov     r8, [rdi]
0x14001598f  movzx   edx, word ptr [r8]
0x140015993  mov     ecx, edx
0x140015995  sub     ecx, 9
0x140015998  jz      short loc_1400159A9
0x14001599a  sub     ecx, 1
0x14001599d  jz      short loc_1400159A9
0x14001599f  sub     ecx, 3
0x1400159a2  jz      short loc_1400159A9
0x1400159a4  cmp     ecx, 13h
0x1400159a7  jnz     short loc_1400159BD
0x1400159a9  mov     rcx, r8; lpsz
0x1400159ac  call    cs:__imp_CharNextW
0x1400159b3  nop     dword ptr [rax+rax+00h]
0x1400159b8  mov     [rdi], rax
0x1400159bb  jmp     short loc_14001598C
0x1400159bd  xor     eax, eax
0x1400159bf  cmp     ax, dx
0x1400159c2  jnz     loc_140015890
0x1400159c8  jmp     loc_1400158D1
```
