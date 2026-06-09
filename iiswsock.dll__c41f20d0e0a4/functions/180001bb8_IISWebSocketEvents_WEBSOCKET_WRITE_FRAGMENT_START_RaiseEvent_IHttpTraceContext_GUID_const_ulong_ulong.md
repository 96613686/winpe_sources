# IISWebSocketEvents::WEBSOCKET_WRITE_FRAGMENT_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ulong)

- ea: `0x180001bb8`
- end: `0x180001cd8`
- name: `?RaiseEvent@WEBSOCKET_WRITE_FRAGMENT_START@IISWebSocketEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KK@Z`
- size: `288`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007420`

## callees

- `0x180008600`
- `0x180009010`

## string_xrefs

- `0x180001c1a`: `WEBSOCKET_WRITE_FRAGMENT_START`

## pseudocode

```c
__int64 __fastcall IISWebSocketEvents::WEBSOCKET_WRITE_FRAGMENT_START::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3,
        int a4)
{
  __int64 v4; // rax
  void (__fastcall *v5)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v7[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v8; // [rsp+48h] [rbp-B8h]
  int v9; // [rsp+4Ch] [rbp-B4h]
  __int128 v10; // [rsp+50h] [rbp-B0h]
  int v11; // [rsp+60h] [rbp-A0h]
  int v12; // [rsp+64h] [rbp-9Ch]
  __int64 v13; // [rsp+68h] [rbp-98h]
  const wchar_t **v14; // [rsp+70h] [rbp-90h]
  const wchar_t *v15; // [rsp+80h] [rbp-80h] BYREF
  int v16; // [rsp+88h] [rbp-78h]
  __int64 v17; // [rsp+90h] [rbp-70h]
  int v18; // [rsp+98h] [rbp-68h]
  __int64 v19; // [rsp+A0h] [rbp-60h]
  const wchar_t *v20; // [rsp+A8h] [rbp-58h]
  int v21; // [rsp+B0h] [rbp-50h]
  int *v22; // [rsp+B8h] [rbp-48h]
  int v23; // [rsp+C0h] [rbp-40h]
  __int64 v24; // [rsp+C8h] [rbp-38h]
  const wchar_t *v25; // [rsp+D0h] [rbp-30h]
  int v26; // [rsp+D8h] [rbp-28h]
  int *v27; // [rsp+E0h] [rbp-20h]
  int v28; // [rsp+E8h] [rbp-18h]
  __int64 v29; // [rsp+F0h] [rbp-10h]
  int v30; // [rsp+130h] [rbp+30h] BYREF
  int v31; // [rsp+138h] [rbp+38h] BYREF

  v31 = a4;
  v30 = a3;
  v7[1] = 0x4000;
  v7[3] = 9;
  v7[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v13 = 3;
  v7[2] = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
  v23 = 4;
  v7[4] = L"WEBSOCKET_WRITE_FRAGMENT_START";
  v28 = 4;
  v8 = 1;
  v12 = 1;
  v15 = L"ContextId";
  v20 = L"DataType";
  v22 = &v30;
  v25 = L"DataSize";
  v27 = &v31;
  v14 = &v15;
  v4 = *(_QWORD *)a1;
  v9 = 5;
  v10 = 0;
  v11 = 0;
  v5 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v4 + 16);
  v16 = 72;
  v17 = 0;
  v18 = 16;
  v19 = 0;
  v21 = 19;
  v24 = 0;
  v26 = 19;
  v29 = 0;
  v5(a1, v7);
  return 0;
}

```

## disassembly

```asm
0x180001bb8  mov     [rsp-8+arg_18], r9d
0x180001bbd  mov     [rsp-8+arg_10], r8d
0x180001bc2  push    rbp
0x180001bc3  lea     rbp, [rsp-10h]
0x180001bc8  sub     rsp, 110h
0x180001bcf  mov     rax, cs:__security_cookie
0x180001bd6  xor     rax, rsp
0x180001bd9  mov     [rbp+10h+var_10], rax
0x180001bdd  xor     r9d, r9d
0x180001be0  mov     [rsp+110h+var_E8], 4000h
0x180001be9  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001bf0  mov     [rsp+110h+var_D8], 9
0x180001bf9  mov     [rsp+110h+var_F0], rax
0x180001bfe  xorps   xmm0, xmm0
0x180001c01  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180001c08  mov     [rsp+110h+var_A8], 3
0x180001c11  mov     [rsp+110h+var_E0], rax
0x180001c16  lea     edx, [r9+4]
0x180001c1a  lea     rax, aWebsocketWrite_0; "WEBSOCKET_WRITE_FRAGMENT_START"
0x180001c21  mov     [rbp+10h+var_50], edx
0x180001c24  mov     [rsp+110h+var_D0], rax
0x180001c29  lea     r8d, [r9+13h]
0x180001c2d  mov     eax, 1
0x180001c32  mov     [rbp+10h+var_28], edx
0x180001c35  mov     [rsp+110h+var_C8], eax
0x180001c39  lea     rdx, [rsp+110h+var_F0]
0x180001c3e  mov     [rsp+110h+var_AC], eax
0x180001c42  lea     rax, aContextid; "ContextId"
0x180001c49  mov     [rbp+10h+var_90], rax
0x180001c4d  lea     rax, aDatatype; "DataType"
0x180001c54  mov     [rbp+10h+var_68], rax
0x180001c58  lea     rax, [rbp+10h+arg_10]
0x180001c5c  mov     [rbp+10h+var_58], rax
0x180001c60  lea     rax, aDatasize; "DataSize"
0x180001c67  mov     [rbp+10h+var_40], rax
0x180001c6b  lea     rax, [rbp+10h+arg_18]
0x180001c6f  mov     [rbp+10h+var_30], rax
0x180001c73  lea     rax, [rbp+10h+var_90]
0x180001c77  mov     [rsp+110h+var_A0], rax
0x180001c7c  mov     rax, [rcx]
0x180001c7f  mov     [rsp+110h+var_C4], 5
0x180001c87  movdqa  [rsp+110h+var_C0], xmm0
0x180001c8d  mov     [rsp+110h+var_B0], r9d
0x180001c92  mov     rax, [rax+10h]
0x180001c96  mov     [rbp+10h+var_88], 48h ; 'H'
0x180001c9d  mov     [rbp+10h+var_80], r9
0x180001ca1  mov     [rbp+10h+var_78], 10h
0x180001ca8  mov     [rbp+10h+var_70], r9
0x180001cac  mov     [rbp+10h+var_60], r8d
0x180001cb0  mov     [rbp+10h+var_48], r9
0x180001cb4  mov     [rbp+10h+var_38], r8d
0x180001cb8  mov     [rbp+10h+var_20], r9
0x180001cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cc1  xor     eax, eax
0x180001cc3  mov     rcx, [rbp+10h+var_10]
0x180001cc7  xor     rcx, rsp; StackCookie
0x180001cca  call    __security_check_cookie
0x180001ccf  add     rsp, 110h
0x180001cd6  pop     rbp
0x180001cd7  retn
```
