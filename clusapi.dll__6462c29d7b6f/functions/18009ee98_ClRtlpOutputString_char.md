# ClRtlpOutputString(char *)

- ea: `0x18009ee98`
- end: `0x18009ef5a`
- name: `?ClRtlpOutputString@@YAXPEAD@Z`
- size: `194`
- prototype: `void __fastcall(LPCSTR lpOutputString)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18009edd0`

## callees

- `0x18000d5d0`
- `0x18009ee98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009eec9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009eec9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009eee9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009eee9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ef49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ef49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ef0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ef0f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18009ef3c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18009ef3c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009ef2f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009ef2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009eef2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009eef2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009eeb4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009eeb4`

## pseudocode

```c
void __fastcall ClRtlpOutputString(LPCSTR lpOutputString)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v2 = *(struct _RTL_CRITICAL_SECTION **)&lpCriticalSection;
  if ( !*(_QWORD *)&lpCriticalSection )
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)LocalAlloc(0, 0x28u);
    v4 = v3;
    if ( !v3 )
      return;
    InitializeCriticalSection(v3);
    _InterlockedCompareExchange64((volatile signed __int64 *)&lpCriticalSection, (signed __int64)v4, 0);
    v2 = *(struct _RTL_CRITICAL_SECTION **)&lpCriticalSection;
    if ( *(struct _RTL_CRITICAL_SECTION **)&lpCriticalSection == v4 )
    {
      qword_180124818 = &lpCriticalSection;
    }
    else
    {
      DeleteCriticalSection(v4);
      LocalFree(v4);
      v2 = *(struct _RTL_CRITICAL_SECTION **)&lpCriticalSection;
    }
  }
  EnterCriticalSection(v2);
  if ( ClRtlpDbgOutputToConsole )
  {
    printf("%hs \n", lpOutputString);
  }
  else if ( IsDebuggerPresent() )
  {
    OutputDebugStringA(lpOutputString);
  }
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)&lpCriticalSection);
}

```

## disassembly

```asm
0x18009ee98  mov     [rsp+arg_0], rbx
0x18009ee9d  push    rdi
0x18009ee9e  sub     rsp, 20h
0x18009eea2  mov     rdi, rcx
0x18009eea5  mov     rcx, cs:lpCriticalSection; uFlags
0x18009eeac  test    rcx, rcx
0x18009eeaf  jnz     short loc_18009EF0F
0x18009eeb1  lea     edx, [rcx+28h]; uBytes
0x18009eeb4  call    cs:__imp_LocalAlloc
0x18009eeba  mov     rbx, rax
0x18009eebd  test    rax, rax
0x18009eec0  jz      loc_18009EF4F
0x18009eec6  mov     rcx, rax; lpCriticalSection
0x18009eec9  call    cs:__imp_InitializeCriticalSection
0x18009eecf  xor     eax, eax
0x18009eed1  lock cmpxchg cs:lpCriticalSection, rbx
0x18009eeda  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x18009eee1  cmp     rcx, rbx
0x18009eee4  jz      short loc_18009EF01
0x18009eee6  mov     rcx, rbx; lpCriticalSection
0x18009eee9  call    cs:__imp_DeleteCriticalSection
0x18009eeef  mov     rcx, rbx; hMem
0x18009eef2  call    cs:__imp_LocalFree
0x18009eef8  mov     rcx, cs:lpCriticalSection
0x18009eeff  jmp     short loc_18009EF0F
0x18009ef01  lea     rax, lpCriticalSection
0x18009ef08  mov     cs:qword_180124818, rax
0x18009ef0f  call    cs:__imp_EnterCriticalSection
0x18009ef15  cmp     cs:?ClRtlpDbgOutputToConsole@@3HA, 0; int ClRtlpDbgOutputToConsole
0x18009ef1c  jz      short loc_18009EF2F
0x18009ef1e  mov     rdx, rdi
0x18009ef21  lea     rcx, aHs; "%hs \n"
0x18009ef28  call    printf
0x18009ef2d  jmp     short loc_18009EF42
0x18009ef2f  call    cs:__imp_IsDebuggerPresent
0x18009ef35  test    eax, eax
0x18009ef37  jz      short loc_18009EF42
0x18009ef39  mov     rcx, rdi; lpOutputString
0x18009ef3c  call    cs:__imp_OutputDebugStringA
0x18009ef42  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x18009ef49  call    cs:__imp_LeaveCriticalSection
0x18009ef4f  mov     rbx, [rsp+28h+arg_0]
0x18009ef54  add     rsp, 20h
0x18009ef58  pop     rdi
0x18009ef59  retn
```
