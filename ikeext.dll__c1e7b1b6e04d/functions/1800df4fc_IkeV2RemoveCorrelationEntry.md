# IkeV2RemoveCorrelationEntry

- ea: `0x1800df4fc`
- end: `0x1800df5c2`
- name: `IkeV2RemoveCorrelationEntry`
- size: `198`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180030ee0`
- `0x180066d30`
- `0x1800687ac`
- `0x1800949cc`

## callees

- `0x180008388`
- `0x18001afe0`
- `0x18004aa3c`
- `0x1800dedb0`
- `0x1800def90`
- `0x1800df4fc`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1800df569`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800df569`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df595`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df595`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800df52e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800df52e`

## string_xrefs

- `0x1800df512`: `IkeV2RemoveCorrelationEntry`
- `0x1800df59d`: `IkeV2RemoveCorrelationEntry`
- `0x1800df5a9`: `IkeV2RemoveCorrelationEntry`

## pseudocode

```c
__int64 __fastcall IkeV2RemoveCorrelationEntry(__int64 a1)
{
  __int64 CorrelationEntry; // rdi
  __int64 v3; // rbx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  TraceLogHelper("IkeV2RemoveCorrelationEntry", 1);
  EnterCriticalSection(gIkeExtGlobals + 3);
  CorrelationEntry = IkeV2FindCorrelationEntry(a1, 0, &v5);
  if ( !CorrelationEntry )
  {
    v3 = v5;
    if ( v5 )
    {
      RtlRemoveEntryHashTable(&gIkeExtGlobals[59].LockCount, v5, 0);
      WfpRestructureHashtable(&gIkeExtGlobals[59].LockCount);
      IkeV2FreeCorrelationEntry(v3);
    }
  }
  LeaveCriticalSection(gIkeExtGlobals + 3);
  TraceLogHelper("IkeV2RemoveCorrelationEntry", 0);
  return IkeReturnError(CorrelationEntry, "IkeV2RemoveCorrelationEntry");
}

```

## disassembly

```asm
0x1800df4fc  mov     [rsp+arg_0], rbx
0x1800df501  push    rdi
0x1800df502  sub     rsp, 20h
0x1800df506  mov     rbx, rcx
0x1800df509  mov     [rsp+28h+arg_8], 0
0x1800df512  lea     rcx, aIkev2removecor; "IkeV2RemoveCorrelationEntry"
0x1800df519  mov     edx, 1
0x1800df51e  call    TraceLogHelper
0x1800df523  mov     rcx, cs:gIkeExtGlobals
0x1800df52a  add     rcx, 78h ; 'x'; lpCriticalSection
0x1800df52e  call    cs:__imp_EnterCriticalSection
0x1800df534  lea     r8, [rsp+28h+arg_8]
0x1800df539  xor     edx, edx
0x1800df53b  mov     rcx, rbx
0x1800df53e  call    IkeV2FindCorrelationEntry
0x1800df543  mov     rdi, rax
0x1800df546  test    rax, rax
0x1800df549  jnz     short loc_1800DF58A
0x1800df54b  mov     rbx, [rsp+28h+arg_8]
0x1800df550  test    rbx, rbx
0x1800df553  jz      short loc_1800DF58A
0x1800df555  mov     rcx, cs:gIkeExtGlobals
0x1800df55c  xor     r8d, r8d
0x1800df55f  add     rcx, 940h
0x1800df566  mov     rdx, rbx
0x1800df569  call    cs:__imp_RtlRemoveEntryHashTable
0x1800df56f  mov     rcx, cs:gIkeExtGlobals
0x1800df576  add     rcx, 940h
0x1800df57d  call    WfpRestructureHashtable
0x1800df582  mov     rcx, rbx
0x1800df585  call    IkeV2FreeCorrelationEntry
0x1800df58a  mov     rcx, cs:gIkeExtGlobals
0x1800df591  add     rcx, 78h ; 'x'; lpCriticalSection
0x1800df595  call    cs:__imp_LeaveCriticalSection
0x1800df59b  xor     edx, edx
0x1800df59d  lea     rcx, aIkev2removecor; "IkeV2RemoveCorrelationEntry"
0x1800df5a4  call    TraceLogHelper
0x1800df5a9  lea     rdx, aIkev2removecor; "IkeV2RemoveCorrelationEntry"
0x1800df5b0  mov     rcx, rdi
0x1800df5b3  mov     rbx, [rsp+28h+arg_0]
0x1800df5b8  add     rsp, 20h
0x1800df5bc  pop     rdi
0x1800df5bd  jmp     IkeReturnError
```
