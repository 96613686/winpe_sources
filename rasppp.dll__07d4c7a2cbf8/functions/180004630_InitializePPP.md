# InitializePPP

- ea: `0x180004630`
- end: `0x1800048df`
- name: `InitializePPP`
- size: `687`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180008320`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180004630`
- `0x180005704`
- `0x1800060a4`
- `0x180011928`
- `0x18001816c`
- `0x180018360`
- `0x1800184ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180004674`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180004674`
- `ntdll!RtlGetNtProductType` at `0x180004834`
- `ntdll!RtlGetNtProductType` at `0x180004834`
- `ntdll!RtlGetVersion` at `0x180004865`
- `ntdll!RtlGetVersion` at `0x180004865`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047b4`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800046f3`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800046f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000475a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004792`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000475a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046e1`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800046cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800047f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180004819`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800046cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800047f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180004819`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800046bb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800046bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000489f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000489f`

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
  qword_18004CAA8 = 0;
  *(_OWORD *)&WorkItemQ = 0;
  dword_18004CA20 = 3;
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
    result = InitEndpointDiscriminator(&byte_18004CF10);
    if ( !result )
    {
      dword_18004CACC = 0;
      v5 = 8LL * (unsigned int)qword_18004C970;
      if ( v5 > 0xFFFFFFFF )
        return 534;
      PcbTable = HeapAlloc(hHeap, 8u, (unsigned int)v5);
      if ( !PcbTable )
        return GetLastError();
      v6 = 8LL * (unsigned int)qword_18004C970;
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
        if ( (_DWORD)qword_18004C970 )
        {
          do
          {
            *((_QWORD *)PcbTable + v8) = 0;
            *((_QWORD *)*(&PcbTable + 1) + v8) = 0;
            v8 = (unsigned int)(v8 + 1);
          }
          while ( (unsigned int)v8 < (unsigned int)qword_18004C970 );
        }
        *(&TimerQ + 1) = CreateEventA(0, 0, 0, 0);
        if ( !*(&TimerQ + 1) )
          return GetLastError();
        qword_18004CA40 = CreateEventA(0, 0, 0, 0);
        if ( !qword_18004CA40 )
          return GetLastError();
        RtlGetNtProductType(ProductType);
        if ( ProductType[0] == NtProductWinNt )
          dword_18004C9EC |= 1u;
        memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
        VersionInformation.dwOSVersionInfoSize = 284;
        RtlGetVersion(&VersionInformation);
        if ( (v11 & 0x400) != 0 )
          dword_18004C9EC |= 1u;
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
0x180004630  mov     [rsp+arg_8], rbx
0x180004635  push    rsi
0x180004636  sub     rsp, 170h
0x18000463d  mov     rax, cs:__security_cookie
0x180004644  xor     rax, rsp
0x180004647  mov     [rsp+178h+var_18], rax
0x18000464f  mov     rbx, rcx
0x180004652  mov     [rsp+178h+ProductType], 0
0x18000465a  lea     rcx, [rsp+178h+VersionInformation]; void *
0x18000465f  xor     edx, edx; Val
0x180004661  mov     r8d, 11Ch; Size
0x180004667  call    memset_0
0x18000466c  call    time
0x180004671  mov     rcx, rax
0x180004674  call    cs:__imp__o_srand
0x18000467a  call    McGenEventRegister_EventRegister
0x18000467f  test    eax, eax
0x180004681  js      short loc_18000468D
0x180004683  call    SetLibParams
0x180004688  call    SetLibParamsWithBuffer
0x18000468d  xorps   xmm0, xmm0
0x180004690  mov     cs:hLogHandle, rbx
0x180004697  lea     rcx, CriticalSection; lpCriticalSection
0x18000469e  mov     cs:qword_18004CAA8, 0
0x1800046a9  movdqu  cs:WorkItemQ, xmm0
0x1800046b1  mov     cs:dword_18004CA20, 3
0x1800046bb  call    cs:__imp_InitializeCriticalSection
0x1800046c1  xor     r9d, r9d; lpName
0x1800046c4  xor     r8d, r8d; bInitialState
0x1800046c7  xor     ecx, ecx; lpEventAttributes
0x1800046c9  lea     ebx, [r9+1]
0x1800046cd  mov     edx, ebx; bManualReset
0x1800046cf  call    cs:__imp_CreateEventA
0x1800046d5  mov     cs:hEvent, rax
0x1800046dc  test    rax, rax
0x1800046df  jnz     short loc_1800046EC
0x1800046e1  call    cs:__imp_GetLastError
0x1800046e7  jmp     loc_1800048BE
0x1800046ec  xor     r8d, r8d; dwMaximumSize
0x1800046ef  xor     edx, edx; dwInitialSize
0x1800046f1  xor     ecx, ecx; flOptions
0x1800046f3  call    cs:__imp_HeapCreate
0x1800046f9  mov     cs:hHeap, rax
0x180004700  test    rax, rax
0x180004703  jz      short loc_1800046E1
0x180004705  lea     rcx, hKey; phkResult
0x18000470c  call    ReadRegistryInfo
0x180004711  test    eax, eax
0x180004713  jnz     loc_1800048BE
0x180004719  lea     rcx, byte_18004CF10
0x180004720  call    InitEndpointDiscriminator
0x180004725  test    eax, eax
0x180004727  jnz     loc_1800048BE
0x18000472d  mov     cs:dword_18004CACC, eax
0x180004733  mov     esi, 0FFFFFFFFh
0x180004738  mov     eax, dword ptr cs:qword_18004C970
0x18000473e  shl     rax, 3
0x180004742  cmp     rax, rsi
0x180004745  ja      loc_1800048B9
0x18000474b  mov     rcx, cs:hHeap; hHeap
0x180004752  mov     edx, 8; dwFlags
0x180004757  mov     r8d, eax; dwBytes
0x18000475a  call    cs:__imp_HeapAlloc
0x180004760  mov     qword ptr cs:PcbTable, rax
0x180004767  test    rax, rax
0x18000476a  jz      loc_1800046E1
0x180004770  mov     eax, dword ptr cs:qword_18004C970
0x180004776  shl     rax, 3
0x18000477a  cmp     rax, rsi
0x18000477d  ja      loc_1800048B9
0x180004783  mov     rcx, cs:hHeap; hHeap
0x18000478a  mov     edx, 8; dwFlags
0x18000478f  mov     r8d, eax; dwBytes
0x180004792  call    cs:__imp_HeapAlloc
0x180004798  xor     edx, edx; dwFlags
0x18000479a  mov     qword ptr cs:PcbTable+8, rax
0x1800047a1  test    rax, rax
0x1800047a4  jnz     short loc_1800047BF
0x1800047a6  mov     r8, qword ptr cs:PcbTable; lpMem
0x1800047ad  mov     rcx, cs:hHeap; hHeap
0x1800047b4  call    cs:__imp_HeapFree
0x1800047ba  jmp     loc_1800046E1
0x1800047bf  cmp     dword ptr cs:qword_18004C970, edx
0x1800047c5  jbe     short loc_1800047EF
0x1800047c7  mov     rax, qword ptr cs:PcbTable
0x1800047ce  mov     qword ptr [rax+rdx*8], 0
0x1800047d6  mov     rax, qword ptr cs:PcbTable+8
0x1800047dd  mov     qword ptr [rax+rdx*8], 0
0x1800047e5  add     edx, ebx
0x1800047e7  cmp     edx, dword ptr cs:qword_18004C970
0x1800047ed  jb      short loc_1800047C7
0x1800047ef  xor     r9d, r9d; lpName
0x1800047f2  xor     r8d, r8d; bInitialState
0x1800047f5  xor     edx, edx; bManualReset
0x1800047f7  xor     ecx, ecx; lpEventAttributes
0x1800047f9  call    cs:__imp_CreateEventA
0x1800047ff  mov     qword ptr cs:TimerQ+8, rax
0x180004806  test    rax, rax
0x180004809  jz      loc_1800046E1
0x18000480f  xor     r9d, r9d; lpName
0x180004812  xor     r8d, r8d; bInitialState
0x180004815  xor     edx, edx; bManualReset
0x180004817  xor     ecx, ecx; lpEventAttributes
0x180004819  call    cs:__imp_CreateEventA
0x18000481f  mov     cs:qword_18004CA40, rax
0x180004826  test    rax, rax
0x180004829  jz      loc_1800046E1
0x18000482f  lea     rcx, [rsp+178h+ProductType]; ProductType
0x180004834  call    cs:__imp_RtlGetNtProductType
0x18000483a  cmp     [rsp+178h+ProductType], ebx
0x18000483e  jnz     short loc_180004846
0x180004840  or      cs:dword_18004C9EC, ebx
0x180004846  xor     edx, edx; Val
0x180004848  lea     rcx, [rsp+178h+VersionInformation.dwMajorVersion]; void *
0x18000484d  mov     r8d, 118h; Size
0x180004853  call    memset_0
0x180004858  lea     rcx, [rsp+178h+VersionInformation]; lpVersionInformation
0x18000485d  mov     [rsp+178h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180004865  call    cs:__imp_RtlGetVersion
0x18000486b  mov     eax, 400h
0x180004870  test    [rsp+178h+var_20], ax
0x180004878  jz      short loc_180004880
0x18000487a  or      cs:dword_18004C9EC, ebx
0x180004880  mov     [rsp+178h+lpThreadId], 0; lpThreadId
0x180004889  lea     r8, WorkerThread; lpStartAddress
0x180004890  xor     r9d, r9d; lpParameter
0x180004893  mov     [rsp+178h+dwCreationFlags], 0; dwCreationFlags
0x18000489b  xor     edx, edx; dwStackSize
0x18000489d  xor     ecx, ecx; lpThreadAttributes
0x18000489f  call    cs:__imp_CreateThread
0x1800048a5  mov     cs:hHandle, rax
0x1800048ac  test    rax, rax
0x1800048af  jz      loc_1800046E1
0x1800048b5  xor     eax, eax
0x1800048b7  jmp     short loc_1800048BE
0x1800048b9  mov     eax, 216h
0x1800048be  mov     rcx, [rsp+178h+var_18]
0x1800048c6  xor     rcx, rsp; StackCookie
0x1800048c9  call    __security_check_cookie
0x1800048ce  mov     rbx, [rsp+178h+arg_8]
0x1800048d6  add     rsp, 170h
0x1800048dd  pop     rsi
0x1800048de  retn
```
