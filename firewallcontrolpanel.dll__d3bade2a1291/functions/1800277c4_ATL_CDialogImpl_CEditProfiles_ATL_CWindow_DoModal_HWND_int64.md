# ATL::CDialogImpl<CEditProfiles,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x1800277c4`
- end: `0x1800278af`
- name: `?DoModal@?$CDialogImpl@VCEditProfiles@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `235`
- prototype: `INT_PTR __fastcall(__int64, HWND)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180027fb4`
- `0x180028ca4`
- `0x180029b60`

## callees

- `0x180009a80`
- `0x18000b0cc`
- `0x1800277c4`
- `0x18002d634`
- `0x18002d748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800278a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800278a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800277f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800277f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002782b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002782b`
- `USER32!DialogBoxParamW` at `0x18002788e`
- `USER32!DialogBoxParamW` at `0x18002788e`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImpl<CEditProfiles,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x1800278AELL);
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
    return DialogBoxParamW(hInstance, (LPCWSTR)0x5E1, a2, ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc, 0);
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
0x1800277c4  mov     [rsp+arg_0], rbx
0x1800277c9  mov     [rsp+arg_8], rsi
0x1800277ce  push    rdi
0x1800277cf  sub     rsp, 40h
0x1800277d3  mov     rax, [rcx+28h]
0x1800277d7  mov     rsi, rdx
0x1800277da  mov     rdi, rcx
0x1800277dd  test    rax, rax
0x1800277e0  jnz     short loc_18002780D
0x1800277e2  call    AtlThunk_AllocateData
0x1800277e7  mov     [rdi+28h], rax
0x1800277eb  test    rax, rax
0x1800277ee  jnz     short loc_18002780D
0x1800277f0  lea     ecx, [rax+0Eh]; dwErrCode
0x1800277f3  call    cs:__imp_SetLastError
0x1800277f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800277fd  mov     rbx, [rsp+48h+arg_0]
0x180027802  mov     rsi, [rsp+48h+arg_8]
0x180027807  add     rsp, 40h
0x18002780b  pop     rdi
0x18002780c  retn
0x18002780d  xor     r8d, r8d; FirstParameter
0x180027810  xor     edx, edx; Proc
0x180027812  mov     rcx, rax; Thunk
0x180027815  call    AtlThunk_InitData
0x18002781a  lea     rbx, [rdi+10h]
0x18002781e  test    rbx, rbx
0x180027821  jz      short loc_180027899
0x180027823  test    rdi, rdi
0x180027826  jz      short loc_180027899
0x180027828  mov     [rbx], rdi
0x18002782b  call    cs:__imp_GetCurrentThreadId
0x180027831  lea     rcx, [rsp+48h+var_18]
0x180027836  mov     [rsp+48h+var_10], 0
0x18002783b  mov     [rbx+8], eax
0x18002783e  lea     rax, qword_180045AA8
0x180027845  mov     [rsp+48h+var_18], rax
0x18002784a  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18002784f  test    eax, eax
0x180027851  js      short loc_180027865
0x180027853  mov     rax, cs:qword_180045AD0
0x18002785a  mov     [rbx+10h], rax
0x18002785e  mov     cs:qword_180045AD0, rbx
0x180027865  lea     rcx, [rsp+48h+var_18]
0x18002786a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002786f  mov     rcx, cs:hInstance; hInstance
0x180027876  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18002787d  mov     r8, rsi; hWndParent
0x180027880  mov     [rsp+48h+dwInitParam], 0; dwInitParam
0x180027889  mov     edx, 5E1h; lpTemplateName
0x18002788e  call    cs:__imp_DialogBoxParamW
0x180027894  jmp     loc_1800277FD
0x180027899  xor     r9d, r9d; lpArguments
0x18002789c  xor     r8d, r8d; nNumberOfArguments
0x18002789f  mov     ecx, 0C0000005h; dwExceptionCode
0x1800278a4  lea     edx, [r9+1]; dwExceptionFlags
0x1800278a8  call    cs:__imp_RaiseException
```
