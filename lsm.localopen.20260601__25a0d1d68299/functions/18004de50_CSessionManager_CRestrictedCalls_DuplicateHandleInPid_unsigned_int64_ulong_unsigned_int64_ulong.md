# CSessionManager::CRestrictedCalls::DuplicateHandleInPid(unsigned __int64,ulong,unsigned __int64 *,ulong)

- ea: `0x18004de50`
- end: `0x18004e025`
- name: `?DuplicateHandleInPid@CRestrictedCalls@CSessionManager@@UEAAJ_KKPEA_KK@Z`
- size: `469`
- prototype: `int(CSessionManager::CRestrictedCalls *__hidden this, unsigned __int64, unsigned int, unsigned __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800077a0`
- `0x180012650`
- `0x1800248ac`
- `0x18004de50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dfd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dfd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004df25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004df91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004df25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004df91`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004df56`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004dfc1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004df56`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004dfc1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004de83`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004dee0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004de83`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004dee0`

## string_xrefs

- `0x18004debf`: `OpenProcess( SourcePid ) failed: 0x%x`
- `0x18004df1c`: `OpenProcess( TargetPid ) failed: 0x%x`

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
  HANDLE v7; // rax
  HANDLE v8; // rdi
  signed int v9; // eax
  unsigned int v10; // ebx
  HANDLE v11; // rax
  HANDLE v12; // rbx
  signed int v13; // eax
  HANDLE CurrentProcess; // rax
  signed int v15; // eax
  HANDLE v16; // rdi
  HANDLE v17; // rax
  signed int LastError; // eax
  HANDLE TargetHandle; // [rsp+40h] [rbp-20h] BYREF
  HANDLE hTargetProcessHandle; // [rsp+48h] [rbp-18h] BYREF
  HANDLE hSourceProcessHandle[2]; // [rsp+50h] [rbp-10h] BYREF

  hSourceProcessHandle[0] = 0;
  hTargetProcessHandle = 0;
  TargetHandle = 0;
  v7 = OpenProcess(0x40u, 0, a3);
  SmartHANDLE::operator=(hSourceProcessHandle, v7);
  v8 = hSourceProcessHandle[0];
  if ( hSourceProcessHandle[0] )
  {
    v11 = OpenProcess(0x40u, 0, dwProcessId);
    SmartHANDLE::operator=(&hTargetProcessHandle, v11);
    v12 = hTargetProcessHandle;
    if ( hTargetProcessHandle )
    {
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(v8, a2, CurrentProcess, &TargetHandle, 0, 0, 6u) )
      {
        v16 = TargetHandle;
        v17 = GetCurrentProcess();
        if ( DuplicateHandle(v17, v16, v12, a4, 0, 0, 6u) )
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
        v15 = GetLastError();
        v10 = v15;
        if ( v15 > 0 )
          v10 = (unsigned __int16)v15 | 0x80070000;
        _DbgPrintMessage(8, "DuplicateHandle( Source, My ) failed: 0x%x", v10);
      }
    }
    else
    {
      v13 = GetLastError();
      v10 = v13;
      if ( v13 > 0 )
        v10 = (unsigned __int16)v13 | 0x80070000;
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
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&TargetHandle);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&hTargetProcessHandle);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)hSourceProcessHandle);
  return v10;
}

```

## disassembly

