# std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>>>,_lambda_c16354c18a8367b613a24b6278bec278_>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>>>,_lambda_c16354c18a8367b613a24b6278bec278_)

- ea: `0x18003a6b8`
- end: `0x18003a7da`
- name: `??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@@std@@@std@@@std@@@std@@V_lambda_c16354c18a8367b613a24b6278bec278_@@@std@@YA?AV_lambda_c16354c18a8367b613a24b6278bec278_@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@@std@@@std@@@std@@@0@0V1@@Z`
- size: `290`
- prototype: `_OWORD *__fastcall(_OWORD *, __int64 *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001b72c`

## callees

- `0x1800104b4`
- `0x180010b64`
- `0x18003a6b8`
- `0x18003ae00`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003a72f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003a72f`

## pseudocode

```c
_OWORD *__fastcall std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>>>,_lambda_c16354c18a8367b613a24b6278bec278_>(
        _OWORD *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 a4)
{
  unsigned int v8; // r8d
  const char *v9; // r9
  __int64 **v10; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  LPCVOID lpBuffer; // [rsp+30h] [rbp-58h] BYREF
  std::_Ref_count_base *v15; // [rsp+38h] [rbp-50h]
  __int128 v16; // [rsp+40h] [rbp-48h]
  _BYTE v17[8]; // [rsp+50h] [rbp-38h] BYREF
  std::_Ref_count_base *v18; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  while ( a2 != a3 )
  {
    v16 = *((_OWORD *)a2 + 2);
    std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>(v17, a2 + 6);
    std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>(&lpBuffer, v17);
    if ( lpBuffer && !WriteFile(**(HANDLE **)a4, lpBuffer, 0x248u, *(LPDWORD *)(a4 + 8), 0) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xEA, v8, v9);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    v10 = (__int64 **)a2[2];
    if ( *((_BYTE *)v10 + 25) )
    {
      for ( i = (__int64 *)a2[1]; !*((_BYTE *)i + 25) && a2 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        a2 = i;
      a2 = i;
    }
    else
    {
      a2 = (__int64 *)a2[2];
      for ( j = *v10; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        a2 = j;
    }
  }
  *a1 = *(_OWORD *)a4;
  return a1;
}

```

## disassembly

```asm
0x18003a6b8  push    rbx
0x18003a6ba  push    rsi
0x18003a6bb  push    rdi
0x18003a6bc  push    r14
0x18003a6be  sub     rsp, 68h
0x18003a6c2  mov     r14, r9
0x18003a6c5  mov     rdi, r8
0x18003a6c8  mov     rbx, rdx
0x18003a6cb  mov     rsi, rcx
0x18003a6ce  cmp     rbx, rdi
0x18003a6d1  jz      loc_18003A7B9
0x18003a6d7  movups  xmm0, xmmword ptr [rbx+20h]
0x18003a6db  movdqu  [rsp+88h+var_48], xmm0
0x18003a6e1  lea     rdx, [rbx+30h]
0x18003a6e5  lea     rcx, [rsp+88h+var_38]
0x18003a6ea  call    ??0?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>(std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2> const &)
0x18003a6ef  lea     rcx, [rsp+88h+var_48]
0x18003a6f4  mov     [rsp+88h+arg_8], rcx
0x18003a6fc  lea     rdx, [rsp+88h+var_38]
0x18003a701  lea     rcx, [rsp+88h+lpBuffer]
0x18003a706  call    ??0?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>(std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2> const &)
0x18003a70b  nop
0x18003a70c  mov     rdx, [rsp+88h+lpBuffer]; lpBuffer
0x18003a711  test    rdx, rdx
0x18003a714  jz      short loc_18003A74B
0x18003a716  mov     rcx, [r14]
0x18003a719  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x18003a722  mov     r9, [r14+8]; lpNumberOfBytesWritten
0x18003a726  mov     r8d, 248h; nNumberOfBytesToWrite
0x18003a72c  mov     rcx, [rcx]; hFile
0x18003a72f  call    cs:__imp_WriteFile
0x18003a736  nop     dword ptr [rax+rax+00h]
0x18003a73b  mov     rcx, [rsp+88h]; this
0x18003a743  test    eax, eax
0x18003a745  jz      loc_18003A7CF
0x18003a74b  mov     rcx, [rsp+88h+var_50]; this
0x18003a750  test    rcx, rcx
0x18003a753  jz      short loc_18003A75B
0x18003a755  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003a75a  nop
0x18003a75b  mov     rcx, [rsp+88h+var_30]; this
0x18003a760  test    rcx, rcx
0x18003a763  jz      short loc_18003A76A
0x18003a765  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003a76a  mov     rcx, [rbx+10h]
0x18003a76e  cmp     byte ptr [rcx+19h], 0
0x18003a772  jz      short loc_18003A795
0x18003a774  mov     rax, [rbx+8]
0x18003a778  jmp     short loc_18003A787
0x18003a77a  cmp     rbx, [rax+10h]
0x18003a77e  jnz     short loc_18003A78D
0x18003a780  mov     rbx, rax
0x18003a783  mov     rax, [rax+8]
0x18003a787  cmp     byte ptr [rax+19h], 0
0x18003a78b  jz      short loc_18003A77A
0x18003a78d  mov     rbx, rax
0x18003a790  jmp     loc_18003A6CE
0x18003a795  mov     rbx, rcx
0x18003a798  mov     rcx, [rcx]
0x18003a79b  cmp     byte ptr [rcx+19h], 0
0x18003a79f  jnz     loc_18003A6CE
0x18003a7a5  mov     rbx, rcx
0x18003a7a8  mov     rax, [rcx]
0x18003a7ab  mov     rcx, rax
0x18003a7ae  cmp     byte ptr [rax+19h], 0
0x18003a7b2  jz      short loc_18003A7A5
0x18003a7b4  jmp     loc_18003A6CE
0x18003a7b9  movaps  xmm0, xmmword ptr [r14]
0x18003a7bd  movdqu  xmmword ptr [rsi], xmm0
0x18003a7c1  mov     rax, rsi
0x18003a7c4  add     rsp, 68h
0x18003a7c8  pop     r14
0x18003a7ca  pop     rdi
0x18003a7cb  pop     rsi
0x18003a7cc  pop     rbx
0x18003a7cd  retn
0x18003a7cf  mov     edx, 0EAh; void *
0x18003a7d4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
