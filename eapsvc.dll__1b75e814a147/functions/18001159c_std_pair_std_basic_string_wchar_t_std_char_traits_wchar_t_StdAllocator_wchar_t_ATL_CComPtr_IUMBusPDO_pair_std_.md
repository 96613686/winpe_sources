# std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>::~pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>(void)

- ea: `0x18001159c`
- end: `0x1800115e5`
- name: `??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@QEAA@XZ`
- size: `73`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015ebd`

## callees

- `0x18000ab70`
- `0x18001159c`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>::~pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 32);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *(_QWORD *)(a1 + 24) > 7u )
    operator delete(*(LPCVOID *)a1);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  result = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18001159c  push    rbx
0x18001159e  sub     rsp, 20h
0x1800115a2  mov     rbx, rcx
0x1800115a5  mov     rcx, [rcx+20h]
0x1800115a9  test    rcx, rcx
0x1800115ac  jz      short loc_1800115BB
0x1800115ae  mov     rax, [rcx]
0x1800115b1  mov     rax, [rax+10h]
0x1800115b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115ba  nop
0x1800115bb  cmp     qword ptr [rbx+18h], 7
0x1800115c0  jbe     short loc_1800115CA
0x1800115c2  mov     rcx, [rbx]; lpMem
0x1800115c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800115ca  mov     qword ptr [rbx+10h], 0
0x1800115d2  mov     qword ptr [rbx+18h], 7
0x1800115da  xor     eax, eax
0x1800115dc  mov     [rbx], ax
0x1800115df  add     rsp, 20h
0x1800115e3  pop     rbx
0x1800115e4  retn
```
