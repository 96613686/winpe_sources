# MFMkvPropertyHandler::AddStreamDescriptorProperties(IMFStreamDescriptor *)

- ea: `0x18004f800`
- end: `0x18004f898`
- name: `?AddStreamDescriptorProperties@MFMkvPropertyHandler@@MEAAJPEAUIMFStreamDescriptor@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(MFMkvPropertyHandler *__hidden this, struct IMFStreamDescriptor *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180009b04`
- `0x18004f800`
- `0x18005c5f0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f81d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f81d`

## string_xrefs

- `0x18004f87a`: `MFMkvPropertyHandler::AddStreamDescriptorProperties`

## pseudocode

```c
__int64 __fastcall MFMkvPropertyHandler::AddStreamDescriptorProperties(
        MFMkvPropertyHandler *this,
        struct IMFStreamDescriptor *a2)
{
  __int64 v2; // rdx
  int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax

  v3 = CWMPropHandlerBase::AddStreamDescriptorProperties(this, a2);
  if ( v3 < 0 )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2, v4, v5);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MFMkvPropertyHandler::AddStreamDescriptorProperties",
          90,
          v3);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004f800  push    rbx
0x18004f802  sub     rsp, 20h
0x18004f806  call    ?AddStreamDescriptorProperties@CWMPropHandlerBase@@MEAAJPEAUIMFStreamDescriptor@@@Z; CWMPropHandlerBase::AddStreamDescriptorProperties(IMFStreamDescriptor *)
0x18004f80b  mov     ebx, eax
0x18004f80d  test    eax, eax
0x18004f80f  jns     short loc_18004F88F
0x18004f811  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f818  test    rcx, rcx
0x18004f81b  jnz     short loc_18004F864
0x18004f81d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f824  nop     dword ptr [rax+rax+00h]
0x18004f829  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f830  mov     rcx, rax
0x18004f833  test    rax, rax
0x18004f836  jz      short loc_18004F856
0x18004f838  mov     rax, [rax]
0x18004f83b  mov     edx, 7F0h
0x18004f840  mov     rax, [rax+8]
0x18004f844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f849  test    eax, eax
0x18004f84b  jz      short loc_18004F856
0x18004f84d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f854  jmp     short loc_18004F864
0x18004f856  lea     rcx, qword_1800DBF70; this
0x18004f85d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f864  cmp     byte ptr [rcx+8], 0
0x18004f868  jz      short loc_18004F88F
0x18004f86a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f86f  cmp     [rax+7CCh], ebx
0x18004f875  jz      short loc_18004F88F
0x18004f877  mov     r9d, ebx; int
0x18004f87a  lea     rdx, aMfmkvpropertyh; "MFMkvPropertyHandler::AddStreamDescript"...
0x18004f881  mov     r8d, 5Ah ; 'Z'; int
0x18004f887  mov     rcx, rax; this
0x18004f88a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004f88f  mov     eax, ebx
0x18004f891  add     rsp, 20h
0x18004f895  pop     rbx
0x18004f896  retn
```
