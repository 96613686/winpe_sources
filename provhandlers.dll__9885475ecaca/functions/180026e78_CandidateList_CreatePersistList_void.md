# CandidateList::CreatePersistList(void)

- ea: `0x180026e78`
- end: `0x180026f5b`
- name: `?CreatePersistList@CandidateList@@IEAAXXZ`
- size: `227`
- prototype: `void __fastcall(CandidateList *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800269e0`

## callees

- `0x180012390`
- `0x180026c90`
- `0x180026e78`
- `0x1800284c0`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180026f0c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026f0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026f2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026f2a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026eed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026eed`

## pseudocode

```c
void __fastcall CandidateList::CreatePersistList(CandidateList *this)
{
  __int64 v2; // rax
  unsigned int v3; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-68h]
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  void *v6[4]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  hKey = 0;
  v2 = CandidateList::ComposeFullListPath((__int64)this, (__int64)v6);
  if ( *(_QWORD *)(v2 + 24) >= 8u )
    v2 = *(_QWORD *)v2;
  v3 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v2, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
      (const char *)v3,
      dwOptions);
  if ( v6[3] >= (void *)8 )
    operator delete(v6[0]);
  CandidateList::InitializePersistList(this, &hKey);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180026e78  push    rbx
0x180026e7a  sub     rsp, 80h
0x180026e81  mov     rax, cs:__security_cookie
0x180026e88  xor     rax, rsp
0x180026e8b  mov     [rsp+88h+var_10], rax
0x180026e90  mov     rbx, rcx
0x180026e93  mov     [rsp+88h+hKey], 0
0x180026e9c  lea     rdx, [rsp+88h+var_30]
0x180026ea1  call    ?ComposeFullListPath@CandidateList@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CandidateList::ComposeFullListPath(void)
0x180026ea6  nop
0x180026ea7  cmp     qword ptr [rax+18h], 8
0x180026eac  jb      short loc_180026EB1
0x180026eae  mov     rax, [rax]
0x180026eb1  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x180026eba  lea     rcx, [rsp+88h+hKey]
0x180026ebf  mov     [rsp+88h+phkResult], rcx; phkResult
0x180026ec4  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180026ecd  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x180026ed5  mov     [rsp+88h+dwOptions], 0; unsigned int
0x180026edd  xor     r9d, r9d; lpClass
0x180026ee0  xor     r8d, r8d; Reserved
0x180026ee3  mov     rdx, rax; lpSubKey
0x180026ee6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026eed  call    cs:__imp_RegCreateKeyExW
0x180026ef3  mov     rcx, [rsp+88h]; this
0x180026efb  test    eax, eax
0x180026efd  jnz     short loc_180026F46
0x180026eff  cmp     [rsp+88h+var_18], 8
0x180026f05  jb      short loc_180026F12
0x180026f07  mov     rcx, [rsp+88h+var_30]
0x180026f0c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026f12  lea     rdx, [rsp+88h+hKey]
0x180026f17  mov     rcx, rbx
0x180026f1a  call    ?InitializePersistList@CandidateList@@IEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CandidateList::InitializePersistList(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x180026f1f  nop
0x180026f20  mov     rcx, [rsp+88h+hKey]; hKey
0x180026f25  test    rcx, rcx
0x180026f28  jz      short loc_180026F30
0x180026f2a  call    cs:__imp_RegCloseKey
0x180026f30  mov     rcx, [rsp+88h+var_10]
0x180026f35  xor     rcx, rsp; StackCookie
0x180026f38  call    __security_check_cookie
0x180026f3d  add     rsp, 80h
0x180026f44  pop     rbx
0x180026f45  retn
0x180026f46  mov     r9d, eax; char *
0x180026f49  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180026f50  mov     edx, 12Eh; void *
0x180026f55  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
