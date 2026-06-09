# TRACE_HELPER::RaiseTraceEventOnModuleCloseConnection(IHttpContext *,ulong)

- ea: `0x180002974`
- end: `0x180002afc`
- name: `?RaiseTraceEventOnModuleCloseConnection@TRACE_HELPER@@QEAAXPEAVIHttpContext@@K@Z`
- size: `392`
- prototype: `void __fastcall(TRACE_HELPER *__hidden this, struct IHttpContext *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800069a0`

## callees

- `0x180002974`
- `0x180009010`

## pseudocode

```c
void __fastcall TRACE_HELPER::RaiseTraceEventOnModuleCloseConnection(
        TRACE_HELPER *this,
        struct IHttpContext *a2,
        int a3)
{
  int (__fastcall ***v4)(_QWORD, GUID **); // rax
  int (__fastcall **v5)(_QWORD, GUID **); // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  const wchar_t *v8; // rax
  GUID *v9; // [rsp+28h] [rbp-79h] BYREF
  __int128 v10; // [rsp+30h] [rbp-71h]
  _QWORD v11[5]; // [rsp+48h] [rbp-59h] BYREF
  int v12; // [rsp+70h] [rbp-31h]
  int v13; // [rsp+74h] [rbp-2Dh]
  __int128 v14; // [rsp+78h] [rbp-29h]
  int v15; // [rsp+88h] [rbp-19h]
  int v16; // [rsp+8Ch] [rbp-15h]
  __int64 v17; // [rsp+90h] [rbp-11h]
  const wchar_t **v18; // [rsp+98h] [rbp-9h]
  const wchar_t *v19; // [rsp+A8h] [rbp+7h] BYREF
  int v20; // [rsp+B0h] [rbp+Fh]
  __int64 v21; // [rsp+B8h] [rbp+17h]
  int v22; // [rsp+C0h] [rbp+1Fh]
  __int64 v23; // [rsp+C8h] [rbp+27h]
  const wchar_t *v24; // [rsp+D0h] [rbp+2Fh]
  int v25; // [rsp+D8h] [rbp+37h]
  int *v26; // [rsp+E0h] [rbp+3Fh]
  int v27; // [rsp+E8h] [rbp+47h]
  const wchar_t *v28; // [rsp+F0h] [rbp+4Fh]
  int v29; // [rsp+118h] [rbp+77h] BYREF

  v29 = a3;
  v4 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
  v9 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v5 = *v4;
  v10 = 0;
  if ( (*v5)(v4, &v9) >= 0 && DWORD2(v10) && DWORD1(v10) >= 4 && ((_DWORD)v10 == 0x4000 || (v10 & 0x4000) != 0) )
  {
    v6 = *(_QWORD *)a2;
    v29 = 1;
    v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v6 + 272))(a2);
    v11[1] = 0x4000;
    v11[2] = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
    v11[3] = 14;
    v11[4] = L"WEBSOCKET_MODULE_CLOSE_CONNECTION";
    v19 = L"ContextId";
    v24 = L"Reason";
    v26 = &v29;
    v17 = 2;
    v11[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v12 = 1;
    v13 = 4;
    v14 = 0;
    v15 = 0;
    v16 = 1;
    v20 = 72;
    v21 = 0;
    v22 = 16;
    v23 = 0;
    v25 = 19;
    v27 = 4;
    if ( v29 == 1 )
      v8 = L"PING_TIMEOUT";
    else
      v8 = 0;
    v28 = v8;
    v18 = &v19;
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 16LL))(v7, v11);
  }
}

```

## disassembly

