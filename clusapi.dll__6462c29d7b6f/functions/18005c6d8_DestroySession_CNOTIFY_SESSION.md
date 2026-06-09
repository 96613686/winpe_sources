# DestroySession(_CNOTIFY_SESSION *)

- ea: `0x18005c6d8`
- end: `0x18005c957`
- name: `?DestroySession@@YAXPEAU_CNOTIFY_SESSION@@@Z`
- size: `639`
- prototype: `void __fastcall(struct _CNOTIFY_SESSION *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005c424`

## callees

- `0x18005c6d8`
- `0x18006f910`
- `0x180090a64`
- `0x180090fc0`

## import_xrefs

- `RPCRT4!RpcSmDestroyClientContext` at `0x18005c919`
- `RPCRT4!RpcSmDestroyClientContext` at `0x18005c919`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005c7d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005c859`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005c7d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005c859`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c7bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c7bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c880`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c86f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c86f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c94b`

## string_xrefs

- `0x18005c727`: `Calling ApiUnblockGetNotifyThread before NotifyThread termination, hNotify = 0x%p`
- `0x18005c7e9`: `Calling ApiUnblockGetNotifyThread before NotifyThread termination, hNotify = 0x%p`
- `0x18005c72e`: `ApiUnblockGetNotifyThread returned error code 0x%x`
- `0x18005c838`: `ApiUnblockGetNotifyThread returned error code 0x%x`
- `0x18005c8a4`: `Calling RpcSmDestroyClientContext after terminating NotifyThread, hNotify = 0x%p`
- `0x18005c8c3`: `Calling ApiCloseNotify after terminating NotifyThread, hNotify = 0x%p`
- `0x18005c8fd`: `Calling RpcSmDestroyClientContext since ApiCloseNotify failed after terminating NotifyThread, hNotify = 0x%p, error %d`

## pseudocode

