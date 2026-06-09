# QASF_DllRegisterServer

- ea: `0x180001ee0`
- end: `0x180002092`
- name: `QASF_DllRegisterServer`
- size: `434`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001460`
- `0x180001ee0`
- `0x180002450`
- `0x1800026d4`
- `0x18000277c`
- `0x1800028b0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180001fd2`
- `KERNEL32!lstrlenW` at `0x18000200c`
- `KERNEL32!lstrlenW` at `0x180001fd2`
- `KERNEL32!lstrlenW` at `0x18000200c`
- `ADVAPI32!RegCloseKey` at `0x180002047`
- `ADVAPI32!RegCloseKey` at `0x180002047`
- `ADVAPI32!RegSetValueExW` at `0x180001ffb`
- `ADVAPI32!RegSetValueExW` at `0x18000203a`
- `ADVAPI32!RegSetValueExW` at `0x180001ffb`
- `ADVAPI32!RegSetValueExW` at `0x18000203a`
- `ADVAPI32!RegCreateKeyW` at `0x180001f9c`
- `ADVAPI32!RegCreateKeyW` at `0x180001f9c`
- `ole32!StringFromGUID2` at `0x180001f7c`
- `ole32!StringFromGUID2` at `0x180001f7c`

## pseudocode

```c
HRESULT __stdcall QASF_DllRegisterServer()
{
  unsigned int v0; // r9d
  const struct _GUID *v1; // r14
  unsigned int v2; // esi
  unsigned int i; // edi
  const struct _GUID *v4; // rcx
  const struct _GUID *v5; // rbx
  const WCHAR *lpData; // r15
  HRESULT MediaTypePath; // ebx
  LSTATUS v8; // eax
  int v9; // eax
  int v10; // eax
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR ValueName[12]; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR sz[104]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[200]; // [rsp+120h] [rbp+20h] BYREF

  v1 = 0;
  v2 = 0;
  for ( i = 0; i < 2; ++i )
  {
    v4 = v1;
    v5 = (const struct _GUID *)*((_QWORD *)&off_180021800 + 2 * (int)i);
    lpData = (const WCHAR *)*((_QWORD *)&off_180021800 + 2 * (int)i + 1);
    if ( v1 != v5 )
      v1 = (const struct _GUID *)*((_QWORD *)&off_180021800 + 2 * (int)i);
    ++v2;
    phkResult = 0;
    if ( v4 != v5 )
      v2 = 0;
    if ( !v2 )
      DeleteMediaTypeFile(v4, v5);
    MediaTypePath = GetMediaTypePath(v4, v5, SubKey, v0);
    if ( MediaTypePath < 0 )
      return MediaTypePath;
    MediaTypePath = StringFromGUID2(&CLSID_WMAsfReader, sz, 100);
    if ( MediaTypePath < 0 )
      return MediaTypePath;
    v8 = RegCreateKeyW(HKEY_CLASSES_ROOT, SubKey, &phkResult);
    MediaTypePath = v8;
    if ( !v8 )
    {
      StringCchPrintfW(ValueName, 0xAu, L"%d", v2);
      v9 = lstrlenW(lpData);
      MediaTypePath = RegSetValueExW(phkResult, ValueName, 0, 1u, (const BYTE *)lpData, 2 * v9 + 2);
      if ( !MediaTypePath )
      {
        v10 = lstrlenW(sz);
        MediaTypePath = RegSetValueExW(phkResult, L"Source Filter", 0, 1u, (const BYTE *)sz, 2 * v10 + 2);
      }
      RegCloseKey(phkResult);
      if ( MediaTypePath <= 0 )
        goto LABEL_19;
      MediaTypePath = (unsigned __int16)MediaTypePath;
      goto LABEL_18;
    }
    if ( v8 > 0 )
    {
      MediaTypePath = (unsigned __int16)v8;
LABEL_18:
      MediaTypePath |= 0x80070000;
    }
LABEL_19:
    if ( MediaTypePath < 0 )
      return MediaTypePath;
  }
  return AMovieDllRegisterServer2(1, &off_180021800);
}

