# NsiAllocateAndGetTable

- ea: `0x1800016b0`
- end: `0x180001ca2`
- name: `NsiAllocateAndGetTable`
- size: `1522`
- prototype: `__int64 __fastcall(int, __int64, unsigned int, _QWORD *, unsigned int, _QWORD *, unsigned int, _QWORD *, unsigned int, _QWORD *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800016b0`
- `0x180001cb0`
- `0x1800030e1`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x1800017c4`
- `ntdll!NtDeviceIoControlFile` at `0x1800019ec`
- `ntdll!NtDeviceIoControlFile` at `0x1800017c4`
- `ntdll!NtDeviceIoControlFile` at `0x1800019ec`
- `ntdll!NtWaitForSingleObject` at `0x180001c45`
- `ntdll!NtWaitForSingleObject` at `0x180001c72`
- `ntdll!NtWaitForSingleObject` at `0x180001c45`
- `ntdll!NtWaitForSingleObject` at `0x180001c72`
- `ntdll!RtlNtStatusToDosError` at `0x180001aec`
- `ntdll!RtlNtStatusToDosError` at `0x180001b62`
- `ntdll!RtlNtStatusToDosError` at `0x180001aec`
- `ntdll!RtlNtStatusToDosError` at `0x180001b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800017da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800017da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001aaf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ac6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ba5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001aaf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ac6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ba5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001855`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001b31`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001855`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001b31`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000176f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180001995`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000176f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180001995`

## pseudocode

