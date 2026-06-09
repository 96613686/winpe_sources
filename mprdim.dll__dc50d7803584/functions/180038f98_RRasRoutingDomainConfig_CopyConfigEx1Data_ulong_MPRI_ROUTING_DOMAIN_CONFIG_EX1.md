# RRasRoutingDomainConfig::CopyConfigEx1Data(ulong,_MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)

- ea: `0x180038f98`
- end: `0x1800394d3`
- name: `?CopyConfigEx1Data@RRasRoutingDomainConfig@@AEAAKKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX1@@@Z`
- size: `1339`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18003c608`

## callees

- `0x18002223c`
- `0x1800351f0`
- `0x180038f1c`
- `0x180038f98`
- `0x1800394dc`
- `0x180039b4c`
- `0x180039cd8`
- `0x180039f2c`
- `0x18003a284`
- `0x180043fbc`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800391be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800391be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039495`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039495`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800391a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800391a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800393ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800393ff`
- `KERNEL32!GetProcessHeap` at `0x1800391ac`
- `KERNEL32!GetProcessHeap` at `0x180039487`
- `KERNEL32!GetProcessHeap` at `0x1800391ac`
- `KERNEL32!GetProcessHeap` at `0x180039487`

## string_xrefs

- `0x1800390d6`: `RRasRoutingDomainConfig::CopyConfigEx1Data`
- `0x180039201`: `RRasRoutingDomainConfig::CopyConfigEx1Data`
- `0x1800392b0`: `RRasRoutingDomainConfig::CopyConfigEx1Data`
- `0x18003941d`: `RRasRoutingDomainConfig::CopyConfigEx1Data`
- `0x180039424`: `%s: GetConfig: Malloc failed.`
- `0x18003920f`: `%s: CopyTransportInfo failed for IPv4: %d.`
- `0x1800392be`: `%s: CopyTransportInfo failed for IPv6: %d.`
- `0x1800390dd`: `%s: Un-supported config type '%d'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::CopyConfigEx1Data(
        RRasRoutingDomainConfig *this,
        int a2,
        struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *a3)
{
  unsigned int v5; // r12d
  unsigned int v6; // ebx
  struct _MPRI_TRANSPORT_INFO_1 *v7; // rsi
  const struct _GUID *v8; // r14
  __int64 i; // r13
  __int64 v10; // rdx
  int v11; // r9d
  const struct _GUID *v12; // r9
  unsigned int v13; // eax
  struct _MPRI_TRANSPORT_INFO_1 *v14; // rax
  HANDLE ProcessHeap; // rax
  const struct _GUID *v16; // r9
  unsigned int v17; // r14d
  GUID *v18; // r9
  struct _MPRI_TRANSPORT_INFO_1 *v19; // rcx
  unsigned int v20; // eax
  const struct _GUID *v21; // r9
  HANDLE v22; // rax
  GUID v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v27; // [rsp+5Ch] [rbp-A4h]
  __int128 v28; // [rsp+6Ch] [rbp-94h]
  int v29; // [rsp+7Ch] [rbp-84h]
  int v30; // [rsp+80h] [rbp-80h] BYREF
  char v31[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v30 = 0;
  v5 = a2 & 0x80000000;
  v6 = 0;
  v7 = 0;
  memset_0(v31, 0, sizeof(v31));
  v8 = (const struct _GUID *)((char *)this + 516);
  v26 = 0;
  v27 = 0;
  v29 = 0;
  v28 = 0;
  *(_OWORD *)((char *)a3 + 516) = *(_OWORD *)((char *)this + 516);
  *((_DWORD *)a3 + 160) = *((_DWORD *)this + 133);
  StringCchCopyW((STRSAFE_LPWSTR)a3, 0x101u, (STRSAFE_LPCWSTR)this);
  for ( i = 0; (unsigned int)i < 0xC; i = (unsigned int)(i + 1) )
  {
    v10 = (unsigned int)i;
    v11 = *((_DWORD *)qword_180066550 + i);
    if ( (v11 & a2) == 0 )
      continue;
    if ( v11 == 1 )
    {
      v13 = RRasRoutingDomainConfig::CopyIpv4AddrPool(
              this,
              v5,
              (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a3 + 648));
LABEL_21:
      v6 = v13;
      goto LABEL_45;
    }
    if ( v11 == 2 )
    {
      v13 = RRasRoutingDomainConfig::CopyIpv6AddrPool(
              this,
              (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a3 + 664));
      goto LABEL_21;
    }
    if ( v11 != 4 )
    {
      switch ( v11 )
      {
        case 8:
          v13 = RRasRoutingDomainConfig::CopyIkev2Config(
                  this,
                  (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a3 + 688));
          goto LABEL_21;
        case 0x10:
          if ( v5 )
          {
            v14 = (struct _MPRI_TRANSPORT_INFO_1 *)LocalAlloc(0x40u, 0x20u);
          }
          else
          {
            ProcessHeap = GetProcessHeap();
            v14 = (struct _MPRI_TRANSPORT_INFO_1 *)HeapAlloc(ProcessHeap, 8u, 0x20u);
          }
          v7 = v14;
          if ( !v14 )
          {
            if ( (_QWORD)xmmword_1800710A0 )
            {
              LOWORD(v30) = 0;
              LOWORD(v26) = 0;
              v25 = GUID_NULL;
              FormatRRASErrorString(
                &v30,
                L"%s: GetConfig: Malloc failed.",
                L"RRasRoutingDomainConfig::CopyConfigEx1Data");
              v21 = &v25;
              if ( v8 )
                v21 = v8;
              gCfgStoreParamTemplateFunc(
                gCfgStoreEtwContext,
                (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
                (const unsigned __int16 *)&v30,
                v21,
                0,
                (const unsigned __int16 *)&v26);
            }
            v6 = 8;
            goto LABEL_67;
          }
          v6 = RRasRoutingDomainConfig::CopyTransportInfo(this, v5, 1, v14);
          if ( v6 )
          {
            if ( (_QWORD)xmmword_1800710A0 )
            {
              LOWORD(v30) = 0;
              LOWORD(v26) = 0;
              v25 = GUID_NULL;
              FormatRRASErrorString(
                &v30,
                L"%s: CopyTransportInfo failed for IPv4: %d.",
                L"RRasRoutingDomainConfig::CopyConfigEx1Data",
                v6);
              v16 = &v25;
              if ( v8 )
                v16 = v8;
              gCfgStoreParamTemplateFunc(
                gCfgStoreEtwContext,
                (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
                (const unsigned __int16 *)&v30,
                v16,
                0,
                (const unsigned __int16 *)&v26);
            }
            if ( v6 != 2 )
              goto LABEL_53;
            v17 = 0;
          }
          else
          {
            v17 = 1;
          }
          v6 = RRasRoutingDomainConfig::CopyTransportInfo(
                 this,
                 v5,
                 0,
                 (struct _MPRI_TRANSPORT_INFO_1 *)((char *)v7 + 16 * v17));
          if ( v6 )
          {
            if ( (_QWORD)xmmword_1800710A0 )
            {
              LOWORD(v30) = 0;
              LOWORD(v26) = 0;
              v25 = GUID_NULL;
              FormatRRASErrorString(
                &v30,
                L"%s: CopyTransportInfo failed for IPv6: %d.",
                L"RRasRoutingDomainConfig::CopyConfigEx1Data",
                v6);
              v18 = &v25;
              if ( this != (RRasRoutingDomainConfig *)-516LL )
                v18 = (GUID *)((char *)this + 516);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                gCfgStoreEtwContext,
                xmmword_1800710A0,
                &v30,
                v18,
                0,
                &v26);
            }
          }
          else
          {
            ++v17;
          }
          if ( v17 )
          {
            *((_QWORD *)a3 + 101) = v7;
            v7 = 0;
            *((_DWORD *)a3 + 200) = v17;
          }
          v8 = (const struct _GUID *)((char *)this + 516);
          break;
        case 0x800:
          v13 = RRasRoutingDomainConfig::CopyAccoountingConfig(
                  this,
                  (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a3 + 792));
          goto LABEL_21;
        case 0x2000:
          CopyValidQoSPoliciesToUserBuffer((char *)a3 + 832, (char *)this + 544);
          break;
        case 0x4000:
          v13 = RRasRoutingDomainConfig::CopyDialInConfig(
                  this,
                  v5,
                  (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a3 + 536));
          goto LABEL_21;
        case 0x8000:
          *((_DWORD *)a3 + 133) = *((_DWORD *)this + 134);
LABEL_46:
          if ( !v6 )
            goto LABEL_47;
          goto LABEL_53;
        default:
          if ( (_QWORD)xmmword_1800710A0 )
          {
            LOWORD(v30) = 0;
            LOWORD(v26) = 0;
            v25 = GUID_NULL;
            FormatRRASErrorString(
              &v30,
              L"%s: Un-supported config type '%d'.",
              L"RRasRoutingDomainConfig::CopyConfigEx1Data");
            v12 = &v25;
            if ( v8 )
              v12 = v8;
            gCfgStoreParamTemplateFunc(
              gCfgStoreEtwContext,
              (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
              (const unsigned __int16 *)&v30,
              v12,
              0,
              (const unsigned __int16 *)&v26);
          }
LABEL_17:
          v6 = 0;
          continue;
      }
LABEL_45:
      v10 = (unsigned int)i;
      goto LABEL_46;
    }
    if ( !v6 )
    {
      *((_DWORD *)a3 + 204) = 0;
      *((_QWORD *)a3 + 103) = 0;
LABEL_47:
      v19 = v7;
      *((_DWORD *)a3 + 161) |= *((_DWORD *)qword_180066550 + v10);
      v20 = v6;
      goto LABEL_55;
    }
LABEL_53:
    v19 = v7;
    v20 = v6;
    if ( v6 == 2 || v6 == 50 )
      goto LABEL_17;
LABEL_55:
    if ( v6 == 1168 )
      goto LABEL_17;
    v6 = v20;
    v7 = v19;
    if ( v20 )
      break;
  }
  *((_DWORD *)a3 + 161) &= ~4u;
  if ( v7 )
  {
    if ( v5 )
    {
      LocalFree(v7);
    }
    else
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v7);
    }
  }
  if ( v6 )
LABEL_67:
    FreeMpriRoutingDomainConfigEx1Object(a3);
  return v6;
}

```

