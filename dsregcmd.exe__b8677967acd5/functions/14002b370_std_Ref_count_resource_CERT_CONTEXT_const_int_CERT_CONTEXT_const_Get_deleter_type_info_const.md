# std::_Ref_count_resource<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *)>::_Get_deleter(type_info const &)

- ea: `0x14002b370`
- end: `0x14002b39f`
- name: `?_Get_deleter@?$_Ref_count_resource@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14002b384`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14002b384`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *)>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_140045498);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x14002b370  push    rbx
0x14002b372  sub     rsp, 20h
0x14002b376  mov     rbx, rcx
0x14002b379  lea     rcx, [rdx+8]
0x14002b37d  lea     rdx, qword_140045498
0x14002b384  call    cs:__imp___std_type_info_compare
0x14002b38a  xor     ecx, ecx
0x14002b38c  lea     rdx, [rbx+10h]
0x14002b390  test    eax, eax
0x14002b392  cmovnz  rdx, rcx
0x14002b396  mov     rax, rdx
0x14002b399  add     rsp, 20h
0x14002b39d  pop     rbx
0x14002b39e  retn
```
