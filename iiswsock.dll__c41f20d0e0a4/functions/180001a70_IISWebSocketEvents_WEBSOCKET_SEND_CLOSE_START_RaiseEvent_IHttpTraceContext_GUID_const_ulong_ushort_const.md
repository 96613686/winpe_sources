# IISWebSocketEvents::WEBSOCKET_SEND_CLOSE_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ushort const *)

- ea: `0x180001a70`
- end: `0x180001baf`
- name: `?RaiseEvent@WEBSOCKET_SEND_CLOSE_START@IISWebSocketEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KPEBG@Z`
- size: `319`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000282c`

## callees

- `0x180001a70`
- `0x180008600`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall IISWebSocketEvents::WEBSOCKET_SEND_CLOSE_START::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3,
        const unsigned __int16 *a4)
{
  int v4; // eax
  __int64 v5; // rax
  __int64 v6; // rax
  _QWORD v8[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v9; // [rsp+48h] [rbp-B8h]
  int v10; // [rsp+4Ch] [rbp-B4h]
  __int128 v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+60h] [rbp-A0h]
  int v13; // [rsp+64h] [rbp-9Ch]
  int v14; // [rsp+68h] [rbp-98h]
  _QWORD v15[2]; // [rsp+6Ch] [rbp-94h] BYREF
  const wchar_t *v16; // [rsp+80h] [rbp-80h] BYREF
  int v17; // [rsp+88h] [rbp-78h]
  __int64 v18; // [rsp+90h] [rbp-70h]
  int v19; // [rsp+98h] [rbp-68h]
  __int64 v20; // [rsp+A0h] [rbp-60h]
  const wchar_t *v21; // [rsp+A8h] [rbp-58h]
  int v22; // [rsp+B0h] [rbp-50h]
  int *v23; // [rsp+B8h] [rbp-48h]
  int v24; // [rsp+C0h] [rbp-40h]
  __int64 v25; // [rsp+C8h] [rbp-38h]
  const wchar_t *v26; // [rsp+D0h] [rbp-30h]
  int v27; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v28; // [rsp+E0h] [rbp-20h]
  int v29; // [rsp+E8h] [rbp-18h]
  __int64 v30; // [rsp+F0h] [rbp-10h]
  int v31; // [rsp+130h] [rbp+30h] BYREF

  v31 = a3;
  v8[1] = 0x4000;
  memset(v15, 0, 12);
  v8[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v8[2] = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
  v8[4] = L"WEBSOCKET_SEND_CLOSE_START";
  v9 = 1;
  v13 = 1;
  v16 = L"ContextId";
  v21 = L"Status";
  v23 = &v31;
  v26 = L"Reason";
  v8[3] = 18;
  v10 = 5;
  v14 = 3;
  v11 = 0;
  v12 = 0;
  v17 = 72;
  v18 = 0;
  v19 = 16;
  v20 = 0;
  v22 = 19;
  v24 = 4;
  v25 = 0;
  v27 = 31;
  v28 = a4;
  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v4 = 2 * v5 + 2;
  }
  else
  {
    v4 = 0;
  }
  v29 = v4;
  *(_QWORD *)((char *)v15 + 4) = &v16;
  v6 = *(_QWORD *)a1;
  v30 = 0;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v6 + 16))(a1, v8);
  return 0;
}

```

## disassembly

```asm
0x180001a70  mov     [rsp-8+arg_10], r8d
0x180001a75  push    rbp
0x180001a76  lea     rbp, [rsp-10h]
0x180001a7b  sub     rsp, 110h
0x180001a82  mov     rax, cs:__security_cookie
0x180001a89  xor     rax, rsp
0x180001a8c  mov     [rbp+10h+var_10], rax
0x180001a90  xor     eax, eax
0x180001a92  mov     [rsp+110h+var_E8], 4000h
0x180001a9b  mov     [rsp+110h+var_A4], rax
0x180001aa0  xor     edx, edx
0x180001aa2  mov     [rsp+110h+var_9C], eax
0x180001aa6  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001aad  mov     [rsp+110h+var_F0], rax
0x180001ab2  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180001ab9  mov     [rsp+110h+var_E0], rax
0x180001abe  lea     rax, aWebsocketSendC_0; "WEBSOCKET_SEND_CLOSE_START"
0x180001ac5  mov     [rsp+110h+var_D0], rax
0x180001aca  mov     eax, 1
0x180001acf  mov     [rsp+110h+var_C8], eax
0x180001ad3  xorps   xmm0, xmm0
0x180001ad6  mov     [rsp+110h+var_AC], eax
0x180001ada  lea     rax, aContextid; "ContextId"
0x180001ae1  mov     [rbp+10h+var_90], rax
0x180001ae5  lea     rax, aStatus; "Status"
0x180001aec  mov     [rbp+10h+var_68], rax
0x180001af0  lea     rax, [rbp+10h+arg_10]
0x180001af4  mov     [rbp+10h+var_58], rax
0x180001af8  lea     rax, aReason; "Reason"
0x180001aff  mov     [rbp+10h+var_40], rax
0x180001b03  mov     [rsp+110h+var_D8], 12h
0x180001b0c  mov     [rsp+110h+var_C4], 5
0x180001b14  mov     [rsp+110h+var_A8], 3
0x180001b1c  movdqa  [rsp+110h+var_C0], xmm0
0x180001b22  mov     [rsp+110h+var_B0], edx
0x180001b26  mov     [rbp+10h+var_88], 48h ; 'H'
0x180001b2d  mov     [rbp+10h+var_80], rdx
0x180001b31  mov     [rbp+10h+var_78], 10h
0x180001b38  mov     [rbp+10h+var_70], rdx
0x180001b3c  mov     [rbp+10h+var_60], 13h
0x180001b43  mov     [rbp+10h+var_50], 4
0x180001b4a  mov     [rbp+10h+var_48], rdx
0x180001b4e  mov     [rbp+10h+var_38], 1Fh
0x180001b55  mov     [rbp+10h+var_30], r9
0x180001b59  test    r9, r9
0x180001b5c  jnz     short loc_180001B62
0x180001b5e  mov     eax, edx
0x180001b60  jmp     short loc_180001B77
0x180001b62  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001b66  inc     rax
0x180001b69  cmp     [r9+rax*2], dx
0x180001b6e  jnz     short loc_180001B66
0x180001b70  lea     eax, ds:2[rax*2]
0x180001b77  mov     [rbp+10h+var_28], eax
0x180001b7a  lea     rax, [rbp+10h+var_90]
0x180001b7e  mov     [rsp+110h+var_A4+4], rax
0x180001b83  mov     rax, [rcx]
0x180001b86  mov     [rbp+10h+var_20], rdx
0x180001b8a  lea     rdx, [rsp+110h+var_F0]
0x180001b8f  mov     rax, [rax+10h]
0x180001b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b98  xor     eax, eax
0x180001b9a  mov     rcx, [rbp+10h+var_10]
0x180001b9e  xor     rcx, rsp; StackCookie
0x180001ba1  call    __security_check_cookie
0x180001ba6  add     rsp, 110h
0x180001bad  pop     rbp
0x180001bae  retn
```
