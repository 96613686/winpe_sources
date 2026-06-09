# IsConfigRefreshSemaphoreSignaled(ushort const *)

- ea: `0x18000de10`
- end: `0x18000decb`
- name: `?IsConfigRefreshSemaphoreSignaled@@YAHPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000de10`
- `0x1800145f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000de66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000de66`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000de32`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000de32`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000de4b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000de4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000deac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000deac`

## string_xrefs

- `0x18000de22`: `__CONFIGREFRESH_NAMED_SEMAPHORE__`

## pseudocode

```c
__int64 __fastcall IsConfigRefreshSemaphoreSignaled(const unsigned __int16 *a1)
{
  unsigned int v2; // edi
  HANDLE v3; // rax
  void *v4; // rbx
  signed int LastError; // eax
  __int64 v6; // rcx

  v2 = 0;
  v3 = OpenSemaphoreW(0x100002u, 0, L"__CONFIGREFRESH_NAMED_SEMAPHORE__");
  v4 = v3;
  if ( v3 )
  {
    if ( !WaitForSingleObject(v3, 0) )
    {
      v2 = 1;
      if ( !ReleaseSemaphore(v4, 1, 0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( (byte_180032C41 & 2) != 0 )
          McTemplateU0zd_EventWriteTransfer(v6, ReleaseConfigRefreshSemaphoreFailure, a1, (unsigned int)LastError);
      }
    }
    CloseHandle(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18000de10  mov     [rsp+arg_0], rbx
0x18000de15  mov     [rsp+arg_8], rsi
0x18000de1a  push    rdi
0x18000de1b  sub     rsp, 20h
0x18000de1f  mov     rsi, rcx
0x18000de22  lea     r8, aConfigrefreshN_0; "__CONFIGREFRESH_NAMED_SEMAPHORE__"
0x18000de29  mov     ecx, 100002h; dwDesiredAccess
0x18000de2e  xor     edx, edx; bInheritHandle
0x18000de30  xor     edi, edi
0x18000de32  call    cs:__imp_OpenSemaphoreW
0x18000de39  nop     dword ptr [rax+rax+00h]
0x18000de3e  mov     rbx, rax
0x18000de41  test    rax, rax
0x18000de44  jz      short loc_18000DEB8
0x18000de46  xor     edx, edx; dwMilliseconds
0x18000de48  mov     rcx, rax; hHandle
0x18000de4b  call    cs:__imp_WaitForSingleObject
0x18000de52  nop     dword ptr [rax+rax+00h]
0x18000de57  test    eax, eax
0x18000de59  jnz     short loc_18000DEA9
0x18000de5b  lea     edi, [rax+1]
0x18000de5e  xor     r8d, r8d; lpPreviousCount
0x18000de61  mov     edx, edi; lReleaseCount
0x18000de63  mov     rcx, rbx; hSemaphore
0x18000de66  call    cs:__imp_ReleaseSemaphore
0x18000de6d  nop     dword ptr [rax+rax+00h]
0x18000de72  test    eax, eax
0x18000de74  jnz     short loc_18000DEA9
0x18000de76  call    cs:__imp_GetLastError
0x18000de7d  nop     dword ptr [rax+rax+00h]
0x18000de82  test    eax, eax
0x18000de84  jle     short loc_18000DE8E
0x18000de86  movzx   eax, ax
0x18000de89  or      eax, 80070000h
0x18000de8e  test    cs:byte_180032C41, 2
0x18000de95  jz      short loc_18000DEA9
0x18000de97  mov     r9d, eax
0x18000de9a  lea     rdx, ReleaseConfigRefreshSemaphoreFailure
0x18000dea1  mov     r8, rsi
0x18000dea4  call    McTemplateU0zd_EventWriteTransfer
0x18000dea9  mov     rcx, rbx; hObject
0x18000deac  call    cs:__imp_CloseHandle
0x18000deb3  nop     dword ptr [rax+rax+00h]
0x18000deb8  mov     rbx, [rsp+28h+arg_0]
0x18000debd  mov     eax, edi
0x18000debf  mov     rsi, [rsp+28h+arg_8]
0x18000dec4  add     rsp, 20h
0x18000dec8  pop     rdi
0x18000dec9  retn
```