```c
void __fastcall DestroySession(struct _CNOTIFY_SESSION *a1)
{
  __int64 v2; // rax
  struct _CNOTIFY_SESSION **v3; // rcx
  void *v4; // rdi
  _QWORD *v5; // rdi
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rcx
  struct _CNOTIFY_SESSION **v9; // rdx
  __int64 v10; // [rsp+28h] [rbp-50h]
  __int64 v11; // [rsp+28h] [rbp-50h]
  __int64 v12; // [rsp+28h] [rbp-50h]
  int v13; // [rsp+30h] [rbp-48h]

  *((_DWORD *)a1 + 22) = 1;
  TraceMsg(4, 7, L"DestroySession", 3342, L"Destroying session 0x%p", a1);
  if ( (*(_DWORD *)(*((_QWORD *)a1 + 6) + 32LL) & 6) != 2 && *((_QWORD *)a1 + 7) )
  {
    TraceMsg(
      4,
      7,
      L"DestroySession",
      3353,
      L"Calling ApiUnblockGetNotifyThread before NotifyThread termination, hNotify = 0x%p",
      *((_QWORD *)a1 + 7));
    LODWORD(v10) = ApiUnblockGetNotifyCall(*((_QWORD *)a1 + 7));
    TraceMsg(4, 7, L"DestroySession", 3355, L"ApiUnblockGetNotifyThread returned error code 0x%x", v10);
  }
  v2 = *(_QWORD *)a1;
  if ( *(struct _CNOTIFY_SESSION **)(*(_QWORD *)a1 + 8LL) != a1
    || (v3 = (struct _CNOTIFY_SESSION **)*((_QWORD *)a1 + 1), *v3 != a1) )
  {
LABEL_23:
    __fastfail(3u);
  }
  *v3 = (struct _CNOTIFY_SESSION *)v2;
  *(_QWORD *)(v2 + 8) = v3;
  LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)a1 + 6) + 232LL));
  v4 = (void *)*((_QWORD *)a1 + 9);
  if ( !v4 )
    v4 = (void *)*((_QWORD *)a1 + 8);
  while ( WaitForSingleObject(v4, 0x1388u) == 258 )
  {
    if ( (*(_DWORD *)(*((_QWORD *)a1 + 6) + 32LL) & 6) != 2 && *((_QWORD *)a1 + 7) )
    {
      TraceMsg(
        4,
        7,
        L"DestroySession",
        3378,
        L"Calling ApiUnblockGetNotifyThread before NotifyThread termination, hNotify = 0x%p",
        *((_QWORD *)a1 + 7));
      LODWORD(v11) = ApiUnblockGetNotifyCall(*((_QWORD *)a1 + 7));
      TraceMsg(4, 7, L"DestroySession", 3380, L"ApiUnblockGetNotifyThread returned error code 0x%x", v11);
    }
  }
  CloseHandle(v4);
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)a1 + 6) + 232LL));
  v5 = (_QWORD *)((char *)a1 + 56);
  v12 = *((_QWORD *)a1 + 7);
  if ( (*(_BYTE *)(*((_QWORD *)a1 + 6) + 32LL) & 2) != 0 )
  {
    TraceMsg(
      4,
      7,
      L"DestroySession",
      3399,
      L"Calling RpcSmDestroyClientContext after terminating NotifyThread, hNotify = 0x%p",
      v12);
    if ( *v5 )
      goto LABEL_19;
  }
  else
  {
    TraceMsg(
      4,
      7,
      L"DestroySession",
      3406,
      L"Calling ApiCloseNotify after terminating NotifyThread, hNotify = 0x%p",
      v12);
    v7 = ApiCloseNotify((char *)a1 + 56, v6);
    if ( v7 && *v5 )
    {
      v13 = v7;
      TraceMsg(
        3,
        7,
        L"DestroySession",
        3414,
        L"Calling RpcSmDestroyClientContext since ApiCloseNotify failed after terminating NotifyThread, hNotify = 0x%p, error %d",
        *v5,
        v13);
LABEL_19:
      RpcSmDestroyClientContext((void **)a1 + 7);
    }
  }
  v8 = *((_QWORD *)a1 + 2);
  if ( *(struct _CNOTIFY_SESSION **)(v8 + 8) != (struct _CNOTIFY_SESSION *)((char *)a1 + 16) )
    goto LABEL_23;
  v9 = (struct _CNOTIFY_SESSION **)*((_QWORD *)a1 + 3);
  if ( *v9 != (struct _CNOTIFY_SESSION *)((char *)a1 + 16) )
    goto LABEL_23;
  *v9 = (struct _CNOTIFY_SESSION *)v8;
  *(_QWORD *)(v8 + 8) = v9;
  LocalFree(a1);
}

```

## disassembly

