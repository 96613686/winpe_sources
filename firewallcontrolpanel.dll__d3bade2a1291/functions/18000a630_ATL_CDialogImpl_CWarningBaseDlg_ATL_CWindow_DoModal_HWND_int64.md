# ATL::CDialogImpl<CWarningBaseDlg,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x18000a630`
- end: `0x18000a71b`
- name: `?DoModal@?$CDialogImpl@VCWarningBaseDlg@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `235`
- prototype: `INT_PTR __fastcall(__int64, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000bdd0`

## callees

- `0x180009a80`
- `0x18000a630`
- `0x18000b0cc`
- `0x18002d634`
- `0x18002d748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a714`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a714`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a65f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a65f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a697`
- `USER32!DialogBoxParamW` at `0x18000a6fa`
- `USER32!DialogBoxParamW` at `0x18000a6fa`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImpl<CWarningBaseDlg,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x18000A71ALL);
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
    return DialogBoxParamW(hInstance, (LPCWSTR)0x2FB1, a2, ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc, 0);
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
0x18000a630  mov     [rsp+arg_0], rbx
0x18000a635  mov     [rsp+arg_8], rsi
0x18000a63a  push    rdi
0x18000a63b  sub     rsp, 40h
0x18000a63f  mov     rax, [rcx+28h]
0x18000a643  mov     rsi, rdx
0x18000a646  mov     rdi, rcx
0x18000a649  test    rax, rax
0x18000a64c  jnz     short loc_18000A679
0x18000a64e  call    AtlThunk_AllocateData
0x18000a653  mov     [rdi+28h], rax
0x18000a657  test    rax, rax
0x18000a65a  jnz     short loc_18000A679
0x18000a65c  lea     ecx, [rax+0Eh]; dwErrCode
0x18000a65f  call    cs:__imp_SetLastError
0x18000a665  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a669  mov     rbx, [rsp+48h+arg_0]
0x18000a66e  mov     rsi, [rsp+48h+arg_8]
0x18000a673  add     rsp, 40h
0x18000a677  pop     rdi
0x18000a678  retn
0x18000a679  xor     r8d, r8d; FirstParameter
0x18000a67c  xor     edx, edx; Proc
0x18000a67e  mov     rcx, rax; Thunk
0x18000a681  call    AtlThunk_InitData
0x18000a686  lea     rbx, [rdi+10h]
0x18000a68a  test    rbx, rbx
0x18000a68d  jz      short loc_18000A705
0x18000a68f  test    rdi, rdi
0x18000a692  jz      short loc_18000A705
0x18000a694  mov     [rbx], rdi
0x18000a697  call    cs:__imp_GetCurrentThreadId
0x18000a69d  lea     rcx, [rsp+48h+var_18]
0x18000a6a2  mov     [rsp+48h+var_10], 0
0x18000a6a7  mov     [rbx+8], eax
0x18000a6aa  lea     rax, qword_180045AA8
0x18000a6b1  mov     [rsp+48h+var_18], rax
0x18000a6b6  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000a6bb  test    eax, eax
0x18000a6bd  js      short loc_18000A6D1
0x18000a6bf  mov     rax, cs:qword_180045AD0
0x18000a6c6  mov     [rbx+10h], rax
0x18000a6ca  mov     cs:qword_180045AD0, rbx
0x18000a6d1  lea     rcx, [rsp+48h+var_18]
0x18000a6d6  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000a6db  mov     rcx, cs:hInstance; hInstance
0x18000a6e2  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000a6e9  mov     r8, rsi; hWndParent
0x18000a6ec  mov     [rsp+48h+dwInitParam], 0; dwInitParam
0x18000a6f5  mov     edx, 2FB1h; lpTemplateName
0x18000a6fa  call    cs:__imp_DialogBoxParamW
0x18000a700  jmp     loc_18000A669
0x18000a705  xor     r9d, r9d; lpArguments
0x18000a708  xor     r8d, r8d; nNumberOfArguments
0x18000a70b  mov     ecx, 0C0000005h; dwExceptionCode
0x18000a710  lea     edx, [r9+1]; dwExceptionFlags
0x18000a714  call    cs:__imp_RaiseException
```
