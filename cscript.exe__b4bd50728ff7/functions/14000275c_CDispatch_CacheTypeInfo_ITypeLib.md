# CDispatch::CacheTypeInfo(ITypeLib *)

- ea: `0x14000275c`
- end: `0x14000280f`
- name: `?CacheTypeInfo@CDispatch@@QEAAJPEAUITypeLib@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(CDispatch *__hidden this, struct ITypeLib *)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140001bd0`
- `0x1400068f0`
- `0x140007290`
- `0x14001385c`

## callees

- `0x14000275c`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall CDispatch::CacheTypeInfo(CDispatch *this, struct ITypeLib *a2)
{
  struct ITypeLibVtbl *lpVtbl; // rax
  __int64 result; // rax
  int v5; // edi
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  lpVtbl = a2->lpVtbl;
  v7 = 0;
  result = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, __int64 *))lpVtbl->GetTypeInfoOfGuid)(
             a2,
             *(_QWORD *)(*((_QWORD *)this + 5) + 40LL),
             &v7);
  if ( (int)result >= 0 )
  {
    v6 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v7 + 64LL))(v7, 0xFFFFFFFFLL, &v6);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v7 + 112LL))(
             v7,
             v6,
             *((_QWORD *)this + 5) + 56LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v5 >= 0 )
        *((_BYTE *)this + 48) = 1;
    }
    else
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000275c  mov     [rsp+arg_10], rbx
0x140002761  push    rdi
0x140002762  sub     rsp, 20h
0x140002766  mov     rax, [rdx]
0x140002769  lea     r8, [rsp+28h+arg_8]
0x14000276e  mov     r9, rdx
0x140002771  mov     [rsp+28h+arg_8], 0
0x14000277a  mov     rdx, [rcx+28h]
0x14000277e  mov     rbx, rcx
0x140002781  mov     rcx, r9
0x140002784  mov     rax, [rax+30h]
0x140002788  mov     rdx, [rdx+28h]
0x14000278c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002791  test    eax, eax
0x140002793  js      short loc_140002804
0x140002795  mov     rcx, [rsp+28h+arg_8]
0x14000279a  lea     r8, [rsp+28h+arg_0]
0x14000279f  mov     [rsp+28h+arg_0], 0
0x1400027a7  or      edx, 0FFFFFFFFh
0x1400027aa  mov     rax, [rcx]
0x1400027ad  mov     rax, [rax+40h]
0x1400027b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027b6  mov     rcx, [rsp+28h+arg_8]
0x1400027bb  mov     edi, eax
0x1400027bd  test    eax, eax
0x1400027bf  jns     short loc_1400027CF
0x1400027c1  mov     rdx, [rcx]
0x1400027c4  mov     rax, [rdx+10h]
0x1400027c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027cd  jmp     short loc_140002802
0x1400027cf  mov     rax, [rcx]
0x1400027d2  mov     r8, [rbx+28h]
0x1400027d6  mov     edx, [rsp+28h+arg_0]
0x1400027da  add     r8, 38h ; '8'
0x1400027de  mov     rax, [rax+70h]
0x1400027e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027e7  mov     rcx, [rsp+28h+arg_8]
0x1400027ec  mov     edi, eax
0x1400027ee  mov     rdx, [rcx]
0x1400027f1  mov     rax, [rdx+10h]
0x1400027f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027fa  test    edi, edi
0x1400027fc  js      short loc_140002802
0x1400027fe  mov     byte ptr [rbx+30h], 1
0x140002802  mov     eax, edi
0x140002804  mov     rbx, [rsp+28h+arg_10]
0x140002809  add     rsp, 20h
0x14000280d  pop     rdi
0x14000280e  retn
```
