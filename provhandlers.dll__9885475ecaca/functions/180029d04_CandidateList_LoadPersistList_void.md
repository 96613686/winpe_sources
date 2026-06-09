# CandidateList::LoadPersistList(void)

- ea: `0x180029d04`
- end: `0x180029de4`
- name: `?LoadPersistList@CandidateList@@IEAA_NXZ`
- size: `224`
- prototype: `char __fastcall(CandidateList *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800269e0`
- `0x1800276b0`
- `0x180027ab4`

## callees

- `0x180012390`
- `0x180026c90`
- `0x1800284c0`
- `0x180029d04`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180029d6f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029d6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029daf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029daf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029d5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029d5a`

## pseudocode

```c
char __fastcall CandidateList::LoadPersistList(CandidateList *this)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-48h]
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  void *v7[4]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  hKey = 0;
  v2 = CandidateList::ComposeFullListPath((__int64)this, (__int64)v7);
  if ( *(_QWORD *)(v2 + 24) >= 8u )
    v2 = *(_QWORD *)v2;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v2, 0, 0x2001Fu, &hKey);
  if ( v7[3] >= (void *)8 )
    operator delete(v7[0]);
  if ( v3 == 2 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
        (const char *)v3,
        phkResult);
    CandidateList::InitializePersistList(this, &hKey);
    if ( hKey )
      RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x180029d04  mov     [rsp+arg_8], rbx
0x180029d09  push    rdi
0x180029d0a  sub     rsp, 60h
0x180029d0e  mov     rax, cs:__security_cookie
0x180029d15  xor     rax, rsp
0x180029d18  mov     [rsp+68h+var_10], rax
0x180029d1d  mov     rdi, rcx
0x180029d20  mov     [rsp+68h+hKey], 0
0x180029d29  lea     rdx, [rsp+68h+var_30]
0x180029d2e  call    ?ComposeFullListPath@CandidateList@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CandidateList::ComposeFullListPath(void)
0x180029d33  cmp     qword ptr [rax+18h], 8
0x180029d38  jb      short loc_180029D3D
0x180029d3a  mov     rax, [rax]
0x180029d3d  lea     rcx, [rsp+68h+hKey]
0x180029d42  mov     qword ptr [rsp+68h+phkResult], rcx; unsigned int
0x180029d47  mov     r9d, 2001Fh; samDesired
0x180029d4d  xor     r8d, r8d; ulOptions
0x180029d50  mov     rdx, rax; lpSubKey
0x180029d53  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029d5a  call    cs:__imp_RegOpenKeyExW
0x180029d60  mov     ebx, eax
0x180029d62  cmp     [rsp+68h+var_18], 8
0x180029d68  jb      short loc_180029D75
0x180029d6a  mov     rcx, [rsp+68h+var_30]
0x180029d6f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180029d75  cmp     ebx, 2
0x180029d78  jnz     short loc_180029D8E
0x180029d7a  mov     rcx, [rsp+68h+hKey]; hKey
0x180029d7f  test    rcx, rcx
0x180029d82  jz      short loc_180029D8A
0x180029d84  call    cs:__imp_RegCloseKey
0x180029d8a  xor     al, al
0x180029d8c  jmp     short loc_180029DB7
0x180029d8e  mov     rcx, [rsp+68h]; this
0x180029d93  test    ebx, ebx
0x180029d95  jnz     short loc_180029DCF
0x180029d97  lea     rdx, [rsp+68h+hKey]
0x180029d9c  mov     rcx, rdi
0x180029d9f  call    ?InitializePersistList@CandidateList@@IEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CandidateList::InitializePersistList(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x180029da4  nop
0x180029da5  mov     rcx, [rsp+68h+hKey]; hKey
0x180029daa  test    rcx, rcx
0x180029dad  jz      short loc_180029DB5
0x180029daf  call    cs:__imp_RegCloseKey
0x180029db5  mov     al, 1
0x180029db7  mov     rcx, [rsp+68h+var_10]
0x180029dbc  xor     rcx, rsp; StackCookie
0x180029dbf  call    __security_check_cookie
0x180029dc4  mov     rbx, [rsp+68h+arg_8]
0x180029dc9  add     rsp, 60h
0x180029dcd  pop     rdi
0x180029dce  retn
0x180029dcf  mov     r9d, ebx; char *
0x180029dd2  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180029dd9  mov     edx, 124h; void *
0x180029dde  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
