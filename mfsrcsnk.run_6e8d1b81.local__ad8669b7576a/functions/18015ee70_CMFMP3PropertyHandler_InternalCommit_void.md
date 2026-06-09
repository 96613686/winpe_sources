# CMFMP3PropertyHandler::InternalCommit(void)

- ea: `0x18015ee70`
- end: `0x18015f81d`
- name: `?InternalCommit@CMFMP3PropertyHandler@@MEAAJXZ`
- size: `2477`
- prototype: `__int64 __fastcall(CMFMP3PropertyHandler *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180042320`
- `0x180056e38`
- `0x1800607d8`
- `0x18007341c`
- `0x1800f97a4`
- `0x1801099f0`
- `0x18015ee70`
- `0x18015fb34`
- `0x1801600f0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015ef4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015efdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f065`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f108`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f1b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f244`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f2d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f36d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f424`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f4b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f54e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f5e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f66c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f6fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f785`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015ef4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015efdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f065`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f108`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f1b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f244`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f2d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f36d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f424`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f4b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f54e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f5e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f66c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f6fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015f785`
- `MFPlat!MFCreateMemoryBuffer` at `0x18015f04d`
- `MFPlat!MFCreateMemoryBuffer` at `0x18015f198`
- `MFPlat!MFCreateMemoryBuffer` at `0x18015f04d`
- `MFPlat!MFCreateMemoryBuffer` at `0x18015f198`

## string_xrefs

- `0x18015ee96`: `CMFMP3PropertyHandler::InternalCommit`

## pseudocode

```c
__int64 __fastcall CMFMP3PropertyHandler::InternalCommit(CMFMP3PropertyHandler *this)
{
  __int64 v2; // rdx
  HRESULT updated; // ebx
  wchar_t *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v7; // r8d
  __int64 v8; // rdx
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  DWORD v17; // eax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  int v31; // r8d
  __int64 v32; // rdx
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  __int64 v38; // rdx
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  __int64 v41; // rdx
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  __int64 v46; // rdx
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  _BYTE v52[4]; // [rsp+30h] [rbp-39h] BYREF
  DWORD cbMaxLength; // [rsp+34h] [rbp-35h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-31h] BYREF
  int v55; // [rsp+40h] [rbp-29h] BYREF
  int v56; // [rsp+44h] [rbp-25h] BYREF
  int v57; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int8 *v58; // [rsp+50h] [rbp-19h] BYREF
  struct CMFProperty *v59; // [rsp+58h] [rbp-11h] BYREF
  __int128 v60; // [rsp+60h] [rbp-9h] BYREF
  __int128 v61; // [rsp+70h] [rbp+7h] BYREF
  int v62; // [rsp+80h] [rbp+17h]

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v52, "CMFMP3PropertyHandler::InternalCommit", 178);
  ppBuffer = 0;
  cbMaxLength = 0;
  v60 = 0;
  v58 = 0;
  v56 = 0;
  v55 = 0;
  v57 = 0;
  if ( (unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::GetFirstPosition((char *)this + 48, &v60) )
  {
    while ( (_QWORD)v60 )
    {
      v59 = 0;
      v62 = 0;
      v61 = 0;
      CTBucketHash<_tagpropertykey,CMFProperty *>::GetNext((char *)this + 48, &v60, &v61, &v59);
      if ( (unsigned int)MFGetAttributeUINT32(v59, MF_MD_MODIFIED, 0) )
      {
        updated = CMFMP3PropertyHandler::WritePropertyInMFMetadata(this, v59);
        if ( updated < 0 )
        {
          v4 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
            CallStackTracing::s_wpInstance = v5;
            if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
            {
              v4 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
            {
              v7 = 213;
              goto LABEL_147;
            }
          }
          goto LABEL_148;
        }
      }
    }
  }
  updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, DWORD *))(**((_QWORD **)this + 238) + 40LL))(
              *((_QWORD *)this + 238),
              0,
              &cbMaxLength);
  if ( updated < 0 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
      {
        v7 = 222;
LABEL_147:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFMP3PropertyHandler::InternalCommit", v7, updated);
        goto LABEL_148;
      }
    }
    goto LABEL_148;
  }
  updated = MFCreateMemoryBuffer(*((_DWORD *)this + 478), &ppBuffer);
  if ( updated >= 0 )
  {
    updated = (*(__int64 (__fastcall **)(_QWORD, IMFMediaBuffer *, DWORD *))(**((_QWORD **)this + 238) + 40LL))(
                *((_QWORD *)this + 238),
                ppBuffer,
                &cbMaxLength);
    if ( (int)(updated + 0x80000000) >= 0 && updated != -1072875855 )
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
        {
          v7 = 233;
          goto LABEL_147;
        }
      }
      goto LABEL_148;
    }
    v17 = cbMaxLength;
    if ( cbMaxLength > *((_DWORD *)this + 478) )
    {
      if ( ppBuffer )
      {
        ATL::AtlComPtrAssign((struct IUnknown **)&ppBuffer, 0);
        v17 = cbMaxLength;
      }
      updated = MFCreateMemoryBuffer(v17, &ppBuffer);
      if ( updated < 0 )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
          {
            v7 = 240;
            goto LABEL_147;
          }
        }
        goto LABEL_148;
      }
      updated = (*(__int64 (__fastcall **)(_QWORD, IMFMediaBuffer *, DWORD *))(**((_QWORD **)this + 238) + 40LL))(
                  *((_QWORD *)this + 238),
                  ppBuffer,
                  &cbMaxLength);
      if ( updated < 0 )
      {
        v22 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
          {
            v7 = 242;
            goto LABEL_147;
          }
        }
        goto LABEL_148;
      }
      updated = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned __int8 **, int *, int *))ppBuffer->lpVtbl->Lock)(
                  ppBuffer,
                  &v58,
                  &v56,
                  &v55);
      if ( updated < 0 )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
          {
            v7 = 244;
            goto LABEL_147;
          }
        }
        goto LABEL_148;
      }
      updated = CMFMP3PropertyHandler::MoveFileData(this, v58, *((_DWORD *)this + 478), cbMaxLength);
      if ( updated < 0 )
      {
        v28 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( !*((_BYTE *)v28 + 8) )
          goto LABEL_138;
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) == updated )
          goto LABEL_138;
        v31 = 257;
        goto LABEL_80;
      }
