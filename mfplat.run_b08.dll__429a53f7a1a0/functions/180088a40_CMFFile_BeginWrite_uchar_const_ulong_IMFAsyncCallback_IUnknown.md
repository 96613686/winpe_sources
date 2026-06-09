# CMFFile::BeginWrite(uchar const *,ulong,IMFAsyncCallback *,IUnknown *)

- ea: `0x180088a40`
- end: `0x180088c4a`
- name: `?BeginWrite@CMFFile@@UEAAJPEBEKPEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `522`
- prototype: `__int64 __usercall@<rax>(CMFFile *__hidden this@<rcx>, const unsigned __int8 *@<rdx>, unsigned int@<r8d>, struct IMFAsyncCallback *@<r9>, struct IUnknown *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000ac1c`
- `0x18000ac98`
- `0x18000b080`
- `0x18000b2d0`
- `0x1800255b0`
- `0x180038bf0`
- `0x180088a40`
- `0x1800de040`
- `0x18011fff0`
- `0x180124f58`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180088a78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180088b99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180088a78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180088b99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088ab2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088bad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088ab2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088bad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088bd2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180088b78`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180088b78`

## string_xrefs

- `0x180088a58`: `CMFFile::BeginWrite`

## pseudocode

```c
__int64 __fastcall CMFFile::BeginWrite(
        CMFFile *this,
        unsigned __int8 *a2,
        unsigned int a3,
        struct IMFAsyncCallback *a4)
{
  __int64 v8; // rcx
  signed int v9; // ebx
  __int64 v10; // rdi
  void *v12; // rax
  __int64 v13; // rax
  unsigned int *v14; // r9
  signed int LastError; // eax
  char v16; // [rsp+28h] [rbp-50h]
  int v17; // [rsp+80h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v17, "CMFFile::BeginWrite", 1980);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( !a2 || !a4 )
  {
    v9 = -2147024809;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 65) || (v8 = *((_QWORD *)this + 20), v8 == -1) )
  {
    v9 = *((_DWORD *)this + 50);
    v10 = 0;
  }
  else
  {
    if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    {
      v16 = *((_QWORD *)this + 30);
      v17 = 1177695063;
      McTemplateU0s4ppxq_EventWriteTransfer(
        v8,
        (unsigned int)&IOWrite_Request,
        (unsigned int)&v17,
        (_DWORD)this,
        v8,
        v16,
        a3);
    }
    v12 = operator new(0xA8u);
    if ( !v12 || (v13 = CMFFileAsyncResult::CMFFileAsyncResult(v12, 2), (v10 = v13) == 0) )
    {
      v9 = -2147024882;
      goto LABEL_7;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    v9 = CMFFile::PrepareAsyncResult(this, a2, a3, v14, v10);
    if ( v9 < 0 )
    {
LABEL_21:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_7;
    }
    MFCallStackTracingTakeSnapshot((struct IMFAsyncResult *)v10);
    if ( WriteFile(*((HANDLE *)this + 20), *(LPCVOID *)(v10 + 128), *(_DWORD *)(v10 + 136), 0, (LPOVERLAPPED)(v10 + 8))
      || GetLastError() == 997 )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 64);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      *((_QWORD *)this + 31) = -1;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      CMFFile::SetOffset(this, *((_QWORD *)this + 30) + *(unsigned int *)(v10 + 120));
      goto LABEL_7;
    }
    MFCallStackTracingClearSnapshot((struct IMFAsyncResult *)v10);
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v9 < 0 && v10 )
    goto LABEL_21;
