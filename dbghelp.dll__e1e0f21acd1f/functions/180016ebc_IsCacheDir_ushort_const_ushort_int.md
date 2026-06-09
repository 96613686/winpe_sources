# IsCacheDir(ushort const *,ushort *,int)

- ea: `0x180016ebc`
- end: `0x180016f2e`
- name: `?IsCacheDir@@YAHPEBGPEAGH@Z`
- size: `114`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180011e08`
- `0x18001a5fc`
- `0x18001b03c`
- `0x1801a8ed0`

## callees

- `0x180012e6c`
- `0x180016ebc`
- `0x1801a82d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180016ed9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180016ed9`

## string_xrefs

- `0x180016ecf`: `cache*`

## pseudocode

```c
__int64 __fastcall IsCacheDir(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  const unsigned __int16 *v5; // r8

  if ( (unsigned int)_o__wcsnicmp(a1, L"cache*", 6) )
    return 0;
  v5 = a1 + 6;
  if ( !a1[6] || *v5 == 42 )
  {
    if ( !word_1802B0BBA )
      SymSetHomeDirectoryW(0, 0);
    v5 = &word_1802B0BBA;
  }
  wcscpy_s_ex(a2, 0x105u, v5);
  return 1;
}

```

## disassembly

```asm
0x180016ebc  mov     [rsp+arg_0], rbx
0x180016ec1  push    rdi
0x180016ec2  sub     rsp, 20h
0x180016ec6  mov     rdi, rdx
0x180016ec9  mov     r8d, 6
0x180016ecf  lea     rdx, aCache_0; "cache*"
0x180016ed6  mov     rbx, rcx
0x180016ed9  call    cs:__imp__o__wcsnicmp
0x180016edf  xor     ecx, ecx; hProcess
0x180016ee1  test    eax, eax
0x180016ee3  jz      short loc_180016EF2
0x180016ee5  xor     eax, eax
0x180016ee7  mov     rbx, [rsp+28h+arg_0]
0x180016eec  add     rsp, 20h
0x180016ef0  pop     rdi
0x180016ef1  retn
0x180016ef2  lea     r8, [rbx+0Ch]
0x180016ef6  cmp     [r8], cx
0x180016efa  jz      short loc_180016F03
0x180016efc  cmp     word ptr [r8], 2Ah ; '*'
0x180016f01  jnz     short loc_180016F1A
0x180016f03  cmp     cs:word_1802B0BBA, cx
0x180016f0a  jnz     short loc_180016F13
0x180016f0c  xor     edx, edx; dir
0x180016f0e  call    SymSetHomeDirectoryW
0x180016f13  lea     r8, word_1802B0BBA; unsigned __int16 *
0x180016f1a  mov     edx, 105h; unsigned __int64
0x180016f1f  mov     rcx, rdi; unsigned __int16 *
0x180016f22  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x180016f27  mov     eax, 1
0x180016f2c  jmp     short loc_180016EE7
```
