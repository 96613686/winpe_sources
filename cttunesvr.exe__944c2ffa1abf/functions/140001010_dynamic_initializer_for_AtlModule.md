# _dynamic_initializer_for___AtlModule__

- ea: `0x140001010`
- end: `0x140001116`
- name: `_dynamic_initializer_for___AtlModule__`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001010`
- `0x140001a68`
- `0x14000353c`
- `0x140007010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400010a9`
- `KERNEL32!GetModuleHandleW` at `0x1400010a9`
- `KERNEL32!GetCurrentThreadId` at `0x140001056`
- `KERNEL32!GetCurrentThreadId` at `0x140001056`
- `ole32!CoInitialize` at `0x140001091`
- `ole32!CoInitialize` at `0x140001091`

## string_xrefs

- `0x1400010a2`: `Mscoree.dll`

## pseudocode

```c
int dynamic_initializer_for___AtlModule__()
{
  DWORD CurrentThreadId; // eax
  HRESULT v1; // eax
  __int64 v2; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rbx
  __int64 *v4; // rax

  ATL::_pAtlModule = (struct ATL::CAtlModule *)&_AtlModule;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)qword_14000B828) >= 0 )
    dword_14000B818 = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  ATL::CAtlModule::m_libid = LIBID_cttunesvrLib;
  CurrentThreadId = GetCurrentThreadId();
  hObject = 0;
  dword_14000B858 = CurrentThreadId;
  dword_14000B868 = 5000;
  dwMilliseconds = 1000;
  byte_14000B870 = 1;
  byte_14000B872 = 0;
  v1 = CoInitialize(0);
  if ( v1 >= 0 )
  {
    byte_14000B872 = 1;
  }
  else if ( v1 != -2147417850 || !GetModuleHandleW(L"Mscoree.dll") )
  {
    ATL::CAtlBaseModule::m_bInitFailed = 1;
    goto LABEL_14;
  }
  v3 = off_14000B100;
  v4 = off_14000B108;
  while ( v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    if ( *v3 )
    {
      LOBYTE(v2) = 1;
      (*((void (__fastcall **)(__int64))*v3 + 8))(v2);
      v4 = off_14000B108;
    }
    ++v3;
  }
LABEL_14:
  _AtlModule = (__int64)&CcttunesvrModule::`vftable';
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for___AtlModule__);
}

```

## disassembly

```asm
0x140001010  push    rbx
0x140001012  sub     rsp, 20h
0x140001016  lea     rax, ?_AtlModule@@3VCcttunesvrModule@@A; CcttunesvrModule _AtlModule
0x14000101d  lea     rcx, qword_14000B828; this
0x140001024  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rax; ATL::CAtlModule * ATL::_pAtlModule
0x14000102b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140001030  test    eax, eax
0x140001032  jns     short loc_14000103D
0x140001034  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x14000103b  jmp     short loc_140001047
0x14000103d  mov     cs:dword_14000B818, 38h ; '8'
0x140001047  movups  xmm0, xmmword ptr cs:LIBID_cttunesvrLib.Data1
0x14000104e  movdqu  xmmword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CAtlModule::m_libid ...
0x140001056  call    cs:__imp_GetCurrentThreadId
0x14000105c  xor     ecx, ecx; pvReserved
0x14000105e  mov     cs:hObject, 0
0x140001069  mov     cs:dword_14000B858, eax
0x14000106f  mov     cs:dword_14000B868, 1388h
0x140001079  mov     cs:dwMilliseconds, 3E8h
0x140001083  mov     cs:byte_14000B870, 1
0x14000108a  mov     cs:byte_14000B872, 0
0x140001091  call    cs:__imp_CoInitialize
0x140001097  test    eax, eax
0x140001099  jns     short loc_1400010BD
0x14000109b  cmp     eax, 80010106h
0x1400010a0  jnz     short loc_1400010B4
0x1400010a2  lea     rcx, ModuleName; "Mscoree.dll"
0x1400010a9  call    cs:__imp_GetModuleHandleW
0x1400010af  test    rax, rax
0x1400010b2  jnz     short loc_1400010C4
0x1400010b4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1400010bb  jmp     short loc_1400010F7
0x1400010bd  mov     cs:byte_14000B872, 1
0x1400010c4  mov     rbx, cs:off_14000B100
0x1400010cb  mov     rax, cs:off_14000B108
0x1400010d2  jmp     short loc_1400010F2
0x1400010d4  mov     rdx, [rbx]
0x1400010d7  test    rdx, rdx
0x1400010da  jz      short loc_1400010EE
0x1400010dc  mov     rax, [rdx+40h]
0x1400010e0  mov     cl, 1
0x1400010e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400010e7  mov     rax, cs:off_14000B108
0x1400010ee  add     rbx, 8
0x1400010f2  cmp     rbx, rax
0x1400010f5  jb      short loc_1400010D4
0x1400010f7  lea     rax, ??_7CcttunesvrModule@@6B@; const CcttunesvrModule::`vftable'
0x1400010fe  lea     rcx, _dynamic_atexit_destructor_for___AtlModule__
0x140001105  mov     cs:?_AtlModule@@3VCcttunesvrModule@@A, rax; CcttunesvrModule _AtlModule
0x14000110c  add     rsp, 20h
0x140001110  pop     rbx
0x140001111  jmp     atexit
```
