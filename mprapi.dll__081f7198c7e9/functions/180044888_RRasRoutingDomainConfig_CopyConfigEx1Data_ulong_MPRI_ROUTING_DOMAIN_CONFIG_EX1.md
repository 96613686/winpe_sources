# RRasRoutingDomainConfig::CopyConfigEx1Data(ulong,_MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)

- ea: `0x180044888`
- end: `0x180044e66`
- name: `?CopyConfigEx1Data@RRasRoutingDomainConfig@@AEAAKKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX1@@@Z`
- size: `1502`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180047dec`

## callees

- `0x18004480c`
- `0x180044888`
- `0x180044e6c`
- `0x1800454dc`
- `0x180045668`
- `0x1800458bc`
- `0x180045c14`
- `0x18004f714`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044b51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044b51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044a8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044a8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044b59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044e1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044b59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044e1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044b6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044b6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044e28`

## string_xrefs

- `0x1800449f2`: `RRasRoutingDomainConfig::CopyConfigEx1Data`
- `0x180044bb6`: `RRasRoutingDomainConfig::CopyConfigEx1Data`
- `0x180044c6a`: `RRasRoutingDomainConfig::CopyConfigEx1Data`
- `0x180044db0`: `RRasRoutingDomainConfig::CopyConfigEx1Data`
- `0x180044db7`: `%s: GetConfig: Malloc failed.`
- `0x180044bc3`: `%s: CopyTransportInfo failed for IPv4: %d.`
- `0x180044c77`: `%s: CopyTransportInfo failed for IPv6: %d.`
- `0x1800449fe`: `%s: Un-supported config type '%d'.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::CopyConfigEx1Data(
        RRasRoutingDomainConfig *this,
        int a2,
        struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *a3)
{
  unsigned int v4; // ebx
  struct _MPRI_TRANSPORT_INFO_1 *v5; // rsi
  unsigned int v7; // r12d
  const struct _GUID *v8; // r15
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdx
  struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *v12; // rax
  struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *v13; // rcx
  unsigned int v14; // r13d
  int v15; // eax
  __int64 v16; // rdx
  void (*v17)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  const struct _GUID *v18; // r9
  unsigned int v19; // eax
  unsigned int v20; // edx
  unsigned int i; // r9d
  __int64 v22; // rax
  __int64 v23; // rcx
  struct _MPRI_TRANSPORT_INFO_1 *v24; // rax
  HANDLE ProcessHeap; // rax
  unsigned int v26; // eax
  const struct _GUID *v27; // r9
  unsigned int v28; // r15d
  unsigned int v29; // eax
  GUID *v30; // r9
  struct _MPRI_TRANSPORT_INFO_1 *v31; // rcx
  unsigned int v32; // eax
  const struct _GUID *v33; // r9
  HANDLE v34; // rax
  GUID v37; // [rsp+48h] [rbp-B8h] BYREF
  int v38; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v39; // [rsp+5Ch] [rbp-A4h]
  __int128 v40; // [rsp+6Ch] [rbp-94h]
  int v41; // [rsp+7Ch] [rbp-84h]
  int v42; // [rsp+80h] [rbp-80h] BYREF
  char v43[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v4 = 0;
  v42 = 0;
  v5 = 0;
  v7 = a2 & 0x80000000;
  memset_0(v43, 0, sizeof(v43));
  v8 = (const struct _GUID *)((char *)this + 516);
  v9 = 2147483646;
  v38 = 0;
  v41 = 0;
  v10 = (__int64)this;
  v39 = 0;
  v11 = 257;
  v40 = 0;
  *(_OWORD *)((char *)a3 + 516) = *(_OWORD *)((char *)this + 516);
  *((_DWORD *)a3 + 160) = *((_DWORD *)this + 133);
  v12 = a3;
  do
  {
    if ( !v9 )
      break;
    if ( !*(_WORD *)v10 )
      break;
    *(_WORD *)v12 = *(_WORD *)v10;
    v10 += 2;
    v12 = (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)v12 + 2);
    --v9;
    --v11;
  }
  while ( v11 );
  v13 = (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)v12 - 2);
  v14 = 0;
  if ( v11 )
    v13 = v12;
  v15 = a2;
  *(_WORD *)v13 = 0;
  while ( 1 )
  {
    v16 = v14;
    v17 = (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))*((unsigned int *)qword_18006EAD0
                                                                                                  + v14);
    if ( ((unsigned int)v17 & v15) != 0 )
      break;
LABEL_24:
    if ( ++v14 >= 0xC )
      goto LABEL_25;
  }
  switch ( (_DWORD)v17 )
  {
    case 1:
      v19 = RRasRoutingDomainConfig::CopyIpv4AddrPool(
              this,
              v7,
              (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a3 + 648));
      goto LABEL_30;
    case 2:
      v19 = RRasRoutingDomainConfig::CopyIpv6AddrPool(
              this,
              (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a3 + 664));
      goto LABEL_30;
    case 4:
      *((_DWORD *)a3 + 204) = 0;
      *((_QWORD *)a3 + 103) = 0;
      goto LABEL_60;
    case 8:
      v19 = RRasRoutingDomainConfig::CopyIkev2Config(this, (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a3 + 688));
      goto LABEL_30;
    case 0x10:
      if ( v7 )
      {
        v24 = (struct _MPRI_TRANSPORT_INFO_1 *)LocalAlloc(0x40u, 0x20u);
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        v24 = (struct _MPRI_TRANSPORT_INFO_1 *)HeapAlloc(ProcessHeap, 8u, 0x20u);
      }
      v5 = v24;
      if ( !v24 )
      {
        if ( (_QWORD)xmmword_180078C60 )
        {
          LOWORD(v42) = 0;
          LOWORD(v38) = 0;
          v37 = GUID_NULL;
          FormatRRASErrorString(&v42, L"%s: GetConfig: Malloc failed.", L"RRasRoutingDomainConfig::CopyConfigEx1Data");
          v33 = &v37;
          if ( v8 )
            v33 = v8;
          gCfgStoreParamTemplateFunc(
            gCfgStoreEtwContext,
            (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
            (const unsigned __int16 *)&v42,
            v33,
            0,
            (const unsigned __int16 *)&v38);
        }
        v4 = 8;
        goto LABEL_77;
      }
      v26 = RRasRoutingDomainConfig::CopyTransportInfo(this, v7, 1, v24);
      v4 = v26;
      if ( v26 )
      {
        if ( (_QWORD)xmmword_180078C60 )
        {
          LOWORD(v42) = 0;
          LOWORD(v38) = 0;
          v37 = GUID_NULL;
          FormatRRASErrorString(
            &v42,
            L"%s: CopyTransportInfo failed for IPv4: %d.",
            L"RRasRoutingDomainConfig::CopyConfigEx1Data",
            v26);
          v27 = &v37;
          if ( v8 )
            v27 = v8;
          gCfgStoreParamTemplateFunc(
            gCfgStoreEtwContext,
            (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
            (const unsigned __int16 *)&v42,
            v27,
            0,
            (const unsigned __int16 *)&v38);
        }
        if ( v4 != 2 )
          goto LABEL_65;
        v28 = 0;
      }
      else
      {
        v28 = 1;
      }
      v29 = RRasRoutingDomainConfig::CopyTransportInfo(
              this,
              v7,
              0,
              (struct _MPRI_TRANSPORT_INFO_1 *)((char *)v5 + 16 * v28));
      v4 = v29;
      if ( v29 )
      {
        if ( (_QWORD)xmmword_180078C60 )
        {
          LOWORD(v42) = 0;
          LOWORD(v38) = 0;
          v37 = GUID_NULL;
          FormatRRASErrorString(
            &v42,
            L"%s: CopyTransportInfo failed for IPv6: %d.",
            L"RRasRoutingDomainConfig::CopyConfigEx1Data",
            v29);
          v30 = &v37;
          if ( this != (RRasRoutingDomainConfig *)-516LL )
            v30 = (GUID *)((char *)this + 516);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180078C60,
            &v42,
            v30,
            0,
            &v38);
        }
      }
      else
      {
        ++v28;
      }
      if ( v28 )
      {
        *((_QWORD *)a3 + 101) = v5;
        v5 = 0;
        *((_DWORD *)a3 + 200) = v28;
      }
      v8 = (const struct _GUID *)((char *)this + 516);
      goto LABEL_58;
    case 0x800:
      v19 = RRasRoutingDomainConfig::CopyAccoountingConfig(
              this,
              (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a3 + 792),
              v10,
              v17);
      goto LABEL_30;
    case 0x2000:
      v20 = 0;
      for ( i = 0; v20 < *((_DWORD *)this + 136); ++v20 )
      {
        v10 = 3LL * v20;
        if ( *((_DWORD *)this + 3 * v20 + 137) )
        {
          v22 = i++;
          v23 = 3 * v22;
          *((_DWORD *)a3 + v23 + 210) = *((_DWORD *)this + 3 * v20 + 138);
          *((_DWORD *)a3 + v23 + 209) = *((_DWORD *)this + 3 * v20 + 137);
          *((_DWORD *)a3 + v23 + 211) = *((_DWORD *)this + 3 * v20 + 139);
        }
      }
      *((_DWORD *)a3 + 208) = i;
      goto LABEL_58;
    case 0x4000:
      v19 = RRasRoutingDomainConfig::CopyDialInConfig(
              this,
              v7,
              (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a3 + 536));
LABEL_30:
      v4 = v19;
LABEL_58:
      v16 = v14;
      goto LABEL_59;
  }
  if ( (_DWORD)v17 != 0x8000 )
  {
    if ( (_QWORD)xmmword_180078C60 )
    {
      LOWORD(v42) = 0;
      LOWORD(v38) = 0;
      v37 = GUID_NULL;
      FormatRRASErrorString(&v42, L"%s: Un-supported config type '%d'.", L"RRasRoutingDomainConfig::CopyConfigEx1Data");
      v18 = &v37;
      if ( v8 )
        v18 = v8;
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
        (const unsigned __int16 *)&v42,
        v18,
        0,
        (const unsigned __int16 *)&v38);
    }
    goto LABEL_22;
  }
  *((_DWORD *)a3 + 133) = *((_DWORD *)this + 134);
LABEL_59:
  if ( !v4 )
  {
LABEL_60:
    v31 = v5;
    *((_DWORD *)a3 + 161) |= *((_DWORD *)qword_18006EAD0 + v16);
    v32 = v4;
    goto LABEL_67;
  }
LABEL_65:
  v31 = v5;
  v32 = v4;
  if ( v4 == 2 || v4 == 50 )
    goto LABEL_22;
LABEL_67:
  if ( v4 == 1168 )
  {
LABEL_22:
    v4 = 0;
LABEL_23:
    v15 = a2;
    goto LABEL_24;
  }
  v4 = v32;
  v5 = v31;
  if ( !v32 )
    goto LABEL_23;
LABEL_25:
  *((_DWORD *)a3 + 161) &= ~4u;
  if ( v5 )
  {
    if ( v7 )
    {
      LocalFree(v5);
    }
    else
    {
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v5);
    }
  }
  if ( v4 )
LABEL_77:
    FreeMpriRoutingDomainConfigEx1Object(a3);
  return v4;
}

```

