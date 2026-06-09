# CSpWmiDataHandle::_UnRegisterIndications(void)

- ea: `0x18005d41c`
- end: `0x18005d611`
- name: `?_UnRegisterIndications@CSpWmiDataHandle@@AEAAXXZ`
- size: `501`
- prototype: `void __fastcall(CSpWmiDataHandle *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180056290`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x18005d41c`
- `0x18005db6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d4df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d4df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005d4b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005d4b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005d4cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005d4cf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005d4ff`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005d521`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005d4ff`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005d521`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005d54e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005d5c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005d54e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005d5c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d4a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d4a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d478`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d536`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d536`

## pseudocode

```c
void __fastcall CSpWmiDataHandle::_UnRegisterIndications(CSpWmiDataHandle *this, __int64 a2, int a3, int a4)
{
  BOOL v5; // edi
  int v6; // r8d
  int v7; // r9d
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  MI_CancellationReason v10; // edx
  DWORD v11; // ecx
  int *v12; // rdx
  void *v13; // rcx
  int v14; // [rsp+70h] [rbp+30h] BYREF
  const char *v15; // [rsp+78h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+40h] BYREF
  const char *v17; // [rsp+88h] [rbp+48h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v14 = 1603;
    v15 = "CSpWmiDataHandle::_UnRegisterIndications";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_18030E495,
      a3,
      a4,
      (__int64)&v15,
      (__int64)&v14);
  }
  v5 = 0;
  TokenHandle = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 24);
  if ( *((_DWORD *)this + 88) )
    v5 = *((_DWORD *)this + 89) == 0;
  *((_DWORD *)this + 89) = 1;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 24);
  if ( v5 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle) || (LastError = GetLastError()) == 0 || LastError == 1008 )
    {
      if ( SetThreadToken(0, *((HANDLE *)this + 41)) )
      {
        MI_Operation_Cancel((MI_Operation *)((char *)this + 304), v10);
        SetThreadToken(0, TokenHandle);
      }
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    v11 = WaitForSingleObject(*((HANDLE *)this + 43), 0x7530u);
    if ( v11 )
    {
      if ( v11 == 122 )
      {
        if ( (unsigned int)dword_18039EB68 <= 3 )
          goto LABEL_20;
        v14 = 122;
        v12 = (int *)&byte_18030EF57;
      }
      else
      {
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_20;
        v14 = v11;
        v12 = &dword_18031046C;
      }
      LODWORD(v15) = 1681;
      v17 = "CSpWmiDataHandle::_UnRegisterIndications";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (_DWORD)v12,
        v6,
        v7,
        (__int64)&v17,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
LABEL_20:
  v13 = (void *)*((_QWORD *)this + 46);
  if ( v13 )
    WaitForSingleObject(v13, 0xFFFFFFFF);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v14 = 1692;
    v15 = "CSpWmiDataHandle::_UnRegisterIndications";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v13,
      (unsigned int)byte_18030DF85,
      v6,
      v7,
      (__int64)&v15,
      (__int64)&v14);
  }
}

