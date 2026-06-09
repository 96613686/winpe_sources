# InitializePPP

- ea: `0x1800046e0`
- end: `0x1800049de`
- name: `InitializePPP`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180008630`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x1800046e0`
- `0x180005908`
- `0x180006314`
- `0x180011edc`
- `0x1800189dc`
- `0x180018be0`
- `0x180018d2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180004724`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180004724`
- `ntdll!RtlGetNtProductType` at `0x180004920`
- `ntdll!RtlGetNtProductType` at `0x180004920`
- `ntdll!RtlGetVersion` at `0x180004957`
- `ntdll!RtlGetVersion` at `0x180004957`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000488e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000488e`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800047bb`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800047bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004828`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004866`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004828`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000478b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800048d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800048ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000478b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800048d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800048ff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004771`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004771`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180004997`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180004997`

## pseudocode

```c
DWORD __fastcall InitializePPP(void *a1)
{
  time_t *const v2; // rcx
  time_t v3; // rax
  DWORD result; // eax
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rax
  void *v7; // rax
  __int64 v8; // rdx
  _NT_PRODUCT_TYPE ProductType[4]; // [rsp+30h] [rbp-148h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-138h] BYREF
  __int16 v11; // [rsp+158h] [rbp-20h]

  ProductType[0] = 0;
  memset_0(&VersionInformation, 0, 0x11Cu);
  v3 = time(v2);
  _o_srand(v3);
  if ( (int)McGenEventRegister_EventRegister() >= 0 )
  {
    SetLibParams();
    SetLibParamsWithBuffer();
  }
  hLogHandle = a1;
  qword_18004DAA8 = 0;
  *(_OWORD *)&WorkItemQ = 0;
  dword_18004DA20 = 3;
  InitializeCriticalSection(&CriticalSection);
  hEvent = CreateEventA(0, 1, 0, 0);
  if ( !hEvent )
    return GetLastError();
  hHeap = HeapCreate(0, 0, 0);
  if ( !hHeap )
    return GetLastError();
  result = ReadRegistryInfo(&hKey);
  if ( !result )
  {
    result = InitEndpointDiscriminator(&byte_18004DF10);
    if ( !result )
    {
      dword_18004DACC = 0;
      v5 = 8LL * (unsigned int)qword_18004D970;
      if ( v5 > 0xFFFFFFFF )
        return 534;
      PcbTable = HeapAlloc(hHeap, 8u, (unsigned int)v5);
      if ( !PcbTable )
        return GetLastError();
      v6 = 8LL * (unsigned int)qword_18004D970;
      if ( v6 > 0xFFFFFFFF )
      {
        return 534;
      }
      else
      {
        v7 = HeapAlloc(hHeap, 8u, (unsigned int)v6);
        v8 = 0;
        *(&PcbTable + 1) = v7;
        if ( !v7 )
        {
          HeapFree(hHeap, 0, PcbTable);
          return GetLastError();
        }
        if ( (_DWORD)qword_18004D970 )
        {
          do
          {
            *((_QWORD *)PcbTable + v8) = 0;
            *((_QWORD *)*(&PcbTable + 1) + v8) = 0;
            v8 = (unsigned int)(v8 + 1);
          }
          while ( (unsigned int)v8 < (unsigned int)qword_18004D970 );
        }
        *(&TimerQ + 1) = CreateEventA(0, 0, 0, 0);
        if ( !*(&TimerQ + 1) )
          return GetLastError();
        qword_18004DA40 = CreateEventA(0, 0, 0, 0);
        if ( !qword_18004DA40 )
          return GetLastError();
        RtlGetNtProductType(ProductType);
        if ( ProductType[0] == NtProductWinNt )
          dword_18004D9EC |= 1u;
        memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
        VersionInformation.dwOSVersionInfoSize = 284;
        RtlGetVersion(&VersionInformation);
        if ( (v11 & 0x400) != 0 )
          dword_18004D9EC |= 1u;
        hHandle = CreateThread(0, 0, WorkerThread, 0, 0, 0);
        if ( !hHandle )
          return GetLastError();
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800046e0  mov     [rsp+arg_8], rbx
0x1800046e5  push    rsi
0x1800046e6  sub     rsp, 170h
0x1800046ed  mov     rax, cs:__security_cookie
0x1800046f4  xor     rax, rsp
0x1800046f7  mov     [rsp+178h+var_18], rax
0x1800046ff  mov     rbx, rcx
0x180004702  mov     [rsp+178h+ProductType], 0
0x18000470a  lea     rcx, [rsp+178h+VersionInformation]; void *
0x18000470f  xor     edx, edx; Val
0x180004711  mov     r8d, 11Ch; Size
0x180004717  call    memset_0
0x18000471c  call    time
0x180004721  mov     rcx, rax
0x180004724  call    cs:__imp__o_srand
0x18000472b  nop     dword ptr [rax+rax+00h]
0x180004730  call    McGenEventRegister_EventRegister
0x180004735  test    eax, eax
0x180004737  js      short loc_180004743
0x180004739  call    SetLibParams
0x18000473e  call    SetLibParamsWithBuffer
0x180004743  xorps   xmm0, xmm0
0x180004746  mov     cs:hLogHandle, rbx
0x18000474d  lea     rcx, CriticalSection; lpCriticalSection
0x180004754  mov     cs:qword_18004DAA8, 0
0x18000475f  movdqu  cs:WorkItemQ, xmm0
0x180004767  mov     cs:dword_18004DA20, 3
0x180004771  call    cs:__imp_InitializeCriticalSection
0x180004778  nop     dword ptr [rax+rax+00h]
0x18000477d  xor     r9d, r9d; lpName
0x180004780  xor     r8d, r8d; bInitialState
0x180004783  xor     ecx, ecx; lpEventAttributes
0x180004785  lea     ebx, [r9+1]
0x180004789  mov     edx, ebx; bManualReset
0x18000478b  call    cs:__imp_CreateEventA
0x180004792  nop     dword ptr [rax+rax+00h]
0x180004797  mov     cs:hEvent, rax
0x18000479e  test    rax, rax
0x1800047a1  jnz     short loc_1800047B4
0x1800047a3  call    cs:__imp_GetLastError
0x1800047aa  nop     dword ptr [rax+rax+00h]
0x1800047af  jmp     loc_1800049BC
0x1800047b4  xor     r8d, r8d; dwMaximumSize
0x1800047b7  xor     edx, edx; dwInitialSize
0x1800047b9  xor     ecx, ecx; flOptions
0x1800047bb  call    cs:__imp_HeapCreate
0x1800047c2  nop     dword ptr [rax+rax+00h]
0x1800047c7  mov     cs:hHeap, rax
0x1800047ce  test    rax, rax
0x1800047d1  jz      short loc_1800047A3
0x1800047d3  lea     rcx, hKey; phkResult
0x1800047da  call    ReadRegistryInfo
0x1800047df  test    eax, eax
0x1800047e1  jnz     loc_1800049BC
0x1800047e7  lea     rcx, byte_18004DF10
0x1800047ee  call    InitEndpointDiscriminator
0x1800047f3  test    eax, eax
0x1800047f5  jnz     loc_1800049BC
0x1800047fb  mov     cs:dword_18004DACC, eax
0x180004801  mov     esi, 0FFFFFFFFh
0x180004806  mov     eax, dword ptr cs:qword_18004D970
0x18000480c  shl     rax, 3
0x180004810  cmp     rax, rsi
0x180004813  ja      loc_1800049B7
0x180004819  mov     rcx, cs:hHeap; hHeap
0x180004820  mov     edx, 8; dwFlags
0x180004825  mov     r8d, eax; dwBytes
0x180004828  call    cs:__imp_HeapAlloc
0x18000482f  nop     dword ptr [rax+rax+00h]
0x180004834  mov     qword ptr cs:PcbTable, rax
0x18000483b  test    rax, rax
0x18000483e  jz      loc_1800047A3
0x180004844  mov     eax, dword ptr cs:qword_18004D970
0x18000484a  shl     rax, 3
0x18000484e  cmp     rax, rsi
0x180004851  ja      loc_1800049B7
0x180004857  mov     rcx, cs:hHeap; hHeap
0x18000485e  mov     edx, 8; dwFlags
0x180004863  mov     r8d, eax; dwBytes
0x180004866  call    cs:__imp_HeapAlloc
0x18000486d  nop     dword ptr [rax+rax+00h]
0x180004872  xor     edx, edx; dwFlags
0x180004874  mov     qword ptr cs:PcbTable+8, rax
0x18000487b  test    rax, rax
0x18000487e  jnz     short loc_18000489F
0x180004880  mov     r8, qword ptr cs:PcbTable; lpMem
0x180004887  mov     rcx, cs:hHeap; hHeap
0x18000488e  call    cs:__imp_HeapFree
0x180004895  nop     dword ptr [rax+rax+00h]
0x18000489a  jmp     loc_1800047A3
0x18000489f  cmp     dword ptr cs:qword_18004D970, edx
0x1800048a5  jbe     short loc_1800048CF
0x1800048a7  mov     rax, qword ptr cs:PcbTable
0x1800048ae  mov     qword ptr [rax+rdx*8], 0
0x1800048b6  mov     rax, qword ptr cs:PcbTable+8
0x1800048bd  mov     qword ptr [rax+rdx*8], 0
0x1800048c5  add     edx, ebx
0x1800048c7  cmp     edx, dword ptr cs:qword_18004D970
0x1800048cd  jb      short loc_1800048A7
0x1800048cf  xor     r9d, r9d; lpName
0x1800048d2  xor     r8d, r8d; bInitialState
0x1800048d5  xor     edx, edx; bManualReset
0x1800048d7  xor     ecx, ecx; lpEventAttributes
0x1800048d9  call    cs:__imp_CreateEventA
0x1800048e0  nop     dword ptr [rax+rax+00h]
0x1800048e5  mov     qword ptr cs:TimerQ+8, rax
0x1800048ec  test    rax, rax
0x1800048ef  jz      loc_1800047A3
0x1800048f5  xor     r9d, r9d; lpName
0x1800048f8  xor     r8d, r8d; bInitialState
0x1800048fb  xor     edx, edx; bManualReset
0x1800048fd  xor     ecx, ecx; lpEventAttributes
0x1800048ff  call    cs:__imp_CreateEventA
0x180004906  nop     dword ptr [rax+rax+00h]
0x18000490b  mov     cs:qword_18004DA40, rax
0x180004912  test    rax, rax
0x180004915  jz      loc_1800047A3
0x18000491b  lea     rcx, [rsp+178h+ProductType]; ProductType
0x180004920  call    cs:__imp_RtlGetNtProductType
0x180004927  nop     dword ptr [rax+rax+00h]
0x18000492c  cmp     [rsp+178h+ProductType], ebx
0x180004930  jnz     short loc_180004938
0x180004932  or      cs:dword_18004D9EC, ebx
0x180004938  xor     edx, edx; Val
0x18000493a  lea     rcx, [rsp+178h+VersionInformation.dwMajorVersion]; void *
0x18000493f  mov     r8d, 118h; Size
0x180004945  call    memset_0
0x18000494a  lea     rcx, [rsp+178h+VersionInformation]; lpVersionInformation
0x18000494f  mov     [rsp+178h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180004957  call    cs:__imp_RtlGetVersion
0x18000495e  nop     dword ptr [rax+rax+00h]
0x180004963  mov     eax, 400h
0x180004968  test    [rsp+178h+var_20], ax
0x180004970  jz      short loc_180004978
0x180004972  or      cs:dword_18004D9EC, ebx
0x180004978  mov     [rsp+178h+lpThreadId], 0; lpThreadId
0x180004981  lea     r8, WorkerThread; lpStartAddress
0x180004988  xor     r9d, r9d; lpParameter
0x18000498b  mov     [rsp+178h+dwCreationFlags], 0; dwCreationFlags
0x180004993  xor     edx, edx; dwStackSize
0x180004995  xor     ecx, ecx; lpThreadAttributes
0x180004997  call    cs:__imp_CreateThread
0x18000499e  nop     dword ptr [rax+rax+00h]
0x1800049a3  mov     cs:hHandle, rax
0x1800049aa  test    rax, rax
0x1800049ad  jz      loc_1800047A3
0x1800049b3  xor     eax, eax
0x1800049b5  jmp     short loc_1800049BC
0x1800049b7  mov     eax, 216h
0x1800049bc  mov     rcx, [rsp+178h+var_18]
0x1800049c4  xor     rcx, rsp; StackCookie
0x1800049c7  call    __security_check_cookie
0x1800049cc  mov     rbx, [rsp+178h+arg_8]
0x1800049d4  add     rsp, 170h
0x1800049db  pop     rsi
0x1800049dc  retn
```
