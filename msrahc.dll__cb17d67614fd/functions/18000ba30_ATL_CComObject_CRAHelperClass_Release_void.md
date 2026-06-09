# ATL::CComObject<CRAHelperClass>::Release(void)

- ea: `0x18000ba30`
- end: `0x18000ba99`
- name: `?Release@?$CComObject@VCRAHelperClass@@@ATL@@UEAAKXZ`
- size: `105`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000baa0`
- `0x18000bab0`

## callees

- `0x18000ba30`
- `0x18000bb64`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRAHelperClass>::Release(volatile int *a1)
{
  unsigned int v2; // edi

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 16);
  if ( !v2 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 168LL))(a1, v2 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ba30  mov     [rsp+arg_0], rbx
0x18000ba35  push    rdi
0x18000ba36  sub     rsp, 20h
0x18000ba3a  mov     rbx, rcx
0x18000ba3d  add     rcx, 40h ; '@'; volatile int *
0x18000ba41  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000ba46  mov     edi, eax
0x18000ba48  test    eax, eax
0x18000ba4a  jnz     short loc_18000BA8C
0x18000ba4c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ba53  mov     rdx, [rcx]
0x18000ba56  mov     rax, [rdx+8]
0x18000ba5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba5f  test    rbx, rbx
0x18000ba62  jz      short loc_18000BA79
0x18000ba64  mov     rax, [rbx]
0x18000ba67  lea     edx, [rdi+1]
0x18000ba6a  mov     rcx, rbx
0x18000ba6d  mov     rax, [rax+0A8h]
0x18000ba74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba79  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ba80  mov     rax, [rcx]
0x18000ba83  mov     rax, [rax+10h]
0x18000ba87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba8c  mov     rbx, [rsp+28h+arg_0]
0x18000ba91  mov     eax, edi
0x18000ba93  add     rsp, 20h
0x18000ba97  pop     rdi
0x18000ba98  retn
```
