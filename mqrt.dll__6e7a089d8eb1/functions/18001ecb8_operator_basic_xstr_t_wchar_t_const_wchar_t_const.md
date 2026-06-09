# operator==(basic_xstr_t<wchar_t> const &,wchar_t const *)

- ea: `0x18001ecb8`
- end: `0x18001ecf6`
- name: `??8@YA_NAEBV?$basic_xstr_t@_W@@PEB_W@Z`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001f2ac`

## callees

- `0x18001ecb8`
- `0x180023c72`

## string_xrefs

- `0x18001ecc5`: `xmlns`

## pseudocode

```c
char __fastcall operator==(const wchar_t **a1)
{
  __int64 v1; // rbx
  char result; // al

  v1 = *(int *)a1;
  if ( wcsncmp_0(a1[1], L"xmlns", (unsigned int)v1) )
    return 0;
  result = 1;
  if ( aXmlns[v1] )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18001ecb8  mov     [rsp+arg_0], rbx
0x18001ecbd  push    rdi
0x18001ecbe  sub     rsp, 20h
0x18001ecc2  movsxd  rbx, dword ptr [rcx]
0x18001ecc5  lea     rdi, aXmlns; "xmlns"
0x18001eccc  mov     rcx, [rcx+8]; String1
0x18001ecd0  mov     r8d, ebx; MaxCount
0x18001ecd3  mov     rdx, rdi; String2
0x18001ecd6  call    wcsncmp_0
0x18001ecdb  xor     ecx, ecx
0x18001ecdd  test    eax, eax
0x18001ecdf  jnz     short loc_18001ECE9
0x18001ece1  mov     al, 1
0x18001ece3  cmp     [rdi+rbx*2], cx
0x18001ece7  jz      short loc_18001ECEB
0x18001ece9  mov     al, cl
0x18001eceb  mov     rbx, [rsp+28h+arg_0]
0x18001ecf0  add     rsp, 20h
0x18001ecf4  pop     rdi
0x18001ecf5  retn
```
