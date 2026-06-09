# IISGeneralEvents::GENERAL_NOT_SEND_CUSTOM_ERROR::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x1800043e0`
- end: `0x1800044fb`
- name: `?RaiseEvent@GENERAL_NOT_SEND_CUSTOM_ERROR@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `283`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005394`

## callees

- `0x1800043e0`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall IISGeneralEvents::GENERAL_NOT_SEND_CUSTOM_ERROR::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3)
{
  int v3; // r8d
  int v4; // r8d
  int v5; // r8d
  const wchar_t *v6; // rax
  _QWORD v8[5]; // [rsp+20h] [rbp-59h] BYREF
  int v9; // [rsp+48h] [rbp-31h]
  int v10; // [rsp+4Ch] [rbp-2Dh]
  __int128 v11; // [rsp+50h] [rbp-29h]
  int v12; // [rsp+60h] [rbp-19h]
  int v13; // [rsp+64h] [rbp-15h]
  __int64 v14; // [rsp+68h] [rbp-11h]
  const wchar_t **v15; // [rsp+70h] [rbp-9h]
  const wchar_t *v16; // [rsp+80h] [rbp+7h] BYREF
  int v17; // [rsp+88h] [rbp+Fh]
  __int64 v18; // [rsp+90h] [rbp+17h]
  int v19; // [rsp+98h] [rbp+1Fh]
  __int64 v20; // [rsp+A0h] [rbp+27h]
  const wchar_t *v21; // [rsp+A8h] [rbp+2Fh]
  int v22; // [rsp+B0h] [rbp+37h]
  int *v23; // [rsp+B8h] [rbp+3Fh]
  int v24; // [rsp+C0h] [rbp+47h]
  const wchar_t *v25; // [rsp+C8h] [rbp+4Fh]
  int v26; // [rsp+F0h] [rbp+77h] BYREF

  v26 = a3;
  v8[3] = 52;
  v8[1] = 0;
  v14 = 2;
  v8[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v8[2] = &`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid;
  v8[4] = L"GENERAL_NOT_SEND_CUSTOM_ERROR";
  v9 = 1;
  v13 = 1;
  v16 = L"ContextId";
  v21 = L"Reason";
  v23 = &v26;
  v10 = 5;
  v11 = 0;
  v12 = 0;
  v17 = 72;
  v18 = 0;
  v19 = 16;
  v20 = 0;
  v22 = 19;
  v24 = 4;
  if ( a3 )
  {
    v3 = a3 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          if ( v5 == 1 )
            v6 = L"EXISTINGRESPONSE_AUTO";
          else
            v6 = 0;
        }
        else
        {
          v6 = L"EXISTINGRESPONSE_PASSTHROUGH";
        }
      }
      else
      {
        v6 = L"SETSTATUS_TRYSKIP";
      }
    }
    else
    {
      v6 = L"SETSTATUS_SUCCESS";
    }
  }
  else
  {
    v6 = L"UNKNOWN";
  }
  v25 = v6;
  v15 = &v16;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v8);
  return 0;
}

```

## disassembly

```asm
0x1800043e0  mov     [rsp-8+arg_10], r8d
0x1800043e5  push    rbp
0x1800043e6  lea     rbp, [rsp-57h]
0x1800043eb  sub     rsp, 0D0h
0x1800043f2  xor     eax, eax
0x1800043f4  mov     [rbp+57h+var_98], 34h ; '4'
0x1800043fc  mov     [rbp+57h+var_A8], rax
0x180004400  xor     edx, edx
0x180004402  mov     [rbp+57h+var_68], 2
0x18000440a  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004411  mov     [rbp+57h+var_B0], rax
0x180004415  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000441c  mov     [rbp+57h+var_A0], rax
0x180004420  lea     rax, aGeneralNotSend; "GENERAL_NOT_SEND_CUSTOM_ERROR"
0x180004427  mov     [rbp+57h+var_90], rax
0x18000442b  lea     eax, [rdx+1]
0x18000442e  mov     [rbp+57h+var_88], eax
0x180004431  xorps   xmm0, xmm0
0x180004434  mov     [rbp+57h+var_6C], eax
0x180004437  lea     rax, aContextid; "ContextId"
0x18000443e  mov     [rbp+57h+var_50], rax
0x180004442  lea     rax, aReason; "Reason"
0x180004449  mov     [rbp+57h+var_28], rax
0x18000444d  lea     rax, [rbp+57h+arg_10]
0x180004451  mov     [rbp+57h+var_18], rax
0x180004455  mov     [rbp+57h+var_84], 5
0x18000445c  movdqa  [rbp+57h+var_80], xmm0
0x180004461  mov     [rbp+57h+var_70], edx
0x180004464  mov     [rbp+57h+var_48], 48h ; 'H'
0x18000446b  mov     [rbp+57h+var_40], rdx
0x18000446f  mov     [rbp+57h+var_38], 10h
0x180004476  mov     [rbp+57h+var_30], rdx
0x18000447a  mov     [rbp+57h+var_20], 13h
0x180004481  mov     [rbp+57h+var_10], 4
0x180004488  test    r8d, r8d
0x18000448b  jz      short loc_1800044CD
0x18000448d  sub     r8d, 1
0x180004491  jz      short loc_1800044C4
0x180004493  sub     r8d, 1
0x180004497  jz      short loc_1800044BB
0x180004499  sub     r8d, 1
0x18000449d  jz      short loc_1800044B2
0x18000449f  cmp     r8d, 1
0x1800044a3  jz      short loc_1800044A9
0x1800044a5  mov     eax, edx
0x1800044a7  jmp     short loc_1800044D4
0x1800044a9  lea     rax, aExistingrespon_0; "EXISTINGRESPONSE_AUTO"
0x1800044b0  jmp     short loc_1800044D4
0x1800044b2  lea     rax, aExistingrespon_1; "EXISTINGRESPONSE_PASSTHROUGH"
0x1800044b9  jmp     short loc_1800044D4
0x1800044bb  lea     rax, aSetstatusTrysk; "SETSTATUS_TRYSKIP"
0x1800044c2  jmp     short loc_1800044D4
0x1800044c4  lea     rax, aSetstatusSucce; "SETSTATUS_SUCCESS"
0x1800044cb  jmp     short loc_1800044D4
0x1800044cd  lea     rax, aUnknown_0; "UNKNOWN"
0x1800044d4  mov     [rbp+57h+var_8], rax
0x1800044d8  lea     rdx, [rbp+57h+var_B0]
0x1800044dc  lea     rax, [rbp+57h+var_50]
0x1800044e0  mov     [rbp+57h+var_60], rax
0x1800044e4  mov     rax, [rcx]
0x1800044e7  mov     rax, [rax+10h]
0x1800044eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044f0  xor     eax, eax
0x1800044f2  add     rsp, 0D0h
0x1800044f9  pop     rbp
0x1800044fa  retn
```
