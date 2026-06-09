# ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_

- ea: `0x18000a0dc`
- end: `0x18000a32a`
- name: `ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6___`
- size: `590`
- prototype: `__int64 __fastcall(HKEY hKey, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000b660`

## callees

- `0x180006760`
- `0x180007800`
- `0x18000899c`
- `0x18000a050`
- `0x18000a0dc`
- `0x18000b3f0`
- `0x18000ba6c`
- `0x18000c600`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a2e7`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a2e7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a2af`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a2af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a291`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a291`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a1ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a1ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a21e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a21e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a156`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a156`

## string_xrefs

- `0x18000a2ee`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x18000a303`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x18000a318`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`

## pseudocode

```c
__int64 __fastcall ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_(HKEY hKey, __int64 *a2)
{
  unsigned int v4; // eax
  DWORD v5; // edx
  DWORD v6; // eax
  DWORD v7; // r8d
  const char *v8; // r9
  DWORD i; // ebx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r14
  const struct Command *v13; // rax
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
  void *v27[14]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x40,
      (int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      (const char *)v4,
      lpcSubKeys);
  v5 = cbMaxSubKeyLen;
  v6 = cbMaxSubKeyLen + 1;
  v7 = -1;
  if ( cbMaxSubKeyLen + 1 >= cbMaxSubKeyLen )
    v7 = cbMaxSubKeyLen + 1;
  v8 = v6 < cbMaxSubKeyLen ? (const char *)0x80070216LL : 0LL;
  cbMaxSubKeyLen = v7;
  if ( v6 < v5 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      67,
      (__int64)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      v8,
      lpcSubKeys);
  *(_OWORD *)lpName = 0;
  v26 = 0;
  if ( v7 )
    std::vector<unsigned short>::_Reallocate((__int64)lpName, v7);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = cbMaxSubKeyLen;
    v10 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x4C,
        (int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
        (const char *)v10,
        lpcSubKeysa);
    phkResult = 0;
    if ( !RegOpenKeyExW(hKey, lpName[0], 0, 0x20019u, &phkResult) )
    {
      v12 = *a2;
      v13 = (const struct Command *)RegistryConfig::ParseCommand(v11, v27, phkResult, lpName[0]);
      v14 = *(_QWORD *)(v12 + 8);
      v16 = std::_List_buy<Command>::_Buynode<Command>(v15, v14, *(_QWORD *)(v14 + 8), v13);
      v17 = *(_QWORD *)(v12 + 16);
      if ( v17 == 0x1FFFFFFFFFFFFFELL )
        std::_Xlength_error("list<T> too long");
      *(_QWORD *)(v12 + 16) = v17 + 1;
      *(_QWORD *)(v14 + 8) = v16;
      **(_QWORD **)(v16 + 8) = v16;
      Command::~Command(v27);
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
0x18000a0dc  mov     [rsp-8+arg_10], rbx
0x18000a0e1  mov     [rsp-8+arg_18], rsi
0x18000a0e6  push    rbp
0x18000a0e7  push    r12
0x18000a0e9  push    r13
0x18000a0eb  push    r14
0x18000a0ed  push    r15
0x18000a0ef  lea     rbp, [rsp-10h]
0x18000a0f4  sub     rsp, 110h
0x18000a0fb  mov     rax, cs:__security_cookie
0x18000a102  xor     rax, rsp
0x18000a105  mov     [rbp+30h+var_30], rax
0x18000a109  mov     r12, rdx
0x18000a10c  mov     rsi, rcx
0x18000a10f  xor     r13d, r13d
0x18000a112  mov     [rsp+130h+cSubKeys], r13d
0x18000a117  mov     [rsp+130h+cbMaxSubKeyLen], r13d
0x18000a11c  mov     [rsp+130h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000a121  mov     [rsp+130h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000a126  mov     [rsp+130h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000a12b  mov     [rsp+130h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18000a130  mov     [rsp+130h+lpcValues], r13; lpcValues
0x18000a135  mov     [rsp+130h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000a13a  lea     rax, [rsp+130h+cbMaxSubKeyLen]
0x18000a13f  mov     [rsp+130h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000a144  lea     rax, [rsp+130h+cSubKeys]
0x18000a149  mov     [rsp+130h+lpcSubKeys], rax; unsigned int
0x18000a14e  xor     r9d, r9d; lpReserved
0x18000a151  xor     r8d, r8d; lpcchClass
0x18000a154  xor     edx, edx; lpClass
0x18000a156  call    cs:__imp_RegQueryInfoKeyW
0x18000a15c  mov     rcx, [rbp+38h]; this
0x18000a160  test    eax, eax
0x18000a162  jnz     loc_18000A315
0x18000a168  mov     edx, [rsp+130h+cbMaxSubKeyLen]
0x18000a16c  lea     eax, [rdx+1]
0x18000a16f  or      r8d, 0FFFFFFFFh
0x18000a173  cmp     eax, edx
0x18000a175  cmovnb  r8d, eax
0x18000a179  sbb     r9d, r9d
0x18000a17c  and     r9d, 80070216h; char *
0x18000a183  mov     [rsp+130h+cbMaxSubKeyLen], r8d
0x18000a188  mov     rcx, [rbp+38h]; this
0x18000a18c  cmp     eax, edx
0x18000a18e  jb      loc_18000A2EE
0x18000a194  xorps   xmm0, xmm0
0x18000a197  movdqu  xmmword ptr [rsp+130h+lpName], xmm0
0x18000a19d  mov     [rbp+30h+var_A8], r13
0x18000a1a1  mov     edx, r8d
0x18000a1a4  test    r8d, r8d
0x18000a1a7  jz      short loc_18000A1B3
0x18000a1a9  lea     rcx, [rsp+130h+lpName]
0x18000a1ae  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18000a1b3  mov     ebx, r13d
0x18000a1b6  cmp     [rsp+130h+cSubKeys], r13d
0x18000a1bb  jbe     loc_18000A2A3
0x18000a1c1  mov     eax, [rsp+130h+cbMaxSubKeyLen]
0x18000a1c5  mov     [rsp+130h+cchName], eax
0x18000a1c9  mov     [rsp+130h+lpcValues], r13; lpftLastWriteTime
0x18000a1ce  mov     [rsp+130h+lpcbMaxClassLen], r13; lpcchClass
0x18000a1d3  mov     [rsp+130h+lpcbMaxSubKeyLen], r13; lpClass
0x18000a1d8  mov     [rsp+130h+lpcSubKeys], r13; unsigned int
0x18000a1dd  lea     r9, [rsp+130h+cchName]; lpcchName
0x18000a1e2  mov     r8, [rsp+130h+lpName]; lpName
0x18000a1e7  mov     edx, ebx; dwIndex
0x18000a1e9  mov     rcx, rsi; hKey
0x18000a1ec  call    cs:__imp_RegEnumKeyExW
0x18000a1f2  mov     rcx, [rbp+38h]; this
0x18000a1f6  test    eax, eax
0x18000a1f8  jnz     loc_18000A300
0x18000a1fe  mov     [rsp+130h+phkResult], r13
0x18000a203  lea     rax, [rsp+130h+phkResult]
0x18000a208  mov     [rsp+130h+lpcSubKeys], rax; phkResult
0x18000a20d  mov     r9d, 20019h; samDesired
0x18000a213  xor     r8d, r8d; ulOptions
0x18000a216  mov     rdx, [rsp+130h+lpName]; lpSubKey
0x18000a21b  mov     rcx, rsi; hKey
0x18000a21e  call    cs:__imp_RegOpenKeyExW
0x18000a224  test    eax, eax
0x18000a226  jnz     short loc_18000A287
0x18000a228  mov     r14, [r12]
0x18000a22c  mov     r9, [rsp+130h+lpName]
0x18000a231  mov     r8, [rsp+130h+phkResult]
0x18000a236  lea     rdx, [rbp+30h+var_A0]
0x18000a23a  call    ?ParseCommand@RegistryConfig@@AEAA?AUCommand@@PEAUHKEY__@@PEBG@Z; RegistryConfig::ParseCommand(HKEY__ *,ushort const *)
0x18000a23f  nop
0x18000a240  mov     r15, [r14+8]
0x18000a244  mov     r9, rax
0x18000a247  mov     r8, [r15+8]
0x18000a24b  mov     rdx, r15
0x18000a24e  call    ??$_Buynode@UCommand@@@?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@1@PEAU21@0$$QEAUCommand@@@Z; std::_List_buy<Command>::_Buynode<Command>(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *,Command &&)
0x18000a253  mov     rdx, [r14+10h]
0x18000a257  mov     rcx, 1FFFFFFFFFFFFFEh
0x18000a261  sub     rcx, rdx
0x18000a264  cmp     rcx, 1
0x18000a268  jb      short loc_18000A2E0
0x18000a26a  lea     rcx, [rdx+1]
0x18000a26e  mov     [r14+10h], rcx
0x18000a272  mov     [r15+8], rax
0x18000a276  mov     rcx, [rax+8]
0x18000a27a  mov     [rcx], rax
0x18000a27d  lea     rcx, [rbp+30h+var_A0]; this
0x18000a281  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x18000a286  nop
0x18000a287  mov     rcx, [rsp+130h+phkResult]; hKey
0x18000a28c  test    rcx, rcx
0x18000a28f  jz      short loc_18000A297
0x18000a291  call    cs:__imp_RegCloseKey
0x18000a297  inc     ebx
0x18000a299  cmp     ebx, [rsp+130h+cSubKeys]
0x18000a29d  jb      loc_18000A1C1
0x18000a2a3  cmp     [rsp+130h+lpName], r13
0x18000a2a8  jz      short loc_18000A2B5
0x18000a2aa  mov     rcx, [rsp+130h+lpName]
0x18000a2af  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a2b5  mov     eax, ebx
0x18000a2b7  mov     rcx, [rbp+30h+var_30]
0x18000a2bb  xor     rcx, rsp; StackCookie
0x18000a2be  call    __security_check_cookie
0x18000a2c3  lea     r11, [rsp+130h+var_20]
0x18000a2cb  mov     rbx, [r11+40h]
0x18000a2cf  mov     rsi, [r11+48h]
0x18000a2d3  mov     rsp, r11
0x18000a2d6  pop     r15
0x18000a2d8  pop     r14
0x18000a2da  pop     r13
0x18000a2dc  pop     r12
0x18000a2de  pop     rbp
0x18000a2df  retn
0x18000a2e0  lea     rcx, aListTTooLong; "list<T> too long"
0x18000a2e7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000a2ee  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x18000a2f5  mov     edx, 43h ; 'C'; void *
0x18000a2fa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a300  mov     r9d, eax; char *
0x18000a303  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x18000a30a  mov     edx, 4Ch ; 'L'; void *
0x18000a30f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000a315  mov     r9d, eax; char *
0x18000a318  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x18000a31f  mov     edx, 40h ; '@'; void *
0x18000a324  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