```asm
0x180002974  mov     rax, rsp
0x180002977  mov     [rax+8], rbx
0x18000297b  mov     [rax+10h], r12
0x18000297f  mov     [rax+18h], r8d
0x180002983  push    rbp
0x180002984  lea     rbp, [rax-5Fh]
0x180002988  sub     rsp, 0F0h
0x18000298f  mov     rax, [rdx]
0x180002992  mov     rcx, rdx
0x180002995  mov     rbx, rdx
0x180002998  mov     rax, [rax+110h]
0x18000299f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a4  mov     r8, rax
0x1800029a7  lea     r12, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800029ae  xorps   xmm0, xmm0
0x1800029b1  mov     [rbp+57h+var_D0], r12
0x1800029b5  lea     rdx, [rbp+57h+var_D0]
0x1800029b9  mov     rcx, [rax]
0x1800029bc  movdqu  [rbp+57h+var_C8], xmm0
0x1800029c1  mov     rax, [rcx]
0x1800029c4  mov     rcx, r8
0x1800029c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029cc  test    eax, eax
0x1800029ce  js      loc_180002AE7
0x1800029d4  cmp     dword ptr [rbp+57h+var_C8+8], 0
0x1800029d8  jz      loc_180002AE7
0x1800029de  cmp     dword ptr [rbp+57h+var_C8+4], 4
0x1800029e2  jb      loc_180002AE7
0x1800029e8  cmp     dword ptr [rbp+57h+var_C8], 4000h
0x1800029ef  jz      short loc_1800029FE
0x1800029f1  test    dword ptr [rbp+57h+var_C8], 4000h
0x1800029f8  jz      loc_180002AE7
0x1800029fe  mov     rax, [rbx]
0x180002a01  mov     rcx, rbx
0x180002a04  mov     [rbp+57h+arg_10], 1
0x180002a0b  mov     rax, [rax+110h]
0x180002a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a17  cmp     [rbp+57h+arg_10], 1
0x180002a1b  mov     rcx, rax
0x180002a1e  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180002a25  mov     [rbp+57h+var_A8], 4000h
0x180002a2d  mov     [rbp+57h+var_A0], rax
0x180002a31  xorps   xmm0, xmm0
0x180002a34  lea     rax, aWebsocketModul_1; "WEBSOCKET_MODULE_CLOSE_CONNECTION"
0x180002a3b  mov     [rbp+57h+var_98], 0Eh
0x180002a43  mov     [rbp+57h+var_90], rax
0x180002a47  lea     rax, aContextid; "ContextId"
0x180002a4e  mov     [rbp+57h+var_50], rax
0x180002a52  lea     rax, aReason; "Reason"
0x180002a59  mov     [rbp+57h+var_28], rax
0x180002a5d  lea     rax, [rbp+57h+arg_10]
0x180002a61  mov     [rbp+57h+var_18], rax
0x180002a65  mov     [rbp+57h+var_68], 2
0x180002a6d  mov     [rbp+57h+var_B0], r12
0x180002a71  mov     [rbp+57h+var_88], 1
0x180002a78  mov     [rbp+57h+var_84], 4
0x180002a7f  movdqa  [rbp+57h+var_80], xmm0
0x180002a84  mov     [rbp+57h+var_70], 0
0x180002a8b  mov     [rbp+57h+var_6C], 1
0x180002a92  mov     [rbp+57h+var_48], 48h ; 'H'
0x180002a99  mov     [rbp+57h+var_40], 0
0x180002aa1  mov     [rbp+57h+var_38], 10h
0x180002aa8  mov     [rbp+57h+var_30], 0
0x180002ab0  mov     [rbp+57h+var_20], 13h
0x180002ab7  mov     [rbp+57h+var_10], 4
0x180002abe  jz      short loc_180002AC4
0x180002ac0  xor     eax, eax
0x180002ac2  jmp     short loc_180002ACB
0x180002ac4  lea     rax, aPingTimeout; "PING_TIMEOUT"
0x180002acb  mov     [rbp+57h+var_8], rax
0x180002acf  lea     rdx, [rbp+57h+var_B0]
0x180002ad3  lea     rax, [rbp+57h+var_50]
0x180002ad7  mov     [rbp+57h+var_60], rax
0x180002adb  mov     rax, [rcx]
0x180002ade  mov     rax, [rax+10h]
0x180002ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae7  lea     r11, [rsp+0F0h+var_s0]
0x180002aef  mov     rbx, [r11+10h]
0x180002af3  mov     r12, [r11+18h]
0x180002af7  mov     rsp, r11
0x180002afa  pop     rbp
0x180002afb  retn
```
