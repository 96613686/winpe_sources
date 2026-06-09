# ComponentOnDemandp_ProcessQueue(void)

- ea: `0x18005288c`
- end: `0x180052beb`
- name: `?ComponentOnDemandp_ProcessQueue@@YAKXZ`
- size: `863`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180029500`

## callees

- `0x180012920`
- `0x1800212b0`
- `0x18005288c`
- `0x180052bf4`
- `0x180056262`
- `0x18007a9cf`
- `0x1800a7990`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180052bcb`
- `ntdll!RtlLeaveCriticalSection` at `0x180052bcb`
- `ntdll!RtlEnterCriticalSection` at `0x1800528ac`
- `ntdll!RtlEnterCriticalSection` at `0x1800528ac`
- `ntdll!NtSuspendProcess` at `0x180052935`
- `ntdll!NtSuspendProcess` at `0x180052935`
- `ntdll!RtlNtStatusToDosError` at `0x180052941`
- `ntdll!RtlNtStatusToDosError` at `0x180052941`
- `ntdll!RtlReAllocateHeap` at `0x180052b9b`
- `ntdll!RtlReAllocateHeap` at `0x180052b9b`
- `ntdll!RtlAllocateHeap` at `0x180052b7b`
- `ntdll!RtlAllocateHeap` at `0x180052b7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180052979`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180052979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529e0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800529aa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800529aa`

## string_xrefs

- `0x1800529ec`: `Failed to create event [%d]`
- `0x1800528b4`: `ComponentOnDemandp_ProcessQueue`
- `0x1800529d7`: `Failed to create Arp monitor thread [%d]`

## pseudocode

```c
__int64 ComponentOnDemandp_ProcessQueue(void)
{
  ULONGLONG i; // rdi
  __int64 *v1; // rbx
  __int64 v2; // rbx
  bool v3; // zf
  int v4; // eax
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  DWORD LastError; // eax
  int v8; // r8d
  const char *v9; // r9
  DWORD v10; // r15d
  char *v11; // r14
  ULONGLONG v12; // rsi
  ULONGLONG v13; // rcx
  unsigned __int64 v14; // rdi
  ULONGLONG v15; // rdi
  size_t v16; // r14
  PVOID v17; // rax
  PVOID Heap; // rsi
  ULONGLONG pullResult; // [rsp+60h] [rbp+30h] BYREF
  ULONGLONG Size; // [rsp+68h] [rbp+38h] BYREF

  RtlEnterCriticalSection(&g_CODQueueLock);
  for ( i = 0; i < xmmword_180159848; ++i )
  {
    pullResult = 0;
    if ( ULongLongMult((ULONGLONG)*(&g_CODQueue + 1), i, &pullResult) < 0
      || (v1 = (__int64 *)(*((_QWORD *)&xmmword_180159858 + 1) + pullResult),
          *((_QWORD *)&xmmword_180159858 + 1) + pullResult < *((_QWORD *)&xmmword_180159858 + 1)) )
    {
      v1 = 0;
    }
    v2 = *v1;
    if ( *(_DWORD *)(v2 + 520) != 1 && *(_DWORD *)(v2 + 528) != 1 )
    {
      v3 = *(_DWORD *)(v2 + 524) == 0;
      *(_DWORD *)(v2 + 528) = 1;
      if ( !v3 )
      {
        v4 = NtSuspendProcess(*(HANDLE *)(v2 + 536));
        if ( v4 < 0 )
        {
          RtlNtStatusToDosError(v4);
          AslLogCallPrintf(
            1,
            (unsigned int)"ComponentOnDemandp_ProcessQueue",
            918,
            (unsigned int)"Failed to suspend process [%d]");
        }
      }
      if ( !(unsigned int)ComponentOnDemandp_IsComponentInstallInProgress((struct _PCA_COMPONENT_ON_DEMAND_DATA *)v2) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *(_QWORD *)(v2 + 560) = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
          v8 = 938;
          v9 = "Failed to create event [%d]";
LABEL_18:
          v10 = LastError;
          AslLogCallPrintf(1, (unsigned int)"ComponentOnDemandp_ProcessQueue", v8, (_DWORD)v9);
          if ( !v2 )
            goto LABEL_40;
          if ( i < xmmword_180159848 )
          {
            pullResult = 0;
            if ( ULongLongMult((ULONGLONG)*(&g_CODQueue + 1), i, &pullResult) >= 0 )
            {
              v11 = (char *)(*((_QWORD *)&xmmword_180159858 + 1) + pullResult);
              if ( *((_QWORD *)&xmmword_180159858 + 1) + pullResult >= *((_QWORD *)&xmmword_180159858 + 1) )
              {
                v12 = xmmword_180159848 + ~i;
                Size = v12;
                if ( !v12 )
                  goto LABEL_27;
                if ( ULongLongMult(xmmword_180159848 + ~i, (ULONGLONG)*(&g_CODQueue + 1), &Size) >= 0 )
                {
                  pullResult = 0;
                  if ( ULongLongMult((ULONGLONG)*(&g_CODQueue + 1), i + 1, &pullResult) >= 0
                    && *((_QWORD *)&xmmword_180159858 + 1) + pullResult >= *((_QWORD *)&xmmword_180159858 + 1) )
                  {
                    v12 = Size;
                    memmove_0(v11, (const void *)(*((_QWORD *)&xmmword_180159858 + 1) + pullResult), Size);
LABEL_27:
                    memset_0(&v11[v12], 0, (size_t)*(&g_CODQueue + 1));
                    v13 = xmmword_180159848 - 1;
                    xmmword_180159848 = v13;
                    if ( v13 > 0x10 )
                    {
                      v14 = *(&xmmword_180159848 + 1);
                      if ( (unsigned __int64)*(&g_CODQueue + 1) * *(&xmmword_180159848 + 1) >= 0x400
                        && v13 < *(&xmmword_180159848 + 1) >> 2 )
                      {
                        pullResult = 0;
                        if ( ULongLongMult(*(&xmmword_180159848 + 1), (ULONGLONG)*(&g_CODQueue + 1), &Size) >= 0 )
                        {
                          v15 = v14 >> 1;
                          if ( ULongLongMult(v15, (ULONGLONG)*(&g_CODQueue + 1), &pullResult) >= 0 )
                          {
                            v16 = pullResult;
                            if ( *((_QWORD *)&xmmword_180159858 + 1) )
                            {
                              Heap = RtlReAllocateHeap(g_CODQueue, 0, *((PVOID *)&xmmword_180159858 + 1), pullResult);
                            }
                            else
                            {
                              v17 = RtlAllocateHeap(g_CODQueue, 0, pullResult);
                              Heap = v17;
                              if ( v17 )
                                memset_0(v17, 0, v16);
                            }
                            if ( Heap )
                            {
                              *((_QWORD *)&xmmword_180159858 + 1) = Heap;
                              *(&xmmword_180159848 + 1) = v15;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          ComponentOnDemandp_CleanupCODRequest((struct _PCA_COMPONENT_ON_DEMAND_DATA *)v2);
          goto LABEL_40;
        }
        Thread = CreateThread(0, 0, ComponentOnDemandp_InstallLaunchThreadProc, (LPVOID)v2, 0, 0);
        *(_QWORD *)(v2 + 568) = Thread;
        if ( !Thread )
        {
          LastError = GetLastError();
          v8 = 956;
          v9 = "Failed to create Arp monitor thread [%d]";
          goto LABEL_18;
        }
        *(_DWORD *)(v2 + 520) = 1;
      }
    }
  }
  v10 = 0;
LABEL_40:
  RtlLeaveCriticalSection(&g_CODQueueLock);
  return v10;
}

```

## disassembly

```asm
0x18005288c  mov     [rsp-28h+arg_10], rbx
0x180052891  mov     [rsp-28h+arg_18], rsi
0x180052896  push    rbp
0x180052897  push    rdi
0x180052898  push    r13
0x18005289a  push    r14
0x18005289c  push    r15
0x18005289e  mov     rbp, rsp
0x1800528a1  sub     rsp, 30h
0x1800528a5  lea     rcx, ?g_CODQueueLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800528ac  call    cs:__imp_RtlEnterCriticalSection
0x1800528b2  xor     edi, edi
0x1800528b4  lea     rsi, aComponentondem_4; "ComponentOnDemandp_ProcessQueue"
0x1800528bb  lea     r13d, [rdi+1]
0x1800528bf  cmp     rdi, qword ptr cs:xmmword_180159848
0x1800528c6  jnb     loc_180052BC1
0x1800528cc  mov     rcx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A+8; ullMultiplicand
0x1800528d3  lea     r8, [rbp+pullResult]; pullResult
0x1800528d7  mov     rdx, rdi; ullMultiplier
0x1800528da  mov     [rbp+pullResult], 0
0x1800528e2  call    ULongLongMult
0x1800528e7  test    eax, eax
0x1800528e9  js      short loc_1800528FF
0x1800528eb  mov     rbx, [rbp+pullResult]
0x1800528ef  add     rbx, qword ptr cs:xmmword_180159858+8
0x1800528f6  cmp     rbx, qword ptr cs:xmmword_180159858+8
0x1800528fd  jnb     short loc_180052901
0x1800528ff  xor     ebx, ebx
0x180052901  mov     rbx, [rbx]
0x180052904  cmp     [rbx+208h], r13d
0x18005290b  jz      loc_1800529C3
0x180052911  cmp     [rbx+210h], r13d
0x180052918  jz      loc_1800529C3
0x18005291e  cmp     dword ptr [rbx+20Ch], 0
0x180052925  mov     [rbx+210h], r13d
0x18005292c  jz      short loc_180052963
0x18005292e  mov     rcx, [rbx+218h]; ProcessHandle
0x180052935  call    cs:__imp_NtSuspendProcess
0x18005293b  test    eax, eax
0x18005293d  jns     short loc_180052963
0x18005293f  mov     ecx, eax; Status
0x180052941  call    cs:__imp_RtlNtStatusToDosError
0x180052947  lea     r9, aFailedToSuspen; "Failed to suspend process [%d]"
0x18005294e  mov     r8d, 396h
0x180052954  mov     rdx, rsi
0x180052957  mov     [rsp+30h+dwCreationFlags], eax
0x18005295b  mov     ecx, r13d
0x18005295e  call    AslLogCallPrintf
0x180052963  mov     rcx, rbx; struct _PCA_COMPONENT_ON_DEMAND_DATA *
0x180052966  call    ?ComponentOnDemandp_IsComponentInstallInProgress@@YAHPEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@Z; ComponentOnDemandp_IsComponentInstallInProgress(_PCA_COMPONENT_ON_DEMAND_DATA *)
0x18005296b  test    eax, eax
0x18005296d  jnz     short loc_1800529C3
0x18005296f  xor     r9d, r9d; lpName
0x180052972  xor     r8d, r8d; bInitialState
0x180052975  xor     edx, edx; bManualReset
0x180052977  xor     ecx, ecx; lpEventAttributes
0x180052979  call    cs:__imp_CreateEventW
0x18005297f  mov     [rbx+230h], rax
0x180052986  test    rax, rax
0x180052989  jz      short loc_1800529E0
0x18005298b  mov     [rsp+30h+lpThreadId], 0; lpThreadId
0x180052994  lea     r8, ?ComponentOnDemandp_InstallLaunchThreadProc@@YAKPEAX@Z; lpStartAddress
0x18005299b  mov     r9, rbx; lpParameter
0x18005299e  mov     [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x1800529a6  xor     edx, edx; dwStackSize
0x1800529a8  xor     ecx, ecx; lpThreadAttributes
0x1800529aa  call    cs:__imp_CreateThread
0x1800529b0  mov     [rbx+238h], rax
0x1800529b7  test    rax, rax
0x1800529ba  jz      short loc_1800529CB
0x1800529bc  mov     [rbx+208h], r13d
0x1800529c3  add     rdi, r13
0x1800529c6  jmp     loc_1800528BF
0x1800529cb  call    cs:__imp_GetLastError
0x1800529d1  mov     r8d, 3BCh
0x1800529d7  lea     r9, aFailedToCreate_7; "Failed to create Arp monitor thread [%d"...
0x1800529de  jmp     short loc_1800529F3
0x1800529e0  call    cs:__imp_GetLastError
0x1800529e6  mov     r8d, 3AAh
0x1800529ec  lea     r9, aFailedToCreate_60; "Failed to create event [%d]"
0x1800529f3  mov     ecx, r13d
0x1800529f6  mov     r15d, eax
0x1800529f9  mov     rdx, rsi
0x1800529fc  mov     [rsp+30h+dwCreationFlags], eax
0x180052a00  call    AslLogCallPrintf
0x180052a05  test    rbx, rbx
0x180052a08  jz      loc_180052BC4
0x180052a0e  cmp     rdi, qword ptr cs:xmmword_180159848
0x180052a15  jnb     loc_180052BB7
0x180052a1b  mov     rcx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A+8; ullMultiplicand
0x180052a22  lea     r8, [rbp+pullResult]; pullResult
0x180052a26  mov     rdx, rdi; ullMultiplier
0x180052a29  mov     [rbp+pullResult], 0
0x180052a31  call    ULongLongMult
0x180052a36  test    eax, eax
0x180052a38  js      loc_180052BB7
0x180052a3e  mov     r14, [rbp+pullResult]
0x180052a42  add     r14, qword ptr cs:xmmword_180159858+8
0x180052a49  cmp     r14, qword ptr cs:xmmword_180159858+8
0x180052a50  jb      loc_180052BB7
0x180052a56  mov     rsi, rdi
0x180052a59  not     rsi
0x180052a5c  add     rsi, qword ptr cs:xmmword_180159848
0x180052a63  mov     [rbp+Size], rsi
0x180052a67  jz      short loc_180052ACF
0x180052a69  mov     rdx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A+8; ullMultiplier
0x180052a70  lea     r8, [rbp+Size]; pullResult
0x180052a74  mov     rcx, rsi; ullMultiplicand
0x180052a77  call    ULongLongMult
0x180052a7c  test    eax, eax
0x180052a7e  js      loc_180052BB7
0x180052a84  mov     rcx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A+8; ullMultiplicand
0x180052a8b  lea     rdx, [rdi+1]; ullMultiplier
0x180052a8f  lea     r8, [rbp+pullResult]; pullResult
0x180052a93  mov     [rbp+pullResult], 0
0x180052a9b  call    ULongLongMult
0x180052aa0  test    eax, eax
0x180052aa2  js      loc_180052BB7
0x180052aa8  mov     rdx, [rbp+pullResult]
0x180052aac  add     rdx, qword ptr cs:xmmword_180159858+8; Src
0x180052ab3  cmp     rdx, qword ptr cs:xmmword_180159858+8
0x180052aba  jb      loc_180052BB7
0x180052ac0  mov     rsi, [rbp+Size]
0x180052ac4  mov     rcx, r14; void *
0x180052ac7  mov     r8, rsi; Size
0x180052aca  call    memmove_0
0x180052acf  mov     r8, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A+8; Size
0x180052ad6  lea     rcx, [r14+rsi]; void *
0x180052ada  xor     edx, edx; Val
0x180052adc  call    memset_0
0x180052ae1  mov     rcx, qword ptr cs:xmmword_180159848
0x180052ae8  sub     rcx, r13
0x180052aeb  mov     qword ptr cs:xmmword_180159848, rcx
0x180052af2  cmp     rcx, 10h
0x180052af6  jbe     loc_180052BB7
0x180052afc  mov     rdi, qword ptr cs:xmmword_180159848+8
0x180052b03  mov     rdx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A+8; ullMultiplier
0x180052b0a  mov     rax, rdi
0x180052b0d  imul    rax, rdx
0x180052b11  cmp     rax, 400h
0x180052b17  jb      loc_180052BB7
0x180052b1d  mov     rax, rdi
0x180052b20  shr     rax, 2
0x180052b24  cmp     rcx, rax
0x180052b27  jnb     loc_180052BB7
0x180052b2d  lea     r8, [rbp+Size]; pullResult
0x180052b31  mov     [rbp+pullResult], 0
0x180052b39  mov     rcx, rdi; ullMultiplicand
0x180052b3c  call    ULongLongMult
0x180052b41  test    eax, eax
0x180052b43  js      short loc_180052BB7
0x180052b45  mov     rdx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A+8; ullMultiplier
0x180052b4c  lea     r8, [rbp+pullResult]; pullResult
0x180052b50  shr     rdi, 1
0x180052b53  mov     rcx, rdi; ullMultiplicand
0x180052b56  call    ULongLongMult
0x180052b5b  test    eax, eax
0x180052b5d  js      short loc_180052BB7
0x180052b5f  mov     r8, qword ptr cs:xmmword_180159858+8; Ptr
0x180052b66  xor     edx, edx; Flags
0x180052b68  mov     r14, [rbp+pullResult]
0x180052b6c  mov     rcx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A; Heap
0x180052b73  test    r8, r8
0x180052b76  jnz     short loc_180052B98
0x180052b78  mov     r8, r14; Size
0x180052b7b  call    cs:__imp_RtlAllocateHeap
0x180052b81  mov     rsi, rax
0x180052b84  test    rax, rax
0x180052b87  jz      short loc_180052BA4
0x180052b89  mov     r8, r14; Size
0x180052b8c  xor     edx, edx; Val
0x180052b8e  mov     rcx, rax; void *
0x180052b91  call    memset_0
0x180052b96  jmp     short loc_180052BA4
0x180052b98  mov     r9, r14; Size
0x180052b9b  call    cs:__imp_RtlReAllocateHeap
0x180052ba1  mov     rsi, rax
0x180052ba4  test    rsi, rsi
0x180052ba7  jz      short loc_180052BB7
0x180052ba9  mov     qword ptr cs:xmmword_180159858+8, rsi
0x180052bb0  mov     qword ptr cs:xmmword_180159848+8, rdi
0x180052bb7  mov     rcx, rbx; struct _PCA_COMPONENT_ON_DEMAND_DATA *
0x180052bba  call    ?ComponentOnDemandp_CleanupCODRequest@@YAXPEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@Z; ComponentOnDemandp_CleanupCODRequest(_PCA_COMPONENT_ON_DEMAND_DATA *)
0x180052bbf  jmp     short loc_180052BC4
0x180052bc1  xor     r15d, r15d
0x180052bc4  lea     rcx, ?g_CODQueueLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180052bcb  call    cs:__imp_RtlLeaveCriticalSection
0x180052bd1  mov     rbx, [rsp+30h+arg_10]
0x180052bd6  mov     eax, r15d
0x180052bd9  mov     rsi, [rsp+30h+arg_18]
0x180052bde  add     rsp, 30h
0x180052be2  pop     r15
0x180052be4  pop     r14
0x180052be6  pop     r13
0x180052be8  pop     rdi
0x180052be9  pop     rbp
0x180052bea  retn
```
