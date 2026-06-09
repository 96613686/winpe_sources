# CdvmftMFTTypeHandler::Init(CdvmftMFTDataHandler *)

- ea: `0x18000440c`
- end: `0x180004812`
- name: `?Init@CdvmftMFTTypeHandler@@QEAAJPEAVCdvmftMFTDataHandler@@@Z`
- size: `1030`
- prototype: `__int64 __fastcall(CdvmftMFTTypeHandler *__hidden this, struct CdvmftMFTDataHandler *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180004818`

## callees

- `0x180001580`
- `0x180001ec8`
- `0x180002200`
- `0x18000440c`
- `0x180006950`
- `0x1800082ec`
- `0x180008358`
- `0x180009404`
- `0x18001e010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000447b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180004610`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180004696`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180004719`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000447b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180004610`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180004696`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180004719`
- `MFPlat!MFCreateMediaType` at `0x180004522`
- `MFPlat!MFCreateMediaType` at `0x180004522`

## pseudocode

```c
__int64 __fastcall CdvmftMFTTypeHandler::Init(CdvmftMFTTypeHandler *this, struct CdvmftMFTDataHandler *a2)
{
  HRESULT inited; // ebx
  CallStackTracing *v4; // rax
  struct CallStackContext *v5; // rax
  __int64 v6; // rdx
  unsigned int v7; // esi
  IMFMediaType *v8; // r15
  __int64 v9; // rcx
  __int64 v10; // rcx
  IMFMediaType *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  struct CallStackContext *v18; // rax
  int v19; // ecx
  int v20; // ecx
  IMFMediaType *ppMFType; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v23[8]; // [rsp+38h] [rbp-30h] BYREF
  _DWORD v24[4]; // [rsp+40h] [rbp-28h] BYREF

  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 13) = a2;
  ppMFType = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v23, "CdvmftMFTTypeHandler::Init", 687);
  inited = CMFTSimpleTypeHandler::InitAvailableInputTypeArray(this, 4u);
  if ( inited >= 0 )
  {
    v7 = 0;
    while ( 1 )
    {
      v24[1] = 0x100000;
      v24[2] = -1442840448;
      v24[3] = 1905997824;
      v24[0] = dword_180020150[v7];
      inited = MFCreateMediaType(&ppMFType);
      if ( inited < 0 )
        break;
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_MAJOR_TYPE,
                 &MFMediaType_Video);
      if ( inited < 0 )
      {
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v14;
          if ( !v14 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
        }
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          v15 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
          if ( *((_DWORD *)v15 + 499) != inited )
            CallStackContext::TraceFailure(v15, "CdvmftMFTTypeHandler::Init", 698, inited);
        }
        if ( g_wppLevels )
        {
          v6 = 52;
          goto LABEL_50;
        }
        goto LABEL_51;
      }
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _DWORD *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_SUBTYPE,
                 v24);
      if ( inited < 0 )
      {
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v12;
          if ( !v12 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
        }
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          v13 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
          if ( *((_DWORD *)v13 + 499) != inited )
            CallStackContext::TraceFailure(v13, "CdvmftMFTTypeHandler::Init", 700, inited);
        }
        if ( g_wppLevels )
        {
          v6 = 53;
          goto LABEL_50;
        }
        goto LABEL_51;
      }
      if ( v7 < *((_DWORD *)this + 4) )
      {
        v8 = ppMFType;
        v9 = *(_QWORD *)(*((_QWORD *)this + 3) + 16LL * v7);
        if ( v9 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          *(_QWORD *)(*((_QWORD *)this + 3) + 16LL * v7) = 0;
        }
        *(_QWORD *)(*((_QWORD *)this + 3) + 16LL * v7) = v8;
        v10 = *(_QWORD *)(*((_QWORD *)this + 3) + 16LL * v7);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        *(_DWORD *)(*((_QWORD *)this + 3) + 16LL * v7 + 8) = 1;
      }
      v11 = ppMFType;
      if ( ppMFType )
      {
        ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
        v11 = 0;
        ppMFType = 0;
      }
      if ( ++v7 >= 4 )
        goto LABEL_52;
    }
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v16;
      if ( !v16 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v17 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v17 + 499) != inited )
        CallStackContext::TraceFailure(v17, "CdvmftMFTTypeHandler::Init", 697, inited);
    }
    if ( g_wppLevels )
    {
      v6 = 51;
      goto LABEL_50;
    }
  }
  else
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      v4 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v4;
      if ( !v4 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v4 + 8LL))(v4, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v5 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v5 + 499) != inited )
        CallStackContext::TraceFailure(v5, "CdvmftMFTTypeHandler::Init", 687, inited);
    }
    if ( g_wppLevels )
    {
      v6 = 50;
LABEL_50:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_eab3d75b25033173348b4e1d8c19ad3b_Traceguids, this, inited);
    }
  }
