# DeleteCurrentUserKey

- ea: `0x18000c704`
- end: `0x18000c730`
- name: `DeleteCurrentUserKey`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c738`

## callees

- `0x18000c704`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000c715`
- `ADVAPI32!RegCloseKey` at `0x18000c715`

## pseudocode

```c
__int64 __fastcall DeleteCurrentUserKey(HKEY *a1, _DWORD *a2)
{
  if ( *a2 )
  {
    RegCloseKey(*a1);
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c704  push    rbx
0x18000c706  sub     rsp, 20h
0x18000c70a  cmp     dword ptr [rdx], 0
0x18000c70d  mov     rbx, rdx
0x18000c710  jz      short loc_18000C727
0x18000c712  mov     rcx, [rcx]; hKey
0x18000c715  call    cs:__imp_RegCloseKey
0x18000c71c  nop     dword ptr [rax+rax+00h]
0x18000c721  mov     dword ptr [rbx], 0
0x18000c727  xor     eax, eax
0x18000c729  add     rsp, 20h
0x18000c72d  pop     rbx
0x18000c72e  retn
```
