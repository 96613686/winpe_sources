# VIDMM_GLOBAL::OpenLocalAllocation(VIDMM_GLOBAL_ALLOC *,VIDMM_PROCESS *,bool)

- ea: `0x140104c48`
- end: `0x14010516e`
- name: `?OpenLocalAllocation@VIDMM_GLOBAL@@QEAAPEAUVIDMM_LOCAL_ALLOC@@PEAUVIDMM_GLOBAL_ALLOC@@PEAVVIDMM_PROCESS@@_N@Z`
- size: `1318`
- prototype: `struct VIDMM_LOCAL_ALLOC *__fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_GLOBAL_ALLOC *, struct VIDMM_PROCESS *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14010416c`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140030ae0`
- `0x140058680`
- `0x140058760`
- `0x1400e84b4`
- `0x1400efba0`
- `0x1400f0f80`
- `0x140104c48`
- `0x14010ae1c`
- `0x140116764`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140105128`
- `ntoskrnl!KeStackAttachProcess` at `0x140105128`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14010515d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14010515d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140104c98`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140105058`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140104c98`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140105058`
- `watchdog!WdLogSingleEntry0` at `0x140104d64`
- `watchdog!WdLogSingleEntry0` at `0x140104f62`
- `watchdog!WdLogSingleEntry0` at `0x140104f81`
- `watchdog!WdLogSingleEntry0` at `0x140104fa8`
- `watchdog!WdLogSingleEntry0` at `0x140104d64`
- `watchdog!WdLogSingleEntry0` at `0x140104f62`
- `watchdog!WdLogSingleEntry0` at `0x140104f81`
- `watchdog!WdLogSingleEntry0` at `0x140104fa8`
- `watchdog!WdLogSingleEntry1` at `0x140104ff5`
- `watchdog!WdLogSingleEntry1` at `0x140104ff5`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140104c8c`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140104df1`

## string_xrefs

- `0x140104f73`: `Trying to open allocation on non graphics process.`
- `0x140104fb9`: `Trying to open a non-shareable allocation more than once.\n`
- `0x140104f92`: `Trying to open Alloc backed by ExistingSysMem from non-owner's process.`

## pseudocode

