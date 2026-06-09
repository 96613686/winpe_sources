# ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_

- ea: `0x18000a5f4`
- end: `0x18000a86b`
- name: `ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6___`
- size: `631`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000bce8`

## callees

- `0x180006a70`
- `0x180007b84`
- `0x180008da4`
- `0x18000a554`
- `0x18000a5f4`
- `0x18000ba60`
- `0x18000c12c`
- `0x18000ccc0`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a822`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a822`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a7e3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a7e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a7bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a7bf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a70a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a70a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a742`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a742`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a66e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a66e`

## string_xrefs

- `0x18000a82f`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x18000a844`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x18000a859`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_(HKEY hKey, __int64 *a2)
{
  unsigned int v4; // eax
  DWORD v5; // edx
  DWORD v6; // eax
  __int64 v7; // r8
  const char *v8; // r9
  DWORD i; // ebx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r14
  __int64 v13; // rax
  __int64 v14; // r15
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR lpName[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+88h] [rbp-78h]
  _BYTE v27[112]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      (const char *)v4,
      lpcSubKeys);
  v5 = cbMaxSubKeyLen;
  v6 = cbMaxSubKeyLen + 1;
  v7 = 0xFFFFFFFFLL;
  if ( cbMaxSubKeyLen + 1 >= cbMaxSubKeyLen )
    v7 = v6;
  v8 = v6 < cbMaxSubKeyLen ? (const char *)0x80070216LL : 0LL;
  cbMaxSubKeyLen = v7;
  if ( v6 < v5 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      v8,
      lpcSubKeys);
  *(_OWORD *)lpName = 0;
  v26 = 0;
  if ( (_DWORD)v7 )
    std::vector<unsigned short>::_Reallocate(lpName, (unsigned int)v7, v7, v8);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = cbMaxSubKeyLen;
    v10 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
        (const char *)v10,
        lpcSubKeysa);
    phkResult = 0;
    if ( !RegOpenKeyExW(hKey, lpName[0], 0, 0x20019u, &phkResult) )
    {
      v12 = *a2;
      v13 = RegistryConfig::ParseCommand(v11, v27, phkResult, lpName[0]);
      v14 = *(_QWORD *)(v12 + 8);
      v16 = std::_List_buy<Command>::_Buynode<Command>(v15, v14, *(_QWORD *)(v14 + 8), v13);
      v17 = *(_QWORD *)(v12 + 16);
      if ( v17 == 0x1FFFFFFFFFFFFFELL )
        std::_Xlength_error("list<T> too long");
      *(_QWORD *)(v12 + 16) = v17 + 1;
      *(_QWORD *)(v14 + 8) = v16;
      **(_QWORD **)(v16 + 8) = v16;
      Command::~Command((Command *)v27);
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( lpName[0] )
    operator delete(lpName[0]);
  return i;
}