```asm
0x18005c6d8  push    rbx
0x18005c6da  push    rbp
0x18005c6db  push    rsi
0x18005c6dc  push    rdi
0x18005c6dd  push    r14
0x18005c6df  push    r15
0x18005c6e1  sub     rsp, 48h
0x18005c6e5  mov     [rsp+78h+var_50], rcx
0x18005c6ea  lea     rax, aDestroyingSess; "Destroying session 0x%p"
0x18005c6f1  mov     ebp, 7
0x18005c6f6  mov     dword ptr [rcx+58h], 1
0x18005c6fd  mov     rbx, rcx
0x18005c700  mov     [rsp+78h+var_58], rax
0x18005c705  lea     rsi, aDestroysession; "DestroySession"
0x18005c70c  mov     r9d, 0D0Eh
0x18005c712  mov     r8, rsi
0x18005c715  mov     edx, ebp
0x18005c717  lea     r14d, [rbp-3]
0x18005c71b  mov     ecx, r14d
0x18005c71e  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c723  mov     rax, [rbx+30h]
0x18005c727  lea     rdx, aCallingApiunbl; "Calling ApiUnblockGetNotifyThread befor"...
0x18005c72e  lea     rdi, aApiunblockgetn; "ApiUnblockGetNotifyThread returned erro"...
0x18005c735  mov     ecx, [rax+20h]
0x18005c738  and     cl, 6
0x18005c73b  cmp     cl, 2
0x18005c73e  jz      short loc_18005C78B
0x18005c740  mov     rax, [rbx+38h]
0x18005c744  test    rax, rax
0x18005c747  jz      short loc_18005C78B
0x18005c749  mov     [rsp+78h+var_50], rax
0x18005c74e  mov     r9d, 0D19h
0x18005c754  mov     [rsp+78h+var_58], rdx
0x18005c759  mov     r8, rsi
0x18005c75c  mov     edx, ebp
0x18005c75e  mov     ecx, r14d
0x18005c761  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c766  mov     rcx, [rbx+38h]
0x18005c76a  call    ApiUnblockGetNotifyCall
0x18005c76f  mov     dword ptr [rsp+78h+var_50], eax
0x18005c773  mov     r9d, 0D1Bh
0x18005c779  mov     r8, rsi
0x18005c77c  mov     [rsp+78h+var_58], rdi
0x18005c781  mov     edx, ebp
0x18005c783  mov     ecx, r14d
0x18005c786  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c78b  mov     rax, [rbx]
0x18005c78e  mov     r15d, 3
0x18005c794  cmp     [rax+8], rbx
0x18005c798  jnz     loc_18005C952
0x18005c79e  mov     rcx, [rbx+8]
0x18005c7a2  cmp     [rcx], rbx
0x18005c7a5  jnz     loc_18005C952
0x18005c7ab  mov     [rcx], rax
0x18005c7ae  mov     [rax+8], rcx
0x18005c7b2  mov     rcx, [rbx+30h]
0x18005c7b6  add     rcx, 0E8h; lpCriticalSection
0x18005c7bd  call    cs:__imp_LeaveCriticalSection
0x18005c7c3  mov     rdi, [rbx+48h]
0x18005c7c7  test    rdi, rdi
0x18005c7ca  jnz     short loc_18005C7D0
0x18005c7cc  mov     rdi, [rbx+40h]
0x18005c7d0  mov     edx, 1388h; dwMilliseconds
0x18005c7d5  mov     rcx, rdi; hHandle
0x18005c7d8  call    cs:__imp_WaitForSingleObject
0x18005c7de  cmp     eax, 102h
0x18005c7e3  jnz     loc_18005C86C
0x18005c7e9  lea     r15, aCallingApiunbl; "Calling ApiUnblockGetNotifyThread befor"...
0x18005c7f0  mov     rax, [rbx+30h]
0x18005c7f4  mov     ecx, [rax+20h]
0x18005c7f7  and     cl, 6
0x18005c7fa  cmp     cl, 2
0x18005c7fd  jz      short loc_18005C851
0x18005c7ff  mov     rax, [rbx+38h]
0x18005c803  test    rax, rax
0x18005c806  jz      short loc_18005C851
0x18005c808  mov     [rsp+78h+var_50], rax
0x18005c80d  mov     r9d, 0D32h
0x18005c813  mov     r8, rsi
0x18005c816  mov     [rsp+78h+var_58], r15
0x18005c81b  mov     edx, ebp
0x18005c81d  mov     ecx, r14d
0x18005c820  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c825  mov     rcx, [rbx+38h]
0x18005c829  call    ApiUnblockGetNotifyCall
0x18005c82e  mov     dword ptr [rsp+78h+var_50], eax
0x18005c832  mov     r9d, 0D34h
0x18005c838  lea     rax, aApiunblockgetn; "ApiUnblockGetNotifyThread returned erro"...
0x18005c83f  mov     r8, rsi
0x18005c842  mov     edx, ebp
0x18005c844  mov     [rsp+78h+var_58], rax
0x18005c849  mov     ecx, r14d
0x18005c84c  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c851  mov     edx, 1388h; dwMilliseconds
0x18005c856  mov     rcx, rdi; hHandle
0x18005c859  call    cs:__imp_WaitForSingleObject
0x18005c85f  cmp     eax, 102h
0x18005c864  jz      short loc_18005C7F0
0x18005c866  mov     r15d, 3
0x18005c86c  mov     rcx, rdi; hObject
0x18005c86f  call    cs:__imp_CloseHandle
0x18005c875  mov     rcx, [rbx+30h]
0x18005c879  add     rcx, 0E8h; lpCriticalSection
0x18005c880  call    cs:__imp_EnterCriticalSection
0x18005c886  mov     rax, [rbx+30h]
0x18005c88a  lea     rdi, [rbx+38h]
0x18005c88e  mov     r9, [rdi]
0x18005c891  mov     r8, rsi
0x18005c894  mov     [rsp+78h+var_50], r9
0x18005c899  mov     edx, ebp
0x18005c89b  mov     ecx, r14d
0x18005c89e  test    byte ptr [rax+20h], 2
0x18005c8a2  jz      short loc_18005C8C3
0x18005c8a4  lea     rax, aCallingRpcsmde_5; "Calling RpcSmDestroyClientContext after"...
0x18005c8ab  mov     r9d, 0D47h
0x18005c8b1  mov     [rsp+78h+var_58], rax
0x18005c8b6  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c8bb  cmp     qword ptr [rdi], 0
0x18005c8bf  jz      short loc_18005C91F
0x18005c8c1  jmp     short loc_18005C916
0x18005c8c3  lea     rax, aCallingApiclos; "Calling ApiCloseNotify after terminatin"...
0x18005c8ca  mov     r9d, 0D4Eh
0x18005c8d0  mov     [rsp+78h+var_58], rax
0x18005c8d5  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c8da  mov     rcx, rdi
0x18005c8dd  call    ApiCloseNotify
0x18005c8e2  test    eax, eax
0x18005c8e4  jz      short loc_18005C91F
0x18005c8e6  mov     rcx, [rdi]
0x18005c8e9  test    rcx, rcx
0x18005c8ec  jz      short loc_18005C91F
0x18005c8ee  mov     [rsp+78h+var_48], eax
0x18005c8f2  mov     r9d, 0D56h
0x18005c8f8  mov     [rsp+78h+var_50], rcx
0x18005c8fd  lea     rax, aCallingRpcsmde_9; "Calling RpcSmDestroyClientContext since"...
0x18005c904  mov     ecx, r15d
0x18005c907  mov     [rsp+78h+var_58], rax
0x18005c90c  mov     r8, rsi
0x18005c90f  mov     edx, ebp
0x18005c911  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005c916  mov     rcx, rdi; ContextHandle
0x18005c919  call    cs:__imp_RpcSmDestroyClientContext
0x18005c91f  lea     rax, [rbx+10h]
0x18005c923  mov     rcx, [rax]
0x18005c926  cmp     [rcx+8], rax
0x18005c92a  jnz     short loc_18005C952
0x18005c92c  mov     rdx, [rax+8]
0x18005c930  cmp     [rdx], rax
0x18005c933  jnz     short loc_18005C952
0x18005c935  mov     [rdx], rcx
0x18005c938  mov     [rcx+8], rdx
0x18005c93c  mov     rcx, rbx
0x18005c93f  add     rsp, 48h
0x18005c943  pop     r15
0x18005c945  pop     r14
0x18005c947  pop     rdi
0x18005c948  pop     rsi
0x18005c949  pop     rbp
0x18005c94a  pop     rbx
0x18005c94b  jmp     cs:__imp_LocalFree
0x18005c952  mov     rcx, r15
0x18005c955  int     29h; Win8: RtlFailFast(ecx)
```