```c
struct VIDMM_LOCAL_ALLOC *__fastcall VIDMM_GLOBAL::OpenLocalAllocation(
        VIDMM_GLOBAL *this,
        char ***a2,
        struct VIDMM_PROCESS *a3,
        char a4)
{
  char **v4; // r13
  struct VIDMM_PROCESS *v6; // rbp
  struct VIDMM_GLOBAL_ALLOC *v9; // rsi
  struct VIDMM_GLOBAL_ALLOC *v10; // rdx
  VIDMM_GLOBAL *v11; // rcx
  __int64 v12; // rax
  char *v13; // rdi
  char **v14; // rax
  int v15; // ecx
  int v16; // r8d
  __int64 v17; // rax
  const wchar_t *v18; // r9
  int v19; // edx
  char v21; // al
  _DWORD *v22; // rsi
  char **v23; // r8
  char *v24; // r14
  __int64 v25; // rcx
  char **v26; // rax
  char **v27; // rax
  char **v28; // rax
  char **v29; // rcx
  struct _KAPC_STATE ApcState; // [rsp+50h] [rbp-78h] BYREF

  v4 = *a2;
  v6 = a3;
  if ( !a3 )
    v6 = (struct VIDMM_PROCESS *)*((_QWORD *)this + 4584);
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(this, a2) + 24) = a2;
    WdLogGlobalForLineNumber = 14471;
  }
  if ( !v6 )
  {
    WdLogSingleEntry0(1);
    v17 = 14482;
    v18 = L"Trying to open allocation on non graphics process.";
LABEL_40:
    v19 = 0x40000;
    goto LABEL_14;
  }
  v9 = (struct VIDMM_GLOBAL_ALLOC *)(a2 + 14);
  v10 = (struct VIDMM_GLOBAL_ALLOC *)a2[14];
  if ( v10 != (struct VIDMM_GLOBAL_ALLOC *)(a2 + 14) && (*(_DWORD *)a2[48] & 0x20000000) == 0 )
  {
    WdLogSingleEntry0(1);
    v17 = 14492;
    v18 = L"Trying to open a non-shareable allocation more than once.\n";
    goto LABEL_40;
  }
  v11 = (VIDMM_GLOBAL *)(*(_DWORD *)a2[48] & 0x20000010);
  if ( (_DWORD)v11 == 536870928 )
  {
    v27 = a2[6];
    if ( v27 )
    {
      if ( v27[1] != (char *)v6 )
      {
        if ( v6 == *((struct VIDMM_PROCESS **)this + 4584) )
          return 0;
        WdLogSingleEntry0(1);
        v17 = 14511;
        v18 = L"Trying to open Alloc backed by ExistingSysMem from non-owner's process.";
        goto LABEL_40;
      }
    }
  }
  if ( (*((_DWORD *)v6 + 38) & 0x20) != 0 )
  {
LABEL_10:
    v12 = operator new(80, 842033494, 256);
    v13 = (char *)v12;
    if ( !v12 )
    {
      _InterlockedIncrement(&dword_1400866B0);
      WdLogSingleEntry0(6);
      v17 = 14594;
      v18 = L"Couldn't allocate memory for local alloc object.";
      v19 = 262145;
LABEL_14:
      WdLogGlobalForLineNumber = v17;
      DxgkLogInternalTriageEvent(v15, v19, v16, (_DWORD)v18, v17, 0, 0, 0);
      return 0;
    }
    *(_QWORD *)v12 = a2;
    *(_QWORD *)(v12 + 8) = v6;
    *(_BYTE *)(v12 + 24) = (8 * a4) | *(_BYTE *)(v12 + 24) & 0xF7;
    *(_QWORD *)(v12 + 40) = v12 + 32;
    *(_QWORD *)(v12 + 32) = v12 + 32;
    ++*((_DWORD *)a2 + 32);
    v14 = a2[15];
    if ( *v14 != (char *)v9 )
LABEL_12:
      __fastfail(3u);
    v24 = v13 + 48;
    *((_QWORD *)v13 + 6) = v9;
    *((_QWORD *)v13 + 7) = v14;
    *v14 = v13 + 48;
    a2[15] = (char **)(v13 + 48);
    v22 = a2 + 4;
    if ( ((_DWORD)a2[4] & 0x20) != 0
      && (int)VIDMM_GLOBAL::CommitLocalBackingStore(this, (struct VIDMM_LOCAL_ALLOC *)v13) < 0 )
    {
      VIDMM_GLOBAL::UncommitLocalBackingStore(this, (struct VIDMM_LOCAL_ALLOC *)v13, 1);
      --*((_DWORD *)a2 + 32);
      v25 = *(_QWORD *)v24;
      if ( *(char **)(*(_QWORD *)v24 + 8LL) == v24 )
      {
        v26 = (char **)*((_QWORD *)v13 + 7);
        if ( *v26 == v24 )
        {
          *v26 = (char *)v25;
          *(_QWORD *)(v25 + 8) = v26;
          operator delete(v13);
          return 0;
        }
      }
      goto LABEL_12;
    }
  }
  else
  {
    while ( 1 )
    {
      if ( v10 == v9 )
        goto LABEL_10;
      v13 = (char *)v10 - 48;
      if ( *((struct VIDMM_PROCESS **)v10 - 5) == v6 )
        break;
      v10 = *(struct VIDMM_GLOBAL_ALLOC **)v10;
    }
    v21 = v13[24];
    if ( (v21 & 1) != 0 )
    {
      v13[24] = v21 & 0xFE;
      WdLogSingleEntry1(4, (char *)v10 - 48);
      WdLogGlobalForLineNumber = 14546;
      v28 = a2[6];
      if ( !v28 || ((_BYTE)v28[3] & 1) != 0 )
      {
        a2[6] = (char **)v13;
        if ( ((_DWORD)v4[8] & 1) != 0 )
          VidMmRecordAlloc(
            *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*((_DWORD *)v4 + 15) >> 2) & 0x3F)),
            v4,
            *((_QWORD *)v13 + 1),
            0);
      }
    }
    if ( g_IsInternalReleaseOrDbg )
    {
      *(_QWORD *)(WdLogNewEntry5_WdTrace(v11, v10) + 24) = v13;
      WdLogGlobalForLineNumber = 14571;
    }
    v22 = a2 + 4;
  }
  ++*((_DWORD *)v13 + 7);
  if ( (*(_DWORD *)a2[48] & 0x20000000) != 0 )
  {
    v23 = a2[6];
    if ( v23 && (*v22 & 4) == 0 )
      goto LABEL_25;
    if ( (*(_BYTE *)v22 & 0x60) == 0x60 )
    {
      VIDMM_GLOBAL::TransferAllocationDecommit(
        v11,
        (struct VIDMM_GLOBAL_ALLOC *)a2,
        (struct VIDMM_LOCAL_ALLOC *)v23,
        (struct VIDMM_LOCAL_ALLOC *)v13);
      v23 = a2[6];
    }
    if ( (*v22 & 4) != 0 && ((_DWORD)v4[8] & 1) != 0 )
    {
      VidMmRecordAlloc(
        *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*((_DWORD *)v4 + 15) >> 2) & 0x3F)),
        v4,
        v23[1],
        1);
      VidMmRecordAlloc(
        *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*((_DWORD *)v4 + 15) >> 2) & 0x3F)),
        v4,
        *((_QWORD *)v13 + 1),
        0);
    }
    *((_QWORD *)v13 + 1) = v6;
    if ( a2[6] )
    {
      *(_QWORD *)v13 = a2;
      v29 = a2[6];
      if ( ((_BYTE)v29[3] & 1) == 0 )
      {
        memset(&ApcState, 0, sizeof(ApcState));
        KeStackAttachProcess(*((PRKPROCESS *)v29[1] + 2), &ApcState);
        VIDMM_GLOBAL::CloseOneAllocation(this, (__int64 **)a2[6][4] - 5, 0, 0, 0, 0);
        KeUnstackDetachProcess(&ApcState);
      }
    }
    *v22 &= ~4u;
  }
  a2[6] = (char **)v13;
LABEL_25:
  if ( *((_DWORD *)a2 + 18) )
    (*(void (__fastcall **)(_QWORD, char **, __int64 (__fastcall *)(), __int64, _DWORD, _DWORD, _DWORD))(**(_QWORD **)(*((_QWORD *)this + 4560) + 8LL * ((*((_DWORD *)v4 + 15) >> 2) & 0x3F)) + 104LL))(
      *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*((_DWORD *)v4 + 15) >> 2) & 0x3F)),
      v4,
      AddResidencyPerfCountersCB,
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v6 + 4) + 8LL * *(unsigned int *)(*((_QWORD *)this + 3) + 240LL)) + 8LL)
    + 304LL * ((unsigned __int8)*((_DWORD *)v4 + 15) >> 2)
    + 8,
      0,
      0,
      (unsigned __int64)v4[2] >> 12);
  return (struct VIDMM_LOCAL_ALLOC *)v13;
}

```

