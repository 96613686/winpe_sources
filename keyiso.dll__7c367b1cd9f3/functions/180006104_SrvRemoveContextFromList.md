# SrvRemoveContextFromList

- ea: `0x180006104`
- end: `0x18000616b`
- name: `SrvRemoveContextFromList`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006040`
- `0x180013c18`

## callees

- `0x180006104`
- `0x180006280`
- `0x18000a5c0`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180006114`
- `ntdll!RtlEnterCriticalSection` at `0x180006114`
- `ntdll!RtlLeaveCriticalSection` at `0x180006141`
- `ntdll!RtlLeaveCriticalSection` at `0x180006141`

## pseudocode

```c
__int64 __fastcall SrvRemoveContextFromList(__int64 *a1)
{
  __int64 v2; // rax
  __int64 v3; // r8
  _QWORD *v4; // rdx
  __int64 result; // rax

  RtlEnterCriticalSection(&g_ResLock);
  v2 = *a1 + 24;
  v3 = *(_QWORD *)v2;
  if ( *(_QWORD *)(*(_QWORD *)v2 + 8LL) != v2 || (v4 = *(_QWORD **)(*a1 + 32), *v4 != v2) )
    __fastfail(3u);
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  RtlLeaveCriticalSection(&g_ResLock);
  SrvRundownContext(*a1);
  result = MSCryptFree(*a1);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180006104  push    rbx
0x180006106  sub     rsp, 20h
0x18000610a  mov     rbx, rcx
0x18000610d  lea     rcx, g_ResLock; CriticalSection
0x180006114  call    cs:__imp_RtlEnterCriticalSection
0x18000611a  mov     rax, [rbx]
0x18000611d  add     rax, 18h
0x180006121  mov     r8, [rax]
0x180006124  cmp     [r8+8], rax
0x180006128  jnz     short loc_180006164
0x18000612a  mov     rdx, [rax+8]
0x18000612e  cmp     [rdx], rax
0x180006131  jnz     short loc_180006164
0x180006133  mov     [rdx], r8
0x180006136  lea     rcx, g_ResLock; CriticalSection
0x18000613d  mov     [r8+8], rdx
0x180006141  call    cs:__imp_RtlLeaveCriticalSection
0x180006147  mov     rcx, [rbx]
0x18000614a  call    SrvRundownContext
0x18000614f  mov     rcx, [rbx]
0x180006152  call    MSCryptFree
0x180006157  mov     qword ptr [rbx], 0
0x18000615e  add     rsp, 20h
0x180006162  pop     rbx
0x180006163  retn
0x180006164  mov     ecx, 3
0x180006169  int     29h; Win8: RtlFailFast(ecx)
```