```

## disassembly

```asm
0x18005d41c  push    rbp
0x18005d41e  push    rbx
0x18005d41f  push    rsi
0x18005d420  push    rdi
0x18005d421  push    r15
0x18005d423  mov     rbp, rsp
0x18005d426  sub     rsp, 40h
0x18005d42a  mov     eax, cs:dword_18039EB68
0x18005d430  lea     r15, aCspwmidatahand; "CSpWmiDataHandle::_UnRegisterIndication"...
0x18005d437  mov     rbx, rcx
0x18005d43a  cmp     eax, 5
0x18005d43d  jbe     short loc_18005D468
0x18005d43f  lea     rax, [rbp+arg_0]
0x18005d443  mov     [rbp+arg_0], 643h
0x18005d44a  mov     [rsp+40h+var_18], rax
0x18005d44f  lea     rdx, byte_18030E495
0x18005d456  lea     rax, [rbp+arg_8]
0x18005d45a  mov     [rbp+arg_8], r15
0x18005d45e  mov     [rsp+40h+var_20], rax
0x18005d463  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005d468  lea     rsi, [rbx+0C0h]
0x18005d46f  xor     edi, edi
0x18005d471  mov     rcx, rsi; SRWLock
0x18005d474  mov     [rbp+TokenHandle], rdi
0x18005d478  call    cs:__imp_AcquireSRWLockExclusive
0x18005d47f  nop     dword ptr [rax+rax+00h]
0x18005d484  lea     eax, [rdi+1]
0x18005d487  cmp     [rbx+160h], edi
0x18005d48d  jz      short loc_18005D498
0x18005d48f  cmp     [rbx+164h], edi
0x18005d495  cmovz   edi, eax
0x18005d498  mov     rcx, rsi; SRWLock
0x18005d49b  mov     [rbx+164h], eax
0x18005d4a1  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d4a8  nop     dword ptr [rax+rax+00h]
0x18005d4ad  test    edi, edi
0x18005d4af  jz      loc_18005D5B6
0x18005d4b5  call    cs:__imp_GetCurrentThread
0x18005d4bc  nop     dword ptr [rax+rax+00h]
0x18005d4c1  xor     r8d, r8d; OpenAsSelf
0x18005d4c4  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18005d4c8  mov     rcx, rax; ThreadHandle
0x18005d4cb  lea     edx, [r8+0Ch]; DesiredAccess
0x18005d4cf  call    cs:__imp_OpenThreadToken
0x18005d4d6  nop     dword ptr [rax+rax+00h]
0x18005d4db  test    eax, eax
0x18005d4dd  jnz     short loc_18005D4F6
0x18005d4df  call    cs:__imp_GetLastError
0x18005d4e6  nop     dword ptr [rax+rax+00h]
0x18005d4eb  test    eax, eax
0x18005d4ed  jz      short loc_18005D4F6
0x18005d4ef  cmp     eax, 3F0h
0x18005d4f4  jnz     short loc_18005D52D
0x18005d4f6  mov     rdx, [rbx+148h]; Token
0x18005d4fd  xor     ecx, ecx; Thread
0x18005d4ff  call    cs:__imp_SetThreadToken
0x18005d506  nop     dword ptr [rax+rax+00h]
0x18005d50b  test    eax, eax
0x18005d50d  jz      short loc_18005D52D
0x18005d50f  lea     rcx, [rbx+130h]; operation
0x18005d516  call    MI_Operation_Cancel
0x18005d51b  mov     rdx, [rbp+TokenHandle]; Token
0x18005d51f  xor     ecx, ecx; Thread
0x18005d521  call    cs:__imp_SetThreadToken
0x18005d528  nop     dword ptr [rax+rax+00h]
0x18005d52d  mov     rcx, [rbp+TokenHandle]; hObject
0x18005d531  test    rcx, rcx
0x18005d534  jz      short loc_18005D542
0x18005d536  call    cs:__imp_CloseHandle
0x18005d53d  nop     dword ptr [rax+rax+00h]
0x18005d542  mov     rcx, [rbx+158h]; hHandle
0x18005d549  mov     edx, 7530h; dwMilliseconds
0x18005d54e  call    cs:__imp_WaitForSingleObject
0x18005d555  nop     dword ptr [rax+rax+00h]
0x18005d55a  mov     ecx, eax
0x18005d55c  test    eax, eax
0x18005d55e  jz      short loc_18005D5B6
0x18005d560  mov     eax, cs:dword_18039EB68
0x18005d566  cmp     ecx, 7Ah ; 'z'
0x18005d569  jnz     short loc_18005D57C
0x18005d56b  cmp     eax, 3
0x18005d56e  jbe     short loc_18005D5B6
0x18005d570  mov     [rbp+arg_0], ecx
0x18005d573  lea     rdx, byte_18030EF57
0x18005d57a  jmp     short loc_18005D58B
0x18005d57c  cmp     eax, 2
0x18005d57f  jbe     short loc_18005D5B6
0x18005d581  mov     [rbp+arg_0], ecx
0x18005d584  lea     rdx, dword_18031046C
0x18005d58b  lea     rax, [rbp+arg_0]
0x18005d58f  mov     dword ptr [rbp+arg_8], 691h
0x18005d596  mov     [rsp+40h+var_10], rax
0x18005d59b  lea     rax, [rbp+arg_8]
0x18005d59f  mov     [rsp+40h+var_18], rax
0x18005d5a4  lea     rax, [rbp+arg_18]
0x18005d5a8  mov     [rsp+40h+var_20], rax
0x18005d5ad  mov     [rbp+arg_18], r15
0x18005d5b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005d5b6  mov     rcx, [rbx+170h]; hHandle
0x18005d5bd  test    rcx, rcx
0x18005d5c0  jz      short loc_18005D5D1
0x18005d5c2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005d5c5  call    cs:__imp_WaitForSingleObject
0x18005d5cc  nop     dword ptr [rax+rax+00h]
0x18005d5d1  mov     eax, cs:dword_18039EB68
0x18005d5d7  cmp     eax, 5
0x18005d5da  jbe     short loc_18005D605
0x18005d5dc  lea     rax, [rbp+arg_0]
0x18005d5e0  mov     [rbp+arg_0], 69Ch
0x18005d5e7  mov     [rsp+40h+var_18], rax
0x18005d5ec  lea     rdx, byte_18030DF85
0x18005d5f3  lea     rax, [rbp+arg_8]
0x18005d5f7  mov     [rbp+arg_8], r15
0x18005d5fb  mov     [rsp+40h+var_20], rax
0x18005d600  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005d605  add     rsp, 40h
0x18005d609  pop     r15
0x18005d60b  pop     rdi
0x18005d60c  pop     rsi
0x18005d60d  pop     rbx
0x18005d60e  pop     rbp
0x18005d60f  retn
```
