# ATL::CComObject<CBackupSession>::Release(void)

- ea: `0x180006130`
- end: `0x180006190`
- name: `?Release@?$CComObject@VCBackupSession@@@ATL@@UEAAKXZ`
- size: `96`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f08`
- `0x180006130`
- `0x180006498`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CBackupSession>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 72);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180006130  mov     [rsp+arg_8], rbx
0x180006135  push    rdi
0x180006136  sub     rsp, 20h
0x18000613a  mov     rbx, rcx
0x18000613d  add     rcx, 120h; volatile int *
0x180006144  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180006149  mov     edi, eax
0x18000614b  test    eax, eax
0x18000614d  jnz     short loc_180006183
0x18000614f  lea     rcx, [rsp+28h+arg_0]; this
0x180006154  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180006159  test    rbx, rbx
0x18000615c  jz      short loc_180006170
0x18000615e  mov     rdx, [rbx]
0x180006161  mov     rcx, rbx
0x180006164  mov     rax, [rdx+70h]
0x180006168  lea     edx, [rdi+1]
0x18000616b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006170  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006177  mov     rax, [rcx]
0x18000617a  mov     rax, [rax+10h]
0x18000617e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006183  mov     rbx, [rsp+28h+arg_8]
0x180006188  mov     eax, edi
0x18000618a  add     rsp, 20h
0x18000618e  pop     rdi
0x18000618f  retn
```
