# std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>::pop_front(void)

- ea: `0x18001117c`
- end: `0x1800111c9`
- name: `?pop_front@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@QEAAXXZ`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c4dc`

## callees

- `0x1800033d4`
- `0x18001117c`

## pseudocode

```c
__int64 __fastcall std::deque<ATL::CComPtr<IBackgroundCopyFile>>::pop_front(_QWORD *a1)
{
  __int64 result; // rax

  result = ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)(*(_QWORD *)(a1[1]
                                                                                    + 8 * ((a1[2] - 1LL) & (a1[3] >> 1)))
                                                                        + 8 * (a1[3] & 1LL)));
  if ( a1[4]-- == 1 )
    a1[3] = 0;
  else
    ++a1[3];
  return result;
}

```

## disassembly

```asm
0x18001117c  push    rbx
0x18001117e  sub     rsp, 20h
0x180011182  mov     r8, [rcx+18h]
0x180011186  mov     rbx, rcx
0x180011189  mov     rax, [rcx+10h]
0x18001118d  mov     rdx, r8
0x180011190  dec     rax
0x180011193  shr     rdx, 1
0x180011196  and     rdx, rax
0x180011199  and     r8d, 1
0x18001119d  mov     rax, [rcx+8]
0x1800111a1  mov     rax, [rax+rdx*8]
0x1800111a5  lea     rcx, [rax+r8*8]
0x1800111a9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800111ae  sub     qword ptr [rbx+20h], 1
0x1800111b3  jnz     short loc_1800111BF
0x1800111b5  mov     qword ptr [rbx+18h], 0
0x1800111bd  jmp     short loc_1800111C3
0x1800111bf  inc     qword ptr [rbx+18h]
0x1800111c3  add     rsp, 20h
0x1800111c7  pop     rbx
0x1800111c8  retn
```
