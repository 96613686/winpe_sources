# ATL::CComObject<CFmIfsEngine>::`vector deleting destructor'(uint)

- ea: `0x1800028d0`
- end: `0x180002958`
- name: `??_E?$CComObject@VCFmIfsEngine@@@ATL@@UEAAPEAXI@Z`
- size: `136`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800028d0`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002926`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002926`
- `ntdll!RtlFreeHeap` at `0x180002944`
- `ntdll!RtlFreeHeap` at `0x180002944`

## pseudocode

```c
char *__fastcall ATL::CComObject<CFmIfsEngine>::`vector deleting destructor'(char *P, char a2)
{
  __int64 v4; // rcx

  *((_DWORD *)P + 2) = -1073741823;
  *(_QWORD *)P = &ATL::CComObject<CFmIfsEngine>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *((_QWORD *)P + 8);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( P[56] )
  {
    P[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(P + 16));
  }
  if ( (a2 & 1) != 0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return P;
}

```

## disassembly

```asm
0x1800028d0  mov     [rsp+arg_0], rbx
0x1800028d5  push    rdi
0x1800028d6  sub     rsp, 20h
0x1800028da  mov     dword ptr [rcx+8], 0C0000001h
0x1800028e1  lea     rax, ??_7?$CComObject@VCFmIfsEngine@@@ATL@@6B@; const ATL::CComObject<CFmIfsEngine>::`vftable'
0x1800028e8  mov     [rcx], rax
0x1800028eb  mov     rbx, rcx
0x1800028ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800028f5  mov     edi, edx
0x1800028f7  mov     rax, [rcx]
0x1800028fa  mov     rax, [rax+10h]
0x1800028fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002903  mov     rcx, [rbx+40h]
0x180002907  test    rcx, rcx
0x18000290a  jz      short loc_180002918
0x18000290c  mov     rax, [rcx]
0x18000290f  mov     rax, [rax+10h]
0x180002913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002918  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000291c  cmp     byte ptr [rcx+28h], 0
0x180002920  jz      short loc_18000292C
0x180002922  mov     byte ptr [rcx+28h], 0
0x180002926  call    cs:__imp_DeleteCriticalSection
0x18000292c  test    dil, 1
0x180002930  jz      short loc_18000294A
0x180002932  mov     rcx, gs:60h
0x18000293b  mov     r8, rbx; P
0x18000293e  xor     edx, edx; Flags
0x180002940  mov     rcx, [rcx+30h]; HeapHandle
0x180002944  call    cs:__imp_RtlFreeHeap
0x18000294a  mov     rax, rbx
0x18000294d  mov     rbx, [rsp+28h+arg_0]
0x180002952  add     rsp, 20h
0x180002956  pop     rdi
0x180002957  retn
```