```asm
0x18004de50  push    rbp
0x18004de52  push    rbx
0x18004de53  push    rsi
0x18004de54  push    rdi
0x18004de55  push    r14
0x18004de57  mov     rbp, rsp
0x18004de5a  sub     rsp, 60h
0x18004de5e  mov     r14, r9
0x18004de61  mov     rsi, rdx
0x18004de64  mov     [rbp+hSourceProcessHandle], 0
0x18004de6c  mov     [rbp+hTargetProcessHandle], 0
0x18004de74  mov     [rbp+TargetHandle], 0
0x18004de7c  xor     edx, edx; bInheritHandle
0x18004de7e  lea     ebx, [rdx+40h]
0x18004de81  mov     ecx, ebx; dwDesiredAccess
0x18004de83  call    cs:__imp_OpenProcess
0x18004de8a  nop     dword ptr [rax+rax+00h]
0x18004de8f  mov     rdx, rax
0x18004de92  lea     rcx, [rbp+hSourceProcessHandle]
0x18004de96  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x18004de9b  mov     rdi, [rbp+hSourceProcessHandle]
0x18004de9f  test    rdi, rdi
0x18004dea2  jnz     short loc_18004DED8
0x18004dea4  call    cs:__imp_GetLastError
0x18004deab  nop     dword ptr [rax+rax+00h]
0x18004deb0  mov     ebx, eax
0x18004deb2  test    eax, eax
0x18004deb4  jle     short loc_18004DEBF
0x18004deb6  movzx   ebx, ax
0x18004deb9  or      ebx, 80070000h
0x18004debf  lea     rdx, aOpenprocessSou; "OpenProcess( SourcePid ) failed: 0x%x"
0x18004dec6  mov     r8d, ebx
0x18004dec9  mov     ecx, 8; int
0x18004dece  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004ded3  jmp     loc_18004DFFA
0x18004ded8  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x18004dedc  xor     edx, edx; bInheritHandle
0x18004dede  mov     ecx, ebx; dwDesiredAccess
0x18004dee0  call    cs:__imp_OpenProcess
0x18004dee7  nop     dword ptr [rax+rax+00h]
0x18004deec  mov     rdx, rax
0x18004deef  lea     rcx, [rbp+hTargetProcessHandle]
0x18004def3  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x18004def8  mov     rbx, [rbp+hTargetProcessHandle]
0x18004defc  test    rbx, rbx
0x18004deff  jnz     short loc_18004DF25
0x18004df01  call    cs:__imp_GetLastError
0x18004df08  nop     dword ptr [rax+rax+00h]
0x18004df0d  mov     ebx, eax
0x18004df0f  test    eax, eax
0x18004df11  jle     short loc_18004DF1C
0x18004df13  movzx   ebx, ax
0x18004df16  or      ebx, 80070000h
0x18004df1c  lea     rdx, aOpenprocessTar; "OpenProcess( TargetPid ) failed: 0x%x"
0x18004df23  jmp     short loc_18004DEC6
0x18004df25  call    cs:__imp_GetCurrentProcess
0x18004df2c  nop     dword ptr [rax+rax+00h]
0x18004df31  mov     [rsp+60h+dwOptions], 6; dwOptions
0x18004df39  mov     [rsp+60h+bInheritHandle], 0; bInheritHandle
0x18004df41  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x18004df49  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18004df4d  mov     r8, rax; hTargetProcessHandle
0x18004df50  mov     rdx, rsi; hSourceHandle
0x18004df53  mov     rcx, rdi; hSourceProcessHandle
0x18004df56  call    cs:__imp_DuplicateHandle
0x18004df5d  nop     dword ptr [rax+rax+00h]
0x18004df62  test    eax, eax
0x18004df64  jnz     short loc_18004DF8D
0x18004df66  call    cs:__imp_GetLastError
0x18004df6d  nop     dword ptr [rax+rax+00h]
0x18004df72  mov     ebx, eax
0x18004df74  test    eax, eax
0x18004df76  jle     short loc_18004DF81
0x18004df78  movzx   ebx, ax
0x18004df7b  or      ebx, 80070000h
0x18004df81  lea     rdx, aDuplicatehandl_4; "DuplicateHandle( Source, My ) failed: 0"...
0x18004df88  jmp     loc_18004DEC6
0x18004df8d  mov     rdi, [rbp+TargetHandle]
0x18004df91  call    cs:__imp_GetCurrentProcess
0x18004df98  nop     dword ptr [rax+rax+00h]
0x18004df9d  mov     [rsp+60h+dwOptions], 6; dwOptions
0x18004dfa5  mov     [rsp+60h+bInheritHandle], 0; bInheritHandle
0x18004dfad  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x18004dfb5  mov     r9, r14; lpTargetHandle
0x18004dfb8  mov     r8, rbx; hTargetProcessHandle
0x18004dfbb  mov     rdx, rdi; hSourceHandle
0x18004dfbe  mov     rcx, rax; hSourceProcessHandle
0x18004dfc1  call    cs:__imp_DuplicateHandle
0x18004dfc8  nop     dword ptr [rax+rax+00h]
0x18004dfcd  test    eax, eax
0x18004dfcf  jnz     short loc_18004DFF8
0x18004dfd1  call    cs:__imp_GetLastError
0x18004dfd8  nop     dword ptr [rax+rax+00h]
0x18004dfdd  mov     ebx, eax
0x18004dfdf  test    eax, eax
0x18004dfe1  jle     short loc_18004DFEC
0x18004dfe3  movzx   ebx, ax
0x18004dfe6  or      ebx, 80070000h
0x18004dfec  lea     rdx, aDuplicatehandl; "DuplicateHandle( Target, My ) failed: 0"...
0x18004dff3  jmp     loc_18004DEC6
0x18004dff8  xor     ebx, ebx
0x18004dffa  lea     rcx, [rbp+TargetHandle]; this
0x18004dffe  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18004e003  nop
0x18004e004  lea     rcx, [rbp+hTargetProcessHandle]; this
0x18004e008  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18004e00d  nop
0x18004e00e  lea     rcx, [rbp+hSourceProcessHandle]; this
0x18004e012  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18004e017  mov     eax, ebx
0x18004e019  add     rsp, 60h
0x18004e01d  pop     r14
0x18004e01f  pop     rdi
0x18004e020  pop     rsi
0x18004e021  pop     rbx
0x18004e022  pop     rbp
0x18004e023  retn
```
