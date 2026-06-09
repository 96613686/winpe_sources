# ATL::CDialogImpl<CAdvIpcfgDlg,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x180059128`
- end: `0x180059212`
- name: `?DoModal@?$CDialogImpl@VCAdvIpcfgDlg@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005a450`

## callees

- `0x180023cac`
- `0x180027f20`
- `0x1800348b0`
- `0x1800349c4`
- `0x180059128`
- `0x180060544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059157`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059157`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005920b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005920b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005918f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005918f`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImpl<CAdvIpcfgDlg,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x180059211LL);
    }
    *(_QWORD *)(a1 + 16) = a1;
    v7 = 0;
    *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
    v6 = qword_180089778;
    if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v6) >= 0 )
    {
      *(_QWORD *)(a1 + 32) = qword_1800897A0;
      qword_1800897A0 = a1 + 16;
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v6);
    return SHFusionDialogBoxParam(
             hInst,
             (LPCWSTR)0x5EEC,
             a2,
             (DLGPROC)ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc,
             0);
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
0x180059128  mov     [rsp+arg_0], rbx
0x18005912d  mov     [rsp+arg_8], rsi
0x180059132  push    rdi
0x180059133  sub     rsp, 40h
0x180059137  mov     rax, [rcx+28h]
0x18005913b  mov     rsi, rdx
0x18005913e  mov     rdi, rcx
0x180059141  test    rax, rax
0x180059144  jnz     short loc_180059171
0x180059146  call    AtlThunk_AllocateData
0x18005914b  mov     [rdi+28h], rax
0x18005914f  test    rax, rax
0x180059152  jnz     short loc_180059171
0x180059154  lea     ecx, [rax+0Eh]; dwErrCode
0x180059157  call    cs:__imp_SetLastError
0x18005915d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059161  mov     rbx, [rsp+48h+arg_0]
0x180059166  mov     rsi, [rsp+48h+arg_8]
0x18005916b  add     rsp, 40h
0x18005916f  pop     rdi
0x180059170  retn
0x180059171  xor     r8d, r8d; FirstParameter
0x180059174  xor     edx, edx; Proc
0x180059176  mov     rcx, rax; Thunk
0x180059179  call    AtlThunk_InitData
0x18005917e  lea     rbx, [rdi+10h]
0x180059182  test    rbx, rbx
0x180059185  jz      short loc_1800591FC
0x180059187  test    rdi, rdi
0x18005918a  jz      short loc_1800591FC
0x18005918c  mov     [rbx], rdi
0x18005918f  call    cs:__imp_GetCurrentThreadId
0x180059195  lea     rcx, [rsp+48h+var_18]
0x18005919a  mov     [rsp+48h+var_10], 0
0x18005919f  mov     [rbx+8], eax
0x1800591a2  lea     rax, qword_180089778
0x1800591a9  mov     [rsp+48h+var_18], rax
0x1800591ae  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800591b3  test    eax, eax
0x1800591b5  js      short loc_1800591C9
0x1800591b7  mov     rax, cs:qword_1800897A0
0x1800591be  mov     [rbx+10h], rax
0x1800591c2  mov     cs:qword_1800897A0, rbx
0x1800591c9  lea     rcx, [rsp+48h+var_18]
0x1800591ce  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800591d3  mov     rcx, cs:hInst; hInstance
0x1800591da  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800591e1  mov     r8, rsi; hWndParent
0x1800591e4  mov     [rsp+48h+var_28], 0; LPARAM
0x1800591ed  mov     edx, 5EECh; lpTemplateName
0x1800591f2  call    SHFusionDialogBoxParam
0x1800591f7  jmp     loc_180059161
0x1800591fc  xor     r9d, r9d; lpArguments
0x1800591ff  xor     r8d, r8d; nNumberOfArguments
0x180059202  mov     ecx, 0C0000005h; dwExceptionCode
0x180059207  lea     edx, [r9+1]; dwExceptionFlags
0x18005920b  call    cs:__imp_RaiseException
```
