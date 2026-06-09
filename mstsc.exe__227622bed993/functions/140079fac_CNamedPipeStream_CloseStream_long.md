# CNamedPipeStream::CloseStream(long)

- ea: `0x140079fac`
- end: `0x14007a0c9`
- name: `?CloseStream@CNamedPipeStream@@AEAAJJ@Z`
- size: `285`
- prototype: `__int64 __fastcall(PVOID pv, int)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140079f50`
- `0x14007a0d0`
- `0x14007a3f4`
- `0x14007b1d0`
- `0x14007baf0`

## callees

- `0x140001940`
- `0x140059568`
- `0x140059b04`
- `0x140079fac`
- `0x140112010`

## import_xrefs

- `KERNEL32!CloseThreadpoolWork` at `0x14007a04f`
- `KERNEL32!CloseThreadpoolWork` at `0x14007a04f`
- `KERNEL32!SubmitThreadpoolWork` at `0x14007a046`
- `KERNEL32!SubmitThreadpoolWork` at `0x14007a046`
- `KERNEL32!CreateThreadpoolWork` at `0x14007a035`
- `KERNEL32!CreateThreadpoolWork` at `0x14007a035`
- `KERNEL32!DisconnectNamedPipe` at `0x140079feb`
- `KERNEL32!DisconnectNamedPipe` at `0x140079feb`
- `KERNEL32!CloseHandle` at `0x140079ff5`
- `KERNEL32!CloseHandle` at `0x140079ff5`
- `KERNEL32!GetLastError` at `0x14007a057`
- `KERNEL32!GetLastError` at `0x14007a057`

## string_xrefs

- `0x14007a077`: `CreateThreadpoolWork failed`

## pseudocode

```c
__int64 __fastcall CNamedPipeStream::CloseStream(char *pv, int a2)
{
  int v4; // edi
  void *v5; // rcx
  __int64 v6; // rcx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v8; // rdi
  signed int LastError; // eax
  int v10; // r8d
  int v11; // r9d
  unsigned int v12; // ecx
  char *v14; // [rsp+40h] [rbp+8h] BYREF
  const char *v15; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  v14 = pv + 80;
  CTSCriticalSection::Lock((CTSCriticalSection *)(pv + 80));
  if ( *((_DWORD *)pv + 24) )
  {
    v4 = 1;
    *((_DWORD *)pv + 24) = 0;
  }
  v5 = (void *)*((_QWORD *)pv + 7);
  if ( v5 != (void *)-1LL )
  {
    DisconnectNamedPipe(v5);
    CloseHandle(*((HANDLE *)pv + 7));
    *((_QWORD *)pv + 7) = -1;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v14);
  if ( v4 )
  {
    v6 = *((_QWORD *)pv + 5);
    *((_DWORD *)pv + 25) = a2;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    ThreadpoolWork = CreateThreadpoolWork(CNamedPipeStream::STATIC_OnCloseCallbackThreadProc, pv, 0);
    v8 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v8);
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_140150118 > 3 )
      {
        LODWORD(v14) = v12;
        v15 = "CreateThreadpoolWork failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)byte_14013F4C9,
          v10,
          v11,
          (__int64)&v15,
          (__int64)&v14);
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)pv + 5) + 16LL))(*((_QWORD *)pv + 5));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140079fac  mov     [rsp+arg_8], rbx
0x140079fb1  mov     [rsp+arg_18], rsi
0x140079fb6  push    rdi
0x140079fb7  sub     rsp, 30h
0x140079fbb  mov     rbx, rcx
0x140079fbe  mov     esi, edx
0x140079fc0  add     rcx, 50h ; 'P'; this
0x140079fc4  xor     edi, edi
0x140079fc6  mov     [rsp+38h+arg_0], rcx
0x140079fcb  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x140079fd0  cmp     [rbx+60h], edi
0x140079fd3  jz      short loc_140079FE1
0x140079fd5  mov     edi, 1
0x140079fda  mov     dword ptr [rbx+60h], 0
0x140079fe1  mov     rcx, [rbx+38h]; hNamedPipe
0x140079fe5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140079fe9  jz      short loc_14007A003
0x140079feb  call    cs:__imp_DisconnectNamedPipe
0x140079ff1  mov     rcx, [rbx+38h]; hObject
0x140079ff5  call    cs:__imp_CloseHandle
0x140079ffb  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x14007a003  lea     rcx, [rsp+38h+arg_0]; this
0x14007a008  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14007a00d  test    edi, edi
0x14007a00f  jz      loc_14007A0B7
0x14007a015  mov     rcx, [rbx+28h]
0x14007a019  mov     [rbx+64h], esi
0x14007a01c  mov     rax, [rcx]
0x14007a01f  mov     rax, [rax+8]
0x14007a023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a028  xor     r8d, r8d; pcbe
0x14007a02b  lea     rcx, ?STATIC_OnCloseCallbackThreadProc@CNamedPipeStream@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14007a032  mov     rdx, rbx; pv
0x14007a035  call    cs:__imp_CreateThreadpoolWork
0x14007a03b  mov     rdi, rax
0x14007a03e  test    rax, rax
0x14007a041  jz      short loc_14007A057
0x14007a043  mov     rcx, rax; pwk
0x14007a046  call    cs:__imp_SubmitThreadpoolWork
0x14007a04c  mov     rcx, rdi; pwk
0x14007a04f  call    cs:__imp_CloseThreadpoolWork
0x14007a055  jmp     short loc_14007A0B7
0x14007a057  call    cs:__imp_GetLastError
0x14007a05d  mov     ecx, eax
0x14007a05f  test    eax, eax
0x14007a061  jle     short loc_14007A06C
0x14007a063  movzx   ecx, ax
0x14007a066  or      ecx, 80070000h
0x14007a06c  mov     eax, cs:dword_140150118
0x14007a072  cmp     eax, 3
0x14007a075  jbe     short loc_14007A0A7
0x14007a077  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x14007a07e  mov     dword ptr [rsp+38h+arg_0], ecx
0x14007a082  mov     [rsp+38h+arg_10], rax
0x14007a087  lea     rdx, byte_14013F4C9
0x14007a08e  lea     rax, [rsp+38h+arg_0]
0x14007a093  mov     [rsp+38h+var_10], rax
0x14007a098  lea     rax, [rsp+38h+arg_10]
0x14007a09d  mov     [rsp+38h+var_18], rax
0x14007a0a2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14007a0a7  mov     rcx, [rbx+28h]
0x14007a0ab  mov     rax, [rcx]
0x14007a0ae  mov     rax, [rax+10h]
0x14007a0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a0b7  mov     rbx, [rsp+38h+arg_8]
0x14007a0bc  xor     eax, eax
0x14007a0be  mov     rsi, [rsp+38h+arg_18]
0x14007a0c3  add     rsp, 30h
0x14007a0c7  pop     rdi
0x14007a0c8  retn
```
