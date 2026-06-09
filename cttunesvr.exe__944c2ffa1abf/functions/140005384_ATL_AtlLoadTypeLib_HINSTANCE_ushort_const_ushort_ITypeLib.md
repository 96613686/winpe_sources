# ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)

- ea: `0x140005384`
- end: `0x140005525`
- name: `?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z`
- size: `417`
- prototype: `int(HINSTANCE, const unsigned __int16 *, unsigned __int16 **, struct ITypeLib **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400059e8`
- `0x1400061fc`

## callees

- `0x140002bd8`
- `0x140002c14`
- `0x140005384`
- `0x1400065f0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1400053cf`
- `KERNEL32!GetModuleFileNameW` at `0x1400053cf`
- `USER32!CharNextW` at `0x14000541a`
- `USER32!CharNextW` at `0x14000541a`
- `msvcrt!wcscpy_s` at `0x140005492`
- `msvcrt!wcscpy_s` at `0x140005492`
- `OLEAUT32!__imp_SysAllocString` at `0x1400054c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1400054c9`
- `OLEAUT32!__imp_LoadTypeLib` at `0x14000543b`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1400054b8`
- `OLEAUT32!__imp_LoadTypeLib` at `0x14000543b`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1400054b8`

## pseudocode

```c
__int64 __fastcall ATL::AtlLoadTypeLib(
        HINSTANCE a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct ITypeLib **a4)
{
  DWORD ModuleFileNameW; // eax
  WCHAR v8; // ax
  WCHAR *v9; // rcx
  wchar_t *v10; // rdi
  HRESULT TypeLib; // ebx
  __int64 v12; // rcx
  errno_t v13; // eax
  unsigned __int16 *v14; // rax
  wchar_t Source[8]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Filename[272]; // [rsp+30h] [rbp-258h] BYREF

  if ( !a3 || !a4 )
    return 2147500035LL;
  *a3 = 0;
  *a4 = 0;
  ModuleFileNameW = GetModuleFileNameW(a1, Filename, 0x104u);
  if ( !ModuleFileNameW )
    return ATL::AtlHresultFromLastError();
  if ( ModuleFileNameW == 260 )
    return 2147942522LL;
  v8 = Filename[0];
  v9 = Filename;
  if ( !Filename[0] )
    goto LABEL_15;
  v10 = 0;
  do
  {
    if ( v8 == 46 )
    {
      v10 = v9;
    }
    else if ( v8 == 92 )
    {
      v10 = 0;
    }
    v9 = CharNextW(v9);
    v8 = *v9;
  }
  while ( *v9 );
  if ( !v10 )
LABEL_15:
    v10 = v9;
  TypeLib = LoadTypeLib(Filename, a4);
  if ( TypeLib >= 0 )
    goto LABEL_25;
  wcscpy(Source, L".tlb");
  v12 = v10 - Filename;
  if ( (unsigned __int64)(v12 + 5) > 0x104 )
    return 2147500037LL;
  v13 = wcscpy_s(v10, 270 - v12, Source);
  if ( v13 )
  {
    if ( v13 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v13 == 22 || v13 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v13 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  TypeLib = LoadTypeLib(Filename, a4);
  if ( TypeLib >= 0 )
  {
LABEL_25:
    v14 = SysAllocString(Filename);
    *a3 = v14;
    if ( !v14 )
      return (unsigned int)-2147024882;
  }
  return (unsigned int)TypeLib;
}

```

## disassembly

