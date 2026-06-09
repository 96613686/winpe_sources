# std::vector<ATL::CComPtr<IUMBusPDO>,std::allocator<ATL::CComPtr<IUMBusPDO>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x1800115fc`
- end: `0x180011690`
- name: `??1_Reallocation_guard@?$vector@V?$CComPtr@UIUMBusPDO@@@ATL@@V?$allocator@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@QEAA@XZ`
- size: `148`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001100c`

## callees

- `0x180002330`
- `0x1800115fc`
- `0x180017010`

## pseudocode

```c
void __fastcall std::vector<ATL::CComPtr<IUMBusPDO>>::_Reallocation_guard::~_Reallocation_guard(_QWORD *a1)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rdi
  __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  void *v6; // rax

  if ( a1[1] )
  {
    v2 = (_QWORD *)a1[4];
    for ( i = (_QWORD *)a1[3]; i != v2; ++i )
    {
      if ( *i )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*i + 16LL))(*i);
    }
    v4 = a1[1];
    v5 = 8LL * a1[2];
    if ( v5 < 0x1000 )
    {
      v6 = (void *)a1[1];
    }
    else
    {
      v6 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
  }
}

```

## disassembly

```asm
0x1800115fc  mov     [rsp+arg_0], rbx
0x180011601  mov     [rsp+arg_8], rsi
0x180011606  push    rdi
0x180011607  sub     rsp, 20h
0x18001160b  mov     rbx, rcx
0x18001160e  cmp     qword ptr [rcx+8], 0
0x180011613  jz      short loc_180011680
0x180011615  mov     rsi, [rcx+20h]
0x180011619  mov     rdi, [rcx+18h]
0x18001161d  jmp     short loc_180011638
0x18001161f  mov     rcx, [rdi]
0x180011622  test    rcx, rcx
0x180011625  jz      short loc_180011634
0x180011627  mov     rax, [rcx]
0x18001162a  mov     rax, [rax+10h]
0x18001162e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011633  nop
0x180011634  add     rdi, 8
0x180011638  cmp     rdi, rsi
0x18001163b  jnz     short loc_18001161F
0x18001163d  mov     rcx, [rbx+8]
0x180011641  mov     rax, [rbx+10h]
0x180011645  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18001164d  cmp     rdx, 1000h
0x180011654  jb      short loc_180011674
0x180011656  mov     rax, [rcx-8]
0x18001165a  sub     rcx, rax
0x18001165d  sub     rcx, 8
0x180011661  cmp     rcx, 1Fh
0x180011665  ja      short loc_18001166D
0x180011667  add     rdx, 27h ; '''
0x18001166b  jmp     short loc_180011677
0x18001166d  mov     ecx, 5
0x180011672  int     29h; Win8: RtlFailFast(ecx)
0x180011674  mov     rax, rcx
0x180011677  mov     rcx, rax; void *
0x18001167a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001167f  nop
0x180011680  mov     rbx, [rsp+28h+arg_0]
0x180011685  mov     rsi, [rsp+28h+arg_8]
0x18001168a  add     rsp, 20h
0x18001168e  pop     rdi
0x18001168f  retn
```
