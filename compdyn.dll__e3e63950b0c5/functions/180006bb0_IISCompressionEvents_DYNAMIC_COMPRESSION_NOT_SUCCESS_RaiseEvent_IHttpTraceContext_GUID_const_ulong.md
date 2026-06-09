# IISCompressionEvents::DYNAMIC_COMPRESSION_NOT_SUCCESS::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x180006bb0`
- end: `0x180006c94`
- name: `?RaiseEvent@DYNAMIC_COMPRESSION_NOT_SUCCESS@IISCompressionEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `228`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001eb0`

## callees

- `0x180006fc0`
- `0x180008010`

## string_xrefs

- `0x180006bf7`: `DYNAMIC_COMPRESSION_NOT_SUCCESS`

## pseudocode

```c
__int64 __fastcall IISCompressionEvents::DYNAMIC_COMPRESSION_NOT_SUCCESS::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3)
{
  __int64 v3; // r9
  _QWORD v5[5]; // [rsp+20h] [rbp-59h] BYREF
  int v6; // [rsp+48h] [rbp-31h]
  int v7; // [rsp+4Ch] [rbp-2Dh]
  __int128 v8; // [rsp+50h] [rbp-29h]
  int v9; // [rsp+60h] [rbp-19h]
  int v10; // [rsp+64h] [rbp-15h]
  __int64 v11; // [rsp+68h] [rbp-11h]
  const wchar_t **v12; // [rsp+70h] [rbp-9h]
  const wchar_t *v13; // [rsp+80h] [rbp+7h] BYREF
  int v14; // [rsp+88h] [rbp+Fh]
  __int64 v15; // [rsp+90h] [rbp+17h]
  int v16; // [rsp+98h] [rbp+1Fh]
  __int64 v17; // [rsp+A0h] [rbp+27h]
  const wchar_t *v18; // [rsp+A8h] [rbp+2Fh]
  int v19; // [rsp+B0h] [rbp+37h]
  int *v20; // [rsp+B8h] [rbp+3Fh]
  int v21; // [rsp+C0h] [rbp+47h]
  const wchar_t *v22; // [rsp+C8h] [rbp+4Fh]
  int v23; // [rsp+F0h] [rbp+77h] BYREF

  v23 = a3;
  v5[1] = 64;
  v5[3] = 8;
  v9 = 0;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v15 = 0;
  v5[2] = &`IISCompressionEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"DYNAMIC_COMPRESSION_NOT_SUCCESS";
  v13 = L"ContextId";
  v18 = L"Reason";
  v17 = 0;
  v20 = &v23;
  v11 = 2;
  v6 = 1;
  v7 = 4;
  v8 = 0;
  v10 = 1;
  v14 = 72;
  v16 = 16;
  v19 = 19;
  v21 = 4;
  v22 = IISCompressionEvents::DYNAMIC_COMPRESSION_NOT_SUCCESS::TranslateEnumReasonToString(a3);
  v12 = &v13;
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v3 + 16LL))(v3, v5);
  return 0;
}

```

## disassembly

```asm
0x180006bb0  mov     [rsp-8+arg_10], r8d
0x180006bb5  push    rbp
0x180006bb6  lea     rbp, [rsp-57h]
0x180006bbb  sub     rsp, 0D0h
0x180006bc2  mov     r9, rcx
0x180006bc5  mov     [rbp+57h+var_A8], 40h ; '@'
0x180006bcd  xor     ecx, ecx
0x180006bcf  mov     [rbp+57h+var_98], 8
0x180006bd7  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180006bde  mov     [rbp+57h+var_70], ecx
0x180006be1  mov     [rbp+57h+var_B0], rax
0x180006be5  xorps   xmm0, xmm0
0x180006be8  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCompressionEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCompressionEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180006bef  mov     [rbp+57h+var_40], rcx
0x180006bf3  mov     [rbp+57h+var_A0], rax
0x180006bf7  lea     rax, aDynamicCompres_0; "DYNAMIC_COMPRESSION_NOT_SUCCESS"
0x180006bfe  mov     [rbp+57h+var_90], rax
0x180006c02  lea     rax, aContextid; "ContextId"
0x180006c09  mov     [rbp+57h+var_50], rax
0x180006c0d  lea     rax, aReason; "Reason"
0x180006c14  mov     [rbp+57h+var_28], rax
0x180006c18  lea     rax, [rbp+57h+arg_10]
0x180006c1c  mov     [rbp+57h+var_30], rcx
0x180006c20  mov     ecx, r8d
0x180006c23  mov     [rbp+57h+var_18], rax
0x180006c27  mov     [rbp+57h+var_68], 2
0x180006c2f  mov     [rbp+57h+var_88], 1
0x180006c36  mov     [rbp+57h+var_84], 4
0x180006c3d  movdqa  [rbp+57h+var_80], xmm0
0x180006c42  mov     [rbp+57h+var_6C], 1
0x180006c49  mov     [rbp+57h+var_48], 48h ; 'H'
0x180006c50  mov     [rbp+57h+var_38], 10h
0x180006c57  mov     [rbp+57h+var_20], 13h
0x180006c5e  mov     [rbp+57h+var_10], 4
0x180006c65  call    ?TranslateEnumReasonToString@DYNAMIC_COMPRESSION_NOT_SUCCESS@IISCompressionEvents@@SAPEBGW4enumReason@12@@Z; IISCompressionEvents::DYNAMIC_COMPRESSION_NOT_SUCCESS::TranslateEnumReasonToString(IISCompressionEvents::DYNAMIC_COMPRESSION_NOT_SUCCESS::enumReason)
0x180006c6a  mov     [rbp+57h+var_8], rax
0x180006c6e  lea     rdx, [rbp+57h+var_B0]
0x180006c72  lea     rax, [rbp+57h+var_50]
0x180006c76  mov     rcx, r9
0x180006c79  mov     [rbp+57h+var_60], rax
0x180006c7d  mov     rax, [r9]
0x180006c80  mov     rax, [rax+10h]
0x180006c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c89  xor     eax, eax
0x180006c8b  add     rsp, 0D0h
0x180006c92  pop     rbp
0x180006c93  retn
```