```asm
0x140005384  push    rbx
0x140005386  push    rbp
0x140005387  push    rsi
0x140005388  push    rdi
0x140005389  push    r14
0x14000538b  sub     rsp, 260h
0x140005392  mov     rax, cs:__security_cookie
0x140005399  xor     rax, rsp
0x14000539c  mov     [rsp+288h+var_38], rax
0x1400053a4  xor     ebp, ebp
0x1400053a6  mov     rsi, r9
0x1400053a9  mov     r14, r8
0x1400053ac  test    r8, r8
0x1400053af  jz      loc_1400054E1
0x1400053b5  test    r9, r9
0x1400053b8  jz      loc_1400054E1
0x1400053be  mov     [r8], rbp
0x1400053c1  lea     rdx, [rsp+288h+Filename]; lpFilename
0x1400053c6  mov     r8d, 104h; nSize
0x1400053cc  mov     [r9], rbp
0x1400053cf  call    cs:__imp_GetModuleFileNameW
0x1400053d5  test    eax, eax
0x1400053d7  jnz     short loc_1400053E3
0x1400053d9  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400053de  jmp     loc_1400054E6
0x1400053e3  cmp     eax, 104h
0x1400053e8  jnz     short loc_1400053F4
0x1400053ea  mov     eax, 8007007Ah
0x1400053ef  jmp     loc_1400054E6
0x1400053f4  movzx   eax, [rsp+288h+Filename]
0x1400053f9  lea     rcx, [rsp+288h+Filename]; lpsz
0x1400053fe  test    ax, ax
0x140005401  jz      short loc_140005430
0x140005403  mov     rdi, rbp
0x140005406  cmp     ax, 2Eh ; '.'
0x14000540a  jz      short loc_140005417
0x14000540c  cmp     ax, 5Ch ; '\'
0x140005410  jnz     short loc_14000541A
0x140005412  mov     rdi, rbp
0x140005415  jmp     short loc_14000541A
0x140005417  mov     rdi, rcx
0x14000541a  call    cs:__imp_CharNextW
0x140005420  mov     rcx, rax
0x140005423  movzx   eax, word ptr [rax]
0x140005426  test    ax, ax
0x140005429  jnz     short loc_140005406
0x14000542b  test    rdi, rdi
0x14000542e  jnz     short loc_140005433
0x140005430  mov     rdi, rcx
0x140005433  mov     rdx, rsi; pptlib
0x140005436  lea     rcx, [rsp+288h+Filename]; szFile
0x14000543b  call    cs:__imp_LoadTypeLib
0x140005441  mov     ebx, eax
0x140005443  test    eax, eax
0x140005445  jns     short loc_1400054C4
0x140005447  movzx   eax, word ptr cs:aTlb+8; ""
0x14000544e  mov     rcx, rdi
0x140005451  movsd   xmm0, qword ptr cs:aTlb; ".tlb"
0x140005459  mov     [rsp+288h+var_260], ax
0x14000545e  lea     rax, [rsp+288h+Filename]
0x140005463  sub     rcx, rax
0x140005466  movsd   qword ptr [rsp+288h+Source], xmm0
0x14000546c  sar     rcx, 1
0x14000546f  lea     rax, [rcx+5]
0x140005473  cmp     rax, 104h
0x140005479  jbe     short loc_140005482
0x14000547b  mov     eax, 80004005h
0x140005480  jmp     short loc_1400054E6
0x140005482  mov     edx, 10Eh
0x140005487  lea     r8, [rsp+288h+Source]; Source
0x14000548c  sub     rdx, rcx; SizeInWords
0x14000548f  mov     rcx, rdi; Destination
0x140005492  call    cs:__imp_wcscpy_s
0x140005498  test    eax, eax
0x14000549a  jz      short loc_1400054B0
0x14000549c  cmp     eax, 0Ch
0x14000549f  jz      short loc_140005504
0x1400054a1  cmp     eax, 16h
0x1400054a4  jz      short loc_14000551A
0x1400054a6  cmp     eax, 22h ; '"'
0x1400054a9  jz      short loc_14000551A
0x1400054ab  cmp     eax, 50h ; 'P'
0x1400054ae  jnz     short loc_14000550F
0x1400054b0  mov     rdx, rsi; pptlib
0x1400054b3  lea     rcx, [rsp+288h+Filename]; szFile
0x1400054b8  call    cs:__imp_LoadTypeLib
0x1400054be  mov     ebx, eax
0x1400054c0  test    eax, eax
0x1400054c2  js      short loc_1400054DD
0x1400054c4  lea     rcx, [rsp+288h+Filename]; psz
0x1400054c9  call    cs:__imp_SysAllocString
0x1400054cf  test    rax, rax
0x1400054d2  mov     [r14], rax
0x1400054d5  mov     ecx, 8007000Eh
0x1400054da  cmovz   ebx, ecx
0x1400054dd  mov     eax, ebx
0x1400054df  jmp     short loc_1400054E6
0x1400054e1  mov     eax, 80004003h
0x1400054e6  mov     rcx, [rsp+288h+var_38]
0x1400054ee  xor     rcx, rsp; StackCookie
0x1400054f1  call    __security_check_cookie
0x1400054f6  add     rsp, 260h
0x1400054fd  pop     r14
0x1400054ff  pop     rdi
0x140005500  pop     rsi
0x140005501  pop     rbp
0x140005502  pop     rbx
0x140005503  retn
0x140005504  mov     ecx, 8007000Eh; int
0x140005509  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000550f  mov     ecx, 80004005h; int
0x140005514  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000551a  mov     ecx, 80070057h; int
0x14000551f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
