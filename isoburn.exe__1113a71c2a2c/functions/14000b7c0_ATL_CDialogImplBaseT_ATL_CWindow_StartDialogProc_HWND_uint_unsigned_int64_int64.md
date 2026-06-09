# ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x14000b7c0`
- end: `0x14000b8b7`
- name: `?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `247`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000b7c0`
- `0x14000f4a0`
- `0x14000f518`
- `0x14000f5bc`
- `0x140010010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000b7e0`
- `KERNEL32!EnterCriticalSection` at `0x14000b7e0`
- `KERNEL32!LeaveCriticalSection` at `0x14000b82f`
- `KERNEL32!LeaveCriticalSection` at `0x14000b82f`
- `KERNEL32!GetCurrentThreadId` at `0x14000b7f4`
- `KERNEL32!GetCurrentThreadId` at `0x14000b7f4`
- `USER32!SetWindowLongPtrW` at `0x14000b890`
- `USER32!SetWindowLongPtrW` at `0x14000b890`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(
        HWND a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rdi
  size_t v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v14; // rax
  void *v15; // rdi
  AtlThunkData_t *Data; // rax
  WNDPROC v17; // rbx

  EnterCriticalSection(&stru_140016468);
  v8 = qword_140016490;
  v9 = 0;
  if ( qword_140016490 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    while ( 1 )
    {
      v12 = *(_QWORD *)(v8 + 16);
      if ( *(_DWORD *)(v8 + 8) == CurrentThreadId )
        break;
      v11 = v8;
      v8 = *(_QWORD *)(v8 + 16);
      if ( !v12 )
        goto LABEL_10;
    }
    if ( v11 )
      *(_QWORD *)(v11 + 16) = v12;
    else
      qword_140016490 = *(_QWORD *)(v8 + 16);
    v9 = *(_QWORD *)v8;
  }
LABEL_10:
  LeaveCriticalSection(&stru_140016468);
  if ( !v9 )
    return 0;
  v14 = *(_QWORD *)v9;
  *(_QWORD *)(v9 + 8) = a1;
  v15 = (void *)(*(__int64 (__fastcall **)(size_t))(v14 + 16))(v9);
  Data = *(AtlThunkData_t **)(v9 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v9 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v15, v9);
  v17 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v9 + 40));
  SetWindowLongPtrW(a1, 8, (LONG_PTR)v17);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v17)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000b7c0  push    rbx
0x14000b7c2  push    rbp
0x14000b7c3  push    rsi
0x14000b7c4  push    rdi
0x14000b7c5  push    r14
0x14000b7c7  push    r15
0x14000b7c9  sub     rsp, 38h
0x14000b7cd  mov     rsi, rcx
0x14000b7d0  mov     rbp, r9
0x14000b7d3  lea     rcx, stru_140016468; lpCriticalSection
0x14000b7da  mov     r14, r8
0x14000b7dd  mov     r15d, edx
0x14000b7e0  call    cs:__imp_EnterCriticalSection
0x14000b7e6  mov     rdi, cs:qword_140016490
0x14000b7ed  xor     ebx, ebx
0x14000b7ef  test    rdi, rdi
0x14000b7f2  jz      short loc_14000B828
0x14000b7f4  call    cs:__imp_GetCurrentThreadId
0x14000b7fa  xor     r8d, r8d
0x14000b7fd  mov     rcx, [rdi+10h]
0x14000b801  cmp     [rdi+8], eax
0x14000b804  jz      short loc_14000B813
0x14000b806  mov     r8, rdi
0x14000b809  mov     rdi, rcx
0x14000b80c  test    rcx, rcx
0x14000b80f  jnz     short loc_14000B7FD
0x14000b811  jmp     short loc_14000B828
0x14000b813  test    r8, r8
0x14000b816  jnz     short loc_14000B821
0x14000b818  mov     cs:qword_140016490, rcx
0x14000b81f  jmp     short loc_14000B825
0x14000b821  mov     [r8+10h], rcx
0x14000b825  mov     rbx, [rdi]
0x14000b828  lea     rcx, stru_140016468; lpCriticalSection
0x14000b82f  call    cs:__imp_LeaveCriticalSection
0x14000b835  test    rbx, rbx
0x14000b838  jnz     short loc_14000B83E
0x14000b83a  xor     eax, eax
0x14000b83c  jmp     short loc_14000B8AA
0x14000b83e  mov     rax, [rbx]
0x14000b841  mov     rcx, rbx
0x14000b844  mov     [rbx+8], rsi
0x14000b848  mov     rax, [rax+10h]
0x14000b84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b851  mov     rdi, rax
0x14000b854  mov     rax, [rbx+28h]
0x14000b858  test    rax, rax
0x14000b85b  jnz     short loc_14000B86B
0x14000b85d  call    AtlThunk_AllocateData
0x14000b862  mov     [rbx+28h], rax
0x14000b866  test    rax, rax
0x14000b869  jz      short loc_14000B879
0x14000b86b  mov     r8, rbx; FirstParameter
0x14000b86e  mov     rdx, rdi; Proc
0x14000b871  mov     rcx, rax; Thunk
0x14000b874  call    AtlThunk_InitData
0x14000b879  mov     rcx, [rbx+28h]; AtlThunkData_t *
0x14000b87d  call    AtlThunk_DataToCode
0x14000b882  mov     r8, rax; dwNewLong
0x14000b885  mov     edx, 8; nIndex
0x14000b88a  mov     rcx, rsi; hWnd
0x14000b88d  mov     rbx, rax
0x14000b890  call    cs:__imp_SetWindowLongPtrW
0x14000b896  mov     r9, rbp
0x14000b899  mov     r8, r14
0x14000b89c  mov     edx, r15d
0x14000b89f  mov     rcx, rsi
0x14000b8a2  mov     rax, rbx
0x14000b8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b8aa  add     rsp, 38h
0x14000b8ae  pop     r15
0x14000b8b0  pop     r14
0x14000b8b2  pop     rdi
0x14000b8b3  pop     rsi
0x14000b8b4  pop     rbp
0x14000b8b5  pop     rbx
0x14000b8b6  retn
```
