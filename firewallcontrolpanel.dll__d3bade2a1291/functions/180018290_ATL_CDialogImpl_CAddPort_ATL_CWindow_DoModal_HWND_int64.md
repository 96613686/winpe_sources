# ATL::CDialogImpl<CAddPort,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x180018290`
- end: `0x18001837b`
- name: `?DoModal@?$CDialogImpl@VCAddPort@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `235`
- prototype: `INT_PTR __fastcall(__int64, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001aaec`

## callees

- `0x180009a80`
- `0x18000b0cc`
- `0x180018290`
- `0x18002d634`
- `0x18002d748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018374`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018374`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800182bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800182bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800182f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800182f7`
- `USER32!DialogBoxParamW` at `0x18001835a`
- `USER32!DialogBoxParamW` at `0x18001835a`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImpl<CAddPort,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x18001837ALL);
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
    return DialogBoxParamW(hInstance, (LPCWSTR)0x5DF, a2, ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc, 0);
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
0x180018290  mov     [rsp+arg_0], rbx
0x180018295  mov     [rsp+arg_8], rsi
0x18001829a  push    rdi
0x18001829b  sub     rsp, 40h
0x18001829f  mov     rax, [rcx+28h]
0x1800182a3  mov     rsi, rdx
0x1800182a6  mov     rdi, rcx
0x1800182a9  test    rax, rax
0x1800182ac  jnz     short loc_1800182D9
0x1800182ae  call    AtlThunk_AllocateData
0x1800182b3  mov     [rdi+28h], rax
0x1800182b7  test    rax, rax
0x1800182ba  jnz     short loc_1800182D9
0x1800182bc  lea     ecx, [rax+0Eh]; dwErrCode
0x1800182bf  call    cs:__imp_SetLastError
0x1800182c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800182c9  mov     rbx, [rsp+48h+arg_0]
0x1800182ce  mov     rsi, [rsp+48h+arg_8]
0x1800182d3  add     rsp, 40h
0x1800182d7  pop     rdi
0x1800182d8  retn
0x1800182d9  xor     r8d, r8d; FirstParameter
0x1800182dc  xor     edx, edx; Proc
0x1800182de  mov     rcx, rax; Thunk
0x1800182e1  call    AtlThunk_InitData
0x1800182e6  lea     rbx, [rdi+10h]
0x1800182ea  test    rbx, rbx
0x1800182ed  jz      short loc_180018365
0x1800182ef  test    rdi, rdi
0x1800182f2  jz      short loc_180018365
0x1800182f4  mov     [rbx], rdi
0x1800182f7  call    cs:__imp_GetCurrentThreadId
0x1800182fd  lea     rcx, [rsp+48h+var_18]
0x180018302  mov     [rsp+48h+var_10], 0
0x180018307  mov     [rbx+8], eax
0x18001830a  lea     rax, qword_180045AA8
0x180018311  mov     [rsp+48h+var_18], rax
0x180018316  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18001831b  test    eax, eax
0x18001831d  js      short loc_180018331
0x18001831f  mov     rax, cs:qword_180045AD0
0x180018326  mov     [rbx+10h], rax
0x18001832a  mov     cs:qword_180045AD0, rbx
0x180018331  lea     rcx, [rsp+48h+var_18]
0x180018336  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001833b  mov     rcx, cs:hInstance; hInstance
0x180018342  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180018349  mov     r8, rsi; hWndParent
0x18001834c  mov     [rsp+48h+dwInitParam], 0; dwInitParam
0x180018355  mov     edx, 5DFh; lpTemplateName
0x18001835a  call    cs:__imp_DialogBoxParamW
0x180018360  jmp     loc_1800182C9
0x180018365  xor     r9d, r9d; lpArguments
0x180018368  xor     r8d, r8d; nNumberOfArguments
0x18001836b  mov     ecx, 0C0000005h; dwExceptionCode
0x180018370  lea     edx, [r9+1]; dwExceptionFlags
0x180018374  call    cs:__imp_RaiseException
```
