# WEBSOCKET_CONFIG::ReadConfig(IHttpContext *,WEBSOCKET_CONFIG * *,IAppHostConfigException * *)

- ea: `0x180002e44`
- end: `0x180003179`
- name: `?ReadConfig@WEBSOCKET_CONFIG@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAUIAppHostConfigException@@@Z`
- size: `821`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct WEBSOCKET_CONFIG **, struct IAppHostConfigException **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180006c98`
- `0x1800079b0`

## callees

- `0x180001008`
- `0x180002b04`
- `0x180002bf4`
- `0x180002cec`
- `0x180002e44`
- `0x180009010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002f31`
- `OLEAUT32!__imp_SysAllocString` at `0x180002f41`
- `OLEAUT32!__imp_SysAllocString` at `0x180002f31`
- `OLEAUT32!__imp_SysAllocString` at `0x180002f41`
- `OLEAUT32!__imp_SysFreeString` at `0x180002f7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180002f8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180002f7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180002f8c`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800030f1`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800030f1`

## string_xrefs

- `0x180003007`: `readBufferBlockSize`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONFIG::ReadConfig(
        struct IHttpContext *a1,
        struct WEBSOCKET_CONFIG **a2,
        struct IAppHostConfigException **a3)
{
  struct IAppHostConfigException **v3; // r15
  __int64 v6; // rax
  const OLECHAR *v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 (__fastcall ***v10)(_QWORD, void *); // rax
  volatile signed __int32 *v11; // rax
  char *v13; // rax
  volatile signed __int32 *v14; // rbx
  struct IHttpServer *v15; // rcx
  __int64 v16; // rdi
  OLECHAR *v17; // r15
  BSTR v18; // rax
  const unsigned __int16 *v19; // rdx
  OLECHAR *v20; // r14
  int ConfigBool; // edi
  BOOL v22; // eax
  const unsigned __int16 *v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  __int64 (__fastcall ***v28)(_QWORD, void *); // rax
  IErrorInfo *pperrinfo; // [rsp+70h] [rbp+40h] BYREF
  struct IAppHostElement *v30; // [rsp+78h] [rbp+48h] BYREF
  struct IAppHostConfigException **v31; // [rsp+80h] [rbp+50h]
  unsigned __int64 v32; // [rsp+88h] [rbp+58h] BYREF

  v31 = a3;
  v3 = a3;
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v7 = (const OLECHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  *a2 = 0;
  v8 = *(_QWORD *)a1;
  v30 = 0;
  LODWORD(pperrinfo) = 0;
  v32 = 0;
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v8 + 8))(a1);
  v10 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
  v11 = (volatile signed __int32 *)(**v10)(v10, g_pWebSocketModuleId);
  if ( v11 )
  {
    _InterlockedIncrement(v11 + 2);
    *a2 = (struct WEBSOCKET_CONFIG *)v11;
    return 0;
  }
  v13 = (char *)operator new(0x20u);
  v14 = (volatile signed __int32 *)v13;
  if ( !v13 )
  {
    ConfigBool = -2147024882;
    v14 = 0;
LABEL_25:
    pperrinfo = 0;
    if ( !GetErrorInfo(0, &pperrinfo) )
    {
      ((void (__fastcall *)(IErrorInfo *, GUID *, struct IAppHostConfigException **))pperrinfo->lpVtbl->QueryInterface)(
        pperrinfo,
        &IID_IAppHostConfigException,
        v3);
      ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
    }
    goto LABEL_27;
  }
  v15 = g_pGlobalInfo;
  *(_QWORD *)v13 = &WEBSOCKET_CONFIG::`vftable';
  *((_QWORD *)v13 + 1) = 1;
  *((_DWORD *)v13 + 4) = 1000;
  *(_QWORD *)(v13 + 20) = 4096;
  v16 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v15 + 56LL))(v15);
  v17 = SysAllocString(v7);
  v18 = SysAllocString(L"system.webServer/webSocket");
  v20 = v18;
  if ( v17 && v18 )
  {
    ConfigBool = (*(__int64 (__fastcall **)(__int64, BSTR, OLECHAR *, struct IAppHostElement **))(*(_QWORD *)v16 + 24LL))(
                   v16,
                   v18,
                   v17,
                   &v30);
  }
  else
  {
    ConfigBool = -2147024882;
    if ( !v18 )
      goto LABEL_9;
  }
  SysFreeString(v20);
