# ATL::CComObject<CDpUrlAccessor>::CComObject<CDpUrlAccessor>(void *)

- ea: `0x180002e98`
- end: `0x180002f28`
- name: `??0?$CComObject@VCDpUrlAccessor@@@ATL@@QEAA@PEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004628`
- `0x18000487c`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDpUrlAccessor>::CComObject<CDpUrlAccessor>(__int64 a1)
{
  struct ATL::CAtlModule *v2; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 88) = 7;
  *(_QWORD *)(a1 + 80) = 0;
  *(_WORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 128) = 7;
  *(_QWORD *)(a1 + 120) = 0;
  *(_WORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 168) = 7;
  *(_QWORD *)(a1 + 160) = 0;
  *(_WORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 208) = 7;
  v2 = ATL::_pAtlModule;
  *(_QWORD *)(a1 + 200) = 0;
  *(_WORD *)(a1 + 184) = 0;
  *(_QWORD *)a1 = &ATL::CComObject<CDpUrlAccessor>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x180002e98  push    rbx
0x180002e9a  sub     rsp, 20h
0x180002e9e  mov     rbx, rcx
0x180002ea1  xor     edx, edx
0x180002ea3  mov     [rcx+8], edx
0x180002ea6  xor     eax, eax
0x180002ea8  xorps   xmm0, xmm0
0x180002eab  movups  xmmword ptr [rcx+10h], xmm0
0x180002eaf  movups  xmmword ptr [rcx+20h], xmm0
0x180002eb3  mov     [rcx+30h], rax
0x180002eb7  lea     rax, ??_7?$CComObject@VCDpUrlAccessor@@@ATL@@6B@; const ATL::CComObject<CDpUrlAccessor>::`vftable'
0x180002ebe  mov     [rcx+38h], dl
0x180002ec1  lea     ecx, [rdx+7]
0x180002ec4  mov     [rbx+58h], rcx
0x180002ec8  mov     [rbx+50h], rdx
0x180002ecc  mov     [rbx+40h], dx
0x180002ed0  mov     [rbx+80h], rcx
0x180002ed7  mov     [rbx+78h], rdx
0x180002edb  mov     [rbx+68h], dx
0x180002edf  mov     [rbx+0A8h], rcx
0x180002ee6  mov     [rbx+0A0h], rdx
0x180002eed  mov     [rbx+90h], dx
0x180002ef4  mov     [rbx+0D0h], rcx
0x180002efb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002f02  mov     [rbx+0C8h], rdx
0x180002f09  mov     [rbx+0B8h], dx
0x180002f10  mov     [rbx], rax
0x180002f13  mov     rax, [rcx]
0x180002f16  mov     rax, [rax+8]
0x180002f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f1f  mov     rax, rbx
0x180002f22  add     rsp, 20h
0x180002f26  pop     rbx
0x180002f27  retn
```
