# PipeManager::PipeImplementation::OnWriteMessage(ulong,ulong,_OVERLAPPED *)

- ea: `0x1800ee830`
- end: `0x1800eea04`
- name: `?OnWriteMessage@PipeImplementation@PipeManager@@CAXKKPEAU_OVERLAPPED@@@Z`
- size: `468`
- prototype: `void __stdcall(DWORD dwErrorCode, DWORD dwNumberOfBytesTransfered, LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000199c`
- `0x1800602e0`
- `0x18006ba8c`
- `0x1800709e4`
- `0x1800ecb60`
- `0x1800ee830`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ee9cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ee9cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ee918`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ee918`
- `api-ms-win-core-file-l1-1-0!WriteFileEx` at `0x1800ee9b2`
- `api-ms-win-core-file-l1-1-0!WriteFileEx` at `0x1800ee9b2`

## string_xrefs

- `0x1800ee86b`: `PipeManager::PipeImplementation::OnWriteMessage`
- `0x1800ee8bf`: `PipeManager::PipeImplementation::OnWriteMessage`

## pseudocode

```c
void __fastcall PipeManager::PipeImplementation::OnWriteMessage(
        int dwErrorCode,
        DWORD dwNumberOfBytesTransfered,
        LPOVERLAPPED lpOverlapped,
        int a4)
{
  ULONG_PTR Internal; // rbx
  signed int LastErrorToHResultAndForceFailure; // edi
  char v6; // r15
  void *v9; // rsi
  _QWORD *v10; // rdx
  std::_Ref_count_base *v11; // rcx
  __int64 v12; // rdx
  CommonUtil *v13; // rcx
  PipeManager *v14; // rcx
  const char *v15; // [rsp+50h] [rbp-10h] BYREF
  const char *v16; // [rsp+58h] [rbp-8h] BYREF
  int v17; // [rsp+A0h] [rbp+40h] BYREF
  DWORD v18; // [rsp+B0h] [rbp+50h] BYREF
  int v19; // [rsp+B8h] [rbp+58h] BYREF

  Internal = lpOverlapped[1].Internal;
  LastErrorToHResultAndForceFailure = 0;
  v6 = 0;
  if ( dwErrorCode )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v19 = *(_DWORD *)(Internal + 16);
      v16 = "PipeManager::PipeImplementation::OnWriteMessage";
      v15 = "LuiPipe";
      v18 = dwNumberOfBytesTransfered;
      v17 = dwErrorCode;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dwErrorCode,
        (unsigned int)byte_1801357F3,
        (_DWORD)lpOverlapped,
        a4,
        (__int64)&v15,
        (__int64)&v16,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v17);
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v19 = *(_DWORD *)(Internal + 16);
    v15 = "PipeManager::PipeImplementation::OnWriteMessage";
    v16 = "LuiPipe";
    v18 = dwNumberOfBytesTransfered;
    v17 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      0,
      (unsigned int)&word_18013578E,
      (_DWORD)lpOverlapped,
      a4,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v17);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(Internal + 120));
  if ( !*(_BYTE *)(Internal + 40) )
  {
    if ( dwErrorCode )
    {
      if ( dwErrorCode > 0 )
        LastErrorToHResultAndForceFailure = (unsigned __int16)dwErrorCode | 0x80070000;
      else
        LastErrorToHResultAndForceFailure = dwErrorCode;
    }
    else
    {
      v9 = **(void ***)(Internal + 160);
      v10 = *(_QWORD **)v9;
      --*(_QWORD *)(Internal + 168);
      **((_QWORD **)v9 + 1) = v10;
      v10[1] = *((_QWORD *)v9 + 1);
      v11 = (std::_Ref_count_base *)*((_QWORD *)v9 + 3);
      if ( v11 )
        std::_Ref_count_base::_Decref(v11);
      std::_Deallocate<16>(v9, (struct std::nothrow_t *)0x20);
      if ( *(_QWORD *)(Internal + 168) )
      {
        v12 = *(_QWORD *)(**(_QWORD **)(Internal + 160) + 16LL);
        if ( WriteFileEx(
               *(HANDLE *)(Internal + 32),
               *(LPCVOID *)(v12 + 8),
               *(_DWORD *)v12,
               lpOverlapped,
               PipeManager::PipeImplementation::OnWriteMessage) )
        {
          v6 = 1;
        }
        else
        {
          LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v13);
        }
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(Internal + 120));
  if ( LastErrorToHResultAndForceFailure < 0 )
    PipeManager::OnPipeError(v14, (struct PipeManager::PipeImplementation *)Internal, LastErrorToHResultAndForceFailure);
  if ( !v6 )
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)Internal + 16LL))(Internal);
}

```

