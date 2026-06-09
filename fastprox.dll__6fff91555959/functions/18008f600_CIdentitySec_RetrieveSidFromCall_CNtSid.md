# CIdentitySec::RetrieveSidFromCall(CNtSid &)

- ea: `0x18008f600`
- end: `0x18008f776`
- name: `?RetrieveSidFromCall@CIdentitySec@@AEAAJAEAVCNtSid@@@Z`
- size: `374`
- prototype: `int(CIdentitySec *__hidden this, struct CNtSid *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800852d0`
- `0x18008e3ac`

## callees

- `0x180037120`
- `0x18008e544`
- `0x18008ec08`
- `0x18008f600`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008f634`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008f634`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f61f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f61f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18008f6e2`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18008f6e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f642`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f65d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f66a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f65d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f66a`
- `wbemcomn!GetMemLogObject` at `0x18008f683`
- `wbemcomn!GetMemLogObject` at `0x18008f683`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f68e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f68e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall CIdentitySec::RetrieveSidFromCall(CIdentitySec *this, struct CNtSid *a2)
{
  HANDLE CurrentThread; // rax
  CIdentitySec *v4; // rcx
  signed int LastError; // eax
  signed int v7; // ebx
  CMemoryLog *MemLogObject; // rax
  void *v9; // rbx
  CIdentitySec *v10; // rcx
  signed int SidFromThreadOrProcess; // edi
  CIdentitySec *v12; // rcx
  int v13; // esi
  void *ppInterface; // [rsp+50h] [rbp+20h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  void *v16; // [rsp+68h] [rbp+38h] BYREF

  ppInterface = this;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle) )
  {
    CloseHandle(TokenHandle);
    return CIdentitySec::GetSidFromThreadOrProcess(v4, a2);
  }
  if ( GetLastError() == 1008 )
  {
    ppInterface = 0;
    if ( CoGetCallContext(&IID_IServerSecurity, &ppInterface) )
      return CIdentitySec::GetSidFromThreadOrProcess(v4, a2);
    v9 = ppInterface;
    if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
    {
      SidFromThreadOrProcess = CIdentitySec::GetSidFromThreadOrProcess(v10, a2);
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
      if ( v13 < 0 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
        return v13;
      }
      v16 = ppInterface;
      SidFromThreadOrProcess = CIdentitySec::GetSidFromThreadOrProcess(v12, a2);
      OnDeleteObj0<IServerSecurity,long (IServerSecurity::*)(void),&[thunk]: IServerSecurity::`vcall'{40,{flat}}>::~OnDeleteObj0<IServerSecurity,long (IServerSecurity::*)(void),&[thunk]: IServerSecurity::`vcall'{40,{flat}}>(&v16);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
    return SidFromThreadOrProcess;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v7);
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids, (unsigned int)v7);
  }
  return v7;
}

