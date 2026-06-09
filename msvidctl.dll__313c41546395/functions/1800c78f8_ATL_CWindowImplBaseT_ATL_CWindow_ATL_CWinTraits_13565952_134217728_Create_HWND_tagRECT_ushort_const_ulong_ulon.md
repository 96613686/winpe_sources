# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<13565952,134217728>>::Create(HWND__ *,tagRECT &,ushort const *,ulong,ulong,uint,ushort,void *)

- ea: `0x1800c78f8`
- end: `0x1800c7a3c`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0MPAAAA@$0IAAAAAA@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@AEAUtagRECT@@PEBGKKIGPEAX@Z`
- size: `324`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwStyle, DWORD dwExStyle, int, __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800c55a4`

## callees

- `0x1800c78f8`
- `0x1800ee708`
- `0x1800ee81c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800c7a35`
- `KERNEL32!RaiseException` at `0x1800c7a35`
- `KERNEL32!SetLastError` at `0x1800c7927`
- `KERNEL32!SetLastError` at `0x1800c7927`
- `KERNEL32!GetCurrentThreadId` at `0x1800c796f`
- `KERNEL32!GetCurrentThreadId` at `0x1800c796f`
- `KERNEL32!LeaveCriticalSection` at `0x1800c799e`
- `KERNEL32!LeaveCriticalSection` at `0x1800c799e`
- `KERNEL32!EnterCriticalSection` at `0x1800c797f`
- `KERNEL32!EnterCriticalSection` at `0x1800c797f`
- `USER32!CreateWindowExW` at `0x1800c7a1b`
- `USER32!CreateWindowExW` at `0x1800c7a1b`

## pseudocode

```c
HWND __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<13565952,134217728>>::Create(
        __int64 a1,
        __int64 a2,
        int *a3,
        __int64 a4,
        DWORD dwStyle,
        DWORD dwExStyle,
        int a7,
        unsigned __int16 a8)
{
  AtlThunkData_t *Data; // rax
  unsigned __int32 v12; // edi

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
    JUMPOUT(0x1800C7A3BLL);
  }
  v12 = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  EnterCriticalSection(&stru_18021D030);
  *(_QWORD *)(a1 + 32) = qword_18021D088;
  qword_18021D088 = a1 + 16;
  LeaveCriticalSection(&stru_18021D030);
  if ( (dwStyle & 0x40000000) != 0 )
    v12 = _InterlockedIncrement(&dword_18021D0C0);
  return CreateWindowExW(
           dwExStyle,
           (LPCWSTR)a8,
           L"MSVidCtl System Broadcast Message Receiver",
           dwStyle,
           *a3,
           a3[1],
           a3[2] - *a3,
           a3[3] - a3[1],
           0,
           (HMENU)v12,
           lpSource,
           0);
}

```

## disassembly

```asm
0x1800c78f8  push    rbx
0x1800c78fa  push    rsi
0x1800c78fb  push    rdi
0x1800c78fc  push    r14
0x1800c78fe  push    r15
0x1800c7900  sub     rsp, 60h
0x1800c7904  mov     rax, [rcx+28h]
0x1800c7908  xor     r15d, r15d
0x1800c790b  mov     r14, r8
0x1800c790e  mov     rbx, rcx
0x1800c7911  test    rax, rax
0x1800c7914  jnz     short loc_1800C793B
0x1800c7916  call    AtlThunk_AllocateData
0x1800c791b  mov     [rbx+28h], rax
0x1800c791f  test    rax, rax
0x1800c7922  jnz     short loc_1800C793B
0x1800c7924  lea     ecx, [rax+0Eh]; dwErrCode
0x1800c7927  call    cs:__imp_SetLastError
0x1800c792d  xor     eax, eax
0x1800c792f  add     rsp, 60h
0x1800c7933  pop     r15
0x1800c7935  pop     r14
0x1800c7937  pop     rdi
0x1800c7938  pop     rsi
0x1800c7939  pop     rbx
0x1800c793a  retn
0x1800c793b  xor     r8d, r8d; FirstParameter
0x1800c793e  xor     edx, edx; Proc
0x1800c7940  mov     rcx, rax; Thunk
0x1800c7943  call    AtlThunk_InitData
0x1800c7948  cmp     [rsp+88h+arg_38], r15w
0x1800c7951  jz      short loc_1800C792D
0x1800c7953  lea     rsi, [rbx+10h]
0x1800c7957  test    rsi, rsi
0x1800c795a  jz      loc_1800C7A26
0x1800c7960  test    rbx, rbx
0x1800c7963  jz      loc_1800C7A26
0x1800c7969  mov     edi, r15d
0x1800c796c  mov     [rsi], rbx
0x1800c796f  call    cs:__imp_GetCurrentThreadId
0x1800c7975  lea     rcx, stru_18021D030; lpCriticalSection
0x1800c797c  mov     [rsi+8], eax
0x1800c797f  call    cs:__imp_EnterCriticalSection
0x1800c7985  mov     rax, cs:qword_18021D088
0x1800c798c  lea     rcx, stru_18021D030; lpCriticalSection
0x1800c7993  mov     [rsi+10h], rax
0x1800c7997  mov     cs:qword_18021D088, rsi
0x1800c799e  call    cs:__imp_LeaveCriticalSection
0x1800c79a4  mov     r9d, [rsp+88h+dwStyle]; dwStyle
0x1800c79ac  bt      r9d, 1Eh
0x1800c79b1  jnb     short loc_1800C79C2
0x1800c79b3  mov     edi, 1
0x1800c79b8  lock xadd cs:dword_18021D0C0, edi
0x1800c79c0  inc     edi
0x1800c79c2  mov     r8d, [r14+0Ch]
0x1800c79c6  mov     r11d, [r14+4]
0x1800c79ca  sub     r8d, r11d
0x1800c79cd  mov     ebx, [r14]
0x1800c79d0  mov     r10, cs:lpSource
0x1800c79d7  mov     ecx, [r14+8]
0x1800c79db  movzx   edx, [rsp+88h+arg_38]; lpClassName
0x1800c79e3  sub     ecx, ebx
0x1800c79e5  mov     [rsp+88h+lpParam], r15; lpParam
0x1800c79ea  mov     [rsp+88h+hInstance], r10; hInstance
0x1800c79ef  mov     eax, edi
0x1800c79f1  mov     [rsp+88h+hMenu], rax; hMenu
0x1800c79f6  mov     [rsp+88h+hWndParent], r15; hWndParent
0x1800c79fb  mov     [rsp+88h+nHeight], r8d; nHeight
0x1800c7a00  lea     r8, WindowName; "MSVidCtl System Broadcast Message Recei"...
0x1800c7a07  mov     [rsp+88h+nWidth], ecx; nWidth
0x1800c7a0b  mov     ecx, [rsp+88h+dwExStyle]; dwExStyle
0x1800c7a12  mov     [rsp+88h+Y], r11d; Y
0x1800c7a17  mov     [rsp+88h+X], ebx; X
0x1800c7a1b  call    cs:__imp_CreateWindowExW
0x1800c7a21  jmp     loc_1800C792F
0x1800c7a26  xor     r9d, r9d; lpArguments
0x1800c7a29  xor     r8d, r8d; nNumberOfArguments
0x1800c7a2c  mov     ecx, 0C0000005h; dwExceptionCode
0x1800c7a31  lea     edx, [r9+1]; dwExceptionFlags
0x1800c7a35  call    cs:__imp_RaiseException
```
