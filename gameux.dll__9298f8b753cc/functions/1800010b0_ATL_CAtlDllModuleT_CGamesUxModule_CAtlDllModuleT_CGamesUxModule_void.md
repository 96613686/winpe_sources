# ATL::CAtlDllModuleT<CGamesUxModule>::CAtlDllModuleT<CGamesUxModule>(void)

- ea: `0x1800010b0`
- end: `0x18000115e`
- name: `??0?$CAtlDllModuleT@VCGamesUxModule@@@ATL@@QEAA@XZ`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001060`

## callees

- `0x1800010b0`
- `0x180001170`
- `0x180004010`

## pseudocode

```c
__int64 *ATL::CAtlDllModuleT<CGamesUxModule>::CAtlDllModuleT<CGamesUxModule>()
{
  __int64 v0; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v1; // rdi
  __int64 *i; // rax

  CriticalSection.SpinCount = 0;
  qword_180007748 = 0;
  *(_OWORD *)&CriticalSection.DebugInfo = 0;
  qword_180007750 = 0;
  *(_OWORD *)&CriticalSection.OwningThread = 0;
  ATL::_pAtlModule = (struct ATL::CAtlModule *)&_AtlModule;
  qword_180007780 = 0;
  if ( (int)ATL::CComCriticalSection::Init(&CriticalSection) >= 0 )
    qword_180007748 = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  v1 = off_1800070B0;
  for ( i = off_1800070B8; v1 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v1 )
  {
    if ( *v1 )
    {
      LOBYTE(v0) = 1;
      (*((void (__fastcall **)(__int64))*v1 + 8))(v0);
      i = off_1800070B8;
    }
  }
  return &_AtlModule;
}

```

## disassembly

```asm
0x1800010b0  mov     [rsp+arg_0], rbx
0x1800010b5  push    rdi
0x1800010b6  sub     rsp, 20h
0x1800010ba  xor     eax, eax
0x1800010bc  lea     rbx, ?_AtlModule@@3VCGamesUxModule@@A; CGamesUxModule _AtlModule
0x1800010c3  xorps   xmm0, xmm0
0x1800010c6  mov     cs:CriticalSection.SpinCount, rax
0x1800010cd  lea     rcx, CriticalSection; this
0x1800010d4  mov     cs:qword_180007748, rax
0x1800010db  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x1800010e2  mov     cs:qword_180007750, rax
0x1800010e9  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x1800010f0  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rbx; ATL::CAtlModule * ATL::_pAtlModule
0x1800010f7  mov     cs:qword_180007780, rax
0x1800010fe  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001103  test    eax, eax
0x180001105  jns     short loc_180001110
0x180001107  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000110e  jmp     short loc_18000111A
0x180001110  mov     dword ptr cs:qword_180007748, 38h ; '8'
0x18000111a  mov     rdi, cs:off_1800070B0
0x180001121  mov     rax, cs:off_1800070B8
0x180001128  cmp     rdi, rax
0x18000112b  jnb     short loc_180001150
0x18000112d  mov     rdx, [rdi]
0x180001130  test    rdx, rdx
0x180001133  jz      short loc_180001147
0x180001135  mov     rax, [rdx+40h]
0x180001139  mov     cl, 1
0x18000113b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001140  mov     rax, cs:off_1800070B8
0x180001147  add     rdi, 8
0x18000114b  cmp     rdi, rax
0x18000114e  jb      short loc_18000112D
0x180001150  mov     rax, rbx
0x180001153  mov     rbx, [rsp+28h+arg_0]
0x180001158  add     rsp, 20h
0x18000115c  pop     rdi
0x18000115d  retn
```
