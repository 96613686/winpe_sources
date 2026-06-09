# ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000b480`
- end: `0x18000b591`
- name: `?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `273`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180009a80`
- `0x18000b0cc`
- `0x18000b480`
- `0x18002d634`
- `0x18002d6ac`
- `0x18002d748`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b4d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b4d2`
- `USER32!SetWindowLongPtrW` at `0x18000b56a`
- `USER32!SetWindowLongPtrW` at `0x18000b56a`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(
        HWND a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rbx
  size_t v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // rdx
  __int64 v13; // rax
  void *v14; // rbx
  AtlThunkData_t *Data; // rax
  WNDPROC v16; // rbx
  __int64 *v17; // [rsp+30h] [rbp-48h] BYREF
  char v18; // [rsp+38h] [rbp-40h]

  v18 = 0;
  v17 = qword_180045AA8;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v17) < 0 )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v17);
    return 0;
  }
  v8 = qword_180045AD0;
  v9 = 0;
  if ( qword_180045AD0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    while ( v8 )
    {
      if ( *(_DWORD *)(v8 + 8) == CurrentThreadId )
      {
        if ( v11 )
          *(_QWORD *)(v11 + 16) = *(_QWORD *)(v8 + 16);
        else
          qword_180045AD0 = *(_QWORD *)(v8 + 16);
        v9 = *(_QWORD *)v8;
        break;
      }
      v11 = v8;
      v8 = *(_QWORD *)(v8 + 16);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v17);
  if ( !v9 )
    return 0;
  v13 = *(_QWORD *)v9;
  *(_QWORD *)(v9 + 8) = a1;
  v14 = (void *)(*(__int64 (__fastcall **)(size_t))(v13 + 16))(v9);
  Data = *(AtlThunkData_t **)(v9 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v9 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v14, v9);
  v16 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v9 + 40));
  SetWindowLongPtrW(a1, 8, (LONG_PTR)v16);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v16)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b480  push    rbx
0x18000b482  push    rbp
0x18000b483  push    rsi
0x18000b484  push    rdi
0x18000b485  push    r14
0x18000b487  push    r15
0x18000b489  sub     rsp, 48h
0x18000b48d  mov     rsi, rcx
0x18000b490  mov     [rsp+78h+var_40], 0
0x18000b495  lea     rax, qword_180045AA8
0x18000b49c  mov     rbp, r9
0x18000b49f  lea     rcx, [rsp+78h+var_48]
0x18000b4a4  mov     [rsp+78h+var_48], rax
0x18000b4a9  mov     r14, r8
0x18000b4ac  mov     r15d, edx
0x18000b4af  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000b4b4  test    eax, eax
0x18000b4b6  jns     short loc_18000B4C4
0x18000b4b8  lea     rcx, [rsp+78h+var_48]
0x18000b4bd  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000b4c2  jmp     short loc_18000B514
0x18000b4c4  mov     rbx, cs:qword_180045AD0
0x18000b4cb  xor     edi, edi
0x18000b4cd  test    rbx, rbx
0x18000b4d0  jz      short loc_18000B505
0x18000b4d2  call    cs:__imp_GetCurrentThreadId
0x18000b4d8  xor     edx, edx
0x18000b4da  test    rbx, rbx
0x18000b4dd  jz      short loc_18000B505
0x18000b4df  mov     rcx, [rbx+10h]
0x18000b4e3  cmp     [rbx+8], eax
0x18000b4e6  jz      short loc_18000B4F0
0x18000b4e8  mov     rdx, rbx
0x18000b4eb  mov     rbx, rcx
0x18000b4ee  jmp     short loc_18000B4DA
0x18000b4f0  test    rdx, rdx
0x18000b4f3  jnz     short loc_18000B4FE
0x18000b4f5  mov     cs:qword_180045AD0, rcx
0x18000b4fc  jmp     short loc_18000B502
0x18000b4fe  mov     [rdx+10h], rcx
0x18000b502  mov     rdi, [rbx]
0x18000b505  lea     rcx, [rsp+78h+var_48]
0x18000b50a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000b50f  test    rdi, rdi
0x18000b512  jnz     short loc_18000B518
0x18000b514  xor     eax, eax
0x18000b516  jmp     short loc_18000B584
0x18000b518  mov     rax, [rdi]
0x18000b51b  mov     rcx, rdi
0x18000b51e  mov     [rdi+8], rsi
0x18000b522  mov     rax, [rax+10h]
0x18000b526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b52b  mov     rbx, rax
0x18000b52e  mov     rax, [rdi+28h]
0x18000b532  test    rax, rax
0x18000b535  jnz     short loc_18000B545
0x18000b537  call    AtlThunk_AllocateData
0x18000b53c  mov     [rdi+28h], rax
0x18000b540  test    rax, rax
0x18000b543  jz      short loc_18000B553
0x18000b545  mov     r8, rdi; FirstParameter
0x18000b548  mov     rdx, rbx; Proc
0x18000b54b  mov     rcx, rax; Thunk
0x18000b54e  call    AtlThunk_InitData
0x18000b553  mov     rcx, [rdi+28h]; AtlThunkData_t *
0x18000b557  call    AtlThunk_DataToCode
0x18000b55c  mov     r8, rax; dwNewLong
0x18000b55f  mov     edx, 8; nIndex
0x18000b564  mov     rcx, rsi; hWnd
0x18000b567  mov     rbx, rax
0x18000b56a  call    cs:__imp_SetWindowLongPtrW
0x18000b570  mov     r9, rbp
0x18000b573  mov     r8, r14
0x18000b576  mov     edx, r15d
0x18000b579  mov     rcx, rsi
0x18000b57c  mov     rax, rbx
0x18000b57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b584  add     rsp, 48h
0x18000b588  pop     r15
0x18000b58a  pop     r14
0x18000b58c  pop     rdi
0x18000b58d  pop     rsi
0x18000b58e  pop     rbp
0x18000b58f  pop     rbx
0x18000b590  retn
```
