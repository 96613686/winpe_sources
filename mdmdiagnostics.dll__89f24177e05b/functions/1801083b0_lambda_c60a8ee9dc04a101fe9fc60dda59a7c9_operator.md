# _lambda_c60a8ee9dc04a101fe9fc60dda59a7c9_::operator()

- ea: `0x1801083b0`
- end: `0x180108468`
- name: `_lambda_c60a8ee9dc04a101fe9fc60dda59a7c9_::operator()`
- size: `184`
- prototype: `char __fastcall(struct _iobuf ***, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18010aee4`

## callees

- `0x1800ef188`
- `0x1801083b0`
- `0x1801109fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108401`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801083df`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801083df`

## string_xrefs

- `0x180108416`: `Failed (HResult:0x%08x) to CopyFile:%s, to:%s\n`

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
0x1801083b0  push    rbx
0x1801083b2  push    rsi
0x1801083b3  push    rdi
0x1801083b4  push    r14
0x1801083b6  sub     rsp, 38h
0x1801083ba  mov     r14, rcx
0x1801083bd  mov     rdi, r8
0x1801083c0  mov     rcx, r8
0x1801083c3  mov     rsi, rdx
0x1801083c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801083cb  mov     rcx, rsi
0x1801083ce  mov     rbx, rax
0x1801083d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801083d6  xor     r8d, r8d; bFailIfExists
0x1801083d9  mov     rdx, rbx; lpNewFileName
0x1801083dc  mov     rcx, rax; lpExistingFileName
0x1801083df  call    cs:__imp_CopyFileW
0x1801083e5  mov     rcx, rdi
0x1801083e8  test    eax, eax
0x1801083ea  jnz     short loc_180108432
0x1801083ec  xor     bl, bl
0x1801083ee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801083f3  mov     rcx, rsi
0x1801083f6  mov     rdi, rax
0x1801083f9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801083fe  mov     rsi, rax
0x180108401  call    cs:__imp_GetLastError
0x180108407  test    eax, eax
0x180108409  jle     short loc_180108413
0x18010840b  movzx   eax, ax
0x18010840e  or      eax, 80070000h
0x180108413  mov     rcx, [r14]
0x180108416  lea     rdx, aFailedHresult0_1; "Failed (HResult:0x%08x) to CopyFile:%s,"...
0x18010841d  mov     r9, rsi
0x180108420  mov     [rsp+58h+var_38], rdi
0x180108425  mov     r8d, eax
0x180108428  mov     rcx, [rcx]; struct _iobuf *
0x18010842b  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x180108430  jmp     short loc_18010845C
0x180108432  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180108437  mov     rcx, rsi
0x18010843a  mov     rbx, rax
0x18010843d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180108442  mov     rcx, [r14]
0x180108445  lea     rdx, aCopiedFileSToS; "Copied file:%s, to:%s\n"
0x18010844c  mov     r9, rbx
0x18010844f  mov     r8, rax
0x180108452  mov     rcx, [rcx]; struct _iobuf *
0x180108455  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010845a  mov     bl, 1
0x18010845c  mov     al, bl
0x18010845e  add     rsp, 38h
0x180108462  pop     r14
0x180108464  pop     rdi
0x180108465  pop     rsi
0x180108466  pop     rbx
0x180108467  retn
```
