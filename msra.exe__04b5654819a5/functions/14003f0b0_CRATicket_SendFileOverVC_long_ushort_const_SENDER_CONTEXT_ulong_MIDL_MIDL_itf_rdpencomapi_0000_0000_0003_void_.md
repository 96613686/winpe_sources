# CRATicket::SendFileOverVC(long,ushort const *,SENDER_CONTEXT,ulong,__MIDL___MIDL_itf_rdpencomapi_0000_0000_0003,void *,RAFileXferClient *,CFileWorkItem * *,RAXferWorker * *)

- ea: `0x14003f0b0`
- end: `0x14003f44d`
- name: `?SendFileOverVC@CRATicket@@AEAAJJPEBGUSENDER_CONTEXT@@KW4__MIDL___MIDL_itf_rdpencomapi_0000_0000_0003@@PEAXPEAVRAFileXferClient@@PEAPEAVCFileWorkItem@@PEAPEAVRAXferWorker@@@Z`
- size: `925`
- prototype: `int __high(int, const unsigned __int16 *, struct SENDER_CONTEXT, unsigned int, enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0003, void *, struct RAFileXferClient *, struct CFileWorkItem **, struct RAXferWorker **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140044508`

## callees

- `0x140001cc4`
- `0x140008088`
- `0x140034ce4`
- `0x14003f0b0`
- `0x140046428`
- `0x1400492ec`
- `0x14004991c`
- `0x1400499ec`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14003f20a`
- `KERNEL32!CreateFileW` at `0x14003f20a`
- `KERNEL32!CloseHandle` at `0x14003f3e6`
- `KERNEL32!CloseHandle` at `0x14003f3e6`
- `KERNEL32!CreateTimerQueueTimer` at `0x14003f34f`
- `KERNEL32!CreateTimerQueueTimer` at `0x14003f34f`
- `msvcrt!malloc` at `0x14003f299`
- `msvcrt!malloc` at `0x14003f299`
- `msvcrt!free` at `0x14003f391`
- `msvcrt!free` at `0x14003f391`
- `SHLWAPI!PathFindFileNameW` at `0x14003f22c`
- `SHLWAPI!PathFindFileNameW` at `0x14003f22c`

## pseudocode

```c
__int64 __fastcall CRATicket::SendFileOverVC(
        CEventLogger *a1,
        int a2,
        const WCHAR *a3,
        signed int *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        _QWORD *a10)
{
  unsigned int v11; // ebx
  __int64 v12; // rsi
  char *v13; // rax
  __int64 v14; // rcx
  char *v15; // rdi
  __int64 v16; // rcx
  _BYTE *v17; // rax
  _BYTE *v18; // rax
  HANDLE FileW; // r14
  LPWSTR FileNameW; // rax
  const unsigned __int16 *v21; // r15
  __int64 v22; // rcx
  __int64 v23; // r8
  unsigned __int64 v24; // rbx
  size_t v25; // rcx
  unsigned __int16 *v26; // rax
  unsigned __int16 *v27; // rbp
  __int128 v28; // xmm0
  signed int v29; // eax
  CEventLogger *v30; // rcx

  if ( !a3 )
  {
    v11 = -2147467261;
    CEventLogger::LogError(
      a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      0x1BA8u,
      L"CRATicket::SendFileOverVC",
      0x80004003);
    return v11;
  }
  if ( !a9 )
  {
    v11 = -2147467261;
    CEventLogger::LogError(
      a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      0x1BA9u,
      L"CRATicket::SendFileOverVC",
      0x80004003);
    return v11;
  }
  if ( !a10 )
  {
    v11 = -2147467261;
    CEventLogger::LogError(
      a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      0x1BAAu,
      L"CRATicket::SendFileOverVC",
      0x80004003);
    return v11;
  }
  if ( !a8 )
  {
    v11 = -2147467261;
    CEventLogger::LogError(
      a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      0x1BABu,
      L"CRATicket::SendFileOverVC",
      0x80004003);
    return v11;
  }
  v12 = *((_QWORD *)a1 + 58);
  if ( !v12 )
    return (unsigned int)-2147467259;
  v13 = (char *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v13;
  if ( !v13 )
    goto LABEL_41;
  *((_DWORD *)v13 + 5) = 0;
  *(_QWORD *)v13 = &CWorkItem::`vftable';
  v16 = 64;
  *((_DWORD *)v13 + 4) = 0;
  *(_QWORD *)v13 = &CFileWorkItem::`vftable';
  v17 = v13 + 32;
  *((_QWORD *)v15 + 3) = 0;
  do
  {
    *v17++ = 0;
    --v16;
  }
  while ( v16 );
  v14 = 16;
  v18 = v15 + 96;
  do
  {
    *v18++ = 0;
    --v14;
  }
  while ( v14 );
  *((_QWORD *)v15 + 14) = 0;
  if ( !v15 )
  {
LABEL_41:
    v11 = -2147024882;
    CEventLogger::LogError(
      (CEventLogger *)v14,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      0x1BB6u,
      L"CRATicket::SendFileOverVC",
      0x8007000E);
    return v11;
  }
  FileW = CreateFileW(a3, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v11 = -2147024890;
LABEL_40:
    ReleaseFileItemMemory((struct CFileWorkItem *)v15);
    return v11;
  }
  FileNameW = PathFindFileNameW(a3);
  v21 = FileNameW;
  if ( !FileNameW )
  {
    v11 = -2147024809;
LABEL_38:
    if ( FileW )
    {
      CloseHandle(FileW);
      *((_QWORD *)v15 + 5) = 0;
    }
    goto LABEL_40;
  }
  v22 = 260;
  do
  {
    if ( !*FileNameW )
      break;
    ++FileNameW;
    --v22;
  }
  while ( v22 );
  v11 = v22 == 0 ? 0x80070057 : 0;
  v23 = (260 - v22) & -(__int64)(v22 != 0);
  if ( !v22 )
    goto LABEL_38;
  v24 = v23 + 1;
  v25 = 2 * (v23 + 1);
  if ( v25 < v23 + 1 )
  {
    v11 = -2147467259;
    goto LABEL_38;
  }
  v26 = (unsigned __int16 *)malloc(v25);
  v27 = v26;
  if ( !v26 )
  {
    v11 = -2147024882;
    goto LABEL_38;
  }
  v11 = StringCchCopyW(v26, v24, v21);
  if ( (v11 & 0x80000000) != 0 )
  {
LABEL_32:
    free(v27);
    *((_QWORD *)v15 + 6) = 0;
    goto LABEL_38;
  }
  *((_DWORD *)v15 + 8) = a2;
  v28 = *(_OWORD *)a4;
  *((_QWORD *)v15 + 11) = a7;
  *((_DWORD *)v15 + 21) = a4[1];
  *((_QWORD *)v15 + 14) = a8;
  v29 = *a4;
  *((_QWORD *)v15 + 5) = FileW;
  *((_QWORD *)v15 + 6) = v27;
  *((_QWORD *)v15 + 7) = 0;
  *((_QWORD *)v15 + 8) = 0;
  *((_QWORD *)v15 + 9) = 1;
  *((_DWORD *)v15 + 20) = 0;
  *((_OWORD *)v15 + 6) = v28;
  if ( v29 > 0 && !CreateTimerQueueTimer((PHANDLE)v15 + 3, *(HANDLE *)(v12 + 600), FileXferTimerOut, v15, v29, 0, 0) )
  {
    CEventLogger::LogError(
      v30,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      0x1C03u,
      L"CRATicket::SendFileOverVC",
      0);
    v11 = -2147467259;
    goto LABEL_32;
  }
  *a9 = v15;
  *a10 = v12;
  RAXferWorker::InsertToInternalWorkList((RAXferWorker *)v12, (struct CWorkItem *)v15);
  if ( !*(_QWORD *)(v12 + 608) && (int)RAXferWorker::SendOneCommandOverFileChannel((RAXferWorker *)v12) < 0 )
    RAXferWorker::PrepareOneItemToProcess((RAXferWorker *)v12);
  return 0;
}

```

## disassembly

```asm
0x14003f0b0  mov     rax, rsp
0x14003f0b3  mov     [rax+8], rbx
0x14003f0b7  mov     [rax+20h], r9
0x14003f0bb  mov     [rax+10h], edx
0x14003f0be  push    rbp
0x14003f0bf  push    rsi
0x14003f0c0  push    rdi
0x14003f0c1  push    r12
0x14003f0c3  push    r13
0x14003f0c5  push    r14
0x14003f0c7  push    r15
0x14003f0c9  sub     rsp, 40h
0x14003f0cd  xor     ebp, ebp
0x14003f0cf  mov     rbx, r8
0x14003f0d2  test    r8, r8
0x14003f0d5  jnz     short loc_14003F0EE
0x14003f0d7  mov     ebx, 80004003h
0x14003f0dc  mov     dword ptr [rax-50h], 80004003h
0x14003f0e3  mov     r9d, 1BA8h
0x14003f0e9  jmp     loc_14003F413
0x14003f0ee  mov     r12, [rsp+78h+arg_40]
0x14003f0f6  test    r12, r12
0x14003f0f9  jnz     short loc_14003F113
0x14003f0fb  mov     ebx, 80004003h
0x14003f100  mov     [rsp+78h+dwFlagsAndAttributes], 80004003h
0x14003f108  mov     r9d, 1BA9h
0x14003f10e  jmp     loc_14003F413
0x14003f113  mov     r13, [rsp+78h+arg_48]
0x14003f11b  test    r13, r13
0x14003f11e  jnz     short loc_14003F138
0x14003f120  mov     ebx, 80004003h
0x14003f125  mov     [rsp+78h+dwFlagsAndAttributes], 80004003h
0x14003f12d  mov     r9d, 1BAAh
0x14003f133  jmp     loc_14003F413
0x14003f138  cmp     [rsp+78h+arg_38], rbp
0x14003f140  jnz     short loc_14003F15A
0x14003f142  mov     ebx, 80004003h
0x14003f147  mov     [rsp+78h+dwFlagsAndAttributes], 80004003h
0x14003f14f  mov     r9d, 1BABh
0x14003f155  jmp     loc_14003F413
0x14003f15a  mov     rsi, [rcx+1D0h]
0x14003f161  test    rsi, rsi
0x14003f164  jnz     short loc_14003F170
0x14003f166  mov     ebx, 80004005h
0x14003f16b  jmp     loc_14003F432
0x14003f170  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003f177  mov     ecx, 80h; unsigned __int64
0x14003f17c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003f181  mov     [rsp+78h+arg_10], rax
0x14003f189  mov     rdi, rax
0x14003f18c  test    rax, rax
0x14003f18f  jz      loc_14003F400
0x14003f195  lea     rax, ??_7CWorkItem@@6B@; const CWorkItem::`vftable'
0x14003f19c  mov     [rdi+14h], ebp
0x14003f19f  mov     [rdi], rax
0x14003f1a2  mov     ecx, 40h ; '@'
0x14003f1a7  lea     rax, ??_7CFileWorkItem@@6B@; const CFileWorkItem::`vftable'
0x14003f1ae  mov     [rdi+10h], ebp
0x14003f1b1  mov     [rdi], rax
0x14003f1b4  lea     rax, [rdi+20h]
0x14003f1b8  mov     [rdi+18h], rbp
0x14003f1bc  mov     [rax], bpl
0x14003f1bf  inc     rax
0x14003f1c2  sub     rcx, 1
0x14003f1c6  jnz     short loc_14003F1BC
0x14003f1c8  mov     ecx, 10h
0x14003f1cd  lea     rax, [rdi+60h]
0x14003f1d1  mov     [rax], bpl
0x14003f1d4  inc     rax
0x14003f1d7  sub     rcx, 1
0x14003f1db  jnz     short loc_14003F1D1
0x14003f1dd  mov     [rdi+70h], rbp
0x14003f1e1  test    rdi, rdi
0x14003f1e4  jz      loc_14003F400
0x14003f1ea  mov     [rsp+78h+hTemplateFile], rbp; hTemplateFile
0x14003f1ef  lea     r8d, [rcx+1]; dwShareMode
0x14003f1f3  mov     [rsp+78h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x14003f1f7  mov     rcx, rbx; lpFileName
0x14003f1fa  xor     r9d, r9d; lpSecurityAttributes
0x14003f1fd  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x14003f205  mov     edx, 80000000h; dwDesiredAccess
0x14003f20a  call    cs:__imp_CreateFileW
0x14003f211  nop     dword ptr [rax+rax+00h]
0x14003f216  mov     r14, rax
0x14003f219  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003f21d  jnz     short loc_14003F229
0x14003f21f  mov     ebx, 80070006h
0x14003f224  jmp     loc_14003F3F6
0x14003f229  mov     rcx, rbx; pszPath
0x14003f22c  call    cs:__imp_PathFindFileNameW
0x14003f233  nop     dword ptr [rax+rax+00h]
0x14003f238  mov     r15, rax
0x14003f23b  test    rax, rax
0x14003f23e  jz      loc_14003F3D9
0x14003f244  mov     edx, 104h
0x14003f249  mov     ecx, edx
0x14003f24b  cmp     [rax], bp
0x14003f24e  jz      short loc_14003F25A
0x14003f250  add     rax, 2
0x14003f254  sub     rcx, 1
0x14003f258  jnz     short loc_14003F24B
0x14003f25a  mov     rax, rcx
0x14003f25d  neg     rax
0x14003f260  mov     rax, rcx
0x14003f263  sbb     ebx, ebx
0x14003f265  sub     rdx, rcx
0x14003f268  not     ebx
0x14003f26a  and     ebx, 80070057h
0x14003f270  neg     rax
0x14003f273  sbb     r8, r8
0x14003f276  and     r8, rdx
0x14003f279  test    rcx, rcx
0x14003f27c  jz      loc_14003F3DE
0x14003f282  lea     rbx, [r8+1]
0x14003f286  lea     rcx, [rbx+rbx]; Size
0x14003f28a  cmp     rcx, rbx
0x14003f28d  jnb     short loc_14003F299
0x14003f28f  mov     ebx, 80004005h
0x14003f294  jmp     loc_14003F3DE
0x14003f299  call    cs:__imp_malloc
0x14003f2a0  nop     dword ptr [rax+rax+00h]
0x14003f2a5  mov     rbp, rax
0x14003f2a8  test    rax, rax
0x14003f2ab  jnz     short loc_14003F2B7
0x14003f2ad  mov     ebx, 8007000Eh
0x14003f2b2  jmp     loc_14003F3DE
0x14003f2b7  mov     r8, r15; unsigned __int16 *
0x14003f2ba  mov     rdx, rbx; unsigned __int64
0x14003f2bd  mov     rcx, rbp; unsigned __int16 *
0x14003f2c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003f2c5  xor     r15d, r15d
0x14003f2c8  mov     ebx, eax
0x14003f2ca  test    eax, eax
0x14003f2cc  js      loc_14003F38E
0x14003f2d2  mov     rcx, [rsp+78h+arg_18]
0x14003f2da  mov     eax, [rsp+78h+arg_8]
0x14003f2e1  mov     [rdi+20h], eax
0x14003f2e4  mov     rax, [rsp+78h+arg_30]
0x14003f2ec  movaps  xmm0, xmmword ptr [rcx]
0x14003f2ef  mov     [rdi+58h], rax
0x14003f2f3  mov     eax, [rcx+4]
0x14003f2f6  mov     [rdi+54h], eax
0x14003f2f9  mov     rax, [rsp+78h+arg_38]
0x14003f301  mov     [rdi+70h], rax
0x14003f305  mov     eax, [rcx]
0x14003f307  mov     [rdi+28h], r14
0x14003f30b  mov     [rdi+30h], rbp
0x14003f30f  mov     [rdi+38h], r15
0x14003f313  mov     [rdi+40h], r15
0x14003f317  mov     qword ptr [rdi+48h], 1
0x14003f31f  mov     [rdi+50h], r15d
0x14003f323  movdqu  xmmword ptr [rdi+60h], xmm0
0x14003f328  test    eax, eax
0x14003f32a  jle     short loc_14003F3A5
0x14003f32c  mov     rdx, [rsi+258h]; TimerQueue
0x14003f333  lea     rcx, [rdi+18h]; phNewTimer
0x14003f337  mov     dword ptr [rsp+78h+hTemplateFile], r15d; Flags
0x14003f33c  lea     r8, ?FileXferTimerOut@@YAXPEAXE@Z; Callback
0x14003f343  mov     [rsp+78h+dwFlagsAndAttributes], r15d; Period
0x14003f348  mov     r9, rdi; Parameter
0x14003f34b  mov     [rsp+78h+dwCreationDisposition], eax; DueTime
0x14003f34f  call    cs:__imp_CreateTimerQueueTimer
0x14003f356  nop     dword ptr [rax+rax+00h]
0x14003f35b  test    eax, eax
0x14003f35d  jnz     short loc_14003F3A5
0x14003f35f  lea     rax, aCraticketSendf; "CRATicket::SendFileOverVC"
0x14003f366  mov     [rsp+78h+dwFlagsAndAttributes], r15d; unsigned int
0x14003f36b  mov     r9d, 1C03h; unsigned int
0x14003f371  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; unsigned __int16 *
0x14003f376  lea     r8, aBaseDiagnosisR_26; "base\\diagnosis\\ra\\core\\lib\\raticke"...
0x14003f37d  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003f384  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003f389  mov     ebx, 80004005h
0x14003f38e  mov     rcx, rbp; Block
0x14003f391  call    cs:__imp_free
0x14003f398  nop     dword ptr [rax+rax+00h]
0x14003f39d  xor     ebp, ebp
0x14003f39f  mov     [rdi+30h], rbp
0x14003f3a3  jmp     short loc_14003F3DE
0x14003f3a5  mov     [r12], rdi
0x14003f3a9  mov     rdx, rdi; struct CWorkItem *
0x14003f3ac  mov     rcx, rsi; this
0x14003f3af  mov     [r13+0], rsi
0x14003f3b3  call    ?InsertToInternalWorkList@RAXferWorker@@QEAAJPEAVCWorkItem@@@Z; RAXferWorker::InsertToInternalWorkList(CWorkItem *)
0x14003f3b8  cmp     [rsi+260h], r15
0x14003f3bf  jnz     short loc_14003F3D5
0x14003f3c1  mov     rcx, rsi; this
0x14003f3c4  call    ?SendOneCommandOverFileChannel@RAXferWorker@@QEAAJXZ; RAXferWorker::SendOneCommandOverFileChannel(void)
0x14003f3c9  test    eax, eax
0x14003f3cb  jns     short loc_14003F3D5
0x14003f3cd  mov     rcx, rsi; this
0x14003f3d0  call    ?PrepareOneItemToProcess@RAXferWorker@@QEAAJXZ; RAXferWorker::PrepareOneItemToProcess(void)
0x14003f3d5  xor     eax, eax
0x14003f3d7  jmp     short loc_14003F434
0x14003f3d9  mov     ebx, 80070057h
0x14003f3de  test    r14, r14
0x14003f3e1  jz      short loc_14003F3F6
0x14003f3e3  mov     rcx, r14; hObject
0x14003f3e6  call    cs:__imp_CloseHandle
0x14003f3ed  nop     dword ptr [rax+rax+00h]
0x14003f3f2  mov     [rdi+28h], rbp
0x14003f3f6  mov     rcx, rdi; struct CFileWorkItem *
0x14003f3f9  call    ?ReleaseFileItemMemory@@YAXPEAVCFileWorkItem@@@Z; ReleaseFileItemMemory(CFileWorkItem *)
0x14003f3fe  jmp     short loc_14003F432
0x14003f400  mov     ebx, 8007000Eh
0x14003f405  mov     [rsp+78h+dwFlagsAndAttributes], 8007000Eh; unsigned int
0x14003f40d  mov     r9d, 1BB6h; unsigned int
0x14003f413  lea     rax, aCraticketSendf; "CRATicket::SendFileOverVC"
0x14003f41a  lea     r8, aBaseDiagnosisR_26; "base\\diagnosis\\ra\\core\\lib\\raticke"...
0x14003f421  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; unsigned __int16 *
0x14003f426  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003f42d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003f432  mov     eax, ebx
0x14003f434  mov     rbx, [rsp+78h+arg_0]
0x14003f43c  add     rsp, 40h
0x14003f440  pop     r15
0x14003f442  pop     r14
0x14003f444  pop     r13
0x14003f446  pop     r12
0x14003f448  pop     rdi
0x14003f449  pop     rsi
0x14003f44a  pop     rbp
0x14003f44b  retn
```
