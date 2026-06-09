# GetSstpGroupIDFromQueryString

- ea: `0x180002610`
- end: `0x180002651`
- name: `GetSstpGroupIDFromQueryString`
- size: `65`
- prototype: `const wchar_t *__fastcall(const wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002610`

## import_xrefs

- `ntdll!wcsstr` at `0x180002631`
- `ntdll!wcsstr` at `0x180002631`

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
0x180002610  push    rbx
0x180002612  sub     rsp, 20h
0x180002616  xor     eax, eax
0x180002618  mov     rbx, rcx
0x18000261b  test    rcx, rcx
0x18000261e  jz      short loc_180002648
0x180002620  cmp     edx, 9
0x180002623  jb      short loc_180002648
0x180002625  cmp     [rcx], ax
0x180002628  jz      short loc_180002648
0x18000262a  lea     rdx, aTenant; "?tenant="
0x180002631  call    cs:__imp_wcsstr
0x180002638  nop     dword ptr [rax+rax+00h]
0x18000263d  cmp     rax, rbx
0x180002640  jnz     short loc_180002648
0x180002642  lea     rax, [rbx+10h]
0x180002646  jmp     short loc_18000264A
0x180002648  xor     eax, eax
0x18000264a  add     rsp, 20h
0x18000264e  pop     rbx
0x18000264f  retn
```
