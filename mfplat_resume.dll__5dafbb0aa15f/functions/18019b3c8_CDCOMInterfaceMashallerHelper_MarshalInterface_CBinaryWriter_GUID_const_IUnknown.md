# CDCOMInterfaceMashallerHelper::MarshalInterface(CBinaryWriter &,_GUID const &,IUnknown *)

- ea: `0x18019b3c8`
- end: `0x18019b946`
- name: `?MarshalInterface@CDCOMInterfaceMashallerHelper@@SAJAEAVCBinaryWriter@@AEBU_GUID@@PEAUIUnknown@@@Z`
- size: `1406`
- prototype: `__int64 __fastcall(struct CBinaryWriter *this, IID *riid, LPUNKNOWN pUnk)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800bba7c`
- `0x1800e6d98`
- `0x18010b020`

## callees

- `0x180015b20`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1801200d0`
- `0x180120ecc`
- `0x18019b3c8`
- `0x18019bf58`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18019b909`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18019b909`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18019b8ff`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18019b8ff`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18019b6ff`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18019b6ff`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18019b437`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18019b437`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18019b5b1`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18019b5b1`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18019b50e`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18019b50e`

## string_xrefs

- `0x18019b416`: `CDCOMInterfaceMashallerHelper::MarshalInterface`

## pseudocode

```c
__int64 __fastcall CDCOMInterfaceMashallerHelper::MarshalInterface(
        struct CBinaryWriter *this,
        IID *riid,
        LPUNKNOWN pUnk)
{
  HRESULT HGlobalFromStream; // ebx
  CallStackTracing *v7; // rcx
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  LPVOID v16; // rdi
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackScopeTrace v24; // [rsp+30h] [rbp-49h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-41h] BYREF
  HGLOBAL phglobal; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v27[16]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v28; // [rsp+60h] [rbp-19h]

  ppstm = 0;
  phglobal = 0;
  memset_0(v27, 0, 0x50u);
  CallStackScopeTrace::CallStackScopeTrace(&v24, "CDCOMInterfaceMashallerHelper::MarshalInterface", 1240);
  HGlobalFromStream = CreateStreamOnHGlobal(0, 0, &ppstm);
  if ( HGlobalFromStream >= 0 )
  {
    HGlobalFromStream = CoMarshalInterface(ppstm, riid, pUnk, 0, 0, 0);
    if ( HGlobalFromStream >= 0 )
    {
      HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
      if ( HGlobalFromStream >= 0 )
      {
        HGlobalFromStream = ppstm->Stat(ppstm, (tagSTATSTG *)v27, 1u);
        if ( HGlobalFromStream >= 0 )
        {
          v16 = GlobalLock(phglobal);
          if ( v16 )
          {
            if ( v28 )
            {
              HGlobalFromStream = CBinaryWriter::WriteInt64(this, v28);
              if ( HGlobalFromStream >= 0 )
              {
                HGlobalFromStream = (**(__int64 (__fastcall ***)(struct CBinaryWriter *, LPVOID, _QWORD))this)(
                                      this,
                                      v16,
                                      (unsigned int)v28);
                if ( HGlobalFromStream < 0 )
                {
                  v21 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v21 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v21 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v21->m_fEnabled )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v21);
                    if ( ThreadRelativeContext->m_result != HGlobalFromStream )
                      CallStackContext::TraceFailure(
                        ThreadRelativeContext,
                        "CDCOMInterfaceMashallerHelper::MarshalInterface",
                        1260,
                        HGlobalFromStream);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v9 = 98;
                    goto LABEL_11;
                  }
                }
              }
              else
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
                  if ( v20->m_result != HGlobalFromStream )
                    CallStackContext::TraceFailure(
                      v20,
                      "CDCOMInterfaceMashallerHelper::MarshalInterface",
                      1259,
                      HGlobalFromStream);
                }
                if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                {
                  v9 = 97;
                  goto LABEL_11;
                }
              }
            }
            else
            {
              HGlobalFromStream = -2147418113;
            }
          }
          else
          {
            v17 = CallStackTracing::s_wpInstance;
            HGlobalFromStream = -2147418113;
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
              if ( v18->m_result != -2147418113 )
                CallStackContext::TraceFailure(
                  v18,
                  "CDCOMInterfaceMashallerHelper::MarshalInterface",
                  1255,
                  -2147418113);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v9 = 96;
              goto LABEL_11;
            }
          }
        }
        else
        {
          v14 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v14 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v14 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v14->m_fEnabled )
          {
            v15 = CallStackTracing::GetThreadRelativeContext(v14);
            if ( v15->m_result != HGlobalFromStream )
              CallStackContext::TraceFailure(
                v15,
                "CDCOMInterfaceMashallerHelper::MarshalInterface",
                1252,
                HGlobalFromStream);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v9 = 95;
            goto LABEL_11;
          }
        }
      }
      else
      {
        v12 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v12 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v12->m_fEnabled )
        {
          v13 = CallStackTracing::GetThreadRelativeContext(v12);
          if ( v13->m_result != HGlobalFromStream )
            CallStackContext::TraceFailure(
              v13,
              "CDCOMInterfaceMashallerHelper::MarshalInterface",
              1250,
              HGlobalFromStream);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v9 = 94;
          goto LABEL_11;
        }
      }
    }
    else
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
        if ( v11->m_result != HGlobalFromStream )
          CallStackContext::TraceFailure(
            v11,
            "CDCOMInterfaceMashallerHelper::MarshalInterface",
            1245,
            HGlobalFromStream);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v9 = 93;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v7->m_fEnabled )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( v8->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(v8, "CDCOMInterfaceMashallerHelper::MarshalInterface", 1240, HGlobalFromStream);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v9 = 92;
LABEL_11:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids,
        0,
        HGlobalFromStream);
    }
  }
  if ( phglobal )
  {
    GlobalUnlock(phglobal);
    GlobalFree(phglobal);
  }
  CallStackScopeTrace::~CallStackScopeTrace(&v24);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppstm);
  return (unsigned int)HGlobalFromStream;
}

