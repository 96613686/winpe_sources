# CachedAdapterInformation::~CachedAdapterInformation(void)

- ea: `0x140006700`
- end: `0x140006726`
- name: `??1CachedAdapterInformation@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(char **this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400115fa`
- `0x140011a76`

## callees

- `0x140006334`
- `0x140006700`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000671a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000671a`

## pseudocode

```c
void __fastcall CachedAdapterInformation::~CachedAdapterInformation(char **this)
{
  std::wstring::~wstring(this + 5);
  if ( *this )
    RegCloseKey((HKEY)*this);
}

```

## disassembly

```asm
0x140006700  push    rbx
0x140006702  sub     rsp, 20h
0x140006706  mov     rbx, rcx
0x140006709  add     rcx, 28h ; '('
0x14000670d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140006712  mov     rcx, [rbx]; hKey
0x140006715  test    rcx, rcx
0x140006718  jz      short loc_140006720
0x14000671a  call    cs:__imp_RegCloseKey
0x140006720  add     rsp, 20h
0x140006724  pop     rbx
0x140006725  retn
```