```

## disassembly

```asm
0x180001ee0  push    rbp
0x180001ee2  push    rbx
0x180001ee3  push    rsi
0x180001ee4  push    rdi
0x180001ee5  push    r14
0x180001ee7  push    r15
0x180001ee9  lea     rbp, [rsp-1C8h]
0x180001ef1  sub     rsp, 2C8h
0x180001ef8  mov     rax, cs:__security_cookie
0x180001eff  xor     rax, rsp
0x180001f02  mov     [rbp+1F0h+var_40], rax
0x180001f09  xor     r14d, r14d
0x180001f0c  xor     esi, esi
0x180001f0e  xor     edi, edi
0x180001f10  lea     rdx, off_180021800
0x180001f17  cmp     edi, 2
0x180001f1a  jnb     loc_180002065
0x180001f20  mov     rcx, r14
0x180001f23  movsxd  r8, edi
0x180001f26  add     r8, r8
0x180001f29  mov     rbx, [rdx+r8*8]
0x180001f2d  mov     r15, [rdx+r8*8+8]
0x180001f32  cmp     r14, rbx
0x180001f35  cmovnz  r14, rbx
0x180001f39  xor     eax, eax
0x180001f3b  inc     esi
0x180001f3d  mov     [rsp+2F0h+phkResult], rax
0x180001f42  cmp     rcx, rbx
0x180001f45  cmovnz  esi, eax
0x180001f48  test    esi, esi
0x180001f4a  jnz     short loc_180001F54
0x180001f4c  mov     rdx, rbx
0x180001f4f  call    DeleteMediaTypeFile
0x180001f54  lea     r8, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180001f58  mov     rdx, rbx; struct _GUID *
0x180001f5b  call    ?GetMediaTypePath@@YAJPEBU_GUID@@0PEAGK@Z; GetMediaTypePath(_GUID const *,_GUID const *,ushort *,ulong)
0x180001f60  mov     ebx, eax
0x180001f62  test    eax, eax
0x180001f64  js      loc_180002071
0x180001f6a  mov     r8d, 64h ; 'd'; cchMax
0x180001f70  lea     rdx, [rsp+2F0h+sz]; lpsz
0x180001f75  lea     rcx, CLSID_WMAsfReader; rguid
0x180001f7c  call    cs:__imp_StringFromGUID2
0x180001f82  mov     ebx, eax
0x180001f84  test    eax, eax
0x180001f86  js      loc_180002071
0x180001f8c  lea     r8, [rsp+2F0h+phkResult]; phkResult
0x180001f91  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180001f98  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180001f9c  call    cs:__imp_RegCreateKeyW
0x180001fa2  mov     ebx, eax
0x180001fa4  test    eax, eax
0x180001fa6  jz      short loc_180001FB6
0x180001fa8  jle     loc_18000205A
0x180001fae  movzx   ebx, ax
0x180001fb1  jmp     loc_180002054
0x180001fb6  mov     r9d, esi
0x180001fb9  lea     r8, aD; "%d"
0x180001fc0  mov     edx, 0Ah; unsigned __int64
0x180001fc5  lea     rcx, [rsp+2F0h+ValueName]; unsigned __int16 *
0x180001fca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001fcf  mov     rcx, r15; lpString
0x180001fd2  call    cs:__imp_lstrlenW
0x180001fd8  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x180001fdd  lea     rdx, [rsp+2F0h+ValueName]; lpValueName
0x180001fe2  mov     r9d, 1; dwType
0x180001fe8  xor     r8d, r8d; Reserved
0x180001feb  lea     eax, ds:2[rax*2]
0x180001ff2  mov     [rsp+2F0h+cbData], eax; cbData
0x180001ff6  mov     [rsp+2F0h+lpData], r15; lpData
0x180001ffb  call    cs:__imp_RegSetValueExW
0x180002001  mov     ebx, eax
0x180002003  test    eax, eax
0x180002005  jnz     short loc_180002042
0x180002007  lea     rcx, [rsp+2F0h+sz]; lpString
0x18000200c  call    cs:__imp_lstrlenW
0x180002012  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x180002017  lea     r9d, [rbx+1]; dwType
0x18000201b  xor     r8d, r8d; Reserved
0x18000201e  lea     rdx, ValueName; "Source Filter"
0x180002025  lea     eax, ds:2[rax*2]
0x18000202c  mov     [rsp+2F0h+cbData], eax; cbData
0x180002030  lea     rax, [rsp+2F0h+sz]
0x180002035  mov     [rsp+2F0h+lpData], rax; lpData
0x18000203a  call    cs:__imp_RegSetValueExW
0x180002040  mov     ebx, eax
0x180002042  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x180002047  call    cs:__imp_RegCloseKey
0x18000204d  test    ebx, ebx
0x18000204f  jle     short loc_18000205A
0x180002051  movzx   ebx, bx
0x180002054  or      ebx, 80070000h
0x18000205a  inc     edi
0x18000205c  test    ebx, ebx
0x18000205e  js      short loc_180002071
0x180002060  jmp     loc_180001F10
0x180002065  mov     ecx, 1
0x18000206a  call    AMovieDllRegisterServer2
0x18000206f  mov     ebx, eax
0x180002071  mov     eax, ebx
0x180002073  mov     rcx, [rbp+1F0h+var_40]
0x18000207a  xor     rcx, rsp; StackCookie
0x18000207d  call    __security_check_cookie
0x180002082  add     rsp, 2C8h
0x180002089  pop     r15
0x18000208b  pop     r14
0x18000208d  pop     rdi
0x18000208e  pop     rsi
0x18000208f  pop     rbx
0x180002090  pop     rbp
0x180002091  retn
```
