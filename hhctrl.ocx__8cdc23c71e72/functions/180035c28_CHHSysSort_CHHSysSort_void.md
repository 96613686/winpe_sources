# CHHSysSort::~CHHSysSort(void)

- ea: `0x180035c28`
- end: `0x180035cbd`
- name: `??1CHHSysSort@@UEAA@XZ`
- size: `149`
- prototype: `void __fastcall(CHHSysSort *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035cd0`
- `0x18003eb48`
- `0x18003eb98`

## callees

- `0x180035c08`
- `0x180035c28`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180035c5a`
- `KERNEL32!GlobalFree` at `0x180035c7b`
- `KERNEL32!GlobalFree` at `0x180035c5a`
- `KERNEL32!GlobalFree` at `0x180035c7b`
- `KERNEL32!DeleteCriticalSection` at `0x180035ca9`
- `KERNEL32!DeleteCriticalSection` at `0x180035ca9`

## pseudocode

```c
void __fastcall CHHSysSort::~CHHSysSort(CHHSysSort *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CHHSysSort::`vftable'{for `IITSortKey'};
  *((_QWORD *)this + 1) = &CHHSysSort::`vftable'{for `IITSortKeyConfig'};
  *((_QWORD *)this + 2) = &CHHSysSort::`vftable'{for `IPersistStreamInit'};
  v2 = (void *)*((_QWORD *)this + 14);
  if ( v2 )
  {
    GlobalFree(v2);
    *((_QWORD *)this + 14) = 0;
    *((_DWORD *)this + 32) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 15);
  if ( v3 )
  {
    GlobalFree(v3);
    *((_QWORD *)this + 15) = 0;
    *((_DWORD *)this + 33) = 0;
  }
  *(_OWORD *)((char *)this + 92) = 0;
  *((_QWORD *)this + 10) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((CHHSysSort *)((char *)this + 32));
}

```

## disassembly

```asm
0x180035c28  push    rbx
0x180035c2a  sub     rsp, 20h
0x180035c2e  lea     rax, ??_7CHHSysSort@@6BIITSortKey@@@; const CHHSysSort::`vftable'{for `IITSortKey'}
0x180035c35  mov     rbx, rcx
0x180035c38  mov     [rcx], rax
0x180035c3b  lea     rax, ??_7CHHSysSort@@6BIITSortKeyConfig@@@; const CHHSysSort::`vftable'{for `IITSortKeyConfig'}
0x180035c42  mov     [rcx+8], rax
0x180035c46  lea     rax, ??_7CHHSysSort@@6BIPersistStreamInit@@@; const CHHSysSort::`vftable'{for `IPersistStreamInit'}
0x180035c4d  mov     [rcx+10h], rax
0x180035c51  mov     rcx, [rcx+70h]; hMem
0x180035c55  test    rcx, rcx
0x180035c58  jz      short loc_180035C72
0x180035c5a  call    cs:__imp_GlobalFree
0x180035c60  mov     qword ptr [rbx+70h], 0
0x180035c68  mov     dword ptr [rbx+80h], 0
0x180035c72  mov     rcx, [rbx+78h]; hMem
0x180035c76  test    rcx, rcx
0x180035c79  jz      short loc_180035C93
0x180035c7b  call    cs:__imp_GlobalFree
0x180035c81  mov     qword ptr [rbx+78h], 0
0x180035c89  mov     dword ptr [rbx+84h], 0
0x180035c93  xorps   xmm0, xmm0
0x180035c96  lea     rcx, [rbx+88h]; lpCriticalSection
0x180035c9d  movups  xmmword ptr [rbx+5Ch], xmm0
0x180035ca1  mov     qword ptr [rbx+50h], 0
0x180035ca9  call    cs:__imp_DeleteCriticalSection
0x180035caf  lea     rcx, [rbx+20h]; this
0x180035cb3  add     rsp, 20h
0x180035cb7  pop     rbx
0x180035cb8  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
