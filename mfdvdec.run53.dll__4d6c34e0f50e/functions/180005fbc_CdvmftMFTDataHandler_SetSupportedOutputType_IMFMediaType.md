# CdvmftMFTDataHandler::SetSupportedOutputType(IMFMediaType *)

- ea: `0x180005fbc`
- end: `0x1800065bf`
- name: `?SetSupportedOutputType@CdvmftMFTDataHandler@@QEAAJPEAUIMFMediaType@@@Z`
- size: `1539`
- prototype: `__int64 __fastcall(CdvmftMFTDataHandler *__hidden this, struct IMFMediaType *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180002ac0`
- `0x180005340`

## callees

- `0x180001580`
- `0x180001ec8`
- `0x180002200`
- `0x180005fbc`
- `0x180006950`
- `0x1800082ec`
- `0x180008358`
- `0x18001e010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800061e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006272`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006304`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006396`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006428`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800064ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800061e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006272`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006304`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006396`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006428`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800064ba`
- `MFPlat!MFCreateMediaType` at `0x180006034`
- `MFPlat!MFCreateMediaType` at `0x180006034`

## pseudocode

```c
__int64 __fastcall CdvmftMFTDataHandler::SetSupportedOutputType(CdvmftMFTDataHandler *this, struct IMFMediaType *a2)
{
  unsigned int v2; // esi
  HRESULT v5; // ebx
  __int64 v6; // rdi
  IMFMediaType *v7; // r12
  __int64 v8; // rcx
  __int64 v9; // rcx
  struct CallStackContext *v10; // rax
  int v11; // ecx
  int v12; // ecx
  void ***v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  struct CallStackContext *v27; // rax
  int v28; // ecx
  int v29; // ecx
  IMFMediaType *ppMFType; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v32[8]; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v33[4]; // [rsp+40h] [rbp-20h] BYREF

  ppMFType = 0;
  v2 = 0;
  while ( 1 )
  {
    v33[1] = 0x100000;
    v33[2] = -1442840448;
    v33[3] = 1905997824;
    v33[0] = *(_DWORD *)&aYuy2[4 * v2];
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v32,
      "CdvmftMFTDataHandler::SetSupportedOutputType",
      300);
    v5 = MFCreateMediaType(&ppMFType);
    if ( v5 < 0 )
    {
      v13 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v13 = (void ***)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &off_180022080;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v26 = CallStackTracing::Context((CallStackTracing *)v13);
        if ( *((_DWORD *)v26 + 499) != v5 )
          CallStackContext::TraceFailure(v26, "CdvmftMFTDataHandler::SetSupportedOutputType", 300, v5);
        v13 = (void ***)CallStackTracing::s_wpInstance;
      }
      if ( g_wppLevels )
      {
        v16 = 16;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    v5 = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))a2->lpVtbl->CopyAllItems)(a2, ppMFType);
    if ( v5 < 0 )
    {
      v13 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v13 = (void ***)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &off_180022080;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v24 = CallStackTracing::Context((CallStackTracing *)v13);
        if ( *((_DWORD *)v24 + 499) != v5 )
          CallStackContext::TraceFailure(v24, "CdvmftMFTDataHandler::SetSupportedOutputType", 301, v5);
        v13 = (void ***)CallStackTracing::s_wpInstance;
      }
      if ( g_wppLevels )
      {
        v16 = 17;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    v5 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _DWORD *))ppMFType->lpVtbl->SetGUID)(
           ppMFType,
           &MF_MT_SUBTYPE,
           v33);
    if ( v5 < 0 )
    {
      v13 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v13 = (void ***)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &off_180022080;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v22 = CallStackTracing::Context((CallStackTracing *)v13);
        if ( *((_DWORD *)v22 + 499) != v5 )
          CallStackContext::TraceFailure(v22, "CdvmftMFTDataHandler::SetSupportedOutputType", 303, v5);
        v13 = (void ***)CallStackTracing::s_wpInstance;
      }
      if ( g_wppLevels )
      {
        v16 = 18;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    v5 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
           ppMFType,
           &MF_MT_INTERLACE_MODE,
           7);
    if ( v5 < 0 )
    {
      v13 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v13 = (void ***)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &off_180022080;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v20 = CallStackTracing::Context((CallStackTracing *)v13);
        if ( *((_DWORD *)v20 + 499) != v5 )
          CallStackContext::TraceFailure(v20, "CdvmftMFTDataHandler::SetSupportedOutputType", 304, v5);
        v13 = (void ***)CallStackTracing::s_wpInstance;
      }
      if ( g_wppLevels )
      {
        v16 = 19;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    v5 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
           ppMFType,
           &MF_MT_ALL_SAMPLES_INDEPENDENT,
           1);
    if ( v5 < 0 )
      break;
    v5 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, unsigned __int64))ppMFType->lpVtbl->SetUINT64)(
           ppMFType,
           &MF_MT_PIXEL_ASPECT_RATIO,
           *((unsigned int *)this + 31) | ((unsigned __int64)*((unsigned int *)this + 30) << 32));
    if ( v5 < 0 )
    {
      v13 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (void ***)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &off_180022080;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::Context((CallStackTracing *)v13);
        if ( *((_DWORD *)v15 + 499) != v5 )
          CallStackContext::TraceFailure(v15, "CdvmftMFTDataHandler::SetSupportedOutputType", 307, v5);
        v13 = (void ***)CallStackTracing::s_wpInstance;
      }
      if ( g_wppLevels )
      {
        v16 = 21;
LABEL_86:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_eab3d75b25033173348b4e1d8c19ad3b_Traceguids, this, v5);
        v13 = (void ***)CallStackTracing::s_wpInstance;
        goto LABEL_87;
      }
      goto LABEL_87;
    }
    v6 = *((_QWORD *)this + 4);
    if ( v2 < *(_DWORD *)(v6 + 32) )
    {
      v7 = ppMFType;
      v8 = *(_QWORD *)(*(_QWORD *)(v6 + 40) + 16LL * v2);
      if ( v8 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        *(_QWORD *)(*(_QWORD *)(v6 + 40) + 16LL * v2) = 0;
      }
      *(_QWORD *)(*(_QWORD *)(v6 + 40) + 16LL * v2) = v7;
      v9 = *(_QWORD *)(*(_QWORD *)(v6 + 40) + 16LL * v2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      *(_DWORD *)(*(_QWORD *)(v6 + 40) + 16LL * v2 + 8) = 1;
    }
    if ( ppMFType )
    {
      ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
      ppMFType = 0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v10 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
      v11 = *((_DWORD *)v10 + 497);
      if ( v11 )
      {
        v12 = v11 - 1;
        *((_DWORD *)v10 + 497) = v12;
        if ( !v12 )
          CallStackContext::ClearState(v10);
      }
    }
    if ( ++v2 )
      goto LABEL_91;
  }
  v13 = (void ***)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v13 = (void ***)CallStackTracing::s_wpInstance;
    }
    else
    {
      v13 = &off_180022080;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v18 = CallStackTracing::Context((CallStackTracing *)v13);
    if ( *((_DWORD *)v18 + 499) != v5 )
      CallStackContext::TraceFailure(v18, "CdvmftMFTDataHandler::SetSupportedOutputType", 305, v5);
    v13 = (void ***)CallStackTracing::s_wpInstance;
  }
  if ( g_wppLevels )
  {
    v16 = 20;
    goto LABEL_86;
  }
LABEL_87:
  if ( *((_BYTE *)v13 + 8) )
  {
    v27 = CallStackTracing::Context((CallStackTracing *)v13);
    v28 = *((_DWORD *)v27 + 497);
    if ( v28 )
    {
      v29 = v28 - 1;
      *((_DWORD *)v27 + 497) = v29;
      if ( !v29 )
        CallStackContext::ClearState(v27);
    }
  }
LABEL_91:
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005fbc  mov     [rsp-38h+arg_10], rbx
0x180005fc1  push    rbp
0x180005fc2  push    rsi
0x180005fc3  push    rdi
0x180005fc4  push    r12
0x180005fc6  push    r13
0x180005fc8  push    r14
0x180005fca  push    r15
0x180005fcc  mov     rbp, rsp
0x180005fcf  sub     rsp, 60h
0x180005fd3  mov     rax, cs:__security_cookie
0x180005fda  xor     rax, rsp
0x180005fdd  mov     [rbp+var_10], rax
0x180005fe1  xor     r12d, r12d
0x180005fe4  lea     rdi, aCdvmftmftdatah; "CdvmftMFTDataHandler::SetSupportedOutpu"...
0x180005feb  mov     [rbp+ppMFType], r12
0x180005fef  mov     esi, r12d
0x180005ff2  mov     r13, rdx
0x180005ff5  mov     r15, rcx
0x180005ff8  lea     rax, aYuy2; "YUY2"
0x180005fff  mov     r14d, esi
0x180006002  mov     r8d, 12Ch; int
0x180006008  mov     [rbp+var_1C], 100000h
0x18000600f  mov     rdx, rdi; char *
0x180006012  mov     [rbp+var_18], 0AA000080h
0x180006019  lea     rcx, [rbp+var_28]; this
0x18000601d  mov     [rbp+var_14], 719B3800h
0x180006024  mov     eax, [rax+r14*4]
0x180006028  mov     [rbp+var_20], eax
0x18000602b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180006030  lea     rcx, [rbp+ppMFType]; ppMFType
0x180006034  call    cs:__imp_MFCreateMediaType
0x18000603a  mov     ebx, eax
0x18000603c  test    eax, eax
0x18000603e  js      loc_1800064AE
0x180006044  mov     rax, [r13+0]
0x180006048  mov     rcx, r13
0x18000604b  mov     rdx, [rbp+ppMFType]
0x18000604f  mov     rax, [rax+100h]
0x180006056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000605b  mov     ebx, eax
0x18000605d  test    eax, eax
0x18000605f  js      loc_18000641C
0x180006065  mov     rcx, [rbp+ppMFType]
0x180006069  lea     r8, [rbp+var_20]
0x18000606d  lea     rdx, MF_MT_SUBTYPE
0x180006074  mov     rax, [rcx]
0x180006077  mov     rax, [rax+0C0h]
0x18000607e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006083  mov     ebx, eax
0x180006085  test    eax, eax
0x180006087  js      loc_18000638A
0x18000608d  mov     rcx, [rbp+ppMFType]
0x180006091  lea     rdx, MF_MT_INTERLACE_MODE
0x180006098  mov     r8d, 7
0x18000609e  mov     rax, [rcx]
0x1800060a1  mov     rax, [rax+0A8h]
0x1800060a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ad  mov     ebx, eax
0x1800060af  test    eax, eax
0x1800060b1  js      loc_1800062F8
0x1800060b7  mov     rcx, [rbp+ppMFType]
0x1800060bb  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x1800060c2  mov     r8d, 1
0x1800060c8  mov     rax, [rcx]
0x1800060cb  mov     rax, [rax+0A8h]
0x1800060d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d7  mov     ebx, eax
0x1800060d9  test    eax, eax
0x1800060db  js      loc_180006266
0x1800060e1  mov     eax, [r15+7Ch]
0x1800060e5  lea     rdx, MF_MT_PIXEL_ASPECT_RATIO
0x1800060ec  mov     rcx, [rbp+ppMFType]
0x1800060f0  mov     r8d, [r15+78h]
0x1800060f4  shl     r8, 20h
0x1800060f8  or      r8, rax
0x1800060fb  mov     r9, [rcx]
0x1800060fe  mov     rax, [r9+0B0h]
0x180006105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610a  mov     ebx, eax
0x18000610c  test    eax, eax
0x18000610e  js      loc_1800061D4
0x180006114  mov     rdi, [r15+20h]
0x180006118  cmp     esi, [rdi+20h]
0x18000611b  jnb     short loc_180006175
0x18000611d  mov     rax, [rdi+28h]
0x180006121  add     r14, r14
0x180006124  mov     r12, [rbp+ppMFType]
0x180006128  mov     rcx, [rax+r14*8]
0x18000612c  test    rcx, rcx
0x18000612f  jz      short loc_180006149
0x180006131  mov     rax, [rcx]
0x180006134  mov     rax, [rax+10h]
0x180006138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000613d  mov     rax, [rdi+28h]
0x180006141  mov     qword ptr [rax+r14*8], 0
0x180006149  mov     rax, [rdi+28h]
0x18000614d  mov     [rax+r14*8], r12
0x180006151  mov     rax, [rdi+28h]
0x180006155  mov     rcx, [rax+r14*8]
0x180006159  mov     rax, [rcx]
0x18000615c  mov     rax, [rax+8]
0x180006160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006165  mov     rax, [rdi+28h]
0x180006169  xor     r12d, r12d
0x18000616c  mov     dword ptr [rax+r14*8+8], 1
0x180006175  mov     rcx, [rbp+ppMFType]
0x180006179  test    rcx, rcx
0x18000617c  jz      short loc_18000618E
0x18000617e  mov     rax, [rcx]
0x180006181  mov     rax, [rax+10h]
0x180006185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000618a  mov     [rbp+ppMFType], r12
0x18000618e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180006195  cmp     [rcx+8], r12b
0x180006199  jz      short loc_1800061BD
0x18000619b  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800061a0  mov     ecx, [rax+7C4h]
0x1800061a6  test    ecx, ecx
0x1800061a8  jz      short loc_1800061BD
0x1800061aa  sub     ecx, 1
0x1800061ad  mov     [rax+7C4h], ecx
0x1800061b3  jnz     short loc_1800061BD
0x1800061b5  mov     rcx, rax; this
0x1800061b8  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x1800061bd  inc     esi
0x1800061bf  lea     rdi, aCdvmftmftdatah; "CdvmftMFTDataHandler::SetSupportedOutpu"...
0x1800061c6  cmp     esi, 1
0x1800061c9  jb      loc_180005FF8
0x1800061cf  jmp     loc_180006584
0x1800061d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800061db  test    rcx, rcx
0x1800061de  jnz     short loc_180006221
0x1800061e0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800061e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800061ed  mov     rcx, rax
0x1800061f0  test    rax, rax
0x1800061f3  jz      short loc_180006213
0x1800061f5  mov     rax, [rax]
0x1800061f8  mov     edx, 7F0h
0x1800061fd  mov     rax, [rax+8]
0x180006201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006206  test    eax, eax
0x180006208  jz      short loc_180006213
0x18000620a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180006211  jmp     short loc_180006221
0x180006213  lea     rcx, off_180022080; this
0x18000621a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180006221  cmp     [rcx+8], r12b
0x180006225  jz      short loc_18000624F
0x180006227  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x18000622c  cmp     [rax+7CCh], ebx
0x180006232  jz      short loc_180006248
0x180006234  mov     r9d, ebx; int
0x180006237  mov     r8d, 133h; int
0x18000623d  mov     rdx, rdi; char *
0x180006240  mov     rcx, rax; this
0x180006243  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180006248  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000624f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180006256  jb      loc_18000655C
0x18000625c  mov     edx, 15h
0x180006261  jmp     loc_180006537
0x180006266  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000626d  test    rcx, rcx
0x180006270  jnz     short loc_1800062B3
0x180006272  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180006278  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000627f  mov     rcx, rax
0x180006282  test    rax, rax
0x180006285  jz      short loc_1800062A5
0x180006287  mov     rax, [rax]
0x18000628a  mov     edx, 7F0h
0x18000628f  mov     rax, [rax+8]
0x180006293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006298  test    eax, eax
0x18000629a  jz      short loc_1800062A5
0x18000629c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800062a3  jmp     short loc_1800062B3
0x1800062a5  lea     rcx, off_180022080; this
0x1800062ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800062b3  cmp     [rcx+8], r12b
0x1800062b7  jz      short loc_1800062E1
0x1800062b9  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800062be  cmp     [rax+7CCh], ebx
0x1800062c4  jz      short loc_1800062DA
0x1800062c6  mov     r9d, ebx; int
0x1800062c9  mov     r8d, 131h; int
0x1800062cf  mov     rdx, rdi; char *
0x1800062d2  mov     rcx, rax; this
0x1800062d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800062da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800062e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800062e8  jb      loc_18000655C
0x1800062ee  mov     edx, 14h
0x1800062f3  jmp     loc_180006537
0x1800062f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800062ff  test    rcx, rcx
0x180006302  jnz     short loc_180006345
0x180006304  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000630a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006311  mov     rcx, rax
0x180006314  test    rax, rax
0x180006317  jz      short loc_180006337
0x180006319  mov     rax, [rax]
0x18000631c  mov     edx, 7F0h
0x180006321  mov     rax, [rax+8]
0x180006325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000632a  test    eax, eax
0x18000632c  jz      short loc_180006337
0x18000632e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180006335  jmp     short loc_180006345
0x180006337  lea     rcx, off_180022080; this
0x18000633e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180006345  cmp     [rcx+8], r12b
0x180006349  jz      short loc_180006373
0x18000634b  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180006350  cmp     [rax+7CCh], ebx
0x180006356  jz      short loc_18000636C
0x180006358  mov     r9d, ebx; int
0x18000635b  mov     r8d, 130h; int
0x180006361  mov     rdx, rdi; char *
0x180006364  mov     rcx, rax; this
0x180006367  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000636c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180006373  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000637a  jb      loc_18000655C
0x180006380  mov     edx, 13h
0x180006385  jmp     loc_180006537
0x18000638a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180006391  test    rcx, rcx
0x180006394  jnz     short loc_1800063D7
0x180006396  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000639c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800063a3  mov     rcx, rax
0x1800063a6  test    rax, rax
0x1800063a9  jz      short loc_1800063C9
0x1800063ab  mov     rax, [rax]
0x1800063ae  mov     edx, 7F0h
0x1800063b3  mov     rax, [rax+8]
0x1800063b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063bc  test    eax, eax
0x1800063be  jz      short loc_1800063C9
0x1800063c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800063c7  jmp     short loc_1800063D7
0x1800063c9  lea     rcx, off_180022080; this
0x1800063d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800063d7  cmp     [rcx+8], r12b
0x1800063db  jz      short loc_180006405
0x1800063dd  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800063e2  cmp     [rax+7CCh], ebx
0x1800063e8  jz      short loc_1800063FE
0x1800063ea  mov     r9d, ebx; int
0x1800063ed  mov     r8d, 12Fh; int
0x1800063f3  mov     rdx, rdi; char *
0x1800063f6  mov     rcx, rax; this
0x1800063f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800063fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180006405  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000640c  jb      loc_18000655C
0x180006412  mov     edx, 12h
0x180006417  jmp     loc_180006537
0x18000641c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180006423  test    rcx, rcx
0x180006426  jnz     short loc_180006469
0x180006428  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000642e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006435  mov     rcx, rax
0x180006438  test    rax, rax
0x18000643b  jz      short loc_18000645B
0x18000643d  mov     rax, [rax]
0x180006440  mov     edx, 7F0h
0x180006445  mov     rax, [rax+8]
0x180006449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000644e  test    eax, eax
0x180006450  jz      short loc_18000645B
0x180006452  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180006459  jmp     short loc_180006469
0x18000645b  lea     rcx, off_180022080; this
0x180006462  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180006469  cmp     [rcx+8], r12b
0x18000646d  jz      short loc_180006497
0x18000646f  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180006474  cmp     [rax+7CCh], ebx
0x18000647a  jz      short loc_180006490
0x18000647c  mov     r9d, ebx; int
0x18000647f  mov     r8d, 12Dh; int
0x180006485  mov     rdx, rdi; char *
0x180006488  mov     rcx, rax; this
0x18000648b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180006490  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180006497  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000649e  jb      loc_18000655C
0x1800064a4  mov     edx, 11h
0x1800064a9  jmp     loc_180006537
0x1800064ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800064b5  test    rcx, rcx
0x1800064b8  jnz     short loc_1800064FB
0x1800064ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800064c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
