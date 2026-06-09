# CPipeVC::IssueRead(void)

- ea: `0x180016864`
- end: `0x180016b09`
- name: `?IssueRead@CPipeVC@@IEAAJXZ`
- size: `677`
- prototype: `__int64 __fastcall(CPipeVC *this, __int64, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011bd4`
- `0x180016188`
- `0x180074000`

## callees

- `0x1800091a8`
- `0x18000a8e0`
- `0x18000a93c`
- `0x18000c8c0`
- `0x180012200`
- `0x180016864`
- `0x18002e600`
- `0x180032f60`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180016a34`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180016a34`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016a7d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a92`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x180016a6c`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x180016a6c`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001688b`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001691e`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001688b`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001691e`

## string_xrefs

- `0x180016ad8`: `ReadFileEx failed`

## pseudocode

```c
__int64 __fastcall CPipeVC::IssueRead(CPipeVC *this, __int64 a2, __int64 a3)
{
  __int64 *v3; // rbx
  char *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // eax
  __int64 **v9; // rsi
  __int64 *v10; // rbp
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int64 *v13; // rbp
  __int64 *v14; // rbp
  unsigned int v15; // eax
  void *v16; // rcx
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 *v20; // [rsp+50h] [rbp+8h] BYREF
  char *v21; // [rsp+58h] [rbp+10h] BYREF
  char *v22; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  v5 = (char *)this + 88;
  v20 = 0;
  v22 = v5;
  if ( *((_DWORD *)v5 + 2) )
    PAL_System_CritSecEnter(*(_QWORD *)v5, a2, a3);
  if ( (unsigned int)CPipeVC::IsValidObjectState(this) )
  {
    v21 = (char *)this + 400;
    if ( *((_DWORD *)this + 102) )
      PAL_System_CritSecEnter(*((_QWORD *)this + 50), v6, v7);
    v9 = (__int64 **)((char *)this + 336);
    if ( !*((_QWORD *)this + 42) )
    {
      v10 = (__int64 *)*((_QWORD *)this + 45);
      if ( v10 == (__int64 *)((char *)this + 360) )
      {
        CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
        goto LABEL_34;
      }
      v11 = (_QWORD *)v10[1];
      v12 = *v10;
      v13 = v10 - 10;
      *v11 = v12;
      *(_QWORD *)(v12 + 8) = v11;
      *(__int64 *)((char *)v13 + 60) = *((unsigned int *)v13 + 14);
      if ( v13 != *v9 )
      {
        TCntPtr<CWppAutoTrace>::SafeRelease((char *)this + 336);
        *v9 = v13;
        TCntPtr<CTermInputMgr>::SafeAddRef((char *)this + 336);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13[4] + 16LL))(v13[4]);
    }
    v14 = 0;
    if ( *v9 )
    {
      TCntPtr<CWppAutoTrace>::SafeRelease(&v20);
      v20 = *v9;
      v3 = v20;
      TCntPtr<CTermInputMgr>::SafeAddRef(&v20);
      v14 = v3;
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
    if ( v14 )
    {
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 6) + 8LL))((char *)this + 48);
      ResetEvent(*((HANDLE *)this + 40));
      v16 = (void *)*((_QWORD *)this + 16);
      *((_DWORD *)this + 98) = 1;
      if ( ReadFileEx(
             v16,
             (LPVOID)(v3[6] + *((unsigned int *)v3 + 16)),
             *((_DWORD *)v3 + 15) - *((_DWORD *)v3 + 16),
             (LPOVERLAPPED)this + 9,
             CPipeVC::StaticReadFromPipeComplete) )
      {
        LODWORD(v3) = 0;
      }
      else
      {
        SetEvent(*((HANDLE *)this + 40));
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 6) + 16LL))((char *)this + 48);
        LastError = GetLastError();
        LODWORD(v3) = LastError;
        if ( LastError > 0 )
          LODWORD(v3) = (unsigned __int16)LastError | 0x80070000;
        if ( (int)v3 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            112,
            (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"ReadFileEx failed",
            (char)v3);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
          v15,
          -2147418113);
      }
      LODWORD(v3) = -2147418113;
    }
  }
  else
  {
    LODWORD(v3) = -2147024884;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        110,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        v8,
        (__int64)"!IsValidObjectState()",
        12);
    }
  }
LABEL_34:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v22);
  TCntPtr<CWppAutoTrace>::SafeRelease(&v20);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016864  mov     [rsp+arg_18], rbx
