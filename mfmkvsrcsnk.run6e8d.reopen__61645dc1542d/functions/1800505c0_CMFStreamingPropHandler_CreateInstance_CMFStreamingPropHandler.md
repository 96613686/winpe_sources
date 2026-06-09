# CMFStreamingPropHandler::CreateInstance(CMFStreamingPropHandler * *)

- ea: `0x1800505c0`
- end: `0x18005073d`
- name: `?CreateInstance@CMFStreamingPropHandler@@SAJPEAPEAV1@@Z`
- size: `381`
- prototype: `__int64 __fastcall(struct CMFStreamingPropHandler **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fe50`

## callees

- `0x180001f90`
- `0x180005ab8`
- `0x1800097f0`
- `0x18004f44c`
- `0x1800505c0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18005060d`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18005060d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050629`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800506bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050629`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800506bf`

## string_xrefs

- `0x180050680`: `CMFStreamingPropHandler::CreateInstance`
- `0x180050716`: `CMFStreamingPropHandler::CreateInstance`

## pseudocode

```c
__int64 __fastcall CMFStreamingPropHandler::CreateInstance(void ***a1)
{
  CMFStreamingPropHandler *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  CMFStreamingPropHandler *v6; // rax
  void **v7; // rdi
  __int64 v8; // rdx
  HRESULT v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax

  v2 = (CMFStreamingPropHandler *)operator new(0x20u);
  if ( v2 && (v6 = CMFStreamingPropHandler::CMFStreamingPropHandler(v2), (v7 = (void **)v6) != 0) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v6 + 24);
    v9 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, v7 + 3);
    if ( v9 >= 0 )
    {
      *a1 = v7;
    }
    else
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFStreamingPropHandler::CreateInstance", 41, v9);
      }
      (*((void (__fastcall **)(void **))*v7 + 2))(v7);
    }
  }
  else
  {
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3, v4, v5);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v17, "CMFStreamingPropHandler::CreateInstance", 40, -2147024882);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800505c0  mov     [rsp+arg_0], rbx
0x1800505c5  mov     [rsp+arg_8], rsi
0x1800505ca  push    rdi
0x1800505cb  sub     rsp, 20h
0x1800505cf  mov     rsi, rcx
0x1800505d2  mov     ecx, 20h ; ' '; Size
0x1800505d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800505dc  test    rax, rax
0x1800505df  jz      loc_1800506AE
0x1800505e5  mov     rcx, rax; this
0x1800505e8  call    ??0CMFStreamingPropHandler@@AEAA@XZ; CMFStreamingPropHandler::CMFStreamingPropHandler(void)
0x1800505ed  mov     rdi, rax
0x1800505f0  test    rax, rax
0x1800505f3  jz      loc_1800506AE
0x1800505f9  lea     rcx, [rax+18h]
0x1800505fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050602  lea     rdx, [rdi+18h]; ppv
0x180050606  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18005060d  call    cs:__imp_PSCreateMemoryPropertyStore
0x180050613  mov     ebx, eax
0x180050615  test    eax, eax
0x180050617  jns     loc_1800506A9
0x18005061d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050624  test    rcx, rcx
0x180050627  jnz     short loc_18005066A
0x180050629  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005062f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050636  mov     rcx, rax
0x180050639  test    rax, rax
0x18005063c  jz      short loc_18005065C
0x18005063e  mov     rax, [rax]
0x180050641  mov     edx, 7F0h
0x180050646  mov     rax, [rax+8]
0x18005064a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005064f  test    eax, eax
0x180050651  jz      short loc_18005065C
0x180050653  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005065a  jmp     short loc_18005066A
0x18005065c  lea     rcx, qword_1800D6F70; this
0x180050663  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005066a  cmp     byte ptr [rcx+8], 0
0x18005066e  jz      short loc_180050695
0x180050670  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050675  cmp     [rax+7CCh], ebx
0x18005067b  jz      short loc_180050695
0x18005067d  mov     r9d, ebx; int
0x180050680  lea     rdx, aCmfstreamingpr_3; "CMFStreamingPropHandler::CreateInstance"
0x180050687  mov     r8d, 29h ; ')'; int
0x18005068d  mov     rcx, rax; this
0x180050690  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050695  mov     rax, [rdi]
0x180050698  mov     rcx, rdi
0x18005069b  mov     rax, [rax+10h]
0x18005069f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506a4  jmp     loc_18005072B
0x1800506a9  mov     [rsi], rdi
0x1800506ac  jmp     short loc_18005072B
0x1800506ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800506b5  mov     ebx, 8007000Eh
0x1800506ba  test    rcx, rcx
0x1800506bd  jnz     short loc_180050700
0x1800506bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800506c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800506cc  mov     rcx, rax
0x1800506cf  test    rax, rax
0x1800506d2  jz      short loc_1800506F2
0x1800506d4  mov     rax, [rax]
0x1800506d7  mov     edx, 7F0h
0x1800506dc  mov     rax, [rax+8]
0x1800506e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506e5  test    eax, eax
0x1800506e7  jz      short loc_1800506F2
0x1800506e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800506f0  jmp     short loc_180050700
0x1800506f2  lea     rcx, qword_1800D6F70; this
0x1800506f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050700  cmp     byte ptr [rcx+8], 0
0x180050704  jz      short loc_18005072B
0x180050706  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005070b  cmp     [rax+7CCh], ebx
0x180050711  jz      short loc_18005072B
0x180050713  mov     r9d, ebx; int
0x180050716  lea     rdx, aCmfstreamingpr_3; "CMFStreamingPropHandler::CreateInstance"
0x18005071d  mov     r8d, 28h ; '('; int
0x180050723  mov     rcx, rax; this
0x180050726  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005072b  mov     rsi, [rsp+28h+arg_8]
0x180050730  mov     eax, ebx
0x180050732  mov     rbx, [rsp+28h+arg_0]
0x180050737  add     rsp, 20h
0x18005073b  pop     rdi
0x18005073c  retn
```
