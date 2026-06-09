# ATL::CDialogImpl<CDlgAddPolicyServer,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x180023ce0`
- end: `0x180023dca`
- name: `?DoModal@?$CDialogImpl@VCDlgAddPolicyServer@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023710`

## callees

- `0x180004fe0`
- `0x1800133d4`
- `0x180014908`
- `0x180023ce0`
- `0x180039650`
- `0x180039764`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023dc3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023dc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023d47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023d47`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImpl<CDlgAddPolicyServer,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x180023DC9LL);
    }
    *(_QWORD *)(a1 + 16) = a1;
    *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
    v6 = qword_180050388;
    v7 = 0;
    if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v6) >= 0 )
    {
      *(_QWORD *)(a1 + 32) = qword_1800503B0;
      qword_1800503B0 = a1 + 16;
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v6);
    return IsolationAwareDialogBoxParamW(
             qword_180050CA0,
             (LPCWSTR)0xA2,
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
0x180023ce0  mov     [rsp+arg_0], rbx
0x180023ce5  mov     [rsp+arg_8], rsi
0x180023cea  push    rdi
0x180023ceb  sub     rsp, 40h
0x180023cef  mov     rsi, rdx
0x180023cf2  mov     rdi, rcx
0x180023cf5  mov     rax, [rcx+28h]
0x180023cf9  test    rax, rax
0x180023cfc  jnz     short loc_180023D29
0x180023cfe  call    AtlThunk_AllocateData
0x180023d03  mov     [rdi+28h], rax
0x180023d07  test    rax, rax
0x180023d0a  jnz     short loc_180023D29
0x180023d0c  lea     ecx, [rax+0Eh]; dwErrCode
0x180023d0f  call    cs:__imp_SetLastError
0x180023d15  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023d19  mov     rbx, [rsp+48h+arg_0]
0x180023d1e  mov     rsi, [rsp+48h+arg_8]
0x180023d23  add     rsp, 40h
0x180023d27  pop     rdi
0x180023d28  retn
0x180023d29  xor     r8d, r8d; FirstParameter
0x180023d2c  xor     edx, edx; Proc
0x180023d2e  mov     rcx, rax; Thunk
0x180023d31  call    AtlThunk_InitData
0x180023d36  lea     rbx, [rdi+10h]
0x180023d3a  test    rbx, rbx
0x180023d3d  jz      short loc_180023DB4
0x180023d3f  test    rdi, rdi
0x180023d42  jz      short loc_180023DB4
0x180023d44  mov     [rbx], rdi
0x180023d47  call    cs:__imp_GetCurrentThreadId
0x180023d4d  mov     [rbx+8], eax
0x180023d50  lea     rax, qword_180050388
0x180023d57  mov     [rsp+48h+var_18], rax
0x180023d5c  mov     [rsp+48h+var_10], 0
0x180023d61  lea     rcx, [rsp+48h+var_18]
0x180023d66  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180023d6b  test    eax, eax
0x180023d6d  js      short loc_180023D81
0x180023d6f  mov     rax, cs:qword_1800503B0
0x180023d76  mov     [rbx+10h], rax
0x180023d7a  mov     cs:qword_1800503B0, rbx
0x180023d81  lea     rcx, [rsp+48h+var_18]
0x180023d86  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180023d8b  mov     [rsp+48h+var_28], 0; LPARAM
0x180023d94  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180023d9b  mov     r8, rsi; hWndParent
0x180023d9e  mov     edx, 0A2h; lpTemplateName
0x180023da3  mov     rcx, cs:qword_180050CA0; hInstance
0x180023daa  call    IsolationAwareDialogBoxParamW
0x180023daf  jmp     loc_180023D19
0x180023db4  xor     r9d, r9d; lpArguments
0x180023db7  xor     r8d, r8d; nNumberOfArguments
0x180023dba  lea     edx, [r9+1]; dwExceptionFlags
0x180023dbe  mov     ecx, 0C0000005h; dwExceptionCode
0x180023dc3  call    cs:__imp_RaiseException
```
