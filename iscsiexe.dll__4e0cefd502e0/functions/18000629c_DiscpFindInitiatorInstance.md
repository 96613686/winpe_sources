# DiscpFindInitiatorInstance

- ea: `0x18000629c`
- end: `0x18000630d`
- name: `DiscpFindInitiatorInstance`
- size: `113`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 **)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003e50`
- `0x180004690`
- `0x180005098`
- `0x180006998`
- `0x180007c44`
- `0x180009898`
- `0x18000b17c`
- `0x18000b2dc`
- `0x18000f388`

## callees

- `0x18000629c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800062d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800062d6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800062fa`
- `ntdll!RtlLeaveCriticalSection` at `0x1800062fa`
- `ntdll!RtlEnterCriticalSection` at `0x1800062b4`
- `ntdll!RtlEnterCriticalSection` at `0x1800062b4`

## pseudocode

```c
__int64 __fastcall DiscpFindInitiatorInstance(__int64 a1, volatile signed __int32 **a2)
{
  volatile signed __int32 *v4; // rbx
  unsigned int v5; // edi

  RtlEnterCriticalSection(&DiscpCritSection);
  v4 = (volatile signed __int32 *)DiscpInitiatorInstanceList;
  v5 = -268500924;
  while ( v4 != (volatile signed __int32 *)&DiscpInitiatorInstanceList )
  {
    if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)v4 + 5), a1) )
    {
      _InterlockedIncrement(v4 + 4);
      *a2 = v4;
      v5 = 0;
      break;
    }
    v4 = *(volatile signed __int32 **)v4;
  }
  RtlLeaveCriticalSection(&DiscpCritSection);
  return v5;
}

```

## disassembly

```asm
0x18000629c  push    rbx
0x18000629e  push    rbp
0x18000629f  push    rsi
0x1800062a0  push    rdi
0x1800062a1  push    r14
0x1800062a3  sub     rsp, 20h
0x1800062a7  mov     rbp, rcx
0x1800062aa  mov     rsi, rdx
0x1800062ad  lea     rcx, DiscpCritSection; CriticalSection
0x1800062b4  call    cs:__imp_RtlEnterCriticalSection
0x1800062ba  mov     rbx, cs:DiscpInitiatorInstanceList
0x1800062c1  lea     r14, DiscpInitiatorInstanceList
0x1800062c8  mov     edi, 0EFFF0044h
0x1800062cd  jmp     short loc_1800062E3
0x1800062cf  mov     rcx, [rbx+28h]
0x1800062d3  mov     rdx, rbp
0x1800062d6  call    cs:__imp__o__wcsicmp
0x1800062dc  test    eax, eax
0x1800062de  jz      short loc_1800062EA
0x1800062e0  mov     rbx, [rbx]
0x1800062e3  cmp     rbx, r14
0x1800062e6  jnz     short loc_1800062CF
0x1800062e8  jmp     short loc_1800062F3
0x1800062ea  lock inc dword ptr [rbx+10h]
0x1800062ee  mov     [rsi], rbx
0x1800062f1  xor     edi, edi
0x1800062f3  lea     rcx, DiscpCritSection; CriticalSection
0x1800062fa  call    cs:__imp_RtlLeaveCriticalSection
0x180006300  mov     eax, edi
0x180006302  add     rsp, 20h
0x180006306  pop     r14
0x180006308  pop     rdi
0x180006309  pop     rsi
0x18000630a  pop     rbp
0x18000630b  pop     rbx
0x18000630c  retn
```
