# ATL::CComObject<CServicingSession>::Release(void)

- ea: `0x180006210`
- end: `0x180006270`
- name: `?Release@?$CComObject@VCServicingSession@@@ATL@@UEAAKXZ`
- size: `96`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002f08`
- `0x180006210`
- `0x180006498`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CServicingSession>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 72);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180006210  mov     [rsp+arg_8], rbx
0x180006215  push    rdi
0x180006216  sub     rsp, 20h
0x18000621a  mov     rbx, rcx
0x18000621d  add     rcx, 120h; volatile int *
0x180006224  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180006229  mov     edi, eax
0x18000622b  test    eax, eax
0x18000622d  jnz     short loc_180006263
0x18000622f  lea     rcx, [rsp+28h+arg_0]; this
0x180006234  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180006239  test    rbx, rbx
0x18000623c  jz      short loc_180006250
0x18000623e  mov     rdx, [rbx]
0x180006241  mov     rcx, rbx
0x180006244  mov     rax, [rdx+48h]
0x180006248  lea     edx, [rdi+1]
0x18000624b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006250  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006257  mov     rax, [rcx]
0x18000625a  mov     rax, [rax+10h]
0x18000625e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006263  mov     rbx, [rsp+28h+arg_8]
0x180006268  mov     eax, edi
0x18000626a  add     rsp, 20h
0x18000626e  pop     rdi
0x18000626f  retn
```
