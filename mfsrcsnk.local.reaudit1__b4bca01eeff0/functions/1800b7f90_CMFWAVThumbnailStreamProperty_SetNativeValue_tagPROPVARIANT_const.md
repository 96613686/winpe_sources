# CMFWAVThumbnailStreamProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x1800b7f90`
- end: `0x1800b837f`
- name: `?SetNativeValue@CMFWAVThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1007`
- prototype: `int(CMFWAVThumbnailStreamProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x180036c30`
- `0x1800b7f90`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7ff4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b8086`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b811d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b81ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b8252`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b82ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7ff4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b8086`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b811d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b81ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b8252`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b82ed`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800b8068`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800b8068`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b80ff`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b80ff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b7fbc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b7fd6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b7fbc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b7fd6`

## pseudocode

```c
__int64 __fastcall CMFWAVThumbnailStreamProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rdx
  HRESULT v6; // ebx
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v10; // r8d
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  int v26; // [rsp+50h] [rbp+8h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp+10h] BYREF

  ppstm = 0;
  v26 = 0;
  PropVariantClear(this + 4);
  if ( a2->vt == 65 )
  {
    v6 = PropVariantClear(this + 5);
    if ( v6 >= 0 )
    {
      v6 = PropVariantCopy(this + 5, a2);
      if ( v6 >= 0 )
      {
        v6 = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( v6 >= 0 )
        {
          v6 = ((__int64 (__fastcall *)(LPSTREAM, BYTE *, _QWORD, int *))ppstm->lpVtbl->Write)(
                 ppstm,
                 a2->bstrblobVal.pData,
                 a2->ulVal,
                 &v26);
          if ( v6 >= 0 )
          {
            v6 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
            if ( v6 >= 0 )
            {
              this[4].hVal.QuadPart = (LONGLONG)ppstm;
              this[4].vt = 66;
              ppstm = 0;
            }
            else
            {
              v21 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
                CallStackTracing::s_wpInstance = v22;
                if ( v22
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
                {
                  v21 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v21 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v21 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
                {
                  v10 = 70;
                  goto LABEL_56;
                }
              }
            }
          }
          else
          {
            v18 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
              CallStackTracing::s_wpInstance = v19;
              if ( v19
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
              {
                v18 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v18 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v18 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
              {
                v10 = 68;
                goto LABEL_56;
              }
            }
          }
        }
        else
        {
          v15 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
            CallStackTracing::s_wpInstance = v16;
            if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
            {
              v15 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v15 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v15 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
            {
              v10 = 64;
              goto LABEL_56;
            }
          }
        }
      }
      else
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v12 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          {
            v10 = 53;
            goto LABEL_56;
          }
        }
      }
    }
    else
    {
      v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        {
          v10 = 51;
LABEL_56:
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFWAVThumbnailStreamProperty::SetNativeValue",
            v10,
            v6);
        }
      }
    }
  }
  else
  {
    v23 = (wchar_t *)CallStackTracing::s_wpInstance;
    v6 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
      {
        v10 = 81;
        goto LABEL_56;
      }
    }
  }
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppstm);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b7f90  mov     rax, rsp
0x1800b7f93  mov     [rax+18h], rbx
0x1800b7f97  mov     [rax+20h], rbp
0x1800b7f9b  push    rsi
0x1800b7f9c  push    rdi
0x1800b7f9d  push    r14
0x1800b7f9f  sub     rsp, 30h
0x1800b7fa3  mov     rdi, rcx
0x1800b7fa6  mov     qword ptr [rax+10h], 0
0x1800b7fae  add     rcx, 60h ; '`'; pvar
0x1800b7fb2  mov     dword ptr [rax+8], 0
0x1800b7fb9  mov     rsi, rdx
0x1800b7fbc  call    cs:__imp_PropVariantClear
0x1800b7fc3  nop     dword ptr [rax+rax+00h]
0x1800b7fc8  cmp     word ptr [rsi], 41h ; 'A'
0x1800b7fcc  jnz     loc_1800B82DC
0x1800b7fd2  lea     rcx, [rdi+78h]; pvar
0x1800b7fd6  call    cs:__imp_PropVariantClear
0x1800b7fdd  nop     dword ptr [rax+rax+00h]
0x1800b7fe2  mov     ebx, eax
0x1800b7fe4  test    eax, eax
0x1800b7fe6  jns     short loc_1800B8061
0x1800b7fe8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7fef  test    rcx, rcx
0x1800b7ff2  jnz     short loc_1800B803B
0x1800b7ff4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7ffb  nop     dword ptr [rax+rax+00h]
0x1800b8000  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8007  mov     rcx, rax
0x1800b800a  test    rax, rax
0x1800b800d  jz      short loc_1800B802D
0x1800b800f  mov     rax, [rax]
0x1800b8012  mov     edx, 7F0h
0x1800b8017  mov     rax, [rax+8]
0x1800b801b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8020  test    eax, eax
0x1800b8022  jz      short loc_1800B802D
0x1800b8024  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b802b  jmp     short loc_1800B803B
0x1800b802d  lea     rcx, qword_1801B97E0; this
0x1800b8034  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b803b  cmp     byte ptr [rcx+8], 0
0x1800b803f  jz      loc_1800B835F
0x1800b8045  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b804a  cmp     [rax+7CCh], ebx
0x1800b8050  jz      loc_1800B835F
0x1800b8056  mov     r8d, 33h ; '3'
0x1800b805c  jmp     loc_1800B834D
0x1800b8061  mov     rdx, rsi; pvarSrc
0x1800b8064  lea     rcx, [rdi+78h]; pvarDest
0x1800b8068  call    cs:__imp_PropVariantCopy
0x1800b806f  nop     dword ptr [rax+rax+00h]
0x1800b8074  mov     ebx, eax
0x1800b8076  test    eax, eax
0x1800b8078  jns     short loc_1800B80F3
0x1800b807a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8081  test    rcx, rcx
0x1800b8084  jnz     short loc_1800B80CD
0x1800b8086  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b808d  nop     dword ptr [rax+rax+00h]
0x1800b8092  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8099  mov     rcx, rax
0x1800b809c  test    rax, rax
0x1800b809f  jz      short loc_1800B80BF
0x1800b80a1  mov     rax, [rax]
0x1800b80a4  mov     edx, 7F0h
0x1800b80a9  mov     rax, [rax+8]
0x1800b80ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b80b2  test    eax, eax
0x1800b80b4  jz      short loc_1800B80BF
0x1800b80b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b80bd  jmp     short loc_1800B80CD
0x1800b80bf  lea     rcx, qword_1801B97E0; this
0x1800b80c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b80cd  cmp     byte ptr [rcx+8], 0
0x1800b80d1  jz      loc_1800B835F
0x1800b80d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b80dc  cmp     [rax+7CCh], ebx
0x1800b80e2  jz      loc_1800B835F
0x1800b80e8  mov     r8d, 35h ; '5'
0x1800b80ee  jmp     loc_1800B834D
0x1800b80f3  lea     r8, [rsp+48h+ppstm]; ppstm
0x1800b80f8  mov     edx, 1; fDeleteOnRelease
0x1800b80fd  xor     ecx, ecx; hGlobal
0x1800b80ff  call    cs:__imp_CreateStreamOnHGlobal
0x1800b8106  nop     dword ptr [rax+rax+00h]
0x1800b810b  mov     ebx, eax
0x1800b810d  test    eax, eax
0x1800b810f  jns     short loc_1800B818A
0x1800b8111  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8118  test    rcx, rcx
0x1800b811b  jnz     short loc_1800B8164
0x1800b811d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b8124  nop     dword ptr [rax+rax+00h]
0x1800b8129  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8130  mov     rcx, rax
0x1800b8133  test    rax, rax
0x1800b8136  jz      short loc_1800B8156
0x1800b8138  mov     rax, [rax]
0x1800b813b  mov     edx, 7F0h
0x1800b8140  mov     rax, [rax+8]
0x1800b8144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8149  test    eax, eax
0x1800b814b  jz      short loc_1800B8156
0x1800b814d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8154  jmp     short loc_1800B8164
0x1800b8156  lea     rcx, qword_1801B97E0; this
0x1800b815d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8164  cmp     byte ptr [rcx+8], 0
0x1800b8168  jz      loc_1800B835F
0x1800b816e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b8173  cmp     [rax+7CCh], ebx
0x1800b8179  jz      loc_1800B835F
0x1800b817f  mov     r8d, 40h ; '@'
0x1800b8185  jmp     loc_1800B834D
0x1800b818a  mov     rcx, [rsp+48h+ppstm]
0x1800b818f  lea     r9, [rsp+48h+arg_0]
0x1800b8194  mov     r8d, [rsi+8]
0x1800b8198  mov     rdx, [rsi+10h]
0x1800b819c  mov     rax, [rcx]
0x1800b819f  mov     rax, [rax+20h]
0x1800b81a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b81a8  mov     ebx, eax
0x1800b81aa  test    eax, eax
0x1800b81ac  jns     short loc_1800B8227
0x1800b81ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b81b5  test    rcx, rcx
0x1800b81b8  jnz     short loc_1800B8201
0x1800b81ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b81c1  nop     dword ptr [rax+rax+00h]
0x1800b81c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b81cd  mov     rcx, rax
0x1800b81d0  test    rax, rax
0x1800b81d3  jz      short loc_1800B81F3
0x1800b81d5  mov     rax, [rax]
0x1800b81d8  mov     edx, 7F0h
0x1800b81dd  mov     rax, [rax+8]
0x1800b81e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b81e6  test    eax, eax
0x1800b81e8  jz      short loc_1800B81F3
0x1800b81ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b81f1  jmp     short loc_1800B8201
0x1800b81f3  lea     rcx, qword_1801B97E0; this
0x1800b81fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8201  cmp     byte ptr [rcx+8], 0
0x1800b8205  jz      loc_1800B835F
0x1800b820b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b8210  cmp     [rax+7CCh], ebx
0x1800b8216  jz      loc_1800B835F
0x1800b821c  mov     r8d, 44h ; 'D'
0x1800b8222  jmp     loc_1800B834D
0x1800b8227  mov     rcx, [rsp+48h+ppstm]
0x1800b822c  xor     edx, edx
0x1800b822e  xor     r9d, r9d
0x1800b8231  xor     r8d, r8d
0x1800b8234  mov     rax, [rcx]
0x1800b8237  mov     rax, [rax+28h]
0x1800b823b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8240  mov     ebx, eax
0x1800b8242  test    eax, eax
0x1800b8244  jns     short loc_1800B82BF
0x1800b8246  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b824d  test    rcx, rcx
0x1800b8250  jnz     short loc_1800B8299
0x1800b8252  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b8259  nop     dword ptr [rax+rax+00h]
0x1800b825e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8265  mov     rcx, rax
0x1800b8268  test    rax, rax
0x1800b826b  jz      short loc_1800B828B
0x1800b826d  mov     rax, [rax]
0x1800b8270  mov     edx, 7F0h
0x1800b8275  mov     rax, [rax+8]
0x1800b8279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b827e  test    eax, eax
0x1800b8280  jz      short loc_1800B828B
0x1800b8282  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8289  jmp     short loc_1800B8299
0x1800b828b  lea     rcx, qword_1801B97E0; this
0x1800b8292  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8299  cmp     byte ptr [rcx+8], 0
0x1800b829d  jz      loc_1800B835F
0x1800b82a3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b82a8  cmp     [rax+7CCh], ebx
0x1800b82ae  jz      loc_1800B835F
0x1800b82b4  mov     r8d, 46h ; 'F'
0x1800b82ba  jmp     loc_1800B834D
0x1800b82bf  mov     rax, [rsp+48h+ppstm]
0x1800b82c4  mov     [rdi+68h], rax
0x1800b82c8  mov     word ptr [rdi+60h], 42h ; 'B'
0x1800b82ce  mov     [rsp+48h+ppstm], 0
0x1800b82d7  jmp     loc_1800B835F
0x1800b82dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b82e3  mov     ebx, 8000FFFFh
0x1800b82e8  test    rcx, rcx
0x1800b82eb  jnz     short loc_1800B8334
0x1800b82ed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b82f4  nop     dword ptr [rax+rax+00h]
0x1800b82f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8300  mov     rcx, rax
0x1800b8303  test    rax, rax
0x1800b8306  jz      short loc_1800B8326
0x1800b8308  mov     rax, [rax]
0x1800b830b  mov     edx, 7F0h
0x1800b8310  mov     rax, [rax+8]
0x1800b8314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8319  test    eax, eax
0x1800b831b  jz      short loc_1800B8326
0x1800b831d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8324  jmp     short loc_1800B8334
0x1800b8326  lea     rcx, qword_1801B97E0; this
0x1800b832d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8334  cmp     byte ptr [rcx+8], 0
0x1800b8338  jz      short loc_1800B835F
0x1800b833a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b833f  cmp     [rax+7CCh], ebx
0x1800b8345  jz      short loc_1800B835F
0x1800b8347  mov     r8d, 51h ; 'Q'; int
0x1800b834d  mov     r9d, ebx; int
0x1800b8350  lea     rdx, aCmfwavthumbnai; "CMFWAVThumbnailStreamProperty::SetNativ"...
0x1800b8357  mov     rcx, rax; this
0x1800b835a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b835f  lea     rcx, [rsp+48h+ppstm]; void *
0x1800b8364  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800b8369  mov     rbp, [rsp+48h+arg_18]
0x1800b836e  mov     eax, ebx
0x1800b8370  mov     rbx, [rsp+48h+arg_10]
0x1800b8375  add     rsp, 30h
0x1800b8379  pop     r14
0x1800b837b  pop     rdi
0x1800b837c  pop     rsi
0x1800b837d  retn
```
