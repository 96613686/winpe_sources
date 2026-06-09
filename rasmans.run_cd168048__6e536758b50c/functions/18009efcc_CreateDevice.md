# CreateDevice

- ea: `0x18009efcc`
- end: `0x18009f1e1`
- name: `CreateDevice`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18009f1e8`

## callees

- `0x18009efcc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f0a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f0a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009f08c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009f08c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f001`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f001`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f1a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f1a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f10d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f12d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f16a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f10d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f12d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f16a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f0f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f119`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f155`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f18c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f0f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f119`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f155`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f18c`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18009f071`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18009f071`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18009f0e0`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18009f0e0`

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
0x18009efcc  mov     [rsp-20h+arg_10], r8
0x18009efd1  push    rbp
0x18009efd2  push    rbx
0x18009efd3  push    rsi
0x18009efd4  push    rdi
0x18009efd5  mov     rbp, rsp
0x18009efd8  sub     rsp, 68h
0x18009efdc  xorps   xmm0, xmm0
0x18009efdf  mov     [rbp+arg_10], 0
0x18009efe7  mov     rsi, r9
0x18009efea  mov     rbx, rcx
0x18009efed  xor     r9d, r9d; lpName
0x18009eff0  xor     ecx, ecx; lpEventAttributes
0x18009eff2  xor     r8d, r8d; bInitialState
0x18009eff5  xor     edx, edx; bManualReset
0x18009eff7  movups  xmmword ptr [rbp+hHandle], xmm0
0x18009effb  xor     edi, edi
0x18009effd  movups  xmmword ptr [rbp+lpMem], xmm0
0x18009f001  call    cs:__imp_CreateEventW
0x18009f008  nop     dword ptr [rax+rax+00h]
0x18009f00d  mov     [rbp+hHandle], rax
0x18009f011  test    rax, rax
0x18009f014  jnz     short loc_18009F03A
0x18009f016  call    cs:__imp_GetLastError
0x18009f01d  nop     dword ptr [rax+rax+00h]
0x18009f022  mov     ebx, eax
0x18009f024  test    eax, eax
0x18009f026  jle     loc_18009F0D3
0x18009f02c  movzx   ebx, ax
0x18009f02f  or      ebx, 80070000h
0x18009f035  jmp     loc_18009F0D3
0x18009f03a  lea     rax, [rbp+arg_10]
0x18009f03e  xor     r9d, r9d
0x18009f041  mov     [rsp+68h+var_30], rax
0x18009f046  lea     rdx, aSwdMsrras5e259; "SWD\\MSRRAS\\{5e259276-bc7e-40e3-b93b-8"...
0x18009f04d  lea     rax, [rbp+hHandle]
0x18009f051  mov     r8, rbx
0x18009f054  mov     [rsp+68h+var_38], rax
0x18009f059  lea     rcx, aMsrras; "MSRRAS"
0x18009f060  lea     rax, RrasSwDeviceCreateCallback
0x18009f067  mov     [rsp+68h+var_40], rax
0x18009f06c  mov     [rsp+68h+var_48], rdi
0x18009f071  call    cs:__imp_SwDeviceCreate
0x18009f078  nop     dword ptr [rax+rax+00h]
0x18009f07d  mov     ebx, eax
0x18009f07f  test    eax, eax
0x18009f081  js      short loc_18009F0D7
0x18009f083  mov     rcx, [rbp+hHandle]; hHandle
0x18009f087  mov     edx, 7530h; dwMilliseconds
0x18009f08c  call    cs:__imp_WaitForSingleObject
0x18009f093  nop     dword ptr [rax+rax+00h]
0x18009f098  test    eax, eax
0x18009f09a  jz      short loc_18009F0C6
0x18009f09c  cmp     eax, 102h
0x18009f0a1  jz      loc_18009F182
0x18009f0a7  call    cs:__imp_GetLastError
0x18009f0ae  nop     dword ptr [rax+rax+00h]
0x18009f0b3  mov     ebx, eax
0x18009f0b5  test    eax, eax
0x18009f0b7  jle     short loc_18009F0C2
0x18009f0b9  movzx   ebx, ax
0x18009f0bc  or      ebx, 80070000h
0x18009f0c2  test    ebx, ebx
0x18009f0c4  js      short loc_18009F0D7
0x18009f0c6  mov     eax, dword ptr [rbp+lpMem]
0x18009f0c9  test    eax, eax
0x18009f0cb  jns     loc_18009F18C
0x18009f0d1  mov     ebx, eax
0x18009f0d3  test    ebx, ebx
0x18009f0d5  jns     short loc_18009F139
0x18009f0d7  mov     rcx, [rbp+arg_10]
0x18009f0db  test    rcx, rcx
0x18009f0de  jz      short loc_18009F0EC
0x18009f0e0  call    cs:__imp_SwDeviceClose
0x18009f0e7  nop     dword ptr [rax+rax+00h]
0x18009f0ec  test    rdi, rdi
0x18009f0ef  jz      short loc_18009F139
0x18009f0f1  mov     rsi, [rdi]
0x18009f0f4  test    rsi, rsi
0x18009f0f7  jz      short loc_18009F119
0x18009f0f9  call    cs:__imp_GetProcessHeap
0x18009f100  nop     dword ptr [rax+rax+00h]
0x18009f105  mov     r8, rsi; lpMem
0x18009f108  xor     edx, edx; dwFlags
0x18009f10a  mov     rcx, rax; hHeap
0x18009f10d  call    cs:__imp_HeapFree
0x18009f114  nop     dword ptr [rax+rax+00h]
0x18009f119  call    cs:__imp_GetProcessHeap
0x18009f120  nop     dword ptr [rax+rax+00h]
0x18009f125  mov     r8, rdi; lpMem
0x18009f128  xor     edx, edx; dwFlags
0x18009f12a  mov     rcx, rax; hHeap
0x18009f12d  call    cs:__imp_HeapFree
0x18009f134  nop     dword ptr [rax+rax+00h]
0x18009f139  mov     rcx, [rbp+hHandle]; hObject
0x18009f13d  test    rcx, rcx
0x18009f140  jz      short loc_18009F14E
0x18009f142  call    cs:__imp_CloseHandle
0x18009f149  nop     dword ptr [rax+rax+00h]
0x18009f14e  cmp     [rbp+lpMem+8], 0
0x18009f153  jz      short loc_18009F176
0x18009f155  call    cs:__imp_GetProcessHeap
0x18009f15c  nop     dword ptr [rax+rax+00h]
0x18009f161  mov     r8, [rbp+lpMem+8]; lpMem
0x18009f165  xor     edx, edx; dwFlags
0x18009f167  mov     rcx, rax; hHeap
0x18009f16a  call    cs:__imp_HeapFree
0x18009f171  nop     dword ptr [rax+rax+00h]
0x18009f176  mov     eax, ebx
0x18009f178  add     rsp, 68h
0x18009f17c  pop     rdi
0x18009f17d  pop     rsi
0x18009f17e  pop     rbx
0x18009f17f  pop     rbp
0x18009f180  retn
0x18009f182  mov     ebx, 800705B4h
0x18009f187  jmp     loc_18009F0D7
0x18009f18c  call    cs:__imp_GetProcessHeap
0x18009f193  nop     dword ptr [rax+rax+00h]
0x18009f198  mov     edx, 8; dwFlags
0x18009f19d  mov     rcx, rax; hHeap
0x18009f1a0  lea     r8d, [rdx+8]; dwBytes
0x18009f1a4  call    cs:__imp_HeapAlloc
0x18009f1ab  nop     dword ptr [rax+rax+00h]
0x18009f1b0  mov     rdi, rax
0x18009f1b3  test    rax, rax
0x18009f1b6  jnz     short loc_18009F1C2
0x18009f1b8  mov     ebx, 8007000Eh
0x18009f1bd  jmp     loc_18009F0D7
0x18009f1c2  mov     rax, [rbp+arg_10]
0x18009f1c6  mov     [rdi+8], rax
0x18009f1ca  mov     rax, [rbp+lpMem+8]
0x18009f1ce  mov     [rdi], rax
0x18009f1d1  mov     [rbp+lpMem+8], 0
0x18009f1d9  mov     [rsi], rdi
0x18009f1dc  jmp     loc_18009F139
```
