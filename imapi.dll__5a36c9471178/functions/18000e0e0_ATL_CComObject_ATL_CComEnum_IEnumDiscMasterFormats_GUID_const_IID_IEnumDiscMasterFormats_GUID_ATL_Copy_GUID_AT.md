# ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::Release(void)

- ea: `0x18000e0e0`
- end: `0x18000e161`
- name: `?Release@?$CComObject@V?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e0e0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::Release(
        volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 12);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 12, i - 1, i);
        i = *((_DWORD *)a1 + 12) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18000e0e0  mov     [rsp+arg_0], rbx
0x18000e0e5  push    rdi
0x18000e0e6  sub     rsp, 20h
0x18000e0ea  mov     r8d, [rcx+30h]
0x18000e0ee  mov     rbx, rcx
0x18000e0f1  mov     ecx, 7FFFFFFFh
0x18000e0f6  jmp     short loc_18000E10A
0x18000e0f8  lea     edx, [r8-1]
0x18000e0fc  mov     eax, r8d
0x18000e0ff  lock cmpxchg [rbx+30h], edx
0x18000e104  jz      short loc_18000E10F
0x18000e106  mov     r8d, [rbx+30h]
0x18000e10a  cmp     r8d, ecx
0x18000e10d  jnz     short loc_18000E0F8
0x18000e10f  lea     edi, [r8-1]
0x18000e113  test    edi, edi
0x18000e115  jnz     short loc_18000E154
0x18000e117  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e11e  mov     rax, [rcx]
0x18000e121  mov     rax, [rax+8]
0x18000e125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e12a  test    rbx, rbx
0x18000e12d  jz      short loc_18000E141
0x18000e12f  mov     rax, [rbx]
0x18000e132  lea     edx, [rdi+1]
0x18000e135  mov     rcx, rbx
0x18000e138  mov     rax, [rax+38h]
0x18000e13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e141  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e148  mov     rdx, [rcx]
0x18000e14b  mov     rax, [rdx+10h]
0x18000e14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e154  mov     rbx, [rsp+28h+arg_0]
0x18000e159  mov     eax, edi
0x18000e15b  add     rsp, 20h
0x18000e15f  pop     rdi
0x18000e160  retn
```
