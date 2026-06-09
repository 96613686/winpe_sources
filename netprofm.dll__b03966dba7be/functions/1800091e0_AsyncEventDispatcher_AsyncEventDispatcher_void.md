# AsyncEventDispatcher::~AsyncEventDispatcher(void)

- ea: `0x1800091e0`
- end: `0x180009245`
- name: `??1AsyncEventDispatcher@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(AsyncEventDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800091b4`

## callees

- `0x1800091e0`
- `0x18000924c`
- `0x18000c650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000923e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall AsyncEventDispatcher::~AsyncEventDispatcher(AsyncEventDispatcher *this)
{
  void *v2; // rcx

  AsyncEventDispatcher::Shutdown(this);
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, 8 * ((__int64)(*((_QWORD *)this + 10) - (_QWORD)v2) >> 3));
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x1800091e0  push    rbx
0x1800091e2  sub     rsp, 20h
0x1800091e6  mov     rbx, rcx
0x1800091e9  call    ?Shutdown@AsyncEventDispatcher@@QEAAXXZ; AsyncEventDispatcher::Shutdown(void)
0x1800091ee  mov     rcx, [rbx+40h]
0x1800091f2  test    rcx, rcx
0x1800091f5  jz      short loc_180009235
0x1800091f7  mov     rax, [rbx+50h]
0x1800091fb  sub     rax, rcx
0x1800091fe  sar     rax, 3
0x180009202  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18000920c  imul    rax, rdx
0x180009210  lea     rdx, [rax+rax*2]
0x180009214  shl     rdx, 3
0x180009218  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000921d  mov     qword ptr [rbx+40h], 0
0x180009225  mov     qword ptr [rbx+48h], 0
0x18000922d  mov     qword ptr [rbx+50h], 0
0x180009235  lea     rcx, [rbx+18h]
0x180009239  add     rsp, 20h
0x18000923d  pop     rbx
0x18000923e  jmp     cs:__imp_DeleteCriticalSection
```
