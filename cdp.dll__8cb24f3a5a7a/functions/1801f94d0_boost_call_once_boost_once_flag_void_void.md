# boost::call_once(boost::once_flag &,void (*)(void))

- ea: `0x1801f94d0`
- end: `0x1801f96eb`
- name: `?call_once@boost@@YAXAEAUonce_flag@1@P6AXXZ@Z`
- size: `539`
- prototype: `void __fastcall(struct boost::once_flag *, void (*)(void))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801f9c90`

## callees

- `0x1801f6fb0`
- `0x1801f94d0`
- `0x1801f9a20`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801f95f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801f96aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801f95f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801f96aa`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x1801f9569`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x1801f9569`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1801f96df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1801f96df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801f9622`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801f9622`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801f9594`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801f9594`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f9581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f9608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f963a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f96c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f9581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f9608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f963a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f96c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall boost::call_once(struct boost::once_flag *a1, void (*a2)(void), void *a3)
{
  HANDLE v5; // rdi
  struct boost::detail::once_context *v6; // r8
  char *v7; // rdi
  HANDLE v8; // rcx
  HANDLE EventA; // rdi
  __int32 v11; // [rsp+30h] [rbp-88h] BYREF
  signed __int32 v12; // [rsp+34h] [rbp-84h]
  char v13; // [rsp+38h] [rbp-80h]
  HANDLE hObject; // [rsp+40h] [rbp-78h]
  CHAR Name[88]; // [rsp+48h] [rbp-70h] BYREF

  v11 = -1051250462;
  v12 = 2131174883;
  v13 = 0;
  hObject = 0;
  Name[0] = 0;
  while ( 1 )
  {
    if ( *(_DWORD *)a1 == v11 )
      goto LABEL_23;
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)a1, v12, 0) )
      break;
    if ( v13 )
    {
      v8 = hObject;
      goto LABEL_36;
    }
    _InterlockedIncrement((volatile signed __int32 *)a1 + 1);
    v13 = 1;
    if ( *(_DWORD *)a1 == v11 )
      goto LABEL_23;
    v8 = hObject;
    if ( hObject )
    {
LABEL_36:
      WaitForSingleObjectEx(v8, 0xFFFFFFFF, 0);
    }
    else
    {
      if ( !Name[0] )
        boost::detail::name_once_mutex((boost::detail *)Name, (char *)a1, a3);
      EventA = CreateEventA(0, 1, 0, Name);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      hObject = EventA;
    }
  }
  v5 = hObject;
  if ( hObject )
    goto LABEL_10;
  if ( !Name[0] )
    boost::detail::name_once_mutex((boost::detail *)Name, (char *)a1, a3);
  v5 = OpenEventA(0x100002u, 0, Name);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  hObject = v5;
  if ( v5 )
LABEL_10:
    ResetEvent(v5);
  try
  {
    a2();
    if ( !v13 )
    {
      _InterlockedIncrement((volatile signed __int32 *)a1 + 1);
      v13 = 1;
    }
  }
  catch ( ... )
  {
    boost::detail::rollback_once_region(a1, (struct boost::once_flag *)&v11, v6);
    throw;
  }
  _InterlockedExchange((volatile __int32 *)a1, v11);
  v7 = (char *)hObject;
  if ( hObject )
    goto LABEL_22;
  if ( *((int *)a1 + 1) <= 1 )
  {
    v7 = (char *)hObject;
  }
  else
  {
    if ( Name[0] == (_BYTE)hObject )
      boost::detail::name_once_mutex((boost::detail *)Name, (char *)a1, v6);
    v7 = (char *)CreateEventA(0, 1, 0, Name);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    hObject = v7;
  }
  if ( v7 )
  {
LABEL_22:
    SetEvent(v7);
LABEL_23:
    v7 = (char *)hObject;
  }
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
}

```

## disassembly