0x180016869  push    rbp
0x18001686a  push    rsi
0x18001686b  push    rdi
0x18001686c  sub     rsp, 30h
0x180016870  xor     ebx, ebx
0x180016872  mov     rdi, rcx
0x180016875  add     rcx, 58h ; 'X'
0x180016879  mov     [rsp+48h+arg_0], rbx
0x18001687e  mov     [rsp+48h+arg_10], rcx
0x180016883  cmp     [rcx+8], ebx
0x180016886  jz      short loc_180016891
0x180016888  mov     rcx, [rcx]
0x18001688b  call    cs:__imp_PAL_System_CritSecEnter
0x180016891  mov     rcx, rdi; this
0x180016894  call    ?IsValidObjectState@CPipeVC@@IEAAHXZ; CPipeVC::IsValidObjectState(void)
0x180016899  test    eax, eax
0x18001689b  jnz     short loc_18001690A
0x18001689d  mov     ebx, 8007000Ch
0x1800168a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168a9  lea     rax, WPP_GLOBAL_Control
0x1800168b0  cmp     rcx, rax
0x1800168b3  jz      loc_180016AE6
0x1800168b9  test    byte ptr [rcx+1Ch], 8
0x1800168bd  jz      loc_180016AE6
0x1800168c3  cmp     byte ptr [rcx+19h], 2
0x1800168c7  jb      loc_180016AE6
0x1800168cd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800168d2  mov     edx, 6Eh ; 'n'
0x1800168d7  mov     [rsp+48h+var_20], 8007000Ch
0x1800168df  lea     rcx, aIsvalidobjects; "!IsValidObjectState()"
0x1800168e6  mov     [rsp+48h+lpCompletionRoutine], rcx
0x1800168eb  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x1800168f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168f9  mov     r9d, eax
0x1800168fc  mov     rcx, [rcx+10h]
0x180016900  call    WPP_SF_DsD
0x180016905  jmp     loc_180016AE6
0x18001690a  lea     rcx, [rdi+190h]
0x180016911  mov     [rsp+48h+arg_8], rcx
0x180016916  cmp     [rcx+8], ebx
0x180016919  jz      short loc_180016924
0x18001691b  mov     rcx, [rcx]
0x18001691e  call    cs:__imp_PAL_System_CritSecEnter
0x180016924  lea     rsi, [rdi+150h]
0x18001692b  cmp     [rsi], rbx
0x18001692e  jnz     short loc_180016992
0x180016930  lea     rax, [rdi+168h]
0x180016937  mov     rbp, [rax]
0x18001693a  cmp     rbp, rax
0x18001693d  jnz     short loc_18001694E
0x18001693f  lea     rcx, [rsp+48h+arg_8]; this
0x180016944  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180016949  jmp     loc_180016AE6
0x18001694e  mov     rax, [rbp+8]
0x180016952  mov     rcx, [rbp+0]
0x180016956  add     rbp, 0FFFFFFFFFFFFFFB0h
0x18001695a  mov     [rax], rcx
0x18001695d  mov     [rcx+8], rax
0x180016961  mov     eax, [rbp+38h]
0x180016964  mov     [rbp+3Ch], eax
0x180016967  mov     [rbp+40h], ebx
0x18001696a  cmp     rbp, [rsi]
0x18001696d  jz      short loc_180016982
0x18001696f  mov     rcx, rsi
0x180016972  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x180016977  mov     rcx, rsi
0x18001697a  mov     [rsi], rbp
0x18001697d  call    ?SafeAddRef@?$TCntPtr@VCTermInputMgr@@@@AEAAXXZ; TCntPtr<CTermInputMgr>::SafeAddRef(void)
0x180016982  mov     rcx, [rbp+20h]
0x180016986  mov     rax, [rcx]
0x180016989  mov     rax, [rax+10h]
0x18001698d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016992  xor     ebp, ebp
0x180016994  cmp     [rsi], rbx
0x180016997  jz      short loc_1800169B8
0x180016999  lea     rcx, [rsp+48h+arg_0]
0x18001699e  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x1800169a3  mov     rbx, [rsi]
0x1800169a6  lea     rcx, [rsp+48h+arg_0]
0x1800169ab  mov     [rsp+48h+arg_0], rbx
0x1800169b0  call    ?SafeAddRef@?$TCntPtr@VCTermInputMgr@@@@AEAAXXZ; TCntPtr<CTermInputMgr>::SafeAddRef(void)
0x1800169b5  mov     rbp, rbx
0x1800169b8  lea     rcx, [rsp+48h+arg_8]; this
0x1800169bd  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800169c2  test    rbp, rbp
0x1800169c5  jnz     short loc_180016A1A
0x1800169c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169ce  lea     rax, WPP_GLOBAL_Control
0x1800169d5  cmp     rcx, rax
0x1800169d8  jz      short loc_180016A10
0x1800169da  test    byte ptr [rcx+1Ch], 8
0x1800169de  jz      short loc_180016A10
0x1800169e0  cmp     byte ptr [rcx+19h], 2
0x1800169e4  jb      short loc_180016A10
0x1800169e6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800169eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169f2  lea     edx, [rbp+6Fh]
0x1800169f5  mov     r9d, eax
0x1800169f8  mov     dword ptr [rsp+48h+lpCompletionRoutine], 8000FFFFh
0x180016a00  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180016a07  mov     rcx, [rcx+10h]
0x180016a0b  call    WPP_SF_Dd
0x180016a10  mov     ebx, 8000FFFFh
0x180016a15  jmp     loc_180016AE6
0x180016a1a  lea     rsi, [rdi+30h]
0x180016a1e  mov     rax, [rsi]
0x180016a21  mov     rcx, rsi
0x180016a24  mov     rax, [rax+8]
0x180016a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a2d  mov     rcx, [rdi+140h]; hEvent
0x180016a34  call    cs:__imp_ResetEvent
0x180016a3a  mov     rcx, [rdi+80h]; hFile
0x180016a41  lea     rax, ?StaticReadFromPipeComplete@CPipeVC@@KAXKKPEAU_OVERLAPPED@@@Z; CPipeVC::StaticReadFromPipeComplete(ulong,ulong,_OVERLAPPED *)
0x180016a48  mov     dword ptr [rdi+188h], 1
0x180016a52  lea     r9, [rdi+120h]; lpOverlapped
0x180016a59  mov     edx, [rbx+40h]
0x180016a5c  mov     r8d, [rbx+3Ch]
0x180016a60  sub     r8d, edx; nNumberOfBytesToRead
0x180016a63  mov     [rsp+48h+lpCompletionRoutine], rax; lpCompletionRoutine
0x180016a68  add     rdx, [rbx+30h]; lpBuffer
0x180016a6c  call    cs:__imp_ReadFileEx
0x180016a72  test    eax, eax
0x180016a74  jnz     short loc_180016AE4
0x180016a76  mov     rcx, [rdi+140h]; hEvent
0x180016a7d  call    cs:__imp_SetEvent
0x180016a83  mov     rax, [rsi]
0x180016a86  mov     rcx, rsi
0x180016a89  mov     rax, [rax+10h]
0x180016a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a92  call    cs:__imp_GetLastError
0x180016a98  mov     ebx, eax
0x180016a9a  test    eax, eax
0x180016a9c  jle     short loc_180016AA7
0x180016a9e  movzx   ebx, ax
0x180016aa1  or      ebx, 80070000h
0x180016aa7  test    ebx, ebx
0x180016aa9  jns     short loc_180016AE6
0x180016aab  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ab2  lea     rax, WPP_GLOBAL_Control
0x180016ab9  cmp     rcx, rax
0x180016abc  jz      short loc_180016AE6
0x180016abe  test    byte ptr [rcx+1Ch], 8
0x180016ac2  jz      short loc_180016AE6
0x180016ac4  cmp     byte ptr [rcx+19h], 2
0x180016ac8  jb      short loc_180016AE6
0x180016aca  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180016acf  mov     edx, 70h ; 'p'
0x180016ad4  mov     [rsp+48h+var_20], ebx
0x180016ad8  lea     rcx, aReadfileexFail; "ReadFileEx failed"
0x180016adf  jmp     loc_1800168E6
0x180016ae4  xor     ebx, ebx
0x180016ae6  lea     rcx, [rsp+48h+arg_10]; this
0x180016aeb  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180016af0  lea     rcx, [rsp+48h+arg_0]
0x180016af5  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x180016afa  mov     eax, ebx
0x180016afc  mov     rbx, [rsp+48h+arg_18]
0x180016b01  add     rsp, 30h
0x180016b05  pop     rdi
0x180016b06  pop     rsi
0x180016b07  pop     rbp
0x180016b08  retn
```
