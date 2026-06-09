# ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18002b4d0`
- end: `0x18002b5e1`
- name: `?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `273`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180023cac`
- `0x180027f20`
- `0x18002b4d0`
- `0x1800348b0`
- `0x180034928`
- `0x1800349c4`
- `0x180065010`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x18002b5ba`
- `USER32!SetWindowLongPtrW` at `0x18002b5ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b522`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b522`

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
  v17 = qword_180089778;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v17) < 0 )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v17);
    return 0;
  }
  v8 = qword_1800897A0;
  v9 = 0;
  if ( qword_1800897A0 )
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
          qword_1800897A0 = *(_QWORD *)(v8 + 16);
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
0x18002b4d0  push    rbx
0x18002b4d2  push    rbp
0x18002b4d3  push    rsi
0x18002b4d4  push    rdi
0x18002b4d5  push    r14
0x18002b4d7  push    r15
0x18002b4d9  sub     rsp, 48h
0x18002b4dd  mov     rsi, rcx
0x18002b4e0  mov     [rsp+78h+var_40], 0
0x18002b4e5  lea     rax, qword_180089778
0x18002b4ec  mov     rbp, r9
0x18002b4ef  lea     rcx, [rsp+78h+var_48]
0x18002b4f4  mov     [rsp+78h+var_48], rax
0x18002b4f9  mov     r14, r8
0x18002b4fc  mov     r15d, edx
0x18002b4ff  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18002b504  test    eax, eax
0x18002b506  jns     short loc_18002B514
0x18002b508  lea     rcx, [rsp+78h+var_48]
0x18002b50d  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002b512  jmp     short loc_18002B564
0x18002b514  mov     rbx, cs:qword_1800897A0
0x18002b51b  xor     edi, edi
0x18002b51d  test    rbx, rbx
0x18002b520  jz      short loc_18002B555
0x18002b522  call    cs:__imp_GetCurrentThreadId
0x18002b528  xor     edx, edx
0x18002b52a  test    rbx, rbx
0x18002b52d  jz      short loc_18002B555
0x18002b52f  mov     rcx, [rbx+10h]
0x18002b533  cmp     [rbx+8], eax
0x18002b536  jz      short loc_18002B540
0x18002b538  mov     rdx, rbx
0x18002b53b  mov     rbx, rcx
0x18002b53e  jmp     short loc_18002B52A
0x18002b540  test    rdx, rdx
0x18002b543  jnz     short loc_18002B54E
0x18002b545  mov     cs:qword_1800897A0, rcx
0x18002b54c  jmp     short loc_18002B552
0x18002b54e  mov     [rdx+10h], rcx
0x18002b552  mov     rdi, [rbx]
0x18002b555  lea     rcx, [rsp+78h+var_48]
0x18002b55a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002b55f  test    rdi, rdi
0x18002b562  jnz     short loc_18002B568
0x18002b564  xor     eax, eax
0x18002b566  jmp     short loc_18002B5D4
0x18002b568  mov     rax, [rdi]
0x18002b56b  mov     rcx, rdi
0x18002b56e  mov     [rdi+8], rsi
0x18002b572  mov     rax, [rax+10h]
0x18002b576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b57b  mov     rbx, rax
0x18002b57e  mov     rax, [rdi+28h]
0x18002b582  test    rax, rax
0x18002b585  jnz     short loc_18002B595
0x18002b587  call    AtlThunk_AllocateData
0x18002b58c  mov     [rdi+28h], rax
0x18002b590  test    rax, rax
0x18002b593  jz      short loc_18002B5A3
0x18002b595  mov     r8, rdi; FirstParameter
0x18002b598  mov     rdx, rbx; Proc
0x18002b59b  mov     rcx, rax; Thunk
0x18002b59e  call    AtlThunk_InitData
0x18002b5a3  mov     rcx, [rdi+28h]; AtlThunkData_t *
0x18002b5a7  call    AtlThunk_DataToCode
0x18002b5ac  mov     r8, rax; dwNewLong
0x18002b5af  mov     edx, 8; nIndex
0x18002b5b4  mov     rcx, rsi; hWnd
0x18002b5b7  mov     rbx, rax
0x18002b5ba  call    cs:__imp_SetWindowLongPtrW
0x18002b5c0  mov     r9, rbp
0x18002b5c3  mov     r8, r14
0x18002b5c6  mov     edx, r15d
0x18002b5c9  mov     rcx, rsi
0x18002b5cc  mov     rax, rbx
0x18002b5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5d4  add     rsp, 48h
0x18002b5d8  pop     r15
0x18002b5da  pop     r14
0x18002b5dc  pop     rdi
0x18002b5dd  pop     rsi
0x18002b5de  pop     rbp
0x18002b5df  pop     rbx
0x18002b5e0  retn
```
