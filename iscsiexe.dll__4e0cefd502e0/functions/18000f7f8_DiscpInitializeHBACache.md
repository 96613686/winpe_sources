# DiscpInitializeHBACache

- ea: `0x18000f7f8`
- end: `0x18000f8df`
- name: `DiscpInitializeHBACache`
- size: `231`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180005720`

## callees

- `0x180008960`
- `0x180009c74`
- `0x18000f5b0`
- `0x18000f7f8`
- `0x18000f8e8`
- `0x18000ff88`
- `0x180010404`
- `0x18001d38c`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x18000f874`
- `ISCSIUM!DiscpAllocMemory` at `0x18000f874`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f851`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f8bf`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f851`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f8bf`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f8a8`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f8ce`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f8a8`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f8ce`
- `ntdll!RtlEnterCriticalSection` at `0x18000f85e`
- `ntdll!RtlEnterCriticalSection` at `0x18000f85e`

## pseudocode

```c
__int64 __fastcall DiscpInitializeHBACache(__int64 a1)
{
  unsigned int v2; // ebp
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // edi
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  __int64 v9; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v9 = 0;
  DiscpSetGroupKeyForInitiator(0, a1);
  v3 = DiscpInitializeTunnelCaches(a1);
  if ( v3 )
    v2 = v3;
  v4 = DiscpInitializeAuthCaches(a1);
  if ( v4 )
    v2 = v4;
  if ( !(unsigned int)DiscpGetDefaultiScsiName((__int64)&v9) )
  {
    DiscpChangeiqnNameForHBA(a1, 0, v9);
    DiscpFreeMemory(v9);
  }
  RtlEnterCriticalSection(&DiscpCritSection);
  v5 = DiscpInitiatorSharedSecretLength + 4;
  if ( (unsigned int)DiscpInitiatorSharedSecretLength < 0xFFFFFFFC
    && (v6 = (_DWORD *)DiscpAllocMemory(v5), (v7 = v6) != 0) )
  {
    *v6 = DiscpInitiatorSharedSecretLength;
    memcpy_0(v6 + 1, DiscpInitiatorSharedSecret, (unsigned int)DiscpInitiatorSharedSecretLength);
    RtlLeaveCriticalSection(&DiscpCritSection);
    DiscpSetInitiatorSharedSecretForAdapter(a1, v7, v5);
    DiscpFreeMemory(v7);
  }
  else
  {
    RtlLeaveCriticalSection(&DiscpCritSection);
  }
  return v2;
}

```

## disassembly

```asm
0x18000f7f8  push    rbx
0x18000f7fa  push    rbp
0x18000f7fb  push    rsi
0x18000f7fc  push    rdi
0x18000f7fd  sub     rsp, 28h
0x18000f801  mov     rsi, rcx
0x18000f804  mov     rdx, rcx
0x18000f807  xor     ebp, ebp
0x18000f809  xor     ecx, ecx
0x18000f80b  mov     [rsp+48h+arg_8], rbp
0x18000f810  call    DiscpSetGroupKeyForInitiator
0x18000f815  mov     rcx, rsi
0x18000f818  call    DiscpInitializeTunnelCaches
0x18000f81d  test    eax, eax
0x18000f81f  mov     rcx, rsi
0x18000f822  cmovnz  ebp, eax
0x18000f825  call    DiscpInitializeAuthCaches
0x18000f82a  test    eax, eax
0x18000f82c  lea     rcx, [rsp+48h+arg_8]
0x18000f831  cmovnz  ebp, eax
0x18000f834  call    DiscpGetDefaultiScsiName
0x18000f839  test    eax, eax
0x18000f83b  jnz     short loc_18000F857
0x18000f83d  mov     r8, [rsp+48h+arg_8]
0x18000f842  xor     edx, edx
0x18000f844  mov     rcx, rsi
0x18000f847  call    DiscpChangeiqnNameForHBA
0x18000f84c  mov     rcx, [rsp+48h+arg_8]
0x18000f851  call    cs:__imp_DiscpFreeMemory
0x18000f857  lea     rcx, DiscpCritSection; CriticalSection
0x18000f85e  call    cs:__imp_RtlEnterCriticalSection
0x18000f864  mov     edi, cs:DiscpInitiatorSharedSecretLength
0x18000f86a  add     edi, 4
0x18000f86d  cmp     edi, 4
0x18000f870  jb      short loc_18000F8C7
0x18000f872  mov     ecx, edi
0x18000f874  call    cs:__imp_DiscpAllocMemory
0x18000f87a  mov     rbx, rax
0x18000f87d  test    rax, rax
0x18000f880  jz      short loc_18000F8C7
0x18000f882  mov     edx, cs:DiscpInitiatorSharedSecretLength
0x18000f888  lea     rcx, [rax+4]; void *
0x18000f88c  mov     [rax], edx
0x18000f88e  mov     r8d, cs:DiscpInitiatorSharedSecretLength; Size
0x18000f895  mov     rdx, cs:DiscpInitiatorSharedSecret; Src
0x18000f89c  call    memcpy_0
0x18000f8a1  lea     rcx, DiscpCritSection; CriticalSection
0x18000f8a8  call    cs:__imp_RtlLeaveCriticalSection
0x18000f8ae  mov     r8d, edi
0x18000f8b1  mov     rdx, rbx
0x18000f8b4  mov     rcx, rsi
0x18000f8b7  call    DiscpSetInitiatorSharedSecretForAdapter
0x18000f8bc  mov     rcx, rbx
0x18000f8bf  call    cs:__imp_DiscpFreeMemory
0x18000f8c5  jmp     short loc_18000F8D4
0x18000f8c7  lea     rcx, DiscpCritSection; CriticalSection
0x18000f8ce  call    cs:__imp_RtlLeaveCriticalSection
0x18000f8d4  mov     eax, ebp
0x18000f8d6  add     rsp, 28h
0x18000f8da  pop     rdi
0x18000f8db  pop     rsi
0x18000f8dc  pop     rbp
0x18000f8dd  pop     rbx
0x18000f8de  retn
```
