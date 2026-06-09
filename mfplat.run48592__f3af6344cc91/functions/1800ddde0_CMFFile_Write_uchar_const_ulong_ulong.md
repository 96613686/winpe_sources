# CMFFile::Write(uchar const *,ulong,ulong *)

- ea: `0x1800ddde0`
- end: `0x1800de034`
- name: `?Write@CMFFile@@UEAAJPEBEKPEAK@Z`
- size: `596`
- prototype: `__int64 __fastcall(CMFFile *__hidden this, const unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800054a0`
- `0x18000ac1c`
- `0x18000ac98`
- `0x18000b080`
- `0x18000b2d0`
- `0x18000ef58`
- `0x1800255b0`
- `0x180038bf0`
- `0x18007e1f0`
- `0x1800ddde0`
- `0x1800de040`
- `0x18011fff0`
- `0x180124edc`
- `0x180124f58`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ddf7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ddf7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ddf93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ddf93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddf29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddf4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddf29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddf4d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ddf1f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ddf1f`

## string_xrefs

- `0x1800dddf9`: `CMFFile::Write`

## pseudocode

```c
__int64 __fastcall CMFFile::Write(CMFFile *this, unsigned __int8 *a2, unsigned int a3, unsigned int *a4)
{
  __int64 v8; // rcx
  void *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rsi
  unsigned int *v12; // r9
  signed int v13; // ebx
  unsigned int v14; // edx
  signed int LastError; // eax
  int v16; // ecx
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-28h]
  char v19; // [rsp+28h] [rbp-20h]
  int v20; // [rsp+80h] [rbp+38h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v20, "CMFFile::Write", 1873);
  if ( a2 && a4 )
  {
    if ( *((_DWORD *)this + 65) || (v8 = *((_QWORD *)this + 20), v8 == -1) )
    {
      v13 = *((_DWORD *)this + 50);
    }
    else
    {
      if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
      {
        v19 = *((_QWORD *)this + 30);
        v20 = 1177695063;
        McTemplateU0s4ppxq_EventWriteTransfer(
          v8,
          (unsigned int)IOWrite_Request,
          (unsigned int)&v20,
          (_DWORD)this,
          v8,
          v19,
          a3);
      }
      v9 = operator new(0xA8u);
      if ( v9 && (v10 = CMFFileAsyncResult::CMFFileAsyncResult(v9, 2), (v11 = v10) != 0) )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        v13 = CMFFile::PrepareAsyncResult(this, a2, a3, v12, v11);
        if ( v13 >= 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
          CAsyncResult::EnsureEvent((struct tagMFASYNCRESULT *)v11);
          MFCallStackTracingTakeSnapshot((struct IMFAsyncResult *)v11);
          if ( WriteFile(
                 *((HANDLE *)this + 20),
                 *(LPCVOID *)(v11 + 128),
                 *(_DWORD *)(v11 + 136),
                 0,
                 (LPOVERLAPPED)(v11 + 8))
            || GetLastError() == 997 )
          {
            _InterlockedIncrement((volatile signed __int32 *)this + 64);
            CAsyncResult::Wait((CAsyncResult *)v11, v14);
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
            *((_QWORD *)this + 31) = -1;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
            v13 = CMFFile::FinishAsyncResult(this, a4, (struct CMFFileAsyncResult *)v11);
            if ( v13 >= 0 )
            {
              if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
              {
                lpOverlapped = (LPOVERLAPPED)*((_QWORD *)this + 20);
                v20 = 1177695063;
                McTemplateU0s4pp_EventWriteTransfer(
                  v16,
                  (unsigned int)IOWrite_Complete,
                  (unsigned int)&v20,
                  (_DWORD)this,
                  (char)lpOverlapped);
              }
              CMFFile::SetOffset(this, *((_QWORD *)this + 30) + *(unsigned int *)(v11 + 120));
            }
          }
          else
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            MFCallStackTracingClearSnapshot((struct IMFAsyncResult *)v11);
            LastError = GetLastError();
            v13 = LastError;
            if ( LastError > 0 )
              v13 = (unsigned __int16)LastError | 0x80070000;
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      else
      {
        v13 = -2147024882;
      }
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v20);
    return (unsigned int)v13;
  }
  else
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v20);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800ddde0  push    rbp
0x1800ddde2  push    rbx
0x1800ddde3  push    rsi
0x1800ddde4  push    rdi
0x1800ddde5  push    r14
0x1800ddde7  push    r15
0x1800ddde9  mov     rbp, rsp
0x1800dddec  sub     rsp, 48h
0x1800dddf0  mov     r15d, r8d
0x1800dddf3  mov     rbx, rdx
0x1800dddf6  mov     rdi, rcx
0x1800dddf9  lea     rdx, aCmffileWrite; "CMFFile::Write"
0x1800dde00  mov     r8d, 751h; int
0x1800dde06  lea     rcx, [rbp+arg_0]; this
0x1800dde0a  mov     r14, r9
0x1800dde0d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800dde12  test    rbx, rbx
0x1800dde15  jz      loc_1800DE019
0x1800dde1b  test    r14, r14
0x1800dde1e  jz      loc_1800DE019
0x1800dde24  mov     eax, [rdi+104h]
0x1800dde2a  test    eax, eax
0x1800dde2c  jnz     loc_1800DE006
0x1800dde32  mov     rcx, [rdi+0A0h]
0x1800dde39  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800dde3d  jz      loc_1800DE006
0x1800dde43  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x1800dde4a  jz      short loc_1800DDE7C
0x1800dde4c  mov     rax, [rdi+0F0h]
0x1800dde53  lea     r8, [rbp+arg_0]
0x1800dde57  mov     [rsp+48h+var_18], r15d
0x1800dde5c  lea     rdx, IOWrite_Request
0x1800dde63  mov     [rsp+48h+var_20], rax
0x1800dde68  mov     r9, rdi
0x1800dde6b  mov     [rsp+48h+lpOverlapped], rcx
0x1800dde70  mov     [rbp+arg_0], 46323357h
0x1800dde77  call    McTemplateU0s4ppxq_EventWriteTransfer
0x1800dde7c  mov     ecx, 0A8h; Size
0x1800dde81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dde86  test    rax, rax
0x1800dde89  jz      loc_1800DDFFF
0x1800dde8f  xor     r9d, r9d
0x1800dde92  mov     [rsp+48h+lpOverlapped], 0
0x1800dde9b  mov     rcx, rax
0x1800dde9e  lea     edx, [r9+2]
0x1800ddea2  call    ??0CMFFileAsyncResult@@QEAA@W4IoType@0@PEAUIUnknown@@PEAUIMFAsyncCallback@@1@Z; CMFFileAsyncResult::CMFFileAsyncResult(CMFFileAsyncResult::IoType,IUnknown *,IMFAsyncCallback *,IUnknown *)
0x1800ddea7  mov     rsi, rax
0x1800ddeaa  test    rax, rax
0x1800ddead  jz      loc_1800DDFFF
0x1800ddeb3  mov     rcx, [rax]
0x1800ddeb6  mov     rax, [rcx+8]
0x1800ddeba  mov     rcx, rsi
0x1800ddebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddec2  mov     r8d, r15d; unsigned int
0x1800ddec5  mov     [rsp+48h+lpOverlapped], rsi; FileSizeHigh
0x1800ddeca  mov     rdx, rbx; unsigned __int8 *
0x1800ddecd  mov     rcx, rdi; this
0x1800dded0  call    ?PrepareAsyncResult@CMFFile@@AEAAJPEAEKPEAKPEAVCMFFileAsyncResult@@@Z; CMFFile::PrepareAsyncResult(uchar *,ulong,ulong *,CMFFileAsyncResult *)
0x1800dded5  mov     ebx, eax
0x1800dded7  test    eax, eax
0x1800dded9  js      loc_1800DDFEE
0x1800ddedf  mov     rax, [rsi]
0x1800ddee2  mov     rcx, rsi
0x1800ddee5  mov     rax, [rax+8]
0x1800ddee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddeee  mov     rcx, rsi; struct tagMFASYNCRESULT *
0x1800ddef1  call    ?EnsureEvent@CAsyncResult@@SAJPEAUtagMFASYNCRESULT@@@Z; CAsyncResult::EnsureEvent(tagMFASYNCRESULT *)
0x1800ddef6  mov     rcx, rsi; struct IMFAsyncResult *
0x1800ddef9  call    MFCallStackTracingTakeSnapshot
0x1800ddefe  mov     r8d, [rsi+88h]; nNumberOfBytesToWrite
0x1800ddf05  lea     rax, [rsi+8]
0x1800ddf09  mov     rdx, [rsi+80h]; lpBuffer
0x1800ddf10  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800ddf13  mov     rcx, [rdi+0A0h]; hFile
0x1800ddf1a  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x1800ddf1f  call    cs:__imp_WriteFile
0x1800ddf25  test    eax, eax
0x1800ddf27  jnz     short loc_1800DDF6B
0x1800ddf29  call    cs:__imp_GetLastError
0x1800ddf2f  cmp     eax, 3E5h
0x1800ddf34  jz      short loc_1800DDF6B
0x1800ddf36  mov     rax, [rsi]
0x1800ddf39  mov     rcx, rsi
0x1800ddf3c  mov     rax, [rax+10h]
0x1800ddf40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddf45  mov     rcx, rsi; struct IMFAsyncResult *
0x1800ddf48  call    MFCallStackTracingClearSnapshot
0x1800ddf4d  call    cs:__imp_GetLastError
0x1800ddf53  mov     ebx, eax
0x1800ddf55  test    eax, eax
0x1800ddf57  jle     loc_1800DDFEE
0x1800ddf5d  movzx   ebx, ax
0x1800ddf60  or      ebx, 80070000h
0x1800ddf66  jmp     loc_1800DDFEE
0x1800ddf6b  lock inc dword ptr [rdi+100h]
0x1800ddf72  mov     rcx, rsi; this
0x1800ddf75  call    ?Wait@CAsyncResult@@QEAAKK@Z; CAsyncResult::Wait(ulong)
0x1800ddf7a  lea     rcx, [rdi+70h]; lpCriticalSection
0x1800ddf7e  call    cs:__imp_EnterCriticalSection
0x1800ddf84  lea     rcx, [rdi+70h]; lpCriticalSection
0x1800ddf88  mov     qword ptr [rdi+0F8h], 0FFFFFFFFFFFFFFFFh
0x1800ddf93  call    cs:__imp_LeaveCriticalSection
0x1800ddf99  mov     r8, rsi; struct CMFFileAsyncResult *
0x1800ddf9c  mov     rdx, r14; unsigned int *
0x1800ddf9f  mov     rcx, rdi; this
0x1800ddfa2  call    ?FinishAsyncResult@CMFFile@@AEAAJPEAKPEAVCMFFileAsyncResult@@@Z; CMFFile::FinishAsyncResult(ulong *,CMFFileAsyncResult *)
0x1800ddfa7  mov     ebx, eax
0x1800ddfa9  test    eax, eax
0x1800ddfab  js      short loc_1800DDFEE
0x1800ddfad  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x1800ddfb4  jz      short loc_1800DDFDC
0x1800ddfb6  mov     rax, [rdi+0A0h]
0x1800ddfbd  lea     r8, [rbp+arg_0]
0x1800ddfc1  mov     r9, rdi
0x1800ddfc4  mov     [rsp+48h+lpOverlapped], rax
0x1800ddfc9  lea     rdx, IOWrite_Complete
0x1800ddfd0  mov     [rbp+arg_0], 46323357h
0x1800ddfd7  call    McTemplateU0s4pp_EventWriteTransfer
0x1800ddfdc  mov     edx, [rsi+78h]
0x1800ddfdf  mov     rcx, rdi; this
0x1800ddfe2  add     rdx, [rdi+0F0h]; unsigned __int64
0x1800ddfe9  call    ?SetOffset@CMFFile@@AEAAX_K@Z; CMFFile::SetOffset(unsigned __int64)
0x1800ddfee  mov     rax, [rsi]
0x1800ddff1  mov     rcx, rsi
0x1800ddff4  mov     rax, [rax+10h]
0x1800ddff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddffd  jmp     short loc_1800DE00C
0x1800ddfff  mov     ebx, 8007000Eh
0x1800de004  jmp     short loc_1800DE00C
0x1800de006  mov     ebx, [rdi+0C8h]
0x1800de00c  lea     rcx, [rbp+arg_0]; this
0x1800de010  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800de015  mov     eax, ebx
0x1800de017  jmp     short loc_1800DE027
0x1800de019  lea     rcx, [rbp+arg_0]; this
0x1800de01d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800de022  mov     eax, 80070057h
0x1800de027  add     rsp, 48h
0x1800de02b  pop     r15
0x1800de02d  pop     r14
0x1800de02f  pop     rdi
0x1800de030  pop     rsi
0x1800de031  pop     rbx
0x1800de032  pop     rbp
0x1800de033  retn
```
