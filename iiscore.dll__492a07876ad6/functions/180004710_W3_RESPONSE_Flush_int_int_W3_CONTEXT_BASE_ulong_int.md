# W3_RESPONSE::Flush(int,int,W3_CONTEXT_BASE *,ulong *,int *)

- ea: `0x180004710`
- end: `0x180004dc2`
- name: `?Flush@W3_RESPONSE@@QEAAJHHPEAVW3_CONTEXT_BASE@@PEAKPEAH@Z`
- size: `1714`
- prototype: `__int64 __fastcall(W3_RESPONSE *this, int, int, struct W3_CONTEXT_BASE *, unsigned int *, int *)`
- caller_count: `4`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005930`
- `0x180026a40`
- `0x180026ac0`
- `0x180028974`

## callees

- `0x18000164c`
- `0x1800018c8`
- `0x180001b40`
- `0x18000220c`
- `0x180004710`
- `0x180004f3c`
- `0x180005030`
- `0x180015fd0`
- `0x18002319c`
- `0x180025c78`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004afe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004afe`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004b20`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004b20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004968`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004968`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004d1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004d1a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180004c5e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180004c5e`
- `iisutil!WriteRefTraceLog` at `0x1800049c6`
- `iisutil!WriteRefTraceLog` at `0x180004aa3`
- `iisutil!WriteRefTraceLog` at `0x1800049c6`
- `iisutil!WriteRefTraceLog` at `0x180004aa3`

## pseudocode

