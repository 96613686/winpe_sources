# CKsOutputPin2::CompleteConnect(IPin *)

- ea: `0x18002dc30`
- end: `0x18002dcbf`
- name: `?CompleteConnect@CKsOutputPin2@@UEAAJPEAUIPin@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(CBaseOutputPin *this, struct IPin *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000b6fc`
- `0x18002dc30`
- `0x180031e78`
- `0x18003ee50`
- `0x180045010`

## string_xrefs

- `0x18002dc97`: `CKsOutputPin2::CompleteConnect`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::CompleteConnect(CBaseOutputPin *this, struct IPin *a2)
{
  int v4; // ebx
  int v5; // r8d

  v4 = ((__int64 (__fastcall *)(CBaseOutputPin *))this->CBasePin::CUnknown::INonDelegatingUnknown::__vftable[1].NonDelegatingQueryInterface)(this);
  if ( v4 >= 0 )
  {
    v4 = CBaseOutputPin::CompleteConnect(this, a2);
    if ( v4 >= 0 )
      CKsProxy::GeneratePinInstances((CKsProxy *)this->m_pFilter, this[4].m_mt.subtype.Data1);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v5, (unsigned int)"CKsOutputPin2::CompleteConnect", v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002dc30  mov     [rsp+arg_0], rbx
0x18002dc35  mov     [rsp+arg_8], rsi
0x18002dc3a  push    rdi
0x18002dc3b  sub     rsp, 30h
0x18002dc3f  mov     rax, [rcx]
0x18002dc42  mov     rsi, rdx
0x18002dc45  mov     rdi, rcx
0x18002dc48  mov     rax, [rax+0B8h]
0x18002dc4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc54  mov     ebx, eax
0x18002dc56  test    eax, eax
0x18002dc58  js      short loc_18002DC7A
0x18002dc5a  mov     rdx, rsi; struct IPin *
0x18002dc5d  mov     rcx, rdi; this
0x18002dc60  call    ?CompleteConnect@CBaseOutputPin@@UEAAJPEAUIPin@@@Z; CBaseOutputPin::CompleteConnect(IPin *)
0x18002dc65  mov     ebx, eax
0x18002dc67  test    eax, eax
0x18002dc69  js      short loc_18002DC7A
0x18002dc6b  mov     edx, [rdi+418h]; int
0x18002dc71  mov     rcx, [rdi+50h]; this
0x18002dc75  call    ?GeneratePinInstances@CKsProxy@@QEAAJH@Z; CKsProxy::GeneratePinInstances(int)
0x18002dc7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc81  lea     rax, WPP_GLOBAL_Control
0x18002dc88  cmp     rcx, rax
0x18002dc8b  jz      short loc_18002DCAC
0x18002dc8d  cmp     byte ptr [rcx+19h], 2
0x18002dc91  jb      short loc_18002DCAC
0x18002dc93  mov     rcx, [rcx+10h]
0x18002dc97  lea     r9, aCksoutputpin2C; "CKsOutputPin2::CompleteConnect"
0x18002dc9e  mov     edx, 1Ah
0x18002dca3  mov     [rsp+38h+var_18], ebx
0x18002dca7  call    WPP_SF_sd
0x18002dcac  mov     rsi, [rsp+38h+arg_8]
0x18002dcb1  mov     eax, ebx
0x18002dcb3  mov     rbx, [rsp+38h+arg_0]
0x18002dcb8  add     rsp, 30h
0x18002dcbc  pop     rdi
0x18002dcbd  retn
```
