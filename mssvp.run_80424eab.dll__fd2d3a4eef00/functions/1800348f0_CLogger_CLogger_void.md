# CLogger::~CLogger(void)

- ea: `0x1800348f0`
- end: `0x18003494e`
- name: `??1CLogger@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(CLogger *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800349d0`

## callees

- `0x1800048c0`
- `0x1800348f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034907`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034907`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034917`

## pseudocode

```c
void __fastcall CLogger::~CLogger(CLogger *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CLogger::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 6) = -1;
  }
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>((char *)this + 32);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>((char *)this + 24);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>((char *)this + 16);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>((char *)this + 8);
}

```

## disassembly

```asm
0x1800348f0  push    rbx
0x1800348f2  sub     rsp, 20h
0x1800348f6  lea     rax, ??_7CLogger@@6B@; const CLogger::`vftable'
0x1800348fd  mov     rbx, rcx
0x180034900  mov     [rcx], rax
0x180034903  add     rcx, 48h ; 'H'; lpCriticalSection
0x180034907  call    cs:__imp_DeleteCriticalSection
0x18003490d  mov     rcx, [rbx+30h]; hObject
0x180034911  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180034915  jz      short loc_180034925
0x180034917  call    cs:__imp_CloseHandle
0x18003491d  mov     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFFFh
0x180034925  lea     rcx, [rbx+20h]
0x180034929  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18003492e  lea     rcx, [rbx+18h]
0x180034932  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180034937  lea     rcx, [rbx+10h]
0x18003493b  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180034940  lea     rcx, [rbx+8]
0x180034944  add     rsp, 20h
0x180034948  pop     rbx
0x180034949  jmp     ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
```
