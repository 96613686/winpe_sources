# CMP3MediaSourcePlugin::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x1801597a0`
- end: `0x180159bf6`
- name: `?GetService@CMP3MediaSourcePlugin@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `1110`
- prototype: `int(CMP3MediaSourcePlugin *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1801597a0`
- `0x18017b734`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801597f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015991b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180159a10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180159aa8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180159b3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801597f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015991b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180159a10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180159aa8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180159b3e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801599ee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801599ee`

## string_xrefs

- `0x1801597b3`: `CMP3MediaSourcePlugin::GetService`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::GetService(
        CMP3MediaSourcePlugin *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v8; // rdx
  wchar_t *v9; // rcx
  HRESULT Instance; // ebx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  _BYTE v33[56]; // [rsp+30h] [rbp-38h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v33, "CMP3MediaSourcePlugin::GetService", 216);
  if ( !a4 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    Instance = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSourcePlugin::GetService", 218, -2147467261);
    }
    if ( g_wppLevels )
    {
      v13 = 22;
LABEL_64:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
        this,
        Instance);
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  *a4 = 0;
  if ( !memcmp_0(&MF_MEDIASOURCE_SERVICE, a2, 0x10u) )
  {
    if ( !memcmp_0(&IID_IMFSourceHeaderParserPlugin, a3, 0x10u) )
    {
      v14 = (unsigned __int64)this + 8;
LABEL_19:
      Instance = 0;
      *a4 = (void *)(v14 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
      _InterlockedIncrement((volatile signed __int32 *)this + 30);
      goto LABEL_65;
    }
    if ( !memcmp_0(&IID_IMFSourceIndexParserPlugin, a3, 0x10u) )
    {
      v14 = (unsigned __int64)this + 24;
      goto LABEL_19;
    }
    if ( !memcmp_0(&IID_IMFSourceDataParserPlugin, a3, 0x10u) )
    {
      v14 = (unsigned __int64)this + 16;
      goto LABEL_19;
    }
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    Instance = -2147467262;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != -2147467262 )
        CallStackContext::TraceFailure(v18, "CMP3MediaSourcePlugin::GetService", 237, -2147467262);
    }
    if ( !g_wppLevels )
      goto LABEL_65;
    v19 = 23;
LABEL_30:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      this,
      -2147467262);
    goto LABEL_65;
  }
  if ( memcmp_0(&MF_PROPERTY_HANDLER_SERVICE, a2, 0x10u) )
  {
    v29 = (wchar_t *)CallStackTracing::s_wpInstance;
    Instance = -1072875846;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v31 + 499) != -1072875846 )
        CallStackContext::TraceFailure(v31, "CMP3MediaSourcePlugin::GetService", 259, -1072875846);
    }
    if ( g_wppLevels )
    {
      v13 = 26;
      goto LABEL_64;
    }
    goto LABEL_65;
  }
  if ( memcmp_0(&IID_IInitializeWithStream, a3, 0x10u) )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    Instance = -2147467262;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v28 + 499) != -2147467262 )
        CallStackContext::TraceFailure(v28, "CMP3MediaSourcePlugin::GetService", 254, -2147467262);
    }
    if ( !g_wppLevels )
      goto LABEL_65;
    v19 = 25;
    goto LABEL_30;
  }
  Instance = CoCreateInstance(&CLSID_MFMP3PropertyHandler, 0, 1u, &IID_IInitializeWithStream, a4);
  if ( Instance < 0 )
  {
    v23 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
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
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v25 + 499) != Instance )
        CallStackContext::TraceFailure(v25, "CMP3MediaSourcePlugin::GetService", 248, Instance);
    }
    if ( g_wppLevels )
    {
      v13 = 24;
      goto LABEL_64;
    }
  }
