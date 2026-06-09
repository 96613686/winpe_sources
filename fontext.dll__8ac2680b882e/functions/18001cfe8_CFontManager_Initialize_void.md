# CFontManager::Initialize(void)

- ea: `0x18001cfe8`
- end: `0x18001d023`
- name: `?Initialize@CFontManager@@QEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(CFontManager *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011384`
- `0x180012a60`
- `0x180021d90`
- `0x1800269cc`

## import_xrefs

- `SHELL32!__imp_IsUserAnAdmin` at `0x18001cff1`
- `SHELL32!__imp_IsUserAnAdmin` at `0x18001cff1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d017`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d017`

## pseudocode

```c
HRESULT __fastcall CFontManager::Initialize(CFontManager *this)
{
  *((_DWORD *)this + 12) = IsUserAnAdmin();
  return CoCreateInstance(&CLSID_FontManager, 0, 1u, &GUID_935ad8eb_cbf8_4fd3_8f4f_385f55258f2e, (LPVOID *)this + 5);
}

```

## disassembly

```asm
0x18001cfe8  push    rbx
0x18001cfea  sub     rsp, 30h
0x18001cfee  mov     rbx, rcx
0x18001cff1  call    cs:__imp_IsUserAnAdmin
0x18001cff7  xor     edx, edx; pUnkOuter
0x18001cff9  mov     [rbx+30h], eax
0x18001cffc  lea     r9, _GUID_935ad8eb_cbf8_4fd3_8f4f_385f55258f2e; riid
0x18001d003  lea     rax, [rbx+28h]
0x18001d007  lea     rcx, CLSID_FontManager; rclsid
0x18001d00e  mov     [rsp+38h+ppv], rax; ppv
0x18001d013  lea     r8d, [rdx+1]; dwClsContext
0x18001d017  call    cs:__imp_CoCreateInstance
0x18001d01d  add     rsp, 30h
0x18001d021  pop     rbx
0x18001d022  retn
```
