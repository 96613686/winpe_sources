# ATL::CDialogImpl<CViewExpiringCertificatesDialog,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x180013ce4`
- end: `0x180013dce`
- name: `?DoModal@?$CDialogImpl@VCViewExpiringCertificatesDialog@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800157e0`

## callees

- `0x180004fe0`
- `0x1800133d4`
- `0x180013ce4`
- `0x180014908`
- `0x180039650`
- `0x180039764`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013dc7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013dc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013d13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013d13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013d4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013d4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CDialogImpl<CViewExpiringCertificatesDialog,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x180013DCDLL);
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
             (LPCWSTR)0x9D,
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
0x180013ce4  mov     [rsp+arg_0], rbx
0x180013ce9  mov     [rsp+arg_8], rsi
0x180013cee  push    rdi
0x180013cef  sub     rsp, 40h
0x180013cf3  mov     rsi, rdx
0x180013cf6  mov     rdi, rcx
0x180013cf9  mov     rax, [rcx+28h]
0x180013cfd  test    rax, rax
0x180013d00  jnz     short loc_180013D2D
0x180013d02  call    AtlThunk_AllocateData
0x180013d07  mov     [rdi+28h], rax
0x180013d0b  test    rax, rax
0x180013d0e  jnz     short loc_180013D2D
0x180013d10  lea     ecx, [rax+0Eh]; dwErrCode
0x180013d13  call    cs:__imp_SetLastError
0x180013d19  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013d1d  mov     rbx, [rsp+48h+arg_0]
0x180013d22  mov     rsi, [rsp+48h+arg_8]
0x180013d27  add     rsp, 40h
0x180013d2b  pop     rdi
0x180013d2c  retn
0x180013d2d  xor     r8d, r8d; FirstParameter
0x180013d30  xor     edx, edx; Proc
0x180013d32  mov     rcx, rax; Thunk
0x180013d35  call    AtlThunk_InitData
0x180013d3a  lea     rbx, [rdi+10h]
0x180013d3e  test    rbx, rbx
0x180013d41  jz      short loc_180013DB8
0x180013d43  test    rdi, rdi
0x180013d46  jz      short loc_180013DB8
0x180013d48  mov     [rbx], rdi
0x180013d4b  call    cs:__imp_GetCurrentThreadId
0x180013d51  mov     [rbx+8], eax
0x180013d54  lea     rax, qword_180050388
0x180013d5b  mov     [rsp+48h+var_18], rax
0x180013d60  mov     [rsp+48h+var_10], 0
0x180013d65  lea     rcx, [rsp+48h+var_18]
0x180013d6a  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180013d6f  test    eax, eax
0x180013d71  js      short loc_180013D85
0x180013d73  mov     rax, cs:qword_1800503B0
0x180013d7a  mov     [rbx+10h], rax
0x180013d7e  mov     cs:qword_1800503B0, rbx
0x180013d85  lea     rcx, [rsp+48h+var_18]
0x180013d8a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180013d8f  mov     [rsp+48h+var_28], 0; LPARAM
0x180013d98  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180013d9f  mov     r8, rsi; hWndParent
0x180013da2  mov     edx, 9Dh; lpTemplateName
0x180013da7  mov     rcx, cs:qword_180050CA0; hInstance
0x180013dae  call    IsolationAwareDialogBoxParamW
0x180013db3  jmp     loc_180013D1D
0x180013db8  xor     r9d, r9d; lpArguments
0x180013dbb  xor     r8d, r8d; nNumberOfArguments
0x180013dbe  lea     edx, [r9+1]; dwExceptionFlags
0x180013dc2  mov     ecx, 0C0000005h; dwExceptionCode
0x180013dc7  call    cs:__imp_RaiseException
```
