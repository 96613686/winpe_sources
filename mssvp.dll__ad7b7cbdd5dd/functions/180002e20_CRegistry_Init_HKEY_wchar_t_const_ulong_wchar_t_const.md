# CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)

- ea: `0x180002e20`
- end: `0x180002f50`
- name: `?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z`
- size: `304`
- prototype: `int(CRegistry *__hidden this, HKEY, const wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002cc0`
- `0x18002ecc8`
- `0x180034aa4`

## callees

- `0x180002e20`
- `0x180006270`
- `0x18003833c`
- `0x180038474`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002eee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002eee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e5f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180002e97`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180002e97`

## pseudocode

```c
__int64 __fastcall CRegistry::Init(CRegistry *this, HKEY a2, wchar_t *a3, __int64 a4, const wchar_t *a5)
{
  HKEY v8; // rcx
  const wchar_t *v9; // rcx
  bool v10; // al
  wchar_t *v11; // rdx
  LSTATUS v12; // eax
  signed int v13; // ebx
  __int64 result; // rax
  struct CSearchRegistryRedirectHelper *v15; // [rsp+30h] [rbp-258h] BYREF
  ATL::CAtlException *v16; // [rsp+38h] [rbp-250h] BYREF
  wchar_t v17[264]; // [rsp+40h] [rbp-248h] BYREF
  void *retaddr; // [rsp+288h] [rbp+0h]

  if ( *((_DWORD *)this + 42) )
  {
    v8 = (HKEY)*((_QWORD *)this + 22);
    if ( v8 )
    {
      RegCloseKey(v8);
      *((_QWORD *)this + 22) = 0;
    }
  }
  SetLastError(0);
  *((_DWORD *)this + 42) = 1;
  v15 = 0;
  v10 = a2 == HKEY_LOCAL_MACHINE
     && a3
     && (unsigned __int8)RtlIsStateSeparationEnabled()
     && GetSearchRegistryRedirect(v9, &v15)
     && (int)CSearchRegistryRedirectHelper::MapRegistryKeyPath((const wchar_t *)v15, a3, v17) >= 0;
  v11 = v17;
  if ( !v10 )
    v11 = a3;
  v12 = RegOpenKeyExW(a2, v11, 0, 0x20019u, (PHKEY)this + 22);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 < 0 )
    *((_QWORD *)this + 22) = 0;
  try
  {
    (*(void (__fastcall **)(char *, wchar_t *, _QWORD, __int64))(*((_QWORD *)this + 1) + 32LL))(
      (char *)this + 8,
      a3,
      0,
      0xFFFFFFFFLL);
    result = (unsigned int)v13;
  }
  catch ( ATL::CAtlException *v16 )
  {
    return *(unsigned int *)v16;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      152,
      "onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx");
  }
  return result;
}

```

## disassembly

```asm
0x180002e20  push    rbx
0x180002e22  push    rsi
0x180002e23  push    rdi
0x180002e24  push    r14
0x180002e26  push    r15
0x180002e28  sub     rsp, 260h
0x180002e2f  mov     rax, cs:__security_cookie
0x180002e36  xor     rax, rsp
0x180002e39  mov     [rsp+288h+var_38], rax
0x180002e41  mov     r14, r8
0x180002e44  mov     rbx, rdx
0x180002e47  mov     rdi, rcx
0x180002e4a  cmp     dword ptr [rcx+0A8h], 0
0x180002e51  jz      short loc_180002E70
0x180002e53  mov     rcx, [rcx+0B0h]; hKey
0x180002e5a  test    rcx, rcx
0x180002e5d  jz      short loc_180002E70
0x180002e5f  call    cs:__imp_RegCloseKey
0x180002e65  xor     esi, esi
0x180002e67  mov     [rdi+0B0h], rsi
0x180002e6e  jmp     short loc_180002E72
0x180002e70  xor     esi, esi
0x180002e72  xor     ecx, ecx; dwErrCode
0x180002e74  call    cs:__imp_SetLastError
0x180002e7a  mov     dword ptr [rdi+0A8h], 1
0x180002e84  mov     [rsp+288h+var_258], rsi
0x180002e89  cmp     rbx, 0FFFFFFFF80000002h
0x180002e90  jnz     short loc_180002EC9
0x180002e92  test    r14, r14
0x180002e95  jz      short loc_180002EC9
0x180002e97  call    cs:__imp_RtlIsStateSeparationEnabled
0x180002e9d  test    al, al
0x180002e9f  jz      short loc_180002EC9
0x180002ea1  lea     rdx, [rsp+288h+var_258]; struct CSearchRegistryRedirectHelper **
0x180002ea6  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x180002eab  test    al, al
0x180002ead  jz      short loc_180002EC9
0x180002eaf  lea     r8, [rsp+288h+var_248]; wchar_t *
0x180002eb4  mov     rdx, r14; wchar_t *
0x180002eb7  mov     rcx, [rsp+288h+var_258]; this
0x180002ebc  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x180002ec1  test    eax, eax
0x180002ec3  js      short loc_180002EC9
0x180002ec5  mov     al, 1
0x180002ec7  jmp     short loc_180002ECB
0x180002ec9  xor     al, al
0x180002ecb  lea     r15, [rdi+0B0h]
0x180002ed2  lea     rdx, [rsp+288h+var_248]
0x180002ed7  test    al, al
0x180002ed9  cmovz   rdx, r14; lpSubKey
0x180002edd  mov     [rsp+288h+phkResult], r15; phkResult
0x180002ee2  mov     r9d, 20019h; samDesired
0x180002ee8  xor     r8d, r8d; ulOptions
0x180002eeb  mov     rcx, rbx; hKey
0x180002eee  call    cs:__imp_RegOpenKeyExW
0x180002ef4  mov     ebx, eax
0x180002ef6  test    eax, eax
0x180002ef8  jle     short loc_180002F03
0x180002efa  movzx   ebx, ax
0x180002efd  or      ebx, 80070000h
0x180002f03  test    ebx, ebx
0x180002f05  jns     short loc_180002F0A
0x180002f07  mov     [r15], rsi
0x180002f0a  lea     rcx, [rdi+8]
0x180002f0e  mov     rax, [rcx]
0x180002f11  mov     r9d, 0FFFFFFFFh
0x180002f17  xor     r8d, r8d
0x180002f1a  mov     rdx, r14
0x180002f1d  mov     rax, [rax+20h]
0x180002f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f26  nop
0x180002f27  mov     eax, ebx
0x180002f29  jmp     short loc_180002F31
0x180002f2b  jmp     short $+2
0x180002f2d  mov     eax, dword ptr [rsp+288h+var_258]
0x180002f31  mov     rcx, [rsp+288h+var_38]
0x180002f39  xor     rcx, rsp; StackCookie
0x180002f3c  call    __security_check_cookie
0x180002f41  add     rsp, 260h
0x180002f48  pop     r15
0x180002f4a  pop     r14
0x180002f4c  pop     rdi
0x180002f4d  pop     rsi
0x180002f4e  pop     rbx
0x180002f4f  retn
```
