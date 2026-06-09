# OAuthTokenRequestBase::GetPasswordChangeUrl(void)

- ea: `0x140014c70`
- end: `0x140014d01`
- name: `?GetPasswordChangeUrl@OAuthTokenRequestBase@@UEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `145`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140005458`
- `0x14000e000`
- `0x140014c70`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
_QWORD *__fastcall OAuthTokenRequestBase::GetPasswordChangeUrl(__int64 *a1, _QWORD *a2)
{
  int v5; // eax
  _BYTE pExceptionObject[32]; // [rsp+28h] [rbp-20h] BYREF

  if ( (*(unsigned int (__fastcall **)(__int64 *))(*a1 + 48))(a1) )
  {
    v5 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 48))(a1);
    InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, v5);
    throw (InvalidCallException *)pExceptionObject;
  }
  if ( !a1[16] )
  {
    InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, -894894032);
    throw (InvalidCallException *)pExceptionObject;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a2,
    a1 + 16);
  return a2;
}

```

## disassembly

```asm
0x140014c70  mov     [rsp+arg_0], rbx
0x140014c75  push    rdi
0x140014c76  sub     rsp, 40h
0x140014c7a  mov     rax, [rcx]
0x140014c7d  mov     rdi, rdx
0x140014c80  mov     rbx, rcx
0x140014c83  mov     rax, [rax+30h]
0x140014c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c8c  test    eax, eax
0x140014c8e  jnz     short loc_140014CD4
0x140014c90  lea     rdx, [rbx+80h]
0x140014c97  cmp     qword ptr [rdx], 0
0x140014c9b  jz      short loc_140014CB3
0x140014c9d  mov     rcx, rdi
0x140014ca0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140014ca5  mov     rbx, [rsp+48h+arg_0]
0x140014caa  mov     rax, rdi
0x140014cad  add     rsp, 40h
0x140014cb1  pop     rdi
0x140014cb2  retn
0x140014cb3  mov     edx, 0CAA90030h; unsigned int
0x140014cb8  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140014cbd  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x140014cc2  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x140014cc9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140014cce  call    _CxxThrowException_0
0x140014cd4  mov     rax, [rbx]
0x140014cd7  mov     rcx, rbx
0x140014cda  mov     rax, [rax+30h]
0x140014cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ce3  mov     edx, eax; unsigned int
0x140014ce5  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140014cea  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x140014cef  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x140014cf6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140014cfb  call    _CxxThrowException_0
```
