# IndexHashDelete

- ea: `0x180042a70`
- end: `0x180042b00`
- name: `IndexHashDelete`
- size: `144`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180007e38`
- `0x18000fae4`
- `0x180011500`
- `0x180042a70`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180042a97`
- `ntdll!RtlRemoveEntryHashTable` at `0x180042a97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042ad1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042ad1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042a81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042a81`

## string_xrefs

- `0x180042aad`: `RtlRemoveEntryHashTable`
- `0x180042ae2`: `IndexHashDelete`

## pseudocode

```c
__int64 __fastcall IndexHashDelete(LPCRITICAL_SECTION lpCriticalSection, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // rcx
  __int64 v5; // rbx

  v2 = *(_QWORD *)(a2 + 32);
  EnterCriticalSection(lpCriticalSection);
  if ( (unsigned __int8)RtlRemoveEntryHashTable(lpCriticalSection[1].OwningThread, v2, 0) )
  {
    v5 = 0;
    WfpRestructureHashtable(lpCriticalSection[1].OwningThread);
    lpCriticalSection[1].LockSemaphore = (char *)lpCriticalSection[1].LockSemaphore - 32;
  }
  else
  {
    v5 = WfpReportSysErrorAsNtStatus(v4, "RtlRemoveEntryHashTable", 3221225473LL);
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( v5 )
    WfpReportError(v5, "IndexHashDelete");
  return v5;
}

```

## disassembly

```asm
0x180042a70  mov     [rsp+arg_0], rbx
0x180042a75  push    rdi
0x180042a76  sub     rsp, 20h
0x180042a7a  mov     rbx, [rdx+20h]
0x180042a7e  mov     rdi, rcx
0x180042a81  call    cs:__imp_EnterCriticalSection
0x180042a88  nop     dword ptr [rax+rax+00h]
0x180042a8d  mov     rcx, [rdi+38h]
0x180042a91  xor     r8d, r8d
0x180042a94  mov     rdx, rbx
0x180042a97  call    cs:__imp_RtlRemoveEntryHashTable
0x180042a9e  nop     dword ptr [rax+rax+00h]
0x180042aa3  test    al, al
0x180042aa5  jnz     short loc_180042ABE
0x180042aa7  mov     r8d, 0C0000001h
0x180042aad  lea     rdx, aRtlremoveentry; "RtlRemoveEntryHashTable"
0x180042ab4  call    WfpReportSysErrorAsNtStatus
0x180042ab9  mov     rbx, rax
0x180042abc  jmp     short loc_180042ACE
0x180042abe  mov     rcx, [rdi+38h]
0x180042ac2  xor     ebx, ebx
0x180042ac4  call    WfpRestructureHashtable
0x180042ac9  add     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFE0h
0x180042ace  mov     rcx, rdi; lpCriticalSection
0x180042ad1  call    cs:__imp_LeaveCriticalSection
0x180042ad8  nop     dword ptr [rax+rax+00h]
0x180042add  test    rbx, rbx
0x180042ae0  jz      short loc_180042AF1
0x180042ae2  lea     rdx, aIndexhashdelet; "IndexHashDelete"
0x180042ae9  mov     rcx, rbx
0x180042aec  call    WfpReportError
0x180042af1  mov     rax, rbx
0x180042af4  mov     rbx, [rsp+28h+arg_0]
0x180042af9  add     rsp, 20h
0x180042afd  pop     rdi
0x180042afe  retn
```
