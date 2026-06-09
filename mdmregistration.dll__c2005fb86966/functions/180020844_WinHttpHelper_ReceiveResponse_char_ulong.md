# WinHttpHelper::ReceiveResponse(char * *,ulong *)

- ea: `0x180020844`
- end: `0x180020bf2`
- name: `?ReceiveResponse@WinHttpHelper@@QEAAJPEAPEADPEAK@Z`
- size: `942`
- prototype: `__int64 __fastcall(WinHttpHelper *__hidden this, char **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001f594`
- `0x180021458`

## callees

- `0x1800026d0`
- `0x180012f70`
- `0x1800141b0`
- `0x180020844`
- `0x18004b988`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002091e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800209d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002091e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800209d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800209ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020a41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020ae9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020b0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800209ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020a41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020ae9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020b0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020907`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800209c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800209eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ad5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020afa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020907`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800209c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800209eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ad5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020afa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bdf`
- `WINHTTP!WinHttpReadData` at `0x180020945`
- `WINHTTP!WinHttpReadData` at `0x180020945`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800208c5`
- `WINHTTP!WinHttpQueryHeaders` at `0x180020a84`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800208c5`
- `WINHTTP!WinHttpQueryHeaders` at `0x180020a84`

## pseudocode

```c
__int64 __fastcall WinHttpHelper::ReceiveResponse(WinHttpHelper *this, char **a2, unsigned int *a3)
{
  void *v6; // rdi
  unsigned int v7; // esi
  void *v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  void *v12; // rax
  void *v13; // rbx
  __int64 v14; // r8
  int v15; // esi
  HANDLE v16; // rax
  void *v17; // rsi
  HANDLE v18; // rax
  HANDLE v19; // rax
  int v20; // esi
  unsigned int LastError; // esi
  HANDLE v22; // rax
  HANDLE v23; // rax
  unsigned int v25; // [rsp+30h] [rbp-50h] BYREF
  int Buffer; // [rsp+34h] [rbp-4Ch] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+38h] [rbp-48h] BYREF
  DWORD dwBufferLength; // [rsp+3Ch] [rbp-44h] BYREF
  int v29; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v30[2]; // [rsp+48h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+58h] [rbp-28h] BYREF
  int *v32; // [rsp+68h] [rbp-18h]
  __int64 v33; // [rsp+70h] [rbp-10h]

  v30[0] = "WinHttpHelper::ReceiveResponse";
  v25 = 0;
  v30[1] = &v25;
  dwNumberOfBytesRead = 0;
  v6 = 0;
  *a3 = 0;
  v7 = 0;
  do
  {
    v8 = (void *)*((_QWORD *)this + 2);
    Buffer = 0;
    dwBufferLength = 4;
    if ( !WinHttpQueryHeaders(v8, 0x20000005u, 0, &Buffer, &dwBufferLength, 0) )
      goto LABEL_21;
    if ( !Buffer )
      goto LABEL_20;
    v9 = 3LL * (unsigned int)Buffer;
    if ( v9 > 0xFFFFFFFF || (int)v9 + 1 < (unsigned int)v9 )
    {
      LastError = -2147024362;
      goto LABEL_24;
    }
    v25 = 0;
    v10 = v9 + 1;
    ProcessHeap = GetProcessHeap();
    v12 = HeapAlloc(ProcessHeap, 8u, v10);
    v13 = v12;
    if ( !v12 )
      goto LABEL_31;
    if ( !WinHttpReadData(*((HINTERNET *)this + 2), v12, Buffer, &dwNumberOfBytesRead) )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80190000;
      else
        LastError = GetLastError();
      goto LABEL_25;
    }
    if ( dwNumberOfBytesRead )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
      {
        v29 = Buffer;
        v33 = 4;
        v32 = &v29;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)DataReceivedEvent,
          v14,
          2u,
          &v31);
      }
      if ( v7 )
        goto LABEL_33;
      if ( Buffer + 1 < (unsigned int)Buffer )
      {
        LastError = -2147024362;
        goto LABEL_25;
      }
      v25 = 0;
      v15 = Buffer + 1;
      v16 = GetProcessHeap();
      v17 = HeapAlloc(v16, 8u, (unsigned int)v15);
      if ( v6 )
      {
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v6);
      }
      v6 = v17;
      if ( !v17 )
      {
LABEL_31:
        LastError = -2147024882;
        goto LABEL_25;
      }
      memcpy_0(v17, v13, (unsigned int)Buffer);
      v7 = Buffer;
      v25 = 0;
    }
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v13);
    if ( !Buffer )
    {
LABEL_20:
      if ( WinHttpQueryHeaders(*((HINTERNET *)this + 2), 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
      {
        LastError = Buffer;
        if ( Buffer > 0 )
        {
          v20 = (unsigned __int16)Buffer;
LABEL_23:
          LastError = v20 | 0x80190000;
        }
      }
      else
      {
LABEL_21:
        if ( (int)GetLastError() > 0 )
        {
          v20 = (unsigned __int16)GetLastError();
          goto LABEL_23;
        }
        LastError = GetLastError();
      }
LABEL_24:
      v13 = 0;
LABEL_25:
      v25 = LastError;
      goto LABEL_26;
    }
  }
  while ( dwNumberOfBytesRead );
  v13 = 0;
  if ( !v6 )
  {
LABEL_33:
    LastError = -2147467259;
    goto LABEL_25;
  }
  *((_BYTE *)v6 + v7) = 0;
  *a2 = (char *)v6;
  v6 = 0;
  *a3 = v7;
  LastError = v25;
LABEL_26:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v30);
  if ( v6 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v6);
  }
  if ( v13 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v13);
  }
  return LastError;
}

