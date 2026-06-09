# ATL::CComObject<CDpSearchProtocol>::Release(void)

- ea: `0x180005ec0`
- end: `0x180005f41`
- name: `?Release@?$CComObject@VCDpSearchProtocol@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005ec0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDpSearchProtocol>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005ec0  mov     [rsp+arg_0], rbx
0x180005ec5  push    rdi
0x180005ec6  sub     rsp, 20h
0x180005eca  mov     r8d, [rcx+8]
0x180005ece  mov     rbx, rcx
0x180005ed1  mov     ecx, 7FFFFFFFh
0x180005ed6  jmp     short loc_180005EEA
0x180005ed8  lea     edx, [r8-1]
0x180005edc  mov     eax, r8d
0x180005edf  lock cmpxchg [rbx+8], edx
0x180005ee4  jz      short loc_180005EEF
0x180005ee6  mov     r8d, [rbx+8]
0x180005eea  cmp     r8d, ecx
0x180005eed  jnz     short loc_180005ED8
0x180005eef  lea     edi, [r8-1]
0x180005ef3  test    edi, edi
0x180005ef5  jnz     short loc_180005F34
0x180005ef7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005efe  mov     rax, [rcx]
0x180005f01  mov     rax, [rax+8]
0x180005f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f0a  test    rbx, rbx
0x180005f0d  jz      short loc_180005F21
0x180005f0f  mov     rax, [rbx]
0x180005f12  lea     edx, [rdi+1]
0x180005f15  mov     rcx, rbx
0x180005f18  mov     rax, [rax+40h]
0x180005f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f21  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005f28  mov     rdx, [rcx]
0x180005f2b  mov     rax, [rdx+10h]
0x180005f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f34  mov     rbx, [rsp+28h+arg_0]
0x180005f39  mov     eax, edi
0x180005f3b  add     rsp, 20h
0x180005f3f  pop     rdi
0x180005f40  retn
```
