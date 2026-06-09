# MasterKeyDiagnosticInfo::LoadRecords(void *)

- ea: `0x180010190`
- end: `0x18001042a`
- name: `?LoadRecords@MasterKeyDiagnosticInfo@@QEAAXPEAX@Z`
- size: `666`
- prototype: `void __fastcall(MasterKeyDiagnosticInfo *this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18001cd50`

## callees

- `0x18001014c`
- `0x180010190`
- `0x1800104b4`
- `0x180010504`
- `0x1800107c4`
- `0x18001bbd0`
- `0x18001bd84`
- `0x18003ae00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800103bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800103bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800101c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800101c0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001020c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800102bc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180010364`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001020c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800102bc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180010364`

## pseudocode

```c
void __fastcall MasterKeyDiagnosticInfo::LoadRecords(MasterKeyDiagnosticInfo *this, void *a2)
{
  BOOL v3; // eax
  unsigned int v4; // r8d
  const char *v5; // r9
  unsigned int v6; // r8d
  const char *v7; // r9
  bool v8; // si
  char *v9; // r15
  std::_Ref_count_base *v10; // rcx
  _OWORD *v11; // rdi
  _QWORD *v12; // rax
  _OWORD *v13; // [rsp+30h] [rbp-68h] BYREF
  std::_Ref_count_base *v14; // [rsp+38h] [rbp-60h]
  LPVOID lpBuffer; // [rsp+40h] [rbp-58h] BYREF
  std::_Ref_count_base *v16; // [rsp+48h] [rbp-50h]
  LPVOID v17; // [rsp+50h] [rbp-48h] BYREF
  std::_Ref_count_base *v18; // [rsp+58h] [rbp-40h]
  _BYTE v19[56]; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  MasterKeyDiagnosticInfo *NumberOfBytesRead; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int Buffer; // [rsp+B0h] [rbp+18h] BYREF
  RTL_SRWLOCK *v23; // [rsp+B8h] [rbp+20h] BYREF

  NumberOfBytesRead = this;
  if ( byte_18004C938 )
    return;
  AcquireSRWLockExclusive(&SRWLock);
  v23 = &SRWLock;
  Buffer = 0;
  LODWORD(NumberOfBytesRead) = 0;
  v3 = ReadFile(a2, &Buffer, 4u, (LPDWORD)&NumberOfBytesRead, 0);
  try
  {
    if ( !v3 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x5F, v4, v5);
    if ( (_DWORD)NumberOfBytesRead == 4 && Buffer <= 2 )
    {
      v8 = Buffer < 2;
      while ( 1 )
      {
        std::make_shared<MasterKeyDiagnosticInfo::Record_v2,>(&v13);
        if ( v8 )
        {
          std::make_shared<MasterKeyDiagnosticInfo::Record_v1,>(&lpBuffer);
          v9 = (char *)lpBuffer;
          if ( !ReadFile(a2, lpBuffer, 0x1Cu, (LPDWORD)&NumberOfBytesRead, 0) )
            wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x80, v6, v7);
          if ( !(_DWORD)NumberOfBytesRead )
          {
            v10 = v16;
LABEL_19:
            if ( v10 )
              std::_Ref_count_base::_Decref(v10);
            if ( v14 )
              std::_Ref_count_base::_Decref(v14);
            byte_18004C938 = 1;
            if ( &SRWLock )
              ReleaseSRWLockExclusive(&SRWLock);
            return;
          }
          v11 = v13;
          *v13 = *(_OWORD *)v9;
          *((_BYTE *)v11 + 52) = v9[16];
          *((_QWORD *)v11 + 72) = *(_QWORD *)(v9 + 20);
          v11[1] = 0;
          v11[2] = 0;
          *((_DWORD *)v11 + 12) = 0;
          v10 = v16;
          if ( v16 )
            std::_Ref_count_base::_Decref(v16);
        }
        else
        {
          std::make_shared<MasterKeyDiagnosticInfo::Record_v2,>(&v17);
          if ( !ReadFile(a2, v17, 0x248u, (LPDWORD)&NumberOfBytesRead, 0) )
            wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x95, v6, v7);
          v10 = v18;
          if ( !(_DWORD)NumberOfBytesRead )
            goto LABEL_19;
          if ( v18 )
            std::_Ref_count_base::_Decref(v18);
          v11 = v13;
        }
        v12 = (_QWORD *)std::map<_GUID,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>::_Try_emplace<_GUID const &,>(
                          v10,
                          v19,
                          v11);
        std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>::operator=(*v12 + 48LL, &v13);
        if ( v14 )
          std::_Ref_count_base::_Decref(v14);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0xA3, v6, v7);
  }
}

