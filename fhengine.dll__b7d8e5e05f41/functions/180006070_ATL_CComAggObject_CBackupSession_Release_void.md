# ATL::CComAggObject<CBackupSession>::Release(void)

- ea: `0x180006070`
- end: `0x1800060cd`
- name: `?Release@?$CComAggObject@VCBackupSession@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f08`
- `0x180006070`
- `0x180006498`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CBackupSession>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180006070  mov     [rsp+arg_8], rbx
0x180006075  push    rdi
0x180006076  sub     rsp, 20h
0x18000607a  mov     rbx, rcx
0x18000607d  add     rcx, 8; volatile int *
0x180006081  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180006086  mov     edi, eax
0x180006088  test    eax, eax
0x18000608a  jnz     short loc_1800060C0
0x18000608c  lea     rcx, [rsp+28h+arg_0]; this
0x180006091  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180006096  test    rbx, rbx
0x180006099  jz      short loc_1800060AD
0x18000609b  mov     rdx, [rbx]
0x18000609e  mov     rcx, rbx
0x1800060a1  mov     rax, [rdx+18h]
0x1800060a5  lea     edx, [rdi+1]
0x1800060a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ad  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800060b4  mov     rax, [rcx]
0x1800060b7  mov     rax, [rax+10h]
0x1800060bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c0  mov     rbx, [rsp+28h+arg_8]
0x1800060c5  mov     eax, edi
0x1800060c7  add     rsp, 20h
0x1800060cb  pop     rdi
0x1800060cc  retn
```
