# CRegistry::CreateSchemeKey(ushort const *,HKEY__ * *,ulong *)

- ea: `0x1800448a8`
- end: `0x18004495a`
- name: `?CreateSchemeKey@CRegistry@@AEAAJPEBGPEAPEAUHKEY__@@PEAK@Z`
- size: `178`
- prototype: `int(CRegistry *__hidden this, const unsigned __int16 *, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800454cc`

## callees

- `0x180029560`
- `0x1800448a8`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1800448e2`
- `ADVAPI32!RegCreateKeyExW` at `0x180044913`
- `ADVAPI32!RegCreateKeyExW` at `0x1800448e2`
- `ADVAPI32!RegCreateKeyExW` at `0x180044913`

## string_xrefs

- `0x180044937`: `<CRegistry::CreateSchemeKey|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CRegistry::CreateSchemeKey(
        HKEY *this,
        const unsigned __int16 *a2,
        HKEY *phkResult,
        unsigned int *lpdwDisposition)
{
  unsigned int v4; // ebx

  v4 = 0;
  if ( RegCreateKeyExW(*this, a2, 0, 0, 0, 0xF003Fu, 0, phkResult, lpdwDisposition)
    && RegCreateKeyExW(*this, a2, 0, 0, 0, 0x1Fu, 0, phkResult, lpdwDisposition) )
  {
    *phkResult = 0;
    *lpdwDisposition = 0;
    v4 = -2147418113;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C83A8[0], 842761, L"<CRegistry::CreateSchemeKey|Trace|HR> ", v4);
  return v4;
}

```

## disassembly

```asm
0x1800448a8  mov     rax, rsp
0x1800448ab  push    rbx
0x1800448ac  push    rbp
0x1800448ad  push    rsi
0x1800448ae  push    rdi
0x1800448af  push    r14
0x1800448b1  sub     rsp, 50h
0x1800448b5  mov     [rax-38h], r9
0x1800448b9  xor     ebx, ebx
0x1800448bb  mov     [rax-40h], r8
0x1800448bf  mov     rdi, r9
0x1800448c2  mov     [rax-48h], rbx
0x1800448c6  mov     rsi, r8
0x1800448c9  mov     r14, rcx
0x1800448cc  mov     dword ptr [rax-50h], 0F003Fh
0x1800448d3  mov     rcx, [rcx]; hKey
0x1800448d6  xor     r9d, r9d; lpClass
0x1800448d9  xor     r8d, r8d; Reserved
0x1800448dc  mov     [rax-58h], ebx
0x1800448df  mov     rbp, rdx
0x1800448e2  call    cs:__imp_RegCreateKeyExW
0x1800448e8  test    eax, eax
0x1800448ea  jz      short loc_180044927
0x1800448ec  mov     rcx, [r14]; hKey
0x1800448ef  xor     r9d, r9d; lpClass
0x1800448f2  mov     [rsp+78h+lpdwDisposition], rdi; lpdwDisposition
0x1800448f7  xor     r8d, r8d; Reserved
0x1800448fa  mov     [rsp+78h+phkResult], rsi; phkResult
0x1800448ff  mov     rdx, rbp; lpSubKey
0x180044902  mov     [rsp+78h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180044907  mov     [rsp+78h+samDesired], 1Fh; samDesired
0x18004490f  mov     [rsp+78h+dwOptions], ebx; dwOptions
0x180044913  call    cs:__imp_RegCreateKeyExW
0x180044919  test    eax, eax
0x18004491b  jz      short loc_180044927
0x18004491d  mov     [rsi], rbx
0x180044920  mov     [rdi], ebx
0x180044922  mov     ebx, 8000FFFFh
0x180044927  test    byte ptr cs:_bidGblFlags, 2
0x18004492e  jz      short loc_18004494D
0x180044930  mov     rcx, cs:off_1800C83A8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180044937  lea     r8, aCregistryCreat; "<CRegistry::CreateSchemeKey|Trace|HR> "
0x18004493e  mov     r9d, ebx
0x180044941  mov     edx, 0CDC09h
0x180044946  call    _bidTraceHR
0x18004494b  mov     ebx, eax
0x18004494d  mov     eax, ebx
0x18004494f  add     rsp, 50h
0x180044953  pop     r14
0x180044955  pop     rdi
0x180044956  pop     rsi
0x180044957  pop     rbp
0x180044958  pop     rbx
0x180044959  retn
```
