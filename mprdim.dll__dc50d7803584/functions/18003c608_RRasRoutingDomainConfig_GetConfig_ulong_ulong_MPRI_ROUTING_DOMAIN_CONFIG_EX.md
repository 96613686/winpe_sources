# RRasRoutingDomainConfig::GetConfig(ulong,ulong,_MPRI_ROUTING_DOMAIN_CONFIG_EX *)

- ea: `0x18003c608`
- end: `0x18003c80a`
- name: `?GetConfig@RRasRoutingDomainConfig@@QEAAKKKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, unsigned int, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003d3f4`

## callees

- `0x180038f98`
- `0x18003c608`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x18003c680`: `RRasRoutingDomainConfig::GetConfig`
- `0x18003c6df`: `RRasRoutingDomainConfig::GetConfig`
- `0x18003c77e`: `RRasRoutingDomainConfig::GetConfig`
- `0x18003c789`: `%s: CopyConfigEx1Data failed: %d.`
- `0x18003c6eb`: `%s: GetConfig: Un-supported revision (%d).`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::GetConfig(
        RRasRoutingDomainConfig *this,
        int a2,
        unsigned int a3,
        struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *a4)
{
  unsigned int v8; // ebx
  const struct _GUID *v9; // r9
  unsigned int v10; // eax
  const struct _GUID *v11; // r9
  GUID v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+54h] [rbp-ACh]
  __int128 v16; // [rsp+64h] [rbp-9Ch]
  int v17; // [rsp+74h] [rbp-8Ch]
  int v18; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v19[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v14 = 0;
  v17 = 0;
  v15 = 0;
  v16 = 0;
  if ( a4 )
  {
    if ( a3 == 1 )
    {
      *(_BYTE *)a4 = 1;
      v10 = RRasRoutingDomainConfig::CopyConfigEx1Data(
              this,
              a2,
              (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *)((char *)a4 + 8));
      v8 = v10;
      if ( v10 && (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v18) = 0;
        LOWORD(v14) = 0;
        v13 = GUID_NULL;
        FormatRRASErrorString(&v18, L"%s: CopyConfigEx1Data failed: %d.", L"RRasRoutingDomainConfig::GetConfig", v10);
        v11 = &v13;
        if ( this != (RRasRoutingDomainConfig *)-516LL )
          v11 = (const struct _GUID *)((char *)this + 516);
        gCfgStoreParamTemplateFunc(
          gCfgStoreEtwContext,
          (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
          (const unsigned __int16 *)&v18,
          v11,
          0,
          (const unsigned __int16 *)&v14);
      }
    }
    else
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v18) = 0;
        LOWORD(v14) = 0;
        v13 = GUID_NULL;
        FormatRRASErrorString(
          &v18,
          L"%s: GetConfig: Un-supported revision (%d).",
          L"RRasRoutingDomainConfig::GetConfig",
          a3);
        v9 = &v13;
        if ( this != (RRasRoutingDomainConfig *)-516LL )
          v9 = (const struct _GUID *)((char *)this + 516);
        gCfgStoreParamTemplateFunc(
          gCfgStoreEtwContext,
          (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
          (const unsigned __int16 *)&v18,
          v9,
          0,
          (const unsigned __int16 *)&v14);
      }
      return 50;
    }
  }
  else
  {
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"%hs(Line#%d): Invalid parameter.", "RRasRoutingDomainConfig::GetConfig", 1788);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v18);
    }
    return 87;
  }
  return v8;
}

```

## disassembly

