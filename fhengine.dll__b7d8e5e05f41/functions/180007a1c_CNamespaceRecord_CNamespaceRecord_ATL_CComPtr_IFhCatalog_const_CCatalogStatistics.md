# CNamespaceRecord::CNamespaceRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)

- ea: `0x180007a1c`
- end: `0x180007a66`
- name: `??0CNamespaceRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z`
- size: `74`
- prototype: `CNamespaceRecord *__fastcall(CNamespaceRecord *this, __int64 *, __int64)`
- caller_count: `16`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a4ac`
- `0x18000a818`
- `0x18000d0fc`
- `0x18000d4f4`
- `0x18000fde8`
- `0x180010b18`
- `0x180010de8`
- `0x1800128fc`
- `0x180013e14`
- `0x18001789c`
- `0x180017c68`
- `0x180018778`
- `0x18001afe4`
- `0x18001baf8`
- `0x18001cb74`
- `0x18001f92c`

## callees

- `0x180007a1c`
- `0x180008f50`
- `0x180034010`

## pseudocode

```c
CNamespaceRecord *__fastcall CNamespaceRecord::CNamespaceRecord(CNamespaceRecord *this, __int64 *a2, __int64 a3)
{
  __int64 v5; // rcx

  v5 = *a2;
  *(_QWORD *)this = *a2;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  *((_QWORD *)this + 1) = a3;
  *((_QWORD *)this + 3) = 0;
  CNamespaceRecord::Release(this);
  return this;
}

```

## disassembly

```asm
0x180007a1c  mov     [rsp+arg_0], rbx
0x180007a21  push    rdi
0x180007a22  sub     rsp, 20h
0x180007a26  mov     rdi, r8
0x180007a29  mov     rbx, rcx
0x180007a2c  mov     rcx, [rdx]
0x180007a2f  mov     [rbx], rcx
0x180007a32  test    rcx, rcx
0x180007a35  jz      short loc_180007A44
0x180007a37  mov     rax, [rcx]
0x180007a3a  mov     rax, [rax+8]
0x180007a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a43  nop
0x180007a44  mov     [rbx+8], rdi
0x180007a48  mov     qword ptr [rbx+18h], 0
0x180007a50  mov     rcx, rbx; this
0x180007a53  call    ?Release@CNamespaceRecord@@QEAAXXZ; CNamespaceRecord::Release(void)
0x180007a58  mov     rax, rbx
0x180007a5b  mov     rbx, [rsp+28h+arg_0]
0x180007a60  add     rsp, 20h
0x180007a64  pop     rdi
0x180007a65  retn
```