LABEL_137:
      *((_DWORD *)this + 478) = cbMaxLength;
      goto LABEL_138;
    }
    if ( cbMaxLength != *((_DWORD *)this + 478) )
    {
      v49 = (wchar_t *)CallStackTracing::s_wpInstance;
      updated = -1072875854;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        {
          v7 = 289;
          goto LABEL_147;
        }
      }
      goto LABEL_148;
    }
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 238) + 32LL))(*((_QWORD *)this + 238)) )
    {
      updated = CMFMP3PropertyHandler::UpdateFooter(this, *((struct IStream **)this + 111));
      if ( updated < 0 )
      {
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
          {
            v7 = 266;
            goto LABEL_147;
          }
        }
        goto LABEL_148;
      }
    }
    updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 111) + 40LL))(
                *((_QWORD *)this + 111),
                0,
                0,
                0);
    if ( updated < 0 )
    {
      v36 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
        {
          v7 = 272;
          goto LABEL_147;
        }
      }
      goto LABEL_148;
    }
    updated = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned __int8 **, int *, int *))ppBuffer->lpVtbl->Lock)(
                ppBuffer,
                &v58,
                &v56,
                &v55);
    if ( updated < 0 )
    {
      v39 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v39 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
        {
          v7 = 274;
          goto LABEL_147;
        }
      }
      goto LABEL_148;
    }
    updated = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, int *))(**((_QWORD **)this + 111) + 32LL))(
                *((_QWORD *)this + 111),
                v58,
                *((unsigned int *)this + 478),
                &v57);
    if ( updated >= 0 )
    {
      if ( v57 == *((_DWORD *)this + 478) )
      {
        updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 111) + 64LL))(
                    *((_QWORD *)this + 111),
                    0);
        if ( updated >= 0 )
          goto LABEL_137;
        v47 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
          CallStackTracing::s_wpInstance = v48;
          if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
          {
            v47 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v47 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( !*((_BYTE *)v47 + 8) )
          goto LABEL_138;
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
        if ( *((_DWORD *)v30 + 499) == updated )
          goto LABEL_138;
        v31 = 285;
      }
      else
      {
        v44 = (wchar_t *)CallStackTracing::s_wpInstance;
        updated = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
          CallStackTracing::s_wpInstance = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
          {
            v44 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( !*((_BYTE *)v44 + 8) )
          goto LABEL_138;
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v30 + 499) == -2147418113 )
          goto LABEL_138;
        v31 = 282;
      }
    }
    else
    {
      v42 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( !*((_BYTE *)v42 + 8) )
        goto LABEL_138;
      v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
      if ( *((_DWORD *)v30 + 499) == updated )
        goto LABEL_138;
      v31 = 278;
    }
