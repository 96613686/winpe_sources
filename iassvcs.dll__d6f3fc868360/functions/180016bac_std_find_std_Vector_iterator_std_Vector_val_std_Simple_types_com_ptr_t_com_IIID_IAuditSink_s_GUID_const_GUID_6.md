# std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>>,IAuditSink *>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>>,IAuditSink * const &)

- ea: `0x180016bac`
- end: `0x180016cae`
- name: `??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@@std@@PEAUIAuditSink@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@@0@V10@0AEBQEAUIAuditSink@@@Z`
- size: `258`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016e60`
- `0x180016f50`

## callees

- `0x1800137b0`
- `0x180016bac`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>>,IAuditSink *>(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64 *),
        __int64 (__fastcall ****a3)(_QWORD, GUID *, __int64 *),
        __int64 (__fastcall ****a4)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall ****i)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  _QWORD *result; // rax
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF
  __int64 v15; // [rsp+50h] [rbp+18h] BYREF

  for ( i = a2; i != a3; ++i )
  {
    v8 = *a4;
    v9 = *i;
    if ( *i == *a4 )
      break;
    v15 = 0;
    v14 = 0;
    if ( v9 )
    {
      v10 = (**v9)(v9, &GUID_00000000_0000_0000_c000_000000000046, &v15);
      if ( v10 < 0 )
        _com_issue_error(v10);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    if ( v8 )
    {
      v11 = (**v8)(v8, &GUID_00000000_0000_0000_c000_000000000046, &v14);
      if ( v11 < 0 )
        _com_issue_error(v11);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v12 = v14;
    }
    else
    {
      v12 = 0;
    }
    if ( !(unsigned int)((v15 - v12) >> 3) )
      break;
  }
  result = a1;
  *a1 = i;
  return result;
}

```

## disassembly

```asm
0x180016bac  mov     [rsp+arg_0], rbx
0x180016bb1  mov     [rsp+arg_18], rsi
0x180016bb6  push    rdi
0x180016bb7  push    r14
0x180016bb9  push    r15
0x180016bbb  sub     rsp, 20h
0x180016bbf  mov     r15, r9
0x180016bc2  mov     rbx, r8
0x180016bc5  mov     rdi, rdx
0x180016bc8  mov     r14, rcx
0x180016bcb  cmp     rdx, r8
0x180016bce  jz      loc_180016C84
0x180016bd4  mov     rsi, [r15]
0x180016bd7  mov     rcx, [rdi]
0x180016bda  cmp     rcx, rsi
0x180016bdd  jz      loc_180016C84
0x180016be3  mov     [rsp+38h+arg_10], 0
0x180016bec  mov     [rsp+38h+arg_8], 0
0x180016bf5  test    rcx, rcx
0x180016bf8  jz      short loc_180016C2A
0x180016bfa  mov     rax, [rcx]
0x180016bfd  lea     r8, [rsp+38h+arg_10]
0x180016c02  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180016c09  mov     rax, [rax]
0x180016c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c11  test    eax, eax
0x180016c13  js      loc_180016CA6
0x180016c19  mov     rcx, [rsp+38h+arg_10]
0x180016c1e  mov     rax, [rcx]
0x180016c21  mov     rax, [rax+10h]
0x180016c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c2a  test    rsi, rsi
0x180016c2d  jz      short loc_180016C65
0x180016c2f  mov     rax, [rsi]
0x180016c32  lea     r8, [rsp+38h+arg_8]
0x180016c37  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180016c3e  mov     rcx, rsi
0x180016c41  mov     rax, [rax]
0x180016c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c49  test    eax, eax
0x180016c4b  js      short loc_180016C9E
0x180016c4d  mov     rcx, [rsp+38h+arg_8]
0x180016c52  mov     rax, [rcx]
0x180016c55  mov     rax, [rax+10h]
0x180016c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c5e  mov     rcx, [rsp+38h+arg_8]
0x180016c63  jmp     short loc_180016C67
0x180016c65  xor     ecx, ecx
0x180016c67  mov     rax, [rsp+38h+arg_10]
0x180016c6c  sub     rax, rcx
0x180016c6f  sar     rax, 3
0x180016c73  test    eax, eax
0x180016c75  jz      short loc_180016C84
0x180016c77  add     rdi, 8
0x180016c7b  cmp     rdi, rbx
0x180016c7e  jnz     loc_180016BD4
0x180016c84  mov     rbx, [rsp+38h+arg_0]
0x180016c89  mov     rax, r14
0x180016c8c  mov     rsi, [rsp+38h+arg_18]
0x180016c91  mov     [r14], rdi
0x180016c94  add     rsp, 20h
0x180016c98  pop     r15
0x180016c9a  pop     r14
0x180016c9c  pop     rdi
0x180016c9d  retn
0x180016c9e  mov     ecx, eax; int
0x180016ca0  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180016ca6  mov     ecx, eax; int
0x180016ca8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
