# CRegistry::~CRegistry(void)

- ea: `0x140005f20`
- end: `0x140005f3e`
- name: `??1CRegistry@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `25`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140005fc8`
- `0x1400068b8`
- `0x140006ab0`
- `0x14000c2bc`
- `0x14000dd80`
- `0x14000f8a0`
- `0x140020be8`
- `0x140020cf8`
- `0x1400212e4`
- `0x140021460`
- `0x140021a0c`
- `0x140021e40`
- `0x140022598`
- `0x140022f98`
- `0x140023070`
- `0x1400231c0`
- `0x140024768`
- `0x140024830`
- `0x1400249e0`
- `0x140036bd0`
- `0x140037bbc`
- `0x140045478`
- `0x140047170`
- `0x1400480c0`
- `0x1400572f8`

## callees

- `0x140005f20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005f2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005f2c`

## pseudocode

```c
void __fastcall CRegistry::~CRegistry(HKEY *this)
{
  HKEY v1; // rcx

  v1 = *this;
  if ( v1 )
    RegCloseKey(v1);
}

```

## disassembly

```asm
0x140005f20  sub     rsp, 28h
0x140005f24  mov     rcx, [rcx]; hKey
0x140005f27  test    rcx, rcx
0x140005f2a  jz      short loc_140005F38
0x140005f2c  call    cs:__imp_RegCloseKey
0x140005f33  nop     dword ptr [rax+rax+00h]
0x140005f38  add     rsp, 28h
0x140005f3c  retn
```