LABEL_65:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v33);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801597a0  mov     [rsp+arg_8], rbx
0x1801597a5  push    rbp
0x1801597a6  push    rsi
0x1801597a7  push    rdi
0x1801597a8  push    r12
0x1801597aa  push    r15
0x1801597ac  sub     rsp, 40h
0x1801597b0  mov     rbx, r8
0x1801597b3  lea     r12, aCmp3mediasourc_34; "CMP3MediaSourcePlugin::GetService"
0x1801597ba  mov     rbp, rdx
0x1801597bd  mov     rsi, rcx
0x1801597c0  mov     rdx, r12; char *
0x1801597c3  lea     rcx, [rsp+68h+var_38]; this
0x1801597c8  mov     r8d, 0D8h; int
0x1801597ce  mov     rdi, r9
0x1801597d1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801597d6  test    rdi, rdi
0x1801597d9  jnz     loc_180159875
0x1801597df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801597e6  mov     ebx, 80004003h
0x1801597eb  test    rcx, rcx
0x1801597ee  jnz     short loc_180159837
0x1801597f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801597f7  nop     dword ptr [rax+rax+00h]
0x1801597fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180159803  mov     rcx, rax
0x180159806  test    rax, rax
0x180159809  jz      short loc_180159829
0x18015980b  mov     rax, [rax]
0x18015980e  mov     edx, 7F0h
0x180159813  mov     rax, [rax+8]
0x180159817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015981c  test    eax, eax
0x18015981e  jz      short loc_180159829
0x180159820  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180159827  jmp     short loc_180159837
0x180159829  lea     rcx, qword_1801B97E0; this
0x180159830  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180159837  cmp     byte ptr [rcx+8], 0
0x18015983b  jz      short loc_18015985E
0x18015983d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180159842  cmp     [rax+7CCh], ebx
0x180159848  jz      short loc_18015985E
0x18015984a  mov     r9d, ebx; int
0x18015984d  mov     r8d, 0DAh; int
0x180159853  mov     rdx, r12; char *
0x180159856  mov     rcx, rax; this
0x180159859  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18015985e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180159865  jb      loc_180159BD8
0x18015986b  mov     edx, 16h
0x180159870  jmp     loc_180159BBA
0x180159875  mov     r15d, 10h
0x18015987b  mov     qword ptr [rdi], 0
0x180159882  mov     r8d, r15d; Size
0x180159885  lea     rcx, MF_MEDIASOURCE_SERVICE; Buf1
0x18015988c  mov     rdx, rbp; Buf2
0x18015988f  call    memcmp_0
0x180159894  mov     r8d, r15d; Size
0x180159897  test    eax, eax
0x180159899  jnz     loc_1801599A4
0x18015989f  mov     rdx, rbx; Buf2
0x1801598a2  lea     rcx, IID_IMFSourceHeaderParserPlugin; Buf1
0x1801598a9  call    memcmp_0
0x1801598ae  test    eax, eax
0x1801598b0  jnz     short loc_1801598B8
0x1801598b2  lea     rcx, [rsi+8]
0x1801598b6  jmp     short loc_1801598EE
0x1801598b8  mov     r8, r15; Size
0x1801598bb  lea     rcx, IID_IMFSourceIndexParserPlugin; Buf1
0x1801598c2  mov     rdx, rbx; Buf2
0x1801598c5  call    memcmp_0
0x1801598ca  test    eax, eax
0x1801598cc  jnz     short loc_1801598D4
0x1801598ce  lea     rcx, [rsi+18h]
0x1801598d2  jmp     short loc_1801598EE
0x1801598d4  mov     r8, r15; Size
0x1801598d7  lea     rcx, IID_IMFSourceDataParserPlugin; Buf1
0x1801598de  mov     rdx, rbx; Buf2
0x1801598e1  call    memcmp_0
0x1801598e6  test    eax, eax
0x1801598e8  jnz     short loc_180159908
0x1801598ea  lea     rcx, [rsi+10h]
0x1801598ee  mov     rax, rsi
0x1801598f1  neg     rax
0x1801598f4  sbb     rdx, rdx
0x1801598f7  and     rdx, rcx
0x1801598fa  xor     ebx, ebx
0x1801598fc  mov     [rdi], rdx
0x1801598ff  lock inc dword ptr [rsi+78h]
0x180159903  jmp     loc_180159BD8
0x180159908  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015990f  mov     edi, 80004002h
0x180159914  mov     ebx, edi
0x180159916  test    rcx, rcx
0x180159919  jnz     short loc_180159962
0x18015991b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180159922  nop     dword ptr [rax+rax+00h]
0x180159927  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015992e  mov     rcx, rax
0x180159931  test    rax, rax
0x180159934  jz      short loc_180159954
0x180159936  mov     rax, [rax]
0x180159939  mov     edx, 7F0h
0x18015993e  mov     rax, [rax+8]
0x180159942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159947  test    eax, eax
0x180159949  jz      short loc_180159954
0x18015994b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180159952  jmp     short loc_180159962
0x180159954  lea     rcx, qword_1801B97E0; this
0x18015995b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180159962  cmp     byte ptr [rcx+8], 0
0x180159966  jz      short loc_180159989
0x180159968  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015996d  cmp     [rax+7CCh], edi
0x180159973  jz      short loc_180159989
0x180159975  mov     r9d, edi; int
0x180159978  mov     r8d, 0EDh; int
0x18015997e  mov     rdx, r12; char *
0x180159981  mov     rcx, rax; this
0x180159984  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180159989  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180159990  jb      loc_180159BD8
0x180159996  mov     edx, 17h
0x18015999b  mov     dword ptr [rsp+68h+ppv], edi
0x18015999f  jmp     loc_180159BBE
0x1801599a4  mov     rdx, rbp; Buf2
0x1801599a7  lea     rcx, MF_PROPERTY_HANDLER_SERVICE; Buf1
0x1801599ae  call    memcmp_0
0x1801599b3  test    eax, eax
0x1801599b5  jnz     loc_180159B2D
0x1801599bb  mov     r8, r15; Size
0x1801599be  lea     rcx, IID_IInitializeWithStream; Buf1
0x1801599c5  mov     rdx, rbx; Buf2
0x1801599c8  call    memcmp_0
0x1801599cd  test    eax, eax
0x1801599cf  jnz     loc_180159A95
0x1801599d5  lea     r9, IID_IInitializeWithStream; riid
0x1801599dc  mov     [rsp+68h+ppv], rdi; ppv
0x1801599e1  xor     edx, edx; pUnkOuter
0x1801599e3  lea     r8d, [rax+1]; dwClsContext
0x1801599e7  lea     rcx, CLSID_MFMP3PropertyHandler; rclsid
0x1801599ee  call    cs:__imp_CoCreateInstance
0x1801599f5  nop     dword ptr [rax+rax+00h]
0x1801599fa  mov     ebx, eax
0x1801599fc  test    eax, eax
0x1801599fe  jns     loc_180159BD8
0x180159a04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180159a0b  test    rcx, rcx
0x180159a0e  jnz     short loc_180159A57
0x180159a10  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180159a17  nop     dword ptr [rax+rax+00h]
0x180159a1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180159a23  mov     rcx, rax
0x180159a26  test    rax, rax
0x180159a29  jz      short loc_180159A49
0x180159a2b  mov     rax, [rax]
0x180159a2e  mov     edx, 7F0h
0x180159a33  mov     rax, [rax+8]
0x180159a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159a3c  test    eax, eax
0x180159a3e  jz      short loc_180159A49
0x180159a40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180159a47  jmp     short loc_180159A57
0x180159a49  lea     rcx, qword_1801B97E0; this
0x180159a50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180159a57  cmp     byte ptr [rcx+8], 0
0x180159a5b  jz      short loc_180159A7E
0x180159a5d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180159a62  cmp     [rax+7CCh], ebx
0x180159a68  jz      short loc_180159A7E
0x180159a6a  mov     r9d, ebx; int
0x180159a6d  mov     r8d, 0F8h; int
0x180159a73  mov     rdx, r12; char *
0x180159a76  mov     rcx, rax; this
0x180159a79  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180159a7e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180159a85  jb      loc_180159BD8
0x180159a8b  mov     edx, 18h
0x180159a90  jmp     loc_180159BBA
0x180159a95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180159a9c  mov     edi, 80004002h
0x180159aa1  mov     ebx, edi
0x180159aa3  test    rcx, rcx
0x180159aa6  jnz     short loc_180159AEF
0x180159aa8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180159aaf  nop     dword ptr [rax+rax+00h]
0x180159ab4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180159abb  mov     rcx, rax
0x180159abe  test    rax, rax
0x180159ac1  jz      short loc_180159AE1
0x180159ac3  mov     rax, [rax]
0x180159ac6  mov     edx, 7F0h
0x180159acb  mov     rax, [rax+8]
0x180159acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159ad4  test    eax, eax
0x180159ad6  jz      short loc_180159AE1
0x180159ad8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180159adf  jmp     short loc_180159AEF
0x180159ae1  lea     rcx, qword_1801B97E0; this
0x180159ae8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180159aef  cmp     byte ptr [rcx+8], 0
0x180159af3  jz      short loc_180159B16
0x180159af5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180159afa  cmp     [rax+7CCh], edi
0x180159b00  jz      short loc_180159B16
0x180159b02  mov     r9d, edi; int
0x180159b05  mov     r8d, 0FEh; int
0x180159b0b  mov     rdx, r12; char *
0x180159b0e  mov     rcx, rax; this
0x180159b11  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180159b16  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180159b1d  jb      loc_180159BD8
0x180159b23  mov     edx, 19h
0x180159b28  jmp     loc_18015999B
0x180159b2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180159b34  mov     ebx, 0C00D36BAh
0x180159b39  test    rcx, rcx
0x180159b3c  jnz     short loc_180159B85
0x180159b3e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180159b45  nop     dword ptr [rax+rax+00h]
0x180159b4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180159b51  mov     rcx, rax
0x180159b54  test    rax, rax
0x180159b57  jz      short loc_180159B77
0x180159b59  mov     rax, [rax]
0x180159b5c  mov     edx, 7F0h
0x180159b61  mov     rax, [rax+8]
0x180159b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159b6a  test    eax, eax
0x180159b6c  jz      short loc_180159B77
0x180159b6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180159b75  jmp     short loc_180159B85
0x180159b77  lea     rcx, qword_1801B97E0; this
0x180159b7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180159b85  cmp     byte ptr [rcx+8], 0
0x180159b89  jz      short loc_180159BAC
0x180159b8b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180159b90  cmp     [rax+7CCh], ebx
0x180159b96  jz      short loc_180159BAC
0x180159b98  mov     r9d, ebx; int
0x180159b9b  mov     r8d, 103h; int
0x180159ba1  mov     rdx, r12; char *
0x180159ba4  mov     rcx, rax; this
0x180159ba7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180159bac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180159bb3  jb      short loc_180159BD8
0x180159bb5  mov     edx, 1Ah
0x180159bba  mov     dword ptr [rsp+68h+ppv], ebx
0x180159bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180159bc5  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x180159bcc  mov     r9, rsi
0x180159bcf  mov     rcx, [rcx+10h]
0x180159bd3  call    WPP_SF_qD
0x180159bd8  lea     rcx, [rsp+68h+var_38]; this
0x180159bdd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180159be2  mov     eax, ebx
0x180159be4  mov     rbx, [rsp+68h+arg_8]
0x180159be9  add     rsp, 40h
0x180159bed  pop     r15
0x180159bef  pop     r12
0x180159bf1  pop     rdi
0x180159bf2  pop     rsi
0x180159bf3  pop     rbp
0x180159bf4  retn
```
