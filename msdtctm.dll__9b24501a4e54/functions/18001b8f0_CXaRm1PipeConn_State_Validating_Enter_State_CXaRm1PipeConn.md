# CXaRm1PipeConn_State_Validating::Enter_State(CXaRm1PipeConn *)

- ea: `0x18001b8f0`
- end: `0x18001bb7c`
- name: `?Enter_State@CXaRm1PipeConn_State_Validating@@UEAAXPEAVCXaRm1PipeConn@@@Z`
- size: `652`
- prototype: `void __fastcall(CXaRm1PipeConn_State_Validating *__hidden this, struct CXaRm1PipeConn *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a7010`

## callees

- `0x18001b8f0`
- `0x18001bb84`
- `0x18001bc70`
- `0x18001bda4`
- `0x180021688`
- `0x1800240b0`
- `0x18009abb8`
- `0x18009dfc0`
- `0x18009e3a0`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9b7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001b95e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001b95e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b9e8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b9e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b9ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b9ac`

## string_xrefs

- `0x18001b982`: `com\complus\dtc\dtc\xatm\src\xarmconn.cpp`
- `0x18001b9d2`: `com\complus\dtc\dtc\xatm\src\xarmconn.cpp`
- `0x18001bb2a`: `com\complus\dtc\dtc\xatm\src\xarmconn.cpp`
- `0x18001bb37`: `COpenTask`

## pseudocode

```c
void __fastcall CXaRm1PipeConn_State_Validating::Enter_State(
        CXaRm1PipeConn_State_Validating *this,
        struct CXaRm1PipeConn *a2)
{
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v6; // ecx
  FARPROC ProcAddress; // rax
  DWORD v8; // eax
  unsigned int v9; // eax
  struct IXaNotifySink *v10; // rax
  CValidateTask *v11; // rbx
  char *v12; // rax
  int v13; // [rsp+28h] [rbp-160h]
  struct IXaNotifySink *v14[2]; // [rsp+40h] [rbp-148h] BYREF
  CHAR LibFileName[272]; // [rsp+50h] [rbp-138h] BYREF

  v14[0] = 0;
  memset_0(LibFileName, 0, 0x105u);
  if ( (int)LookUpXaDllPath((char *)a2 + 524, LibFileName) < 0 )
    goto LABEL_18;
  Library = LoadLibraryExA(LibFileName, 0, 0);
  *((_QWORD *)a2 + 30) = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    XA_TRACE_WARNING(v6, LastError, LibFileName, "com\\complus\\dtc\\dtc\\xatm\\src\\xarmconn.cpp", 2503);
    goto LABEL_18;
  }
  ProcAddress = GetProcAddress(Library, "GetXaSwitch");
  if ( !ProcAddress )
  {
    v8 = GetLastError();
    XA_TRACE_WARNING(0x8000D05A, "com\\complus\\dtc\\dtc\\xatm\\src\\xarmconn.cpp", 2515, v8, LibFileName, v13);
LABEL_8:
    FreeLibrary(*((HMODULE *)a2 + 30));
    *((_QWORD *)a2 + 30) = 0;
LABEL_18:
    CXaRm1PipeConn_State::Change_State_RespondAndWaitForDown(this, a2, 0xA0000003);
    return;
  }
  v9 = ((__int64 (__fastcall *)(__int64, char *))ProcAddress)(1, (char *)a2 + 232);
  if ( v9 )
  {
    XA_TRACE_WARNING(0x8000D04F, "com\\complus\\dtc\\dtc\\xatm\\src\\xarmconn.cpp", 2532, v9, LibFileName, v13);
    goto LABEL_8;
  }
  v10 = (struct IXaNotifySink *)operator new(0x80u);
  v14[1] = v10;
  v11 = v10;
  if ( !v10 )
  {
    COMMON_TRACE("COpenTask", "com\\complus\\dtc\\dtc\\xatm\\src\\xarmconn.cpp", 2548, 0xC000110B);
    goto LABEL_18;
  }
  *((_QWORD *)v10 + 4) = 0;
  *((_QWORD *)v10 + 1) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_QWORD *)v10 + 3) = 0;
  *((_DWORD *)v10 + 10) = 0;
  *((_QWORD *)v10 + 6) = 0;
  *(_QWORD *)v10 = &CValidateTask::`vftable';
  *((_DWORD *)v10 + 14) = 0;
  *((_QWORD *)v10 + 9) = 0;
  *((_DWORD *)v10 + 20) = 0;
  (**(void (__fastcall ***)(struct CXaRm1PipeConn *, GUID *, struct IXaNotifySink **))a2)(a2, &IID_IXaNotifySink, v14);
  if ( !v14[0] )
  {
    (*(void (__fastcall **)(CValidateTask *, __int64))(*(_QWORD *)v11 + 48LL))(v11, 1);
    goto LABEL_18;
  }
  v12 = (char *)*((_QWORD *)a2 + 172);
  if ( !v12 )
    v12 = (char *)a2 + 268;
  CValidateTask::Init(
    v11,
    v14[0],
    *((_DWORD *)a2 + 62),
    *((struct xa_switch_t **)a2 + 29),
    v12,
    v12,
    (unsigned int *)a2 + 196,
    (char *)a2 + 524);
  CTaskManager::Enqueue(v11, 2u);
}

```

