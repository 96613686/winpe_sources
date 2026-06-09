# CGPService::GetLastReplicationIssue(ushort const *)

- ea: `0x180084e38`
- end: `0x180085276`
- name: `?GetLastReplicationIssue@CGPService@@AEAAPEAGPEBG@Z`
- size: `1086`
- prototype: `unsigned __int16 *(CGPService *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800853d4`

## callees

- `0x18000a504`
- `0x18004b210`
- `0x180075ec0`
- `0x180084e38`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008515d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008518d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800851b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008515d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008518d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800851b3`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180085025`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180085025`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180084faa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180084faa`
- `OLEAUT32!__imp_SysFreeString` at `0x18008525b`
- `OLEAUT32!__imp_SysFreeString` at `0x18008525b`
- `wevtapi!EvtCreateRenderContext` at `0x180084ea6`
- `wevtapi!EvtCreateRenderContext` at `0x180084ea6`
- `wevtapi!EvtRender` at `0x180084f85`
- `wevtapi!EvtRender` at `0x180084fdc`
- `wevtapi!EvtRender` at `0x180084f85`
- `wevtapi!EvtRender` at `0x180084fdc`
- `wevtapi!EvtQuery` at `0x180084e7d`
- `wevtapi!EvtQuery` at `0x180084e7d`
- `wevtapi!EvtClose` at `0x180085129`
- `wevtapi!EvtClose` at `0x180085228`
- `wevtapi!EvtClose` at `0x180085244`
- `wevtapi!EvtClose` at `0x180085252`
- `wevtapi!EvtClose` at `0x180085129`
- `wevtapi!EvtClose` at `0x180085228`
- `wevtapi!EvtClose` at `0x180085244`
- `wevtapi!EvtClose` at `0x180085252`
- `wevtapi!EvtNext` at `0x180084f3a`
- `wevtapi!EvtNext` at `0x180084f3a`

## string_xrefs

