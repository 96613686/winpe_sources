# CRegistry::SetRegistryVal(ushort const *,_GUID const *)

- ea: `0x1800454cc`
- end: `0x180045602`
- name: `?SetRegistryVal@CRegistry@@QEAAJPEBGPEBU_GUID@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002c978`

## callees

- `0x1800112b0`
- `0x180029560`
- `0x1800448a8`
- `0x180045488`
- `0x1800454cc`
- `0x18007e700`
- `0x18007e7c0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800455ae`
- `ADVAPI32!RegSetValueExW` at `0x1800455ae`
- `ADVAPI32!RegCloseKey` at `0x1800455ba`
- `ADVAPI32!RegCloseKey` at `0x1800455ba`
- `ole32!StringFromGUID2` at `0x180045588`
- `ole32!StringFromGUID2` at `0x180045588`

## string_xrefs

- `0x1800455d0`: `<CRegistry::SetRegistryVal|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CRegistry::SetRegistryVal(HKEY *this, const unsigned __int16 *a2, const struct _GUID *a3)
{
  __int64 v4; // rax
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  CRegistry *v13; // rcx
  unsigned int v14; // ebx
  unsigned __int16 v16[2]; // [rsp+30h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp+8h] BYREF
  unsigned __int16 *v18; // [rsp+40h] [rbp+10h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp+18h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp+20h] BYREF

  hKey = 0;
  v4 = -1;
  *(_DWORD *)v16 = 0;
  do
    ++v4;
  while ( a2[v4] );
  v7 = v4 + 1;
  v18 = 0;
  v8 = 2 * (v4 + 1);
  v9 = v8 + 15;
  if ( v8 + 15 < v8 )
    v9 = 0xFFFFFFFFFFFFFF0LL;
  v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
  v11 = alloca(v10);
  v12 = alloca(v10);
  lpValueName = v16;
  v14 = StringCchCopyW(v16, v7, a2);
  if ( *this )
  {
    if ( (unsigned int)CRegistry::SeparateSchemeFromPrefix(v13, (unsigned __int16 **)&lpValueName, &v18) )
    {
      v14 = CRegistry::CreateSchemeKey(this, v18, &hKey, (unsigned int *)v16);
      if ( !v14 )
      {
        StringFromGUID2(a3, sz, 39);
        v14 = RegSetValueExW(hKey, lpValueName, 0, 1u, (const BYTE *)sz, 0x4Eu);
        RegCloseKey(hKey);
      }
    }
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C83A8[0], 315401, L"<CRegistry::SetRegistryVal|Trace|HR> ", v14);
  return v14;
}

```

## disassembly

```asm
0x1800454cc  push    rbp
0x1800454ce  push    rbx
0x1800454cf  push    rsi
0x1800454d0  push    rdi
0x1800454d1  push    r14
0x1800454d3  sub     rsp, 0B0h
0x1800454da  lea     rbp, [rsp+30h]
0x1800454df  mov     rax, cs:__security_cookie
0x1800454e6  xor     rax, rbp
0x1800454e9  mov     [rbp+0A0h+var_30], rax
0x1800454ed  xor     r14d, r14d
0x1800454f0  mov     rsi, r8
0x1800454f3  mov     [rbp+0A0h+hKey], r14
0x1800454f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800454fb  mov     dword ptr [rbp+0A0h+var_A0], r14d
0x1800454ff  mov     r8, rdx
0x180045502  mov     rdi, rcx
0x180045505  inc     rax
0x180045508  cmp     [rdx+rax*2], r14w
0x18004550d  jnz     short loc_180045505
0x18004550f  lea     rdx, [rax+1]
0x180045513  mov     [rbp+0A0h+var_90], r14
0x180045517  lea     rax, [rdx+rdx]
0x18004551b  lea     rcx, [rax+0Fh]
0x18004551f  cmp     rcx, rax
0x180045522  ja      short loc_18004552E
0x180045524  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18004552e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180045532  mov     rax, rcx
0x180045535  call    _alloca_probe
0x18004553a  sub     rsp, rcx
0x18004553d  lea     rcx, [rsp+0D0h+var_A0]; unsigned __int16 *
0x180045542  mov     [rbp+0A0h+lpValueName], rcx
0x180045546  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004554b  mov     ebx, eax
0x18004554d  cmp     [rdi], r14
0x180045550  jz      short loc_1800455C0
0x180045552  lea     r8, [rbp+0A0h+var_90]; unsigned __int16 **
0x180045556  lea     rdx, [rbp+0A0h+lpValueName]; unsigned __int16 **
0x18004555a  call    ?SeparateSchemeFromPrefix@CRegistry@@AEAAHPEAPEAG0@Z; CRegistry::SeparateSchemeFromPrefix(ushort * *,ushort * *)
0x18004555f  test    eax, eax
0x180045561  jz      short loc_1800455C0
0x180045563  mov     rdx, [rbp+0A0h+var_90]; unsigned __int16 *
0x180045567  lea     r9, [rbp+0A0h+var_A0]; unsigned int *
0x18004556b  lea     r8, [rbp+0A0h+hKey]; HKEY *
0x18004556f  mov     rcx, rdi; this
0x180045572  call    ?CreateSchemeKey@CRegistry@@AEAAJPEBGPEAPEAUHKEY__@@PEAK@Z; CRegistry::CreateSchemeKey(ushort const *,HKEY__ * *,ulong *)
0x180045577  mov     ebx, eax
0x180045579  test    eax, eax
0x18004557b  jnz     short loc_1800455C0
0x18004557d  lea     r8d, [rax+27h]; cchMax
0x180045581  mov     rcx, rsi; rguid
0x180045584  lea     rdx, [rbp+0A0h+sz]; lpsz
0x180045588  call    cs:__imp_StringFromGUID2
0x18004558e  mov     rdx, [rbp+0A0h+lpValueName]; lpValueName
0x180045592  lea     rax, [rbp+0A0h+sz]
0x180045596  mov     rcx, [rbp+0A0h+hKey]; hKey
0x18004559a  lea     r9d, [rbx+1]; dwType
0x18004559e  mov     [rsp+0D0h+cbData], 4Eh ; 'N'; cbData
0x1800455a6  xor     r8d, r8d; Reserved
0x1800455a9  mov     [rsp+0D0h+lpData], rax; lpData
0x1800455ae  call    cs:__imp_RegSetValueExW
0x1800455b4  mov     rcx, [rbp+0A0h+hKey]; hKey
0x1800455b8  mov     ebx, eax
0x1800455ba  call    cs:__imp_RegCloseKey
0x1800455c0  test    byte ptr cs:_bidGblFlags, 2
0x1800455c7  jz      short loc_1800455E6
0x1800455c9  mov     rcx, cs:off_1800C83A8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800455d0  lea     r8, aCregistrySetre; "<CRegistry::SetRegistryVal|Trace|HR> "
0x1800455d7  mov     r9d, ebx
0x1800455da  mov     edx, 4D009h
0x1800455df  call    _bidTraceHR
0x1800455e4  mov     ebx, eax
0x1800455e6  mov     eax, ebx
0x1800455e8  mov     rcx, [rbp+0A0h+var_30]
0x1800455ec  xor     rcx, rbp; StackCookie
0x1800455ef  call    __security_check_cookie
0x1800455f4  lea     rsp, [rbp+80h]
0x1800455fb  pop     r14
0x1800455fd  pop     rdi
0x1800455fe  pop     rsi
0x1800455ff  pop     rbx
0x180045600  pop     rbp
0x180045601  retn
```
