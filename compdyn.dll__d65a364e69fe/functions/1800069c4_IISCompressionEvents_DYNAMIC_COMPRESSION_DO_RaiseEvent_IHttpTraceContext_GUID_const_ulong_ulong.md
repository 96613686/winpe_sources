# IISCompressionEvents::DYNAMIC_COMPRESSION_DO::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ulong)

- ea: `0x1800069c4`
- end: `0x180006aeb`
- name: `?RaiseEvent@DYNAMIC_COMPRESSION_DO@IISCompressionEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KK@Z`
- size: `295`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002820`

## callees

- `0x180004c10`
- `0x180008010`

## string_xrefs

- `0x180006a17`: `DYNAMIC_COMPRESSION_DO`
- `0x180006a41`: `CompressedSize`

## pseudocode

```c
__int64 __fastcall IISCompressionEvents::DYNAMIC_COMPRESSION_DO::RaiseEvent(
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
  v7[1] = 64;
  v11 = 0;
  v7[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v17 = 0;
  v7[2] = &`IISCompressionEvents::GetAreaGuid'::`2'::AreaGuid;
  v7[4] = L"DYNAMIC_COMPRESSION_DO";
  v15 = L"ContextId";
  v20 = L"OriginalSize";
  v22 = &v30;
  v25 = L"CompressedSize";
  v27 = &v31;
  v14 = &v15;
  v4 = *(_QWORD *)a1;
  v19 = 0;
  v24 = 0;
  v29 = 0;
  v5 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v4 + 16);
  v7[3] = 9;
  v13 = 3;
  v8 = 1;
  v9 = 5;
  v10 = 0;
  v12 = 1;
  v16 = 72;
  v18 = 16;
  v21 = 19;
  v23 = 4;
  v26 = 19;
  v28 = 4;
  v5(a1, v7);
  return 0;
}

```

## disassembly

```asm
0x1800069c4  mov     [rsp-8+arg_18], r9d
0x1800069c9  mov     [rsp-8+arg_10], r8d
0x1800069ce  push    rbp
0x1800069cf  lea     rbp, [rsp-10h]
0x1800069d4  sub     rsp, 110h
0x1800069db  mov     rax, cs:__security_cookie
0x1800069e2  xor     rax, rsp
0x1800069e5  mov     [rbp+10h+var_10], rax
0x1800069e9  xor     edx, edx
0x1800069eb  mov     [rsp+110h+var_E8], 40h ; '@'
0x1800069f4  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800069fb  mov     [rsp+110h+var_B0], edx
0x1800069ff  mov     [rsp+110h+var_F0], rax
0x180006a04  xorps   xmm0, xmm0
0x180006a07  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCompressionEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCompressionEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180006a0e  mov     [rbp+10h+var_80], rdx
0x180006a12  mov     [rsp+110h+var_E0], rax
0x180006a17  lea     rax, aDynamicCompres_1; "DYNAMIC_COMPRESSION_DO"
0x180006a1e  mov     [rsp+110h+var_D0], rax
0x180006a23  lea     rax, aContextid; "ContextId"
0x180006a2a  mov     [rbp+10h+var_90], rax
0x180006a2e  lea     rax, aOriginalsize; "OriginalSize"
0x180006a35  mov     [rbp+10h+var_68], rax
0x180006a39  lea     rax, [rbp+10h+arg_10]
0x180006a3d  mov     [rbp+10h+var_58], rax
0x180006a41  lea     rax, aCompressedsize; "CompressedSize"
0x180006a48  mov     [rbp+10h+var_40], rax
0x180006a4c  lea     rax, [rbp+10h+arg_18]
0x180006a50  mov     [rbp+10h+var_30], rax
0x180006a54  lea     rax, [rbp+10h+var_90]
0x180006a58  mov     [rsp+110h+var_A0], rax
0x180006a5d  mov     rax, [rcx]
0x180006a60  mov     [rbp+10h+var_70], rdx
0x180006a64  mov     [rbp+10h+var_48], rdx
0x180006a68  mov     [rbp+10h+var_20], rdx
0x180006a6c  lea     rdx, [rsp+110h+var_F0]
0x180006a71  mov     rax, [rax+10h]
0x180006a75  mov     [rsp+110h+var_D8], 9
0x180006a7e  mov     [rsp+110h+var_A8], 3
0x180006a87  mov     [rsp+110h+var_C8], 1
0x180006a8f  mov     [rsp+110h+var_C4], 5
0x180006a97  movdqa  [rsp+110h+var_C0], xmm0
0x180006a9d  mov     [rsp+110h+var_AC], 1
0x180006aa5  mov     [rbp+10h+var_88], 48h ; 'H'
0x180006aac  mov     [rbp+10h+var_78], 10h
0x180006ab3  mov     [rbp+10h+var_60], 13h
0x180006aba  mov     [rbp+10h+var_50], 4
0x180006ac1  mov     [rbp+10h+var_38], 13h
0x180006ac8  mov     [rbp+10h+var_28], 4
0x180006acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad4  xor     eax, eax
0x180006ad6  mov     rcx, [rbp+10h+var_10]
0x180006ada  xor     rcx, rsp; StackCookie
0x180006add  call    __security_check_cookie
0x180006ae2  add     rsp, 110h
0x180006ae9  pop     rbp
0x180006aea  retn
```
