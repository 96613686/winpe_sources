# ATL::CDialogImpl<CLanAddComponentDlg,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x18002bfb8`
- end: `0x18002c0a2`
- name: `?DoModal@?$CDialogImpl@VCLanAddComponentDlg@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002c334`

## callees

- `0x180023cac`
- `0x180027f20`
- `0x18002bfb8`
- `0x1800348b0`
- `0x1800349c4`
- `0x180060544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bfe7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bfe7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c09b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c09b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c01f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c01f`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImpl<CLanAddComponentDlg,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x18002C0A1LL);
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
    return SHFusionDialogBoxParam(hInst, (LPCWSTR)0x3E81, a2, ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc, 0);
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
0x18002bfb8  mov     [rsp+arg_0], rbx
0x18002bfbd  mov     [rsp+arg_8], rsi
0x18002bfc2  push    rdi
0x18002bfc3  sub     rsp, 40h
0x18002bfc7  mov     rax, [rcx+28h]
0x18002bfcb  mov     rsi, rdx
0x18002bfce  mov     rdi, rcx
0x18002bfd1  test    rax, rax
0x18002bfd4  jnz     short loc_18002C001
0x18002bfd6  call    AtlThunk_AllocateData
0x18002bfdb  mov     [rdi+28h], rax
0x18002bfdf  test    rax, rax
0x18002bfe2  jnz     short loc_18002C001
0x18002bfe4  lea     ecx, [rax+0Eh]; dwErrCode
0x18002bfe7  call    cs:__imp_SetLastError
0x18002bfed  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bff1  mov     rbx, [rsp+48h+arg_0]
0x18002bff6  mov     rsi, [rsp+48h+arg_8]
0x18002bffb  add     rsp, 40h
0x18002bfff  pop     rdi
0x18002c000  retn
0x18002c001  xor     r8d, r8d; FirstParameter
0x18002c004  xor     edx, edx; Proc
0x18002c006  mov     rcx, rax; Thunk
0x18002c009  call    AtlThunk_InitData
0x18002c00e  lea     rbx, [rdi+10h]
0x18002c012  test    rbx, rbx
0x18002c015  jz      short loc_18002C08C
0x18002c017  test    rdi, rdi
0x18002c01a  jz      short loc_18002C08C
0x18002c01c  mov     [rbx], rdi
0x18002c01f  call    cs:__imp_GetCurrentThreadId
0x18002c025  lea     rcx, [rsp+48h+var_18]
0x18002c02a  mov     [rsp+48h+var_10], 0
0x18002c02f  mov     [rbx+8], eax
0x18002c032  lea     rax, qword_180089778
0x18002c039  mov     [rsp+48h+var_18], rax
0x18002c03e  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18002c043  test    eax, eax
0x18002c045  js      short loc_18002C059
0x18002c047  mov     rax, cs:qword_1800897A0
0x18002c04e  mov     [rbx+10h], rax
0x18002c052  mov     cs:qword_1800897A0, rbx
0x18002c059  lea     rcx, [rsp+48h+var_18]
0x18002c05e  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002c063  mov     rcx, cs:hInst; hInstance
0x18002c06a  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18002c071  mov     r8, rsi; hWndParent
0x18002c074  mov     [rsp+48h+var_28], 0; LPARAM
0x18002c07d  mov     edx, 3E81h; lpTemplateName
0x18002c082  call    SHFusionDialogBoxParam
0x18002c087  jmp     loc_18002BFF1
0x18002c08c  xor     r9d, r9d; lpArguments
0x18002c08f  xor     r8d, r8d; nNumberOfArguments
0x18002c092  mov     ecx, 0C0000005h; dwExceptionCode
0x18002c097  lea     edx, [r9+1]; dwExceptionFlags
0x18002c09b  call    cs:__imp_RaiseException
```
