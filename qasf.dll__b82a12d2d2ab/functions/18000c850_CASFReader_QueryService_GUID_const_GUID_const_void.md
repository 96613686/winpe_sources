# CASFReader::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x18000c850`
- end: `0x18000c8b8`
- name: `?QueryService@CASFReader@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `104`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000c850`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::QueryService(
        CASFReader *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ecx
  __int64 (__fastcall ***v7)(_QWORD, const struct _GUID *, void **); // rcx

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v6 = -2147467262;
  if ( *(_OWORD *)&IID_IWMDRMReader == *(_OWORD *)a2 )
  {
    v7 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 24);
    if ( v7 )
      return (unsigned int)(**v7)(v7, a3, a4);
    else
      return (unsigned int)-2147467259;
  }
  return v6;
}

```

## disassembly

```asm
0x18000c850  sub     rsp, 28h
0x18000c854  mov     r11, r8
0x18000c857  mov     r10, rcx
0x18000c85a  test    r9, r9
0x18000c85d  jnz     short loc_18000C866
0x18000c85f  mov     eax, 80004003h
0x18000c864  jmp     short loc_18000C8B3
0x18000c866  mov     qword ptr [r9], 0
0x18000c86d  mov     ecx, 80004002h
0x18000c872  mov     rax, qword ptr cs:IID_IWMDRMReader.Data1
0x18000c879  cmp     rax, [rdx]
0x18000c87c  jnz     short loc_18000C8B1
0x18000c87e  mov     rax, qword ptr cs:IID_IWMDRMReader.Data4
0x18000c885  cmp     rax, [rdx+8]
0x18000c889  jnz     short loc_18000C8B1
0x18000c88b  mov     rcx, [r10+0C0h]
0x18000c892  test    rcx, rcx
0x18000c895  jz      short loc_18000C8AC
0x18000c897  mov     rax, [rcx]
0x18000c89a  mov     r8, r9
0x18000c89d  mov     rdx, r11
0x18000c8a0  mov     rax, [rax]
0x18000c8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8a8  mov     ecx, eax
0x18000c8aa  jmp     short loc_18000C8B1
0x18000c8ac  mov     ecx, 80004005h
0x18000c8b1  mov     eax, ecx
0x18000c8b3  add     rsp, 28h
0x18000c8b7  retn
```
