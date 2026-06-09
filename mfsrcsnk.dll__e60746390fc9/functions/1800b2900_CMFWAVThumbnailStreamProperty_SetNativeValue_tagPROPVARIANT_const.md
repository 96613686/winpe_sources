# CMFWAVThumbnailStreamProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x1800b2900`
- end: `0x1800b2caf`
- name: `?SetNativeValue@CMFWAVThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `943`
- prototype: `int(CMFWAVThumbnailStreamProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180010190`
- `0x18001303c`
- `0x180034d10`
- `0x1800b2900`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2958`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b29de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2a69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2b00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2b92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2c24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2958`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b29de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2a69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2b00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2b92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2c24`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800b29c6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800b29c6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b2a51`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b2a51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b292c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b2940`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b292c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b2940`

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
                  v21 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                v18 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v15 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v12 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v7 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v23 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800b2900  mov     rax, rsp
0x1800b2903  mov     [rax+18h], rbx
0x1800b2907  mov     [rax+20h], rbp
0x1800b290b  push    rsi
0x1800b290c  push    rdi
0x1800b290d  push    r14
0x1800b290f  sub     rsp, 30h
0x1800b2913  mov     rdi, rcx
0x1800b2916  mov     qword ptr [rax+10h], 0
0x1800b291e  add     rcx, 60h ; '`'; pvar
0x1800b2922  mov     dword ptr [rax+8], 0
0x1800b2929  mov     rsi, rdx
0x1800b292c  call    cs:__imp_PropVariantClear
0x1800b2932  cmp     word ptr [rsi], 41h ; 'A'
0x1800b2936  jnz     loc_1800B2C13
0x1800b293c  lea     rcx, [rdi+78h]; pvar
0x1800b2940  call    cs:__imp_PropVariantClear
0x1800b2946  mov     ebx, eax
0x1800b2948  test    eax, eax
0x1800b294a  jns     short loc_1800B29BF
0x1800b294c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2953  test    rcx, rcx
0x1800b2956  jnz     short loc_1800B2999
0x1800b2958  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b295e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2965  mov     rcx, rax
0x1800b2968  test    rax, rax
0x1800b296b  jz      short loc_1800B298B
0x1800b296d  mov     rax, [rax]
0x1800b2970  mov     edx, 7F0h
0x1800b2975  mov     rax, [rax+8]
0x1800b2979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b297e  test    eax, eax
0x1800b2980  jz      short loc_1800B298B
0x1800b2982  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2989  jmp     short loc_1800B2999
0x1800b298b  lea     rcx, qword_1801B07E0; this
0x1800b2992  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2999  cmp     byte ptr [rcx+8], 0
0x1800b299d  jz      loc_1800B2C90
0x1800b29a3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b29a8  cmp     [rax+7CCh], ebx
0x1800b29ae  jz      loc_1800B2C90
0x1800b29b4  mov     r8d, 33h ; '3'
0x1800b29ba  jmp     loc_1800B2C7E
0x1800b29bf  mov     rdx, rsi; pvarSrc
0x1800b29c2  lea     rcx, [rdi+78h]; pvarDest
0x1800b29c6  call    cs:__imp_PropVariantCopy
0x1800b29cc  mov     ebx, eax
0x1800b29ce  test    eax, eax
0x1800b29d0  jns     short loc_1800B2A45
0x1800b29d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b29d9  test    rcx, rcx
0x1800b29dc  jnz     short loc_1800B2A1F
0x1800b29de  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b29e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b29eb  mov     rcx, rax
0x1800b29ee  test    rax, rax
0x1800b29f1  jz      short loc_1800B2A11
0x1800b29f3  mov     rax, [rax]
0x1800b29f6  mov     edx, 7F0h
0x1800b29fb  mov     rax, [rax+8]
0x1800b29ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2a04  test    eax, eax
0x1800b2a06  jz      short loc_1800B2A11
0x1800b2a08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2a0f  jmp     short loc_1800B2A1F
0x1800b2a11  lea     rcx, qword_1801B07E0; this
0x1800b2a18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2a1f  cmp     byte ptr [rcx+8], 0
0x1800b2a23  jz      loc_1800B2C90
0x1800b2a29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b2a2e  cmp     [rax+7CCh], ebx
0x1800b2a34  jz      loc_1800B2C90
0x1800b2a3a  mov     r8d, 35h ; '5'
0x1800b2a40  jmp     loc_1800B2C7E
0x1800b2a45  lea     r8, [rsp+48h+ppstm]; ppstm
0x1800b2a4a  mov     edx, 1; fDeleteOnRelease
0x1800b2a4f  xor     ecx, ecx; hGlobal
0x1800b2a51  call    cs:__imp_CreateStreamOnHGlobal
0x1800b2a57  mov     ebx, eax
0x1800b2a59  test    eax, eax
0x1800b2a5b  jns     short loc_1800B2AD0
0x1800b2a5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2a64  test    rcx, rcx
0x1800b2a67  jnz     short loc_1800B2AAA
0x1800b2a69  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b2a6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2a76  mov     rcx, rax
0x1800b2a79  test    rax, rax
0x1800b2a7c  jz      short loc_1800B2A9C
0x1800b2a7e  mov     rax, [rax]
0x1800b2a81  mov     edx, 7F0h
0x1800b2a86  mov     rax, [rax+8]
0x1800b2a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2a8f  test    eax, eax
0x1800b2a91  jz      short loc_1800B2A9C
0x1800b2a93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2a9a  jmp     short loc_1800B2AAA
0x1800b2a9c  lea     rcx, qword_1801B07E0; this
0x1800b2aa3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2aaa  cmp     byte ptr [rcx+8], 0
0x1800b2aae  jz      loc_1800B2C90
0x1800b2ab4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b2ab9  cmp     [rax+7CCh], ebx
0x1800b2abf  jz      loc_1800B2C90
0x1800b2ac5  mov     r8d, 40h ; '@'
0x1800b2acb  jmp     loc_1800B2C7E
0x1800b2ad0  mov     rcx, [rsp+48h+ppstm]
0x1800b2ad5  lea     r9, [rsp+48h+arg_0]
0x1800b2ada  mov     r8d, [rsi+8]
0x1800b2ade  mov     rdx, [rsi+10h]
0x1800b2ae2  mov     rax, [rcx]
0x1800b2ae5  mov     rax, [rax+20h]
0x1800b2ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2aee  mov     ebx, eax
0x1800b2af0  test    eax, eax
0x1800b2af2  jns     short loc_1800B2B67
0x1800b2af4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2afb  test    rcx, rcx
0x1800b2afe  jnz     short loc_1800B2B41
0x1800b2b00  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b2b06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2b0d  mov     rcx, rax
0x1800b2b10  test    rax, rax
0x1800b2b13  jz      short loc_1800B2B33
0x1800b2b15  mov     rax, [rax]
0x1800b2b18  mov     edx, 7F0h
0x1800b2b1d  mov     rax, [rax+8]
0x1800b2b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b26  test    eax, eax
0x1800b2b28  jz      short loc_1800B2B33
0x1800b2b2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2b31  jmp     short loc_1800B2B41
0x1800b2b33  lea     rcx, qword_1801B07E0; this
0x1800b2b3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2b41  cmp     byte ptr [rcx+8], 0
0x1800b2b45  jz      loc_1800B2C90
0x1800b2b4b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b2b50  cmp     [rax+7CCh], ebx
0x1800b2b56  jz      loc_1800B2C90
0x1800b2b5c  mov     r8d, 44h ; 'D'
0x1800b2b62  jmp     loc_1800B2C7E
0x1800b2b67  mov     rcx, [rsp+48h+ppstm]
0x1800b2b6c  xor     edx, edx
0x1800b2b6e  xor     r9d, r9d
0x1800b2b71  xor     r8d, r8d
0x1800b2b74  mov     rax, [rcx]
0x1800b2b77  mov     rax, [rax+28h]
0x1800b2b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b80  mov     ebx, eax
0x1800b2b82  test    eax, eax
0x1800b2b84  jns     short loc_1800B2BF9
0x1800b2b86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2b8d  test    rcx, rcx
0x1800b2b90  jnz     short loc_1800B2BD3
0x1800b2b92  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b2b98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2b9f  mov     rcx, rax
0x1800b2ba2  test    rax, rax
0x1800b2ba5  jz      short loc_1800B2BC5
0x1800b2ba7  mov     rax, [rax]
0x1800b2baa  mov     edx, 7F0h
0x1800b2baf  mov     rax, [rax+8]
0x1800b2bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2bb8  test    eax, eax
0x1800b2bba  jz      short loc_1800B2BC5
0x1800b2bbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2bc3  jmp     short loc_1800B2BD3
0x1800b2bc5  lea     rcx, qword_1801B07E0; this
0x1800b2bcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2bd3  cmp     byte ptr [rcx+8], 0
0x1800b2bd7  jz      loc_1800B2C90
0x1800b2bdd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b2be2  cmp     [rax+7CCh], ebx
0x1800b2be8  jz      loc_1800B2C90
0x1800b2bee  mov     r8d, 46h ; 'F'
0x1800b2bf4  jmp     loc_1800B2C7E
0x1800b2bf9  mov     rax, [rsp+48h+ppstm]
0x1800b2bfe  mov     [rdi+68h], rax
0x1800b2c02  mov     word ptr [rdi+60h], 42h ; 'B'
0x1800b2c08  mov     [rsp+48h+ppstm], 0
0x1800b2c11  jmp     short loc_1800B2C90
0x1800b2c13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2c1a  mov     ebx, 8000FFFFh
0x1800b2c1f  test    rcx, rcx
0x1800b2c22  jnz     short loc_1800B2C65
0x1800b2c24  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b2c2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2c31  mov     rcx, rax
0x1800b2c34  test    rax, rax
0x1800b2c37  jz      short loc_1800B2C57
0x1800b2c39  mov     rax, [rax]
0x1800b2c3c  mov     edx, 7F0h
0x1800b2c41  mov     rax, [rax+8]
0x1800b2c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2c4a  test    eax, eax
0x1800b2c4c  jz      short loc_1800B2C57
0x1800b2c4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2c55  jmp     short loc_1800B2C65
0x1800b2c57  lea     rcx, qword_1801B07E0; this
0x1800b2c5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2c65  cmp     byte ptr [rcx+8], 0
0x1800b2c69  jz      short loc_1800B2C90
0x1800b2c6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b2c70  cmp     [rax+7CCh], ebx
0x1800b2c76  jz      short loc_1800B2C90
0x1800b2c78  mov     r8d, 51h ; 'Q'; int
0x1800b2c7e  mov     r9d, ebx; int
0x1800b2c81  lea     rdx, aCmfwavthumbnai; "CMFWAVThumbnailStreamProperty::SetNativ"...
0x1800b2c88  mov     rcx, rax; this
0x1800b2c8b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b2c90  lea     rcx, [rsp+48h+ppstm]; void *
0x1800b2c95  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800b2c9a  mov     rbp, [rsp+48h+arg_18]
0x1800b2c9f  mov     eax, ebx
0x1800b2ca1  mov     rbx, [rsp+48h+arg_10]
0x1800b2ca6  add     rsp, 30h
0x1800b2caa  pop     r14
0x1800b2cac  pop     rdi
0x1800b2cad  pop     rsi
0x1800b2cae  retn
```
