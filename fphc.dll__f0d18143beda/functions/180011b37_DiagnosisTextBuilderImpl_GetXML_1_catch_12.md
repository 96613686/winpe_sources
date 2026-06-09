# _DiagnosisTextBuilderImpl::GetXML_::_1_::catch$12

- ea: `0x180011b37`
- end: `0x180011b61`
- name: `_DiagnosisTextBuilderImpl::GetXML_::_1_::catch$12`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall DiagnosisTextBuilderImpl::GetXML_::_1_::catch_12(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 128) = **(_DWORD **)(a2 + 40);
  return 0;
}

```

## disassembly

```asm
0x180011b37  mov     [rsp+arg_8], rdx
0x180011b3c  push    rbp
0x180011b3d  sub     rsp, 20h
0x180011b41  mov     rbp, rdx
0x180011b44  mov     rax, [rbp+28h]
0x180011b48  mov     ecx, [rax]
0x180011b4a  mov     [rbp+80h], ecx
0x180011b50  mov     rax, 0
0x180011b5a  add     rsp, 20h
0x180011b5e  pop     rbp
0x180011b5f  retn
```
