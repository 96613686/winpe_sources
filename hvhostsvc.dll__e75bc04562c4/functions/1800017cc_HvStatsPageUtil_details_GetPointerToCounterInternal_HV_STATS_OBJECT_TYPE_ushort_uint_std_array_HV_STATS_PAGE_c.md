# HvStatsPageUtil::details::GetPointerToCounterInternal(_HV_STATS_OBJECT_TYPE,ushort,uint,std::array<_HV_STATS_PAGE const *,2> const &)

- ea: `0x1800017cc`
- end: `0x180001821`
- name: `?GetPointerToCounterInternal@details@HvStatsPageUtil@@YAPEA_KW4_HV_STATS_OBJECT_TYPE@@GIAEBV?$array@PEBU_HV_STATS_PAGE@@$01@std@@@Z`
- size: `85`
- prototype: `_QWORD *__fastcall(__int64, unsigned __int16, unsigned int, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800013a0`
- `0x180001540`
- `0x1800072d4`

## callees

- `0x1800017cc`
- `0x180001828`

## pseudocode

```c
_QWORD *__fastcall HvStatsPageUtil::details::GetPointerToCounterInternal(
        __int64 a1,
        unsigned __int16 a2,
        unsigned int a3,
        _QWORD *a4)
{
  _QWORD *result; // rax
  unsigned int v8; // ebp
  __int64 v9; // rdx

  result = 0;
  v8 = a1;
  if ( !*a4
    || (result = (_QWORD *)HvStatsPageUtil::details::GetPointerToCounterFromStatsPage(a1, *a4, a2, a3)) == 0
    || !*result )
  {
    v9 = a4[1];
    if ( v9 )
      return (_QWORD *)HvStatsPageUtil::details::GetPointerToCounterFromStatsPage(v8, v9, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x1800017cc  push    rbx
0x1800017ce  push    rbp
0x1800017cf  push    rsi
0x1800017d0  push    rdi
0x1800017d1  sub     rsp, 28h
0x1800017d5  movzx   esi, dx
0x1800017d8  xor     eax, eax
0x1800017da  mov     rdx, [r9]
0x1800017dd  mov     rbx, r9
0x1800017e0  mov     edi, r8d
0x1800017e3  mov     ebp, ecx
0x1800017e5  test    rdx, rdx
0x1800017e8  jz      short loc_180001801
0x1800017ea  mov     r9d, r8d
0x1800017ed  movzx   r8d, si
0x1800017f1  call    ?GetPointerToCounterFromStatsPage@details@HvStatsPageUtil@@YAPEA_KW4_HV_STATS_OBJECT_TYPE@@PEBU_HV_STATS_PAGE@@GI@Z; HvStatsPageUtil::details::GetPointerToCounterFromStatsPage(_HV_STATS_OBJECT_TYPE,_HV_STATS_PAGE const *,ushort,uint)
0x1800017f6  test    rax, rax
0x1800017f9  jz      short loc_180001801
0x1800017fb  cmp     qword ptr [rax], 0
0x1800017ff  jnz     short loc_180001818
0x180001801  mov     rdx, [rbx+8]
0x180001805  test    rdx, rdx
0x180001808  jz      short loc_180001818
0x18000180a  mov     r9d, edi
0x18000180d  movzx   r8d, si
0x180001811  mov     ecx, ebp
0x180001813  call    ?GetPointerToCounterFromStatsPage@details@HvStatsPageUtil@@YAPEA_KW4_HV_STATS_OBJECT_TYPE@@PEBU_HV_STATS_PAGE@@GI@Z; HvStatsPageUtil::details::GetPointerToCounterFromStatsPage(_HV_STATS_OBJECT_TYPE,_HV_STATS_PAGE const *,ushort,uint)
0x180001818  add     rsp, 28h
0x18000181c  pop     rdi
0x18000181d  pop     rsi
0x18000181e  pop     rbp
0x18000181f  pop     rbx
0x180001820  retn
```
