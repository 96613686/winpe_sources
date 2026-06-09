# ATL::CComObject<CRedbookWriterEvent>::Release(void)

- ea: `0x180016b20`
- end: `0x180016ba1`
- name: `?Release@?$CComObject@VCRedbookWriterEvent@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016bb0`

## callees

- `0x180016b20`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRedbookWriterEvent>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 14);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 14, i - 1, i);
        i = *((_DWORD *)a1 + 14) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180016b20  mov     [rsp+arg_0], rbx
0x180016b25  push    rdi
0x180016b26  sub     rsp, 20h
0x180016b2a  mov     r8d, [rcx+38h]
0x180016b2e  mov     rbx, rcx
0x180016b31  mov     ecx, 7FFFFFFFh
0x180016b36  jmp     short loc_180016B4A
0x180016b38  lea     edx, [r8-1]
0x180016b3c  mov     eax, r8d
0x180016b3f  lock cmpxchg [rbx+38h], edx
0x180016b44  jz      short loc_180016B4F
0x180016b46  mov     r8d, [rbx+38h]
0x180016b4a  cmp     r8d, ecx
0x180016b4d  jnz     short loc_180016B38
0x180016b4f  lea     edi, [r8-1]
0x180016b53  test    edi, edi
0x180016b55  jnz     short loc_180016B94
0x180016b57  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180016b5e  mov     rax, [rcx]
0x180016b61  mov     rax, [rax+8]
0x180016b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b6a  test    rbx, rbx
0x180016b6d  jz      short loc_180016B81
0x180016b6f  mov     rax, [rbx]
0x180016b72  lea     edx, [rdi+1]
0x180016b75  mov     rcx, rbx
0x180016b78  mov     rax, [rax+40h]
0x180016b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b81  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180016b88  mov     rdx, [rcx]
0x180016b8b  mov     rax, [rdx+10h]
0x180016b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b94  mov     rbx, [rsp+28h+arg_0]
0x180016b99  mov     eax, edi
0x180016b9b  add     rsp, 20h
0x180016b9f  pop     rdi
0x180016ba0  retn
```