```c
__int64 __fastcall NsiAllocateAndGetTable(
        int a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned int a5,
        _QWORD *a6,
        unsigned int a7,
        _QWORD *a8,
        unsigned int a9,
        _QWORD *a10,
        unsigned int a11,
        unsigned int *a12)
{
  __int64 v12; // rax
  unsigned int v14; // ebx
  unsigned int v15; // r12d
  void *v16; // rsi
  void *v17; // r15
  void *v18; // r14
  void *v19; // rdi
  int v20; // ebx
  HANDLE EventA; // rax
  void *v22; // rbx
  int Status; // edi
  int v24; // eax
  unsigned int v25; // edx
  unsigned int v26; // eax
  unsigned __int64 v27; // r12
  SIZE_T v28; // r8
  SIZE_T v29; // r8
  SIZE_T v30; // rax
  unsigned int v31; // r12d
  HANDLE v32; // rax
  void *v33; // r12
  int v34; // ebx
  ULONG LastError; // eax
  SIZE_T v37; // rdi
  void *v38; // rax
  ULONG v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // [rsp+50h] [rbp-B0h]
  unsigned int v42; // [rsp+54h] [rbp-ACh]
  __int128 OutputBuffer; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+78h] [rbp-88h]
  int v46; // [rsp+80h] [rbp-80h]
  int v47; // [rsp+84h] [rbp-7Ch]
  void *v48; // [rsp+88h] [rbp-78h]
  __int64 v49; // [rsp+90h] [rbp-70h]
  void *v50; // [rsp+98h] [rbp-68h]
  __int64 v51; // [rsp+A0h] [rbp-60h]
  void *v52; // [rsp+A8h] [rbp-58h]
  __int64 v53; // [rsp+B0h] [rbp-50h]
  void *v54; // [rsp+B8h] [rbp-48h]
  __int128 v55; // [rsp+C0h] [rbp-40h]
  __int128 InputBuffer; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  int v59; // [rsp+F0h] [rbp-10h]
  int v60; // [rsp+F4h] [rbp-Ch]
  __int64 v61; // [rsp+F8h] [rbp-8h]
  __int128 v62; // [rsp+100h] [rbp+0h]
  __int128 v63; // [rsp+110h] [rbp+10h]
  __int128 v64; // [rsp+120h] [rbp+20h]
  __int128 v65; // [rsp+130h] [rbp+30h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+140h] [rbp+40h] BYREF
  struct _IO_STATUS_BLOCK v67; // [rsp+150h] [rbp+50h] BYREF
  int v68; // [rsp+1A0h] [rbp+A0h]

  v68 = a1;
  v12 = a2;
  v14 = 0;
  v15 = 0;
  while ( 1 )
  {
    v41 = v15;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    if ( v15 >= 3 )
      goto LABEL_35;
    v61 = 0;
    v57 = v12;
    v58 = a3;
    v62 = 0u;
    v65 = 0;
    v63 = 0u;
    v64 = 0u;
    LODWORD(v65) = 0;
    v59 = a1;
    v60 = 1;
    DWORD2(v65) = 0;
    InputBuffer = 0;
    IoStatusBlock = 0;
    v20 = NsiOpenDevice();
    if ( v20 )
      goto LABEL_56;
    EventA = CreateEventA(0, 0, 0, 0);
    v22 = EventA;
    if ( EventA )
    {
      Status = NtDeviceIoControlFile(
                 g_NsiAsyncDeviceHandle,
                 EventA,
                 0,
                 0,
                 &IoStatusBlock,
                 0x12001Bu,
                 &InputBuffer,
                 0x70u,
                 &InputBuffer,
                 0x70u);
      if ( Status == 259 )
      {
        Status = NtWaitForSingleObject(v22, 0, 0);
        if ( Status >= 0 )
          Status = IoStatusBlock.Status;
      }
      CloseHandle(v22);
      if ( Status >= 0 && Status != 261 )
      {
        v20 = 0;
        goto LABEL_9;
      }
      LastError = RtlNtStatusToDosError(Status);
    }
    else
    {
      LastError = GetLastError();
    }
    v20 = LastError;
    if ( LastError )
    {
LABEL_56:
      if ( v20 != 234 )
        return (unsigned int)v20;
    }
LABEL_9:
    v24 = DWORD2(v65) >> 3;
    if ( DWORD2(v65) >> 3 < 0xA )
      v24 = 10;
    v25 = -1;
    v26 = DWORD2(v65) + v24;
    if ( v26 >= DWORD2(v65) )
      v25 = v26;
    v42 = v25;
    v27 = v25;
    if ( a5 )
    {
      v28 = -1;
      if ( is_mul_ok(v25, a5) )
        v28 = v25 * (unsigned __int64)a5;
      if ( v20 < 0 )
        return 534;
      v16 = HeapAlloc(g_NsiHeap, 0, v28);
      if ( !v16 )
        return 534;
    }
    else
    {
      v16 = 0;
    }
    v17 = 0;
    if ( a7 )
    {
      v37 = -1;
      if ( is_mul_ok(v27, a7) )
        v37 = v27 * a7;
      if ( v20 < 0 )
      {
        v18 = 0;
        v31 = 534;
        v19 = 0;
        goto LABEL_45;
      }
      v38 = HeapAlloc(g_NsiHeap, 0, v37);
      v17 = v38;
      if ( !v38 )
      {
        v18 = 0;
        v31 = 8;
        v19 = 0;
        goto LABEL_45;
      }
      memset_0(v38, 0, v37);
    }
    v18 = 0;
    if ( a9 )
    {
      v29 = -1;
      if ( is_mul_ok(v27, a9) )
        v29 = v27 * a9;
      if ( v20 < 0 )
      {
        v31 = 534;
        v19 = 0;
LABEL_45:
        if ( v16 )
          HeapFree(g_NsiHeap, 0, v16);
        if ( v17 )
          HeapFree(g_NsiHeap, 0, v17);
        if ( v18 )
          HeapFree(g_NsiHeap, 0, v18);
        if ( v19 )
          HeapFree(g_NsiHeap, 0, v19);
        return v31;
      }
      v18 = HeapAlloc(g_NsiHeap, 0, v29);
      if ( !v18 )
      {
        v19 = 0;
LABEL_92:
        v31 = 8;
        goto LABEL_45;
      }
    }
    v19 = 0;
    if ( a11 )
    {
      v30 = v27 * a11;
      if ( !is_mul_ok(v27, a11) )
        v30 = -1;
      if ( v20 < 0 )
      {
        v31 = 534;
        goto LABEL_45;
      }
      v19 = HeapAlloc(g_NsiHeap, 0, v30);
      if ( !v19 )
        goto LABEL_92;
    }
    v48 = v16;
    v44 = a2;
    v49 = a5;
    v51 = a7;
    v53 = a9;
    v55 = 0;
    LODWORD(v55) = a11;
    v46 = v68;
    DWORD2(v55) = v42;
    OutputBuffer = 0;
    v45 = a3;
    v50 = v17;
    v52 = v18;
    v54 = v19;
    v47 = 1;
    v67 = 0;
    v31 = NsiOpenDevice();
    if ( !v31 )
    {
      v32 = CreateEventA(0, 0, 0, 0);
      v33 = v32;
      if ( v32 )
      {
        v34 = NtDeviceIoControlFile(
                g_NsiAsyncDeviceHandle,
                v32,
                0,
                0,
                &v67,
                0x12001Bu,
                &OutputBuffer,
                0x70u,
                &OutputBuffer,
                0x70u);
        if ( v34 == 259 )
        {
          v34 = NtWaitForSingleObject(v33, 0, 0);
          if ( v34 >= 0 )
            v34 = v67.Status;
        }
        CloseHandle(v33);
        if ( v34 >= 0 && v34 != 261 )
        {
          v14 = DWORD2(v55);
          goto LABEL_35;
        }
        v39 = RtlNtStatusToDosError(v34);
      }
      else
      {
        v39 = GetLastError();
      }
      v31 = v39;
    }
    v14 = DWORD2(v55);
    if ( v31 != 234 )
      break;
    if ( v41 == 2 )
    {
      v40 = v42;
      if ( DWORD2(v55) <= v42 )
        v40 = DWORD2(v55);
      v14 = v40;
      goto LABEL_35;
    }
    if ( v16 )
      HeapFree(g_NsiHeap, 0, v16);
    if ( v17 )
      HeapFree(g_NsiHeap, 0, v17);
    if ( v18 )
      HeapFree(g_NsiHeap, 0, v18);
    if ( v19 )
      HeapFree(g_NsiHeap, 0, v19);
    v12 = a2;
    v15 = v41 + 1;
    a1 = v68;
  }
  if ( v31 )
    goto LABEL_45;
LABEL_35:
  *a12 = v14;
  if ( v16 )
    *a4 = v16;
  if ( v17 )
    *a6 = v17;
  if ( v18 )
    *a8 = v18;
  if ( v19 )
    *a10 = v19;
  return 0;
}

```

