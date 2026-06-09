# ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::Init(IConnectionPoint * *,IConnectionPoint * *,IUnknown *,ATL::CComEnumFlags)

- ea: `0x18000f23c`
- end: `0x18000f344`
- name: `?Init@?$CComEnumImpl@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@V?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAAJPEAPEAUIConnectionPoint@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000c9fc`
- `0x18000e560`

## callees

- `0x18000173c`
- `0x18000178c`
- `0x1800095d4`
- `0x18000a6cc`
- `0x18000f23c`
- `0x180012d1c`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::Init(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct IUnknown *a4,
        int a5)
{
  __int64 v6; // rsi
  __int64 v7; // rdi
  __int64 v9; // r15
  void *v10; // rax
  __int64 result; // rax
  int v12; // ebp
  unsigned __int64 i; // rdi
  unsigned __int64 v14; // rcx

  v6 = a3;
  v7 = a2;
  if ( a5 == 3 )
  {
    v9 = (a3 - a2) >> 3;
    v10 = operator new(saturated_mul((unsigned int)v9, 8u));
    *(_QWORD *)(a1 + 16) = v10;
    *(_QWORD *)(a1 + 32) = v10;
    if ( v10 )
    {
      while ( 1 )
      {
        if ( v7 == v6 )
        {
          v6 = *(_QWORD *)(a1 + 16) + 8 * v9;
          goto LABEL_13;
        }
        v12 = ATL::_CopyInterface<IConnectionPoint>::copy(v10, v7);
        if ( v12 < 0 )
          break;
        *(_QWORD *)(a1 + 32) += 8LL;
        v10 = *(void **)(a1 + 32);
        v7 += 8;
      }
      for ( i = *(_QWORD *)(a1 + 16); i < *(_QWORD *)(a1 + 32); i += 8LL )
      {
        v14 = i;
        ATL::_CopyInterface<IConnectionPoint>::destroy(v14);
      }
      operator delete(*(void **)(a1 + 16));
      result = (unsigned int)v12;
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 16) = 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    *(_QWORD *)(a1 + 16) = a2;
LABEL_13:
    *(_QWORD *)(a1 + 24) = v6;
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 8), a4);
    *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 16);
    result = 0;
    *(_DWORD *)(a1 + 40) = a5;
  }
  return result;
}

```

## disassembly

```asm
0x18000f23c  push    rbx
0x18000f23e  push    rbp
0x18000f23f  push    rsi
0x18000f240  push    rdi
0x18000f241  push    r12
0x18000f243  push    r14
0x18000f245  push    r15
0x18000f247  sub     rsp, 20h
0x18000f24b  mov     r14d, [rsp+58h+arg_20]
0x18000f253  mov     r12, r9
0x18000f256  mov     rsi, r8
0x18000f259  mov     rdi, rdx
0x18000f25c  mov     rbx, rcx
0x18000f25f  cmp     r14d, 3
0x18000f263  jnz     loc_18000F313
0x18000f269  mov     r15, r8
0x18000f26c  lea     eax, [r14+5]
0x18000f270  sub     r15, rdx
0x18000f273  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f27a  sar     r15, 3
0x18000f27e  mov     r8d, r15d
0x18000f281  mul     r8
0x18000f284  cmovb   rax, rcx
0x18000f288  mov     rcx, rax; Size
0x18000f28b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f290  mov     [rbx+10h], rax
0x18000f294  mov     [rbx+20h], rax
0x18000f298  test    rax, rax
0x18000f29b  jnz     short loc_18000F2A7
0x18000f29d  mov     eax, 8007000Eh
0x18000f2a2  jmp     loc_18000F335
0x18000f2a7  cmp     rdi, rsi
0x18000f2aa  jz      short loc_18000F309
0x18000f2ac  mov     rdx, rdi
0x18000f2af  mov     rcx, rax
0x18000f2b2  call    ?copy@?$_CopyInterface@UIConnectionPoint@@@ATL@@SAJPEAPEAUIConnectionPoint@@0@Z; ATL::_CopyInterface<IConnectionPoint>::copy(IConnectionPoint * *,IConnectionPoint * *)
0x18000f2b7  mov     ebp, eax
0x18000f2b9  test    eax, eax
0x18000f2bb  js      short loc_18000F2CC
0x18000f2bd  add     qword ptr [rbx+20h], 8
0x18000f2c2  mov     rax, [rbx+20h]
0x18000f2c6  add     rdi, 8
0x18000f2ca  jmp     short loc_18000F2A7
0x18000f2cc  mov     rdi, [rbx+10h]
0x18000f2d0  jmp     short loc_18000F2DE
0x18000f2d2  mov     rcx, rdi
0x18000f2d5  add     rdi, 8
0x18000f2d9  call    ?destroy@?$_CopyInterface@UIConnectionPoint@@@ATL@@SAXPEAPEAUIConnectionPoint@@@Z; ATL::_CopyInterface<IConnectionPoint>::destroy(IConnectionPoint * *)
0x18000f2de  cmp     rdi, [rbx+20h]
0x18000f2e2  jb      short loc_18000F2D2
0x18000f2e4  mov     rcx, [rbx+10h]; Block
0x18000f2e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f2ed  mov     eax, ebp
0x18000f2ef  mov     qword ptr [rbx+20h], 0
0x18000f2f7  mov     qword ptr [rbx+18h], 0
0x18000f2ff  mov     qword ptr [rbx+10h], 0
0x18000f307  jmp     short loc_18000F335
0x18000f309  mov     rax, [rbx+10h]
0x18000f30d  lea     rsi, [rax+r15*8]
0x18000f311  jmp     short loc_18000F317
0x18000f313  mov     [rcx+10h], rdx
0x18000f317  lea     rcx, [rbx+8]; struct IUnknown **
0x18000f31b  mov     [rbx+18h], rsi
0x18000f31f  mov     rdx, r12; struct IUnknown *
0x18000f322  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000f327  mov     rax, [rbx+10h]
0x18000f32b  mov     [rbx+20h], rax
0x18000f32f  xor     eax, eax
0x18000f331  mov     [rbx+28h], r14d
0x18000f335  add     rsp, 20h
0x18000f339  pop     r15
0x18000f33b  pop     r14
0x18000f33d  pop     r12
0x18000f33f  pop     rdi
0x18000f340  pop     rsi
0x18000f341  pop     rbp
0x18000f342  pop     rbx
0x18000f343  retn
```
