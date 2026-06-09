# CProviderImpersonation::QueryInterface(_GUID const &,void * *)

- ea: `0x140019060`
- end: `0x1400190e0`
- name: `?QueryInterface@CProviderImpersonation@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(CProviderImpersonation *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140019060`
- `0x14001c010`

## pseudocode

```c
__int64 __fastcall CProviderImpersonation::QueryInterface(
        CProviderImpersonation *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v5; // ebx

  if ( a3 )
  {
    v5 = 0;
    *a3 = 0;
    if ( *(_OWORD *)&GUID_00000000_0000_0000_c000_000000000046 == *(_OWORD *)a2
      || *(_QWORD *)&GUID_a19c25bd_c8bb_4a85_a4c7_5e69a6cf7cd3.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)GUID_a19c25bd_c8bb_4a85_a4c7_5e69a6cf7cd3.Data4 == *(_QWORD *)a2->Data4 )
    {
      (*(void (__fastcall **)(CProviderImpersonation *))(*(_QWORD *)this + 8LL))(this);
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
0x140019060  mov     [rsp+arg_0], rbx
0x140019065  mov     [rsp+arg_8], rsi
0x14001906a  push    rdi
0x14001906b  sub     rsp, 20h
0x14001906f  mov     rsi, r8
0x140019072  mov     rdi, rcx
0x140019075  test    r8, r8
0x140019078  jz      short loc_1400190C9
0x14001907a  xor     ebx, ebx
0x14001907c  mov     [r8], rbx
0x14001907f  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x140019086  cmp     rax, [rdx]
0x140019089  jnz     short loc_140019098
0x14001908b  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140019092  cmp     rax, [rdx+8]
0x140019096  jz      short loc_1400190B1
0x140019098  mov     rax, qword ptr cs:_GUID_a19c25bd_c8bb_4a85_a4c7_5e69a6cf7cd3.Data1
0x14001909f  cmp     rax, [rdx]
0x1400190a2  jnz     short loc_1400190C2
0x1400190a4  mov     rax, qword ptr cs:_GUID_a19c25bd_c8bb_4a85_a4c7_5e69a6cf7cd3.Data4
0x1400190ab  cmp     rax, [rdx+8]
0x1400190af  jnz     short loc_1400190C2
0x1400190b1  mov     rax, [rcx]
0x1400190b4  mov     rax, [rax+8]
0x1400190b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400190bd  mov     [rsi], rdi
0x1400190c0  jmp     short loc_1400190CE
0x1400190c2  mov     ebx, 80004002h
0x1400190c7  jmp     short loc_1400190CE
0x1400190c9  mov     ebx, 80070057h
0x1400190ce  mov     rsi, [rsp+28h+arg_8]
0x1400190d3  mov     eax, ebx
0x1400190d5  mov     rbx, [rsp+28h+arg_0]
0x1400190da  add     rsp, 20h
0x1400190de  pop     rdi
0x1400190df  retn
```
