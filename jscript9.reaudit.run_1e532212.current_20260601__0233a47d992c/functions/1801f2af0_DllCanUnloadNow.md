# DllCanUnloadNow

- ea: `0x1801f2af0`
- end: `0x1801f2b9f`
- name: `DllCanUnloadNow`
- size: `175`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1801b7960`
- `0x1801f2af0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1801f2b32`
- `KERNEL32!EnterCriticalSection` at `0x1801f2b48`
- `KERNEL32!EnterCriticalSection` at `0x1801f2b32`
- `KERNEL32!EnterCriticalSection` at `0x1801f2b48`
- `KERNEL32!LeaveCriticalSection` at `0x1801f2b66`
- `KERNEL32!LeaveCriticalSection` at `0x1801f2b70`
- `KERNEL32!LeaveCriticalSection` at `0x1801f2b7e`
- `KERNEL32!LeaveCriticalSection` at `0x1801f2b88`
- `KERNEL32!LeaveCriticalSection` at `0x1801f2b66`
- `KERNEL32!LeaveCriticalSection` at `0x1801f2b70`
- `KERNEL32!LeaveCriticalSection` at `0x1801f2b7e`
- `KERNEL32!LeaveCriticalSection` at `0x1801f2b88`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1801f2b0b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1801f2b0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
  {
    if ( !(g_cLibLocks + dword_18043D818) )
    {
      EnterCriticalSection(&CriticalSection);
      EnterCriticalSection(&ThreadContext::s_csThreadContext);
      if ( !(g_cLibLocks + dword_18043D818) )
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
0x1801f2af0  push    rdi
0x1801f2af2  sub     rsp, 40h
0x1801f2af6  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1801f2aff  mov     [rsp+48h+arg_0], rbx
0x1801f2b04  lea     rcx, gPFactory; pPSFactoryBuffer
0x1801f2b0b  call    cs:__imp_NdrDllCanUnloadNow
0x1801f2b11  test    eax, eax
0x1801f2b13  jnz     short loc_1801F2B94
0x1801f2b15  mov     ecx, cs:dword_18043D818
0x1801f2b1b  add     ecx, cs:?g_cLibLocks@@3JA; long g_cLibLocks
0x1801f2b21  jnz     short loc_1801F2B8F
0x1801f2b23  lea     rbx, CriticalSection
0x1801f2b2a  mov     [rsp+48h+var_20], rbx
0x1801f2b2f  mov     rcx, rbx; lpCriticalSection
0x1801f2b32  call    cs:__imp_EnterCriticalSection
0x1801f2b38  nop
0x1801f2b39  lea     rdi, ?s_csThreadContext@ThreadContext@@0VCriticalSection@@A; CriticalSection ThreadContext::s_csThreadContext
0x1801f2b40  mov     [rsp+48h+var_18], rdi
0x1801f2b45  mov     rcx, rdi; lpCriticalSection
0x1801f2b48  call    cs:__imp_EnterCriticalSection
0x1801f2b4e  nop
0x1801f2b4f  mov     edx, cs:dword_18043D818
0x1801f2b55  add     edx, cs:?g_cLibLocks@@3JA; long g_cLibLocks
0x1801f2b5b  jnz     short loc_1801F2B7B
0x1801f2b5d  call    ?DestroyAllContexts@ThreadBoundThreadContextManager@@SAXXZ; ThreadBoundThreadContextManager::DestroyAllContexts(void)
0x1801f2b62  nop
0x1801f2b63  mov     rcx, rdi; lpCriticalSection
0x1801f2b66  call    cs:__imp_LeaveCriticalSection
0x1801f2b6c  nop
0x1801f2b6d  mov     rcx, rbx; lpCriticalSection
0x1801f2b70  call    cs:__imp_LeaveCriticalSection
0x1801f2b76  nop
0x1801f2b77  xor     eax, eax
0x1801f2b79  jmp     short loc_1801F2B94
0x1801f2b7b  mov     rcx, rdi; lpCriticalSection
0x1801f2b7e  call    cs:__imp_LeaveCriticalSection
0x1801f2b84  nop
0x1801f2b85  mov     rcx, rbx; lpCriticalSection
0x1801f2b88  call    cs:__imp_LeaveCriticalSection
0x1801f2b8e  nop
0x1801f2b8f  mov     eax, 1
0x1801f2b94  mov     rbx, [rsp+48h+arg_0]
0x1801f2b99  add     rsp, 40h
0x1801f2b9d  pop     rdi
0x1801f2b9e  retn
```