```

## disassembly

```asm
0x18019b3c8  mov     [rsp-8+arg_18], rbx
0x18019b3cd  push    rbp
0x18019b3ce  push    rsi
0x18019b3cf  push    rdi
0x18019b3d0  push    r12
0x18019b3d2  push    r14
0x18019b3d4  lea     rbp, [rsp-37h]
0x18019b3d9  sub     rsp, 0B0h
0x18019b3e0  mov     rax, cs:__security_cookie
0x18019b3e7  xor     rax, rsp
0x18019b3ea  mov     [rbp+57h+var_30], rax
0x18019b3ee  mov     rdi, rdx
0x18019b3f1  mov     [rbp+57h+ppstm], 0
0x18019b3f9  xor     edx, edx; Val
0x18019b3fb  mov     [rbp+57h+phglobal], 0
0x18019b403  mov     r14, r8
0x18019b406  mov     rsi, rcx
0x18019b409  lea     rcx, [rbp+57h+var_80]; void *
0x18019b40d  lea     r8d, [rdx+50h]; Size
0x18019b411  call    memset_0
0x18019b416  lea     r12, aCdcominterface_0; "CDCOMInterfaceMashallerHelper::MarshalI"...
0x18019b41d  mov     r8d, 4D8h; int
0x18019b423  mov     rdx, r12; char *
0x18019b426  lea     rcx, [rbp+57h+var_A0]; this
0x18019b42a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18019b42f  lea     r8, [rbp+57h+ppstm]; ppstm
0x18019b433  xor     edx, edx; fDeleteOnRelease
0x18019b435  xor     ecx, ecx; hGlobal
0x18019b437  call    cs:__imp_CreateStreamOnHGlobal
0x18019b43d  mov     ebx, eax
0x18019b43f  test    eax, eax
0x18019b441  jns     loc_18019B4F0
0x18019b447  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b44e  test    rcx, rcx
0x18019b451  jnz     short loc_18019B494
0x18019b453  mov     rcx, cs:stru_1801FC290.__vftable
0x18019b45a  lea     r8, stru_1801FC290
0x18019b461  mov     edx, 7F0h
0x18019b466  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b46d  mov     rax, [rcx+8]
0x18019b471  mov     rcx, r8
0x18019b474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b479  test    eax, eax
0x18019b47b  jnz     short loc_18019B48D
0x18019b47d  lea     rcx, stru_1801F8A30
0x18019b484  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b48b  jmp     short loc_18019B494
0x18019b48d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019b494  cmp     byte ptr [rcx+8], 0
0x18019b498  jz      short loc_18019B4BB
0x18019b49a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019b49f  cmp     [rax+7CCh], ebx
0x18019b4a5  jz      short loc_18019B4BB
0x18019b4a7  mov     r9d, ebx; int
0x18019b4aa  mov     r8d, 4D8h; int
0x18019b4b0  mov     rdx, r12; char *
0x18019b4b3  mov     rcx, rax; this
0x18019b4b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019b4bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019b4c2  jb      loc_18019B8F6
0x18019b4c8  mov     edx, 5Ch ; '\'
0x18019b4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18019b4d4  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x18019b4db  xor     r9d, r9d
0x18019b4de  mov     dword ptr [rsp+0D0h+pvDestContext], ebx
0x18019b4e2  mov     rcx, [rcx+10h]
0x18019b4e6  call    WPP_SF_qD
0x18019b4eb  jmp     loc_18019B8F6
0x18019b4f0  mov     rcx, [rbp+57h+ppstm]; pStm
0x18019b4f4  xor     r9d, r9d; dwDestContext
0x18019b4f7  mov     [rsp+0D0h+mshlflags], 0; mshlflags
0x18019b4ff  mov     r8, r14; pUnk
0x18019b502  mov     rdx, rdi; riid
0x18019b505  mov     [rsp+0D0h+pvDestContext], 0; pvDestContext
0x18019b50e  call    cs:__imp_CoMarshalInterface
0x18019b514  mov     ebx, eax
0x18019b516  test    eax, eax
0x18019b518  jns     loc_18019B5A9
0x18019b51e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b525  test    rcx, rcx
0x18019b528  jnz     short loc_18019B56B
0x18019b52a  mov     rax, cs:stru_1801FC290.__vftable
0x18019b531  lea     r8, stru_1801FC290
0x18019b538  mov     edx, 7F0h
0x18019b53d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b544  mov     rcx, r8
0x18019b547  mov     rax, [rax+8]
0x18019b54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b550  test    eax, eax
0x18019b552  jnz     short loc_18019B564
0x18019b554  lea     rcx, stru_1801F8A30
0x18019b55b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b562  jmp     short loc_18019B56B
0x18019b564  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019b56b  cmp     byte ptr [rcx+8], 0
0x18019b56f  jz      short loc_18019B592
0x18019b571  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019b576  cmp     [rax+7CCh], ebx
0x18019b57c  jz      short loc_18019B592
0x18019b57e  mov     r9d, ebx; int
0x18019b581  mov     r8d, 4DDh; int
0x18019b587  mov     rdx, r12; char *
0x18019b58a  mov     rcx, rax; this
0x18019b58d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019b592  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019b599  jb      loc_18019B8F6
0x18019b59f  mov     edx, 5Dh ; ']'
0x18019b5a4  jmp     loc_18019B4CD
0x18019b5a9  mov     rcx, [rbp+57h+ppstm]; pstm
0x18019b5ad  lea     rdx, [rbp+57h+phglobal]; phglobal
0x18019b5b1  call    cs:__imp_GetHGlobalFromStream
0x18019b5b7  mov     ebx, eax
0x18019b5b9  test    eax, eax
0x18019b5bb  jns     loc_18019B64C
0x18019b5c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b5c8  test    rcx, rcx
0x18019b5cb  jnz     short loc_18019B60E
0x18019b5cd  mov     rax, cs:stru_1801FC290.__vftable
0x18019b5d4  lea     r8, stru_1801FC290
0x18019b5db  mov     edx, 7F0h
0x18019b5e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b5e7  mov     rcx, r8
0x18019b5ea  mov     rax, [rax+8]
0x18019b5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b5f3  test    eax, eax
0x18019b5f5  jnz     short loc_18019B607
0x18019b5f7  lea     rcx, stru_1801F8A30
0x18019b5fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b605  jmp     short loc_18019B60E
0x18019b607  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019b60e  cmp     byte ptr [rcx+8], 0
0x18019b612  jz      short loc_18019B635
0x18019b614  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019b619  cmp     [rax+7CCh], ebx
0x18019b61f  jz      short loc_18019B635
0x18019b621  mov     r9d, ebx; int
0x18019b624  mov     r8d, 4E2h; int
0x18019b62a  mov     rdx, r12; char *
0x18019b62d  mov     rcx, rax; this
0x18019b630  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019b635  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019b63c  jb      loc_18019B8F6
0x18019b642  mov     edx, 5Eh ; '^'
0x18019b647  jmp     loc_18019B4CD
0x18019b64c  mov     rcx, [rbp+57h+ppstm]
0x18019b650  lea     rdx, [rbp+57h+var_80]
0x18019b654  mov     r8d, 1
0x18019b65a  mov     rax, [rcx]
0x18019b65d  mov     rax, [rax+60h]
0x18019b661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b666  mov     ebx, eax
0x18019b668  test    eax, eax
0x18019b66a  jns     loc_18019B6FB
0x18019b670  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b677  test    rcx, rcx
0x18019b67a  jnz     short loc_18019B6BD
0x18019b67c  mov     rax, cs:stru_1801FC290.__vftable
0x18019b683  lea     r8, stru_1801FC290
0x18019b68a  mov     edx, 7F0h
0x18019b68f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b696  mov     rcx, r8
0x18019b699  mov     rax, [rax+8]
0x18019b69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b6a2  test    eax, eax
0x18019b6a4  jnz     short loc_18019B6B6
0x18019b6a6  lea     rcx, stru_1801F8A30
0x18019b6ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b6b4  jmp     short loc_18019B6BD
0x18019b6b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019b6bd  cmp     byte ptr [rcx+8], 0
0x18019b6c1  jz      short loc_18019B6E4
0x18019b6c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019b6c8  cmp     [rax+7CCh], ebx
0x18019b6ce  jz      short loc_18019B6E4
0x18019b6d0  mov     r9d, ebx; int
0x18019b6d3  mov     r8d, 4E4h; int
0x18019b6d9  mov     rdx, r12; char *
0x18019b6dc  mov     rcx, rax; this
0x18019b6df  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019b6e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019b6eb  jb      loc_18019B8F6
0x18019b6f1  mov     edx, 5Fh ; '_'
0x18019b6f6  jmp     loc_18019B4CD
0x18019b6fb  mov     rcx, [rbp+57h+phglobal]; hMem
0x18019b6ff  call    cs:__imp_GlobalLock
0x18019b705  mov     rdi, rax
0x18019b708  test    rax, rax
0x18019b70b  jnz     loc_18019B7A1
0x18019b711  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b718  mov     ebx, 8000FFFFh
0x18019b71d  test    rcx, rcx
0x18019b720  jnz     short loc_18019B763
0x18019b722  mov     rax, cs:stru_1801FC290.__vftable
0x18019b729  lea     r8, stru_1801FC290
0x18019b730  mov     edx, 7F0h
0x18019b735  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b73c  mov     rcx, r8
0x18019b73f  mov     rax, [rax+8]
0x18019b743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b748  test    eax, eax
0x18019b74a  jnz     short loc_18019B75C
0x18019b74c  lea     rcx, stru_1801F8A30
0x18019b753  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b75a  jmp     short loc_18019B763
0x18019b75c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019b763  cmp     byte ptr [rcx+8], 0
0x18019b767  jz      short loc_18019B78A
0x18019b769  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019b76e  cmp     [rax+7CCh], ebx
0x18019b774  jz      short loc_18019B78A
0x18019b776  mov     r9d, ebx; int
0x18019b779  mov     r8d, 4E7h; int
0x18019b77f  mov     rdx, r12; char *
0x18019b782  mov     rcx, rax; this
0x18019b785  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019b78a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019b791  jb      loc_18019B8F6
0x18019b797  mov     edx, 60h ; '`'
0x18019b79c  jmp     loc_18019B4CD
0x18019b7a1  mov     rdx, [rbp+57h+var_70]; __int64
0x18019b7a5  test    rdx, rdx
0x18019b7a8  jz      loc_18019B8F1
0x18019b7ae  mov     rcx, rsi; this
0x18019b7b1  call    ?WriteInt64@CBinaryWriter@@QEAAJ_J@Z; CBinaryWriter::WriteInt64(__int64)
0x18019b7b6  mov     ebx, eax
0x18019b7b8  test    eax, eax
0x18019b7ba  jns     loc_18019B84B
0x18019b7c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b7c7  test    rcx, rcx
0x18019b7ca  jnz     short loc_18019B80D
0x18019b7cc  mov     rax, cs:stru_1801FC290.__vftable
0x18019b7d3  lea     r8, stru_1801FC290
0x18019b7da  mov     edx, 7F0h
0x18019b7df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b7e6  mov     rcx, r8
0x18019b7e9  mov     rax, [rax+8]
0x18019b7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b7f2  test    eax, eax
0x18019b7f4  jnz     short loc_18019B806
0x18019b7f6  lea     rcx, stru_1801F8A30
0x18019b7fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b804  jmp     short loc_18019B80D
0x18019b806  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019b80d  cmp     byte ptr [rcx+8], 0
0x18019b811  jz      short loc_18019B834
0x18019b813  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019b818  cmp     [rax+7CCh], ebx
0x18019b81e  jz      short loc_18019B834
0x18019b820  mov     r9d, ebx; int
0x18019b823  mov     r8d, 4EBh; int
0x18019b829  mov     rdx, r12; char *
0x18019b82c  mov     rcx, rax; this
0x18019b82f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019b834  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019b83b  jb      loc_18019B8F6
0x18019b841  mov     edx, 61h ; 'a'
0x18019b846  jmp     loc_18019B4CD
0x18019b84b  mov     rax, [rsi]
0x18019b84e  mov     rdx, rdi
0x18019b851  mov     r8d, dword ptr [rbp+57h+var_70]
0x18019b855  mov     rcx, rsi
0x18019b858  mov     rax, [rax]
0x18019b85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b860  mov     ebx, eax
0x18019b862  test    eax, eax
0x18019b864  jns     loc_18019B8F6
0x18019b86a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b871  test    rcx, rcx
0x18019b874  jnz     short loc_18019B8B7
0x18019b876  mov     rax, cs:stru_1801FC290.__vftable
0x18019b87d  lea     r8, stru_1801FC290
0x18019b884  mov     edx, 7F0h
0x18019b889  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b890  mov     rcx, r8
0x18019b893  mov     rax, [rax+8]
0x18019b897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b89c  test    eax, eax
0x18019b89e  jnz     short loc_18019B8B0
0x18019b8a0  lea     rcx, stru_1801F8A30
0x18019b8a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019b8ae  jmp     short loc_18019B8B7
0x18019b8b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019b8b7  cmp     byte ptr [rcx+8], 0
0x18019b8bb  jz      short loc_18019B8DE
0x18019b8bd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019b8c2  cmp     [rax+7CCh], ebx
0x18019b8c8  jz      short loc_18019B8DE
0x18019b8ca  mov     r9d, ebx; int
0x18019b8cd  mov     r8d, 4ECh; int
0x18019b8d3  mov     rdx, r12; char *
0x18019b8d6  mov     rcx, rax; this
0x18019b8d9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019b8de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019b8e5  jb      short loc_18019B8F6
0x18019b8e7  mov     edx, 62h ; 'b'
0x18019b8ec  jmp     loc_18019B4CD
0x18019b8f1  mov     ebx, 8000FFFFh
0x18019b8f6  mov     rcx, [rbp+57h+phglobal]; hMem
0x18019b8fa  test    rcx, rcx
0x18019b8fd  jz      short loc_18019B90F
  ... truncated ...
```