- `0x180084e6d`: `Event/System[EventID=4302 and TimeCreated[timediff(@SystemTime) <= 600000]]`
- `0x180084ed6`: `GetLastReplicationIssue: EvtCreateRenderContext failed with %d`
- `0x180084f0d`: `GetLastReplicationIssue: EvtCreateRenderContext failed with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BSTR __fastcall CGPService::GetLastReplicationIssue(CGPService *this, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rdi
  EVT_HANDLE v3; // r12
  EVT_HANDLE RenderContext; // rsi
  void (*v5)(unsigned int, const unsigned __int16 *, ...); // rbx
  __int64 v6; // r8
  DWORD v7; // eax
  DWORD i; // r15d
  DWORD v9; // ebx
  const OLECHAR **v10; // r14
  unsigned int v11; // ebx
  void (*v12)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // ebx
  DWORD j; // eax
  void *v18; // rcx
  HANDLE Events; // [rsp+50h] [rbp-28h] BYREF
  const OLECHAR **v21; // [rsp+58h] [rbp-20h] BYREF
  BSTR v22; // [rsp+60h] [rbp-18h] BYREF
  CGPService *PropertyCount; // [rsp+C0h] [rbp+48h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+50h]
  DWORD Returned; // [rsp+D0h] [rbp+58h] BYREF
  DWORD BufferUsed; // [rsp+D8h] [rbp+60h] BYREF

  v24 = a2;
  PropertyCount = this;
  v2 = a2;
  v22 = 0;
  Events = 0;
  Returned = 0;
  v3 = EvtQuery(
         0,
         L"DFS Replication",
         L"Event/System[EventID=4302 and TimeCreated[timediff(@SystemTime) <= 600000]]",
         0x201u);
  if ( v3 )
  {
    RenderContext = EvtCreateRenderContext(0, 0, 2u);
    if ( RenderContext )
    {
      while ( EvtNext(v3, 1u, &Events, 0xFFFFFFFF, 0, &Returned) )
      {
        for ( i = 0; i < Returned; ++i )
        {
          v21 = 0;
          BufferUsed = 0;
          LODWORD(PropertyCount) = 0;
          if ( !EvtRender(RenderContext, *(&Events + i), 0, 0, 0, &BufferUsed, (PDWORD)&PropertyCount) )
          {
            if ( GetLastError() != 122 )
              goto LABEL_43;
            v9 = BufferUsed;
            v10 = (const OLECHAR **)LocalAlloc(0x40u, BufferUsed);
            v21 = v10;
            if ( !EvtRender(RenderContext, *(&Events + i), 0, v9, v10, &BufferUsed, (PDWORD)&PropertyCount) )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v12 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  LastError = GetLastError();
                  v12(2u, L"GetLastReplicationIssue:  EvtRender failed with %d", LastError);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  v14 = GetLastError();
                  RedirectDebugMsg(2u, L"GetLastReplicationIssue:  EvtRender failed with %d", v14);
                }
              }
LABEL_43:
              XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v21);
              goto LABEL_51;
            }
            if ( (_DWORD)PropertyCount == 8 && CompareStringEx(&DomainName, 1u, v2, -1, v10[12], -1, 0, 0, 0) == 2 )
            {
              v11 = 0;
              if ( (_DWORD)PropertyCount )
              {
                do
                {
                  if ( HIDWORD(v10[2 * v11 + 1]) != 1 && *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(2u, L"GetLastReplicationIssue(%d):  %d != EvtVarTypeString ", v11);
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(2u, L"GetLastReplicationIssue(%d):  %d != EvtVarTypeString ", v11);
                    }
                  }
                  if ( HIDWORD(v10[2 * v11 + 1]) == 1 && *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(4u, L"GetLastReplicationIssue: Data(%d) = %s", v11, v10[2 * v11]);
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(4u, L"GetLastReplicationIssue: Data(%d) = %s", v11, v10[2 * v11]);
                    }
                  }
                  ++v11;
                }
                while ( v11 < (unsigned int)PropertyCount );
                v2 = v24;
              }
              XBStr::operator=(&v22, v10[2]);
            }
          }
          EvtClose(*(&Events + i));
          *(&Events + i) = 0;
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v21);
        }
      }
      v15 = GetLastError();
      if ( v15 != 259 && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"GetLastReplicationIssue:  EvtNext failed with %d", v15);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"GetLastReplicationIssue:  EvtNext failed with %d", v15);
        }
      }
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v5 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v6 = GetLastError();
        v5(2u, L"GetLastReplicationIssue: EvtCreateRenderContext failed with %d", v6);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v7 = GetLastError();
        RedirectDebugMsg(2u, L"GetLastReplicationIssue: EvtCreateRenderContext failed with %d", v7);
      }
    }
  }
  else
  {
    RenderContext = 0;
    GetLastError();
  }
LABEL_51:
  v16 = 0;
  for ( j = Returned; v16 < j; ++v16 )
  {
    v18 = *(&Events + v16);
    if ( v18 )
    {
      EvtClose(v18);
      *(&Events + v16) = 0;
      j = Returned;
    }
  }
  if ( v3 )
    EvtClose(v3);
  if ( RenderContext )
    EvtClose(RenderContext);
  SysFreeString(0);
  return v22;
}

```

## disassembly

