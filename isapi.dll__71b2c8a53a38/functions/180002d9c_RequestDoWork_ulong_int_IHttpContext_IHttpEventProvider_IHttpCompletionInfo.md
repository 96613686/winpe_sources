# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180002d9c`
- end: `0x1800032a8`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `1292`
- prototype: `__int64 __fastcall(int, __int64, struct IHttpContext *, __int64, __int64)`
- caller_count: `17`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800021b0`
- `0x180002220`
- `0x180002280`
- `0x1800022f0`
- `0x180002360`
- `0x1800023d0`
- `0x180002440`
- `0x1800024b0`
- `0x180002540`
- `0x1800025b0`
- `0x180002620`
- `0x180002890`
- `0x180002900`
- `0x180002970`
- `0x1800029e0`
- `0x180002a90`
- `0x180002b80`

## callees

- `0x180001a24`
- `0x180001ddc`
- `0x180002d9c`
- `0x1800033a0`
- `0x180005224`
- `0x18000b3d0`
- `0x180013010`

## import_xrefs

- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180002e70`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180002e9a`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180002e70`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180002e9a`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180002ea7`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180002ea7`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x180002eb4`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x180002eb4`

## pseudocode

```c
__int64 __fastcall RequestDoWork(int a1, __int64 a2, struct IHttpContext *a3, __int64 a4, __int64 a5)
{
  int v8; // r15d
  unsigned int v9; // r12d
  unsigned int v10; // edi
  int Isapi; // edi
  __int64 (__fastcall ***v12)(_QWORD, void *); // rax
  __int64 v13; // rax
  STRA *v14; // rsi
  _WORD *v15; // rbx
  __int64 v16; // rdi
  __int64 v18; // rax
  void *v19; // rsi
  __int64 v20; // rax
  const unsigned __int16 *v21; // r14
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  ISAPI_DLL_MANAGER *v27; // rcx
  void *v28; // rdi
  __int64 v29; // rax
  __int64 v30; // rax
  W3_ISAPI_HANDLER *v31; // rax
  ISAPI_DLL *v32; // rsi
  W3_ISAPI_HANDLER *v33; // r14
  __int64 v34; // rax
  __int64 v35; // rcx
  unsigned int v36; // r9d
  unsigned int v37; // r8d
  int v38; // edx
  __int64 v39; // rax
  __int64 v40; // rax
  unsigned int v41; // eax
  bool v42; // zf
  struct IHttpContext *v43; // rcx
  __int64 (__fastcall *v44)(struct IHttpContext *); // rax
  __int64 v45; // rax
  __int64 v46; // rdx
  const char *v47; // r8
  __int64 v48; // r9
  __int64 v49; // rax
  __int64 (__fastcall ***v50)(_QWORD, void *); // rax
  __int64 v51; // rax
  __int64 v52; // [rsp+40h] [rbp-28h] BYREF
  struct ISAPI_DLL *v53; // [rsp+48h] [rbp-20h] BYREF
  struct INativeSectionException *v54; // [rsp+50h] [rbp-18h] BYREF

  v54 = 0;
  v52 = 0;
  v53 = 0;
  if ( a5 )
  {
    v8 = 1;
    v9 = (**(__int64 (__fastcall ***)(__int64))a5)(a5);
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
  }
  else
  {
    v8 = 0;
    v10 = 0;
    v9 = 0;
  }
  if ( a1 == 128 )
  {
    v18 = *(_QWORD *)a3;
    if ( !v8 )
    {
      v19 = 0;
      v20 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v18 + 192))(a3);
      v21 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 24LL))(v20, 0);
      if ( !*v21 )
        v21 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a3 + 184LL))(
                                          a3,
                                          0);
      v22 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 160LL))(a3);
      v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v24 = *(_QWORD *)a3;
      if ( v23 )
      {
        v25 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v24 + 160))(a3);
        v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        v28 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 56LL))(v26);
      }
      else
      {
        v29 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v24 + 48))(a3);
        v28 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 32LL))(v29);
        if ( v28 )
        {
          v30 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 48LL))(a3);
          v19 = (void *)(*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)v30 + 80LL))(v30, "SID");
        }
      }
      Isapi = ISAPI_DLL_MANAGER::GetIsapi(v27, v21, &v53, v28, v19, &v54, a3);
      if ( Isapi < 0 )
      {
        v32 = v53;
      }
      else
      {
        v31 = (W3_ISAPI_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a3 + 144LL))(
                                    a3,
                                    416);
        v32 = v53;
        if ( v31 )
        {
          v33 = W3_ISAPI_HANDLER::W3_ISAPI_HANDLER(v31, a3, v53, v21);
          if ( v33 )
          {
            v32 = 0;
            v34 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
            Isapi = (*(__int64 (__fastcall **)(__int64, W3_ISAPI_HANDLER *, void *))(*(_QWORD *)v34 + 8LL))(
                      v34,
                      v33,
                      g_pModuleContext);
            v35 = (__int64)v33;
            if ( Isapi < 0 )
            {
              (**(void (__fastcall ***)(W3_ISAPI_HANDLER *))v33)(v33);
              goto LABEL_31;
            }
            v36 = 0;
            v37 = 0;
            v38 = 0;
            return W3_ISAPI_HANDLER::DoWork(v35, v38, v37, v36);
          }
        }
        Isapi = -2147024888;
      }
