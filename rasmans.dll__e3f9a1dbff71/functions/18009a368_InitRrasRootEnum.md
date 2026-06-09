# InitRrasRootEnum

- ea: `0x18009a368`
- end: `0x18009a5dc`
- name: `InitRrasRootEnum`
- size: `628`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180099bf4`

## callees

- `0x18009a368`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009a475`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009a475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a547`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009a536`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009a536`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009a407`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009a407`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009a493`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009a493`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009a483`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009a585`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009a483`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009a585`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009a597`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009a597`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18009a43f`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18009a43f`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18009a4d0`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18009a4d0`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18009a45a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18009a45a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18009a51c`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18009a51c`

## pseudocode

```c
__int64 __fastcall InitRrasRootEnum(_QWORD *a1)
{
  signed int LastError; // eax
  signed int v3; // ebx
  HANDLE v4; // rax
  DWORD v6; // eax
  signed int v7; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v9; // rax
  DEVNODE pdnDevInst; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem[2]; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v14; // [rsp+78h] [rbp-88h]
  int v15; // [rsp+98h] [rbp-68h]
  const wchar_t *v16; // [rsp+A0h] [rbp-60h]
  WCHAR Buffer[200]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(&v13, 0, 0x48u);
  *(_OWORD *)hObject = 0;
  *(_OWORD *)lpMem = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  pdnDevInst = 0;
  v14 = L"{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}";
  g_RrasRootEnum = 0;
  v16 = L"Microsoft RRAS Root Enumerator";
  v13 = 72;
  v15 = 2;
  hObject[0] = CreateEventW(0, 0, 0, 0);
  if ( !hObject[0] )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
LABEL_22:
    if ( v3 >= 0 )
      goto LABEL_8;
    goto LABEL_6;
  }
  if ( CM_Locate_DevNodeW(&pdnDevInst, 0, 0) || CM_Get_Device_IDW(pdnDevInst, Buffer, 0xC8u, 0) )
  {
    v3 = -2147467259;
    goto LABEL_6;
  }
  v3 = SwDeviceCreate(L"MSRRAS", Buffer, &v13, 0, 0, &RrasSwDeviceCreateCallback, hObject, &g_RrasRootEnum);
  if ( v3 < 0 )
  {
LABEL_6:
    if ( g_RrasRootEnum )
    {
      SwDeviceClose();
      g_RrasRootEnum = 0;
    }
    goto LABEL_8;
  }
  v6 = WaitForSingleObject(hObject[0], 0x7530u);
  if ( v6 )
  {
    if ( v6 == 258 )
    {
      v3 = -2147023436;
      goto LABEL_6;
    }
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_6;
  }
  if ( SLODWORD(lpMem[0]) < 0 )
  {
    v3 = (signed int)lpMem[0];
    goto LABEL_22;
  }
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( !v9 )
  {
    v3 = -2147024882;
    goto LABEL_6;
  }
  v9[1] = g_RrasRootEnum;
  *v9 = lpMem[1];
  lpMem[1] = 0;
  if ( a1 )
    *a1 = v9;
