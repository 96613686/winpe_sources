# PushRouter::Initialize(ushort const *,ushort const *,_RTL_CRITICAL_SECTION *)

- ea: `0x180014dcc`
- end: `0x180014f78`
- name: `?Initialize@PushRouter@@AEAAJPEBG0PEAU_RTL_CRITICAL_SECTION@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(PushRouter *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180013f64`

## callees

- `0x180006090`
- `0x180014040`
- `0x180014dcc`
- `0x180015500`
- `0x18001b700`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180014f32`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180014f32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f44`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014e8a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014eaa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014e8a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014eaa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014ec5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014ec5`
- `DMCmnUtils!CopyString` at `0x180014deb`
- `DMCmnUtils!CopyString` at `0x180014e09`
- `DMCmnUtils!CopyString` at `0x180014deb`
- `DMCmnUtils!CopyString` at `0x180014e09`

## pseudocode

```c
__int64 __fastcall PushRouter::Initialize(
        PushRouter *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _RTL_CRITICAL_SECTION *a4)
{
  int ProgIDs; // ebx
  PushMsgAuthModule *v6; // rax
  HANDLE EventW; // rax
  HANDLE v8; // rax
  signed int LastError; // eax
  HANDLE Thread; // rax
  signed int v11; // eax

  ProgIDs = CopyString(a2, 0xFFFFFFFF, (unsigned __int16 **)this);
  if ( ProgIDs < 0 )
    goto LABEL_20;
  ProgIDs = CopyString(L"*.queue", 0xFFFFFFFF, (unsigned __int16 **)this + 1);
  if ( ProgIDs < 0 )
    goto LABEL_20;
  *((_QWORD *)this + 33) = &g_csPushRouter;
  v6 = (PushMsgAuthModule *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
  {
    *(_DWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = 0;
  }
  *((_QWORD *)this + 26) = v6;
  if ( !v6 )
  {
    ProgIDs = -2147024882;
    goto LABEL_20;
  }
  ProgIDs = PushMsgAuthModule::LoadProgIDs(v6);
  if ( ProgIDs < 0 )
    goto LABEL_20;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 22) = EventW;
  if ( !EventW )
    goto LABEL_19;
  v8 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 25) = v8;
  if ( !v8 )
    goto LABEL_19;
  if ( !CreateDirectoryW(*(LPCWSTR *)this, 0) )
  {
    LastError = GetLastError();
    ProgIDs = LastError;
    if ( LastError != 183 )
    {
      if ( LastError > 0 )
        ProgIDs = (unsigned __int16)LastError | 0x80070000;
      if ( ProgIDs < 0 )
        goto LABEL_20;
    }
  }
  ProgIDs = PushRouter::ProcessPersistedMessages(
              *(const unsigned __int16 **)this,
              *((const unsigned __int16 **)this + 1),
              this,
              0,
              0);
  if ( ProgIDs < 0 )
    goto LABEL_20;
  Thread = CreateThread(0, 0, PushRouter::RoutingThread, this, 0, (LPDWORD)this + 48);
  *((_QWORD *)this + 23) = Thread;
  if ( !Thread )
  {
LABEL_19:
    v11 = GetLastError();
    ProgIDs = v11;
    if ( v11 > 0 )
      ProgIDs = (unsigned __int16)v11 | 0x80070000;
    if ( ProgIDs < 0 )
LABEL_20:
      PushRouter::Deinitialize(this);
  }
  return (unsigned int)ProgIDs;
}

