# ATL::CDialogImpl<CEditAppSettings,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x18001856c`
- end: `0x180018657`
- name: `?DoModal@?$CDialogImpl@VCEditAppSettings@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `235`
- prototype: `INT_PTR __fastcall(__int64, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aaec`

## callees

- `0x180009a80`
- `0x18000b0cc`
- `0x18001856c`
- `0x18002d634`
- `0x18002d748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018650`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018650`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001859b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001859b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800185d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800185d3`
- `USER32!DialogBoxParamW` at `0x180018636`
- `USER32!DialogBoxParamW` at `0x180018636`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImpl<CEditAppSettings,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x180018656LL);
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
    return DialogBoxParamW(hInstance, (LPCWSTR)0x5E0, a2, ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc, 0);
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
0x18001856c  mov     [rsp+arg_0], rbx
0x180018571  mov     [rsp+arg_8], rsi
0x180018576  push    rdi
0x180018577  sub     rsp, 40h
0x18001857b  mov     rax, [rcx+28h]
0x18001857f  mov     rsi, rdx
0x180018582  mov     rdi, rcx
0x180018585  test    rax, rax
0x180018588  jnz     short loc_1800185B5
0x18001858a  call    AtlThunk_AllocateData
0x18001858f  mov     [rdi+28h], rax
0x180018593  test    rax, rax
0x180018596  jnz     short loc_1800185B5
0x180018598  lea     ecx, [rax+0Eh]; dwErrCode
0x18001859b  call    cs:__imp_SetLastError
0x1800185a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800185a5  mov     rbx, [rsp+48h+arg_0]
0x1800185aa  mov     rsi, [rsp+48h+arg_8]
0x1800185af  add     rsp, 40h
0x1800185b3  pop     rdi
0x1800185b4  retn
0x1800185b5  xor     r8d, r8d; FirstParameter
0x1800185b8  xor     edx, edx; Proc
0x1800185ba  mov     rcx, rax; Thunk
0x1800185bd  call    AtlThunk_InitData
0x1800185c2  lea     rbx, [rdi+10h]
0x1800185c6  test    rbx, rbx
0x1800185c9  jz      short loc_180018641
0x1800185cb  test    rdi, rdi
0x1800185ce  jz      short loc_180018641
0x1800185d0  mov     [rbx], rdi
0x1800185d3  call    cs:__imp_GetCurrentThreadId
0x1800185d9  lea     rcx, [rsp+48h+var_18]
0x1800185de  mov     [rsp+48h+var_10], 0
0x1800185e3  mov     [rbx+8], eax
0x1800185e6  lea     rax, qword_180045AA8
0x1800185ed  mov     [rsp+48h+var_18], rax
0x1800185f2  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800185f7  test    eax, eax
0x1800185f9  js      short loc_18001860D
0x1800185fb  mov     rax, cs:qword_180045AD0
0x180018602  mov     [rbx+10h], rax
0x180018606  mov     cs:qword_180045AD0, rbx
0x18001860d  lea     rcx, [rsp+48h+var_18]
0x180018612  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180018617  mov     rcx, cs:hInstance; hInstance
0x18001861e  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180018625  mov     r8, rsi; hWndParent
0x180018628  mov     [rsp+48h+dwInitParam], 0; dwInitParam
0x180018631  mov     edx, 5E0h; lpTemplateName
0x180018636  call    cs:__imp_DialogBoxParamW
0x18001863c  jmp     loc_1800185A5
0x180018641  xor     r9d, r9d; lpArguments
0x180018644  xor     r8d, r8d; nNumberOfArguments
0x180018647  mov     ecx, 0C0000005h; dwExceptionCode
0x18001864c  lea     edx, [r9+1]; dwExceptionFlags
0x180018650  call    cs:__imp_RaiseException
```
