# ATL::CDialogImpl<CSharedAccessConnectionUiDlg,ATL::CWindow>::Create(HWND__ *,__int64)

- ea: `0x18002b030`
- end: `0x18002b103`
- name: `?Create@?$CDialogImpl@VCSharedAccessConnectionUiDlg@@VCWindow@ATL@@@ATL@@QEAAPEAUHWND__@@PEAU3@_J@Z`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002af00`
- `0x180030710`

## callees

- `0x180023cac`
- `0x180027f20`
- `0x18002b030`
- `0x1800348b0`
- `0x1800349c4`
- `0x1800604c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b05f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b05f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b0fc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b0fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b095`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b095`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImpl<CSharedAccessConnectionUiDlg,ATL::CWindow>::Create(__int64 a1)
{
  AtlThunkData_t *Data; // rax
  __int64 *v4; // [rsp+30h] [rbp-18h] BYREF
  char v5; // [rsp+38h] [rbp-10h]

  Data = *(AtlThunkData_t **)(a1 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(a1 + 40) = Data) != 0) )
  {
    AtlThunk_InitData(Data, 0, 0);
    if ( a1 == -16 || !a1 )
    {
      RaiseException(0xC0000005, 1u, 0, 0);
      JUMPOUT(0x18002B102LL);
    }
    *(_QWORD *)(a1 + 16) = a1;
    v5 = 0;
    *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
    v4 = qword_180089778;
    if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v4) >= 0 )
    {
      *(_QWORD *)(a1 + 32) = qword_1800897A0;
      qword_1800897A0 = a1 + 16;
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v4);
    return SHFusionCreateDialogParam(hInst);
  }
  else
  {
    SetLastError(0xEu);
    return 0;
  }
}

```

## disassembly

```asm
0x18002b030  mov     [rsp+arg_0], rbx
0x18002b035  mov     [rsp+arg_8], rsi
0x18002b03a  push    rdi
0x18002b03b  sub     rsp, 40h
0x18002b03f  mov     rax, [rcx+28h]
0x18002b043  mov     rsi, rdx
0x18002b046  mov     rdi, rcx
0x18002b049  test    rax, rax
0x18002b04c  jnz     short loc_18002B077
0x18002b04e  call    AtlThunk_AllocateData
0x18002b053  mov     [rdi+28h], rax
0x18002b057  test    rax, rax
0x18002b05a  jnz     short loc_18002B077
0x18002b05c  lea     ecx, [rax+0Eh]; dwErrCode
0x18002b05f  call    cs:__imp_SetLastError
0x18002b065  xor     eax, eax
0x18002b067  mov     rbx, [rsp+48h+arg_0]
0x18002b06c  mov     rsi, [rsp+48h+arg_8]
0x18002b071  add     rsp, 40h
0x18002b075  pop     rdi
0x18002b076  retn
0x18002b077  xor     r8d, r8d; FirstParameter
0x18002b07a  xor     edx, edx; Proc
0x18002b07c  mov     rcx, rax; Thunk
0x18002b07f  call    AtlThunk_InitData
0x18002b084  lea     rbx, [rdi+10h]
0x18002b088  test    rbx, rbx
0x18002b08b  jz      short loc_18002B0ED
0x18002b08d  test    rdi, rdi
0x18002b090  jz      short loc_18002B0ED
0x18002b092  mov     [rbx], rdi
0x18002b095  call    cs:__imp_GetCurrentThreadId
0x18002b09b  lea     rcx, [rsp+48h+var_18]
0x18002b0a0  mov     [rsp+48h+var_10], 0
0x18002b0a5  mov     [rbx+8], eax
0x18002b0a8  lea     rax, qword_180089778
0x18002b0af  mov     [rsp+48h+var_18], rax
0x18002b0b4  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18002b0b9  test    eax, eax
0x18002b0bb  js      short loc_18002B0CF
0x18002b0bd  mov     rax, cs:qword_1800897A0
0x18002b0c4  mov     [rbx+10h], rax
0x18002b0c8  mov     cs:qword_1800897A0, rbx
0x18002b0cf  lea     rcx, [rsp+48h+var_18]
0x18002b0d4  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002b0d9  mov     rcx, cs:hInst; hInstance
0x18002b0e0  mov     r8, rsi
0x18002b0e3  call    SHFusionCreateDialogParam
0x18002b0e8  jmp     loc_18002B067
0x18002b0ed  xor     r9d, r9d; lpArguments
0x18002b0f0  xor     r8d, r8d; nNumberOfArguments
0x18002b0f3  mov     ecx, 0C0000005h; dwExceptionCode
0x18002b0f8  lea     edx, [r9+1]; dwExceptionFlags
0x18002b0fc  call    cs:__imp_RaiseException
```
