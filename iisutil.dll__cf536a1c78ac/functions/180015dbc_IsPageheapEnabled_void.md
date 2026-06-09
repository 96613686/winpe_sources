# IsPageheapEnabled(void)

- ea: `0x180015dbc`
- end: `0x180015e1d`
- name: `?IsPageheapEnabled@@YAHXZ`
- size: `97`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012d10`

## callees

- `0x180015dbc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015dd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015dd8`

## string_xrefs

- `0x180015dd1`: `verifier.dll`

## pseudocode

```c
__int64 IsPageheapEnabled(void)
{
  __int64 result; // rax

  if ( dword_18005066C )
    return (unsigned int)dword_180050668;
  if ( GetModuleHandleW(L"verifier.dll") )
  {
    result = 1;
  }
  else
  {
    result = (__int64)NtCurrentPeb();
    if ( result )
      result = (*(_DWORD *)(result + 188) >> 25) & 1;
  }
  dword_180050668 = result;
  dword_18005066C = 1;
  return result;
}

```

## disassembly

```asm
0x180015dbc  sub     rsp, 28h
0x180015dc0  cmp     cs:dword_18005066C, 0
0x180015dc7  jz      short loc_180015DD1
0x180015dc9  mov     eax, cs:dword_180050668
0x180015dcf  jmp     short loc_180015E17
0x180015dd1  lea     rcx, aVerifierDll; "verifier.dll"
0x180015dd8  call    cs:__imp_GetModuleHandleW
0x180015ddf  nop     dword ptr [rax+rax+00h]
0x180015de4  mov     ecx, 1
0x180015de9  test    rax, rax
0x180015dec  jz      short loc_180015DF2
0x180015dee  mov     eax, ecx
0x180015df0  jmp     short loc_180015E0B
0x180015df2  mov     rax, gs:60h
0x180015dfb  test    rax, rax
0x180015dfe  jz      short loc_180015E0B
0x180015e00  mov     eax, [rax+0BCh]
0x180015e06  shr     eax, 19h
0x180015e09  and     eax, ecx
0x180015e0b  mov     cs:dword_180050668, eax
0x180015e11  mov     cs:dword_18005066C, ecx
0x180015e17  add     rsp, 28h
0x180015e1b  retn
```
