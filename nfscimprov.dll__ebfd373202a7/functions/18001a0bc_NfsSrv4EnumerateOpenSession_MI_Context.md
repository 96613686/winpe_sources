# NfsSrv4EnumerateOpenSession(_MI_Context *)

- ea: `0x18001a0bc`
- end: `0x18001a252`
- name: `?NfsSrv4EnumerateOpenSession@@YAKPEAU_MI_Context@@@Z`
- size: `406`
- prototype: `unsigned int __fastcall(struct _MI_Context *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800092b0`

## callees

- `0x1800098c4`
- `0x18000bde0`
- `0x18000cd6c`
- `0x180019504`
- `0x18001a0bc`
- `0x18001a6d4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001a222`
- `KERNEL32!HeapFree` at `0x18001a222`
- `KERNEL32!GetLastError` at `0x18001a12a`
- `KERNEL32!GetLastError` at `0x18001a19c`
- `KERNEL32!GetLastError` at `0x18001a12a`
- `KERNEL32!GetLastError` at `0x18001a19c`
- `KERNEL32!CloseHandle` at `0x18001a209`
- `KERNEL32!CloseHandle` at `0x18001a209`
- `KERNEL32!HeapAlloc` at `0x18001a153`
- `KERNEL32!HeapAlloc` at `0x18001a153`
- `KERNEL32!GetProcessHeap` at `0x18001a13a`
- `KERNEL32!GetProcessHeap` at `0x18001a214`
- `KERNEL32!GetProcessHeap` at `0x18001a13a`
- `KERNEL32!GetProcessHeap` at `0x18001a214`
- `KERNEL32!CreateFileW` at `0x18001a11b`
- `KERNEL32!CreateFileW` at `0x18001a11b`
- `KERNEL32!DeviceIoControl` at `0x18001a192`
- `KERNEL32!DeviceIoControl` at `0x18001a192`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NfsSrv4EnumerateOpenSession(struct _MI_Context *a1)
{
  DWORD LastError; // ebx
  HANDLE FileW; // r14
  HANDLE ProcessHeap; // rax
  unsigned int *v4; // rdi
  DWORD v5; // eax
  unsigned int i; // esi
  HANDLE v7; // rax
  _QWORD v9[2]; // [rsp+50h] [rbp-9h] BYREF
  __int16 v10; // [rsp+60h] [rbp+7h]
  struct _MI_Context *v11; // [rsp+68h] [rbp+Fh]
  int v12; // [rsp+70h] [rbp+17h]
  __int64 v13; // [rsp+74h] [rbp+1Bh]
  DWORD BytesReturned; // [rsp+C0h] [rbp+67h] BYREF

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
      goto LABEL_18;
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
        goto LABEL_14;
      }
      if ( v5 )
        goto LABEL_14;
    }
    for ( i = 0; i < *v4; ++i )
    {
      LastError = NfsSrv4EnumeratePerVsOpenSession(FileW);
      if ( CWMIContext::IsCanceled((CWMIContext *)v9) )
      {
        LastError = 1223;
        goto LABEL_14;
      }
    }
    goto LABEL_14;
  }
  LastError = 8;
LABEL_14:
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( v4 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v4);
  }
LABEL_18:
  LODWORD(v13) = LastError;
  CWMIContext::PostResult((CWMIContext *)v9, MI_RESULT_OK);
  CWMIContext::~CWMIContext((CWMIContext *)v9);
  return LastError;
}

