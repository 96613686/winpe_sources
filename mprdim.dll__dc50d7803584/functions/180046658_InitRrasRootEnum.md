# InitRrasRootEnum

- ea: `0x180046658`
- end: `0x1800468cc`
- name: `InitRrasRootEnum`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045ee8`

## callees

- `0x180046658`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046765`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046837`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046887`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046887`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046783`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046783`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046826`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046826`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800466f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800466f7`
- `KERNEL32!GetProcessHeap` at `0x180046773`
- `KERNEL32!GetProcessHeap` at `0x180046875`
- `KERNEL32!GetProcessHeap` at `0x180046773`
- `KERNEL32!GetProcessHeap` at `0x180046875`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18004680c`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18004680c`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18004674a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18004674a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x1800467c0`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x1800467c0`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18004672f`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18004672f`

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
0x180046658  mov     [rsp-8+arg_8], rbx
0x18004665d  mov     [rsp-8+arg_10], rdi
0x180046662  push    rbp
0x180046663  lea     rbp, [rsp-160h]
0x18004666b  sub     rsp, 260h
0x180046672  mov     rax, cs:__security_cookie
0x180046679  xor     rax, rsp
0x18004667c  mov     [rbp+160h+var_10], rax
0x180046683  mov     rdi, rcx
0x180046686  mov     ebx, 48h ; 'H'
0x18004668b  mov     r8d, ebx; Size
0x18004668e  lea     rcx, [rsp+260h+var_1F0]; void *
0x180046693  xor     edx, edx; Val
0x180046695  call    memset_0
0x18004669a  xorps   xmm0, xmm0
0x18004669d  lea     rcx, [rbp+160h+Buffer]; void *
0x1800466a1  xor     edx, edx; Val
0x1800466a3  mov     r8d, 190h; Size
0x1800466a9  movups  xmmword ptr [rsp+260h+hObject], xmm0
0x1800466ae  movups  xmmword ptr [rsp+260h+lpMem], xmm0
0x1800466b3  call    memset_0
0x1800466b8  lea     rax, a5e259276Bc7e40; "{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}"
0x1800466bf  mov     [rsp+260h+pdnDevInst], 0
0x1800466c7  mov     [rsp+260h+var_1E8], rax
0x1800466cc  xor     r9d, r9d; lpName
0x1800466cf  lea     rax, aMicrosoftRrasR; "Microsoft RRAS Root Enumerator"
0x1800466d6  mov     cs:g_RrasRootEnum, 0
0x1800466e1  xor     r8d, r8d; bInitialState
0x1800466e4  mov     [rbp+160h+var_1C0], rax
0x1800466e8  xor     edx, edx; bManualReset
0x1800466ea  mov     [rsp+260h+var_1F0], ebx
0x1800466ee  xor     ecx, ecx; lpEventAttributes
0x1800466f0  mov     [rbp+160h+var_1C8], 2
0x1800466f7  call    cs:__imp_CreateEventW
0x1800466fd  mov     [rsp+260h+hObject], rax
0x180046702  test    rax, rax
0x180046705  jnz     short loc_180046725
0x180046707  call    cs:__imp_GetLastError
0x18004670d  mov     ebx, eax
0x18004670f  test    eax, eax
0x180046711  jle     loc_18004685E
0x180046717  movzx   ebx, ax
0x18004671a  or      ebx, 80070000h
0x180046720  jmp     loc_18004685E
0x180046725  xor     r8d, r8d; ulFlags
0x180046728  lea     rcx, [rsp+260h+pdnDevInst]; pdnDevInst
0x18004672d  xor     edx, edx; pDeviceID
0x18004672f  call    cs:__imp_CM_Locate_DevNodeW
0x180046735  test    eax, eax
0x180046737  jz      short loc_1800467AF
0x180046739  mov     ebx, 80004005h
0x18004673e  mov     rcx, cs:g_RrasRootEnum
0x180046745  test    rcx, rcx
0x180046748  jz      short loc_18004675B
0x18004674a  call    cs:__imp_SwDeviceClose
0x180046750  mov     cs:g_RrasRootEnum, 0
0x18004675b  mov     rcx, [rsp+260h+hObject]; hObject
0x180046760  test    rcx, rcx
0x180046763  jz      short loc_18004676B
0x180046765  call    cs:__imp_CloseHandle
0x18004676b  cmp     [rsp+260h+lpMem+8], 0
0x180046771  jz      short loc_180046789
0x180046773  call    cs:__imp_GetProcessHeap
0x180046779  mov     r8, [rsp+260h+lpMem+8]; lpMem
0x18004677e  xor     edx, edx; dwFlags
0x180046780  mov     rcx, rax; hHeap
0x180046783  call    cs:__imp_HeapFree
0x180046789  mov     eax, ebx
0x18004678b  mov     rcx, [rbp+160h+var_10]
0x180046792  xor     rcx, rsp; StackCookie
0x180046795  call    __security_check_cookie
0x18004679a  lea     r11, [rsp+260h+var_s0]
0x1800467a2  mov     rbx, [r11+18h]
0x1800467a6  mov     rdi, [r11+20h]
0x1800467aa  mov     rsp, r11
0x1800467ad  pop     rbp
0x1800467ae  retn
0x1800467af  mov     ecx, [rsp+260h+pdnDevInst]; dnDevInst
0x1800467b3  lea     rdx, [rbp+160h+Buffer]; Buffer
0x1800467b7  xor     r9d, r9d; ulFlags
0x1800467ba  mov     r8d, 0C8h; BufferLen
0x1800467c0  call    cs:__imp_CM_Get_Device_IDW
0x1800467c6  test    eax, eax
0x1800467c8  jnz     loc_180046739
0x1800467ce  lea     rax, g_RrasRootEnum
0x1800467d5  xor     r9d, r9d
0x1800467d8  mov     [rsp+260h+var_228], rax
0x1800467dd  lea     r8, [rsp+260h+var_1F0]
0x1800467e2  lea     rax, [rsp+260h+hObject]
0x1800467e7  mov     [rsp+260h+var_230], rax
0x1800467ec  lea     rdx, [rbp+160h+Buffer]
0x1800467f0  lea     rax, RrasSwDeviceCreateCallback
0x1800467f7  mov     [rsp+260h+var_238], rax
0x1800467fc  lea     rcx, aMsrras; "MSRRAS"
0x180046803  mov     [rsp+260h+var_240], 0
0x18004680c  call    cs:__imp_SwDeviceCreate
0x180046812  mov     ebx, eax
0x180046814  test    eax, eax
0x180046816  js      loc_18004673E
0x18004681c  mov     rcx, [rsp+260h+hObject]; hHandle
0x180046821  mov     edx, 7530h; dwMilliseconds
0x180046826  call    cs:__imp_WaitForSingleObject
0x18004682c  test    eax, eax
0x18004682e  jz      short loc_180046854
0x180046830  cmp     eax, 102h
0x180046835  jz      short loc_18004686B
0x180046837  call    cs:__imp_GetLastError
0x18004683d  mov     ebx, eax
0x18004683f  test    eax, eax
0x180046841  jle     short loc_18004684C
0x180046843  movzx   ebx, ax
0x180046846  or      ebx, 80070000h
0x18004684c  test    ebx, ebx
0x18004684e  js      loc_18004673E
0x180046854  mov     eax, dword ptr [rsp+260h+lpMem]
0x180046858  test    eax, eax
0x18004685a  jns     short loc_180046875
0x18004685c  mov     ebx, eax
0x18004685e  test    ebx, ebx
0x180046860  jns     loc_18004675B
0x180046866  jmp     loc_18004673E
0x18004686b  mov     ebx, 800705B4h
0x180046870  jmp     loc_18004673E
0x180046875  call    cs:__imp_GetProcessHeap
0x18004687b  mov     edx, 8; dwFlags
0x180046880  mov     rcx, rax; hHeap
0x180046883  lea     r8d, [rdx+8]; dwBytes
0x180046887  call    cs:__imp_HeapAlloc
0x18004688d  mov     rcx, rax
0x180046890  test    rax, rax
0x180046893  jnz     short loc_18004689F
0x180046895  mov     ebx, 8007000Eh
0x18004689a  jmp     loc_18004673E
0x18004689f  mov     rax, cs:g_RrasRootEnum
0x1800468a6  mov     [rcx+8], rax
0x1800468aa  mov     rax, [rsp+260h+lpMem+8]
0x1800468af  mov     [rcx], rax
0x1800468b2  mov     [rsp+260h+lpMem+8], 0
0x1800468bb  test    rdi, rdi
0x1800468be  jz      loc_18004675B
0x1800468c4  mov     [rdi], rcx
0x1800468c7  jmp     loc_18004675B
```
