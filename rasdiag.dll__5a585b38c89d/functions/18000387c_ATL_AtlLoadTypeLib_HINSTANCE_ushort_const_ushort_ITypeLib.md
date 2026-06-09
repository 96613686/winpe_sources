# ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)

- ea: `0x18000387c`
- end: `0x180003a4a`
- name: `?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z`
- size: `462`
- prototype: `HRESULT __fastcall(HINSTANCE, const unsigned __int16 *, unsigned __int16 **, struct ITypeLib **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180003f80`
- `0x180005824`

## callees

- `0x18000383c`
- `0x18000387c`
- `0x18000418c`
- `0x18000df10`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800039a0`
- `msvcrt!wcscpy_s` at `0x1800039a0`
- `KERNEL32!GetModuleFileNameW` at `0x1800038c7`
- `KERNEL32!GetModuleFileNameW` at `0x1800038c7`
- `USER32!CharNextW` at `0x180003918`
- `USER32!CharNextW` at `0x180003918`
- `OLEAUT32!__imp_SysAllocString` at `0x1800039e7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800039e7`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000393f`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1800039d0`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000393f`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1800039d0`

## pseudocode

```c
HRESULT __fastcall ATL::AtlLoadTypeLib(
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
    return -2147467261;
  *a3 = 0;
  *a4 = 0;
  ModuleFileNameW = GetModuleFileNameW(a1, Filename, 0x104u);
  if ( !ModuleFileNameW )
    return ATL::AtlHresultFromLastError();
  if ( ModuleFileNameW == 260 )
    return -2147024774;
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
    return -2147467259;
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
      return -2147024882;
  }
  return TypeLib;
}

