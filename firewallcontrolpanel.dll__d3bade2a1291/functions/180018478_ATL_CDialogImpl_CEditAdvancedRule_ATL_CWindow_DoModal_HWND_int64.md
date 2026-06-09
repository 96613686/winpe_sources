# ATL::CDialogImpl<CEditAdvancedRule,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x180018478`
- end: `0x180018563`
- name: `?DoModal@?$CDialogImpl@VCEditAdvancedRule@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
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
- `0x180018478`
- `0x18002d634`
- `0x18002d748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001855c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001855c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800184a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800184a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800184df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800184df`
- `USER32!DialogBoxParamW` at `0x180018542`
- `USER32!DialogBoxParamW` at `0x180018542`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImpl<CEditAdvancedRule,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x180018562LL);
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
    return DialogBoxParamW(hInstance, (LPCWSTR)0x5DD, a2, ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc, 0);
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
0x180018478  mov     [rsp+arg_0], rbx
0x18001847d  mov     [rsp+arg_8], rsi
0x180018482  push    rdi
0x180018483  sub     rsp, 40h
0x180018487  mov     rax, [rcx+28h]
0x18001848b  mov     rsi, rdx
0x18001848e  mov     rdi, rcx
0x180018491  test    rax, rax
0x180018494  jnz     short loc_1800184C1
0x180018496  call    AtlThunk_AllocateData
0x18001849b  mov     [rdi+28h], rax
0x18001849f  test    rax, rax
0x1800184a2  jnz     short loc_1800184C1
0x1800184a4  lea     ecx, [rax+0Eh]; dwErrCode
0x1800184a7  call    cs:__imp_SetLastError
0x1800184ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800184b1  mov     rbx, [rsp+48h+arg_0]
0x1800184b6  mov     rsi, [rsp+48h+arg_8]
0x1800184bb  add     rsp, 40h
0x1800184bf  pop     rdi
0x1800184c0  retn
0x1800184c1  xor     r8d, r8d; FirstParameter
0x1800184c4  xor     edx, edx; Proc
0x1800184c6  mov     rcx, rax; Thunk
0x1800184c9  call    AtlThunk_InitData
0x1800184ce  lea     rbx, [rdi+10h]
0x1800184d2  test    rbx, rbx
0x1800184d5  jz      short loc_18001854D
0x1800184d7  test    rdi, rdi
0x1800184da  jz      short loc_18001854D
0x1800184dc  mov     [rbx], rdi
0x1800184df  call    cs:__imp_GetCurrentThreadId
0x1800184e5  lea     rcx, [rsp+48h+var_18]
0x1800184ea  mov     [rsp+48h+var_10], 0
0x1800184ef  mov     [rbx+8], eax
0x1800184f2  lea     rax, qword_180045AA8
0x1800184f9  mov     [rsp+48h+var_18], rax
0x1800184fe  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180018503  test    eax, eax
0x180018505  js      short loc_180018519
0x180018507  mov     rax, cs:qword_180045AD0
0x18001850e  mov     [rbx+10h], rax
0x180018512  mov     cs:qword_180045AD0, rbx
0x180018519  lea     rcx, [rsp+48h+var_18]
0x18001851e  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180018523  mov     rcx, cs:hInstance; hInstance
0x18001852a  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180018531  mov     r8, rsi; hWndParent
0x180018534  mov     [rsp+48h+dwInitParam], 0; dwInitParam
0x18001853d  mov     edx, 5DDh; lpTemplateName
0x180018542  call    cs:__imp_DialogBoxParamW
0x180018548  jmp     loc_1800184B1
0x18001854d  xor     r9d, r9d; lpArguments
0x180018550  xor     r8d, r8d; nNumberOfArguments
0x180018553  mov     ecx, 0C0000005h; dwExceptionCode
0x180018558  lea     edx, [r9+1]; dwExceptionFlags
0x18001855c  call    cs:__imp_RaiseException
```
