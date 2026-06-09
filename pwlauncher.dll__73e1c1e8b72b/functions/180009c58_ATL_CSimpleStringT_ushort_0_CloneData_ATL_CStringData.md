# ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)

- ea: `0x180009c58`
- end: `0x180009cdd`
- name: `?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z`
- size: `133`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000946c`
- `0x18000cab8`
- `0x18000e948`
- `0x18000eb10`

## callees

- `0x180009c58`
- `0x18000b14c`
- `0x180011010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009cc3`
- `msvcrt!memcpy_s` at `0x180009cc3`

## pseudocode

```c
volatile signed __int32 *__fastcall ATL::CSimpleStringT<unsigned short,0>::CloneData(volatile signed __int32 *a1)
{
  __int64 (__fastcall ***v2)(_QWORD, _QWORD, __int64); // rax
  volatile signed __int32 *v3; // rdi
  __int64 v4; // rax
  rsize_t v5; // r9

  v2 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1);
  if ( *((int *)a1 + 4) >= 0 && v2 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))a1 )
  {
    v3 = a1;
    _InterlockedIncrement(a1 + 4);
  }
  else
  {
    v4 = (**v2)(v2, *((unsigned int *)a1 + 2), 2);
    v3 = (volatile signed __int32 *)v4;
    if ( !v4 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException();
    *(_DWORD *)(v4 + 8) = *((_DWORD *)a1 + 2);
    v5 = 2LL * (*((_DWORD *)a1 + 2) + 1);
    memcpy_s((void *const)(v4 + 24), v5, (const void *const)(a1 + 6), v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180009c58  mov     [rsp+arg_0], rbx
0x180009c5d  push    rdi
0x180009c5e  sub     rsp, 20h
0x180009c62  mov     rbx, rcx
0x180009c65  mov     rcx, [rcx]
0x180009c68  mov     rax, [rcx]
0x180009c6b  mov     rax, [rax+20h]
0x180009c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c74  cmp     dword ptr [rbx+10h], 0
0x180009c78  mov     rcx, rax
0x180009c7b  jl      short loc_180009C8B
0x180009c7d  cmp     rax, [rbx]
0x180009c80  jnz     short loc_180009C8B
0x180009c82  mov     rdi, rbx
0x180009c85  lock inc dword ptr [rbx+10h]
0x180009c89  jmp     short loc_180009CC9
0x180009c8b  mov     rax, [rax]
0x180009c8e  mov     r8d, 2
0x180009c94  mov     edx, [rbx+8]
0x180009c97  mov     rax, [rax]
0x180009c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c9f  mov     rdi, rax
0x180009ca2  test    rax, rax
0x180009ca5  jz      short loc_180009CD7
0x180009ca7  mov     eax, [rbx+8]
0x180009caa  lea     r8, [rbx+18h]; Source
0x180009cae  mov     [rdi+8], eax
0x180009cb1  lea     rcx, [rdi+18h]; Destination
0x180009cb5  mov     eax, [rbx+8]
0x180009cb8  inc     eax
0x180009cba  movsxd  rdx, eax
0x180009cbd  add     rdx, rdx; DestinationSize
0x180009cc0  mov     r9, rdx; SourceSize
0x180009cc3  call    cs:__imp_memcpy_s
0x180009cc9  mov     rbx, [rsp+28h+arg_0]
0x180009cce  mov     rax, rdi
0x180009cd1  add     rsp, 20h
0x180009cd5  pop     rdi
0x180009cd6  retn
0x180009cd7  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
```
