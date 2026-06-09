# ATL::CDialogImpl<CDlgConfigureFriendlyName,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x180023dd0`
- end: `0x180023eba`
- name: `?DoModal@?$CDialogImpl@VCDlgConfigureFriendlyName@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024560`

## callees

- `0x180004fe0`
- `0x1800133d4`
- `0x180014908`
- `0x180023dd0`
- `0x180039650`
- `0x180039764`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023eb3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023eb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023dff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023dff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023e37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023e37`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImpl<CDlgConfigureFriendlyName,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x180023EB9LL);
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
             (LPCWSTR)0xA4,
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
0x180023dd0  mov     [rsp+arg_0], rbx
0x180023dd5  mov     [rsp+arg_8], rsi
0x180023dda  push    rdi
0x180023ddb  sub     rsp, 40h
0x180023ddf  mov     rsi, rdx
0x180023de2  mov     rdi, rcx
0x180023de5  mov     rax, [rcx+28h]
0x180023de9  test    rax, rax
0x180023dec  jnz     short loc_180023E19
0x180023dee  call    AtlThunk_AllocateData
0x180023df3  mov     [rdi+28h], rax
0x180023df7  test    rax, rax
0x180023dfa  jnz     short loc_180023E19
0x180023dfc  lea     ecx, [rax+0Eh]; dwErrCode
0x180023dff  call    cs:__imp_SetLastError
0x180023e05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023e09  mov     rbx, [rsp+48h+arg_0]
0x180023e0e  mov     rsi, [rsp+48h+arg_8]
0x180023e13  add     rsp, 40h
0x180023e17  pop     rdi
0x180023e18  retn
0x180023e19  xor     r8d, r8d; FirstParameter
0x180023e1c  xor     edx, edx; Proc
0x180023e1e  mov     rcx, rax; Thunk
0x180023e21  call    AtlThunk_InitData
0x180023e26  lea     rbx, [rdi+10h]
0x180023e2a  test    rbx, rbx
0x180023e2d  jz      short loc_180023EA4
0x180023e2f  test    rdi, rdi
0x180023e32  jz      short loc_180023EA4
0x180023e34  mov     [rbx], rdi
0x180023e37  call    cs:__imp_GetCurrentThreadId
0x180023e3d  mov     [rbx+8], eax
0x180023e40  lea     rax, qword_180050388
0x180023e47  mov     [rsp+48h+var_18], rax
0x180023e4c  mov     [rsp+48h+var_10], 0
0x180023e51  lea     rcx, [rsp+48h+var_18]
0x180023e56  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180023e5b  test    eax, eax
0x180023e5d  js      short loc_180023E71
0x180023e5f  mov     rax, cs:qword_1800503B0
0x180023e66  mov     [rbx+10h], rax
0x180023e6a  mov     cs:qword_1800503B0, rbx
0x180023e71  lea     rcx, [rsp+48h+var_18]
0x180023e76  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180023e7b  mov     [rsp+48h+var_28], 0; LPARAM
0x180023e84  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180023e8b  mov     r8, rsi; hWndParent
0x180023e8e  mov     edx, 0A4h; lpTemplateName
0x180023e93  mov     rcx, cs:qword_180050CA0; hInstance
0x180023e9a  call    IsolationAwareDialogBoxParamW
0x180023e9f  jmp     loc_180023E09
0x180023ea4  xor     r9d, r9d; lpArguments
0x180023ea7  xor     r8d, r8d; nNumberOfArguments
0x180023eaa  lea     edx, [r9+1]; dwExceptionFlags
0x180023eae  mov     ecx, 0C0000005h; dwExceptionCode
0x180023eb3  call    cs:__imp_RaiseException
```
