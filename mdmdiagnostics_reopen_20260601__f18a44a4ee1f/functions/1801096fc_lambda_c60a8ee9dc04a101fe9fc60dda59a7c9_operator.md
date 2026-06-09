# _lambda_c60a8ee9dc04a101fe9fc60dda59a7c9_::operator()

- ea: `0x1801096fc`
- end: `0x1801097c1`
- name: `_lambda_c60a8ee9dc04a101fe9fc60dda59a7c9_::operator()`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18010c300`

## callees

- `0x1800ef8c4`
- `0x1801096fc`
- `0x180111ec4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180109753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180109753`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18010972b`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18010972b`

## string_xrefs

- `0x18010976e`: `Failed (HResult:0x%08x) to CopyFile:%s, to:%s\n`

## pseudocode

```c
char __fastcall lambda_c60a8ee9dc04a101fe9fc60dda59a7c9_::operator()(struct _iobuf ***a1, __int64 a2, __int64 a3)
{
  const WCHAR *v6; // rbx
  const WCHAR *v7; // rax
  char v8; // bl
  __int64 v9; // rdi
  __int64 v10; // rsi
  signed int LastError; // eax
  __int64 v12; // rbx
  __int64 v13; // rax

  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( CopyFileW(v7, v6, 0) )
  {
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    MdmLogCollector::WriteToFile(**a1, L"Copied file:%s, to:%s\n", v13, v12);
    return 1;
  }
  else
  {
    v8 = 0;
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    MdmLogCollector::WriteToFile(
      **a1,
      L"Failed (HResult:0x%08x) to CopyFile:%s, to:%s\n",
      (unsigned int)LastError,
      v10,
      v9);
  }
  return v8;
}

```

## disassembly

```asm
0x1801096fc  push    rbx
0x1801096fe  push    rsi
0x1801096ff  push    rdi
0x180109700  push    r14
0x180109702  sub     rsp, 38h
0x180109706  mov     r14, rcx
0x180109709  mov     rdi, r8
0x18010970c  mov     rcx, r8
0x18010970f  mov     rsi, rdx
0x180109712  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180109717  mov     rcx, rsi
0x18010971a  mov     rbx, rax
0x18010971d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180109722  xor     r8d, r8d; bFailIfExists
0x180109725  mov     rdx, rbx; lpNewFileName
0x180109728  mov     rcx, rax; lpExistingFileName
0x18010972b  call    cs:__imp_CopyFileW
0x180109732  nop     dword ptr [rax+rax+00h]
0x180109737  mov     rcx, rdi
0x18010973a  test    eax, eax
0x18010973c  jnz     short loc_18010978A
0x18010973e  xor     bl, bl
0x180109740  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180109745  mov     rcx, rsi
0x180109748  mov     rdi, rax
0x18010974b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180109750  mov     rsi, rax
0x180109753  call    cs:__imp_GetLastError
0x18010975a  nop     dword ptr [rax+rax+00h]
0x18010975f  test    eax, eax
0x180109761  jle     short loc_18010976B
0x180109763  movzx   eax, ax
0x180109766  or      eax, 80070000h
0x18010976b  mov     rcx, [r14]
0x18010976e  lea     rdx, aFailedHresult0_1; "Failed (HResult:0x%08x) to CopyFile:%s,"...
0x180109775  mov     r9, rsi
0x180109778  mov     [rsp+58h+var_38], rdi
0x18010977d  mov     r8d, eax
0x180109780  mov     rcx, [rcx]; struct _iobuf *
0x180109783  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x180109788  jmp     short loc_1801097B4
0x18010978a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010978f  mov     rcx, rsi
0x180109792  mov     rbx, rax
0x180109795  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010979a  mov     rcx, [r14]
0x18010979d  lea     rdx, aCopiedFileSToS; "Copied file:%s, to:%s\n"
0x1801097a4  mov     r9, rbx
0x1801097a7  mov     r8, rax
0x1801097aa  mov     rcx, [rcx]; struct _iobuf *
0x1801097ad  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x1801097b2  mov     bl, 1
0x1801097b4  mov     al, bl
0x1801097b6  add     rsp, 38h
0x1801097ba  pop     r14
0x1801097bc  pop     rdi
0x1801097bd  pop     rsi
0x1801097be  pop     rbx
0x1801097bf  retn
```
