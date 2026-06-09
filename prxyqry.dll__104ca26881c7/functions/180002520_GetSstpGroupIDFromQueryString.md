# GetSstpGroupIDFromQueryString

- ea: `0x180002520`
- end: `0x18000255a`
- name: `GetSstpGroupIDFromQueryString`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002520`

## import_xrefs

- `ntdll!wcsstr` at `0x180002541`
- `ntdll!wcsstr` at `0x180002541`

## pseudocode

```c
const wchar_t *__fastcall GetSstpGroupIDFromQueryString(const wchar_t *a1, unsigned int a2)
{
  if ( a1 && a2 >= 9 && *a1 && wcsstr(a1, L"?tenant=") == a1 )
    return a1 + 8;
  else
    return 0;
}

```

## disassembly

```asm
0x180002520  push    rbx
0x180002522  sub     rsp, 20h
0x180002526  xor     eax, eax
0x180002528  mov     rbx, rcx
0x18000252b  test    rcx, rcx
0x18000252e  jz      short loc_180002552
0x180002530  cmp     edx, 9
0x180002533  jb      short loc_180002552
0x180002535  cmp     [rcx], ax
0x180002538  jz      short loc_180002552
0x18000253a  lea     rdx, aTenant; "?tenant="
0x180002541  call    cs:__imp_wcsstr
0x180002547  cmp     rax, rbx
0x18000254a  jnz     short loc_180002552
0x18000254c  lea     rax, [rbx+10h]
0x180002550  jmp     short loc_180002554
0x180002552  xor     eax, eax
0x180002554  add     rsp, 20h
0x180002558  pop     rbx
0x180002559  retn
```
