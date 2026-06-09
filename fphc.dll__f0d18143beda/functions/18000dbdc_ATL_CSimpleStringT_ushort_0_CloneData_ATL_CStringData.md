# ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)

- ea: `0x18000dbdc`
- end: `0x18000dc61`
- name: `?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z`
- size: `133`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d238`
- `0x18000d91c`
- `0x18000d9a4`
- `0x18000e920`

## callees

- `0x18000dbdc`
- `0x18000eb7c`
- `0x180012010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000dc47`
- `msvcrt!memcpy_s` at `0x18000dc47`

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
0x18000dbdc  mov     [rsp+arg_0], rbx
0x18000dbe1  push    rdi
0x18000dbe2  sub     rsp, 20h
0x18000dbe6  mov     rbx, rcx
0x18000dbe9  mov     rcx, [rcx]
0x18000dbec  mov     rax, [rcx]
0x18000dbef  mov     rax, [rax+20h]
0x18000dbf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbf8  cmp     dword ptr [rbx+10h], 0
0x18000dbfc  mov     rcx, rax
0x18000dbff  jl      short loc_18000DC0F
0x18000dc01  cmp     rax, [rbx]
0x18000dc04  jnz     short loc_18000DC0F
0x18000dc06  mov     rdi, rbx
0x18000dc09  lock inc dword ptr [rbx+10h]
0x18000dc0d  jmp     short loc_18000DC4D
0x18000dc0f  mov     rax, [rax]
0x18000dc12  mov     r8d, 2
0x18000dc18  mov     edx, [rbx+8]
0x18000dc1b  mov     rax, [rax]
0x18000dc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc23  mov     rdi, rax
0x18000dc26  test    rax, rax
0x18000dc29  jz      short loc_18000DC5B
0x18000dc2b  mov     eax, [rbx+8]
0x18000dc2e  lea     r8, [rbx+18h]; Source
0x18000dc32  mov     [rdi+8], eax
0x18000dc35  lea     rcx, [rdi+18h]; Destination
0x18000dc39  mov     eax, [rbx+8]
0x18000dc3c  inc     eax
0x18000dc3e  movsxd  rdx, eax
0x18000dc41  add     rdx, rdx; DestinationSize
0x18000dc44  mov     r9, rdx; SourceSize
0x18000dc47  call    cs:__imp_memcpy_s
0x18000dc4d  mov     rbx, [rsp+28h+arg_0]
0x18000dc52  mov     rax, rdi
0x18000dc55  add     rsp, 20h
0x18000dc59  pop     rdi
0x18000dc5a  retn
0x18000dc5b  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
```
