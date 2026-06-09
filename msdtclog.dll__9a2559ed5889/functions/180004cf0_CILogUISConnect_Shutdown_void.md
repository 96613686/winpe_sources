# CILogUISConnect::Shutdown(void)

- ea: `0x180004cf0`
- end: `0x180004d52`
- name: `?Shutdown@CILogUISConnect@@UEAAJXZ`
- size: `98`
- prototype: `__int64 __fastcall(CILogUISConnect *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004cf0`
- `0x180006248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004d1d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004d1d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180004d34`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180004d34`

## pseudocode

```c
__int64 __fastcall CILogUISConnect::Shutdown(CILogUISConnect *this)
{
  CLogMgr *v2; // rcx
  DWORD v3; // ebx
  void *v4; // rcx
  DWORD v6; // [rsp+20h] [rbp-18h] BYREF
  ulong v7; // [rsp+24h] [rbp-14h] BYREF

  v2 = (CLogMgr *)*((_QWORD *)this + 1);
  try
  {
    v3 = CLogMgr::CrashShutDown(v2);
    v4 = *(void **)(*((_QWORD *)this + 1) + 584LL);
    if ( v4 && WaitForSingleObject(v4, 0x1388u) )
    {
      TerminateThread(*(HANDLE *)(*((_QWORD *)this + 1) + 584LL), 0);
      v3 = -2147467259;
    }
  }
  catch ( long v6 )
  {
    return v6;
  }
  catch ( ulong v7 )
  {
    return v7;
  }
  v3 = CLogMgr::CrashShutDown(v2);
}

```

## disassembly

```asm
0x180004cf0  mov     [rsp+arg_8], rbx
0x180004cf5  push    rdi
0x180004cf6  sub     rsp, 30h
0x180004cfa  mov     rdi, rcx
0x180004cfd  mov     rcx, [rcx+8]; this
0x180004d01  call    ?CrashShutDown@CLogMgr@@QEAAJXZ; CLogMgr::CrashShutDown(void)
0x180004d06  mov     ebx, eax
0x180004d08  mov     rax, [rdi+8]
0x180004d0c  mov     rcx, [rax+248h]; hHandle
0x180004d13  test    rcx, rcx
0x180004d16  jz      short loc_180004D3F
0x180004d18  mov     edx, 1388h; dwMilliseconds
0x180004d1d  call    cs:__imp_WaitForSingleObject
0x180004d23  test    eax, eax
0x180004d25  jz      short loc_180004D3F
0x180004d27  mov     rcx, [rdi+8]
0x180004d2b  xor     edx, edx; dwExitCode
0x180004d2d  mov     rcx, [rcx+248h]; hThread
0x180004d34  call    cs:__imp_TerminateThread
0x180004d3a  mov     ebx, 80004005h
0x180004d3f  jmp     short loc_180004D45
0x180004d41  mov     ebx, [rsp+38h+arg_0]
0x180004d45  mov     eax, ebx
0x180004d47  mov     rbx, [rsp+38h+arg_8]
0x180004d4c  add     rsp, 30h
0x180004d50  pop     rdi
0x180004d51  retn
```
