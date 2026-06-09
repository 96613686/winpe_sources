# CAPCThread::Initialize(void)

- ea: `0x140026170`
- end: `0x14002634f`
- name: `?Initialize@CAPCThread@@UEAAJXZ`
- size: `479`
- prototype: `__int64 __fastcall(CAPCThread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140025b50`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140026170`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400261f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400261f3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002632f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002632f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026292`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140026192`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140026192`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140026269`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140026269`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026318`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026318`

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
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
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
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
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
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
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
0x140026170  mov     [rsp+arg_0], rbx
0x140026175  mov     [rsp+arg_8], rsi
0x14002617a  push    rdi
0x14002617b  sub     rsp, 30h
0x14002617f  or      dword ptr [rcx+14h], 2
0x140026183  xor     r9d, r9d; lpName
0x140026186  mov     rdi, rcx
0x140026189  xor     r8d, r8d; bInitialState
0x14002618c  xor     ecx, ecx; lpEventAttributes
0x14002618e  lea     edx, [r9+1]; bManualReset
0x140026192  call    cs:__imp_CreateEventW
0x140026198  mov     [rdi+30h], rax
0x14002619c  test    rax, rax
0x14002619f  jnz     short loc_1400261E3
0x1400261a1  call    cs:__imp_GetLastError
0x1400261a7  mov     ebx, eax
0x1400261a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400261b0  lea     rax, WPP_GLOBAL_Control
0x1400261b7  cmp     rcx, rax
0x1400261ba  jz      loc_1400262E1
0x1400261c0  test    byte ptr [rcx+1Ch], 8
0x1400261c4  jz      loc_1400262E1
0x1400261ca  cmp     byte ptr [rcx+19h], 2
0x1400261ce  jb      loc_1400262E1
0x1400261d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400261d9  mov     edx, 0Dh
0x1400261de  jmp     loc_1400262C3
0x1400261e3  lea     r8, [rdi+38h]; phModule
0x1400261e7  mov     ecx, 4; dwFlags
0x1400261ec  lea     rdx, ?static_APC_thread@CAPCThread@@SAKPEAX@Z; lpModuleName
0x1400261f3  call    cs:__imp_GetModuleHandleExW
0x1400261f9  test    eax, eax
0x1400261fb  jnz     short loc_14002623F
0x1400261fd  call    cs:__imp_GetLastError
0x140026203  mov     ebx, eax
0x140026205  mov     rcx, cs:WPP_GLOBAL_Control
0x14002620c  lea     rax, WPP_GLOBAL_Control
0x140026213  cmp     rcx, rax
0x140026216  jz      loc_1400262E1
0x14002621c  test    byte ptr [rcx+1Ch], 8
0x140026220  jz      loc_1400262E1
0x140026226  cmp     byte ptr [rcx+19h], 2
0x14002622a  jb      loc_1400262E1
0x140026230  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140026235  mov     edx, 0Eh
0x14002623a  jmp     loc_1400262C3
0x14002623f  mov     rcx, [rdi+18h]
0x140026243  xor     ebx, ebx
0x140026245  mov     rax, [rcx]
0x140026248  mov     rax, [rax+8]
0x14002624c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026251  lea     r9, [rdi-10h]; lpParameter
0x140026255  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x14002625a  lea     r8, ?static_APC_thread@CAPCThread@@SAKPEAX@Z; lpStartAddress
0x140026261  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x140026265  xor     edx, edx; dwStackSize
0x140026267  xor     ecx, ecx; lpThreadAttributes
0x140026269  call    cs:__imp_CreateThread
0x14002626f  mov     [rdi+28h], rax
0x140026273  test    rax, rax
0x140026276  jnz     short loc_140026288
0x140026278  mov     rcx, [rdi+18h]
0x14002627c  mov     rax, [rcx]
0x14002627f  mov     rax, [rax+10h]
0x140026283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026288  cmp     [rdi+28h], rbx
0x14002628c  jnz     loc_14002633D
0x140026292  call    cs:__imp_GetLastError
0x140026298  mov     ebx, eax
0x14002629a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400262a1  lea     rax, WPP_GLOBAL_Control
0x1400262a8  cmp     rcx, rax
0x1400262ab  jz      short loc_1400262E1
0x1400262ad  test    byte ptr [rcx+1Ch], 8
0x1400262b1  jz      short loc_1400262E1
0x1400262b3  cmp     byte ptr [rcx+19h], 2
0x1400262b7  jb      short loc_1400262E1
0x1400262b9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400262be  mov     edx, 0Fh
0x1400262c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400262ca  lea     r8, WPP_e06d9da063383fc2b93c39ab877dcc3d_Traceguids
0x1400262d1  mov     r9d, eax
0x1400262d4  mov     [rsp+38h+dwCreationFlags], ebx
0x1400262d8  mov     rcx, [rcx+10h]
0x1400262dc  call    WPP_SF_Dd
0x1400262e1  test    ebx, ebx
0x1400262e3  jle     short loc_1400262F0
0x1400262e5  movzx   ebx, bx
0x1400262e8  or      ebx, 80070000h
0x1400262ee  test    ebx, ebx
0x1400262f0  mov     rcx, [rdi+30h]; hObject
0x1400262f4  mov     eax, 80004005h
0x1400262f9  cmovns  ebx, eax
0x1400262fc  test    rcx, rcx
0x1400262ff  jz      short loc_14002630F
0x140026301  call    cs:__imp_CloseHandle
0x140026307  mov     qword ptr [rdi+30h], 0
0x14002630f  mov     rcx, [rdi+28h]; hObject
0x140026313  test    rcx, rcx
0x140026316  jz      short loc_140026326
0x140026318  call    cs:__imp_CloseHandle
0x14002631e  mov     qword ptr [rdi+28h], 0
0x140026326  mov     rcx, [rdi+38h]; hLibModule
0x14002632a  test    rcx, rcx
0x14002632d  jz      short loc_14002633D
0x14002632f  call    cs:__imp_FreeLibrary
0x140026335  mov     qword ptr [rdi+38h], 0
0x14002633d  mov     rsi, [rsp+38h+arg_8]
0x140026342  mov     eax, ebx
0x140026344  mov     rbx, [rsp+38h+arg_0]
0x140026349  add     rsp, 30h
0x14002634d  pop     rdi
0x14002634e  retn
```
