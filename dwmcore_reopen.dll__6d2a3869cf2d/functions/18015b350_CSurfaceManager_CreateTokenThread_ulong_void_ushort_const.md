# CSurfaceManager::CreateTokenThread(ulong (*)(void *),ushort const *)

- ea: `0x18015b350`
- end: `0x18015b46c`
- name: `?CreateTokenThread@CSurfaceManager@@IEAAJP6AKPEAX@ZPEBG@Z`
- size: `284`
- prototype: `__int64 __fastcall(CSurfaceManager *__hidden this, unsigned int (*)(void *), const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1801ee2ec`

## callees

- `0x180050270`
- `0x18015adb4`
- `0x18015b350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18015b39f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18015b39f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18015b457`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18015b457`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18015b44e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18015b44e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18015b3f7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18015b3f7`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18015b440`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18015b440`

## string_xrefs

- `0x18015b439`: `DWM Token Thread`

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
0x18015b350  mov     [rsp+arg_0], rbx
0x18015b355  push    rdi
0x18015b356  sub     rsp, 30h
0x18015b35a  xor     r8d, r8d; unsigned int
0x18015b35d  mov     rdi, rcx
0x18015b360  cmp     [rcx+90h], r8b
0x18015b367  jz      short loc_18015B38F
0x18015b369  mov     ebx, 80004004h
0x18015b36e  mov     [rsp+38h+lpThreadId], r8; void *
0x18015b373  mov     r9d, ebx; int
0x18015b376  mov     [rsp+38h+dwCreationFlags], 20h ; ' '; unsigned int
0x18015b37e  xor     edx, edx; int *
0x18015b380  mov     ecx, 14h; unsigned int
0x18015b385  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18015b38a  jmp     loc_18015B45F
0x18015b38f  xor     r9d, r9d; lpName
0x18015b392  lea     rbx, [rcx+80h]
0x18015b399  xor     ecx, ecx; lpEventAttributes
0x18015b39b  lea     edx, [r9+1]; bManualReset
0x18015b39f  call    cs:__imp_CreateEventW
0x18015b3a5  mov     rdx, rax
0x18015b3a8  mov     rcx, rbx
0x18015b3ab  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18015b3b0  mov     rax, [rbx]
0x18015b3b3  xor     edx, edx; dwStackSize
0x18015b3b5  inc     rax
0x18015b3b8  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18015b3c1  test    rax, 0FFFFFFFFFFFFFFFEh
0x18015b3c7  jnz     short loc_18015B3DF
0x18015b3c9  mov     r9d, 8007000Eh
0x18015b3cf  mov     [rsp+38h+dwCreationFlags], 28h ; '('
0x18015b3d7  mov     ebx, r9d
0x18015b3da  xor     r8d, r8d
0x18015b3dd  jmp     short loc_18015B380
0x18015b3df  mov     r9, rdi; lpParameter
0x18015b3e2  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18015b3ea  lea     r8, ?s_TokenThreadMain@CGlobalSurfaceManager@@CAKPEAX@Z; lpStartAddress
0x18015b3f1  xor     ecx, ecx; lpThreadAttributes
0x18015b3f3  lea     rbx, [rdi+78h]
0x18015b3f7  call    cs:__imp_CreateThread
0x18015b3fd  mov     rdx, rax
0x18015b400  mov     rcx, rbx
0x18015b403  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18015b408  mov     rcx, [rbx]; hThread
0x18015b40b  lea     rax, [rcx+1]
0x18015b40f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18015b415  jnz     short loc_18015B439
0x18015b417  mov     r9d, 8007000Eh
0x18015b41d  mov     [rsp+38h+lpThreadId], 0
0x18015b426  mov     ebx, r9d
0x18015b429  mov     [rsp+38h+dwCreationFlags], 33h ; '3'
0x18015b431  xor     r8d, r8d
0x18015b434  jmp     loc_18015B37E
0x18015b439  lea     rdx, aDwmTokenThread; "DWM Token Thread"
0x18015b440  call    cs:__imp_SetThreadDescription
0x18015b446  mov     rcx, [rbx]; hThread
0x18015b449  mov     edx, 0Fh; nPriority
0x18015b44e  call    cs:__imp_SetThreadPriority
0x18015b454  mov     rcx, [rbx]; hThread
0x18015b457  call    cs:__imp_ResumeThread
0x18015b45d  xor     ebx, ebx
0x18015b45f  mov     eax, ebx
0x18015b461  mov     rbx, [rsp+38h+arg_0]
0x18015b466  add     rsp, 30h
0x18015b46a  pop     rdi
0x18015b46b  retn
```
