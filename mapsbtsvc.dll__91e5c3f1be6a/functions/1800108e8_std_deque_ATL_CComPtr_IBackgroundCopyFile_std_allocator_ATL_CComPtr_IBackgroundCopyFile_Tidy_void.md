# std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>::_Tidy(void)

- ea: `0x1800108e8`
- end: `0x18001094e`
- name: `?_Tidy@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@AEAAXXZ`
- size: `102`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b274`

## callees

- `0x1800033d4`
- `0x180010808`
- `0x1800108e8`

## pseudocode

```c
void __fastcall std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Tidy(_QWORD *a1)
{
  __int64 v2; // rcx

  while ( 1 )
  {
    v2 = a1[4];
    if ( !v2 )
      break;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)(*(_QWORD *)(a1[1]
                                                                             + 8
                                                                             * ((a1[2] - 1LL)
                                                                              & ((unsigned __int64)(v2 - 1 + a1[3]) >> 1)))
                                                                 + 8LL * (((_DWORD)v2 - 1 + *((_DWORD *)a1 + 6)) & 1)));
    if ( a1[4]-- == 1 )
      a1[3] = 0;
  }
  if ( a1[1] )
    std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Reset_map((__int64)a1);
}

```

## disassembly

```asm
0x1800108e8  push    rbx
0x1800108ea  sub     rsp, 20h
0x1800108ee  mov     rbx, rcx
0x1800108f1  mov     rcx, [rbx+20h]
0x1800108f5  test    rcx, rcx
0x1800108f8  jz      short loc_180010939
0x1800108fa  mov     rdx, [rbx+18h]
0x1800108fe  dec     rcx
0x180010901  mov     rax, [rbx+10h]
0x180010905  add     rdx, rcx
0x180010908  dec     rax
0x18001090b  mov     rcx, rdx
0x18001090e  shr     rcx, 1
0x180010911  and     edx, 1
0x180010914  and     rcx, rax
0x180010917  mov     rax, [rbx+8]
0x18001091b  mov     rax, [rax+rcx*8]
0x18001091f  lea     rcx, [rax+rdx*8]
0x180010923  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010928  sub     qword ptr [rbx+20h], 1
0x18001092d  jnz     short loc_1800108F1
0x18001092f  mov     qword ptr [rbx+18h], 0
0x180010937  jmp     short loc_1800108F1
0x180010939  cmp     qword ptr [rbx+8], 0
0x18001093e  jz      short loc_180010948
0x180010940  mov     rcx, rbx
0x180010943  call    ?_Reset_map@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@AEAAXXZ; std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Reset_map(void)
0x180010948  add     rsp, 20h
0x18001094c  pop     rbx
0x18001094d  retn
```
