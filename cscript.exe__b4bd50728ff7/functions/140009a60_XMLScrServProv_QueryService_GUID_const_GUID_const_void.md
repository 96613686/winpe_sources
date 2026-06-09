# XMLScrServProv::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x140009a60`
- end: `0x140009aad`
- name: `?QueryService@XMLScrServProv@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `77`
- prototype: `__int64 __fastcall(XMLScrServProv *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task`

## callees

- `0x140009a60`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrServProv::QueryService(
        XMLScrServProv *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v5; // rax

  if ( !a4 )
    return 2147500035LL;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&SID_ScriptletContext.Revision;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SID_ScriptletContext.Revision )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)SID_ScriptletContext.SubAuthority;
  if ( !v5 )
    return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 1))(
             *((_QWORD *)this + 1),
             a3,
             a4);
  *a4 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x140009a60  mov     r10, r8
0x140009a63  test    r9, r9
0x140009a66  jnz     short loc_140009A6F
0x140009a68  mov     eax, 80004003h
0x140009a6d  jmp     short locret_140009AAC
0x140009a6f  mov     rax, [rdx]
0x140009a72  sub     rax, qword ptr cs:SID_ScriptletContext.Revision
0x140009a79  jnz     short loc_140009A86
0x140009a7b  mov     rax, [rdx+8]
0x140009a7f  sub     rax, qword ptr cs:SID_ScriptletContext.SubAuthority
0x140009a86  test    rax, rax
0x140009a89  jnz     short loc_140009AA0
0x140009a8b  mov     rcx, [rcx+8]
0x140009a8f  mov     r8, r9
0x140009a92  mov     rdx, r10
0x140009a95  mov     rax, [rcx]
0x140009a98  mov     rax, [rax]
0x140009a9b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140009aa0  mov     qword ptr [r9], 0
0x140009aa7  mov     eax, 80004002h
0x140009aac  retn
```
