# CreateOrPulseEvent(void * *,ushort *)

- ea: `0x140026874`
- end: `0x1400269e7`
- name: `?CreateOrPulseEvent@@YAHPEAPEAXPEAG@Z`
- size: `371`
- prototype: `__int64 __fastcall(void **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002c0a4`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x140026874`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140026963`
- `KERNEL32!SetEvent` at `0x140026963`
- `KERNEL32!CreateEventW` at `0x140026905`
- `KERNEL32!CreateEventW` at `0x140026905`
- `KERNEL32!CloseHandle` at `0x140026977`
- `KERNEL32!CloseHandle` at `0x140026977`
- `KERNEL32!GetLastError` at `0x140026921`
- `KERNEL32!GetLastError` at `0x140026931`
- `KERNEL32!GetLastError` at `0x14002694d`
- `KERNEL32!GetLastError` at `0x140026921`
- `KERNEL32!GetLastError` at `0x140026931`
- `KERNEL32!GetLastError` at `0x14002694d`

## string_xrefs

- `0x1400268cd`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140026990`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x1400268d4`: `CreateOrPulseEvent`
- `0x140026997`: `CreateOrPulseEvent`

## pseudocode

```c
_BOOL8 __fastcall CreateOrPulseEvent(void **a1, unsigned __int16 *a2)
{
  signed int v3; // eax
  CEventLogger *v4; // rcx
  HANDLE EventW; // rbx
  CEventLogger *v6; // rcx
  signed int LastError; // eax
  bool v8; // sf
  WCHAR Name[1024]; // [rsp+30h] [rbp-818h] BYREF

  memset_0(Name, 0, sizeof(Name));
  v3 = StringCchPrintfW(Name, 0x400u, L"Local\\%s", L"CANT_BE_NOVICE");
  if ( v3 < 0 )
  {
    EventW = 0;
    CEventLogger::LogError(
      v4,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x18A3u,
      L"CreateOrPulseEvent",
      v3);
    return EventW != 0;
  }
  EventW = CreateEventW(0, 0, 0, Name);
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v8 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v8 = LastError < 0;
      }
      if ( !v8 )
        goto LABEL_8;
    }
    else
    {
      LastError = -2147467259;
    }
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x18A6u,
      L"CreateOrPulseEvent",
      LastError);
    goto LABEL_13;
  }
LABEL_8:
  if ( GetLastError() == 183 )
  {
    SetEvent(EventW);
    if ( EventW )
    {
      CloseHandle(EventW);
      EventW = 0;
    }
    return EventW != 0;
  }
LABEL_13:
  if ( EventW )
    *a1 = EventW;
  return EventW != 0;
}

```

## disassembly

```asm
0x140026874  mov     [rsp+arg_8], rbx
0x140026879  push    rdi
0x14002687a  sub     rsp, 840h
0x140026881  mov     rax, cs:__security_cookie
0x140026888  xor     rax, rsp
0x14002688b  mov     [rsp+848h+var_18], rax
0x140026893  mov     rdi, rcx
0x140026896  xor     edx, edx; Val
0x140026898  lea     rcx, [rsp+848h+Name]; void *
0x14002689d  mov     r8d, 800h; Size
0x1400268a3  call    memset_0
0x1400268a8  lea     r9, aCantBeNovice; "CANT_BE_NOVICE"
0x1400268af  mov     edx, 400h; unsigned __int64
0x1400268b4  lea     r8, aLocalS; "Local\\%s"
0x1400268bb  lea     rcx, [rsp+848h+Name]; unsigned __int16 *
0x1400268c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400268c5  test    eax, eax
0x1400268c7  jns     short loc_1400268F9
0x1400268c9  mov     [rsp+848h+var_820], eax; unsigned int
0x1400268cd  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x1400268d4  lea     rax, aCreateorpulsee; "CreateOrPulseEvent"
0x1400268db  xor     ebx, ebx
0x1400268dd  mov     r9d, 18A3h; unsigned int
0x1400268e3  mov     [rsp+848h+var_828], rax; unsigned __int16 *
0x1400268e8  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400268ef  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400268f4  jmp     loc_1400269BD
0x1400268f9  lea     r9, [rsp+848h+Name]; lpName
0x1400268fe  xor     r8d, r8d; bInitialState
0x140026901  xor     edx, edx; bManualReset
0x140026903  xor     ecx, ecx; lpEventAttributes
0x140026905  call    cs:__imp_CreateEventW
0x14002690c  nop     dword ptr [rax+rax+00h]
0x140026911  mov     rbx, rax
0x140026914  lea     rcx, [rax+1]
0x140026918  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14002691f  jnz     short loc_14002694D
0x140026921  call    cs:__imp_GetLastError
0x140026928  nop     dword ptr [rax+rax+00h]
0x14002692d  test    eax, eax
0x14002692f  jz      short loc_140026987
0x140026931  call    cs:__imp_GetLastError
0x140026938  nop     dword ptr [rax+rax+00h]
0x14002693d  test    eax, eax
0x14002693f  jle     short loc_14002694B
0x140026941  movzx   eax, ax
0x140026944  or      eax, 80070000h
0x140026949  test    eax, eax
0x14002694b  js      short loc_14002698C
0x14002694d  call    cs:__imp_GetLastError
0x140026954  nop     dword ptr [rax+rax+00h]
0x140026959  cmp     eax, 0B7h
0x14002695e  jnz     short loc_1400269B5
0x140026960  mov     rcx, rbx; hEvent
0x140026963  call    cs:__imp_SetEvent
0x14002696a  nop     dword ptr [rax+rax+00h]
0x14002696f  test    rbx, rbx
0x140026972  jz      short loc_1400269BD
0x140026974  mov     rcx, rbx; hObject
0x140026977  call    cs:__imp_CloseHandle
0x14002697e  nop     dword ptr [rax+rax+00h]
0x140026983  xor     ebx, ebx
0x140026985  jmp     short loc_1400269BD
0x140026987  mov     eax, 80004005h
0x14002698c  mov     [rsp+848h+var_820], eax; unsigned int
0x140026990  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140026997  lea     rax, aCreateorpulsee; "CreateOrPulseEvent"
0x14002699e  mov     r9d, 18A6h; unsigned int
0x1400269a4  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400269ab  mov     [rsp+848h+var_828], rax; unsigned __int16 *
0x1400269b0  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400269b5  test    rbx, rbx
0x1400269b8  jz      short loc_1400269BD
0x1400269ba  mov     [rdi], rbx
0x1400269bd  xor     eax, eax
0x1400269bf  test    rbx, rbx
0x1400269c2  setnz   al
0x1400269c5  mov     rcx, [rsp+848h+var_18]
0x1400269cd  xor     rcx, rsp; StackCookie
0x1400269d0  call    __security_check_cookie
0x1400269d5  mov     rbx, [rsp+848h+arg_8]
0x1400269dd  add     rsp, 840h
0x1400269e4  pop     rdi
0x1400269e5  retn
```
