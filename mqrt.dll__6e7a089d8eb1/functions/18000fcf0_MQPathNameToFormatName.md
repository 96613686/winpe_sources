# MQPathNameToFormatName

- ea: `0x18000fcf0`
- end: `0x180010256`
- name: `MQPathNameToFormatName`
- size: `1382`
- prototype: `HRESULT __stdcall(LPCWSTR lpwcsPathName, LPWSTR lpwcsFormatName, LPDWORD lpdwFormatNameLength)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x18000e590`

## callees

- `0x180005488`
- `0x180006f5c`
- `0x180006fdc`
- `0x180007e10`
- `0x1800087f8`
- `0x1800090f4`
- `0x180009254`
- `0x18000a364`
- `0x18000da98`
- `0x18000fcf0`
- `0x180013c74`
- `0x180014458`
- `0x180017ce0`
- `0x18001a864`
- `0x18001d468`
- `0x180021010`
- `0x180021060`
- `0x180021e3c`
- `0x180023c36`
- `0x180023ca0`

## import_xrefs

- `msvcrt!wcschr` at `0x18000fdfa`
- `msvcrt!wcschr` at `0x18000fdfa`
- `RPCRT4!NdrClientCall3` at `0x18000ff8b`
- `RPCRT4!NdrClientCall3` at `0x18000ff8b`
- `KERNEL32!TlsGetValue` at `0x18000ff55`
- `KERNEL32!TlsGetValue` at `0x18000ff55`

## pseudocode

