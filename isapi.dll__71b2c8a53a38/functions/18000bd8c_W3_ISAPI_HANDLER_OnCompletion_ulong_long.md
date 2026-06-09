# W3_ISAPI_HANDLER::OnCompletion(ulong,long)

- ea: `0x18000bd8c`
- end: `0x18000be71`
- name: `?OnCompletion@W3_ISAPI_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KJ@Z`
- size: `229`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b3d0`

## callees

- `0x1800033a0`
- `0x180003744`
- `0x18000b30c`
- `0x18000bd8c`
- `0x18000c208`
- `0x18000c2b4`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall W3_ISAPI_HANDLER::OnCompletion(__int64 a1, unsigned int a2, int a3)
{
  __int64 v6; // rax
  ISAPI_CONTEXT *v7; // rbp
  struct IHttpTraceContext *v8; // rax
  struct IHttpTraceContext *v9; // rax
  const struct _GUID *v10; // rdx
  unsigned int v11; // eax

  if ( (unsigned int)(*(_DWORD *)(a1 + 40) - 3) <= 1 )
  {
    W3_ISAPI_HANDLER::SetRequestHandledAndTrace((W3_ISAPI_HANDLER *)a1);
    return 0;
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 16);
    v7 = *(ISAPI_CONTEXT **)(v6 + 16);
    *(_DWORD *)(v6 + 40) = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 240LL))(*(_QWORD *)(a1 + 16));
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
    v8 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
    if ( (unsigned int)WWWIsapiExtensionTraceProvider::CheckTracingEnabled(v8, 4u) )
    {
      v9 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
      W3IsapiEvents::NOTIFY_ISAPI_COMPLETION::RaiseEvent(v9, v10);
    }
    v11 = WIN32_FROM_HRESULT(a3);
    ProcessIsapiCompletion(v7, a2, v11);
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 32LL))(g_pGlobalInfo);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 248LL))(*(_QWORD *)(a1 + 16));
    return 1;
  }
}

```

## disassembly

```asm
0x18000bd8c  push    rbx
0x18000bd8e  push    rbp
0x18000bd8f  push    rsi
0x18000bd90  push    rdi
0x18000bd91  sub     rsp, 28h
0x18000bd95  mov     eax, [rcx+28h]
0x18000bd98  mov     edi, r8d
0x18000bd9b  sub     eax, 3
0x18000bd9e  mov     esi, edx
0x18000bda0  mov     rbx, rcx
0x18000bda3  cmp     eax, 1
0x18000bda6  jbe     loc_18000BE61
0x18000bdac  mov     rax, [rcx+10h]
0x18000bdb0  mov     rbp, [rax+10h]
0x18000bdb4  mov     dword ptr [rax+28h], 0
0x18000bdbb  mov     rcx, [rcx+10h]
0x18000bdbf  mov     rax, [rcx]
0x18000bdc2  mov     rax, [rax+0F0h]
0x18000bdc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdce  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000bdd5  mov     rax, [rcx]
0x18000bdd8  mov     rax, [rax+18h]
0x18000bddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde1  mov     rcx, [rbx+8]
0x18000bde5  mov     rax, [rcx]
0x18000bde8  mov     rax, [rax+110h]
0x18000bdef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf4  mov     edx, 4; unsigned int
0x18000bdf9  mov     rcx, rax; struct IHttpTraceContext *
0x18000bdfc  call    ?CheckTracingEnabled@WWWIsapiExtensionTraceProvider@@SAHPEAVIHttpTraceContext@@K@Z; WWWIsapiExtensionTraceProvider::CheckTracingEnabled(IHttpTraceContext *,ulong)
0x18000be01  test    eax, eax
0x18000be03  jz      short loc_18000BE20
0x18000be05  mov     rcx, [rbx+8]
0x18000be09  mov     rax, [rcx]
0x18000be0c  mov     rax, [rax+110h]
0x18000be13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be18  mov     rcx, rax; struct IHttpTraceContext *
0x18000be1b  call    ?RaiseEvent@NOTIFY_ISAPI_COMPLETION@W3IsapiEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; W3IsapiEvents::NOTIFY_ISAPI_COMPLETION::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000be20  mov     ecx, edi; int
0x18000be22  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000be27  mov     r8d, eax; unsigned int
0x18000be2a  mov     edx, esi; unsigned int
0x18000be2c  mov     rcx, rbp; this
0x18000be2f  call    ?ProcessIsapiCompletion@@YAJ_KKK@Z; ProcessIsapiCompletion(unsigned __int64,ulong,ulong)
0x18000be34  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000be3b  mov     rdx, [rcx]
0x18000be3e  mov     rax, [rdx+20h]
0x18000be42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be47  mov     rcx, [rbx+10h]
0x18000be4b  mov     rdx, [rcx]
0x18000be4e  mov     rax, [rdx+0F8h]
0x18000be55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be5a  mov     eax, 1
0x18000be5f  jmp     short loc_18000BE68
0x18000be61  call    ?SetRequestHandledAndTrace@W3_ISAPI_HANDLER@@AEAAJXZ; W3_ISAPI_HANDLER::SetRequestHandledAndTrace(void)
0x18000be66  xor     eax, eax
0x18000be68  add     rsp, 28h
0x18000be6c  pop     rdi
0x18000be6d  pop     rsi
0x18000be6e  pop     rbp
0x18000be6f  pop     rbx
0x18000be70  retn
```
