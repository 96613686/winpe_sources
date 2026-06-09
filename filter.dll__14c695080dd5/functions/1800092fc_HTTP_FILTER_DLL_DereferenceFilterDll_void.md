# HTTP_FILTER_DLL::DereferenceFilterDll(void)

- ea: `0x1800092fc`
- end: `0x18000933f`
- name: `?DereferenceFilterDll@HTTP_FILTER_DLL@@QEAAXXZ`
- size: `67`
- prototype: `void __fastcall(HTTP_FILTER_DLL *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006880`
- `0x180006e10`

## callees

- `0x1800092c8`
- `0x1800092fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000930c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000930c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009338`

## pseudocode

```c
void __fastcall HTTP_FILTER_DLL::DereferenceFilterDll(HTTP_FILTER_DLL *this)
{
  unsigned int v2; // edx

  EnterCriticalSection(&HTTP_FILTER_DLL::sm_csFilterDlls);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 17, 0xFFFFFFFF) == 1 && this )
    HTTP_FILTER_DLL::`scalar deleting destructor'(this, v2);
  LeaveCriticalSection(&HTTP_FILTER_DLL::sm_csFilterDlls);
}

```

## disassembly

```asm
0x1800092fc  push    rbx
0x1800092fe  sub     rsp, 20h
0x180009302  mov     rbx, rcx
0x180009305  lea     rcx, ?sm_csFilterDlls@HTTP_FILTER_DLL@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000930c  call    cs:__imp_EnterCriticalSection
0x180009312  or      eax, 0FFFFFFFFh
0x180009315  lock xadd [rbx+44h], eax
0x18000931a  cmp     eax, 1
0x18000931d  jnz     short loc_18000932C
0x18000931f  test    rbx, rbx
0x180009322  jz      short loc_18000932C
0x180009324  mov     rcx, rbx; this
0x180009327  call    ??_GHTTP_FILTER_DLL@@QEAAPEAXI@Z; HTTP_FILTER_DLL::`scalar deleting destructor'(uint)
0x18000932c  lea     rcx, ?sm_csFilterDlls@HTTP_FILTER_DLL@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION HTTP_FILTER_DLL::sm_csFilterDlls
0x180009333  add     rsp, 20h
0x180009337  pop     rbx
0x180009338  jmp     cs:__imp_LeaveCriticalSection
```