```c
__int64 __fastcall W3_RESPONSE::Flush(
        W3_RESPONSE *this,
        int a2,
        int a3,
        struct W3_CONTEXT_BASE *a4,
        unsigned int *a5,
        int *a6)
{
  unsigned int *v6; // r12
  int *v7; // r14
  struct W3_CLONE_CONTEXT *W3SendContext; // r13
  _QWORD *v12; // rcx
  __int64 v13; // rbx
  int v14; // edx
  int v15; // edi
  __int64 v16; // rcx
  USHORT *v17; // rsi
  __int64 v18; // rsi
  int v19; // eax
  __int64 result; // rax
  _QWORD *v21; // rcx
  __int64 v22; // rbx
  int v23; // ebp
  DWORD TickCount; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rax
  int v29; // edx
  __int64 v30; // rcx
  __int64 v31; // rsi
  int v32; // esi
  unsigned int v33; // esi
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rdx
  int v37; // r9d
  int CurrentModuleIndex; // [rsp+40h] [rbp-68h] BYREF
  _HTTP_DATA_CHUNK v39; // [rsp+48h] [rbp-60h] BYREF
  int v40; // [rsp+B0h] [rbp+8h]
  unsigned int v41; // [rsp+B8h] [rbp+10h] BYREF
  W3_CONTEXT_BASE *v42; // [rsp+C8h] [rbp+20h]

  v42 = a4;
  v6 = a5;
  v7 = a6;
  W3SendContext = a4;
  memset(&v39, 0, sizeof(v39));
  if ( (!a2 || a6) && !a5 )
    return 2147942487LL;
  v12 = (_QWORD *)*((_QWORD *)this + 6);
  v13 = v12[49];
  if ( ((*(__int64 (__fastcall **)(_QWORD *))(*v12 + 112LL))(v12) & 0x21) != 0 )
    return 2147942450LL;
  if ( *(_BYTE *)(v13 + 9345) )
    return 2147942487LL;
  if ( !*(_DWORD *)(v13 + 9352) && (*(_BYTE *)(v13 + 9356) & 1) != 0 )
    return 2147943397LL;
  v14 = 0;
  v15 = -2147467259;
  v40 = 0;
  if ( *(_BYTE *)(v13 + 9347) )
  {
    v14 = 1;
    if ( *(_BYTE *)(v13 + 9348) )
      v14 = 257;
    v40 = v14;
  }
  v16 = *(_QWORD *)(*((_QWORD *)this + 6) + 8912LL);
  if ( v16 && *(_DWORD *)(v16 + 308) )
  {
    v14 |= 8u;
    v40 = v14;
  }
  if ( a3 )
  {
    v40 = v14 | 2;
  }
  else
  {
    v17 = (USHORT *)*((_QWORD *)this + 197);
    if ( v17 )
    {
      if ( *(_DWORD *)v17 )
      {
        v39.DataChunkType = HttpDataChunkMaximum;
        v39.FromFileHandle.ByteRange.Length.QuadPart = (ULONGLONG)BUFFER::QueryPtr((BUFFER *)(v17 + 4));
        v39.FromFragmentCache.FragmentNameLength = *v17;
        result = W3_RESPONSE::WriteEntityChunkByReference(this, &v39, -1);
        v15 = result;
        if ( (int)result < 0 )
          return result;
      }
    }
  }
  v18 = *((_QWORD *)W3SendContext + 10);
  if ( !v18
    || !*(_QWORD *)(v18 + 80)
    || (v35 = *(_QWORD *)(v18 + 112),
        v36 = *(_QWORD *)(v18 + 104),
        *(_DWORD *)(v36 + 4LL * *(unsigned int *)(v35 + 236)) == -1)
    && *(_DWORD *)(v36 + 4LL * *(unsigned int *)(v35 + 232)) == -1 )
  {
    v41 = 0;
    CurrentModuleIndex = 0;
    if ( !IISCORE_ASYNC_CONTEXT::SetIoCompletionContext(this, W3SendContext) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)W3SendContext + 10) + 52LL));
      *(_DWORD *)(v13 + 9356) |= 2u;
      v15 = W3_RESPONSE::DoActualSendResponse(this, a2, v40, &v41, 0, 1, &CurrentModuleIndex);
      if ( v15 < 0 )
      {
        *(_DWORD *)(v13 + 9356) &= ~2u;
        _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)W3SendContext + 10) + 52LL));
        IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(this);
      }
      else
      {
        v19 = CurrentModuleIndex;
        if ( a2 )
        {
          if ( !v7 )
          {
            if ( !CurrentModuleIndex )
            {
              *(_DWORD *)(v13 + 9356) &= ~2u;
              _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)W3SendContext + 10) + 52LL));
              IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(this);
              return W3_CONTEXT_BASE::PostCompletion(W3SendContext, v41, 2u);
            }
            return (unsigned int)v15;
          }
          *v7 = CurrentModuleIndex;
        }
        if ( !v19 )
        {
          *(_DWORD *)(v13 + 9356) &= ~2u;
          _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)W3SendContext + 10) + 52LL));
          IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(this);
          *v6 = v41;
        }
      }
      return (unsigned int)v15;
    }
    return 2147943397LL;
  }
  if ( *(_DWORD *)(v18 + 8) == 0x20000000 )
  {
    CurrentModuleIndex = NOTIFICATION_CONTEXT::QueryCurrentModuleIndex(*((NOTIFICATION_CONTEXT **)W3SendContext + 10));
    LOBYTE(v41) = 0;
  }
  else
  {
    CurrentModuleIndex = -1;
    LOBYTE(v41) = 1;
  }
  if ( *(_DWORD *)(v13 + 9352)
    && !*((_DWORD *)W3SendContext + 22)
    && (W3SendContext = W3_CONTEXT::QueryW3SendContext(W3SendContext)) == 0 )
  {
    return (unsigned int)-2147024888;
  }
  if ( (v21 = (_QWORD *)*((_QWORD *)this + 6)) == 0 )
    return (unsigned int)-2147024888;
  v22 = v21[249];
  v23 = 0;
  v21[249] = 0;
  if ( !v22 && (v22 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v21 + 144LL))(v21, 168)) == 0 )
    return (unsigned int)-2147024888;
  *(_DWORD *)(v22 + 8) = 0;
  *(_QWORD *)v22 = &NOTIFICATION_CONTEXT::`vftable';
  *(_WORD *)(v22 + 12) = 0;
  *(_DWORD *)(v22 + 16) = -1;
  *(_QWORD *)(v22 + 24) = W3SendContext;
  *(_DWORD *)(v22 + 32) = 1480807502;
  *(_DWORD *)(v22 + 36) = 1;
  *(_DWORD *)(v22 + 40) = 1;
  TickCount = GetTickCount();
  v25 = *(_QWORD *)(v22 + 24);
  *(_DWORD *)(v22 + 44) = TickCount;
  *(_QWORD *)(v22 + 48) = 0;
  *(_QWORD *)(v22 + 56) = 0;
  *(_QWORD *)(v22 + 64) = 0;
  *(_QWORD *)(v22 + 72) = 0;
  *(_QWORD *)(v22 + 80) = 0;
  *(_QWORD *)(v22 + 88) = 0;
  *(_QWORD *)(v22 + 96) = 0;
  *(_QWORD *)(v22 + 104) = 0;
  *(_QWORD *)(v22 + 112) = 0;
  *(_DWORD *)(v22 + 120) = 0;
  *(_DWORD *)(v22 + 124) = -1;
  *(_QWORD *)(v22 + 128) = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v25 + 76));
  if ( W3_CONTEXT_BASE::sm_pTraceLog )
    WriteRefTraceLog(W3_CONTEXT_BASE::sm_pTraceLog, *(unsigned int *)(v25 + 76), v25);
  *(_QWORD *)v22 = &NOTIFICATION_SEND_RESPONSE::`vftable'{for `NOTIFICATION_CONTEXT'};
  *(_QWORD *)(v22 + 144) = v6;
  *(_QWORD *)(v22 + 136) = &NOTIFICATION_SEND_RESPONSE::`vftable'{for `ISendResponseProvider'};
  *(_BYTE *)(v22 + 164) = a2 != 0;
  *(_BYTE *)(v22 + 166) = v41;
  *(_QWORD *)(v22 + 152) = 0;
  *(_DWORD *)(v22 + 160) = v40;
  *(_BYTE *)(v22 + 165) = 0;
  v26 = *(_QWORD *)(v18 + 80);
  *(_QWORD *)(v22 + 80) = v26;
  *(_QWORD *)(v22 + 88) = *(_QWORD *)(v18 + 88);
  v27 = *(_QWORD *)(v18 + 104);
  *(_QWORD *)(v22 + 104) = v27;
  *(_DWORD *)(v22 + 120) = *(_DWORD *)(v18 + 120);
  v28 = *(_QWORD *)(v18 + 112);
  *(_QWORD *)(v22 + 112) = v28;
  if ( v26 )
  {
    v29 = CurrentModuleIndex;
    *(_DWORD *)(v22 + 8) = 0x20000000;
    *(_BYTE *)(v22 + 12) = 0;
    *(_DWORD *)(v22 + 16) = -1;
    v30 = *(unsigned int *)(v28 + 232);
    *(_DWORD *)(v22 + 124) = v30;
    if ( v29 != -1 )
    {
      v37 = *(_DWORD *)(v27 + 4 * v30);
      if ( v37 == v29 )
      {
LABEL_77:
        if ( v37 != -1 )
          *(_DWORD *)(v22 + 124) = v30 + 1;
      }
      else
      {
        while ( v37 != -1 )
        {
          v30 = (unsigned int)(v30 + 1);
          *(_DWORD *)(v22 + 124) = v30;
          v37 = *(_DWORD *)(v27 + 4 * v30);
          if ( v37 == v29 )
            goto LABEL_77;
        }
      }
    }
  }
  if ( !a2 )
  {
    v23 = 1;
    v34 = NOTIFICATION_CONTEXT::SetupSynchronousCall((NOTIFICATION_CONTEXT *)v22);
    if ( v34 < 0 )
    {
      *(_DWORD *)(v22 + 72) = v34;
      goto LABEL_41;
    }
  }
  v31 = *((_QWORD *)W3SendContext + 10);
  if ( v31 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v31 + 36));
    if ( NOTIFICATION_CONTEXT::sm_pTraceLog )
      WriteRefTraceLog(NOTIFICATION_CONTEXT::sm_pTraceLog, *(unsigned int *)(v31 + 36), v31);
    _InterlockedIncrement((volatile signed __int32 *)(v31 + 52));
  }
  *(_QWORD *)(v22 + 56) = v31;
  *((_QWORD *)W3SendContext + 10) = v22;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 24LL))(v22);
  v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v22 + 8LL))(v22, 0, 0, 0, 0);
  if ( v32 != 1 )
  {
    if ( !v23 )
      goto LABEL_40;
    goto LABEL_37;
  }
  if ( v23 )
  {
    WaitForSingleObject(*(HANDLE *)(v22 + 64), 0xFFFFFFFF);
    v32 = 0;
LABEL_37:
    if ( TlsGetValue(g_TlsEventIndex) )
      CloseHandle(*(HANDLE *)(v22 + 64));
    else
      TlsSetValue(g_TlsEventIndex, *(LPVOID *)(v22 + 64));
    *(_QWORD *)(v22 + 64) = 0;
LABEL_40:
    if ( !v32 )
    {
LABEL_41:
      if ( v7 )
        *v7 = 0;
      v15 = *(_DWORD *)(v22 + 72);
      v33 = *(_DWORD *)(v22 + 76);
      W3_CONTEXT_BASE::FinishNotificationLoop(v22);
      if ( v15 >= 0 )
      {
        if ( a2 && !v7 )
          W3_CONTEXT_BASE::PostCompletion(v42, v33, 2u);
        else
          *v6 = v33;
      }
    }
    return (unsigned int)v15;
  }
  if ( v7 )
    *v7 = 1;
  return 0;
}

