# ATL::CComObject<CIRepairInfo>::Release(void)

- ea: `0x180014850`
- end: `0x1800148d1`
- name: `?Release@?$CComObject@VCIRepairInfo@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180014850`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIRepairInfo>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 120LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180014850  mov     [rsp+arg_0], rbx
0x180014855  push    rdi
0x180014856  sub     rsp, 20h
0x18001485a  mov     r8d, [rcx+8]
0x18001485e  mov     rbx, rcx
0x180014861  mov     ecx, 7FFFFFFFh
0x180014866  jmp     short loc_18001487A
0x180014868  lea     edx, [r8-1]
0x18001486c  mov     eax, r8d
0x18001486f  lock cmpxchg [rbx+8], edx
0x180014874  jz      short loc_18001487F
0x180014876  mov     r8d, [rbx+8]
0x18001487a  cmp     r8d, ecx
0x18001487d  jnz     short loc_180014868
0x18001487f  lea     edi, [r8-1]
0x180014883  test    edi, edi
0x180014885  jnz     short loc_1800148C4
0x180014887  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001488e  mov     rax, [rcx]
0x180014891  mov     rax, [rax+8]
0x180014895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001489a  test    rbx, rbx
0x18001489d  jz      short loc_1800148B1
0x18001489f  mov     rax, [rbx]
0x1800148a2  lea     edx, [rdi+1]
0x1800148a5  mov     rcx, rbx
0x1800148a8  mov     rax, [rax+78h]
0x1800148ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148b1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800148b8  mov     rdx, [rcx]
0x1800148bb  mov     rax, [rdx+10h]
0x1800148bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148c4  mov     rbx, [rsp+28h+arg_0]
0x1800148c9  mov     eax, edi
0x1800148cb  add     rsp, 20h
0x1800148cf  pop     rdi
0x1800148d0  retn
```