## disassembly

```asm
0x18001b8f0  mov     [rsp+arg_10], rbx
0x18001b8f5  mov     [rsp+arg_18], rbp
0x18001b8fa  push    rsi
0x18001b8fb  push    rdi
0x18001b8fc  push    r14
0x18001b8fe  sub     rsp, 170h
0x18001b905  mov     rax, cs:__security_cookie
0x18001b90c  xor     rax, rsp
0x18001b90f  mov     [rsp+188h+var_28], rax
0x18001b917  mov     rdi, rdx
0x18001b91a  mov     [rsp+188h+var_148], 0
0x18001b923  mov     rsi, rcx
0x18001b926  xor     edx, edx; Val
0x18001b928  lea     rcx, [rsp+188h+LibFileName]; void *
0x18001b92d  mov     r8d, 105h; Size
0x18001b933  call    memset_0
0x18001b938  lea     rbp, [rdi+20Ch]
0x18001b93f  mov     rcx, rbp; lpValueName
0x18001b942  lea     rdx, [rsp+188h+LibFileName]; char *
0x18001b947  call    ?LookUpXaDllPath@@YAJPEAD0K@Z; LookUpXaDllPath(char *,char *,ulong)
0x18001b94c  test    eax, eax
0x18001b94e  js      loc_18001BB43
0x18001b954  xor     r8d, r8d; dwFlags
0x18001b957  lea     rcx, [rsp+188h+LibFileName]; lpLibFileName
0x18001b95c  xor     edx, edx; hFile
0x18001b95e  call    cs:__imp_LoadLibraryExA
0x18001b964  mov     [rdi+0F0h], rax
0x18001b96b  test    rax, rax
0x18001b96e  jnz     short loc_18001B9A2
0x18001b970  call    cs:__imp_GetLastError
0x18001b976  test    eax, eax
0x18001b978  jle     short loc_18001B982
0x18001b97a  movzx   eax, ax
0x18001b97d  or      eax, 80070000h
0x18001b982  lea     r9, aComComplusDtcD_10; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001b989  mov     dword ptr [rsp+188h+var_168], 9C7h; int
0x18001b991  lea     r8, [rsp+188h+LibFileName]; char *
0x18001b996  mov     edx, eax; unsigned int
0x18001b998  call    ?XA_TRACE_WARNING@@YAXKKPEAD0H@Z; XA_TRACE_WARNING(ulong,ulong,char *,char *,int)
0x18001b99d  jmp     loc_18001BB43
0x18001b9a2  lea     rdx, aGetxaswitch; "GetXaSwitch"
0x18001b9a9  mov     rcx, rax; hModule
0x18001b9ac  call    cs:__imp_GetProcAddress
0x18001b9b2  test    rax, rax
0x18001b9b5  jnz     short loc_18001B9FE
0x18001b9b7  call    cs:__imp_GetLastError
0x18001b9bd  lea     rcx, [rsp+188h+LibFileName]
0x18001b9c2  mov     r8d, 9D3h; int
0x18001b9c8  mov     [rsp+188h+var_168], rcx; char *
0x18001b9cd  mov     ecx, 8000D05Ah; unsigned int
0x18001b9d2  lea     rdx, aComComplusDtcD_10; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001b9d9  mov     r9d, eax; unsigned int
0x18001b9dc  call    ?XA_TRACE_WARNING@@YAXKPEADHK0H@Z; XA_TRACE_WARNING(ulong,char *,int,ulong,char *,int)
0x18001b9e1  mov     rcx, [rdi+0F0h]; hLibModule
0x18001b9e8  call    cs:__imp_FreeLibrary
0x18001b9ee  mov     qword ptr [rdi+0F0h], 0
0x18001b9f9  jmp     loc_18001BB43
0x18001b9fe  lea     r14, [rdi+0E8h]
0x18001ba05  mov     ecx, 1
0x18001ba0a  mov     rdx, r14
0x18001ba0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba12  test    eax, eax
0x18001ba14  jz      short loc_18001BA2D
0x18001ba16  lea     rcx, [rsp+188h+LibFileName]
0x18001ba1b  mov     r8d, 9E4h
0x18001ba21  mov     [rsp+188h+var_168], rcx
0x18001ba26  mov     ecx, 8000D04Fh
0x18001ba2b  jmp     short loc_18001B9D2
0x18001ba2d  mov     ecx, 80h; Size
0x18001ba32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ba37  mov     [rsp+188h+var_140], rax
0x18001ba3c  mov     rbx, rax
0x18001ba3f  test    rax, rax
0x18001ba42  jz      loc_18001BB24
0x18001ba48  mov     qword ptr [rbx+20h], 0
0x18001ba50  lea     rax, ??_7?$UTLink@PEAU_IOMGROVERLAP@@@@6B@; const UTLink<_IOMGROVERLAP *>::`vftable'
0x18001ba57  mov     [rbx+8], rax
0x18001ba5b  lea     rax, ??_7CValidateTask@@6B@; const CValidateTask::`vftable'
0x18001ba62  mov     qword ptr [rbx+18h], 0
0x18001ba6a  mov     dword ptr [rbx+28h], 0
0x18001ba71  mov     qword ptr [rbx+30h], 0
0x18001ba79  mov     [rbx], rax
0x18001ba7c  mov     dword ptr [rbx+38h], 0
0x18001ba83  mov     qword ptr [rbx+48h], 0
0x18001ba8b  mov     dword ptr [rbx+50h], 0
0x18001ba92  test    rbx, rbx
0x18001ba95  jz      loc_18001BB24
0x18001ba9b  mov     rax, [rdi]
0x18001ba9e  lea     r8, [rsp+188h+var_148]
0x18001baa3  lea     rdx, IID_IXaNotifySink
0x18001baaa  mov     rcx, rdi
0x18001baad  mov     rax, [rax]
0x18001bab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bab5  mov     rdx, [rsp+188h+var_148]; struct IXaNotifySink *
0x18001baba  test    rdx, rdx
0x18001babd  jnz     short loc_18001BAD5
0x18001babf  mov     rax, [rbx]
0x18001bac2  mov     edx, 1
0x18001bac7  mov     rcx, rbx
0x18001baca  mov     rax, [rax+30h]
0x18001bace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bad3  jmp     short loc_18001BB43
0x18001bad5  mov     rax, [rdi+560h]
0x18001badc  lea     rcx, [rdi+310h]
0x18001bae3  mov     r8d, [rdi+0F8h]; unsigned int
0x18001baea  mov     r9, [r14]; struct xa_switch_t *
0x18001baed  mov     [rsp+188h+var_150], rbp; char *
0x18001baf2  mov     [rsp+188h+var_158], rcx; unsigned int *
0x18001baf7  mov     rcx, rbx; this
0x18001bafa  test    rax, rax
0x18001bafd  jnz     short loc_18001BB06
0x18001baff  lea     rax, [rdi+10Ch]
0x18001bb06  mov     [rsp+188h+var_160], rax; char *
0x18001bb0b  mov     [rsp+188h+var_168], rax; char *
0x18001bb10  call    ?Init@CValidateTask@@QEAAXPEAUIXaNotifySink@@IPEAUxa_switch_t@@PEAD2PEAK2@Z; CValidateTask::Init(IXaNotifySink *,uint,xa_switch_t *,char *,char *,ulong *,char *)
0x18001bb15  mov     edx, 2; unsigned int
0x18001bb1a  mov     rcx, rbx; struct CWorkerTask *
0x18001bb1d  call    ?Enqueue@CTaskManager@@SAXPEAVCWorkerTask@@K@Z; CTaskManager::Enqueue(CWorkerTask *,ulong)
0x18001bb22  jmp     short loc_18001BB54
0x18001bb24  mov     r9d, 0C000110Bh; unsigned int
0x18001bb2a  lea     rdx, aComComplusDtcD_10; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001bb31  mov     r8d, 9F4h; int
0x18001bb37  lea     rcx, aCopentask; "COpenTask"
0x18001bb3e  call    ?COMMON_TRACE@@YAXPEAD0HK@Z; COMMON_TRACE(char *,char *,int,ulong)
0x18001bb43  mov     r8d, 0A0000003h; unsigned int
0x18001bb49  mov     rdx, rdi; struct CXaRm1PipeConn *
0x18001bb4c  mov     rcx, rsi; this
0x18001bb4f  call    ?Change_State_RespondAndWaitForDown@CXaRm1PipeConn_State@@QEAAXPEAVCXaRm1PipeConn@@K@Z; CXaRm1PipeConn_State::Change_State_RespondAndWaitForDown(CXaRm1PipeConn *,ulong)
0x18001bb54  mov     rcx, [rsp+188h+var_28]
0x18001bb5c  xor     rcx, rsp; StackCookie
0x18001bb5f  call    __security_check_cookie
0x18001bb64  lea     r11, [rsp+188h+var_18]
0x18001bb6c  mov     rbx, [r11+30h]
0x18001bb70  mov     rbp, [r11+38h]
0x18001bb74  mov     rsp, r11
0x18001bb77  pop     r14
0x18001bb79  pop     rdi
0x18001bb7a  pop     rsi
0x18001bb7b  retn
```