LABEL_31:
      if ( v32 )
        ISAPI_DLL::DereferenceIsapiDll(v32);
LABEL_33:
      v39 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39) + 536) = 0;
      if ( Isapi >= 0 )
        return 2;
      if ( v54 )
      {
        (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v54)(
          v54,
          &IID_IAppHostConfigException,
          &v52);
        v40 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v40 + 24LL))(
          v40,
          500,
          "Internal Server Error",
          19,
          Isapi,
          v52,
          0);
        if ( v52 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
          v52 = 0;
        }
        (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v54 + 16LL))(v54);
        return 2;
      }
      v41 = WIN32_FROM_HRESULT(Isapi);
      if ( v41 != 3 )
      {
        if ( v41 == 5 )
        {
          v45 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
          v46 = 401;
          v47 = "Unauthorized";
          v48 = 3;
          goto LABEL_49;
        }
        if ( v41 != 123 && v41 != 126 )
        {
          v42 = v41 == 1260;
          v43 = a3;
          v44 = *(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL);
          if ( !v42 )
            goto LABEL_43;
          v45 = v44(a3);
          v48 = 2;
          v47 = "Not Found";
          v46 = 404;
LABEL_49:
          (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v45 + 24LL))(
            v45,
            v46,
            v47,
            v48,
            Isapi,
            0,
            0);
          return 2;
        }
      }
      v49 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 192LL))(a3);
      v42 = *(_WORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 24LL))(v49, 0) == 0;
      v43 = a3;
      v44 = *(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL);
      if ( v42 )
      {
        v45 = v44(a3);
        v46 = 404;
        v47 = "Not Found";
        goto LABEL_48;
      }
LABEL_43:
      v45 = v44(v43);
      v46 = 500;
      v47 = "Internal Server Error";