```

## disassembly

```asm
0x180014dcc  mov     [rsp+arg_0], rbx
0x180014dd1  mov     [rsp+arg_8], rdi
0x180014dd6  push    r14
0x180014dd8  sub     rsp, 30h
0x180014ddc  mov     rax, rdx
0x180014ddf  mov     rdi, rcx
0x180014de2  mov     r8, rcx
0x180014de5  or      edx, 0FFFFFFFFh
0x180014de8  mov     rcx, rax
0x180014deb  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180014df1  mov     ebx, eax
0x180014df3  test    eax, eax
0x180014df5  js      loc_180014F5D
0x180014dfb  lea     r8, [rdi+8]
0x180014dff  or      edx, 0FFFFFFFFh
0x180014e02  lea     rcx, ?c_szClientQueueVolumeName@@3QBGB; "*.queue"
0x180014e09  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180014e0f  mov     ebx, eax
0x180014e11  test    eax, eax
0x180014e13  js      loc_180014F5D
0x180014e19  lea     rax, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csPushRouter
0x180014e20  mov     ecx, 18h; unsigned __int64
0x180014e25  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014e2c  mov     [rdi+108h], rax
0x180014e33  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014e38  mov     [rsp+38h+arg_18], rax
0x180014e3d  test    rax, rax
0x180014e40  jz      short loc_180014E58
0x180014e42  mov     dword ptr [rax], 0
0x180014e48  mov     qword ptr [rax+8], 0
0x180014e50  mov     qword ptr [rax+10h], 0
0x180014e58  mov     [rdi+0D0h], rax
0x180014e5f  test    rax, rax
0x180014e62  jnz     short loc_180014E6E
0x180014e64  mov     ebx, 8007000Eh
0x180014e69  jmp     loc_180014F5D
0x180014e6e  mov     rcx, rax; this
0x180014e71  call    ?LoadProgIDs@PushMsgAuthModule@@AEAAJXZ; PushMsgAuthModule::LoadProgIDs(void)
0x180014e76  mov     ebx, eax
0x180014e78  test    eax, eax
0x180014e7a  js      loc_180014F5D
0x180014e80  xor     r9d, r9d; lpName
0x180014e83  xor     r8d, r8d; bInitialState
0x180014e86  xor     edx, edx; bManualReset
0x180014e88  xor     ecx, ecx; lpEventAttributes
0x180014e8a  call    cs:__imp_CreateEventW
0x180014e90  mov     [rdi+0B0h], rax
0x180014e97  test    rax, rax
0x180014e9a  jz      loc_180014F44
0x180014ea0  xor     r9d, r9d; lpName
0x180014ea3  xor     r8d, r8d; bInitialState
0x180014ea6  xor     edx, edx; bManualReset
0x180014ea8  xor     ecx, ecx; lpEventAttributes
0x180014eaa  call    cs:__imp_CreateEventW
0x180014eb0  mov     [rdi+0C8h], rax
0x180014eb7  test    rax, rax
0x180014eba  jz      loc_180014F44
0x180014ec0  mov     rcx, [rdi]; lpPathName
0x180014ec3  xor     edx, edx; lpSecurityAttributes
0x180014ec5  call    cs:__imp_CreateDirectoryW
0x180014ecb  test    eax, eax
0x180014ecd  jnz     short loc_180014EEF
0x180014ecf  call    cs:__imp_GetLastError
0x180014ed5  mov     ebx, eax
0x180014ed7  cmp     eax, 0B7h
0x180014edc  jz      short loc_180014EEF
0x180014ede  test    eax, eax
0x180014ee0  jle     short loc_180014EEB
0x180014ee2  movzx   ebx, ax
0x180014ee5  or      ebx, 80070000h
0x180014eeb  test    ebx, ebx
0x180014eed  js      short loc_180014F5D
0x180014eef  mov     rdx, [rdi+8]; unsigned __int16 *
0x180014ef3  xor     r9d, r9d; int
0x180014ef6  mov     rcx, [rdi]; unsigned __int16 *
0x180014ef9  mov     r8, rdi; struct PushRouter *
0x180014efc  mov     qword ptr [rsp+38h+dwCreationFlags], 0; int *
0x180014f05  call    ?ProcessPersistedMessages@PushRouter@@CAJPEBG0PEAV1@HPEAH@Z; PushRouter::ProcessPersistedMessages(ushort const *,ushort const *,PushRouter *,int,int *)
0x180014f0a  mov     ebx, eax
0x180014f0c  test    eax, eax
0x180014f0e  js      short loc_180014F5D
0x180014f10  lea     rax, [rdi+0C0h]
0x180014f17  mov     r9, rdi; lpParameter
0x180014f1a  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180014f1f  lea     r8, ?RoutingThread@PushRouter@@CAKPEAX@Z; lpStartAddress
0x180014f26  xor     edx, edx; dwStackSize
0x180014f28  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180014f30  xor     ecx, ecx; lpThreadAttributes
0x180014f32  call    cs:__imp_CreateThread
0x180014f38  mov     [rdi+0B8h], rax
0x180014f3f  test    rax, rax
0x180014f42  jnz     short loc_180014F65
0x180014f44  call    cs:__imp_GetLastError
0x180014f4a  mov     ebx, eax
0x180014f4c  test    eax, eax
0x180014f4e  jle     short loc_180014F59
0x180014f50  movzx   ebx, ax
0x180014f53  or      ebx, 80070000h
0x180014f59  test    ebx, ebx
0x180014f5b  jns     short loc_180014F65
0x180014f5d  mov     rcx, rdi; this
0x180014f60  call    ?Deinitialize@PushRouter@@AEAAJXZ; PushRouter::Deinitialize(void)
0x180014f65  mov     rdi, [rsp+38h+arg_8]
0x180014f6a  mov     eax, ebx
0x180014f6c  mov     rbx, [rsp+38h+arg_0]
0x180014f71  add     rsp, 30h
0x180014f75  pop     r14
0x180014f77  retn
```
