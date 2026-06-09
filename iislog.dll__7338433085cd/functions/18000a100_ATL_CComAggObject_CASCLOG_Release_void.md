# ATL::CComAggObject<CASCLOG>::Release(void)

- ea: `0x18000a100`
- end: `0x18000a17c`
- name: `?Release@?$CComAggObject@VCASCLOG@@@ATL@@UEAAKXZ`
- size: `124`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x18000a100`
- `0x18000bf30`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CASCLOG>::Release(char *Block)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)Block + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, i - 1, i);
        i = *((_DWORD *)Block + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    _InterlockedIncrement(&dword_180017A78);
    if ( Block )
    {
      *((_DWORD *)Block + 2) = 1;
      *(_QWORD *)Block = &ATL::CComAggObject<CASCLOG>::`vftable';
      _InterlockedDecrement(&dword_180017A78);
      CASCLOG::~CASCLOG((CASCLOG *)(Block + 24));
      operator delete(Block);
    }
    _InterlockedDecrement(&dword_180017A78);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a100  mov     [rsp+arg_0], rbx
0x18000a105  push    rdi
0x18000a106  sub     rsp, 20h
0x18000a10a  mov     rbx, rcx
0x18000a10d  mov     r8d, 7FFFFFFFh
0x18000a113  mov     ecx, [rcx+8]
0x18000a116  jmp     short loc_18000A127
0x18000a118  lea     edx, [rcx-1]
0x18000a11b  mov     eax, ecx
0x18000a11d  lock cmpxchg [rbx+8], edx
0x18000a122  jz      short loc_18000A12C
0x18000a124  mov     ecx, [rbx+8]
0x18000a127  cmp     ecx, r8d
0x18000a12a  jnz     short loc_18000A118
0x18000a12c  lea     edi, [rcx-1]
0x18000a12f  test    edi, edi
0x18000a131  jnz     short loc_18000A16F
0x18000a133  lock inc cs:dword_180017A78
0x18000a13a  test    rbx, rbx
0x18000a13d  jz      short loc_18000A168
0x18000a13f  lea     rax, ??_7?$CComAggObject@VCASCLOG@@@ATL@@6B@; const ATL::CComAggObject<CASCLOG>::`vftable'
0x18000a146  mov     dword ptr [rbx+8], 1
0x18000a14d  mov     [rbx], rax
0x18000a150  lea     rcx, [rbx+18h]; this
0x18000a154  lock dec cs:dword_180017A78
0x18000a15b  call    ??1CASCLOG@@MEAA@XZ; CASCLOG::~CASCLOG(void)
0x18000a160  mov     rcx, rbx; Block
0x18000a163  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a168  lock dec cs:dword_180017A78
0x18000a16f  mov     rbx, [rsp+28h+arg_0]
0x18000a174  mov     eax, edi
0x18000a176  add     rsp, 20h
0x18000a17a  pop     rdi
0x18000a17b  retn
```
