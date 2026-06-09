# CSessionManager::CRestrictedCalls::DuplicateHandleInPid(unsigned __int64,ulong,unsigned __int64 *,ulong)

- ea: `0x18004aaa0`
- end: `0x18004ac57`
- name: `?DuplicateHandleInPid@CRestrictedCalls@CSessionManager@@UEAAJ_KKPEA_KK@Z`
- size: `439`
- prototype: `int(CSessionManager::CRestrictedCalls *__hidden this, unsigned __int64, unsigned int, unsigned __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x1800074c0`
- `0x180022bb8`
- `0x18004aaa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ab3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ab95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ab3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ab95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ab5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004abbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ab5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004abbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ac1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ac2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ac3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ac1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ac2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ac3f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004ab8b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004abe5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004ab8b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004abe5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004aacd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004ab22`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004aacd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004ab22`

## string_xrefs

- `0x18004aafc`: `OpenProcess( SourcePid ) failed: 0x%x`
- `0x18004ab54`: `OpenProcess( TargetPid ) failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSessionManager::CRestrictedCalls::DuplicateHandleInPid(
        CSessionManager::CRestrictedCalls *this,
        void *a2,
        DWORD a3,
        HANDLE *a4,
        DWORD dwProcessId)
{
  HANDLE v7; // rbx
  HANDLE v8; // rax
  signed int v9; // eax
  unsigned int v10; // esi
  HANDLE v11; // rax
  signed int v12; // eax
  HANDLE CurrentProcess; // rax
  signed int v14; // eax
  HANDLE v15; // rsi
  HANDLE v16; // rax
  signed int LastError; // eax
  HANDLE hSourceProcessHandle; // [rsp+40h] [rbp-28h] BYREF
  HANDLE TargetHandle; // [rsp+48h] [rbp-20h] BYREF
  HANDLE hTargetProcessHandle[3]; // [rsp+50h] [rbp-18h] BYREF

  hSourceProcessHandle = 0;
  v7 = 0;
  hTargetProcessHandle[0] = 0;
  TargetHandle = 0;
  v8 = OpenProcess(0x40u, 0, a3);
  SmartHANDLE::operator=(&hSourceProcessHandle, v8);
  if ( hSourceProcessHandle )
  {
    v11 = OpenProcess(0x40u, 0, dwProcessId);
    SmartHANDLE::operator=(hTargetProcessHandle, v11);
    v7 = hTargetProcessHandle[0];
    if ( hTargetProcessHandle[0] )
    {
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(hSourceProcessHandle, a2, CurrentProcess, &TargetHandle, 0, 0, 6u) )
      {
        v15 = TargetHandle;
        v16 = GetCurrentProcess();
        if ( DuplicateHandle(v16, v15, v7, a4, 0, 0, 6u) )
        {
          v10 = 0;
        }
        else
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          _DbgPrintMessage(8, "DuplicateHandle( Target, My ) failed: 0x%x", v10);
        }
      }
      else
      {
        v14 = GetLastError();
        v10 = v14;
        if ( v14 > 0 )
          v10 = (unsigned __int16)v14 | 0x80070000;
        _DbgPrintMessage(8, "DuplicateHandle( Source, My ) failed: 0x%x", v10);
      }
    }
    else
    {
      v12 = GetLastError();
      v10 = v12;
      if ( v12 > 0 )
        v10 = (unsigned __int16)v12 | 0x80070000;
      _DbgPrintMessage(8, "OpenProcess( TargetPid ) failed: 0x%x", v10);
    }
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    _DbgPrintMessage(8, "OpenProcess( SourcePid ) failed: 0x%x", v10);
  }
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( v7 )
    CloseHandle(v7);
  if ( hSourceProcessHandle )
    CloseHandle(hSourceProcessHandle);
  return v10;
}