LABEL_7:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180088a40  mov     rax, rsp
0x180088a43  push    rbx
0x180088a44  push    rbp
0x180088a45  push    rsi
0x180088a46  push    rdi
0x180088a47  push    r14
0x180088a49  push    r15
0x180088a4b  sub     rsp, 48h
0x180088a4f  mov     r14d, r8d
0x180088a52  mov     r15, rdx
0x180088a55  mov     rsi, rcx
0x180088a58  lea     rdx, aCmffileBeginwr; "CMFFile::BeginWrite"
0x180088a5f  mov     r8d, 7BCh; int
0x180088a65  lea     rcx, [rax+8]; this
0x180088a69  mov     rbx, r9
0x180088a6c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180088a71  lea     rbp, [rsi+70h]
0x180088a75  mov     rcx, rbp; lpCriticalSection
0x180088a78  call    cs:__imp_EnterCriticalSection
0x180088a7e  test    r15, r15
0x180088a81  jz      short loc_180088AF7
0x180088a83  test    rbx, rbx
0x180088a86  jz      short loc_180088AF7
0x180088a88  mov     eax, [rsi+104h]
0x180088a8e  test    eax, eax
0x180088a90  jnz     short loc_180088A9F
0x180088a92  mov     rcx, [rsi+0A0h]
0x180088a99  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180088a9d  jnz     short loc_180088AD4
0x180088a9f  mov     ebx, [rsi+0C8h]
0x180088aa5  xor     edi, edi
0x180088aa7  test    ebx, ebx
0x180088aa9  js      loc_180088C2D
0x180088aaf  mov     rcx, rbp; lpCriticalSection
0x180088ab2  call    cs:__imp_LeaveCriticalSection
0x180088ab8  lea     rcx, [rsp+78h+arg_0]; this
0x180088ac0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180088ac5  mov     eax, ebx
0x180088ac7  add     rsp, 48h
0x180088acb  pop     r15
0x180088acd  pop     r14
0x180088acf  pop     rdi
0x180088ad0  pop     rsi
0x180088ad1  pop     rbp
0x180088ad2  pop     rbx
0x180088ad3  retn
0x180088ad4  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180088adb  jnz     loc_180088BF0
0x180088ae1  mov     ecx, 0A8h; Size
0x180088ae6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180088aeb  test    rax, rax
0x180088aee  jnz     short loc_180088AFE
0x180088af0  mov     ebx, 8007000Eh
0x180088af5  jmp     short loc_180088AAF
0x180088af7  mov     ebx, 80070057h
0x180088afc  jmp     short loc_180088AAF
0x180088afe  mov     rcx, [rsp+78h+arg_20]
0x180088b06  mov     r9, rbx
0x180088b09  mov     [rsp+78h+lpOverlapped], rcx
0x180088b0e  mov     edx, 2
0x180088b13  mov     rcx, rax
0x180088b16  call    ??0CMFFileAsyncResult@@QEAA@W4IoType@0@PEAUIUnknown@@PEAUIMFAsyncCallback@@1@Z; CMFFileAsyncResult::CMFFileAsyncResult(CMFFileAsyncResult::IoType,IUnknown *,IMFAsyncCallback *,IUnknown *)
0x180088b1b  mov     rdi, rax
0x180088b1e  test    rax, rax
0x180088b21  jz      short loc_180088AF0
0x180088b23  mov     rax, [rax]
0x180088b26  mov     rcx, rdi
0x180088b29  mov     rax, [rax+8]
0x180088b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088b32  mov     r8d, r14d; unsigned int
0x180088b35  mov     [rsp+78h+lpOverlapped], rdi; FileSizeHigh
0x180088b3a  mov     rdx, r15; unsigned __int8 *
0x180088b3d  mov     rcx, rsi; this
0x180088b40  call    ?PrepareAsyncResult@CMFFile@@AEAAJPEAEKPEAKPEAVCMFFileAsyncResult@@@Z; CMFFile::PrepareAsyncResult(uchar *,ulong,ulong *,CMFFileAsyncResult *)
0x180088b45  mov     ebx, eax
0x180088b47  test    eax, eax
0x180088b49  js      loc_180088C36
0x180088b4f  mov     rcx, rdi; struct IMFAsyncResult *
0x180088b52  call    MFCallStackTracingTakeSnapshot
0x180088b57  mov     r8d, [rdi+88h]; nNumberOfBytesToWrite
0x180088b5e  lea     rax, [rdi+8]
0x180088b62  mov     rdx, [rdi+80h]; lpBuffer
0x180088b69  xor     r9d, r9d; lpNumberOfBytesWritten
0x180088b6c  mov     rcx, [rsi+0A0h]; hFile
0x180088b73  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180088b78  call    cs:__imp_WriteFile
0x180088b7e  test    eax, eax
0x180088b80  jnz     short loc_180088B8F
0x180088b82  call    cs:__imp_GetLastError
0x180088b88  cmp     eax, 3E5h
0x180088b8d  jnz     short loc_180088BCA
0x180088b8f  lock inc dword ptr [rsi+100h]
0x180088b96  mov     rcx, rbp; lpCriticalSection
0x180088b99  call    cs:__imp_EnterCriticalSection
0x180088b9f  mov     rcx, rbp; lpCriticalSection
0x180088ba2  mov     qword ptr [rsi+0F8h], 0FFFFFFFFFFFFFFFFh
0x180088bad  call    cs:__imp_LeaveCriticalSection
0x180088bb3  mov     edx, [rdi+78h]
0x180088bb6  mov     rcx, rsi; this
0x180088bb9  add     rdx, [rsi+0F0h]; unsigned __int64
0x180088bc0  call    ?SetOffset@CMFFile@@AEAAX_K@Z; CMFFile::SetOffset(unsigned __int64)
0x180088bc5  jmp     loc_180088AAF
0x180088bca  mov     rcx, rdi; struct IMFAsyncResult *
0x180088bcd  call    MFCallStackTracingClearSnapshot
0x180088bd2  call    cs:__imp_GetLastError
0x180088bd8  mov     ebx, eax
0x180088bda  test    eax, eax
0x180088bdc  jle     loc_180088AA7
0x180088be2  movzx   ebx, ax
0x180088be5  or      ebx, 80070000h
0x180088beb  jmp     loc_180088AA7
0x180088bf0  mov     rax, [rsi+0F0h]
0x180088bf7  lea     r8, [rsp+78h+arg_0]
0x180088bff  mov     [rsp+78h+var_48], r14d
0x180088c04  lea     rdx, IOWrite_Request
0x180088c0b  mov     [rsp+78h+var_50], rax
0x180088c10  mov     r9, rsi
0x180088c13  mov     [rsp+78h+lpOverlapped], rcx
0x180088c18  mov     [rsp+78h+arg_0], 46323357h
0x180088c23  call    McTemplateU0s4ppxq_EventWriteTransfer
0x180088c28  jmp     loc_180088AE1
0x180088c2d  test    rdi, rdi
0x180088c30  jz      loc_180088AAF
0x180088c36  mov     rax, [rdi]
0x180088c39  mov     rcx, rdi
0x180088c3c  mov     rax, [rax+10h]
0x180088c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088c45  jmp     loc_180088AAF
```