LABEL_51:
  v11 = ppMFType;
LABEL_52:
  if ( v11 )
  {
    ((void (__fastcall *)(IMFMediaType *))v11->lpVtbl->Release)(v11);
    ppMFType = 0;
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v18 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
    v19 = *((_DWORD *)v18 + 497);
    if ( v19 )
    {
      v20 = v19 - 1;
      *((_DWORD *)v18 + 497) = v20;
      if ( !v20 )
        CallStackContext::ClearState((GUID *)v18);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000440c  push    rbp
0x18000440e  push    rbx
0x18000440f  push    rsi
0x180004410  push    rdi
0x180004411  push    r12
0x180004413  push    r13
0x180004415  push    r14
0x180004417  push    r15
0x180004419  mov     rbp, rsp
0x18000441c  sub     rsp, 68h
0x180004420  mov     rax, cs:__security_cookie
0x180004427  xor     rax, rsp
0x18000442a  mov     [rbp+var_18], rax
0x18000442e  mov     [rcx+8], rdx
0x180004432  lea     r13, aCdvmftmfttypeh; "CdvmftMFTTypeHandler::Init"
0x180004439  mov     [rcx+68h], rdx
0x18000443d  mov     rdi, rcx
0x180004440  mov     esi, 2AFh
0x180004445  lea     rcx, [rbp+var_30]; this
0x180004449  xor     r12d, r12d
0x18000444c  mov     r8d, esi; int
0x18000444f  mov     rdx, r13; char *
0x180004452  mov     [rbp+ppMFType], r12
0x180004456  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000445b  lea     edx, [r12+4]; unsigned int
0x180004460  mov     rcx, rdi; this
0x180004463  call    ?InitAvailableInputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableInputTypeArray(ulong)
0x180004468  mov     ebx, eax
0x18000446a  test    eax, eax
0x18000446c  jns     loc_1800044F5
0x180004472  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180004479  jnz     short loc_1800044B3
0x18000447b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180004481  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180004488  mov     rcx, rax
0x18000448b  test    rax, rax
0x18000448e  jz      short loc_1800044A5
0x180004490  mov     rdx, [rax]
0x180004493  mov     rax, [rdx+8]
0x180004497  mov     edx, 7F0h
0x18000449c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a1  test    eax, eax
0x1800044a3  jnz     short loc_1800044B3
0x1800044a5  lea     rax, off_180022080
0x1800044ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800044b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800044ba  cmp     [rcx+8], r12b
0x1800044be  jz      short loc_1800044DE
0x1800044c0  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800044c5  cmp     [rax+7CCh], ebx
0x1800044cb  jz      short loc_1800044DE
0x1800044cd  mov     r9d, ebx; int
0x1800044d0  mov     r8d, esi; int
0x1800044d3  mov     rdx, r13; char *
0x1800044d6  mov     rcx, rax; this
0x1800044d9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800044de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800044e5  jb      loc_1800047AB
0x1800044eb  mov     edx, 32h ; '2'
0x1800044f0  jmp     loc_18000478D
0x1800044f5  mov     esi, r12d
0x1800044f8  lea     rax, dword_180020150
0x1800044ff  mov     r14d, esi
0x180004502  lea     rcx, [rbp+ppMFType]; ppMFType
0x180004506  mov     [rbp+var_24], 100000h
0x18000450d  mov     [rbp+var_20], 0AA000080h
0x180004514  mov     [rbp+var_1C], 719B3800h
0x18000451b  mov     eax, [rax+r14*4]
0x18000451f  mov     [rbp+var_28], eax
0x180004522  call    cs:__imp_MFCreateMediaType
0x180004528  mov     ebx, eax
0x18000452a  test    eax, eax
0x18000452c  js      loc_180004710
0x180004532  mov     rcx, [rbp+ppMFType]
0x180004536  lea     r8, MFMediaType_Video
0x18000453d  lea     rdx, MF_MT_MAJOR_TYPE
0x180004544  mov     rax, [rcx]
0x180004547  mov     rax, [rax+0C0h]
0x18000454e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004553  mov     ebx, eax
0x180004555  test    eax, eax
0x180004557  js      loc_18000468D
0x18000455d  mov     rcx, [rbp+ppMFType]
0x180004561  lea     r8, [rbp+var_28]
0x180004565  lea     rdx, MF_MT_SUBTYPE
0x18000456c  mov     rax, [rcx]
0x18000456f  mov     rax, [rax+0C0h]
0x180004576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000457b  mov     ebx, eax
0x18000457d  test    eax, eax
0x18000457f  js      loc_180004607
0x180004585  cmp     esi, [rdi+10h]
0x180004588  jnb     short loc_1800045DB
0x18000458a  mov     rax, [rdi+18h]
0x18000458e  add     r14, r14
0x180004591  mov     r15, [rbp+ppMFType]
0x180004595  mov     rcx, [rax+r14*8]
0x180004599  test    rcx, rcx
0x18000459c  jz      short loc_1800045B2
0x18000459e  mov     rax, [rcx]
0x1800045a1  mov     rax, [rax+10h]
0x1800045a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045aa  mov     rax, [rdi+18h]
0x1800045ae  mov     [rax+r14*8], r12
0x1800045b2  mov     rax, [rdi+18h]
0x1800045b6  mov     [rax+r14*8], r15
0x1800045ba  mov     rax, [rdi+18h]
0x1800045be  mov     rcx, [rax+r14*8]
0x1800045c2  mov     rax, [rcx]
0x1800045c5  mov     rax, [rax+8]
0x1800045c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ce  mov     rax, [rdi+18h]
0x1800045d2  mov     dword ptr [rax+r14*8+8], 1
0x1800045db  mov     rcx, [rbp+ppMFType]
0x1800045df  test    rcx, rcx
0x1800045e2  jz      short loc_1800045F7
0x1800045e4  mov     rax, [rcx]
0x1800045e7  mov     rax, [rax+10h]
0x1800045eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045f0  mov     rcx, r12
0x1800045f3  mov     [rbp+ppMFType], rcx
0x1800045f7  inc     esi
0x1800045f9  cmp     esi, 4
0x1800045fc  jb      loc_1800044F8
0x180004602  jmp     loc_1800047AF
0x180004607  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x18000460e  jnz     short loc_180004648
0x180004610  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180004616  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000461d  mov     rcx, rax
0x180004620  test    rax, rax
0x180004623  jz      short loc_18000463A
0x180004625  mov     rax, [rax]
0x180004628  mov     edx, 7F0h
0x18000462d  mov     rax, [rax+8]
0x180004631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004636  test    eax, eax
0x180004638  jnz     short loc_180004648
0x18000463a  lea     rax, off_180022080
0x180004641  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180004648  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000464f  cmp     [rcx+8], r12b
0x180004653  jz      short loc_180004676
0x180004655  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x18000465a  cmp     [rax+7CCh], ebx
0x180004660  jz      short loc_180004676
0x180004662  mov     r9d, ebx; int
0x180004665  mov     r8d, 2BCh; int
0x18000466b  mov     rdx, r13; char *
0x18000466e  mov     rcx, rax; this
0x180004671  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180004676  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000467d  jb      loc_1800047AB
0x180004683  mov     edx, 35h ; '5'
0x180004688  jmp     loc_18000478D
0x18000468d  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180004694  jnz     short loc_1800046CE
0x180004696  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000469c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800046a3  mov     rcx, rax
0x1800046a6  test    rax, rax
0x1800046a9  jz      short loc_1800046C0
0x1800046ab  mov     rax, [rax]
0x1800046ae  mov     edx, 7F0h
0x1800046b3  mov     rax, [rax+8]
0x1800046b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046bc  test    eax, eax
0x1800046be  jnz     short loc_1800046CE
0x1800046c0  lea     rax, off_180022080
0x1800046c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800046ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800046d5  cmp     [rcx+8], r12b
0x1800046d9  jz      short loc_1800046FC
0x1800046db  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800046e0  cmp     [rax+7CCh], ebx
0x1800046e6  jz      short loc_1800046FC
0x1800046e8  mov     r9d, ebx; int
0x1800046eb  mov     r8d, 2BAh; int
0x1800046f1  mov     rdx, r13; char *
0x1800046f4  mov     rcx, rax; this
0x1800046f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800046fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004703  jb      loc_1800047AB
0x180004709  mov     edx, 34h ; '4'
0x18000470e  jmp     short loc_18000478D
0x180004710  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180004717  jnz     short loc_180004751
0x180004719  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000471f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180004726  mov     rcx, rax
0x180004729  test    rax, rax
0x18000472c  jz      short loc_180004743
0x18000472e  mov     rax, [rax]
0x180004731  mov     edx, 7F0h
0x180004736  mov     rax, [rax+8]
0x18000473a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473f  test    eax, eax
0x180004741  jnz     short loc_180004751
0x180004743  lea     rax, off_180022080
0x18000474a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180004751  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180004758  cmp     [rcx+8], r12b
0x18000475c  jz      short loc_18000477F
0x18000475e  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180004763  cmp     [rax+7CCh], ebx
0x180004769  jz      short loc_18000477F
0x18000476b  mov     r9d, ebx; int
0x18000476e  mov     r8d, 2B9h; int
0x180004774  mov     rdx, r13; char *
0x180004777  mov     rcx, rax; this
0x18000477a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000477f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004786  jb      short loc_1800047AB
0x180004788  mov     edx, 33h ; '3'
0x18000478d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004794  lea     r8, WPP_eab3d75b25033173348b4e1d8c19ad3b_Traceguids
0x18000479b  mov     r9, rdi
0x18000479e  mov     [rsp+68h+var_48], ebx
0x1800047a2  mov     rcx, [rcx+10h]
0x1800047a6  call    WPP_SF_qd
0x1800047ab  mov     rcx, [rbp+ppMFType]
0x1800047af  test    rcx, rcx
0x1800047b2  jz      short loc_1800047C4
0x1800047b4  mov     rax, [rcx]
0x1800047b7  mov     rax, [rax+10h]
0x1800047bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047c0  mov     [rbp+ppMFType], r12
0x1800047c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800047cb  cmp     [rcx+8], r12b
0x1800047cf  jz      short loc_1800047F3
0x1800047d1  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800047d6  mov     ecx, [rax+7C4h]
0x1800047dc  test    ecx, ecx
0x1800047de  jz      short loc_1800047F3
0x1800047e0  sub     ecx, 1
0x1800047e3  mov     [rax+7C4h], ecx
0x1800047e9  jnz     short loc_1800047F3
0x1800047eb  mov     rcx, rax; this
0x1800047ee  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x1800047f3  mov     eax, ebx
0x1800047f5  mov     rcx, [rbp+var_18]
0x1800047f9  xor     rcx, rsp; StackCookie
0x1800047fc  call    __security_check_cookie
0x180004801  add     rsp, 68h
0x180004805  pop     r15
0x180004807  pop     r14
0x180004809  pop     r13
0x18000480b  pop     r12
0x18000480d  pop     rdi
0x18000480e  pop     rsi
0x18000480f  pop     rbx
0x180004810  pop     rbp
0x180004811  retn
```
