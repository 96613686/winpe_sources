# CModule::GetGlobalDeviceConfiguration(_GUID const &,void * *)

- ea: `0x18000fe90`
- end: `0x18000fec6`
- name: `?GetGlobalDeviceConfiguration@CModule@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `54`
- prototype: `__int64 __fastcall(CModule *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000fe90`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CModule::GetGlobalDeviceConfiguration(CModule *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v4)(const struct _GUID *, void **); // rax

  v3 = *((_QWORD *)this + 16);
  if ( v3 && (v4 = *(__int64 (__fastcall **)(const struct _GUID *, void **))(v3 + 152)) != 0 )
    return v4(a2, a3);
  else
    return 2289958915LL;
}

```

## disassembly

```asm
0x18000fe90  sub     rsp, 28h
0x18000fe94  mov     r9, rdx
0x18000fe97  mov     rax, [rcx+80h]
0x18000fe9e  test    rax, rax
0x18000fea1  jz      short loc_18000FEBC
0x18000fea3  mov     rax, [rax+98h]
0x18000feaa  test    rax, rax
0x18000fead  jz      short loc_18000FEBC
0x18000feaf  mov     rdx, r8
0x18000feb2  mov     rcx, r9
0x18000feb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feba  jmp     short loc_18000FEC1
0x18000febc  mov     eax, 887E0003h
0x18000fec1  add     rsp, 28h
0x18000fec5  retn
```
