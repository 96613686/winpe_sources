# ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)

- ea: `0x180006d38`
- end: `0x180006dbd`
- name: `?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z`
- size: `133`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012d0`
- `0x1800065c0`
- `0x18000a360`
- `0x18000aa08`
- `0x18000bc98`
- `0x18000dd60`

## callees

- `0x180006d38`
- `0x18000dd28`
- `0x180013010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006da9`
- `msvcrt!memcpy_s` at `0x180006da9`

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
0x180006d38  mov     [rsp+arg_0], rbx
0x180006d3d  push    rdi
0x180006d3e  sub     rsp, 20h
0x180006d42  mov     rbx, rcx
0x180006d45  mov     rcx, [rcx]
0x180006d48  mov     rax, [rcx]
0x180006d4b  mov     rax, [rax+20h]
0x180006d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d54  cmp     dword ptr [rbx+10h], 0
0x180006d58  mov     rcx, rax
0x180006d5b  jl      short loc_180006D6B
0x180006d5d  cmp     rax, [rbx]
0x180006d60  jnz     short loc_180006D6B
0x180006d62  mov     rdi, rbx
0x180006d65  lock inc dword ptr [rbx+10h]
0x180006d69  jmp     short loc_180006DAF
0x180006d6b  mov     rax, [rax]
0x180006d6e  mov     r8d, 2
0x180006d74  mov     edx, [rbx+8]
0x180006d77  mov     rax, [rax]
0x180006d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d7f  mov     rdi, rax
0x180006d82  test    rax, rax
0x180006d85  jnz     short loc_180006D8D
0x180006d87  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x180006d8d  mov     eax, [rbx+8]
0x180006d90  lea     r8, [rbx+18h]; Source
0x180006d94  mov     [rdi+8], eax
0x180006d97  lea     rcx, [rdi+18h]; Destination
0x180006d9b  mov     eax, [rbx+8]
0x180006d9e  inc     eax
0x180006da0  movsxd  rdx, eax
0x180006da3  add     rdx, rdx; DestinationSize
0x180006da6  mov     r9, rdx; SourceSize
0x180006da9  call    cs:__imp_memcpy_s
0x180006daf  mov     rbx, [rsp+28h+arg_0]
0x180006db4  mov     rax, rdi
0x180006db7  add     rsp, 20h
0x180006dbb  pop     rdi
0x180006dbc  retn
```