```

## disassembly

```asm
0x18008f600  mov     [rsp-18h+arg_8], rbx
0x18008f605  mov     [rsp-18h+ppInterface], rcx
0x18008f60a  push    rbp
0x18008f60b  push    rsi
0x18008f60c  push    rdi
0x18008f60d  mov     rbp, rsp
0x18008f610  sub     rsp, 30h
0x18008f614  mov     rdi, rdx
0x18008f617  mov     [rbp+TokenHandle], 0
0x18008f61f  call    cs:__imp_GetCurrentThread
0x18008f625  mov     rcx, rax; ThreadHandle
0x18008f628  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18008f62c  xor     r8d, r8d; OpenAsSelf
0x18008f62f  mov     edx, 20008h; DesiredAccess
0x18008f634  call    cs:__imp_OpenThreadToken
0x18008f63a  test    eax, eax
0x18008f63c  jz      short loc_18008F65D
0x18008f63e  mov     rcx, [rbp+TokenHandle]; hObject
0x18008f642  call    cs:__imp_CloseHandle
0x18008f648  mov     rdx, rdi; struct CNtSid *
0x18008f64b  call    ?GetSidFromThreadOrProcess@CIdentitySec@@AEAAJAEAVCNtSid@@@Z; CIdentitySec::GetSidFromThreadOrProcess(CNtSid &)
0x18008f650  mov     rbx, [rsp+30h+arg_8]
0x18008f655  add     rsp, 30h
0x18008f659  pop     rdi
0x18008f65a  pop     rsi
0x18008f65b  pop     rbp
0x18008f65c  retn
0x18008f65d  call    cs:__imp_GetLastError
0x18008f663  cmp     eax, 3F0h
0x18008f668  jz      short loc_18008F6CF
0x18008f66a  call    cs:__imp_GetLastError
0x18008f670  mov     ebx, eax
0x18008f672  test    eax, eax
0x18008f674  jle     short loc_18008F67F
0x18008f676  movzx   ebx, ax
0x18008f679  or      ebx, 80070000h
0x18008f67f  test    ebx, ebx
0x18008f681  jns     short loc_18008F694
0x18008f683  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f689  mov     edx, ebx
0x18008f68b  mov     rcx, rax
0x18008f68e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f694  lea     rax, WPP_GLOBAL_Control
0x18008f69b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f6a2  cmp     rcx, rax
0x18008f6a5  jz      short loc_18008F6CB
0x18008f6a7  test    byte ptr [rcx+1Ch], 1
0x18008f6ab  jz      short loc_18008F6CB
0x18008f6ad  cmp     byte ptr [rcx+19h], 2
0x18008f6b1  jb      short loc_18008F6CB
0x18008f6b3  mov     edx, 22h ; '"'
0x18008f6b8  mov     r9d, ebx
0x18008f6bb  lea     r8, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids
0x18008f6c2  mov     rcx, [rcx+10h]
0x18008f6c6  call    WPP_SF_d
0x18008f6cb  mov     eax, ebx
0x18008f6cd  jmp     short loc_18008F650
0x18008f6cf  mov     [rbp+ppInterface], 0
0x18008f6d7  lea     rdx, [rbp+ppInterface]; ppInterface
0x18008f6db  lea     rcx, IID_IServerSecurity; riid
0x18008f6e2  call    cs:__imp_CoGetCallContext
0x18008f6e8  test    eax, eax
0x18008f6ea  jnz     loc_18008F648
0x18008f6f0  mov     rbx, [rbp+ppInterface]
0x18008f6f4  mov     [rbp+var_10], rbx
0x18008f6f8  mov     rcx, [rbp+ppInterface]
0x18008f6fc  mov     rax, [rcx]
0x18008f6ff  mov     rax, [rax+30h]
0x18008f703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f708  test    eax, eax
0x18008f70a  jz      short loc_18008F72C
0x18008f70c  mov     rdx, rdi; struct CNtSid *
0x18008f70f  call    ?GetSidFromThreadOrProcess@CIdentitySec@@AEAAJAEAVCNtSid@@@Z; CIdentitySec::GetSidFromThreadOrProcess(CNtSid &)
0x18008f714  mov     edi, eax
0x18008f716  mov     rcx, [rbx]
0x18008f719  mov     rax, [rcx+10h]
0x18008f71d  mov     rcx, rbx
0x18008f720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f725  mov     eax, edi
0x18008f727  jmp     loc_18008F650
0x18008f72c  mov     rcx, [rbp+ppInterface]
0x18008f730  mov     rax, [rcx]
0x18008f733  mov     rax, [rax+20h]
0x18008f737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f73c  mov     esi, eax
0x18008f73e  test    eax, eax
0x18008f740  jns     short loc_18008F758
0x18008f742  mov     rcx, [rbx]
0x18008f745  mov     rax, [rcx+10h]
0x18008f749  mov     rcx, rbx
0x18008f74c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f751  mov     eax, esi
0x18008f753  jmp     loc_18008F650
0x18008f758  mov     rax, [rbp+ppInterface]
0x18008f75c  mov     [rbp+arg_18], rax
0x18008f760  mov     rdx, rdi; struct CNtSid *
0x18008f763  call    ?GetSidFromThreadOrProcess@CIdentitySec@@AEAAJAEAVCNtSid@@@Z; CIdentitySec::GetSidFromThreadOrProcess(CNtSid &)
0x18008f768  mov     edi, eax
0x18008f76a  lea     rcx, [rbp+arg_18]
0x18008f76e  call    ??1?$OnDeleteObj0@UIServerSecurity@@P81@EAAJXZ$1??_91@$BCI@AA@@QEAA@XZ; OnDeleteObj0<IServerSecurity,long (IServerSecurity::*)(void),&[thunk]: IServerSecurity::`vcall'{40,{flat}}>::~OnDeleteObj0<IServerSecurity,long (IServerSecurity::*)(void),&[thunk]: IServerSecurity::`vcall'{40,{flat}}>(void)
0x18008f773  jmp     short loc_18008F716
```