```c
HRESULT __stdcall MQPathNameToFormatName(LPCWSTR lpwcsPathName, LPWSTR lpwcsFormatName, LPDWORD lpdwFormatNameLength)
{
  int v4; // eax
  HRESULT v5; // ebx
  int v7; // r13d
  wchar_t *v8; // r15
  int v9; // ecx
  int v10; // ecx
  int Pointer; // ebx
  int v12; // ecx
  const wchar_t *v13; // rax
  __int64 v14; // r8
  int v15; // ebx
  int v16; // eax
  int v17; // edi
  int v18; // ecx
  LPVOID Value; // rax
  CLIENT_CALL_RETURN v20; // rax
  unsigned int v21; // ebx
  wchar_t *v22; // r12
  int v23; // ebx
  int v24; // eax
  int v25; // r12d
  int v26; // ebx
  __int64 v27; // [rsp+0h] [rbp-148h] BYREF
  int v28; // [rsp+40h] [rbp-108h]
  int v29; // [rsp+44h] [rbp-104h]
  unsigned int v30; // [rsp+48h] [rbp-100h]
  int v31; // [rsp+50h] [rbp-F8h]
  int v32; // [rsp+54h] [rbp-F4h] BYREF
  wchar_t *Str; // [rsp+58h] [rbp-F0h] BYREF
  void *v34; // [rsp+60h] [rbp-E8h] BYREF
  HRESULT v35; // [rsp+68h] [rbp-E0h]
  wchar_t *v36; // [rsp+70h] [rbp-D8h]
  void *v37; // [rsp+78h] [rbp-D0h]
  _OWORD v38[2]; // [rsp+80h] [rbp-C8h] BYREF
  wchar_t *v39; // [rsp+A0h] [rbp-A8h]
  unsigned int *v40; // [rsp+A8h] [rbp-A0h]
  wchar_t *v41; // [rsp+B0h] [rbp-98h]
  LPCWSTR v42; // [rsp+B8h] [rbp-90h]
  LPCWSTR v43; // [rsp+C0h] [rbp-88h]
  _QWORD v44[2]; // [rsp+C8h] [rbp-80h] BYREF
  __int64 *v45; // [rsp+D8h] [rbp-70h]
  __int16 v46; // [rsp+E0h] [rbp-68h] BYREF
  __int128 *v47; // [rsp+E8h] [rbp-60h]
  __int128 v48; // [rsp+F8h] [rbp-50h] BYREF

  v45 = &v27;
  v40 = lpdwFormatNameLength;
  v41 = lpwcsFormatName;
  v42 = lpwcsPathName;
  v43 = lpwcsPathName;
  v4 = RtpOneTimeThreadInit();
  v5 = v4;
  if ( v4 < 0 )
  {
    LogMsgHR(v4, (wchar_t *)L"rt/queue", 0x478u);
    return v5;
  }
  v30 = 1;
  memset(v38, 0, sizeof(v38));
  v34 = 0;
  v37 = 0;
  v7 = 0;
  v31 = 0;
  v8 = 0;
  v36 = 0;
  Str = 0;
  v9 = FnValidateAndExpandQueuePath(lpwcsPathName, &Str, &v34);
  if ( v9 == 4 )
  {
    v7 = 1;
    v31 = 1;
    v37 = v34;
    v34 = 0;
    v8 = wcschr(Str, 0x3Bu);
    v36 = v8;
    *v8 = 0;
    v39 = v8 + 1;
    v9 = FnValidateAndExpandQueuePath(Str, &Str, &v34);
  }
  else
  {
    v39 = 0;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v44[0] = 1;
    v44[1] = v38;
    Value = TlsGetValue(g_hBindIndex);
    *(_QWORD *)&v48 = 0;
    v20.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xCu, 0, Value, Str, v44).Pointer;
    Pointer = (int)v20.Pointer;
    *(CLIENT_CALL_RETURN *)&v48 = v20;
    v12 = (int)v20.Pointer;
    goto LABEL_16;
  }
  if ( v10 == 1 )
  {
    v48 = 0;
    v32 = 101;
    v46 = 72;
    v47 = &v48;
    v13 = MachineDomain();
    v15 = ADGetObjectProperties(0, v13, v14, Str, 1, &v32, &v46);
    v16 = RTpConvertToMQCode(v15, 1u);
    v17 = v16;
    v28 = v16;
    v29 = v15;
    if ( v16 < 0 )
    {
      v18 = -1072824301;
      if ( v16 == -1072824301 )
        goto LABEL_14;
      v18 = -1072824214;
      if ( v16 == -1072824214 )
        goto LABEL_14;
      v16 = RTpConvertToMQCode(-1072824317, 1u);
      v17 = v16;
      v28 = v16;
      v29 = -1072824317;
    }
    v18 = v16;
LABEL_14:
    LOWORD(v38[0]) = 1;
    *(_OWORD *)((char *)v38 + 8) = v48;
    goto LABEL_17;
  }
  Pointer = -1072824300;
  v12 = -1072824300;
LABEL_16:
  v28 = RTpConvertToMQCode(v12, 1u);
  v17 = v28;
  v29 = Pointer;
  v18 = v28;
LABEL_17:
  if ( v18 >= 0 )
  {
    if ( v7 )
    {
      QUEUE_FORMAT::DisposeString((QUEUE_FORMAT *)v38);
      v21 = mqwcslen(Str) + 4;
      v22 = (wchar_t *)MmAllocate(saturated_mul(v21, 2u));
      v32 = StringCchCopyW(v22, v21, L"OS:");
      v23 = StringCchCatW(v22, v21, Str);
      if ( v32 < 0 || v23 < 0 )
      {
        LogHR(v32, (wchar_t *)L"rt/queue", 0x208u);
        LogHR(v23, (wchar_t *)L"rt/queue", 0x209u);
        v35 = LogHR(-1072824317, (wchar_t *)L"rt/queue", 0x20Au);
        local_unwind_0(v45, &loc_180010130);
        return v35;
      }
      LOWORD(v38[0]) = 3;
      *((_QWORD *)&v38[0] + 1) = v22;
      v24 = MQpSubqueueFormatToFormatName((const struct QUEUE_FORMAT *)v38, v39, v41, *v40, v40);
      v25 = v24;
      if ( v24 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_88d719a3250f3244a7ac6a4d49ff882c_Traceguids,
          (unsigned int)v24);
      v17 = RTpConvertToMQCode(v25, 1u);
      v28 = v17;
      v29 = v25;
    }
    else
    {
      v26 = RTpQueueFormatToFormatName((struct QUEUE_FORMAT *)v38, v41, *v40, v40);
      v17 = RTpConvertToMQCode(v26, 1u);
      v28 = v17;
      v29 = v26;
    }
  }
  QUEUE_FORMAT::DisposeString((QUEUE_FORMAT *)v38);
  if ( v7 )
  {
    if ( v8 )
      *v8 = 59;
    MmDeallocate(v37);
  }
  MmDeallocate(v34);
  if ( v17 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17);
  return v17;
}

```

## disassembly

