# ATL::CComObject<CEnhancedStorageActEnumerator>::Release(void)

- ea: `0x18000b410`
- end: `0x18000b46d`
- name: `?Release@?$CComObject@VCEnhancedStorageActEnumerator@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000209c`
- `0x180003894`
- `0x18000b410`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageActEnumerator>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b410  mov     [rsp+arg_8], rbx
0x18000b415  push    rdi
0x18000b416  sub     rsp, 20h
0x18000b41a  mov     rbx, rcx
0x18000b41d  add     rcx, 8; volatile int *
0x18000b421  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000b426  mov     edi, eax
0x18000b428  test    eax, eax
0x18000b42a  jnz     short loc_18000B460
0x18000b42c  lea     rcx, [rsp+28h+arg_0]; this
0x18000b431  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x18000b436  test    rbx, rbx
0x18000b439  jz      short loc_18000B44D
0x18000b43b  mov     rdx, [rbx]
0x18000b43e  mov     rcx, rbx
0x18000b441  mov     rax, [rdx+28h]
0x18000b445  lea     edx, [rdi+1]
0x18000b448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b44d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b454  mov     rax, [rcx]
0x18000b457  mov     rax, [rax+10h]
0x18000b45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b460  mov     rbx, [rsp+28h+arg_8]
0x18000b465  mov     eax, edi
0x18000b467  add     rsp, 20h
0x18000b46b  pop     rdi
0x18000b46c  retn
```