## disassembly

```asm
0x1800ee830  mov     r11, rsp
0x1800ee833  push    rbp
0x1800ee834  push    rbx
0x1800ee835  push    rsi
0x1800ee836  push    rdi
0x1800ee837  push    r13
0x1800ee839  push    r14
0x1800ee83b  push    r15
0x1800ee83d  mov     rbp, rsp
0x1800ee840  sub     rsp, 60h
0x1800ee844  mov     rbx, [r8+20h]
0x1800ee848  xor     edi, edi
0x1800ee84a  mov     eax, cs:CallbackContext
0x1800ee850  xor     r15b, r15b
0x1800ee853  mov     r13, r8
0x1800ee856  mov     esi, ecx
0x1800ee858  test    ecx, ecx
0x1800ee85a  jnz     short loc_1800EE8B4
0x1800ee85c  cmp     eax, 4
0x1800ee85f  jbe     loc_1800EE914
0x1800ee865  mov     eax, [rbx+10h]
0x1800ee868  mov     [rbp+arg_18], eax
0x1800ee86b  lea     rax, aPipemanagerPip_1; "PipeManager::PipeImplementation::OnWrit"...
0x1800ee872  mov     [rbp+var_10], rax
0x1800ee876  lea     rax, aLuipipe; "LuiPipe"
0x1800ee87d  mov     [rbp+var_8], rax
0x1800ee881  lea     rax, [rbp+arg_0]
0x1800ee885  mov     [r11-58h], rax
0x1800ee889  lea     rax, [rbp+arg_10]
0x1800ee88d  mov     [r11-60h], rax
0x1800ee891  lea     rax, [rbp+arg_18]
0x1800ee895  mov     [r11-68h], rax
0x1800ee899  lea     rax, [rbp+var_10]
0x1800ee89d  mov     [r11-70h], rax
0x1800ee8a1  lea     rax, [rbp+var_8]
0x1800ee8a5  mov     [rbp+arg_10], edx
0x1800ee8a8  lea     rdx, word_18013578E
0x1800ee8af  mov     [rbp+arg_0], edi
0x1800ee8b2  jmp     short loc_1800EE90A
0x1800ee8b4  cmp     eax, 2
0x1800ee8b7  jbe     short loc_1800EE914
0x1800ee8b9  mov     eax, [rbx+10h]
0x1800ee8bc  mov     [rbp+arg_18], eax
0x1800ee8bf  lea     rax, aPipemanagerPip_1; "PipeManager::PipeImplementation::OnWrit"...
0x1800ee8c6  mov     [rbp+var_8], rax
0x1800ee8ca  lea     rax, aLuipipe; "LuiPipe"
0x1800ee8d1  mov     [rbp+var_10], rax
0x1800ee8d5  lea     rax, [rbp+arg_0]
0x1800ee8d9  mov     [rsp+60h+var_20], rax
0x1800ee8de  lea     rax, [rbp+arg_10]
0x1800ee8e2  mov     [rsp+60h+var_28], rax
0x1800ee8e7  lea     rax, [rbp+arg_18]
0x1800ee8eb  mov     [rsp+60h+var_30], rax
0x1800ee8f0  lea     rax, [rbp+var_8]
0x1800ee8f4  mov     [rsp+60h+var_38], rax
0x1800ee8f9  lea     rax, [rbp+var_10]
0x1800ee8fd  mov     [rbp+arg_10], edx
0x1800ee900  lea     rdx, byte_1801357F3
0x1800ee907  mov     [rbp+arg_0], esi
0x1800ee90a  mov     [rsp+60h+lpCompletionRoutine], rax
0x1800ee90f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ee914  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800ee918  call    cs:__imp_EnterCriticalSection
0x1800ee91e  cmp     [rbx+28h], dil
0x1800ee922  jnz     loc_1800EE9C8
0x1800ee928  test    esi, esi
0x1800ee92a  jz      short loc_1800EE943
0x1800ee92c  jg      short loc_1800EE935
0x1800ee92e  mov     edi, esi
0x1800ee930  jmp     loc_1800EE9C8
0x1800ee935  movzx   edi, si
0x1800ee938  or      edi, 80070000h
0x1800ee93e  jmp     loc_1800EE9C8
0x1800ee943  mov     rax, [rbx+0A0h]
0x1800ee94a  mov     rsi, [rax]
0x1800ee94d  mov     rdx, [rsi]
0x1800ee950  dec     qword ptr [rbx+0A8h]
0x1800ee957  mov     rax, [rsi+8]
0x1800ee95b  mov     [rax], rdx
0x1800ee95e  mov     rax, [rsi+8]
0x1800ee962  mov     [rdx+8], rax
0x1800ee966  mov     rcx, [rsi+18h]; this
0x1800ee96a  test    rcx, rcx
0x1800ee96d  jz      short loc_1800EE974
0x1800ee96f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ee974  mov     edx, 20h ; ' '
0x1800ee979  mov     rcx, rsi
0x1800ee97c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800ee981  cmp     [rbx+0A8h], rdi
0x1800ee988  jz      short loc_1800EE9C8
0x1800ee98a  mov     rax, [rbx+0A0h]
0x1800ee991  mov     r9, r13; lpOverlapped
0x1800ee994  mov     rcx, [rax]
0x1800ee997  lea     rax, ?OnWriteMessage@PipeImplementation@PipeManager@@CAXKKPEAU_OVERLAPPED@@@Z; PipeManager::PipeImplementation::OnWriteMessage(ulong,ulong,_OVERLAPPED *)
0x1800ee99e  mov     [rsp+60h+lpCompletionRoutine], rax; lpCompletionRoutine
0x1800ee9a3  mov     rdx, [rcx+10h]
0x1800ee9a7  mov     rcx, [rbx+20h]; hFile
0x1800ee9ab  mov     r8d, [rdx]; nNumberOfBytesToWrite
0x1800ee9ae  mov     rdx, [rdx+8]; lpBuffer
0x1800ee9b2  call    cs:__imp_WriteFileEx
0x1800ee9b8  test    eax, eax
0x1800ee9ba  jnz     short loc_1800EE9C5
0x1800ee9bc  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ee9c1  mov     edi, eax
0x1800ee9c3  jmp     short loc_1800EE9C8
0x1800ee9c5  mov     r15b, 1
0x1800ee9c8  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800ee9cc  call    cs:__imp_LeaveCriticalSection
0x1800ee9d2  test    edi, edi
0x1800ee9d4  jns     short loc_1800EE9E1
0x1800ee9d6  mov     r8d, edi; int
0x1800ee9d9  mov     rdx, rbx; struct PipeManager::PipeImplementation *
0x1800ee9dc  call    ?OnPipeError@PipeManager@@AEAAXPEAVPipeImplementation@1@J@Z; PipeManager::OnPipeError(PipeManager::PipeImplementation *,long)
0x1800ee9e1  test    r15b, r15b
0x1800ee9e4  jnz     short loc_1800EE9F5
0x1800ee9e6  mov     rax, [rbx]
0x1800ee9e9  mov     rcx, rbx
0x1800ee9ec  mov     rax, [rax+10h]
0x1800ee9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee9f5  add     rsp, 60h
0x1800ee9f9  pop     r15
0x1800ee9fb  pop     r14
0x1800ee9fd  pop     r13
0x1800ee9ff  pop     rdi
0x1800eea00  pop     rsi
0x1800eea01  pop     rbx
0x1800eea02  pop     rbp
0x1800eea03  retn
```
