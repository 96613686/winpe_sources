# KGT_TrackClient(KEYGUARD_TELEMETRY_GLOBAL *,long,int)

- ea: `0x180028d5c`
- end: `0x180028ffb`
- name: `?KGT_TrackClient@@YAPEAUKEYGUARD_TELEMETRY_IMAGE_T@@PEAUKEYGUARD_TELEMETRY_GLOBAL@@JH@Z`
- size: `671`
- prototype: `struct KEYGUARD_TELEMETRY_IMAGE_T *__fastcall(struct KEYGUARD_TELEMETRY_GLOBAL *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800167fc`

## callees

- `0x18001a0cc`
- `0x18001add4`
- `0x18001b754`
- `0x1800240f4`
- `0x1800245d0`
- `0x180028a70`
- `0x180028d5c`
- `0x180040cc8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180028e99`
- `ntdll!RtlLeaveCriticalSection` at `0x180028e99`
- `ntdll!RtlEnterCriticalSection` at `0x180028e5f`
- `ntdll!RtlEnterCriticalSection` at `0x180028e5f`
- `ntdll!RtlDllShutdownInProgress` at `0x180028ebb`
- `ntdll!RtlDllShutdownInProgress` at `0x180028ebb`

## pseudocode

```c
struct KEYGUARD_TELEMETRY_IMAGE_T *__fastcall KGT_TrackClient(struct KEYGUARD_TELEMETRY_GLOBAL *a1, int a2, int a3)
{
  int v5; // edx
  unsigned int ClientProcessId; // esi
  struct KEYGUARD_TELEMETRY_IMAGE_T *v7; // rax
  struct KEYGUARD_TELEMETRY_IMAGE_T *v8; // rdi
  struct KEYGUARD_TELEMETRY_PID *v10; // rsi
  int v11; // r12d
  __int64 v12; // rsi
  int *v13; // r15
  int *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // r8d
  bool v20; // zf
  __int64 v21; // rax
  struct KEYGUARD_TELEMETRY_PID *v22; // [rsp+58h] [rbp-9h] BYREF
  __int64 v23; // [rsp+60h] [rbp-1h] BYREF
  int *v24; // [rsp+68h] [rbp+7h] BYREF
  __int64 v25; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+78h] [rbp+17h] BYREF
  __int64 v27; // [rsp+80h] [rbp+1Fh] BYREF
  int *v28; // [rsp+88h] [rbp+27h]
  int v29; // [rsp+D8h] [rbp+77h] BYREF
  __int64 v30; // [rsp+E0h] [rbp+7Fh] BYREF

  v29 = a3;
  ClientProcessId = KGT_GetClientProcessId();
  if ( !ClientProcessId )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_e4946bd270313a60ab1af95b4d7edf4d_Traceguids,
        "KGT_TrackClient");
    return 0;
  }
  v29 = 0;
  LODWORD(v30) = 0;
  v22 = 0;
  v7 = KGT_AcquireImageCreatePid(a1, v5, ClientProcessId, &v22, &v29, (int *)&v30);
  v8 = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_e4946bd270313a60ab1af95b4d7edf4d_Traceguids,
        (unsigned int)"KGT_TrackClient",
        ClientProcessId);
    return 0;
  }
  v10 = v22;
  if ( !*((_DWORD *)v22 + 1) )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v7 + 24));
    v11 = 0;
    if ( !*((_DWORD *)v10 + 1) && !a2 )
    {
      *((_DWORD *)v10 + 1) = 1;
      if ( !*((_DWORD *)v8 + 3) )
        *((_DWORD *)v8 + 3) = 1;
      v11 = 1;
    }
    v12 = ++*((_QWORD *)v10 + 1);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v8 + 24));
    v13 = &dword_18006B48C;
    v14 = &dword_18006B48C;
    if ( *(_QWORD *)v8 )
      v14 = *(int **)v8;
    v28 = v14;
    if ( !RtlDllShutdownInProgress()
      && dword_180079160
      && (unsigned __int8)tlgKeywordOn(&dword_180079160, 0x400000000000LL, v17, v18) )
    {
      v20 = *(_QWORD *)v8 == 0;
      v22 = (struct KEYGUARD_TELEMETRY_PID *)0x2000000;
      if ( !v20 )
        v13 = *(int **)v8;
      v24 = v13;
      v23 = 0x1000000;
      v25 = 0;
      if ( v29 == 1 )
      {
        v30 = 1;
        v21 = 1;
      }
      else
      {
        v30 = 0;
        v21 = 0;
      }
      v26 = v21;
      v27 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v16,
        (unsigned int)byte_18006FE2B,
        v19,
        (unsigned int)&v27,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22);
    }
    if ( v29 || v11 || v12 == 1 || (v15 = v12 / 1000, v16 = 1000 * (v12 / 1000), v12 == v16) )
    {
      if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 0x10) != 0 )
        McTemplateU0zddi_EventWriteTransfer(v16, v15, (_DWORD)v28, a2, a2, v12);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180028d5c  mov     rax, rsp
0x180028d5f  mov     [rax+8], rbx
0x180028d63  mov     [rax+10h], rsi
0x180028d67  mov     [rax+18h], r8d
0x180028d6b  push    rbp
0x180028d6c  push    rdi
0x180028d6d  push    r12
0x180028d6f  push    r14
0x180028d71  push    r15
0x180028d73  lea     rbp, [rax-5Fh]
0x180028d77  sub     rsp, 90h
0x180028d7e  mov     r14d, edx
0x180028d81  mov     rbx, rcx
0x180028d84  call    ?KGT_GetClientProcessId@@YAKXZ; KGT_GetClientProcessId(void)
0x180028d89  mov     esi, eax
0x180028d8b  test    eax, eax
0x180028d8d  jnz     short loc_180028DCE
0x180028d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d96  lea     rax, WPP_GLOBAL_Control
0x180028d9d  cmp     rcx, rax
0x180028da0  jz      loc_180028E46
0x180028da6  lea     ebx, [rsi+1]
0x180028da9  test    [rcx+1Ch], bl
0x180028dac  jz      loc_180028E46
0x180028db2  mov     rcx, [rcx+10h]
0x180028db6  lea     edx, [rsi+0Ah]
0x180028db9  lea     r9, aKgtTrackclient; "KGT_TrackClient"
0x180028dc0  lea     r8, WPP_e4946bd270313a60ab1af95b4d7edf4d_Traceguids
0x180028dc7  call    WPP_SF_s
0x180028dcc  jmp     short loc_180028E46
0x180028dce  lea     rax, [rbp+57h+arg_18]
0x180028dd2  mov     [rbp+57h+arg_10], 0
0x180028dd9  mov     [rsp+0B0h+var_88], rax; int *
0x180028dde  lea     r9, [rbp+57h+var_60]; struct KEYGUARD_TELEMETRY_PID **
0x180028de2  lea     rax, [rbp+57h+arg_10]
0x180028de6  mov     dword ptr [rbp+57h+arg_18], 0
0x180028ded  mov     r8d, esi; unsigned int
0x180028df0  mov     [rsp+0B0h+var_90], rax; int *
0x180028df5  mov     rcx, rbx; struct KEYGUARD_TELEMETRY_GLOBAL *
0x180028df8  mov     [rbp+57h+var_60], 0
0x180028e00  call    ?KGT_AcquireImageCreatePid@@YAPEAUKEYGUARD_TELEMETRY_IMAGE_T@@PEAUKEYGUARD_TELEMETRY_GLOBAL@@HKPEAPEAUKEYGUARD_TELEMETRY_PID@@PEAH2@Z; KGT_AcquireImageCreatePid(KEYGUARD_TELEMETRY_GLOBAL *,int,ulong,KEYGUARD_TELEMETRY_PID * *,int *,int *)
0x180028e05  mov     rdi, rax
0x180028e08  test    rax, rax
0x180028e0b  jnz     short loc_180028E4D
0x180028e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e14  lea     rax, WPP_GLOBAL_Control
0x180028e1b  cmp     rcx, rax
0x180028e1e  jz      short loc_180028E46
0x180028e20  lea     ebx, [rdi+1]
0x180028e23  test    [rcx+1Ch], bl
0x180028e26  jz      short loc_180028E46
0x180028e28  mov     rcx, [rcx+10h]
0x180028e2c  lea     edx, [rdi+0Bh]
0x180028e2f  lea     r9, aKgtTrackclient; "KGT_TrackClient"
0x180028e36  mov     dword ptr [rsp+0B0h+var_90], esi
0x180028e3a  lea     r8, WPP_e4946bd270313a60ab1af95b4d7edf4d_Traceguids
0x180028e41  call    WPP_SF_sD
0x180028e46  xor     eax, eax
0x180028e48  jmp     loc_180028FDE
0x180028e4d  mov     rsi, [rbp+57h+var_60]
0x180028e51  cmp     dword ptr [rsi+4], 0
0x180028e55  jnz     loc_180028FDB
0x180028e5b  lea     rcx, [rax+18h]; CriticalSection
0x180028e5f  call    cs:__imp_RtlEnterCriticalSection
0x180028e66  nop     dword ptr [rax+rax+00h]
0x180028e6b  xor     r12d, r12d
0x180028e6e  lea     ebx, [r12+1]
0x180028e73  cmp     [rsi+4], r12d
0x180028e77  jnz     short loc_180028E8D
0x180028e79  test    r14d, r14d
0x180028e7c  jnz     short loc_180028E8D
0x180028e7e  mov     [rsi+4], ebx
0x180028e81  cmp     [rdi+0Ch], r12d
0x180028e85  jnz     short loc_180028E8A
0x180028e87  mov     [rdi+0Ch], ebx
0x180028e8a  mov     r12d, ebx
0x180028e8d  add     [rsi+8], rbx
0x180028e91  lea     rcx, [rdi+18h]; CriticalSection
0x180028e95  mov     rsi, [rsi+8]
0x180028e99  call    cs:__imp_RtlLeaveCriticalSection
0x180028ea0  nop     dword ptr [rax+rax+00h]
0x180028ea5  cmp     qword ptr [rdi], 0
0x180028ea9  lea     r15, dword_18006B48C
0x180028eb0  mov     rax, r15
0x180028eb3  cmovnz  rax, [rdi]
0x180028eb7  mov     [rbp+57h+var_30], rax
0x180028ebb  call    cs:__imp_RtlDllShutdownInProgress
0x180028ec2  nop     dword ptr [rax+rax+00h]
0x180028ec7  test    al, al
0x180028ec9  jnz     loc_180028F85
0x180028ecf  mov     eax, cs:dword_180079160
0x180028ed5  test    eax, eax
0x180028ed7  jz      loc_180028F85
0x180028edd  mov     rdx, 400000000000h
0x180028ee7  lea     rcx, dword_180079160
0x180028eee  call    _tlgKeywordOn
0x180028ef3  test    al, al
0x180028ef5  jz      loc_180028F85
0x180028efb  cmp     qword ptr [rdi], 0
0x180028eff  mov     [rbp+57h+var_60], 2000000h
0x180028f07  cmovnz  r15, [rdi]
0x180028f0b  mov     [rbp+57h+var_50], r15
0x180028f0f  mov     [rbp+57h+var_58], 1000000h
0x180028f17  mov     [rbp+57h+var_48], 0
0x180028f1f  cmp     [rbp+57h+arg_10], ebx
0x180028f22  jnz     short loc_180028F2D
0x180028f24  mov     [rbp+57h+arg_18], rbx
0x180028f28  mov     rax, rbx
0x180028f2b  jmp     short loc_180028F37
0x180028f2d  mov     [rbp+57h+arg_18], 0
0x180028f35  xor     eax, eax
0x180028f37  mov     [rbp+57h+var_40], rax
0x180028f3b  lea     r9, [rbp+57h+var_38]
0x180028f3f  lea     rax, [rbp+57h+var_60]
0x180028f43  mov     [rbp+57h+var_38], rbx
0x180028f47  mov     [rsp+0B0h+var_68], rax
0x180028f4c  lea     rdx, byte_18006FE2B
0x180028f53  lea     rax, [rbp+57h+var_58]
0x180028f57  mov     [rsp+0B0h+var_70], rax
0x180028f5c  lea     rax, [rbp+57h+var_50]
0x180028f60  mov     [rsp+0B0h+var_78], rax
0x180028f65  lea     rax, [rbp+57h+var_48]
0x180028f69  mov     [rsp+0B0h+var_80], rax
0x180028f6e  lea     rax, [rbp+57h+arg_18]
0x180028f72  mov     [rsp+0B0h+var_88], rax
0x180028f77  lea     rax, [rbp+57h+var_40]
0x180028f7b  mov     [rsp+0B0h+var_90], rax
0x180028f80  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@222AEBU?$_tlgWrapSz@G@@22@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180028f85  cmp     [rbp+57h+arg_10], 0
0x180028f89  jnz     short loc_180028FBC
0x180028f8b  test    r12d, r12d
0x180028f8e  jnz     short loc_180028FBC
0x180028f90  cmp     rsi, rbx
0x180028f93  jz      short loc_180028FBC
0x180028f95  mov     rax, 20C49BA5E353F7CFh
0x180028f9f  imul    rsi
0x180028fa2  sar     rdx, 7
0x180028fa6  mov     rax, rdx
0x180028fa9  shr     rax, 3Fh
0x180028fad  add     rdx, rax
0x180028fb0  imul    rcx, rdx, 3E8h
0x180028fb7  cmp     rsi, rcx
0x180028fba  jnz     short loc_180028FDB
0x180028fbc  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 10h
0x180028fc3  jz      short loc_180028FDB
0x180028fc5  mov     r8, [rbp+57h+var_30]
0x180028fc9  mov     r9d, r14d
0x180028fcc  mov     [rsp+0B0h+var_88], rsi
0x180028fd1  mov     dword ptr [rsp+0B0h+var_90], r14d
0x180028fd6  call    McTemplateU0zddi_EventWriteTransfer
0x180028fdb  mov     rax, rdi
0x180028fde  lea     r11, [rsp+0B0h+var_20]
0x180028fe6  mov     rbx, [r11+30h]
0x180028fea  mov     rsi, [r11+38h]
0x180028fee  mov     rsp, r11
0x180028ff1  pop     r15
0x180028ff3  pop     r14
0x180028ff5  pop     r12
0x180028ff7  pop     rdi
0x180028ff8  pop     rbp
0x180028ff9  retn
```
