# CreateNotifySession(_CNOTIFY *,_CLUSTER *,CLUSTER_NOTIFICATIONS_VERSION)

- ea: `0x18005c114`
- end: `0x18005c41c`
- name: `?CreateNotifySession@@YAPEAU_CNOTIFY_SESSION@@PEAU_CNOTIFY@@PEAU_CLUSTER@@W4CLUSTER_NOTIFICATIONS_VERSION@@@Z`
- size: `776`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x18005d99c`
- `0x18005e840`
- `0x18005ea10`
- `0x18005f310`

## callees

- `0x18005acb8`
- `0x18005ae80`
- `0x18005c114`
- `0x18005e5a0`
- `0x18006f910`
- `0x180090a64`

## import_xrefs

- `RPCRT4!RpcSmDestroyClientContext` at `0x18005c2d5`
- `RPCRT4!RpcSmDestroyClientContext` at `0x18005c2d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c3cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c3cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c3a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c3a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c331`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c2e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c2e7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005c322`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005c322`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c2de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c2de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c18b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c18b`

## string_xrefs

- `0x18005c168`: `CreateNotifySession`
- `0x18005c1b9`: `CreateNotifySession`
- `0x18005c344`: `CreateNotifySession`
- `0x18005c3e3`: `CreateNotifySession`
- `0x18005c1a7`: `Calling ApiCreateNotify`
- `0x18005c34b`: `Create notify thread failed - %d`
- `0x18005c3fa`: `Session=0x%p hNotifyRpc=0x%p Thread=0x%p\n`
- `0x18005c1e4`: `ApiCreateNotifyV2`
- `0x18005c211`: `ApiCreateNotify`

## pseudocode

```c
_QWORD *__fastcall CreateNotifySession(_QWORD *a1, __int64 a2, int a3)
{
  _QWORD *v3; // rbx
  DWORD v8; // ecx
  __int64 v9; // rax
  __int64 v10; // rdx
  _QWORD *v11; // r15
  char v12; // al
  HANDLE Thread; // rax
  _QWORD *v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rsi
  __int64 *v16; // rdi
  __int64 v17; // rdx
  LPDWORD lpThreadId; // [rsp+28h] [rbp-40h]
  const char *v19; // [rsp+40h] [rbp-28h] BYREF
  __int64 v20; // [rsp+48h] [rbp-20h]
  DWORD *p_dwErrCode; // [rsp+50h] [rbp-18h]
  DWORD dwErrCode; // [rsp+B0h] [rbp+48h] BYREF

  v3 = (_QWORD *)*a1;
  dwErrCode = 0;
  while ( v3 != a1 )
  {
    if ( v3[6] == a2 && *((_DWORD *)v3 + 24) == a3 )
    {
      TraceMsg(4, 7, L"CreateNotifySession", 829, L"found a matching session: %p", v3);
      return v3;
    }
    v3 = (_QWORD *)*v3;
  }
  v3 = LocalAlloc(0, 0x128u);
  if ( v3 )
  {
    TraceMsg(4, 7, L"CreateNotifySession", 848, L"Calling ApiCreateNotify");
    if ( a3 == 1 )
    {
      v19 = "ApiCreateNotify";
      v20 = a2 + 40;
      p_dwErrCode = &dwErrCode;
      v9 = ReconnectOnNull<CreateNotifyFunctor>(&v19, &dwErrCode, a2);
    }
    else
    {
      if ( a3 != 2 )
      {
        v8 = 87;
        goto LABEL_29;
      }
      v19 = "ApiCreateNotifyV2";
      v20 = a2 + 40;
      p_dwErrCode = &dwErrCode;
      v9 = ReconnectOnNull<CreateNotifyV2Functor>(&v19, &dwErrCode, a2);
    }
    v11 = v3 + 7;
    v3[7] = v9;
    if ( !v9 || dwErrCode )
    {
LABEL_28:
      LocalFree(v3);
      v8 = dwErrCode;
      goto LABEL_29;
    }
    LOBYTE(v10) = 0;
    v3[5] = v3 + 4;
    v3[4] = v3 + 4;
    *(_QWORD *)((char *)v3 + 284) = 0;
    *((_DWORD *)v3 + 70) = 0;
    v3[6] = a2;
    v3[10] = a1;
    v3[11] = 0;
    *((_DWORD *)v3 + 24) = a3;
    v3[8] = 0;
    v3[9] = 0;
    if ( *(_WORD *)(a2 + 324) <= 7u )
    {
      v12 = 0;
      if ( *(_WORD *)(a2 + 324) != 7 )
        goto LABEL_21;
      LOBYTE(v10) = *(_WORD *)(a2 + 326) < 0x1FAEu;
    }
    v12 = 1;
LABEL_21:
    if ( dwErrCode )
    {
LABEL_25:
      if ( (unsigned int)ApiCloseNotify(v3 + 7, v10) && *v11 )
        RpcSmDestroyClientContext((void **)v3 + 7);
      goto LABEL_28;
    }
    if ( v12 )
    {
      if ( !(_BYTE)v10 || a3 != 1 )
      {
        dwErrCode = StartAsyncNotifications((struct _CNOTIFY_SESSION *)v3);
        goto LABEL_35;
      }
    }
    else if ( a3 != 1 )
    {
      dwErrCode = 1745;
      goto LABEL_25;
    }
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)NotifyThread, v3, 0, 0);
    v3[8] = Thread;
    if ( !Thread )
    {
      LODWORD(lpThreadId) = GetLastError();
      dwErrCode = (unsigned int)lpThreadId;
      TraceMsg(2, 7, L"CreateNotifySession", 926, L"Create notify thread failed - %d", lpThreadId);
    }
LABEL_35:
    if ( !dwErrCode )
    {
      v14 = (_QWORD *)*a1;
      if ( *(_QWORD **)(*a1 + 8LL) != a1 )
        goto LABEL_39;
      v3[1] = a1;
      *v3 = v14;
      v14[1] = v3;
      *a1 = v3;
      v15 = (struct _RTL_CRITICAL_SECTION *)(a2 + 232);
      EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 232));
      v16 = (__int64 *)(a2 + 168);
      v17 = *v16;
      if ( *(__int64 **)(*v16 + 8) != v16 )
LABEL_39:
        __fastfail(3u);
      v3[2] = v17;
      v3[3] = v16;
      *(_QWORD *)(v17 + 8) = v3 + 2;
      *v16 = (__int64)(v3 + 2);
      LeaveCriticalSection(v15);
      TraceMsg(4, 7, L"CreateNotifySession", 954, L"Session=0x%p hNotifyRpc=0x%p Thread=0x%p\n", v3, *v11, NotifyThread);
      return v3;
    }
    goto LABEL_25;
  }
  v8 = 8;
LABEL_29:
  SetLastError(v8);
  return 0;
}

```

