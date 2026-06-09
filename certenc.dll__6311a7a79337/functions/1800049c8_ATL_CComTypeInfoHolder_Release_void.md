# ATL::CComTypeInfoHolder::Release(void)

- ea: `0x1800049c8`
- end: `0x180004a14`
- name: `?Release@CComTypeInfoHolder@ATL@@QEAAXXZ`
- size: `76`
- prototype: `void __fastcall(ATL::CComTypeInfoHolder *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a2c`
- `0x1800022ac`
- `0x180002acc`
- `0x18000374c`
- `0x180004bc8`
- `0x180007a20`

## callees

- `0x1800049c8`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800049d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800049d8`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::Release(ATL::CComTypeInfoHolder *this)
{
  __int64 v3; // rcx

  EnterCriticalSection(&CriticalSection);
  if ( (*((_DWORD *)this + 8))-- == 1 )
  {
    v3 = *((_QWORD *)this + 3);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 3) = 0;
  }
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x1800049c8  push    rbx
0x1800049ca  sub     rsp, 20h
0x1800049ce  mov     rbx, rcx
0x1800049d1  lea     rcx, CriticalSection; lpCriticalSection
0x1800049d8  call    cs:__imp_EnterCriticalSection
0x1800049de  sub     dword ptr [rbx+20h], 1
0x1800049e2  jnz     short loc_180004A01
0x1800049e4  mov     rcx, [rbx+18h]
0x1800049e8  test    rcx, rcx
0x1800049eb  jz      short loc_1800049F9
0x1800049ed  mov     rax, [rcx]
0x1800049f0  mov     rax, [rax+10h]
0x1800049f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f9  mov     qword ptr [rbx+18h], 0
0x180004a01  lea     rcx, CriticalSection
0x180004a08  add     rsp, 20h
0x180004a0c  pop     rbx
0x180004a0d  jmp     cs:__imp_LeaveCriticalSection
```
