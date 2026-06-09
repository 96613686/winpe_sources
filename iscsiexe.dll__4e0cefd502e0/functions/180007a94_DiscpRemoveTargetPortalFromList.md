# DiscpRemoveTargetPortalFromList

- ea: `0x180007a94`
- end: `0x180007b19`
- name: `DiscpRemoveTargetPortalFromList`
- size: `133`
- prototype: `NTSTATUS __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800068cc`
- `0x180007b20`

## callees

- `0x180006870`
- `0x180007a94`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180007af9`
- `ntdll!RtlLeaveCriticalSection` at `0x180007af9`
- `ntdll!RtlLeaveCriticalSection` at `0x180007b0b`
- `ntdll!RtlEnterCriticalSection` at `0x180007aa4`
- `ntdll!RtlEnterCriticalSection` at `0x180007ad2`
- `ntdll!RtlEnterCriticalSection` at `0x180007aa4`
- `ntdll!RtlEnterCriticalSection` at `0x180007ad2`

## pseudocode

```c
NTSTATUS __fastcall DiscpRemoveTargetPortalFromList(__int64 *a1)
{
  __int64 *v2; // rcx
  __int64 **v3; // rax

  RtlEnterCriticalSection(&DiscpCritSection);
  v2 = (__int64 *)*a1;
  if ( *(__int64 **)(*a1 + 8) != a1 || (v3 = (__int64 **)a1[1], *v3 != a1) )
    __fastfail(3u);
  *v3 = v2;
  v2[1] = (__int64)v3;
  *((_DWORD *)a1 + 5) &= ~1u;
  *((_DWORD *)a1 + 5) |= 2u;
  RtlEnterCriticalSection(&DiscpCritSection);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1[5] + 16), 0xFFFFFFFF) == 1 )
    DiscpFreeTargetAddress((__int64 *)a1[5]);
  RtlLeaveCriticalSection(&DiscpCritSection);
  return RtlLeaveCriticalSection(&DiscpCritSection);
}

```

## disassembly

```asm
0x180007a94  push    rbx
0x180007a96  sub     rsp, 20h
0x180007a9a  mov     rbx, rcx
0x180007a9d  lea     rcx, DiscpCritSection; CriticalSection
0x180007aa4  call    cs:__imp_RtlEnterCriticalSection
0x180007aaa  mov     rcx, [rbx]
0x180007aad  cmp     [rcx+8], rbx
0x180007ab1  jnz     short loc_180007B12
0x180007ab3  mov     rax, [rbx+8]
0x180007ab7  cmp     [rax], rbx
0x180007aba  jnz     short loc_180007B12
0x180007abc  mov     [rax], rcx
0x180007abf  mov     [rcx+8], rax
0x180007ac3  lea     rcx, DiscpCritSection; CriticalSection
0x180007aca  and     dword ptr [rbx+14h], 0FFFFFFFEh
0x180007ace  or      dword ptr [rbx+14h], 2
0x180007ad2  call    cs:__imp_RtlEnterCriticalSection
0x180007ad8  mov     rdx, [rbx+28h]
0x180007adc  or      eax, 0FFFFFFFFh
0x180007adf  lock xadd [rdx+10h], eax
0x180007ae4  cmp     eax, 1
0x180007ae7  jnz     short loc_180007AF2
0x180007ae9  mov     rcx, [rbx+28h]
0x180007aed  call    DiscpFreeTargetAddress
0x180007af2  lea     rcx, DiscpCritSection; CriticalSection
0x180007af9  call    cs:__imp_RtlLeaveCriticalSection
0x180007aff  lea     rcx, DiscpCritSection
0x180007b06  add     rsp, 20h
0x180007b0a  pop     rbx
0x180007b0b  jmp     cs:__imp_RtlLeaveCriticalSection
0x180007b12  mov     ecx, 3
0x180007b17  int     29h; Win8: RtlFailFast(ecx)
```
