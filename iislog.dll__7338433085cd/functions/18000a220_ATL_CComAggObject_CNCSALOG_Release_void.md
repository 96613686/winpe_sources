# ATL::CComAggObject<CNCSALOG>::Release(void)

- ea: `0x18000a220`
- end: `0x18000a29c`
- name: `?Release@?$CComAggObject@VCNCSALOG@@@ATL@@UEAAKXZ`
- size: `124`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x1800075f4`
- `0x18000a220`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CNCSALOG>::Release(char *Block)
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
      *(_QWORD *)Block = &ATL::CComAggObject<CNCSALOG>::`vftable';
      _InterlockedDecrement(&dword_180017A78);
      CNCSALOG::~CNCSALOG((CNCSALOG *)(Block + 24));
      operator delete(Block);
    }
    _InterlockedDecrement(&dword_180017A78);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a220  mov     [rsp+arg_0], rbx
0x18000a225  push    rdi
0x18000a226  sub     rsp, 20h
0x18000a22a  mov     rbx, rcx
0x18000a22d  mov     r8d, 7FFFFFFFh
0x18000a233  mov     ecx, [rcx+8]
0x18000a236  jmp     short loc_18000A247
0x18000a238  lea     edx, [rcx-1]
0x18000a23b  mov     eax, ecx
0x18000a23d  lock cmpxchg [rbx+8], edx
0x18000a242  jz      short loc_18000A24C
0x18000a244  mov     ecx, [rbx+8]
0x18000a247  cmp     ecx, r8d
0x18000a24a  jnz     short loc_18000A238
0x18000a24c  lea     edi, [rcx-1]
0x18000a24f  test    edi, edi
0x18000a251  jnz     short loc_18000A28F
0x18000a253  lock inc cs:dword_180017A78
0x18000a25a  test    rbx, rbx
0x18000a25d  jz      short loc_18000A288
0x18000a25f  lea     rax, ??_7?$CComAggObject@VCNCSALOG@@@ATL@@6B@; const ATL::CComAggObject<CNCSALOG>::`vftable'
0x18000a266  mov     dword ptr [rbx+8], 1
0x18000a26d  mov     [rbx], rax
0x18000a270  lea     rcx, [rbx+18h]; this
0x18000a274  lock dec cs:dword_180017A78
0x18000a27b  call    ??1CNCSALOG@@MEAA@XZ; CNCSALOG::~CNCSALOG(void)
0x18000a280  mov     rcx, rbx; Block
0x18000a283  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a288  lock dec cs:dword_180017A78
0x18000a28f  mov     rbx, [rsp+28h+arg_0]
0x18000a294  mov     eax, edi
0x18000a296  add     rsp, 20h
0x18000a29a  pop     rdi
0x18000a29b  retn
```
