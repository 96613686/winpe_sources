# ProcessorData::ProcessorData(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,unsigned __int64)

- ea: `0x18005719c`
- end: `0x180057218`
- name: `??0ProcessorData@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800830e8`

## callees

- `0x18000b6f0`
- `0x18003274c`
- `0x18004ca90`
- `0x18005719c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800571ee`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800571ee`

## pseudocode

```c
__int64 __fastcall ProcessorData::ProcessorData(__int64 a1, _QWORD *a2, __int64 a3)
{
  void *v3; // rbx
  _QWORD *v6; // [rsp+20h] [rbp-18h]

  v3 = a2;
  v6 = a2;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  BlockerData::BlockerData(a1, a2, 4, a3, v6);
  *(_QWORD *)a1 = &ProcessorData::`vftable';
  CoCreateGuid((GUID *)(a1 + 576));
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v3);
  return a1;
}

```

## disassembly

```asm
0x18005719c  mov     [rsp+arg_10], rbx
0x1800571a1  push    rdi
0x1800571a2  sub     rsp, 30h
0x1800571a6  mov     rax, cs:__security_cookie
0x1800571ad  xor     rax, rsp
0x1800571b0  mov     [rsp+38h+var_10], rax
0x1800571b5  mov     rbx, rdx
0x1800571b8  mov     rdi, rcx
0x1800571bb  mov     [rsp+38h+var_18], rcx
0x1800571c0  mov     [rsp+38h+var_18], rdx
0x1800571c5  cmp     qword ptr [rdx+18h], 7
0x1800571ca  jbe     short loc_1800571CF
0x1800571cc  mov     rdx, [rdx]
0x1800571cf  mov     r9, r8
0x1800571d2  mov     r8d, 4
0x1800571d8  call    ??0BlockerData@@QEAA@PEBGW4BlockerType@@_K@Z; BlockerData::BlockerData(ushort const *,BlockerType,unsigned __int64)
0x1800571dd  lea     rax, ??_7ProcessorData@@6B@; const ProcessorData::`vftable'
0x1800571e4  mov     [rdi], rax
0x1800571e7  lea     rcx, [rdi+240h]; pguid
0x1800571ee  call    cs:__imp_CoCreateGuid
0x1800571f4  nop
0x1800571f5  mov     rcx, rbx; void *
0x1800571f8  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x1800571fd  mov     rax, rdi
0x180057200  mov     rcx, [rsp+38h+var_10]
0x180057205  xor     rcx, rsp; StackCookie
0x180057208  call    __security_check_cookie
0x18005720d  mov     rbx, [rsp+38h+arg_10]
0x180057212  add     rsp, 30h
0x180057216  pop     rdi
0x180057217  retn
```
