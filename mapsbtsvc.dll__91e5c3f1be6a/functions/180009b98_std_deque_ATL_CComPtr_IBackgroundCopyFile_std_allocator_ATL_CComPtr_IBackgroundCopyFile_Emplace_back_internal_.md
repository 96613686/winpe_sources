# std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>::_Emplace_back_internal<ATL::CComPtr<IBackgroundCopyFile>>(ATL::CComPtr<IBackgroundCopyFile> &&)

- ea: `0x180009b98`
- end: `0x180009c2f`
- name: `??$_Emplace_back_internal@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@AEAAX$$QEAV?$CComPtr@UIBackgroundCopyFile@@@ATL@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000dd10`

## callees

- `0x180003a00`
- `0x180009b98`
- `0x18000a990`
- `0x18000fb2c`
- `0x180010434`
- `0x180010594`

## pseudocode

```c
__int64 __fastcall std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Emplace_back_internal<ATL::CComPtr<IBackgroundCopyFile>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 result; // rax

  v4 = *(_QWORD *)(a1 + 32);
  if ( ((*(_BYTE *)(a1 + 24) + (_BYTE)v4) & 1) == 0 && *(_QWORD *)(a1 + 16) <= (unsigned __int64)(v4 + 2) >> 1 )
    std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Growmap(a1);
  *(_QWORD *)(a1 + 24) &= 2LL * *(_QWORD *)(a1 + 16) - 1;
  v5 = *(_QWORD *)(a1 + 32) + *(_QWORD *)(a1 + 24);
  v6 = std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Getblock(a1, v5);
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v6) )
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v6) = std::_Allocate<16,std::_Default_allocate_traits>(0x10u);
  v7 = std::_Deque_val<std::_Deque_simple_types<ATL::CComPtr<IBackgroundCopyFile>>>::_Address_subscript(a1, v5);
  result = std::_Default_allocator_traits<std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>::construct<ATL::CComPtr<IBackgroundCopyFile>,ATL::CComPtr<IBackgroundCopyFile>>(
             v8,
             v7,
             a2);
  ++*(_QWORD *)(a1 + 32);
  return result;
}

```

## disassembly

```asm
0x180009b98  push    rbx
0x180009b9a  push    rbp
0x180009b9b  push    rsi
0x180009b9c  push    rdi
0x180009b9d  sub     rsp, 28h
0x180009ba1  mov     rbx, rcx
0x180009ba4  mov     rbp, rdx
0x180009ba7  mov     rcx, [rcx+20h]
0x180009bab  mov     al, cl
0x180009bad  add     al, [rbx+18h]
0x180009bb0  test    al, 1
0x180009bb2  jnz     short loc_180009BC9
0x180009bb4  lea     rax, [rcx+2]
0x180009bb8  shr     rax, 1
0x180009bbb  cmp     [rbx+10h], rax
0x180009bbf  ja      short loc_180009BC9
0x180009bc1  mov     rcx, rbx
0x180009bc4  call    ?_Growmap@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@AEAAX_K@Z; std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Growmap(unsigned __int64)
0x180009bc9  mov     rax, [rbx+10h]
0x180009bcd  mov     rcx, rbx
0x180009bd0  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rax*2]
0x180009bd8  and     [rbx+18h], rax
0x180009bdc  mov     rsi, [rbx+18h]
0x180009be0  add     rsi, [rbx+20h]
0x180009be4  mov     rdx, rsi
0x180009be7  call    ?_Getblock@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@AEBA_J_K@Z; std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Getblock(unsigned __int64)
0x180009bec  mov     rcx, [rbx+8]
0x180009bf0  mov     rdi, rax
0x180009bf3  cmp     qword ptr [rcx+rax*8], 0
0x180009bf8  jnz     short loc_180009C0C
0x180009bfa  mov     ecx, 10h
0x180009bff  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009c04  mov     rcx, [rbx+8]
0x180009c08  mov     [rcx+rdi*8], rax
0x180009c0c  mov     rdx, rsi
0x180009c0f  mov     rcx, rbx
0x180009c12  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@QEAAPEAV?$CComPtr@UIBackgroundCopyFile@@@ATL@@_K@Z; std::_Deque_val<std::_Deque_simple_types<ATL::CComPtr<IBackgroundCopyFile>>>::_Address_subscript(unsigned __int64)
0x180009c17  mov     r8, rbp
0x180009c1a  mov     rdx, rax
0x180009c1d  call    ??$construct@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V12@@?$_Default_allocator_traits@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@SAXAEAV?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@1@QEAV?$CComPtr@UIBackgroundCopyFile@@@ATL@@$$QEAV34@@Z; std::_Default_allocator_traits<std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>::construct<ATL::CComPtr<IBackgroundCopyFile>,ATL::CComPtr<IBackgroundCopyFile>>(std::allocator<ATL::CComPtr<IBackgroundCopyFile>> &,ATL::CComPtr<IBackgroundCopyFile> * const,ATL::CComPtr<IBackgroundCopyFile> &&)
0x180009c22  inc     qword ptr [rbx+20h]
0x180009c26  add     rsp, 28h
0x180009c2a  pop     rdi
0x180009c2b  pop     rsi
0x180009c2c  pop     rbp
0x180009c2d  pop     rbx
0x180009c2e  retn
```
