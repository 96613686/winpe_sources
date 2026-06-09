# ATL::CComAggObject<CEXTLOG>::Release(void)

- ea: `0x18000a190`
- end: `0x18000a20c`
- name: `?Release@?$CComAggObject@VCEXTLOG@@@ATL@@UEAAKXZ`
- size: `124`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x180003984`
- `0x18000a190`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CEXTLOG>::Release(char *Block)
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
      *(_QWORD *)Block = &ATL::CComAggObject<CEXTLOG>::`vftable';
      _InterlockedDecrement(&dword_180017A78);
      CEXTLOG::~CEXTLOG((CEXTLOG *)(Block + 24));
      operator delete(Block);
    }
    _InterlockedDecrement(&dword_180017A78);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a190  mov     [rsp+arg_0], rbx
0x18000a195  push    rdi
0x18000a196  sub     rsp, 20h
0x18000a19a  mov     rbx, rcx
0x18000a19d  mov     r8d, 7FFFFFFFh
0x18000a1a3  mov     ecx, [rcx+8]
0x18000a1a6  jmp     short loc_18000A1B7
0x18000a1a8  lea     edx, [rcx-1]
0x18000a1ab  mov     eax, ecx
0x18000a1ad  lock cmpxchg [rbx+8], edx
0x18000a1b2  jz      short loc_18000A1BC
0x18000a1b4  mov     ecx, [rbx+8]
0x18000a1b7  cmp     ecx, r8d
0x18000a1ba  jnz     short loc_18000A1A8
0x18000a1bc  lea     edi, [rcx-1]
0x18000a1bf  test    edi, edi
0x18000a1c1  jnz     short loc_18000A1FF
0x18000a1c3  lock inc cs:dword_180017A78
0x18000a1ca  test    rbx, rbx
0x18000a1cd  jz      short loc_18000A1F8
0x18000a1cf  lea     rax, ??_7?$CComAggObject@VCEXTLOG@@@ATL@@6B@; const ATL::CComAggObject<CEXTLOG>::`vftable'
0x18000a1d6  mov     dword ptr [rbx+8], 1
0x18000a1dd  mov     [rbx], rax
0x18000a1e0  lea     rcx, [rbx+18h]; this
0x18000a1e4  lock dec cs:dword_180017A78
0x18000a1eb  call    ??1CEXTLOG@@MEAA@XZ; CEXTLOG::~CEXTLOG(void)
0x18000a1f0  mov     rcx, rbx; Block
0x18000a1f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a1f8  lock dec cs:dword_180017A78
0x18000a1ff  mov     rbx, [rsp+28h+arg_0]
0x18000a204  mov     eax, edi
0x18000a206  add     rsp, 20h
0x18000a20a  pop     rdi
0x18000a20b  retn
```
