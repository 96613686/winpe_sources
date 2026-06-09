# CRegistry::~CRegistry(void)

- ea: `0x1400021e4`
- end: `0x140002205`
- name: `??1CRegistry@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140004c30`
- `0x140004d20`
- `0x140004dd0`

## callees

- `0x1400021e4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400021f6`
- `ADVAPI32!RegCloseKey` at `0x1400021f6`

## pseudocode

```c
void __fastcall CRegistry::~CRegistry(HKEY *this)
{
  if ( *(_BYTE *)this )
  {
    RegCloseKey(this[1]);
    *(_BYTE *)this = 0;
  }
}

```

## disassembly

```asm
0x1400021e4  push    rbx
0x1400021e6  sub     rsp, 20h
0x1400021ea  cmp     byte ptr [rcx], 0
0x1400021ed  mov     rbx, rcx
0x1400021f0  jz      short loc_1400021FF
0x1400021f2  mov     rcx, [rcx+8]; hKey
0x1400021f6  call    cs:__imp_RegCloseKey
0x1400021fc  mov     byte ptr [rbx], 0
0x1400021ff  add     rsp, 20h
0x140002203  pop     rbx
0x140002204  retn
```
