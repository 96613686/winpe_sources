# CBinaryReader::ReadVariantValue(ushort,tagPROPVARIANT *)

- ea: `0x180105110`
- end: `0x180106e67`
- name: `?ReadVariantValue@CBinaryReader@@QEAAJGPEAUtagPROPVARIANT@@@Z`
- size: `7511`
- prototype: `__int64 __fastcall(CBinaryReader *__hidden this, unsigned __int16, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b5000`
- `0x1801950e8`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18008d798`
- `0x1800b5000`
- `0x180105110`
- `0x18019c398`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106e30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106e30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010584b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801062ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801065ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010584b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801062ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801065ab`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180105297`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180105297`
- `OLEAUT32!__imp_SysFreeString` at `0x180106e3e`
- `OLEAUT32!__imp_SysFreeString` at `0x180106e3e`

## string_xrefs

- `0x180105131`: `CBinaryReader::ReadVariantValue`
- `0x180105310`: `CBinaryReader::ReadVariantValue`
- `0x1801053d9`: `CBinaryReader::ReadVariantValue`
- `0x1801055ad`: `CBinaryReader::ReadVariantValue`
- `0x18010599c`: `CBinaryReader::ReadVariantValue`
- `0x18010644e`: `CBinaryReader::ReadVariantValue`
- `0x1801064da`: `CBinaryReader::ReadVariantValue`
- `0x180106714`: `CBinaryReader::ReadVariantValue`
- `0x1801067a0`: `CBinaryReader::ReadVariantValue`

## pseudocode

