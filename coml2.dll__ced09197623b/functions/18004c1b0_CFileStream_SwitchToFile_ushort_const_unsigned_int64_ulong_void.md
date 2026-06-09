# CFileStream::SwitchToFile(ushort const *,unsigned __int64,ulong,void *)

- ea: `0x18004c1b0`
- end: `0x18004c595`
- name: `?SwitchToFile@CFileStream@@UEAAJPEBG_KKPEAX@Z`
- size: `997`
- prototype: `int(CFileStream *__hidden this, const unsigned __int16 *, unsigned __int64, unsigned int, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x18001defc`
- `0x18001e2f0`
- `0x180025154`
- `0x180025768`
- `0x180025a10`
- `0x180026bc4`
- `0x180034518`
- `0x180034df4`
- `0x18003f858`
- `0x180042800`
- `0x18004c1b0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c24e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c4d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c24e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c4d8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004c3aa`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004c3aa`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004c432`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004c4b5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004c554`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004c432`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004c4b5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004c554`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c4fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c4fe`

## pseudocode

```c
__int64 __fastcall CFileStream::SwitchToFile(
        CFileStream *this,
        const unsigned __int16 *a2,
        __int64 a3,
        DWORD a4,
        void *a5)
{
  CFileStream *v5; // rsi
  CContextList *v7; // rcx
  int inited; // ebx
  DWORD LastError; // eax
  CGlobalFileStream *v13; // rcx
  void *v14; // r12
  LONG v15; // ebx
  __int64 v16; // rax
  DWORD v17; // r13d
  unsigned __int64 v18; // rdx
  int v19; // r15d
  LPVOID v20; // rbx
  DWORD v21; // eax
  const unsigned __int16 *v22; // rdx
  void *v23; // rcx
  DWORD v24; // eax
  __int64 v25; // rcx
  DWORD v27; // eax
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rcx
  void *v30; // rcx
  DWORD v31; // eax
  __int64 v32; // rcx
  LONG v33[2]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v34; // [rsp+38h] [rbp-C8h]
  DWORD NumberOfBytesRead; // [rsp+3Ch] [rbp-C4h] BYREF
  LONG DistanceToMoveHigh[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v38[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v39[264]; // [rsp+260h] [rbp+160h] BYREF

  v5 = (CFileStream *)((char *)this - 8);
  lpBuffer = a5;
  NumberOfBytesRead = 0;
  v7 = (CContextList *)*((_QWORD *)this + 5);
  v34 = 0;
  *(_QWORD *)DistanceToMoveHigh = 0;
  if ( CContextList::CountContexts(v7) != 1 )
  {
    inited = -2147286776;
LABEL_41:
    v30 = (void *)*((_QWORD *)this + 7);
    v33[1] = 0;
    v31 = SetFilePointer(v30, 0, &v33[1], 1u);
    v32 = *((_QWORD *)this + 5);
    v33[0] = v31;
    if ( v32 )
      *(_QWORD *)(v32 + 48) = *(_QWORD *)v33;
    return (unsigned int)inited;
  }
  inited = CFileStream::TurnOffMapping(v5, 1);
  if ( inited < 0 )
    goto LABEL_41;
  if ( CFileStream::SeekTo(v5, 0) == 0xFFFFFFFF )
  {
    LastError = GetLastError();
    inited = Win32ErrorToScode(LastError);
    goto LABEL_41;
  }
  StringCbCopyW(v39, 0x20Au, (const unsigned __int16 *)(*((_QWORD *)this + 5) + 72LL));
  v13 = (CGlobalFileStream *)*((_QWORD *)this + 5);
  v14 = (void *)*((_QWORD *)this + 7);
  v15 = *((_DWORD *)v13 + 9);
  v33[0] = v15;
  CGlobalFileStream::SetName(v13, 0);
  *(_DWORD *)(*((_QWORD *)this + 5) + 60LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 5) + 64LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 5) + 68LL) = 0;
  v16 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 7) = -1;
  *(_DWORD *)(v16 + 36) = v15 & 0xFFFFFFC8 | 4;
  if ( (int)StringCbCopyW(v38, 0x20Au, a2) < 0 )
  {
    inited = -2147287031;
    goto LABEL_39;
  }
  inited = CFileStream::InitWorker(v5, v38, 0, 0);
  if ( inited < 0 )
  {
LABEL_39:
    v29 = *((_QWORD *)this + 5);
    *((_QWORD *)this + 7) = v14;
    if ( v29 )
    {
      StringCbCopyW((unsigned __int16 *)(v29 + 72), 0x20Au, v39);
      *(_DWORD *)(*((_QWORD *)this + 5) + 36LL) = v33[0];
    }
    goto LABEL_41;
  }
  inited = (*(__int64 (__fastcall **)(CFileStream *, __int64))(*(_QWORD *)v5 + 48LL))(v5, a3);
  if ( inited < 0 )
  {
LABEL_38:
    CFileStream::TurnOffMapping(v5, 0);
    UnProtectHandle(*((HANDLE *)this + 7));
    CloseHandle(*((HANDLE *)this + 7));
    CFileStream::DeleteTheFile(v5, v28);
    goto LABEL_39;
  }
  if ( CFileStream::SeekTo(v5, 0) == 0xFFFFFFFF )
  {
LABEL_37:
    v27 = GetLastError();
    inited = Win32ErrorToScode(v27);
    goto LABEL_38;
  }
  v17 = 0;
  v18 = 0;
  *(_QWORD *)DistanceToMoveHigh = 0;
  while ( 1 )
  {
    if ( v18 + a4 <= 0x7FFFFF00 || v18 > 0x7FFFFFE3 )
    {
      v19 = 0;
    }
    else
    {
      v17 = a4;
      if ( ((*(_DWORD *)(*((_QWORD *)this + 5) + 32LL) & 0x80000) != 0 ? 2147479552 : 2147483136) - (int)v18 > a4 )
      {
        inited = -2147418113;
        goto LABEL_38;
      }
      v19 = 1;
      a4 = ((*(_DWORD *)(*((_QWORD *)this + 5) + 32LL) & 0x80000) != 0 ? 2147479552 : 2147483136) - v18;
    }
    if ( !a4 )
      goto LABEL_23;
    v20 = lpBuffer;
    if ( !ReadFile(v14, lpBuffer, a4, &NumberOfBytesRead, 0) )
      goto LABEL_37;
    if ( !NumberOfBytesRead )
      break;
    inited = (*(__int64 (__fastcall **)(CFileStream *, _QWORD, LPVOID))(*(_QWORD *)v5 + 32LL))(
               v5,
               *(_QWORD *)DistanceToMoveHigh,
               v20);
    if ( inited < 0 )
      goto LABEL_38;
    if ( v34 != NumberOfBytesRead )
    {
      inited = -2147287011;
      goto LABEL_38;
    }
    v18 = *(_QWORD *)DistanceToMoveHigh;
LABEL_23:
    if ( v19 )
    {
      a4 = v17;
      v34 = v17;
    }
    v18 += v34;
    *(_QWORD *)DistanceToMoveHigh = v18;
    if ( v19 )
    {
      if ( SetFilePointer(v14, v18, &DistanceToMoveHigh[1], 0) == -1 )
      {
        v21 = GetLastError();
        inited = Win32ErrorToScode(v21);
        if ( inited < 0 )
          goto LABEL_38;
        v18 = *(_QWORD *)DistanceToMoveHigh;
      }
      else
      {
        v18 = *(_QWORD *)DistanceToMoveHigh;
      }
    }
  }
  UnProtectHandle(v14);
  CloseHandle(v14);
  if ( (v33[0] & 0x10) != 0 )
    CFileStream::DeleteTheFile(v5, v22);
  v23 = (void *)*((_QWORD *)this + 7);
  v33[1] = 0;
  v24 = SetFilePointer(v23, 0, &v33[1], 1u);
  v25 = *((_QWORD *)this + 5);
  v33[0] = v24;
  if ( v25 )
    *(_QWORD *)(v25 + 48) = *(_QWORD *)v33;
  return 0;
}

```

