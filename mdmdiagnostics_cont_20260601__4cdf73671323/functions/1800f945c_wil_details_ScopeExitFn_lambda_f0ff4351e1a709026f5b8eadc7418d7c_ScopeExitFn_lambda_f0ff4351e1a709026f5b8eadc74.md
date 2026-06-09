# wil::details::ScopeExitFn__lambda_f0ff4351e1a709026f5b8eadc7418d7c___::_ScopeExitFn__lambda_f0ff4351e1a709026f5b8eadc7418d7c___

- ea: `0x1800f945c`
- end: `0x1800f9498`
- name: `wil::details::ScopeExitFn__lambda_f0ff4351e1a709026f5b8eadc7418d7c___::_ScopeExitFn__lambda_f0ff4351e1a709026f5b8eadc7418d7c___`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1801677b4`

## callees

- `0x1800ef188`
- `0x1800f945c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f947a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f948c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f947a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f948c`

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
0x1800f945c  push    rbx
0x1800f945e  sub     rsp, 20h
0x1800f9462  cmp     byte ptr [rcx+10h], 0
0x1800f9466  mov     rbx, rcx
0x1800f9469  jz      short loc_1800F9492
0x1800f946b  mov     byte ptr [rcx+10h], 0
0x1800f946f  mov     rcx, [rcx]
0x1800f9472  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f9477  mov     rcx, rax; lpFileName
0x1800f947a  call    cs:__imp_DeleteFileW
0x1800f9480  mov     rcx, [rbx+8]
0x1800f9484  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f9489  mov     rcx, rax; lpFileName
0x1800f948c  call    cs:__imp_DeleteFileW
0x1800f9492  add     rsp, 20h
0x1800f9496  pop     rbx
0x1800f9497  retn
```
