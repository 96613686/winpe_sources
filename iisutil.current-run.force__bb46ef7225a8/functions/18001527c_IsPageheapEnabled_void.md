# IsPageheapEnabled(void)

- ea: `0x18001527c`
- end: `0x1800152d6`
- name: `?IsPageheapEnabled@@YAHXZ`
- size: `90`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800123b0`

## callees

- `0x18001527c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015298`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015298`

## string_xrefs

- `0x180015291`: `verifier.dll`

## pseudocode

```c
__int64 IsPageheapEnabled(void)
{
  __int64 result; // rax

  if ( dword_18004E67C )
    return (unsigned int)dword_18004E678;
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
  dword_18004E678 = result;
  dword_18004E67C = 1;
  return result;
}

```

## disassembly

```asm
0x18001527c  sub     rsp, 28h
0x180015280  cmp     cs:dword_18004E67C, 0
0x180015287  jz      short loc_180015291
0x180015289  mov     eax, cs:dword_18004E678
0x18001528f  jmp     short loc_1800152D1
0x180015291  lea     rcx, aVerifierDll; "verifier.dll"
0x180015298  call    cs:__imp_GetModuleHandleW
0x18001529e  mov     ecx, 1
0x1800152a3  test    rax, rax
0x1800152a6  jz      short loc_1800152AC
0x1800152a8  mov     eax, ecx
0x1800152aa  jmp     short loc_1800152C5
0x1800152ac  mov     rax, gs:60h
0x1800152b5  test    rax, rax
0x1800152b8  jz      short loc_1800152C5
0x1800152ba  mov     eax, [rax+0BCh]
0x1800152c0  shr     eax, 19h
0x1800152c3  and     eax, ecx
0x1800152c5  mov     cs:dword_18004E678, eax
0x1800152cb  mov     cs:dword_18004E67C, ecx
0x1800152d1  add     rsp, 28h
0x1800152d5  retn
```
