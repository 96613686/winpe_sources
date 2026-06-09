# InitRrasRootEnum

- ea: `0x18009f624`
- end: `0x18009f8eb`
- name: `InitRrasRootEnum`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009edf8`

## callees

- `0x18009f624`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f74d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f6d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f6d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f844`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009f82d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009f82d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f6c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f6c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f8a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f8a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f777`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f777`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f761`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f888`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f761`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f888`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18009f7bb`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18009f7bb`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18009f707`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18009f707`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18009f80d`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18009f80d`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18009f72c`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18009f72c`

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
0x18009f624  mov     [rsp-8+arg_8], rbx
0x18009f629  mov     [rsp-8+arg_10], rdi
0x18009f62e  push    rbp
0x18009f62f  lea     rbp, [rsp-160h]
0x18009f637  sub     rsp, 260h
0x18009f63e  mov     rax, cs:__security_cookie
0x18009f645  xor     rax, rsp
0x18009f648  mov     [rbp+160h+var_10], rax
0x18009f64f  mov     rdi, rcx
0x18009f652  mov     ebx, 48h ; 'H'
0x18009f657  mov     r8d, ebx; Size
0x18009f65a  lea     rcx, [rsp+260h+var_1F0]; void *
0x18009f65f  xor     edx, edx; Val
0x18009f661  call    memset_0
0x18009f666  xorps   xmm0, xmm0
0x18009f669  lea     rcx, [rbp+160h+Buffer]; void *
0x18009f66d  xor     edx, edx; Val
0x18009f66f  mov     r8d, 190h; Size
0x18009f675  movups  xmmword ptr [rsp+260h+hObject], xmm0
0x18009f67a  movups  xmmword ptr [rsp+260h+lpMem], xmm0
0x18009f67f  call    memset_0
0x18009f684  lea     rax, a5e259276Bc7e40; "{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}"
0x18009f68b  mov     [rsp+260h+pdnDevInst], 0
0x18009f693  mov     [rsp+260h+var_1E8], rax
0x18009f698  xor     r9d, r9d; lpName
0x18009f69b  lea     rax, aMicrosoftRrasR; "Microsoft RRAS Root Enumerator"
0x18009f6a2  mov     cs:g_RrasRootEnum, 0
0x18009f6ad  xor     r8d, r8d; bInitialState
0x18009f6b0  mov     [rbp+160h+var_1C0], rax
0x18009f6b4  xor     edx, edx; bManualReset
0x18009f6b6  mov     [rsp+260h+var_1F0], ebx
0x18009f6ba  xor     ecx, ecx; lpEventAttributes
0x18009f6bc  mov     [rbp+160h+var_1C8], 2
0x18009f6c3  call    cs:__imp_CreateEventW
0x18009f6ca  nop     dword ptr [rax+rax+00h]
0x18009f6cf  mov     [rsp+260h+hObject], rax
0x18009f6d4  test    rax, rax
0x18009f6d7  jnz     short loc_18009F6FD
0x18009f6d9  call    cs:__imp_GetLastError
0x18009f6e0  nop     dword ptr [rax+rax+00h]
0x18009f6e5  mov     ebx, eax
0x18009f6e7  test    eax, eax
0x18009f6e9  jle     loc_18009F871
0x18009f6ef  movzx   ebx, ax
0x18009f6f2  or      ebx, 80070000h
0x18009f6f8  jmp     loc_18009F871
0x18009f6fd  xor     r8d, r8d; ulFlags
0x18009f700  lea     rcx, [rsp+260h+pdnDevInst]; pdnDevInst
0x18009f705  xor     edx, edx; pDeviceID
0x18009f707  call    cs:__imp_CM_Locate_DevNodeW
0x18009f70e  nop     dword ptr [rax+rax+00h]
0x18009f713  test    eax, eax
0x18009f715  jz      loc_18009F7AA
0x18009f71b  mov     ebx, 80004005h
0x18009f720  mov     rcx, cs:g_RrasRootEnum
0x18009f727  test    rcx, rcx
0x18009f72a  jz      short loc_18009F743
0x18009f72c  call    cs:__imp_SwDeviceClose
0x18009f733  nop     dword ptr [rax+rax+00h]
0x18009f738  mov     cs:g_RrasRootEnum, 0
0x18009f743  mov     rcx, [rsp+260h+hObject]; hObject
0x18009f748  test    rcx, rcx
0x18009f74b  jz      short loc_18009F759
0x18009f74d  call    cs:__imp_CloseHandle
0x18009f754  nop     dword ptr [rax+rax+00h]
0x18009f759  cmp     [rsp+260h+lpMem+8], 0
0x18009f75f  jz      short loc_18009F783
0x18009f761  call    cs:__imp_GetProcessHeap
0x18009f768  nop     dword ptr [rax+rax+00h]
0x18009f76d  mov     r8, [rsp+260h+lpMem+8]; lpMem
0x18009f772  xor     edx, edx; dwFlags
0x18009f774  mov     rcx, rax; hHeap
0x18009f777  call    cs:__imp_HeapFree
0x18009f77e  nop     dword ptr [rax+rax+00h]
0x18009f783  mov     eax, ebx
0x18009f785  mov     rcx, [rbp+160h+var_10]
0x18009f78c  xor     rcx, rsp; StackCookie
0x18009f78f  call    __security_check_cookie
0x18009f794  lea     r11, [rsp+260h+var_s0]
0x18009f79c  mov     rbx, [r11+18h]
0x18009f7a0  mov     rdi, [r11+20h]
0x18009f7a4  mov     rsp, r11
0x18009f7a7  pop     rbp
0x18009f7a8  retn
0x18009f7aa  mov     ecx, [rsp+260h+pdnDevInst]; dnDevInst
0x18009f7ae  lea     rdx, [rbp+160h+Buffer]; Buffer
0x18009f7b2  xor     r9d, r9d; ulFlags
0x18009f7b5  mov     r8d, 0C8h; BufferLen
0x18009f7bb  call    cs:__imp_CM_Get_Device_IDW
0x18009f7c2  nop     dword ptr [rax+rax+00h]
0x18009f7c7  test    eax, eax
0x18009f7c9  jnz     loc_18009F71B
0x18009f7cf  lea     rax, g_RrasRootEnum
0x18009f7d6  xor     r9d, r9d
0x18009f7d9  mov     [rsp+260h+var_228], rax
0x18009f7de  lea     r8, [rsp+260h+var_1F0]
0x18009f7e3  lea     rax, [rsp+260h+hObject]
0x18009f7e8  mov     [rsp+260h+var_230], rax
0x18009f7ed  lea     rdx, [rbp+160h+Buffer]
0x18009f7f1  lea     rax, RrasSwDeviceCreateCallback
0x18009f7f8  mov     [rsp+260h+var_238], rax
0x18009f7fd  lea     rcx, aMsrras; "MSRRAS"
0x18009f804  mov     [rsp+260h+var_240], 0
0x18009f80d  call    cs:__imp_SwDeviceCreate
0x18009f814  nop     dword ptr [rax+rax+00h]
0x18009f819  mov     ebx, eax
0x18009f81b  test    eax, eax
0x18009f81d  js      loc_18009F720
0x18009f823  mov     rcx, [rsp+260h+hObject]; hHandle
0x18009f828  mov     edx, 7530h; dwMilliseconds
0x18009f82d  call    cs:__imp_WaitForSingleObject
0x18009f834  nop     dword ptr [rax+rax+00h]
0x18009f839  test    eax, eax
0x18009f83b  jz      short loc_18009F867
0x18009f83d  cmp     eax, 102h
0x18009f842  jz      short loc_18009F87E
0x18009f844  call    cs:__imp_GetLastError
0x18009f84b  nop     dword ptr [rax+rax+00h]
0x18009f850  mov     ebx, eax
0x18009f852  test    eax, eax
0x18009f854  jle     short loc_18009F85F
0x18009f856  movzx   ebx, ax
0x18009f859  or      ebx, 80070000h
0x18009f85f  test    ebx, ebx
0x18009f861  js      loc_18009F720
0x18009f867  mov     eax, dword ptr [rsp+260h+lpMem]
0x18009f86b  test    eax, eax
0x18009f86d  jns     short loc_18009F888
0x18009f86f  mov     ebx, eax
0x18009f871  test    ebx, ebx
0x18009f873  jns     loc_18009F743
0x18009f879  jmp     loc_18009F720
0x18009f87e  mov     ebx, 800705B4h
0x18009f883  jmp     loc_18009F720
0x18009f888  call    cs:__imp_GetProcessHeap
0x18009f88f  nop     dword ptr [rax+rax+00h]
0x18009f894  mov     edx, 8; dwFlags
0x18009f899  mov     rcx, rax; hHeap
0x18009f89c  lea     r8d, [rdx+8]; dwBytes
0x18009f8a0  call    cs:__imp_HeapAlloc
0x18009f8a7  nop     dword ptr [rax+rax+00h]
0x18009f8ac  mov     rcx, rax
0x18009f8af  test    rax, rax
0x18009f8b2  jnz     short loc_18009F8BE
0x18009f8b4  mov     ebx, 8007000Eh
0x18009f8b9  jmp     loc_18009F720
0x18009f8be  mov     rax, cs:g_RrasRootEnum
0x18009f8c5  mov     [rcx+8], rax
0x18009f8c9  mov     rax, [rsp+260h+lpMem+8]
0x18009f8ce  mov     [rcx], rax
0x18009f8d1  mov     [rsp+260h+lpMem+8], 0
0x18009f8da  test    rdi, rdi
0x18009f8dd  jz      loc_18009F743
0x18009f8e3  mov     [rdi], rcx
0x18009f8e6  jmp     loc_18009F743
```
