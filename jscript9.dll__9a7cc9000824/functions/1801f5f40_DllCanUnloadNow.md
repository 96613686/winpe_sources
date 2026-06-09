# DllCanUnloadNow

- ea: `0x1801f5f40`
- end: `0x1801f6022`
- name: `DllCanUnloadNow`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1801ba0b8`
- `0x1801f5f40`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1801f5f90`
- `KERNEL32!EnterCriticalSection` at `0x1801f5fac`
- `KERNEL32!EnterCriticalSection` at `0x1801f5f90`
- `KERNEL32!EnterCriticalSection` at `0x1801f5fac`
- `KERNEL32!LeaveCriticalSection` at `0x1801f5fd0`
- `KERNEL32!LeaveCriticalSection` at `0x1801f5fe0`
- `KERNEL32!LeaveCriticalSection` at `0x1801f5ff4`
- `KERNEL32!LeaveCriticalSection` at `0x1801f6004`
- `KERNEL32!LeaveCriticalSection` at `0x1801f5fd0`
- `KERNEL32!LeaveCriticalSection` at `0x1801f5fe0`
- `KERNEL32!LeaveCriticalSection` at `0x1801f5ff4`
- `KERNEL32!LeaveCriticalSection` at `0x1801f6004`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1801f5f5b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1801f5f5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
  {
    if ( !(g_cLibLocks + dword_180443818) )
    {
      EnterCriticalSection(&CriticalSection);
      EnterCriticalSection(&ThreadContext::s_csThreadContext);
      if ( !(g_cLibLocks + dword_180443818) )
      {
        ThreadBoundThreadContextManager::DestroyAllContexts();
        LeaveCriticalSection(&ThreadContext::s_csThreadContext);
        LeaveCriticalSection(&CriticalSection);
        return 0;
      }
      LeaveCriticalSection(&ThreadContext::s_csThreadContext);
      LeaveCriticalSection(&CriticalSection);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1801f5f40  push    rdi
0x1801f5f42  sub     rsp, 40h
0x1801f5f46  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1801f5f4f  mov     [rsp+48h+arg_0], rbx
0x1801f5f54  lea     rcx, gPFactory; pPSFactoryBuffer
0x1801f5f5b  call    cs:__imp_NdrDllCanUnloadNow
0x1801f5f62  nop     dword ptr [rax+rax+00h]
0x1801f5f67  test    eax, eax
0x1801f5f69  jnz     loc_1801F6016
0x1801f5f6f  mov     ecx, cs:dword_180443818
0x1801f5f75  add     ecx, cs:?g_cLibLocks@@3JA; long g_cLibLocks
0x1801f5f7b  jnz     loc_1801F6011
0x1801f5f81  lea     rbx, CriticalSection
0x1801f5f88  mov     [rsp+48h+var_20], rbx
0x1801f5f8d  mov     rcx, rbx; lpCriticalSection
0x1801f5f90  call    cs:__imp_EnterCriticalSection
0x1801f5f97  nop     dword ptr [rax+rax+00h]
0x1801f5f9c  nop
0x1801f5f9d  lea     rdi, ?s_csThreadContext@ThreadContext@@0VCriticalSection@@A; CriticalSection ThreadContext::s_csThreadContext
0x1801f5fa4  mov     [rsp+48h+var_18], rdi
0x1801f5fa9  mov     rcx, rdi; lpCriticalSection
0x1801f5fac  call    cs:__imp_EnterCriticalSection
0x1801f5fb3  nop     dword ptr [rax+rax+00h]
0x1801f5fb8  nop
0x1801f5fb9  mov     edx, cs:dword_180443818
0x1801f5fbf  add     edx, cs:?g_cLibLocks@@3JA; long g_cLibLocks
0x1801f5fc5  jnz     short loc_1801F5FF1
0x1801f5fc7  call    ?DestroyAllContexts@ThreadBoundThreadContextManager@@SAXXZ; ThreadBoundThreadContextManager::DestroyAllContexts(void)
0x1801f5fcc  nop
0x1801f5fcd  mov     rcx, rdi; lpCriticalSection
0x1801f5fd0  call    cs:__imp_LeaveCriticalSection
0x1801f5fd7  nop     dword ptr [rax+rax+00h]
0x1801f5fdc  nop
0x1801f5fdd  mov     rcx, rbx; lpCriticalSection
0x1801f5fe0  call    cs:__imp_LeaveCriticalSection
0x1801f5fe7  nop     dword ptr [rax+rax+00h]
0x1801f5fec  nop
0x1801f5fed  xor     eax, eax
0x1801f5fef  jmp     short loc_1801F6016
0x1801f5ff1  mov     rcx, rdi; lpCriticalSection
0x1801f5ff4  call    cs:__imp_LeaveCriticalSection
0x1801f5ffb  nop     dword ptr [rax+rax+00h]
0x1801f6000  nop
0x1801f6001  mov     rcx, rbx; lpCriticalSection
0x1801f6004  call    cs:__imp_LeaveCriticalSection
0x1801f600b  nop     dword ptr [rax+rax+00h]
0x1801f6010  nop
0x1801f6011  mov     eax, 1
0x1801f6016  mov     rbx, [rsp+48h+arg_0]
0x1801f601b  add     rsp, 40h
0x1801f601f  pop     rdi
0x1801f6020  retn
```
