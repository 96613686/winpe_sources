# VolumeArrivalCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x18002a7f0`
- end: `0x18002a8a9`
- name: `?VolumeArrivalCallback@@YAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180008fac`
- `0x180009a38`
- `0x18002a608`
- `0x18002a7f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18002a870`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18002a870`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002a87e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002a87e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a894`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a894`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a844`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a850`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a850`

## pseudocode

```c
__int64 __fastcall VolumeArrivalCallback(__int64 a1, __int64 a2, int a3)
{
  __int64 DiskVolumePath; // rax
  RTL_CONDITION_VARIABLE *v5; // rcx
  char *v7[5]; // [rsp+30h] [rbp-28h] BYREF

  if ( !a3 )
  {
    DiskVolumePath = TryGetDiskVolumePath(v7, *(_QWORD *)(a2 + 40));
    std::wstring::operator=(a2 + 48, DiskVolumePath);
    std::wstring::~wstring(v7);
    if ( *(_QWORD *)(a2 + 64) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)a2);
      *(_DWORD *)(a2 + 8) = GetCurrentThreadId();
      *(_DWORD *)(a2 + 28) = 1;
      v5 = (RTL_CONDITION_VARIABLE *)(a2 + 16);
      if ( *(_DWORD *)(a2 + 24) )
        WakeConditionVariable(v5);
      else
        WakeAllConditionVariable(v5);
      *(_DWORD *)(a2 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)a2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002a7f0  push    rbx
0x18002a7f2  sub     rsp, 50h
0x18002a7f6  mov     rbx, rdx
0x18002a7f9  mov     [rsp+58h+SRWLock], rdx
0x18002a7fe  test    r8d, r8d
0x18002a801  jnz     loc_18002A8A0
0x18002a807  mov     rdx, [rdx+28h]
0x18002a80b  lea     rcx, [rsp+58h+var_28]
0x18002a810  call    ?TryGetDiskVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; TryGetDiskVolumePath(void *)
0x18002a815  lea     rcx, [rbx+30h]
0x18002a819  mov     rdx, rax
0x18002a81c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002a821  lea     rcx, [rsp+58h+var_28]
0x18002a826  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a82b  nop
0x18002a82c  jmp     short loc_18002A83A
0x18002a82e  mov     rbx, [rsp+58h+SRWLock]
0x18002a833  cmp     [rsp+58h+var_38], 0
0x18002a838  jl      short loc_18002A841
0x18002a83a  cmp     qword ptr [rbx+40h], 0
0x18002a83f  jz      short loc_18002A8A0
0x18002a841  mov     rcx, rbx; SRWLock
0x18002a844  call    cs:__imp_AcquireSRWLockExclusive
0x18002a84b  nop     dword ptr [rax+rax+00h]
0x18002a850  call    cs:__imp_GetCurrentThreadId
0x18002a857  nop     dword ptr [rax+rax+00h]
0x18002a85c  mov     [rbx+8], eax
0x18002a85f  mov     dword ptr [rbx+1Ch], 1
0x18002a866  lea     rcx, [rbx+10h]; ConditionVariable
0x18002a86a  cmp     dword ptr [rbx+18h], 0
0x18002a86e  jz      short loc_18002A87E
0x18002a870  call    cs:__imp_WakeConditionVariable
0x18002a877  nop     dword ptr [rax+rax+00h]
0x18002a87c  jmp     short loc_18002A88A
0x18002a87e  call    cs:__imp_WakeAllConditionVariable
0x18002a885  nop     dword ptr [rax+rax+00h]
0x18002a88a  mov     dword ptr [rbx+8], 0
0x18002a891  mov     rcx, rbx; SRWLock
0x18002a894  call    cs:__imp_ReleaseSRWLockExclusive
0x18002a89b  nop     dword ptr [rax+rax+00h]
0x18002a8a0  xor     eax, eax
0x18002a8a2  add     rsp, 50h
0x18002a8a6  pop     rbx
0x18002a8a7  retn
```