```

## disassembly

```asm
0x180010190  mov     [rsp+arg_8], rbx
0x180010195  mov     [rsp+NumberOfBytesRead], rcx
0x18001019a  push    rsi
0x18001019b  push    rdi
0x18001019c  push    r13
0x18001019e  push    r14
0x1800101a0  push    r15
0x1800101a2  sub     rsp, 70h
0x1800101a6  mov     r14, rdx
0x1800101a9  cmp     cs:byte_18004C938, 0
0x1800101b0  jnz     loc_1800103CC
0x1800101b6  lea     rbx, SRWLock
0x1800101bd  mov     rcx, rbx; SRWLock
0x1800101c0  call    cs:__imp_AcquireSRWLockExclusive
0x1800101c7  nop     dword ptr [rax+rax+00h]
0x1800101cc  mov     [rsp+98h+arg_18], rbx
0x1800101d4  mov     [rsp+98h+Buffer], 0
0x1800101df  mov     dword ptr [rsp+98h+NumberOfBytesRead], 0
0x1800101ea  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x1800101f3  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800101fb  mov     r8d, 4; nNumberOfBytesToRead
0x180010201  lea     rdx, [rsp+98h+Buffer]; lpBuffer
0x180010209  mov     rcx, r14; hFile
0x18001020c  call    cs:__imp_ReadFile
0x180010213  nop     dword ptr [rax+rax+00h]
0x180010218  mov     rcx, [rsp+98h]; this
0x180010220  test    eax, eax
0x180010222  jnz     short loc_18001022C
0x180010224  lea     edx, [rax+5Fh]; void *
0x180010227  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001022c  cmp     dword ptr [rsp+98h+NumberOfBytesRead], 4
0x180010234  jz      short loc_180010248
0x180010236  lea     rcx, [rsp+98h+arg_18]
0x18001023e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010243  jmp     loc_1800103CC
0x180010248  cmp     [rsp+98h+Buffer], 2
0x180010250  jbe     short loc_180010264
0x180010252  lea     rcx, [rsp+98h+arg_18]
0x18001025a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001025f  jmp     loc_1800103CC
0x180010264  xor     al, al
0x180010266  movzx   esi, al
0x180010269  mov     r13d, 1
0x18001026f  cmp     [rsp+98h+Buffer], 2
0x180010277  cmovb   esi, r13d
0x18001027b  lea     rcx, [rsp+98h+var_68]
0x180010280  call    ??$make_shared@URecord_v2@MasterKeyDiagnosticInfo@@$$V@std@@YA?AV?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@0@XZ; std::make_shared<MasterKeyDiagnosticInfo::Record_v2,>(void)
0x180010285  nop
0x180010286  test    sil, sil
0x180010289  jz      loc_18001033A
0x18001028f  lea     rcx, [rsp+98h+lpBuffer]
0x180010294  call    ??$make_shared@URecord_v1@MasterKeyDiagnosticInfo@@$$V@std@@YA?AV?$shared_ptr@URecord_v1@MasterKeyDiagnosticInfo@@@0@XZ; std::make_shared<MasterKeyDiagnosticInfo::Record_v1,>(void)
0x180010299  nop
0x18001029a  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x1800102a3  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800102ab  mov     r8d, 1Ch; nNumberOfBytesToRead
0x1800102b1  mov     r15, [rsp+98h+lpBuffer]
0x1800102b6  mov     rdx, r15; lpBuffer
0x1800102b9  mov     rcx, r14; hFile
0x1800102bc  call    cs:__imp_ReadFile
0x1800102c3  nop     dword ptr [rax+rax+00h]
0x1800102c8  mov     rcx, [rsp+98h]; this
0x1800102d0  test    eax, eax
0x1800102d2  jnz     short loc_1800102DE
0x1800102d4  mov     edx, 80h; void *
0x1800102d9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800102de  cmp     dword ptr [rsp+98h+NumberOfBytesRead], 0
0x1800102e6  jnz     short loc_1800102F2
0x1800102e8  mov     rcx, [rsp+98h+var_50]
0x1800102ed  jmp     loc_180010396
0x1800102f2  movups  xmm0, xmmword ptr [r15]
0x1800102f6  mov     rdi, [rsp+98h+var_68]
0x1800102fb  movdqu  xmmword ptr [rdi], xmm0
0x1800102ff  mov     al, [r15+10h]
0x180010303  mov     [rdi+34h], al
0x180010306  mov     rax, [r15+14h]
0x18001030a  mov     [rdi+240h], rax
0x180010311  xorps   xmm0, xmm0
0x180010314  movdqu  xmmword ptr [rdi+10h], xmm0
0x180010319  xor     eax, eax
0x18001031b  movups  xmmword ptr [rdi+20h], xmm0
0x18001031f  mov     [rdi+30h], eax
0x180010322  mov     rcx, [rsp+98h+var_50]; this
0x180010327  test    rcx, rcx
0x18001032a  jz      loc_1800103F1
0x180010330  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010335  jmp     loc_1800103F1
0x18001033a  lea     rcx, [rsp+98h+var_48]
0x18001033f  call    ??$make_shared@URecord_v2@MasterKeyDiagnosticInfo@@$$V@std@@YA?AV?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@0@XZ; std::make_shared<MasterKeyDiagnosticInfo::Record_v2,>(void)
0x180010344  nop
0x180010345  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x18001034e  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180010356  mov     r8d, 248h; nNumberOfBytesToRead
0x18001035c  mov     rdx, [rsp+98h+var_48]; lpBuffer
0x180010361  mov     rcx, r14; hFile
0x180010364  call    cs:__imp_ReadFile
0x18001036b  nop     dword ptr [rax+rax+00h]
0x180010370  mov     rcx, [rsp+98h]; this
0x180010378  test    eax, eax
0x18001037a  jnz     short loc_180010387
0x18001037c  mov     edx, 95h; void *
0x180010381  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180010387  mov     rcx, [rsp+98h+var_40]; this
0x18001038c  cmp     dword ptr [rsp+98h+NumberOfBytesRead], 0
0x180010394  jnz     short loc_1800103E2
0x180010396  test    rcx, rcx
0x180010399  jz      short loc_1800103A1
0x18001039b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800103a0  nop
0x1800103a1  mov     rcx, [rsp+98h+var_60]; this
0x1800103a6  test    rcx, rcx
0x1800103a9  jz      short loc_1800103B0
0x1800103ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800103b0  mov     cs:byte_18004C938, r13b
0x1800103b7  test    rbx, rbx
0x1800103ba  jz      short loc_1800103CC
0x1800103bc  mov     rcx, rbx; SRWLock
0x1800103bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800103c6  nop     dword ptr [rax+rax+00h]
0x1800103cb  nop
0x1800103cc  mov     rbx, [rsp+98h+arg_8]
0x1800103d4  add     rsp, 70h
0x1800103d8  pop     r15
0x1800103da  pop     r14
0x1800103dc  pop     r13
0x1800103de  pop     rdi
0x1800103df  pop     rsi
0x1800103e0  retn
0x1800103e2  test    rcx, rcx
0x1800103e5  jz      short loc_1800103EC
0x1800103e7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800103ec  mov     rdi, [rsp+98h+var_68]
0x1800103f1  mov     r8, rdi
0x1800103f4  lea     rdx, [rsp+98h+var_38]
0x1800103f9  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x1800103fe  mov     rcx, [rax]
0x180010401  add     rcx, 30h ; '0'
0x180010405  lea     rdx, [rsp+98h+var_68]
0x18001040a  call    ??4?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>::operator=(std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2> &&)
0x18001040f  nop
0x180010410  mov     rcx, [rsp+98h+var_60]; this
0x180010415  test    rcx, rcx
0x180010418  jz      loc_18001027B
0x18001041e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010423  jmp     loc_18001027B
```
