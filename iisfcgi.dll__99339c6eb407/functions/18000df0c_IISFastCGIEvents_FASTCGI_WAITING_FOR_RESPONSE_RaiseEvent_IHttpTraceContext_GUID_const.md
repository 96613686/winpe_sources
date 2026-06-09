# IISFastCGIEvents::FASTCGI_WAITING_FOR_RESPONSE::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x18000df0c`
- end: `0x18000dfb6`
- name: `?RaiseEvent@FASTCGI_WAITING_FOR_RESPONSE@IISFastCGIEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b3ac`
- `0x18000cb30`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall IISFastCGIEvents::FASTCGI_WAITING_FOR_RESPONSE::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2)
{
  __int64 v2; // rax
  void (__fastcall *v3)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v5[5]; // [rsp+20h] [rbp-39h] BYREF
  int v6; // [rsp+48h] [rbp-11h]
  int v7; // [rsp+4Ch] [rbp-Dh]
  __int128 v8; // [rsp+50h] [rbp-9h]
  int v9; // [rsp+60h] [rbp+7h]
  int v10; // [rsp+64h] [rbp+Bh]
  __int64 v11; // [rsp+68h] [rbp+Fh]
  const wchar_t **v12; // [rsp+70h] [rbp+17h]
  const wchar_t *v13; // [rsp+80h] [rbp+27h] BYREF
  int v14; // [rsp+88h] [rbp+2Fh]
  __int64 v15; // [rsp+90h] [rbp+37h]
  int v16; // [rsp+98h] [rbp+3Fh]
  __int64 v17; // [rsp+A0h] [rbp+47h]

  v5[1] = 4096;
  v9 = 0;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v15 = 0;
  v5[2] = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"FASTCGI_WAITING_FOR_RESPONSE";
  v6 = 1;
  v10 = 1;
  v13 = L"ContextId";
  v12 = &v13;
  v2 = *(_QWORD *)a1;
  v17 = 0;
  v5[3] = 12;
  v11 = 1;
  v3 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v2 + 16);
  v7 = 5;
  v8 = 0;
  v14 = 72;
  v16 = 16;
  v3(a1, v5);
  return 0;
}

```

## disassembly

```asm
0x18000df0c  push    rbp
0x18000df0e  lea     rbp, [rsp-57h]
0x18000df13  sub     rsp, 0B0h
0x18000df1a  xor     edx, edx
0x18000df1c  mov     [rbp+57h+var_88], 1000h
0x18000df24  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000df2b  mov     [rbp+57h+var_50], edx
0x18000df2e  mov     [rbp+57h+var_90], rax
0x18000df32  xorps   xmm0, xmm0
0x18000df35  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000df3c  mov     [rbp+57h+var_20], rdx
0x18000df40  mov     [rbp+57h+var_80], rax
0x18000df44  lea     rax, aFastcgiWaiting; "FASTCGI_WAITING_FOR_RESPONSE"
0x18000df4b  mov     [rbp+57h+var_70], rax
0x18000df4f  mov     eax, 1
0x18000df54  mov     [rbp+57h+var_68], eax
0x18000df57  mov     [rbp+57h+var_4C], eax
0x18000df5a  lea     rax, aContextid; "ContextId"
0x18000df61  mov     [rbp+57h+var_30], rax
0x18000df65  lea     rax, [rbp+57h+var_30]
0x18000df69  mov     [rbp+57h+var_40], rax
0x18000df6d  mov     rax, [rcx]
0x18000df70  mov     [rbp+57h+var_10], rdx
0x18000df74  lea     rdx, [rbp+57h+var_90]
0x18000df78  mov     [rbp+57h+var_78], 0Ch
0x18000df80  mov     [rbp+57h+var_48], 1
0x18000df88  mov     rax, [rax+10h]
0x18000df8c  mov     [rbp+57h+var_64], 5
0x18000df93  movdqa  [rbp+57h+var_60], xmm0
0x18000df98  mov     [rbp+57h+var_28], 48h ; 'H'
0x18000df9f  mov     [rbp+57h+var_18], 10h
0x18000dfa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfab  xor     eax, eax
0x18000dfad  add     rsp, 0B0h
0x18000dfb4  pop     rbp
0x18000dfb5  retn
```
