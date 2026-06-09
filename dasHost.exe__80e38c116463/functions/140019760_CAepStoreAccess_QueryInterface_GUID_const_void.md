# CAepStoreAccess::QueryInterface(_GUID const &,void * *)

- ea: `0x140019760`
- end: `0x1400197e0`
- name: `?QueryInterface@CAepStoreAccess@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(CAepStoreAccess *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140019760`
- `0x14001c010`

## pseudocode

```c
__int64 __fastcall CAepStoreAccess::QueryInterface(CAepStoreAccess *this, const struct _GUID *a2, void **a3)
{
  unsigned int v5; // ebx

  if ( a3 )
  {
    v5 = 0;
    *a3 = 0;
    if ( *(_OWORD *)&GUID_00000000_0000_0000_c000_000000000046 == *(_OWORD *)a2
      || *(_QWORD *)&GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4 == *(_QWORD *)a2->Data4 )
    {
      (*(void (__fastcall **)(CAepStoreAccess *))(*(_QWORD *)this + 8LL))(this);
      *a3 = this;
    }
    else
    {
      return (unsigned int)-2147467262;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x140019760  mov     [rsp+arg_0], rbx
0x140019765  mov     [rsp+arg_8], rsi
0x14001976a  push    rdi
0x14001976b  sub     rsp, 20h
0x14001976f  mov     rsi, r8
0x140019772  mov     rdi, rcx
0x140019775  test    r8, r8
0x140019778  jz      short loc_1400197C9
0x14001977a  xor     ebx, ebx
0x14001977c  mov     [r8], rbx
0x14001977f  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x140019786  cmp     rax, [rdx]
0x140019789  jnz     short loc_140019798
0x14001978b  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140019792  cmp     rax, [rdx+8]
0x140019796  jz      short loc_1400197B1
0x140019798  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1
0x14001979f  cmp     rax, [rdx]
0x1400197a2  jnz     short loc_1400197C2
0x1400197a4  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4
0x1400197ab  cmp     rax, [rdx+8]
0x1400197af  jnz     short loc_1400197C2
0x1400197b1  mov     rax, [rcx]
0x1400197b4  mov     rax, [rax+8]
0x1400197b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400197bd  mov     [rsi], rdi
0x1400197c0  jmp     short loc_1400197CE
0x1400197c2  mov     ebx, 80004002h
0x1400197c7  jmp     short loc_1400197CE
0x1400197c9  mov     ebx, 80070057h
0x1400197ce  mov     rsi, [rsp+28h+arg_8]
0x1400197d3  mov     eax, ebx
0x1400197d5  mov     rbx, [rsp+28h+arg_0]
0x1400197da  add     rsp, 20h
0x1400197de  pop     rdi
0x1400197df  retn
```