## disassembly

```asm
0x1800016b0  mov     [rsp-8+arg_10], rbx
0x1800016b5  mov     [rsp-8+arg_18], r9
0x1800016ba  mov     [rsp-8+arg_8], rdx
0x1800016bf  mov     [rsp-8+arg_0], ecx
0x1800016c3  push    rbp
0x1800016c4  push    rsi
0x1800016c5  push    rdi
0x1800016c6  push    r12
0x1800016c8  push    r13
0x1800016ca  push    r14
0x1800016cc  push    r15
0x1800016ce  lea     rbp, [rsp-60h]
0x1800016d3  sub     rsp, 160h
0x1800016da  mov     rax, rdx
0x1800016dd  mov     r13d, r8d
0x1800016e0  xor     edx, edx
0x1800016e2  mov     ebx, edx
0x1800016e4  mov     r12d, edx
0x1800016e7  mov     [rsp+190h+var_140], r12d
0x1800016ec  mov     rsi, rdx
0x1800016ef  mov     r15, rdx
0x1800016f2  mov     r14, rdx
0x1800016f5  mov     rdi, rdx
0x1800016f8  cmp     r12d, 3
0x1800016fc  jnb     loc_180001A1F
0x180001702  xorps   xmm0, xmm0
0x180001705  movups  [rbp+90h+var_A0], xmm0
0x180001709  mov     qword ptr [rbp+90h+var_A0+8], rdx
0x18000170d  movups  [rbp+90h+var_B0], xmm0
0x180001711  mov     qword ptr [rbp+90h+var_B0], rax
0x180001715  movups  [rbp+90h+var_90], xmm0
0x180001719  mov     dword ptr [rbp+90h+var_B0+8], r13d
0x18000171d  movups  [rbp+90h+var_80], xmm0
0x180001721  mov     dword ptr [rbp+90h+var_90], edx
0x180001724  movups  [rbp+90h+var_70], xmm0
0x180001728  mov     qword ptr [rbp+90h+var_90+8], rdx
0x18000172c  movups  [rbp+90h+var_60], xmm0
0x180001730  mov     dword ptr [rbp+90h+var_80], edx
0x180001733  mov     qword ptr [rbp+90h+var_80+8], rdx
0x180001737  mov     dword ptr [rbp+90h+var_70], edx
0x18000173a  mov     qword ptr [rbp+90h+var_70+8], rdx
0x18000173e  mov     dword ptr [rbp+90h+var_60], edx
0x180001741  mov     dword ptr [rbp+90h+var_A0], ecx
0x180001744  mov     dword ptr [rbp+90h+var_A0+4], 1
0x18000174b  mov     dword ptr [rbp+90h+var_60+8], edx
0x18000174e  movups  [rbp+90h+var_C0], xmm0
0x180001752  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x180001756  call    NsiOpenDevice
0x18000175b  mov     ebx, eax
0x18000175d  test    eax, eax
0x18000175f  jnz     loc_180001AFC
0x180001765  xor     r9d, r9d; lpName
0x180001768  xor     r8d, r8d; bInitialState
0x18000176b  xor     edx, edx; bManualReset
0x18000176d  xor     ecx, ecx; lpEventAttributes
0x18000176f  call    cs:__imp_CreateEventA
0x180001775  mov     rbx, rax
0x180001778  test    rax, rax
0x18000177b  jz      loc_180001C32
0x180001781  mov     rcx, cs:g_NsiAsyncDeviceHandle; FileHandle
0x180001788  lea     rax, [rbp+90h+var_C0]
0x18000178c  mov     [rsp+190h+OutputBufferLength], 70h ; 'p'; OutputBufferLength
0x180001794  xor     r9d, r9d; ApcContext
0x180001797  mov     [rsp+190h+OutputBuffer], rax; OutputBuffer
0x18000179c  xor     r8d, r8d; ApcRoutine
0x18000179f  mov     [rsp+190h+InputBufferLength], 70h ; 'p'; InputBufferLength
0x1800017a7  lea     rax, [rbp+90h+var_C0]
0x1800017ab  mov     [rsp+190h+InputBuffer], rax; InputBuffer
0x1800017b0  mov     rdx, rbx; Event
0x1800017b3  lea     rax, [rbp+90h+var_50]
0x1800017b7  mov     [rsp+190h+IoControlCode], 12001Bh; IoControlCode
0x1800017bf  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x1800017c4  call    cs:__imp_NtDeviceIoControlFile
0x1800017ca  mov     edi, eax
0x1800017cc  cmp     eax, 103h
0x1800017d1  jz      loc_180001C3D
0x1800017d7  mov     rcx, rbx; hObject
0x1800017da  call    cs:__imp_CloseHandle
0x1800017e0  test    edi, edi
0x1800017e2  js      loc_180001AEA
0x1800017e8  cmp     edi, 105h
0x1800017ee  jz      loc_180001AEA
0x1800017f4  xor     ebx, ebx
0x1800017f6  mov     ecx, dword ptr [rbp+90h+var_60+8]
0x1800017f9  mov     edx, 0Ah
0x1800017fe  mov     eax, ecx
0x180001800  shr     eax, 3
0x180001803  cmp     eax, 0Ah
0x180001806  cmovb   eax, edx
0x180001809  mov     edx, 0FFFFFFFFh
0x18000180e  add     eax, ecx
0x180001810  cmp     eax, ecx
0x180001812  cmovnb  edx, eax
0x180001815  mov     eax, [rbp+90h+arg_20]
0x18000181b  mov     [rsp+190h+var_13C], edx
0x18000181f  mov     r12d, edx
0x180001822  test    eax, eax
0x180001824  jz      loc_180001C58
0x18000182a  mul     r12
0x18000182d  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180001834  mov     [rsp+190h+var_138], 0
0x18000183d  test    rdx, rdx
0x180001840  cmovz   r8, rax; dwBytes
0x180001844  test    ebx, ebx
0x180001846  js      loc_180001B55
0x18000184c  mov     rcx, cs:g_NsiHeap; hHeap
0x180001853  xor     edx, edx; dwFlags
0x180001855  call    cs:__imp_HeapAlloc
0x18000185b  mov     rsi, rax
0x18000185e  test    rax, rax
0x180001861  jz      loc_180001B55
0x180001867  mov     eax, [rbp+90h+arg_30]
0x18000186d  xor     r15d, r15d
0x180001870  test    eax, eax
0x180001872  jnz     loc_180001B0C
0x180001878  mov     eax, [rbp+90h+arg_40]
0x18000187e  xor     r14d, r14d
0x180001881  test    eax, eax
0x180001883  jz      short loc_1800018B9
0x180001885  mul     r12
0x180001888  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000188f  test    rdx, rdx
0x180001892  cmovz   r8, rax; dwBytes
0x180001896  test    ebx, ebx
0x180001898  js      loc_180001A68
0x18000189e  mov     rcx, cs:g_NsiHeap; hHeap
0x1800018a5  xor     edx, edx; dwFlags
0x1800018a7  call    cs:__imp_HeapAlloc
0x1800018ad  mov     r14, rax
0x1800018b0  test    rax, rax
0x1800018b3  jz      loc_180001C85
0x1800018b9  mov     eax, [rbp+90h+arg_50]
0x1800018bf  xor     edi, edi
0x1800018c1  test    eax, eax
0x1800018c3  jz      short loc_1800018FA
0x1800018c5  mul     r12
0x1800018c8  test    rdx, rdx
0x1800018cb  jz      short loc_1800018D4
0x1800018cd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800018d4  test    ebx, ebx
0x1800018d6  js      loc_180001C07
0x1800018dc  mov     rcx, cs:g_NsiHeap; hHeap
0x1800018e3  mov     r8, rax; dwBytes
0x1800018e6  xor     edx, edx; dwFlags
0x1800018e8  call    cs:__imp_HeapAlloc
0x1800018ee  mov     rdi, rax
0x1800018f1  test    rax, rax
0x1800018f4  jz      loc_180001C87
0x1800018fa  mov     rax, [rbp+90h+arg_8]
0x180001901  xorps   xmm0, xmm0
0x180001904  movups  [rbp+90h+var_110], xmm0
0x180001908  mov     qword ptr [rbp+90h+var_110+8], rsi
0x18000190c  movups  [rsp+190h+var_120], xmm0
0x180001911  mov     qword ptr [rsp+190h+var_120], rax
0x180001916  mov     eax, [rbp+90h+arg_20]
0x18000191c  movups  [rbp+90h+var_100], xmm0
0x180001920  mov     dword ptr [rbp+90h+var_100], eax
0x180001923  mov     eax, [rbp+90h+arg_30]
0x180001929  movups  [rbp+90h+var_F0], xmm0
0x18000192d  mov     dword ptr [rbp+90h+var_F0], eax
0x180001930  mov     eax, [rbp+90h+arg_40]
0x180001936  movups  [rbp+90h+var_E0], xmm0
0x18000193a  mov     dword ptr [rbp+90h+var_E0], eax
0x18000193d  mov     eax, [rbp+90h+arg_50]
0x180001943  movups  [rbp+90h+var_D0], xmm0
0x180001947  mov     dword ptr [rbp+90h+var_D0], eax
0x18000194a  mov     eax, [rbp+90h+arg_0]
0x180001950  mov     dword ptr [rbp+90h+var_110], eax
0x180001953  mov     eax, [rsp+190h+var_13C]
0x180001957  mov     dword ptr [rbp+90h+var_D0+8], eax
0x18000195a  movups  [rsp+190h+var_130], xmm0
0x18000195f  mov     dword ptr [rsp+190h+var_120+8], r13d
0x180001964  mov     qword ptr [rbp+90h+var_100+8], r15
0x180001968  mov     qword ptr [rbp+90h+var_F0+8], r14
0x18000196c  mov     qword ptr [rbp+90h+var_E0+8], rdi
0x180001970  mov     dword ptr [rbp+90h+var_110+4], 1
0x180001977  movups  xmmword ptr [rbp+90h+var_40], xmm0
0x18000197b  call    NsiOpenDevice
0x180001980  mov     r12d, eax
0x180001983  test    eax, eax
0x180001985  jnz     loc_180001B6B
0x18000198b  xor     r9d, r9d; lpName
0x18000198e  xor     r8d, r8d; bInitialState
0x180001991  xor     edx, edx; bManualReset
0x180001993  xor     ecx, ecx; lpEventAttributes
0x180001995  call    cs:__imp_CreateEventA
0x18000199b  mov     r12, rax
0x18000199e  test    rax, rax
0x1800019a1  jz      loc_180001C5F
0x1800019a7  mov     rcx, cs:g_NsiAsyncDeviceHandle; FileHandle
0x1800019ae  lea     rax, [rsp+190h+var_130]
0x1800019b3  mov     [rsp+190h+OutputBufferLength], 70h ; 'p'; OutputBufferLength
0x1800019bb  xor     r9d, r9d; ApcContext
0x1800019be  mov     [rsp+190h+OutputBuffer], rax; OutputBuffer
0x1800019c3  xor     r8d, r8d; ApcRoutine
0x1800019c6  mov     [rsp+190h+InputBufferLength], 70h ; 'p'; InputBufferLength
0x1800019ce  lea     rax, [rsp+190h+var_130]
0x1800019d3  mov     [rsp+190h+InputBuffer], rax; InputBuffer
0x1800019d8  mov     rdx, r12; Event
0x1800019db  lea     rax, [rbp+90h+var_40]
0x1800019df  mov     [rsp+190h+IoControlCode], 12001Bh; IoControlCode
0x1800019e7  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x1800019ec  call    cs:__imp_NtDeviceIoControlFile
0x1800019f2  mov     ebx, eax
0x1800019f4  cmp     eax, 103h
0x1800019f9  jz      loc_180001C6A
0x1800019ff  mov     rcx, r12; hObject
0x180001a02  call    cs:__imp_CloseHandle
0x180001a08  test    ebx, ebx
0x180001a0a  js      loc_180001B60
0x180001a10  cmp     ebx, 105h
0x180001a16  jz      loc_180001B60
0x180001a1c  mov     ebx, dword ptr [rbp+90h+var_D0+8]
0x180001a1f  mov     rax, [rbp+90h+arg_58]
0x180001a26  mov     [rax], ebx
0x180001a28  test    rsi, rsi
0x180001a2b  jz      short loc_180001A37
0x180001a2d  mov     rax, [rbp+90h+arg_18]
0x180001a34  mov     [rax], rsi
0x180001a37  test    r15, r15
0x180001a3a  jz      short loc_180001A46
0x180001a3c  mov     rax, [rbp+90h+arg_28]
0x180001a43  mov     [rax], r15
0x180001a46  test    r14, r14
0x180001a49  jz      short loc_180001A55
0x180001a4b  mov     rax, [rbp+90h+arg_38]
0x180001a52  mov     [rax], r14
0x180001a55  test    rdi, rdi
0x180001a58  jz      short loc_180001A64
0x180001a5a  mov     rax, [rbp+90h+arg_48]
0x180001a61  mov     [rax], rdi
0x180001a64  xor     eax, eax
0x180001a66  jmp     short loc_180001ACF
0x180001a68  mov     r12d, 216h
0x180001a6e  xor     edi, edi
0x180001a70  test    rsi, rsi
0x180001a73  jz      short loc_180001A87
0x180001a75  mov     rcx, cs:g_NsiHeap; hHeap
0x180001a7c  mov     r8, rsi; lpMem
0x180001a7f  xor     edx, edx; dwFlags
0x180001a81  call    cs:__imp_HeapFree
0x180001a87  test    r15, r15
0x180001a8a  jz      short loc_180001A9E
0x180001a8c  mov     rcx, cs:g_NsiHeap; hHeap
0x180001a93  mov     r8, r15; lpMem
0x180001a96  xor     edx, edx; dwFlags
0x180001a98  call    cs:__imp_HeapFree
0x180001a9e  test    r14, r14
0x180001aa1  jz      short loc_180001AB5
0x180001aa3  mov     rcx, cs:g_NsiHeap; hHeap
0x180001aaa  mov     r8, r14; lpMem
0x180001aad  xor     edx, edx; dwFlags
0x180001aaf  call    cs:__imp_HeapFree
0x180001ab5  test    rdi, rdi
0x180001ab8  jz      short loc_180001ACC
0x180001aba  mov     rcx, cs:g_NsiHeap; hHeap
0x180001ac1  mov     r8, rdi; lpMem
0x180001ac4  xor     edx, edx; dwFlags
0x180001ac6  call    cs:__imp_HeapFree
0x180001acc  mov     eax, r12d
0x180001acf  mov     rbx, [rsp+190h+arg_10]
0x180001ad7  add     rsp, 160h
0x180001ade  pop     r15
0x180001ae0  pop     r14
0x180001ae2  pop     r13
0x180001ae4  pop     r12
0x180001ae6  pop     rdi
0x180001ae7  pop     rsi
0x180001ae8  pop     rbp
0x180001ae9  retn
0x180001aea  mov     ecx, edi; Status
0x180001aec  call    cs:__imp_RtlNtStatusToDosError
0x180001af2  mov     ebx, eax
0x180001af4  test    eax, eax
0x180001af6  jz      loc_1800017F6
0x180001afc  cmp     ebx, 0EAh
0x180001b02  jz      loc_1800017F6
0x180001b08  mov     eax, ebx
0x180001b0a  jmp     short loc_180001ACF
0x180001b0c  mul     r12
0x180001b0f  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180001b16  test    rdx, rdx
0x180001b19  cmovz   rdi, rax
0x180001b1d  test    ebx, ebx
0x180001b1f  js      loc_180001C12
0x180001b25  mov     rcx, cs:g_NsiHeap; hHeap
0x180001b2c  mov     r8, rdi; dwBytes
0x180001b2f  xor     edx, edx; dwFlags
0x180001b31  call    cs:__imp_HeapAlloc
0x180001b37  mov     r15, rax
0x180001b3a  test    rax, rax
0x180001b3d  jz      loc_180001C22
0x180001b43  mov     r8, rdi; Size
0x180001b46  xor     edx, edx; Val
0x180001b48  mov     rcx, rax; void *
0x180001b4b  call    memset_0
0x180001b50  jmp     loc_180001878
0x180001b55  mov     r12d, 216h
0x180001b5b  jmp     loc_180001ACC
0x180001b60  mov     ecx, ebx; Status
  ... truncated ...
```
