# std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>,std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>::push_back(_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> &&)

- ea: `0x180017150`
- end: `0x1800172b2`
- name: `?push_back@?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@QEAAX$$QEAV?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@Z`
- size: `354`
- prototype: `__int64 *__fastcall(void **, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016e60`

## callees

- `0x180017050`
- `0x180017138`
- `0x180017150`
- `0x180019010`

## pseudocode

```c
__int64 *__fastcall std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::push_back(
        void **a1,
        __int64 *a2)
{
  unsigned __int64 v4; // rcx
  bool v5; // al
  _BYTE *v6; // r8
  _BYTE *v7; // rsi
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 *result; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rdx
  __int64 v18; // rcx

  v4 = (unsigned __int64)a1[1];
  v5 = (unsigned __int64)a2 < v4 && *a1 <= a2;
  v6 = a1[2];
  if ( v5 )
  {
    v7 = *a1;
    if ( (_BYTE *)v4 == v6 && !((__int64)&v6[-v4] >> 3) )
    {
      v8 = (__int64)(v4 - (_QWORD)v7) >> 3;
      if ( v8 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::_Xlen();
      v9 = v8 + 1;
      v10 = (v6 - v7) >> 3;
      v11 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) >= v10 )
        v11 = v10 + (v10 >> 1);
      if ( v11 < v9 )
        v11 = v9;
      std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::_Reallocate(
        a1,
        v11);
    }
    v12 = *((_QWORD *)*a1 + (((char *)a2 - v7) >> 3));
    result = (__int64 *)a1[1];
    *result = v12;
    if ( v12 )
      result = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  else
  {
    if ( (_BYTE *)v4 == v6 && !((__int64)&v6[-v4] >> 3) )
    {
      v14 = (__int64)(v4 - (_QWORD)*a1) >> 3;
      if ( v14 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::_Xlen();
      v15 = v14 + 1;
      v16 = (v6 - (_BYTE *)*a1) >> 3;
      v17 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v16 >> 1) >= v16 )
        v17 = v16 + (v16 >> 1);
      if ( v17 < v15 )
        v17 = v15;
      std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::_Reallocate(
        a1,
        v17);
    }
    v18 = *a2;
    result = (__int64 *)a1[1];
    *result = *a2;
    if ( v18 )
      result = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  }
  a1[1] = (char *)a1[1] + 8;
  return result;
}

```

## disassembly

```asm
0x180017150  mov     [rsp+arg_0], rbx
0x180017155  mov     [rsp+arg_8], rsi
0x18001715a  push    rdi
0x18001715b  sub     rsp, 20h
0x18001715f  mov     rdi, rdx
0x180017162  mov     rbx, rcx
0x180017165  mov     rcx, [rcx+8]
0x180017169  cmp     rdx, rcx
0x18001716c  jnb     short loc_180017177
0x18001716e  cmp     [rbx], rdx
0x180017171  ja      short loc_180017177
0x180017173  mov     al, 1
0x180017175  jmp     short loc_180017179
0x180017177  xor     al, al
0x180017179  mov     r8, [rbx+10h]
0x18001717d  test    al, al
0x18001717f  jz      loc_180017215
0x180017185  mov     rsi, [rbx]
0x180017188  cmp     rcx, r8
0x18001718b  jnz     short loc_1800171EC
0x18001718d  mov     rax, r8
0x180017190  sub     rax, rcx
0x180017193  sar     rax, 3
0x180017197  cmp     rax, 1
0x18001719b  jnb     short loc_1800171EC
0x18001719d  sub     rcx, rsi
0x1800171a0  sar     rcx, 3
0x1800171a4  mov     r9, 1FFFFFFFFFFFFFFFh
0x1800171ae  mov     rax, r9
0x1800171b1  sub     rax, rcx
0x1800171b4  cmp     rax, 1
0x1800171b8  jb      loc_1800172AC
0x1800171be  inc     rcx
0x1800171c1  sub     r8, rsi
0x1800171c4  sar     r8, 3
0x1800171c8  mov     rax, r8
0x1800171cb  shr     rax, 1
0x1800171ce  sub     r9, rax
0x1800171d1  add     rax, r8
0x1800171d4  xor     edx, edx
0x1800171d6  cmp     r9, r8
0x1800171d9  cmovnb  rdx, rax
0x1800171dd  cmp     rdx, rcx
0x1800171e0  cmovb   rdx, rcx
0x1800171e4  mov     rcx, rbx
0x1800171e7  call    ?_Reallocate@?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@IEAAX_K@Z; std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::_Reallocate(unsigned __int64)
0x1800171ec  sub     rdi, rsi
0x1800171ef  sar     rdi, 3
0x1800171f3  mov     rax, [rbx]
0x1800171f6  mov     rcx, [rax+rdi*8]
0x1800171fa  mov     rax, [rbx+8]
0x1800171fe  mov     [rax], rcx
0x180017201  test    rcx, rcx
0x180017204  jz      short loc_180017213
0x180017206  mov     rax, [rcx]
0x180017209  mov     rax, [rax+8]
0x18001720d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017212  nop
0x180017213  jmp     short loc_180017291
0x180017215  cmp     rcx, r8
0x180017218  jnz     short loc_180017275
0x18001721a  mov     rax, r8
0x18001721d  sub     rax, rcx
0x180017220  sar     rax, 3
0x180017224  cmp     rax, 1
0x180017228  jnb     short loc_180017275
0x18001722a  sub     rcx, [rbx]
0x18001722d  sar     rcx, 3
0x180017231  mov     r9, 1FFFFFFFFFFFFFFFh
0x18001723b  mov     rax, r9
0x18001723e  sub     rax, rcx
0x180017241  cmp     rax, 1
0x180017245  jb      short loc_1800172A6
0x180017247  inc     rcx
0x18001724a  sub     r8, [rbx]
0x18001724d  sar     r8, 3
0x180017251  mov     rax, r8
0x180017254  shr     rax, 1
0x180017257  sub     r9, rax
0x18001725a  add     rax, r8
0x18001725d  xor     edx, edx
0x18001725f  cmp     r9, r8
0x180017262  cmovnb  rdx, rax
0x180017266  cmp     rdx, rcx
0x180017269  cmovb   rdx, rcx
0x18001726d  mov     rcx, rbx
0x180017270  call    ?_Reallocate@?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@IEAAX_K@Z; std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::_Reallocate(unsigned __int64)
0x180017275  mov     rcx, [rdi]
0x180017278  mov     rax, [rbx+8]
0x18001727c  mov     [rax], rcx
0x18001727f  test    rcx, rcx
0x180017282  jz      short loc_180017291
0x180017284  mov     rax, [rcx]
0x180017287  mov     rax, [rax+8]
0x18001728b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017290  nop
0x180017291  add     qword ptr [rbx+8], 8
0x180017296  mov     rbx, [rsp+28h+arg_0]
0x18001729b  mov     rsi, [rsp+28h+arg_8]
0x1800172a0  add     rsp, 20h
0x1800172a4  pop     rdi
0x1800172a5  retn
0x1800172a6  call    ?_Xlen@?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@IEBAXXZ; std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::_Xlen(void)
0x1800172ac  call    ?_Xlen@?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@IEBAXXZ; std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::_Xlen(void)
```