```asm
0x18003c608  push    rbp
0x18003c60a  push    rbx
0x18003c60b  push    rsi
0x18003c60c  push    rdi
0x18003c60d  push    r14
0x18003c60f  lea     rbp, [rsp-790h]
0x18003c617  sub     rsp, 890h
0x18003c61e  mov     rax, cs:__security_cookie
0x18003c625  xor     rax, rsp
0x18003c628  mov     [rbp+7B0h+var_30], rax
0x18003c62f  mov     edi, r8d
0x18003c632  mov     r14d, edx
0x18003c635  mov     rsi, rcx
0x18003c638  xor     eax, eax
0x18003c63a  xor     edx, edx; Val
0x18003c63c  mov     [rbp+7B0h+var_830], eax
0x18003c63f  mov     r8d, 7FCh; Size
0x18003c645  lea     rcx, [rbp+7B0h+var_82C]; void *
0x18003c649  mov     rbx, r9
0x18003c64c  call    memset_0
0x18003c651  xor     eax, eax
0x18003c653  xorps   xmm0, xmm0
0x18003c656  mov     [rsp+8B0h+var_860], eax
0x18003c65a  mov     [rsp+8B0h+var_83C], eax
0x18003c65e  movups  [rsp+8B0h+var_85C], xmm0
0x18003c663  movups  [rsp+8B0h+var_84C], xmm0
0x18003c668  test    rbx, rbx
0x18003c66b  jnz     short loc_18003C6BF
0x18003c66d  cmp     qword ptr cs:xmmword_180071090, rax
0x18003c674  jz      short loc_18003C6B5
0x18003c676  mov     r9d, 6FCh
0x18003c67c  mov     word ptr [rbp+7B0h+var_830], ax
0x18003c680  lea     r8, aRrasroutingdom_12; "RRasRoutingDomainConfig::GetConfig"
0x18003c687  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003c68e  lea     rcx, [rbp+7B0h+var_830]
0x18003c692  call    FormatRRASErrorString
0x18003c697  mov     rdx, qword ptr cs:xmmword_180071090
0x18003c69e  lea     r8, [rbp+7B0h+var_830]
0x18003c6a2  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c6a9  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003c6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6b5  mov     ebx, 57h ; 'W'
0x18003c6ba  jmp     loc_18003C7EB
0x18003c6bf  cmp     edi, 1
0x18003c6c2  jz      loc_18003C74F
0x18003c6c8  cmp     qword ptr cs:xmmword_1800710A0, rax
0x18003c6cf  jz      short loc_18003C745
0x18003c6d1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003c6d8  mov     r9d, edi
0x18003c6db  mov     word ptr [rbp+7B0h+var_830], ax
0x18003c6df  lea     r8, aRrasroutingdom_30; "RRasRoutingDomainConfig::GetConfig"
0x18003c6e6  mov     word ptr [rsp+8B0h+var_860], ax
0x18003c6eb  lea     rdx, aSGetconfigUnSu; "%s: GetConfig: Un-supported revision (%"...
0x18003c6f2  lea     rcx, [rbp+7B0h+var_830]
0x18003c6f6  movdqu  [rsp+8B0h+var_870], xmm0
0x18003c6fc  call    FormatRRASErrorString
0x18003c701  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003c708  lea     rcx, [rsi+204h]
0x18003c70f  test    rcx, rcx
0x18003c712  lea     rax, [rsp+8B0h+var_860]
0x18003c717  mov     [rsp+8B0h+var_888], rax
0x18003c71c  lea     r9, [rsp+8B0h+var_870]
0x18003c721  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003c728  lea     r8, [rbp+7B0h+var_830]
0x18003c72c  cmovnz  r9, rcx
0x18003c730  mov     [rsp+8B0h+var_890], 0
0x18003c739  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c745  mov     ebx, 32h ; '2'
0x18003c74a  jmp     loc_18003C7EB
0x18003c74f  lea     r8, [rbx+8]; struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *
0x18003c753  mov     byte ptr [rbx], 1
0x18003c756  mov     edx, r14d; unsigned int
0x18003c759  mov     rcx, rsi; this
0x18003c75c  call    ?CopyConfigEx1Data@RRasRoutingDomainConfig@@AEAAKKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX1@@@Z; RRasRoutingDomainConfig::CopyConfigEx1Data(ulong,_MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)
0x18003c761  mov     ebx, eax
0x18003c763  test    eax, eax
0x18003c765  jz      loc_18003C7EB
0x18003c76b  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18003c773  jz      short loc_18003C7EB
0x18003c775  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003c77c  xor     ecx, ecx
0x18003c77e  lea     r8, aRrasroutingdom_30; "RRasRoutingDomainConfig::GetConfig"
0x18003c785  mov     word ptr [rbp+7B0h+var_830], cx
0x18003c789  lea     rdx, aSCopyconfigex1; "%s: CopyConfigEx1Data failed: %d."
0x18003c790  mov     word ptr [rsp+8B0h+var_860], cx
0x18003c795  mov     r9d, eax
0x18003c798  lea     rcx, [rbp+7B0h+var_830]
0x18003c79c  movdqu  [rsp+8B0h+var_870], xmm0
0x18003c7a2  call    FormatRRASErrorString
0x18003c7a7  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003c7ae  lea     rcx, [rsi+204h]
0x18003c7b5  test    rcx, rcx
0x18003c7b8  lea     rax, [rsp+8B0h+var_860]
0x18003c7bd  mov     [rsp+8B0h+var_888], rax
0x18003c7c2  lea     r9, [rsp+8B0h+var_870]
0x18003c7c7  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003c7ce  lea     r8, [rbp+7B0h+var_830]
0x18003c7d2  cmovnz  r9, rcx
0x18003c7d6  mov     [rsp+8B0h+var_890], 0
0x18003c7df  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7eb  mov     eax, ebx
0x18003c7ed  mov     rcx, [rbp+7B0h+var_30]
0x18003c7f4  xor     rcx, rsp; StackCookie
0x18003c7f7  call    __security_check_cookie
0x18003c7fc  add     rsp, 890h
0x18003c803  pop     r14
0x18003c805  pop     rdi
0x18003c806  pop     rsi
0x18003c807  pop     rbx
0x18003c808  pop     rbp
0x18003c809  retn
```
