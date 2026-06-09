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
  __int64 v4; // r8
  __int64 v5; // r9
  wchar_t *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v9; // r8d
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  DWORD v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  int v47; // r8d
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  wchar_t *v61; // rcx
  CallStackTracing *v62; // rax
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  wchar_t *v68; // rcx
  CallStackTracing *v69; // rax
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  wchar_t *v73; // rcx
  CallStackTracing *v74; // rax
  wchar_t *v75; // rcx
  CallStackTracing *v76; // rax
  _BYTE v78[4]; // [rsp+30h] [rbp-39h] BYREF
  DWORD cbMaxLength; // [rsp+34h] [rbp-35h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-31h] BYREF
  int v81; // [rsp+40h] [rbp-29h] BYREF
  int v82; // [rsp+44h] [rbp-25h] BYREF
  int v83; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int8 *v84; // [rsp+50h] [rbp-19h] BYREF
  struct CMFProperty *v85; // [rsp+58h] [rbp-11h] BYREF
  __int128 v86; // [rsp+60h] [rbp-9h] BYREF
  __int128 v87; // [rsp+70h] [rbp+7h] BYREF
  int v88; // [rsp+80h] [rbp+17h]

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v78, "CMFMP3PropertyHandler::InternalCommit", 178);
  ppBuffer = 0;
  cbMaxLength = 0;
  v86 = 0;
  v84 = 0;
  v82 = 0;
  v81 = 0;
  v83 = 0;
  if ( (unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::GetFirstPosition((char *)this + 48, &v86) )
  {
    while ( (_QWORD)v86 )
    {
      v85 = 0;
      v88 = 0;
      v87 = 0;
      CTBucketHash<_tagpropertykey,CMFProperty *>::GetNext((char *)this + 48, &v86, &v87, &v85);
      if ( (unsigned int)MFGetAttributeUINT32(v85, &MF_MD_MODIFIED, 0) )
      {
        updated = CMFMP3PropertyHandler::WritePropertyInMFMetadata(this, v85);
        if ( updated < 0 )
        {
          v6 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2, v4, v5);
            CallStackTracing::s_wpInstance = v7;
            if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
            {
              v6 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v6 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v6 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
            {
              v9 = 213;
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
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
      {
        v9 = 222;
LABEL_147:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFMP3PropertyHandler::InternalCommit", v9, updated);
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
      v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
        {
          v9 = 233;
          goto LABEL_147;
        }
      }
      goto LABEL_148;
    }
    v25 = cbMaxLength;
    if ( cbMaxLength > *((_DWORD *)this + 478) )
    {
      if ( ppBuffer )
      {
        ATL::AtlComPtrAssign((struct IUnknown **)&ppBuffer, 0);
        v25 = cbMaxLength;
      }
      updated = MFCreateMemoryBuffer(v25, &ppBuffer);
      if ( updated < 0 )
      {
        v29 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v29 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v29 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
          {
            v9 = 240;
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
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
          {
            v9 = 242;
            goto LABEL_147;
          }
        }
        goto LABEL_148;
      }
      updated = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned __int8 **, int *, int *))ppBuffer->lpVtbl->Lock)(
                  ppBuffer,
                  &v84,
                  &v82,
                  &v81);
      if ( updated < 0 )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
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
            v9 = 244;
            goto LABEL_147;
          }
        }
        goto LABEL_148;
      }
      updated = CMFMP3PropertyHandler::MoveFileData(this, v84, *((_DWORD *)this + 478), cbMaxLength);
      if ( updated < 0 )
      {
        v44 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
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
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) == updated )
          goto LABEL_138;
        v47 = 257;
        goto LABEL_80;
      }
LABEL_137:
      *((_DWORD *)this + 478) = cbMaxLength;
      goto LABEL_138;
    }
    if ( cbMaxLength != *((_DWORD *)this + 478) )
    {
      v75 = (wchar_t *)CallStackTracing::s_wpInstance;
      updated = -1072875854;
      if ( !CallStackTracing::s_wpInstance )
      {
        v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
        CallStackTracing::s_wpInstance = v76;
        if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
        {
          v75 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v75 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v75 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        {
          v9 = 289;
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
        v51 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49, v50);
          CallStackTracing::s_wpInstance = v52;
          if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
          {
            v51 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v51 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v51 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
          {
            v9 = 266;
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
      v56 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53, v54, v55);
        CallStackTracing::s_wpInstance = v57;
        if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
        {
          v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v56 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v56 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
        {
          v9 = 272;
          goto LABEL_147;
        }
      }
      goto LABEL_148;
    }
    updated = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned __int8 **, int *, int *))ppBuffer->lpVtbl->Lock)(
                ppBuffer,
                &v84,
                &v82,
                &v81);
    if ( updated < 0 )
    {
      v61 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
        CallStackTracing::s_wpInstance = v62;
        if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
        {
          v61 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v61 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v61 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
        {
          v9 = 274;
          goto LABEL_147;
        }
      }
      goto LABEL_148;
    }
    updated = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, int *))(**((_QWORD **)this + 111) + 32LL))(
                *((_QWORD *)this + 111),
                v84,
                *((unsigned int *)this + 478),
                &v83);
    if ( updated >= 0 )
    {
      if ( v83 == *((_DWORD *)this + 478) )
      {
        updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 111) + 64LL))(
                    *((_QWORD *)this + 111),
                    0);
        if ( updated >= 0 )
          goto LABEL_137;
        v73 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71, v72);
          CallStackTracing::s_wpInstance = v74;
          if ( v74 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
          {
            v73 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v73 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( !*((_BYTE *)v73 + 8) )
          goto LABEL_138;
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
        if ( *((_DWORD *)v46 + 499) == updated )
          goto LABEL_138;
        v47 = 285;
      }
      else
      {
        v68 = (wchar_t *)CallStackTracing::s_wpInstance;
        updated = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64, v65);
          CallStackTracing::s_wpInstance = v69;
          if ( v69 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
          {
            v68 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v68 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( !*((_BYTE *)v68 + 8) )
          goto LABEL_138;
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
        if ( *((_DWORD *)v46 + 499) == -2147418113 )
          goto LABEL_138;
        v47 = 282;
      }
    }
    else
    {
      v66 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64, v65);
        CallStackTracing::s_wpInstance = v67;
        if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
        {
          v66 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v66 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( !*((_BYTE *)v66 + 8) )
        goto LABEL_138;
      v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
      if ( *((_DWORD *)v46 + 499) == updated )
        goto LABEL_138;
      v47 = 278;
    }
LABEL_80:
    CallStackContext::TraceFailure(v46, "CMFMP3PropertyHandler::InternalCommit", v47, updated);
LABEL_138:
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
    goto LABEL_148;
  }
  v18 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
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
    if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
    {
      v9 = 228;
      goto LABEL_147;
    }
  }
LABEL_148:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v78);
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
