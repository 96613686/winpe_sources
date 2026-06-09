# AddThreadingModel(wchar_t const *,wchar_t const *)

- ea: `0x18001f5ac`
- end: `0x18001f733`
- name: `?AddThreadingModel@@YAJPEB_W0@Z`
- size: `391`
- prototype: `int(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002107c`

## callees

- `0x180014130`
- `0x18001f4f4`
- `0x18001f53c`
- `0x18001f5ac`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f6d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f6d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f6ee`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f6ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f694`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f694`

## string_xrefs

- `0x18001f6cc`: `ThreadingModel`
- `0x18001f6e2`: `ThreadingModel`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddThreadingModel(const wchar_t *a1, const BYTE *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v8[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v9; // [rsp+54h] [rbp-ACh]

  TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(v8);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v8[0] + 32LL))(v8, L"\\", v9, 0xFFFFFFFFLL);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v8[0] + 32LL))(v8, a1, v9, 0xFFFFFFFFLL);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v8[0] + 32LL))(v8, L"\\", v9, 0xFFFFFFFFLL);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v8[0] + 32LL))(
    v8,
    L"InprocServer32",
    v9,
    0xFFFFFFFFLL);
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, (LPCWSTR)v8[1], 0, 0x2001Fu, &hKey);
  if ( !v4 )
  {
    if ( a2 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)&a2[2 * v5] );
      v4 = RegSetValueExW(hKey, L"ThreadingModel", 0, 1u, a2, 2 * v5 + 2);
    }
    else
    {
      RegDeleteValueW(hKey, L"ThreadingModel");
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
  }
  TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v8);
  return v4;
}

```

## disassembly

```asm
0x18001f5ac  mov     [rsp-8+arg_10], rbx
0x18001f5b1  push    rbp
0x18001f5b2  push    rsi
0x18001f5b3  push    rdi
0x18001f5b4  lea     rbp, [rsp-770h]
0x18001f5bc  sub     rsp, 870h
0x18001f5c3  mov     rax, cs:__security_cookie
0x18001f5ca  xor     rax, rsp
0x18001f5cd  mov     [rbp+780h+var_20], rax
0x18001f5d4  mov     rdi, rdx
0x18001f5d7  mov     rbx, rcx
0x18001f5da  lea     rcx, [rsp+880h+var_840]
0x18001f5df  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@PEB_W@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(wchar_t const *)
0x18001f5e4  nop
0x18001f5e5  mov     rax, [rsp+880h+var_840]
0x18001f5ea  or      esi, 0FFFFFFFFh
0x18001f5ed  mov     r9d, esi
0x18001f5f0  mov     r8d, [rsp+880h+var_82C]
0x18001f5f5  lea     rdx, asc_180031388; "\\"
0x18001f5fc  lea     rcx, [rsp+880h+var_840]
0x18001f601  mov     rax, [rax+20h]
0x18001f605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f60a  mov     rax, [rsp+880h+var_840]
0x18001f60f  mov     r9d, esi
0x18001f612  mov     r8d, [rsp+880h+var_82C]
0x18001f617  mov     rdx, rbx
0x18001f61a  lea     rcx, [rsp+880h+var_840]
0x18001f61f  mov     rax, [rax+20h]
0x18001f623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f628  mov     rax, [rsp+880h+var_840]
0x18001f62d  mov     r9d, esi
0x18001f630  mov     r8d, [rsp+880h+var_82C]
0x18001f635  lea     rdx, asc_180031388; "\\"
0x18001f63c  lea     rcx, [rsp+880h+var_840]
0x18001f641  mov     rax, [rax+20h]
0x18001f645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f64a  mov     rax, [rsp+880h+var_840]
0x18001f64f  mov     r9d, esi
0x18001f652  mov     r8d, [rsp+880h+var_82C]
0x18001f657  lea     rdx, aInprocserver32; "InprocServer32"
0x18001f65e  lea     rcx, [rsp+880h+var_840]
0x18001f663  mov     rax, [rax+20h]
0x18001f667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f66c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f670  mov     [rsp+880h+hKey], rsi
0x18001f675  lea     rax, [rsp+880h+hKey]
0x18001f67a  mov     [rsp+880h+phkResult], rax; phkResult
0x18001f67f  mov     r9d, 2001Fh; samDesired
0x18001f685  xor     r8d, r8d; ulOptions
0x18001f688  mov     rdx, [rsp+880h+lpSubKey]; lpSubKey
0x18001f68d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001f694  call    cs:__imp_RegOpenKeyExW
0x18001f69a  mov     ebx, eax
0x18001f69c  xor     ecx, ecx
0x18001f69e  test    eax, eax
0x18001f6a0  jnz     short loc_18001F705
0x18001f6a2  test    rdi, rdi
0x18001f6a5  jz      short loc_18001F6E2
0x18001f6a7  mov     rax, rsi
0x18001f6aa  inc     rax
0x18001f6ad  cmp     [rdi+rax*2], cx
0x18001f6b1  jnz     short loc_18001F6AA
0x18001f6b3  lea     eax, ds:2[rax*2]
0x18001f6ba  mov     [rsp+880h+cbData], eax; cbData
0x18001f6be  mov     [rsp+880h+phkResult], rdi; lpData
0x18001f6c3  mov     r9d, 1; dwType
0x18001f6c9  xor     r8d, r8d; Reserved
0x18001f6cc  lea     rdx, ValueName; "ThreadingModel"
0x18001f6d3  mov     rcx, [rsp+880h+hKey]; hKey
0x18001f6d8  call    cs:__imp_RegSetValueExW
0x18001f6de  mov     ebx, eax
0x18001f6e0  jmp     short loc_18001F6F4
0x18001f6e2  lea     rdx, ValueName; "ThreadingModel"
0x18001f6e9  mov     rcx, [rsp+880h+hKey]; hKey
0x18001f6ee  call    cs:__imp_RegDeleteValueW
0x18001f6f4  mov     rcx, [rsp+880h+hKey]; hKey
0x18001f6f9  cmp     rcx, rsi
0x18001f6fc  jz      short loc_18001F705
0x18001f6fe  call    cs:__imp_RegCloseKey
0x18001f704  nop
0x18001f705  lea     rcx, [rsp+880h+var_840]
0x18001f70a  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x18001f70f  mov     eax, ebx
0x18001f711  mov     rcx, [rbp+780h+var_20]
0x18001f718  xor     rcx, rsp; StackCookie
0x18001f71b  call    __security_check_cookie
0x18001f720  mov     rbx, [rsp+880h+arg_10]
0x18001f728  add     rsp, 870h
0x18001f72f  pop     rdi
0x18001f730  pop     rsi
0x18001f731  pop     rbp
0x18001f732  retn
```
