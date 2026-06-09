# MFMkvPropertyHandler::AddStreamDescriptorProperties(IMFStreamDescriptor *)

- ea: `0x18004d7c0`
- end: `0x18004d851`
- name: `?AddStreamDescriptorProperties@MFMkvPropertyHandler@@MEAAJPEAUIMFStreamDescriptor@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(MFMkvPropertyHandler *__hidden this, struct IMFStreamDescriptor *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800097f0`
- `0x18004d7c0`
- `0x180059fa0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d7dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d7dd`

## string_xrefs

- `0x18004d834`: `MFMkvPropertyHandler::AddStreamDescriptorProperties`

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
        v6 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18004d7c0  push    rbx
0x18004d7c2  sub     rsp, 20h
0x18004d7c6  call    ?AddStreamDescriptorProperties@CWMPropHandlerBase@@MEAAJPEAUIMFStreamDescriptor@@@Z; CWMPropHandlerBase::AddStreamDescriptorProperties(IMFStreamDescriptor *)
0x18004d7cb  mov     ebx, eax
0x18004d7cd  test    eax, eax
0x18004d7cf  jns     short loc_18004D849
0x18004d7d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d7d8  test    rcx, rcx
0x18004d7db  jnz     short loc_18004D81E
0x18004d7dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d7e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d7ea  mov     rcx, rax
0x18004d7ed  test    rax, rax
0x18004d7f0  jz      short loc_18004D810
0x18004d7f2  mov     rax, [rax]
0x18004d7f5  mov     edx, 7F0h
0x18004d7fa  mov     rax, [rax+8]
0x18004d7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d803  test    eax, eax
0x18004d805  jz      short loc_18004D810
0x18004d807  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d80e  jmp     short loc_18004D81E
0x18004d810  lea     rcx, qword_1800D6F70; this
0x18004d817  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d81e  cmp     byte ptr [rcx+8], 0
0x18004d822  jz      short loc_18004D849
0x18004d824  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d829  cmp     [rax+7CCh], ebx
0x18004d82f  jz      short loc_18004D849
0x18004d831  mov     r9d, ebx; int
0x18004d834  lea     rdx, aMfmkvpropertyh; "MFMkvPropertyHandler::AddStreamDescript"...
0x18004d83b  mov     r8d, 5Ah ; 'Z'; int
0x18004d841  mov     rcx, rax; this
0x18004d844  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d849  mov     eax, ebx
0x18004d84b  add     rsp, 20h
0x18004d84f  pop     rbx
0x18004d850  retn
```
