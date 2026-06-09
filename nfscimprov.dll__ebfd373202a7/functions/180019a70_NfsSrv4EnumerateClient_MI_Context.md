# NfsSrv4EnumerateClient(_MI_Context *)

- ea: `0x180019a70`
- end: `0x180019c6e`
- name: `?NfsSrv4EnumerateClient@@YAKPEAU_MI_Context@@@Z`
- size: `510`
- prototype: `unsigned int __fastcall(struct _MI_Context *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009310`

## callees

- `0x1800098c4`
- `0x18000bde0`
- `0x18000cd6c`
- `0x180019504`
- `0x180019a70`
- `0x18001a258`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180019c32`
- `KERNEL32!HeapFree` at `0x180019c32`
- `KERNEL32!GetLastError` at `0x180019ae5`
- `KERNEL32!GetLastError` at `0x180019b5a`
- `KERNEL32!GetLastError` at `0x180019ae5`
- `KERNEL32!GetLastError` at `0x180019b5a`
- `KERNEL32!CloseHandle` at `0x180019c19`
- `KERNEL32!CloseHandle` at `0x180019c19`
- `KERNEL32!HeapAlloc` at `0x180019b10`
- `KERNEL32!HeapAlloc` at `0x180019b10`
- `KERNEL32!GetProcessHeap` at `0x180019af5`
- `KERNEL32!GetProcessHeap` at `0x180019c24`
- `KERNEL32!GetProcessHeap` at `0x180019af5`
- `KERNEL32!GetProcessHeap` at `0x180019c24`
- `KERNEL32!CreateFileW` at `0x180019ad6`
- `KERNEL32!CreateFileW` at `0x180019ad6`
- `KERNEL32!DeviceIoControl` at `0x180019b50`
- `KERNEL32!DeviceIoControl` at `0x180019b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NfsSrv4EnumerateClient(struct _MI_Context *a1)
{
  DWORD LastError; // ebx
  HANDLE FileW; // rsi
  HANDLE ProcessHeap; // rax
  unsigned int *v4; // rdi
  DWORD v5; // eax
  unsigned int v6; // r14d
  HANDLE v7; // rax
  _QWORD v9[2]; // [rsp+50h] [rbp-30h] BYREF
  __int16 v10; // [rsp+60h] [rbp-20h]
  struct _MI_Context *v11; // [rsp+68h] [rbp-18h]
  int v12; // [rsp+70h] [rbp-10h]
  __int64 v13; // [rsp+74h] [rbp-Ch]
  DWORD BytesReturned; // [rsp+B0h] [rbp+30h] BYREF

  LastError = 0;
  BytesReturned = 0;
  v9[0] = &CWMIContext::`vftable';
  v11 = a1;
  v9[1] = 0;
  v10 = 0;
  v13 = 0;
  v12 = 0;
  FileW = CreateFileW(L"\\\\.\\NfsSvr", 0x80000000, 0, 0, 3u, 0x1000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_23;
  }
  ProcessHeap = GetProcessHeap();
  v4 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, 0x1000u);
  if ( v4 )
  {
    if ( !DeviceIoControl(FileW, 0x1000059Cu, 0, 0, v4, 0x1000u, &BytesReturned, 0) )
    {
      v5 = GetLastError();
      LastError = v5;
      if ( v5 == 50 )
      {
        NfsPostNfsv4DisabledError(50, v9);
        goto LABEL_19;
      }
      if ( v5 )
        goto LABEL_19;
    }
    v6 = 0;
    do
    {
      if ( CWMIContext::IsCanceled((CWMIContext *)v9) || v6 >= *v4 )
        break;
      LastError = NfsSrv4EnumeratePerVsClient(FileW);
      if ( !LastError && !CWMIContext::IsCanceled((CWMIContext *)v9) )
        LastError = NfsSrv4EnumeratePerVsClient(FileW);
      ++v6;
    }
    while ( !LastError );
    if ( !LastError && CWMIContext::IsCanceled((CWMIContext *)v9) )
      LastError = 1223;
    goto LABEL_19;
  }
  LastError = 8;
LABEL_19:
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( v4 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v4);
  }
LABEL_23:
  LODWORD(v13) = LastError;
  CWMIContext::PostResult((CWMIContext *)v9, MI_RESULT_OK);
  CWMIContext::~CWMIContext((CWMIContext *)v9);
  return LastError;
}

```

## disassembly

```asm
0x180019a70  mov     [rsp-28h+arg_8], rbx
0x180019a75  mov     [rsp-28h+arg_10], rsi
0x180019a7a  push    rbp
0x180019a7b  push    rdi
0x180019a7c  push    r12
0x180019a7e  push    r14
0x180019a80  push    r15
0x180019a82  mov     rbp, rsp
0x180019a85  sub     rsp, 80h
0x180019a8c  xor     ebx, ebx
0x180019a8e  mov     [rbp+BytesReturned], ebx
0x180019a91  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180019a98  mov     [rbp+var_30], rax
0x180019a9c  mov     [rbp+var_18], rcx
0x180019aa0  mov     [rbp+var_28], rbx
0x180019aa4  mov     [rbp+var_20], bx
0x180019aa8  mov     [rbp+var_C], rbx
0x180019aac  mov     [rbp+var_10], ebx
0x180019aaf  mov     [rsp+80h+hTemplateFile], rbx; hTemplateFile
0x180019ab4  mov     [rsp+80h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x180019abc  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180019ac4  xor     r9d, r9d; lpSecurityAttributes
0x180019ac7  xor     r8d, r8d; dwShareMode
0x180019aca  mov     edx, 80000000h; dwDesiredAccess
0x180019acf  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x180019ad6  call    cs:__imp_CreateFileW
0x180019adc  mov     rsi, rax
0x180019adf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019ae3  jnz     short loc_180019AF5
0x180019ae5  call    cs:__imp_GetLastError
0x180019aeb  mov     ebx, eax
0x180019aed  test    eax, eax
0x180019aef  jnz     loc_180019C38
0x180019af5  call    cs:__imp_GetProcessHeap
0x180019afb  mov     rcx, rax; hHeap
0x180019afe  mov     r15d, 1000h
0x180019b04  mov     r8d, r15d; dwBytes
0x180019b07  mov     r14d, 8
0x180019b0d  mov     edx, r14d; dwFlags
0x180019b10  call    cs:__imp_HeapAlloc
0x180019b16  mov     rdi, rax
0x180019b19  test    rax, rax
0x180019b1c  jnz     short loc_180019B26
0x180019b1e  mov     ebx, r14d
0x180019b21  jmp     loc_180019C10
0x180019b26  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x180019b2f  lea     rax, [rbp+BytesReturned]
0x180019b33  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x180019b38  mov     [rsp+80h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x180019b3d  mov     qword ptr [rsp+80h+dwCreationDisposition], rdi; lpOutBuffer
0x180019b42  xor     r9d, r9d; nInBufferSize
0x180019b45  xor     r8d, r8d; lpInBuffer
0x180019b48  mov     edx, 1000059Ch; dwIoControlCode
0x180019b4d  mov     rcx, rsi; hDevice
0x180019b50  call    cs:__imp_DeviceIoControl
0x180019b56  test    eax, eax
0x180019b58  jnz     short loc_180019B81
0x180019b5a  call    cs:__imp_GetLastError
0x180019b60  mov     ebx, eax
0x180019b62  mov     ecx, 32h ; '2'
0x180019b67  cmp     eax, ecx
0x180019b69  jnz     short loc_180019B79
0x180019b6b  lea     rdx, [rbp+var_30]
0x180019b6f  call    NfsPostNfsv4DisabledError
0x180019b74  jmp     loc_180019C10
0x180019b79  test    eax, eax
0x180019b7b  jnz     loc_180019C10
0x180019b81  mov     r15d, [rdi+8]
0x180019b85  add     r15, rdi
0x180019b88  xor     r14d, r14d
0x180019b8b  lea     rcx, [rbp+var_30]; this
0x180019b8f  call    ?IsCanceled@CWMIContext@@UEAA_NXZ; CWMIContext::IsCanceled(void)
0x180019b94  test    al, al
0x180019b96  jnz     short loc_180019BF9
0x180019b98  cmp     r14d, [rdi]
0x180019b9b  jnb     short loc_180019BF9
0x180019b9d  lea     r12, [r14+r14*4]
0x180019ba1  movups  xmm0, xmmword ptr [r15+r12*4+4]
0x180019ba7  movdqu  [rbp+var_40], xmm0
0x180019bac  lea     r9, [rbp+var_30]
0x180019bb0  mov     r8b, 1
0x180019bb3  lea     rdx, [rbp+var_40]
0x180019bb7  mov     rcx, rsi; hDevice
0x180019bba  call    NfsSrv4EnumeratePerVsClient
0x180019bbf  mov     ebx, eax
0x180019bc1  test    eax, eax
0x180019bc3  jnz     short loc_180019BF2
0x180019bc5  lea     rcx, [rbp+var_30]; this
0x180019bc9  call    ?IsCanceled@CWMIContext@@UEAA_NXZ; CWMIContext::IsCanceled(void)
0x180019bce  test    al, al
0x180019bd0  jnz     short loc_180019BF2
0x180019bd2  movups  xmm0, xmmword ptr [r15+r12*4+4]
0x180019bd8  movdqu  [rbp+var_40], xmm0
0x180019bdd  lea     r9, [rbp+var_30]
0x180019be1  xor     r8d, r8d
0x180019be4  lea     rdx, [rbp+var_40]
0x180019be8  mov     rcx, rsi; hDevice
0x180019beb  call    NfsSrv4EnumeratePerVsClient
0x180019bf0  mov     ebx, eax
0x180019bf2  inc     r14d
0x180019bf5  test    ebx, ebx
0x180019bf7  jz      short loc_180019B8B
0x180019bf9  test    ebx, ebx
0x180019bfb  jnz     short loc_180019C10
0x180019bfd  lea     rcx, [rbp+var_30]; this
0x180019c01  call    ?IsCanceled@CWMIContext@@UEAA_NXZ; CWMIContext::IsCanceled(void)
0x180019c06  mov     ecx, 4C7h
0x180019c0b  test    al, al
0x180019c0d  cmovnz  ebx, ecx
0x180019c10  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180019c14  jz      short loc_180019C1F
0x180019c16  mov     rcx, rsi; hObject
0x180019c19  call    cs:__imp_CloseHandle
0x180019c1f  test    rdi, rdi
0x180019c22  jz      short loc_180019C38
0x180019c24  call    cs:__imp_GetProcessHeap
0x180019c2a  mov     rcx, rax; hHeap
0x180019c2d  mov     r8, rdi; lpMem
0x180019c30  xor     edx, edx; dwFlags
0x180019c32  call    cs:__imp_HeapFree
0x180019c38  mov     dword ptr [rbp+var_C], ebx
0x180019c3b  xor     edx, edx; enum _MI_Result
0x180019c3d  lea     rcx, [rbp+var_30]; this
0x180019c41  call    ?PostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::PostResult(_MI_Result)
0x180019c46  nop
0x180019c47  lea     rcx, [rbp+var_30]; this
0x180019c4b  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x180019c50  mov     eax, ebx
0x180019c52  lea     r11, [rsp+80h+var_s0]
0x180019c5a  mov     rbx, [r11+38h]
0x180019c5e  mov     rsi, [r11+40h]
0x180019c62  mov     rsp, r11
0x180019c65  pop     r15
0x180019c67  pop     r14
0x180019c69  pop     r12
0x180019c6b  pop     rdi
0x180019c6c  pop     rbp
0x180019c6d  retn
```