```

## disassembly

```asm
0x18000387c  push    rbx
0x18000387e  push    rbp
0x18000387f  push    rsi
0x180003880  push    rdi
0x180003881  push    r14
0x180003883  sub     rsp, 260h
0x18000388a  mov     rax, cs:__security_cookie
0x180003891  xor     rax, rsp
0x180003894  mov     [rsp+288h+var_38], rax
0x18000389c  xor     ebp, ebp
0x18000389e  mov     rsi, r9
0x1800038a1  mov     r14, r8
0x1800038a4  test    r8, r8
0x1800038a7  jz      loc_180003A05
0x1800038ad  test    r9, r9
0x1800038b0  jz      loc_180003A05
0x1800038b6  mov     [r8], rbp
0x1800038b9  lea     rdx, [rsp+288h+Filename]; lpFilename
0x1800038be  mov     r8d, 104h; nSize
0x1800038c4  mov     [r9], rbp
0x1800038c7  call    cs:__imp_GetModuleFileNameW
0x1800038ce  nop     dword ptr [rax+rax+00h]
0x1800038d3  test    eax, eax
0x1800038d5  jnz     short loc_1800038E1
0x1800038d7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800038dc  jmp     loc_180003A0A
0x1800038e1  cmp     eax, 104h
0x1800038e6  jnz     short loc_1800038F2
0x1800038e8  mov     eax, 8007007Ah
0x1800038ed  jmp     loc_180003A0A
0x1800038f2  movzx   eax, [rsp+288h+Filename]
0x1800038f7  lea     rcx, [rsp+288h+Filename]; lpsz
0x1800038fc  test    ax, ax
0x1800038ff  jz      short loc_180003934
0x180003901  mov     rdi, rbp
0x180003904  cmp     ax, 2Eh ; '.'
0x180003908  jz      short loc_180003915
0x18000390a  cmp     ax, 5Ch ; '\'
0x18000390e  jnz     short loc_180003918
0x180003910  mov     rdi, rbp
0x180003913  jmp     short loc_180003918
0x180003915  mov     rdi, rcx
0x180003918  call    cs:__imp_CharNextW
0x18000391f  nop     dword ptr [rax+rax+00h]
0x180003924  mov     rcx, rax
0x180003927  movzx   eax, word ptr [rax]
0x18000392a  test    ax, ax
0x18000392d  jnz     short loc_180003904
0x18000392f  test    rdi, rdi
0x180003932  jnz     short loc_180003937
0x180003934  mov     rdi, rcx
0x180003937  mov     rdx, rsi; pptlib
0x18000393a  lea     rcx, [rsp+288h+Filename]; szFile
0x18000393f  call    cs:__imp_LoadTypeLib
0x180003946  nop     dword ptr [rax+rax+00h]
0x18000394b  mov     ebx, eax
0x18000394d  test    eax, eax
0x18000394f  jns     loc_1800039E2
0x180003955  movzx   eax, word ptr cs:aTlb+8; ""
0x18000395c  mov     rcx, rdi
0x18000395f  movsd   xmm0, qword ptr cs:aTlb; ".tlb"
0x180003967  mov     [rsp+288h+var_260], ax
0x18000396c  lea     rax, [rsp+288h+Filename]
0x180003971  sub     rcx, rax
0x180003974  movsd   qword ptr [rsp+288h+Source], xmm0
0x18000397a  sar     rcx, 1
0x18000397d  lea     rax, [rcx+5]
0x180003981  cmp     rax, 104h
0x180003987  jbe     short loc_180003990
0x180003989  mov     eax, 80004005h
0x18000398e  jmp     short loc_180003A0A
0x180003990  mov     edx, 10Eh
0x180003995  lea     r8, [rsp+288h+Source]; Source
0x18000399a  sub     rdx, rcx; SizeInWords
0x18000399d  mov     rcx, rdi; Destination
0x1800039a0  call    cs:__imp_wcscpy_s
0x1800039a7  nop     dword ptr [rax+rax+00h]
0x1800039ac  test    eax, eax
0x1800039ae  jz      short loc_1800039C8
0x1800039b0  cmp     eax, 0Ch
0x1800039b3  jz      short loc_180003A29
0x1800039b5  cmp     eax, 16h
0x1800039b8  jz      loc_180003A3F
0x1800039be  cmp     eax, 22h ; '"'
0x1800039c1  jz      short loc_180003A3F
0x1800039c3  cmp     eax, 50h ; 'P'
0x1800039c6  jnz     short loc_180003A34
0x1800039c8  mov     rdx, rsi; pptlib
0x1800039cb  lea     rcx, [rsp+288h+Filename]; szFile
0x1800039d0  call    cs:__imp_LoadTypeLib
0x1800039d7  nop     dword ptr [rax+rax+00h]
0x1800039dc  mov     ebx, eax
0x1800039de  test    eax, eax
0x1800039e0  js      short loc_180003A01
0x1800039e2  lea     rcx, [rsp+288h+Filename]; psz
0x1800039e7  call    cs:__imp_SysAllocString
0x1800039ee  nop     dword ptr [rax+rax+00h]
0x1800039f3  test    rax, rax
0x1800039f6  mov     [r14], rax
0x1800039f9  mov     ecx, 8007000Eh
0x1800039fe  cmovz   ebx, ecx
0x180003a01  mov     eax, ebx
0x180003a03  jmp     short loc_180003A0A
0x180003a05  mov     eax, 80004003h
0x180003a0a  mov     rcx, [rsp+288h+var_38]
0x180003a12  xor     rcx, rsp; StackCookie
0x180003a15  call    __security_check_cookie
0x180003a1a  add     rsp, 260h
0x180003a21  pop     r14
0x180003a23  pop     rdi
0x180003a24  pop     rsi
0x180003a25  pop     rbp
0x180003a26  pop     rbx
0x180003a27  retn
0x180003a29  mov     ecx, 8007000Eh; int
0x180003a2e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003a34  mov     ecx, 80004005h; int
0x180003a39  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003a3f  mov     ecx, 80070057h; int
0x180003a44  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
