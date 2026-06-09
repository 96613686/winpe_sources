# SrvRemoveProviderFromList

- ea: `0x180003540`
- end: `0x1800035ba`
- name: `SrvRemoveProviderFromList`
- size: `122`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002630`
- `0x180009e90`

## callees

- `0x180003540`
- `0x180005540`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180003554`
- `ntdll!RtlEnterCriticalSection` at `0x180003554`
- `ntdll!RtlLeaveCriticalSection` at `0x180003590`
- `ntdll!RtlLeaveCriticalSection` at `0x180003590`

## pseudocode

```c
__int64 __fastcall SrvRemoveProviderFromList(struct _RTL_CRITICAL_SECTION *a1, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v4; // rdx
  _QWORD *v5; // rax
  int v6; // ebx

  v2 = a1 + 1;
  RtlEnterCriticalSection(a1 + 1);
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(v4 + 8) != a2 + 16 || (v5 = *(_QWORD **)(a2 + 24), *v5 != a2 + 16) )
    __fastfail(3u);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(a2 + 8), 0xFFFFFFFFFFFFFFFFuLL) != 1
    || (v6 = SrvFreeProvider((char *)a2), v6 >= 0) )
  {
    v6 = 0;
  }
  RtlLeaveCriticalSection(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003540  mov     [rsp+arg_8], rbx
0x180003545  push    rdi
0x180003546  sub     rsp, 20h
0x18000354a  lea     rdi, [rcx+28h]
0x18000354e  mov     rbx, rdx
0x180003551  mov     rcx, rdi; CriticalSection
0x180003554  call    cs:__imp_RtlEnterCriticalSection
0x18000355a  mov     rdx, [rbx+10h]
0x18000355e  lea     rcx, [rbx+10h]
0x180003562  cmp     [rdx+8], rcx
0x180003566  jnz     short loc_1800035B3
0x180003568  mov     rax, [rcx+8]
0x18000356c  cmp     [rax], rcx
0x18000356f  jnz     short loc_1800035B3
0x180003571  mov     [rax], rdx
0x180003574  mov     [rdx+8], rax
0x180003578  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000357f  lock xadd [rbx+8], rax
0x180003585  cmp     rax, 1
0x180003589  jz      short loc_1800035A3
0x18000358b  xor     ebx, ebx
0x18000358d  mov     rcx, rdi; CriticalSection
0x180003590  call    cs:__imp_RtlLeaveCriticalSection
0x180003596  mov     eax, ebx
0x180003598  mov     rbx, [rsp+28h+arg_8]
0x18000359d  add     rsp, 20h
0x1800035a1  pop     rdi
0x1800035a2  retn
0x1800035a3  mov     rcx, rbx; P
0x1800035a6  call    SrvFreeProvider
0x1800035ab  mov     ebx, eax
0x1800035ad  test    eax, eax
0x1800035af  js      short loc_18000358D
0x1800035b1  jmp     short loc_18000358B
0x1800035b3  mov     ecx, 3
0x1800035b8  int     29h; Win8: RtlFailFast(ecx)
```
