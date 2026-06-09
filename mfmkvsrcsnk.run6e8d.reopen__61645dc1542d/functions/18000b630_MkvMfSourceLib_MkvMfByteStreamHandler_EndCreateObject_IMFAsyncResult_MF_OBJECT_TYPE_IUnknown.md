# MkvMfSourceLib::MkvMfByteStreamHandler::EndCreateObject(IMFAsyncResult *,MF_OBJECT_TYPE *,IUnknown * *)

- ea: `0x18000b630`
- end: `0x18000b9f5`
- name: `?EndCreateObject@MkvMfByteStreamHandler@MkvMfSourceLib@@UEAAJPEAUIMFAsyncResult@@PEAW4MF_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z`
- size: `965`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfByteStreamHandler *__hidden this, struct IMFAsyncResult *, enum MF_OBJECT_TYPE *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000b630`
- `0x18000e49c`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b657`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b657`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b9da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b9da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b676`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b6f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b778`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b804`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b88c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b91b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b676`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b6f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b778`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b804`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b88c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b91b`

## string_xrefs

- `0x18000b978`: `MkvMfSourceLib::MkvMfByteStreamHandler::EndCreateObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvMfSourceLib::MkvMfByteStreamHandler::EndCreateObject(
        MkvMfSourceLib::MkvMfByteStreamHandler *this,
        struct IMFAsyncResult *a2,
        enum MF_OBJECT_TYPE *a3,
        struct IUnknown **a4)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbp
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // edi
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v15; // r9d
  int v16; // r8d
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  HRESULT (__stdcall *GetObjectA)(IMFAsyncResult *, IUnknown **); // rbx
  MkvMfSourceLib::MkvMfSource *v35; // [rsp+40h] [rbp+8h] BYREF
  char *v36; // [rsp+48h] [rbp+10h]

  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  v36 = (char *)this + 56;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( !a2 )
  {
    v11 = -2147024809;
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( !*((_BYTE *)v12 + 8) )
      goto LABEL_57;
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
    if ( *((_DWORD *)ThreadRelativeContext + 499) == -2147024809 )
      goto LABEL_57;
    v15 = -2147024809;
    v16 = 94;
    goto LABEL_56;
  }
  if ( !a3 )
  {
    v11 = -2147024809;
    v17 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( !*((_BYTE *)v17 + 8) )
      goto LABEL_57;
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)ThreadRelativeContext + 499) == -2147024809 )
      goto LABEL_57;
    v15 = -2147024809;
    v16 = 95;
    goto LABEL_56;
  }
  if ( !a4 )
  {
    v11 = -2147467261;
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( !*((_BYTE *)v19 + 8) )
      goto LABEL_57;
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
    if ( *((_DWORD *)ThreadRelativeContext + 499) == -2147467261 )
      goto LABEL_57;
    v16 = 96;
    goto LABEL_55;
  }
  *a4 = 0;
  *a3 = MF_OBJECT_INVALID;
  if ( LODWORD(a2[12].lpVtbl) )
  {
    v11 = -1072875795;
    v21 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( !*((_BYTE *)v21 + 8) )
      goto LABEL_57;
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
    if ( *((_DWORD *)ThreadRelativeContext + 499) == -1072875795 )
      goto LABEL_57;
    v16 = 104;
    goto LABEL_55;
  }
  v11 = ((__int64 (__fastcall *)(struct IMFAsyncResult *))a2->lpVtbl->GetStatus)(a2);
  if ( v11 < 0 )
  {
    v26 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( !*((_BYTE *)v26 + 8) )
      goto LABEL_57;
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
    if ( *((_DWORD *)ThreadRelativeContext + 499) == v11 )
      goto LABEL_57;
    v16 = 107;
    goto LABEL_55;
  }
  v11 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, struct IUnknown **))a2->lpVtbl->GetObjectA)(a2, a4);
  if ( v11 >= 0 )
  {
    *a3 = MF_OBJECT_MEDIASOURCE;
    goto LABEL_62;
  }
  v31 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
    CallStackTracing::s_wpInstance = v32;
    if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v31 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v31 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
    {
      v16 = 109;
LABEL_55:
      v15 = v11;
LABEL_56:
      CallStackContext::TraceFailure(
        ThreadRelativeContext,
        "MkvMfSourceLib::MkvMfByteStreamHandler::EndCreateObject",
        v16,
        v15);
    }
  }
LABEL_57:
  v35 = 0;
  if ( a2 )
  {
    GetObjectA = a2->lpVtbl->GetObjectA;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    if ( ((int (__fastcall *)(struct IMFAsyncResult *, MkvMfSourceLib::MkvMfSource **))GetObjectA)(a2, &v35) >= 0 )
      MkvMfSourceLib::MkvMfSource::Close(v35);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
LABEL_62:
  LeaveCriticalSection(v7);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000b630  mov     [rsp+arg_10], rbx
0x18000b635  mov     [rsp+arg_18], rbp
0x18000b63a  push    rsi
0x18000b63b  push    rdi
0x18000b63c  push    r14
0x18000b63e  sub     rsp, 20h
0x18000b642  mov     rsi, r9
0x18000b645  mov     rbx, r8
0x18000b648  mov     r14, rdx
0x18000b64b  lea     rbp, [rcx+38h]
0x18000b64f  mov     [rsp+38h+arg_8], rbp
0x18000b654  mov     rcx, rbp; lpCriticalSection
0x18000b657  call    cs:__imp_EnterCriticalSection
0x18000b65d  nop
0x18000b65e  test    r14, r14
0x18000b661  jnz     short loc_18000B6E0
0x18000b663  mov     ebx, 80070057h
0x18000b668  mov     edi, ebx
0x18000b66a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b671  test    rcx, rcx
0x18000b674  jnz     short loc_18000B6B7
0x18000b676  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b67c  mov     rcx, rax
0x18000b67f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b686  test    rax, rax
0x18000b689  jz      short loc_18000B6A9
0x18000b68b  mov     rax, [rax]
0x18000b68e  mov     edx, 7F0h
0x18000b693  mov     rax, [rax+8]
0x18000b697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b69c  test    eax, eax
0x18000b69e  jz      short loc_18000B6A9
0x18000b6a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b6a7  jmp     short loc_18000B6B7
0x18000b6a9  lea     rcx, qword_1800D6F70; this
0x18000b6b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b6b7  cmp     byte ptr [rcx+8], 0
0x18000b6bb  jz      loc_18000B987
0x18000b6c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b6c6  cmp     [rax+7CCh], ebx
0x18000b6cc  jz      loc_18000B987
0x18000b6d2  mov     r9d, ebx
0x18000b6d5  mov     r8d, 5Eh ; '^'
0x18000b6db  jmp     loc_18000B978
0x18000b6e0  test    rbx, rbx
0x18000b6e3  jnz     short loc_18000B762
0x18000b6e5  mov     ebx, 80070057h
0x18000b6ea  mov     edi, ebx
0x18000b6ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b6f3  test    rcx, rcx
0x18000b6f6  jnz     short loc_18000B739
0x18000b6f8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b6fe  mov     rcx, rax
0x18000b701  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b708  test    rax, rax
0x18000b70b  jz      short loc_18000B72B
0x18000b70d  mov     rax, [rax]
0x18000b710  mov     edx, 7F0h
0x18000b715  mov     rax, [rax+8]
0x18000b719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b71e  test    eax, eax
0x18000b720  jz      short loc_18000B72B
0x18000b722  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b729  jmp     short loc_18000B739
0x18000b72b  lea     rcx, qword_1800D6F70; this
0x18000b732  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b739  cmp     byte ptr [rcx+8], 0
0x18000b73d  jz      loc_18000B987
0x18000b743  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b748  cmp     [rax+7CCh], ebx
0x18000b74e  jz      loc_18000B987
0x18000b754  mov     r9d, ebx
0x18000b757  mov     r8d, 5Fh ; '_'
0x18000b75d  jmp     loc_18000B978
0x18000b762  test    rsi, rsi
0x18000b765  jnz     short loc_18000B7DF
0x18000b767  mov     edi, 80004003h
0x18000b76c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b773  test    rcx, rcx
0x18000b776  jnz     short loc_18000B7B9
0x18000b778  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b77e  mov     rcx, rax
0x18000b781  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b788  test    rax, rax
0x18000b78b  jz      short loc_18000B7AB
0x18000b78d  mov     rax, [rax]
0x18000b790  mov     edx, 7F0h
0x18000b795  mov     rax, [rax+8]
0x18000b799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b79e  test    eax, eax
0x18000b7a0  jz      short loc_18000B7AB
0x18000b7a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b7a9  jmp     short loc_18000B7B9
0x18000b7ab  lea     rcx, qword_1800D6F70; this
0x18000b7b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b7b9  cmp     byte ptr [rcx+8], 0
0x18000b7bd  jz      loc_18000B987
0x18000b7c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b7c8  cmp     [rax+7CCh], edi
0x18000b7ce  jz      loc_18000B987
0x18000b7d4  mov     r8d, 60h ; '`'
0x18000b7da  jmp     loc_18000B975
0x18000b7df  mov     qword ptr [rsi], 0
0x18000b7e6  mov     dword ptr [rbx], 2
0x18000b7ec  cmp     dword ptr [r14+60h], 0
0x18000b7f1  jz      short loc_18000B86B
0x18000b7f3  mov     edi, 0C00D36EDh
0x18000b7f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b7ff  test    rcx, rcx
0x18000b802  jnz     short loc_18000B845
0x18000b804  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b80a  mov     rcx, rax
0x18000b80d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b814  test    rax, rax
0x18000b817  jz      short loc_18000B837
0x18000b819  mov     rax, [rax]
0x18000b81c  mov     edx, 7F0h
0x18000b821  mov     rax, [rax+8]
0x18000b825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b82a  test    eax, eax
0x18000b82c  jz      short loc_18000B837
0x18000b82e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b835  jmp     short loc_18000B845
0x18000b837  lea     rcx, qword_1800D6F70; this
0x18000b83e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b845  cmp     byte ptr [rcx+8], 0
0x18000b849  jz      loc_18000B987
0x18000b84f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b854  cmp     [rax+7CCh], edi
0x18000b85a  jz      loc_18000B987
0x18000b860  mov     r8d, 68h ; 'h'
0x18000b866  jmp     loc_18000B975
0x18000b86b  mov     rax, [r14]
0x18000b86e  mov     rcx, r14
0x18000b871  mov     rax, [rax+20h]
0x18000b875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b87a  mov     edi, eax
0x18000b87c  test    eax, eax
0x18000b87e  jns     short loc_18000B8F3
0x18000b880  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b887  test    rcx, rcx
0x18000b88a  jnz     short loc_18000B8CD
0x18000b88c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b892  mov     rcx, rax
0x18000b895  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b89c  test    rax, rax
0x18000b89f  jz      short loc_18000B8BF
0x18000b8a1  mov     rax, [rax]
0x18000b8a4  mov     edx, 7F0h
0x18000b8a9  mov     rax, [rax+8]
0x18000b8ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8b2  test    eax, eax
0x18000b8b4  jz      short loc_18000B8BF
0x18000b8b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b8bd  jmp     short loc_18000B8CD
0x18000b8bf  lea     rcx, qword_1800D6F70; this
0x18000b8c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b8cd  cmp     byte ptr [rcx+8], 0
0x18000b8d1  jz      loc_18000B987
0x18000b8d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b8dc  cmp     [rax+7CCh], edi
0x18000b8e2  jz      loc_18000B987
0x18000b8e8  mov     r8d, 6Bh ; 'k'
0x18000b8ee  jmp     loc_18000B975
0x18000b8f3  mov     rax, [r14]
0x18000b8f6  mov     rdx, rsi
0x18000b8f9  mov     rcx, r14
0x18000b8fc  mov     rax, [rax+30h]
0x18000b900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b905  mov     edi, eax
0x18000b907  test    eax, eax
0x18000b909  jns     loc_18000B9D1
0x18000b90f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b916  test    rcx, rcx
0x18000b919  jnz     short loc_18000B95C
0x18000b91b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b921  mov     rcx, rax
0x18000b924  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b92b  test    rax, rax
0x18000b92e  jz      short loc_18000B94E
0x18000b930  mov     rax, [rax]
0x18000b933  mov     edx, 7F0h
0x18000b938  mov     rax, [rax+8]
0x18000b93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b941  test    eax, eax
0x18000b943  jz      short loc_18000B94E
0x18000b945  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b94c  jmp     short loc_18000B95C
0x18000b94e  lea     rcx, qword_1800D6F70; this
0x18000b955  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b95c  cmp     byte ptr [rcx+8], 0
0x18000b960  jz      short loc_18000B987
0x18000b962  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b967  cmp     [rax+7CCh], edi
0x18000b96d  jz      short loc_18000B987
0x18000b96f  mov     r8d, 6Dh ; 'm'; int
0x18000b975  mov     r9d, edi; int
0x18000b978  lea     rdx, aMkvmfsourcelib_152; "MkvMfSourceLib::MkvMfByteStreamHandler:"...
0x18000b97f  mov     rcx, rax; this
0x18000b982  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000b987  mov     [rsp+38h+arg_0], 0
0x18000b990  test    r14, r14
0x18000b993  jz      short loc_18000B9C5
0x18000b995  mov     rax, [r14]
0x18000b998  mov     rbx, [rax+30h]
0x18000b99c  lea     rcx, [rsp+38h+arg_0]
0x18000b9a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b9a6  lea     rdx, [rsp+38h+arg_0]
0x18000b9ab  mov     rcx, r14
0x18000b9ae  mov     rax, rbx
0x18000b9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9b6  test    eax, eax
0x18000b9b8  js      short loc_18000B9C5
0x18000b9ba  mov     rcx, [rsp+38h+arg_0]; this
0x18000b9bf  call    ?Close@MkvMfSource@MkvMfSourceLib@@QEAAXXZ; MkvMfSourceLib::MkvMfSource::Close(void)
0x18000b9c4  nop
0x18000b9c5  lea     rcx, [rsp+38h+arg_0]
0x18000b9ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b9cf  jmp     short loc_18000B9D7
0x18000b9d1  mov     dword ptr [rbx], 0
0x18000b9d7  mov     rcx, rbp; lpCriticalSection
0x18000b9da  call    cs:__imp_LeaveCriticalSection
0x18000b9e0  mov     eax, edi
0x18000b9e2  mov     rbx, [rsp+38h+arg_10]
0x18000b9e7  mov     rbp, [rsp+38h+arg_18]
0x18000b9ec  add     rsp, 20h
0x18000b9f0  pop     r14
0x18000b9f2  pop     rdi
0x18000b9f3  pop     rsi
0x18000b9f4  retn
```
