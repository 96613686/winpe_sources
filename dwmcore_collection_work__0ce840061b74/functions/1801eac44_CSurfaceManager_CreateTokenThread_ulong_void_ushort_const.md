# CSurfaceManager::CreateTokenThread(ulong (*)(void *),ushort const *)

- ea: `0x1801eac44`
- end: `0x1801ead60`
- name: `?CreateTokenThread@CSurfaceManager@@IEAAJP6AKPEAX@ZPEBG@Z`
- size: `284`
- prototype: `__int64 __fastcall(CSurfaceManager *__hidden this, unsigned int (*)(void *), const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1801ee94c`

## callees

- `0x1800098f8`
- `0x180042de0`
- `0x1801eac44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801eac93`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801eac93`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801ead4b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801ead4b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801ead42`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801ead42`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801eaceb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801eaceb`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1801ead34`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1801ead34`

## string_xrefs

- `0x1801ead2d`: `DWM Token Thread`

## pseudocode

```c
__int64 __fastcall CSurfaceManager::CreateTokenThread(
        CSurfaceManager *this,
        unsigned int (*a2)(void *),
        const unsigned __int16 *a3)
{
  unsigned int v4; // ebx
  int v5; // r9d
  _QWORD *v6; // rbx
  HANDLE EventW; // rax
  HANDLE *v8; // rbx
  HANDLE Thread; // rax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]

  if ( *((_BYTE *)this + 144) )
  {
    v4 = -2147467260;
    v5 = -2147467260;
    dwCreationFlags = 32;
LABEL_3:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v5, dwCreationFlags, 0);
    return v4;
  }
  v6 = (_QWORD *)((char *)this + 128);
  EventW = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v6,
    EventW);
  if ( ((*v6 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v8 = (HANDLE *)((char *)this + 120);
    Thread = CreateThread(0, 0, CGlobalSurfaceManager::s_TokenThreadMain, this, 4u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 120,
      Thread);
    if ( ((*((_QWORD *)this + 15) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v5 = -2147024882;
      v4 = -2147024882;
      dwCreationFlags = 51;
      goto LABEL_3;
    }
    SetThreadDescription(*((HANDLE *)this + 15), L"DWM Token Thread");
    SetThreadPriority(*v8, 15);
    ResumeThread(*v8);
    return 0;
  }
  else
  {
    v4 = -2147024882;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x28u, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x1801eac44  mov     [rsp+arg_0], rbx
0x1801eac49  push    rdi
0x1801eac4a  sub     rsp, 30h
0x1801eac4e  xor     r8d, r8d; unsigned int
0x1801eac51  mov     rdi, rcx
0x1801eac54  cmp     [rcx+90h], r8b
0x1801eac5b  jz      short loc_1801EAC83
0x1801eac5d  mov     ebx, 80004004h
0x1801eac62  mov     [rsp+38h+lpThreadId], r8; void *
0x1801eac67  mov     r9d, ebx; int
0x1801eac6a  mov     [rsp+38h+dwCreationFlags], 20h ; ' '; unsigned int
0x1801eac72  xor     edx, edx; int *
0x1801eac74  mov     ecx, 14h; unsigned int
0x1801eac79  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801eac7e  jmp     loc_1801EAD53
0x1801eac83  xor     r9d, r9d; lpName
0x1801eac86  lea     rbx, [rcx+80h]
0x1801eac8d  xor     ecx, ecx; lpEventAttributes
0x1801eac8f  lea     edx, [r9+1]; bManualReset
0x1801eac93  call    cs:__imp_CreateEventW
0x1801eac99  mov     rdx, rax
0x1801eac9c  mov     rcx, rbx
0x1801eac9f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801eaca4  mov     rax, [rbx]
0x1801eaca7  xor     edx, edx; dwStackSize
0x1801eaca9  inc     rax
0x1801eacac  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1801eacb5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801eacbb  jnz     short loc_1801EACD3
0x1801eacbd  mov     r9d, 8007000Eh
0x1801eacc3  mov     [rsp+38h+dwCreationFlags], 28h ; '('
0x1801eaccb  mov     ebx, r9d
0x1801eacce  xor     r8d, r8d
0x1801eacd1  jmp     short loc_1801EAC74
0x1801eacd3  mov     r9, rdi; lpParameter
0x1801eacd6  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1801eacde  lea     r8, ?s_TokenThreadMain@CGlobalSurfaceManager@@CAKPEAX@Z; lpStartAddress
0x1801eace5  xor     ecx, ecx; lpThreadAttributes
0x1801eace7  lea     rbx, [rdi+78h]
0x1801eaceb  call    cs:__imp_CreateThread
0x1801eacf1  mov     rdx, rax
0x1801eacf4  mov     rcx, rbx
0x1801eacf7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801eacfc  mov     rcx, [rbx]; hThread
0x1801eacff  lea     rax, [rcx+1]
0x1801ead03  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801ead09  jnz     short loc_1801EAD2D
0x1801ead0b  mov     r9d, 8007000Eh
0x1801ead11  mov     [rsp+38h+lpThreadId], 0
0x1801ead1a  mov     ebx, r9d
0x1801ead1d  mov     [rsp+38h+dwCreationFlags], 33h ; '3'
0x1801ead25  xor     r8d, r8d
0x1801ead28  jmp     loc_1801EAC72
0x1801ead2d  lea     rdx, aDwmTokenThread; "DWM Token Thread"
0x1801ead34  call    cs:__imp_SetThreadDescription
0x1801ead3a  mov     rcx, [rbx]; hThread
0x1801ead3d  mov     edx, 0Fh; nPriority
0x1801ead42  call    cs:__imp_SetThreadPriority
0x1801ead48  mov     rcx, [rbx]; hThread
0x1801ead4b  call    cs:__imp_ResumeThread
0x1801ead51  xor     ebx, ebx
0x1801ead53  mov     eax, ebx
0x1801ead55  mov     rbx, [rsp+38h+arg_0]
0x1801ead5a  add     rsp, 30h
0x1801ead5e  pop     rdi
0x1801ead5f  retn
```
