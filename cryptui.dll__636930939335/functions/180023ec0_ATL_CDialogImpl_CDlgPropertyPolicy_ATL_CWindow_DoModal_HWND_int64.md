# ATL::CDialogImpl<CDlgPropertyPolicy,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x180023ec0`
- end: `0x180023faa`
- name: `?DoModal@?$CDialogImpl@VCDlgPropertyPolicy@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023890`

## callees

- `0x180004fe0`
- `0x1800133d4`
- `0x180014908`
- `0x180023ec0`
- `0x180039650`
- `0x180039764`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023fa3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023fa3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023eef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023eef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023f27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023f27`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImpl<CDlgPropertyPolicy,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x180023FA9LL);
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
             (LPCWSTR)0xA3,
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
0x180023ec0  mov     [rsp+arg_0], rbx
0x180023ec5  mov     [rsp+arg_8], rsi
0x180023eca  push    rdi
0x180023ecb  sub     rsp, 40h
0x180023ecf  mov     rsi, rdx
0x180023ed2  mov     rdi, rcx
0x180023ed5  mov     rax, [rcx+28h]
0x180023ed9  test    rax, rax
0x180023edc  jnz     short loc_180023F09
0x180023ede  call    AtlThunk_AllocateData
0x180023ee3  mov     [rdi+28h], rax
0x180023ee7  test    rax, rax
0x180023eea  jnz     short loc_180023F09
0x180023eec  lea     ecx, [rax+0Eh]; dwErrCode
0x180023eef  call    cs:__imp_SetLastError
0x180023ef5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023ef9  mov     rbx, [rsp+48h+arg_0]
0x180023efe  mov     rsi, [rsp+48h+arg_8]
0x180023f03  add     rsp, 40h
0x180023f07  pop     rdi
0x180023f08  retn
0x180023f09  xor     r8d, r8d; FirstParameter
0x180023f0c  xor     edx, edx; Proc
0x180023f0e  mov     rcx, rax; Thunk
0x180023f11  call    AtlThunk_InitData
0x180023f16  lea     rbx, [rdi+10h]
0x180023f1a  test    rbx, rbx
0x180023f1d  jz      short loc_180023F94
0x180023f1f  test    rdi, rdi
0x180023f22  jz      short loc_180023F94
0x180023f24  mov     [rbx], rdi
0x180023f27  call    cs:__imp_GetCurrentThreadId
0x180023f2d  mov     [rbx+8], eax
0x180023f30  lea     rax, qword_180050388
0x180023f37  mov     [rsp+48h+var_18], rax
0x180023f3c  mov     [rsp+48h+var_10], 0
0x180023f41  lea     rcx, [rsp+48h+var_18]
0x180023f46  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180023f4b  test    eax, eax
0x180023f4d  js      short loc_180023F61
0x180023f4f  mov     rax, cs:qword_1800503B0
0x180023f56  mov     [rbx+10h], rax
0x180023f5a  mov     cs:qword_1800503B0, rbx
0x180023f61  lea     rcx, [rsp+48h+var_18]
0x180023f66  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180023f6b  mov     [rsp+48h+var_28], 0; LPARAM
0x180023f74  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180023f7b  mov     r8, rsi; hWndParent
0x180023f7e  mov     edx, 0A3h; lpTemplateName
0x180023f83  mov     rcx, cs:qword_180050CA0; hInstance
0x180023f8a  call    IsolationAwareDialogBoxParamW
0x180023f8f  jmp     loc_180023EF9
0x180023f94  xor     r9d, r9d; lpArguments
0x180023f97  xor     r8d, r8d; nNumberOfArguments
0x180023f9a  lea     edx, [r9+1]; dwExceptionFlags
0x180023f9e  mov     ecx, 0C0000005h; dwExceptionCode
0x180023fa3  call    cs:__imp_RaiseException
```
