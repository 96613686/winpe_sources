# CMFAVIThumbnailStreamProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x1800e28c0`
- end: `0x1800e2caf`
- name: `?SetNativeValue@CMFAVIThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1007`
- prototype: `int(CMFAVIThumbnailStreamProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x180036c30`
- `0x1800e28c0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2924`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e29b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2a4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2aea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2b82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2c1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2924`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e29b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2a4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2aea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2b82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2c1d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800e2998`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800e2998`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800e2a2f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800e2a2f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e28ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e2906`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e28ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e2906`

## pseudocode

```c
__int64 __fastcall CMFAVIThumbnailStreamProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
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
            "CMFAVIThumbnailStreamProperty::SetNativeValue",
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
0x1800e28c0  mov     rax, rsp
0x1800e28c3  mov     [rax+18h], rbx
0x1800e28c7  mov     [rax+20h], rbp
0x1800e28cb  push    rsi
0x1800e28cc  push    rdi
0x1800e28cd  push    r14
0x1800e28cf  sub     rsp, 30h
0x1800e28d3  mov     rdi, rcx
0x1800e28d6  mov     qword ptr [rax+10h], 0
0x1800e28de  add     rcx, 60h ; '`'; pvar
0x1800e28e2  mov     dword ptr [rax+8], 0
0x1800e28e9  mov     rsi, rdx
0x1800e28ec  call    cs:__imp_PropVariantClear
0x1800e28f3  nop     dword ptr [rax+rax+00h]
0x1800e28f8  cmp     word ptr [rsi], 41h ; 'A'
0x1800e28fc  jnz     loc_1800E2C0C
0x1800e2902  lea     rcx, [rdi+78h]; pvar
0x1800e2906  call    cs:__imp_PropVariantClear
0x1800e290d  nop     dword ptr [rax+rax+00h]
0x1800e2912  mov     ebx, eax
0x1800e2914  test    eax, eax
0x1800e2916  jns     short loc_1800E2991
0x1800e2918  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e291f  test    rcx, rcx
0x1800e2922  jnz     short loc_1800E296B
0x1800e2924  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e292b  nop     dword ptr [rax+rax+00h]
0x1800e2930  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2937  mov     rcx, rax
0x1800e293a  test    rax, rax
0x1800e293d  jz      short loc_1800E295D
0x1800e293f  mov     rax, [rax]
0x1800e2942  mov     edx, 7F0h
0x1800e2947  mov     rax, [rax+8]
0x1800e294b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2950  test    eax, eax
0x1800e2952  jz      short loc_1800E295D
0x1800e2954  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e295b  jmp     short loc_1800E296B
0x1800e295d  lea     rcx, qword_1801B97E0; this
0x1800e2964  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e296b  cmp     byte ptr [rcx+8], 0
0x1800e296f  jz      loc_1800E2C8F
0x1800e2975  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e297a  cmp     [rax+7CCh], ebx
0x1800e2980  jz      loc_1800E2C8F
0x1800e2986  mov     r8d, 33h ; '3'
0x1800e298c  jmp     loc_1800E2C7D
0x1800e2991  mov     rdx, rsi; pvarSrc
0x1800e2994  lea     rcx, [rdi+78h]; pvarDest
0x1800e2998  call    cs:__imp_PropVariantCopy
0x1800e299f  nop     dword ptr [rax+rax+00h]
0x1800e29a4  mov     ebx, eax
0x1800e29a6  test    eax, eax
0x1800e29a8  jns     short loc_1800E2A23
0x1800e29aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e29b1  test    rcx, rcx
0x1800e29b4  jnz     short loc_1800E29FD
0x1800e29b6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e29bd  nop     dword ptr [rax+rax+00h]
0x1800e29c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e29c9  mov     rcx, rax
0x1800e29cc  test    rax, rax
0x1800e29cf  jz      short loc_1800E29EF
0x1800e29d1  mov     rax, [rax]
0x1800e29d4  mov     edx, 7F0h
0x1800e29d9  mov     rax, [rax+8]
0x1800e29dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e29e2  test    eax, eax
0x1800e29e4  jz      short loc_1800E29EF
0x1800e29e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e29ed  jmp     short loc_1800E29FD
0x1800e29ef  lea     rcx, qword_1801B97E0; this
0x1800e29f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e29fd  cmp     byte ptr [rcx+8], 0
0x1800e2a01  jz      loc_1800E2C8F
0x1800e2a07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2a0c  cmp     [rax+7CCh], ebx
0x1800e2a12  jz      loc_1800E2C8F
0x1800e2a18  mov     r8d, 35h ; '5'
0x1800e2a1e  jmp     loc_1800E2C7D
0x1800e2a23  lea     r8, [rsp+48h+ppstm]; ppstm
0x1800e2a28  mov     edx, 1; fDeleteOnRelease
0x1800e2a2d  xor     ecx, ecx; hGlobal
0x1800e2a2f  call    cs:__imp_CreateStreamOnHGlobal
0x1800e2a36  nop     dword ptr [rax+rax+00h]
0x1800e2a3b  mov     ebx, eax
0x1800e2a3d  test    eax, eax
0x1800e2a3f  jns     short loc_1800E2ABA
0x1800e2a41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2a48  test    rcx, rcx
0x1800e2a4b  jnz     short loc_1800E2A94
0x1800e2a4d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2a54  nop     dword ptr [rax+rax+00h]
0x1800e2a59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2a60  mov     rcx, rax
0x1800e2a63  test    rax, rax
0x1800e2a66  jz      short loc_1800E2A86
0x1800e2a68  mov     rax, [rax]
0x1800e2a6b  mov     edx, 7F0h
0x1800e2a70  mov     rax, [rax+8]
0x1800e2a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2a79  test    eax, eax
0x1800e2a7b  jz      short loc_1800E2A86
0x1800e2a7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2a84  jmp     short loc_1800E2A94
0x1800e2a86  lea     rcx, qword_1801B97E0; this
0x1800e2a8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2a94  cmp     byte ptr [rcx+8], 0
0x1800e2a98  jz      loc_1800E2C8F
0x1800e2a9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2aa3  cmp     [rax+7CCh], ebx
0x1800e2aa9  jz      loc_1800E2C8F
0x1800e2aaf  mov     r8d, 40h ; '@'
0x1800e2ab5  jmp     loc_1800E2C7D
0x1800e2aba  mov     rcx, [rsp+48h+ppstm]
0x1800e2abf  lea     r9, [rsp+48h+arg_0]
0x1800e2ac4  mov     r8d, [rsi+8]
0x1800e2ac8  mov     rdx, [rsi+10h]
0x1800e2acc  mov     rax, [rcx]
0x1800e2acf  mov     rax, [rax+20h]
0x1800e2ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2ad8  mov     ebx, eax
0x1800e2ada  test    eax, eax
0x1800e2adc  jns     short loc_1800E2B57
0x1800e2ade  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2ae5  test    rcx, rcx
0x1800e2ae8  jnz     short loc_1800E2B31
0x1800e2aea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2af1  nop     dword ptr [rax+rax+00h]
0x1800e2af6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2afd  mov     rcx, rax
0x1800e2b00  test    rax, rax
0x1800e2b03  jz      short loc_1800E2B23
0x1800e2b05  mov     rax, [rax]
0x1800e2b08  mov     edx, 7F0h
0x1800e2b0d  mov     rax, [rax+8]
0x1800e2b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2b16  test    eax, eax
0x1800e2b18  jz      short loc_1800E2B23
0x1800e2b1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2b21  jmp     short loc_1800E2B31
0x1800e2b23  lea     rcx, qword_1801B97E0; this
0x1800e2b2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2b31  cmp     byte ptr [rcx+8], 0
0x1800e2b35  jz      loc_1800E2C8F
0x1800e2b3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2b40  cmp     [rax+7CCh], ebx
0x1800e2b46  jz      loc_1800E2C8F
0x1800e2b4c  mov     r8d, 44h ; 'D'
0x1800e2b52  jmp     loc_1800E2C7D
0x1800e2b57  mov     rcx, [rsp+48h+ppstm]
0x1800e2b5c  xor     edx, edx
0x1800e2b5e  xor     r9d, r9d
0x1800e2b61  xor     r8d, r8d
0x1800e2b64  mov     rax, [rcx]
0x1800e2b67  mov     rax, [rax+28h]
0x1800e2b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2b70  mov     ebx, eax
0x1800e2b72  test    eax, eax
0x1800e2b74  jns     short loc_1800E2BEF
0x1800e2b76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2b7d  test    rcx, rcx
0x1800e2b80  jnz     short loc_1800E2BC9
0x1800e2b82  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2b89  nop     dword ptr [rax+rax+00h]
0x1800e2b8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2b95  mov     rcx, rax
0x1800e2b98  test    rax, rax
0x1800e2b9b  jz      short loc_1800E2BBB
0x1800e2b9d  mov     rax, [rax]
0x1800e2ba0  mov     edx, 7F0h
0x1800e2ba5  mov     rax, [rax+8]
0x1800e2ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2bae  test    eax, eax
0x1800e2bb0  jz      short loc_1800E2BBB
0x1800e2bb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2bb9  jmp     short loc_1800E2BC9
0x1800e2bbb  lea     rcx, qword_1801B97E0; this
0x1800e2bc2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2bc9  cmp     byte ptr [rcx+8], 0
0x1800e2bcd  jz      loc_1800E2C8F
0x1800e2bd3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2bd8  cmp     [rax+7CCh], ebx
0x1800e2bde  jz      loc_1800E2C8F
0x1800e2be4  mov     r8d, 46h ; 'F'
0x1800e2bea  jmp     loc_1800E2C7D
0x1800e2bef  mov     rax, [rsp+48h+ppstm]
0x1800e2bf4  mov     [rdi+68h], rax
0x1800e2bf8  mov     word ptr [rdi+60h], 42h ; 'B'
0x1800e2bfe  mov     [rsp+48h+ppstm], 0
0x1800e2c07  jmp     loc_1800E2C8F
0x1800e2c0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2c13  mov     ebx, 8000FFFFh
0x1800e2c18  test    rcx, rcx
0x1800e2c1b  jnz     short loc_1800E2C64
0x1800e2c1d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2c24  nop     dword ptr [rax+rax+00h]
0x1800e2c29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2c30  mov     rcx, rax
0x1800e2c33  test    rax, rax
0x1800e2c36  jz      short loc_1800E2C56
0x1800e2c38  mov     rax, [rax]
0x1800e2c3b  mov     edx, 7F0h
0x1800e2c40  mov     rax, [rax+8]
0x1800e2c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2c49  test    eax, eax
0x1800e2c4b  jz      short loc_1800E2C56
0x1800e2c4d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2c54  jmp     short loc_1800E2C64
0x1800e2c56  lea     rcx, qword_1801B97E0; this
0x1800e2c5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2c64  cmp     byte ptr [rcx+8], 0
0x1800e2c68  jz      short loc_1800E2C8F
0x1800e2c6a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2c6f  cmp     [rax+7CCh], ebx
0x1800e2c75  jz      short loc_1800E2C8F
0x1800e2c77  mov     r8d, 51h ; 'Q'; int
0x1800e2c7d  mov     r9d, ebx; int
0x1800e2c80  lea     rdx, aCmfavithumbnai_0; "CMFAVIThumbnailStreamProperty::SetNativ"...
0x1800e2c87  mov     rcx, rax; this
0x1800e2c8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2c8f  lea     rcx, [rsp+48h+ppstm]; void *
0x1800e2c94  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800e2c99  mov     rbp, [rsp+48h+arg_18]
0x1800e2c9e  mov     eax, ebx
0x1800e2ca0  mov     rbx, [rsp+48h+arg_10]
0x1800e2ca5  add     rsp, 30h
0x1800e2ca9  pop     r14
0x1800e2cab  pop     rdi
0x1800e2cac  pop     rsi
0x1800e2cad  retn
```
