# RRasRoutingDomainConfig::UpdateDialInConfig(_MPRI_DIAL_IN_CONFIG_1 *)

- ea: `0x1800427d0`
- end: `0x180042af9`
- name: `?UpdateDialInConfig@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_DIAL_IN_CONFIG_1@@@Z`
- size: `809`
- prototype: `unsigned int __fastcall(RRasRoutingDomainConfig *__hidden this, struct _MPRI_DIAL_IN_CONFIG_1 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x1800416fc`
- `0x180042398`

## callees

- `0x180039794`
- `0x180039970`
- `0x18003a0a8`
- `0x1800427d0`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x1800428e6`: `%s: CopyIPv4AddressList(DHCP) failed with error %d`
- `0x180042985`: `%s: CopyIPv6AddressList(DHCP) failed with error %d`
- `0x1800429bd`: `%s: CopyIPv4AddressList(DNS) failed with error %d`
- `0x1800429f5`: `%s: CopyIPv6AddressList(DNS) failed with error %d`
- `0x180042a2d`: `%s: CopyIPv4AddressList(NetBIOS) failed with error %d`
- `0x180042a61`: `%s: CopyStringList(TenantID) failed with error %d`
- `0x180042877`: `RRasRoutingDomainConfig::UpdateDialInConfig`
- `0x1800428f4`: `RRasRoutingDomainConfig::UpdateDialInConfig`
- `0x180042a8a`: `RRasRoutingDomainConfig::UpdateDialInConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::UpdateDialInConfig(RRasRoutingDomainConfig *this, const void *const *a2)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v5; // eax
  unsigned int v6; // ebx
  const wchar_t *v7; // rdx
  GUID *v8; // r9
  unsigned __int16 *v10; // [rsp+28h] [rbp-D8h]
  unsigned int v11; // [rsp+30h] [rbp-D0h]
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v14; // [rsp+50h] [rbp-B0h]
  __int128 v15; // [rsp+60h] [rbp-A0h]
  __int64 v16; // [rsp+70h] [rbp-90h]
  int v17; // [rsp+78h] [rbp-88h]
  int v18; // [rsp+7Ch] [rbp-84h]
  GUID v19; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+90h] [rbp-70h] BYREF
  __int128 v21; // [rsp+94h] [rbp-6Ch]
  __int128 v22; // [rsp+A4h] [rbp-5Ch]
  int v23; // [rsp+B4h] [rbp-4Ch]
  int v24; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v25[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v12 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v13,
      L"RRasRoutingDomainConfig::UpdateDialInConfig",
      &v12,
      v4,
      (struct _GUID *)((char *)this + 516),
      v10,
      v11);
  if ( *(_DWORD *)a2 && *((_DWORD *)a2 + 2) <= 2u && *((_DWORD *)a2 + 14) <= 2u && *((_DWORD *)a2 + 10) <= 2u )
  {
    *((_DWORD *)this + 156) = *(_DWORD *)a2;
    v5 = RRasRoutingDomainConfig::CopyIPv4AddressList(this, 0, a2 + 3, (RRasRoutingDomainConfig *)((char *)this + 648));
    v6 = v5;
    v12 = v5;
    if ( v5 )
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        v7 = L"%s: CopyIPv4AddressList(DHCP) failed with error %d";
LABEL_10:
        LOWORD(v20) = 0;
        v19 = GUID_NULL;
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, v7, L"RRasRoutingDomainConfig::UpdateDialInConfig", v5);
        v8 = &v19;
        if ( this != (RRasRoutingDomainConfig *)-516LL )
          v8 = (GUID *)((char *)this + 516);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v24,
          v8,
          0,
          &v20);
        goto LABEL_30;
      }
    }
    else
    {
      v5 = RRasRoutingDomainConfig::CopyIPv6AddressList(
             this,
             0,
             a2 + 9,
             (RRasRoutingDomainConfig *)((char *)this + 696));
      v6 = v5;
      v12 = v5;
      if ( v5 )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          v7 = L"%s: CopyIPv6AddressList(DHCP) failed with error %d";
          goto LABEL_10;
        }
      }
      else
      {
        v5 = RRasRoutingDomainConfig::CopyIPv4AddressList(
               this,
               0,
               a2 + 1,
               (RRasRoutingDomainConfig *)((char *)this + 632));
        v6 = v5;
        v12 = v5;
        if ( v5 )
        {
          if ( (_QWORD)xmmword_1800710A0 )
          {
            v7 = L"%s: CopyIPv4AddressList(DNS) failed with error %d";
            goto LABEL_10;
          }
        }
        else
        {
          v5 = RRasRoutingDomainConfig::CopyIPv6AddressList(
                 this,
                 0,
                 a2 + 7,
                 (RRasRoutingDomainConfig *)((char *)this + 680));
          v6 = v5;
          v12 = v5;
          if ( v5 )
          {
            if ( (_QWORD)xmmword_1800710A0 )
            {
              v7 = L"%s: CopyIPv6AddressList(DNS) failed with error %d";
              goto LABEL_10;
            }
          }
          else
          {
            v5 = RRasRoutingDomainConfig::CopyIPv4AddressList(
                   this,
                   0,
                   a2 + 5,
                   (RRasRoutingDomainConfig *)((char *)this + 664));
            v6 = v5;
            v12 = v5;
            if ( v5 )
            {
              if ( (_QWORD)xmmword_1800710A0 )
              {
                v7 = L"%s: CopyIPv4AddressList(NetBIOS) failed with error %d";
                goto LABEL_10;
              }
            }
            else
            {
              v5 = RRasRoutingDomainConfig::CopyStringList(
                     this,
                     0,
                     a2 + 11,
                     (RRasRoutingDomainConfig *)((char *)this + 712));
              v6 = v5;
              v12 = v5;
              if ( v5 && (_QWORD)xmmword_1800710A0 )
              {
                v7 = L"%s: CopyStringList(TenantID) failed with error %d";
                goto LABEL_10;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v6 = 87;
    v12 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasRoutingDomainConfig::UpdateDialInConfig",
        3823);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v24);
LABEL_30:
      v6 = v12;
    }
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v6;
}

```

## disassembly

```asm
0x1800427d0  mov     [rsp-8+arg_10], rbx
0x1800427d5  push    rbp
0x1800427d6  push    rsi
0x1800427d7  push    rdi
0x1800427d8  push    r12
0x1800427da  push    r13
0x1800427dc  push    r14
0x1800427de  push    r15
0x1800427e0  lea     rbp, [rsp-7D0h]
0x1800427e8  sub     rsp, 8D0h
0x1800427ef  mov     rax, cs:__security_cookie
0x1800427f6  xor     rax, rsp
0x1800427f9  mov     [rbp+800h+var_40], rax
0x180042800  mov     rsi, rdx
0x180042803  mov     rdi, rcx
0x180042806  xor     r13d, r13d
0x180042809  mov     [rsp+900h+var_8C0], r13d
0x18004280e  mov     [rbp+800h+var_840], r13d
0x180042812  xor     edx, edx; Val
0x180042814  mov     r8d, 7FCh; Size
0x18004281a  lea     rcx, [rbp+800h+var_83C]; void *
0x18004281e  call    memset_0
0x180042823  mov     [rbp+800h+var_870], r13d
0x180042827  xorps   xmm0, xmm0
0x18004282a  xor     eax, eax
0x18004282c  movups  [rbp+800h+var_86C], xmm0
0x180042830  movups  [rbp+800h+var_85C], xmm0
0x180042834  mov     [rbp+800h+var_84C], eax
0x180042837  movdqu  [rsp+900h+var_8B0], xmm0
0x18004283d  mov     [rsp+900h+var_8B8], r13
0x180042842  xorps   xmm1, xmm1
0x180042845  movdqu  [rsp+900h+var_8A0], xmm1
0x18004284b  mov     [rsp+900h+var_890], r13
0x180042850  mov     [rsp+900h+var_888], 0FFFFFFFFh
0x180042858  mov     [rsp+900h+var_884], r13d
0x18004285d  cmp     qword ptr cs:xmmword_1800710A0+8, r13
0x180042864  jz      short loc_180042888
0x180042866  lea     rax, [rdi+204h]
0x18004286d  mov     [rsp+900h+var_8E0], rax; struct _GUID *
0x180042872  lea     r8, [rsp+900h+var_8C0]; unsigned int *
0x180042877  lea     rdx, aRrasroutingdom_43; "RRasRoutingDomainConfig::UpdateDialInCo"...
0x18004287e  lea     rcx, [rsp+900h+var_8B8]; this
0x180042883  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180042888  mov     eax, [rsi]
0x18004288a  test    eax, eax
0x18004288c  jz      loc_180042A6D
0x180042892  cmp     dword ptr [rsi+8], 2
0x180042896  ja      loc_180042A6D
0x18004289c  cmp     dword ptr [rsi+38h], 2
0x1800428a0  ja      loc_180042A6D
0x1800428a6  cmp     dword ptr [rsi+28h], 2
0x1800428aa  ja      loc_180042A6D
0x1800428b0  mov     [rdi+270h], eax
0x1800428b6  lea     r9, [rdi+288h]; struct _MPRI_IPV4_ADDRESS_LIST *
0x1800428bd  lea     r8, [rsi+18h]; struct _MPRI_IPV4_ADDRESS_LIST *
0x1800428c1  xor     edx, edx; int
0x1800428c3  mov     rcx, rdi; this
0x1800428c6  call    ?CopyIPv4AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_ADDRESS_LIST@@0@Z; RRasRoutingDomainConfig::CopyIPv4AddressList(int,_MPRI_IPV4_ADDRESS_LIST *,_MPRI_IPV4_ADDRESS_LIST *)
0x1800428cb  mov     ebx, eax
0x1800428cd  mov     [rsp+900h+var_8C0], eax
0x1800428d1  test    eax, eax
0x1800428d3  jz      loc_180042959
0x1800428d9  cmp     qword ptr cs:xmmword_1800710A0, r13
0x1800428e0  jz      loc_180042AC3
0x1800428e6  lea     rdx, aSCopyipv4addre_1; "%s: CopyIPv4AddressList(DHCP) failed wi"...
0x1800428ed  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800428f4  lea     r8, aRrasroutingdom_43; "RRasRoutingDomainConfig::UpdateDialInCo"...
0x1800428fb  mov     r9d, eax
0x1800428fe  mov     word ptr [rbp+800h+var_870], r13w
0x180042903  movdqu  [rbp+800h+var_880], xmm0
0x180042908  mov     word ptr [rbp+800h+var_840], r13w
0x18004290d  lea     rcx, [rbp+800h+var_840]
0x180042911  call    FormatRRASErrorString
0x180042916  lea     rcx, [rdi+204h]
0x18004291d  lea     r9, [rbp+800h+var_880]
0x180042921  test    rcx, rcx
0x180042924  cmovnz  r9, rcx
0x180042928  lea     rax, [rbp+800h+var_870]
0x18004292c  mov     [rsp+900h+var_8D8], rax
0x180042931  mov     [rsp+900h+var_8E0], r13
0x180042936  lea     r8, [rbp+800h+var_840]
0x18004293a  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180042941  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042948  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004294f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042954  jmp     loc_180042ABF
0x180042959  lea     r9, [rdi+2B8h]; struct _MPRI_IPV6_ADDRESS_LIST *
0x180042960  lea     r8, [rsi+48h]; struct _MPRI_IPV6_ADDRESS_LIST *
0x180042964  xor     edx, edx; int
0x180042966  mov     rcx, rdi; this
0x180042969  call    ?CopyIPv6AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV6_ADDRESS_LIST@@0@Z; RRasRoutingDomainConfig::CopyIPv6AddressList(int,_MPRI_IPV6_ADDRESS_LIST *,_MPRI_IPV6_ADDRESS_LIST *)
0x18004296e  mov     ebx, eax
0x180042970  mov     [rsp+900h+var_8C0], eax
0x180042974  test    eax, eax
0x180042976  jz      short loc_180042991
0x180042978  cmp     qword ptr cs:xmmword_1800710A0, r13
0x18004297f  jz      loc_180042AC3
0x180042985  lea     rdx, aSCopyipv6addre; "%s: CopyIPv6AddressList(DHCP) failed wi"...
0x18004298c  jmp     loc_1800428ED
0x180042991  lea     r9, [rdi+278h]; struct _MPRI_IPV4_ADDRESS_LIST *
0x180042998  lea     r8, [rsi+8]; struct _MPRI_IPV4_ADDRESS_LIST *
0x18004299c  xor     edx, edx; int
0x18004299e  mov     rcx, rdi; this
0x1800429a1  call    ?CopyIPv4AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_ADDRESS_LIST@@0@Z; RRasRoutingDomainConfig::CopyIPv4AddressList(int,_MPRI_IPV4_ADDRESS_LIST *,_MPRI_IPV4_ADDRESS_LIST *)
0x1800429a6  mov     ebx, eax
0x1800429a8  mov     [rsp+900h+var_8C0], eax
0x1800429ac  test    eax, eax
0x1800429ae  jz      short loc_1800429C9
0x1800429b0  cmp     qword ptr cs:xmmword_1800710A0, r13
0x1800429b7  jz      loc_180042AC3
0x1800429bd  lea     rdx, aSCopyipv4addre_0; "%s: CopyIPv4AddressList(DNS) failed wit"...
0x1800429c4  jmp     loc_1800428ED
0x1800429c9  lea     r9, [rdi+2A8h]; struct _MPRI_IPV6_ADDRESS_LIST *
0x1800429d0  lea     r8, [rsi+38h]; struct _MPRI_IPV6_ADDRESS_LIST *
0x1800429d4  xor     edx, edx; int
0x1800429d6  mov     rcx, rdi; this
0x1800429d9  call    ?CopyIPv6AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV6_ADDRESS_LIST@@0@Z; RRasRoutingDomainConfig::CopyIPv6AddressList(int,_MPRI_IPV6_ADDRESS_LIST *,_MPRI_IPV6_ADDRESS_LIST *)
0x1800429de  mov     ebx, eax
0x1800429e0  mov     [rsp+900h+var_8C0], eax
0x1800429e4  test    eax, eax
0x1800429e6  jz      short loc_180042A01
0x1800429e8  cmp     qword ptr cs:xmmword_1800710A0, r13
0x1800429ef  jz      loc_180042AC3
0x1800429f5  lea     rdx, aSCopyipv6addre_0; "%s: CopyIPv6AddressList(DNS) failed wit"...
0x1800429fc  jmp     loc_1800428ED
0x180042a01  lea     r9, [rdi+298h]; struct _MPRI_IPV4_ADDRESS_LIST *
0x180042a08  lea     r8, [rsi+28h]; struct _MPRI_IPV4_ADDRESS_LIST *
0x180042a0c  xor     edx, edx; int
0x180042a0e  mov     rcx, rdi; this
0x180042a11  call    ?CopyIPv4AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_ADDRESS_LIST@@0@Z; RRasRoutingDomainConfig::CopyIPv4AddressList(int,_MPRI_IPV4_ADDRESS_LIST *,_MPRI_IPV4_ADDRESS_LIST *)
0x180042a16  mov     ebx, eax
0x180042a18  mov     [rsp+900h+var_8C0], eax
0x180042a1c  test    eax, eax
0x180042a1e  jz      short loc_180042A39
0x180042a20  cmp     qword ptr cs:xmmword_1800710A0, r13
0x180042a27  jz      loc_180042AC3
0x180042a2d  lea     rdx, aSCopyipv4addre; "%s: CopyIPv4AddressList(NetBIOS) failed"...
0x180042a34  jmp     loc_1800428ED
0x180042a39  lea     r9, [rdi+2C8h]; struct _MPRI_STRING_LIST *
0x180042a40  lea     r8, [rsi+58h]; struct _MPRI_STRING_LIST *
0x180042a44  xor     edx, edx; int
0x180042a46  mov     rcx, rdi; this
0x180042a49  call    ?CopyStringList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_STRING_LIST@@0@Z; RRasRoutingDomainConfig::CopyStringList(int,_MPRI_STRING_LIST *,_MPRI_STRING_LIST *)
0x180042a4e  mov     ebx, eax
0x180042a50  mov     [rsp+900h+var_8C0], eax
0x180042a54  test    eax, eax
0x180042a56  jz      short loc_180042AC3
0x180042a58  cmp     qword ptr cs:xmmword_1800710A0, r13
0x180042a5f  jz      short loc_180042AC3
0x180042a61  lea     rdx, aSCopystringlis; "%s: CopyStringList(TenantID) failed wit"...
0x180042a68  jmp     loc_1800428ED
0x180042a6d  mov     ebx, 57h ; 'W'
0x180042a72  mov     [rsp+900h+var_8C0], ebx
0x180042a76  cmp     qword ptr cs:xmmword_180071090, r13
0x180042a7d  jz      short loc_180042AC3
0x180042a7f  mov     word ptr [rbp+800h+var_840], r13w
0x180042a84  mov     r9d, 0EEFh
0x180042a8a  lea     r8, aRrasroutingdom_44; "RRasRoutingDomainConfig::UpdateDialInCo"...
0x180042a91  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180042a98  lea     rcx, [rbp+800h+var_840]
0x180042a9c  call    FormatRRASErrorString
0x180042aa1  lea     r8, [rbp+800h+var_840]
0x180042aa5  mov     rdx, qword ptr cs:xmmword_180071090
0x180042aac  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042ab3  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180042aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042abf  mov     ebx, [rsp+900h+var_8C0]
0x180042ac3  lea     rcx, [rsp+900h+var_8B8]; this
0x180042ac8  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180042acd  mov     eax, ebx
0x180042acf  mov     rcx, [rbp+800h+var_40]
0x180042ad6  xor     rcx, rsp; StackCookie
0x180042ad9  call    __security_check_cookie
0x180042ade  mov     rbx, [rsp+900h+arg_10]
0x180042ae6  add     rsp, 8D0h
0x180042aed  pop     r15
0x180042aef  pop     r14
0x180042af1  pop     r13
0x180042af3  pop     r12
0x180042af5  pop     rdi
0x180042af6  pop     rsi
0x180042af7  pop     rbp
0x180042af8  retn
```
