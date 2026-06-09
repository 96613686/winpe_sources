# CMFStreamingPropHandler::CreateInstance(CMFStreamingPropHandler * *)

- ea: `0x1800473e4`
- end: `0x180047561`
- name: `?CreateInstance@CMFStreamingPropHandler@@SAJPEAPEAV1@@Z`
- size: `381`
- prototype: `__int64 __fastcall(struct CMFStreamingPropHandler **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800223b8`

## callees

- `0x1800018a4`
- `0x180031bdc`
- `0x180039e60`
- `0x1800462f4`
- `0x1800473e4`
- `0x180048710`
- `0x180056010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180047431`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180047431`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004744d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800474e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004744d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800474e3`

## string_xrefs

- `0x1800474a4`: `CMFStreamingPropHandler::CreateInstance`
- `0x18004753a`: `CMFStreamingPropHandler::CreateInstance`

## pseudocode

```c
__int64 __fastcall CMFStreamingPropHandler::CreateInstance(void ***a1)
{
  CMFStreamingPropHandler *v2; // rax
  __int64 v3; // rdx
  CMFStreamingPropHandler *v4; // rax
  void **v5; // rdi
  __int64 v6; // rdx
  HRESULT v7; // ebx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax

  v2 = (CMFStreamingPropHandler *)operator new(0x20u);
  if ( v2 && (v4 = CMFStreamingPropHandler::CMFStreamingPropHandler(v2), (v5 = (void **)v4) != 0) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v4 + 24);
    v7 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, v5 + 3);
    if ( v7 >= 0 )
    {
      *a1 = v5;
    }
    else
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFStreamingPropHandler::CreateInstance", 41, v7);
      }
      (*((void (__fastcall **)(void **))*v5 + 2))(v5);
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v13, "CMFStreamingPropHandler::CreateInstance", 40, -2147024882);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800473e4  mov     [rsp+arg_0], rbx
0x1800473e9  mov     [rsp+arg_8], rsi
0x1800473ee  push    rdi
0x1800473ef  sub     rsp, 20h
0x1800473f3  mov     rsi, rcx
0x1800473f6  mov     ecx, 20h ; ' '; Size
0x1800473fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047400  test    rax, rax
0x180047403  jz      loc_1800474D2
0x180047409  mov     rcx, rax; this
0x18004740c  call    ??0CMFStreamingPropHandler@@AEAA@XZ; CMFStreamingPropHandler::CMFStreamingPropHandler(void)
0x180047411  mov     rdi, rax
0x180047414  test    rax, rax
0x180047417  jz      loc_1800474D2
0x18004741d  lea     rcx, [rax+18h]
0x180047421  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047426  lea     rdx, [rdi+18h]; ppv
0x18004742a  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180047431  call    cs:__imp_PSCreateMemoryPropertyStore
0x180047437  mov     ebx, eax
0x180047439  test    eax, eax
0x18004743b  jns     loc_1800474CD
0x180047441  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047448  test    rcx, rcx
0x18004744b  jnz     short loc_18004748E
0x18004744d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180047453  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004745a  mov     rcx, rax
0x18004745d  test    rax, rax
0x180047460  jz      short loc_180047480
0x180047462  mov     rax, [rax]
0x180047465  mov     edx, 7F0h
0x18004746a  mov     rax, [rax+8]
0x18004746e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047473  test    eax, eax
0x180047475  jz      short loc_180047480
0x180047477  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004747e  jmp     short loc_18004748E
0x180047480  lea     rcx, qword_18006EB20; this
0x180047487  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004748e  cmp     byte ptr [rcx+8], 0
0x180047492  jz      short loc_1800474B9
0x180047494  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047499  cmp     [rax+7CCh], ebx
0x18004749f  jz      short loc_1800474B9
0x1800474a1  mov     r9d, ebx; int
0x1800474a4  lea     rdx, aCmfstreamingpr_3; "CMFStreamingPropHandler::CreateInstance"
0x1800474ab  mov     r8d, 29h ; ')'; int
0x1800474b1  mov     rcx, rax; this
0x1800474b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800474b9  mov     rax, [rdi]
0x1800474bc  mov     rcx, rdi
0x1800474bf  mov     rax, [rax+10h]
0x1800474c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474c8  jmp     loc_18004754F
0x1800474cd  mov     [rsi], rdi
0x1800474d0  jmp     short loc_18004754F
0x1800474d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800474d9  mov     ebx, 8007000Eh
0x1800474de  test    rcx, rcx
0x1800474e1  jnz     short loc_180047524
0x1800474e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800474e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800474f0  mov     rcx, rax
0x1800474f3  test    rax, rax
0x1800474f6  jz      short loc_180047516
0x1800474f8  mov     rax, [rax]
0x1800474fb  mov     edx, 7F0h
0x180047500  mov     rax, [rax+8]
0x180047504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047509  test    eax, eax
0x18004750b  jz      short loc_180047516
0x18004750d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047514  jmp     short loc_180047524
0x180047516  lea     rcx, qword_18006EB20; this
0x18004751d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047524  cmp     byte ptr [rcx+8], 0
0x180047528  jz      short loc_18004754F
0x18004752a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004752f  cmp     [rax+7CCh], ebx
0x180047535  jz      short loc_18004754F
0x180047537  mov     r9d, ebx; int
0x18004753a  lea     rdx, aCmfstreamingpr_3; "CMFStreamingPropHandler::CreateInstance"
0x180047541  mov     r8d, 28h ; '('; int
0x180047547  mov     rcx, rax; this
0x18004754a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004754f  mov     rsi, [rsp+28h+arg_8]
0x180047554  mov     eax, ebx
0x180047556  mov     rbx, [rsp+28h+arg_0]
0x18004755b  add     rsp, 20h
0x18004755f  pop     rdi
0x180047560  retn
```
