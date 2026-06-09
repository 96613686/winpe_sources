# KnownUiccs::Enumerate(void)

- ea: `0x180034f2c`
- end: `0x180034fda`
- name: `?Enumerate@KnownUiccs@@SA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKnownUicc@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKnownUicc@@@std@@@2@@std@@XZ`
- size: `174`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800308d0`

## callees

- `0x180012390`
- `0x1800332a4`
- `0x180034f2c`
- `0x180036294`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034fac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034fac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034f8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034f8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall KnownUiccs::Enumerate(_QWORD *a1)
{
  unsigned int v2; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,KnownUicc>>>::_Buyheadnode();
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegUicc, 0, 9u, &hKey);
  if ( v2 )
  {
    if ( v2 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x153,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v2,
        phkResult);
  }
  else
  {
    ForEachRegSubKey__lambda_8b4099812ee4e38ebdb49a8aae6d6b5e_(hKey);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x180034f2c  mov     [rsp+arg_0], rcx
0x180034f31  push    rbx
0x180034f32  sub     rsp, 40h
0x180034f36  mov     rbx, rcx
0x180034f39  mov     [rsp+48h+var_18], 0
0x180034f41  mov     qword ptr [rcx], 0
0x180034f48  mov     qword ptr [rcx+8], 0
0x180034f50  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKnownUicc@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKnownUicc@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKnownUicc@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,KnownUicc>>>::_Buyheadnode(void)
0x180034f55  mov     [rbx], rax
0x180034f58  mov     [rsp+48h+var_18], 1
0x180034f60  mov     [rsp+48h+hKey], 0
0x180034f69  lea     rax, [rsp+48h+hKey]
0x180034f6e  mov     qword ptr [rsp+48h+phkResult], rax; unsigned int
0x180034f73  mov     r9d, 9; samDesired
0x180034f79  xor     r8d, r8d; ulOptions
0x180034f7c  mov     rdx, cs:?gc_wszRegUicc@@3PEBGEB; lpSubKey
0x180034f83  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034f8a  call    cs:__imp_RegOpenKeyExW
0x180034f90  test    eax, eax
0x180034f92  jnz     short loc_180034FBB
0x180034f94  mov     rdx, rbx
0x180034f97  mov     rcx, [rsp+48h+hKey]; hKey
0x180034f9c  call    ForEachRegSubKey__lambda_8b4099812ee4e38ebdb49a8aae6d6b5e___; ForEachRegSubKey__lambda_8b4099812ee4e38ebdb49a8aae6d6b5e_
0x180034fa1  nop
0x180034fa2  mov     rcx, [rsp+48h+hKey]; hKey
0x180034fa7  test    rcx, rcx
0x180034faa  jz      short loc_180034FB2
0x180034fac  call    cs:__imp_RegCloseKey
0x180034fb2  mov     rax, rbx
0x180034fb5  add     rsp, 40h
0x180034fb9  pop     rbx
0x180034fba  retn
0x180034fbb  cmp     eax, 2
0x180034fbe  jz      short loc_180034FA2
0x180034fc0  mov     rcx, [rsp+48h]; this
0x180034fc5  mov     r9d, eax; char *
0x180034fc8  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034fcf  mov     edx, 153h; void *
0x180034fd4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
