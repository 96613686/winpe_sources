# CDataObject::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x180009580`
- end: `0x180009612`
- name: `?GetData@CDataObject@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(CDataObject *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180009580`
- `0x180009a24`
- `0x180024010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x1800095b9`
- `ole32!CreateStreamOnHGlobal` at `0x1800095b9`

## pseudocode

```c
__int64 __fastcall CDataObject::GetData(CDataObject *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  int cfFormat; // ebp
  HRESULT v7; // ebx
  LPSTREAM v9; // [rsp+48h] [rbp+10h] BYREF

  cfFormat = a2->cfFormat;
  a3->pUnkForRelease = 0;
  v9 = 0;
  v7 = CreateStreamOnHGlobal(a3->hBitmap, 0, &v9);
  if ( v7 >= 0 )
  {
    if ( cfFormat == CDataObject::s_cfNodeId2 && a2->tymed == 1 )
      v7 = CDataObject::_WriteNodeId2(this, a3);
    else
      v7 = -2147221404;
  }
  if ( v9 )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009580  mov     rax, rsp
0x180009583  mov     [rax+8], rbx
0x180009587  mov     [rax+18h], rbp
0x18000958b  push    rsi
0x18000958c  push    rdi
0x18000958d  push    r14
0x18000958f  sub     rsp, 20h
0x180009593  movzx   ebp, word ptr [rdx]
0x180009596  mov     rdi, r8
0x180009599  mov     rsi, rdx
0x18000959c  mov     qword ptr [r8+10h], 0
0x1800095a4  mov     r14, rcx
0x1800095a7  mov     qword ptr [rax+10h], 0
0x1800095af  lea     r8, [rax+10h]; ppstm
0x1800095b3  xor     edx, edx; fDeleteOnRelease
0x1800095b5  mov     rcx, [rdi+8]; hGlobal
0x1800095b9  call    cs:__imp_CreateStreamOnHGlobal
0x1800095bf  mov     ebx, eax
0x1800095c1  test    eax, eax
0x1800095c3  js      short loc_1800095E7
0x1800095c5  cmp     ebp, cs:?s_cfNodeId2@CDataObject@@2IB; uint const CDataObject::s_cfNodeId2
0x1800095cb  jnz     short loc_1800095E2
0x1800095cd  cmp     dword ptr [rsi+18h], 1
0x1800095d1  jnz     short loc_1800095E2
0x1800095d3  mov     rdx, rdi; struct tagSTGMEDIUM *
0x1800095d6  mov     rcx, r14; this
0x1800095d9  call    ?_WriteNodeId2@CDataObject@@AEAAJPEAUtagSTGMEDIUM@@@Z; CDataObject::_WriteNodeId2(tagSTGMEDIUM *)
0x1800095de  mov     ebx, eax
0x1800095e0  jmp     short loc_1800095E7
0x1800095e2  mov     ebx, 80040064h
0x1800095e7  mov     rcx, [rsp+38h+arg_8]
0x1800095ec  test    rcx, rcx
0x1800095ef  jz      short loc_1800095FD
0x1800095f1  mov     rax, [rcx]
0x1800095f4  mov     rax, [rax+10h]
0x1800095f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095fd  mov     rbp, [rsp+38h+arg_10]
0x180009602  mov     eax, ebx
0x180009604  mov     rbx, [rsp+38h+arg_0]
0x180009609  add     rsp, 20h
0x18000960d  pop     r14
0x18000960f  pop     rdi
0x180009610  pop     rsi
0x180009611  retn
```
