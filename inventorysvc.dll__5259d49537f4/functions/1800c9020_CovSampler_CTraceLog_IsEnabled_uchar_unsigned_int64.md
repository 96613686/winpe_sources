# CovSampler::CTraceLog::IsEnabled(uchar,unsigned __int64)

- ea: `0x1800c9020`
- end: `0x1800c914a`
- name: `?IsEnabled@CTraceLog@CovSampler@@SA_NE_K@Z`
- size: `298`
- prototype: `bool __fastcall(unsigned __int8, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c860c`

## callees

- `0x180001b28`
- `0x1800030e0`
- `0x1800c9020`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800c90ff`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800c90ff`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800c9053`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800c9053`

## pseudocode

```c
char __fastcall CovSampler::CTraceLog::IsEnabled()
{
  char v0; // bl
  __int64 v1; // rcx
  WINBOOL v3; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  v0 = 1;
  if ( InitOnceBeginInitialize(&`CovSampler::CTraceLog::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    qword_1800FF978 = 0;
    v4 = &qword_1800FF970;
    qword_1800FF970 = (__int64)&CovSampler::CTraceLog::`vftable';
    byte_1800FF980 = 0;
    dword_1800FF984 = 0;
    qword_1800FF988 = &`CovSampler::CTraceLog::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_794672c0d1a5a6e18182a3e6b9ae191b_::_lambda_invoker_cdecl_);
    qword_1800FF978 = (__int64)qword_1800FF988;
    byte_1800FF980 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1800FF988);
    dword_1800FF984 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800FF970 + 8))(&qword_1800FF970);
    InitOnceComplete(&`CovSampler::CTraceLog::Instance'::`2'::wrapper, 0, &qword_1800FF970);
  }
  v1 = v4[1];
  if ( !v1
    || !*(_DWORD *)v1
    || (*(_QWORD *)(v1 + 16) & 0x400000000000LL) == 0
    || (*(_QWORD *)(v1 + 24) & 0x400000000000LL) != *(_QWORD *)(v1 + 24) )
  {
    return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x1800c9020  mov     rax, rsp
0x1800c9023  mov     [rax+18h], rbx
0x1800c9027  mov     [rax+10h], rdx
0x1800c902b  mov     [rax+8], cl
0x1800c902e  push    rdi
0x1800c902f  sub     rsp, 20h
0x1800c9033  lea     r9, [rax+10h]; lpContext
0x1800c9037  mov     qword ptr [rax+10h], 0
0x1800c903f  lea     r8, [rax+8]; fPending
0x1800c9043  mov     dword ptr [rax+8], 0
0x1800c904a  xor     edx, edx; dwFlags
0x1800c904c  lea     rcx, ?wrapper@?1??Instance@CTraceLog@CovSampler@@KAPEAV23@XZ@4V?$static_lazy@VCTraceLog@CovSampler@@@details@wil@@A; lpInitOnce
0x1800c9053  call    cs:__imp_InitOnceBeginInitialize
0x1800c9059  mov     ebx, 1
0x1800c905e  test    eax, eax
0x1800c9060  jz      loc_1800C9105
0x1800c9066  cmp     [rsp+28h+arg_0], 0
0x1800c906b  jz      loc_1800C9105
0x1800c9071  lea     rdi, qword_1800FF970
0x1800c9078  mov     cs:qword_1800FF978, 0
0x1800c9083  lea     rax, ??_7CTraceLog@CovSampler@@6B@; const CovSampler::CTraceLog::`vftable'
0x1800c908a  mov     [rsp+28h+arg_8], rdi
0x1800c908f  mov     cs:qword_1800FF970, rax
0x1800c9096  mov     cs:byte_1800FF980, 0
0x1800c909d  mov     cs:dword_1800FF984, 0
0x1800c90a7  lea     rax, ?__hInner@?1???0StaticHandle@CTraceLog@CovSampler@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `CovSampler::CTraceLog::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800c90ae  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_794672c0d1a5a6e18182a3e6b9ae191b_@@CA@XZ; void (__cdecl *)()
0x1800c90b5  mov     cs:qword_1800FF988, rax
0x1800c90bc  call    atexit
0x1800c90c1  mov     rcx, cs:qword_1800FF988; CallbackContext
0x1800c90c8  mov     cs:qword_1800FF978, rcx
0x1800c90cf  mov     cs:byte_1800FF980, bl
0x1800c90d5  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800c90da  mov     rax, cs:qword_1800FF970
0x1800c90e1  mov     rcx, rdi
0x1800c90e4  mov     cs:dword_1800FF984, ebx
0x1800c90ea  mov     rax, [rax+8]
0x1800c90ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c90f3  mov     r8, rdi; lpContext
0x1800c90f6  lea     rcx, ?wrapper@?1??Instance@CTraceLog@CovSampler@@KAPEAV23@XZ@4V?$static_lazy@VCTraceLog@CovSampler@@@details@wil@@A; lpInitOnce
0x1800c90fd  xor     edx, edx; dwFlags
0x1800c90ff  call    cs:__imp_InitOnceComplete
0x1800c9105  mov     rax, [rsp+28h+arg_8]
0x1800c910a  mov     rcx, [rax+8]
0x1800c910e  test    rcx, rcx
0x1800c9111  jz      short loc_1800C913B
0x1800c9113  mov     eax, [rcx]
0x1800c9115  test    eax, eax
0x1800c9117  jz      short loc_1800C913B
0x1800c9119  mov     rdx, [rcx+18h]
0x1800c911d  mov     rax, [rcx+10h]
0x1800c9121  mov     rcx, 400000000000h
0x1800c912b  test    rcx, rax
0x1800c912e  jz      short loc_1800C913B
0x1800c9130  mov     rax, rdx
0x1800c9133  and     rax, rcx
0x1800c9136  cmp     rax, rdx
0x1800c9139  jz      short loc_1800C913D
0x1800c913b  xor     bl, bl
0x1800c913d  mov     al, bl
0x1800c913f  mov     rbx, [rsp+28h+arg_10]
0x1800c9144  add     rsp, 20h
0x1800c9148  pop     rdi
0x1800c9149  retn
```
