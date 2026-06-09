# ATL::CComAggObject<CODBCLOG>::Release(void)

- ea: `0x18000a2b0`
- end: `0x18000a32c`
- name: `?Release@?$CComAggObject@VCODBCLOG@@@ATL@@UEAAKXZ`
- size: `124`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x18000a2b0`
- `0x18000a774`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CODBCLOG>::Release(char *Block)
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
      *(_QWORD *)Block = &ATL::CComAggObject<CODBCLOG>::`vftable';
      _InterlockedDecrement(&dword_180017A78);
      CODBCLOG::~CODBCLOG((CODBCLOG *)(Block + 24));
      operator delete(Block);
    }
    _InterlockedDecrement(&dword_180017A78);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a2b0  mov     [rsp+arg_0], rbx
0x18000a2b5  push    rdi
0x18000a2b6  sub     rsp, 20h
0x18000a2ba  mov     rbx, rcx
0x18000a2bd  mov     r8d, 7FFFFFFFh
0x18000a2c3  mov     ecx, [rcx+8]
0x18000a2c6  jmp     short loc_18000A2D7
0x18000a2c8  lea     edx, [rcx-1]
0x18000a2cb  mov     eax, ecx
0x18000a2cd  lock cmpxchg [rbx+8], edx
0x18000a2d2  jz      short loc_18000A2DC
0x18000a2d4  mov     ecx, [rbx+8]
0x18000a2d7  cmp     ecx, r8d
0x18000a2da  jnz     short loc_18000A2C8
0x18000a2dc  lea     edi, [rcx-1]
0x18000a2df  test    edi, edi
0x18000a2e1  jnz     short loc_18000A31F
0x18000a2e3  lock inc cs:dword_180017A78
0x18000a2ea  test    rbx, rbx
0x18000a2ed  jz      short loc_18000A318
0x18000a2ef  lea     rax, ??_7?$CComAggObject@VCODBCLOG@@@ATL@@6B@; const ATL::CComAggObject<CODBCLOG>::`vftable'
0x18000a2f6  mov     dword ptr [rbx+8], 1
0x18000a2fd  mov     [rbx], rax
0x18000a300  lea     rcx, [rbx+18h]; this
0x18000a304  lock dec cs:dword_180017A78
0x18000a30b  call    ??1CODBCLOG@@IEAA@XZ; CODBCLOG::~CODBCLOG(void)
0x18000a310  mov     rcx, rbx; Block
0x18000a313  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a318  lock dec cs:dword_180017A78
0x18000a31f  mov     rbx, [rsp+28h+arg_0]
0x18000a324  mov     eax, edi
0x18000a326  add     rsp, 20h
0x18000a32a  pop     rdi
0x18000a32b  retn
```
