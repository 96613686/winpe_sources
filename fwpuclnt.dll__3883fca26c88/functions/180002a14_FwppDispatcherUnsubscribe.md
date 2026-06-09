# FwppDispatcherUnsubscribe

- ea: `0x180002a14`
- end: `0x180002af1`
- name: `FwppDispatcherUnsubscribe`
- size: `221`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `31`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180001740`
- `0x1800017f0`
- `0x180001930`
- `0x180002ce0`
- `0x18000fb50`
- `0x180010a30`
- `0x180010ef0`
- `0x180010fb0`
- `0x180014220`
- `0x1800143f0`
- `0x180014b10`
- `0x180014c60`
- `0x180016430`
- `0x180016550`
- `0x180016670`
- `0x180016790`
- `0x180017ab0`
- `0x180017f70`
- `0x180018140`
- `0x180018600`
- `0x1800187d0`
- `0x180018880`
- `0x1800189d0`
- `0x180019070`
- `0x18001a490`
- `0x18001a8c0`
- `0x18001aa20`
- `0x18001b710`
- `0x18001b8e0`
- `0x18001bf00`
- `0x18001e948`

## callees

- `0x180002a14`
- `0x18000e820`
- `0x18000fae4`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180002a56`
- `ntdll!RtlRemoveEntryHashTable` at `0x180002a56`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002a93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002a93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002aa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002aa5`

## pseudocode

```c
__int64 __fastcall FwppDispatcherUnsubscribe(LPCRITICAL_SECTION lpCriticalSection, __int64 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  v3 = *a2;
  v8 = v3;
  if ( v3 )
  {
    EnterCriticalSection(lpCriticalSection);
    RtlRemoveEntryHashTable(&lpCriticalSection[1].OwningThread, v3, 0);
    WfpRestructureHashtable(&lpCriticalSection[1].OwningThread);
    LeaveCriticalSection(lpCriticalSection);
    if ( a3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 48), 0xFFFFFFFF) > 1 )
        WaitForSingleObject(*(HANDLE *)(v3 + 56), 0xFFFFFFFF);
      goto LABEL_6;
    }
    CloseHandle(*(HANDLE *)(v3 + 56));
    *(_QWORD *)(v3 + 56) = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 48), 0xFFFFFFFF) == 1 )
LABEL_6:
      FwppSubscriptionDestroy(&v8);
  }
  result = 0xBADBADFABADBADFAuLL;
  *a2 = 0xBADBADFABADBADFAuLL;
  return result;
}

```

## disassembly

```asm
0x180002a14  mov     [rsp+arg_0], rbx
0x180002a19  mov     [rsp+arg_10], rbp
0x180002a1e  push    rsi
0x180002a1f  push    rdi
0x180002a20  push    r14
0x180002a22  sub     rsp, 20h
0x180002a26  mov     rdi, [rdx]
0x180002a29  mov     r14d, r8d
0x180002a2c  mov     [rsp+38h+arg_8], rdi
0x180002a31  mov     rsi, rdx
0x180002a34  mov     rbp, rcx
0x180002a37  test    rdi, rdi
0x180002a3a  jz      loc_180002AD0
0x180002a40  call    cs:__imp_EnterCriticalSection
0x180002a47  nop     dword ptr [rax+rax+00h]
0x180002a4c  xor     r8d, r8d
0x180002a4f  lea     rcx, [rbp+38h]
0x180002a53  mov     rdx, rdi
0x180002a56  call    cs:__imp_RtlRemoveEntryHashTable
0x180002a5d  nop     dword ptr [rax+rax+00h]
0x180002a62  lea     rcx, [rbp+38h]
0x180002a66  call    WfpRestructureHashtable
0x180002a6b  mov     rcx, rbp; lpCriticalSection
0x180002a6e  call    cs:__imp_LeaveCriticalSection
0x180002a75  nop     dword ptr [rax+rax+00h]
0x180002a7a  test    r14d, r14d
0x180002a7d  jz      short loc_180002AA1
0x180002a7f  or      eax, 0FFFFFFFFh
0x180002a82  lock xadd [rdi+30h], eax
0x180002a87  sub     eax, 1
0x180002a8a  jle     short loc_180002AC6
0x180002a8c  mov     rcx, [rdi+38h]; hHandle
0x180002a90  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002a93  call    cs:__imp_WaitForSingleObject
0x180002a9a  nop     dword ptr [rax+rax+00h]
0x180002a9f  jmp     short loc_180002AC6
0x180002aa1  mov     rcx, [rdi+38h]; hObject
0x180002aa5  call    cs:__imp_CloseHandle
0x180002aac  nop     dword ptr [rax+rax+00h]
0x180002ab1  or      eax, 0FFFFFFFFh
0x180002ab4  mov     qword ptr [rdi+38h], 0
0x180002abc  lock xadd [rdi+30h], eax
0x180002ac1  cmp     eax, 1
0x180002ac4  jnz     short loc_180002AD0
0x180002ac6  lea     rcx, [rsp+38h+arg_8]
0x180002acb  call    FwppSubscriptionDestroy
0x180002ad0  mov     rbx, [rsp+38h+arg_0]
0x180002ad5  mov     rax, 0BADBADFABADBADFAh
0x180002adf  mov     rbp, [rsp+38h+arg_10]
0x180002ae4  mov     [rsi], rax
0x180002ae7  add     rsp, 20h
0x180002aeb  pop     r14
0x180002aed  pop     rdi
0x180002aee  pop     rsi
0x180002aef  retn
```
