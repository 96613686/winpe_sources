# TComObject<NOutermost::CDevice>::Release(void)

- ea: `0x1800026a0`
- end: `0x18000274c`
- name: `?Release@?$TComObject@VCDevice@NOutermost@@@@UEAAKXZ`
- size: `172`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800026a0`
- `0x180002754`
- `0x18000b3f4`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TComObject<NOutermost::CDevice>::Release(struct IUnknown *a1)
{
  signed __int32 lpVtbl; // ecx
  unsigned __int32 v3; // edx
  ULONG (__stdcall *AddRef)(IUnknown *); // r14
  unsigned __int32 v6; // esi

  while ( 1 )
  {
    lpVtbl = (signed __int32)a1[1].lpVtbl;
    v3 = lpVtbl - 1;
    if ( lpVtbl == 1 )
      break;
    if ( lpVtbl == _InterlockedCompareExchange((volatile signed __int32 *)&a1[1], v3, lpVtbl) )
      return v3;
  }
  AddRef = a1[15].lpVtbl->AddRef;
  (*(void (__fastcall **)(ULONG (__stdcall *)(IUnknown *)))(*(_QWORD *)AddRef + 24LL))(AddRef);
  v6 = _InterlockedDecrement((volatile signed __int32 *)&a1[1]);
  if ( !v6 )
  {
    D3DCoreModule::RemoveSingletonShadow((D3DCoreModule *)a1[15].lpVtbl, (struct _LUID)a1[14].lpVtbl, a1);
    ((void (__fastcall *)(struct IUnknownVtbl *, struct IUnknown *))a1[15].lpVtbl[5].Release)(a1[13].lpVtbl, &a1[14]);
    ((void (__fastcall *)(struct IUnknown *, _QWORD))a1->lpVtbl[3].AddRef)(a1, 0);
    operator delete(a1);
  }
  (*(void (__fastcall **)(ULONG (__stdcall *)(IUnknown *)))(*(_QWORD *)AddRef + 32LL))(AddRef);
  return v6;
}

```

## disassembly

```asm
0x1800026a0  push    rbx
0x1800026a2  push    rsi
0x1800026a3  push    rdi
0x1800026a4  push    r14
0x1800026a6  sub     rsp, 28h
0x1800026aa  mov     rbx, rcx
0x1800026ad  mov     ecx, [rbx+8]
0x1800026b0  lea     edx, [rcx-1]
0x1800026b3  test    edx, edx
0x1800026b5  jz      short loc_1800026CE
0x1800026b7  mov     eax, ecx
0x1800026b9  lock cmpxchg [rbx+8], edx
0x1800026be  cmp     ecx, eax
0x1800026c0  jnz     short loc_1800026AD
0x1800026c2  mov     eax, edx
0x1800026c4  add     rsp, 28h
0x1800026c8  pop     r14
0x1800026ca  pop     rdi
0x1800026cb  pop     rsi
0x1800026cc  pop     rbx
0x1800026cd  retn
0x1800026ce  mov     rax, [rbx+78h]
0x1800026d2  mov     r14, [rax+8]
0x1800026d6  mov     rax, [r14]
0x1800026d9  mov     rcx, r14
0x1800026dc  mov     rax, [rax+18h]
0x1800026e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026e5  nop
0x1800026e6  mov     esi, 0FFFFFFFFh
0x1800026eb  lock xadd [rbx+8], esi
0x1800026f0  sub     esi, 1
0x1800026f3  jz      short loc_180002709
0x1800026f5  mov     rdx, [r14]
0x1800026f8  mov     rcx, r14
0x1800026fb  mov     rax, [rdx+20h]
0x1800026ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002704  nop
0x180002705  mov     eax, esi
0x180002707  jmp     short loc_1800026C4
0x180002709  mov     r8, rbx; struct IUnknown *
0x18000270c  mov     rdx, [rbx+70h]; struct _LUID
0x180002710  mov     rcx, [rbx+78h]; this
0x180002714  call    ?RemoveSingletonShadow@D3DCoreModule@@QEAAXU_LUID@@PEAUIUnknown@@@Z; D3DCoreModule::RemoveSingletonShadow(_LUID,IUnknown *)
0x180002719  mov     rax, [rbx+78h]
0x18000271d  lea     rdx, [rbx+70h]
0x180002721  mov     rcx, [rbx+68h]
0x180002725  mov     rax, [rax+88h]
0x18000272c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002731  mov     rax, [rbx]
0x180002734  xor     edx, edx
0x180002736  mov     rcx, rbx
0x180002739  mov     rax, [rax+50h]
0x18000273d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002742  mov     rcx, rbx; Block
0x180002745  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000274a  jmp     short loc_1800026F5
```
