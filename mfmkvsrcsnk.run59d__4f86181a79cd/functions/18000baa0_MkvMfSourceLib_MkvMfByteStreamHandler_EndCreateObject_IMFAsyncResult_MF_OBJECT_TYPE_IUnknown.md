# MkvMfSourceLib::MkvMfByteStreamHandler::EndCreateObject(IMFAsyncResult *,MF_OBJECT_TYPE *,IUnknown * *)

- ea: `0x18000baa0`
- end: `0x18000be9e`
- name: `?EndCreateObject@MkvMfByteStreamHandler@MkvMfSourceLib@@UEAAJPEAUIMFAsyncResult@@PEAW4MF_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z`
- size: `1022`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfByteStreamHandler *__hidden this, struct IMFAsyncResult *, enum MF_OBJECT_TYPE *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000baa0`
- `0x18000eab8`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bac7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bac7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000be7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000be7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000baf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000bb7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000bc02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000bc94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000bd22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000bdb7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000baf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000bb7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000bc02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000bc94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000bd22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000bdb7`

## string_xrefs

- `0x18000be1a`: `MkvMfSourceLib::MkvMfByteStreamHandler::EndCreateObject`

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
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v17 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v19 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v21 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v26 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v31 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18000baa0  mov     [rsp+arg_10], rbx
0x18000baa5  mov     [rsp+arg_18], rbp
0x18000baaa  push    rsi
0x18000baab  push    rdi
0x18000baac  push    r14
0x18000baae  sub     rsp, 20h
0x18000bab2  mov     rsi, r9
0x18000bab5  mov     rbx, r8
0x18000bab8  mov     r14, rdx
0x18000babb  lea     rbp, [rcx+38h]
0x18000babf  mov     [rsp+38h+arg_8], rbp
0x18000bac4  mov     rcx, rbp; lpCriticalSection
0x18000bac7  call    cs:__imp_EnterCriticalSection
0x18000bace  nop     dword ptr [rax+rax+00h]
0x18000bad3  nop
0x18000bad4  test    r14, r14
0x18000bad7  jnz     loc_18000BB60
0x18000badd  mov     ebx, 80070057h
0x18000bae2  mov     edi, ebx
0x18000bae4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000baeb  test    rcx, rcx
0x18000baee  jnz     short loc_18000BB37
0x18000baf0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000baf7  nop     dword ptr [rax+rax+00h]
0x18000bafc  mov     rcx, rax
0x18000baff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bb06  test    rax, rax
0x18000bb09  jz      short loc_18000BB29
0x18000bb0b  mov     rax, [rax]
0x18000bb0e  mov     edx, 7F0h
0x18000bb13  mov     rax, [rax+8]
0x18000bb17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb1c  test    eax, eax
0x18000bb1e  jz      short loc_18000BB29
0x18000bb20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bb27  jmp     short loc_18000BB37
0x18000bb29  lea     rcx, qword_1800DBF70; this
0x18000bb30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bb37  cmp     byte ptr [rcx+8], 0
0x18000bb3b  jz      loc_18000BE29
0x18000bb41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000bb46  cmp     [rax+7CCh], ebx
0x18000bb4c  jz      loc_18000BE29
0x18000bb52  mov     r9d, ebx
0x18000bb55  mov     r8d, 5Eh ; '^'
0x18000bb5b  jmp     loc_18000BE1A
0x18000bb60  test    rbx, rbx
0x18000bb63  jnz     loc_18000BBEC
0x18000bb69  mov     ebx, 80070057h
0x18000bb6e  mov     edi, ebx
0x18000bb70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bb77  test    rcx, rcx
0x18000bb7a  jnz     short loc_18000BBC3
0x18000bb7c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000bb83  nop     dword ptr [rax+rax+00h]
0x18000bb88  mov     rcx, rax
0x18000bb8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bb92  test    rax, rax
0x18000bb95  jz      short loc_18000BBB5
0x18000bb97  mov     rax, [rax]
0x18000bb9a  mov     edx, 7F0h
0x18000bb9f  mov     rax, [rax+8]
0x18000bba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bba8  test    eax, eax
0x18000bbaa  jz      short loc_18000BBB5
0x18000bbac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bbb3  jmp     short loc_18000BBC3
0x18000bbb5  lea     rcx, qword_1800DBF70; this
0x18000bbbc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bbc3  cmp     byte ptr [rcx+8], 0
0x18000bbc7  jz      loc_18000BE29
0x18000bbcd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000bbd2  cmp     [rax+7CCh], ebx
0x18000bbd8  jz      loc_18000BE29
0x18000bbde  mov     r9d, ebx
0x18000bbe1  mov     r8d, 5Fh ; '_'
0x18000bbe7  jmp     loc_18000BE1A
0x18000bbec  test    rsi, rsi
0x18000bbef  jnz     short loc_18000BC6F
0x18000bbf1  mov     edi, 80004003h
0x18000bbf6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bbfd  test    rcx, rcx
0x18000bc00  jnz     short loc_18000BC49
0x18000bc02  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000bc09  nop     dword ptr [rax+rax+00h]
0x18000bc0e  mov     rcx, rax
0x18000bc11  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bc18  test    rax, rax
0x18000bc1b  jz      short loc_18000BC3B
0x18000bc1d  mov     rax, [rax]
0x18000bc20  mov     edx, 7F0h
0x18000bc25  mov     rax, [rax+8]
0x18000bc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc2e  test    eax, eax
0x18000bc30  jz      short loc_18000BC3B
0x18000bc32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bc39  jmp     short loc_18000BC49
0x18000bc3b  lea     rcx, qword_1800DBF70; this
0x18000bc42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bc49  cmp     byte ptr [rcx+8], 0
0x18000bc4d  jz      loc_18000BE29
0x18000bc53  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000bc58  cmp     [rax+7CCh], edi
0x18000bc5e  jz      loc_18000BE29
0x18000bc64  mov     r8d, 60h ; '`'
0x18000bc6a  jmp     loc_18000BE17
0x18000bc6f  mov     qword ptr [rsi], 0
0x18000bc76  mov     dword ptr [rbx], 2
0x18000bc7c  cmp     dword ptr [r14+60h], 0
0x18000bc81  jz      short loc_18000BD01
0x18000bc83  mov     edi, 0C00D36EDh
0x18000bc88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bc8f  test    rcx, rcx
0x18000bc92  jnz     short loc_18000BCDB
0x18000bc94  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000bc9b  nop     dword ptr [rax+rax+00h]
0x18000bca0  mov     rcx, rax
0x18000bca3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bcaa  test    rax, rax
0x18000bcad  jz      short loc_18000BCCD
0x18000bcaf  mov     rax, [rax]
0x18000bcb2  mov     edx, 7F0h
0x18000bcb7  mov     rax, [rax+8]
0x18000bcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc0  test    eax, eax
0x18000bcc2  jz      short loc_18000BCCD
0x18000bcc4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bccb  jmp     short loc_18000BCDB
0x18000bccd  lea     rcx, qword_1800DBF70; this
0x18000bcd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bcdb  cmp     byte ptr [rcx+8], 0
0x18000bcdf  jz      loc_18000BE29
0x18000bce5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000bcea  cmp     [rax+7CCh], edi
0x18000bcf0  jz      loc_18000BE29
0x18000bcf6  mov     r8d, 68h ; 'h'
0x18000bcfc  jmp     loc_18000BE17
0x18000bd01  mov     rax, [r14]
0x18000bd04  mov     rcx, r14
0x18000bd07  mov     rax, [rax+20h]
0x18000bd0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd10  mov     edi, eax
0x18000bd12  test    eax, eax
0x18000bd14  jns     short loc_18000BD8F
0x18000bd16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bd1d  test    rcx, rcx
0x18000bd20  jnz     short loc_18000BD69
0x18000bd22  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000bd29  nop     dword ptr [rax+rax+00h]
0x18000bd2e  mov     rcx, rax
0x18000bd31  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bd38  test    rax, rax
0x18000bd3b  jz      short loc_18000BD5B
0x18000bd3d  mov     rax, [rax]
0x18000bd40  mov     edx, 7F0h
0x18000bd45  mov     rax, [rax+8]
0x18000bd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd4e  test    eax, eax
0x18000bd50  jz      short loc_18000BD5B
0x18000bd52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bd59  jmp     short loc_18000BD69
0x18000bd5b  lea     rcx, qword_1800DBF70; this
0x18000bd62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bd69  cmp     byte ptr [rcx+8], 0
0x18000bd6d  jz      loc_18000BE29
0x18000bd73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000bd78  cmp     [rax+7CCh], edi
0x18000bd7e  jz      loc_18000BE29
0x18000bd84  mov     r8d, 6Bh ; 'k'
0x18000bd8a  jmp     loc_18000BE17
0x18000bd8f  mov     rax, [r14]
0x18000bd92  mov     rdx, rsi
0x18000bd95  mov     rcx, r14
0x18000bd98  mov     rax, [rax+30h]
0x18000bd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bda1  mov     edi, eax
0x18000bda3  test    eax, eax
0x18000bda5  jns     loc_18000BE73
0x18000bdab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bdb2  test    rcx, rcx
0x18000bdb5  jnz     short loc_18000BDFE
0x18000bdb7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000bdbe  nop     dword ptr [rax+rax+00h]
0x18000bdc3  mov     rcx, rax
0x18000bdc6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bdcd  test    rax, rax
0x18000bdd0  jz      short loc_18000BDF0
0x18000bdd2  mov     rax, [rax]
0x18000bdd5  mov     edx, 7F0h
0x18000bdda  mov     rax, [rax+8]
0x18000bdde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde3  test    eax, eax
0x18000bde5  jz      short loc_18000BDF0
0x18000bde7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bdee  jmp     short loc_18000BDFE
0x18000bdf0  lea     rcx, qword_1800DBF70; this
0x18000bdf7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000bdfe  cmp     byte ptr [rcx+8], 0
0x18000be02  jz      short loc_18000BE29
0x18000be04  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000be09  cmp     [rax+7CCh], edi
0x18000be0f  jz      short loc_18000BE29
0x18000be11  mov     r8d, 6Dh ; 'm'; int
0x18000be17  mov     r9d, edi; int
0x18000be1a  lea     rdx, aMkvmfsourcelib_152; "MkvMfSourceLib::MkvMfByteStreamHandler:"...
0x18000be21  mov     rcx, rax; this
0x18000be24  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000be29  mov     [rsp+38h+arg_0], 0
0x18000be32  test    r14, r14
0x18000be35  jz      short loc_18000BE67
0x18000be37  mov     rax, [r14]
0x18000be3a  mov     rbx, [rax+30h]
0x18000be3e  lea     rcx, [rsp+38h+arg_0]
0x18000be43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000be48  lea     rdx, [rsp+38h+arg_0]
0x18000be4d  mov     rcx, r14
0x18000be50  mov     rax, rbx
0x18000be53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be58  test    eax, eax
0x18000be5a  js      short loc_18000BE67
0x18000be5c  mov     rcx, [rsp+38h+arg_0]; this
0x18000be61  call    ?Close@MkvMfSource@MkvMfSourceLib@@QEAAXXZ; MkvMfSourceLib::MkvMfSource::Close(void)
0x18000be66  nop
0x18000be67  lea     rcx, [rsp+38h+arg_0]
0x18000be6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000be71  jmp     short loc_18000BE79
0x18000be73  mov     dword ptr [rbx], 0
0x18000be79  mov     rcx, rbp; lpCriticalSection
0x18000be7c  call    cs:__imp_LeaveCriticalSection
0x18000be83  nop     dword ptr [rax+rax+00h]
0x18000be88  mov     eax, edi
0x18000be8a  mov     rbx, [rsp+38h+arg_10]
0x18000be8f  mov     rbp, [rsp+38h+arg_18]
0x18000be94  add     rsp, 20h
0x18000be98  pop     r14
0x18000be9a  pop     rdi
0x18000be9b  pop     rsi
0x18000be9c  retn
```
