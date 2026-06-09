# SrvRemoveKeyFromList

- ea: `0x180007140`
- end: `0x1800071d5`
- name: `SrvRemoveKeyFromList`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007088`
- `0x180009ca0`

## callees

- `0x180003cf0`
- `0x180007140`
- `0x18000a520`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180007154`
- `ntdll!RtlEnterCriticalSection` at `0x180007154`
- `ntdll!RtlLeaveCriticalSection` at `0x180007190`
- `ntdll!RtlLeaveCriticalSection` at `0x180007190`

## string_xrefs

- `0x1800071b7`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
__int64 __fastcall SrvRemoveKeyFromList(__int64 a1, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v4; // rdx
  _QWORD *v5; // rax
  unsigned int v6; // ebx
  int v8; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 104);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(v4 + 8) != a2 + 16 || (v5 = *(_QWORD **)(a2 + 24), *v5 != a2 + 16) )
    __fastfail(3u);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(a2 + 8), 0xFFFFFFFFFFFFFFFFuLL) == 1
    && (v8 = SrvFreeKey((PVOID)a2), v6 = v8, v8 < 0) )
  {
    DebugTraceError(
      (unsigned int)v8,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
      740);
  }
  else
  {
    v6 = 0;
  }
  RtlLeaveCriticalSection(v2);
  return v6;
}

```

## disassembly

```asm
0x180007140  mov     [rsp+arg_8], rbx
0x180007145  push    rdi
0x180007146  sub     rsp, 20h
0x18000714a  lea     rdi, [rcx+68h]
0x18000714e  mov     rbx, rdx
0x180007151  mov     rcx, rdi; CriticalSection
0x180007154  call    cs:__imp_RtlEnterCriticalSection
0x18000715a  mov     rdx, [rbx+10h]
0x18000715e  lea     rcx, [rbx+10h]
0x180007162  cmp     [rdx+8], rcx
0x180007166  jnz     short loc_1800071CE
0x180007168  mov     rax, [rcx+8]
0x18000716c  cmp     [rax], rcx
0x18000716f  jnz     short loc_1800071CE
0x180007171  mov     [rax], rdx
0x180007174  mov     [rdx+8], rax
0x180007178  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000717f  lock xadd [rbx+8], rax
0x180007185  cmp     rax, 1
0x180007189  jz      short loc_1800071A3
0x18000718b  xor     ebx, ebx
0x18000718d  mov     rcx, rdi; CriticalSection
0x180007190  call    cs:__imp_RtlLeaveCriticalSection
0x180007196  mov     eax, ebx
0x180007198  mov     rbx, [rsp+28h+arg_8]
0x18000719d  add     rsp, 20h
0x1800071a1  pop     rdi
0x1800071a2  retn
0x1800071a3  mov     rcx, rbx; P
0x1800071a6  call    SrvFreeKey
0x1800071ab  mov     ebx, eax
0x1800071ad  test    eax, eax
0x1800071af  jns     short loc_18000718B
0x1800071b1  mov     r9d, 2E4h
0x1800071b7  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800071be  lea     rdx, aStatus; "Status"
0x1800071c5  mov     ecx, eax
0x1800071c7  call    DebugTraceError
0x1800071cc  jmp     short loc_18000718D
0x1800071ce  mov     ecx, 3
0x1800071d3  int     29h; Win8: RtlFailFast(ecx)
```
