# Concurrency::details::_Reschedule_chore(Concurrency::details::_Threadpool_chore const *)

- ea: `0x1803756a0`
- end: `0x1803756d7`
- name: `?_Reschedule_chore@details@Concurrency@@YAHPEBU_Threadpool_chore@12@@Z`
- size: `55`
- prototype: `__int64 __fastcall(Concurrency::details *__hidden this, const struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1803756d8`

## callees

- `0x18037563c`
- `0x1803756a0`

## import_xrefs

- `KERNEL32!SubmitThreadpoolWork` at `0x1803756c9`
- `KERNEL32!SubmitThreadpoolWork` at `0x1803756c9`
- `KERNEL32!GetModuleHandleExW` at `0x1803756c0`
- `KERNEL32!GetModuleHandleExW` at `0x1803756c0`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Reschedule_chore(
        LPCWSTR *this,
        const struct Concurrency::details::_Threadpool_chore *a2)
{
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  if ( (unsigned int)Concurrency::details::_anonymous_namespace_::_Get_STL_host_status(this, a2) )
    GetModuleHandleExW(4u, this[1], &phModule);
  SubmitThreadpoolWork((PTP_WORK)*this);
  return 0;
}

```

## disassembly

```asm
0x1803756a0  push    rbx
0x1803756a2  sub     rsp, 20h
0x1803756a6  mov     rbx, rcx
0x1803756a9  call    Concurrency__details___anonymous_namespace____Get_STL_host_status
0x1803756ae  test    eax, eax
0x1803756b0  jz      short loc_1803756C6
0x1803756b2  mov     rdx, [rbx+8]; lpModuleName
0x1803756b6  lea     r8, [rsp+28h+phModule]; phModule
0x1803756bb  mov     ecx, 4; dwFlags
0x1803756c0  call    cs:__imp_GetModuleHandleExW
0x1803756c6  mov     rcx, [rbx]; pwk
0x1803756c9  call    cs:__imp_SubmitThreadpoolWork
0x1803756cf  xor     eax, eax
0x1803756d1  add     rsp, 20h
0x1803756d5  pop     rbx
0x1803756d6  retn
```
