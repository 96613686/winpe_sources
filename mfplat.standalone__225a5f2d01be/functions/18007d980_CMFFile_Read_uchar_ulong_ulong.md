# CMFFile::Read(uchar *,ulong,ulong *)

- ea: `0x18007d980`
- end: `0x18007dc28`
- name: `?Read@CMFFile@@UEAAJPEAEKPEAK@Z`
- size: `680`
- prototype: `__int64 __fastcall(CMFFile *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
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
- `0x18007d980`
- `0x18007e1f0`
- `0x1800de040`
- `0x18011fff0`
- `0x180124edc`
- `0x180124f58`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d9d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007db3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d9d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007db3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007db2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dbb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dbd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dbee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007db2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dbb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dbd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dbee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dadf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007db03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dadf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007db03`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007dad5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007dad5`

## string_xrefs

- `0x18007d9a2`: `CMFFile::Read`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMFFile::Read(CMFFile *this, unsigned __int8 *a2, unsigned int a3, unsigned int *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  __int64 v9; // rcx
  void *v10; // rax
  __int64 v11; // rax
  __int64 v12; // r14
  unsigned int *v13; // r9
  signed int v14; // edi
  signed int LastError; // eax
  unsigned int v16; // edx
  int v17; // ecx
  __int64 v18; // rax
  unsigned int v20; // ebx
  char v21; // [rsp+28h] [rbp-18h]
  int v22; // [rsp+70h] [rbp+30h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CMFFile::Read", 1599);
  if ( a2 && a4 )
  {
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
    if ( *((_DWORD *)this + 65) || (v9 = *((_QWORD *)this + 20), v9 == -1) )
    {
      v20 = *((_DWORD *)this + 50);
      LeaveCriticalSection(v8);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
      return v20;
    }
    else
    {
      if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
      {
        v21 = *((_QWORD *)this + 30);
        v22 = 1177695063;
        McTemplateU0s4ppxq_EventWriteTransfer(
          v9,
          (unsigned int)IORead_Request,
          (unsigned int)&v22,
          (_DWORD)this,
          v9,
          v21,
          a3);
      }
      v10 = operator new(0xA8u);
      if ( v10 && (v11 = CMFFileAsyncResult::CMFFileAsyncResult(v10, 1), (v12 = v11) != 0) )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
        v14 = CMFFile::PrepareAsyncResult(this, a2, a3, v13, v12);
        if ( v14 >= 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
          CAsyncResult::EnsureEvent((struct tagMFASYNCRESULT *)v12);
          MFCallStackTracingTakeSnapshot((struct IMFAsyncResult *)v12);
          if ( ReadFile(
                 *((HANDLE *)this + 20),
                 *(LPVOID *)(v12 + 128),
                 *(_DWORD *)(v12 + 136),
                 0,
                 (LPOVERLAPPED)(v12 + 8))
            || GetLastError() == 997 )
          {
            _InterlockedIncrement((volatile signed __int32 *)this + 64);
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
            CAsyncResult::Wait((CAsyncResult *)v12, v16);
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
            v14 = CMFFile::FinishAsyncResult(this, a4, (struct CMFFileAsyncResult *)v12);
            if ( v14 >= 0 )
            {
              if ( *((_DWORD *)this + 65) || (v18 = *((_QWORD *)this + 20), v18 == -1) )
              {
                v14 = *((_DWORD *)this + 50);
              }
              else
              {
                if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
                {
                  v22 = 1177695063;
                  McTemplateU0s4pp_EventWriteTransfer(
                    v17,
                    (unsigned int)IORead_Complete,
                    (unsigned int)&v22,
                    (_DWORD)this,
                    v18);
                }
                CMFFile::SetOffset(this, *((_QWORD *)this + 30) + *(unsigned int *)(v12 + 120));
              }
            }
          }
          else
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            MFCallStackTracingClearSnapshot((struct IMFAsyncResult *)v12);
            LastError = GetLastError();
            v14 = LastError;
            if ( LastError > 0 )
              v14 = (unsigned __int16)LastError | 0x80070000;
          }
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      else
      {
        v14 = -2147024882;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      }
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
      return (unsigned int)v14;
    }
  }
  else
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18007d980  mov     [rsp-28h+arg_8], rbx
0x18007d985  mov     [rsp-28h+arg_10], rsi
0x18007d98a  push    rbp
0x18007d98b  push    rdi
0x18007d98c  push    r12
0x18007d98e  push    r14
0x18007d990  push    r15
0x18007d992  mov     rbp, rsp
0x18007d995  sub     rsp, 40h
0x18007d999  mov     r12d, r8d
0x18007d99c  mov     rdi, rdx
0x18007d99f  mov     rbx, rcx
0x18007d9a2  lea     rdx, aCmffileRead; "CMFFile::Read"
0x18007d9a9  mov     r8d, 63Fh; int
0x18007d9af  lea     rcx, [rbp+arg_0]; this
0x18007d9b3  mov     r15, r9
0x18007d9b6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007d9bb  test    rdi, rdi
0x18007d9be  jz      loc_18007DC01
0x18007d9c4  test    r15, r15
0x18007d9c7  jz      loc_18007DC01
0x18007d9cd  lea     rsi, [rbx+70h]
0x18007d9d1  mov     rcx, rsi; lpCriticalSection
0x18007d9d4  call    cs:__imp_EnterCriticalSection
0x18007d9da  mov     eax, [rbx+104h]
0x18007d9e0  test    eax, eax
0x18007d9e2  jnz     loc_18007DBE5
0x18007d9e8  mov     rcx, [rbx+0A0h]
0x18007d9ef  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007d9f3  jz      loc_18007DBE5
0x18007d9f9  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x18007da00  jz      short loc_18007DA32
0x18007da02  mov     rax, [rbx+0F0h]
0x18007da09  lea     r8, [rbp+arg_0]
0x18007da0d  mov     [rsp+40h+var_10], r12d
0x18007da12  lea     rdx, IORead_Request
0x18007da19  mov     [rsp+40h+var_18], rax
0x18007da1e  mov     r9, rbx
0x18007da21  mov     [rsp+40h+lpOverlapped], rcx
0x18007da26  mov     [rbp+arg_0], 46323357h
0x18007da2d  call    McTemplateU0s4ppxq_EventWriteTransfer
0x18007da32  mov     ecx, 0A8h; Size
0x18007da37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007da3c  test    rax, rax
0x18007da3f  jz      loc_18007DBCA
0x18007da45  xor     r9d, r9d
0x18007da48  mov     [rsp+40h+lpOverlapped], 0
0x18007da51  mov     rcx, rax
0x18007da54  lea     edx, [r9+1]
0x18007da58  call    ??0CMFFileAsyncResult@@QEAA@W4IoType@0@PEAUIUnknown@@PEAUIMFAsyncCallback@@1@Z; CMFFileAsyncResult::CMFFileAsyncResult(CMFFileAsyncResult::IoType,IUnknown *,IMFAsyncCallback *,IUnknown *)
0x18007da5d  mov     r14, rax
0x18007da60  test    rax, rax
0x18007da63  jz      loc_18007DBCA
0x18007da69  mov     rcx, [rax]
0x18007da6c  mov     rax, [rcx+8]
0x18007da70  mov     rcx, r14
0x18007da73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da78  mov     r8d, r12d; unsigned int
0x18007da7b  mov     [rsp+40h+lpOverlapped], r14; FileSizeHigh
0x18007da80  mov     rdx, rdi; unsigned __int8 *
0x18007da83  mov     rcx, rbx; this
0x18007da86  call    ?PrepareAsyncResult@CMFFile@@AEAAJPEAEKPEAKPEAVCMFFileAsyncResult@@@Z; CMFFile::PrepareAsyncResult(uchar *,ulong,ulong *,CMFFileAsyncResult *)
0x18007da8b  mov     edi, eax
0x18007da8d  test    eax, eax
0x18007da8f  js      loc_18007DBB0
0x18007da95  mov     rax, [r14]
0x18007da98  mov     rcx, r14
0x18007da9b  mov     rax, [rax+8]
0x18007da9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007daa4  mov     rcx, r14; struct tagMFASYNCRESULT *
0x18007daa7  call    ?EnsureEvent@CAsyncResult@@SAJPEAUtagMFASYNCRESULT@@@Z; CAsyncResult::EnsureEvent(tagMFASYNCRESULT *)
0x18007daac  mov     rcx, r14; struct IMFAsyncResult *
0x18007daaf  call    MFCallStackTracingTakeSnapshot
0x18007dab4  mov     r8d, [r14+88h]; nNumberOfBytesToRead
0x18007dabb  lea     rax, [r14+8]
0x18007dabf  mov     rdx, [r14+80h]; lpBuffer
0x18007dac6  xor     r9d, r9d; lpNumberOfBytesRead
0x18007dac9  mov     rcx, [rbx+0A0h]; hFile
0x18007dad0  mov     [rsp+40h+lpOverlapped], rax; lpOverlapped
0x18007dad5  call    cs:__imp_ReadFile
0x18007dadb  test    eax, eax
0x18007dadd  jnz     short loc_18007DB21
0x18007dadf  call    cs:__imp_GetLastError
0x18007dae5  cmp     eax, 3E5h
0x18007daea  jz      short loc_18007DB21
0x18007daec  mov     rax, [r14]
0x18007daef  mov     rcx, r14
0x18007daf2  mov     rax, [rax+10h]
0x18007daf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dafb  mov     rcx, r14; struct IMFAsyncResult *
0x18007dafe  call    MFCallStackTracingClearSnapshot
0x18007db03  call    cs:__imp_GetLastError
0x18007db09  mov     edi, eax
0x18007db0b  test    eax, eax
0x18007db0d  jle     loc_18007DBB0
0x18007db13  movzx   edi, ax
0x18007db16  or      edi, 80070000h
0x18007db1c  jmp     loc_18007DBB0
0x18007db21  lock inc dword ptr [rbx+100h]
0x18007db28  mov     rcx, rsi; lpCriticalSection
0x18007db2b  call    cs:__imp_LeaveCriticalSection
0x18007db31  mov     rcx, r14; this
0x18007db34  call    ?Wait@CAsyncResult@@QEAAKK@Z; CAsyncResult::Wait(ulong)
0x18007db39  mov     rcx, rsi; lpCriticalSection
0x18007db3c  call    cs:__imp_EnterCriticalSection
0x18007db42  mov     r8, r14; struct CMFFileAsyncResult *
0x18007db45  mov     rdx, r15; unsigned int *
0x18007db48  mov     rcx, rbx; this
0x18007db4b  call    ?FinishAsyncResult@CMFFile@@AEAAJPEAKPEAVCMFFileAsyncResult@@@Z; CMFFile::FinishAsyncResult(ulong *,CMFFileAsyncResult *)
0x18007db50  mov     edi, eax
0x18007db52  test    eax, eax
0x18007db54  js      short loc_18007DBB0
0x18007db56  mov     eax, [rbx+104h]
0x18007db5c  test    eax, eax
0x18007db5e  jnz     short loc_18007DBAA
0x18007db60  mov     rax, [rbx+0A0h]
0x18007db67  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007db6b  jz      short loc_18007DBAA
0x18007db6d  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x18007db74  jz      short loc_18007DB95
0x18007db76  mov     r9, rbx
0x18007db79  mov     [rbp+arg_0], 46323357h
0x18007db80  lea     r8, [rbp+arg_0]
0x18007db84  mov     [rsp+40h+lpOverlapped], rax
0x18007db89  lea     rdx, IORead_Complete
0x18007db90  call    McTemplateU0s4pp_EventWriteTransfer
0x18007db95  mov     edx, [r14+78h]
0x18007db99  mov     rcx, rbx; this
0x18007db9c  add     rdx, [rbx+0F0h]; unsigned __int64
0x18007dba3  call    ?SetOffset@CMFFile@@AEAAX_K@Z; CMFFile::SetOffset(unsigned __int64)
0x18007dba8  jmp     short loc_18007DBB0
0x18007dbaa  mov     edi, [rbx+0C8h]
0x18007dbb0  mov     rcx, rsi; lpCriticalSection
0x18007dbb3  call    cs:__imp_LeaveCriticalSection
0x18007dbb9  mov     rax, [r14]
0x18007dbbc  mov     rcx, r14
0x18007dbbf  mov     rax, [rax+10h]
0x18007dbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dbc8  jmp     short loc_18007DBD8
0x18007dbca  mov     rcx, rsi; lpCriticalSection
0x18007dbcd  mov     edi, 8007000Eh
0x18007dbd2  call    cs:__imp_LeaveCriticalSection
0x18007dbd8  lea     rcx, [rbp+arg_0]; this
0x18007dbdc  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007dbe1  mov     eax, edi
0x18007dbe3  jmp     short loc_18007DC0F
0x18007dbe5  mov     ebx, [rbx+0C8h]
0x18007dbeb  mov     rcx, rsi; lpCriticalSection
0x18007dbee  call    cs:__imp_LeaveCriticalSection
0x18007dbf4  lea     rcx, [rbp+arg_0]; this
0x18007dbf8  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007dbfd  mov     eax, ebx
0x18007dbff  jmp     short loc_18007DC0F
0x18007dc01  lea     rcx, [rbp+arg_0]; this
0x18007dc05  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007dc0a  mov     eax, 80070057h
0x18007dc0f  lea     r11, [rsp+40h+var_s0]
0x18007dc14  mov     rbx, [r11+38h]
0x18007dc18  mov     rsi, [r11+40h]
0x18007dc1c  mov     rsp, r11
0x18007dc1f  pop     r15
0x18007dc21  pop     r14
0x18007dc23  pop     r12
0x18007dc25  pop     rdi
0x18007dc26  pop     rbp
0x18007dc27  retn
```
