# CCompFrameStats::Initialize(void)

- ea: `0x180081a40`
- end: `0x180081b6d`
- name: `?Initialize@CCompFrameStats@@IEAAJXZ`
- size: `301`
- prototype: `__int64 __fastcall(CCompFrameStats *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008131c`
- `0x18008184c`
- `0x180176a24`
- `0x180177990`

## callees

- `0x180081a40`
- `0x180081b74`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081ab2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081ab2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180081a60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180081a60`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180081b62`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180081b62`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180081af1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180081af1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180081b59`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180081b59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081b2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081b3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081b2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081b3a`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180081a71`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180081a71`

## pseudocode

```c
__int64 __fastcall CCompFrameStats::Initialize(HMODULE *this)
{
  HMODULE *v1; // rsi
  unsigned int v3; // ebx
  HANDLE *v5; // r14
  HANDLE hObject; // [rsp+60h] [rbp+8h] BYREF

  v1 = this + 6;
  if ( GetModuleHandleExA(4u, (LPCSTR)CCompFrameStats::ThreadEntryPoint, this + 6) )
  {
    hObject = CreateWaitableTimerW(0, 0, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      this + 8,
      &hObject);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( (unsigned __int64)this[8] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v5 = (HANDLE *)(this + 7);
      hObject = CreateThread(0, 0, CCompFrameStats::ThreadEntryPoint, this, 4u, 0);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        this + 7,
        &hObject);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( (char *)*v5 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v3 = 0;
        (*((void (__fastcall **)(HMODULE *))*this + 1))(this);
        SetThreadPriority(*v5, -1);
        ResumeThread(*v5);
        return v3;
      }
      v3 = -2147024882;
    }
    else
    {
      v3 = -2147024890;
    }
    FreeLibrary(*v1);
    *v1 = 0;
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v3;
}

```

## disassembly

```asm
0x180081a40  push    rbx
0x180081a42  push    rsi
0x180081a43  push    rdi
0x180081a44  push    r14
0x180081a46  sub     rsp, 38h
0x180081a4a  lea     rsi, [rcx+30h]
0x180081a4e  mov     rdi, rcx
0x180081a51  mov     r8, rsi; phModule
0x180081a54  lea     rdx, ?ThreadEntryPoint@CCompFrameStats@@KAKPEAX@Z; lpModuleName
0x180081a5b  mov     ecx, 4; dwFlags
0x180081a60  call    cs:__imp_GetModuleHandleExA
0x180081a66  test    eax, eax
0x180081a68  jz      short loc_180081ACB
0x180081a6a  xor     r8d, r8d; lpTimerName
0x180081a6d  xor     edx, edx; bManualReset
0x180081a6f  xor     ecx, ecx; lpTimerAttributes
0x180081a71  call    cs:__imp_CreateWaitableTimerW
0x180081a77  lea     rdx, [rsp+58h+hObject]
0x180081a7c  mov     [rsp+58h+hObject], rax
0x180081a81  lea     rcx, [rdi+40h]
0x180081a85  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180081a8a  mov     rcx, [rsp+58h+hObject]; hObject
0x180081a8f  lea     rax, [rcx-1]
0x180081a93  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081a97  jbe     loc_180081B2F
0x180081a9d  mov     rax, [rdi+40h]
0x180081aa1  dec     rax
0x180081aa4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081aa8  jbe     short loc_180081AD2
0x180081aaa  mov     ebx, 80070006h
0x180081aaf  mov     rcx, [rsi]; hLibModule
0x180081ab2  call    cs:__imp_FreeLibrary
0x180081ab8  mov     qword ptr [rsi], 0
0x180081abf  mov     eax, ebx
0x180081ac1  add     rsp, 38h
0x180081ac5  pop     r14
0x180081ac7  pop     rdi
0x180081ac8  pop     rsi
0x180081ac9  pop     rbx
0x180081aca  retn
0x180081acb  mov     ebx, 80004005h
0x180081ad0  jmp     short loc_180081ABF
0x180081ad2  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180081adb  lea     r8, ?ThreadEntryPoint@CCompFrameStats@@KAKPEAX@Z; lpStartAddress
0x180081ae2  mov     r9, rdi; lpParameter
0x180081ae5  mov     [rsp+58h+dwCreationFlags], 4; dwCreationFlags
0x180081aed  xor     edx, edx; dwStackSize
0x180081aef  xor     ecx, ecx; lpThreadAttributes
0x180081af1  call    cs:__imp_CreateThread
0x180081af7  lea     r14, [rdi+38h]
0x180081afb  mov     [rsp+58h+hObject], rax
0x180081b00  mov     rcx, r14
0x180081b03  lea     rdx, [rsp+58h+hObject]
0x180081b08  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180081b0d  mov     rcx, [rsp+58h+hObject]; hObject
0x180081b12  lea     rax, [rcx-1]
0x180081b16  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081b1a  jbe     short loc_180081B3A
0x180081b1c  mov     rax, [r14]
0x180081b1f  dec     rax
0x180081b22  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081b26  jbe     short loc_180081B42
0x180081b28  mov     ebx, 8007000Eh
0x180081b2d  jmp     short loc_180081AAF
0x180081b2f  call    cs:__imp_CloseHandle
0x180081b35  jmp     loc_180081A9D
0x180081b3a  call    cs:__imp_CloseHandle
0x180081b40  jmp     short loc_180081B1C
0x180081b42  mov     rax, [rdi]
0x180081b45  mov     rcx, rdi
0x180081b48  xor     ebx, ebx
0x180081b4a  mov     rax, [rax+8]
0x180081b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081b53  mov     rcx, [r14]; hThread
0x180081b56  or      edx, 0FFFFFFFFh; nPriority
0x180081b59  call    cs:__imp_SetThreadPriority
0x180081b5f  mov     rcx, [r14]; hThread
0x180081b62  call    cs:__imp_ResumeThread
0x180081b68  jmp     loc_180081ABF
```
