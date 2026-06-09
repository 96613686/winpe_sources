# CKsOutputPin::CompletePartialMediaType(CMediaType *,_AMMediaType * *)

- ea: `0x18002998c`
- end: `0x180029ac4`
- name: `?CompletePartialMediaType@CKsOutputPin@@QEAAJPEAVCMediaType@@PEAPEAU_AMMediaType@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(CKsOutputPin *this, struct CMediaType *, struct _AMMediaType **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c620`
- `0x180031360`

## callees

- `0x18001b190`
- `0x18002998c`
- `0x18003e1cc`
- `0x18003e22c`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::CompletePartialMediaType(
        CKsOutputPin *this,
        struct CMediaType *a2,
        struct _AMMediaType **a3)
{
  struct _AMMediaType *MediaType; // rax
  struct _AMMediaType *v7; // r14
  unsigned int m_PinFactoryId; // ebx
  __int64 (__fastcall *v9)(__int64, __int64, _QWORD, struct _AMMediaType *); // rdi
  __int64 v10; // rax
  int v11; // ebx
  struct IUnknown *v12; // rcx
  __int64 v14; // [rsp+60h] [rbp+30h] BYREF
  struct IUnknown *v15; // [rsp+70h] [rbp+40h] BYREF
  struct IKsDataTypeHandler *v16; // [rsp+78h] [rbp+48h] BYREF

  v16 = 0;
  v15 = 0;
  v14 = 0;
  OpenDataHandler(
    a2,
    (LPUNKNOWN)((unsigned __int64)&this->IPin & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    &v16,
    (LPVOID *)&v15);
  if ( v15 )
  {
    if ( v15->QueryInterface(v15, &GUID_827d1a0e_0f73_11d2_b27a_00a0c9223196, (void **)&v14) >= 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  else
  {
    v14 = 0;
  }
  MediaType = CreateMediaType(a2);
  *a3 = MediaType;
  v7 = MediaType;
  if ( MediaType )
  {
    if ( v14 )
    {
      m_PinFactoryId = this->m_PinFactoryId;
      v9 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct _AMMediaType *))(*(_QWORD *)v14 + 24LL);
      v10 = ((__int64 (__fastcall *)(IReferenceClock **))this->m_pFilter[1].m_pClock[3].__vftable)(&this->m_pFilter[1].m_pClock);
      v11 = v9(v14, v10, m_PinFactoryId, v7);
      if ( v11 < 0 )
      {
        DeleteMediaType(*a3);
        *a3 = 0;
      }
    }
    else
    {
      v11 = 0;
    }
  }
  else
  {
    v11 = -2147024882;
  }
  v12 = v15;
  if ( v15 )
  {
    v15 = 0;
    v12->Release(v12);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002998c  mov     [rsp-28h+arg_8], rbx
0x180029991  push    rbp
0x180029992  push    rsi
0x180029993  push    rdi
0x180029994  push    r14
0x180029996  push    r15
0x180029998  mov     rbp, rsp
0x18002999b  sub     rsp, 30h
0x18002999f  mov     rbx, rdx
0x1800299a2  mov     [rbp+arg_18], 0
0x1800299aa  lea     r9, [rcx+18h]
0x1800299ae  mov     [rbp+arg_10], 0
0x1800299b6  mov     rax, rcx
0x1800299b9  mov     [rbp+arg_0], 0
0x1800299c1  neg     rax
0x1800299c4  mov     rsi, r8
0x1800299c7  mov     r15, rcx
0x1800299ca  lea     r8, [rbp+arg_18]; struct IKsDataTypeHandler **
0x1800299ce  sbb     rdx, rdx
0x1800299d1  mov     rcx, rbx; rclsid
0x1800299d4  and     rdx, r9; pUnkOuter
0x1800299d7  lea     r9, [rbp+arg_10]; struct IUnknown **
0x1800299db  call    ?OpenDataHandler@@YAXPEBVCMediaType@@PEAUIUnknown@@PEAPEAUIKsDataTypeHandler@@PEAPEAU2@@Z; OpenDataHandler(CMediaType const *,IUnknown *,IKsDataTypeHandler * *,IUnknown * *)
0x1800299e0  mov     rcx, [rbp+arg_10]
0x1800299e4  test    rcx, rcx
0x1800299e7  jz      short loc_180029A15
0x1800299e9  mov     rax, [rcx]
0x1800299ec  lea     r8, [rbp+arg_0]
0x1800299f0  lea     rdx, _GUID_827d1a0e_0f73_11d2_b27a_00a0c9223196
0x1800299f7  mov     rax, [rax]
0x1800299fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299ff  test    eax, eax
0x180029a01  js      short loc_180029A1D
0x180029a03  mov     rcx, [rbp+arg_0]
0x180029a07  mov     rax, [rcx]
0x180029a0a  mov     rax, [rax+10h]
0x180029a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a13  jmp     short loc_180029A1D
0x180029a15  mov     [rbp+arg_0], 0
0x180029a1d  mov     rcx, rbx; const struct _AMMediaType *
0x180029a20  call    ?CreateMediaType@@YAPEAU_AMMediaType@@PEBU1@@Z; CreateMediaType(_AMMediaType const *)
0x180029a25  mov     [rsi], rax
0x180029a28  mov     r14, rax
0x180029a2b  test    rax, rax
0x180029a2e  jz      short loc_180029A8E
0x180029a30  mov     rcx, [rbp+arg_0]
0x180029a34  test    rcx, rcx
0x180029a37  jz      short loc_180029A8A
0x180029a39  mov     rcx, [rcx]
0x180029a3c  mov     ebx, [r15+248h]
0x180029a43  mov     rdi, [rcx+18h]
0x180029a47  mov     rcx, [r15+50h]
0x180029a4b  add     rcx, 0A8h
0x180029a52  mov     rdx, [rcx]
0x180029a55  mov     rax, [rdx+18h]
0x180029a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a5e  mov     rcx, [rbp+arg_0]
0x180029a62  mov     rdx, rax
0x180029a65  mov     rax, rdi
0x180029a68  mov     r9, r14
0x180029a6b  mov     r8d, ebx
0x180029a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a73  mov     ebx, eax
0x180029a75  test    eax, eax
0x180029a77  jns     short loc_180029A93
0x180029a79  mov     rcx, [rsi]; pv
0x180029a7c  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180029a81  mov     qword ptr [rsi], 0
0x180029a88  jmp     short loc_180029A93
0x180029a8a  xor     ebx, ebx
0x180029a8c  jmp     short loc_180029A93
0x180029a8e  mov     ebx, 8007000Eh
0x180029a93  mov     rcx, [rbp+arg_10]
0x180029a97  test    rcx, rcx
0x180029a9a  jz      short loc_180029AB0
0x180029a9c  mov     [rbp+arg_10], 0
0x180029aa4  mov     rax, [rcx]
0x180029aa7  mov     rax, [rax+10h]
0x180029aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ab0  mov     eax, ebx
0x180029ab2  mov     rbx, [rsp+30h+arg_8]
0x180029ab7  add     rsp, 30h
0x180029abb  pop     r15
0x180029abd  pop     r14
0x180029abf  pop     rdi
0x180029ac0  pop     rsi
0x180029ac1  pop     rbp
0x180029ac2  retn
```
