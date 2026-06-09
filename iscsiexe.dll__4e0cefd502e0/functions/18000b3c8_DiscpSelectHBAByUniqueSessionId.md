# DiscpSelectHBAByUniqueSessionId

- ea: `0x18000b3c8`
- end: `0x18000b43d`
- name: `DiscpSelectHBAByUniqueSessionId`
- size: `117`
- prototype: `__int64 __fastcall(void **, volatile signed __int32 **)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800034a0`
- `0x180003da0`
- `0x1800041d0`
- `0x1800045d0`
- `0x180008710`

## callees

- `0x18000b3c8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000b425`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b425`
- `ntdll!RtlEnterCriticalSection` at `0x18000b3e9`
- `ntdll!RtlEnterCriticalSection` at `0x18000b3e9`

## pseudocode

```c
__int64 __fastcall DiscpSelectHBAByUniqueSessionId(void **a1, volatile signed __int32 **a2)
{
  unsigned int v4; // ebx
  volatile signed __int32 *v5; // rax

  v4 = -268500964;
  RtlEnterCriticalSection(&DiscpCritSection);
  v5 = (volatile signed __int32 *)DiscpInitiatorInstanceList;
  if ( DiscpInitiatorInstanceList != (_UNKNOWN *)&DiscpInitiatorInstanceList )
  {
    while ( *((void **)v5 + 3) != *a1 )
    {
      v5 = *(volatile signed __int32 **)v5;
      if ( v5 == (volatile signed __int32 *)&DiscpInitiatorInstanceList )
        goto LABEL_6;
    }
    *a2 = v5;
    _InterlockedIncrement(v5 + 4);
    v4 = 0;
  }
LABEL_6:
  RtlLeaveCriticalSection(&DiscpCritSection);
  return v4;
}

```

## disassembly

```asm
0x18000b3c8  mov     [rsp+arg_0], rbx
0x18000b3cd  mov     [rsp+arg_8], rsi
0x18000b3d2  push    rdi
0x18000b3d3  sub     rsp, 20h
0x18000b3d7  mov     rdi, rcx
0x18000b3da  mov     rsi, rdx
0x18000b3dd  lea     rcx, DiscpCritSection; CriticalSection
0x18000b3e4  mov     ebx, 0EFFF001Ch
0x18000b3e9  call    cs:__imp_RtlEnterCriticalSection
0x18000b3ef  mov     rax, cs:DiscpInitiatorInstanceList
0x18000b3f6  lea     rdx, DiscpInitiatorInstanceList
0x18000b3fd  cmp     rax, rdx
0x18000b400  jz      short loc_18000B41E
0x18000b402  mov     rcx, [rdi]
0x18000b405  cmp     [rax+18h], rcx
0x18000b409  jz      short loc_18000B415
0x18000b40b  mov     rax, [rax]
0x18000b40e  cmp     rax, rdx
0x18000b411  jnz     short loc_18000B405
0x18000b413  jmp     short loc_18000B41E
0x18000b415  mov     [rsi], rax
0x18000b418  lock inc dword ptr [rax+10h]
0x18000b41c  xor     ebx, ebx
0x18000b41e  lea     rcx, DiscpCritSection; CriticalSection
0x18000b425  call    cs:__imp_RtlLeaveCriticalSection
0x18000b42b  mov     rsi, [rsp+28h+arg_8]
0x18000b430  mov     eax, ebx
0x18000b432  mov     rbx, [rsp+28h+arg_0]
0x18000b437  add     rsp, 20h
0x18000b43b  pop     rdi
0x18000b43c  retn
```
