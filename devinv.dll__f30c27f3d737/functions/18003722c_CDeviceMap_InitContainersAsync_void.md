# CDeviceMap::InitContainersAsync(void)

- ea: `0x18003722c`
- end: `0x180037454`
- name: `?InitContainersAsync@CDeviceMap@@AEAAJXZ`
- size: `552`
- prototype: `__int64 __fastcall(CDeviceMap *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180034d4c`

## callees

- `0x180006d02`
- `0x180007014`
- `0x180034788`
- `0x18003722c`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037251`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037251`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037367`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037431`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037431`

## string_xrefs

- `0x18003726c`: `CreateEvent failed`
- `0x18003738c`: `DevCreateObjectQuery failed with 0x%08x`
- `0x1800373e1`: `DevCreateObjectQuery failed with 0x%08x`
- `0x180037413`: `DevCreateObjectQuery failed with 0x%08x`

## pseudocode

```c
signed int __fastcall CDeviceMap::InitContainersAsync(CDeviceMap *this)
{
  HANDLE EventW; // rax
  __int64 v3; // r8
  FILE *v4; // rax
  FILE *v5; // rax
  FILE *v6; // rax
  signed int result; // eax
  int v8; // eax
  int v9; // esi
  void (__fastcall *v10)(__int64); // rax
  FILE *v11; // rax
  FILE *v12; // rax
  FILE *v13; // rax
  signed int v14; // ebx
  __int64 v15; // [rsp+60h] [rbp+8h] BYREF

  v15 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 100) = EventW;
  if ( EventW )
  {
    v8 = CDeviceMap::DevCreateObjectQuery(
           this,
           2,
           v3,
           18,
           &CDeviceContainer::s_PropertyKeys,
           0,
           0,
           CDeviceMap::EnumerateContainersCallback,
           this,
           &v15);
    v9 = v8;
    if ( v8 < 0 )
    {
      AslLogCallPrintf(2, "CDeviceMap::InitContainersAsync", 1648, "DevCreateObjectQuery failed with 0x%08x", v8);
      if ( EnableDevInvStdErrLog )
      {
        v11 = o___acrt_iob_func_0(2u);
        fprintf(v11, "Error: %s, %u: ", "CDeviceMap::InitContainersAsync", 1648);
        v12 = o___acrt_iob_func_0(2u);
        fprintf(v12, "DevCreateObjectQuery failed with 0x%08x", v9);
        v13 = o___acrt_iob_func_0(2u);
        fprintf(v13, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "DevCreateObjectQuery failed with 0x%08x", v9);
    }
    else
    {
      WaitForSingleObject(*((HANDLE *)this + 100), 0xFFFFFFFF);
      v10 = (void (__fastcall *)(__int64))*((_QWORD *)this + 86);
      if ( v10 )
        v10(v15);
    }
    v14 = *((_DWORD *)this + 198);
    CloseHandle(*((HANDLE *)this + 100));
    result = v14;
    *((_QWORD *)this + 100) = 0;
  }
  else
  {
    AslLogCallPrintf(2, "CDeviceMap::InitContainersAsync", 1625, "CreateEvent failed");
    if ( EnableDevInvStdErrLog )
    {
      v4 = o___acrt_iob_func_0(2u);
      fprintf(v4, "Error: %s, %u: ", "CDeviceMap::InitContainersAsync", 1625);
      v5 = o___acrt_iob_func_0(2u);
      fprintf(v5, "CreateEvent failed");
      v6 = o___acrt_iob_func_0(2u);
      fprintf(v6, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "CreateEvent failed");
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18003722c  mov     [rsp+arg_8], rbx
0x180037231  mov     [rsp+arg_10], rsi
0x180037236  push    rdi
0x180037237  sub     rsp, 50h
0x18003723b  mov     rdi, rcx
0x18003723e  mov     [rsp+58h+arg_0], 0
0x180037247  xor     ecx, ecx; lpEventAttributes
0x180037249  xor     r9d, r9d; lpName
0x18003724c  xor     r8d, r8d; bInitialState
0x18003724f  xor     edx, edx; bManualReset
0x180037251  call    cs:__imp_CreateEventW
0x180037257  mov     [rdi+320h], rax
0x18003725e  mov     ebx, 2
0x180037263  test    rax, rax
0x180037266  jnz     loc_18003730F
0x18003726c  lea     rdi, aCreateeventFai; "CreateEvent failed"
0x180037273  mov     esi, 659h
0x180037278  mov     r9, rdi
0x18003727b  lea     rdx, aCdevicemapInit_1; "CDeviceMap::InitContainersAsync"
0x180037282  mov     r8d, esi
0x180037285  mov     ecx, ebx
0x180037287  call    AslLogCallPrintf
0x18003728c  cmp     cs:EnableDevInvStdErrLog, 0
0x180037293  jz      short loc_1800372DD
0x180037295  mov     ecx, ebx; Ix
0x180037297  call    _o___acrt_iob_func_0
0x18003729c  mov     rcx, rax; Stream
0x18003729f  lea     r8, aCdevicemapInit_1; "CDeviceMap::InitContainersAsync"
0x1800372a6  mov     r9d, esi
0x1800372a9  lea     rdx, Format; "Error: %s, %u: "
0x1800372b0  call    fprintf
0x1800372b5  mov     ecx, ebx; Ix
0x1800372b7  call    _o___acrt_iob_func_0
0x1800372bc  mov     rcx, rax; Stream
0x1800372bf  mov     rdx, rdi; Format
0x1800372c2  call    fprintf
0x1800372c7  mov     ecx, ebx; Ix
0x1800372c9  call    _o___acrt_iob_func_0
0x1800372ce  mov     rcx, rax; Stream
0x1800372d1  lea     rdx, asc_18011EAD8; "\n"
0x1800372d8  call    fprintf
0x1800372dd  cmp     cs:g_DeviceMapLogFunction, 0
0x1800372e5  jz      short loc_1800372F4
0x1800372e7  mov     rdx, rdi
0x1800372ea  mov     ecx, 2000000h
0x1800372ef  call    TraceMessageCallback
0x1800372f4  call    cs:__imp_GetLastError
0x1800372fa  test    eax, eax
0x1800372fc  jle     loc_180037444
0x180037302  movzx   eax, ax
0x180037305  or      eax, 80070000h
0x18003730a  jmp     loc_180037444
0x18003730f  lea     rax, [rsp+58h+arg_0]
0x180037314  mov     r9d, 12h
0x18003731a  mov     [rsp+58h+var_10], rax
0x18003731f  mov     edx, ebx
0x180037321  mov     [rsp+58h+var_18], rdi
0x180037326  lea     rax, ?EnumerateContainersCallback@CDeviceMap@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; CDeviceMap::EnumerateContainersCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18003732d  mov     [rsp+58h+var_20], rax
0x180037332  mov     rcx, rdi
0x180037335  mov     [rsp+58h+var_28], 0
0x18003733e  lea     rax, ?s_PropertyKeys@CDeviceContainer@@0QBU_DEVPROPCOMPKEY@@B; _DEVPROPCOMPKEY const near * const CDeviceContainer::s_PropertyKeys
0x180037345  mov     [rsp+58h+var_30], 0
0x18003734d  mov     [rsp+58h+var_38], rax
0x180037352  call    ?DevCreateObjectQuery@CDeviceMap@@QEAAJW4_DEV_OBJECT_TYPE@@KKPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@P6AXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z4PEAPEAU5@@Z; CDeviceMap::DevCreateObjectQuery(_DEV_OBJECT_TYPE,ulong,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,void (*)(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *),void *,HDEVQUERY__ * *)
0x180037357  mov     esi, eax
0x180037359  test    eax, eax
0x18003735b  js      short loc_18003738C
0x18003735d  mov     rcx, [rdi+320h]; hHandle
0x180037364  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180037367  call    cs:__imp_WaitForSingleObject
0x18003736d  mov     rax, [rdi+2B0h]
0x180037374  test    rax, rax
0x180037377  jz      loc_180037424
0x18003737d  mov     rcx, [rsp+58h+arg_0]
0x180037382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037387  jmp     loc_180037424
0x18003738c  lea     r9, aDevcreateobjec; "DevCreateObjectQuery failed with 0x%08x"
0x180037393  mov     dword ptr [rsp+58h+var_38], esi
0x180037397  mov     r8d, 670h
0x18003739d  lea     rdx, aCdevicemapInit_1; "CDeviceMap::InitContainersAsync"
0x1800373a4  mov     ecx, ebx
0x1800373a6  call    AslLogCallPrintf
0x1800373ab  cmp     cs:EnableDevInvStdErrLog, 0
0x1800373b2  jz      short loc_180037406
0x1800373b4  mov     ecx, ebx; Ix
0x1800373b6  call    _o___acrt_iob_func_0
0x1800373bb  mov     rcx, rax; Stream
0x1800373be  lea     r8, aCdevicemapInit_1; "CDeviceMap::InitContainersAsync"
0x1800373c5  mov     r9d, 670h
0x1800373cb  lea     rdx, Format; "Error: %s, %u: "
0x1800373d2  call    fprintf
0x1800373d7  mov     ecx, ebx; Ix
0x1800373d9  call    _o___acrt_iob_func_0
0x1800373de  mov     rcx, rax; Stream
0x1800373e1  lea     rdx, aDevcreateobjec; "DevCreateObjectQuery failed with 0x%08x"
0x1800373e8  mov     r8d, esi
0x1800373eb  call    fprintf
0x1800373f0  mov     ecx, ebx; Ix
0x1800373f2  call    _o___acrt_iob_func_0
0x1800373f7  mov     rcx, rax; Stream
0x1800373fa  lea     rdx, asc_18011EAD8; "\n"
0x180037401  call    fprintf
0x180037406  cmp     cs:g_DeviceMapLogFunction, 0
0x18003740e  jz      short loc_180037424
0x180037410  mov     r8d, esi
0x180037413  lea     rdx, aDevcreateobjec; "DevCreateObjectQuery failed with 0x%08x"
0x18003741a  mov     ecx, 2000000h
0x18003741f  call    TraceMessageCallback
0x180037424  mov     rcx, [rdi+320h]; hObject
0x18003742b  mov     ebx, [rdi+318h]
0x180037431  call    cs:__imp_CloseHandle
0x180037437  mov     eax, ebx
0x180037439  mov     qword ptr [rdi+320h], 0
0x180037444  mov     rbx, [rsp+58h+arg_8]
0x180037449  mov     rsi, [rsp+58h+arg_10]
0x18003744e  add     rsp, 50h
0x180037452  pop     rdi
0x180037453  retn
```
