# IISGeneralEvents::GENERAL_TRACE_HANDLER::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x180003e74`
- end: `0x180003f1d`
- name: `?RaiseEvent@GENERAL_TRACE_HANDLER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003aa4`

## callees

- `0x180005010`

## pseudocode

```c
__int64 __fastcall IISGeneralEvents::GENERAL_TRACE_HANDLER::RaiseEvent(
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
  v4[3] = 17;
  v8 = 1;
  v4[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v4[2] = &`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid;
  v4[4] = L"GENERAL_TRACE_HANDLER";
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
0x180003e74  mov     r11, rsp
0x180003e77  sub     rsp, 0B8h
0x180003e7e  xor     eax, eax
0x180003e80  mov     dword ptr [r11-30h], 48h ; 'H'
0x180003e88  mov     [rsp+0B8h+var_90], rax
0x180003e8d  xor     edx, edx
0x180003e8f  mov     qword ptr [r11-80h], 11h
0x180003e97  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180003e9e  mov     qword ptr [r11-50h], 1
0x180003ea6  xorps   xmm0, xmm0
0x180003ea9  mov     [rsp+0B8h+var_98], rax
0x180003eae  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180003eb5  mov     [rsp+0B8h+var_88], rax
0x180003eba  lea     rax, aGeneralTraceHa; "GENERAL_TRACE_HANDLER"
0x180003ec1  mov     [r11-78h], rax
0x180003ec5  lea     rax, aContextid; "ContextId"
0x180003ecc  mov     [r11-38h], rax
0x180003ed0  lea     rax, [r11-38h]
0x180003ed4  mov     qword ptr [r11-70h], 1
0x180003edc  mov     [rsp+0B8h+var_58], edx
0x180003ee0  movdqa  [rsp+0B8h+var_68], xmm0
0x180003ee6  mov     [rsp+0B8h+var_54], 1
0x180003eee  mov     [r11-48h], rax
0x180003ef2  mov     rax, [rcx]
0x180003ef5  mov     [r11-28h], rdx
0x180003ef9  mov     [r11-18h], rdx
0x180003efd  lea     rdx, [rsp+0B8h+var_98]
0x180003f02  mov     dword ptr [r11-20h], 10h
0x180003f0a  mov     rax, [rax+10h]
0x180003f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f13  xor     eax, eax
0x180003f15  add     rsp, 0B8h
0x180003f1c  retn
```
