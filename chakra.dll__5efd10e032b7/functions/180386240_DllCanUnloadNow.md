# DllCanUnloadNow

- ea: `0x180386240`
- end: `0x180386314`
- name: `DllCanUnloadNow`
- size: `212`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180386240`
- `0x18053e484`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803862ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803862de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803862f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180386302`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803862ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803862de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803862f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180386302`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180386293`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1803862af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180386293`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1803862af`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18038625b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18038625b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
  {
    if ( !dword_180740AE0 )
    {
      EnterCriticalSection(&stru_18073EC08);
      EnterCriticalSection(&ThreadContext::s_csThreadContext);
      if ( !dword_180740AE0 )
      {
        ThreadBoundThreadContextManager::DestroyAllContexts();
        LeaveCriticalSection(&ThreadContext::s_csThreadContext);
        LeaveCriticalSection(&stru_18073EC08);
        return 0;
      }
      LeaveCriticalSection(&ThreadContext::s_csThreadContext);
      LeaveCriticalSection(&stru_18073EC08);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180386240  push    rdi
0x180386242  sub     rsp, 40h
0x180386246  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18038624f  mov     [rsp+48h+arg_0], rbx
0x180386254  lea     rcx, gPFactory; pPSFactoryBuffer
0x18038625b  call    cs:__imp_NdrDllCanUnloadNow
0x180386262  nop     dword ptr [rax+rax+00h]
0x180386267  test    eax, eax
0x180386269  jnz     short loc_180386278
0x18038626b  cmp     cs:dword_180740AE0, eax
0x180386271  jz      short loc_180386284
0x180386273  mov     eax, 1
0x180386278  mov     rbx, [rsp+48h+arg_0]
0x18038627d  add     rsp, 40h
0x180386281  pop     rdi
0x180386282  retn
0x180386284  lea     rbx, stru_18073EC08
0x18038628b  mov     [rsp+48h+var_20], rbx
0x180386290  mov     rcx, rbx; lpCriticalSection
0x180386293  call    cs:__imp_EnterCriticalSection
0x18038629a  nop     dword ptr [rax+rax+00h]
0x18038629f  nop
0x1803862a0  lea     rdi, ?s_csThreadContext@ThreadContext@@0VCriticalSection@@A; CriticalSection ThreadContext::s_csThreadContext
0x1803862a7  mov     [rsp+48h+var_18], rdi
0x1803862ac  mov     rcx, rdi; lpCriticalSection
0x1803862af  call    cs:__imp_EnterCriticalSection
0x1803862b6  nop     dword ptr [rax+rax+00h]
0x1803862bb  nop
0x1803862bc  cmp     cs:dword_180740AE0, 0
0x1803862c3  jnz     short loc_1803862EF
0x1803862c5  call    ?DestroyAllContexts@ThreadBoundThreadContextManager@@SAXXZ; ThreadBoundThreadContextManager::DestroyAllContexts(void)
0x1803862ca  nop
0x1803862cb  mov     rcx, rdi; lpCriticalSection
0x1803862ce  call    cs:__imp_LeaveCriticalSection
0x1803862d5  nop     dword ptr [rax+rax+00h]
0x1803862da  nop
0x1803862db  mov     rcx, rbx; lpCriticalSection
0x1803862de  call    cs:__imp_LeaveCriticalSection
0x1803862e5  nop     dword ptr [rax+rax+00h]
0x1803862ea  nop
0x1803862eb  xor     eax, eax
0x1803862ed  jmp     short loc_180386278
0x1803862ef  mov     rcx, rdi; lpCriticalSection
0x1803862f2  call    cs:__imp_LeaveCriticalSection
0x1803862f9  nop     dword ptr [rax+rax+00h]
0x1803862fe  nop
0x1803862ff  mov     rcx, rbx; lpCriticalSection
0x180386302  call    cs:__imp_LeaveCriticalSection
0x180386309  nop     dword ptr [rax+rax+00h]
0x18038630e  nop
0x18038630f  jmp     loc_180386273
```
