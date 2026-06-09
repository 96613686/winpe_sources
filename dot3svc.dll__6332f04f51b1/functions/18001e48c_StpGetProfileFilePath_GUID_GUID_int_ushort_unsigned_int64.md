# StpGetProfileFilePath(_GUID *,_GUID *,int,ushort *,unsigned __int64)

- ea: `0x18001e48c`
- end: `0x18001e618`
- name: `?StpGetProfileFilePath@@YAKPEAU_GUID@@0HPEAG_K@Z`
- size: `396`
- prototype: `__int64 __fastcall(GUID *rguid, GUID *, int, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c338`
- `0x18001cbe4`
- `0x18001d828`

## callees

- `0x1800025f0`
- `0x180008c7c`
- `0x18001e48c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e503`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e577`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e503`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e577`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18001e4d2`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18001e4d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StpGetProfileFilePath(GUID *rguid, GUID *a2, int a3, unsigned __int16 *a4)
{
  HRESULT v7; // eax
  unsigned int v8; // ecx
  int v9; // eax
  OLECHAR sz[40]; // [rsp+50h] [rbp-2D8h] BYREF
  OLECHAR v12[40]; // [rsp+A0h] [rbp-288h] BYREF
  WCHAR pszPath[264]; // [rsp+F0h] [rbp-238h] BYREF

  v7 = SHGetFolderPathW(0, a3 != 0 ? 28 : 35, 0, 0, pszPath);
  v8 = v7;
  if ( v7 >= 0 )
    goto LABEL_5;
  if ( (v7 & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)v7;
  if ( !v8 )
  {
LABEL_5:
    StringFromGUID2(a2, sz, 39);
    if ( rguid )
    {
      StringFromGUID2(rguid, v12, 39);
      v9 = StringCchPrintfW(
             a4,
             0x104u,
             L"%s\\%s\\%s\\%s\\%s\\%s.%s",
             pszPath,
             L"Microsoft\\dot3svc",
             L"Profiles",
             L"Interfaces",
             v12,
             sz,
             L"xml");
    }
    else
    {
      v9 = StringCchPrintfW(
             a4,
             0x104u,
             L"%s\\%s\\%s\\%s\\%s.%s",
             pszPath,
             L"Microsoft\\dot3svc",
             L"Profiles",
             L"Machine",
             sz,
             L"xml");
    }
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        return (unsigned __int16)v9;
    }
    else
    {
      return 0;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18001e48c  push    rbx
0x18001e48e  push    rsi
0x18001e48f  push    rdi
0x18001e490  sub     rsp, 310h
0x18001e497  mov     rax, cs:__security_cookie
0x18001e49e  xor     rax, rsp
0x18001e4a1  mov     [rsp+328h+var_28], rax
0x18001e4a9  mov     rdi, rdx
0x18001e4ac  lea     rax, [rsp+328h+var_238]
0x18001e4b4  neg     r8d
0x18001e4b7  mov     [rsp+328h+pszPath], rax; pszPath
0x18001e4bc  mov     rsi, r9
0x18001e4bf  mov     rbx, rcx
0x18001e4c2  sbb     edx, edx
0x18001e4c4  xor     r9d, r9d; dwFlags
0x18001e4c7  and     edx, 0FFFFFFF9h
0x18001e4ca  xor     r8d, r8d; hToken
0x18001e4cd  add     edx, 23h ; '#'; csidl
0x18001e4d0  xor     ecx, ecx; hwnd
0x18001e4d2  call    cs:__imp_SHGetFolderPathW
0x18001e4d8  mov     ecx, eax
0x18001e4da  test    eax, eax
0x18001e4dc  jns     short loc_18001E4F5
0x18001e4de  and     eax, 1FFF0000h
0x18001e4e3  cmp     eax, 70000h
0x18001e4e8  jnz     short loc_18001E4ED
0x18001e4ea  movzx   ecx, cx
0x18001e4ed  test    ecx, ecx
0x18001e4ef  jnz     loc_18001E5FB
0x18001e4f5  mov     r8d, 27h ; '''; cchMax
0x18001e4fb  lea     rdx, [rsp+328h+sz]; lpsz
0x18001e500  mov     rcx, rdi; rguid
0x18001e503  call    cs:__imp_StringFromGUID2
0x18001e509  test    rbx, rbx
0x18001e50c  jnz     short loc_18001E566
0x18001e50e  lea     rax, aXml; "xml"
0x18001e515  mov     edx, 104h; unsigned __int64
0x18001e51a  mov     [rsp+328h+var_2E8], rax
0x18001e51f  lea     r9, [rsp+328h+var_238]
0x18001e527  lea     rax, [rsp+328h+sz]
0x18001e52c  mov     rcx, rsi; unsigned __int16 *
0x18001e52f  mov     [rsp+328h+var_2F0], rax
0x18001e534  lea     r8, aSSSSSS; "%s\\%s\\%s\\%s\\%s.%s"
0x18001e53b  lea     rax, aMachine_0; "Machine"
0x18001e542  mov     [rsp+328h+var_2F8], rax
0x18001e547  lea     rax, aProfiles; "Profiles"
0x18001e54e  mov     [rsp+328h+var_300], rax
0x18001e553  lea     rax, aMicrosoftDot3s; "Microsoft\\dot3svc"
0x18001e55a  mov     [rsp+328h+pszPath], rax
0x18001e55f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e564  jmp     short loc_18001E5E0
0x18001e566  mov     r8d, 27h ; '''; cchMax
0x18001e56c  lea     rdx, [rsp+328h+var_288]; lpsz
0x18001e574  mov     rcx, rbx; rguid
0x18001e577  call    cs:__imp_StringFromGUID2
0x18001e57d  lea     rax, aXml; "xml"
0x18001e584  mov     edx, 104h; unsigned __int64
0x18001e589  mov     [rsp+328h+var_2E0], rax
0x18001e58e  lea     r9, [rsp+328h+var_238]
0x18001e596  lea     rax, [rsp+328h+sz]
0x18001e59b  mov     rcx, rsi; unsigned __int16 *
0x18001e59e  mov     [rsp+328h+var_2E8], rax
0x18001e5a3  lea     r8, aSSSSSSS; "%s\\%s\\%s\\%s\\%s\\%s.%s"
0x18001e5aa  lea     rax, [rsp+328h+var_288]
0x18001e5b2  mov     [rsp+328h+var_2F0], rax
0x18001e5b7  lea     rax, aInterfaces; "Interfaces"
0x18001e5be  mov     [rsp+328h+var_2F8], rax
0x18001e5c3  lea     rax, aProfiles; "Profiles"
0x18001e5ca  mov     [rsp+328h+var_300], rax
0x18001e5cf  lea     rax, aMicrosoftDot3s; "Microsoft\\dot3svc"
0x18001e5d6  mov     [rsp+328h+pszPath], rax
0x18001e5db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e5e0  mov     ecx, eax
0x18001e5e2  test    eax, eax
0x18001e5e4  js      short loc_18001E5EA
0x18001e5e6  xor     ecx, ecx
0x18001e5e8  jmp     short loc_18001E5FB
0x18001e5ea  mov     eax, ecx
0x18001e5ec  and     eax, 1FFF0000h
0x18001e5f1  cmp     eax, 70000h
0x18001e5f6  jnz     short loc_18001E5FB
0x18001e5f8  movzx   ecx, cx
0x18001e5fb  mov     eax, ecx
0x18001e5fd  mov     rcx, [rsp+328h+var_28]
0x18001e605  xor     rcx, rsp; StackCookie
0x18001e608  call    __security_check_cookie
0x18001e60d  add     rsp, 310h
0x18001e614  pop     rdi
0x18001e615  pop     rsi
0x18001e616  pop     rbx
0x18001e617  retn
```
