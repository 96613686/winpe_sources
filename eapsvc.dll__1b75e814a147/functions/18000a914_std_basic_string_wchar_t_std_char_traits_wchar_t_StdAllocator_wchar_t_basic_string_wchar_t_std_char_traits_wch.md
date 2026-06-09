# std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)

- ea: `0x18000a914`
- end: `0x18000a943`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180015652`
- `0x1800156d8`
- `0x1800156ea`
- `0x1800156fc`
- `0x180015e3f`
- `0x180015e63`
- `0x180015e99`

## callees

- `0x18000a914`
- `0x18000ab70`

## pseudocode

```c
__int64 __fastcall std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 24) > 7u )
    operator delete(*(LPCVOID *)a1);
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000a914  push    rbx
0x18000a916  sub     rsp, 20h
0x18000a91a  cmp     qword ptr [rcx+18h], 7
0x18000a91f  mov     rbx, rcx
0x18000a922  jbe     short loc_18000A92C
0x18000a924  mov     rcx, [rcx]; lpMem
0x18000a927  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a92c  xor     eax, eax
0x18000a92e  mov     qword ptr [rbx+18h], 7
0x18000a936  mov     [rbx+10h], rax
0x18000a93a  mov     [rbx], ax
0x18000a93d  add     rsp, 20h
0x18000a941  pop     rbx
0x18000a942  retn
```