## disassembly

```asm
0x180044888  mov     [rsp-8+arg_18], rbx
0x18004488d  push    rbp
0x18004488e  push    rsi
0x18004488f  push    rdi
0x180044890  push    r12
0x180044892  push    r13
0x180044894  push    r14
0x180044896  push    r15
0x180044898  lea     rbp, [rsp-790h]
0x1800448a0  sub     rsp, 890h
0x1800448a7  mov     rax, cs:__security_cookie
0x1800448ae  xor     rax, rsp
0x1800448b1  mov     [rbp+7C0h+var_40], rax
0x1800448b8  mov     r14, rcx
0x1800448bb  mov     [rsp+8C0h+var_880], edx
0x1800448bf  xor     ecx, ecx
0x1800448c1  mov     r12d, edx
0x1800448c4  mov     ebx, ecx
0x1800448c6  mov     [rbp+7C0h+var_840], ecx
0x1800448c9  mov     esi, ecx
0x1800448cb  mov     rdi, r8
0x1800448ce  lea     rcx, [rbp+7C0h+var_83C]; void *
0x1800448d2  xor     edx, edx; Val
0x1800448d4  mov     r8d, 7FCh; Size
0x1800448da  and     r12d, 80000000h
0x1800448e1  call    memset_0
0x1800448e6  xorps   xmm0, xmm0
0x1800448e9  lea     r15, [r14+204h]
0x1800448f0  xor     r10d, r10d
0x1800448f3  mov     ecx, 7FFFFFFEh
0x1800448f8  xor     eax, eax
0x1800448fa  mov     [rsp+8C0h+var_868], r10d
0x1800448ff  mov     [rsp+8C0h+var_844], eax
0x180044903  mov     r8, r14
0x180044906  movups  [rsp+8C0h+var_864], xmm0
0x18004490b  mov     edx, 101h
0x180044910  movups  [rsp+8C0h+var_854], xmm0
0x180044915  movups  xmm0, xmmword ptr [r15]
0x180044919  movdqu  xmmword ptr [rdi+204h], xmm0
0x180044921  mov     eax, [r14+214h]
0x180044928  mov     [rdi+280h], eax
0x18004492e  mov     rax, rdi
0x180044931  test    rcx, rcx
0x180044934  jz      short loc_180044955
0x180044936  movzx   r9d, word ptr [r8]
0x18004493a  test    r9w, r9w
0x18004493e  jz      short loc_180044955
0x180044940  mov     [rax], r9w
0x180044944  add     r8, 2
0x180044948  add     rax, 2
0x18004494c  dec     rcx
0x18004494f  sub     rdx, 1
0x180044953  jnz     short loc_180044931
0x180044955  lea     rcx, [rax-2]
0x180044959  test    rdx, rdx
0x18004495c  mov     r13d, r10d
0x18004495f  cmovnz  rcx, rax
0x180044963  mov     eax, [rsp+8C0h+var_880]
0x180044967  mov     [rcx], r10w
0x18004496b  mov     edx, r13d
0x18004496e  lea     r11, qword_18006EAD0
0x180044975  mov     r9d, [r11+rdx*4]
0x180044979  test    eax, r9d
0x18004497c  jz      loc_180044A61
0x180044982  mov     ecx, r9d
0x180044985  sub     ecx, 1
0x180044988  jz      loc_180044D51
0x18004498e  sub     ecx, 1
0x180044991  jz      loc_180044D3D
0x180044997  sub     ecx, 2
0x18004499a  jz      loc_180044D29
0x1800449a0  sub     ecx, 4
0x1800449a3  jz      loc_180044D15
0x1800449a9  sub     ecx, 8
0x1800449ac  jz      loc_180044B44
0x1800449b2  sub     ecx, 7F0h
0x1800449b8  jz      loc_180044B30
0x1800449be  sub     ecx, 1800h
0x1800449c4  jz      loc_180044AC3
0x1800449ca  sub     ecx, 2000h
0x1800449d0  jz      loc_180044AA7
0x1800449d6  cmp     ecx, 4000h
0x1800449dc  jz      loc_180044A95
0x1800449e2  cmp     qword ptr cs:xmmword_180078C60, r10
0x1800449e9  jz      short loc_180044A5A
0x1800449eb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800449f2  lea     r8, aRrasroutingdom_38; "RRasRoutingDomainConfig::CopyConfigEx1D"...
0x1800449f9  mov     word ptr [rbp+7C0h+var_840], r10w
0x1800449fe  lea     rdx, aSUnSupportedCo; "%s: Un-supported config type '%d'."
0x180044a05  mov     word ptr [rsp+8C0h+var_868], r10w
0x180044a0b  lea     rcx, [rbp+7C0h+var_840]
0x180044a0f  movdqu  [rsp+8C0h+var_878], xmm0
0x180044a15  call    FormatRRASErrorString
0x180044a1a  mov     rdx, qword ptr cs:xmmword_180078C60
0x180044a21  lea     rax, [rsp+8C0h+var_868]
0x180044a26  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044a2d  lea     r9, [rsp+8C0h+var_878]
0x180044a32  mov     [rsp+8C0h+var_898], rax
0x180044a37  lea     r8, [rbp+7C0h+var_840]
0x180044a3b  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180044a42  test    r15, r15
0x180044a45  mov     [rsp+8C0h+var_8A0], 0
0x180044a4e  cmovnz  r9, r15
0x180044a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a57  xor     r10d, r10d
0x180044a5a  mov     ebx, r10d
0x180044a5d  mov     eax, [rsp+8C0h+var_880]
0x180044a61  inc     r13d
0x180044a64  cmp     r13d, 0Ch
0x180044a68  jb      loc_18004496B
0x180044a6e  and     dword ptr [rdi+284h], 0FFFFFFFBh
0x180044a75  test    rsi, rsi
0x180044a78  jz      loc_180044E2E
0x180044a7e  test    r12d, r12d
0x180044a81  jz      loc_180044E1A
0x180044a87  mov     rcx, rsi; hMem
0x180044a8a  call    cs:__imp_LocalFree
0x180044a90  jmp     loc_180044E2E
0x180044a95  mov     eax, [r14+218h]
0x180044a9c  mov     [rdi+214h], eax
0x180044aa2  jmp     loc_180044D00
0x180044aa7  lea     r8, [rdi+218h]; struct _MPRI_DIAL_IN_CONFIG_1 *
0x180044aae  mov     edx, r12d; int
0x180044ab1  mov     rcx, r14; this
0x180044ab4  call    ?CopyDialInConfig@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_DIAL_IN_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyDialInConfig(int,_MPRI_DIAL_IN_CONFIG_1 *)
0x180044ab9  mov     ebx, eax
0x180044abb  xor     r10d, r10d
0x180044abe  jmp     loc_180044CF6
0x180044ac3  mov     edx, r10d
0x180044ac6  mov     r9d, r10d
0x180044ac9  cmp     [r14+220h], r10d
0x180044ad0  jbe     short loc_180044B24
0x180044ad2  mov     eax, edx
0x180044ad4  lea     r8, [rax+rax*2]
0x180044ad8  cmp     [r14+r8*4+224h], r10d
0x180044ae0  jz      short loc_180044B19
0x180044ae2  mov     eax, r9d
0x180044ae5  inc     r9d
0x180044ae8  lea     rcx, [rax+rax*2]
0x180044aec  mov     eax, [r14+r8*4+228h]
0x180044af4  mov     [rdi+rcx*4+348h], eax
0x180044afb  mov     eax, [r14+r8*4+224h]
0x180044b03  mov     [rdi+rcx*4+344h], eax
0x180044b0a  mov     eax, [r14+r8*4+22Ch]
0x180044b12  mov     [rdi+rcx*4+34Ch], eax
0x180044b19  inc     edx
0x180044b1b  cmp     edx, [r14+220h]
0x180044b22  jb      short loc_180044AD2
0x180044b24  mov     [rdi+340h], r9d
0x180044b2b  jmp     loc_180044CFD
0x180044b30  lea     rdx, [rdi+318h]; struct _MPRI_ACCOUNTING_CONFIG_1 *
0x180044b37  mov     rcx, r14; this
0x180044b3a  call    ?CopyAccoountingConfig@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_ACCOUNTING_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyAccoountingConfig(_MPRI_ACCOUNTING_CONFIG_1 *)
0x180044b3f  jmp     loc_180044AB9
0x180044b44  test    r12d, r12d
0x180044b47  jz      short loc_180044B59
0x180044b49  mov     edx, 20h ; ' '; uBytes
0x180044b4e  lea     ecx, [rdx+20h]; uFlags
0x180044b51  call    cs:__imp_LocalAlloc
0x180044b57  jmp     short loc_180044B71
0x180044b59  call    cs:__imp_GetProcessHeap
0x180044b5f  mov     edx, 8; dwFlags
0x180044b64  mov     rcx, rax; hHeap
0x180044b67  lea     r8d, [rdx+18h]; dwBytes
0x180044b6b  call    cs:__imp_HeapAlloc
0x180044b71  mov     rsi, rax
0x180044b74  test    rax, rax
0x180044b77  jz      loc_180044D9D
0x180044b7d  mov     r9, rax; struct _MPRI_TRANSPORT_INFO_1 *
0x180044b80  mov     r8d, 1; int
0x180044b86  mov     edx, r12d; int
0x180044b89  mov     rcx, r14; this
0x180044b8c  call    ?CopyTransportInfo@RRasRoutingDomainConfig@@AEAAKHHPEAU_MPRI_TRANSPORT_INFO_1@@@Z; RRasRoutingDomainConfig::CopyTransportInfo(int,int,_MPRI_TRANSPORT_INFO_1 *)
0x180044b91  xor     r10d, r10d
0x180044b94  mov     ebx, eax
0x180044b96  test    eax, eax
0x180044b98  jz      loc_180044C27
0x180044b9e  cmp     qword ptr cs:xmmword_180078C60, r10
0x180044ba5  jz      short loc_180044C19
0x180044ba7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180044bae  mov     r9d, eax
0x180044bb1  mov     word ptr [rbp+7C0h+var_840], r10w
0x180044bb6  lea     r8, aRrasroutingdom_38; "RRasRoutingDomainConfig::CopyConfigEx1D"...
0x180044bbd  mov     word ptr [rsp+8C0h+var_868], r10w
0x180044bc3  lea     rdx, aSCopytransport_0; "%s: CopyTransportInfo failed for IPv4: "...
0x180044bca  lea     rcx, [rbp+7C0h+var_840]
0x180044bce  movdqu  [rsp+8C0h+var_878], xmm0
0x180044bd4  call    FormatRRASErrorString
0x180044bd9  mov     rdx, qword ptr cs:xmmword_180078C60
0x180044be0  lea     rax, [rsp+8C0h+var_868]
0x180044be5  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044bec  lea     r9, [rsp+8C0h+var_878]
0x180044bf1  mov     [rsp+8C0h+var_898], rax
0x180044bf6  lea     r8, [rbp+7C0h+var_840]
0x180044bfa  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180044c01  test    r15, r15
0x180044c04  mov     [rsp+8C0h+var_8A0], 0
0x180044c0d  cmovnz  r9, r15
0x180044c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c16  xor     r10d, r10d
0x180044c19  cmp     ebx, 2
0x180044c1c  jnz     loc_180044D68
0x180044c22  mov     r15d, r10d
0x180044c25  jmp     short loc_180044C2D
0x180044c27  mov     r15d, 1
0x180044c2d  mov     r9d, r15d
0x180044c30  xor     r8d, r8d; int
0x180044c33  shl     r9, 4
0x180044c37  mov     edx, r12d; int
0x180044c3a  add     r9, rsi; struct _MPRI_TRANSPORT_INFO_1 *
0x180044c3d  mov     rcx, r14; this
0x180044c40  call    ?CopyTransportInfo@RRasRoutingDomainConfig@@AEAAKHHPEAU_MPRI_TRANSPORT_INFO_1@@@Z; RRasRoutingDomainConfig::CopyTransportInfo(int,int,_MPRI_TRANSPORT_INFO_1 *)
0x180044c45  xor     r10d, r10d
0x180044c48  mov     ebx, eax
0x180044c4a  test    eax, eax
0x180044c4c  jz      loc_180044CD6
0x180044c52  cmp     qword ptr cs:xmmword_180078C60, r10
0x180044c59  jz      short loc_180044CD9
0x180044c5b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180044c62  mov     r9d, eax
0x180044c65  mov     word ptr [rbp+7C0h+var_840], r10w
0x180044c6a  lea     r8, aRrasroutingdom_38; "RRasRoutingDomainConfig::CopyConfigEx1D"...
0x180044c71  mov     word ptr [rsp+8C0h+var_868], r10w
0x180044c77  lea     rdx, aSCopytransport; "%s: CopyTransportInfo failed for IPv6: "...
0x180044c7e  lea     rcx, [rbp+7C0h+var_840]
0x180044c82  movdqu  [rsp+8C0h+var_878], xmm0
0x180044c88  call    FormatRRASErrorString
0x180044c8d  mov     rdx, qword ptr cs:xmmword_180078C60
0x180044c94  lea     rax, [r14+204h]
0x180044c9b  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044ca2  lea     r9, [rsp+8C0h+var_878]
0x180044ca7  test    rax, rax
0x180044caa  lea     r8, [rbp+7C0h+var_840]
0x180044cae  cmovnz  r9, rax
0x180044cb2  lea     rax, [rsp+8C0h+var_868]
0x180044cb7  mov     [rsp+8C0h+var_898], rax
0x180044cbc  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180044cc3  mov     [rsp+8C0h+var_8A0], 0
0x180044ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044cd1  xor     r10d, r10d
0x180044cd4  jmp     short loc_180044CD9
0x180044cd6  inc     r15d
0x180044cd9  test    r15d, r15d
0x180044cdc  jz      short loc_180044CEF
0x180044cde  mov     [rdi+328h], rsi
0x180044ce5  mov     rsi, r10
0x180044ce8  mov     [rdi+320h], r15d
0x180044cef  lea     r15, [r14+204h]
0x180044cf6  lea     r11, qword_18006EAD0
0x180044cfd  mov     edx, r13d
0x180044d00  test    ebx, ebx
0x180044d02  jnz     short loc_180044D68
0x180044d04  mov     eax, [r11+rdx*4]
0x180044d08  mov     rcx, rsi
0x180044d0b  or      [rdi+284h], eax
0x180044d11  mov     eax, ebx
0x180044d13  jmp     short loc_180044D7F
0x180044d15  lea     rdx, [rdi+2B0h]; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x180044d1c  mov     rcx, r14; this
0x180044d1f  call    ?CopyIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z; RRasRoutingDomainConfig::CopyIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)
0x180044d24  jmp     loc_180044AB9
0x180044d29  test    ebx, ebx
0x180044d2b  jnz     short loc_180044D68
0x180044d2d  mov     [rdi+330h], r10d
0x180044d34  mov     [rdi+338h], r10
0x180044d3b  jmp     short loc_180044D04
0x180044d3d  lea     rdx, [rdi+298h]; struct _MPRI_IPV6_CONFIG_1 *
0x180044d44  mov     rcx, r14; this
0x180044d47  call    ?CopyIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV6_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyIpv6AddrPool(_MPRI_IPV6_CONFIG_1 *)
0x180044d4c  jmp     loc_180044AB9
0x180044d51  lea     r8, [rdi+288h]; struct _MPRI_IPV4_CONFIG_1 *
0x180044d58  mov     edx, r12d; int
0x180044d5b  mov     rcx, r14; this
0x180044d5e  call    ?CopyIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyIpv4AddrPool(int,_MPRI_IPV4_CONFIG_1 *)
0x180044d63  jmp     loc_180044AB9
0x180044d68  mov     rcx, rsi
0x180044d6b  mov     eax, ebx
0x180044d6d  cmp     ebx, 2
0x180044d70  jz      loc_180044A5A
0x180044d76  cmp     ebx, 32h ; '2'
0x180044d79  jz      loc_180044A5A
0x180044d7f  cmp     ebx, 490h
0x180044d85  jz      loc_180044A5A
0x180044d8b  mov     ebx, eax
0x180044d8d  mov     rsi, rcx
0x180044d90  test    eax, eax
0x180044d92  jnz     loc_180044A6E
0x180044d98  jmp     loc_180044A5D
0x180044d9d  cmp     qword ptr cs:xmmword_180078C60, 0
0x180044da5  jz      short loc_180044E13
0x180044da7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180044dae  xor     eax, eax
0x180044db0  lea     r8, aRrasroutingdom_38; "RRasRoutingDomainConfig::CopyConfigEx1D"...
0x180044db7  lea     rdx, aSGetconfigMall; "%s: GetConfig: Malloc failed."
0x180044dbe  mov     word ptr [rbp+7C0h+var_840], ax
0x180044dc2  lea     rcx, [rbp+7C0h+var_840]
0x180044dc6  mov     word ptr [rsp+8C0h+var_868], ax
0x180044dcb  movdqu  [rsp+8C0h+var_878], xmm0
0x180044dd1  call    FormatRRASErrorString
0x180044dd6  mov     rdx, qword ptr cs:xmmword_180078C60
  ... truncated ...
```
