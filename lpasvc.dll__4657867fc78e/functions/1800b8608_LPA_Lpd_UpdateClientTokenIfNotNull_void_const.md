# LPA::Lpd::UpdateClientTokenIfNotNull(void * const *)

- ea: `0x1800b8608`
- end: `0x1800b8830`
- name: `?UpdateClientTokenIfNotNull@Lpd@LPA@@AEAAXPEBQEAX@Z`
- size: `552`
- prototype: `void __fastcall(LPA::Lpd *__hidden this, void *const *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x1800b7990`
- `0x1800b7c90`

## callees

- `0x1800056e4`
- `0x180006448`
- `0x180006530`
- `0x1800b12cc`
- `0x1800b8608`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8678`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b8637`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b8643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b8637`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b8643`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b866e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b866e`

## string_xrefs

- `0x1800b86a5`: `LpaServiceLpd`
- `0x1800b8741`: `LpaServiceLpd`
- `0x1800b87af`: `LpaServiceLpd`
- `0x1800b87fa`: `LpaServiceLpd`
- `0x1800b869a`: `LPA::Lpd::UpdateClientTokenIfNotNull`
- `0x1800b8736`: `LPA::Lpd::UpdateClientTokenIfNotNull`
- `0x1800b87a4`: `LPA::Lpd::UpdateClientTokenIfNotNull`
- `0x1800b87ef`: `LPA::Lpd::UpdateClientTokenIfNotNull`

## pseudocode

```c
void __fastcall LPA::Lpd::UpdateClientTokenIfNotNull(LPA::Lpd *this, void **a2, int a3, int a4)
{
  HANDLE CurrentProcess; // rax
  void *v7; // rdi
  void *v8; // rbx
  HANDLE v9; // rax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  DWORD LastError; // eax
  int v14; // r8d
  int v15; // r9d
  const char *v16; // rcx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  const char *v20; // [rsp+50h] [rbp-20h] BYREF
  const char *v21; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+38h] BYREF
  HANDLE TargetHandle; // [rsp+B0h] [rbp+40h] BYREF
  const char *v25; // [rsp+B8h] [rbp+48h] BYREF

  if ( a2 && *a2 )
  {
    TargetHandle = 0;
    CurrentProcess = GetCurrentProcess();
    v7 = *a2;
    v8 = CurrentProcess;
    v9 = GetCurrentProcess();
    if ( DuplicateHandle(v9, v7, v8, &TargetHandle, 0, 0, 2u) )
    {
      if ( *((HANDLE *)this + 18) == TargetHandle )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v23 = *((_QWORD *)this + 18);
          v25 = "LPA::Lpd::UpdateClientTokenIfNotNull";
          v22[0] = "LpaServiceLpd";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v10,
            (unsigned int)word_18013020A,
            v11,
            v12,
            (__int64)v22,
            (__int64)&v25,
            (__int64)&v23);
        }
      }
      else
      {
        LPA::Lpd::InvalidateClientToken(this);
        *((_QWORD *)this + 18) = TargetHandle;
        if ( (unsigned int)CallbackContext > 4 )
        {
          v23 = *((_QWORD *)this + 18);
          v25 = (const char *)TargetHandle;
          v21 = (const char *)*a2;
          v20 = "LPA::Lpd::UpdateClientTokenIfNotNull";
          v22[0] = "LpaServiceLpd";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v17,
            (unsigned int)word_1801302DA,
            v18,
            v19,
            (__int64)v22,
            (__int64)&v20,
            (__int64)&v21,
            (__int64)&v25,
            (__int64)&v23);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( (unsigned int)CallbackContext > 2 )
      {
        v16 = (const char *)*a2;
        LODWORD(v23) = LastError;
        v20 = "LPA::Lpd::UpdateClientTokenIfNotNull";
        v21 = "LpaServiceLpd";
        v25 = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (_DWORD)v16,
          (unsigned int)&byte_18013028F,
          v14,
          v15,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)&v23,
          (__int64)&v25);
      }
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v23 = *((_QWORD *)this + 18);
    TargetHandle = "LPA::Lpd::UpdateClientTokenIfNotNull";
    v25 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)this,
      (unsigned int)byte_18013024B,
      a3,
      a4,
      (__int64)&v25,
      (__int64)&TargetHandle,
      (__int64)&v23);
  }
}

