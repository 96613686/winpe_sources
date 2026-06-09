# wil::details::ScopeExitFn__lambda_36650952582612cb7f20faec3e22a7c6___::_ScopeExitFn__lambda_36650952582612cb7f20faec3e22a7c6___

- ea: `0x18000e660`
- end: `0x18000e690`
- name: `wil::details::ScopeExitFn__lambda_36650952582612cb7f20faec3e22a7c6___::_ScopeExitFn__lambda_36650952582612cb7f20faec3e22a7c6___`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180036396`

## callees

- `0x18000e660`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000e67e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000e67e`

## pseudocode

```c
int __fastcall wil::details::ScopeExitFn__lambda_36650952582612cb7f20faec3e22a7c6___::_ScopeExitFn__lambda_36650952582612cb7f20faec3e22a7c6___(
        __int64 a1)
{
  _QWORD *v1; // rax

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v1 = *(_QWORD **)a1;
    if ( **(_QWORD **)a1 )
      LODWORD(v1) = SafeArrayUnaccessData(*(SAFEARRAY **)(*(_QWORD *)(a1 + 8) + 8LL));
  }
  return (int)v1;
}

```

## disassembly

```asm
0x18000e660  sub     rsp, 28h
0x18000e664  xor     edx, edx
0x18000e666  cmp     [rcx+10h], dl
0x18000e669  jz      short loc_18000E68A
0x18000e66b  mov     [rcx+10h], dl
0x18000e66e  mov     rax, [rcx]
0x18000e671  cmp     [rax], rdx
0x18000e674  jz      short loc_18000E68A
0x18000e676  mov     rcx, [rcx+8]
0x18000e67a  mov     rcx, [rcx+8]; psa
0x18000e67e  call    cs:__imp_SafeArrayUnaccessData
0x18000e685  nop     dword ptr [rax+rax+00h]
0x18000e68a  add     rsp, 28h
0x18000e68e  retn
```
