# ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Init(IConnectionPoint * *,IConnectionPoint * *,IUnknown *,ATL::CComEnumFlags)

- ea: `0x18000fc4c`
- end: `0x18000fd50`
- name: `?Init@?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@QEAAJPEAPEAUIConnectionPoint@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z`
- size: `260`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800174d0`
- `0x1800185a0`
- `0x1800251a0`
- `0x180028310`
- `0x18002e020`
- `0x180032900`
- `0x180037b30`

## callees

- `0x18000ea20`
- `0x18000fc4c`
- `0x18000fd58`
- `0x18000fdbc`
- `0x18000fdc8`
- `0x180021520`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Init(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct IUnknown *a4,
        int a5)
{
  void **v5; // rdi
  __int64 v7; // rbp
  __int64 v8; // rsi
  unsigned __int64 v10; // r12
  void *v11; // rax
  __int64 result; // rax
  int v13; // r15d
  __int64 *i; // rsi
  __int64 *v15; // rcx

  v5 = (void **)(a1 + 32);
  v7 = a3;
  v8 = a2;
  if ( a5 == 3 )
  {
    v10 = (a3 - a2) >> 3;
    v11 = operator new[](saturated_mul(v10, 8u));
    *(_QWORD *)(a1 + 16) = v11;
    *v5 = v11;
    if ( v11 )
    {
      while ( 1 )
      {
        if ( v8 == v7 )
        {
          v7 = *(_QWORD *)(a1 + 16) + 8 * v10;
          goto LABEL_13;
        }
        v13 = ATL::_CopyInterface<IConnectionPoint>::copy(v11, v8);
        if ( v13 < 0 )
          break;
        *v5 = (char *)*v5 + 8;
        v11 = *v5;
        v8 += 8;
      }
      for ( i = *(__int64 **)(a1 + 16); i < *v5; ++i )
      {
        v15 = i;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v15);
      }
      operator delete[](*(void **)(a1 + 16));
      *v5 = 0;
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 16) = 0;
      return (unsigned int)v13;
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
    *(_QWORD *)(a1 + 24) = v7;
    if ( *(struct IUnknown **)(a1 + 8) != a4 )
      ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 8), a4);
    *v5 = *(void **)(a1 + 16);
    result = 0;
    *(_DWORD *)(a1 + 40) = a5;
  }
  return result;
}

```

## disassembly

```asm
0x18000fc4c  push    rbx
0x18000fc4e  push    rbp
0x18000fc4f  push    rsi
0x18000fc50  push    rdi
0x18000fc51  push    r12
0x18000fc53  push    r13
0x18000fc55  push    r14
0x18000fc57  push    r15
0x18000fc59  sub     rsp, 28h
0x18000fc5d  mov     r13d, [rsp+68h+arg_20]
0x18000fc65  lea     rdi, [rcx+20h]
0x18000fc69  mov     r14, r9
0x18000fc6c  mov     rbp, r8
0x18000fc6f  mov     rsi, rdx
0x18000fc72  mov     rbx, rcx
0x18000fc75  cmp     r13d, 3
0x18000fc79  jnz     loc_18000FD19
0x18000fc7f  mov     r12, r8
0x18000fc82  lea     eax, [r13+5]
0x18000fc86  sub     r12, rdx
0x18000fc89  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fc90  sar     r12, 3
0x18000fc94  mul     r12
0x18000fc97  cmovb   rax, rcx
0x18000fc9b  mov     rcx, rax; unsigned __int64
0x18000fc9e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000fca3  mov     [rbx+10h], rax
0x18000fca7  mov     [rdi], rax
0x18000fcaa  test    rax, rax
0x18000fcad  jnz     short loc_18000FCB9
0x18000fcaf  mov     eax, 8007000Eh
0x18000fcb4  jmp     loc_18000FD3F
0x18000fcb9  cmp     rsi, rbp
0x18000fcbc  jz      short loc_18000FD0F
0x18000fcbe  mov     rdx, rsi
0x18000fcc1  mov     rcx, rax
0x18000fcc4  call    ?copy@?$_CopyInterface@UIConnectionPoint@@@ATL@@SAJPEAPEAUIConnectionPoint@@0@Z; ATL::_CopyInterface<IConnectionPoint>::copy(IConnectionPoint * *,IConnectionPoint * *)
0x18000fcc9  mov     r15d, eax
0x18000fccc  test    eax, eax
0x18000fcce  js      short loc_18000FCDD
0x18000fcd0  add     qword ptr [rdi], 8
0x18000fcd4  mov     rax, [rdi]
0x18000fcd7  add     rsi, 8
0x18000fcdb  jmp     short loc_18000FCB9
0x18000fcdd  mov     rsi, [rbx+10h]
0x18000fce1  jmp     short loc_18000FCEF
0x18000fce3  mov     rcx, rsi
0x18000fce6  add     rsi, 8
0x18000fcea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000fcef  cmp     rsi, [rdi]
0x18000fcf2  jb      short loc_18000FCE3
0x18000fcf4  mov     rcx, [rbx+10h]; Block
0x18000fcf8  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000fcfd  xor     eax, eax
0x18000fcff  mov     [rdi], rax
0x18000fd02  mov     [rbx+18h], rax
0x18000fd06  mov     [rbx+10h], rax
0x18000fd0a  mov     eax, r15d
0x18000fd0d  jmp     short loc_18000FD3F
0x18000fd0f  mov     rax, [rbx+10h]
0x18000fd13  lea     rbp, [rax+r12*8]
0x18000fd17  jmp     short loc_18000FD1D
0x18000fd19  mov     [rcx+10h], rdx
0x18000fd1d  lea     rcx, [rbx+8]; struct IUnknown **
0x18000fd21  mov     [rbx+18h], rbp
0x18000fd25  cmp     [rcx], r14
0x18000fd28  jz      short loc_18000FD32
0x18000fd2a  mov     rdx, r14; struct IUnknown *
0x18000fd2d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000fd32  mov     rax, [rbx+10h]
0x18000fd36  mov     [rdi], rax
0x18000fd39  xor     eax, eax
0x18000fd3b  mov     [rbx+28h], r13d
0x18000fd3f  add     rsp, 28h
0x18000fd43  pop     r15
0x18000fd45  pop     r14
0x18000fd47  pop     r13
0x18000fd49  pop     r12
0x18000fd4b  pop     rdi
0x18000fd4c  pop     rsi
0x18000fd4d  pop     rbp
0x18000fd4e  pop     rbx
0x18000fd4f  retn
```
