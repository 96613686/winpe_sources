# ExecAsync(long (*)(IUnknown *,__int64,__int64),IUnknown *,uint,__int64,__int64,long *)

- ea: `0x18001dd0c`
- end: `0x18001dec6`
- name: `?ExecAsync@@YAJP6AJPEAUIUnknown@@_J1@Z0I11PEAJ@Z`
- size: `442`
- prototype: `int(int (*)(struct IUnknown *, __int64, __int64), struct IUnknown *, unsigned int, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024240`

## callees

- `0x18001c50c`
- `0x18001dd0c`
- `0x18001decc`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de0f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001de5c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001de5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de89`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001de01`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001de01`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001de70`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001de70`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dd75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dd75`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18001de3b`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18001de3b`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001ddd2`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001ddd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ExecAsync(
        int (*a1)(struct IUnknown *, __int64, __int64),
        struct IUnknown *a2,
        DWORD a3,
        IStream *a4,
        IStream *a5,
        int *a6)
{
  int *v8; // r15
  BOOL v9; // ebx
  LPSTREAM *v10; // rax
  LPSTREAM *v11; // rdi
  int v12; // ebx
  HANDLE Thread; // rax
  void *v14; // rbx
  signed int LastError; // eax
  int (*v17)(struct IUnknown *, __int64, __int64); // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF
  DWORD ExitCode; // [rsp+70h] [rbp+40h] BYREF

  ExitCode = a3;
  v17 = a1;
  v8 = a6;
  *a6 = 0;
  a6 = 0;
  v9 = !((__int64 (__fastcall *)(struct IUnknown *, GUID *, int **))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_IProxyManager,
          &a6)
    && a6;
  v10 = (LPSTREAM *)LocalAlloc(0x40u, 0x20u);
  v11 = v10;
  v17 = (int (*)(struct IUnknown *, __int64, __int64))v10;
  if ( v10 )
  {
    v10[3] = 0;
    v17 = (int (*)(struct IUnknown *, __int64, __int64))v10;
    *v10 = (LPSTREAM)AccWrap_LocationEtcFix::DoDefaultActionCallback;
    v10[1] = a4;
    v10[2] = a5;
    if ( v9 )
    {
      v12 = CoMarshalInterThreadInterfaceInStream(&GUID_00000000_0000_0000_c000_000000000046, a2, v10 + 3);
      if ( v12 >= 0 )
      {
        Thread = CreateThread(0, 0, ExecAsyncThreadProc, v11, 0, 0);
        v14 = Thread;
        if ( Thread )
        {
          v17 = 0;
          if ( !WaitForSingleObject(Thread, 0x3E8u) )
          {
            ExitCode = 0;
            if ( GetExitCodeThread(v14, &ExitCode) )
              *v8 = ExitCode;
          }
          if ( v14 != (void *)-1LL )
            CloseHandle(v14);
          v12 = 0;
        }
        else
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
          ppv = 0;
          CoUnmarshalInterface(v11[3], &GUID_00000000_0000_0000_c000_000000000046, &ppv);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
        }
      }
    }
    else
    {
      v12 = -2147467259;
    }
  }
  else
  {
    v17 = 0;
    v12 = -2147024882;
  }
  AutoDelete<ExecAsyncThreadParams *>::~AutoDelete<ExecAsyncThreadParams *>(&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&a6);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001dd0c  mov     [rsp-28h+arg_18], rbx
0x18001dd11  mov     [rsp-28h+ExitCode], r8d
0x18001dd16  mov     [rsp-28h+arg_0], rcx
0x18001dd1b  push    rbp
0x18001dd1c  push    rsi
0x18001dd1d  push    rdi
0x18001dd1e  push    r14
0x18001dd20  push    r15
0x18001dd22  mov     rbp, rsp
0x18001dd25  sub     rsp, 30h
0x18001dd29  mov     rsi, r9
0x18001dd2c  mov     r14, rdx
0x18001dd2f  mov     r15, [rbp+arg_28]
0x18001dd33  mov     dword ptr [r15], 0
0x18001dd3a  mov     [rbp+arg_28], 0
0x18001dd42  mov     rax, [rdx]
0x18001dd45  lea     r8, [rbp+arg_28]
0x18001dd49  lea     rdx, IID_IProxyManager
0x18001dd50  mov     rcx, r14
0x18001dd53  mov     rax, [rax]
0x18001dd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd5b  test    eax, eax
0x18001dd5d  jnz     short loc_18001DD6B
0x18001dd5f  cmp     [rbp+arg_28], 0
0x18001dd64  jz      short loc_18001DD6B
0x18001dd66  lea     ebx, [rax+1]
0x18001dd69  jmp     short loc_18001DD6D
0x18001dd6b  xor     ebx, ebx
0x18001dd6d  mov     edx, 20h ; ' '; uBytes
0x18001dd72  lea     ecx, [rdx+20h]; uFlags
0x18001dd75  call    cs:__imp_LocalAlloc
0x18001dd7b  mov     rdi, rax
0x18001dd7e  mov     [rbp+arg_0], rax
0x18001dd82  test    rax, rax
0x18001dd85  jz      loc_18001DE93
0x18001dd8b  mov     qword ptr [rax+18h], 0
0x18001dd93  mov     [rbp+arg_0], rax
0x18001dd97  test    rax, rax
0x18001dd9a  jz      loc_18001DE9B
0x18001dda0  lea     rax, ?DoDefaultActionCallback@AccWrap_LocationEtcFix@@SAJPEAUIUnknown@@_J1@Z; AccWrap_LocationEtcFix::DoDefaultActionCallback(IUnknown *,__int64,__int64)
0x18001dda7  mov     [rdi], rax
0x18001ddaa  mov     [rdi+8], rsi
0x18001ddae  mov     rax, [rbp+arg_20]
0x18001ddb2  mov     [rdi+10h], rax
0x18001ddb6  test    ebx, ebx
0x18001ddb8  jnz     short loc_18001DDC4
0x18001ddba  mov     ebx, 80004005h
0x18001ddbf  jmp     loc_18001DEA0
0x18001ddc4  lea     r8, [rdi+18h]; ppStm
0x18001ddc8  mov     rdx, r14; pUnk
0x18001ddcb  lea     rcx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001ddd2  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18001ddd8  mov     ebx, eax
0x18001ddda  test    eax, eax
0x18001dddc  js      loc_18001DEA0
0x18001dde2  mov     [rsp+30h+lpThreadId], 0; lpThreadId
0x18001ddeb  mov     [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x18001ddf3  mov     r9, rdi; lpParameter
0x18001ddf6  lea     r8, ?ExecAsyncThreadProc@@YAKPEAX@Z; lpStartAddress
0x18001ddfd  xor     edx, edx; dwStackSize
0x18001ddff  xor     ecx, ecx; lpThreadAttributes
0x18001de01  call    cs:__imp_CreateThread
0x18001de07  mov     rbx, rax
0x18001de0a  test    rax, rax
0x18001de0d  jnz     short loc_18001DE4C
0x18001de0f  call    cs:__imp_GetLastError
0x18001de15  mov     ebx, eax
0x18001de17  test    eax, eax
0x18001de19  jle     short loc_18001DE24
0x18001de1b  movzx   ebx, ax
0x18001de1e  or      ebx, 80070000h
0x18001de24  mov     [rbp+ppv], 0
0x18001de2c  lea     r8, [rbp+ppv]; ppv
0x18001de30  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001de37  mov     rcx, [rdi+18h]; pStm
0x18001de3b  call    cs:__imp_CoUnmarshalInterface
0x18001de41  lea     rcx, [rbp+ppv]
0x18001de45  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001de4a  jmp     short loc_18001DEA0
0x18001de4c  mov     [rbp+arg_0], 0
0x18001de54  mov     edx, 3E8h; dwMilliseconds
0x18001de59  mov     rcx, rbx; hHandle
0x18001de5c  call    cs:__imp_WaitForSingleObject
0x18001de62  test    eax, eax
0x18001de64  jnz     short loc_18001DE80
0x18001de66  mov     [rbp+ExitCode], eax
0x18001de69  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18001de6d  mov     rcx, rbx; hThread
0x18001de70  call    cs:__imp_GetExitCodeThread
0x18001de76  test    eax, eax
0x18001de78  jz      short loc_18001DE80
0x18001de7a  mov     eax, [rbp+ExitCode]
0x18001de7d  mov     [r15], eax
0x18001de80  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001de84  jz      short loc_18001DE8F
0x18001de86  mov     rcx, rbx; hObject
0x18001de89  call    cs:__imp_CloseHandle
0x18001de8f  xor     ebx, ebx
0x18001de91  jmp     short loc_18001DEA0
0x18001de93  mov     [rbp+arg_0], 0
0x18001de9b  mov     ebx, 8007000Eh
0x18001dea0  lea     rcx, [rbp+arg_0]
0x18001dea4  call    ??1?$AutoDelete@PEAUExecAsyncThreadParams@@@@QEAA@XZ; AutoDelete<ExecAsyncThreadParams *>::~AutoDelete<ExecAsyncThreadParams *>(void)
0x18001dea9  nop
0x18001deaa  lea     rcx, [rbp+arg_28]
0x18001deae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001deb3  mov     eax, ebx
0x18001deb5  mov     rbx, [rsp+30h+arg_18]
0x18001deba  add     rsp, 30h
0x18001debe  pop     r15
0x18001dec0  pop     r14
0x18001dec2  pop     rdi
0x18001dec3  pop     rsi
0x18001dec4  pop     rbp
0x18001dec5  retn
```
