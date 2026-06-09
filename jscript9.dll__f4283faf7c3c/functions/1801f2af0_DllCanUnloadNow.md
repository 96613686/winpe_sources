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
  __int64 v1; // rcx

  result = NdrDllCanUnloadNow(&pPSFactoryBuffer);
  if ( !result )
  {
    if ( !(dword_180439E98 + dword_18043D818) )
    {
      EnterCriticalSection(&stru_18043CCD0);
      EnterCriticalSection(&CriticalSection);
      if ( !(dword_180439E98 + dword_18043D818) )
      {
        sub_1801B7960(v1, (unsigned int)(dword_180439E98 + dword_18043D818));
        LeaveCriticalSection(&CriticalSection);
        LeaveCriticalSection(&stru_18043CCD0);
        return 0;
      }
      LeaveCriticalSection(&CriticalSection);
      LeaveCriticalSection(&stru_18043CCD0);
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
0x1801f2b04  lea     rcx, pPSFactoryBuffer; pPSFactoryBuffer
0x1801f2b0b  call    cs:NdrDllCanUnloadNow
0x1801f2b11  test    eax, eax
0x1801f2b13  jnz     short loc_1801F2B94
0x1801f2b15  mov     ecx, cs:dword_18043D818
0x1801f2b1b  add     ecx, cs:dword_180439E98
0x1801f2b21  jnz     short loc_1801F2B8F
0x1801f2b23  lea     rbx, stru_18043CCD0
0x1801f2b2a  mov     [rsp+48h+var_20], rbx
0x1801f2b2f  mov     rcx, rbx; lpCriticalSection
0x1801f2b32  call    cs:EnterCriticalSection
0x1801f2b38  nop
0x1801f2b39  lea     rdi, CriticalSection
0x1801f2b40  mov     [rsp+48h+var_18], rdi
0x1801f2b45  mov     rcx, rdi; lpCriticalSection
0x1801f2b48  call    cs:EnterCriticalSection
0x1801f2b4e  nop
0x1801f2b4f  mov     edx, cs:dword_18043D818
0x1801f2b55  add     edx, cs:dword_180439E98
0x1801f2b5b  jnz     short loc_1801F2B7B
0x1801f2b5d  call    sub_1801B7960
0x1801f2b62  nop
0x1801f2b63  mov     rcx, rdi; lpCriticalSection
0x1801f2b66  call    cs:LeaveCriticalSection
0x1801f2b6c  nop
0x1801f2b6d  mov     rcx, rbx; lpCriticalSection
0x1801f2b70  call    cs:LeaveCriticalSection
0x1801f2b76  nop
0x1801f2b77  xor     eax, eax
0x1801f2b79  jmp     short loc_1801F2B94
0x1801f2b7b  mov     rcx, rdi; lpCriticalSection
0x1801f2b7e  call    cs:LeaveCriticalSection
0x1801f2b84  nop
0x1801f2b85  mov     rcx, rbx; lpCriticalSection
0x1801f2b88  call    cs:LeaveCriticalSection
0x1801f2b8e  nop
0x1801f2b8f  mov     eax, 1
0x1801f2b94  mov     rbx, [rsp+48h+arg_0]
0x1801f2b99  add     rsp, 40h
0x1801f2b9d  pop     rdi
0x1801f2b9e  retn
```
