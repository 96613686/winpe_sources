# CMFStreamingPropHandler::CreateInstance(CMFStreamingPropHandler * *)

- ea: `0x180052850`
- end: `0x1800529e3`
- name: `?CreateInstance@CMFStreamingPropHandler@@SAJPEAPEAV1@@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct CMFStreamingPropHandler **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010540`

## callees

- `0x180001fb0`
- `0x180005c68`
- `0x180009b04`
- `0x180051674`
- `0x180052850`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18005289d`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18005289d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800528bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005295e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800528bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005295e`

## string_xrefs

- `0x18005291c`: `CMFStreamingPropHandler::CreateInstance`
- `0x1800529bb`: `CMFStreamingPropHandler::CreateInstance`

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
          v12 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v15 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180052850  mov     [rsp+arg_0], rbx
0x180052855  mov     [rsp+arg_8], rsi
0x18005285a  push    rdi
0x18005285b  sub     rsp, 20h
0x18005285f  mov     rsi, rcx
0x180052862  mov     ecx, 20h ; ' '; Size
0x180052867  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005286c  test    rax, rax
0x18005286f  jz      loc_18005294D
0x180052875  mov     rcx, rax; this
0x180052878  call    ??0CMFStreamingPropHandler@@AEAA@XZ; CMFStreamingPropHandler::CMFStreamingPropHandler(void)
0x18005287d  mov     rdi, rax
0x180052880  test    rax, rax
0x180052883  jz      loc_18005294D
0x180052889  lea     rcx, [rax+18h]
0x18005288d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052892  lea     rdx, [rdi+18h]; ppv
0x180052896  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18005289d  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800528a4  nop     dword ptr [rax+rax+00h]
0x1800528a9  mov     ebx, eax
0x1800528ab  test    eax, eax
0x1800528ad  jns     loc_180052945
0x1800528b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800528ba  test    rcx, rcx
0x1800528bd  jnz     short loc_180052906
0x1800528bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800528c6  nop     dword ptr [rax+rax+00h]
0x1800528cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800528d2  mov     rcx, rax
0x1800528d5  test    rax, rax
0x1800528d8  jz      short loc_1800528F8
0x1800528da  mov     rax, [rax]
0x1800528dd  mov     edx, 7F0h
0x1800528e2  mov     rax, [rax+8]
0x1800528e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528eb  test    eax, eax
0x1800528ed  jz      short loc_1800528F8
0x1800528ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800528f6  jmp     short loc_180052906
0x1800528f8  lea     rcx, qword_1800DBF70; this
0x1800528ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052906  cmp     byte ptr [rcx+8], 0
0x18005290a  jz      short loc_180052931
0x18005290c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052911  cmp     [rax+7CCh], ebx
0x180052917  jz      short loc_180052931
0x180052919  mov     r9d, ebx; int
0x18005291c  lea     rdx, aCmfstreamingpr_3; "CMFStreamingPropHandler::CreateInstance"
0x180052923  mov     r8d, 29h ; ')'; int
0x180052929  mov     rcx, rax; this
0x18005292c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052931  mov     rax, [rdi]
0x180052934  mov     rcx, rdi
0x180052937  mov     rax, [rax+10h]
0x18005293b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052940  jmp     loc_1800529D0
0x180052945  mov     [rsi], rdi
0x180052948  jmp     loc_1800529D0
0x18005294d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052954  mov     ebx, 8007000Eh
0x180052959  test    rcx, rcx
0x18005295c  jnz     short loc_1800529A5
0x18005295e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052965  nop     dword ptr [rax+rax+00h]
0x18005296a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052971  mov     rcx, rax
0x180052974  test    rax, rax
0x180052977  jz      short loc_180052997
0x180052979  mov     rax, [rax]
0x18005297c  mov     edx, 7F0h
0x180052981  mov     rax, [rax+8]
0x180052985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005298a  test    eax, eax
0x18005298c  jz      short loc_180052997
0x18005298e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052995  jmp     short loc_1800529A5
0x180052997  lea     rcx, qword_1800DBF70; this
0x18005299e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800529a5  cmp     byte ptr [rcx+8], 0
0x1800529a9  jz      short loc_1800529D0
0x1800529ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800529b0  cmp     [rax+7CCh], ebx
0x1800529b6  jz      short loc_1800529D0
0x1800529b8  mov     r9d, ebx; int
0x1800529bb  lea     rdx, aCmfstreamingpr_3; "CMFStreamingPropHandler::CreateInstance"
0x1800529c2  mov     r8d, 28h ; '('; int
0x1800529c8  mov     rcx, rax; this
0x1800529cb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800529d0  mov     rsi, [rsp+28h+arg_8]
0x1800529d5  mov     eax, ebx
0x1800529d7  mov     rbx, [rsp+28h+arg_0]
0x1800529dc  add     rsp, 20h
0x1800529e0  pop     rdi
0x1800529e1  retn
```
