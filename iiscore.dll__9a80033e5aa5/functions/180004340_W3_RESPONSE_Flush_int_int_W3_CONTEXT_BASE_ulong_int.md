# W3_RESPONSE::Flush(int,int,W3_CONTEXT_BASE *,ulong *,int *)

- ea: `0x180004340`
- end: `0x1800049c0`
- name: `?Flush@W3_RESPONSE@@QEAAJHHPEAVW3_CONTEXT_BASE@@PEAKPEAH@Z`
- size: `1664`
- prototype: `__int64 __usercall@<rax>(W3_RESPONSE *__hidden this@<rcx>, int@<edx>, int@<r8d>, struct W3_CONTEXT_BASE *@<r9>, unsigned int *, int *)`
- caller_count: `4`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800054d0`
- `0x180024b50`
- `0x180024bd0`
- `0x1800268d0`

## callees

- `0x1800015f8`
- `0x180001850`
- `0x180001ab0`
- `0x180002158`
- `0x180004340`
- `0x180004b2c`
- `0x180004c00`
- `0x180014db0`
- `0x180021520`
- `0x180023df4`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000471b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000471b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004737`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004737`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004932`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004932`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004597`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004597`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004924`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004924`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000486e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000486e`
- `iisutil!WriteRefTraceLog` at `0x1800045ef`
- `iisutil!WriteRefTraceLog` at `0x1800046c6`
- `iisutil!WriteRefTraceLog` at `0x1800045ef`
- `iisutil!WriteRefTraceLog` at `0x1800046c6`

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
0x180004340  mov     [rsp+arg_18], r9
0x180004345  push    rbx
0x180004346  push    rbp
0x180004347  push    rsi
0x180004348  push    r12
0x18000434a  push    r13
0x18000434c  push    r14
0x18000434e  push    r15
0x180004350  sub     rsp, 70h
0x180004354  mov     r12, [rsp+0A8h+arg_20]
0x18000435c  xorps   xmm0, xmm0
0x18000435f  mov     r14, [rsp+0A8h+arg_28]
0x180004367  mov     r13, r9
0x18000436a  mov     esi, r8d
0x18000436d  mov     r15d, edx
0x180004370  mov     rbp, rcx
0x180004373  movups  xmmword ptr [rsp+0A8h+var_60.DataChunkType], xmm0
0x180004378  movups  xmmword ptr [rsp+0A8h+var_60.8+8], xmm0
0x18000437d  test    edx, edx
0x18000437f  jnz     loc_180004790
0x180004385  test    r12, r12
0x180004388  jz      loc_1800049B6
0x18000438e  mov     rcx, [rcx+30h]
0x180004392  mov     rax, [rcx]
0x180004395  mov     rbx, [rcx+188h]
0x18000439c  mov     rax, [rax+70h]
0x1800043a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a5  test    al, 21h
0x1800043a7  jnz     loc_1800044E5
0x1800043ad  cmp     byte ptr [rbx+2481h], 0
0x1800043b4  jnz     loc_1800049B6
0x1800043ba  cmp     dword ptr [rbx+2488h], 0
0x1800043c1  mov     [rsp+0A8h+arg_10], rdi
0x1800043c9  jnz     short loc_1800043D8
0x1800043cb  test    byte ptr [rbx+248Ch], 1
0x1800043d2  jnz     loc_180004957
0x1800043d8  xor     edx, edx
0x1800043da  mov     edi, 80004005h
0x1800043df  mov     [rsp+0A8h+arg_0], edx
0x1800043e6  cmp     [rbx+2483h], dl
0x1800043ec  jnz     loc_18000480E
0x1800043f2  mov     rax, [rbp+30h]
0x1800043f6  mov     rcx, [rax+22D0h]
0x1800043fd  test    rcx, rcx
0x180004400  jnz     loc_18000482E
0x180004406  test    esi, esi
0x180004408  jnz     loc_18000484A
0x18000440e  mov     rsi, [rbp+628h]
0x180004415  test    rsi, rsi
0x180004418  jnz     loc_180004859
0x18000441e  mov     rsi, [r13+50h]
0x180004422  test    rsi, rsi
0x180004425  jnz     loc_1800047D6
0x18000442b  mov     rdx, r13; struct W3_CONTEXT_BASE *
0x18000442e  mov     [rsp+0A8h+arg_8], 0
0x180004439  mov     rcx, rbp; this
0x18000443c  mov     [rsp+0A8h+var_68], 0
0x180004444  call    ?SetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@PEAV2@@Z; IISCORE_ASYNC_CONTEXT::SetIoCompletionContext(W3_CONTEXT_BASE *)
0x180004449  test    rax, rax
0x18000444c  jnz     loc_180004957
0x180004452  mov     rax, [r13+50h]
0x180004456  lock inc dword ptr [rax+34h]
0x18000445a  mov     r8d, [rsp+0A8h+arg_0]; unsigned int
0x180004462  lea     rax, [rsp+0A8h+var_68]
0x180004467  or      dword ptr [rbx+248Ch], 2
0x18000446e  lea     r9, [rsp+0A8h+arg_8]; unsigned int *
0x180004476  mov     [rsp+0A8h+var_78], rax; int *
0x18000447b  mov     edx, r15d; int
0x18000447e  mov     [rsp+0A8h+var_80], 1; int
0x180004486  mov     rcx, rbp; this
0x180004489  mov     [rsp+0A8h+var_88], 0; struct _HTTP_LOG_DATA *
0x180004492  call    ?DoActualSendResponse@W3_RESPONSE@@QEAAJHKPEAKPEAU_HTTP_LOG_DATA@@HPEAH@Z; W3_RESPONSE::DoActualSendResponse(int,ulong,ulong *,_HTTP_LOG_DATA *,int,int *)
0x180004497  mov     edi, eax
0x180004499  test    eax, eax
0x18000449b  js      loc_18000499A
0x1800044a1  mov     eax, [rsp+0A8h+var_68]
0x1800044a5  test    r15d, r15d
0x1800044a8  jz      short loc_1800044B6
0x1800044aa  test    r14, r14
0x1800044ad  jz      loc_180004961
0x1800044b3  mov     [r14], eax
0x1800044b6  test    eax, eax
0x1800044b8  jnz     loc_180004776
0x1800044be  and     dword ptr [rbx+248Ch], 0FFFFFFFDh
0x1800044c5  mov     rcx, rbp; this
0x1800044c8  mov     rax, [r13+50h]
0x1800044cc  lock dec dword ptr [rax+34h]
0x1800044d0  call    ?ResetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@XZ; IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(void)
0x1800044d5  mov     eax, [rsp+0A8h+arg_8]
0x1800044dc  mov     [r12], eax
0x1800044e0  jmp     loc_180004776
0x1800044e5  mov     eax, 80070032h
0x1800044ea  add     rsp, 70h
0x1800044ee  pop     r15
0x1800044f0  pop     r14
0x1800044f2  pop     r13
0x1800044f4  pop     r12
0x1800044f6  pop     rsi
0x1800044f7  pop     rbp
0x1800044f8  pop     rbx
0x1800044f9  retn
0x1800044fa  cmp     dword ptr [rsi+8], 20000000h
0x180004501  jz      loc_1800048A3
0x180004507  mov     [rsp+0A8h+var_68], 0FFFFFFFFh
0x18000450f  mov     byte ptr [rsp+0A8h+arg_8], 1
0x180004517  cmp     dword ptr [rbx+2488h], 0
0x18000451e  jnz     loc_1800048BC
0x180004524  mov     rcx, [rbp+30h]
0x180004528  test    rcx, rcx
0x18000452b  jz      loc_1800048DB
0x180004531  mov     rbx, [rcx+7C8h]
0x180004538  xor     ebp, ebp
0x18000453a  mov     [rcx+7C8h], rbp
0x180004541  test    rbx, rbx
0x180004544  jnz     short loc_180004566
0x180004546  mov     rax, [rcx]
0x180004549  mov     edx, 0A8h
0x18000454e  mov     rax, [rax+90h]
0x180004555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000455a  mov     rbx, rax
0x18000455d  test    rax, rax
0x180004560  jz      loc_1800048DB
0x180004566  lea     rax, ??_7NOTIFICATION_CONTEXT@@6B@; const NOTIFICATION_CONTEXT::`vftable'
0x18000456d  mov     [rbx+8], ebp
0x180004570  mov     [rbx], rax
0x180004573  mov     [rbx+0Ch], bp
0x180004577  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x18000457e  mov     [rbx+18h], r13
0x180004582  mov     dword ptr [rbx+20h], 5843544Eh
0x180004589  mov     dword ptr [rbx+24h], 1
0x180004590  mov     dword ptr [rbx+28h], 1
0x180004597  call    cs:__imp_GetTickCount
0x18000459d  mov     rdx, [rbx+18h]
0x1800045a1  mov     [rbx+2Ch], eax
0x1800045a4  mov     [rbx+30h], rbp
0x1800045a8  mov     [rbx+38h], rbp
0x1800045ac  mov     [rbx+40h], rbp
0x1800045b0  mov     [rbx+48h], rbp
0x1800045b4  mov     [rbx+50h], rbp
0x1800045b8  mov     [rbx+58h], rbp
0x1800045bc  mov     [rbx+60h], rbp
0x1800045c0  mov     [rbx+68h], rbp
0x1800045c4  mov     [rbx+70h], rbp
0x1800045c8  mov     [rbx+78h], ebp
0x1800045cb  mov     dword ptr [rbx+7Ch], 0FFFFFFFFh
0x1800045d2  mov     [rbx+80h], rbp
0x1800045d9  lock inc dword ptr [rdx+4Ch]
0x1800045dd  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x1800045e4  test    rcx, rcx
0x1800045e7  jz      short loc_1800045F5
0x1800045e9  mov     r8, rdx
0x1800045ec  mov     edx, [rdx+4Ch]
0x1800045ef  call    cs:__imp_WriteRefTraceLog
0x1800045f5  mov     r8d, [rsp+0A8h+arg_0]
0x1800045fd  lea     rax, ??_7NOTIFICATION_SEND_RESPONSE@@6BNOTIFICATION_CONTEXT@@@; const NOTIFICATION_SEND_RESPONSE::`vftable'{for `NOTIFICATION_CONTEXT'}
0x180004604  mov     [rbx], rax
0x180004607  test    r15d, r15d
0x18000460a  mov     [rbx+90h], r12
0x180004611  lea     rax, ??_7NOTIFICATION_SEND_RESPONSE@@6BISendResponseProvider@@@; const NOTIFICATION_SEND_RESPONSE::`vftable'{for `ISendResponseProvider'}
0x180004618  mov     [rbx+88h], rax
0x18000461f  setnz   al
0x180004622  mov     [rbx+0A4h], al
0x180004628  movzx   eax, byte ptr [rsp+0A8h+arg_8]
0x180004630  mov     [rbx+0A6h], al
0x180004636  mov     [rbx+98h], rbp
0x18000463d  mov     [rbx+0A0h], r8d
0x180004644  mov     [rbx+0A5h], bpl
0x18000464b  mov     rcx, [rsi+50h]
0x18000464f  mov     [rbx+50h], rcx
0x180004653  mov     rax, [rsi+58h]
0x180004657  mov     [rbx+58h], rax
0x18000465b  mov     r8, [rsi+68h]
0x18000465f  mov     [rbx+68h], r8
0x180004663  mov     eax, [rsi+78h]
0x180004666  mov     [rbx+78h], eax
0x180004669  mov     rax, [rsi+70h]
0x18000466d  mov     [rbx+70h], rax
0x180004671  test    rcx, rcx
0x180004674  jz      short loc_18000469E
0x180004676  mov     edx, [rsp+0A8h+var_68]
0x18000467a  mov     dword ptr [rbx+8], 20000000h
0x180004681  mov     [rbx+0Ch], bpl
0x180004685  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x18000468c  mov     ecx, [rax+0E8h]
0x180004692  mov     [rbx+7Ch], ecx
0x180004695  cmp     edx, 0FFFFFFFFh
0x180004698  jnz     loc_1800048E5
0x18000469e  test    r15d, r15d
0x1800046a1  jz      loc_1800047B6
0x1800046a7  mov     rsi, [r13+50h]
0x1800046ab  test    rsi, rsi
0x1800046ae  jz      short loc_1800046D0
0x1800046b0  lock inc dword ptr [rsi+24h]
0x1800046b4  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x1800046bb  test    rcx, rcx
0x1800046be  jz      short loc_1800046CC
0x1800046c0  mov     edx, [rsi+24h]
0x1800046c3  mov     r8, rsi
0x1800046c6  call    cs:__imp_WriteRefTraceLog
0x1800046cc  lock inc dword ptr [rsi+34h]
0x1800046d0  mov     [rbx+38h], rsi
0x1800046d4  mov     rcx, rbx
0x1800046d7  mov     [r13+50h], rbx
0x1800046db  mov     rax, [rbx]
0x1800046de  mov     rax, [rax+18h]
0x1800046e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046e7  mov     rax, [rbx]
0x1800046ea  xor     r13d, r13d
0x1800046ed  xor     r9d, r9d
0x1800046f0  mov     dword ptr [rsp+0A8h+var_88], r13d
0x1800046f5  xor     r8d, r8d
0x1800046f8  xor     edx, edx
0x1800046fa  mov     rcx, rbx
0x1800046fd  mov     rax, [rax+8]
0x180004701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004706  mov     esi, eax
0x180004708  cmp     eax, 1
0x18000470b  jz      loc_18000479E
0x180004711  test    ebp, ebp
0x180004713  jz      short loc_180004746
0x180004715  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x18000471b  call    cs:__imp_TlsGetValue
0x180004721  mov     rcx, [rbx+40h]; hObject
0x180004725  test    rax, rax
0x180004728  jnz     loc_180004932
0x18000472e  mov     rdx, rcx; lpTlsValue
0x180004731  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x180004737  call    cs:__imp_TlsSetValue
0x18000473d  mov     [rbx+40h], r13
0x180004741  cmp     esi, 1
0x180004744  jz      short loc_1800047A6
0x180004746  test    esi, esi
0x180004748  jnz     short loc_180004776
0x18000474a  test    r14, r14
0x18000474d  jz      short loc_180004752
0x18000474f  mov     [r14], r13d
0x180004752  mov     edi, [rbx+48h]
0x180004755  mov     rcx, rbx
0x180004758  mov     esi, [rbx+4Ch]
0x18000475b  call    ?FinishNotificationLoop@W3_CONTEXT_BASE@@SA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@@Z; W3_CONTEXT_BASE::FinishNotificationLoop(NOTIFICATION_CONTEXT *)
0x180004760  test    edi, edi
0x180004762  js      short loc_180004776
0x180004764  test    r15d, r15d
0x180004767  jz      short loc_180004772
0x180004769  test    r14, r14
0x18000476c  jz      loc_18000493D
0x180004772  mov     [r12], esi
0x180004776  mov     eax, edi
0x180004778  mov     rdi, [rsp+0A8h+arg_10]
0x180004780  add     rsp, 70h
0x180004784  pop     r15
0x180004786  pop     r14
0x180004788  pop     r13
0x18000478a  pop     r12
0x18000478c  pop     rsi
0x18000478d  pop     rbp
0x18000478e  pop     rbx
0x18000478f  retn
0x180004790  test    r14, r14
0x180004793  jz      loc_18000438E
0x180004799  jmp     loc_180004385
0x18000479e  test    ebp, ebp
0x1800047a0  jnz     loc_18000491B
0x1800047a6  test    r14, r14
0x1800047a9  jz      short loc_1800047B2
0x1800047ab  mov     dword ptr [r14], 1
0x1800047b2  xor     eax, eax
0x1800047b4  jmp     short loc_180004778
0x1800047b6  mov     rcx, rbx; this
0x1800047b9  mov     ebp, 1
0x1800047be  call    ?SetupSynchronousCall@NOTIFICATION_CONTEXT@@QEAAJXZ; NOTIFICATION_CONTEXT::SetupSynchronousCall(void)
0x1800047c3  test    eax, eax
0x1800047c5  jns     loc_1800046A7
0x1800047cb  mov     [rbx+48h], eax
0x1800047ce  xor     r13d, r13d
0x1800047d1  jmp     loc_18000474A
0x1800047d6  cmp     qword ptr [rsi+50h], 0
0x1800047db  jz      loc_18000442B
0x1800047e1  mov     rcx, [rsi+70h]
0x1800047e5  mov     rdx, [rsi+68h]
0x1800047e9  mov     eax, [rcx+0ECh]
0x1800047ef  cmp     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x1800047f3  jnz     loc_1800044FA
0x1800047f9  mov     eax, [rcx+0E8h]
0x1800047ff  cmp     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x180004803  jz      loc_18000442B
0x180004809  jmp     loc_1800044FA
0x18000480e  cmp     byte ptr [rbx+2484h], 0
0x180004815  mov     edx, 1
0x18000481a  mov     eax, 101h
0x18000481f  cmovnz  edx, eax
0x180004822  mov     [rsp+0A8h+arg_0], edx
0x180004829  jmp     loc_1800043F2
0x18000482e  cmp     dword ptr [rcx+134h], 0
0x180004835  jz      loc_180004406
0x18000483b  or      edx, 8
0x18000483e  mov     [rsp+0A8h+arg_0], edx
0x180004845  jmp     loc_180004406
0x18000484a  or      edx, 2
0x18000484d  mov     [rsp+0A8h+arg_0], edx
  ... truncated ...
```
