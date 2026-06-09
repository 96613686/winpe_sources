# CreateDevice

- ea: `0x180046094`
- end: `0x18004624e`
- name: `CreateDevice`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180046254`

## callees

- `0x180046094`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800461ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800461ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800460d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800460d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046157`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046217`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046217`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800461ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800461bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800461ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800461ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800461bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800461ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046142`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046142`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800460c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800460c9`
- `KERNEL32!GetProcessHeap` at `0x18004619d`
- `KERNEL32!GetProcessHeap` at `0x1800461b1`
- `KERNEL32!GetProcessHeap` at `0x1800461db`
- `KERNEL32!GetProcessHeap` at `0x180046205`
- `KERNEL32!GetProcessHeap` at `0x18004619d`
- `KERNEL32!GetProcessHeap` at `0x1800461b1`
- `KERNEL32!GetProcessHeap` at `0x1800461db`
- `KERNEL32!GetProcessHeap` at `0x180046205`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18004612d`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18004612d`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18004618a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18004618a`

## pseudocode

```c
__int64 __fastcall CreateDevice(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  signed int LastError; // eax
  signed int v7; // ebx
  DWORD v8; // eax
  signed int v9; // eax
  HANDLE v10; // rax
  HANDLE ProcessHeap; // rax
  _QWORD *v13; // rax
  HANDLE hHandle[2]; // [rsp+40h] [rbp-28h] BYREF
  LPVOID lpMem[2]; // [rsp+50h] [rbp-18h]
  __int64 v16; // [rsp+A0h] [rbp+38h] BYREF

  v16 = 0;
  *(_OWORD *)hHandle = 0;
  *(_OWORD *)lpMem = 0;
  hHandle[0] = CreateEventW(0, 0, 0, 0);
  if ( !hHandle[0] )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
    if ( v7 >= 0 )
      goto LABEL_15;
    goto LABEL_13;
  }
  v7 = SwDeviceCreate(
         L"MSRRAS",
         L"SWD\\MSRRAS\\{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}",
         a1,
         0,
         0,
         &RrasSwDeviceCreateCallback,
         hHandle,
         &v16);
  if ( v7 >= 0 )
  {
    v8 = WaitForSingleObject(hHandle[0], 0x7530u);
    if ( v8 )
    {
      if ( v8 == 258 )
      {
        v7 = -2147023436;
        goto LABEL_13;
      }
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      if ( v7 < 0 )
        goto LABEL_13;
    }
    if ( SLODWORD(lpMem[0]) < 0 )
    {
      v7 = (signed int)lpMem[0];
      goto LABEL_12;
    }
    ProcessHeap = GetProcessHeap();
    v13 = HeapAlloc(ProcessHeap, 8u, 0x10u);
    if ( v13 )
    {
      v13[1] = v16;
      *v13 = lpMem[1];
      lpMem[1] = 0;
      *a4 = v13;
      goto LABEL_15;
    }
    v7 = -2147024882;
  }
LABEL_13:
  if ( v16 )
    SwDeviceClose();
LABEL_15:
  if ( hHandle[0] )
    CloseHandle(hHandle[0]);
  if ( lpMem[1] )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, lpMem[1]);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180046094  mov     [rsp-20h+arg_10], r8
0x180046099  push    rbp
0x18004609a  push    rbx
0x18004609b  push    rsi
0x18004609c  push    rdi
0x18004609d  mov     rbp, rsp
0x1800460a0  sub     rsp, 68h
0x1800460a4  xorps   xmm0, xmm0
0x1800460a7  mov     [rbp+arg_10], 0
0x1800460af  mov     rsi, r9
0x1800460b2  mov     rbx, rcx
0x1800460b5  xor     r9d, r9d; lpName
0x1800460b8  xor     ecx, ecx; lpEventAttributes
0x1800460ba  xor     r8d, r8d; bInitialState
0x1800460bd  xor     edx, edx; bManualReset
0x1800460bf  movups  xmmword ptr [rbp+hHandle], xmm0
0x1800460c3  xor     edi, edi
0x1800460c5  movups  xmmword ptr [rbp+lpMem], xmm0
0x1800460c9  call    cs:__imp_CreateEventW
0x1800460cf  mov     [rbp+hHandle], rax
0x1800460d3  test    rax, rax
0x1800460d6  jnz     short loc_1800460F6
0x1800460d8  call    cs:__imp_GetLastError
0x1800460de  mov     ebx, eax
0x1800460e0  test    eax, eax
0x1800460e2  jle     loc_18004617D
0x1800460e8  movzx   ebx, ax
0x1800460eb  or      ebx, 80070000h
0x1800460f1  jmp     loc_18004617D
0x1800460f6  lea     rax, [rbp+arg_10]
0x1800460fa  xor     r9d, r9d
0x1800460fd  mov     [rsp+68h+var_30], rax
0x180046102  lea     rdx, aSwdMsrras5e259; "SWD\\MSRRAS\\{5e259276-bc7e-40e3-b93b-8"...
0x180046109  lea     rax, [rbp+hHandle]
0x18004610d  mov     r8, rbx
0x180046110  mov     [rsp+68h+var_38], rax
0x180046115  lea     rcx, aMsrras; "MSRRAS"
0x18004611c  lea     rax, RrasSwDeviceCreateCallback
0x180046123  mov     [rsp+68h+var_40], rax
0x180046128  mov     [rsp+68h+var_48], rdi
0x18004612d  call    cs:__imp_SwDeviceCreate
0x180046133  mov     ebx, eax
0x180046135  test    eax, eax
0x180046137  js      short loc_180046181
0x180046139  mov     rcx, [rbp+hHandle]; hHandle
0x18004613d  mov     edx, 7530h; dwMilliseconds
0x180046142  call    cs:__imp_WaitForSingleObject
0x180046148  test    eax, eax
0x18004614a  jz      short loc_180046170
0x18004614c  cmp     eax, 102h
0x180046151  jz      loc_1800461FB
0x180046157  call    cs:__imp_GetLastError
0x18004615d  mov     ebx, eax
0x18004615f  test    eax, eax
0x180046161  jle     short loc_18004616C
0x180046163  movzx   ebx, ax
0x180046166  or      ebx, 80070000h
0x18004616c  test    ebx, ebx
0x18004616e  js      short loc_180046181
0x180046170  mov     eax, dword ptr [rbp+lpMem]
0x180046173  test    eax, eax
0x180046175  jns     loc_180046205
0x18004617b  mov     ebx, eax
0x18004617d  test    ebx, ebx
0x18004617f  jns     short loc_1800461C5
0x180046181  mov     rcx, [rbp+arg_10]
0x180046185  test    rcx, rcx
0x180046188  jz      short loc_180046190
0x18004618a  call    cs:__imp_SwDeviceClose
0x180046190  test    rdi, rdi
0x180046193  jz      short loc_1800461C5
0x180046195  mov     rsi, [rdi]
0x180046198  test    rsi, rsi
0x18004619b  jz      short loc_1800461B1
0x18004619d  call    cs:__imp_GetProcessHeap
0x1800461a3  mov     r8, rsi; lpMem
0x1800461a6  xor     edx, edx; dwFlags
0x1800461a8  mov     rcx, rax; hHeap
0x1800461ab  call    cs:__imp_HeapFree
0x1800461b1  call    cs:__imp_GetProcessHeap
0x1800461b7  mov     r8, rdi; lpMem
0x1800461ba  xor     edx, edx; dwFlags
0x1800461bc  mov     rcx, rax; hHeap
0x1800461bf  call    cs:__imp_HeapFree
0x1800461c5  mov     rcx, [rbp+hHandle]; hObject
0x1800461c9  test    rcx, rcx
0x1800461cc  jz      short loc_1800461D4
0x1800461ce  call    cs:__imp_CloseHandle
0x1800461d4  cmp     [rbp+lpMem+8], 0
0x1800461d9  jz      short loc_1800461F0
0x1800461db  call    cs:__imp_GetProcessHeap
0x1800461e1  mov     r8, [rbp+lpMem+8]; lpMem
0x1800461e5  xor     edx, edx; dwFlags
0x1800461e7  mov     rcx, rax; hHeap
0x1800461ea  call    cs:__imp_HeapFree
0x1800461f0  mov     eax, ebx
0x1800461f2  add     rsp, 68h
0x1800461f6  pop     rdi
0x1800461f7  pop     rsi
0x1800461f8  pop     rbx
0x1800461f9  pop     rbp
0x1800461fa  retn
0x1800461fb  mov     ebx, 800705B4h
0x180046200  jmp     loc_180046181
0x180046205  call    cs:__imp_GetProcessHeap
0x18004620b  mov     edx, 8; dwFlags
0x180046210  mov     rcx, rax; hHeap
0x180046213  lea     r8d, [rdx+8]; dwBytes
0x180046217  call    cs:__imp_HeapAlloc
0x18004621d  mov     rdi, rax
0x180046220  test    rax, rax
0x180046223  jnz     short loc_18004622F
0x180046225  mov     ebx, 8007000Eh
0x18004622a  jmp     loc_180046181
0x18004622f  mov     rax, [rbp+arg_10]
0x180046233  mov     [rdi+8], rax
0x180046237  mov     rax, [rbp+lpMem+8]
0x18004623b  mov     [rdi], rax
0x18004623e  mov     [rbp+lpMem+8], 0
0x180046246  mov     [rsi], rdi
0x180046249  jmp     loc_1800461C5
```
