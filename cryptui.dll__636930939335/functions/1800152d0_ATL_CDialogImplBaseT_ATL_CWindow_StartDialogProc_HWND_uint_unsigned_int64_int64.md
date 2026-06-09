# ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800152d0`
- end: `0x1800153e1`
- name: `?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `273`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800133d4`
- `0x180014908`
- `0x1800152d0`
- `0x180039650`
- `0x1800396c8`
- `0x180039764`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015322`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015322`
- `USER32!SetWindowLongPtrW` at `0x1800153ba`
- `USER32!SetWindowLongPtrW` at `0x1800153ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(
        HWND hWnd,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  size_t v8; // rdi
  __int64 v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // rdx
  void *v13; // rbx
  AtlThunkData_t *Data; // rax
  WNDPROC v15; // rbx
  __int64 *v16; // [rsp+30h] [rbp-48h] BYREF
  char v17; // [rsp+38h] [rbp-40h]

  v16 = qword_180050388;
  v17 = 0;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v16) < 0 )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v16);
    return 0;
  }
  v8 = 0;
  v9 = qword_1800503B0;
  if ( qword_1800503B0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    while ( v9 )
    {
      if ( *(_DWORD *)(v9 + 8) == CurrentThreadId )
      {
        if ( v11 )
          *(_QWORD *)(v11 + 16) = *(_QWORD *)(v9 + 16);
        else
          qword_1800503B0 = *(_QWORD *)(v9 + 16);
        v8 = *(_QWORD *)v9;
        break;
      }
      v11 = v9;
      v9 = *(_QWORD *)(v9 + 16);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v16);
  if ( !v8 )
    return 0;
  *(_QWORD *)(v8 + 8) = hWnd;
  v13 = (void *)(*(__int64 (__fastcall **)(size_t))(*(_QWORD *)v8 + 16LL))(v8);
  Data = *(AtlThunkData_t **)(v8 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v8 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v13, v8);
  v15 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v8 + 40));
  SetWindowLongPtrW(hWnd, 8, (LONG_PTR)v15);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v15)(hWnd, a2, a3, a4);
}

```

## disassembly

```asm
0x1800152d0  push    rbx
0x1800152d2  push    rbp
0x1800152d3  push    rsi
0x1800152d4  push    rdi
0x1800152d5  push    r14
0x1800152d7  push    r15
0x1800152d9  sub     rsp, 48h
0x1800152dd  mov     rbp, r9
0x1800152e0  mov     r14, r8
0x1800152e3  mov     r15d, edx
0x1800152e6  mov     rsi, rcx
0x1800152e9  lea     rax, qword_180050388
0x1800152f0  mov     [rsp+78h+var_48], rax
0x1800152f5  mov     [rsp+78h+var_40], 0
0x1800152fa  lea     rcx, [rsp+78h+var_48]
0x1800152ff  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180015304  test    eax, eax
0x180015306  jns     short loc_180015314
0x180015308  lea     rcx, [rsp+78h+var_48]
0x18001530d  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180015312  jmp     short loc_180015364
0x180015314  xor     edi, edi
0x180015316  mov     rbx, cs:qword_1800503B0
0x18001531d  test    rbx, rbx
0x180015320  jz      short loc_180015355
0x180015322  call    cs:__imp_GetCurrentThreadId
0x180015328  xor     edx, edx
0x18001532a  test    rbx, rbx
0x18001532d  jz      short loc_180015355
0x18001532f  mov     rcx, [rbx+10h]
0x180015333  cmp     [rbx+8], eax
0x180015336  jz      short loc_180015340
0x180015338  mov     rdx, rbx
0x18001533b  mov     rbx, rcx
0x18001533e  jmp     short loc_18001532A
0x180015340  test    rdx, rdx
0x180015343  jnz     short loc_18001534E
0x180015345  mov     cs:qword_1800503B0, rcx
0x18001534c  jmp     short loc_180015352
0x18001534e  mov     [rdx+10h], rcx
0x180015352  mov     rdi, [rbx]
0x180015355  lea     rcx, [rsp+78h+var_48]
0x18001535a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001535f  test    rdi, rdi
0x180015362  jnz     short loc_180015368
0x180015364  xor     eax, eax
0x180015366  jmp     short loc_1800153D4
0x180015368  mov     [rdi+8], rsi
0x18001536c  mov     rax, [rdi]
0x18001536f  mov     rcx, rdi
0x180015372  mov     rax, [rax+10h]
0x180015376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001537b  mov     rbx, rax
0x18001537e  mov     rax, [rdi+28h]
0x180015382  test    rax, rax
0x180015385  jnz     short loc_180015395
0x180015387  call    AtlThunk_AllocateData
0x18001538c  mov     [rdi+28h], rax
0x180015390  test    rax, rax
0x180015393  jz      short loc_1800153A3
0x180015395  mov     r8, rdi; FirstParameter
0x180015398  mov     rdx, rbx; Proc
0x18001539b  mov     rcx, rax; Thunk
0x18001539e  call    AtlThunk_InitData
0x1800153a3  mov     rcx, [rdi+28h]; AtlThunkData_t *
0x1800153a7  call    AtlThunk_DataToCode
0x1800153ac  mov     rbx, rax
0x1800153af  mov     r8, rax; dwNewLong
0x1800153b2  mov     edx, 8; nIndex
0x1800153b7  mov     rcx, rsi; hWnd
0x1800153ba  call    cs:__imp_SetWindowLongPtrW
0x1800153c0  mov     r9, rbp
0x1800153c3  mov     r8, r14
0x1800153c6  mov     edx, r15d
0x1800153c9  mov     rcx, rsi
0x1800153cc  mov     rax, rbx
0x1800153cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153d4  add     rsp, 48h
0x1800153d8  pop     r15
0x1800153da  pop     r14
0x1800153dc  pop     rdi
0x1800153dd  pop     rsi
0x1800153de  pop     rbp
0x1800153df  pop     rbx
0x1800153e0  retn
```