```

## disassembly

```asm
0x18004aaa0  mov     rax, rsp
0x18004aaa3  mov     [rax+8], rbx
0x18004aaa7  mov     [rax+10h], rbp
0x18004aaab  push    rsi
0x18004aaac  sub     rsp, 60h
0x18004aab0  mov     rbp, r9
0x18004aab3  mov     rsi, rdx
0x18004aab6  mov     qword ptr [rax-28h], 0
0x18004aabe  xor     ebx, ebx
0x18004aac0  mov     [rax-18h], rbx
0x18004aac4  mov     [rax-20h], rbx
0x18004aac8  xor     edx, edx; bInheritHandle
0x18004aaca  lea     ecx, [rbx+40h]; dwDesiredAccess
0x18004aacd  call    cs:__imp_OpenProcess
0x18004aad3  mov     rdx, rax
0x18004aad6  lea     rcx, [rsp+68h+hSourceProcessHandle]
0x18004aadb  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x18004aae0  cmp     [rsp+68h+hSourceProcessHandle], rbx
0x18004aae5  jnz     short loc_18004AB15
0x18004aae7  call    cs:__imp_GetLastError
0x18004aaed  mov     esi, eax
0x18004aaef  test    eax, eax
0x18004aaf1  jle     short loc_18004AAFC
0x18004aaf3  movzx   esi, ax
0x18004aaf6  or      esi, 80070000h
0x18004aafc  lea     rdx, aOpenprocessSou; "OpenProcess( SourcePid ) failed: 0x%x"
0x18004ab03  mov     r8d, esi
0x18004ab06  mov     ecx, 8; int
0x18004ab0b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004ab10  jmp     loc_18004AC12
0x18004ab15  mov     r8d, [rsp+68h+dwProcessId]; dwProcessId
0x18004ab1d  xor     edx, edx; bInheritHandle
0x18004ab1f  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18004ab22  call    cs:__imp_OpenProcess
0x18004ab28  mov     rdx, rax
0x18004ab2b  lea     rcx, [rsp+68h+hTargetProcessHandle]
0x18004ab30  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x18004ab35  mov     rbx, [rsp+68h+hTargetProcessHandle]
0x18004ab3a  test    rbx, rbx
0x18004ab3d  jnz     short loc_18004AB5D
0x18004ab3f  call    cs:__imp_GetLastError
0x18004ab45  mov     esi, eax
0x18004ab47  test    eax, eax
0x18004ab49  jle     short loc_18004AB54
0x18004ab4b  movzx   esi, ax
0x18004ab4e  or      esi, 80070000h
0x18004ab54  lea     rdx, aOpenprocessTar; "OpenProcess( TargetPid ) failed: 0x%x"
0x18004ab5b  jmp     short loc_18004AB03
0x18004ab5d  call    cs:__imp_GetCurrentProcess
0x18004ab63  mov     [rsp+68h+dwOptions], 6; dwOptions
0x18004ab6b  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18004ab73  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18004ab7b  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x18004ab80  mov     r8, rax; hTargetProcessHandle
0x18004ab83  mov     rdx, rsi; hSourceHandle
0x18004ab86  mov     rcx, [rsp+68h+hSourceProcessHandle]; hSourceProcessHandle
0x18004ab8b  call    cs:__imp_DuplicateHandle
0x18004ab91  test    eax, eax
0x18004ab93  jnz     short loc_18004ABB6
0x18004ab95  call    cs:__imp_GetLastError
0x18004ab9b  mov     esi, eax
0x18004ab9d  test    eax, eax
0x18004ab9f  jle     short loc_18004ABAA
0x18004aba1  movzx   esi, ax
0x18004aba4  or      esi, 80070000h
0x18004abaa  lea     rdx, aDuplicatehandl_4; "DuplicateHandle( Source, My ) failed: 0"...
0x18004abb1  jmp     loc_18004AB03
0x18004abb6  mov     rsi, [rsp+68h+TargetHandle]
0x18004abbb  call    cs:__imp_GetCurrentProcess
0x18004abc1  mov     [rsp+68h+dwOptions], 6; dwOptions
0x18004abc9  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18004abd1  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18004abd9  mov     r9, rbp; lpTargetHandle
0x18004abdc  mov     r8, rbx; hTargetProcessHandle
0x18004abdf  mov     rdx, rsi; hSourceHandle
0x18004abe2  mov     rcx, rax; hSourceProcessHandle
0x18004abe5  call    cs:__imp_DuplicateHandle
0x18004abeb  test    eax, eax
0x18004abed  jnz     short loc_18004AC10
0x18004abef  call    cs:__imp_GetLastError
0x18004abf5  mov     esi, eax
0x18004abf7  test    eax, eax
0x18004abf9  jle     short loc_18004AC04
0x18004abfb  movzx   esi, ax
0x18004abfe  or      esi, 80070000h
0x18004ac04  lea     rdx, aDuplicatehandl; "DuplicateHandle( Target, My ) failed: 0"...
0x18004ac0b  jmp     loc_18004AB03
0x18004ac10  xor     esi, esi
0x18004ac12  mov     rcx, [rsp+68h+TargetHandle]; hObject
0x18004ac17  test    rcx, rcx
0x18004ac1a  jz      short loc_18004AC23
0x18004ac1c  call    cs:__imp_CloseHandle
0x18004ac22  nop
0x18004ac23  test    rbx, rbx
0x18004ac26  jz      short loc_18004AC32
0x18004ac28  mov     rcx, rbx; hObject
0x18004ac2b  call    cs:__imp_CloseHandle
0x18004ac31  nop
0x18004ac32  cmp     [rsp+68h+hSourceProcessHandle], 0
0x18004ac38  jz      short loc_18004AC45
0x18004ac3a  mov     rcx, [rsp+68h+hSourceProcessHandle]; hObject
0x18004ac3f  call    cs:__imp_CloseHandle
0x18004ac45  mov     eax, esi
0x18004ac47  mov     rbx, [rsp+68h+arg_0]
0x18004ac4c  mov     rbp, [rsp+68h+arg_8]
0x18004ac51  add     rsp, 60h
0x18004ac55  pop     rsi
0x18004ac56  retn
```
