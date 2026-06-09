# wil::details::ScopeExitFn__lambda_f0ff4351e1a709026f5b8eadc7418d7c___::_ScopeExitFn__lambda_f0ff4351e1a709026f5b8eadc7418d7c___

- ea: `0x1800fa428`
- end: `0x1800fa471`
- name: `wil::details::ScopeExitFn__lambda_f0ff4351e1a709026f5b8eadc7418d7c___::_ScopeExitFn__lambda_f0ff4351e1a709026f5b8eadc7418d7c___`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18016a324`

## callees

- `0x1800ef8c4`
- `0x1800fa428`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa446`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa45e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa446`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa45e`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_f0ff4351e1a709026f5b8eadc7418d7c___::_ScopeExitFn__lambda_f0ff4351e1a709026f5b8eadc7418d7c___(
        __int64 a1)
{
  const WCHAR *v2; // rax
  const WCHAR *v3; // rax

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*(_QWORD *)a1);
    DeleteFileW(v2);
    v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*(_QWORD *)(a1 + 8));
    DeleteFileW(v3);
  }
}

```

## disassembly

```asm
0x1800fa428  push    rbx
0x1800fa42a  sub     rsp, 20h
0x1800fa42e  cmp     byte ptr [rcx+10h], 0
0x1800fa432  mov     rbx, rcx
0x1800fa435  jz      short loc_1800FA46A
0x1800fa437  mov     byte ptr [rcx+10h], 0
0x1800fa43b  mov     rcx, [rcx]
0x1800fa43e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800fa443  mov     rcx, rax; lpFileName
0x1800fa446  call    cs:__imp_DeleteFileW
0x1800fa44d  nop     dword ptr [rax+rax+00h]
0x1800fa452  mov     rcx, [rbx+8]
0x1800fa456  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800fa45b  mov     rcx, rax; lpFileName
0x1800fa45e  call    cs:__imp_DeleteFileW
0x1800fa465  nop     dword ptr [rax+rax+00h]
0x1800fa46a  add     rsp, 20h
0x1800fa46e  pop     rbx
0x1800fa46f  retn
```
