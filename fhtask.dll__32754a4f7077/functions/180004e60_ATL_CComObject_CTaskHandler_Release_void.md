# ATL::CComObject<CTaskHandler>::Release(void)

- ea: `0x180004e60`
- end: `0x180004ee1`
- name: `?Release@?$CComObject@VCTaskHandler@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004e60`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTaskHandler>::Release(volatile signed __int32 *a1)
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
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180004e60  mov     [rsp+arg_0], rbx
0x180004e65  push    rdi
0x180004e66  sub     rsp, 20h
0x180004e6a  mov     r8d, [rcx+8]
0x180004e6e  mov     rbx, rcx
0x180004e71  mov     ecx, 7FFFFFFFh
0x180004e76  jmp     short loc_180004E8A
0x180004e78  lea     edx, [r8-1]
0x180004e7c  mov     eax, r8d
0x180004e7f  lock cmpxchg [rbx+8], edx
0x180004e84  jz      short loc_180004E8F
0x180004e86  mov     r8d, [rbx+8]
0x180004e8a  cmp     r8d, ecx
0x180004e8d  jnz     short loc_180004E78
0x180004e8f  lea     edi, [r8-1]
0x180004e93  test    edi, edi
0x180004e95  jnz     short loc_180004ED4
0x180004e97  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004e9e  mov     rax, [rcx]
0x180004ea1  mov     rax, [rax+8]
0x180004ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eaa  test    rbx, rbx
0x180004ead  jz      short loc_180004EC1
0x180004eaf  mov     rax, [rbx]
0x180004eb2  lea     edx, [rdi+1]
0x180004eb5  mov     rcx, rbx
0x180004eb8  mov     rax, [rax+38h]
0x180004ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004ec8  mov     rdx, [rcx]
0x180004ecb  mov     rax, [rdx+10h]
0x180004ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed4  mov     rbx, [rsp+28h+arg_0]
0x180004ed9  mov     eax, edi
0x180004edb  add     rsp, 20h
0x180004edf  pop     rdi
0x180004ee0  retn
```
