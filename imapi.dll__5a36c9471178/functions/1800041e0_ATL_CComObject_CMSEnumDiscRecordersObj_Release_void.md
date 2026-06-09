# ATL::CComObject<CMSEnumDiscRecordersObj>::Release(void)

- ea: `0x1800041e0`
- end: `0x180004261`
- name: `?Release@?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800041e0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSEnumDiscRecordersObj>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800041e0  mov     [rsp+arg_0], rbx
0x1800041e5  push    rdi
0x1800041e6  sub     rsp, 20h
0x1800041ea  mov     r8d, [rcx+8]
0x1800041ee  mov     rbx, rcx
0x1800041f1  mov     ecx, 7FFFFFFFh
0x1800041f6  jmp     short loc_18000420A
0x1800041f8  lea     edx, [r8-1]
0x1800041fc  mov     eax, r8d
0x1800041ff  lock cmpxchg [rbx+8], edx
0x180004204  jz      short loc_18000420F
0x180004206  mov     r8d, [rbx+8]
0x18000420a  cmp     r8d, ecx
0x18000420d  jnz     short loc_1800041F8
0x18000420f  lea     edi, [r8-1]
0x180004213  test    edi, edi
0x180004215  jnz     short loc_180004254
0x180004217  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000421e  mov     rax, [rcx]
0x180004221  mov     rax, [rax+8]
0x180004225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000422a  test    rbx, rbx
0x18000422d  jz      short loc_180004241
0x18000422f  mov     rax, [rbx]
0x180004232  lea     edx, [rdi+1]
0x180004235  mov     rcx, rbx
0x180004238  mov     rax, [rax+38h]
0x18000423c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004241  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004248  mov     rdx, [rcx]
0x18000424b  mov     rax, [rdx+10h]
0x18000424f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004254  mov     rbx, [rsp+28h+arg_0]
0x180004259  mov     eax, edi
0x18000425b  add     rsp, 20h
0x18000425f  pop     rdi
0x180004260  retn
```
