# CUserProfile::OpenProfileListKey(ushort const *,HKEY__ * *,ulong *)

- ea: `0x180026d30`
- end: `0x180026e56`
- name: `?OpenProfileListKey@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z`
- size: `294`
- prototype: `int(CUserProfile *__hidden this, const unsigned __int16 *, HKEY *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800133d4`
- `0x180037544`

## callees

- `0x180013770`
- `0x180026d30`
- `0x180031060`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026d78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026d78`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026dce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026dce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026df4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026df4`

## string_xrefs

- `0x180026e2b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::OpenProfileListKey(
        CUserProfile *this,
        const unsigned __int16 *a2,
        HKEY *a3,
        unsigned int *a4)
{
  unsigned int v6; // eax
  LSTATUS ValueW; // eax
  bool v8; // sf
  HKEY v9; // rax
  HKEY v10; // rcx
  unsigned int v12; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CUserProfile *pcbData; // [rsp+50h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  pcbData = this;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  hkey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0xF003Fu, &hkey);
  if ( v6 == 2 )
    goto LABEL_14;
  if ( v6 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xB1F,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)v6,
            phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return v12;
  }
  if ( !a4 )
    goto LABEL_9;
  LODWORD(pcbData) = 4;
  ValueW = RegGetValueW(hkey, 0, L"State", 0x10u, 0, a4, (LPDWORD)&pcbData);
  v8 = ValueW < 0;
  if ( ValueW > 0 )
    v8 = 1;
  if ( v8 )
  {
LABEL_14:
    v10 = hkey;
  }
  else
  {
LABEL_9:
    v9 = hkey;
    v10 = 0;
    hkey = 0;
    *a3 = v9;
  }
  if ( v10 )
    RegCloseKey(v10);
  return 0;
}

```

## disassembly

```asm
0x180026d30  mov     [rsp+arg_8], rbx
0x180026d35  mov     [rsp+arg_0], rcx
0x180026d3a  push    rdi
0x180026d3b  sub     rsp, 40h
0x180026d3f  mov     qword ptr [r8], 0
0x180026d46  mov     rbx, r9
0x180026d49  mov     rdi, r8
0x180026d4c  test    r9, r9
0x180026d4f  jnz     loc_180026E1A
0x180026d55  lea     rax, [rsp+48h+hkey]
0x180026d5a  mov     [rsp+48h+hkey], 0
0x180026d63  mov     r9d, 0F003Fh; samDesired
0x180026d69  mov     [rsp+48h+phkResult], rax; unsigned int
0x180026d6e  xor     r8d, r8d; ulOptions
0x180026d71  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026d78  call    cs:__imp_RegOpenKeyExW
0x180026d7f  nop     dword ptr [rax+rax+00h]
0x180026d84  cmp     eax, 2
0x180026d87  jz      loc_180026E4F
0x180026d8d  test    eax, eax
0x180026d8f  jnz     loc_180026E26
0x180026d95  test    rbx, rbx
0x180026d98  jz      short loc_180026DE0
0x180026d9a  mov     rcx, [rsp+48h+hkey]; hkey
0x180026d9f  lea     rax, [rsp+48h+arg_0]
0x180026da4  mov     [rsp+48h+pcbData], rax; pcbData
0x180026da9  lea     r8, aState; "State"
0x180026db0  mov     [rsp+48h+pvData], rbx; pvData
0x180026db5  mov     r9d, 10h; dwFlags
0x180026dbb  xor     edx, edx; lpSubKey
0x180026dbd  mov     [rsp+48h+phkResult], 0; pdwType
0x180026dc6  mov     dword ptr [rsp+48h+arg_0], 4
0x180026dce  call    cs:__imp_RegGetValueW
0x180026dd5  nop     dword ptr [rax+rax+00h]
0x180026dda  test    eax, eax
0x180026ddc  jg      short loc_180026E0E
0x180026dde  js      short loc_180026E4F
0x180026de0  mov     rax, [rsp+48h+hkey]
0x180026de5  xor     ecx, ecx; hKey
0x180026de7  mov     [rsp+48h+hkey], rcx
0x180026dec  mov     [rdi], rax
0x180026def  test    rcx, rcx
0x180026df2  jz      short loc_180026E00
0x180026df4  call    cs:__imp_RegCloseKey
0x180026dfb  nop     dword ptr [rax+rax+00h]
0x180026e00  xor     eax, eax
0x180026e02  mov     rbx, [rsp+48h+arg_8]
0x180026e07  add     rsp, 40h
0x180026e0b  pop     rdi
0x180026e0c  retn
0x180026e0e  movzx   eax, ax
0x180026e11  or      eax, 80070000h
0x180026e16  test    eax, eax
0x180026e18  jmp     short loc_180026DDE
0x180026e1a  mov     dword ptr [r9], 0
0x180026e21  jmp     loc_180026D55
0x180026e26  mov     rcx, [rsp+48h]; this
0x180026e2b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180026e32  mov     r9d, eax; char *
0x180026e35  mov     edx, 0B1Fh; void *
0x180026e3a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026e3f  lea     rcx, [rsp+48h+hkey]
0x180026e44  mov     ebx, eax
0x180026e46  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026e4b  mov     eax, ebx
0x180026e4d  jmp     short loc_180026E02
0x180026e4f  mov     rcx, [rsp+48h+hkey]
0x180026e54  jmp     short loc_180026DEF
```