```asm
0x180084e38  mov     [rsp-40h+arg_8], rdx
0x180084e3d  mov     [rsp-40h+arg_0], rcx
0x180084e42  push    rbp
0x180084e43  push    rbx
0x180084e44  push    rsi
0x180084e45  push    rdi
0x180084e46  push    r12
0x180084e48  push    r13
0x180084e4a  push    r14
0x180084e4c  push    r15
0x180084e4e  mov     rbp, rsp
0x180084e51  sub     rsp, 78h
0x180084e55  mov     rdi, rdx
0x180084e58  xor     r14d, r14d
0x180084e5b  mov     [rbp+var_18], r14
0x180084e5f  mov     [rbp+Events], r14
0x180084e63  mov     [rbp+arg_10], r14d
0x180084e67  mov     r9d, 201h; Flags
0x180084e6d  lea     r8, Query; "Event/System[EventID=4302 and TimeCreat"...
0x180084e74  lea     rdx, Path; "DFS Replication"
0x180084e7b  xor     ecx, ecx; Session
0x180084e7d  call    cs:__imp_EvtQuery
0x180084e83  mov     r12, rax
0x180084e86  test    rax, rax
0x180084e89  jnz     short loc_180084E99
0x180084e8b  mov     esi, r14d
0x180084e8e  call    cs:__imp_GetLastError
0x180084e94  jmp     loc_180085212
0x180084e99  mov     r15d, 2
0x180084e9f  mov     r8d, r15d; Flags
0x180084ea2  xor     edx, edx; ValuePaths
0x180084ea4  xor     ecx, ecx; ValuePathsCount
0x180084ea6  call    cs:__imp_EvtCreateRenderContext
0x180084eac  mov     rsi, rax
0x180084eaf  test    rax, rax
0x180084eb2  jnz     short loc_180084F1C
0x180084eb4  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180084ebb  jz      loc_180085212
0x180084ec1  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180084ec8  test    rbx, rbx
0x180084ecb  jz      short loc_180084EED
0x180084ecd  call    cs:__imp_GetLastError
0x180084ed3  mov     r8d, eax
0x180084ed6  lea     rdx, aGetlastreplica_2; "GetLastReplicationIssue: EvtCreateRende"...
0x180084edd  mov     ecx, r15d
0x180084ee0  mov     rax, rbx
0x180084ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084ee8  jmp     loc_180085212
0x180084eed  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180084ef4  jz      loc_180085212
0x180084efa  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180084f01  jz      loc_180085212
0x180084f07  call    cs:__imp_GetLastError
0x180084f0d  lea     rdx, aGetlastreplica_2; "GetLastReplicationIssue: EvtCreateRende"...
0x180084f14  mov     ecx, r15d
0x180084f17  jmp     loc_18008520A
0x180084f1c  lea     rax, [rbp+arg_10]
0x180084f20  mov     [rsp+78h+Returned], rax; Returned
0x180084f25  mov     [rsp+78h+Flags], r14d; Flags
0x180084f2a  or      r9d, 0FFFFFFFFh; Timeout
0x180084f2e  lea     r8, [rbp+Events]; Events
0x180084f32  mov     edx, 1; EventsSize
0x180084f37  mov     rcx, r12; ResultSet
0x180084f3a  call    cs:__imp_EvtNext
0x180084f40  test    eax, eax
0x180084f42  jz      loc_1800851B3
0x180084f48  mov     r15d, r14d
0x180084f4b  cmp     r15d, [rbp+arg_10]
0x180084f4f  jnb     short loc_180084F1C
0x180084f51  mov     [rbp+var_20], r14
0x180084f55  mov     [rbp+BufferUsed], r14d
0x180084f59  mov     dword ptr [rbp+arg_0], r14d
0x180084f5d  mov     r13d, r15d
0x180084f60  lea     rax, [rbp+arg_0]
0x180084f64  mov     [rsp+78h+PropertyCount], rax; PropertyCount
0x180084f69  lea     rax, [rbp+BufferUsed]
0x180084f6d  mov     [rsp+78h+Returned], rax; BufferUsed
0x180084f72  mov     qword ptr [rsp+78h+Flags], r14; Buffer
0x180084f77  xor     r9d, r9d; BufferSize
0x180084f7a  xor     r8d, r8d; Flags
0x180084f7d  mov     rdx, [rbp+r13*8+Events]; Fragment
0x180084f82  mov     rcx, rsi; Context
0x180084f85  call    cs:__imp_EvtRender
0x180084f8b  test    eax, eax
0x180084f8d  jnz     loc_180085124
0x180084f93  call    cs:__imp_GetLastError
0x180084f99  cmp     eax, 7Ah ; 'z'
0x180084f9c  jnz     loc_1800851A8
0x180084fa2  mov     ebx, [rbp+BufferUsed]
0x180084fa5  mov     edx, ebx; uBytes
0x180084fa7  lea     ecx, [rax-3Ah]; uFlags
0x180084faa  call    cs:__imp_LocalAlloc
0x180084fb0  mov     r14, rax
0x180084fb3  mov     [rbp+var_20], rax
0x180084fb7  lea     rax, [rbp+arg_0]
0x180084fbb  mov     [rsp+78h+PropertyCount], rax; PropertyCount
0x180084fc0  lea     rax, [rbp+BufferUsed]
0x180084fc4  mov     [rsp+78h+Returned], rax; BufferUsed
0x180084fc9  mov     qword ptr [rsp+78h+Flags], r14; Buffer
0x180084fce  mov     r9d, ebx; BufferSize
0x180084fd1  xor     r8d, r8d; Flags
0x180084fd4  mov     rdx, [rbp+r13*8+Events]; Fragment
0x180084fd9  mov     rcx, rsi; Context
0x180084fdc  call    cs:__imp_EvtRender
0x180084fe2  xor     ecx, ecx
0x180084fe4  test    eax, eax
0x180084fe6  jz      loc_180085145
0x180084fec  cmp     dword ptr [rbp+arg_0], 8
0x180084ff0  jnz     loc_180085121
0x180084ff6  mov     [rsp+78h+lParam], rcx; lParam
0x180084ffb  mov     [rsp+78h+lpReserved], rcx; lpReserved
0x180085000  mov     [rsp+78h+PropertyCount], rcx; lpVersionInformation
0x180085005  or      ebx, 0FFFFFFFFh
0x180085008  mov     dword ptr [rsp+78h+Returned], ebx; cchCount2
0x18008500c  mov     rax, [r14+60h]
0x180085010  mov     qword ptr [rsp+78h+Flags], rax; lpString2
0x180085015  mov     r9d, ebx; cchCount1
0x180085018  mov     r8, rdi; lpString1
0x18008501b  lea     edx, [rcx+1]; dwCmpFlags
0x18008501e  lea     rcx, DomainName; lpLocaleName
0x180085025  call    cs:__imp_CompareStringEx
0x18008502b  cmp     eax, 2
0x18008502e  jnz     loc_180085121
0x180085034  xor     ebx, ebx
0x180085036  cmp     dword ptr [rbp+arg_0], ebx
0x180085039  jbe     loc_180085114
0x18008503f  mov     edi, ebx
0x180085041  add     rdi, rdi
0x180085044  mov     r9d, [r14+rdi*8+0Ch]
0x180085049  cmp     r9d, 1
0x18008504d  jz      short loc_1800850A2
0x18008504f  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180085056  jz      short loc_1800850A2
0x180085058  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008505f  test    rax, rax
0x180085062  jz      short loc_18008507A
0x180085064  mov     r8d, ebx
0x180085067  lea     rdx, aGetlastreplica_3; "GetLastReplicationIssue(%d):  %d != Evt"...
0x18008506e  mov     ecx, 2
0x180085073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085078  jmp     short loc_1800850A2
0x18008507a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180085082  jz      short loc_1800850A2
0x180085084  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008508c  jz      short loc_1800850A2
0x18008508e  mov     r8d, ebx
0x180085091  lea     rdx, aGetlastreplica_3; "GetLastReplicationIssue(%d):  %d != Evt"...
0x180085098  mov     ecx, 2; unsigned int
0x18008509d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800850a2  cmp     dword ptr [r14+rdi*8+0Ch], 1
0x1800850a8  jnz     short loc_180085105
0x1800850aa  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800850b1  jz      short loc_180085105
0x1800850b3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800850ba  test    rax, rax
0x1800850bd  jz      short loc_1800850D9
0x1800850bf  mov     r9, [r14+rdi*8]
0x1800850c3  mov     r8d, ebx
0x1800850c6  lea     rdx, aGetlastreplica_0; "GetLastReplicationIssue: Data(%d) = %s"
0x1800850cd  mov     ecx, 4
0x1800850d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800850d7  jmp     short loc_180085105
0x1800850d9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800850e1  jz      short loc_180085105
0x1800850e3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800850eb  jz      short loc_180085105
0x1800850ed  mov     r9, [r14+rdi*8]
0x1800850f1  mov     r8d, ebx
0x1800850f4  lea     rdx, aGetlastreplica_0; "GetLastReplicationIssue: Data(%d) = %s"
0x1800850fb  mov     ecx, 4; unsigned int
0x180085100  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180085105  inc     ebx
0x180085107  cmp     ebx, dword ptr [rbp+arg_0]
0x18008510a  jb      loc_18008503F
0x180085110  mov     rdi, [rbp+arg_8]
0x180085114  mov     rdx, [r14+10h]
0x180085118  lea     rcx, [rbp+var_18]
0x18008511c  call    ??4XBStr@@QEAAXPEBG@Z; XBStr::operator=(ushort const *)
0x180085121  xor     r14d, r14d
0x180085124  mov     rcx, [rbp+r13*8+Events]; Object
0x180085129  call    cs:__imp_EvtClose
0x18008512f  mov     [rbp+r13*8+Events], r14
0x180085134  lea     rcx, [rbp+var_20]
0x180085138  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18008513d  inc     r15d
0x180085140  jmp     loc_180084F4B
0x180085145  xor     r14d, r14d
0x180085148  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18008514f  jz      short loc_1800851A8
0x180085151  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180085158  test    rbx, rbx
0x18008515b  jz      short loc_18008517B
0x18008515d  call    cs:__imp_GetLastError
0x180085163  mov     r8d, eax
0x180085166  lea     rdx, aGetlastreplica_1; "GetLastReplicationIssue:  EvtRender fai"...
0x18008516d  lea     ecx, [r14+2]
0x180085171  mov     rax, rbx
0x180085174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085179  jmp     short loc_1800851A8
0x18008517b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180085182  jz      short loc_1800851A8
0x180085184  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008518b  jz      short loc_1800851A8
0x18008518d  call    cs:__imp_GetLastError
0x180085193  mov     r8d, eax
0x180085196  lea     rdx, aGetlastreplica_1; "GetLastReplicationIssue:  EvtRender fai"...
0x18008519d  mov     ecx, 2; unsigned int
0x1800851a2  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800851a7  nop
0x1800851a8  lea     rcx, [rbp+var_20]
0x1800851ac  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800851b1  jmp     short loc_180085212
0x1800851b3  call    cs:__imp_GetLastError
0x1800851b9  cmp     eax, 103h
0x1800851be  jz      short loc_180085212
0x1800851c0  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800851c7  jz      short loc_180085212
0x1800851c9  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800851d0  test    r9, r9
0x1800851d3  jz      short loc_1800851EC
0x1800851d5  mov     r8d, eax
0x1800851d8  lea     rdx, aGetlastreplica; "GetLastReplicationIssue:  EvtNext faile"...
0x1800851df  mov     ecx, 2
0x1800851e4  mov     rax, r9
0x1800851e7  jmp     loc_180084EE3
0x1800851ec  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800851f3  jz      short loc_180085212
0x1800851f5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800851fc  jz      short loc_180085212
0x1800851fe  lea     rdx, aGetlastreplica; "GetLastReplicationIssue:  EvtNext faile"...
0x180085205  mov     ecx, 2; unsigned int
0x18008520a  mov     r8d, eax
0x18008520d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180085212  mov     ebx, r14d
0x180085215  mov     eax, [rbp+arg_10]
0x180085218  test    eax, eax
0x18008521a  jz      short loc_18008523C
0x18008521c  mov     edi, ebx
0x18008521e  mov     rcx, [rbp+rdi*8+Events]; Object
0x180085223  test    rcx, rcx
0x180085226  jz      short loc_180085236
0x180085228  call    cs:__imp_EvtClose
0x18008522e  mov     [rbp+rdi*8+Events], r14
0x180085233  mov     eax, [rbp+arg_10]
0x180085236  inc     ebx
0x180085238  cmp     ebx, eax
0x18008523a  jb      short loc_18008521C
0x18008523c  test    r12, r12
0x18008523f  jz      short loc_18008524A
0x180085241  mov     rcx, r12; Object
0x180085244  call    cs:__imp_EvtClose
0x18008524a  test    rsi, rsi
0x18008524d  jz      short loc_180085259
0x18008524f  mov     rcx, rsi; Object
0x180085252  call    cs:__imp_EvtClose
0x180085258  nop
0x180085259  xor     ecx, ecx; bstrString
0x18008525b  call    cs:__imp_SysFreeString
0x180085261  mov     rax, [rbp+var_18]
0x180085265  add     rsp, 78h
0x180085269  pop     r15
0x18008526b  pop     r14
0x18008526d  pop     r13
0x18008526f  pop     r12
0x180085271  pop     rdi
0x180085272  pop     rsi
0x180085273  pop     rbx
0x180085274  pop     rbp
0x180085275  retn
```
