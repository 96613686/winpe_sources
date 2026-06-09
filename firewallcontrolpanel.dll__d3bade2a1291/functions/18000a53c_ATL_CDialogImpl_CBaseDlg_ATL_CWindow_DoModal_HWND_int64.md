# ATL::CDialogImpl<CBaseDlg,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x18000a53c`
- end: `0x18000a627`
- name: `?DoModal@?$CDialogImpl@VCBaseDlg@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `235`
- prototype: `INT_PTR __fastcall(__int64, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b8b0`

## callees

- `0x180009a80`
- `0x18000a53c`
- `0x18000b0cc`
- `0x18002d634`
- `0x18002d748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a620`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a620`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a56b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a56b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5a3`
- `USER32!DialogBoxParamW` at `0x18000a606`
- `USER32!DialogBoxParamW` at `0x18000a606`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImpl<CBaseDlg,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
{
  AtlThunkData_t *Data; // rax
  __int64 *v6; // [rsp+30h] [rbp-18h] BYREF
  char v7; // [rsp+38h] [rbp-10h]

  Data = *(AtlThunkData_t **)(a1 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(a1 + 40) = Data) != 0) )
  {
    AtlThunk_InitData(Data, 0, 0);
    if ( a1 == -16 || !a1 )
    {
      RaiseException(0xC0000005, 1u, 0, 0);
      JUMPOUT(0x18000A626LL);
    }
    *(_QWORD *)(a1 + 16) = a1;
    v7 = 0;
    *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
    v6 = qword_180045AA8;
    if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v6) >= 0 )
    {
      *(_QWORD *)(a1 + 32) = qword_180045AD0;
      qword_180045AD0 = a1 + 16;
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v6);
    return DialogBoxParamW(hInstance, (LPCWSTR)0x5DC, a2, ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc, 0);
  }
  else
  {
    SetLastError(0xEu);
    return -1;
  }
}

```

## disassembly

```asm
0x18000a53c  mov     [rsp+arg_0], rbx
0x18000a541  mov     [rsp+arg_8], rsi
0x18000a546  push    rdi
0x18000a547  sub     rsp, 40h
0x18000a54b  mov     rax, [rcx+28h]
0x18000a54f  mov     rsi, rdx
0x18000a552  mov     rdi, rcx
0x18000a555  test    rax, rax
0x18000a558  jnz     short loc_18000A585
0x18000a55a  call    AtlThunk_AllocateData
0x18000a55f  mov     [rdi+28h], rax
0x18000a563  test    rax, rax
0x18000a566  jnz     short loc_18000A585
0x18000a568  lea     ecx, [rax+0Eh]; dwErrCode
0x18000a56b  call    cs:__imp_SetLastError
0x18000a571  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a575  mov     rbx, [rsp+48h+arg_0]
0x18000a57a  mov     rsi, [rsp+48h+arg_8]
0x18000a57f  add     rsp, 40h
0x18000a583  pop     rdi
0x18000a584  retn
0x18000a585  xor     r8d, r8d; FirstParameter
0x18000a588  xor     edx, edx; Proc
0x18000a58a  mov     rcx, rax; Thunk
0x18000a58d  call    AtlThunk_InitData
0x18000a592  lea     rbx, [rdi+10h]
0x18000a596  test    rbx, rbx
0x18000a599  jz      short loc_18000A611
0x18000a59b  test    rdi, rdi
0x18000a59e  jz      short loc_18000A611
0x18000a5a0  mov     [rbx], rdi
0x18000a5a3  call    cs:__imp_GetCurrentThreadId
0x18000a5a9  lea     rcx, [rsp+48h+var_18]
0x18000a5ae  mov     [rsp+48h+var_10], 0
0x18000a5b3  mov     [rbx+8], eax
0x18000a5b6  lea     rax, qword_180045AA8
0x18000a5bd  mov     [rsp+48h+var_18], rax
0x18000a5c2  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000a5c7  test    eax, eax
0x18000a5c9  js      short loc_18000A5DD
0x18000a5cb  mov     rax, cs:qword_180045AD0
0x18000a5d2  mov     [rbx+10h], rax
0x18000a5d6  mov     cs:qword_180045AD0, rbx
0x18000a5dd  lea     rcx, [rsp+48h+var_18]
0x18000a5e2  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000a5e7  mov     rcx, cs:hInstance; hInstance
0x18000a5ee  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000a5f5  mov     r8, rsi; hWndParent
0x18000a5f8  mov     [rsp+48h+dwInitParam], 0; dwInitParam
0x18000a601  mov     edx, 5DCh; lpTemplateName
0x18000a606  call    cs:__imp_DialogBoxParamW
0x18000a60c  jmp     loc_18000A575
0x18000a611  xor     r9d, r9d; lpArguments
0x18000a614  xor     r8d, r8d; nNumberOfArguments
0x18000a617  mov     ecx, 0C0000005h; dwExceptionCode
0x18000a61c  lea     edx, [r9+1]; dwExceptionFlags
0x18000a620  call    cs:__imp_RaiseException
```