## disassembly

```asm
0x18005c114  push    rbp
0x18005c116  push    rbx
0x18005c117  push    rsi
0x18005c118  push    rdi
0x18005c119  push    r12
0x18005c11b  push    r13
0x18005c11d  push    r14
0x18005c11f  push    r15
0x18005c121  mov     rbp, rsp
0x18005c124  sub     rsp, 68h
0x18005c128  mov     rbx, [rcx]
0x18005c12b  xor     r13d, r13d
0x18005c12e  mov     [rbp+dwErrCode], r13d
0x18005c132  mov     r14d, r8d
0x18005c135  mov     rdi, rdx
0x18005c138  mov     rsi, rcx
0x18005c13b  cmp     rbx, rsi
0x18005c13e  jz      short loc_18005C184
0x18005c140  cmp     [rbx+30h], rdi
0x18005c144  jnz     short loc_18005C14C
0x18005c146  cmp     [rbx+60h], r14d
0x18005c14a  jz      short loc_18005C151
0x18005c14c  mov     rbx, [rbx]
0x18005c14f  jmp     short loc_18005C13B
0x18005c151  mov     edx, 7
0x18005c156  mov     [rsp+68h+lpThreadId], rbx
0x18005c15b  lea     rax, aFoundAMatching; "found a matching session: %p"
0x18005c162  mov     r9d, 33Dh
0x18005c168  lea     r8, aCreatenotifyse; "CreateNotifySession"
0x18005c16f  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x18005c174  lea     ecx, [rdx-3]
0x18005c177  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c17c  mov     rax, rbx
0x18005c17f  jmp     loc_18005C2EF
0x18005c184  mov     edx, 128h; uBytes
0x18005c189  xor     ecx, ecx; uFlags
0x18005c18b  call    cs:__imp_LocalAlloc
0x18005c191  mov     rbx, rax
0x18005c194  test    rax, rax
0x18005c197  jnz     short loc_18005C1A1
0x18005c199  lea     ecx, [rax+8]
0x18005c19c  jmp     loc_18005C2E7
0x18005c1a1  mov     r12d, 7
0x18005c1a7  lea     rax, aCallingApicrea_0; "Calling ApiCreateNotify"
0x18005c1ae  mov     r9d, 350h
0x18005c1b4  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x18005c1b9  lea     r8, aCreatenotifyse; "CreateNotifySession"
0x18005c1c0  mov     edx, r12d
0x18005c1c3  lea     ecx, [r12-3]
0x18005c1c8  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c1cd  mov     ecx, r14d
0x18005c1d0  sub     ecx, 1
0x18005c1d3  jz      short loc_18005C211
0x18005c1d5  cmp     ecx, 1
0x18005c1d8  jz      short loc_18005C1E4
0x18005c1da  lea     ecx, [r12+50h]
0x18005c1df  jmp     loc_18005C2E7
0x18005c1e4  lea     rax, aApicreatenotif_0; "ApiCreateNotifyV2"
0x18005c1eb  mov     r8, rdi
0x18005c1ee  mov     [rbp+var_28], rax
0x18005c1f2  lea     rdx, [rbp+dwErrCode]
0x18005c1f6  lea     rax, [rdi+28h]
0x18005c1fa  mov     [rbp+var_20], rax
0x18005c1fe  lea     rcx, [rbp+var_28]
0x18005c202  lea     rax, [rbp+dwErrCode]
0x18005c206  mov     [rbp+var_18], rax
0x18005c20a  call    ??$ReconnectOnNull@VCreateNotifyV2Functor@@@@YAPEAXAEBVCreateNotifyV2Functor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<CreateNotifyV2Functor>(CreateNotifyV2Functor const &,ulong *,_CLUSTER *)
0x18005c20f  jmp     short loc_18005C23C
0x18005c211  lea     rax, aApicreatenotif; "ApiCreateNotify"
0x18005c218  mov     r8, rdi
0x18005c21b  mov     [rbp+var_28], rax
0x18005c21f  lea     rdx, [rbp+dwErrCode]
0x18005c223  lea     rax, [rdi+28h]
0x18005c227  mov     [rbp+var_20], rax
0x18005c22b  lea     rcx, [rbp+var_28]
0x18005c22f  lea     rax, [rbp+dwErrCode]
0x18005c233  mov     [rbp+var_18], rax
0x18005c237  call    ??$ReconnectOnNull@VCreateNotifyFunctor@@@@YAPEAXAEBVCreateNotifyFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<CreateNotifyFunctor>(CreateNotifyFunctor const &,ulong *,_CLUSTER *)
0x18005c23c  lea     r15, [rbx+38h]
0x18005c240  mov     [r15], rax
0x18005c243  test    rax, rax
0x18005c246  jz      loc_18005C2DB
0x18005c24c  cmp     [rbp+dwErrCode], r13d
0x18005c250  jnz     loc_18005C2DB
0x18005c256  lea     rax, [rbx+20h]
0x18005c25a  mov     dl, r13b
0x18005c25d  mov     [rax+8], rax
0x18005c261  mov     [rax], rax
0x18005c264  mov     [rbx+11Ch], r13
0x18005c26b  mov     [rbx+118h], r13d
0x18005c272  mov     [rbx+30h], rdi
0x18005c276  mov     [rbx+50h], rsi
0x18005c27a  mov     [rbx+58h], r13
0x18005c27e  mov     [rbx+60h], r14d
0x18005c282  mov     [rbx+40h], r13
0x18005c286  mov     [rbx+48h], r13
0x18005c28a  cmp     [rdi+144h], r12w
0x18005c292  ja      short loc_18005C2A8
0x18005c294  mov     al, r13b
0x18005c297  jnz     short loc_18005C2AA
0x18005c299  mov     ecx, 1FAEh
0x18005c29e  cmp     [rdi+146h], cx
0x18005c2a5  setb    dl
0x18005c2a8  mov     al, 1
0x18005c2aa  cmp     [rbp+dwErrCode], r13d
0x18005c2ae  jnz     short loc_18005C2C1
0x18005c2b0  test    al, al
0x18005c2b2  jnz     short loc_18005C300
0x18005c2b4  cmp     r14d, 1
0x18005c2b8  jz      short loc_18005C30A
0x18005c2ba  mov     [rbp+dwErrCode], 6D1h
0x18005c2c1  mov     rcx, r15
0x18005c2c4  call    ApiCloseNotify
0x18005c2c9  test    eax, eax
0x18005c2cb  jz      short loc_18005C2DB
0x18005c2cd  cmp     [r15], r13
0x18005c2d0  jz      short loc_18005C2DB
0x18005c2d2  mov     rcx, r15; ContextHandle
0x18005c2d5  call    cs:__imp_RpcSmDestroyClientContext
0x18005c2db  mov     rcx, rbx; hMem
0x18005c2de  call    cs:__imp_LocalFree
0x18005c2e4  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18005c2e7  call    cs:__imp_SetLastError
0x18005c2ed  xor     eax, eax
0x18005c2ef  add     rsp, 68h
0x18005c2f3  pop     r15
0x18005c2f5  pop     r14
0x18005c2f7  pop     r13
0x18005c2f9  pop     r12
0x18005c2fb  pop     rdi
0x18005c2fc  pop     rsi
0x18005c2fd  pop     rbx
0x18005c2fe  pop     rbp
0x18005c2ff  retn
0x18005c300  test    dl, dl
0x18005c302  jz      short loc_18005C366
0x18005c304  cmp     r14d, 1
0x18005c308  jnz     short loc_18005C366
0x18005c30a  mov     [rsp+68h+lpThreadId], r13; lpThreadId
0x18005c30f  lea     r8, ?NotifyThread@@YAKPEAX@Z; lpStartAddress
0x18005c316  mov     r9, rbx; lpParameter
0x18005c319  mov     [rsp+68h+dwCreationFlags], r13d; dwCreationFlags
0x18005c31e  xor     edx, edx; dwStackSize
0x18005c320  xor     ecx, ecx; lpThreadAttributes
0x18005c322  call    cs:__imp_CreateThread
0x18005c328  mov     [rbx+40h], rax
0x18005c32c  test    rax, rax
0x18005c32f  jnz     short loc_18005C371
0x18005c331  call    cs:__imp_GetLastError
0x18005c337  mov     dword ptr [rsp+68h+lpThreadId], eax
0x18005c33b  mov     r9d, 39Eh
0x18005c341  mov     [rbp+dwErrCode], eax
0x18005c344  lea     r8, aCreatenotifyse; "CreateNotifySession"
0x18005c34b  lea     rax, aCreateNotifyTh; "Create notify thread failed - %d"
0x18005c352  mov     edx, r12d
0x18005c355  mov     ecx, 2
0x18005c35a  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x18005c35f  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c364  jmp     short loc_18005C371
0x18005c366  mov     rcx, rbx; struct _CNOTIFY_SESSION *
0x18005c369  call    ?StartAsyncNotifications@@YAKPEAU_CNOTIFY_SESSION@@@Z; StartAsyncNotifications(_CNOTIFY_SESSION *)
0x18005c36e  mov     [rbp+dwErrCode], eax
0x18005c371  cmp     [rbp+dwErrCode], r13d
0x18005c375  jnz     loc_18005C2C1
0x18005c37b  mov     rax, [rsi]
0x18005c37e  cmp     [rax+8], rsi
0x18005c382  jnz     loc_18005C415
0x18005c388  mov     [rbx+8], rsi
0x18005c38c  mov     [rbx], rax
0x18005c38f  mov     [rax+8], rbx
0x18005c393  mov     [rsi], rbx
0x18005c396  lea     rsi, [rdi+0E8h]
0x18005c39d  mov     rcx, rsi; lpCriticalSection
0x18005c3a0  call    cs:__imp_EnterCriticalSection
0x18005c3a6  add     rdi, 0A8h
0x18005c3ad  mov     rdx, [rdi]
0x18005c3b0  cmp     [rdx+8], rdi
0x18005c3b4  jnz     short loc_18005C415
0x18005c3b6  lea     rax, [rbx+10h]
0x18005c3ba  mov     rcx, rsi; lpCriticalSection
0x18005c3bd  mov     [rax], rdx
0x18005c3c0  mov     [rax+8], rdi
0x18005c3c4  mov     [rdx+8], rax
0x18005c3c8  mov     [rdi], rax
0x18005c3cb  call    cs:__imp_LeaveCriticalSection
0x18005c3d1  lea     rax, ?NotifyThread@@YAKPEAX@Z; NotifyThread(void *)
0x18005c3d8  mov     r9d, 3BAh
0x18005c3de  mov     [rsp+68h+var_30], rax
0x18005c3e3  lea     r8, aCreatenotifyse; "CreateNotifySession"
0x18005c3ea  mov     rax, [r15]
0x18005c3ed  mov     edx, r12d
0x18005c3f0  mov     [rsp+68h+var_38], rax
0x18005c3f5  mov     ecx, 4
0x18005c3fa  lea     rax, aSession0xPHnot; "Session=0x%p hNotifyRpc=0x%p Thread=0x%"...
0x18005c401  mov     [rsp+68h+lpThreadId], rbx
0x18005c406  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x18005c40b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c410  jmp     loc_18005C17C
0x18005c415  mov     ecx, 3
0x18005c41a  int     29h; Win8: RtlFailFast(ecx)
```
