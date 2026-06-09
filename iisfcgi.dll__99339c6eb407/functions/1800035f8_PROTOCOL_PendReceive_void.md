# PROTOCOL::PendReceive(void)

- ea: `0x1800035f8`
- end: `0x1800036af`
- name: `?PendReceive@PROTOCOL@@AEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(PROTOCOL *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003590`
- `0x1800036b8`
- `0x180003ad4`

## callees

- `0x1800033e0`
- `0x1800035f8`
- `0x180008f90`
- `0x180009128`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall PROTOCOL::PendReceive(PROTOCOL *this)
{
  int v1; // edi
  int v3; // edx
  bool v4; // zf
  struct FCGI_BUFFER *v5; // rax

  v1 = 0;
  if ( !*((_DWORD *)this + 27) )
  {
    v3 = 3;
    if ( (unsigned int)(*((_DWORD *)this + 12) - 2) > 1 )
      v3 = 1;
    v4 = *((_QWORD *)this + 15) == 0;
    *((_DWORD *)this + 12) = v3;
    if ( v4 )
    {
      v5 = FCGI_BUFFER::Alloc(*((_DWORD *)this + 34));
      *((_QWORD *)this + 15) = v5;
      if ( !v5 )
        return (unsigned int)-2147024882;
      *((_QWORD *)this + 16) = *(_QWORD *)v5;
    }
    _InterlockedAdd((volatile signed __int32 *)this + 28, 1u);
    v1 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))(**((_QWORD **)this + 4) + 48LL))(
           *((_QWORD *)this + 4),
           0,
           *((_QWORD *)this + 16),
           (unsigned int)(**((_DWORD **)this + 15) + *(_DWORD *)(*((_QWORD *)this + 15) + 8LL) - *((_DWORD *)this + 32)),
           1);
    if ( v1 < 0 )
    {
      FCGI_BUFFER::Free(*((FCGI_BUFFER **)this + 15));
      *((_QWORD *)this + 15) = 0;
      PROTOCOL::DereferenceProtocol(this);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800035f8  mov     [rsp+arg_0], rbx
0x1800035fd  push    rdi
0x1800035fe  sub     rsp, 30h
0x180003602  xor     edi, edi
0x180003604  mov     rbx, rcx
0x180003607  cmp     [rcx+6Ch], edi
0x18000360a  jnz     loc_1800036A2
0x180003610  mov     eax, [rcx+30h]
0x180003613  lea     edx, [rdi+3]
0x180003616  sub     eax, 2
0x180003619  lea     edi, [rdx-2]
0x18000361c  cmp     eax, edi
0x18000361e  cmova   edx, edi
0x180003621  cmp     qword ptr [rcx+78h], 0
0x180003626  mov     [rcx+30h], edx
0x180003629  jnz     short loc_180003650
0x18000362b  mov     ecx, [rcx+88h]; unsigned int
0x180003631  call    ?Alloc@FCGI_BUFFER@@SAPEAV1@K@Z; FCGI_BUFFER::Alloc(ulong)
0x180003636  mov     [rbx+78h], rax
0x18000363a  test    rax, rax
0x18000363d  jnz     short loc_180003646
0x18000363f  mov     edi, 8007000Eh
0x180003644  jmp     short loc_1800036A2
0x180003646  mov     rax, [rax]
0x180003649  mov     [rbx+80h], rax
0x180003650  lock add [rbx+70h], edi
0x180003654  mov     rax, [rbx+78h]
0x180003658  mov     rcx, [rbx+20h]
0x18000365c  mov     r8, [rbx+80h]
0x180003663  mov     [rsp+38h+var_18], edi
0x180003667  mov     r9d, [rax+8]
0x18000366b  mov     rdx, [rcx]
0x18000366e  sub     r9d, [rbx+80h]
0x180003675  add     r9d, [rax]
0x180003678  mov     rax, [rdx+30h]
0x18000367c  xor     edx, edx
0x18000367e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003683  mov     edi, eax
0x180003685  test    eax, eax
0x180003687  jns     short loc_1800036A2
0x180003689  mov     rcx, [rbx+78h]; this
0x18000368d  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x180003692  mov     rcx, rbx; this
0x180003695  mov     qword ptr [rbx+78h], 0
0x18000369d  call    ?DereferenceProtocol@PROTOCOL@@QEAAXXZ; PROTOCOL::DereferenceProtocol(void)
0x1800036a2  mov     rbx, [rsp+38h+arg_0]
0x1800036a7  mov     eax, edi
0x1800036a9  add     rsp, 30h
0x1800036ad  pop     rdi
0x1800036ae  retn
```
