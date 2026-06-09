# CFilterGraph::InitClass(int,_GUID const *)

- ea: `0x180021470`
- end: `0x1800215b3`
- name: `?InitClass@CFilterGraph@@SAXHPEBU_GUID@@@Z`
- size: `323`
- prototype: `void __fastcall(int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180021470`
- `0x18002fb8c`
- `0x18015e010`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x18002158f`
- `KERNEL32!HeapDestroy` at `0x18002158f`
- `KERNEL32!QueryPerformanceFrequency` at `0x1800214c0`
- `KERNEL32!QueryPerformanceFrequency` at `0x1800214c0`
- `KERNEL32!DeleteCriticalSection` at `0x180021509`
- `KERNEL32!DeleteCriticalSection` at `0x180021551`
- `KERNEL32!DeleteCriticalSection` at `0x180021564`
- `KERNEL32!DeleteCriticalSection` at `0x180021577`
- `KERNEL32!DeleteCriticalSection` at `0x180021509`
- `KERNEL32!DeleteCriticalSection` at `0x180021551`
- `KERNEL32!DeleteCriticalSection` at `0x180021564`
- `KERNEL32!DeleteCriticalSection` at `0x180021577`
- `KERNEL32!DeleteCriticalSection` at `0x1800215a7`
- `KERNEL32!InitializeCriticalSection` at `0x1800214a6`
- `KERNEL32!InitializeCriticalSection` at `0x1800214a6`
- `KERNEL32!InitializeCriticalSection` at `0x1800214f6`

## pseudocode

```c
void __fastcall CFilterGraph::InitClass(struct ATL::_ATL_MODULE *a1, struct _GUID *a2)
{
  _QWORD *v2; // rbx
  __int64 v3; // rcx
  LARGE_INTEGER Frequency; // [rsp+40h] [rbp+18h] BYREF

  if ( (_DWORD)a1 )
  {
    _Module = 176;
    qword_18019E870 = 0;
    ATL::AtlModuleInit(a1, (struct ATL::_ATL_OBJMAP_ENTRY *)a2, g_hInst);
    InitializeCriticalSection(&CriticalSection);
    Frequency.QuadPart = 0;
    QueryPerformanceFrequency(&Frequency);
    *(double *)&qword_1801A1CC8 = 1000.0 / (double)(int)Frequency.LowPart;
    InitializeCriticalSection(&g_csObjectThread);
  }
  else
  {
    DeleteCriticalSection(&g_csObjectThread);
    v2 = (_QWORD *)qword_18019E7E0;
    if ( qword_18019E7E0 )
    {
      while ( *v2 )
      {
        v3 = v2[4];
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        v2[4] = 0;
        v2 += 7;
      }
    }
    DeleteCriticalSection(&stru_18019E7F8);
    DeleteCriticalSection(&stru_18019E820);
    DeleteCriticalSection(&stru_18019E848);
    if ( hHeap )
      HeapDestroy(hHeap);
    DeleteCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x180021470  push    rbx
0x180021472  sub     rsp, 20h
0x180021476  test    ecx, ecx
0x180021478  jz      loc_180021502
0x18002147e  mov     r8, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180021485  mov     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x18002148f  mov     cs:qword_18019E870, 0
0x18002149a  call    ?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z; ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)
0x18002149f  lea     rcx, CriticalSection; lpCriticalSection
0x1800214a6  call    cs:__imp_InitializeCriticalSection
0x1800214ad  nop     dword ptr [rax+rax+00h]
0x1800214b2  lea     rcx, [rsp+28h+Frequency]; lpFrequency
0x1800214b7  mov     qword ptr [rsp+28h+Frequency], 0
0x1800214c0  call    cs:__imp_QueryPerformanceFrequency
0x1800214c7  nop     dword ptr [rax+rax+00h]
0x1800214cc  movsd   xmm1, cs:__real@408f400000000000
0x1800214d4  lea     rcx, ?g_csObjectThread@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csObjectThread
0x1800214db  xorps   xmm0, xmm0
0x1800214de  cvtsi2sd xmm0, qword ptr [rsp+28h+Frequency]
0x1800214e5  divsd   xmm1, xmm0
0x1800214e9  movsd   cs:qword_1801A1CC8, xmm1
0x1800214f1  add     rsp, 20h
0x1800214f5  pop     rbx
0x1800214f6  jmp     cs:__imp_InitializeCriticalSection
0x180021502  lea     rcx, ?g_csObjectThread@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021509  call    cs:__imp_DeleteCriticalSection
0x180021510  nop     dword ptr [rax+rax+00h]
0x180021515  mov     rbx, cs:qword_18019E7E0
0x18002151c  test    rbx, rbx
0x18002151f  jnz     short loc_180021544
0x180021521  jmp     short loc_18002154A
0x180021523  mov     rcx, [rbx+20h]
0x180021527  test    rcx, rcx
0x18002152a  jz      short loc_180021538
0x18002152c  mov     rax, [rcx]
0x18002152f  mov     rax, [rax+10h]
0x180021533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021538  mov     qword ptr [rbx+20h], 0
0x180021540  add     rbx, 38h ; '8'
0x180021544  cmp     qword ptr [rbx], 0
0x180021548  jnz     short loc_180021523
0x18002154a  lea     rcx, stru_18019E7F8; lpCriticalSection
0x180021551  call    cs:__imp_DeleteCriticalSection
0x180021558  nop     dword ptr [rax+rax+00h]
0x18002155d  lea     rcx, stru_18019E820; lpCriticalSection
0x180021564  call    cs:__imp_DeleteCriticalSection
0x18002156b  nop     dword ptr [rax+rax+00h]
0x180021570  lea     rcx, stru_18019E848; lpCriticalSection
0x180021577  call    cs:__imp_DeleteCriticalSection
0x18002157e  nop     dword ptr [rax+rax+00h]
0x180021583  mov     rcx, cs:hHeap; hHeap
0x18002158a  test    rcx, rcx
0x18002158d  jz      short loc_18002159B
0x18002158f  call    cs:__imp_HeapDestroy
0x180021596  nop     dword ptr [rax+rax+00h]
0x18002159b  lea     rcx, CriticalSection
0x1800215a2  add     rsp, 20h
0x1800215a6  pop     rbx
0x1800215a7  jmp     cs:__imp_DeleteCriticalSection
```
