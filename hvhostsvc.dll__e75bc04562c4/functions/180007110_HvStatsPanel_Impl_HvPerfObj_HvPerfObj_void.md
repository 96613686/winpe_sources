# HvStatsPanel::Impl::HvPerfObj::~HvPerfObj(void)

- ea: `0x180007110`
- end: `0x1800071c8`
- name: `??1HvPerfObj@Impl@HvStatsPanel@@QEAA@XZ`
- size: `184`
- prototype: `void __fastcall(HvStatsPanel::Impl::HvPerfObj *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180007018`

## callees

- `0x180007048`
- `0x180007110`
- `0x180007268`
- `0x180007af8`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18000713c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18000713c`

## pseudocode

```c
void __fastcall HvStatsPanel::Impl::HvPerfObj::~HvPerfObj(HvStatsPanel::Impl::HvPerfObj *this)
{
  __int64 *v2; // rsi
  PPERF_COUNTERSET_INSTANCE *v3; // rax
  char *v4; // rdi
  __int64 v5; // rdx

  v2 = (__int64 *)((char *)this + 24);
  v3 = (PPERF_COUNTERSET_INSTANCE *)*((_QWORD *)this + 3);
  v4 = (char *)this + 32;
  if ( v3 )
  {
    if ( *v3 )
      PerfDeleteInstance(*(HANDLE *)(*(_QWORD *)v4 + 16LL), *v3);
    v5 = *v2;
    *v2 = 0;
    if ( v5 )
      std::default_delete<_VM_PERF_COUNTERSET_INSTANCE>::operator()();
  }
  if ( *(_QWORD *)this )
  {
    v4 = (char *)this + 32;
    HvServiceUtil::UnmapHvStatsPage(
      *((_QWORD *)this + 4) + 8LL,
      *((unsigned int *)&HvStatsPanel::Impl::m_traits + 16 * (unsigned __int64)*((unsigned __int8 *)this + 16) + 1),
      *((unsigned int *)this + 5));
    *(_QWORD *)this = 0;
  }
  if ( *((_QWORD *)this + 1) )
  {
    HvServiceUtil::UnmapHvStatsPage(
      *(_QWORD *)v4 + 8LL,
      *((unsigned int *)&HvStatsPanel::Impl::m_traits + 16 * (unsigned __int64)*((unsigned __int8 *)this + 16) + 2),
      *((unsigned int *)this + 5));
    *((_QWORD *)this + 1) = 0;
  }
  std::unique_ptr<_VM_PERF_COUNTERSET_INSTANCE>::~unique_ptr<_VM_PERF_COUNTERSET_INSTANCE>(v2);
}

```

## disassembly

```asm
0x180007110  push    rbx
0x180007112  push    rsi
0x180007113  push    rdi
0x180007114  push    r14
0x180007116  sub     rsp, 28h
0x18000711a  mov     rbx, rcx
0x18000711d  lea     rsi, [rcx+18h]
0x180007121  mov     rax, [rsi]
0x180007124  lea     rdi, [rcx+20h]
0x180007128  test    rax, rax
0x18000712b  jz      short loc_180007156
0x18000712d  mov     rdx, [rax]; InstanceBlock
0x180007130  test    rdx, rdx
0x180007133  jz      short loc_180007142
0x180007135  mov     rcx, [rdi]
0x180007138  mov     rcx, [rcx+10h]; Provider
0x18000713c  call    cs:__imp_PerfDeleteInstance
0x180007142  mov     rdx, [rsi]
0x180007145  mov     qword ptr [rsi], 0
0x18000714c  test    rdx, rdx
0x18000714f  jz      short loc_180007156
0x180007151  call    ??R?$default_delete@U_VM_PERF_COUNTERSET_INSTANCE@@@std@@QEBAXPEAU_VM_PERF_COUNTERSET_INSTANCE@@@Z; std::default_delete<_VM_PERF_COUNTERSET_INSTANCE>::operator()(_VM_PERF_COUNTERSET_INSTANCE *)
0x180007156  lea     r14, ?m_traits@Impl@HvStatsPanel@@0QBU_unnamed_type_m_traits_@12@B; HvStatsPanel::Impl::_unnamed_type_m_traits_ const near * const HvStatsPanel::Impl::m_traits
0x18000715d  cmp     qword ptr [rbx], 0
0x180007161  jz      short loc_18000718B
0x180007163  lea     rdi, [rbx+20h]
0x180007167  movzx   edx, byte ptr [rbx+10h]
0x18000716b  shl     rdx, 6
0x18000716f  mov     rcx, [rdi]
0x180007172  add     rcx, 8
0x180007176  mov     r8d, [rbx+14h]
0x18000717a  mov     edx, [rdx+r14+4]
0x18000717f  call    ?UnmapHvStatsPage@HvServiceUtil@@QEBAXW4_HV_STATS_TYPE@@I@Z; HvServiceUtil::UnmapHvStatsPage(_HV_STATS_TYPE,uint)
0x180007184  mov     qword ptr [rbx], 0
0x18000718b  cmp     qword ptr [rbx+8], 0
0x180007190  jz      short loc_1800071B7
0x180007192  movzx   edx, byte ptr [rbx+10h]
0x180007196  shl     rdx, 6
0x18000719a  mov     rcx, [rdi]
0x18000719d  add     rcx, 8
0x1800071a1  mov     r8d, [rbx+14h]
0x1800071a5  mov     edx, [rdx+r14+8]
0x1800071aa  call    ?UnmapHvStatsPage@HvServiceUtil@@QEBAXW4_HV_STATS_TYPE@@I@Z; HvServiceUtil::UnmapHvStatsPage(_HV_STATS_TYPE,uint)
0x1800071af  mov     qword ptr [rbx+8], 0
0x1800071b7  mov     rcx, rsi
0x1800071ba  add     rsp, 28h
0x1800071be  pop     r14
0x1800071c0  pop     rdi
0x1800071c1  pop     rsi
0x1800071c2  pop     rbx
0x1800071c3  jmp     ??1?$unique_ptr@U_VM_PERF_COUNTERSET_INSTANCE@@U?$default_delete@U_VM_PERF_COUNTERSET_INSTANCE@@@std@@@std@@QEAA@XZ; std::unique_ptr<_VM_PERF_COUNTERSET_INSTANCE>::~unique_ptr<_VM_PERF_COUNTERSET_INSTANCE>(void)
```
