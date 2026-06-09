# std::_Ref_count_resource<uchar const *,wil::BufferDeleter>::_Get_deleter(type_info const &)

- ea: `0x18004e870`
- end: `0x18004e89f`
- name: `?_Get_deleter@?$_Ref_count_resource@PEBEVBufferDeleter@wil@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e884`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e884`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<unsigned char const *,wil::BufferDeleter>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_180075418);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18004e870  push    rbx
0x18004e872  sub     rsp, 20h
0x18004e876  mov     rbx, rcx
0x18004e879  lea     rcx, [rdx+8]
0x18004e87d  lea     rdx, qword_180075418
0x18004e884  call    cs:__imp___std_type_info_compare
0x18004e88a  xor     ecx, ecx
0x18004e88c  lea     rdx, [rbx+10h]
0x18004e890  test    eax, eax
0x18004e892  cmovnz  rdx, rcx
0x18004e896  mov     rax, rdx
0x18004e899  add     rsp, 20h
0x18004e89d  pop     rbx
0x18004e89e  retn
```