```

## disassembly

```asm
0x18001a0bc  push    rbp
0x18001a0be  push    rbx
0x18001a0bf  push    rsi
0x18001a0c0  push    rdi
0x18001a0c1  push    r14
0x18001a0c3  push    r15
0x18001a0c5  lea     rbp, [rsp-2Fh]
0x18001a0ca  sub     rsp, 88h
0x18001a0d1  xor     ebx, ebx
0x18001a0d3  mov     [rbp+57h+BytesReturned], ebx
0x18001a0d6  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18001a0dd  mov     [rbp+57h+var_60], rax
0x18001a0e1  mov     [rbp+57h+var_48], rcx
0x18001a0e5  mov     [rbp+57h+var_58], rbx
0x18001a0e9  mov     [rbp+57h+var_50], bx
0x18001a0ed  mov     [rbp+57h+var_3C], rbx
0x18001a0f1  mov     [rbp+57h+var_40], ebx
0x18001a0f4  mov     [rsp+0B0h+hTemplateFile], rbx; hTemplateFile
0x18001a0f9  mov     [rsp+0B0h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x18001a101  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001a109  xor     r9d, r9d; lpSecurityAttributes
0x18001a10c  xor     r8d, r8d; dwShareMode
0x18001a10f  mov     edx, 80000000h; dwDesiredAccess
0x18001a114  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x18001a11b  call    cs:__imp_CreateFileW
0x18001a121  mov     r14, rax
0x18001a124  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a128  jnz     short loc_18001A13A
0x18001a12a  call    cs:__imp_GetLastError
0x18001a130  mov     ebx, eax
0x18001a132  test    eax, eax
0x18001a134  jnz     loc_18001A228
0x18001a13a  call    cs:__imp_GetProcessHeap
0x18001a140  mov     rcx, rax; hHeap
0x18001a143  mov     r15d, 1000h
0x18001a149  mov     r8d, r15d; dwBytes
0x18001a14c  mov     esi, 8
0x18001a151  mov     edx, esi; dwFlags
0x18001a153  call    cs:__imp_HeapAlloc
0x18001a159  mov     rdi, rax
0x18001a15c  test    rax, rax
0x18001a15f  jnz     short loc_18001A168
0x18001a161  mov     ebx, esi
0x18001a163  jmp     loc_18001A200
0x18001a168  mov     [rsp+0B0h+lpOverlapped], 0; lpOverlapped
0x18001a171  lea     rax, [rbp+57h+BytesReturned]
0x18001a175  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x18001a17a  mov     [rsp+0B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18001a17f  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rdi; lpOutBuffer
0x18001a184  xor     r9d, r9d; nInBufferSize
0x18001a187  xor     r8d, r8d; lpInBuffer
0x18001a18a  mov     edx, 1000059Ch; dwIoControlCode
0x18001a18f  mov     rcx, r14; hDevice
0x18001a192  call    cs:__imp_DeviceIoControl
0x18001a198  test    eax, eax
0x18001a19a  jnz     short loc_18001A1BC
0x18001a19c  call    cs:__imp_GetLastError
0x18001a1a2  mov     ebx, eax
0x18001a1a4  mov     ecx, 32h ; '2'
0x18001a1a9  cmp     eax, ecx
0x18001a1ab  jnz     short loc_18001A1B8
0x18001a1ad  lea     rdx, [rbp+57h+var_60]
0x18001a1b1  call    NfsPostNfsv4DisabledError
0x18001a1b6  jmp     short loc_18001A200
0x18001a1b8  test    eax, eax
0x18001a1ba  jnz     short loc_18001A200
0x18001a1bc  mov     r15d, [rdi+8]
0x18001a1c0  add     r15, rdi
0x18001a1c3  xor     esi, esi
0x18001a1c5  cmp     esi, [rdi]
0x18001a1c7  jnb     short loc_18001A200
0x18001a1c9  lea     rcx, [rsi+rsi*4]
0x18001a1cd  movups  xmm0, xmmword ptr [r15+rcx*4+4]
0x18001a1d3  movdqu  [rbp+57h+var_70], xmm0
0x18001a1d8  lea     r8, [rbp+57h+var_60]
0x18001a1dc  lea     rdx, [rbp+57h+var_70]
0x18001a1e0  mov     rcx, r14; hDevice
0x18001a1e3  call    NfsSrv4EnumeratePerVsOpenSession
0x18001a1e8  mov     ebx, eax
0x18001a1ea  lea     rcx, [rbp+57h+var_60]; this
0x18001a1ee  call    ?IsCanceled@CWMIContext@@UEAA_NXZ; CWMIContext::IsCanceled(void)
0x18001a1f3  test    al, al
0x18001a1f5  jnz     short loc_18001A1FB
0x18001a1f7  inc     esi
0x18001a1f9  jmp     short loc_18001A1C5
0x18001a1fb  mov     ebx, 4C7h
0x18001a200  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18001a204  jz      short loc_18001A20F
0x18001a206  mov     rcx, r14; hObject
0x18001a209  call    cs:__imp_CloseHandle
0x18001a20f  test    rdi, rdi
0x18001a212  jz      short loc_18001A228
0x18001a214  call    cs:__imp_GetProcessHeap
0x18001a21a  mov     rcx, rax; hHeap
0x18001a21d  mov     r8, rdi; lpMem
0x18001a220  xor     edx, edx; dwFlags
0x18001a222  call    cs:__imp_HeapFree
0x18001a228  mov     dword ptr [rbp+57h+var_3C], ebx
0x18001a22b  xor     edx, edx; enum _MI_Result
0x18001a22d  lea     rcx, [rbp+57h+var_60]; this
0x18001a231  call    ?PostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::PostResult(_MI_Result)
0x18001a236  nop
0x18001a237  lea     rcx, [rbp+57h+var_60]; this
0x18001a23b  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18001a240  mov     eax, ebx
0x18001a242  add     rsp, 88h
0x18001a249  pop     r15
0x18001a24b  pop     r14
0x18001a24d  pop     rdi
0x18001a24e  pop     rsi
0x18001a24f  pop     rbx
0x18001a250  pop     rbp
0x18001a251  retn
```
