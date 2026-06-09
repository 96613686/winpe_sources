# RcConfig_Load

- ea: `0x180022bfc`
- end: `0x180022c36`
- name: `RcConfig_Load`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180022c3c`

## callees

- `0x180022bfc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180022c2f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180022c13`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180022c13`

## pseudocode

```c
HRSRC __fastcall RcConfig_Load(HMODULE a1)
{
  HRSRC result; // rax

  result = FindResourceExW(a1, L"MUI", (LPCWSTR)1, 0);
  if ( result )
    return (HRSRC)LoadResource(a1, result);
  return result;
}

```

## disassembly

```asm
0x180022bfc  push    rbx
0x180022bfe  sub     rsp, 20h
0x180022c02  xor     r9d, r9d; wLanguage
0x180022c05  lea     rdx, Type; "MUI"
0x180022c0c  mov     rbx, rcx
0x180022c0f  lea     r8d, [r9+1]; lpName
0x180022c13  call    cs:__imp_FindResourceExW
0x180022c19  test    rax, rax
0x180022c1c  jnz     short loc_180022C24
0x180022c1e  add     rsp, 20h
0x180022c22  pop     rbx
0x180022c23  retn
0x180022c24  mov     rdx, rax
0x180022c27  mov     rcx, rbx
0x180022c2a  add     rsp, 20h
0x180022c2e  pop     rbx
0x180022c2f  jmp     cs:__imp_LoadResource
```
