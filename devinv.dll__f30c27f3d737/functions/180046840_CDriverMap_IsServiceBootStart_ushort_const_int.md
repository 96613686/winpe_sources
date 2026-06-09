# CDriverMap::IsServiceBootStart(ushort const *,int &)

- ea: `0x180046840`
- end: `0x1800469f9`
- name: `?IsServiceBootStart@CDriverMap@@AEAAJPEBGAEAH@Z`
- size: `441`
- prototype: `__int64 __fastcall(CDriverMap *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800438cc`

## callees

- `0x180006210`
- `0x18000624c`
- `0x180006d02`
- `0x180007014`
- `0x180046840`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004687c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004687c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468f6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800469c6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800469c6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004686e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004686e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800468a7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800468e8`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800468a7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800468e8`

## string_xrefs

- `0x180046939`: `CDriverMap::IsServiceBootStart`
- `0x180046960`: `CDriverMap::IsServiceBootStart`

## pseudocode

```c
__int64 __fastcall CDriverMap::IsServiceBootStart(CDriverMap *this, const unsigned __int16 *a2, int *a3)
{
  SC_HANDLE v4; // rcx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rsi
  signed int v7; // eax
  unsigned int v8; // ebx
  struct _QUERY_SERVICE_CONFIGW *v9; // rdi
  signed int LastError; // eax
  struct _QUERY_SERVICE_CONFIGW *v11; // rax
  FILE *v12; // rax
  FILE *v13; // rax
  FILE *v14; // rax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp+8h] BYREF

  *a3 = 0;
  v4 = (SC_HANDLE)*((_QWORD *)this + 21);
  pcbBytesNeeded = 0;
  v5 = OpenServiceW(v4, a2, 0x80000000);
  v6 = v5;
  if ( v5 )
  {
    QueryServiceConfigW(v5, 0, 0, &pcbBytesNeeded);
    if ( GetLastError() == 122 )
    {
      while ( 1 )
      {
        pcbBytesNeeded *= 2;
        v11 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](
                                                 pcbBytesNeeded,
                                                 (const struct std::nothrow_t *)std::nothrow);
        v9 = v11;
        if ( !v11 )
          break;
        if ( QueryServiceConfigW(v6, v11, pcbBytesNeeded, &pcbBytesNeeded) )
        {
          *a3 = v9->dwStartType == 0;
          v8 = 0;
          goto LABEL_17;
        }
        if ( GetLastError() != 122 )
          goto LABEL_6;
        operator delete(v9);
      }
      AslLogCallPrintf(2, "CDriverMap::IsServiceBootStart", 1787, "Out of memory");
      if ( EnableDevInvStdErrLog )
      {
        v12 = o___acrt_iob_func_0(2u);
        fprintf(v12, "Error: %s, %u: ", "CDriverMap::IsServiceBootStart", 1787);
        v13 = o___acrt_iob_func_0(2u);
        fprintf(v13, "Out of memory");
        v14 = o___acrt_iob_func_0(2u);
        fprintf(v14, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "Out of memory");
      v8 = -2147024888;
    }
    else
    {
      v9 = 0;
LABEL_6:
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
LABEL_17:
    CloseServiceHandle(v6);
    if ( v9 )
      operator delete(v9);
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x180046840  mov     [rsp+arg_8], rbx
0x180046845  mov     [rsp+arg_10], rsi
0x18004684a  push    rdi
0x18004684b  sub     rsp, 20h
0x18004684f  mov     dword ptr [r8], 0
0x180046856  mov     rbx, r8
0x180046859  mov     rcx, [rcx+0A8h]; hSCManager
0x180046860  mov     r8d, 80000000h; dwDesiredAccess
0x180046866  mov     [rsp+28h+pcbBytesNeeded], 0
0x18004686e  call    cs:__imp_OpenServiceW
0x180046874  mov     rsi, rax
0x180046877  test    rax, rax
0x18004687a  jnz     short loc_18004689A
0x18004687c  call    cs:__imp_GetLastError
0x180046882  mov     ebx, eax
0x180046884  test    eax, eax
0x180046886  jle     loc_1800469D9
0x18004688c  movzx   ebx, ax
0x18004688f  or      ebx, 80070000h
0x180046895  jmp     loc_1800469D9
0x18004689a  lea     r9, [rsp+28h+pcbBytesNeeded]; pcbBytesNeeded
0x18004689f  xor     r8d, r8d; cbBufSize
0x1800468a2  xor     edx, edx; lpServiceConfig
0x1800468a4  mov     rcx, rsi; hService
0x1800468a7  call    cs:__imp_QueryServiceConfigW
0x1800468ad  call    cs:__imp_GetLastError
0x1800468b3  cmp     eax, 7Ah ; 'z'
0x1800468b6  jz      short loc_180046909
0x1800468b8  xor     edi, edi
0x1800468ba  call    cs:__imp_GetLastError
0x1800468c0  mov     ebx, eax
0x1800468c2  test    eax, eax
0x1800468c4  jle     loc_1800469C3
0x1800468ca  movzx   ebx, ax
0x1800468cd  or      ebx, 80070000h
0x1800468d3  jmp     loc_1800469C3
0x1800468d8  mov     r8d, [rsp+28h+pcbBytesNeeded]; cbBufSize
0x1800468dd  lea     r9, [rsp+28h+pcbBytesNeeded]; pcbBytesNeeded
0x1800468e2  mov     rdx, rdi; lpServiceConfig
0x1800468e5  mov     rcx, rsi; hService
0x1800468e8  call    cs:__imp_QueryServiceConfigW
0x1800468ee  test    eax, eax
0x1800468f0  jnz     loc_1800469EB
0x1800468f6  call    cs:__imp_GetLastError
0x1800468fc  cmp     eax, 7Ah ; 'z'
0x1800468ff  jnz     short loc_1800468BA
0x180046901  mov     rcx, rdi; Block
0x180046904  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180046909  mov     eax, [rsp+28h+pcbBytesNeeded]
0x18004690d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180046914  add     eax, eax
0x180046916  mov     ecx, eax; unsigned __int64
0x180046918  mov     [rsp+28h+pcbBytesNeeded], eax
0x18004691c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180046921  mov     rdi, rax
0x180046924  test    rax, rax
0x180046927  jnz     short loc_1800468D8
0x180046929  lea     rbx, aOutOfMemory_0; "Out of memory"
0x180046930  mov     r8d, 6FBh
0x180046936  mov     r9, rbx
0x180046939  lea     rdx, aCdrivermapIsse; "CDriverMap::IsServiceBootStart"
0x180046940  mov     ecx, 2
0x180046945  call    AslLogCallPrintf
0x18004694a  cmp     cs:EnableDevInvStdErrLog, 0
0x180046951  jz      short loc_1800469A7
0x180046953  mov     ecx, 2; Ix
0x180046958  call    _o___acrt_iob_func_0
0x18004695d  mov     rcx, rax; Stream
0x180046960  lea     r8, aCdrivermapIsse; "CDriverMap::IsServiceBootStart"
0x180046967  mov     r9d, 6FBh
0x18004696d  lea     rdx, Format; "Error: %s, %u: "
0x180046974  call    fprintf
0x180046979  mov     ecx, 2; Ix
0x18004697e  call    _o___acrt_iob_func_0
0x180046983  mov     rcx, rax; Stream
0x180046986  mov     rdx, rbx; Format
0x180046989  call    fprintf
0x18004698e  mov     ecx, 2; Ix
0x180046993  call    _o___acrt_iob_func_0
0x180046998  mov     rcx, rax; Stream
0x18004699b  lea     rdx, asc_18011EAD8; "\n"
0x1800469a2  call    fprintf
0x1800469a7  cmp     cs:g_DeviceMapLogFunction, 0
0x1800469af  jz      short loc_1800469BE
0x1800469b1  mov     rdx, rbx
0x1800469b4  mov     ecx, 2000000h
0x1800469b9  call    TraceMessageCallback
0x1800469be  mov     ebx, 80070008h
0x1800469c3  mov     rcx, rsi; hSCObject
0x1800469c6  call    cs:__imp_CloseServiceHandle
0x1800469cc  test    rdi, rdi
0x1800469cf  jz      short loc_1800469D9
0x1800469d1  mov     rcx, rdi; Block
0x1800469d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800469d9  mov     rsi, [rsp+28h+arg_10]
0x1800469de  mov     eax, ebx
0x1800469e0  mov     rbx, [rsp+28h+arg_8]
0x1800469e5  add     rsp, 20h
0x1800469e9  pop     rdi
0x1800469ea  retn
0x1800469eb  xor     eax, eax
0x1800469ed  cmp     [rdi+4], eax
0x1800469f0  setz    al
0x1800469f3  mov     [rbx], eax
0x1800469f5  xor     ebx, ebx
0x1800469f7  jmp     short loc_1800469C3
```
