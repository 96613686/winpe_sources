# IISGeneralEvents::GENERAL_OPTIONS_HANDLER::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x180004018`
- end: `0x1800040c1`
- name: `?RaiseEvent@GENERAL_OPTIONS_HANDLER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003f24`

## callees

- `0x180005010`

## pseudocode

```c
__int64 __fastcall IISGeneralEvents::GENERAL_OPTIONS_HANDLER::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2)
{
  __int64 v2; // rax
  _QWORD v4[6]; // [rsp+20h] [rbp-98h] BYREF
  __int128 v5; // [rsp+50h] [rbp-68h]
  int v6; // [rsp+60h] [rbp-58h]
  int v7; // [rsp+64h] [rbp-54h]
  __int64 v8; // [rsp+68h] [rbp-50h]
  const wchar_t **v9; // [rsp+70h] [rbp-48h]
  const wchar_t *v10; // [rsp+80h] [rbp-38h] BYREF
  int v11; // [rsp+88h] [rbp-30h]
  __int64 v12; // [rsp+90h] [rbp-28h]
  int v13; // [rsp+98h] [rbp-20h]
  __int64 v14; // [rsp+A0h] [rbp-18h]

  v11 = 72;
  v4[1] = 0;
  v4[3] = 16;
  v8 = 1;
  v4[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v4[2] = &`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid;
  v4[4] = L"GENERAL_OPTIONS_HANDLER";
  v10 = L"ContextId";
  v4[5] = 1;
  v6 = 0;
  v5 = 0;
  v7 = 1;
  v9 = &v10;
  v2 = *(_QWORD *)a1;
  v12 = 0;
  v14 = 0;
  v13 = 16;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v2 + 16))(a1, v4);
  return 0;
}

```

## disassembly

```asm
0x180004018  mov     r11, rsp
0x18000401b  sub     rsp, 0B8h
0x180004022  xor     eax, eax
0x180004024  mov     dword ptr [r11-30h], 48h ; 'H'
0x18000402c  mov     [rsp+0B8h+var_90], rax
0x180004031  xor     edx, edx
0x180004033  mov     qword ptr [r11-80h], 10h
0x18000403b  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004042  mov     qword ptr [r11-50h], 1
0x18000404a  xorps   xmm0, xmm0
0x18000404d  mov     [rsp+0B8h+var_98], rax
0x180004052  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180004059  mov     [rsp+0B8h+var_88], rax
0x18000405e  lea     rax, aGeneralOptions; "GENERAL_OPTIONS_HANDLER"
0x180004065  mov     [r11-78h], rax
0x180004069  lea     rax, aContextid; "ContextId"
0x180004070  mov     [r11-38h], rax
0x180004074  lea     rax, [r11-38h]
0x180004078  mov     qword ptr [r11-70h], 1
0x180004080  mov     [rsp+0B8h+var_58], edx
0x180004084  movdqa  [rsp+0B8h+var_68], xmm0
0x18000408a  mov     [rsp+0B8h+var_54], 1
0x180004092  mov     [r11-48h], rax
0x180004096  mov     rax, [rcx]
0x180004099  mov     [r11-28h], rdx
0x18000409d  mov     [r11-18h], rdx
0x1800040a1  lea     rdx, [rsp+0B8h+var_98]
0x1800040a6  mov     dword ptr [r11-20h], 10h
0x1800040ae  mov     rax, [rax+10h]
0x1800040b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040b7  xor     eax, eax
0x1800040b9  add     rsp, 0B8h
0x1800040c0  retn
```
