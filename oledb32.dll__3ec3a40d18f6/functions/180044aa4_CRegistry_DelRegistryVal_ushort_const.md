# CRegistry::DelRegistryVal(ushort const *)

- ea: `0x180044aa4`
- end: `0x180044bb1`
- name: `?DelRegistryVal@CRegistry@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800444e4`
- `0x180044960`

## callees

- `0x1800112b0`
- `0x180029560`
- `0x180044810`
- `0x180044aa4`
- `0x18004535c`
- `0x180045488`
- `0x18007e700`
- `0x18007e7c0`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x180044b4e`
- `ADVAPI32!RegDeleteValueW` at `0x180044b4e`
- `ADVAPI32!RegCloseKey` at `0x180044b6e`
- `ADVAPI32!RegCloseKey` at `0x180044b6e`

## string_xrefs

- `0x180044b84`: `<CRegistry::DelRegistryVal|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CRegistry::DelRegistryVal(HKEY *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  unsigned __int64 v4; // r9
  unsigned __int64 v5; // rax
  __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  void *v8; // rsp
  void *v9; // rsp
  CRegistry *v10; // rcx
  unsigned int v11; // ebx
  HKEY hKey; // [rsp+20h] [rbp+0h] BYREF
  unsigned __int16 *v14; // [rsp+28h] [rbp+8h] BYREF
  LPCWSTR lpValueName; // [rsp+30h] [rbp+10h] BYREF

  hKey = 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  v4 = v3 + 1;
  v14 = 0;
  v5 = 2 * (v3 + 1);
  v6 = v5 + 15;
  if ( v5 + 15 < v5 )
    v6 = 0xFFFFFFFFFFFFFF0LL;
  v7 = v6 & 0xFFFFFFFFFFFFFFF0uLL;
  v8 = alloca(v7);
  v9 = alloca(v7);
  lpValueName = (LPCWSTR)&hKey;
  v11 = StringCchCopyW((unsigned __int16 *)&hKey, v4, a2);
  if ( *this )
  {
    if ( (unsigned int)CRegistry::SeparateSchemeFromPrefix(v10, (unsigned __int16 **)&lpValueName, &v14) )
    {
      v11 = CRegistry::OpenSchemeKey(this, v14, &hKey);
      if ( !v11 )
      {
        v11 = RegDeleteValueW(hKey, lpValueName);
        if ( !v11 )
          CRegistry::CleanUpKeyWhenEmpty((CRegistry *)this, hKey, v14);
        RegCloseKey(hKey);
      }
    }
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C83A8[0], 355337, L"<CRegistry::DelRegistryVal|Trace|HR> ", v11);
  return v11;
}

```

## disassembly

```asm
0x180044aa4  push    rbp
0x180044aa6  push    rbx
0x180044aa7  push    rsi
0x180044aa8  push    rdi
0x180044aa9  sub     rsp, 48h
0x180044aad  lea     rbp, [rsp+20h]
0x180044ab2  mov     rax, cs:__security_cookie
0x180044ab9  xor     rax, rbp
0x180044abc  mov     [rbp+40h+var_28], rax
0x180044ac0  xor     esi, esi
0x180044ac2  mov     rdi, rcx
0x180044ac5  mov     [rbp+40h+hKey], rsi
0x180044ac9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044acd  inc     rax
0x180044ad0  cmp     [rdx+rax*2], si
0x180044ad4  jnz     short loc_180044ACD
0x180044ad6  lea     r9, [rax+1]
0x180044ada  mov     [rbp+40h+var_38], rsi
0x180044ade  lea     rax, [r9+r9]
0x180044ae2  lea     rcx, [rax+0Fh]
0x180044ae6  cmp     rcx, rax
0x180044ae9  ja      short loc_180044AF5
0x180044aeb  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180044af5  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180044af9  mov     rax, rcx
0x180044afc  call    _alloca_probe
0x180044b01  sub     rsp, rcx
0x180044b04  mov     r8, rdx; unsigned __int16 *
0x180044b07  mov     rdx, r9; unsigned __int64
0x180044b0a  lea     rcx, [rsp+60h+hKey]; unsigned __int16 *
0x180044b0f  mov     [rbp+40h+lpValueName], rcx
0x180044b13  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044b18  mov     ebx, eax
0x180044b1a  cmp     [rdi], rsi
0x180044b1d  jz      short loc_180044B74
0x180044b1f  lea     r8, [rbp+40h+var_38]; unsigned __int16 **
0x180044b23  lea     rdx, [rbp+40h+lpValueName]; unsigned __int16 **
0x180044b27  call    ?SeparateSchemeFromPrefix@CRegistry@@AEAAHPEAPEAG0@Z; CRegistry::SeparateSchemeFromPrefix(ushort * *,ushort * *)
0x180044b2c  test    eax, eax
0x180044b2e  jz      short loc_180044B74
0x180044b30  mov     rdx, [rbp+40h+var_38]; unsigned __int16 *
0x180044b34  lea     r8, [rbp+40h+hKey]; HKEY *
0x180044b38  mov     rcx, rdi; this
0x180044b3b  call    ?OpenSchemeKey@CRegistry@@AEAAJPEBGPEAPEAUHKEY__@@@Z; CRegistry::OpenSchemeKey(ushort const *,HKEY__ * *)
0x180044b40  mov     ebx, eax
0x180044b42  test    eax, eax
0x180044b44  jnz     short loc_180044B74
0x180044b46  mov     rdx, [rbp+40h+lpValueName]; lpValueName
0x180044b4a  mov     rcx, [rbp+40h+hKey]; hKey
0x180044b4e  call    cs:__imp_RegDeleteValueW
0x180044b54  mov     ebx, eax
0x180044b56  test    eax, eax
0x180044b58  jnz     short loc_180044B6A
0x180044b5a  mov     r8, [rbp+40h+var_38]; unsigned __int16 *
0x180044b5e  mov     rcx, rdi; this
0x180044b61  mov     rdx, [rbp+40h+hKey]; HKEY
0x180044b65  call    ?CleanUpKeyWhenEmpty@CRegistry@@AEAAXPEAUHKEY__@@PEBG@Z; CRegistry::CleanUpKeyWhenEmpty(HKEY__ *,ushort const *)
0x180044b6a  mov     rcx, [rbp+40h+hKey]; hKey
0x180044b6e  call    cs:__imp_RegCloseKey
0x180044b74  test    byte ptr cs:_bidGblFlags, 2
0x180044b7b  jz      short loc_180044B9A
0x180044b7d  mov     rcx, cs:off_1800C83A8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180044b84  lea     r8, aCregistryDelre; "<CRegistry::DelRegistryVal|Trace|HR> "
0x180044b8b  mov     r9d, ebx
0x180044b8e  mov     edx, 56C09h
0x180044b93  call    _bidTraceHR
0x180044b98  mov     ebx, eax
0x180044b9a  mov     eax, ebx
0x180044b9c  mov     rcx, [rbp+40h+var_28]
0x180044ba0  xor     rcx, rbp; StackCookie
0x180044ba3  call    __security_check_cookie
0x180044ba8  lea     rsp, [rbp+28h]
0x180044bac  pop     rdi
0x180044bad  pop     rsi
0x180044bae  pop     rbx
0x180044baf  pop     rbp
0x180044bb0  retn
```