LABEL_8:
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  if ( lpMem[1] )
  {
    v4 = GetProcessHeap();
    HeapFree(v4, 0, lpMem[1]);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18009a368  mov     [rsp-8+arg_8], rbx
0x18009a36d  mov     [rsp-8+arg_10], rdi
0x18009a372  push    rbp
0x18009a373  lea     rbp, [rsp-160h]
0x18009a37b  sub     rsp, 260h
0x18009a382  mov     rax, cs:__security_cookie
0x18009a389  xor     rax, rsp
0x18009a38c  mov     [rbp+160h+var_10], rax
0x18009a393  mov     rdi, rcx
0x18009a396  mov     ebx, 48h ; 'H'
0x18009a39b  mov     r8d, ebx; Size
0x18009a39e  lea     rcx, [rsp+260h+var_1F0]; void *
0x18009a3a3  xor     edx, edx; Val
0x18009a3a5  call    memset_0
0x18009a3aa  xorps   xmm0, xmm0
0x18009a3ad  lea     rcx, [rbp+160h+Buffer]; void *
0x18009a3b1  xor     edx, edx; Val
0x18009a3b3  mov     r8d, 190h; Size
0x18009a3b9  movups  xmmword ptr [rsp+260h+hObject], xmm0
0x18009a3be  movups  xmmword ptr [rsp+260h+lpMem], xmm0
0x18009a3c3  call    memset_0
0x18009a3c8  lea     rax, a5e259276Bc7e40; "{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}"
0x18009a3cf  mov     [rsp+260h+pdnDevInst], 0
0x18009a3d7  mov     [rsp+260h+var_1E8], rax
0x18009a3dc  xor     r9d, r9d; lpName
0x18009a3df  lea     rax, aMicrosoftRrasR; "Microsoft RRAS Root Enumerator"
0x18009a3e6  mov     cs:g_RrasRootEnum, 0
0x18009a3f1  xor     r8d, r8d; bInitialState
0x18009a3f4  mov     [rbp+160h+var_1C0], rax
0x18009a3f8  xor     edx, edx; bManualReset
0x18009a3fa  mov     [rsp+260h+var_1F0], ebx
0x18009a3fe  xor     ecx, ecx; lpEventAttributes
0x18009a400  mov     [rbp+160h+var_1C8], 2
0x18009a407  call    cs:__imp_CreateEventW
0x18009a40d  mov     [rsp+260h+hObject], rax
0x18009a412  test    rax, rax
0x18009a415  jnz     short loc_18009A435
0x18009a417  call    cs:__imp_GetLastError
0x18009a41d  mov     ebx, eax
0x18009a41f  test    eax, eax
0x18009a421  jle     loc_18009A56E
0x18009a427  movzx   ebx, ax
0x18009a42a  or      ebx, 80070000h
0x18009a430  jmp     loc_18009A56E
0x18009a435  xor     r8d, r8d; ulFlags
0x18009a438  lea     rcx, [rsp+260h+pdnDevInst]; pdnDevInst
0x18009a43d  xor     edx, edx; pDeviceID
0x18009a43f  call    cs:__imp_CM_Locate_DevNodeW
0x18009a445  test    eax, eax
0x18009a447  jz      short loc_18009A4BF
0x18009a449  mov     ebx, 80004005h
0x18009a44e  mov     rcx, cs:g_RrasRootEnum
0x18009a455  test    rcx, rcx
0x18009a458  jz      short loc_18009A46B
0x18009a45a  call    cs:__imp_SwDeviceClose
0x18009a460  mov     cs:g_RrasRootEnum, 0
0x18009a46b  mov     rcx, [rsp+260h+hObject]; hObject
0x18009a470  test    rcx, rcx
0x18009a473  jz      short loc_18009A47B
0x18009a475  call    cs:__imp_CloseHandle
0x18009a47b  cmp     [rsp+260h+lpMem+8], 0
0x18009a481  jz      short loc_18009A499
0x18009a483  call    cs:__imp_GetProcessHeap
0x18009a489  mov     r8, [rsp+260h+lpMem+8]; lpMem
0x18009a48e  xor     edx, edx; dwFlags
0x18009a490  mov     rcx, rax; hHeap
0x18009a493  call    cs:__imp_HeapFree
0x18009a499  mov     eax, ebx
0x18009a49b  mov     rcx, [rbp+160h+var_10]
0x18009a4a2  xor     rcx, rsp; StackCookie
0x18009a4a5  call    __security_check_cookie
0x18009a4aa  lea     r11, [rsp+260h+var_s0]
0x18009a4b2  mov     rbx, [r11+18h]
0x18009a4b6  mov     rdi, [r11+20h]
0x18009a4ba  mov     rsp, r11
0x18009a4bd  pop     rbp
0x18009a4be  retn
0x18009a4bf  mov     ecx, [rsp+260h+pdnDevInst]; dnDevInst
0x18009a4c3  lea     rdx, [rbp+160h+Buffer]; Buffer
0x18009a4c7  xor     r9d, r9d; ulFlags
0x18009a4ca  mov     r8d, 0C8h; BufferLen
0x18009a4d0  call    cs:__imp_CM_Get_Device_IDW
0x18009a4d6  test    eax, eax
0x18009a4d8  jnz     loc_18009A449
0x18009a4de  lea     rax, g_RrasRootEnum
0x18009a4e5  xor     r9d, r9d
0x18009a4e8  mov     [rsp+260h+var_228], rax
0x18009a4ed  lea     r8, [rsp+260h+var_1F0]
0x18009a4f2  lea     rax, [rsp+260h+hObject]
0x18009a4f7  mov     [rsp+260h+var_230], rax
0x18009a4fc  lea     rdx, [rbp+160h+Buffer]
0x18009a500  lea     rax, RrasSwDeviceCreateCallback
0x18009a507  mov     [rsp+260h+var_238], rax
0x18009a50c  lea     rcx, aMsrras; "MSRRAS"
0x18009a513  mov     [rsp+260h+var_240], 0
0x18009a51c  call    cs:__imp_SwDeviceCreate
0x18009a522  mov     ebx, eax
0x18009a524  test    eax, eax
0x18009a526  js      loc_18009A44E
0x18009a52c  mov     rcx, [rsp+260h+hObject]; hHandle
0x18009a531  mov     edx, 7530h; dwMilliseconds
0x18009a536  call    cs:__imp_WaitForSingleObject
0x18009a53c  test    eax, eax
0x18009a53e  jz      short loc_18009A564
0x18009a540  cmp     eax, 102h
0x18009a545  jz      short loc_18009A57B
0x18009a547  call    cs:__imp_GetLastError
0x18009a54d  mov     ebx, eax
0x18009a54f  test    eax, eax
0x18009a551  jle     short loc_18009A55C
0x18009a553  movzx   ebx, ax
0x18009a556  or      ebx, 80070000h
0x18009a55c  test    ebx, ebx
0x18009a55e  js      loc_18009A44E
0x18009a564  mov     eax, dword ptr [rsp+260h+lpMem]
0x18009a568  test    eax, eax
0x18009a56a  jns     short loc_18009A585
0x18009a56c  mov     ebx, eax
0x18009a56e  test    ebx, ebx
0x18009a570  jns     loc_18009A46B
0x18009a576  jmp     loc_18009A44E
0x18009a57b  mov     ebx, 800705B4h
0x18009a580  jmp     loc_18009A44E
0x18009a585  call    cs:__imp_GetProcessHeap
0x18009a58b  mov     edx, 8; dwFlags
0x18009a590  mov     rcx, rax; hHeap
0x18009a593  lea     r8d, [rdx+8]; dwBytes
0x18009a597  call    cs:__imp_HeapAlloc
0x18009a59d  mov     rcx, rax
0x18009a5a0  test    rax, rax
0x18009a5a3  jnz     short loc_18009A5AF
0x18009a5a5  mov     ebx, 8007000Eh
0x18009a5aa  jmp     loc_18009A44E
0x18009a5af  mov     rax, cs:g_RrasRootEnum
0x18009a5b6  mov     [rcx+8], rax
0x18009a5ba  mov     rax, [rsp+260h+lpMem+8]
0x18009a5bf  mov     [rcx], rax
0x18009a5c2  mov     [rsp+260h+lpMem+8], 0
0x18009a5cb  test    rdi, rdi
0x18009a5ce  jz      loc_18009A46B
0x18009a5d4  mov     [rdi], rcx
0x18009a5d7  jmp     loc_18009A46B
```
