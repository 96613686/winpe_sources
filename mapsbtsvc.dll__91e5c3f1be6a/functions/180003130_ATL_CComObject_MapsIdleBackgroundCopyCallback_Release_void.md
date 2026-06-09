# ATL::CComObject<MapsIdleBackgroundCopyCallback>::Release(void)

- ea: `0x180003130`
- end: `0x18000318d`
- name: `?Release@?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002a10`
- `0x180003130`
- `0x1800031f0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<MapsIdleBackgroundCopyCallback>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180003130  mov     [rsp+arg_8], rbx
0x180003135  push    rdi
0x180003136  sub     rsp, 20h
0x18000313a  mov     rbx, rcx
0x18000313d  add     rcx, 8; volatile int *
0x180003141  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180003146  mov     edi, eax
0x180003148  test    eax, eax
0x18000314a  jnz     short loc_180003180
0x18000314c  lea     rcx, [rsp+28h+arg_0]; this
0x180003151  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180003156  test    rbx, rbx
0x180003159  jz      short loc_18000316D
0x18000315b  mov     rdx, [rbx]
0x18000315e  mov     rcx, rbx
0x180003161  mov     rax, [rdx+38h]
0x180003165  lea     edx, [rdi+1]
0x180003168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000316d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003174  mov     rax, [rcx]
0x180003177  mov     rax, [rax+10h]
0x18000317b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003180  mov     rbx, [rsp+28h+arg_8]
0x180003185  mov     eax, edi
0x180003187  add     rsp, 20h
0x18000318b  pop     rdi
0x18000318c  retn
```