```

## disassembly

```asm
0x180004710  mov     [rsp+arg_18], r9
0x180004715  push    rbx
0x180004716  push    rbp
0x180004717  push    rsi
0x180004718  push    r12
0x18000471a  push    r13
0x18000471c  push    r14
0x18000471e  push    r15
0x180004720  sub     rsp, 70h
0x180004724  mov     r12, [rsp+0A8h+arg_20]
0x18000472c  xorps   xmm0, xmm0
0x18000472f  mov     r14, [rsp+0A8h+arg_28]
0x180004737  mov     r13, r9
0x18000473a  mov     esi, r8d
0x18000473d  mov     r15d, edx
0x180004740  mov     rbp, rcx
0x180004743  movups  xmmword ptr [rsp+0A8h+var_60.DataChunkType], xmm0
0x180004748  movups  xmmword ptr [rsp+0A8h+var_60.8+8], xmm0
0x18000474d  test    edx, edx
0x18000474f  jnz     loc_180004B80
0x180004755  test    r12, r12
0x180004758  jz      loc_180004DB8
0x18000475e  mov     rcx, [rcx+30h]
0x180004762  mov     rax, [rcx]
0x180004765  mov     rbx, [rcx+188h]
0x18000476c  mov     rax, [rax+70h]
0x180004770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004775  test    al, 21h
0x180004777  jnz     loc_1800048B5
0x18000477d  cmp     byte ptr [rbx+2481h], 0
0x180004784  jnz     loc_180004DB8
0x18000478a  cmp     dword ptr [rbx+2488h], 0
0x180004791  mov     [rsp+0A8h+arg_10], rdi
0x180004799  jnz     short loc_1800047A8
0x18000479b  test    byte ptr [rbx+248Ch], 1
0x1800047a2  jnz     loc_180004D59
0x1800047a8  xor     edx, edx
0x1800047aa  mov     edi, 80004005h
0x1800047af  mov     [rsp+0A8h+arg_0], edx
0x1800047b6  cmp     [rbx+2483h], dl
0x1800047bc  jnz     loc_180004BFE
0x1800047c2  mov     rax, [rbp+30h]
0x1800047c6  mov     rcx, [rax+22D0h]
0x1800047cd  test    rcx, rcx
0x1800047d0  jnz     loc_180004C1E
0x1800047d6  test    esi, esi
0x1800047d8  jnz     loc_180004C3A
0x1800047de  mov     rsi, [rbp+628h]
0x1800047e5  test    rsi, rsi
0x1800047e8  jnz     loc_180004C49
0x1800047ee  mov     rsi, [r13+50h]
0x1800047f2  test    rsi, rsi
0x1800047f5  jnz     loc_180004BC6
0x1800047fb  mov     rdx, r13; struct W3_CONTEXT_BASE *
0x1800047fe  mov     [rsp+0A8h+arg_8], 0
0x180004809  mov     rcx, rbp; this
0x18000480c  mov     [rsp+0A8h+var_68], 0
0x180004814  call    ?SetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@PEAV2@@Z; IISCORE_ASYNC_CONTEXT::SetIoCompletionContext(W3_CONTEXT_BASE *)
0x180004819  test    rax, rax
0x18000481c  jnz     loc_180004D59
0x180004822  mov     rax, [r13+50h]
0x180004826  lock inc dword ptr [rax+34h]
0x18000482a  mov     r8d, [rsp+0A8h+arg_0]; unsigned int
0x180004832  lea     rax, [rsp+0A8h+var_68]
0x180004837  or      dword ptr [rbx+248Ch], 2
0x18000483e  lea     r9, [rsp+0A8h+arg_8]; unsigned int *
0x180004846  mov     [rsp+0A8h+var_78], rax; int *
0x18000484b  mov     edx, r15d; int
0x18000484e  mov     [rsp+0A8h+var_80], 1; int
0x180004856  mov     rcx, rbp; this
0x180004859  mov     [rsp+0A8h+var_88], 0; struct _HTTP_LOG_DATA *
0x180004862  call    ?DoActualSendResponse@W3_RESPONSE@@QEAAJHKPEAKPEAU_HTTP_LOG_DATA@@HPEAH@Z; W3_RESPONSE::DoActualSendResponse(int,ulong,ulong *,_HTTP_LOG_DATA *,int,int *)
0x180004867  mov     edi, eax
0x180004869  test    eax, eax
0x18000486b  js      loc_180004D9C
0x180004871  mov     eax, [rsp+0A8h+var_68]
0x180004875  test    r15d, r15d
0x180004878  jz      short loc_180004886
0x18000487a  test    r14, r14
0x18000487d  jz      loc_180004D63
0x180004883  mov     [r14], eax
0x180004886  test    eax, eax
0x180004888  jnz     loc_180004B65
0x18000488e  and     dword ptr [rbx+248Ch], 0FFFFFFFDh
0x180004895  mov     rcx, rbp; this
0x180004898  mov     rax, [r13+50h]
0x18000489c  lock dec dword ptr [rax+34h]
0x1800048a0  call    ?ResetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@XZ; IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(void)
0x1800048a5  mov     eax, [rsp+0A8h+arg_8]
0x1800048ac  mov     [r12], eax
0x1800048b0  jmp     loc_180004B65
0x1800048b5  mov     eax, 80070032h
0x1800048ba  add     rsp, 70h
0x1800048be  pop     r15
0x1800048c0  pop     r14
0x1800048c2  pop     r13
0x1800048c4  pop     r12
0x1800048c6  pop     rsi
0x1800048c7  pop     rbp
0x1800048c8  pop     rbx
0x1800048c9  retn
0x1800048cb  cmp     dword ptr [rsi+8], 20000000h
0x1800048d2  jz      loc_180004C99
0x1800048d8  mov     [rsp+0A8h+var_68], 0FFFFFFFFh
0x1800048e0  mov     byte ptr [rsp+0A8h+arg_8], 1
0x1800048e8  cmp     dword ptr [rbx+2488h], 0
0x1800048ef  jnz     loc_180004CB2
0x1800048f5  mov     rcx, [rbp+30h]
0x1800048f9  test    rcx, rcx
0x1800048fc  jz      loc_180004CD1
0x180004902  mov     rbx, [rcx+7C8h]
0x180004909  xor     ebp, ebp
0x18000490b  mov     [rcx+7C8h], rbp
0x180004912  test    rbx, rbx
0x180004915  jnz     short loc_180004937
0x180004917  mov     rax, [rcx]
0x18000491a  mov     edx, 0A8h
0x18000491f  mov     rax, [rax+90h]
0x180004926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492b  mov     rbx, rax
0x18000492e  test    rax, rax
0x180004931  jz      loc_180004CD1
0x180004937  lea     rax, ??_7NOTIFICATION_CONTEXT@@6B@; const NOTIFICATION_CONTEXT::`vftable'
0x18000493e  mov     [rbx+8], ebp
0x180004941  mov     [rbx], rax
0x180004944  mov     [rbx+0Ch], bp
0x180004948  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x18000494f  mov     [rbx+18h], r13
0x180004953  mov     dword ptr [rbx+20h], 5843544Eh
0x18000495a  mov     dword ptr [rbx+24h], 1
0x180004961  mov     dword ptr [rbx+28h], 1
0x180004968  call    cs:__imp_GetTickCount
0x18000496f  nop     dword ptr [rax+rax+00h]
0x180004974  mov     rdx, [rbx+18h]
0x180004978  mov     [rbx+2Ch], eax
0x18000497b  mov     [rbx+30h], rbp
0x18000497f  mov     [rbx+38h], rbp
0x180004983  mov     [rbx+40h], rbp
0x180004987  mov     [rbx+48h], rbp
0x18000498b  mov     [rbx+50h], rbp
0x18000498f  mov     [rbx+58h], rbp
0x180004993  mov     [rbx+60h], rbp
0x180004997  mov     [rbx+68h], rbp
0x18000499b  mov     [rbx+70h], rbp
0x18000499f  mov     [rbx+78h], ebp
0x1800049a2  mov     dword ptr [rbx+7Ch], 0FFFFFFFFh
0x1800049a9  mov     [rbx+80h], rbp
0x1800049b0  lock inc dword ptr [rdx+4Ch]
0x1800049b4  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x1800049bb  test    rcx, rcx
0x1800049be  jz      short loc_1800049D2
0x1800049c0  mov     r8, rdx
0x1800049c3  mov     edx, [rdx+4Ch]
0x1800049c6  call    cs:__imp_WriteRefTraceLog
0x1800049cd  nop     dword ptr [rax+rax+00h]
0x1800049d2  mov     r8d, [rsp+0A8h+arg_0]
0x1800049da  lea     rax, ??_7NOTIFICATION_SEND_RESPONSE@@6BNOTIFICATION_CONTEXT@@@; const NOTIFICATION_SEND_RESPONSE::`vftable'{for `NOTIFICATION_CONTEXT'}
0x1800049e1  mov     [rbx], rax
0x1800049e4  test    r15d, r15d
0x1800049e7  mov     [rbx+90h], r12
0x1800049ee  lea     rax, ??_7NOTIFICATION_SEND_RESPONSE@@6BISendResponseProvider@@@; const NOTIFICATION_SEND_RESPONSE::`vftable'{for `ISendResponseProvider'}
0x1800049f5  mov     [rbx+88h], rax
0x1800049fc  setnz   al
0x1800049ff  mov     [rbx+0A4h], al
0x180004a05  movzx   eax, byte ptr [rsp+0A8h+arg_8]
0x180004a0d  mov     [rbx+0A6h], al
0x180004a13  mov     [rbx+98h], rbp
0x180004a1a  mov     [rbx+0A0h], r8d
0x180004a21  mov     [rbx+0A5h], bpl
0x180004a28  mov     rcx, [rsi+50h]
0x180004a2c  mov     [rbx+50h], rcx
0x180004a30  mov     rax, [rsi+58h]
0x180004a34  mov     [rbx+58h], rax
0x180004a38  mov     r8, [rsi+68h]
0x180004a3c  mov     [rbx+68h], r8
0x180004a40  mov     eax, [rsi+78h]
0x180004a43  mov     [rbx+78h], eax
0x180004a46  mov     rax, [rsi+70h]
0x180004a4a  mov     [rbx+70h], rax
0x180004a4e  test    rcx, rcx
0x180004a51  jz      short loc_180004A7B
0x180004a53  mov     edx, [rsp+0A8h+var_68]
0x180004a57  mov     dword ptr [rbx+8], 20000000h
0x180004a5e  mov     [rbx+0Ch], bpl
0x180004a62  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x180004a69  mov     ecx, [rax+0E8h]
0x180004a6f  mov     [rbx+7Ch], ecx
0x180004a72  cmp     edx, 0FFFFFFFFh
0x180004a75  jnz     loc_180004CDB
0x180004a7b  test    r15d, r15d
0x180004a7e  jz      loc_180004BA6
0x180004a84  mov     rsi, [r13+50h]
0x180004a88  test    rsi, rsi
0x180004a8b  jz      short loc_180004AB3
0x180004a8d  lock inc dword ptr [rsi+24h]
0x180004a91  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x180004a98  test    rcx, rcx
0x180004a9b  jz      short loc_180004AAF
0x180004a9d  mov     edx, [rsi+24h]
0x180004aa0  mov     r8, rsi
0x180004aa3  call    cs:__imp_WriteRefTraceLog
0x180004aaa  nop     dword ptr [rax+rax+00h]
0x180004aaf  lock inc dword ptr [rsi+34h]
0x180004ab3  mov     [rbx+38h], rsi
0x180004ab7  mov     rcx, rbx
0x180004aba  mov     [r13+50h], rbx
0x180004abe  mov     rax, [rbx]
0x180004ac1  mov     rax, [rax+18h]
0x180004ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aca  mov     rax, [rbx]
0x180004acd  xor     r13d, r13d
0x180004ad0  xor     r9d, r9d
0x180004ad3  mov     dword ptr [rsp+0A8h+var_88], r13d
0x180004ad8  xor     r8d, r8d
0x180004adb  xor     edx, edx
0x180004add  mov     rcx, rbx
0x180004ae0  mov     rax, [rax+8]
0x180004ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ae9  mov     esi, eax
0x180004aeb  cmp     eax, 1
0x180004aee  jz      loc_180004B8E
0x180004af4  test    ebp, ebp
0x180004af6  jz      short loc_180004B35
0x180004af8  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x180004afe  call    cs:__imp_TlsGetValue
0x180004b05  nop     dword ptr [rax+rax+00h]
0x180004b0a  mov     rcx, [rbx+40h]; hObject
0x180004b0e  test    rax, rax
0x180004b11  jnz     loc_180004D2E
0x180004b17  mov     rdx, rcx; lpTlsValue
0x180004b1a  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x180004b20  call    cs:__imp_TlsSetValue
0x180004b27  nop     dword ptr [rax+rax+00h]
0x180004b2c  mov     [rbx+40h], r13
0x180004b30  cmp     esi, 1
0x180004b33  jz      short loc_180004B96
0x180004b35  test    esi, esi
0x180004b37  jnz     short loc_180004B65
0x180004b39  test    r14, r14
0x180004b3c  jz      short loc_180004B41
0x180004b3e  mov     [r14], r13d
0x180004b41  mov     edi, [rbx+48h]
0x180004b44  mov     rcx, rbx
0x180004b47  mov     esi, [rbx+4Ch]
0x180004b4a  call    ?FinishNotificationLoop@W3_CONTEXT_BASE@@SA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@@Z; W3_CONTEXT_BASE::FinishNotificationLoop(NOTIFICATION_CONTEXT *)
0x180004b4f  test    edi, edi
0x180004b51  js      short loc_180004B65
0x180004b53  test    r15d, r15d
0x180004b56  jz      short loc_180004B61
0x180004b58  test    r14, r14
0x180004b5b  jz      loc_180004D3F
0x180004b61  mov     [r12], esi
0x180004b65  mov     eax, edi
0x180004b67  mov     rdi, [rsp+0A8h+arg_10]
0x180004b6f  add     rsp, 70h
0x180004b73  pop     r15
0x180004b75  pop     r14
0x180004b77  pop     r13
0x180004b79  pop     r12
0x180004b7b  pop     rsi
0x180004b7c  pop     rbp
0x180004b7d  pop     rbx
0x180004b7e  retn
0x180004b80  test    r14, r14
0x180004b83  jz      loc_18000475E
0x180004b89  jmp     loc_180004755
0x180004b8e  test    ebp, ebp
0x180004b90  jnz     loc_180004D11
0x180004b96  test    r14, r14
0x180004b99  jz      short loc_180004BA2
0x180004b9b  mov     dword ptr [r14], 1
0x180004ba2  xor     eax, eax
0x180004ba4  jmp     short loc_180004B67
0x180004ba6  mov     rcx, rbx; this
0x180004ba9  mov     ebp, 1
0x180004bae  call    ?SetupSynchronousCall@NOTIFICATION_CONTEXT@@QEAAJXZ; NOTIFICATION_CONTEXT::SetupSynchronousCall(void)
0x180004bb3  test    eax, eax
0x180004bb5  jns     loc_180004A84
0x180004bbb  mov     [rbx+48h], eax
0x180004bbe  xor     r13d, r13d
0x180004bc1  jmp     loc_180004B39
0x180004bc6  cmp     qword ptr [rsi+50h], 0
0x180004bcb  jz      loc_1800047FB
0x180004bd1  mov     rcx, [rsi+70h]
0x180004bd5  mov     rdx, [rsi+68h]
0x180004bd9  mov     eax, [rcx+0ECh]
0x180004bdf  cmp     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x180004be3  jnz     loc_1800048CB
0x180004be9  mov     eax, [rcx+0E8h]
0x180004bef  cmp     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x180004bf3  jz      loc_1800047FB
0x180004bf9  jmp     loc_1800048CB
0x180004bfe  cmp     byte ptr [rbx+2484h], 0
0x180004c05  mov     edx, 1
0x180004c0a  mov     eax, 101h
0x180004c0f  cmovnz  edx, eax
0x180004c12  mov     [rsp+0A8h+arg_0], edx
0x180004c19  jmp     loc_1800047C2
0x180004c1e  cmp     dword ptr [rcx+134h], 0
0x180004c25  jz      loc_1800047D6
  ... truncated ...
```