```c
__int64 __fastcall CBinaryReader::ReadVariantValue(CBinaryReader *this, unsigned __int16 a2, struct tagPROPVARIANT *a3)
{
  unsigned int v4; // r12d
  int Int32; // ebx
  OLECHAR *v7; // r13
  bool v8; // zf
  __int64 v9; // r8
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r14
  BSTR v14; // rax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  unsigned int v21; // r14d
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  _WORD *v24; // rdx
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  _BYTE *v29; // rdx
  __int64 v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  unsigned int k; // r14d
  unsigned int v37; // eax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  CallStackTracing *v48; // rcx
  struct CallStackContext *v49; // rax
  CallStackTracing *v50; // rcx
  struct CallStackContext *v51; // rax
  CallStackTracing *v52; // rcx
  struct CallStackContext *v53; // rax
  CallStackTracing *v54; // rcx
  struct CallStackContext *v55; // rax
  CallStackTracing *v56; // rcx
  struct CallStackContext *v57; // rax
  CallStackTracing *v58; // rcx
  struct CallStackContext *v59; // rax
  CallStackTracing *v60; // rcx
  struct CallStackContext *v61; // rax
  CallStackTracing *v62; // rcx
  struct CallStackContext *v63; // rax
  CallStackTracing *v64; // rcx
  struct CallStackContext *v65; // rax
  CallStackTracing *v66; // rcx
  struct CallStackContext *v67; // rax
  CallStackTracing *v68; // rcx
  struct CallStackContext *v69; // rax
  unsigned int j; // r14d
  _QWORD *v71; // rcx
  __int64 v72; // rdx
  CallStackTracing *v73; // rcx
  struct CallStackContext *v74; // rax
  CallStackTracing *v75; // rcx
  struct CallStackContext *v76; // rax
  CallStackTracing *v77; // rcx
  struct CallStackContext *v78; // rax
  CallStackTracing *v79; // rcx
  struct CallStackContext *v80; // rax
  unsigned int i; // r14d
  unsigned int v82; // r15d
  unsigned __int8 *v83; // rdx
  CallStackTracing *v84; // rcx
  struct CallStackContext *v85; // rax
  CallStackTracing *v86; // rcx
  struct CallStackContext *v87; // rax
  CallStackTracing *v88; // rcx
  struct CallStackContext *v89; // rax
  CallStackTracing *v90; // rcx
  struct CallStackContext *v91; // rax
  CallStackTracing *v92; // rcx
  struct CallStackContext *v93; // rax
  CallStackTracing *v94; // rcx
  struct CallStackContext *v95; // rax
  CallStackTracing *v96; // rcx
  struct CallStackContext *v97; // rax
  CallStackTracing *v98; // rcx
  struct CallStackContext *v99; // rax
  CallStackTracing *v100; // rcx
  struct CallStackContext *v101; // rax
  CallStackTracing *v102; // rcx
  struct CallStackContext *v103; // rax
  CallStackTracing *v104; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v106; // rcx
  struct CallStackContext *v107; // rax
  unsigned int v109; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v110; // [rsp+34h] [rbp-1Ch] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 *v112; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int8 *v113; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v114; // [rsp+A8h] [rbp+58h] BYREF

  v4 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v113, "CBinaryReader::ReadVariantValue", 952);
  v109 = 0;
  v114 = 0;
  pv = 0;
  v110 = 0;
  if ( !a3 )
  {
    Int32 = -2147024809;
    goto LABEL_485;
  }
  Int32 = 0;
  v7 = 0;
  if ( v4 > 0x40 )
  {
    if ( v4 > 0x1010 )
    {
      if ( v4 == 4113 )
      {
        Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
        if ( Int32 < 0 )
        {
          v104 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v104 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v104 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v104->m_fEnabled )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v104);
            if ( ThreadRelativeContext->m_result != Int32 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CBinaryReader::ReadVariantValue", 1079, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 63;
          goto LABEL_30;
        }
        Int32 = CBinaryReader::_AllocAndCopy(this, v114, (unsigned __int8 **)&pv);
        if ( Int32 < 0 )
        {
          v106 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v106 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v106 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v106->m_fEnabled )
          {
            v107 = CallStackTracing::GetThreadRelativeContext(v106);
            if ( v107->m_result != Int32 )
              CallStackContext::TraceFailure(v107, "CBinaryReader::ReadVariantValue", 1080, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 64;
          goto LABEL_30;
        }
      }
      else if ( v4 == 4114 )
      {
        Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
        if ( Int32 < 0 )
        {
          v100 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v100 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v100 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v100->m_fEnabled )
          {
            v101 = CallStackTracing::GetThreadRelativeContext(v100);
            if ( v101->m_result != Int32 )
              CallStackContext::TraceFailure(v101, "CBinaryReader::ReadVariantValue", 1093, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 67;
          goto LABEL_30;
        }
        Int32 = CBinaryReader::_AllocAndCopy(this, 2 * v114, (unsigned __int8 **)&pv);
        if ( Int32 < 0 )
        {
          v102 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v102 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v102 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v102->m_fEnabled )
          {
            v103 = CallStackTracing::GetThreadRelativeContext(v102);
            if ( v103->m_result != Int32 )
              CallStackContext::TraceFailure(v103, "CBinaryReader::ReadVariantValue", 1094, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 68;
          goto LABEL_30;
        }
      }
      else if ( v4 == 4115 )
      {
        Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
        if ( Int32 < 0 )
        {
          v96 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v96 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v96 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v96->m_fEnabled )
          {
            v97 = CallStackTracing::GetThreadRelativeContext(v96);
            if ( v97->m_result != Int32 )
              CallStackContext::TraceFailure(v97, "CBinaryReader::ReadVariantValue", 1107, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 71;
          goto LABEL_30;
        }
        Int32 = CBinaryReader::_AllocAndCopy(this, 4 * v114, (unsigned __int8 **)&pv);
        if ( Int32 < 0 )
        {
          v98 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v98 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v98 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v98->m_fEnabled )
          {
            v99 = CallStackTracing::GetThreadRelativeContext(v98);
            if ( v99->m_result != Int32 )
              CallStackContext::TraceFailure(v99, "CBinaryReader::ReadVariantValue", 1108, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 72;
          goto LABEL_30;
        }
      }
      else if ( v4 == 4116 )
      {
        Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
        if ( Int32 < 0 )
        {
          v92 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v92 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v92 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v92->m_fEnabled )
          {
            v93 = CallStackTracing::GetThreadRelativeContext(v92);
            if ( v93->m_result != Int32 )
              CallStackContext::TraceFailure(v93, "CBinaryReader::ReadVariantValue", 1114, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 73;
          goto LABEL_30;
        }
        Int32 = CBinaryReader::_AllocAndCopy(this, 8 * v114, (unsigned __int8 **)&pv);
        if ( Int32 < 0 )
        {
          v94 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v94 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v94 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v94->m_fEnabled )
          {
            v95 = CallStackTracing::GetThreadRelativeContext(v94);
            if ( v95->m_result != Int32 )
              CallStackContext::TraceFailure(v95, "CBinaryReader::ReadVariantValue", 1115, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 74;
          goto LABEL_30;
        }
      }
      else
      {
        if ( v4 != 4117 )
        {
          if ( v4 == 4127 )
          {
            Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
            if ( Int32 < 0 )
            {
              v77 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v77 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v77 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v77->m_fEnabled )
              {
                v78 = CallStackTracing::GetThreadRelativeContext(v77);
                if ( v78->m_result != Int32 )
                  CallStackContext::TraceFailure(v78, "CBinaryReader::ReadVariantValue", 1049, Int32);
              }
              if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                goto LABEL_481;
              v12 = 56;
              goto LABEL_30;
            }
            pv = CoTaskMemAlloc(8LL * v114);
            if ( pv )
            {
              for ( i = 0; ; ++i )
              {
                v37 = v114;
                if ( v114 <= i )
                  break;
                v113 = 0;
                Int32 = CBinaryReader::ReadInt32(this, (int *)&v109);
                if ( Int32 < 0 )
                {
                  v86 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v86 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v86 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v86->m_fEnabled )
                  {
                    v87 = CallStackTracing::GetThreadRelativeContext(v86);
                    if ( v87->m_result != Int32 )
                      CallStackContext::TraceFailure(v87, "CBinaryReader::ReadVariantValue", 1055, Int32);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v12 = 58;
                    goto LABEL_30;
                  }
                  goto LABEL_481;
                }
                v82 = v109 >> 1;
                Int32 = CBinaryReader::_AllocAndCopy(this, v109, &v113);
                if ( Int32 < 0 )
                {
                  v84 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v84 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v84 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v84->m_fEnabled )
                  {
                    v85 = CallStackTracing::GetThreadRelativeContext(v84);
                    if ( v85->m_result != Int32 )
                      CallStackContext::TraceFailure(v85, "CBinaryReader::ReadVariantValue", 1057, Int32);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v12 = 59;
                    goto LABEL_30;
                  }
                  goto LABEL_481;
                }
                v83 = v113;
                *((_QWORD *)pv + i) = v113;
                *(_WORD *)&v83[2 * v82 - 2] = 0;
              }
              goto LABEL_479;
            }
            v79 = CallStackTracing::s_wpInstance;
            Int32 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v79 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v79 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v79->m_fEnabled )
            {
              v80 = CallStackTracing::GetThreadRelativeContext(v79);
              if ( v80->m_result != -2147024882 )
                CallStackContext::TraceFailure(v80, "CBinaryReader::ReadVariantValue", 1051, -2147024882);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v35 = 57;
          }
          else
          {
            if ( v4 != 4161 )
              goto LABEL_485;
            Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
            if ( Int32 < 0 )
            {
              v66 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v66 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v66 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v66->m_fEnabled )
              {
                v67 = CallStackTracing::GetThreadRelativeContext(v66);
                if ( v67->m_result != Int32 )
                  CallStackContext::TraceFailure(v67, "CBinaryReader::ReadVariantValue", 1149, Int32);
              }
              if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                goto LABEL_481;
              v12 = 83;
              goto LABEL_30;
            }
            pv = CoTaskMemAlloc(16LL * v114);
            if ( pv )
            {
              for ( j = 0; ; ++j )
              {
                v37 = v114;
                if ( v114 <= j )
                  break;
                LODWORD(v113) = 0;
                v112 = 0;
                Int32 = CBinaryReader::ReadInt32(this, (int *)&v113);
                if ( Int32 < 0 )
                {
                  v75 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v75 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v75 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v75->m_fEnabled )
                  {
                    v76 = CallStackTracing::GetThreadRelativeContext(v75);
                    if ( v76->m_result != Int32 )
                      CallStackContext::TraceFailure(v76, "CBinaryReader::ReadVariantValue", 1156, Int32);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v12 = 85;
                    goto LABEL_30;
                  }
                  goto LABEL_481;
                }
                Int32 = CBinaryReader::_AllocAndCopy(this, (unsigned int)v113, &v112);
                if ( Int32 < 0 )
                {
                  v73 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v73 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v73 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v73->m_fEnabled )
                  {
                    v74 = CallStackTracing::GetThreadRelativeContext(v73);
                    if ( v74->m_result != Int32 )
                      CallStackContext::TraceFailure(v74, "CBinaryReader::ReadVariantValue", 1157, Int32);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v12 = 86;
                    goto LABEL_30;
                  }
                  goto LABEL_481;
                }
                v71 = pv;
                v72 = 2LL * j;
                *((_DWORD *)pv + 2 * v72) = (_DWORD)v113;
                v71[v72 + 1] = v112;
              }
              goto LABEL_479;
            }
            v68 = CallStackTracing::s_wpInstance;
            Int32 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v68 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v68 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v68->m_fEnabled )
            {
              v69 = CallStackTracing::GetThreadRelativeContext(v68);
              if ( v69->m_result != -2147024882 )
                CallStackContext::TraceFailure(v69, "CBinaryReader::ReadVariantValue", 1151, -2147024882);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v35 = 84;
          }
LABEL_139:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v35,
            &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids,
            this,
            -2147024882);
          goto LABEL_481;
        }
        Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
        if ( Int32 < 0 )
        {
          v88 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v88 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v88 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v88->m_fEnabled )
          {
            v89 = CallStackTracing::GetThreadRelativeContext(v88);
            if ( v89->m_result != Int32 )
              CallStackContext::TraceFailure(v89, "CBinaryReader::ReadVariantValue", 1121, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 75;
          goto LABEL_30;
        }
        Int32 = CBinaryReader::_AllocAndCopy(this, 8 * v114, (unsigned __int8 **)&pv);
        if ( Int32 < 0 )
        {
          v90 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v90 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v90 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v90->m_fEnabled )
          {
            v91 = CallStackTracing::GetThreadRelativeContext(v90);
            if ( v91->m_result != Int32 )
              CallStackContext::TraceFailure(v91, "CBinaryReader::ReadVariantValue", 1122, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 76;
          goto LABEL_30;
        }
      }
    }
    else
    {
      switch ( v4 )
      {
        case 0x1010u:
          Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
          if ( Int32 < 0 )
          {
            v62 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v62 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v62 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v62->m_fEnabled )
            {
              v63 = CallStackTracing::GetThreadRelativeContext(v62);
              if ( v63->m_result != Int32 )
                CallStackContext::TraceFailure(v63, "CBinaryReader::ReadVariantValue", 1072, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 61;
            goto LABEL_30;
          }
          Int32 = CBinaryReader::_AllocAndCopy(this, v114, (unsigned __int8 **)&pv);
          if ( Int32 < 0 )
          {
            v64 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v64 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v64 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v64->m_fEnabled )
            {
              v65 = CallStackTracing::GetThreadRelativeContext(v64);
              if ( v65->m_result != Int32 )
                CallStackContext::TraceFailure(v65, "CBinaryReader::ReadVariantValue", 1073, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 62;
            goto LABEL_30;
          }
          break;
        case 0x41u:
          Int32 = CBinaryReader::ReadInt32(this, (int *)&v110);
          if ( Int32 < 0 )
          {
            v58 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v58 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v58 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v58->m_fEnabled )
            {
              v59 = CallStackTracing::GetThreadRelativeContext(v58);
              if ( v59->m_result != Int32 )
                CallStackContext::TraceFailure(v59, "CBinaryReader::ReadVariantValue", 1142, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 81;
            goto LABEL_30;
          }
          Int32 = CBinaryReader::_AllocAndCopy(this, v110, (unsigned __int8 **)&pv);
          if ( Int32 < 0 )
          {
            v60 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v60 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v60 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v60->m_fEnabled )
            {
              v61 = CallStackTracing::GetThreadRelativeContext(v60);
              if ( v61->m_result != Int32 )
                CallStackContext::TraceFailure(v61, "CBinaryReader::ReadVariantValue", 1143, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 82;
            goto LABEL_30;
          }
          v37 = v110;
          goto LABEL_479;
        case 0x42u:
          goto LABEL_480;
        case 0x48u:
          Int32 = CBinaryReader::_AllocAndCopy(this, 0x10u, (unsigned __int8 **)&pv);
          if ( Int32 < 0 )
          {
            v56 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v56 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v56 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v56->m_fEnabled )
            {
              v57 = CallStackTracing::GetThreadRelativeContext(v56);
              if ( v57->m_result != Int32 )
                CallStackContext::TraceFailure(v57, "CBinaryReader::ReadVariantValue", 1067, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 60;
            goto LABEL_30;
          }
          a3->decVal.Lo64 = (unsigned __int64)pv;
LABEL_480:
          a3->vt = v4;
          if ( Int32 >= 0 )
            goto LABEL_485;
          goto LABEL_481;
        case 0x1002u:
          Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
          if ( Int32 < 0 )
          {
            v52 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v52 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v52 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v52->m_fEnabled )
            {
              v53 = CallStackTracing::GetThreadRelativeContext(v52);
              if ( v53->m_result != Int32 )
                CallStackContext::TraceFailure(v53, "CBinaryReader::ReadVariantValue", 1086, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 65;
            goto LABEL_30;
          }
          Int32 = CBinaryReader::_AllocAndCopy(this, 2 * v114, (unsigned __int8 **)&pv);
          if ( Int32 < 0 )
          {
            v54 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v54 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v54 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v54->m_fEnabled )
            {
              v55 = CallStackTracing::GetThreadRelativeContext(v54);
              if ( v55->m_result != Int32 )
                CallStackContext::TraceFailure(v55, "CBinaryReader::ReadVariantValue", 1087, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 66;
            goto LABEL_30;
          }
          break;
        case 0x1003u:
          Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
          if ( Int32 < 0 )
          {
            v48 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v48 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v48 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v48->m_fEnabled )
            {
              v49 = CallStackTracing::GetThreadRelativeContext(v48);
              if ( v49->m_result != Int32 )
                CallStackContext::TraceFailure(v49, "CBinaryReader::ReadVariantValue", 1100, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 69;
            goto LABEL_30;
          }
          Int32 = CBinaryReader::_AllocAndCopy(this, 4 * v114, (unsigned __int8 **)&pv);
          if ( Int32 < 0 )
          {
            v50 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v50 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v50 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v50->m_fEnabled )
            {
              v51 = CallStackTracing::GetThreadRelativeContext(v50);
              if ( v51->m_result != Int32 )
                CallStackContext::TraceFailure(v51, "CBinaryReader::ReadVariantValue", 1101, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 70;
            goto LABEL_30;
          }
          break;
        case 0x1004u:
          Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
          if ( Int32 < 0 )
          {
            v44 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v44 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v44 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v44->m_fEnabled )
            {
              v45 = CallStackTracing::GetThreadRelativeContext(v44);
              if ( v45->m_result != Int32 )
                CallStackContext::TraceFailure(v45, "CBinaryReader::ReadVariantValue", 1128, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 77;
            goto LABEL_30;
          }
          Int32 = CBinaryReader::_AllocAndCopy(this, 4 * v114, (unsigned __int8 **)&pv);
          if ( Int32 < 0 )
          {
            v46 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v46 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v46 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v46->m_fEnabled )
            {
              v47 = CallStackTracing::GetThreadRelativeContext(v46);
              if ( v47->m_result != Int32 )
                CallStackContext::TraceFailure(v47, "CBinaryReader::ReadVariantValue", 1129, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 78;
            goto LABEL_30;
          }
          break;
        case 0x1005u:
          Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
          if ( Int32 < 0 )
          {
            v40 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v40 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v40 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v40->m_fEnabled )
            {
              v41 = CallStackTracing::GetThreadRelativeContext(v40);
              if ( v41->m_result != Int32 )
                CallStackContext::TraceFailure(v41, "CBinaryReader::ReadVariantValue", 1135, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 79;
            goto LABEL_30;
          }
          Int32 = CBinaryReader::_AllocAndCopy(this, 8 * v114, (unsigned __int8 **)&pv);
          if ( Int32 < 0 )
          {
            v42 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v42 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v42 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v42->m_fEnabled )
            {
              v43 = CallStackTracing::GetThreadRelativeContext(v42);
              if ( v43->m_result != Int32 )
                CallStackContext::TraceFailure(v43, "CBinaryReader::ReadVariantValue", 1136, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 80;
            goto LABEL_30;
          }
          break;
        case 0x100Cu:
          Int32 = CBinaryReader::ReadInt32(this, (int *)&v114);
          if ( Int32 < 0 )
          {
            v31 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v31 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v31 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v31->m_fEnabled )
            {
              v32 = CallStackTracing::GetThreadRelativeContext(v31);
              if ( v32->m_result != Int32 )
                CallStackContext::TraceFailure(v32, "CBinaryReader::ReadVariantValue", 1166, Int32);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v12 = 87;
            goto LABEL_30;
          }
          pv = CoTaskMemAlloc(24LL * v114);
          if ( !pv )
          {
            v33 = CallStackTracing::s_wpInstance;
            Int32 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v33 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v33 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v33->m_fEnabled )
            {
              v34 = CallStackTracing::GetThreadRelativeContext(v33);
              if ( v34->m_result != -2147024882 )
                CallStackContext::TraceFailure(v34, "CBinaryReader::ReadVariantValue", 1168, -2147024882);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_481;
            v35 = 88;
            goto LABEL_139;
          }
          for ( k = 0; ; ++k )
          {
            v37 = v114;
            if ( v114 <= k )
              break;
            Int32 = CBinaryReader::ReadVariant(this, (struct tagPROPVARIANT *)pv + k);
            if ( Int32 < 0 )
            {
              v38 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v38 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v38 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v38->m_fEnabled )
              {
                v39 = CallStackTracing::GetThreadRelativeContext(v38);
                if ( v39->m_result != Int32 )
                  CallStackContext::TraceFailure(v39, "CBinaryReader::ReadVariantValue", 1171, Int32);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v12 = 89;
                goto LABEL_30;
              }
              goto LABEL_481;
            }
          }
LABEL_479:
          a3->decVal.Lo32 = v37;
          a3->bstrblobVal.pData = (unsigned __int8 *)pv;
          goto LABEL_480;
        default:
          goto LABEL_485;
      }
    }
    v37 = v114;
    goto LABEL_479;
  }
  if ( v4 == 64 )
    goto LABEL_15;
  if ( v4 > 0xB )
  {
    if ( v4 <= 0x15 )
    {
      if ( v4 != 21 )
      {
        switch ( v4 )
        {
          case 0x10u:
          case 0x11u:
            v9 = 1;
            goto LABEL_62;
          case 0x12u:
            goto LABEL_52;
          case 0x13u:
            goto LABEL_14;
        }
        if ( v4 != 20 )
          goto LABEL_485;
      }
      goto LABEL_15;
    }
    switch ( v4 )
    {
      case 0x16u:
      case 0x17u:
        goto LABEL_14;
      case 0x1Eu:
        Int32 = CBinaryReader::ReadInt32(this, (int *)&v109);
        if ( Int32 < 0 )
        {
          v25 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v25 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v25->m_fEnabled )
          {
            v26 = CallStackTracing::GetThreadRelativeContext(v25);
            if ( v26->m_result != Int32 )
              CallStackContext::TraceFailure(v26, "CBinaryReader::ReadVariantValue", 1034, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 52;
          goto LABEL_30;
        }
        Int32 = CBinaryReader::_AllocAndCopy(this, v109, (unsigned __int8 **)&pv);
        if ( Int32 < 0 )
        {
          v27 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v27 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v27 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v27->m_fEnabled )
          {
            v28 = CallStackTracing::GetThreadRelativeContext(v27);
            if ( v28->m_result != Int32 )
              CallStackContext::TraceFailure(v28, "CBinaryReader::ReadVariantValue", 1035, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 53;
          goto LABEL_30;
        }
        v29 = pv;
        v30 = v109 - 1;
        a3->decVal.Lo64 = (unsigned __int64)pv;
        v29[v30] = 0;
        break;
      case 0x1Fu:
        Int32 = CBinaryReader::ReadInt32(this, (int *)&v109);
        if ( Int32 < 0 )
        {
          v19 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v19 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v19 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v19->m_fEnabled )
          {
            v20 = CallStackTracing::GetThreadRelativeContext(v19);
            if ( v20->m_result != Int32 )
              CallStackContext::TraceFailure(v20, "CBinaryReader::ReadVariantValue", 1041, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 54;
          goto LABEL_30;
        }
        v21 = v109 >> 1;
        Int32 = CBinaryReader::_AllocAndCopy(this, v109, (unsigned __int8 **)&pv);
        if ( Int32 < 0 )
        {
          v22 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v22 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v22->m_fEnabled )
          {
            v23 = CallStackTracing::GetThreadRelativeContext(v22);
            if ( v23->m_result != Int32 )
              CallStackContext::TraceFailure(v23, "CBinaryReader::ReadVariantValue", 1043, Int32);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_481;
          v12 = 55;
          goto LABEL_30;
        }
        v24 = pv;
        a3->decVal.Lo64 = (unsigned __int64)pv;
        v24[v21 - 1] = 0;
        break;
      default:
        goto LABEL_485;
    }
    goto LABEL_480;
  }
  if ( v4 == 11 )
    goto LABEL_52;
  if ( v4 <= 5 )
  {
    if ( v4 != 5 )
    {
      if ( v4 < 2 )
        goto LABEL_480;
      if ( v4 != 2 )
      {
        if ( v4 != 3 )
        {
          v8 = v4 == 4;
          goto LABEL_13;
        }
LABEL_14:
        v9 = 4;
LABEL_62:
        Int32 = (**(__int64 (__fastcall ***)(CBinaryReader *, int *, __int64))this)(this, &a3->lVal, v9);
        goto LABEL_480;
      }
LABEL_52:
      v9 = 2;
      goto LABEL_62;
    }
LABEL_15:
    v9 = 8;
    goto LABEL_62;
  }
  if ( v4 == 6 || v4 == 7 )
    goto LABEL_15;
  if ( v4 != 8 )
  {
    v8 = v4 == 10;
LABEL_13:
    if ( !v8 )
      goto LABEL_485;
    goto LABEL_14;
  }
  Int32 = CBinaryReader::ReadInt32(this, (int *)&v109);
  if ( Int32 < 0 )
  {
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v10 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v10->m_fEnabled )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( v11->m_result != Int32 )
        CallStackContext::TraceFailure(v11, "CBinaryReader::ReadVariantValue", 1011, Int32);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_481;
    v12 = 49;
    goto LABEL_30;
  }
  v13 = v109 >> 1;
  v14 = SysAllocStringLen(0, v109 >> 1);
  v7 = v14;
  if ( v14 )
  {
    Int32 = (**(__int64 (__fastcall ***)(CBinaryReader *, BSTR, _QWORD))this)(this, v14, v109);
    if ( Int32 >= 0 )
    {
      a3->decVal.Lo64 = (unsigned __int64)v7;
      v7[v13] = 0;
      goto LABEL_480;
    }
    v17 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v17 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v17->m_fEnabled )
    {
      v18 = CallStackTracing::GetThreadRelativeContext(v17);
      if ( v18->m_result != Int32 )
        CallStackContext::TraceFailure(v18, "CBinaryReader::ReadVariantValue", 1016, Int32);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
LABEL_481:
      if ( pv )
        CoTaskMemFree(pv);
      if ( v7 )
        SysFreeString(v7);
      goto LABEL_485;
    }
    v12 = 51;
LABEL_30:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids, this, Int32);
    goto LABEL_481;
  }
  v15 = CallStackTracing::s_wpInstance;
  Int32 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v15 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v15->m_fEnabled )
  {
    v16 = CallStackTracing::GetThreadRelativeContext(v15);
    if ( v16->m_result != -2147024882 )
      CallStackContext::TraceFailure(v16, "CBinaryReader::ReadVariantValue", 1014, -2147024882);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids,
      this,
      -2147024882);
LABEL_485:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v113);
  return (unsigned int)Int32;
}

```

