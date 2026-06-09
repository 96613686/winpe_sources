# DiscpGetInitiatorInstanceList

- ea: `0x180006998`
- end: `0x180006a7e`
- name: `DiscpGetInitiatorInstanceList`
- size: `230`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004af8`
- `0x180004cf8`
- `0x180009898`
- `0x18000b720`
- `0x18000ba10`
- `0x18000f4a8`
- `0x18001026c`
- `0x180010960`

## callees

- `0x18000629c`
- `0x180006998`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x1800069c6`
- `ISCSIUM!DiscpAllocMemory` at `0x180006a16`
- `ISCSIUM!DiscpAllocMemory` at `0x1800069c6`
- `ISCSIUM!DiscpAllocMemory` at `0x180006a16`
- `ISCSIUM!DiscpFreeMemory` at `0x1800069f8`
- `ISCSIUM!DiscpFreeMemory` at `0x1800069f8`
- `ntdll!RtlLeaveCriticalSection` at `0x180006a63`
- `ntdll!RtlLeaveCriticalSection` at `0x180006a63`
- `ntdll!RtlEnterCriticalSection` at `0x180006a07`
- `ntdll!RtlEnterCriticalSection` at `0x180006a07`

## pseudocode

```c
__int64 __fastcall DiscpGetInitiatorInstanceList(__int64 a1, _DWORD *a2, __int64 *a3)
{
  unsigned int InitiatorInstance; // ebx
  volatile signed __int32 **v7; // rax
  volatile signed __int32 **v8; // rdi
  __int64 v9; // rax
  volatile signed __int32 *v10; // rcx
  __int64 i; // rdx

  if ( DiscpInitiatorInstanceCount )
  {
    if ( a1 )
    {
      InitiatorInstance = 8;
      v7 = (volatile signed __int32 **)DiscpAllocMemory(8);
      v8 = v7;
      if ( v7 )
      {
        InitiatorInstance = DiscpFindInitiatorInstance(a1, v7);
        if ( InitiatorInstance )
        {
          DiscpFreeMemory(v8);
        }
        else
        {
          *a2 = 1;
          *a3 = (__int64)v8;
        }
      }
    }
    else
    {
      RtlEnterCriticalSection(&DiscpCritSection);
      v9 = DiscpAllocMemory((unsigned int)(8 * DiscpInitiatorInstanceCount));
      if ( v9 )
      {
        v10 = (volatile signed __int32 *)DiscpInitiatorInstanceList;
        for ( i = 0;
              v10 != (volatile signed __int32 *)&DiscpInitiatorInstanceList
           && (unsigned int)i < DiscpInitiatorInstanceCount;
              i = (unsigned int)(i + 1) )
        {
          *(_QWORD *)(v9 + 8 * i) = v10;
          _InterlockedIncrement(v10 + 4);
          v10 = *(volatile signed __int32 **)v10;
        }
        *a2 = i;
        InitiatorInstance = 0;
        *a3 = v9;
      }
      else
      {
        InitiatorInstance = 8;
      }
      RtlLeaveCriticalSection(&DiscpCritSection);
    }
  }
  else
  {
    return (unsigned int)-268500969;
  }
  return InitiatorInstance;
}

```

## disassembly

```asm
0x180006998  push    rbx
0x18000699a  push    rsi
0x18000699b  push    rdi
0x18000699c  push    r14
0x18000699e  push    r15
0x1800069a0  sub     rsp, 20h
0x1800069a4  cmp     cs:DiscpInitiatorInstanceCount, 0
0x1800069ab  mov     r14, r8
0x1800069ae  mov     r15, rdx
0x1800069b1  mov     rsi, rcx
0x1800069b4  jbe     loc_180006A6B
0x1800069ba  test    rcx, rcx
0x1800069bd  jz      short loc_180006A00
0x1800069bf  mov     ebx, 8
0x1800069c4  mov     ecx, ebx
0x1800069c6  call    cs:__imp_DiscpAllocMemory
0x1800069cc  mov     rdi, rax
0x1800069cf  test    rax, rax
0x1800069d2  jz      loc_180006A70
0x1800069d8  mov     rdx, rax
0x1800069db  mov     rcx, rsi
0x1800069de  call    DiscpFindInitiatorInstance
0x1800069e3  mov     ebx, eax
0x1800069e5  test    eax, eax
0x1800069e7  jnz     short loc_1800069F5
0x1800069e9  mov     dword ptr [r15], 1
0x1800069f0  mov     [r14], rdi
0x1800069f3  jmp     short loc_180006A70
0x1800069f5  mov     rcx, rdi
0x1800069f8  call    cs:__imp_DiscpFreeMemory
0x1800069fe  jmp     short loc_180006A70
0x180006a00  lea     rcx, DiscpCritSection; CriticalSection
0x180006a07  call    cs:__imp_RtlEnterCriticalSection
0x180006a0d  mov     ecx, cs:DiscpInitiatorInstanceCount
0x180006a13  shl     ecx, 3
0x180006a16  call    cs:__imp_DiscpAllocMemory
0x180006a1c  test    rax, rax
0x180006a1f  jz      short loc_180006A57
0x180006a21  mov     rcx, cs:DiscpInitiatorInstanceList
0x180006a28  lea     r9, DiscpInitiatorInstanceList
0x180006a2f  xor     edx, edx
0x180006a31  jmp     short loc_180006A48
0x180006a33  cmp     edx, cs:DiscpInitiatorInstanceCount
0x180006a39  jnb     short loc_180006A4D
0x180006a3b  mov     [rax+rdx*8], rcx
0x180006a3f  lock inc dword ptr [rcx+10h]
0x180006a43  mov     rcx, [rcx]
0x180006a46  inc     edx
0x180006a48  cmp     rcx, r9
0x180006a4b  jnz     short loc_180006A33
0x180006a4d  mov     [r15], edx
0x180006a50  xor     ebx, ebx
0x180006a52  mov     [r14], rax
0x180006a55  jmp     short loc_180006A5C
0x180006a57  mov     ebx, 8
0x180006a5c  lea     rcx, DiscpCritSection; CriticalSection
0x180006a63  call    cs:__imp_RtlLeaveCriticalSection
0x180006a69  jmp     short loc_180006A70
0x180006a6b  mov     ebx, 0EFFF0017h
0x180006a70  mov     eax, ebx
0x180006a72  add     rsp, 20h
0x180006a76  pop     r15
0x180006a78  pop     r14
0x180006a7a  pop     rdi
0x180006a7b  pop     rsi
0x180006a7c  pop     rbx
0x180006a7d  retn
```
