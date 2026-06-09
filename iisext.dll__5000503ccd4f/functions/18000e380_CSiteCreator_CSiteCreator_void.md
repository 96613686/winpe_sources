# CSiteCreator::~CSiteCreator(void)

- ea: `0x18000e380`
- end: `0x18000e3c6`
- name: `??1CSiteCreator@@UEAA@XZ`
- size: `70`
- prototype: `void __fastcall(CSiteCreator *__hidden this)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800086f0`
- `0x180008770`
- `0x180008c40`
- `0x180009200`
- `0x180009260`
- `0x1800092e0`
- `0x180009360`
- `0x1800093c0`
- `0x180009440`
- `0x180009650`
- `0x180009700`
- `0x1800097b0`
- `0x180009950`
- `0x180009a10`
- `0x180009a70`
- `0x18000e3d0`

## callees

- `0x18000e380`
- `0x180012010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000e3b9`
- `KERNEL32!DeleteCriticalSection` at `0x18000e3b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSiteCreator::~CSiteCreator(CSiteCreator *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CSecConLib::`vftable';
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 12, 0, 1) == 1 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18000e380  push    rbx
0x18000e382  sub     rsp, 20h
0x18000e386  mov     rbx, rcx
0x18000e389  lea     rax, ??_7CSecConLib@@6B@; const CSecConLib::`vftable'
0x18000e390  mov     [rcx], rax
0x18000e393  mov     rcx, [rcx+38h]
0x18000e397  test    rcx, rcx
0x18000e39a  jz      short loc_18000E3A9
0x18000e39c  mov     rax, [rcx]
0x18000e39f  mov     rax, [rax+10h]
0x18000e3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3a8  nop
0x18000e3a9  lea     rcx, [rbx+8]; lpCriticalSection
0x18000e3ad  xor     edx, edx
0x18000e3af  lea     eax, [rdx+1]
0x18000e3b2  lock cmpxchg [rcx+28h], edx
0x18000e3b7  jnz     short loc_18000E3C0
0x18000e3b9  call    cs:__imp_DeleteCriticalSection
0x18000e3bf  nop
0x18000e3c0  add     rsp, 20h
0x18000e3c4  pop     rbx
0x18000e3c5  retn
```