## disassembly

```asm
0x180105110  mov     [rsp-38h+arg_0], rbx
0x180105115  push    rbp
0x180105116  push    rsi
0x180105117  push    rdi
0x180105118  push    r12
0x18010511a  push    r13
0x18010511c  push    r14
0x18010511e  push    r15
0x180105120  mov     rbp, rsp
0x180105123  sub     rsp, 50h
0x180105127  mov     rsi, r8
0x18010512a  movzx   r12d, dx
0x18010512e  mov     rdi, rcx
0x180105131  lea     r14, aCbinaryreaderR_1; "CBinaryReader::ReadVariantValue"
0x180105138  mov     rdx, r14; char *
0x18010513b  lea     rcx, [rbp+arg_10]; this
0x18010513f  mov     r8d, 3B8h; int
0x180105145  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18010514a  xor     r15d, r15d
0x18010514d  mov     [rbp+var_20], r15d
0x180105151  mov     [rbp+arg_18], r15d
0x180105155  mov     [rbp+pv], r15
0x180105159  mov     [rbp+var_1C], r15d
0x18010515d  test    rsi, rsi
0x180105160  jnz     short loc_18010516C
0x180105162  mov     ebx, 80070057h
0x180105167  jmp     loc_180106E44
0x18010516c  mov     ebx, r15d
0x18010516f  mov     r13, r15
0x180105172  mov     ecx, r12d
0x180105175  cmp     r12d, 40h ; '@'
0x180105179  ja      loc_180105744
0x18010517f  jz      short loc_1801051CA
0x180105181  cmp     ecx, 0Bh
0x180105184  ja      loc_18010541C
0x18010518a  jz      loc_180105414
0x180105190  cmp     ecx, 5
0x180105193  ja      short loc_1801051D5
0x180105195  jz      short loc_1801051CA
0x180105197  test    ecx, ecx
0x180105199  jz      loc_180106E1C
0x18010519f  sub     ecx, 1
0x1801051a2  jz      loc_180106E1C
0x1801051a8  sub     ecx, 1
0x1801051ab  jz      loc_180105414
0x1801051b1  sub     ecx, 1
0x1801051b4  jz      short loc_1801051BF
0x1801051b6  cmp     ecx, 1
0x1801051b9  jnz     loc_180106E44
0x1801051bf  mov     r8d, 4
0x1801051c5  jmp     loc_180105453
0x1801051ca  mov     r8d, 8
0x1801051d0  jmp     loc_180105453
0x1801051d5  sub     ecx, 6
0x1801051d8  jz      short loc_1801051CA
0x1801051da  sub     ecx, 1
0x1801051dd  jz      short loc_1801051CA
0x1801051df  sub     ecx, 1
0x1801051e2  jz      short loc_1801051E9
0x1801051e4  cmp     ecx, 2
0x1801051e7  jmp     short loc_1801051B9
0x1801051e9  lea     rdx, [rbp+var_20]; int *
0x1801051ed  mov     rcx, rdi; this
0x1801051f0  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1801051f5  mov     ebx, eax
0x1801051f7  test    eax, eax
0x1801051f9  jns     loc_18010528B
0x1801051ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180105206  test    rcx, rcx
0x180105209  jnz     short loc_180105249
0x18010520b  mov     rax, cs:stru_1801FC290.__vftable
0x180105212  lea     rcx, stru_1801FC290
0x180105219  mov     edx, 7F0h
0x18010521e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180105225  mov     rax, [rax+8]
0x180105229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010522e  test    eax, eax
0x180105230  jnz     short loc_180105242
0x180105232  lea     rcx, stru_1801F8A30
0x180105239  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180105240  jmp     short loc_180105249
0x180105242  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180105249  cmp     [rcx+8], r15b
0x18010524d  jz      short loc_180105270
0x18010524f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180105254  cmp     [rax+7CCh], ebx
0x18010525a  jz      short loc_180105270
0x18010525c  mov     r9d, ebx; int
0x18010525f  mov     r8d, 3F3h; int
0x180105265  mov     rdx, r14; char *
0x180105268  mov     rcx, rax; this
0x18010526b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180105270  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180105277  jb      loc_180106E24
0x18010527d  mov     edx, 31h ; '1'
0x180105282  mov     [rsp+50h+var_30], ebx
0x180105286  jmp     loc_1801058EC
0x18010528b  mov     r14d, [rbp+var_20]
0x18010528f  xor     ecx, ecx; strIn
0x180105291  shr     r14d, 1
0x180105294  mov     edx, r14d; ui
0x180105297  call    cs:__imp_SysAllocStringLen
0x18010529d  mov     r13, rax
0x1801052a0  test    rax, rax
0x1801052a3  jnz     loc_18010535A
0x1801052a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801052b0  mov     esi, 8007000Eh
0x1801052b5  mov     ebx, esi
0x1801052b7  test    rcx, rcx
0x1801052ba  jnz     short loc_1801052FA
0x1801052bc  mov     rax, cs:stru_1801FC290.__vftable
0x1801052c3  lea     rcx, stru_1801FC290
0x1801052ca  mov     edx, 7F0h
0x1801052cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801052d6  mov     rax, [rax+8]
0x1801052da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801052df  test    eax, eax
0x1801052e1  jnz     short loc_1801052F3
0x1801052e3  lea     rcx, stru_1801F8A30
0x1801052ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801052f1  jmp     short loc_1801052FA
0x1801052f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801052fa  cmp     [rcx+8], r15b
0x1801052fe  jz      short loc_180105325
0x180105300  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180105305  cmp     [rax+7CCh], esi
0x18010530b  jz      short loc_180105325
0x18010530d  mov     r9d, esi; int
0x180105310  lea     rdx, aCbinaryreaderR_1; "CBinaryReader::ReadVariantValue"
0x180105317  mov     r8d, 3F6h; int
0x18010531d  mov     rcx, rax; this
0x180105320  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180105325  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010532c  jb      loc_180106E44
0x180105332  mov     rcx, cs:WPP_GLOBAL_Control
0x180105339  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x180105340  mov     edx, 32h ; '2'
0x180105345  mov     [rsp+50h+var_30], esi
0x180105349  mov     r9, rdi
0x18010534c  mov     rcx, [rcx+10h]
0x180105350  call    WPP_SF_qD
0x180105355  jmp     loc_180106E44
0x18010535a  mov     rax, [rdi]
0x18010535d  mov     rdx, r13
0x180105360  mov     r8d, [rbp+var_20]
0x180105364  mov     rcx, rdi
0x180105367  mov     rax, [rax]
0x18010536a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010536f  mov     ebx, eax
0x180105371  test    eax, eax
0x180105373  jns     loc_180105405
0x180105379  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180105380  test    rcx, rcx
0x180105383  jnz     short loc_1801053C3
0x180105385  mov     rax, cs:stru_1801FC290.__vftable
0x18010538c  lea     rcx, stru_1801FC290
0x180105393  mov     edx, 7F0h
0x180105398  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010539f  mov     rax, [rax+8]
0x1801053a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801053a8  test    eax, eax
0x1801053aa  jnz     short loc_1801053BC
0x1801053ac  lea     rcx, stru_1801F8A30
0x1801053b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801053ba  jmp     short loc_1801053C3
0x1801053bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801053c3  cmp     [rcx+8], r15b
0x1801053c7  jz      short loc_1801053EE
0x1801053c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801053ce  cmp     [rax+7CCh], ebx
0x1801053d4  jz      short loc_1801053EE
0x1801053d6  mov     r9d, ebx; int
0x1801053d9  lea     rdx, aCbinaryreaderR_1; "CBinaryReader::ReadVariantValue"
0x1801053e0  mov     r8d, 3F8h; int
0x1801053e6  mov     rcx, rax; this
0x1801053e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801053ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801053f5  jb      loc_180106E24
0x1801053fb  mov     edx, 33h ; '3'
0x180105400  jmp     loc_180105282
0x180105405  mov     [rsi+8], r13
0x180105409  mov     [r13+r14*2+0], r15w
0x18010540f  jmp     loc_180106E1C
0x180105414  mov     r8d, 2
0x18010541a  jmp     short loc_180105453
0x18010541c  cmp     ecx, 15h
0x18010541f  ja      short loc_18010546C
0x180105421  jz      loc_1801051CA
0x180105427  sub     ecx, 10h
0x18010542a  jz      short loc_18010544D
0x18010542c  sub     ecx, 1
0x18010542f  jz      short loc_18010544D
0x180105431  sub     ecx, 1
0x180105434  jz      short loc_180105414
0x180105436  sub     ecx, 1
0x180105439  jz      loc_1801051BF
0x18010543f  cmp     ecx, 1
0x180105442  jz      loc_1801051CA
0x180105448  jmp     loc_180106E44
0x18010544d  mov     r8d, 1
0x180105453  mov     rax, [rdi]
0x180105456  lea     rdx, [rsi+8]
0x18010545a  mov     rcx, rdi
0x18010545d  mov     rax, [rax]
0x180105460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105465  mov     ebx, eax
0x180105467  jmp     loc_180106E1C
0x18010546c  sub     ecx, 16h
0x18010546f  jz      loc_1801051BF
0x180105475  sub     ecx, 1
0x180105478  jz      loc_1801051BF
0x18010547e  sub     ecx, 7
0x180105481  jz      loc_1801055EF
0x180105487  cmp     ecx, 1
0x18010548a  jnz     loc_180106E44
0x180105490  lea     rdx, [rbp+var_20]; int *
0x180105494  mov     rcx, rdi; this
0x180105497  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x18010549c  mov     ebx, eax
0x18010549e  test    eax, eax
0x1801054a0  jns     loc_18010552E
0x1801054a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801054ad  test    rcx, rcx
0x1801054b0  jnz     short loc_1801054F0
0x1801054b2  mov     rax, cs:stru_1801FC290.__vftable
0x1801054b9  lea     rcx, stru_1801FC290
0x1801054c0  mov     edx, 7F0h
0x1801054c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801054cc  mov     rax, [rax+8]
0x1801054d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801054d5  test    eax, eax
0x1801054d7  jnz     short loc_1801054E9
0x1801054d9  lea     rcx, stru_1801F8A30
0x1801054e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801054e7  jmp     short loc_1801054F0
0x1801054e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801054f0  cmp     [rcx+8], r15b
0x1801054f4  jz      short loc_180105517
0x1801054f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801054fb  cmp     [rax+7CCh], ebx
0x180105501  jz      short loc_180105517
0x180105503  mov     r9d, ebx; int
0x180105506  mov     r8d, 411h; int
0x18010550c  mov     rdx, r14; char *
0x18010550f  mov     rcx, rax; this
0x180105512  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180105517  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010551e  jb      loc_180106E24
0x180105524  mov     edx, 36h ; '6'
0x180105529  jmp     loc_180105282
0x18010552e  mov     edx, [rbp+var_20]; unsigned int
0x180105531  lea     r8, [rbp+pv]; unsigned __int8 **
0x180105535  mov     r14d, edx
0x180105538  mov     rcx, rdi; this
0x18010553b  shr     r14d, 1
0x18010553e  call    ?_AllocAndCopy@CBinaryReader@@IEAAJKPEAPEAE@Z; CBinaryReader::_AllocAndCopy(ulong,uchar * *)
0x180105543  mov     ebx, eax
0x180105545  test    eax, eax
0x180105547  jns     loc_1801055D9
0x18010554d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180105554  test    rcx, rcx
0x180105557  jnz     short loc_180105597
0x180105559  mov     rax, cs:stru_1801FC290.__vftable
0x180105560  lea     rcx, stru_1801FC290
0x180105567  mov     edx, 7F0h
0x18010556c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180105573  mov     rax, [rax+8]
0x180105577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010557c  test    eax, eax
0x18010557e  jnz     short loc_180105590
0x180105580  lea     rcx, stru_1801F8A30
0x180105587  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010558e  jmp     short loc_180105597
0x180105590  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180105597  cmp     [rcx+8], r15b
0x18010559b  jz      short loc_1801055C2
0x18010559d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801055a2  cmp     [rax+7CCh], ebx
0x1801055a8  jz      short loc_1801055C2
0x1801055aa  mov     r9d, ebx; int
0x1801055ad  lea     rdx, aCbinaryreaderR_1; "CBinaryReader::ReadVariantValue"
0x1801055b4  mov     r8d, 413h; int
0x1801055ba  mov     rcx, rax; this
0x1801055bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801055c2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801055c9  jb      loc_180106E24
0x1801055cf  mov     edx, 37h ; '7'
0x1801055d4  jmp     loc_180105282
0x1801055d9  mov     rdx, [rbp+pv]
0x1801055dd  lea     eax, [r14-1]
0x1801055e1  mov     [rsi+8], rdx
0x1801055e5  mov     [rdx+rax*2], r15w
0x1801055ea  jmp     loc_180106E1C
0x1801055ef  lea     rdx, [rbp+var_20]; int *
0x1801055f3  mov     rcx, rdi; this
0x1801055f6  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1801055fb  mov     ebx, eax
0x1801055fd  test    eax, eax
0x1801055ff  jns     loc_18010568D
0x180105605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
