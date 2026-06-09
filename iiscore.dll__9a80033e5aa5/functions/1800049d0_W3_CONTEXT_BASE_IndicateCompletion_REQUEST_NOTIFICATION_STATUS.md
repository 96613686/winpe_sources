# W3_CONTEXT_BASE::IndicateCompletion(REQUEST_NOTIFICATION_STATUS)

- ea: `0x1800049d0`
- end: `0x180004b26`
- name: `?IndicateCompletion@W3_CONTEXT_BASE@@UEAAXW4REQUEST_NOTIFICATION_STATUS@@@Z`
- size: `342`
- prototype: `void __high(enum REQUEST_NOTIFICATION_STATUS)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001ab0`
- `0x1800049d0`
- `0x180004b2c`
- `0x180008930`
- `0x180017dcc`
- `0x180035010`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180004ae7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180004ae7`
- `w3dt!UlAtqFreeContext` at `0x180004a88`
- `w3dt!UlAtqFreeContext` at `0x180004a88`

## pseudocode

```c
void __fastcall W3_CONTEXT_BASE::IndicateCompletion(__int64 a1, unsigned int a2)
{
  __int64 v3; // rbp
  __int64 v4; // rax
  __int64 *v5; // rbx
  _QWORD *v6; // rdi
  unsigned int v7; // esi
  __int64 v8; // rbx
  unsigned int v9; // ebp
  __int64 v10; // r14
  void *v11; // rbx
  struct IHttpTraceContext *v12; // r14
  __int64 v13; // rbx
  char v14; // di
  unsigned int v15; // esi
  unsigned int CurrentModuleIndex; // eax
  __int64 v17; // r10
  const unsigned __int16 *v18; // rax
  const struct _GUID *v19; // rdx

  v3 = a1;
  if ( *(_DWORD *)(a1 + 88) )
    v4 = *(_QWORD *)(a1 + 96);
  else
    v4 = a1;
  if ( *(_BYTE *)(v4 + 9098) )
  {
    v12 = (struct IHttpTraceContext *)((a1 + 8) & -(__int64)(a1 != 0));
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v12, 256, 5) )
    {
      v13 = *(_QWORD *)(v3 + 80);
      v14 = *(_BYTE *)(v13 + 12);
      v15 = *(_DWORD *)(v13 + 8);
      BUFFER::QueryPtr(*(BUFFER **)(v13 + 80));
      CurrentModuleIndex = NOTIFICATION_CONTEXT::QueryCurrentModuleIndex((NOTIFICATION_CONTEXT *)v13);
      v18 = (const unsigned __int16 *)(***(__int64 (__fastcall ****)(_QWORD))(v17 + 8LL * CurrentModuleIndex))(*(_QWORD *)(v17 + 8LL * CurrentModuleIndex));
      IISRequestNotificationEvents::NOTIFY_MODULE_END::RaiseEvent(v12, v19, v18, v15, v14, a2);
    }
  }
  v5 = (__int64 *)(v3 + 80);
  *(_DWORD *)(*(_QWORD *)(v3 + 80) + 40LL) = a2;
  if ( *(_DWORD *)(v3 + 88) )
    v3 = *(_QWORD *)(v3 + 96);
  v6 = *(_QWORD **)(v3 + 392);
  v7 = 0;
  v8 = *v5;
  v9 = 0;
  while ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)v8 + 8LL))(v8, v9, v7, 0, 1) != 1 )
  {
    v7 = *(_DWORD *)(v8 + 72);
    v9 = *(_DWORD *)(v8 + 76);
    v10 = *(_QWORD *)(v8 + 56);
    if ( (unsigned int)W3_CONTEXT_BASE::FinishNotificationLoop(v8) == 1 )
      break;
    v8 = v10;
    if ( !v10 )
    {
      v11 = (void *)v6[1180];
      if ( v6 )
        (*(void (__fastcall **)(_QWORD *, __int64))(*v6 + 392LL))(v6, 1);
      UlAtqFreeContext(v11);
      return;
    }
  }
}

