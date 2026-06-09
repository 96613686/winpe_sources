# CMFMP3PropertyHandler::InternalCommit(void)

- ea: `0x180167b70`
- end: `0x180168588`
- name: `?InternalCommit@CMFMP3PropertyHandler@@MEAAJXZ`
- size: `2584`
- prototype: `__int64 __fastcall(CMFMP3PropertyHandler *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180044400`
- `0x18005a094`
- `0x180061340`
- `0x18007904c`
- `0x18010055c`
- `0x180110ed0`
- `0x180167b70`
- `0x1801688b8`
- `0x180168ea8`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167c4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167ce2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167d77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167e24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167ed8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167f72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016800d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801680a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180168164`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801681ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016829a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016833b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801683c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180168458`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801684e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167c4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167ce2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167d77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167e24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167ed8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180167f72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016800d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801680a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180168164`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801681ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016829a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016833b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801683c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180168458`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801684e9`
- `MFPlat!MFCreateMemoryBuffer` at `0x180167d59`
- `MFPlat!MFCreateMemoryBuffer` at `0x180167eba`
- `MFPlat!MFCreateMemoryBuffer` at `0x180167d59`
- `MFPlat!MFCreateMemoryBuffer` at `0x180167eba`

## string_xrefs

- `0x180167b96`: `CMFMP3PropertyHandler::InternalCommit`

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
              v4 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v9 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v15 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v19 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v22 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v25 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v28 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v49 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v33 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v36 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v39 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v47 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v44 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v42 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v12 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x180167b70  push    rbp
0x180167b72  push    rbx
0x180167b73  push    rsi
0x180167b74  push    rdi
0x180167b75  push    r14
0x180167b77  push    r15
0x180167b79  lea     rbp, [rsp-2Fh]
0x180167b7e  sub     rsp, 98h
0x180167b85  mov     rax, cs:__security_cookie
0x180167b8c  xor     rax, rsp
0x180167b8f  mov     [rbp+57h+var_38], rax
0x180167b93  mov     rdi, rcx
0x180167b96  lea     r15, aCmfmp3property_2; "CMFMP3PropertyHandler::InternalCommit"
0x180167b9d  mov     rdx, r15; char *
0x180167ba0  lea     rcx, [rbp+57h+var_90]; this
0x180167ba4  mov     r8d, 0B2h; int
0x180167baa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180167baf  xor     r14d, r14d
0x180167bb2  lea     rdx, [rbp+57h+var_60]
0x180167bb6  xorps   xmm0, xmm0
0x180167bb9  mov     [rbp+57h+ppBuffer], r14
0x180167bbd  lea     rcx, [rdi+30h]
0x180167bc1  mov     [rbp+57h+cbMaxLength], r14d
0x180167bc5  movups  [rbp+57h+var_60], xmm0
0x180167bc9  mov     [rbp+57h+var_70], r14
0x180167bcd  mov     [rbp+57h+var_7C], r14d
0x180167bd1  mov     [rbp+57h+var_80], r14d
0x180167bd5  mov     [rbp+57h+var_78], r14d
0x180167bd9  call    ?GetFirstPosition@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::GetFirstPosition(CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x180167bde  test    eax, eax
0x180167be0  jz      loc_180167CB7
0x180167be6  cmp     qword ptr [rbp+57h+var_60], r14
0x180167bea  jz      loc_180167CB7
0x180167bf0  xorps   xmm0, xmm0
0x180167bf3  mov     [rbp+57h+var_68], r14
0x180167bf7  xor     eax, eax
0x180167bf9  lea     r9, [rbp+57h+var_68]
0x180167bfd  lea     r8, [rbp+57h+var_50]
0x180167c01  mov     [rbp+57h+var_40], eax
0x180167c04  lea     rdx, [rbp+57h+var_60]
0x180167c08  lea     rcx, [rdi+30h]
0x180167c0c  movups  [rbp+57h+var_50], xmm0
0x180167c10  call    ?GetNext@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEAU_POSITION@1@AEAU_tagpropertykey@@AEAPEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::GetNext(CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &,_tagpropertykey &,CMFProperty * &)
0x180167c15  mov     rcx, [rbp+57h+var_68]
0x180167c19  lea     rdx, MF_MD_MODIFIED
0x180167c20  xor     r8d, r8d
0x180167c23  call    MFGetAttributeUINT32
0x180167c28  test    eax, eax
0x180167c2a  jz      short loc_180167BE6
0x180167c2c  mov     rdx, [rbp+57h+var_68]; struct CMFProperty *
0x180167c30  mov     rcx, rdi; this
0x180167c33  call    ?WritePropertyInMFMetadata@CMFMP3PropertyHandler@@IEAAJPEAVCMFProperty@@@Z; CMFMP3PropertyHandler::WritePropertyInMFMetadata(CMFProperty *)
0x180167c38  mov     ebx, eax
0x180167c3a  test    eax, eax
0x180167c3c  jns     short loc_180167BE6
0x180167c3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167c45  test    rcx, rcx
0x180167c48  jnz     short loc_180167C91
0x180167c4a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180167c51  nop     dword ptr [rax+rax+00h]
0x180167c56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180167c5d  mov     rcx, rax
0x180167c60  test    rax, rax
0x180167c63  jz      short loc_180167C83
0x180167c65  mov     rax, [rax]
0x180167c68  mov     edx, 7F0h
0x180167c6d  mov     rax, [rax+8]
0x180167c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167c76  test    eax, eax
0x180167c78  jz      short loc_180167C83
0x180167c7a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167c81  jmp     short loc_180167C91
0x180167c83  lea     rcx, qword_1801B97E0; this
0x180167c8a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180167c91  cmp     [rcx+8], r14b
0x180167c95  jz      loc_180168557
0x180167c9b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180167ca0  cmp     [rax+7CCh], ebx
0x180167ca6  jz      loc_180168557
0x180167cac  mov     r8d, 0D5h
0x180167cb2  jmp     loc_180168549
0x180167cb7  mov     rcx, [rdi+770h]
0x180167cbe  lea     r8, [rbp+57h+cbMaxLength]
0x180167cc2  xor     edx, edx
0x180167cc4  mov     rax, [rcx]
0x180167cc7  mov     rax, [rax+28h]
0x180167ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167cd0  mov     ebx, eax
0x180167cd2  test    eax, eax
0x180167cd4  jns     short loc_180167D4F
0x180167cd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167cdd  test    rcx, rcx
0x180167ce0  jnz     short loc_180167D29
0x180167ce2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180167ce9  nop     dword ptr [rax+rax+00h]
0x180167cee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180167cf5  mov     rcx, rax
0x180167cf8  test    rax, rax
0x180167cfb  jz      short loc_180167D1B
0x180167cfd  mov     rax, [rax]
0x180167d00  mov     edx, 7F0h
0x180167d05  mov     rax, [rax+8]
0x180167d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167d0e  test    eax, eax
0x180167d10  jz      short loc_180167D1B
0x180167d12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167d19  jmp     short loc_180167D29
0x180167d1b  lea     rcx, qword_1801B97E0; this
0x180167d22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180167d29  cmp     [rcx+8], r14b
0x180167d2d  jz      loc_180168557
0x180167d33  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180167d38  cmp     [rax+7CCh], ebx
0x180167d3e  jz      loc_180168557
0x180167d44  mov     r8d, 0DEh
0x180167d4a  jmp     loc_180168549
0x180167d4f  mov     ecx, [rdi+778h]; cbMaxLength
0x180167d55  lea     rdx, [rbp+57h+ppBuffer]; ppBuffer
0x180167d59  call    cs:__imp_MFCreateMemoryBuffer
0x180167d60  nop     dword ptr [rax+rax+00h]
0x180167d65  mov     ebx, eax
0x180167d67  test    eax, eax
0x180167d69  jns     short loc_180167DE4
0x180167d6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167d72  test    rcx, rcx
0x180167d75  jnz     short loc_180167DBE
0x180167d77  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180167d7e  nop     dword ptr [rax+rax+00h]
0x180167d83  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180167d8a  mov     rcx, rax
0x180167d8d  test    rax, rax
0x180167d90  jz      short loc_180167DB0
0x180167d92  mov     rax, [rax]
0x180167d95  mov     edx, 7F0h
0x180167d9a  mov     rax, [rax+8]
0x180167d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167da3  test    eax, eax
0x180167da5  jz      short loc_180167DB0
0x180167da7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167dae  jmp     short loc_180167DBE
0x180167db0  lea     rcx, qword_1801B97E0; this
0x180167db7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180167dbe  cmp     [rcx+8], r14b
0x180167dc2  jz      loc_180168557
0x180167dc8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180167dcd  cmp     [rax+7CCh], ebx
0x180167dd3  jz      loc_180168557
0x180167dd9  mov     r8d, 0E4h
0x180167ddf  jmp     loc_180168549
0x180167de4  mov     rcx, [rdi+770h]
0x180167deb  lea     r8, [rbp+57h+cbMaxLength]
0x180167def  mov     rdx, [rbp+57h+ppBuffer]
0x180167df3  mov     rax, [rcx]
0x180167df6  mov     rax, [rax+28h]
0x180167dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167dff  mov     ecx, 80000000h
0x180167e04  mov     ebx, eax
0x180167e06  add     eax, ecx
0x180167e08  test    ecx, eax
0x180167e0a  jnz     loc_180167E91
0x180167e10  cmp     ebx, 0C00D36B1h
0x180167e16  jz      short loc_180167E91
0x180167e18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167e1f  test    rcx, rcx
0x180167e22  jnz     short loc_180167E6B
0x180167e24  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180167e2b  nop     dword ptr [rax+rax+00h]
0x180167e30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180167e37  mov     rcx, rax
0x180167e3a  test    rax, rax
0x180167e3d  jz      short loc_180167E5D
0x180167e3f  mov     rax, [rax]
0x180167e42  mov     edx, 7F0h
0x180167e47  mov     rax, [rax+8]
0x180167e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167e50  test    eax, eax
0x180167e52  jz      short loc_180167E5D
0x180167e54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167e5b  jmp     short loc_180167E6B
0x180167e5d  lea     rcx, qword_1801B97E0; this
0x180167e64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180167e6b  cmp     [rcx+8], r14b
0x180167e6f  jz      loc_180168557
0x180167e75  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180167e7a  cmp     [rax+7CCh], ebx
0x180167e80  jz      loc_180168557
0x180167e86  mov     r8d, 0E9h
0x180167e8c  jmp     loc_180168549
0x180167e91  mov     eax, [rbp+57h+cbMaxLength]
0x180167e94  cmp     eax, [rdi+778h]
0x180167e9a  jbe     loc_180168122
0x180167ea0  cmp     [rbp+57h+ppBuffer], r14
0x180167ea4  jz      short loc_180167EB4
0x180167ea6  xor     edx, edx; struct IUnknown *
0x180167ea8  lea     rcx, [rbp+57h+ppBuffer]; struct IUnknown **
0x180167eac  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180167eb1  mov     eax, [rbp+57h+cbMaxLength]
0x180167eb4  lea     rdx, [rbp+57h+ppBuffer]; ppBuffer
0x180167eb8  mov     ecx, eax; cbMaxLength
0x180167eba  call    cs:__imp_MFCreateMemoryBuffer
0x180167ec1  nop     dword ptr [rax+rax+00h]
0x180167ec6  mov     ebx, eax
0x180167ec8  test    eax, eax
0x180167eca  jns     short loc_180167F45
0x180167ecc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167ed3  test    rcx, rcx
0x180167ed6  jnz     short loc_180167F1F
0x180167ed8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180167edf  nop     dword ptr [rax+rax+00h]
0x180167ee4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180167eeb  mov     rcx, rax
0x180167eee  test    rax, rax
0x180167ef1  jz      short loc_180167F11
0x180167ef3  mov     rax, [rax]
0x180167ef6  mov     edx, 7F0h
0x180167efb  mov     rax, [rax+8]
0x180167eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167f04  test    eax, eax
0x180167f06  jz      short loc_180167F11
0x180167f08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167f0f  jmp     short loc_180167F1F
0x180167f11  lea     rcx, qword_1801B97E0; this
0x180167f18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180167f1f  cmp     [rcx+8], r14b
0x180167f23  jz      loc_180168557
0x180167f29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180167f2e  cmp     [rax+7CCh], ebx
0x180167f34  jz      loc_180168557
0x180167f3a  mov     r8d, 0F0h
0x180167f40  jmp     loc_180168549
0x180167f45  mov     rcx, [rdi+770h]
0x180167f4c  lea     r8, [rbp+57h+cbMaxLength]
0x180167f50  mov     rdx, [rbp+57h+ppBuffer]
0x180167f54  mov     rax, [rcx]
0x180167f57  mov     rax, [rax+28h]
0x180167f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167f60  mov     ebx, eax
0x180167f62  test    eax, eax
0x180167f64  jns     short loc_180167FDF
0x180167f66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167f6d  test    rcx, rcx
0x180167f70  jnz     short loc_180167FB9
0x180167f72  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180167f79  nop     dword ptr [rax+rax+00h]
0x180167f7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180167f85  mov     rcx, rax
0x180167f88  test    rax, rax
0x180167f8b  jz      short loc_180167FAB
0x180167f8d  mov     rax, [rax]
0x180167f90  mov     edx, 7F0h
0x180167f95  mov     rax, [rax+8]
0x180167f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167f9e  test    eax, eax
0x180167fa0  jz      short loc_180167FAB
0x180167fa2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180167fa9  jmp     short loc_180167FB9
0x180167fab  lea     rcx, qword_1801B97E0; this
0x180167fb2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180167fb9  cmp     [rcx+8], r14b
0x180167fbd  jz      loc_180168557
0x180167fc3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180167fc8  cmp     [rax+7CCh], ebx
0x180167fce  jz      loc_180168557
0x180167fd4  mov     r8d, 0F2h
0x180167fda  jmp     loc_180168549
0x180167fdf  mov     rcx, [rbp+57h+ppBuffer]
0x180167fe3  lea     r9, [rbp+57h+var_80]
0x180167fe7  lea     r8, [rbp+57h+var_7C]
0x180167feb  lea     rdx, [rbp+57h+var_70]
0x180167fef  mov     rax, [rcx]
0x180167ff2  mov     rax, [rax+18h]
0x180167ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167ffb  mov     ebx, eax
0x180167ffd  test    eax, eax
0x180167fff  jns     short loc_18016807A
0x180168001  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180168008  test    rcx, rcx
0x18016800b  jnz     short loc_180168054
0x18016800d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180168014  nop     dword ptr [rax+rax+00h]
0x180168019  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180168020  mov     rcx, rax
0x180168023  test    rax, rax
0x180168026  jz      short loc_180168046
0x180168028  mov     rax, [rax]
0x18016802b  mov     edx, 7F0h
0x180168030  mov     rax, [rax+8]
0x180168034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168039  test    eax, eax
0x18016803b  jz      short loc_180168046
0x18016803d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180168044  jmp     short loc_180168054
0x180168046  lea     rcx, qword_1801B97E0; this
0x18016804d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180168054  cmp     [rcx+8], r14b
0x180168058  jz      loc_180168557
0x18016805e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180168063  cmp     [rax+7CCh], ebx
0x180168069  jz      loc_180168557
0x18016806f  mov     r8d, 0F4h
  ... truncated ...
```
