# SrvRemoveSecretFromList

- ea: `0x180008e98`
- end: `0x180008ef9`
- name: `SrvRemoveSecretFromList`
- size: `97`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008dfc`
- `0x18000ebb0`

## callees

- `0x180008e98`
- `0x180008f00`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180008eaf`
- `ntdll!RtlEnterCriticalSection` at `0x180008eaf`
- `ntdll!RtlLeaveCriticalSection` at `0x180008edf`
- `ntdll!RtlLeaveCriticalSection` at `0x180008edf`

## pseudocode

```c
__int64 __fastcall SrvRemoveSecretFromList(__int64 a1, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v4; // r9
  _QWORD *v5; // r8
  unsigned int v6; // ebx

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 168);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 168));
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(v4 + 8) != a2 + 16 || (v5 = *(_QWORD **)(a2 + 24), *v5 != a2 + 16) )
    __fastfail(3u);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  v6 = SrvDereferenceSecret((volatile signed __int64 *)a2);
  RtlLeaveCriticalSection(v2);
  return v6;
}

```

## disassembly

```asm
0x180008e98  mov     [rsp+arg_0], rbx
0x180008e9d  push    rdi
0x180008e9e  sub     rsp, 20h
0x180008ea2  lea     rdi, [rcx+0A8h]
0x180008ea9  mov     rbx, rdx
0x180008eac  mov     rcx, rdi; CriticalSection
0x180008eaf  call    cs:__imp_RtlEnterCriticalSection
0x180008eb5  lea     rax, [rbx+10h]
0x180008eb9  mov     r9, [rax]
0x180008ebc  cmp     [r9+8], rax
0x180008ec0  jnz     short loc_180008EF2
0x180008ec2  mov     r8, [rax+8]
0x180008ec6  cmp     [r8], rax
0x180008ec9  jnz     short loc_180008EF2
0x180008ecb  mov     [r8], r9
0x180008ece  mov     rcx, rbx
0x180008ed1  mov     [r9+8], r8
0x180008ed5  call    SrvDereferenceSecret
0x180008eda  mov     rcx, rdi; CriticalSection
0x180008edd  mov     ebx, eax
0x180008edf  call    cs:__imp_RtlLeaveCriticalSection
0x180008ee5  mov     eax, ebx
0x180008ee7  mov     rbx, [rsp+28h+arg_0]
0x180008eec  add     rsp, 20h
0x180008ef0  pop     rdi
0x180008ef1  retn
0x180008ef2  mov     ecx, 3
0x180008ef7  int     29h; Win8: RtlFailFast(ecx)
```
