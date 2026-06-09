# CDCOMInterfaceMashallerHelper::UnMarshalInterface(CBinaryReader &,_GUID const &,void * *)

- ea: `0x1800cea18`
- end: `0x1800ceff9`
- name: `?UnMarshalInterface@CDCOMInterfaceMashallerHelper@@SAJAEAVCBinaryReader@@AEBU_GUID@@PEAPEAX@Z`
- size: `1505`
- prototype: `__int64 __fastcall(struct CBinaryReader *this, IID *riid, LPVOID *ppv)`
- caller_count: `4`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008dbec`
- `0x1800f5654`
- `0x18014a12c`
- `0x18019b97c`

## callees

- `0x180015b20`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800cea18`
- `0x18019b964`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cef23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cef23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cebb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cebb8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800cea6e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800cea6e`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800cee6f`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800cee6f`

## string_xrefs

- `0x1800cea2f`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1800cec2f`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1800cecd9`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1800ced89`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1800cee39`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1800ceedf`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1800cef93`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`

## pseudocode

```c
__int64 __fastcall CDCOMInterfaceMashallerHelper::UnMarshalInterface(
        struct CBinaryReader *this,
        IID *riid,
        LPVOID *ppv)
{
  HRESULT Int64; // ebx
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  unsigned int v12; // edi
  LPVOID v13; // rax
  void *v14; // r14
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  int v29; // [rsp+30h] [rbp-28h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-20h] BYREF
  SIZE_T cb; // [rsp+40h] [rbp-18h] BYREF
  __int64 v32; // [rsp+48h] [rbp-10h]
  CallStackScopeTrace v33; // [rsp+B8h] [rbp+60h] BYREF

  ppstm = 0;
  cb = 0;
  v29 = 0;
  v32 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v33, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1293);
  Int64 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( Int64 < 0 )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( ThreadRelativeContext->m_result != Int64 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CDCOMInterfaceMashallerHelper::UnMarshalInterface",
          1293,
          Int64);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v9 = 99;
LABEL_83:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids, 0, Int64);
      goto LABEL_84;
    }
    goto LABEL_84;
  }
  Int64 = CBinaryReader::ReadInt64(this, (__int64 *)&cb);
  if ( Int64 >= 0 )
  {
    v12 = cb;
    if ( cb > 0xFFFFFFFF )
    {
      v26 = CallStackTracing::s_wpInstance;
      Int64 = -2147024362;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v26 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v26->m_fEnabled )
      {
        v27 = CallStackTracing::GetThreadRelativeContext(v26);
        if ( v27->m_result != -2147024362 )
          CallStackContext::TraceFailure(v27, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1297, -2147024362);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v9 = 101;
        goto LABEL_83;
      }
      goto LABEL_84;
    }
    v13 = CoTaskMemAlloc((unsigned int)cb);
    v14 = v13;
    if ( !v13 )
    {
      v15 = CallStackTracing::s_wpInstance;
      Int64 = -2147418113;
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
        if ( v16->m_result != -2147418113 )
          CallStackContext::TraceFailure(v16, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1300, -2147418113);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v9 = 102;
        goto LABEL_83;
      }
      goto LABEL_84;
    }
    Int64 = (**(__int64 (__fastcall ***)(struct CBinaryReader *, LPVOID, _QWORD))this)(this, v13, v12);
    if ( Int64 >= 0 )
    {
      Int64 = ppstm->Write(ppstm, v14, v12, (unsigned int *)&v29);
      if ( Int64 >= 0 )
      {
        Int64 = ((__int64 (__fastcall *)(LPSTREAM, __int64, _QWORD, _QWORD))ppstm->Seek)(ppstm, v32, 0, 0);
        if ( Int64 >= 0 )
        {
          Int64 = CoUnmarshalInterface(ppstm, riid, ppv);
          if ( Int64 >= 0 )
            goto LABEL_73;
          v24 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v24 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v24->m_fEnabled )
          {
            v25 = CallStackTracing::GetThreadRelativeContext(v24);
            if ( v25->m_result != Int64 )
              CallStackContext::TraceFailure(v25, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1308, Int64);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_73;
          v19 = 106;
        }
        else
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
            if ( v23->m_result != Int64 )
              CallStackContext::TraceFailure(v23, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1306, Int64);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_73;
          v19 = 105;
        }
      }
      else
      {
        v20 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v20 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v20->m_fEnabled )
        {
          v21 = CallStackTracing::GetThreadRelativeContext(v20);
          if ( v21->m_result != Int64 )
            CallStackContext::TraceFailure(v21, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1304, Int64);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_73;
        v19 = 104;
      }
    }
    else
    {
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
        if ( v18->m_result != Int64 )
          CallStackContext::TraceFailure(v18, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1302, Int64);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_73;
      v19 = 103;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids, 0, Int64);
LABEL_73:
    CoTaskMemFree(v14);
    goto LABEL_84;
  }
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
    if ( v11->m_result != Int64 )
      CallStackContext::TraceFailure(v11, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1295, Int64);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v9 = 100;
    goto LABEL_83;
  }
LABEL_84:
  CallStackScopeTrace::~CallStackScopeTrace(&v33);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppstm);
  return (unsigned int)Int64;
}

```