## disassembly

```asm
0x18004c1b0  push    rbp
0x18004c1b2  push    rbx
0x18004c1b3  push    rsi
0x18004c1b4  push    rdi
0x18004c1b5  push    r12
0x18004c1b7  push    r13
0x18004c1b9  push    r14
0x18004c1bb  push    r15
0x18004c1bd  lea     rbp, [rsp-388h]
0x18004c1c5  sub     rsp, 488h
0x18004c1cc  mov     rax, cs:__security_cookie
0x18004c1d3  xor     rax, rsp
0x18004c1d6  mov     [rbp+3C0h+var_50], rax
0x18004c1dd  mov     rax, [rbp+3C0h+arg_20]
0x18004c1e4  lea     rsi, [rcx-8]
0x18004c1e8  xor     r12d, r12d
0x18004c1eb  mov     [rsp+4C0h+lpBuffer], rax
0x18004c1f0  mov     rdi, rcx
0x18004c1f3  mov     [rsp+4C0h+NumberOfBytesRead], r12d
0x18004c1f8  mov     rcx, [rsi+30h]; this
0x18004c1fc  mov     r14d, r9d
0x18004c1ff  mov     r15, r8
0x18004c202  mov     [rsp+4C0h+var_488], r12d
0x18004c207  mov     r13, rdx
0x18004c20a  mov     qword ptr [rsp+4C0h+DistanceToMoveHigh], r12
0x18004c20f  call    ?CountContexts@CContextList@@QEAAKXZ; CContextList::CountContexts(void)
0x18004c214  cmp     eax, 1
0x18004c217  jz      short loc_18004C223
0x18004c219  mov     ebx, 80030108h
0x18004c21e  jmp     loc_18004C53A
0x18004c223  mov     edx, 1; int
0x18004c228  mov     rcx, rsi; this
0x18004c22b  call    ?TurnOffMapping@CFileStream@@AEAAJH@Z; CFileStream::TurnOffMapping(int)
0x18004c230  mov     ebx, eax
0x18004c232  test    eax, eax
0x18004c234  js      loc_18004C53A
0x18004c23a  xor     edx, edx; unsigned __int64
0x18004c23c  mov     rcx, rsi; this
0x18004c23f  call    ?SeekTo@CFileStream@@AEAA_K_K@Z; CFileStream::SeekTo(unsigned __int64)
0x18004c244  mov     ecx, 0FFFFFFFFh
0x18004c249  cmp     rax, rcx
0x18004c24c  jnz     short loc_18004C262
0x18004c24e  call    cs:__imp_GetLastError
0x18004c254  mov     ecx, eax; unsigned int
0x18004c256  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004c25b  mov     ebx, eax
0x18004c25d  jmp     loc_18004C53A
0x18004c262  mov     r8, [rdi+28h]
0x18004c266  lea     rcx, [rbp+3C0h+var_260]; unsigned __int16 *
0x18004c26d  add     r8, 48h ; 'H'; unsigned __int16 *
0x18004c271  mov     edx, 20Ah; unsigned __int64
0x18004c276  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18004c27b  mov     rcx, [rdi+28h]; this
0x18004c27f  xor     edx, edx; unsigned __int16 *
0x18004c281  mov     r12, [rdi+38h]
0x18004c285  mov     ebx, [rcx+24h]
0x18004c288  mov     [rsp+4C0h+var_490], ebx
0x18004c28c  call    ?SetName@CGlobalFileStream@@QEAAXPEBG@Z; CGlobalFileStream::SetName(ushort const *)
0x18004c291  mov     r11, [rdi+28h]
0x18004c295  xor     ecx, ecx
0x18004c297  mov     r8, r13; unsigned __int16 *
0x18004c29a  mov     edx, 20Ah; unsigned __int64
0x18004c29f  mov     [r11+3Ch], ecx
0x18004c2a3  mov     rax, [rdi+28h]
0x18004c2a7  mov     [rax+40h], ecx
0x18004c2aa  mov     rax, [rdi+28h]
0x18004c2ae  mov     [rax+44h], ecx
0x18004c2b1  mov     ecx, ebx
0x18004c2b3  mov     rax, [rdi+28h]
0x18004c2b7  and     ecx, 0FFFFFFCCh
0x18004c2ba  or      ecx, 4
0x18004c2bd  mov     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFFFh
0x18004c2c5  mov     [rax+24h], ecx
0x18004c2c8  lea     rcx, [rsp+4C0h+var_470]; unsigned __int16 *
0x18004c2cd  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18004c2d2  test    eax, eax
0x18004c2d4  jns     short loc_18004C2E0
0x18004c2d6  mov     ebx, 80030009h
0x18004c2db  jmp     loc_18004C50C
0x18004c2e0  xor     r9d, r9d; void *
0x18004c2e3  lea     rdx, [rsp+4C0h+var_470]; unsigned __int16 *
0x18004c2e8  xor     r8d, r8d; unsigned int
0x18004c2eb  mov     rcx, rsi; this
0x18004c2ee  call    ?InitWorker@CFileStream@@AEAAJPEBGKPEAX@Z; CFileStream::InitWorker(ushort const *,ulong,void *)
0x18004c2f3  mov     ebx, eax
0x18004c2f5  test    eax, eax
0x18004c2f7  js      loc_18004C50C
0x18004c2fd  mov     rax, [rsi]
0x18004c300  mov     rdx, r15
0x18004c303  mov     rcx, rsi
0x18004c306  mov     rax, [rax+30h]
0x18004c30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c30f  mov     ebx, eax
0x18004c311  test    eax, eax
0x18004c313  js      loc_18004C4E7
0x18004c319  xor     edx, edx; unsigned __int64
0x18004c31b  mov     rcx, rsi; this
0x18004c31e  call    ?SeekTo@CFileStream@@AEAA_K_K@Z; CFileStream::SeekTo(unsigned __int64)
0x18004c323  mov     ebx, 0FFFFFFFFh
0x18004c328  cmp     rax, rbx
0x18004c32b  jz      loc_18004C4D8
0x18004c331  xor     r13d, r13d
0x18004c334  xor     edx, edx
0x18004c336  mov     qword ptr [rsp+4C0h+DistanceToMoveHigh], rdx
0x18004c33b  mov     eax, r14d
0x18004c33e  add     rax, rdx
0x18004c341  cmp     rax, 7FFFFF00h
0x18004c347  jbe     short loc_18004C386
0x18004c349  cmp     rdx, 7FFFFFE3h
0x18004c350  ja      short loc_18004C386
0x18004c352  mov     rax, [rdi+28h]
0x18004c356  mov     r13d, r14d
0x18004c359  mov     ecx, [rax+20h]
0x18004c35c  and     ecx, 80000h
0x18004c362  neg     ecx
0x18004c364  sbb     eax, eax
0x18004c366  and     eax, 0FFFFF200h
0x18004c36b  add     eax, 7FFFFE00h
0x18004c370  sub     eax, edx
0x18004c372  cmp     eax, r14d
0x18004c375  ja      loc_18004C46C
0x18004c37b  mov     r15d, 1
0x18004c381  mov     r14d, eax
0x18004c384  jmp     short loc_18004C389
0x18004c386  xor     r15d, r15d
0x18004c389  test    r14d, r14d
0x18004c38c  jz      short loc_18004C405
0x18004c38e  mov     rbx, [rsp+4C0h+lpBuffer]
0x18004c393  lea     r9, [rsp+4C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004c398  mov     rdx, rbx; lpBuffer
0x18004c39b  mov     [rsp+4C0h+lpOverlapped], 0; lpOverlapped
0x18004c3a4  mov     r8d, r14d; nNumberOfBytesToRead
0x18004c3a7  mov     rcx, r12; hFile
0x18004c3aa  call    cs:__imp_ReadFile
0x18004c3b0  test    eax, eax
0x18004c3b2  jz      loc_18004C4D8
0x18004c3b8  mov     r9d, [rsp+4C0h+NumberOfBytesRead]
0x18004c3bd  test    r9d, r9d
0x18004c3c0  jz      loc_18004C47A
0x18004c3c6  mov     rax, [rsi]
0x18004c3c9  lea     rcx, [rsp+4C0h+var_488]
0x18004c3ce  mov     rdx, qword ptr [rsp+4C0h+DistanceToMoveHigh]
0x18004c3d3  mov     r8, rbx
0x18004c3d6  mov     [rsp+4C0h+lpOverlapped], rcx
0x18004c3db  mov     rcx, rsi
0x18004c3de  mov     rax, [rax+20h]
0x18004c3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3e7  mov     ebx, eax
0x18004c3e9  test    eax, eax
0x18004c3eb  js      loc_18004C4E7
0x18004c3f1  mov     eax, [rsp+4C0h+NumberOfBytesRead]
0x18004c3f5  cmp     [rsp+4C0h+var_488], eax
0x18004c3f9  jnz     short loc_18004C473
0x18004c3fb  mov     rdx, qword ptr [rsp+4C0h+DistanceToMoveHigh]
0x18004c400  mov     ebx, 0FFFFFFFFh
0x18004c405  test    r15d, r15d
0x18004c408  jz      short loc_18004C412
0x18004c40a  mov     r14d, r13d
0x18004c40d  mov     [rsp+4C0h+var_488], r13d
0x18004c412  mov     eax, [rsp+4C0h+var_488]
0x18004c416  add     rdx, rax; lDistanceToMove
0x18004c419  mov     qword ptr [rsp+4C0h+DistanceToMoveHigh], rdx
0x18004c41e  test    r15d, r15d
0x18004c421  jz      loc_18004C33B
0x18004c427  xor     r9d, r9d; dwMoveMethod
0x18004c42a  lea     r8, [rsp+4C0h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18004c42f  mov     rcx, r12; hFile
0x18004c432  call    cs:__imp_SetFilePointer
0x18004c438  cmp     eax, ebx
0x18004c43a  jz      short loc_18004C446
0x18004c43c  mov     rdx, qword ptr [rsp+4C0h+DistanceToMoveHigh]
0x18004c441  jmp     loc_18004C33B
0x18004c446  call    cs:__imp_GetLastError
0x18004c44c  mov     ecx, eax; unsigned int
0x18004c44e  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004c453  mov     ebx, eax
0x18004c455  test    eax, eax
0x18004c457  js      loc_18004C4E7
0x18004c45d  mov     rdx, qword ptr [rsp+4C0h+DistanceToMoveHigh]
0x18004c462  mov     ebx, 0FFFFFFFFh
0x18004c467  jmp     loc_18004C33B
0x18004c46c  mov     ebx, 8000FFFFh
0x18004c471  jmp     short loc_18004C4E7
0x18004c473  mov     ebx, 8003001Dh
0x18004c478  jmp     short loc_18004C4E7
0x18004c47a  mov     rcx, r12; ObjectHandle
0x18004c47d  call    ?UnProtectHandle@@YAJPEAX@Z; UnProtectHandle(void *)
0x18004c482  mov     rcx, r12; hObject
0x18004c485  call    cs:__imp_CloseHandle
0x18004c48b  mov     eax, [rsp+4C0h+var_490]
0x18004c48f  test    al, 10h
0x18004c491  jz      short loc_18004C49B
0x18004c493  mov     rcx, rsi; this
0x18004c496  call    ?DeleteTheFile@CFileStream@@AEAAHPEBG@Z; CFileStream::DeleteTheFile(ushort const *)
0x18004c49b  mov     rcx, [rdi+38h]; hFile
0x18004c49f  lea     r8, [rsp+4C0h+var_490+4]; lpDistanceToMoveHigh
0x18004c4a4  mov     r9d, 1; dwMoveMethod
0x18004c4aa  mov     qword ptr [rsp+4C0h+var_490], 0
0x18004c4b3  xor     edx, edx; lDistanceToMove
0x18004c4b5  call    cs:__imp_SetFilePointer
0x18004c4bb  mov     rcx, [rdi+28h]
0x18004c4bf  mov     [rsp+4C0h+var_490], eax
0x18004c4c3  test    rcx, rcx
0x18004c4c6  jz      short loc_18004C4D1
0x18004c4c8  mov     rax, qword ptr [rsp+4C0h+var_490]
0x18004c4cd  mov     [rcx+30h], rax
0x18004c4d1  xor     eax, eax
0x18004c4d3  jmp     loc_18004C572
0x18004c4d8  call    cs:__imp_GetLastError
0x18004c4de  mov     ecx, eax; unsigned int
0x18004c4e0  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004c4e5  mov     ebx, eax
0x18004c4e7  xor     edx, edx; int
0x18004c4e9  mov     rcx, rsi; this
0x18004c4ec  call    ?TurnOffMapping@CFileStream@@AEAAJH@Z; CFileStream::TurnOffMapping(int)
0x18004c4f1  mov     rcx, [rdi+38h]; ObjectHandle
0x18004c4f5  call    ?UnProtectHandle@@YAJPEAX@Z; UnProtectHandle(void *)
0x18004c4fa  mov     rcx, [rdi+38h]; hObject
0x18004c4fe  call    cs:__imp_CloseHandle
0x18004c504  mov     rcx, rsi; this
0x18004c507  call    ?DeleteTheFile@CFileStream@@AEAAHPEBG@Z; CFileStream::DeleteTheFile(ushort const *)
0x18004c50c  mov     rcx, [rdi+28h]
0x18004c510  mov     [rdi+38h], r12
0x18004c514  test    rcx, rcx
0x18004c517  jz      short loc_18004C53A
0x18004c519  add     rcx, 48h ; 'H'; unsigned __int16 *
0x18004c51d  lea     r8, [rbp+3C0h+var_260]; unsigned __int16 *
0x18004c524  mov     edx, 20Ah; unsigned __int64
0x18004c529  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18004c52e  mov     r11, [rdi+28h]
0x18004c532  mov     eax, [rsp+4C0h+var_490]
0x18004c536  mov     [r11+24h], eax
0x18004c53a  mov     rcx, [rdi+38h]; hFile
0x18004c53e  lea     r8, [rsp+4C0h+var_490+4]; lpDistanceToMoveHigh
0x18004c543  mov     r9d, 1; dwMoveMethod
0x18004c549  mov     qword ptr [rsp+4C0h+var_490], 0
0x18004c552  xor     edx, edx; lDistanceToMove
0x18004c554  call    cs:__imp_SetFilePointer
0x18004c55a  mov     rcx, [rdi+28h]
0x18004c55e  mov     [rsp+4C0h+var_490], eax
0x18004c562  test    rcx, rcx
0x18004c565  jz      short loc_18004C570
0x18004c567  mov     rax, qword ptr [rsp+4C0h+var_490]
0x18004c56c  mov     [rcx+30h], rax
0x18004c570  mov     eax, ebx
0x18004c572  mov     rcx, [rbp+3C0h+var_50]
0x18004c579  xor     rcx, rsp; StackCookie
0x18004c57c  call    __security_check_cookie
0x18004c581  add     rsp, 488h
0x18004c588  pop     r15
0x18004c58a  pop     r14
0x18004c58c  pop     r13
0x18004c58e  pop     r12
0x18004c590  pop     rdi
0x18004c591  pop     rsi
0x18004c592  pop     rbx
0x18004c593  pop     rbp
0x18004c594  retn
```
