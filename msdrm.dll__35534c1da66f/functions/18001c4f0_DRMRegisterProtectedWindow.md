# DRMRegisterProtectedWindow

- ea: `0x18001c4f0`
- end: `0x18001c604`
- name: `DRMRegisterProtectedWindow`
- size: `276`
- prototype: `HRESULT __stdcall(DRMENVHANDLE hEnv, HWND hwnd)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800046c8`
- `0x180018d70`
- `0x18001c4f0`
- `0x18004e440`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c52c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c52c`
- `USER32!SetPropW` at `0x18001c583`
- `USER32!SetPropW` at `0x18001c59a`
- `USER32!SetPropW` at `0x18001c5b1`
- `USER32!SetPropW` at `0x18001c583`
- `USER32!SetPropW` at `0x18001c59a`
- `USER32!SetPropW` at `0x18001c5b1`
- `USER32!GetWindowThreadProcessId` at `0x18001c53d`
- `USER32!GetWindowThreadProcessId` at `0x18001c53d`
- `USER32!IsWindowVisible` at `0x18001c55a`
- `USER32!IsWindowVisible` at `0x18001c55a`

## string_xrefs

- `0x18001c579`: `RM_ProcessId`
- `0x18001c5a7`: `RM_ThreadId`

## pseudocode

```c
HRESULT __stdcall DRMRegisterProtectedWindow(DRMENVHANDLE hEnv, HWND hwnd)
{
  void *v2; // rbp
  DRMENVHANDLE v4; // edi
  void *CurrentProcessId; // r14
  void *WindowThreadProcessId; // r15
  int v7; // ebx
  DRMENVHANDLE phCopy; // [rsp+50h] [rbp+8h] BYREF
  DWORD dwProcessId; // [rsp+60h] [rbp+18h] BYREF

  v2 = (void *)hEnv;
  _RTLTRACE("[msdrm]:+DRMRegisterProtectedWindow\n");
  v4 = 0;
  phCopy = 0;
  dwProcessId = 0;
  if ( (_DWORD)v2 && hwnd )
  {
    CurrentProcessId = (void *)GetCurrentProcessId();
    WindowThreadProcessId = (void *)GetWindowThreadProcessId(hwnd, &dwProcessId);
    if ( (_DWORD)CurrentProcessId == dwProcessId )
    {
      if ( IsWindowVisible(hwnd) )
      {
        v7 = DRMDuplicateEnvironmentHandle((DRMENVHANDLE)v2, &phCopy);
        if ( v7 >= 0
          && (!SetPropW(hwnd, L"RM_ProcessId", CurrentProcessId)
           || !SetPropW(hwnd, L"RM_EnvHandle", v2)
           || !SetPropW(hwnd, L"RM_ThreadId", WindowThreadProcessId)) )
        {
          GetLastError();
          v7 = -2147168393;
        }
        v4 = phCopy;
      }
      else
      {
        v7 = -2147168394;
      }
      if ( v4 )
        DRMCloseEnvironmentHandle(v4);
    }
    else
    {
      v7 = -2147168394;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  _RTLTRACE("[msdrm]:-DRMRegisterProtectedWindow HR=%x\n", v7);
  return v7;
}

```

## disassembly

```asm
0x18001c4f0  mov     [rsp+arg_8], rbx
0x18001c4f5  push    rbp
0x18001c4f6  push    rsi
0x18001c4f7  push    rdi
0x18001c4f8  push    r14
0x18001c4fa  push    r15
0x18001c4fc  sub     rsp, 20h
0x18001c500  mov     ebp, ecx
0x18001c502  mov     rsi, rdx
0x18001c505  lea     rcx, aMsdrmDrmregist_2; "[msdrm]:+DRMRegisterProtectedWindow\n"
0x18001c50c  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001c511  xor     edi, edi
0x18001c513  mov     [rsp+48h+phCopy], edi
0x18001c517  mov     [rsp+48h+dwProcessId], edi
0x18001c51b  test    ebp, ebp
0x18001c51d  jz      loc_18001C5DE
0x18001c523  test    rsi, rsi
0x18001c526  jz      loc_18001C5DE
0x18001c52c  call    cs:__imp_GetCurrentProcessId
0x18001c532  lea     rdx, [rsp+48h+dwProcessId]; lpdwProcessId
0x18001c537  mov     rcx, rsi; hWnd
0x18001c53a  mov     r14d, eax
0x18001c53d  call    cs:__imp_GetWindowThreadProcessId
0x18001c543  mov     r15d, eax
0x18001c546  cmp     r14d, [rsp+48h+dwProcessId]
0x18001c54b  jz      short loc_18001C557
0x18001c54d  mov     ebx, 8004CF76h
0x18001c552  jmp     loc_18001C5E3
0x18001c557  mov     rcx, rsi; hWnd
0x18001c55a  call    cs:__imp_IsWindowVisible
0x18001c560  test    eax, eax
0x18001c562  jz      short loc_18001C5CC
0x18001c564  lea     rdx, [rsp+48h+phCopy]; phCopy
0x18001c569  mov     ecx, ebp; hToCopy
0x18001c56b  call    DRMDuplicateEnvironmentHandle
0x18001c570  mov     ebx, eax
0x18001c572  test    eax, eax
0x18001c574  js      short loc_18001C5C6
0x18001c576  mov     r8, r14; hData
0x18001c579  lea     rdx, String; "RM_ProcessId"
0x18001c580  mov     rcx, rsi; hWnd
0x18001c583  call    cs:__imp_SetPropW
0x18001c589  test    eax, eax
0x18001c58b  jz      short loc_18001C5BB
0x18001c58d  mov     r8, rbp; hData
0x18001c590  lea     rdx, aRmEnvhandle; "RM_EnvHandle"
0x18001c597  mov     rcx, rsi; hWnd
0x18001c59a  call    cs:__imp_SetPropW
0x18001c5a0  test    eax, eax
0x18001c5a2  jz      short loc_18001C5BB
0x18001c5a4  mov     r8, r15; hData
0x18001c5a7  lea     rdx, aRmThreadid; "RM_ThreadId"
0x18001c5ae  mov     rcx, rsi; hWnd
0x18001c5b1  call    cs:__imp_SetPropW
0x18001c5b7  test    eax, eax
0x18001c5b9  jnz     short loc_18001C5C6
0x18001c5bb  call    cs:__imp_GetLastError
0x18001c5c1  mov     ebx, 8004CF77h
0x18001c5c6  mov     edi, [rsp+48h+phCopy]
0x18001c5ca  jmp     short loc_18001C5D1
0x18001c5cc  mov     ebx, 8004CF76h
0x18001c5d1  test    edi, edi
0x18001c5d3  jz      short loc_18001C5E3
0x18001c5d5  mov     ecx, edi; hEnv
0x18001c5d7  call    DRMCloseEnvironmentHandle
0x18001c5dc  jmp     short loc_18001C5E3
0x18001c5de  mov     ebx, 80070057h
0x18001c5e3  mov     edx, ebx
0x18001c5e5  lea     rcx, aMsdrmDrmregist_1; "[msdrm]:-DRMRegisterProtectedWindow HR="...
0x18001c5ec  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001c5f1  mov     eax, ebx
0x18001c5f3  mov     rbx, [rsp+48h+arg_8]
0x18001c5f8  add     rsp, 20h
0x18001c5fc  pop     r15
0x18001c5fe  pop     r14
0x18001c600  pop     rdi
0x18001c601  pop     rsi
0x18001c602  pop     rbp
0x18001c603  retn
```
