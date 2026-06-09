# ATL::CComObject<CGameStatistics>::Release(void)

- ea: `0x180002bd0`
- end: `0x180002c3a`
- name: `?Release@?$CComObject@VCGameStatistics@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001bb4`
- `0x180002bd0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CGameStatistics>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 120LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180002bd0  mov     [rsp+arg_8], rbx
0x180002bd5  push    rdi
0x180002bd6  sub     rsp, 20h
0x180002bda  mov     edi, [rcx+8]
0x180002bdd  mov     rbx, rcx
0x180002be0  cmp     edi, 7FFFFFFFh
0x180002be6  jnz     short loc_180002BEF
0x180002be8  mov     edi, 7FFFFFFEh
0x180002bed  jmp     short loc_180002C2D
0x180002bef  sub     edi, 1
0x180002bf2  mov     [rcx+8], edi
0x180002bf5  jnz     short loc_180002C2D
0x180002bf7  lea     rcx, [rsp+28h+arg_0]; this
0x180002bfc  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180002c01  test    rbx, rbx
0x180002c04  jz      short loc_180002C1A
0x180002c06  mov     rax, [rbx]
0x180002c09  mov     edx, 1
0x180002c0e  mov     rcx, rbx
0x180002c11  mov     rax, [rax+78h]
0x180002c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c1a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002c21  mov     rdx, [rcx]
0x180002c24  mov     rax, [rdx+10h]
0x180002c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2d  mov     rbx, [rsp+28h+arg_8]
0x180002c32  mov     eax, edi
0x180002c34  add     rsp, 20h
0x180002c38  pop     rdi
0x180002c39  retn
```
