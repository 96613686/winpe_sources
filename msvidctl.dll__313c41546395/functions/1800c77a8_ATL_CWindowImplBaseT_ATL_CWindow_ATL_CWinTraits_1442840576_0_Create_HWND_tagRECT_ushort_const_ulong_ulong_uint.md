# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,tagRECT &,ushort const *,ulong,ulong,uint,ushort,void *)

- ea: `0x1800c77a8`
- end: `0x1800c78ef`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@AEAUtagRECT@@PEBGKKIGPEAX@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800c7a50`

## callees

- `0x1800c77a8`
- `0x1800ee708`
- `0x1800ee81c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800c78e8`
- `KERNEL32!RaiseException` at `0x1800c78e8`
- `KERNEL32!SetLastError` at `0x1800c77dc`
- `KERNEL32!SetLastError` at `0x1800c77dc`
- `KERNEL32!GetCurrentThreadId` at `0x1800c7826`
- `KERNEL32!GetCurrentThreadId` at `0x1800c7826`
- `KERNEL32!LeaveCriticalSection` at `0x1800c7855`
- `KERNEL32!LeaveCriticalSection` at `0x1800c7855`
- `KERNEL32!EnterCriticalSection` at `0x1800c7836`
- `KERNEL32!EnterCriticalSection` at `0x1800c7836`
- `USER32!CreateWindowExW` at `0x1800c78ce`
- `USER32!CreateWindowExW` at `0x1800c78ce`

## pseudocode

```c
HWND __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
        __int64 a1,
        HWND a2,
        int *a3,
        __int64 a4,
        DWORD dwStyle,
        DWORD dwExStyle,
        __int64 a7,
        unsigned __int16 a8)
{
  AtlThunkData_t *Data; // rax
  unsigned __int32 v13; // edi

  Data = *(AtlThunkData_t **)(a1 + 40);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *(_QWORD *)(a1 + 40) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return 0;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( !a8 )
    return 0;
  if ( a1 == -16 || !a1 )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    JUMPOUT(0x1800C78EELL);
  }
  v13 = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  EnterCriticalSection(&stru_18021D030);
  *(_QWORD *)(a1 + 32) = qword_18021D088;
  qword_18021D088 = a1 + 16;
  LeaveCriticalSection(&stru_18021D030);
  if ( (dwStyle & 0x40000000) != 0 )
    v13 = _InterlockedIncrement(&dword_18021D0C0);
  return CreateWindowExW(
           dwExStyle,
           (LPCWSTR)a8,
           0,
           dwStyle,
           *a3,
           a3[1],
           a3[2] - *a3,
           a3[3] - a3[1],
           a2,
           (HMENU)v13,
           lpSource,
           0);
}

```

## disassembly

```asm
0x1800c77a8  push    rbx
0x1800c77aa  push    rsi
0x1800c77ab  push    rdi
0x1800c77ac  push    r12
0x1800c77ae  push    r14
0x1800c77b0  push    r15
0x1800c77b2  sub     rsp, 68h
0x1800c77b6  mov     rax, [rcx+28h]
0x1800c77ba  xor     r12d, r12d
0x1800c77bd  mov     r14, r8
0x1800c77c0  mov     r15, rdx
0x1800c77c3  mov     rbx, rcx
0x1800c77c6  test    rax, rax
0x1800c77c9  jnz     short loc_1800C77F2
0x1800c77cb  call    AtlThunk_AllocateData
0x1800c77d0  mov     [rbx+28h], rax
0x1800c77d4  test    rax, rax
0x1800c77d7  jnz     short loc_1800C77F2
0x1800c77d9  lea     ecx, [rax+0Eh]; dwErrCode
0x1800c77dc  call    cs:__imp_SetLastError
0x1800c77e2  xor     eax, eax
0x1800c77e4  add     rsp, 68h
0x1800c77e8  pop     r15
0x1800c77ea  pop     r14
0x1800c77ec  pop     r12
0x1800c77ee  pop     rdi
0x1800c77ef  pop     rsi
0x1800c77f0  pop     rbx
0x1800c77f1  retn
0x1800c77f2  xor     r8d, r8d; FirstParameter
0x1800c77f5  xor     edx, edx; Proc
0x1800c77f7  mov     rcx, rax; Thunk
0x1800c77fa  call    AtlThunk_InitData
0x1800c77ff  cmp     [rsp+98h+arg_38], r12w
0x1800c7808  jz      short loc_1800C77E2
0x1800c780a  lea     rsi, [rbx+10h]
0x1800c780e  test    rsi, rsi
0x1800c7811  jz      loc_1800C78D9
0x1800c7817  test    rbx, rbx
0x1800c781a  jz      loc_1800C78D9
0x1800c7820  mov     edi, r12d
0x1800c7823  mov     [rsi], rbx
0x1800c7826  call    cs:__imp_GetCurrentThreadId
0x1800c782c  lea     rcx, stru_18021D030; lpCriticalSection
0x1800c7833  mov     [rsi+8], eax
0x1800c7836  call    cs:__imp_EnterCriticalSection
0x1800c783c  mov     rax, cs:qword_18021D088
0x1800c7843  lea     rcx, stru_18021D030; lpCriticalSection
0x1800c784a  mov     [rsi+10h], rax
0x1800c784e  mov     cs:qword_18021D088, rsi
0x1800c7855  call    cs:__imp_LeaveCriticalSection
0x1800c785b  mov     r9d, [rsp+98h+dwStyle]; dwStyle
0x1800c7863  bt      r9d, 1Eh
0x1800c7868  jnb     short loc_1800C7879
0x1800c786a  mov     edi, 1
0x1800c786f  lock xadd cs:dword_18021D0C0, edi
0x1800c7877  inc     edi
0x1800c7879  mov     r8d, [r14+0Ch]
0x1800c787d  mov     r11d, [r14+4]
0x1800c7881  sub     r8d, r11d
0x1800c7884  mov     ebx, [r14]
0x1800c7887  mov     r10, cs:lpSource
0x1800c788e  mov     ecx, [r14+8]
0x1800c7892  movzx   edx, [rsp+98h+arg_38]; lpClassName
0x1800c789a  sub     ecx, ebx
0x1800c789c  mov     [rsp+98h+lpParam], r12; lpParam
0x1800c78a1  mov     [rsp+98h+hInstance], r10; hInstance
0x1800c78a6  mov     eax, edi
0x1800c78a8  mov     [rsp+98h+hMenu], rax; hMenu
0x1800c78ad  mov     [rsp+98h+hWndParent], r15; hWndParent
0x1800c78b2  mov     [rsp+98h+nHeight], r8d; nHeight
0x1800c78b7  xor     r8d, r8d; lpWindowName
0x1800c78ba  mov     [rsp+98h+nWidth], ecx; nWidth
0x1800c78be  mov     ecx, [rsp+98h+dwExStyle]; dwExStyle
0x1800c78c5  mov     [rsp+98h+Y], r11d; Y
0x1800c78ca  mov     [rsp+98h+X], ebx; X
0x1800c78ce  call    cs:__imp_CreateWindowExW
0x1800c78d4  jmp     loc_1800C77E4
0x1800c78d9  xor     r9d, r9d; lpArguments
0x1800c78dc  xor     r8d, r8d; nNumberOfArguments
0x1800c78df  mov     ecx, 0C0000005h; dwExceptionCode
0x1800c78e4  lea     edx, [r9+1]; dwExceptionFlags
0x1800c78e8  call    cs:__imp_RaiseException
```
