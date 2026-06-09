# ATL::CComObject<CRasDiagHelper>::Release(void)

- ea: `0x180007c70`
- end: `0x180007cf5`
- name: `?Release@?$CComObject@VCRasDiagHelper@@@ATL@@UEAAKXZ`
- size: `133`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007d00`

## callees

- `0x180007c70`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRasDiagHelper>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 14);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 14, i - 1, i);
        i = *((_DWORD *)a1 + 14) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 168LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180007c70  mov     [rsp+arg_0], rbx
0x180007c75  push    rdi
0x180007c76  sub     rsp, 20h
0x180007c7a  mov     r8d, [rcx+38h]
0x180007c7e  mov     rbx, rcx
0x180007c81  mov     ecx, 7FFFFFFFh
0x180007c86  jmp     short loc_180007C9A
0x180007c88  lea     edx, [r8-1]
0x180007c8c  mov     eax, r8d
0x180007c8f  lock cmpxchg [rbx+38h], edx
0x180007c94  jz      short loc_180007C9F
0x180007c96  mov     r8d, [rbx+38h]
0x180007c9a  cmp     r8d, ecx
0x180007c9d  jnz     short loc_180007C88
0x180007c9f  lea     edi, [r8-1]
0x180007ca3  test    edi, edi
0x180007ca5  jnz     short loc_180007CE7
0x180007ca7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007cae  mov     rax, [rcx]
0x180007cb1  mov     rax, [rax+8]
0x180007cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cba  test    rbx, rbx
0x180007cbd  jz      short loc_180007CD4
0x180007cbf  mov     rax, [rbx]
0x180007cc2  lea     edx, [rdi+1]
0x180007cc5  mov     rcx, rbx
0x180007cc8  mov     rax, [rax+0A8h]
0x180007ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cd4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007cdb  mov     rdx, [rcx]
0x180007cde  mov     rax, [rdx+10h]
0x180007ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce7  mov     rbx, [rsp+28h+arg_0]
0x180007cec  mov     eax, edi
0x180007cee  add     rsp, 20h
0x180007cf2  pop     rdi
0x180007cf3  retn
```
