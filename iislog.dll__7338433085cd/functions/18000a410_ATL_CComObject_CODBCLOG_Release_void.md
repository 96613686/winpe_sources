# ATL::CComObject<CODBCLOG>::Release(void)

- ea: `0x18000a410`
- end: `0x18000a48b`
- name: `?Release@?$CComObject@VCODBCLOG@@@ATL@@UEAAKXZ`
- size: `123`
- prototype: `__int64 __fastcall(CODBCLOG *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x18000a410`
- `0x18000a774`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CODBCLOG>::Release(CODBCLOG *this)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)this + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)this + 2, i - 1, i);
        i = *((_DWORD *)this + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    _InterlockedIncrement(&dword_180017A78);
    if ( this )
    {
      *((_DWORD *)this + 2) = 1;
      *(_QWORD *)this = &ATL::CComObject<CODBCLOG>::`vftable';
      _InterlockedDecrement(&dword_180017A78);
      CODBCLOG::~CODBCLOG(this);
      operator delete(this);
    }
    _InterlockedDecrement(&dword_180017A78);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a410  mov     [rsp+arg_0], rbx
0x18000a415  push    rdi
0x18000a416  sub     rsp, 20h
0x18000a41a  mov     rbx, rcx
0x18000a41d  mov     r8d, 7FFFFFFFh
0x18000a423  mov     ecx, [rcx+8]
0x18000a426  jmp     short loc_18000A437
0x18000a428  lea     edx, [rcx-1]
0x18000a42b  mov     eax, ecx
0x18000a42d  lock cmpxchg [rbx+8], edx
0x18000a432  jz      short loc_18000A43C
0x18000a434  mov     ecx, [rbx+8]
0x18000a437  cmp     ecx, r8d
0x18000a43a  jnz     short loc_18000A428
0x18000a43c  lea     edi, [rcx-1]
0x18000a43f  test    edi, edi
0x18000a441  jnz     short loc_18000A47E
0x18000a443  lock inc cs:dword_180017A78
0x18000a44a  test    rbx, rbx
0x18000a44d  jz      short loc_18000A477
0x18000a44f  lea     rax, ??_7?$CComObject@VCODBCLOG@@@ATL@@6B@; const ATL::CComObject<CODBCLOG>::`vftable'
0x18000a456  mov     dword ptr [rbx+8], 1
0x18000a45d  mov     [rbx], rax
0x18000a460  mov     rcx, rbx; this
0x18000a463  lock dec cs:dword_180017A78
0x18000a46a  call    ??1CODBCLOG@@IEAA@XZ; CODBCLOG::~CODBCLOG(void)
0x18000a46f  mov     rcx, rbx; Block
0x18000a472  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a477  lock dec cs:dword_180017A78
0x18000a47e  mov     rbx, [rsp+28h+arg_0]
0x18000a483  mov     eax, edi
0x18000a485  add     rsp, 20h
0x18000a489  pop     rdi
0x18000a48a  retn
```
