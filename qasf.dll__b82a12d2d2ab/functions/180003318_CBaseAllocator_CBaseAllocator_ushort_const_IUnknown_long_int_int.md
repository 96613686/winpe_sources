# CBaseAllocator::CBaseAllocator(ushort const *,IUnknown *,long *,int,int)

- ea: `0x180003318`
- end: `0x1800033ba`
- name: `??0CBaseAllocator@@QEAA@PEBGPEAUIUnknown@@PEAJHH@Z`
- size: `162`
- prototype: `CBaseAllocator *__fastcall(CBaseAllocator *__hidden this, const unsigned __int16 *, struct IUnknown *, int *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b610`

## callees

- `0x180003318`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180003341`
- `KERNEL32!InitializeCriticalSection` at `0x180003341`
- `KERNEL32!CreateSemaphoreExW` at `0x180003392`
- `KERNEL32!CreateSemaphoreExW` at `0x180003392`

## pseudocode

```c
CBaseAllocator *__fastcall CBaseAllocator::CBaseAllocator(
        CBaseAllocator *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        int *a4)
{
  HANDLE Semaphore; // rax

  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)this + 1) = this;
  *((_DWORD *)this + 4) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 36) = 1;
  Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
  *((_QWORD *)this + 11) = Semaphore;
  if ( !Semaphore )
    *a4 = -2147024882;
  return this;
}

```

## disassembly

```asm
0x180003318  mov     [rsp+arg_0], rbx
0x18000331d  mov     [rsp+arg_8], rsi
0x180003322  push    rdi
0x180003323  sub     rsp, 30h
0x180003327  mov     rdi, r9
0x18000332a  mov     rbx, rcx
0x18000332d  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180003334  mov     [rcx+8], rcx
0x180003338  xor     esi, esi
0x18000333a  mov     [rcx+10h], esi
0x18000333d  add     rcx, 20h ; ' '; lpCriticalSection
0x180003341  call    cs:__imp_InitializeCriticalSection
0x180003347  mov     [rbx+48h], rsi
0x18000334b  xor     r9d, r9d; lpName
0x18000334e  mov     [rbx+50h], esi
0x180003351  xor     edx, edx; lInitialCount
0x180003353  xor     ecx, ecx; lpSemaphoreAttributes
0x180003355  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000335d  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180003363  mov     [rbx+58h], rsi
0x180003367  mov     [rbx+60h], rsi
0x18000336b  mov     [rbx+68h], rsi
0x18000336f  mov     [rbx+70h], rsi
0x180003373  mov     [rbx+78h], rsi
0x180003377  mov     [rbx+80h], esi
0x18000337d  mov     [rbx+88h], rsi
0x180003384  mov     dword ptr [rbx+90h], 1
0x18000338e  mov     [rsp+38h+dwFlags], esi; dwFlags
0x180003392  call    cs:__imp_CreateSemaphoreExW
0x180003398  mov     [rbx+58h], rax
0x18000339c  test    rax, rax
0x18000339f  jnz     short loc_1800033A7
0x1800033a1  mov     dword ptr [rdi], 8007000Eh
0x1800033a7  mov     rsi, [rsp+38h+arg_8]
0x1800033ac  mov     rax, rbx
0x1800033af  mov     rbx, [rsp+38h+arg_0]
0x1800033b4  add     rsp, 30h
0x1800033b8  pop     rdi
0x1800033b9  retn
```
