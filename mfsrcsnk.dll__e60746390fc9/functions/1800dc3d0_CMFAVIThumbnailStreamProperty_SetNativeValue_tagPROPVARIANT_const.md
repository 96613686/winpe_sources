# CMFAVIThumbnailStreamProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x1800dc3d0`
- end: `0x1800dc77f`
- name: `?SetNativeValue@CMFAVIThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `943`
- prototype: `int(CMFAVIThumbnailStreamProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180010190`
- `0x18001303c`
- `0x180034d10`
- `0x1800dc3d0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc428`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc4ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc539`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc5d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc662`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc6f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc428`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc4ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc539`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc5d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc662`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc6f4`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800dc496`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800dc496`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800dc521`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800dc521`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800dc3fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800dc410`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800dc3fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800dc410`

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
0x1800dc3d0  mov     rax, rsp
0x1800dc3d3  mov     [rax+18h], rbx
0x1800dc3d7  mov     [rax+20h], rbp
0x1800dc3db  push    rsi
0x1800dc3dc  push    rdi
0x1800dc3dd  push    r14
0x1800dc3df  sub     rsp, 30h
0x1800dc3e3  mov     rdi, rcx
0x1800dc3e6  mov     qword ptr [rax+10h], 0
0x1800dc3ee  add     rcx, 60h ; '`'; pvar
0x1800dc3f2  mov     dword ptr [rax+8], 0
0x1800dc3f9  mov     rsi, rdx
0x1800dc3fc  call    cs:__imp_PropVariantClear
0x1800dc402  cmp     word ptr [rsi], 41h ; 'A'
0x1800dc406  jnz     loc_1800DC6E3
0x1800dc40c  lea     rcx, [rdi+78h]; pvar
0x1800dc410  call    cs:__imp_PropVariantClear
0x1800dc416  mov     ebx, eax
0x1800dc418  test    eax, eax
0x1800dc41a  jns     short loc_1800DC48F
0x1800dc41c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc423  test    rcx, rcx
0x1800dc426  jnz     short loc_1800DC469
0x1800dc428  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dc42e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc435  mov     rcx, rax
0x1800dc438  test    rax, rax
0x1800dc43b  jz      short loc_1800DC45B
0x1800dc43d  mov     rax, [rax]
0x1800dc440  mov     edx, 7F0h
0x1800dc445  mov     rax, [rax+8]
0x1800dc449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc44e  test    eax, eax
0x1800dc450  jz      short loc_1800DC45B
0x1800dc452  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc459  jmp     short loc_1800DC469
0x1800dc45b  lea     rcx, qword_1801B07E0; this
0x1800dc462  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc469  cmp     byte ptr [rcx+8], 0
0x1800dc46d  jz      loc_1800DC760
0x1800dc473  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dc478  cmp     [rax+7CCh], ebx
0x1800dc47e  jz      loc_1800DC760
0x1800dc484  mov     r8d, 33h ; '3'
0x1800dc48a  jmp     loc_1800DC74E
0x1800dc48f  mov     rdx, rsi; pvarSrc
0x1800dc492  lea     rcx, [rdi+78h]; pvarDest
0x1800dc496  call    cs:__imp_PropVariantCopy
0x1800dc49c  mov     ebx, eax
0x1800dc49e  test    eax, eax
0x1800dc4a0  jns     short loc_1800DC515
0x1800dc4a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc4a9  test    rcx, rcx
0x1800dc4ac  jnz     short loc_1800DC4EF
0x1800dc4ae  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dc4b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc4bb  mov     rcx, rax
0x1800dc4be  test    rax, rax
0x1800dc4c1  jz      short loc_1800DC4E1
0x1800dc4c3  mov     rax, [rax]
0x1800dc4c6  mov     edx, 7F0h
0x1800dc4cb  mov     rax, [rax+8]
0x1800dc4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc4d4  test    eax, eax
0x1800dc4d6  jz      short loc_1800DC4E1
0x1800dc4d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc4df  jmp     short loc_1800DC4EF
0x1800dc4e1  lea     rcx, qword_1801B07E0; this
0x1800dc4e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc4ef  cmp     byte ptr [rcx+8], 0
0x1800dc4f3  jz      loc_1800DC760
0x1800dc4f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dc4fe  cmp     [rax+7CCh], ebx
0x1800dc504  jz      loc_1800DC760
0x1800dc50a  mov     r8d, 35h ; '5'
0x1800dc510  jmp     loc_1800DC74E
0x1800dc515  lea     r8, [rsp+48h+ppstm]; ppstm
0x1800dc51a  mov     edx, 1; fDeleteOnRelease
0x1800dc51f  xor     ecx, ecx; hGlobal
0x1800dc521  call    cs:__imp_CreateStreamOnHGlobal
0x1800dc527  mov     ebx, eax
0x1800dc529  test    eax, eax
0x1800dc52b  jns     short loc_1800DC5A0
0x1800dc52d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc534  test    rcx, rcx
0x1800dc537  jnz     short loc_1800DC57A
0x1800dc539  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dc53f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc546  mov     rcx, rax
0x1800dc549  test    rax, rax
0x1800dc54c  jz      short loc_1800DC56C
0x1800dc54e  mov     rax, [rax]
0x1800dc551  mov     edx, 7F0h
0x1800dc556  mov     rax, [rax+8]
0x1800dc55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc55f  test    eax, eax
0x1800dc561  jz      short loc_1800DC56C
0x1800dc563  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc56a  jmp     short loc_1800DC57A
0x1800dc56c  lea     rcx, qword_1801B07E0; this
0x1800dc573  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc57a  cmp     byte ptr [rcx+8], 0
0x1800dc57e  jz      loc_1800DC760
0x1800dc584  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dc589  cmp     [rax+7CCh], ebx
0x1800dc58f  jz      loc_1800DC760
0x1800dc595  mov     r8d, 40h ; '@'
0x1800dc59b  jmp     loc_1800DC74E
0x1800dc5a0  mov     rcx, [rsp+48h+ppstm]
0x1800dc5a5  lea     r9, [rsp+48h+arg_0]
0x1800dc5aa  mov     r8d, [rsi+8]
0x1800dc5ae  mov     rdx, [rsi+10h]
0x1800dc5b2  mov     rax, [rcx]
0x1800dc5b5  mov     rax, [rax+20h]
0x1800dc5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc5be  mov     ebx, eax
0x1800dc5c0  test    eax, eax
0x1800dc5c2  jns     short loc_1800DC637
0x1800dc5c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc5cb  test    rcx, rcx
0x1800dc5ce  jnz     short loc_1800DC611
0x1800dc5d0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dc5d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc5dd  mov     rcx, rax
0x1800dc5e0  test    rax, rax
0x1800dc5e3  jz      short loc_1800DC603
0x1800dc5e5  mov     rax, [rax]
0x1800dc5e8  mov     edx, 7F0h
0x1800dc5ed  mov     rax, [rax+8]
0x1800dc5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc5f6  test    eax, eax
0x1800dc5f8  jz      short loc_1800DC603
0x1800dc5fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc601  jmp     short loc_1800DC611
0x1800dc603  lea     rcx, qword_1801B07E0; this
0x1800dc60a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc611  cmp     byte ptr [rcx+8], 0
0x1800dc615  jz      loc_1800DC760
0x1800dc61b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dc620  cmp     [rax+7CCh], ebx
0x1800dc626  jz      loc_1800DC760
0x1800dc62c  mov     r8d, 44h ; 'D'
0x1800dc632  jmp     loc_1800DC74E
0x1800dc637  mov     rcx, [rsp+48h+ppstm]
0x1800dc63c  xor     edx, edx
0x1800dc63e  xor     r9d, r9d
0x1800dc641  xor     r8d, r8d
0x1800dc644  mov     rax, [rcx]
0x1800dc647  mov     rax, [rax+28h]
0x1800dc64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc650  mov     ebx, eax
0x1800dc652  test    eax, eax
0x1800dc654  jns     short loc_1800DC6C9
0x1800dc656  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc65d  test    rcx, rcx
0x1800dc660  jnz     short loc_1800DC6A3
0x1800dc662  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dc668  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc66f  mov     rcx, rax
0x1800dc672  test    rax, rax
0x1800dc675  jz      short loc_1800DC695
0x1800dc677  mov     rax, [rax]
0x1800dc67a  mov     edx, 7F0h
0x1800dc67f  mov     rax, [rax+8]
0x1800dc683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc688  test    eax, eax
0x1800dc68a  jz      short loc_1800DC695
0x1800dc68c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc693  jmp     short loc_1800DC6A3
0x1800dc695  lea     rcx, qword_1801B07E0; this
0x1800dc69c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc6a3  cmp     byte ptr [rcx+8], 0
0x1800dc6a7  jz      loc_1800DC760
0x1800dc6ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dc6b2  cmp     [rax+7CCh], ebx
0x1800dc6b8  jz      loc_1800DC760
0x1800dc6be  mov     r8d, 46h ; 'F'
0x1800dc6c4  jmp     loc_1800DC74E
0x1800dc6c9  mov     rax, [rsp+48h+ppstm]
0x1800dc6ce  mov     [rdi+68h], rax
0x1800dc6d2  mov     word ptr [rdi+60h], 42h ; 'B'
0x1800dc6d8  mov     [rsp+48h+ppstm], 0
0x1800dc6e1  jmp     short loc_1800DC760
0x1800dc6e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc6ea  mov     ebx, 8000FFFFh
0x1800dc6ef  test    rcx, rcx
0x1800dc6f2  jnz     short loc_1800DC735
0x1800dc6f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dc6fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc701  mov     rcx, rax
0x1800dc704  test    rax, rax
0x1800dc707  jz      short loc_1800DC727
0x1800dc709  mov     rax, [rax]
0x1800dc70c  mov     edx, 7F0h
0x1800dc711  mov     rax, [rax+8]
0x1800dc715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc71a  test    eax, eax
0x1800dc71c  jz      short loc_1800DC727
0x1800dc71e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc725  jmp     short loc_1800DC735
0x1800dc727  lea     rcx, qword_1801B07E0; this
0x1800dc72e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc735  cmp     byte ptr [rcx+8], 0
0x1800dc739  jz      short loc_1800DC760
0x1800dc73b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dc740  cmp     [rax+7CCh], ebx
0x1800dc746  jz      short loc_1800DC760
0x1800dc748  mov     r8d, 51h ; 'Q'; int
0x1800dc74e  mov     r9d, ebx; int
0x1800dc751  lea     rdx, aCmfavithumbnai_0; "CMFAVIThumbnailStreamProperty::SetNativ"...
0x1800dc758  mov     rcx, rax; this
0x1800dc75b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dc760  lea     rcx, [rsp+48h+ppstm]; void *
0x1800dc765  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800dc76a  mov     rbp, [rsp+48h+arg_18]
0x1800dc76f  mov     eax, ebx
0x1800dc771  mov     rbx, [rsp+48h+arg_10]
0x1800dc776  add     rsp, 30h
0x1800dc77a  pop     r14
0x1800dc77c  pop     rdi
0x1800dc77d  pop     rsi
0x1800dc77e  retn
```
