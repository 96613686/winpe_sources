# W3_CONTEXT_BASE::IndicateCompletion(REQUEST_NOTIFICATION_STATUS)

- ea: `0x180004dd0`
- end: `0x180004f33`
- name: `?IndicateCompletion@W3_CONTEXT_BASE@@UEAAXW4REQUEST_NOTIFICATION_STATUS@@@Z`
- size: `355`
- prototype: `void __high(enum REQUEST_NOTIFICATION_STATUS)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001b40`
- `0x180004dd0`
- `0x180004f3c`
- `0x180009030`
- `0x18001924c`
- `0x180038010`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180004eee`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180004eee`
- `w3dt!UlAtqFreeContext` at `0x180004e88`
- `w3dt!UlAtqFreeContext` at `0x180004e88`

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
0x180004dd0  push    rbx
0x180004dd2  push    rbp
0x180004dd3  push    rsi
0x180004dd4  push    rdi
0x180004dd5  push    r14
0x180004dd7  push    r15
0x180004dd9  sub     rsp, 38h
0x180004ddd  cmp     dword ptr [rcx+58h], 0
0x180004de1  mov     r15d, edx
0x180004de4  mov     rbp, rcx
0x180004de7  jnz     loc_180004EA2
0x180004ded  mov     rax, rcx
0x180004df0  cmp     byte ptr [rax+238Ah], 0
0x180004df7  jnz     loc_180004EB4
0x180004dfd  lea     rbx, [rbp+50h]
0x180004e01  mov     rax, [rbx]
0x180004e04  mov     [rax+28h], r15d
0x180004e08  cmp     dword ptr [rbp+58h], 0
0x180004e0c  jnz     loc_180004EAB
0x180004e12  mov     rdi, [rbp+188h]
0x180004e19  xor     esi, esi
0x180004e1b  mov     rbx, [rbx]
0x180004e1e  xor     ebp, ebp
0x180004e20  lea     r15d, [rsi+1]
0x180004e24  mov     rax, [rbx]
0x180004e27  xor     r9d, r9d
0x180004e2a  mov     r8d, esi
0x180004e2d  mov     dword ptr [rsp+68h+var_48], r15d
0x180004e32  mov     edx, ebp
0x180004e34  mov     rcx, rbx
0x180004e37  mov     rax, [rax+8]
0x180004e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e40  cmp     eax, r15d
0x180004e43  jz      short loc_180004E94
0x180004e45  mov     esi, [rbx+48h]
0x180004e48  mov     rcx, rbx
0x180004e4b  mov     ebp, [rbx+4Ch]
0x180004e4e  mov     r14, [rbx+38h]
0x180004e52  call    ?FinishNotificationLoop@W3_CONTEXT_BASE@@SA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@@Z; W3_CONTEXT_BASE::FinishNotificationLoop(NOTIFICATION_CONTEXT *)
0x180004e57  cmp     eax, r15d
0x180004e5a  jz      short loc_180004E94
0x180004e5c  mov     rbx, r14
0x180004e5f  test    r14, r14
0x180004e62  jnz     short loc_180004E24
0x180004e64  mov     rbx, [rdi+24E0h]
0x180004e6b  test    rdi, rdi
0x180004e6e  jz      short loc_180004E85
0x180004e70  mov     rax, [rdi]
0x180004e73  mov     edx, r15d
0x180004e76  mov     rcx, rdi
0x180004e79  mov     rax, [rax+188h]
0x180004e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e85  mov     rcx, rbx
0x180004e88  call    cs:__imp_?UlAtqFreeContext@@YAXPEAX@Z; UlAtqFreeContext(void *)
0x180004e8f  nop     dword ptr [rax+rax+00h]
0x180004e94  add     rsp, 38h
0x180004e98  pop     r15
0x180004e9a  pop     r14
0x180004e9c  pop     rdi
0x180004e9d  pop     rsi
0x180004e9e  pop     rbp
0x180004e9f  pop     rbx
0x180004ea0  retn
0x180004ea2  mov     rax, [rcx+60h]
0x180004ea6  jmp     loc_180004DF0
0x180004eab  mov     rbp, [rbp+60h]
0x180004eaf  jmp     loc_180004E12
0x180004eb4  add     rcx, 8
0x180004eb8  mov     rax, rbp
0x180004ebb  neg     rax
0x180004ebe  mov     edx, 100h
0x180004ec3  mov     r8d, 5
0x180004ec9  sbb     r14, r14
0x180004ecc  and     r14, rcx
0x180004ecf  mov     rcx, r14
0x180004ed2  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180004ed7  test    eax, eax
0x180004ed9  jz      loc_180004DFD
0x180004edf  mov     rbx, [rbp+50h]
0x180004ee3  mov     rcx, [rbx+50h]
0x180004ee7  movzx   edi, byte ptr [rbx+0Ch]
0x180004eeb  mov     esi, [rbx+8]
0x180004eee  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180004ef5  nop     dword ptr [rax+rax+00h]
0x180004efa  mov     rcx, rbx; this
0x180004efd  mov     r10, rax
0x180004f00  call    ?QueryCurrentModuleIndex@NOTIFICATION_CONTEXT@@QEBAKXZ; NOTIFICATION_CONTEXT::QueryCurrentModuleIndex(void)
0x180004f05  mov     r8d, eax
0x180004f08  mov     rcx, [r10+r8*8]
0x180004f0c  mov     rax, [rcx]
0x180004f0f  mov     rax, [rax]
0x180004f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f17  mov     r9d, esi; unsigned int
0x180004f1a  mov     [rsp+68h+var_40], r15d; unsigned int
0x180004f1f  mov     r8, rax; unsigned __int16 *
0x180004f22  mov     dword ptr [rsp+68h+var_48], edi; char
0x180004f26  mov     rcx, r14; struct IHttpTraceContext *
0x180004f29  call    ?RaiseEvent@NOTIFY_MODULE_END@IISRequestNotificationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBGKHK@Z; IISRequestNotificationEvents::NOTIFY_MODULE_END::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ulong,int,ulong)
0x180004f2e  jmp     loc_180004DFD
```