LABEL_80:
    CallStackContext::TraceFailure(v30, "CMFMP3PropertyHandler::InternalCommit", v31, updated);
LABEL_138:
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
    goto LABEL_148;
  }
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
    if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
    {
      v7 = 228;
      goto LABEL_147;
    }
  }
LABEL_148:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v52);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18015ee70  push    rbp
0x18015ee72  push    rbx
0x18015ee73  push    rsi
0x18015ee74  push    rdi
0x18015ee75  push    r14
0x18015ee77  push    r15
0x18015ee79  lea     rbp, [rsp-2Fh]
0x18015ee7e  sub     rsp, 98h
0x18015ee85  mov     rax, cs:__security_cookie
0x18015ee8c  xor     rax, rsp
0x18015ee8f  mov     [rbp+57h+var_38], rax
0x18015ee93  mov     rdi, rcx
0x18015ee96  lea     r15, aCmfmp3property_2; "CMFMP3PropertyHandler::InternalCommit"
0x18015ee9d  mov     rdx, r15; char *
0x18015eea0  lea     rcx, [rbp+57h+var_90]; this
0x18015eea4  mov     r8d, 0B2h; int
0x18015eeaa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18015eeaf  xor     r14d, r14d
0x18015eeb2  lea     rdx, [rbp+57h+var_60]
0x18015eeb6  xorps   xmm0, xmm0
0x18015eeb9  mov     [rbp+57h+ppBuffer], r14
0x18015eebd  lea     rcx, [rdi+30h]
0x18015eec1  mov     [rbp+57h+cbMaxLength], r14d
0x18015eec5  movups  [rbp+57h+var_60], xmm0
0x18015eec9  mov     [rbp+57h+var_70], r14
0x18015eecd  mov     [rbp+57h+var_7C], r14d
0x18015eed1  mov     [rbp+57h+var_80], r14d
0x18015eed5  mov     [rbp+57h+var_78], r14d
0x18015eed9  call    ?GetFirstPosition@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::GetFirstPosition(CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x18015eede  test    eax, eax
0x18015eee0  jz      loc_18015EFB1
0x18015eee6  cmp     qword ptr [rbp+57h+var_60], r14
0x18015eeea  jz      loc_18015EFB1
0x18015eef0  xorps   xmm0, xmm0
0x18015eef3  mov     [rbp+57h+var_68], r14
0x18015eef7  xor     eax, eax
0x18015eef9  lea     r9, [rbp+57h+var_68]
0x18015eefd  lea     r8, [rbp+57h+var_50]
0x18015ef01  mov     [rbp+57h+var_40], eax
0x18015ef04  lea     rdx, [rbp+57h+var_60]
0x18015ef08  lea     rcx, [rdi+30h]
0x18015ef0c  movups  [rbp+57h+var_50], xmm0
0x18015ef10  call    ?GetNext@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEAU_POSITION@1@AEAU_tagpropertykey@@AEAPEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::GetNext(CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &,_tagpropertykey &,CMFProperty * &)
0x18015ef15  mov     rcx, [rbp+57h+var_68]
0x18015ef19  lea     rdx, MF_MD_MODIFIED
0x18015ef20  xor     r8d, r8d
0x18015ef23  call    MFGetAttributeUINT32
0x18015ef28  test    eax, eax
0x18015ef2a  jz      short loc_18015EEE6
0x18015ef2c  mov     rdx, [rbp+57h+var_68]; struct CMFProperty *
0x18015ef30  mov     rcx, rdi; this
0x18015ef33  call    ?WritePropertyInMFMetadata@CMFMP3PropertyHandler@@IEAAJPEAVCMFProperty@@@Z; CMFMP3PropertyHandler::WritePropertyInMFMetadata(CMFProperty *)
0x18015ef38  mov     ebx, eax
0x18015ef3a  test    eax, eax
0x18015ef3c  jns     short loc_18015EEE6
0x18015ef3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015ef45  test    rcx, rcx
0x18015ef48  jnz     short loc_18015EF8B
0x18015ef4a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015ef50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015ef57  mov     rcx, rax
0x18015ef5a  test    rax, rax
0x18015ef5d  jz      short loc_18015EF7D
0x18015ef5f  mov     rax, [rax]
0x18015ef62  mov     edx, 7F0h
0x18015ef67  mov     rax, [rax+8]
0x18015ef6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ef70  test    eax, eax
0x18015ef72  jz      short loc_18015EF7D
0x18015ef74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015ef7b  jmp     short loc_18015EF8B
0x18015ef7d  lea     rcx, qword_1801B07E0; this
0x18015ef84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015ef8b  cmp     [rcx+8], r14b
0x18015ef8f  jz      loc_18015F7ED
0x18015ef95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015ef9a  cmp     [rax+7CCh], ebx
0x18015efa0  jz      loc_18015F7ED
0x18015efa6  mov     r8d, 0D5h
0x18015efac  jmp     loc_18015F7DF
0x18015efb1  mov     rcx, [rdi+770h]
0x18015efb8  lea     r8, [rbp+57h+cbMaxLength]
0x18015efbc  xor     edx, edx
0x18015efbe  mov     rax, [rcx]
0x18015efc1  mov     rax, [rax+28h]
0x18015efc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015efca  mov     ebx, eax
0x18015efcc  test    eax, eax
0x18015efce  jns     short loc_18015F043
0x18015efd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015efd7  test    rcx, rcx
0x18015efda  jnz     short loc_18015F01D
0x18015efdc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015efe2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015efe9  mov     rcx, rax
0x18015efec  test    rax, rax
0x18015efef  jz      short loc_18015F00F
0x18015eff1  mov     rax, [rax]
0x18015eff4  mov     edx, 7F0h
0x18015eff9  mov     rax, [rax+8]
0x18015effd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f002  test    eax, eax
0x18015f004  jz      short loc_18015F00F
0x18015f006  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f00d  jmp     short loc_18015F01D
0x18015f00f  lea     rcx, qword_1801B07E0; this
0x18015f016  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f01d  cmp     [rcx+8], r14b
0x18015f021  jz      loc_18015F7ED
0x18015f027  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015f02c  cmp     [rax+7CCh], ebx
0x18015f032  jz      loc_18015F7ED
0x18015f038  mov     r8d, 0DEh
0x18015f03e  jmp     loc_18015F7DF
0x18015f043  mov     ecx, [rdi+778h]; cbMaxLength
0x18015f049  lea     rdx, [rbp+57h+ppBuffer]; ppBuffer
0x18015f04d  call    cs:__imp_MFCreateMemoryBuffer
0x18015f053  mov     ebx, eax
0x18015f055  test    eax, eax
0x18015f057  jns     short loc_18015F0CC
0x18015f059  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f060  test    rcx, rcx
0x18015f063  jnz     short loc_18015F0A6
0x18015f065  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015f06b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f072  mov     rcx, rax
0x18015f075  test    rax, rax
0x18015f078  jz      short loc_18015F098
0x18015f07a  mov     rax, [rax]
0x18015f07d  mov     edx, 7F0h
0x18015f082  mov     rax, [rax+8]
0x18015f086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f08b  test    eax, eax
0x18015f08d  jz      short loc_18015F098
0x18015f08f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f096  jmp     short loc_18015F0A6
0x18015f098  lea     rcx, qword_1801B07E0; this
0x18015f09f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f0a6  cmp     [rcx+8], r14b
0x18015f0aa  jz      loc_18015F7ED
0x18015f0b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015f0b5  cmp     [rax+7CCh], ebx
0x18015f0bb  jz      loc_18015F7ED
0x18015f0c1  mov     r8d, 0E4h
0x18015f0c7  jmp     loc_18015F7DF
0x18015f0cc  mov     rcx, [rdi+770h]
0x18015f0d3  lea     r8, [rbp+57h+cbMaxLength]
0x18015f0d7  mov     rdx, [rbp+57h+ppBuffer]
0x18015f0db  mov     rax, [rcx]
0x18015f0de  mov     rax, [rax+28h]
0x18015f0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f0e7  mov     ecx, 80000000h
0x18015f0ec  mov     ebx, eax
0x18015f0ee  add     eax, ecx
0x18015f0f0  test    ecx, eax
0x18015f0f2  jnz     short loc_18015F16F
0x18015f0f4  cmp     ebx, 0C00D36B1h
0x18015f0fa  jz      short loc_18015F16F
0x18015f0fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f103  test    rcx, rcx
0x18015f106  jnz     short loc_18015F149
0x18015f108  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015f10e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f115  mov     rcx, rax
0x18015f118  test    rax, rax
0x18015f11b  jz      short loc_18015F13B
0x18015f11d  mov     rax, [rax]
0x18015f120  mov     edx, 7F0h
0x18015f125  mov     rax, [rax+8]
0x18015f129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f12e  test    eax, eax
0x18015f130  jz      short loc_18015F13B
0x18015f132  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f139  jmp     short loc_18015F149
0x18015f13b  lea     rcx, qword_1801B07E0; this
0x18015f142  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f149  cmp     [rcx+8], r14b
0x18015f14d  jz      loc_18015F7ED
0x18015f153  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015f158  cmp     [rax+7CCh], ebx
0x18015f15e  jz      loc_18015F7ED
0x18015f164  mov     r8d, 0E9h
0x18015f16a  jmp     loc_18015F7DF
0x18015f16f  mov     eax, [rbp+57h+cbMaxLength]
0x18015f172  cmp     eax, [rdi+778h]
0x18015f178  jbe     loc_18015F3E2
0x18015f17e  cmp     [rbp+57h+ppBuffer], r14
0x18015f182  jz      short loc_18015F192
0x18015f184  xor     edx, edx; struct IUnknown *
0x18015f186  lea     rcx, [rbp+57h+ppBuffer]; struct IUnknown **
0x18015f18a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18015f18f  mov     eax, [rbp+57h+cbMaxLength]
0x18015f192  lea     rdx, [rbp+57h+ppBuffer]; ppBuffer
0x18015f196  mov     ecx, eax; cbMaxLength
0x18015f198  call    cs:__imp_MFCreateMemoryBuffer
0x18015f19e  mov     ebx, eax
0x18015f1a0  test    eax, eax
0x18015f1a2  jns     short loc_18015F217
0x18015f1a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f1ab  test    rcx, rcx
0x18015f1ae  jnz     short loc_18015F1F1
0x18015f1b0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015f1b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f1bd  mov     rcx, rax
0x18015f1c0  test    rax, rax
0x18015f1c3  jz      short loc_18015F1E3
0x18015f1c5  mov     rax, [rax]
0x18015f1c8  mov     edx, 7F0h
0x18015f1cd  mov     rax, [rax+8]
0x18015f1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f1d6  test    eax, eax
0x18015f1d8  jz      short loc_18015F1E3
0x18015f1da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f1e1  jmp     short loc_18015F1F1
0x18015f1e3  lea     rcx, qword_1801B07E0; this
0x18015f1ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f1f1  cmp     [rcx+8], r14b
0x18015f1f5  jz      loc_18015F7ED
0x18015f1fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015f200  cmp     [rax+7CCh], ebx
0x18015f206  jz      loc_18015F7ED
0x18015f20c  mov     r8d, 0F0h
0x18015f212  jmp     loc_18015F7DF
0x18015f217  mov     rcx, [rdi+770h]
0x18015f21e  lea     r8, [rbp+57h+cbMaxLength]
0x18015f222  mov     rdx, [rbp+57h+ppBuffer]
0x18015f226  mov     rax, [rcx]
0x18015f229  mov     rax, [rax+28h]
0x18015f22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f232  mov     ebx, eax
0x18015f234  test    eax, eax
0x18015f236  jns     short loc_18015F2AB
0x18015f238  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f23f  test    rcx, rcx
0x18015f242  jnz     short loc_18015F285
0x18015f244  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015f24a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f251  mov     rcx, rax
0x18015f254  test    rax, rax
0x18015f257  jz      short loc_18015F277
0x18015f259  mov     rax, [rax]
0x18015f25c  mov     edx, 7F0h
0x18015f261  mov     rax, [rax+8]
0x18015f265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f26a  test    eax, eax
0x18015f26c  jz      short loc_18015F277
0x18015f26e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f275  jmp     short loc_18015F285
0x18015f277  lea     rcx, qword_1801B07E0; this
0x18015f27e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f285  cmp     [rcx+8], r14b
0x18015f289  jz      loc_18015F7ED
0x18015f28f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015f294  cmp     [rax+7CCh], ebx
0x18015f29a  jz      loc_18015F7ED
0x18015f2a0  mov     r8d, 0F2h
0x18015f2a6  jmp     loc_18015F7DF
0x18015f2ab  mov     rcx, [rbp+57h+ppBuffer]
0x18015f2af  lea     r9, [rbp+57h+var_80]
0x18015f2b3  lea     r8, [rbp+57h+var_7C]
0x18015f2b7  lea     rdx, [rbp+57h+var_70]
0x18015f2bb  mov     rax, [rcx]
0x18015f2be  mov     rax, [rax+18h]
0x18015f2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f2c7  mov     ebx, eax
0x18015f2c9  test    eax, eax
0x18015f2cb  jns     short loc_18015F340
0x18015f2cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f2d4  test    rcx, rcx
0x18015f2d7  jnz     short loc_18015F31A
0x18015f2d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015f2df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f2e6  mov     rcx, rax
0x18015f2e9  test    rax, rax
0x18015f2ec  jz      short loc_18015F30C
0x18015f2ee  mov     rax, [rax]
0x18015f2f1  mov     edx, 7F0h
0x18015f2f6  mov     rax, [rax+8]
0x18015f2fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f2ff  test    eax, eax
0x18015f301  jz      short loc_18015F30C
0x18015f303  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f30a  jmp     short loc_18015F31A
0x18015f30c  lea     rcx, qword_1801B07E0; this
0x18015f313  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015f31a  cmp     [rcx+8], r14b
0x18015f31e  jz      loc_18015F7ED
0x18015f324  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015f329  cmp     [rax+7CCh], ebx
0x18015f32f  jz      loc_18015F7ED
0x18015f335  mov     r8d, 0F4h
0x18015f33b  jmp     loc_18015F7DF
0x18015f340  mov     r9d, [rbp+57h+cbMaxLength]; unsigned int
0x18015f344  mov     rcx, rdi; this
0x18015f347  mov     r8d, [rdi+778h]; unsigned int
0x18015f34e  mov     rdx, [rbp+57h+var_70]; unsigned __int8 *
0x18015f352  call    ?MoveFileData@CMFMP3PropertyHandler@@IEAAJPEAEKK@Z; CMFMP3PropertyHandler::MoveFileData(uchar *,ulong,ulong)
0x18015f357  mov     ebx, eax
0x18015f359  test    eax, eax
0x18015f35b  jns     loc_18015F759
  ... truncated ...
```