LABEL_48:
      v48 = 0;
      goto LABEL_49;
    }
    v50 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(v18 + 56))(a3);
    v51 = (**v50)(v50, g_pModuleContext);
    v36 = v10;
    v37 = v9;
    v38 = 1;
    v35 = v51;
    return W3_ISAPI_HANDLER::DoWork(v35, v38, v37, v36);
  }
  Isapi = 0;
  if ( a1 != 0x20000000 )
    goto LABEL_33;
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a4 + 48LL))(a4) )
  {
    v12 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
    v13 = (**v12)(v12, g_pModuleContext);
    if ( v13 )
    {
      v14 = (STRA *)(v13 + 216);
      v15 = (_WORD *)(v13 + 400);
      if ( !STRA::IsEmpty((STRA *)(v13 + 216)) || *v15 )
      {
        v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 32LL))(a4);
        if ( v16 )
        {
          if ( !STRA::IsEmpty(v14) )
          {
            *(_QWORD *)(v16 + 88) = STRA::QueryStr(v14);
            *(_WORD *)(v16 + 18) = STRA::QueryCB(v14);
          }
          if ( *v15 )
            *(_WORD *)(v16 + 130) = *v15;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002d9c  push    rbp
0x180002d9e  push    rbx
0x180002d9f  push    rsi
0x180002da0  push    rdi
0x180002da1  push    r12
0x180002da3  push    r13
0x180002da5  push    r14
0x180002da7  push    r15
0x180002da9  mov     rbp, rsp
0x180002dac  sub     rsp, 68h
0x180002db0  mov     rdi, [rbp+arg_20]
0x180002db4  xor     r13d, r13d
0x180002db7  mov     [rbp+var_18], r13
0x180002dbb  mov     r14, r9
0x180002dbe  mov     [rbp+var_28], r13
0x180002dc2  mov     rbx, r8
0x180002dc5  mov     [rbp+var_20], r13
0x180002dc9  mov     esi, ecx
0x180002dcb  test    rdi, rdi
0x180002dce  jz      short loc_180002DF8
0x180002dd0  mov     rax, [rdi]
0x180002dd3  lea     r15d, [r13+1]
0x180002dd7  mov     rcx, rdi
0x180002dda  mov     rax, [rax]
0x180002ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de2  mov     rdx, [rdi]
0x180002de5  mov     r12d, eax
0x180002de8  mov     rcx, rdi
0x180002deb  mov     rax, [rdx+8]
0x180002def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df4  mov     edi, eax
0x180002df6  jmp     short loc_180002E01
0x180002df8  mov     r15d, r13d
0x180002dfb  mov     edi, r13d
0x180002dfe  mov     r12d, r13d
0x180002e01  cmp     esi, 80h
0x180002e07  jz      loc_180002ED4
0x180002e0d  mov     edi, r13d
0x180002e10  cmp     esi, 20000000h
0x180002e16  jnz     loc_1800030A6
0x180002e1c  mov     rax, [r14]
0x180002e1f  mov     rcx, r14
0x180002e22  mov     rax, [rax+30h]
0x180002e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e2b  test    eax, eax
0x180002e2d  jz      loc_180002ECD
0x180002e33  mov     rax, [rbx]
0x180002e36  mov     rcx, rbx
0x180002e39  mov     rax, [rax+38h]
0x180002e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e42  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180002e49  mov     r8, rax
0x180002e4c  mov     rcx, [rax]
0x180002e4f  mov     rax, [rcx]
0x180002e52  mov     rcx, r8
0x180002e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e5a  test    rax, rax
0x180002e5d  jz      short loc_180002ECD
0x180002e5f  lea     rsi, [rax+0D8h]
0x180002e66  mov     rcx, rsi
0x180002e69  lea     rbx, [rax+190h]
0x180002e70  call    cs:__imp_?IsEmpty@STRA@@QEBA_NXZ; STRA::IsEmpty(void)
0x180002e76  test    al, al
0x180002e78  jz      short loc_180002E80
0x180002e7a  cmp     [rbx], r13w
0x180002e7e  jz      short loc_180002ECD
0x180002e80  mov     rax, [r14]
0x180002e83  mov     rcx, r14
0x180002e86  mov     rax, [rax+20h]
0x180002e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e8f  mov     rdi, rax
0x180002e92  test    rax, rax
0x180002e95  jz      short loc_180002ECD
0x180002e97  mov     rcx, rsi
0x180002e9a  call    cs:__imp_?IsEmpty@STRA@@QEBA_NXZ; STRA::IsEmpty(void)
0x180002ea0  test    al, al
0x180002ea2  jnz     short loc_180002EBE
0x180002ea4  mov     rcx, rsi
0x180002ea7  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180002ead  mov     rcx, rsi
0x180002eb0  mov     [rdi+58h], rax
0x180002eb4  call    cs:__imp_?QueryCB@STRA@@QEBAKXZ; STRA::QueryCB(void)
0x180002eba  mov     [rdi+12h], ax
0x180002ebe  movzx   eax, word ptr [rbx]
0x180002ec1  test    ax, ax
0x180002ec4  jz      short loc_180002ECD
0x180002ec6  mov     [rdi+82h], ax
0x180002ecd  xor     eax, eax
0x180002ecf  jmp     loc_180003297
0x180002ed4  mov     rax, [rbx]
0x180002ed7  mov     rcx, rbx
0x180002eda  test    r15d, r15d
0x180002edd  jnz     loc_180003263
0x180002ee3  mov     rax, [rax+0C0h]
0x180002eea  mov     rsi, r13
0x180002eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef2  mov     r8, rax
0x180002ef5  xor     edx, edx
0x180002ef7  mov     rcx, [rax]
0x180002efa  mov     rax, [rcx+18h]
0x180002efe  mov     rcx, r8
0x180002f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f06  mov     r14, rax
0x180002f09  cmp     [rax], r13w
0x180002f0d  jnz     short loc_180002F26
0x180002f0f  mov     rax, [rbx]
0x180002f12  xor     edx, edx
0x180002f14  mov     rcx, rbx
0x180002f17  mov     rax, [rax+0B8h]
0x180002f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f23  mov     r14, rax
0x180002f26  mov     rax, [rbx]
0x180002f29  mov     rcx, rbx
0x180002f2c  mov     rax, [rax+0A0h]
0x180002f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f38  mov     rdx, rax
0x180002f3b  mov     rcx, [rax]
0x180002f3e  mov     rax, [rcx+10h]
0x180002f42  mov     rcx, rdx
0x180002f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f4a  mov     rdx, [rbx]
0x180002f4d  mov     rcx, rbx
0x180002f50  test    rax, rax
0x180002f53  jz      short loc_180002F8A
0x180002f55  mov     rax, [rdx+0A0h]
0x180002f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f61  mov     rdx, rax
0x180002f64  mov     rcx, [rax]
0x180002f67  mov     rax, [rcx+10h]
0x180002f6b  mov     rcx, rdx
0x180002f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f73  mov     rdx, rax
0x180002f76  mov     rcx, [rax]
0x180002f79  mov     rax, [rcx+38h]
0x180002f7d  mov     rcx, rdx
0x180002f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f85  mov     rdi, rax
0x180002f88  jmp     short loc_180002FD8
0x180002f8a  mov     rax, [rdx+30h]
0x180002f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f93  mov     rdx, rax
0x180002f96  mov     rcx, [rax]
0x180002f99  mov     rax, [rcx+20h]
0x180002f9d  mov     rcx, rdx
0x180002fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa5  mov     rdi, rax
0x180002fa8  test    rax, rax
0x180002fab  jz      short loc_180002FD8
0x180002fad  mov     rax, [rbx]
0x180002fb0  mov     rcx, rbx
0x180002fb3  mov     rax, [rax+30h]
0x180002fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fbc  mov     r8, rax
0x180002fbf  lea     rdx, aSid; "SID"
0x180002fc6  mov     rcx, [rax]
0x180002fc9  mov     rax, [rcx+50h]
0x180002fcd  mov     rcx, r8
0x180002fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd5  mov     rsi, rax
0x180002fd8  lea     rax, [rbp+var_18]
0x180002fdc  mov     [rsp+68h+var_38], rbx; struct IHttpContext *
0x180002fe1  mov     [rsp+68h+var_40], rax; struct INativeSectionException **
0x180002fe6  lea     r8, [rbp+var_20]; struct ISAPI_DLL **
0x180002fea  mov     r9, rdi; void *
0x180002fed  mov     [rsp+68h+var_48], rsi; void *
0x180002ff2  mov     rdx, r14; unsigned __int16 *
0x180002ff5  call    ?GetIsapi@ISAPI_DLL_MANAGER@@QEAAJPEBGPEAPEAVISAPI_DLL@@PEAX2PEAPEAVINativeSectionException@@PEAVIHttpContext@@@Z; ISAPI_DLL_MANAGER::GetIsapi(ushort const *,ISAPI_DLL * *,void *,void *,INativeSectionException * *,IHttpContext *)
0x180002ffa  mov     edi, eax
0x180002ffc  test    eax, eax
0x180002ffe  js      loc_180003095
0x180003004  mov     rax, [rbx]
0x180003007  mov     edx, 1A0h
0x18000300c  mov     rcx, rbx
0x18000300f  mov     rax, [rax+90h]
0x180003016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301b  mov     rsi, [rbp+var_20]
0x18000301f  test    rax, rax
0x180003022  jz      short loc_18000308E
0x180003024  mov     r9, r14; unsigned __int16 *
0x180003027  mov     r8, rsi; struct ISAPI_DLL *
0x18000302a  mov     rdx, rbx; struct IHttpContext *
0x18000302d  mov     rcx, rax; this
0x180003030  call    ??0W3_ISAPI_HANDLER@@QEAA@PEAVIHttpContext@@PEAVISAPI_DLL@@PEBG@Z; W3_ISAPI_HANDLER::W3_ISAPI_HANDLER(IHttpContext *,ISAPI_DLL *,ushort const *)
0x180003035  mov     r14, rax
0x180003038  test    rax, rax
0x18000303b  jz      short loc_18000308E
0x18000303d  mov     rcx, [rbx]
0x180003040  mov     rsi, r13
0x180003043  mov     rax, [rcx+38h]
0x180003047  mov     rcx, rbx
0x18000304a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000304f  mov     r8, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180003056  mov     r9, rax
0x180003059  mov     rdx, r14
0x18000305c  mov     rcx, [rax]
0x18000305f  mov     rax, [rcx+8]
0x180003063  mov     rcx, r9
0x180003066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000306b  mov     edi, eax
0x18000306d  mov     rcx, r14
0x180003070  test    eax, eax
0x180003072  jns     short loc_180003081
0x180003074  mov     rax, [r14]
0x180003077  mov     rax, [rax]
0x18000307a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000307f  jmp     short loc_180003099
0x180003081  xor     r9d, r9d
0x180003084  xor     r8d, r8d
0x180003087  xor     edx, edx
0x180003089  jmp     loc_180003292
0x18000308e  mov     edi, 80070008h
0x180003093  jmp     short loc_180003099
0x180003095  mov     rsi, [rbp+var_20]
0x180003099  test    rsi, rsi
0x18000309c  jz      short loc_1800030A6
0x18000309e  mov     rcx, rsi; this
0x1800030a1  call    ?DereferenceIsapiDll@ISAPI_DLL@@QEAAXXZ; ISAPI_DLL::DereferenceIsapiDll(void)
0x1800030a6  mov     rax, [rbx]
0x1800030a9  mov     rcx, rbx
0x1800030ac  mov     rax, [rax+20h]
0x1800030b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b5  mov     rdx, rax
0x1800030b8  mov     rcx, [rax]
0x1800030bb  mov     rax, [rcx+8]
0x1800030bf  mov     rcx, rdx
0x1800030c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c7  mov     esi, 2
0x1800030cc  mov     [rax+218h], r13w
0x1800030d4  test    edi, edi
0x1800030d6  jns     loc_18000325F
0x1800030dc  mov     rcx, [rbp+var_18]
0x1800030e0  test    rcx, rcx
0x1800030e3  jz      loc_180003170
0x1800030e9  mov     rax, [rcx]
0x1800030ec  lea     r8, [rbp+var_28]
0x1800030f0  lea     rdx, IID_IAppHostConfigException
0x1800030f7  mov     rax, [rax]
0x1800030fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ff  mov     rax, [rbx]
0x180003102  mov     rcx, rbx
0x180003105  mov     rax, [rax+20h]
0x180003109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000310e  mov     r10, rax
0x180003111  mov     dword ptr [rsp+68h+var_38], r13d
0x180003116  mov     edx, 1F4h
0x18000311b  lea     r9d, [rsi+11h]
0x18000311f  lea     r8, aInternalServer; "Internal Server Error"
0x180003126  mov     rcx, [rax]
0x180003129  mov     rax, [rcx+18h]
0x18000312d  mov     rcx, [rbp+var_28]
0x180003131  mov     [rsp+68h+var_40], rcx
0x180003136  mov     rcx, r10
0x180003139  mov     dword ptr [rsp+68h+var_48], edi
0x18000313d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003142  mov     rcx, [rbp+var_28]
0x180003146  test    rcx, rcx
0x180003149  jz      short loc_18000315B
0x18000314b  mov     rax, [rcx]
0x18000314e  mov     rax, [rax+10h]
0x180003152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003157  mov     [rbp+var_28], r13
0x18000315b  mov     rcx, [rbp+var_18]
0x18000315f  mov     rax, [rcx]
0x180003162  mov     rax, [rax+10h]
0x180003166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000316b  jmp     loc_18000325F
0x180003170  mov     ecx, edi; int
0x180003172  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180003177  cmp     eax, 3
0x18000317a  jz      short loc_1800031EE
0x18000317c  cmp     eax, 5
0x18000317f  jz      short loc_1800031CB
0x180003181  cmp     eax, 7Bh ; '{'
0x180003184  jz      short loc_1800031EE
0x180003186  cmp     eax, 7Eh ; '~'
0x180003189  jz      short loc_1800031EE
0x18000318b  mov     rcx, [rbx]
0x18000318e  cmp     eax, 4ECh
0x180003193  mov     rdx, [rcx+20h]
0x180003197  mov     rcx, rbx
0x18000319a  mov     rax, rdx
0x18000319d  jz      short loc_1800031B5
0x18000319f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a4  mov     edx, 1F4h
0x1800031a9  lea     r8, aInternalServer; "Internal Server Error"
0x1800031b0  jmp     loc_18000323C
0x1800031b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ba  mov     r9d, esi
0x1800031bd  lea     r8, aNotFound; "Not Found"
0x1800031c4  mov     edx, 194h
0x1800031c9  jmp     short loc_18000323F
0x1800031cb  mov     rax, [rbx]
0x1800031ce  mov     rcx, rbx
0x1800031d1  mov     rax, [rax+20h]
0x1800031d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031da  mov     edx, 191h
0x1800031df  lea     r8, aUnauthorized; "Unauthorized"
0x1800031e6  mov     r9d, 3
0x1800031ec  jmp     short loc_18000323F
0x1800031ee  mov     rax, [rbx]
  ... truncated ...
```