```asm
0x1801f94d0  mov     [rsp+arg_10], rbx
0x1801f94d5  mov     [rsp+arg_18], rsi
0x1801f94da  push    rdi
0x1801f94db  sub     rsp, 0B0h
0x1801f94e2  mov     rax, cs:__security_cookie
0x1801f94e9  xor     rax, rsp
0x1801f94ec  mov     [rsp+0B8h+var_18], rax
0x1801f94f4  mov     rsi, rdx
0x1801f94f7  mov     rbx, rcx
0x1801f94fa  mov     [rsp+0B8h+var_90], rcx
0x1801f94ff  mov     [rsp+0B8h+var_88], 0C15730E2h
0x1801f9507  mov     [rsp+0B8h+var_84], 7F0725E3h
0x1801f950f  mov     [rsp+0B8h+var_80], 0
0x1801f9514  mov     [rsp+0B8h+hObject], 0
0x1801f951d  mov     [rsp+0B8h+Name], 0
0x1801f9522  mov     eax, [rbx]
0x1801f9524  nop
0x1801f9525  cmp     eax, [rsp+0B8h+var_88]
0x1801f9529  jz      loc_1801F9628
0x1801f952f  mov     ecx, [rsp+0B8h+var_84]
0x1801f9533  xor     eax, eax
0x1801f9535  lock cmpxchg [rbx], ecx
0x1801f9539  jnz     loc_1801F9665
0x1801f953f  mov     rdi, [rsp+0B8h+hObject]
0x1801f9544  test    rdi, rdi
0x1801f9547  jnz     short loc_1801F9591
0x1801f9549  cmp     [rsp+0B8h+Name], dil
0x1801f954e  jnz     short loc_1801F955D
0x1801f9550  mov     rdx, rbx; char *
0x1801f9553  lea     rcx, [rsp+0B8h+Name]; this
0x1801f9558  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x1801f955d  lea     r8, [rsp+0B8h+Name]; lpName
0x1801f9562  xor     edx, edx; bInheritHandle
0x1801f9564  mov     ecx, 100002h; dwDesiredAccess
0x1801f9569  call    cs:__imp_OpenEventA
0x1801f956f  mov     rdi, rax
0x1801f9572  mov     rcx, [rsp+0B8h+hObject]; hObject
0x1801f9577  lea     rax, [rcx-1]
0x1801f957b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f957f  ja      short loc_1801F9587
0x1801f9581  call    cs:__imp_CloseHandle
0x1801f9587  mov     [rsp+0B8h+hObject], rdi
0x1801f958c  test    rdi, rdi
0x1801f958f  jz      short loc_1801F959B
0x1801f9591  mov     rcx, rdi; hEvent
0x1801f9594  call    cs:__imp_ResetEvent
0x1801f959a  nop
0x1801f959b  mov     rax, rsi
0x1801f959e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f95a3  nop
0x1801f95a4  cmp     [rsp+0B8h+var_80], 0
0x1801f95a9  jnz     short loc_1801F95B4
0x1801f95ab  lock inc dword ptr [rbx+4]
0x1801f95af  mov     [rsp+0B8h+var_80], 1
0x1801f95b4  mov     eax, [rsp+0B8h+var_88]
0x1801f95b8  xchg    eax, [rbx]
0x1801f95ba  mov     rdi, [rsp+0B8h+hObject]
0x1801f95bf  test    rdi, rdi
0x1801f95c2  jnz     short loc_1801F961F
0x1801f95c4  mov     eax, [rbx+4]
0x1801f95c7  nop
0x1801f95c8  cmp     eax, 1
0x1801f95cb  jle     short loc_1801F9615
0x1801f95cd  cmp     [rsp+0B8h+Name], dil
0x1801f95d2  jnz     short loc_1801F95E1
0x1801f95d4  mov     rdx, rbx; char *
0x1801f95d7  lea     rcx, [rsp+0B8h+Name]; this
0x1801f95dc  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x1801f95e1  lea     r9, [rsp+0B8h+Name]; lpName
0x1801f95e6  xor     r8d, r8d; bInitialState
0x1801f95e9  mov     edx, 1; bManualReset
0x1801f95ee  xor     ecx, ecx; lpEventAttributes
0x1801f95f0  call    cs:__imp_CreateEventA
0x1801f95f6  mov     rdi, rax
0x1801f95f9  mov     rcx, [rsp+0B8h+hObject]; hObject
0x1801f95fe  lea     rax, [rcx-1]
0x1801f9602  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f9606  ja      short loc_1801F960E
0x1801f9608  call    cs:__imp_CloseHandle
0x1801f960e  mov     [rsp+0B8h+hObject], rdi
0x1801f9613  jmp     short loc_1801F961A
0x1801f9615  mov     rdi, [rsp+0B8h+hObject]
0x1801f961a  test    rdi, rdi
0x1801f961d  jz      short loc_1801F962D
0x1801f961f  mov     rcx, rdi; hEvent
0x1801f9622  call    cs:__imp_SetEvent
0x1801f9628  mov     rdi, [rsp+0B8h+hObject]
0x1801f962d  lea     rax, [rdi-1]
0x1801f9631  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f9635  ja      short loc_1801F9640
0x1801f9637  mov     rcx, rdi; hObject
0x1801f963a  call    cs:__imp_CloseHandle
0x1801f9640  mov     rcx, [rsp+0B8h+var_18]
0x1801f9648  xor     rcx, rsp; StackCookie
0x1801f964b  call    __security_check_cookie
0x1801f9650  lea     r11, [rsp+0B8h+var_8]
0x1801f9658  mov     rbx, [r11+20h]
0x1801f965c  mov     rsi, [r11+28h]
0x1801f9660  mov     rsp, r11
0x1801f9663  pop     rdi
0x1801f9664  retn
0x1801f9665  cmp     [rsp+0B8h+var_80], 0
0x1801f966a  jnz     short loc_1801F96D2
0x1801f966c  lock inc dword ptr [rbx+4]
0x1801f9670  mov     [rsp+0B8h+var_80], 1
0x1801f9675  mov     eax, [rbx]
0x1801f9677  nop
0x1801f9678  cmp     eax, [rsp+0B8h+var_88]
0x1801f967c  jz      short loc_1801F9628
0x1801f967e  mov     rcx, [rsp+0B8h+hObject]
0x1801f9683  test    rcx, rcx
0x1801f9686  jnz     short loc_1801F96D7
0x1801f9688  cmp     [rsp+0B8h+Name], cl
0x1801f968c  jnz     short loc_1801F969B
0x1801f968e  mov     rdx, rbx; char *
0x1801f9691  lea     rcx, [rsp+0B8h+Name]; this
0x1801f9696  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x1801f969b  lea     r9, [rsp+0B8h+Name]; lpName
0x1801f96a0  xor     r8d, r8d; bInitialState
0x1801f96a3  mov     edx, 1; bManualReset
0x1801f96a8  xor     ecx, ecx; lpEventAttributes
0x1801f96aa  call    cs:__imp_CreateEventA
0x1801f96b0  mov     rdi, rax
0x1801f96b3  mov     rcx, [rsp+0B8h+hObject]; hObject
0x1801f96b8  lea     rdx, [rcx-1]
0x1801f96bc  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801f96c0  ja      short loc_1801F96C8
0x1801f96c2  call    cs:__imp_CloseHandle
0x1801f96c8  mov     [rsp+0B8h+hObject], rdi
0x1801f96cd  jmp     loc_1801F9522
0x1801f96d2  mov     rcx, [rsp+0B8h+hObject]; hHandle
0x1801f96d7  xor     r8d, r8d; bAlertable
0x1801f96da  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1801f96df  call    cs:__imp_WaitForSingleObjectEx
0x1801f96e5  jmp     loc_1801F9522
```