## disassembly

```asm
0x1800cea18  push    rbp
0x1800cea1a  push    rbx
0x1800cea1b  push    rsi
0x1800cea1c  push    rdi
0x1800cea1d  push    r12
0x1800cea1f  push    r13
0x1800cea21  push    r14
0x1800cea23  push    r15
0x1800cea25  mov     rbp, rsp
0x1800cea28  sub     rsp, 58h
0x1800cea2c  xor     r13d, r13d
0x1800cea2f  lea     rdi, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1800cea36  mov     r15, r8
0x1800cea39  mov     [rbp+ppstm], r13
0x1800cea3d  mov     r12, rdx
0x1800cea40  mov     [rbp+cb], r13
0x1800cea44  mov     rsi, rcx
0x1800cea47  mov     [rbp+var_28], r13d
0x1800cea4b  mov     rdx, rdi; char *
0x1800cea4e  mov     [rbp+var_10], r13
0x1800cea52  mov     r8d, 50Dh; int
0x1800cea58  lea     rcx, [rbp+arg_18]; this
0x1800cea5c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cea61  lea     r14d, [r13+1]
0x1800cea65  xor     ecx, ecx; hGlobal
0x1800cea67  mov     edx, r14d; fDeleteOnRelease
0x1800cea6a  lea     r8, [rbp+ppstm]; ppstm
0x1800cea6e  call    cs:__imp_CreateStreamOnHGlobal
0x1800cea74  mov     ebx, eax
0x1800cea76  test    eax, eax
0x1800cea78  jns     loc_1800CEB06
0x1800cea7e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cea85  test    rcx, rcx
0x1800cea88  jnz     short loc_1800CEAC8
0x1800cea8a  mov     rdx, cs:stru_1801FC290.__vftable
0x1800cea91  lea     rcx, stru_1801FC290
0x1800cea98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cea9f  mov     rax, [rdx+8]
0x1800ceaa3  mov     edx, 7F0h
0x1800ceaa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceaad  test    eax, eax
0x1800ceaaf  jnz     short loc_1800CEAC1
0x1800ceab1  lea     rcx, stru_1801F8A30
0x1800ceab8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ceabf  jmp     short loc_1800CEAC8
0x1800ceac1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ceac8  cmp     [rcx+8], r13b
0x1800ceacc  jz      short loc_1800CEAEF
0x1800ceace  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cead3  cmp     [rax+7CCh], ebx
0x1800cead9  jz      short loc_1800CEAEF
0x1800ceadb  mov     r9d, ebx; int
0x1800ceade  mov     r8d, 50Dh; int
0x1800ceae4  mov     rdx, rdi; char *
0x1800ceae7  mov     rcx, rax; this
0x1800ceaea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ceaef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800ceaf6  jb      loc_1800CEFD4
0x1800ceafc  mov     edx, 63h ; 'c'
0x1800ceb01  jmp     loc_1800CEFB6
0x1800ceb06  lea     rdx, [rbp+cb]; __int64 *
0x1800ceb0a  mov     rcx, rsi; this
0x1800ceb0d  call    ?ReadInt64@CBinaryReader@@QEAAJAEA_J@Z; CBinaryReader::ReadInt64(__int64 &)
0x1800ceb12  mov     ebx, eax
0x1800ceb14  test    eax, eax
0x1800ceb16  jns     loc_1800CEBA4
0x1800ceb1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ceb23  test    rcx, rcx
0x1800ceb26  jnz     short loc_1800CEB66
0x1800ceb28  mov     rax, cs:stru_1801FC290.__vftable
0x1800ceb2f  lea     rcx, stru_1801FC290
0x1800ceb36  mov     edx, 7F0h
0x1800ceb3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ceb42  mov     rax, [rax+8]
0x1800ceb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceb4b  test    eax, eax
0x1800ceb4d  jnz     short loc_1800CEB5F
0x1800ceb4f  lea     rcx, stru_1801F8A30
0x1800ceb56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ceb5d  jmp     short loc_1800CEB66
0x1800ceb5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ceb66  cmp     [rcx+8], r13b
0x1800ceb6a  jz      short loc_1800CEB8D
0x1800ceb6c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ceb71  cmp     [rax+7CCh], ebx
0x1800ceb77  jz      short loc_1800CEB8D
0x1800ceb79  mov     r9d, ebx; int
0x1800ceb7c  mov     r8d, 50Fh; int
0x1800ceb82  mov     rdx, rdi; char *
0x1800ceb85  mov     rcx, rax; this
0x1800ceb88  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ceb8d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800ceb94  jb      loc_1800CEFD4
0x1800ceb9a  mov     edx, 64h ; 'd'
0x1800ceb9f  jmp     loc_1800CEFB6
0x1800ceba4  mov     rdi, [rbp+cb]
0x1800ceba8  mov     eax, 0FFFFFFFFh
0x1800cebad  cmp     rdi, rax
0x1800cebb0  ja      loc_1800CEF2E
0x1800cebb6  mov     ecx, edi; cb
0x1800cebb8  call    cs:__imp_CoTaskMemAlloc
0x1800cebbe  mov     r14, rax
0x1800cebc1  test    rax, rax
0x1800cebc4  jnz     loc_1800CEC5B
0x1800cebca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cebd1  mov     ebx, 8000FFFFh
0x1800cebd6  test    rcx, rcx
0x1800cebd9  jnz     short loc_1800CEC19
0x1800cebdb  mov     rax, cs:stru_1801FC290.__vftable
0x1800cebe2  lea     rcx, stru_1801FC290
0x1800cebe9  mov     edx, 7F0h
0x1800cebee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cebf5  mov     rax, [rax+8]
0x1800cebf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cebfe  test    eax, eax
0x1800cec00  jnz     short loc_1800CEC12
0x1800cec02  lea     rcx, stru_1801F8A30
0x1800cec09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cec10  jmp     short loc_1800CEC19
0x1800cec12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cec19  cmp     [rcx+8], r13b
0x1800cec1d  jz      short loc_1800CEC44
0x1800cec1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cec24  cmp     [rax+7CCh], ebx
0x1800cec2a  jz      short loc_1800CEC44
0x1800cec2c  mov     r9d, ebx; int
0x1800cec2f  lea     rdx, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1800cec36  mov     r8d, 514h; int
0x1800cec3c  mov     rcx, rax; this
0x1800cec3f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cec44  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cec4b  jb      loc_1800CEFD4
0x1800cec51  mov     edx, 66h ; 'f'
0x1800cec56  jmp     loc_1800CEFB6
0x1800cec5b  mov     rax, [rsi]
0x1800cec5e  mov     r8d, edi
0x1800cec61  mov     rdx, r14
0x1800cec64  mov     rcx, rsi
0x1800cec67  mov     rax, [rax]
0x1800cec6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cec6f  mov     ebx, eax
0x1800cec71  test    eax, eax
0x1800cec73  jns     loc_1800CED05
0x1800cec79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cec80  test    rcx, rcx
0x1800cec83  jnz     short loc_1800CECC3
0x1800cec85  mov     rax, cs:stru_1801FC290.__vftable
0x1800cec8c  lea     rcx, stru_1801FC290
0x1800cec93  mov     edx, 7F0h
0x1800cec98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cec9f  mov     rax, [rax+8]
0x1800ceca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceca8  test    eax, eax
0x1800cecaa  jnz     short loc_1800CECBC
0x1800cecac  lea     rcx, stru_1801F8A30
0x1800cecb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cecba  jmp     short loc_1800CECC3
0x1800cecbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cecc3  cmp     [rcx+8], r13b
0x1800cecc7  jz      short loc_1800CECEE
0x1800cecc9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cecce  cmp     [rax+7CCh], ebx
0x1800cecd4  jz      short loc_1800CECEE
0x1800cecd6  mov     r9d, ebx; int
0x1800cecd9  lea     rdx, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1800cece0  mov     r8d, 516h; int
0x1800cece6  mov     rcx, rax; this
0x1800cece9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cecee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cecf5  jb      loc_1800CEF20
0x1800cecfb  mov     edx, 67h ; 'g'
0x1800ced00  jmp     loc_1800CEF02
0x1800ced05  mov     rcx, [rbp+ppstm]
0x1800ced09  lea     r9, [rbp+var_28]
0x1800ced0d  mov     r8d, edi
0x1800ced10  mov     rdx, r14
0x1800ced13  mov     rax, [rcx]
0x1800ced16  mov     rax, [rax+20h]
0x1800ced1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ced1f  mov     ebx, eax
0x1800ced21  test    eax, eax
0x1800ced23  jns     loc_1800CEDB5
0x1800ced29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ced30  test    rcx, rcx
0x1800ced33  jnz     short loc_1800CED73
0x1800ced35  mov     rax, cs:stru_1801FC290.__vftable
0x1800ced3c  lea     rcx, stru_1801FC290
0x1800ced43  mov     edx, 7F0h
0x1800ced48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ced4f  mov     rax, [rax+8]
0x1800ced53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ced58  test    eax, eax
0x1800ced5a  jnz     short loc_1800CED6C
0x1800ced5c  lea     rcx, stru_1801F8A30
0x1800ced63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ced6a  jmp     short loc_1800CED73
0x1800ced6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ced73  cmp     [rcx+8], r13b
0x1800ced77  jz      short loc_1800CED9E
0x1800ced79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ced7e  cmp     [rax+7CCh], ebx
0x1800ced84  jz      short loc_1800CED9E
0x1800ced86  mov     r9d, ebx; int
0x1800ced89  lea     rdx, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1800ced90  mov     r8d, 518h; int
0x1800ced96  mov     rcx, rax; this
0x1800ced99  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ced9e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ceda5  jb      loc_1800CEF20
0x1800cedab  mov     edx, 68h ; 'h'
0x1800cedb0  jmp     loc_1800CEF02
0x1800cedb5  mov     rcx, [rbp+ppstm]
0x1800cedb9  xor     r9d, r9d
0x1800cedbc  mov     rdx, [rbp+var_10]
0x1800cedc0  xor     r8d, r8d
0x1800cedc3  mov     rax, [rcx]
0x1800cedc6  mov     rax, [rax+28h]
0x1800cedca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cedcf  mov     ebx, eax
0x1800cedd1  test    eax, eax
0x1800cedd3  jns     loc_1800CEE65
0x1800cedd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cede0  test    rcx, rcx
0x1800cede3  jnz     short loc_1800CEE23
0x1800cede5  mov     rax, cs:stru_1801FC290.__vftable
0x1800cedec  lea     rcx, stru_1801FC290
0x1800cedf3  mov     edx, 7F0h
0x1800cedf8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cedff  mov     rax, [rax+8]
0x1800cee03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cee08  test    eax, eax
0x1800cee0a  jnz     short loc_1800CEE1C
0x1800cee0c  lea     rcx, stru_1801F8A30
0x1800cee13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cee1a  jmp     short loc_1800CEE23
0x1800cee1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cee23  cmp     [rcx+8], r13b
0x1800cee27  jz      short loc_1800CEE4E
0x1800cee29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cee2e  cmp     [rax+7CCh], ebx
0x1800cee34  jz      short loc_1800CEE4E
0x1800cee36  mov     r9d, ebx; int
0x1800cee39  lea     rdx, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1800cee40  mov     r8d, 51Ah; int
0x1800cee46  mov     rcx, rax; this
0x1800cee49  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cee4e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cee55  jb      loc_1800CEF20
0x1800cee5b  mov     edx, 69h ; 'i'
0x1800cee60  jmp     loc_1800CEF02
0x1800cee65  mov     rcx, [rbp+ppstm]; pStm
0x1800cee69  mov     r8, r15; ppv
0x1800cee6c  mov     rdx, r12; riid
0x1800cee6f  call    cs:__imp_CoUnmarshalInterface
0x1800cee75  mov     ebx, eax
0x1800cee77  test    eax, eax
0x1800cee79  jns     loc_1800CEF20
0x1800cee7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cee86  test    rcx, rcx
0x1800cee89  jnz     short loc_1800CEEC9
0x1800cee8b  mov     rax, cs:stru_1801FC290.__vftable
0x1800cee92  lea     rcx, stru_1801FC290
0x1800cee99  mov     edx, 7F0h
0x1800cee9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ceea5  mov     rax, [rax+8]
0x1800ceea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceeae  test    eax, eax
0x1800ceeb0  jnz     short loc_1800CEEC2
0x1800ceeb2  lea     rcx, stru_1801F8A30
0x1800ceeb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ceec0  jmp     short loc_1800CEEC9
0x1800ceec2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ceec9  cmp     [rcx+8], r13b
0x1800ceecd  jz      short loc_1800CEEF4
0x1800ceecf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ceed4  cmp     [rax+7CCh], ebx
0x1800ceeda  jz      short loc_1800CEEF4
0x1800ceedc  mov     r9d, ebx; int
0x1800ceedf  lea     rdx, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1800ceee6  mov     r8d, 51Ch; int
0x1800ceeec  mov     rcx, rax; this
0x1800ceeef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ceef4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ceefb  jb      short loc_1800CEF20
0x1800ceefd  mov     edx, 6Ah ; 'j'
0x1800cef02  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cef09  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x1800cef10  xor     r9d, r9d
0x1800cef13  mov     [rsp+58h+var_38], ebx
0x1800cef17  mov     rcx, [rcx+10h]
0x1800cef1b  call    WPP_SF_qD
0x1800cef20  mov     rcx, r14; pv
0x1800cef23  call    cs:__imp_CoTaskMemFree
0x1800cef29  jmp     loc_1800CEFD4
0x1800cef2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cef35  mov     ebx, 80070216h
0x1800cef3a  test    rcx, rcx
0x1800cef3d  jnz     short loc_1800CEF7D
0x1800cef3f  mov     rax, cs:stru_1801FC290.__vftable
0x1800cef46  lea     rcx, stru_1801FC290
  ... truncated ...
```
