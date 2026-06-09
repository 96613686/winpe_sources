# CRegistry::OpenSchemeKey(ushort const *,HKEY__ * *)

- ea: `0x18004535c`
- end: `0x18004541a`
- name: `?OpenSchemeKey@CRegistry@@AEAAJPEBGPEAPEAUHKEY__@@@Z`
- size: `190`
- prototype: `int(CRegistry *__hidden this, const unsigned __int16 *, HKEY *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180044aa4`
- `0x180044bb8`
- `0x180044d5c`

## callees

- `0x180013870`
- `0x180029560`
- `0x18004535c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180045382`
- `ADVAPI32!RegOpenKeyExW` at `0x18004539e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800453bc`
- `ADVAPI32!RegOpenKeyExW` at `0x180045382`
- `ADVAPI32!RegOpenKeyExW` at `0x18004539e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800453bc`

## string_xrefs

- `0x1800453da`: `<CRegistry::OpenSchemeKey|OLEDB|ERR> `
- `0x1800453f8`: `<CRegistry::OpenSchemeKey|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CRegistry::OpenSchemeKey(HKEY *this, const unsigned __int16 *a2, HKEY *phkResult)
{
  unsigned int v6; // ebx

  v6 = 0;
  if ( RegOpenKeyExW(*this, a2, 0, 0xF003Fu, phkResult)
    && RegOpenKeyExW(*this, a2, 0, 0x1Fu, phkResult)
    && RegOpenKeyExW(*this, a2, 0, 0x20019u, phkResult) )
  {
    v6 = -2147418113;
    if ( (bidGblFlags & 2) == 0 )
      return v6;
    OLEDBTraceErr(-2147418113, L"<CRegistry::OpenSchemeKey|OLEDB|ERR> ", 0x2FCu);
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C83A8[0], 790537, L"<CRegistry::OpenSchemeKey|Trace|HR> ", v6);
  return v6;
}

```

## disassembly

```asm
0x18004535c  push    rbx
0x18004535e  push    rsi
0x18004535f  push    rdi
0x180045360  push    r14
0x180045362  sub     rsp, 38h
0x180045366  mov     rdi, r8
0x180045369  mov     [rsp+58h+phkResult], r8; phkResult
0x18004536e  mov     r14, rcx
0x180045371  xor     r8d, r8d; ulOptions
0x180045374  mov     rcx, [rcx]; hKey
0x180045377  mov     r9d, 0F003Fh; samDesired
0x18004537d  mov     rsi, rdx
0x180045380  xor     ebx, ebx
0x180045382  call    cs:__imp_RegOpenKeyExW
0x180045388  test    eax, eax
0x18004538a  jz      short loc_1800453E8
0x18004538c  mov     rcx, [r14]; hKey
0x18004538f  lea     r9d, [rbx+1Fh]; samDesired
0x180045393  xor     r8d, r8d; ulOptions
0x180045396  mov     [rsp+58h+phkResult], rdi; phkResult
0x18004539b  mov     rdx, rsi; lpSubKey
0x18004539e  call    cs:__imp_RegOpenKeyExW
0x1800453a4  test    eax, eax
0x1800453a6  jz      short loc_1800453E8
0x1800453a8  mov     rcx, [r14]; hKey
0x1800453ab  mov     r9d, 20019h; samDesired
0x1800453b1  xor     r8d, r8d; ulOptions
0x1800453b4  mov     [rsp+58h+phkResult], rdi; phkResult
0x1800453b9  mov     rdx, rsi; lpSubKey
0x1800453bc  call    cs:__imp_RegOpenKeyExW
0x1800453c2  test    eax, eax
0x1800453c4  jz      short loc_1800453E8
0x1800453c6  test    byte ptr cs:_bidGblFlags, 2
0x1800453cd  mov     ebx, 8000FFFFh
0x1800453d2  jz      short loc_18004540E
0x1800453d4  mov     r8d, 2FCh; unsigned int
0x1800453da  lea     rdx, aCregistryOpens; "<CRegistry::OpenSchemeKey|OLEDB|ERR> "
0x1800453e1  mov     ecx, ebx; int
0x1800453e3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800453e8  test    byte ptr cs:_bidGblFlags, 2
0x1800453ef  jz      short loc_18004540E
0x1800453f1  mov     rcx, cs:off_1800C83A8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800453f8  lea     r8, aCregistryOpens_0; "<CRegistry::OpenSchemeKey|Trace|HR> "
0x1800453ff  mov     r9d, ebx
0x180045402  mov     edx, 0C1009h
0x180045407  call    _bidTraceHR
0x18004540c  mov     ebx, eax
0x18004540e  mov     eax, ebx
0x180045410  add     rsp, 38h
0x180045414  pop     r14
0x180045416  pop     rdi
0x180045417  pop     rsi
0x180045418  pop     rbx
0x180045419  retn
```
