# CandidateList::Clear(void)

- ea: `0x180026bb0`
- end: `0x180026c8a`
- name: `?Clear@CandidateList@@QEAAXXZ`
- size: `218`
- prototype: `void __fastcall(CandidateList *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d570`
- `0x1800308d0`

## callees

- `0x180012390`
- `0x180026bb0`
- `0x18002b17c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026c5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026c5f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180026c31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180026c31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026c14`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026c14`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CandidateList::Clear(CandidateList *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 5);
  if ( v2 )
  {
    (**v2)(v2, 1);
    *((_QWORD *)this + 5) = 0;
  }
  hKey = 0;
  v3 = (const WCHAR *)&CandidateList::m_regParent;
  if ( (unsigned __int64)qword_1800526A8 >= 8 )
    v3 = CandidateList::m_regParent;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x10009u, &hKey);
  if ( v4 )
  {
    if ( v4 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
        (const char *)v4,
        phkResult);
  }
  else
  {
    v5 = (const WCHAR *)((char *)this + 8);
    if ( *((_QWORD *)this + 4) >= 8u )
      v5 = *(const WCHAR **)v5;
    v6 = RegDeleteTreeW(hKey, v5);
    if ( v6 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
        (const char *)v6,
        phkResult);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180026bb0  push    rbx
0x180026bb2  sub     rsp, 30h
0x180026bb6  mov     rbx, rcx
0x180026bb9  mov     rcx, [rcx+28h]
0x180026bbd  test    rcx, rcx
0x180026bc0  jz      short loc_180026BDA
0x180026bc2  mov     rax, [rcx]
0x180026bc5  mov     edx, 1
0x180026bca  mov     rax, [rax]
0x180026bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bd2  mov     qword ptr [rbx+28h], 0
0x180026bda  mov     [rsp+38h+hKey], 0
0x180026be3  lea     rdx, ?m_regParent@CandidateList@@1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CandidateList::m_regParent
0x180026bea  cmp     cs:qword_1800526A8, 8
0x180026bf2  cmovnb  rdx, cs:?m_regParent@CandidateList@@1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; lpSubKey
0x180026bfa  lea     rax, [rsp+38h+hKey]
0x180026bff  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x180026c04  mov     r9d, 10009h; samDesired
0x180026c0a  xor     r8d, r8d; ulOptions
0x180026c0d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026c14  call    cs:__imp_RegOpenKeyExW
0x180026c1a  test    eax, eax
0x180026c1c  jnz     short loc_180026C6B
0x180026c1e  lea     rdx, [rbx+8]
0x180026c22  cmp     qword ptr [rdx+18h], 8
0x180026c27  jb      short loc_180026C2C
0x180026c29  mov     rdx, [rdx]; lpSubKey
0x180026c2c  mov     rcx, [rsp+38h+hKey]; hKey
0x180026c31  call    cs:__imp_RegDeleteTreeW
0x180026c37  mov     rcx, [rsp+38h]; this
0x180026c3c  test    eax, eax
0x180026c3e  jz      short loc_180026C55
0x180026c40  mov     r9d, eax; char *
0x180026c43  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180026c4a  mov     edx, 10Bh; void *
0x180026c4f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026c54  nop
0x180026c55  mov     rcx, [rsp+38h+hKey]; hKey
0x180026c5a  test    rcx, rcx
0x180026c5d  jz      short loc_180026C65
0x180026c5f  call    cs:__imp_RegCloseKey
0x180026c65  add     rsp, 30h
0x180026c69  pop     rbx
0x180026c6a  retn
0x180026c6b  cmp     eax, 2
0x180026c6e  jz      short loc_180026C55
0x180026c70  mov     rcx, [rsp+38h]; this
0x180026c75  mov     r9d, eax; char *
0x180026c78  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180026c7f  mov     edx, 10Fh; void *
0x180026c84  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
