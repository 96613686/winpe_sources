# ATL::CComObject<CGameStatisticsMgr>::Release(void)

- ea: `0x180002c40`
- end: `0x180002caa`
- name: `?Release@?$CComObject@VCGameStatisticsMgr@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001bb4`
- `0x180002c40`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CGameStatisticsMgr>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v5);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180002c40  mov     [rsp+arg_8], rbx
0x180002c45  push    rdi
0x180002c46  sub     rsp, 20h
0x180002c4a  mov     edi, [rcx+8]
0x180002c4d  mov     rbx, rcx
0x180002c50  cmp     edi, 7FFFFFFFh
0x180002c56  jnz     short loc_180002C5F
0x180002c58  mov     edi, 7FFFFFFEh
0x180002c5d  jmp     short loc_180002C9D
0x180002c5f  sub     edi, 1
0x180002c62  mov     [rcx+8], edi
0x180002c65  jnz     short loc_180002C9D
0x180002c67  lea     rcx, [rsp+28h+arg_0]; this
0x180002c6c  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180002c71  test    rbx, rbx
0x180002c74  jz      short loc_180002C8A
0x180002c76  mov     rax, [rbx]
0x180002c79  mov     edx, 1
0x180002c7e  mov     rcx, rbx
0x180002c81  mov     rax, [rax+28h]
0x180002c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c8a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002c91  mov     rdx, [rcx]
0x180002c94  mov     rax, [rdx+10h]
0x180002c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c9d  mov     rbx, [rsp+28h+arg_8]
0x180002ca2  mov     eax, edi
0x180002ca4  add     rsp, 20h
0x180002ca8  pop     rdi
0x180002ca9  retn
```