```

## disassembly

```asm
0x1800049d0  push    rbx
0x1800049d2  push    rbp
0x1800049d3  push    rsi
0x1800049d4  push    rdi
0x1800049d5  push    r14
0x1800049d7  push    r15
0x1800049d9  sub     rsp, 38h
0x1800049dd  cmp     dword ptr [rcx+58h], 0
0x1800049e1  mov     r15d, edx
0x1800049e4  mov     rbp, rcx
0x1800049e7  jnz     loc_180004A9B
0x1800049ed  mov     rax, rcx
0x1800049f0  cmp     byte ptr [rax+238Ah], 0
0x1800049f7  jnz     loc_180004AAD
0x1800049fd  lea     rbx, [rbp+50h]
0x180004a01  mov     rax, [rbx]
0x180004a04  mov     [rax+28h], r15d
0x180004a08  cmp     dword ptr [rbp+58h], 0
0x180004a0c  jnz     loc_180004AA4
0x180004a12  mov     rdi, [rbp+188h]
0x180004a19  xor     esi, esi
0x180004a1b  mov     rbx, [rbx]
0x180004a1e  xor     ebp, ebp
0x180004a20  lea     r15d, [rsi+1]
0x180004a24  mov     rax, [rbx]
0x180004a27  xor     r9d, r9d
0x180004a2a  mov     r8d, esi
0x180004a2d  mov     dword ptr [rsp+68h+var_48], r15d
0x180004a32  mov     edx, ebp
0x180004a34  mov     rcx, rbx
0x180004a37  mov     rax, [rax+8]
0x180004a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a40  cmp     eax, r15d
0x180004a43  jz      short loc_180004A8E
0x180004a45  mov     esi, [rbx+48h]
0x180004a48  mov     rcx, rbx
0x180004a4b  mov     ebp, [rbx+4Ch]
0x180004a4e  mov     r14, [rbx+38h]
0x180004a52  call    ?FinishNotificationLoop@W3_CONTEXT_BASE@@SA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@@Z; W3_CONTEXT_BASE::FinishNotificationLoop(NOTIFICATION_CONTEXT *)
0x180004a57  cmp     eax, r15d
0x180004a5a  jz      short loc_180004A8E
0x180004a5c  mov     rbx, r14
0x180004a5f  test    r14, r14
0x180004a62  jnz     short loc_180004A24
0x180004a64  mov     rbx, [rdi+24E0h]
0x180004a6b  test    rdi, rdi
0x180004a6e  jz      short loc_180004A85
0x180004a70  mov     rax, [rdi]
0x180004a73  mov     edx, r15d
0x180004a76  mov     rcx, rdi
0x180004a79  mov     rax, [rax+188h]
0x180004a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a85  mov     rcx, rbx
0x180004a88  call    cs:__imp_?UlAtqFreeContext@@YAXPEAX@Z; UlAtqFreeContext(void *)
0x180004a8e  add     rsp, 38h
0x180004a92  pop     r15
0x180004a94  pop     r14
0x180004a96  pop     rdi
0x180004a97  pop     rsi
0x180004a98  pop     rbp
0x180004a99  pop     rbx
0x180004a9a  retn
0x180004a9b  mov     rax, [rcx+60h]
0x180004a9f  jmp     loc_1800049F0
0x180004aa4  mov     rbp, [rbp+60h]
0x180004aa8  jmp     loc_180004A12
0x180004aad  add     rcx, 8
0x180004ab1  mov     rax, rbp
0x180004ab4  neg     rax
0x180004ab7  mov     edx, 100h
0x180004abc  mov     r8d, 5
0x180004ac2  sbb     r14, r14
0x180004ac5  and     r14, rcx
0x180004ac8  mov     rcx, r14
0x180004acb  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180004ad0  test    eax, eax
0x180004ad2  jz      loc_1800049FD
0x180004ad8  mov     rbx, [rbp+50h]
0x180004adc  mov     rcx, [rbx+50h]
0x180004ae0  movzx   edi, byte ptr [rbx+0Ch]
0x180004ae4  mov     esi, [rbx+8]
0x180004ae7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180004aed  mov     rcx, rbx; this
0x180004af0  mov     r10, rax
0x180004af3  call    ?QueryCurrentModuleIndex@NOTIFICATION_CONTEXT@@QEBAKXZ; NOTIFICATION_CONTEXT::QueryCurrentModuleIndex(void)
0x180004af8  mov     r8d, eax
0x180004afb  mov     rcx, [r10+r8*8]
0x180004aff  mov     rax, [rcx]
0x180004b02  mov     rax, [rax]
0x180004b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b0a  mov     r9d, esi; unsigned int
0x180004b0d  mov     [rsp+68h+var_40], r15d; unsigned int
0x180004b12  mov     r8, rax; unsigned __int16 *
0x180004b15  mov     dword ptr [rsp+68h+var_48], edi; char
0x180004b19  mov     rcx, r14; struct IHttpTraceContext *
0x180004b1c  call    ?RaiseEvent@NOTIFY_MODULE_END@IISRequestNotificationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBGKHK@Z; IISRequestNotificationEvents::NOTIFY_MODULE_END::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ulong,int,ulong)
0x180004b21  jmp     loc_1800049FD
```
