# std::vector<ATL::CComPtr<IUMBusPDO>,std::allocator<ATL::CComPtr<IUMBusPDO>>>::~vector<ATL::CComPtr<IUMBusPDO>,std::allocator<ATL::CComPtr<IUMBusPDO>>>(void)

- ea: `0x18000eda8`
- end: `0x18000ee59`
- name: `??1?$vector@V?$CComPtr@UIUMBusPDO@@@ATL@@V?$allocator@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f77c`
- `0x180015df7`

## callees

- `0x180002330`
- `0x18000eda8`
- `0x180017010`

## pseudocode

```c
void __fastcall std::vector<ATL::CComPtr<IUMBusPDO>>::~vector<ATL::CComPtr<IUMBusPDO>>(__int64 a1)
{
  char *v2; // rbx
  char *v3; // rsi
  char *v4; // rcx
  unsigned __int64 v5; // rdx
  char *v6; // rax

  v2 = *(char **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(char **)(a1 + 8);
    while ( v2 != v3 )
    {
      if ( *(_QWORD *)v2 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v2 + 16LL))(*(_QWORD *)v2);
      v2 += 8;
    }
    v4 = *(char **)a1;
    v5 = 8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3);
    if ( v5 < 0x1000 )
    {
      v6 = *(char **)a1;
    }
    else
    {
      v6 = (char *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000eda8  mov     [rsp+arg_0], rbx
0x18000edad  mov     [rsp+arg_8], rsi
0x18000edb2  push    rdi
0x18000edb3  sub     rsp, 20h
0x18000edb7  mov     rdi, rcx
0x18000edba  mov     rbx, [rcx]
0x18000edbd  test    rbx, rbx
0x18000edc0  jz      loc_18000EE49
0x18000edc6  mov     rsi, [rcx+8]
0x18000edca  jmp     short loc_18000EDE5
0x18000edcc  mov     rcx, [rbx]
0x18000edcf  test    rcx, rcx
0x18000edd2  jz      short loc_18000EDE1
0x18000edd4  mov     rax, [rcx]
0x18000edd7  mov     rax, [rax+10h]
0x18000eddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ede0  nop
0x18000ede1  add     rbx, 8
0x18000ede5  cmp     rbx, rsi
0x18000ede8  jnz     short loc_18000EDCC
0x18000edea  mov     rcx, [rdi]
0x18000eded  mov     rax, [rdi+10h]
0x18000edf1  sub     rax, rcx
0x18000edf4  sar     rax, 3
0x18000edf8  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18000ee00  cmp     rdx, 1000h
0x18000ee07  jb      short loc_18000EE27
0x18000ee09  mov     rax, [rcx-8]
0x18000ee0d  sub     rcx, rax
0x18000ee10  sub     rcx, 8
0x18000ee14  cmp     rcx, 1Fh
0x18000ee18  ja      short loc_18000EE20
0x18000ee1a  add     rdx, 27h ; '''
0x18000ee1e  jmp     short loc_18000EE2A
0x18000ee20  mov     ecx, 5
0x18000ee25  int     29h; Win8: RtlFailFast(ecx)
0x18000ee27  mov     rax, rcx
0x18000ee2a  mov     rcx, rax; void *
0x18000ee2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ee32  mov     qword ptr [rdi], 0
0x18000ee39  mov     qword ptr [rdi+8], 0
0x18000ee41  mov     qword ptr [rdi+10h], 0
0x18000ee49  mov     rbx, [rsp+28h+arg_0]
0x18000ee4e  mov     rsi, [rsp+28h+arg_8]
0x18000ee53  add     rsp, 20h
0x18000ee57  pop     rdi
0x18000ee58  retn
```
