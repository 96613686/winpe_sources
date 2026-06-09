# DllUnregisterServer

- ea: `0x180013000`
- end: `0x1800130f1`
- name: `DllUnregisterServer`
- size: `241`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c848`
- `0x180013000`
- `0x180029010`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1800130b6`
- `ADVAPI32!RegDeleteValueW` at `0x1800130b6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800130a0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800130a0`
- `ADVAPI32!RegCloseKey` at `0x1800130c3`
- `ADVAPI32!RegCloseKey` at `0x1800130c3`

## string_xrefs

- `0x1800130af`: `DllSurrogate`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rbx
  __int64 (*v1)(void); // rax
  __int64 (*v2)(void); // rax
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  LSTATUS v4; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v0 = qword_180038600;
  if ( qword_180038600 )
  {
    while ( *(_QWORD *)v0 )
    {
      v1 = *(__int64 (**)(void))(v0 + 48);
      if ( !v1 || !v1() )
      {
        (*(void (__fastcall **)(_QWORD))(v0 + 8))(0);
        if ( _Module == 248 )
        {
          v2 = *(__int64 (**)(void))(v0 + 56);
          if ( !v2 )
            goto LABEL_10;
          v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)v2();
          ATL::AtlRegisterClassCategoriesHelper(*(const struct _GUID **)v0, v3, 0);
        }
      }
      if ( _Module == 176 )
        v0 += 56;
      else
LABEL_10:
        v0 += 72;
    }
  }
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AppID\\{DCBCADF5-DB1b-4764-9320-9a5082af1581}", 0, 0x20006u, &hKey) )
    return -2147221168;
  v4 = RegDeleteValueW(hKey, L"DllSurrogate");
  RegCloseKey(hKey);
  if ( (v4 & 0xFFFFFFFD) == 0 )
    return 0;
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return v4;
}

```

## disassembly

```asm
0x180013000  push    rbx
0x180013002  sub     rsp, 30h
0x180013006  mov     rbx, cs:qword_180038600
0x18001300d  test    rbx, rbx
0x180013010  jz      short loc_180013076
0x180013012  jmp     short loc_180013070
0x180013014  mov     rax, [rbx+30h]
0x180013018  test    rax, rax
0x18001301b  jz      short loc_180013027
0x18001301d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013022  test    rax, rax
0x180013025  jnz     short loc_18001305A
0x180013027  mov     rax, [rbx+8]
0x18001302b  xor     ecx, ecx
0x18001302d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013032  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0F8h; ATL::CComModule _Module
0x18001303c  jnz     short loc_18001305A
0x18001303e  mov     rax, [rbx+38h]
0x180013042  test    rax, rax
0x180013045  jz      short loc_18001306C
0x180013047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001304c  mov     rcx, [rbx]; struct _GUID *
0x18001304f  xor     r8d, r8d; int
0x180013052  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180013055  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18001305a  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x180013064  jnz     short loc_18001306C
0x180013066  add     rbx, 38h ; '8'
0x18001306a  jmp     short loc_180013070
0x18001306c  add     rbx, 48h ; 'H'
0x180013070  cmp     qword ptr [rbx], 0
0x180013074  jnz     short loc_180013014
0x180013076  lea     rax, [rsp+38h+hKey]
0x18001307b  mov     [rsp+38h+hKey], 0
0x180013084  mov     r9d, 20006h; samDesired
0x18001308a  mov     [rsp+38h+phkResult], rax; phkResult
0x18001308f  xor     r8d, r8d; ulOptions
0x180013092  lea     rdx, SubKey; "AppID\\{DCBCADF5-DB1b-4764-9320-9a5082a"...
0x180013099  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800130a0  call    cs:__imp_RegOpenKeyExW
0x1800130a6  test    eax, eax
0x1800130a8  jnz     short loc_1800130E6
0x1800130aa  mov     rcx, [rsp+38h+hKey]; hKey
0x1800130af  lea     rdx, ValueName; "DllSurrogate"
0x1800130b6  call    cs:__imp_RegDeleteValueW
0x1800130bc  mov     rcx, [rsp+38h+hKey]; hKey
0x1800130c1  mov     ebx, eax
0x1800130c3  call    cs:__imp_RegCloseKey
0x1800130c9  test    ebx, 0FFFFFFFDh
0x1800130cf  jz      short loc_1800130E2
0x1800130d1  test    ebx, ebx
0x1800130d3  jle     short loc_1800130DE
0x1800130d5  movzx   ebx, bx
0x1800130d8  or      ebx, 80070000h
0x1800130de  mov     eax, ebx
0x1800130e0  jmp     short loc_1800130EB
0x1800130e2  xor     eax, eax
0x1800130e4  jmp     short loc_1800130EB
0x1800130e6  mov     eax, 80040150h
0x1800130eb  add     rsp, 30h
0x1800130ef  pop     rbx
0x1800130f0  retn
```
