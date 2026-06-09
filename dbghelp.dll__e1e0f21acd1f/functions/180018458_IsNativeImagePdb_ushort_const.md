# IsNativeImagePdb(ushort const *)

- ea: `0x180018458`
- end: `0x180018528`
- name: `?IsNativeImagePdb@@YA_NPEBG@Z`
- size: `208`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c04`

## callees

- `0x180018458`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800184b7`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800184b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800184cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800184cf`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800184aa`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800184aa`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800184e4`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180018510`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800184e4`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180018510`

## pseudocode

```c
bool __fastcall IsNativeImagePdb(const unsigned __int16 *a1)
{
  size_t v1; // rbx
  wchar_t v3[3]; // [rsp+4Ah] [rbp-43Eh]
  wchar_t Source[264]; // [rsp+50h] [rbp-438h] BYREF
  wchar_t Ext[264]; // [rsp+260h] [rbp-228h] BYREF

  _wsplitpath_s(a1, 0, 0, 0, 0, Source, 0x101u, Ext, 0x101u);
  v1 = wcsnlen(Source, 0x101u);
  return !(unsigned int)_o__wcsicmp(Ext, L".pdb")
      && v1 >= 3
      && (unsigned __int16)_o_towlower(v3[v1 + 2]) == 105
      && (unsigned __int16)_o_towlower(v3[v1 + 1]) == 110
      && v3[v1] == 46;
}

```

## disassembly

```asm
0x180018458  push    rbx
0x18001845a  sub     rsp, 480h
0x180018461  mov     rax, cs:__security_cookie
0x180018468  xor     rax, rsp
0x18001846b  mov     [rsp+488h+var_18], rax
0x180018473  mov     ebx, 101h
0x180018478  lea     rax, [rsp+488h+var_228]
0x180018480  mov     [rsp+488h+ExtCount], rbx; ExtCount
0x180018485  xor     r9d, r9d; Dir
0x180018488  mov     [rsp+488h+Ext], rax; Ext
0x18001848d  xor     r8d, r8d; DriveCount
0x180018490  lea     rax, [rsp+488h+Source]
0x180018495  mov     [rsp+488h+FilenameCount], rbx; FilenameCount
0x18001849a  mov     [rsp+488h+Filename], rax; Filename
0x18001849f  xor     edx, edx; Drive
0x1800184a1  mov     [rsp+488h+DirCount], 0; DirCount
0x1800184aa  call    cs:__imp__wsplitpath_s
0x1800184b0  mov     edx, ebx; MaxCount
0x1800184b2  lea     rcx, [rsp+488h+Source]; Source
0x1800184b7  call    cs:__imp_wcsnlen
0x1800184bd  lea     rdx, aPdb_3; ".pdb"
0x1800184c4  mov     rbx, rax
0x1800184c7  lea     rcx, [rsp+488h+var_228]
0x1800184cf  call    cs:__imp__o__wcsicmp
0x1800184d5  test    eax, eax
0x1800184d7  jnz     short loc_1800184F0
0x1800184d9  cmp     rbx, 3
0x1800184dd  jb      short loc_1800184F0
0x1800184df  movzx   ecx, [rsp+rbx*2+488h+var_43A]
0x1800184e4  call    cs:__imp__o_towlower
0x1800184ea  cmp     ax, 69h ; 'i'
0x1800184ee  jz      short loc_18001850B
0x1800184f0  xor     al, al
0x1800184f2  mov     rcx, [rsp+488h+var_18]
0x1800184fa  xor     rcx, rsp; StackCookie
0x1800184fd  call    __security_check_cookie
0x180018502  add     rsp, 480h
0x180018509  pop     rbx
0x18001850a  retn
0x18001850b  movzx   ecx, [rsp+rbx*2+488h+var_43C]
0x180018510  call    cs:__imp__o_towlower
0x180018516  cmp     ax, 6Eh ; 'n'
0x18001851a  jnz     short loc_1800184F0
0x18001851c  cmp     [rsp+rbx*2+488h+var_43E], 2Eh ; '.'
0x180018522  jnz     short loc_1800184F0
0x180018524  mov     al, 1
0x180018526  jmp     short loc_1800184F2
```