```

## disassembly

```asm
0x180020844  mov     [rsp-38h+arg_18], rbx
0x180020849  push    rbp
0x18002084a  push    rsi
0x18002084b  push    rdi
0x18002084c  push    r12
0x18002084e  push    r13
0x180020850  push    r14
0x180020852  push    r15
0x180020854  mov     rbp, rsp
0x180020857  sub     rsp, 80h
0x18002085e  mov     rax, cs:__security_cookie
0x180020865  xor     rax, rsp
0x180020868  mov     [rbp+var_8], rax
0x18002086c  xor     r13d, r13d
0x18002086f  lea     rax, aWinhttphelperR; "WinHttpHelper::ReceiveResponse"
0x180020876  mov     [rbp+var_38], rax
0x18002087a  mov     r15, r8
0x18002087d  lea     rax, [rbp+var_50]
0x180020881  mov     [rbp+var_50], r13d
0x180020885  mov     [rbp+var_30], rax
0x180020889  mov     r12, rdx
0x18002088c  mov     r14, rcx
0x18002088f  mov     [rbp+dwNumberOfBytesRead], r13d
0x180020893  mov     edi, r13d
0x180020896  mov     [r8], r13d
0x180020899  mov     esi, r13d
0x18002089c  mov     rcx, [r14+10h]; hRequest
0x1800208a0  lea     rax, [rbp+dwBufferLength]
0x1800208a4  mov     [rsp+80h+lpdwIndex], r13; lpdwIndex
0x1800208a9  lea     r9, [rbp+Buffer]; lpBuffer
0x1800208ad  xor     r8d, r8d; pwszName
0x1800208b0  mov     [rsp+80h+lpdwBufferLength], rax; lpdwBufferLength
0x1800208b5  mov     edx, 20000005h; dwInfoLevel
0x1800208ba  mov     [rbp+Buffer], r13d
0x1800208be  mov     [rbp+dwBufferLength], 4
0x1800208c5  call    cs:__imp_WinHttpQueryHeaders
0x1800208cc  nop     dword ptr [rax+rax+00h]
0x1800208d1  test    eax, eax
0x1800208d3  jz      loc_180020A98
0x1800208d9  mov     eax, [rbp+Buffer]
0x1800208dc  test    eax, eax
0x1800208de  jz      loc_180020A66
0x1800208e4  lea     rcx, [rax+rax*2]
0x1800208e8  mov     eax, 0FFFFFFFFh
0x1800208ed  cmp     rcx, rax
0x1800208f0  ja      loc_180020B9F
0x1800208f6  lea     eax, [rcx+1]
0x1800208f9  cmp     eax, ecx
0x1800208fb  jb      loc_180020B9F
0x180020901  mov     [rbp+var_50], r13d
0x180020905  mov     ebx, eax
0x180020907  call    cs:__imp_GetProcessHeap
0x18002090e  nop     dword ptr [rax+rax+00h]
0x180020913  mov     r8d, ebx; dwBytes
0x180020916  mov     edx, 8; dwFlags
0x18002091b  mov     rcx, rax; hHeap
0x18002091e  call    cs:__imp_HeapAlloc
0x180020925  nop     dword ptr [rax+rax+00h]
0x18002092a  mov     rbx, rax
0x18002092d  test    rax, rax
0x180020930  jz      loc_180020B44
0x180020936  mov     r8d, [rbp+Buffer]; dwNumberOfBytesToRead
0x18002093a  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18002093e  mov     rcx, [r14+10h]; hRequest
0x180020942  mov     rdx, rax; lpBuffer
0x180020945  call    cs:__imp_WinHttpReadData
0x18002094c  nop     dword ptr [rax+rax+00h]
0x180020951  test    eax, eax
0x180020953  jz      loc_180020B62
0x180020959  cmp     [rbp+dwNumberOfBytesRead], r13d
0x18002095d  jz      loc_180020A2D
0x180020963  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x18002096a  jz      short loc_1800209A4
0x18002096c  mov     eax, [rbp+Buffer]
0x18002096f  lea     rdx, DataReceivedEvent
0x180020976  mov     [rbp+var_40], eax
0x180020979  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180020980  lea     rax, [rbp+var_40]
0x180020984  mov     [rbp+var_10], 4
0x18002098c  mov     [rbp+var_18], rax
0x180020990  mov     r9d, 2
0x180020996  lea     rax, [rbp+var_28]
0x18002099a  mov     [rsp+80h+lpdwBufferLength], rax
0x18002099f  call    McGenEventWrite_EventWriteTransfer
0x1800209a4  test    esi, esi
0x1800209a6  jnz     loc_180020B58
0x1800209ac  mov     eax, [rbp+Buffer]
0x1800209af  lea     ecx, [rax+1]
0x1800209b2  cmp     ecx, eax
0x1800209b4  jb      loc_180020B4E
0x1800209ba  mov     [rbp+var_50], r13d
0x1800209be  mov     esi, ecx
0x1800209c0  call    cs:__imp_GetProcessHeap
0x1800209c7  nop     dword ptr [rax+rax+00h]
0x1800209cc  mov     r8d, esi; dwBytes
0x1800209cf  mov     edx, 8; dwFlags
0x1800209d4  mov     rcx, rax; hHeap
0x1800209d7  call    cs:__imp_HeapAlloc
0x1800209de  nop     dword ptr [rax+rax+00h]
0x1800209e3  mov     rsi, rax
0x1800209e6  test    rdi, rdi
0x1800209e9  jz      short loc_180020A0B
0x1800209eb  call    cs:__imp_GetProcessHeap
0x1800209f2  nop     dword ptr [rax+rax+00h]
0x1800209f7  mov     r8, rdi; lpMem
0x1800209fa  xor     edx, edx; dwFlags
0x1800209fc  mov     rcx, rax; hHeap
0x1800209ff  call    cs:__imp_HeapFree
0x180020a06  nop     dword ptr [rax+rax+00h]
0x180020a0b  mov     rdi, rsi
0x180020a0e  test    rsi, rsi
0x180020a11  jz      loc_180020B44
0x180020a17  mov     r8d, [rbp+Buffer]; Size
0x180020a1b  mov     rdx, rbx; Src
0x180020a1e  mov     rcx, rsi; void *
0x180020a21  call    memcpy_0
0x180020a26  mov     esi, [rbp+Buffer]
0x180020a29  mov     [rbp+var_50], r13d
0x180020a2d  call    cs:__imp_GetProcessHeap
0x180020a34  nop     dword ptr [rax+rax+00h]
0x180020a39  mov     r8, rbx; lpMem
0x180020a3c  xor     edx, edx; dwFlags
0x180020a3e  mov     rcx, rax; hHeap
0x180020a41  call    cs:__imp_HeapFree
0x180020a48  nop     dword ptr [rax+rax+00h]
0x180020a4d  mov     eax, [rbp+Buffer]
0x180020a50  test    eax, eax
0x180020a52  jz      short loc_180020A66
0x180020a54  cmp     [rbp+dwNumberOfBytesRead], r13d
0x180020a58  jnz     loc_18002089C
0x180020a5e  test    eax, eax
0x180020a60  jnz     loc_180020BBC
0x180020a66  mov     rcx, [r14+10h]; hRequest
0x180020a6a  lea     rax, [rbp+dwBufferLength]
0x180020a6e  mov     [rsp+80h+lpdwIndex], r13; lpdwIndex
0x180020a73  lea     r9, [rbp+Buffer]; lpBuffer
0x180020a77  xor     r8d, r8d; pwszName
0x180020a7a  mov     [rsp+80h+lpdwBufferLength], rax; lpdwBufferLength
0x180020a7f  mov     edx, 20000013h; dwInfoLevel
0x180020a84  call    cs:__imp_WinHttpQueryHeaders
0x180020a8b  nop     dword ptr [rax+rax+00h]
0x180020a90  test    eax, eax
0x180020a92  jnz     loc_180020BA9
0x180020a98  call    cs:__imp_GetLastError
0x180020a9f  nop     dword ptr [rax+rax+00h]
0x180020aa4  test    eax, eax
0x180020aa6  jle     loc_180020BDF
0x180020aac  call    cs:__imp_GetLastError
0x180020ab3  nop     dword ptr [rax+rax+00h]
0x180020ab8  movzx   esi, ax
0x180020abb  or      esi, 80190000h
0x180020ac1  mov     rbx, r13
0x180020ac4  mov     [rbp+var_50], esi
0x180020ac7  lea     rcx, [rbp+var_38]; this
0x180020acb  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180020ad0  test    rdi, rdi
0x180020ad3  jz      short loc_180020AF5
0x180020ad5  call    cs:__imp_GetProcessHeap
0x180020adc  nop     dword ptr [rax+rax+00h]
0x180020ae1  mov     r8, rdi; lpMem
0x180020ae4  xor     edx, edx; dwFlags
0x180020ae6  mov     rcx, rax; hHeap
0x180020ae9  call    cs:__imp_HeapFree
0x180020af0  nop     dword ptr [rax+rax+00h]
0x180020af5  test    rbx, rbx
0x180020af8  jz      short loc_180020B1A
0x180020afa  call    cs:__imp_GetProcessHeap
0x180020b01  nop     dword ptr [rax+rax+00h]
0x180020b06  mov     r8, rbx; lpMem
0x180020b09  xor     edx, edx; dwFlags
0x180020b0b  mov     rcx, rax; hHeap
0x180020b0e  call    cs:__imp_HeapFree
0x180020b15  nop     dword ptr [rax+rax+00h]
0x180020b1a  mov     eax, esi
0x180020b1c  mov     rcx, [rbp+var_8]
0x180020b20  xor     rcx, rsp; StackCookie
0x180020b23  call    __security_check_cookie
0x180020b28  mov     rbx, [rsp+80h+arg_18]
0x180020b30  add     rsp, 80h
0x180020b37  pop     r15
0x180020b39  pop     r14
0x180020b3b  pop     r13
0x180020b3d  pop     r12
0x180020b3f  pop     rdi
0x180020b40  pop     rsi
0x180020b41  pop     rbp
0x180020b42  retn
0x180020b44  mov     esi, 8007000Eh
0x180020b49  jmp     loc_180020AC4
0x180020b4e  mov     esi, 80070216h
0x180020b53  jmp     loc_180020AC4
0x180020b58  mov     esi, 80004005h
0x180020b5d  jmp     loc_180020AC4
0x180020b62  call    cs:__imp_GetLastError
0x180020b69  nop     dword ptr [rax+rax+00h]
0x180020b6e  test    eax, eax
0x180020b70  jg      short loc_180020B85
0x180020b72  call    cs:__imp_GetLastError
0x180020b79  nop     dword ptr [rax+rax+00h]
0x180020b7e  mov     esi, eax
0x180020b80  jmp     loc_180020AC4
0x180020b85  call    cs:__imp_GetLastError
0x180020b8c  nop     dword ptr [rax+rax+00h]
0x180020b91  movzx   esi, ax
0x180020b94  or      esi, 80190000h
0x180020b9a  jmp     loc_180020AC4
0x180020b9f  mov     esi, 80070216h
0x180020ba4  jmp     loc_180020AC1
0x180020ba9  mov     esi, [rbp+Buffer]
0x180020bac  test    esi, esi
0x180020bae  jle     loc_180020AC1
0x180020bb4  movzx   esi, si
0x180020bb7  jmp     loc_180020ABB
0x180020bbc  mov     rbx, r13
0x180020bbf  test    rdi, rdi
0x180020bc2  jz      short loc_180020B58
0x180020bc4  mov     eax, esi
0x180020bc6  mov     [rax+rdi], r13b
0x180020bca  mov     rax, rdi
0x180020bcd  mov     [r12], rax
0x180020bd1  mov     rdi, r13
0x180020bd4  mov     [r15], esi
0x180020bd7  mov     esi, [rbp+var_50]
0x180020bda  jmp     loc_180020AC7
0x180020bdf  call    cs:__imp_GetLastError
0x180020be6  nop     dword ptr [rax+rax+00h]
0x180020beb  mov     esi, eax
0x180020bed  jmp     loc_180020AC1
```
