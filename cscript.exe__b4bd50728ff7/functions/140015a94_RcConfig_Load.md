# RcConfig_Load

- ea: `0x140015a94`
- end: `0x140015ace`
- name: `RcConfig_Load`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140015ad4`

## callees

- `0x140015a94`

## import_xrefs

- `KERNEL32!LoadResource` at `0x140015ac7`
- `KERNEL32!FindResourceExW` at `0x140015aab`
- `KERNEL32!FindResourceExW` at `0x140015aab`

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
0x140015a94  push    rbx
0x140015a96  sub     rsp, 20h
0x140015a9a  xor     r9d, r9d; wLanguage
0x140015a9d  lea     rdx, Type; "MUI"
0x140015aa4  mov     rbx, rcx
0x140015aa7  lea     r8d, [r9+1]; lpName
0x140015aab  call    cs:__imp_FindResourceExW
0x140015ab1  test    rax, rax
0x140015ab4  jnz     short loc_140015ABC
0x140015ab6  add     rsp, 20h
0x140015aba  pop     rbx
0x140015abb  retn
0x140015abc  mov     rdx, rax
0x140015abf  mov     rcx, rbx
0x140015ac2  add     rsp, 20h
0x140015ac6  pop     rbx
0x140015ac7  jmp     cs:__imp_LoadResource
```
