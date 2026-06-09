# EfsLsaRpcTelemetryProvider::EfsRpcRegisterDownlevelServer<long &>(long &)

- ea: `0x180002eac`
- end: `0x180003013`
- name: `??$EfsRpcRegisterDownlevelServer@AEAJ@EfsLsaRpcTelemetryProvider@@SAXAEAJ@Z`
- size: `359`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002cf0`

## callees

- `0x18000163c`
- `0x180001f34`
- `0x180002eac`
- `0x180005584`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180002f6e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180002f6e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002ef4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002ef4`

## pseudocode

```c
int __fastcall EfsLsaRpcTelemetryProvider::EfsRpcRegisterDownlevelServer<long &>(WINBOOL *a1)
{
  void (*v2)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  __int64 v3; // rcx
  __int64 v4; // rax
  WINBOOL fPending; // [rsp+30h] [rbp-9h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp+7h] BYREF
  WINBOOL *p_fPending; // [rsp+60h] [rbp+27h]
  __int64 v10; // [rsp+68h] [rbp+2Fh]
  LPVOID *p_Context; // [rsp+70h] [rbp+37h]
  __int64 v12; // [rsp+78h] [rbp+3Fh]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`EfsLsaRpcTelemetryProvider::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_18001EBF8 = 0;
    Context = &qword_18001EBF0;
    qword_18001EBF0 = &EfsLsaRpcTelemetryProvider::`vftable';
    byte_18001EC00 = 0;
    dword_18001EC04 = 0;
    qword_18001EC08 = (struct _tlgProvider_t *)&`EfsLsaRpcTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_aa351e6b4ec36dd33584e3a17829fbea_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18001EBF0, qword_18001EC08, v2);
    InitOnceComplete(&`EfsLsaRpcTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_18001EBF0);
  }
  v3 = *((_QWORD *)Context + 1);
  LODWORD(v4) = *(_DWORD *)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    v4 = *(_QWORD *)(v3 + 16);
    if ( (v4 & 0x800000000000LL) != 0 )
    {
      LODWORD(v4) = 0;
      if ( (*(_QWORD *)(v3 + 24) & 0x800000000000LL) == *(_QWORD *)(v3 + 24) )
      {
        fPending = *a1;
        v10 = 4;
        p_Context = &Context;
        Context = (LPVOID)0x1000000;
        p_fPending = &fPending;
        v12 = 8;
        LODWORD(v4) = tlgWriteTransfer_EventWriteTransfer(v3, (unsigned __int8 *)byte_18001A8B1, 0, 0, 4u, &v8);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180002eac  mov     [rsp-8+arg_0], rbx
0x180002eb1  mov     [rsp-8+arg_8], rdi
0x180002eb6  push    rbp
0x180002eb7  lea     rbp, [rsp-57h]
0x180002ebc  sub     rsp, 90h
0x180002ec3  mov     rax, cs:__security_cookie
0x180002eca  xor     rax, rsp
0x180002ecd  mov     [rbp+57h+var_10], rax
0x180002ed1  mov     rbx, rcx
0x180002ed4  mov     [rbp+57h+Context], 0
0x180002edc  lea     rcx, ?wrapper@?1??Instance@EfsLsaRpcTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VEfsLsaRpcTelemetryProvider@@@details@wil@@A; lpInitOnce
0x180002ee3  mov     [rbp+57h+fPending], 0
0x180002eea  lea     r9, [rbp+57h+Context]; lpContext
0x180002eee  xor     edx, edx; dwFlags
0x180002ef0  lea     r8, [rbp+57h+fPending]; fPending
0x180002ef4  call    cs:__imp_InitOnceBeginInitialize
0x180002efa  test    eax, eax
0x180002efc  jz      short loc_180002F74
0x180002efe  cmp     [rbp+57h+fPending], 0
0x180002f02  jz      short loc_180002F74
0x180002f04  lea     rdi, qword_18001EBF0
0x180002f0b  mov     cs:qword_18001EBF8, 0
0x180002f16  lea     rax, ??_7EfsLsaRpcTelemetryProvider@@6B@; const EfsLsaRpcTelemetryProvider::`vftable'
0x180002f1d  mov     [rbp+57h+Context], rdi
0x180002f21  mov     cs:qword_18001EBF0, rax
0x180002f28  mov     cs:byte_18001EC00, 0
0x180002f2f  mov     cs:dword_18001EC04, 0
0x180002f39  lea     rax, ?__hInner@?1???0StaticHandle@EfsLsaRpcTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `EfsLsaRpcTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180002f40  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_aa351e6b4ec36dd33584e3a17829fbea_@@CA@XZ; void (__cdecl *)()
0x180002f47  mov     cs:qword_18001EC08, rax
0x180002f4e  call    atexit
0x180002f53  mov     rdx, cs:qword_18001EC08; struct _tlgProvider_t *
0x180002f5a  mov     rcx, rdi; this
0x180002f5d  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180002f62  mov     r8, rdi; lpContext
0x180002f65  lea     rcx, ?wrapper@?1??Instance@EfsLsaRpcTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VEfsLsaRpcTelemetryProvider@@@details@wil@@A; lpInitOnce
0x180002f6c  xor     edx, edx; dwFlags
0x180002f6e  call    cs:__imp_InitOnceComplete
0x180002f74  mov     rax, [rbp+57h+Context]
0x180002f78  mov     rcx, [rax+8]
0x180002f7c  mov     eax, [rcx]
0x180002f7e  cmp     eax, 5
0x180002f81  jbe     short loc_180002FF2
0x180002f83  mov     rdx, [rcx+18h]
0x180002f87  mov     r8, 800000000000h
0x180002f91  mov     rax, [rcx+10h]
0x180002f95  test    r8, rax
0x180002f98  jz      short loc_180002FF2
0x180002f9a  mov     rax, rdx
0x180002f9d  and     rax, r8
0x180002fa0  cmp     rax, rdx
0x180002fa3  jnz     short loc_180002FF2
0x180002fa5  mov     eax, [rbx]
0x180002fa7  mov     edx, 4
0x180002fac  mov     [rbp+57h+fPending], eax
0x180002faf  xor     r9d, r9d
0x180002fb2  lea     rax, [rbp+57h+Context]
0x180002fb6  mov     [rbp+57h+var_28], rdx
0x180002fba  mov     [rbp+57h+var_20], rax
0x180002fbe  xor     r8d, r8d
0x180002fc1  lea     rax, [rbp+57h+fPending]
0x180002fc5  mov     [rbp+57h+Context], 1000000h
0x180002fcd  mov     [rbp+57h+var_30], rax
0x180002fd1  lea     rax, [rbp+57h+var_50]
0x180002fd5  mov     [rsp+90h+var_68], rax
0x180002fda  mov     [rsp+90h+var_70], edx
0x180002fde  lea     rdx, byte_18001A8B1
0x180002fe5  mov     [rbp+57h+var_18], 8
0x180002fed  call    _tlgWriteTransfer_EventWriteTransfer
0x180002ff2  mov     rcx, [rbp+57h+var_10]
0x180002ff6  xor     rcx, rsp; StackCookie
0x180002ff9  call    __security_check_cookie
0x180002ffe  lea     r11, [rsp+90h+var_s0]
0x180003006  mov     rbx, [r11+10h]
0x18000300a  mov     rdi, [r11+18h]
0x18000300e  mov     rsp, r11
0x180003011  pop     rbp
0x180003012  retn
```
