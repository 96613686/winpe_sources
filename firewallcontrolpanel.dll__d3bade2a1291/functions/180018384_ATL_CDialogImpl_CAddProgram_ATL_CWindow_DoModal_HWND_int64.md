# ATL::CDialogImpl<CAddProgram,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x180018384`
- end: `0x18001846f`
- name: `?DoModal@?$CDialogImpl@VCAddProgram@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `235`
- prototype: `INT_PTR __fastcall(__int64, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180019c00`

## callees

- `0x180009a80`
- `0x18000b0cc`
- `0x180018384`
- `0x18002d634`
- `0x18002d748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018468`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018468`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800183b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800183b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183eb`
- `USER32!DialogBoxParamW` at `0x18001844e`
- `USER32!DialogBoxParamW` at `0x18001844e`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImpl<CAddProgram,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x18001846ELL);
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
    return DialogBoxParamW(hInstance, (LPCWSTR)0x5DE, a2, ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc, 0);
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
0x180018384  mov     [rsp+arg_0], rbx
0x180018389  mov     [rsp+arg_8], rsi
0x18001838e  push    rdi
0x18001838f  sub     rsp, 40h
0x180018393  mov     rax, [rcx+28h]
0x180018397  mov     rsi, rdx
0x18001839a  mov     rdi, rcx
0x18001839d  test    rax, rax
0x1800183a0  jnz     short loc_1800183CD
0x1800183a2  call    AtlThunk_AllocateData
0x1800183a7  mov     [rdi+28h], rax
0x1800183ab  test    rax, rax
0x1800183ae  jnz     short loc_1800183CD
0x1800183b0  lea     ecx, [rax+0Eh]; dwErrCode
0x1800183b3  call    cs:__imp_SetLastError
0x1800183b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800183bd  mov     rbx, [rsp+48h+arg_0]
0x1800183c2  mov     rsi, [rsp+48h+arg_8]
0x1800183c7  add     rsp, 40h
0x1800183cb  pop     rdi
0x1800183cc  retn
0x1800183cd  xor     r8d, r8d; FirstParameter
0x1800183d0  xor     edx, edx; Proc
0x1800183d2  mov     rcx, rax; Thunk
0x1800183d5  call    AtlThunk_InitData
0x1800183da  lea     rbx, [rdi+10h]
0x1800183de  test    rbx, rbx
0x1800183e1  jz      short loc_180018459
0x1800183e3  test    rdi, rdi
0x1800183e6  jz      short loc_180018459
0x1800183e8  mov     [rbx], rdi
0x1800183eb  call    cs:__imp_GetCurrentThreadId
0x1800183f1  lea     rcx, [rsp+48h+var_18]
0x1800183f6  mov     [rsp+48h+var_10], 0
0x1800183fb  mov     [rbx+8], eax
0x1800183fe  lea     rax, qword_180045AA8
0x180018405  mov     [rsp+48h+var_18], rax
0x18001840a  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18001840f  test    eax, eax
0x180018411  js      short loc_180018425
0x180018413  mov     rax, cs:qword_180045AD0
0x18001841a  mov     [rbx+10h], rax
0x18001841e  mov     cs:qword_180045AD0, rbx
0x180018425  lea     rcx, [rsp+48h+var_18]
0x18001842a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001842f  mov     rcx, cs:hInstance; hInstance
0x180018436  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18001843d  mov     r8, rsi; hWndParent
0x180018440  mov     [rsp+48h+dwInitParam], 0; dwInitParam
0x180018449  mov     edx, 5DEh; lpTemplateName
0x18001844e  call    cs:__imp_DialogBoxParamW
0x180018454  jmp     loc_1800183BD
0x180018459  xor     r9d, r9d; lpArguments
0x18001845c  xor     r8d, r8d; nNumberOfArguments
0x18001845f  mov     ecx, 0C0000005h; dwExceptionCode
0x180018464  lea     edx, [r9+1]; dwExceptionFlags
0x180018468  call    cs:__imp_RaiseException
```