LABEL_9:
  if ( v17 )
    SysFreeString(v17);
  if ( ConfigBool < 0
    || (ConfigBool = GetConfigBool(v30, v19, (int *)&pperrinfo), ConfigBool < 0)
    || (v22 = (_DWORD)pperrinfo != 0, (*((_DWORD *)v14 + 3) = v22) != 0)
    && ((ConfigBool = GetConfigDWORD(v30, L"receiveBufferLimit", (unsigned int *)v14 + 4), ConfigBool < 0)
     || (ConfigBool = GetConfigTimeSpan(v30, v23, &v32), ConfigBool < 0)
     || (*((_DWORD *)v14 + 6) = (unsigned int)v32 / 0x2710,
         ConfigBool = GetConfigDWORD(v30, L"readBufferBlockSize", (unsigned int *)v14 + 5),
         ConfigBool < 0)) )
  {
LABEL_23:
    v3 = v31;
    goto LABEL_25;
  }
  v24 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 24LL))(v24);
  v26 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, void *))(*(_QWORD *)v25 + 8LL))(
          v25,
          v14,
          g_pWebSocketModuleId);
  ConfigBool = v26;
  if ( v26 < 0 )
  {
    if ( v26 == -2147024811 )
    {
      ConfigBool = 0;
      if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 1);
      v27 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 8LL))(a1);
      v28 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
      v14 = (volatile signed __int32 *)(**v28)(v28, g_pWebSocketModuleId);
      goto LABEL_22;
    }
    goto LABEL_23;
  }
LABEL_22:
  _InterlockedIncrement(v14 + 2);
  *a2 = (struct WEBSOCKET_CONFIG *)v14;
  v14 = 0;
LABEL_27:
  if ( v30 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v30->lpVtbl->Release)(v30);
    v30 = 0;
  }
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 1);
  }
  return (unsigned int)ConfigBool;
}