```

## disassembly

```asm
0x18000a5f4  mov     [rsp-8+arg_10], rbx
0x18000a5f9  mov     [rsp-8+arg_18], rsi
0x18000a5fe  push    rbp
0x18000a5ff  push    r12
0x18000a601  push    r13
0x18000a603  push    r14
0x18000a605  push    r15
0x18000a607  lea     rbp, [rsp-10h]
0x18000a60c  sub     rsp, 110h
0x18000a613  mov     rax, cs:__security_cookie
0x18000a61a  xor     rax, rsp
0x18000a61d  mov     [rbp+30h+var_30], rax
0x18000a621  mov     r12, rdx
0x18000a624  mov     rsi, rcx
0x18000a627  xor     r13d, r13d
0x18000a62a  mov     [rsp+130h+cSubKeys], r13d
0x18000a62f  mov     [rsp+130h+cbMaxSubKeyLen], r13d
0x18000a634  mov     [rsp+130h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000a639  mov     [rsp+130h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000a63e  mov     [rsp+130h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000a643  mov     [rsp+130h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18000a648  mov     [rsp+130h+lpcValues], r13; lpcValues
0x18000a64d  mov     [rsp+130h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000a652  lea     rax, [rsp+130h+cbMaxSubKeyLen]
0x18000a657  mov     [rsp+130h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000a65c  lea     rax, [rsp+130h+cSubKeys]
0x18000a661  mov     [rsp+130h+lpcSubKeys], rax; unsigned int
0x18000a666  xor     r9d, r9d; lpReserved
0x18000a669  xor     r8d, r8d; lpcchClass
0x18000a66c  xor     edx, edx; lpClass
0x18000a66e  call    cs:__imp_RegQueryInfoKeyW
0x18000a675  nop     dword ptr [rax+rax+00h]
0x18000a67a  mov     rcx, [rbp+38h]; this
0x18000a67e  test    eax, eax
0x18000a680  jnz     loc_18000A856
0x18000a686  mov     edx, [rsp+130h+cbMaxSubKeyLen]
0x18000a68a  lea     eax, [rdx+1]
0x18000a68d  or      r8d, 0FFFFFFFFh
0x18000a691  cmp     eax, edx
0x18000a693  cmovnb  r8d, eax
0x18000a697  sbb     r9d, r9d
0x18000a69a  and     r9d, 80070216h; char *
0x18000a6a1  mov     [rsp+130h+cbMaxSubKeyLen], r8d
0x18000a6a6  mov     rcx, [rbp+38h]; this
0x18000a6aa  cmp     eax, edx
0x18000a6ac  jb      loc_18000A82F
0x18000a6b2  xorps   xmm0, xmm0
0x18000a6b5  movdqu  xmmword ptr [rsp+130h+lpName], xmm0
0x18000a6bb  mov     [rbp+30h+var_A8], r13
0x18000a6bf  mov     edx, r8d
0x18000a6c2  test    r8d, r8d
0x18000a6c5  jz      short loc_18000A6D1
0x18000a6c7  lea     rcx, [rsp+130h+lpName]
0x18000a6cc  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18000a6d1  mov     ebx, r13d
0x18000a6d4  cmp     [rsp+130h+cSubKeys], r13d
0x18000a6d9  jbe     loc_18000A7D7
0x18000a6df  mov     eax, [rsp+130h+cbMaxSubKeyLen]
0x18000a6e3  mov     [rsp+130h+cchName], eax
0x18000a6e7  mov     [rsp+130h+lpcValues], r13; lpftLastWriteTime
0x18000a6ec  mov     [rsp+130h+lpcbMaxClassLen], r13; lpcchClass
0x18000a6f1  mov     [rsp+130h+lpcbMaxSubKeyLen], r13; lpClass
0x18000a6f6  mov     [rsp+130h+lpcSubKeys], r13; unsigned int
0x18000a6fb  lea     r9, [rsp+130h+cchName]; lpcchName
0x18000a700  mov     r8, [rsp+130h+lpName]; lpName
0x18000a705  mov     edx, ebx; dwIndex
0x18000a707  mov     rcx, rsi; hKey
0x18000a70a  call    cs:__imp_RegEnumKeyExW
0x18000a711  nop     dword ptr [rax+rax+00h]
0x18000a716  mov     rcx, [rbp+38h]; this
0x18000a71a  test    eax, eax
0x18000a71c  jnz     loc_18000A841
0x18000a722  mov     [rsp+130h+phkResult], r13
0x18000a727  lea     rax, [rsp+130h+phkResult]
0x18000a72c  mov     [rsp+130h+lpcSubKeys], rax; phkResult
0x18000a731  mov     r9d, 20019h; samDesired
0x18000a737  xor     r8d, r8d; ulOptions
0x18000a73a  mov     rdx, [rsp+130h+lpName]; lpSubKey
0x18000a73f  mov     rcx, rsi; hKey
0x18000a742  call    cs:__imp_RegOpenKeyExW
0x18000a749  nop     dword ptr [rax+rax+00h]
0x18000a74e  test    eax, eax
0x18000a750  jnz     short loc_18000A7B5
0x18000a752  mov     r14, [r12]
0x18000a756  mov     r9, [rsp+130h+lpName]
0x18000a75b  mov     r8, [rsp+130h+phkResult]
0x18000a760  lea     rdx, [rbp+30h+var_A0]
0x18000a764  call    ?ParseCommand@RegistryConfig@@AEAA?AUCommand@@PEAUHKEY__@@PEBG@Z; RegistryConfig::ParseCommand(HKEY__ *,ushort const *)
0x18000a769  nop
0x18000a76a  mov     r15, [r14+8]
0x18000a76e  mov     r9, rax
0x18000a771  mov     r8, [r15+8]
0x18000a775  mov     rdx, r15
0x18000a778  call    ??$_Buynode@UCommand@@@?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@1@PEAU21@0$$QEAUCommand@@@Z; std::_List_buy<Command>::_Buynode<Command>(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *,Command &&)
0x18000a77d  mov     rdx, [r14+10h]
0x18000a781  mov     rcx, 1FFFFFFFFFFFFFEh
0x18000a78b  sub     rcx, rdx
0x18000a78e  cmp     rcx, 1
0x18000a792  jb      loc_18000A81B
0x18000a798  lea     rcx, [rdx+1]
0x18000a79c  mov     [r14+10h], rcx
0x18000a7a0  mov     [r15+8], rax
0x18000a7a4  mov     rcx, [rax+8]
0x18000a7a8  mov     [rcx], rax
0x18000a7ab  lea     rcx, [rbp+30h+var_A0]; this
0x18000a7af  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x18000a7b4  nop
0x18000a7b5  mov     rcx, [rsp+130h+phkResult]; hKey
0x18000a7ba  test    rcx, rcx
0x18000a7bd  jz      short loc_18000A7CB
0x18000a7bf  call    cs:__imp_RegCloseKey
0x18000a7c6  nop     dword ptr [rax+rax+00h]
0x18000a7cb  inc     ebx
0x18000a7cd  cmp     ebx, [rsp+130h+cSubKeys]
0x18000a7d1  jb      loc_18000A6DF
0x18000a7d7  cmp     [rsp+130h+lpName], r13
0x18000a7dc  jz      short loc_18000A7EF
0x18000a7de  mov     rcx, [rsp+130h+lpName]
0x18000a7e3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a7ea  nop     dword ptr [rax+rax+00h]
0x18000a7ef  mov     eax, ebx
0x18000a7f1  mov     rcx, [rbp+30h+var_30]
0x18000a7f5  xor     rcx, rsp; StackCookie
0x18000a7f8  call    __security_check_cookie
0x18000a7fd  lea     r11, [rsp+130h+var_20]
0x18000a805  mov     rbx, [r11+40h]
0x18000a809  mov     rsi, [r11+48h]
0x18000a80d  mov     rsp, r11
0x18000a810  pop     r15
0x18000a812  pop     r14
0x18000a814  pop     r13
0x18000a816  pop     r12
0x18000a818  pop     rbp
0x18000a819  retn
0x18000a81b  lea     rcx, aListTTooLong; "list<T> too long"
0x18000a822  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000a82f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x18000a836  mov     edx, 43h ; 'C'; void *
0x18000a83b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a841  mov     r9d, eax; char *
0x18000a844  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x18000a84b  mov     edx, 4Ch ; 'L'; void *
0x18000a850  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000a856  mov     r9d, eax; char *
0x18000a859  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x18000a860  mov     edx, 40h ; '@'; void *
0x18000a865  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