## disassembly

```asm
0x180038f98  mov     [rsp-8+arg_18], rbx
0x180038f9d  push    rbp
0x180038f9e  push    rsi
0x180038f9f  push    rdi
0x180038fa0  push    r12
0x180038fa2  push    r13
0x180038fa4  push    r14
0x180038fa6  push    r15
0x180038fa8  lea     rbp, [rsp-790h]
0x180038fb0  sub     rsp, 890h
0x180038fb7  mov     rax, cs:__security_cookie
0x180038fbe  xor     rax, rsp
0x180038fc1  mov     [rbp+7C0h+var_40], rax
0x180038fc8  mov     r12d, edx
0x180038fcb  mov     [rsp+8C0h+var_880], edx
0x180038fcf  mov     rdi, r8
0x180038fd2  mov     r15, rcx
0x180038fd5  xor     eax, eax
0x180038fd7  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180038fdb  xor     edx, edx; Val
0x180038fdd  mov     [rbp+7C0h+var_840], eax
0x180038fe0  mov     r8d, 7FCh; Size
0x180038fe6  and     r12d, 80000000h
0x180038fed  xor     ebx, ebx
0x180038fef  xor     esi, esi
0x180038ff1  call    memset_0
0x180038ff6  xor     eax, eax
0x180038ff8  lea     r14, [r15+204h]
0x180038fff  xorps   xmm0, xmm0
0x180039002  mov     [rsp+8C0h+var_868], eax
0x180039006  movups  [rsp+8C0h+var_864], xmm0
0x18003900b  mov     [rsp+8C0h+var_844], eax
0x18003900f  mov     r8, r15; pszSrc
0x180039012  movups  [rsp+8C0h+var_854], xmm0
0x180039017  mov     edx, 101h; cchDest
0x18003901c  mov     rcx, rdi; pszDest
0x18003901f  movups  xmm0, xmmword ptr [r14]
0x180039023  movdqu  xmmword ptr [rdi+204h], xmm0
0x18003902b  mov     eax, [r15+214h]
0x180039032  mov     [rdi+280h], eax
0x180039038  call    StringCchCopyW
0x18003903d  xor     r13d, r13d
0x180039040  cmp     r13d, 0Ch
0x180039044  jnb     loc_1800393E3
0x18003904a  lea     r8, qword_180066550
0x180039051  mov     edx, r13d
0x180039054  mov     r9d, [r8+r13*4]
0x180039058  test    [rsp+8C0h+var_880], r9d
0x18003905d  jz      loc_18003913B
0x180039063  mov     ecx, r9d
0x180039066  sub     ecx, 1
0x180039069  jz      loc_18003939C
0x18003906f  sub     ecx, 1
0x180039072  jz      loc_180039388
0x180039078  sub     ecx, 2
0x18003907b  jz      loc_180039371
0x180039081  sub     ecx, 4
0x180039084  jz      loc_18003935D
0x18003908a  sub     ecx, 8
0x18003908d  jz      loc_180039197
0x180039093  sub     ecx, 7F0h
0x180039099  jz      loc_180039186
0x18003909f  sub     ecx, 1800h
0x1800390a5  jz      loc_18003916E
0x1800390ab  sub     ecx, 2000h
0x1800390b1  jz      loc_180039155
0x1800390b7  cmp     ecx, 4000h
0x1800390bd  jz      loc_180039143
0x1800390c3  cmp     qword ptr cs:xmmword_1800710A0, 0
0x1800390cb  jz      short loc_180039139
0x1800390cd  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800390d4  xor     eax, eax
0x1800390d6  lea     r8, aRrasroutingdom_39; "RRasRoutingDomainConfig::CopyConfigEx1D"...
0x1800390dd  lea     rdx, aSUnSupportedCo; "%s: Un-supported config type '%d'."
0x1800390e4  mov     word ptr [rbp+7C0h+var_840], ax
0x1800390e8  lea     rcx, [rbp+7C0h+var_840]
0x1800390ec  mov     word ptr [rsp+8C0h+var_868], ax
0x1800390f1  movdqu  [rsp+8C0h+var_878], xmm0
0x1800390f7  call    FormatRRASErrorString
0x1800390fc  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180039103  lea     rax, [rsp+8C0h+var_868]
0x180039108  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003910f  lea     r9, [rsp+8C0h+var_878]
0x180039114  mov     [rsp+8C0h+var_898], rax
0x180039119  lea     r8, [rbp+7C0h+var_840]
0x18003911d  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180039124  test    r14, r14
0x180039127  mov     [rsp+8C0h+var_8A0], 0
0x180039130  cmovnz  r9, r14
0x180039134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039139  xor     ebx, ebx
0x18003913b  inc     r13d
0x18003913e  jmp     loc_180039040
0x180039143  mov     eax, [r15+218h]
0x18003914a  mov     [rdi+214h], eax
0x180039150  jmp     loc_180039348
0x180039155  lea     r8, [rdi+218h]; struct _MPRI_DIAL_IN_CONFIG_1 *
0x18003915c  mov     edx, r12d; int
0x18003915f  mov     rcx, r15; this
0x180039162  call    ?CopyDialInConfig@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_DIAL_IN_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyDialInConfig(int,_MPRI_DIAL_IN_CONFIG_1 *)
0x180039167  mov     ebx, eax
0x180039169  jmp     loc_18003933E
0x18003916e  lea     rdx, [r15+220h]
0x180039175  lea     rcx, [rdi+340h]
0x18003917c  call    CopyValidQoSPoliciesToUserBuffer
0x180039181  jmp     loc_18003933E
0x180039186  lea     rdx, [rdi+318h]; struct _MPRI_ACCOUNTING_CONFIG_1 *
0x18003918d  mov     rcx, r15; this
0x180039190  call    ?CopyAccoountingConfig@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_ACCOUNTING_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyAccoountingConfig(_MPRI_ACCOUNTING_CONFIG_1 *)
0x180039195  jmp     short loc_180039167
0x180039197  test    r12d, r12d
0x18003919a  jz      short loc_1800391AC
0x18003919c  mov     edx, 20h ; ' '; uBytes
0x1800391a1  lea     ecx, [rdx+20h]; uFlags
0x1800391a4  call    cs:__imp_LocalAlloc
0x1800391aa  jmp     short loc_1800391C4
0x1800391ac  call    cs:__imp_GetProcessHeap
0x1800391b2  mov     edx, 8; dwFlags
0x1800391b7  mov     rcx, rax; hHeap
0x1800391ba  lea     r8d, [rdx+18h]; dwBytes
0x1800391be  call    cs:__imp_HeapAlloc
0x1800391c4  mov     rsi, rax
0x1800391c7  test    rax, rax
0x1800391ca  jz      loc_18003940A
0x1800391d0  mov     r9, rax; struct _MPRI_TRANSPORT_INFO_1 *
0x1800391d3  mov     r8d, 1; int
0x1800391d9  mov     edx, r12d; int
0x1800391dc  mov     rcx, r15; this
0x1800391df  call    ?CopyTransportInfo@RRasRoutingDomainConfig@@AEAAKHHPEAU_MPRI_TRANSPORT_INFO_1@@@Z; RRasRoutingDomainConfig::CopyTransportInfo(int,int,_MPRI_TRANSPORT_INFO_1 *)
0x1800391e4  mov     ebx, eax
0x1800391e6  test    eax, eax
0x1800391e8  jz      loc_180039275
0x1800391ee  cmp     qword ptr cs:xmmword_1800710A0, 0
0x1800391f6  jz      short loc_180039267
0x1800391f8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800391ff  xor     eax, eax
0x180039201  lea     r8, aRrasroutingdom_39; "RRasRoutingDomainConfig::CopyConfigEx1D"...
0x180039208  mov     r9d, ebx
0x18003920b  mov     word ptr [rbp+7C0h+var_840], ax
0x18003920f  lea     rdx, aSCopytransport_0; "%s: CopyTransportInfo failed for IPv4: "...
0x180039216  mov     word ptr [rsp+8C0h+var_868], ax
0x18003921b  lea     rcx, [rbp+7C0h+var_840]
0x18003921f  movdqu  [rsp+8C0h+var_878], xmm0
0x180039225  call    FormatRRASErrorString
0x18003922a  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180039231  lea     rax, [rsp+8C0h+var_868]
0x180039236  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003923d  lea     r9, [rsp+8C0h+var_878]
0x180039242  mov     [rsp+8C0h+var_898], rax
0x180039247  lea     r8, [rbp+7C0h+var_840]
0x18003924b  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180039252  test    r14, r14
0x180039255  mov     [rsp+8C0h+var_8A0], 0
0x18003925e  cmovnz  r9, r14
0x180039262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039267  cmp     ebx, 2
0x18003926a  jnz     loc_1800393B3
0x180039270  xor     r14d, r14d
0x180039273  jmp     short loc_18003927B
0x180039275  mov     r14d, 1
0x18003927b  mov     r9d, r14d
0x18003927e  xor     r8d, r8d; int
0x180039281  shl     r9, 4
0x180039285  mov     edx, r12d; int
0x180039288  add     r9, rsi; struct _MPRI_TRANSPORT_INFO_1 *
0x18003928b  mov     rcx, r15; this
0x18003928e  call    ?CopyTransportInfo@RRasRoutingDomainConfig@@AEAAKHHPEAU_MPRI_TRANSPORT_INFO_1@@@Z; RRasRoutingDomainConfig::CopyTransportInfo(int,int,_MPRI_TRANSPORT_INFO_1 *)
0x180039293  mov     ebx, eax
0x180039295  test    eax, eax
0x180039297  jz      loc_18003931F
0x18003929d  cmp     qword ptr cs:xmmword_1800710A0, 0
0x1800392a5  jz      short loc_180039322
0x1800392a7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800392ae  xor     eax, eax
0x1800392b0  lea     r8, aRrasroutingdom_39; "RRasRoutingDomainConfig::CopyConfigEx1D"...
0x1800392b7  mov     r9d, ebx
0x1800392ba  mov     word ptr [rbp+7C0h+var_840], ax
0x1800392be  lea     rdx, aSCopytransport; "%s: CopyTransportInfo failed for IPv6: "...
0x1800392c5  mov     word ptr [rsp+8C0h+var_868], ax
0x1800392ca  lea     rcx, [rbp+7C0h+var_840]
0x1800392ce  movdqu  [rsp+8C0h+var_878], xmm0
0x1800392d4  call    FormatRRASErrorString
0x1800392d9  mov     rdx, qword ptr cs:xmmword_1800710A0
0x1800392e0  lea     rax, [r15+204h]
0x1800392e7  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800392ee  lea     r9, [rsp+8C0h+var_878]
0x1800392f3  test    rax, rax
0x1800392f6  lea     r8, [rbp+7C0h+var_840]
0x1800392fa  cmovnz  r9, rax
0x1800392fe  lea     rax, [rsp+8C0h+var_868]
0x180039303  mov     [rsp+8C0h+var_898], rax
0x180039308  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003930f  mov     [rsp+8C0h+var_8A0], 0
0x180039318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003931d  jmp     short loc_180039322
0x18003931f  inc     r14d
0x180039322  test    r14d, r14d
0x180039325  jz      short loc_180039337
0x180039327  mov     [rdi+328h], rsi
0x18003932e  xor     esi, esi
0x180039330  mov     [rdi+320h], r14d
0x180039337  lea     r14, [r15+204h]
0x18003933e  lea     r8, qword_180066550
0x180039345  mov     edx, r13d
0x180039348  test    ebx, ebx
0x18003934a  jnz     short loc_1800393B3
0x18003934c  mov     eax, [r8+rdx*4]
0x180039350  mov     rcx, rsi
0x180039353  or      [rdi+284h], eax
0x180039359  mov     eax, ebx
0x18003935b  jmp     short loc_1800393CA
0x18003935d  lea     rdx, [rdi+2B0h]; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x180039364  mov     rcx, r15; this
0x180039367  call    ?CopyIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z; RRasRoutingDomainConfig::CopyIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)
0x18003936c  jmp     loc_180039167
0x180039371  test    ebx, ebx
0x180039373  jnz     short loc_1800393B3
0x180039375  mov     [rdi+330h], ebx
0x18003937b  mov     qword ptr [rdi+338h], 0
0x180039386  jmp     short loc_18003934C
0x180039388  lea     rdx, [rdi+298h]; struct _MPRI_IPV6_CONFIG_1 *
0x18003938f  mov     rcx, r15; this
0x180039392  call    ?CopyIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV6_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyIpv6AddrPool(_MPRI_IPV6_CONFIG_1 *)
0x180039397  jmp     loc_180039167
0x18003939c  lea     r8, [rdi+288h]; struct _MPRI_IPV4_CONFIG_1 *
0x1800393a3  mov     edx, r12d; int
0x1800393a6  mov     rcx, r15; this
0x1800393a9  call    ?CopyIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyIpv4AddrPool(int,_MPRI_IPV4_CONFIG_1 *)
0x1800393ae  jmp     loc_180039167
0x1800393b3  mov     rcx, rsi
0x1800393b6  mov     eax, ebx
0x1800393b8  cmp     ebx, 2
0x1800393bb  jz      loc_180039139
0x1800393c1  cmp     ebx, 32h ; '2'
0x1800393c4  jz      loc_180039139
0x1800393ca  cmp     ebx, 490h
0x1800393d0  jz      loc_180039139
0x1800393d6  mov     ebx, eax
0x1800393d8  mov     rsi, rcx
0x1800393db  test    eax, eax
0x1800393dd  jz      loc_18003913B
0x1800393e3  and     dword ptr [rdi+284h], 0FFFFFFFBh
0x1800393ea  test    rsi, rsi
0x1800393ed  jz      loc_18003949B
0x1800393f3  test    r12d, r12d
0x1800393f6  jz      loc_180039487
0x1800393fc  mov     rcx, rsi; hMem
0x1800393ff  call    cs:__imp_LocalFree
0x180039405  jmp     loc_18003949B
0x18003940a  cmp     qword ptr cs:xmmword_1800710A0, 0
0x180039412  jz      short loc_180039480
0x180039414  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003941b  xor     eax, eax
0x18003941d  lea     r8, aRrasroutingdom_39; "RRasRoutingDomainConfig::CopyConfigEx1D"...
0x180039424  lea     rdx, aSGetconfigMall; "%s: GetConfig: Malloc failed."
0x18003942b  mov     word ptr [rbp+7C0h+var_840], ax
0x18003942f  lea     rcx, [rbp+7C0h+var_840]
0x180039433  mov     word ptr [rsp+8C0h+var_868], ax
0x180039438  movdqu  [rsp+8C0h+var_878], xmm0
0x18003943e  call    FormatRRASErrorString
0x180039443  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003944a  lea     rax, [rsp+8C0h+var_868]
0x18003944f  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180039456  lea     r9, [rsp+8C0h+var_878]
0x18003945b  mov     [rsp+8C0h+var_898], rax
0x180039460  lea     r8, [rbp+7C0h+var_840]
0x180039464  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003946b  test    r14, r14
0x18003946e  mov     [rsp+8C0h+var_8A0], 0
0x180039477  cmovnz  r9, r14
0x18003947b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039480  mov     ebx, 8
0x180039485  jmp     short loc_18003949F
0x180039487  call    cs:__imp_GetProcessHeap
0x18003948d  mov     r8, rsi; lpMem
0x180039490  xor     edx, edx; dwFlags
0x180039492  mov     rcx, rax; hHeap
0x180039495  call    cs:__imp_HeapFree
0x18003949b  test    ebx, ebx
0x18003949d  jz      short loc_1800394A7
0x18003949f  mov     rcx, rdi
0x1800394a2  call    FreeMpriRoutingDomainConfigEx1Object
0x1800394a7  mov     eax, ebx
0x1800394a9  mov     rcx, [rbp+7C0h+var_40]
0x1800394b0  xor     rcx, rsp; StackCookie
0x1800394b3  call    __security_check_cookie
0x1800394b8  mov     rbx, [rsp+8C0h+arg_18]
0x1800394c0  add     rsp, 890h
0x1800394c7  pop     r15
0x1800394c9  pop     r14
0x1800394cb  pop     r13
0x1800394cd  pop     r12
0x1800394cf  pop     rdi
0x1800394d0  pop     rsi
0x1800394d1  pop     rbp
0x1800394d2  retn
```