```

## disassembly

```asm
0x180002e44  mov     [rsp-38h+arg_10], r8
0x180002e49  push    rbp
0x180002e4a  push    rbx
0x180002e4b  push    rdi
0x180002e4c  push    r12
0x180002e4e  push    r13
0x180002e50  push    r14
0x180002e52  push    r15
0x180002e54  mov     rbp, rsp
0x180002e57  sub     rsp, 30h
0x180002e5b  mov     rax, [rcx]
0x180002e5e  mov     r15, r8
0x180002e61  mov     r13, rdx
0x180002e64  mov     r12, rcx
0x180002e67  mov     rax, [rax+8]
0x180002e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e70  mov     rcx, rax
0x180002e73  mov     r9, [rax]
0x180002e76  mov     rax, [r9+10h]
0x180002e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e7f  xor     edi, edi
0x180002e81  mov     r14, rax
0x180002e84  mov     [r13+0], rdi
0x180002e88  mov     rcx, [r12]
0x180002e8c  mov     [rbp+arg_8], rdi
0x180002e90  mov     dword ptr [rbp+pperrinfo], edi
0x180002e93  mov     [rbp+arg_18], rdi
0x180002e97  mov     rax, [rcx+8]
0x180002e9b  mov     rcx, r12
0x180002e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea3  mov     rdx, rax
0x180002ea6  mov     rcx, [rax]
0x180002ea9  mov     rax, [rcx+18h]
0x180002ead  mov     rcx, rdx
0x180002eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eb5  mov     rdx, cs:?g_pWebSocketModuleId@@3PEAXEA; void * g_pWebSocketModuleId
0x180002ebc  mov     r8, rax
0x180002ebf  mov     rcx, [rax]
0x180002ec2  mov     rax, [rcx]
0x180002ec5  mov     rcx, r8
0x180002ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ecd  test    rax, rax
0x180002ed0  jz      short loc_180002EE1
0x180002ed2  lock inc dword ptr [rax+8]
0x180002ed6  mov     [r13+0], rax
0x180002eda  xor     eax, eax
0x180002edc  jmp     loc_180003169
0x180002ee1  mov     ecx, 20h ; ' '; Size
0x180002ee6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002eeb  mov     rbx, rax
0x180002eee  test    rax, rax
0x180002ef1  jz      loc_1800030DC
0x180002ef7  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002efe  lea     rax, ??_7WEBSOCKET_CONFIG@@6B@; const WEBSOCKET_CONFIG::`vftable'
0x180002f05  mov     [rbx], rax
0x180002f08  mov     qword ptr [rbx+8], 1
0x180002f10  mov     dword ptr [rbx+10h], 3E8h
0x180002f17  mov     qword ptr [rbx+14h], 1000h
0x180002f1f  mov     rax, [rcx]
0x180002f22  mov     rax, [rax+38h]
0x180002f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f2b  mov     rcx, r14; psz
0x180002f2e  mov     rdi, rax
0x180002f31  call    cs:__imp_SysAllocString
0x180002f37  lea     rcx, aSystemWebserve; "system.webServer/webSocket"
0x180002f3e  mov     r15, rax
0x180002f41  call    cs:__imp_SysAllocString
0x180002f47  mov     r14, rax
0x180002f4a  test    r15, r15
0x180002f4d  jz      short loc_180002F71
0x180002f4f  test    rax, rax
0x180002f52  jz      short loc_180002F71
0x180002f54  mov     rcx, [rdi]
0x180002f57  lea     r9, [rbp+arg_8]
0x180002f5b  mov     r8, r15
0x180002f5e  mov     rdx, r14
0x180002f61  mov     rax, [rcx+18h]
0x180002f65  mov     rcx, rdi
0x180002f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f6d  mov     edi, eax
0x180002f6f  jmp     short loc_180002F7B
0x180002f71  mov     edi, 8007000Eh
0x180002f76  test    r14, r14
0x180002f79  jz      short loc_180002F84
0x180002f7b  mov     rcx, r14; bstrString
0x180002f7e  call    cs:__imp_SysFreeString
0x180002f84  test    r15, r15
0x180002f87  jz      short loc_180002F92
0x180002f89  mov     rcx, r15; bstrString
0x180002f8c  call    cs:__imp_SysFreeString
0x180002f92  test    edi, edi
0x180002f94  js      loc_1800030D6
0x180002f9a  mov     rcx, [rbp+arg_8]; struct IAppHostElement *
0x180002f9e  lea     r8, [rbp+pperrinfo]; int *
0x180002fa2  call    ?GetConfigBool@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; GetConfigBool(IAppHostElement *,ushort const *,int *)
0x180002fa7  mov     edi, eax
0x180002fa9  test    eax, eax
0x180002fab  js      loc_1800030D6
0x180002fb1  xor     eax, eax
0x180002fb3  cmp     dword ptr [rbp+pperrinfo], eax
0x180002fb6  setnz   al
0x180002fb9  mov     [rbx+0Ch], eax
0x180002fbc  test    eax, eax
0x180002fbe  jz      short loc_180003021
0x180002fc0  mov     rcx, [rbp+arg_8]; struct IAppHostElement *
0x180002fc4  lea     r8, [rbx+10h]; unsigned int *
0x180002fc8  lea     rdx, aReceivebufferl; "receiveBufferLimit"
0x180002fcf  call    ?GetConfigDWORD@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; GetConfigDWORD(IAppHostElement *,ushort const *,ulong *)
0x180002fd4  mov     edi, eax
0x180002fd6  test    eax, eax
0x180002fd8  js      loc_1800030D6
0x180002fde  mov     rcx, [rbp+arg_8]; struct IAppHostElement *
0x180002fe2  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x180002fe6  call    ?GetConfigTimeSpan@@YAJPEAUIAppHostElement@@PEBGPEA_K@Z; GetConfigTimeSpan(IAppHostElement *,ushort const *,unsigned __int64 *)
0x180002feb  mov     edi, eax
0x180002fed  test    eax, eax
0x180002fef  js      loc_1800030D6
0x180002ff5  mov     eax, 0D1B71759h
0x180002ffa  lea     r8, [rbx+14h]; unsigned int *
0x180002ffe  mul     dword ptr [rbp+arg_18]
0x180003001  shr     edx, 0Dh
0x180003004  mov     [rbx+18h], edx
0x180003007  lea     rdx, aReadbufferbloc; "readBufferBlockSize"
0x18000300e  mov     rcx, [rbp+arg_8]; struct IAppHostElement *
0x180003012  call    ?GetConfigDWORD@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; GetConfigDWORD(IAppHostElement *,ushort const *,ulong *)
0x180003017  mov     edi, eax
0x180003019  test    eax, eax
0x18000301b  js      loc_1800030D6
0x180003021  mov     rax, [r12]
0x180003025  mov     rcx, r12
0x180003028  mov     rax, [rax+8]
0x18000302c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003031  mov     rdx, rax
0x180003034  mov     rcx, [rax]
0x180003037  mov     rax, [rcx+18h]
0x18000303b  mov     rcx, rdx
0x18000303e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003043  mov     r8, cs:?g_pWebSocketModuleId@@3PEAXEA; void * g_pWebSocketModuleId
0x18000304a  mov     r9, rax
0x18000304d  mov     rdx, rbx
0x180003050  mov     rcx, [rax]
0x180003053  mov     rax, [rcx+8]
0x180003057  mov     rcx, r9
0x18000305a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000305f  mov     edi, eax
0x180003061  test    eax, eax
0x180003063  jns     short loc_1800030CA
0x180003065  cmp     eax, 80070055h
0x18000306a  jnz     short loc_1800030D6
0x18000306c  xor     edi, edi
0x18000306e  or      eax, 0FFFFFFFFh
0x180003071  lock xadd [rbx+8], eax
0x180003076  cmp     eax, 1
0x180003079  jnz     short loc_18000308D
0x18000307b  mov     rax, [rbx]
0x18000307e  lea     edx, [rdi+1]
0x180003081  mov     rcx, rbx
0x180003084  mov     rax, [rax+8]
0x180003088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000308d  mov     rax, [r12]
0x180003091  mov     rcx, r12
0x180003094  mov     rax, [rax+8]
0x180003098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309d  mov     rdx, rax
0x1800030a0  mov     rcx, [rax]
0x1800030a3  mov     rax, [rcx+18h]
0x1800030a7  mov     rcx, rdx
0x1800030aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030af  mov     rdx, cs:?g_pWebSocketModuleId@@3PEAXEA; void * g_pWebSocketModuleId
0x1800030b6  mov     r8, rax
0x1800030b9  mov     rcx, [rax]
0x1800030bc  mov     rax, [rcx]
0x1800030bf  mov     rcx, r8
0x1800030c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c7  mov     rbx, rax
0x1800030ca  lock inc dword ptr [rbx+8]
0x1800030ce  mov     [r13+0], rbx
0x1800030d2  xor     ebx, ebx
0x1800030d4  jmp     short loc_180003124
0x1800030d6  mov     r15, [rbp+arg_10]
0x1800030da  jmp     short loc_1800030E3
0x1800030dc  mov     edi, 8007000Eh
0x1800030e1  xor     ebx, ebx
0x1800030e3  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x1800030e7  mov     [rbp+pperrinfo], 0
0x1800030ef  xor     ecx, ecx; dwReserved
0x1800030f1  call    cs:__imp_GetErrorInfo
0x1800030f7  test    eax, eax
0x1800030f9  jnz     short loc_180003124
0x1800030fb  mov     rcx, [rbp+pperrinfo]
0x1800030ff  lea     rdx, IID_IAppHostConfigException
0x180003106  mov     r8, r15
0x180003109  mov     rax, [rcx]
0x18000310c  mov     rax, [rax]
0x18000310f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003114  mov     rcx, [rbp+pperrinfo]
0x180003118  mov     rax, [rcx]
0x18000311b  mov     rax, [rax+10h]
0x18000311f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003124  mov     rcx, [rbp+arg_8]
0x180003128  test    rcx, rcx
0x18000312b  jz      short loc_180003141
0x18000312d  mov     rax, [rcx]
0x180003130  mov     rax, [rax+10h]
0x180003134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003139  mov     [rbp+arg_8], 0
0x180003141  test    rbx, rbx
0x180003144  jz      short loc_180003167
0x180003146  or      eax, 0FFFFFFFFh
0x180003149  lock xadd [rbx+8], eax
0x18000314e  cmp     eax, 1
0x180003151  jnz     short loc_180003167
0x180003153  mov     rax, [rbx]
0x180003156  mov     edx, 1
0x18000315b  mov     rcx, rbx
0x18000315e  mov     rax, [rax+8]
0x180003162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003167  mov     eax, edi
0x180003169  add     rsp, 30h
0x18000316d  pop     r15
0x18000316f  pop     r14
0x180003171  pop     r13
0x180003173  pop     r12
0x180003175  pop     rdi
0x180003176  pop     rbx
0x180003177  pop     rbp
0x180003178  retn
```
