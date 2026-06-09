# SecUtil::CSecurityDescriptor::SetDacl(int,_ACL *,int)

- ea: `0x180023a4c`
- end: `0x180023aa6`
- name: `?SetDacl@CSecurityDescriptor@SecUtil@@QEAAXHPEAU_ACL@@H@Z`
- size: `90`
- prototype: `void(SecUtil::CSecurityDescriptor *__hidden this, int, struct _ACL *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003970`
- `0x180020be0`

## callees

- `0x180005c00`
- `0x18001e194`
- `0x180023a4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a63`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023a59`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023a59`

## string_xrefs

- `0x180023a78`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x180023a8b`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x180023a69`: `[UtilSecurity] SetSecurityDescriptorDacl failed. 0x%08x`

## pseudocode

```c
void __fastcall SecUtil::CSecurityDescriptor::SetDacl(SecUtil::CSecurityDescriptor *this, __int64 a2, struct _ACL *a3)
{
  const wchar_t *LastError; // rbx
  unsigned int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !SetSecurityDescriptorDacl(this, 1, a3, 0) )
  {
    LastError = (const wchar_t *)GetLastError();
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\secutil\\\\secutil.cxx\"",
      (const wchar_t *)0xC4,
      (__int64)L"[UtilSecurity] SetSecurityDescriptorDacl failed. 0x%08x",
      LastError);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
      (const char *)(unsigned int)LastError,
      v4);
  }
}

```

## disassembly

```asm
0x180023a4c  push    rbx; unsigned int
0x180023a4e  sub     rsp, 20h
0x180023a52  xor     r9d, r9d; bDaclDefaulted
0x180023a55  lea     edx, [r9+1]; bDaclPresent
0x180023a59  call    cs:__imp_SetSecurityDescriptorDacl
0x180023a5f  test    eax, eax
0x180023a61  jnz     short loc_180023AA0
0x180023a63  call    cs:__imp_GetLastError
0x180023a69  lea     r8, aUtilsecuritySe; "[UtilSecurity] SetSecurityDescriptorDac"...
0x180023a70  mov     edx, 0C4h; wchar_t *
0x180023a75  mov     r9d, eax; wchar_t *
0x180023a78  lea     rcx, aOnecoreuapBase_7; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180023a7f  mov     ebx, eax
0x180023a81  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180023a86  mov     rcx, [rsp+28h]; this
0x180023a8b  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\search\\com"...
0x180023a92  mov     r9d, ebx; char *
0x180023a95  mov     edx, 0C5h; void *
0x180023a9a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180023aa0  add     rsp, 20h
0x180023aa4  pop     rbx
0x180023aa5  retn
```