```asm
0x18000fcf0  push    rbx
0x18000fcf2  push    rsi
0x18000fcf3  push    rdi
0x18000fcf4  push    r12
0x18000fcf6  push    r13
0x18000fcf8  push    r14
0x18000fcfa  push    r15
0x18000fcfc  sub     rsp, 110h
0x18000fd03  mov     rax, cs:__security_cookie
0x18000fd0a  xor     rax, rsp
0x18000fd0d  mov     [rsp+148h+var_40], rax
0x18000fd15  mov     [rsp+148h+var_70], rsp
0x18000fd1d  mov     [rsp+148h+var_A0], r8
0x18000fd25  mov     [rsp+148h+var_98], rdx
0x18000fd2d  mov     r12, rcx
0x18000fd30  mov     [rsp+148h+var_90], rcx
0x18000fd38  mov     [rsp+148h+var_88], rcx
0x18000fd40  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x18000fd45  mov     ebx, eax
0x18000fd47  xor     esi, esi
0x18000fd49  test    eax, eax
0x18000fd4b  jns     short loc_18000FD86
0x18000fd4d  mov     r8d, 478h; unsigned __int16
0x18000fd53  lea     rdx, aRtQueue; "rt/queue"
0x18000fd5a  mov     ecx, eax; int
0x18000fd5c  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000fd61  mov     eax, ebx
0x18000fd63  mov     rcx, [rsp+148h+var_40]
0x18000fd6b  xor     rcx, rsp; StackCookie
0x18000fd6e  call    __security_check_cookie
0x18000fd73  add     rsp, 110h
0x18000fd7a  pop     r15
0x18000fd7c  pop     r14
0x18000fd7e  pop     r13
0x18000fd80  pop     r12
0x18000fd82  pop     rdi
0x18000fd83  pop     rsi
0x18000fd84  pop     rbx
0x18000fd85  retn
0x18000fd86  mov     r14d, 1
0x18000fd8c  mov     [rsp+148h+var_100], r14d
0x18000fd91  xorps   xmm0, xmm0
0x18000fd94  movups  [rsp+148h+var_C8], xmm0
0x18000fd9c  movups  [rsp+148h+var_B8], xmm0
0x18000fda4  mov     [rsp+148h+var_E8], rsi
0x18000fda9  mov     [rsp+148h+var_D0], rsi
0x18000fdae  mov     r13d, esi
0x18000fdb1  mov     [rsp+148h+var_F8], esi
0x18000fdb5  mov     r15, rsi
0x18000fdb8  mov     [rsp+148h+var_D8], rsi
0x18000fdbd  mov     [rsp+148h+Str], rsi
0x18000fdc2  lea     r8, [rsp+148h+var_E8]
0x18000fdc7  lea     rdx, [rsp+148h+Str]
0x18000fdcc  mov     rcx, r12
0x18000fdcf  call    ?FnValidateAndExpandQueuePath@@YA?AW4QUEUE_PATH_TYPE@@PEB_WPEAPEB_WPEAPEA_W@Z; FnValidateAndExpandQueuePath(wchar_t const *,wchar_t const * *,wchar_t * *)
0x18000fdd4  mov     ecx, eax
0x18000fdd6  cmp     eax, 4
0x18000fdd9  jnz     short loc_18000FE2F
0x18000fddb  mov     r13d, r14d
0x18000fdde  mov     [rsp+148h+var_F8], r14d
0x18000fde3  mov     rax, [rsp+148h+var_E8]
0x18000fde8  mov     [rsp+148h+var_D0], rax
0x18000fded  mov     [rsp+148h+var_E8], rsi
0x18000fdf2  lea     edx, [rcx+37h]; Ch
0x18000fdf5  mov     rcx, [rsp+148h+Str]; Str
0x18000fdfa  call    cs:__imp_wcschr
0x18000fe00  mov     r15, rax
0x18000fe03  mov     [rsp+148h+var_D8], rax
0x18000fe08  mov     [rax], si
0x18000fe0b  lea     rbx, [rax+2]
0x18000fe0f  mov     [rsp+148h+var_A8], rbx
0x18000fe17  lea     r8, [rsp+148h+var_E8]
0x18000fe1c  lea     rdx, [rsp+148h+Str]
0x18000fe21  mov     rcx, [rsp+148h+Str]
0x18000fe26  call    ?FnValidateAndExpandQueuePath@@YA?AW4QUEUE_PATH_TYPE@@PEB_WPEAPEB_WPEAPEA_W@Z; FnValidateAndExpandQueuePath(wchar_t const *,wchar_t const * *,wchar_t * *)
0x18000fe2b  mov     ecx, eax
0x18000fe2d  jmp     short loc_18000FE37
0x18000fe2f  mov     [rsp+148h+var_A8], rsi
0x18000fe37  sub     ecx, 1
0x18000fe3a  jz      loc_18000FF2C
0x18000fe40  sub     ecx, 1
0x18000fe43  jz      short loc_18000FE54
0x18000fe45  mov     ebx, 0C00E0014h
0x18000fe4a  cmp     ecx, 2
0x18000fe4d  mov     ecx, ebx
0x18000fe4f  jmp     loc_18000FF9E
0x18000fe54  xorps   xmm0, xmm0
0x18000fe57  movups  [rsp+148h+var_50], xmm0
0x18000fe5f  mov     [rsp+148h+var_F4], 65h ; 'e'
0x18000fe67  mov     eax, 48h ; 'H'
0x18000fe6c  mov     [rsp+148h+var_68], ax
0x18000fe74  lea     rax, [rsp+148h+var_50]
0x18000fe7c  mov     [rsp+148h+var_60], rax
0x18000fe84  call    ?MachineDomain@@YAPEB_WXZ; MachineDomain(void)
0x18000fe89  lea     rcx, [rsp+148h+var_68]
0x18000fe91  mov     [rsp+148h+var_118], rcx
0x18000fe96  lea     rcx, [rsp+148h+var_F4]
0x18000fe9b  mov     [rsp+148h+var_120], rcx
0x18000fea0  mov     dword ptr [rsp+148h+var_128], r14d
0x18000fea5  mov     r9, [rsp+148h+Str]
0x18000feaa  mov     rdx, rax
0x18000fead  xor     ecx, ecx
0x18000feaf  call    ?ADGetObjectProperties@@YAJW4AD_OBJECT@@PEB_W_N1KQEBKQEAUtagPROPVARIANT@@@Z; ADGetObjectProperties(AD_OBJECT,wchar_t const *,bool,wchar_t const *,ulong,ulong const * const,tagPROPVARIANT * const)
0x18000feb4  mov     ebx, eax
0x18000feb6  mov     edx, r14d; unsigned int
0x18000feb9  mov     ecx, eax; int
0x18000febb  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000fec0  mov     edi, eax
0x18000fec2  mov     [rsp+148h+var_108], eax
0x18000fec6  mov     [rsp+148h+var_104], ebx
0x18000feca  test    eax, eax
0x18000fecc  jns     short loc_18000FEFB
0x18000fece  mov     ecx, 0C00E0013h
0x18000fed3  cmp     eax, ecx
0x18000fed5  jz      short loc_18000FEFD
0x18000fed7  mov     ecx, 0C00E006Ah
0x18000fedc  cmp     eax, ecx
0x18000fede  jz      short loc_18000FEFD
0x18000fee0  mov     edx, r14d; unsigned int
0x18000fee3  mov     ecx, 0C00E0003h; int
0x18000fee8  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000feed  mov     edi, eax
0x18000feef  mov     [rsp+148h+var_108], eax
0x18000fef3  mov     [rsp+148h+var_104], 0C00E0003h
0x18000fefb  mov     ecx, eax
0x18000fefd  mov     word ptr [rsp+148h+var_C8], 1
0x18000ff07  mov     rax, qword ptr [rsp+148h+var_50]
0x18000ff0f  mov     qword ptr [rsp+148h+var_C8+8], rax
0x18000ff17  mov     rax, qword ptr [rsp+148h+var_50+8]
0x18000ff1f  mov     qword ptr [rsp+148h+var_B8], rax
0x18000ff27  jmp     loc_18000FFB2
0x18000ff2c  xorps   xmm0, xmm0
0x18000ff2f  movups  [rsp+148h+var_80], xmm0
0x18000ff37  mov     dword ptr [rsp+148h+var_80], r14d
0x18000ff3f  lea     rax, [rsp+148h+var_C8]
0x18000ff47  mov     qword ptr [rsp+148h+var_80+8], rax
0x18000ff4f  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x18000ff55  call    cs:__imp_TlsGetValue
0x18000ff5b  mov     qword ptr [rsp+148h+var_50], rsi
0x18000ff63  lea     rcx, [rsp+148h+var_80]
0x18000ff6b  mov     [rsp+148h+var_120], rcx
0x18000ff70  mov     rcx, [rsp+148h+Str]
0x18000ff75  mov     [rsp+148h+var_128], rcx
0x18000ff7a  mov     r9, rax
0x18000ff7d  xor     r8d, r8d; pReturnValue
0x18000ff80  lea     edx, [r8+0Ch]; nProcNum
0x18000ff84  lea     rcx, pProxyInfo; pProxyInfo
0x18000ff8b  call    cs:__imp_NdrClientCall3
0x18000ff91  mov     rbx, rax
0x18000ff94  mov     qword ptr [rsp+148h+var_50], rax
0x18000ff9c  mov     ecx, eax; int
0x18000ff9e  mov     edx, r14d; unsigned int
0x18000ffa1  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000ffa6  mov     [rsp+148h+var_108], eax
0x18000ffaa  mov     edi, eax
0x18000ffac  mov     [rsp+148h+var_104], ebx
0x18000ffb0  mov     ecx, eax
0x18000ffb2  test    ecx, ecx
0x18000ffb4  js      loc_18001016A
0x18000ffba  lea     rcx, [rsp+148h+var_C8]; struct QUEUE_FORMAT *
0x18000ffc2  test    r13d, r13d
0x18000ffc5  jz      loc_180010139
0x18000ffcb  call    ?DisposeString@QUEUE_FORMAT@@QEAAXXZ; QUEUE_FORMAT::DisposeString(void)
0x18000ffd0  mov     rcx, [rsp+148h+Str]; wchar_t *
0x18000ffd5  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000ffda  lea     ebx, [rax+4]
0x18000ffdd  mov     eax, 2
0x18000ffe2  mul     rbx
0x18000ffe5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ffec  cmovb   rax, rcx
0x18000fff0  mov     rcx, rax; unsigned __int64
0x18000fff3  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000fff8  mov     r12, rax
0x18000fffb  lea     r8, aOs; "OS:"
0x180010002  mov     edx, ebx; unsigned __int64
0x180010004  mov     rcx, rax; wchar_t *
0x180010007  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001000c  mov     [rsp+148h+var_F4], eax
0x180010010  mov     r8, [rsp+148h+Str]; wchar_t *
0x180010015  mov     edx, ebx; unsigned __int64
0x180010017  mov     rcx, r12; wchar_t *
0x18001001a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001001f  mov     ebx, eax
0x180010021  mov     eax, [rsp+148h+var_F4]
0x180010025  test    eax, eax
0x180010027  js      loc_1800100D8
0x18001002d  test    ebx, ebx
0x18001002f  js      loc_1800100D8
0x180010035  mov     word ptr [rsp+148h+var_C8], 3
0x18001003f  mov     qword ptr [rsp+148h+var_C8+8], r12
0x180010047  mov     rax, [rsp+148h+var_A0]
0x18001004f  mov     [rsp+148h+var_128], rax; unsigned int *
0x180010054  mov     r9d, [rax]; unsigned int
0x180010057  mov     r8, [rsp+148h+var_98]; wchar_t *
0x18001005f  mov     rdx, [rsp+148h+var_A8]; wchar_t *
0x180010067  lea     rcx, [rsp+148h+var_C8]; struct QUEUE_FORMAT *
0x18001006f  call    ?MQpSubqueueFormatToFormatName@@YAJPEBUQUEUE_FORMAT@@PEB_WPEA_WKPEAK@Z; MQpSubqueueFormatToFormatName(QUEUE_FORMAT const *,wchar_t const *,wchar_t *,ulong,ulong *)
0x180010074  mov     r12d, eax
0x180010077  test    eax, eax
0x180010079  jns     short loc_1800100AE
0x18001007b  lea     rbx, WPP_GLOBAL_Control
0x180010082  mov     rcx, cs:WPP_GLOBAL_Control
0x180010089  cmp     rcx, rbx
0x18001008c  jz      short loc_1800100B5
0x18001008e  test    [rcx+1Ch], r14b
0x180010092  jz      short loc_1800100B5
0x180010094  mov     edx, 0Bh
0x180010099  mov     r9d, eax
0x18001009c  lea     r8, WPP_88d719a3250f3244a7ac6a4d49ff882c_Traceguids
0x1800100a3  mov     rcx, [rcx+10h]
0x1800100a7  call    WPP_SF_d
0x1800100ac  jmp     short loc_1800100B5
0x1800100ae  lea     rbx, WPP_GLOBAL_Control
0x1800100b5  mov     edx, r14d; unsigned int
0x1800100b8  mov     ecx, r12d; int
0x1800100bb  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x1800100c0  mov     edi, eax
0x1800100c2  mov     [rsp+148h+var_108], eax
0x1800100c6  mov     [rsp+148h+var_104], r12d
0x1800100cb  mov     r12, [rsp+148h+var_90]
0x1800100d3  jmp     loc_180010171
0x1800100d8  mov     r8d, 208h; unsigned __int16
0x1800100de  lea     rdx, aRtQueue; "rt/queue"
0x1800100e5  mov     ecx, eax; int
0x1800100e7  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x1800100ec  mov     r8d, 209h; unsigned __int16
0x1800100f2  lea     rdx, aRtQueue; "rt/queue"
0x1800100f9  mov     ecx, ebx; int
0x1800100fb  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x180010100  mov     r8d, 20Ah; unsigned __int16
0x180010106  lea     rdx, aRtQueue; "rt/queue"
0x18001010d  mov     ecx, 0C00E0003h; int
0x180010112  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x180010117  mov     [rsp+148h+var_E0], eax
0x18001011b  lea     rdx, loc_180010130
0x180010122  mov     rcx, [rsp+148h+var_70]
0x18001012a  call    _local_unwind_0
0x18001012f  nop
0x180010130  mov     eax, [rsp+148h+var_E0]
0x180010134  jmp     loc_18000FD63
0x180010139  mov     rax, [rsp+148h+var_A0]
0x180010141  mov     r9, rax; unsigned int *
0x180010144  mov     r8d, [rax]; unsigned int
0x180010147  mov     rdx, [rsp+148h+var_98]; wchar_t *
0x18001014f  call    ?RTpQueueFormatToFormatName@@YAJPEAUQUEUE_FORMAT@@PEA_WKPEAK@Z; RTpQueueFormatToFormatName(QUEUE_FORMAT *,wchar_t *,ulong,ulong *)
0x180010154  mov     ebx, eax
0x180010156  mov     edx, r14d; unsigned int
0x180010159  mov     ecx, eax; int
0x18001015b  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x180010160  mov     edi, eax
0x180010162  mov     [rsp+148h+var_108], eax
0x180010166  mov     [rsp+148h+var_104], ebx
0x18001016a  lea     rbx, WPP_GLOBAL_Control
0x180010171  jmp     short loc_1800101EC
0x180010173  mov     ebx, eax
0x180010175  mov     edx, [rsp+148h+var_100]; unsigned int
0x180010179  mov     ecx, eax; int
0x18001017b  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x180010180  mov     edi, eax
0x180010182  mov     [rsp+148h+var_108], eax
0x180010186  mov     [rsp+148h+var_104], ebx
0x18001018a  test    eax, eax
0x18001018c  jg      short loc_180010192
0x18001018e  mov     ecx, eax
0x180010190  jmp     short loc_18001019B
0x180010192  movzx   ecx, di
0x180010195  or      ecx, 80070000h; int
0x18001019b  mov     r8d, 212h; unsigned __int16
0x1800101a1  lea     rdx, aRtQueue; "rt/queue"
0x1800101a8  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x1800101ad  test    edi, edi
0x1800101af  js      short loc_1800101CD
0x1800101b1  mov     edx, [rsp+148h+var_100]; unsigned int
0x1800101b5  mov     ecx, 0C00E000Bh; int
0x1800101ba  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x1800101bf  mov     edi, eax
0x1800101c1  mov     [rsp+148h+var_108], eax
0x1800101c5  mov     [rsp+148h+var_104], 0C00E000Bh
0x1800101cd  mov     r14d, 1
0x1800101d3  lea     rbx, WPP_GLOBAL_Control
0x1800101da  mov     r13d, [rsp+148h+var_F8]
0x1800101df  mov     r15, [rsp+148h+var_D8]
0x1800101e4  mov     r12, [rsp+148h+var_88]
0x1800101ec  lea     rcx, [rsp+148h+var_C8]; this
0x1800101f4  call    ?DisposeString@QUEUE_FORMAT@@QEAAXXZ; QUEUE_FORMAT::DisposeString(void)
0x1800101f9  test    r13d, r13d
0x1800101fc  jz      short loc_180010213
0x1800101fe  test    r15, r15
0x180010201  jz      short loc_180010209
0x180010203  mov     word ptr [r15], 3Bh ; ';'
0x180010209  mov     rcx, [rsp+148h+var_D0]; void *
0x18001020e  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x180010213  mov     rcx, [rsp+148h+var_E8]; void *
0x180010218  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x18001021d  test    edi, edi
0x18001021f  jns     short loc_18001024F
0x180010221  mov     rcx, cs:WPP_GLOBAL_Control
0x180010228  cmp     rcx, rbx
0x18001022b  jz      short loc_18001024F
0x18001022d  test    [rcx+1Ch], r14b
  ... truncated ...
```