```

## disassembly

```asm
0x1800b8608  push    rbp
0x1800b860a  push    rbx
0x1800b860b  push    rsi
0x1800b860c  push    rdi
0x1800b860d  push    r14
0x1800b860f  mov     rbp, rsp
0x1800b8612  sub     rsp, 70h
0x1800b8616  mov     r14, rdx
0x1800b8619  mov     rsi, rcx
0x1800b861c  test    rdx, rdx
0x1800b861f  jz      loc_1800B87D2
0x1800b8625  cmp     qword ptr [rdx], 0
0x1800b8629  jz      loc_1800B87D2
0x1800b862f  mov     [rbp+TargetHandle], 0
0x1800b8637  call    cs:__imp_GetCurrentProcess
0x1800b863d  mov     rdi, [r14]
0x1800b8640  mov     rbx, rax
0x1800b8643  call    cs:__imp_GetCurrentProcess
0x1800b8649  mov     [rsp+70h+dwOptions], 2; dwOptions
0x1800b8651  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x1800b8655  mov     rcx, rax; hSourceProcessHandle
0x1800b8658  mov     [rsp+70h+bInheritHandle], 0; bInheritHandle
0x1800b8660  mov     r8, rbx; hTargetProcessHandle
0x1800b8663  mov     [rsp+70h+dwDesiredAccess], 0; dwDesiredAccess
0x1800b866b  mov     rdx, rdi; hSourceHandle
0x1800b866e  call    cs:__imp_DuplicateHandle
0x1800b8674  test    eax, eax
0x1800b8676  jnz     short loc_1800B86E2
0x1800b8678  call    cs:__imp_GetLastError
0x1800b867e  mov     ecx, cs:CallbackContext
0x1800b8684  cmp     ecx, 2
0x1800b8687  jbe     loc_1800B8825
0x1800b868d  mov     rcx, [r14]
0x1800b8690  lea     rdx, byte_18013028F
0x1800b8697  mov     dword ptr [rbp+arg_8], eax
0x1800b869a  lea     rax, aLpaLpdUpdatecl; "LPA::Lpd::UpdateClientTokenIfNotNull"
0x1800b86a1  mov     [rbp+var_20], rax
0x1800b86a5  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b86ac  mov     [rbp+var_18], rax
0x1800b86b0  lea     rax, [rbp+arg_18]
0x1800b86b4  mov     [rsp+70h+var_38], rax
0x1800b86b9  lea     rax, [rbp+arg_8]
0x1800b86bd  mov     qword ptr [rsp+70h+dwOptions], rax
0x1800b86c2  lea     rax, [rbp+var_20]
0x1800b86c6  mov     qword ptr [rsp+70h+bInheritHandle], rax
0x1800b86cb  lea     rax, [rbp+var_18]
0x1800b86cf  mov     qword ptr [rsp+70h+dwDesiredAccess], rax
0x1800b86d4  mov     [rbp+arg_18], rcx
0x1800b86d8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800b86dd  jmp     loc_1800B8825
0x1800b86e2  mov     rax, [rbp+TargetHandle]
0x1800b86e6  cmp     [rsi+90h], rax
0x1800b86ed  jz      loc_1800B8783
0x1800b86f3  mov     rcx, rsi; this
0x1800b86f6  call    ?InvalidateClientToken@Lpd@LPA@@QEAAXXZ; LPA::Lpd::InvalidateClientToken(void)
0x1800b86fb  mov     rax, [rbp+TargetHandle]
0x1800b86ff  mov     [rsi+90h], rax
0x1800b8706  mov     eax, cs:CallbackContext
0x1800b870c  cmp     eax, 4
0x1800b870f  jbe     loc_1800B8825
0x1800b8715  mov     rax, [rsi+90h]
0x1800b871c  lea     rdx, word_1801302DA
0x1800b8723  mov     [rbp+arg_8], rax
0x1800b8727  mov     rax, [rbp+TargetHandle]
0x1800b872b  mov     [rbp+arg_18], rax
0x1800b872f  mov     rax, [r14]
0x1800b8732  mov     [rbp+var_18], rax
0x1800b8736  lea     rax, aLpaLpdUpdatecl; "LPA::Lpd::UpdateClientTokenIfNotNull"
0x1800b873d  mov     [rbp+var_20], rax
0x1800b8741  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b8748  mov     [rbp+var_10], rax
0x1800b874c  lea     rax, [rbp+arg_8]
0x1800b8750  mov     [rsp+70h+var_30], rax
0x1800b8755  lea     rax, [rbp+arg_18]
0x1800b8759  mov     [rsp+70h+var_38], rax
0x1800b875e  lea     rax, [rbp+var_18]
0x1800b8762  mov     qword ptr [rsp+70h+dwOptions], rax
0x1800b8767  lea     rax, [rbp+var_20]
0x1800b876b  mov     qword ptr [rsp+70h+bInheritHandle], rax
0x1800b8770  lea     rax, [rbp+var_10]
0x1800b8774  mov     qword ptr [rsp+70h+dwDesiredAccess], rax
0x1800b8779  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800b877e  jmp     loc_1800B8825
0x1800b8783  mov     eax, cs:CallbackContext
0x1800b8789  cmp     eax, 4
0x1800b878c  jbe     loc_1800B8825
0x1800b8792  mov     rax, [rsi+90h]
0x1800b8799  lea     rdx, word_18013020A
0x1800b87a0  mov     [rbp+arg_8], rax
0x1800b87a4  lea     rax, aLpaLpdUpdatecl; "LPA::Lpd::UpdateClientTokenIfNotNull"
0x1800b87ab  mov     [rbp+arg_18], rax
0x1800b87af  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b87b6  mov     [rbp+var_10], rax
0x1800b87ba  lea     rax, [rbp+arg_8]
0x1800b87be  mov     qword ptr [rsp+70h+dwOptions], rax
0x1800b87c3  lea     rax, [rbp+arg_18]
0x1800b87c7  mov     qword ptr [rsp+70h+bInheritHandle], rax
0x1800b87cc  lea     rax, [rbp+var_10]
0x1800b87d0  jmp     short loc_1800B881B
0x1800b87d2  mov     eax, cs:CallbackContext
0x1800b87d8  cmp     eax, 4
0x1800b87db  jbe     short loc_1800B8825
0x1800b87dd  mov     rax, [rcx+90h]
0x1800b87e4  lea     rdx, byte_18013024B
0x1800b87eb  mov     [rbp+arg_8], rax
0x1800b87ef  lea     rax, aLpaLpdUpdatecl; "LPA::Lpd::UpdateClientTokenIfNotNull"
0x1800b87f6  mov     [rbp+TargetHandle], rax
0x1800b87fa  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b8801  mov     [rbp+arg_18], rax
0x1800b8805  lea     rax, [rbp+arg_8]
0x1800b8809  mov     qword ptr [rsp+70h+dwOptions], rax
0x1800b880e  lea     rax, [rbp+TargetHandle]
0x1800b8812  mov     qword ptr [rsp+70h+bInheritHandle], rax
0x1800b8817  lea     rax, [rbp+arg_18]
0x1800b881b  mov     qword ptr [rsp+70h+dwDesiredAccess], rax
0x1800b8820  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800b8825  add     rsp, 70h
0x1800b8829  pop     r14
0x1800b882b  pop     rdi
0x1800b882c  pop     rsi
0x1800b882d  pop     rbx
0x1800b882e  pop     rbp
0x1800b882f  retn
```
