# CFileRecord::CFileRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)

- ea: `0x180007970`
- end: `0x1800079ba`
- name: `??0CFileRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z`
- size: `74`
- prototype: `CFileRecord *__fastcall(CFileRecord *this, __int64 *, __int64)`
- caller_count: `12`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a2f8`
- `0x18000c450`
- `0x18000cafc`
- `0x18000d0fc`
- `0x18000f728`
- `0x180010de8`
- `0x180012b44`
- `0x1800163cc`
- `0x180016da0`
- `0x180017290`
- `0x18001789c`
- `0x180018778`

## callees

- `0x180007970`
- `0x180008f04`
- `0x180034010`

## pseudocode

```c
CFileRecord *__fastcall CFileRecord::CFileRecord(CFileRecord *this, __int64 *a2, __int64 a3)
{
  __int64 v5; // rcx

  v5 = *a2;
  *(_QWORD *)this = *a2;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  *((_QWORD *)this + 1) = a3;
  *((_QWORD *)this + 3) = 0;
  CFileRecord::Release(this);
  return this;
}

```

## disassembly

```asm
0x180007970  mov     [rsp+arg_0], rbx
0x180007975  push    rdi
0x180007976  sub     rsp, 20h
0x18000797a  mov     rdi, r8
0x18000797d  mov     rbx, rcx
0x180007980  mov     rcx, [rdx]
0x180007983  mov     [rbx], rcx
0x180007986  test    rcx, rcx
0x180007989  jz      short loc_180007998
0x18000798b  mov     rax, [rcx]
0x18000798e  mov     rax, [rax+8]
0x180007992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007997  nop
0x180007998  mov     [rbx+8], rdi
0x18000799c  mov     qword ptr [rbx+18h], 0
0x1800079a4  mov     rcx, rbx; this
0x1800079a7  call    ?Release@CFileRecord@@QEAAXXZ; CFileRecord::Release(void)
0x1800079ac  mov     rax, rbx
0x1800079af  mov     rbx, [rsp+28h+arg_0]
0x1800079b4  add     rsp, 20h
0x1800079b8  pop     rdi
0x1800079b9  retn
```
