# CAPCThread::Initialize(void)

- ea: `0x18001fe90`
- end: `0x18002006f`
- name: `?Initialize@CAPCThread@@UEAAJXZ`
- size: `479`
- prototype: `__int64 __fastcall(CAPCThread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f870`

## callees

- `0x18001d04c`
- `0x18001ef44`
- `0x18001fe90`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020038`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020038`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001feb2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001feb2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001ff89`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001ff89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001ff13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001ff13`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002004f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002004f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffb2`

## pseudocode

```c
__int64 __fastcall CAPCThread::Initialize(CAPCThread *this)
{
  HANDLE EventW; // rax
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  HANDLE Thread; // rax
  bool v7; // sf
  void *v8; // rcx
  void *v9; // rcx
  HMODULE v10; // rcx

  *((_DWORD *)this + 5) |= 2u;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 6) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 13;
LABEL_18:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_e06d9da063383fc2b93c39ab877dcc3d_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
LABEL_19:
    v7 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError < 0;
    }
    v8 = (void *)*((_QWORD *)this + 6);
    if ( !v7 )
      LastError = -2147467259;
    if ( v8 )
    {
      CloseHandle(v8);
      *((_QWORD *)this + 6) = 0;
    }
    v9 = (void *)*((_QWORD *)this + 5);
    if ( v9 )
    {
      CloseHandle(v9);
      *((_QWORD *)this + 5) = 0;
    }
    v10 = (HMODULE)*((_QWORD *)this + 7);
    if ( v10 )
    {
      FreeLibrary(v10);
      *((_QWORD *)this + 7) = 0;
    }
    return (unsigned int)LastError;
  }
  if ( !GetModuleHandleExW(4u, (LPCWSTR)CAPCThread::static_APC_thread, (HMODULE *)this + 7) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 14;
    goto LABEL_18;
  }
  LastError = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
  Thread = CreateThread(0, 0, CAPCThread::static_APC_thread, (char *)this - 16, 0, 0);
  *((_QWORD *)this + 5) = Thread;
  if ( !Thread )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 16LL))(*((_QWORD *)this + 3));
  if ( !*((_QWORD *)this + 5) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 15;
    goto LABEL_18;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001fe90  mov     [rsp+arg_0], rbx
0x18001fe95  mov     [rsp+arg_8], rsi
0x18001fe9a  push    rdi
0x18001fe9b  sub     rsp, 30h
0x18001fe9f  or      dword ptr [rcx+14h], 2
0x18001fea3  xor     r9d, r9d; lpName
0x18001fea6  mov     rdi, rcx
0x18001fea9  xor     r8d, r8d; bInitialState
0x18001feac  xor     ecx, ecx; lpEventAttributes
0x18001feae  lea     edx, [r9+1]; bManualReset
0x18001feb2  call    cs:__imp_CreateEventW
0x18001feb8  mov     [rdi+30h], rax
0x18001febc  test    rax, rax
0x18001febf  jnz     short loc_18001FF03
0x18001fec1  call    cs:__imp_GetLastError
0x18001fec7  mov     ebx, eax
0x18001fec9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fed0  lea     rax, WPP_GLOBAL_Control
0x18001fed7  cmp     rcx, rax
0x18001feda  jz      loc_180020001
0x18001fee0  test    byte ptr [rcx+1Ch], 8
0x18001fee4  jz      loc_180020001
0x18001feea  cmp     byte ptr [rcx+19h], 2
0x18001feee  jb      loc_180020001
0x18001fef4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001fef9  mov     edx, 0Dh
0x18001fefe  jmp     loc_18001FFE3
0x18001ff03  lea     r8, [rdi+38h]; phModule
0x18001ff07  mov     ecx, 4; dwFlags
0x18001ff0c  lea     rdx, ?static_APC_thread@CAPCThread@@SAKPEAX@Z; lpModuleName
0x18001ff13  call    cs:__imp_GetModuleHandleExW
0x18001ff19  test    eax, eax
0x18001ff1b  jnz     short loc_18001FF5F
0x18001ff1d  call    cs:__imp_GetLastError
0x18001ff23  mov     ebx, eax
0x18001ff25  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff2c  lea     rax, WPP_GLOBAL_Control
0x18001ff33  cmp     rcx, rax
0x18001ff36  jz      loc_180020001
0x18001ff3c  test    byte ptr [rcx+1Ch], 8
0x18001ff40  jz      loc_180020001
0x18001ff46  cmp     byte ptr [rcx+19h], 2
0x18001ff4a  jb      loc_180020001
0x18001ff50  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001ff55  mov     edx, 0Eh
0x18001ff5a  jmp     loc_18001FFE3
0x18001ff5f  mov     rcx, [rdi+18h]
0x18001ff63  xor     ebx, ebx
0x18001ff65  mov     rax, [rcx]
0x18001ff68  mov     rax, [rax+8]
0x18001ff6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff71  lea     r9, [rdi-10h]; lpParameter
0x18001ff75  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x18001ff7a  lea     r8, ?static_APC_thread@CAPCThread@@SAKPEAX@Z; lpStartAddress
0x18001ff81  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x18001ff85  xor     edx, edx; dwStackSize
0x18001ff87  xor     ecx, ecx; lpThreadAttributes
0x18001ff89  call    cs:__imp_CreateThread
0x18001ff8f  mov     [rdi+28h], rax
0x18001ff93  test    rax, rax
0x18001ff96  jnz     short loc_18001FFA8
0x18001ff98  mov     rcx, [rdi+18h]
0x18001ff9c  mov     rax, [rcx]
0x18001ff9f  mov     rax, [rax+10h]
0x18001ffa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffa8  cmp     [rdi+28h], rbx
0x18001ffac  jnz     loc_18002005D
0x18001ffb2  call    cs:__imp_GetLastError
0x18001ffb8  mov     ebx, eax
0x18001ffba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffc1  lea     rax, WPP_GLOBAL_Control
0x18001ffc8  cmp     rcx, rax
0x18001ffcb  jz      short loc_180020001
0x18001ffcd  test    byte ptr [rcx+1Ch], 8
0x18001ffd1  jz      short loc_180020001
0x18001ffd3  cmp     byte ptr [rcx+19h], 2
0x18001ffd7  jb      short loc_180020001
0x18001ffd9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001ffde  mov     edx, 0Fh
0x18001ffe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffea  lea     r8, WPP_e06d9da063383fc2b93c39ab877dcc3d_Traceguids
0x18001fff1  mov     r9d, eax
0x18001fff4  mov     [rsp+38h+dwCreationFlags], ebx
0x18001fff8  mov     rcx, [rcx+10h]
0x18001fffc  call    WPP_SF_Dd
0x180020001  test    ebx, ebx
0x180020003  jle     short loc_180020010
0x180020005  movzx   ebx, bx
0x180020008  or      ebx, 80070000h
0x18002000e  test    ebx, ebx
0x180020010  mov     rcx, [rdi+30h]; hObject
0x180020014  mov     eax, 80004005h
0x180020019  cmovns  ebx, eax
0x18002001c  test    rcx, rcx
0x18002001f  jz      short loc_18002002F
0x180020021  call    cs:__imp_CloseHandle
0x180020027  mov     qword ptr [rdi+30h], 0
0x18002002f  mov     rcx, [rdi+28h]; hObject
0x180020033  test    rcx, rcx
0x180020036  jz      short loc_180020046
0x180020038  call    cs:__imp_CloseHandle
0x18002003e  mov     qword ptr [rdi+28h], 0
0x180020046  mov     rcx, [rdi+38h]; hLibModule
0x18002004a  test    rcx, rcx
0x18002004d  jz      short loc_18002005D
0x18002004f  call    cs:__imp_FreeLibrary
0x180020055  mov     qword ptr [rdi+38h], 0
0x18002005d  mov     rsi, [rsp+38h+arg_8]
0x180020062  mov     eax, ebx
0x180020064  mov     rbx, [rsp+38h+arg_0]
0x180020069  add     rsp, 30h
0x18002006d  pop     rdi
0x18002006e  retn
```