## disassembly

```asm
0x140104c48  mov     [rsp+arg_18], rbx
0x140104c4d  push    rbp
0x140104c4e  push    rsi
0x140104c4f  push    rdi
0x140104c50  push    r12
0x140104c52  push    r13
0x140104c54  push    r14
0x140104c56  push    r15
0x140104c58  sub     rsp, 90h
0x140104c5f  mov     rax, cs:__security_cookie
0x140104c66  xor     rax, rsp
0x140104c69  mov     [rsp+0C8h+var_48], rax
0x140104c71  mov     r13, [rdx]
0x140104c74  xor     r12d, r12d
0x140104c77  mov     r14b, r9b
0x140104c7a  mov     rbp, r8
0x140104c7d  mov     rbx, rdx
0x140104c80  mov     r15, rcx
0x140104c83  test    r8, r8
0x140104c86  jz      loc_140104F51
0x140104c8c  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x140104c93  cmp     [rax], r12b
0x140104c96  jz      short loc_140104CB2
0x140104c98  call    cs:__imp_WdLogNewEntry5_WdTrace
0x140104c9f  nop     dword ptr [rax+rax+00h]
0x140104ca4  mov     [rax+18h], rbx
0x140104ca8  mov     cs:WdLogGlobalForLineNumber, 3887h
0x140104cb2  test    rbp, rbp
0x140104cb5  jz      loc_140104F5D
0x140104cbb  lea     rsi, [rbx+70h]
0x140104cbf  mov     rdx, [rsi]
0x140104cc2  cmp     rdx, rsi
0x140104cc5  jz      short loc_140104CDA
0x140104cc7  mov     rax, [rbx+180h]
0x140104cce  test    dword ptr [rax], 20000000h
0x140104cd4  jz      loc_140104FA3
0x140104cda  mov     rax, [rbx+180h]
0x140104ce1  mov     ecx, [rax]
0x140104ce3  mov     eax, 20000010h
0x140104ce8  and     ecx, eax; this
0x140104cea  cmp     ecx, eax
0x140104cec  jz      loc_140104FC2
0x140104cf2  mov     eax, [rbp+98h]
0x140104cf8  test    al, 20h
0x140104cfa  jz      loc_140104DCE
0x140104d00  mov     edx, 32306956h
0x140104d05  mov     ecx, 50h ; 'P'
0x140104d0a  mov     r8d, 100h
0x140104d10  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140104d15  mov     rdi, rax
0x140104d18  test    rax, rax
0x140104d1b  jz      short loc_140104D58
0x140104d1d  mov     [rax], rbx
0x140104d20  mov     [rax+8], rbp
0x140104d24  mov     al, [rax+18h]
0x140104d27  and     al, 0F7h
0x140104d29  shl     r14b, 3
0x140104d2d  or      al, r14b
0x140104d30  mov     [rdi+18h], al
0x140104d33  lea     rax, [rdi+20h]
0x140104d37  mov     [rax+8], rax
0x140104d3b  mov     [rax], rax
0x140104d3e  inc     dword ptr [rbx+80h]
0x140104d44  mov     rax, [rsi+8]
0x140104d48  cmp     [rax], rsi
0x140104d4b  jz      loc_140104EDC
0x140104d51  mov     ecx, 3
0x140104d56  int     29h; Win8: RtlFailFast(ecx)
0x140104d58  lock inc cs:dword_1400866B0
0x140104d5f  mov     ecx, 6
0x140104d64  call    cs:__imp_WdLogSingleEntry0
0x140104d6b  nop     dword ptr [rax+rax+00h]
0x140104d70  mov     eax, 3902h
0x140104d75  lea     r9, aCouldnTAllocat_23; "Couldn't allocate memory for local allo"...
0x140104d7c  mov     edx, 40001h
0x140104d81  mov     [rsp+0C8h+var_90], r12
0x140104d86  mov     [rsp+0C8h+var_98], r12
0x140104d8b  mov     [rsp+0C8h+var_A0], r12
0x140104d90  mov     qword ptr [rsp+0C8h+var_A8], rax
0x140104d95  mov     cs:WdLogGlobalForLineNumber, eax
0x140104d9b  call    DxgkLogInternalTriageEvent
0x140104da0  xor     eax, eax
0x140104da2  mov     rcx, [rsp+0C8h+var_48]
0x140104daa  xor     rcx, rsp; StackCookie
0x140104dad  call    __security_check_cookie
0x140104db2  mov     rbx, [rsp+0C8h+arg_18]
0x140104dba  add     rsp, 90h
0x140104dc1  pop     r15
0x140104dc3  pop     r14
0x140104dc5  pop     r13
0x140104dc7  pop     r12
0x140104dc9  pop     rdi
0x140104dca  pop     rsi
0x140104dcb  pop     rbp
0x140104dcc  retn
0x140104dce  cmp     rdx, rsi
0x140104dd1  jz      loc_140104D00
0x140104dd7  lea     rdi, [rdx-30h]
0x140104ddb  cmp     [rdi+8], rbp
0x140104ddf  jz      short loc_140104DE6
0x140104de1  mov     rdx, [rdx]
0x140104de4  jmp     short loc_140104DCE
0x140104de6  mov     al, [rdi+18h]
0x140104de9  test    al, 1
0x140104deb  jnz     loc_140104FE8
0x140104df1  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x140104df8  cmp     [rax], r12b
0x140104dfb  jnz     loc_140105058
0x140104e01  lea     rsi, [rbx+20h]
0x140104e05  inc     dword ptr [rdi+1Ch]
0x140104e08  mov     rax, [rbx+180h]
0x140104e0f  test    dword ptr [rax], 20000000h
0x140104e15  jnz     loc_140104EA2
0x140104e1b  mov     [rbx+30h], rdi
0x140104e1f  cmp     [rbx+48h], r12d
0x140104e23  jnz     short loc_140104E2D
0x140104e25  mov     rax, rdi
0x140104e28  jmp     loc_140104DA2
0x140104e2d  mov     r9d, [r13+3Ch]
0x140104e31  mov     rdx, r13
0x140104e34  mov     rax, [r15+8E80h]
0x140104e3b  mov     ecx, r9d
0x140104e3e  mov     r11, [r13+10h]
0x140104e42  shr     rcx, 2
0x140104e46  and     ecx, 3Fh
0x140104e49  shr     r11, 0Ch
0x140104e4d  mov     dword ptr [rsp+0C8h+var_98], r11d
0x140104e52  mov     dword ptr [rsp+0C8h+var_A0], r12d
0x140104e57  mov     dword ptr [rsp+0C8h+var_A8], r12d
0x140104e5c  mov     rbx, [rax+rcx*8]
0x140104e60  mov     rax, [r15+18h]
0x140104e64  mov     r10, [rbx]
0x140104e67  mov     ecx, [rax+0F0h]
0x140104e6d  mov     rax, [rbp+20h]
0x140104e71  mov     r8, [rax+rcx*8]
0x140104e75  mov     eax, r9d
0x140104e78  shr     eax, 2
0x140104e7b  mov     rcx, rbx
0x140104e7e  and     eax, 3Fh
0x140104e81  imul    r9, rax, 130h
0x140104e88  mov     rax, [r10+68h]
0x140104e8c  add     r9, 8
0x140104e90  add     r9, [r8+8]
0x140104e94  lea     r8, AddResidencyPerfCountersCB
0x140104e9b  call    _guard_dispatch_icall
0x140104ea0  jmp     short loc_140104E25
0x140104ea2  mov     r8, [rbx+30h]; struct VIDMM_LOCAL_ALLOC *
0x140104ea6  test    r8, r8
0x140104ea9  jnz     loc_140105077
0x140104eaf  mov     eax, [rsi]
0x140104eb1  and     eax, 60h
0x140104eb4  cmp     al, 60h ; '`'
0x140104eb6  jz      loc_140105086
0x140104ebc  mov     eax, [rsi]
0x140104ebe  test    al, 4
0x140104ec0  jnz     loc_14010509A
0x140104ec6  mov     [rdi+8], rbp
0x140104eca  cmp     [rbx+30h], r12
0x140104ece  jnz     loc_1401050F8
0x140104ed4  and     dword ptr [rsi], 0FFFFFFFBh
0x140104ed7  jmp     loc_140104E1B
0x140104edc  lea     r14, [rdi+30h]
0x140104ee0  mov     [r14], rsi
0x140104ee3  mov     [r14+8], rax
0x140104ee7  mov     [rax], r14
0x140104eea  mov     [rsi+8], r14
0x140104eee  lea     rsi, [rbx+20h]
0x140104ef2  mov     eax, [rsi]
0x140104ef4  test    al, 20h
0x140104ef6  jz      loc_140104E05
0x140104efc  mov     rdx, rdi; struct VIDMM_LOCAL_ALLOC *
0x140104eff  mov     rcx, r15; this
0x140104f02  call    ?CommitLocalBackingStore@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_LOCAL_ALLOC@@@Z; VIDMM_GLOBAL::CommitLocalBackingStore(VIDMM_LOCAL_ALLOC *)
0x140104f07  test    eax, eax
0x140104f09  jns     loc_140104E05
0x140104f0f  mov     r8b, 1; bool
0x140104f12  mov     rdx, rdi; struct VIDMM_LOCAL_ALLOC *
0x140104f15  mov     rcx, r15; this
0x140104f18  call    ?UncommitLocalBackingStore@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_LOCAL_ALLOC@@_N@Z; VIDMM_GLOBAL::UncommitLocalBackingStore(VIDMM_LOCAL_ALLOC *,bool)
0x140104f1d  dec     dword ptr [rbx+80h]
0x140104f23  mov     rcx, [r14]
0x140104f26  cmp     [rcx+8], r14
0x140104f2a  jnz     loc_140104D51
0x140104f30  mov     rax, [r14+8]
0x140104f34  cmp     [rax], r14
0x140104f37  jnz     loc_140104D51
0x140104f3d  mov     [rax], rcx
0x140104f40  mov     [rcx+8], rax
0x140104f44  mov     rcx, rdi; void *
0x140104f47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140104f4c  jmp     loc_140104DA0
0x140104f51  mov     rbp, [rcx+8F40h]
0x140104f58  jmp     loc_140104C8C
0x140104f5d  mov     ecx, 1
0x140104f62  call    cs:__imp_WdLogSingleEntry0
0x140104f69  nop     dword ptr [rax+rax+00h]
0x140104f6e  mov     eax, 3892h
0x140104f73  lea     r9, aTryingToOpenAl; "Trying to open allocation on non graphi"...
0x140104f7a  jmp     short loc_140104F99
0x140104f7c  mov     ecx, 1
0x140104f81  call    cs:__imp_WdLogSingleEntry0
0x140104f88  nop     dword ptr [rax+rax+00h]
0x140104f8d  mov     eax, 38AFh
0x140104f92  lea     r9, aTryingToOpenAl_0; "Trying to open Alloc backed by Existing"...
0x140104f99  mov     edx, 40000h
0x140104f9e  jmp     loc_140104D81
0x140104fa3  mov     ecx, 1
0x140104fa8  call    cs:__imp_WdLogSingleEntry0
0x140104faf  nop     dword ptr [rax+rax+00h]
0x140104fb4  mov     eax, 389Ch
0x140104fb9  lea     r9, aTryingToOpenAN; "Trying to open a non-shareable allocati"...
0x140104fc0  jmp     short loc_140104F99
0x140104fc2  mov     rax, [rbx+30h]
0x140104fc6  test    rax, rax
0x140104fc9  jz      loc_140104CF2
0x140104fcf  cmp     [rax+8], rbp
0x140104fd3  jz      loc_140104CF2
0x140104fd9  cmp     rbp, [r15+8F40h]
0x140104fe0  jz      loc_140104DA0
0x140104fe6  jmp     short loc_140104F7C
0x140104fe8  and     al, 0FEh
0x140104fea  mov     [rdi+18h], al
0x140104fed  mov     rdx, rdi
0x140104ff0  mov     ecx, 4
0x140104ff5  call    cs:__imp_WdLogSingleEntry1
0x140104ffc  nop     dword ptr [rax+rax+00h]
0x140105001  mov     cs:WdLogGlobalForLineNumber, 38D2h
0x14010500b  mov     rax, [rbx+30h]
0x14010500f  test    rax, rax
0x140105012  jz      short loc_14010501E
0x140105014  test    byte ptr [rax+18h], 1
0x140105018  jz      loc_140104DF1
0x14010501e  mov     [rbx+30h], rdi
0x140105022  mov     eax, [r13+40h]
0x140105026  test    al, 1
0x140105028  jz      loc_140104DF1
0x14010502e  mov     eax, [r13+3Ch]
0x140105032  xor     r9d, r9d
0x140105035  mov     rcx, [r15+8E80h]
0x14010503c  mov     rdx, r13
0x14010503f  mov     r8, [rdi+8]
0x140105043  shr     rax, 2
0x140105047  and     eax, 3Fh
0x14010504a  mov     rcx, [rcx+rax*8]
0x14010504e  call    ?VidMmRecordAlloc@@YAXPEAUVIDMM_PHYSICAL_ADAPTER@@PEAUVIDMM_PHYSICAL_ALLOC@@PEAVVIDMM_PROCESS@@W4VIDMM_ALLOC_RECORD_TYPE@@@Z; VidMmRecordAlloc(VIDMM_PHYSICAL_ADAPTER *,VIDMM_PHYSICAL_ALLOC *,VIDMM_PROCESS *,VIDMM_ALLOC_RECORD_TYPE)
0x140105053  jmp     loc_140104DF1
0x140105058  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14010505f  nop     dword ptr [rax+rax+00h]
0x140105064  mov     [rax+18h], rdi
0x140105068  mov     cs:WdLogGlobalForLineNumber, 38EBh
0x140105072  jmp     loc_140104E01
0x140105077  mov     eax, [rsi]
0x140105079  test    al, 4
0x14010507b  jz      loc_140104E1F
0x140105081  jmp     loc_140104EAF
0x140105086  mov     r9, rdi; struct VIDMM_LOCAL_ALLOC *
0x140105089  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x14010508c  call    ?TransferAllocationDecommit@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_LOCAL_ALLOC@@1@Z; VIDMM_GLOBAL::TransferAllocationDecommit(VIDMM_GLOBAL_ALLOC *,VIDMM_LOCAL_ALLOC *,VIDMM_LOCAL_ALLOC *)
0x140105091  mov     r8, [rbx+30h]
0x140105095  jmp     loc_140104EBC
0x14010509a  mov     eax, [r13+40h]
0x14010509e  test    al, 1
0x1401050a0  jz      loc_140104EC6
0x1401050a6  mov     eax, [r13+3Ch]
0x1401050aa  mov     r9d, 1
0x1401050b0  mov     rcx, [r15+8E80h]
0x1401050b7  mov     rdx, r13
0x1401050ba  mov     r8, [r8+8]
0x1401050be  shr     rax, 2
0x1401050c2  and     eax, 3Fh
0x1401050c5  mov     rcx, [rcx+rax*8]
0x1401050c9  call    ?VidMmRecordAlloc@@YAXPEAUVIDMM_PHYSICAL_ADAPTER@@PEAUVIDMM_PHYSICAL_ALLOC@@PEAVVIDMM_PROCESS@@W4VIDMM_ALLOC_RECORD_TYPE@@@Z; VidMmRecordAlloc(VIDMM_PHYSICAL_ADAPTER *,VIDMM_PHYSICAL_ALLOC *,VIDMM_PROCESS *,VIDMM_ALLOC_RECORD_TYPE)
0x1401050ce  mov     eax, [r13+3Ch]
0x1401050d2  xor     r9d, r9d
0x1401050d5  mov     rcx, [r15+8E80h]
0x1401050dc  mov     rdx, r13
0x1401050df  mov     r8, [rdi+8]
0x1401050e3  shr     rax, 2
0x1401050e7  and     eax, 3Fh
0x1401050ea  mov     rcx, [rcx+rax*8]
0x1401050ee  call    ?VidMmRecordAlloc@@YAXPEAUVIDMM_PHYSICAL_ADAPTER@@PEAUVIDMM_PHYSICAL_ALLOC@@PEAVVIDMM_PROCESS@@W4VIDMM_ALLOC_RECORD_TYPE@@@Z; VidMmRecordAlloc(VIDMM_PHYSICAL_ADAPTER *,VIDMM_PHYSICAL_ALLOC *,VIDMM_PROCESS *,VIDMM_ALLOC_RECORD_TYPE)
0x1401050f3  jmp     loc_140104EC6
0x1401050f8  mov     [rdi], rbx
0x1401050fb  mov     rcx, [rbx+30h]
0x1401050ff  test    byte ptr [rcx+18h], 1
0x140105103  jnz     loc_140104ED4
0x140105109  xorps   xmm0, xmm0
0x14010510c  lea     rdx, [rsp+0C8h+ApcState]; ApcState
0x140105111  movups  xmmword ptr [rsp+0C8h+ApcState.ApcListHead.Flink], xmm0
0x140105116  movups  xmmword ptr [rsp+0C8h+ApcState.ApcListHead.Flink+10h], xmm0
0x14010511b  movups  xmmword ptr [rsp+0C8h+ApcState.Process], xmm0
0x140105120  mov     rcx, [rcx+8]
0x140105124  mov     rcx, [rcx+10h]; PROCESS
0x140105128  call    cs:__imp_KeStackAttachProcess
0x14010512f  nop     dword ptr [rax+rax+00h]
0x140105134  mov     rcx, [rbx+30h]
0x140105138  xor     r9d, r9d; bool
0x14010513b  mov     [rsp+0C8h+var_A0], r12; struct _KEVENT **
0x140105140  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC **
0x140105143  mov     dword ptr [rsp+0C8h+var_A8], r12d; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
  ... truncated ...
```
