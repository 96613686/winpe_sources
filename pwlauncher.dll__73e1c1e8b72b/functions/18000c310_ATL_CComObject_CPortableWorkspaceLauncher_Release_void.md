# ATL::CComObject<CPortableWorkspaceLauncher>::Release(void)

- ea: `0x18000c310`
- end: `0x18000c383`
- name: `?Release@?$CComObject@VCPortableWorkspaceLauncher@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c310`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPortableWorkspaceLauncher>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

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
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 48LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000c310  mov     [rsp+arg_0], rbx
0x18000c315  push    rdi
0x18000c316  sub     rsp, 20h
0x18000c31a  mov     ebx, [rcx+8]
0x18000c31d  mov     rdi, rcx
0x18000c320  cmp     ebx, 7FFFFFFFh
0x18000c326  jnz     short loc_18000C32F
0x18000c328  mov     ebx, 7FFFFFFEh
0x18000c32d  jmp     short loc_18000C376
0x18000c32f  sub     ebx, 1
0x18000c332  mov     [rcx+8], ebx
0x18000c335  jnz     short loc_18000C376
0x18000c337  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c33e  mov     rax, [rcx]
0x18000c341  mov     rax, [rax+8]
0x18000c345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c34a  test    rdi, rdi
0x18000c34d  jz      short loc_18000C363
0x18000c34f  mov     rax, [rdi]
0x18000c352  mov     edx, 1
0x18000c357  mov     rcx, rdi
0x18000c35a  mov     rax, [rax+30h]
0x18000c35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c363  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c36a  mov     rdx, [rcx]
0x18000c36d  mov     rax, [rdx+10h]
0x18000c371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c376  mov     eax, ebx
0x18000c378  mov     rbx, [rsp+28h+arg_0]
0x18000c37d  add     rsp, 20h
0x18000c381  pop     rdi
0x18000c382  retn
```
