# ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)

- ea: `0x180004194`
- end: `0x180004219`
- name: `?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000408c`
- `0x18000521c`
- `0x1800080cc`

## callees

- `0x180003a40`
- `0x180004194`
- `0x18000d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004205`
- `msvcrt!memcpy_s` at `0x180004205`

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
0x180004194  mov     [rsp+arg_0], rbx
0x180004199  push    rdi
0x18000419a  sub     rsp, 20h
0x18000419e  mov     rbx, rcx
0x1800041a1  mov     rcx, [rcx]
0x1800041a4  mov     rax, [rcx]
0x1800041a7  mov     rax, [rax+20h]
0x1800041ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b0  cmp     dword ptr [rbx+10h], 0
0x1800041b4  mov     rcx, rax
0x1800041b7  jl      short loc_1800041C7
0x1800041b9  cmp     rax, [rbx]
0x1800041bc  jnz     short loc_1800041C7
0x1800041be  mov     rdi, rbx
0x1800041c1  lock inc dword ptr [rbx+10h]
0x1800041c5  jmp     short loc_18000420B
0x1800041c7  mov     rax, [rax]
0x1800041ca  mov     r8d, 2
0x1800041d0  mov     edx, [rbx+8]
0x1800041d3  mov     rax, [rax]
0x1800041d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041db  mov     rdi, rax
0x1800041de  test    rax, rax
0x1800041e1  jnz     short loc_1800041E9
0x1800041e3  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x1800041e9  mov     eax, [rbx+8]
0x1800041ec  lea     r8, [rbx+18h]; Source
0x1800041f0  mov     [rdi+8], eax
0x1800041f3  lea     rcx, [rdi+18h]; Destination
0x1800041f7  mov     eax, [rbx+8]
0x1800041fa  inc     eax
0x1800041fc  movsxd  rdx, eax
0x1800041ff  add     rdx, rdx; DestinationSize
0x180004202  mov     r9, rdx; SourceSize
0x180004205  call    cs:__imp_memcpy_s
0x18000420b  mov     rbx, [rsp+28h+arg_0]
0x180004210  mov     rax, rdi
0x180004213  add     rsp, 20h
0x180004217  pop     rdi
0x180004218  retn
```
