# LoadCellState(void)

- ea: `0x180011060`
- end: `0x1800111c3`
- name: `?LoadCellState@@YA?AV?$unique_ptr@VCellState@@U?$default_delete@VCellState@@@std@@@std@@XZ`
- size: `355`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180010b20`
- `0x180010bf0`

## callees

- `0x180002034`
- `0x18000fe50`
- `0x180011060`
- `0x180012390`
- `0x1800128a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800110c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800110c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800110c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011184`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011194`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800110c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011184`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011194`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110f3`

## string_xrefs

- `0x1800110e8`: `Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall LoadCellState(_QWORD *a1)
{
  unsigned int v2; // eax
  HKEY v3; // rdi
  DWORD LastError; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rdi
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HKEY hKey; // [rsp+68h] [rbp+28h] BYREF
  HKEY v13; // [rsp+70h] [rbp+30h] BYREF
  _QWORD *v14; // [rsp+78h] [rbp+38h]

  hKey = 0;
  v13 = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegCellularEmulator, 0, 0x20019u, &v13);
  if ( v2 )
    goto LABEL_8;
  v3 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v3);
    SetLastError(LastError);
  }
  hKey = 0;
  v2 = RegOpenKeyExW(v13, L"Config", 0, 0x20019u, &hKey);
  if ( v2 )
  {
LABEL_8:
    if ( v2 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
        (const char *)v2,
        phkResult);
    v6 = operator new(0x30u);
    v8 = v6;
    v14 = v6;
    if ( v6 )
    {
      *v6 = 0;
      v6[1] = 0;
      v6[2] = 0;
      v6[3] = 0;
      v6[4] = 0;
      v6[3] = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::shared_ptr<Modem>>>>::_Buyheadnode(v7);
      *((_DWORD *)v8 + 10) = 0;
    }
    else
    {
      v8 = 0;
    }
    *a1 = v8;
  }
  else
  {
    v5 = operator new(0x30u);
    v14 = v5;
    if ( v5 )
      v5 = (_QWORD *)CellStateFromKey((__int64)v5, hKey);
    *a1 = v5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v13 )
    RegCloseKey(v13);
  return a1;
}

```

## disassembly

```asm
0x180011060  mov     [rsp-18h+arg_0], rbx
0x180011065  push    rbp
0x180011066  push    rsi
0x180011067  push    rdi
0x180011068  mov     rbp, rsp
0x18001106b  sub     rsp, 40h
0x18001106f  mov     rsi, rcx
0x180011072  mov     [rbp+hKey], 0
0x18001107a  mov     [rbp+arg_10], 0
0x180011082  lea     rax, [rbp+arg_10]
0x180011086  mov     qword ptr [rsp+40h+phkResult], rax; unsigned int
0x18001108b  mov     r9d, 20019h; samDesired
0x180011091  xor     r8d, r8d; ulOptions
0x180011094  mov     rdx, cs:?gc_wszRegCellularEmulator@@3PEBGEB; lpSubKey
0x18001109b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800110a2  call    cs:__imp_RegOpenKeyExW
0x1800110a8  test    eax, eax
0x1800110aa  jnz     short loc_180011120
0x1800110ac  mov     rdi, [rbp+hKey]
0x1800110b0  test    rdi, rdi
0x1800110b3  jz      short loc_1800110CE
0x1800110b5  call    cs:__imp_GetLastError
0x1800110bb  mov     ebx, eax
0x1800110bd  mov     rcx, rdi; hKey
0x1800110c0  call    cs:__imp_RegCloseKey
0x1800110c6  mov     ecx, ebx; dwErrCode
0x1800110c8  call    cs:__imp_SetLastError
0x1800110ce  mov     [rbp+hKey], 0
0x1800110d6  lea     rax, [rbp+hKey]
0x1800110da  mov     qword ptr [rsp+40h+phkResult], rax; phkResult
0x1800110df  mov     r9d, 20019h; samDesired
0x1800110e5  xor     r8d, r8d; ulOptions
0x1800110e8  lea     rdx, ?c_configKeyName@@3QBGB; "Config"
0x1800110ef  mov     rcx, [rbp+arg_10]; hKey
0x1800110f3  call    cs:__imp_RegOpenKeyExW
0x1800110f9  test    eax, eax
0x1800110fb  jnz     short loc_180011120
0x1800110fd  lea     ecx, [rax+30h]; Size
0x180011100  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011105  mov     [rbp+arg_18], rax
0x180011109  test    rax, rax
0x18001110c  jz      short loc_18001111B
0x18001110e  mov     rdx, [rbp+hKey]
0x180011112  mov     rcx, rax
0x180011115  call    ?CellStateFromKey@@YA?AVCellState@@PEAUHKEY__@@@Z; CellStateFromKey(HKEY__ *)
0x18001111a  nop
0x18001111b  mov     [rsi], rax
0x18001111e  jmp     short loc_18001117B
0x180011120  cmp     eax, 2
0x180011123  jnz     loc_1800111AA
0x180011129  lea     ecx, [rax+2Eh]; Size
0x18001112c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011131  mov     rdi, rax
0x180011134  mov     [rbp+arg_18], rax
0x180011138  test    rax, rax
0x18001113b  jz      short loc_180011176
0x18001113d  mov     qword ptr [rax], 0
0x180011144  mov     qword ptr [rax+8], 0
0x18001114c  mov     qword ptr [rax+10h], 0
0x180011154  mov     qword ptr [rax+18h], 0
0x18001115c  mov     qword ptr [rax+20h], 0
0x180011164  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::shared_ptr<Modem>>>>::_Buyheadnode(void)
0x180011169  mov     [rdi+18h], rax
0x18001116d  mov     dword ptr [rdi+28h], 0
0x180011174  jmp     short loc_180011178
0x180011176  xor     edi, edi
0x180011178  mov     [rsi], rdi
0x18001117b  mov     rcx, [rbp+hKey]; hKey
0x18001117f  test    rcx, rcx
0x180011182  jz      short loc_18001118B
0x180011184  call    cs:__imp_RegCloseKey
0x18001118a  nop
0x18001118b  mov     rcx, [rbp+arg_10]; hKey
0x18001118f  test    rcx, rcx
0x180011192  jz      short loc_18001119A
0x180011194  call    cs:__imp_RegCloseKey
0x18001119a  mov     rax, rsi
0x18001119d  mov     rbx, [rsp+40h+arg_0]
0x1800111a2  add     rsp, 40h
0x1800111a6  pop     rdi
0x1800111a7  pop     rsi
0x1800111a8  pop     rbp
0x1800111a9  retn
0x1800111aa  mov     rcx, [rbp+18h]; this
0x1800111ae  mov     r9d, eax; char *
0x1800111b1  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800111b8  mov     edx, 38h ; '8'; void *
0x1800111bd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
