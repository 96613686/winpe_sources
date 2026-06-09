# RRasRoutingDomainConfig::CopyDialInConfig(int,_MPRI_DIAL_IN_CONFIG_1 *)

- ea: `0x1800394dc`
- end: `0x18003978d`
- name: `?CopyDialInConfig@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_DIAL_IN_CONFIG_1@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, struct _MPRI_DIAL_IN_CONFIG_1 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180038f98`
- `0x18003c810`

## callees

- `0x1800394dc`
- `0x180039794`
- `0x180039970`
- `0x18003a0a8`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x180039573`: `RRasRoutingDomainConfig::CopyDialInConfig`
- `0x1800395dd`: `%s: CopyIPv4AddressList(DHCP) failed with error %d`
- `0x180039616`: `%s: CopyIPv6AddressList(DHCP) failed with error %d`
- `0x18003964f`: `%s: CopyIPv4AddressList(DNS) failed with error %d`
- `0x180039688`: `%s: CopyIPv6AddressList(DNS) failed with error %d`
- `0x1800396be`: `%s: CopyIPv4AddressList(NetBIOS) failed with error %d`
- `0x1800396f0`: `%s: CopyStringList(TenantID) failed with error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::CopyDialInConfig(
        RRasRoutingDomainConfig *this,
        int a2,
        struct _MPRI_DIAL_IN_CONFIG_1 *a3)
{
  void (*v6)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v7; // eax
  unsigned int v8; // ebx
  const wchar_t *v9; // rdx
  GUID *v10; // r9
  unsigned __int16 *v12; // [rsp+28h] [rbp-D8h]
  unsigned int v13; // [rsp+30h] [rbp-D0h]
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+50h] [rbp-B0h]
  __int128 v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+70h] [rbp-90h]
  int v19; // [rsp+78h] [rbp-88h]
  int v20; // [rsp+7Ch] [rbp-84h]
  GUID v21; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+90h] [rbp-70h] BYREF
  __int128 v23; // [rsp+94h] [rbp-6Ch]
  __int128 v24; // [rsp+A4h] [rbp-5Ch]
  int v25; // [rsp+B4h] [rbp-4Ch]
  int v26; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v27[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v14 = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v19 = -1;
  v20 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v15,
      L"RRasRoutingDomainConfig::CopyDialInConfig",
      &v14,
      v6,
      (struct _GUID *)((char *)this + 516),
      v12,
      v13);
  memset_0(a3, 0, 0x68u);
  *(_DWORD *)a3 = *((_DWORD *)this + 156);
  v7 = RRasRoutingDomainConfig::CopyIPv4AddressList(
         this,
         a2,
         (RRasRoutingDomainConfig *)((char *)this + 648),
         (struct _MPRI_DIAL_IN_CONFIG_1 *)((char *)a3 + 24));
  v8 = v7;
  v14 = v7;
  if ( v7 )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_24;
    v9 = L"%s: CopyIPv4AddressList(DHCP) failed with error %d";
  }
  else
  {
    v7 = RRasRoutingDomainConfig::CopyIPv6AddressList(
           this,
           a2,
           (RRasRoutingDomainConfig *)((char *)this + 696),
           (struct _MPRI_DIAL_IN_CONFIG_1 *)((char *)a3 + 72));
    v8 = v7;
    v14 = v7;
    if ( v7 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        goto LABEL_24;
      v9 = L"%s: CopyIPv6AddressList(DHCP) failed with error %d";
    }
    else
    {
      v7 = RRasRoutingDomainConfig::CopyIPv4AddressList(
             this,
             a2,
             (RRasRoutingDomainConfig *)((char *)this + 632),
             (struct _MPRI_DIAL_IN_CONFIG_1 *)((char *)a3 + 8));
      v8 = v7;
      v14 = v7;
      if ( v7 )
      {
        if ( !(_QWORD)xmmword_1800710A0 )
          goto LABEL_24;
        v9 = L"%s: CopyIPv4AddressList(DNS) failed with error %d";
      }
      else
      {
        v7 = RRasRoutingDomainConfig::CopyIPv6AddressList(
               this,
               a2,
               (RRasRoutingDomainConfig *)((char *)this + 680),
               (struct _MPRI_DIAL_IN_CONFIG_1 *)((char *)a3 + 56));
        v8 = v7;
        v14 = v7;
        if ( v7 )
        {
          if ( !(_QWORD)xmmword_1800710A0 )
            goto LABEL_24;
          v9 = L"%s: CopyIPv6AddressList(DNS) failed with error %d";
        }
        else
        {
          v7 = RRasRoutingDomainConfig::CopyIPv4AddressList(
                 this,
                 a2,
                 (RRasRoutingDomainConfig *)((char *)this + 664),
                 (struct _MPRI_DIAL_IN_CONFIG_1 *)((char *)a3 + 40));
          v8 = v7;
          v14 = v7;
          if ( v7 )
          {
            if ( !(_QWORD)xmmword_1800710A0 )
              goto LABEL_24;
            v9 = L"%s: CopyIPv4AddressList(NetBIOS) failed with error %d";
          }
          else
          {
            v7 = RRasRoutingDomainConfig::CopyStringList(
                   this,
                   a2,
                   (RRasRoutingDomainConfig *)((char *)this + 712),
                   (struct _MPRI_DIAL_IN_CONFIG_1 *)((char *)a3 + 88));
            v8 = v7;
            v14 = v7;
            if ( !v7 || !(_QWORD)xmmword_1800710A0 )
              goto LABEL_24;
            v9 = L"%s: CopyStringList(TenantID) failed with error %d";
          }
        }
      }
    }
  }
  LOWORD(v26) = 0;
  v21 = GUID_NULL;
  LOWORD(v22) = 0;
  FormatRRASErrorString(&v26, v9, L"RRasRoutingDomainConfig::CopyDialInConfig", v7);
  v10 = &v21;
  if ( this != (RRasRoutingDomainConfig *)-516LL )
    v10 = (GUID *)((char *)this + 516);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_1800710A0,
    &v26,
    v10,
    0,
    &v22);
  v8 = v14;
LABEL_24:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v15);
  return v8;
}

```

## disassembly

```asm
0x1800394dc  mov     [rsp-8+arg_18], rbx
0x1800394e1  push    rbp
0x1800394e2  push    rsi
0x1800394e3  push    rdi
0x1800394e4  push    r12
0x1800394e6  push    r13
0x1800394e8  push    r14
0x1800394ea  push    r15
0x1800394ec  lea     rbp, [rsp-7D0h]
0x1800394f4  sub     rsp, 8D0h
0x1800394fb  mov     rax, cs:__security_cookie
0x180039502  xor     rax, rsp
0x180039505  mov     [rbp+800h+var_40], rax
0x18003950c  mov     rsi, r8
0x18003950f  mov     r14d, edx
0x180039512  mov     rdi, rcx
0x180039515  xor     r12d, r12d
0x180039518  mov     [rsp+900h+var_8C0], r12d
0x18003951d  mov     [rbp+800h+var_840], r12d
0x180039521  xor     edx, edx; Val
0x180039523  mov     r8d, 7FCh; Size
0x180039529  lea     rcx, [rbp+800h+var_83C]; void *
0x18003952d  call    memset_0
0x180039532  mov     [rbp+800h+var_870], r12d
0x180039536  xorps   xmm0, xmm0
0x180039539  xor     eax, eax
0x18003953b  movups  [rbp+800h+var_86C], xmm0
0x18003953f  movups  [rbp+800h+var_85C], xmm0
0x180039543  mov     [rbp+800h+var_84C], eax
0x180039546  movdqu  [rsp+900h+var_8B0], xmm0
0x18003954c  mov     [rsp+900h+var_8B8], r12
0x180039551  xorps   xmm1, xmm1
0x180039554  movdqu  [rsp+900h+var_8A0], xmm1
0x18003955a  mov     [rsp+900h+var_890], r12
0x18003955f  mov     [rsp+900h+var_888], 0FFFFFFFFh
0x180039567  mov     [rsp+900h+var_884], r12d
0x18003956c  lea     r15, [rdi+204h]
0x180039573  lea     r13, aRrasroutingdom_32; "RRasRoutingDomainConfig::CopyDialInConf"...
0x18003957a  cmp     qword ptr cs:xmmword_1800710A0+8, r12
0x180039581  jz      short loc_18003959A
0x180039583  mov     [rsp+900h+var_8E0], r15; struct _GUID *
0x180039588  lea     r8, [rsp+900h+var_8C0]; unsigned int *
0x18003958d  mov     rdx, r13; unsigned __int16 *
0x180039590  lea     rcx, [rsp+900h+var_8B8]; this
0x180039595  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003959a  xor     edx, edx; Val
0x18003959c  lea     r8d, [rdx+68h]; Size
0x1800395a0  mov     rcx, rsi; void *
0x1800395a3  call    memset_0
0x1800395a8  mov     eax, [rdi+270h]
0x1800395ae  mov     [rsi], eax
0x1800395b0  lea     r9, [rsi+18h]; struct _MPRI_IPV4_ADDRESS_LIST *
0x1800395b4  lea     r8, [rdi+288h]; struct _MPRI_IPV4_ADDRESS_LIST *
0x1800395bb  mov     edx, r14d; int
0x1800395be  mov     rcx, rdi; this
0x1800395c1  call    ?CopyIPv4AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_ADDRESS_LIST@@0@Z; RRasRoutingDomainConfig::CopyIPv4AddressList(int,_MPRI_IPV4_ADDRESS_LIST *,_MPRI_IPV4_ADDRESS_LIST *)
0x1800395c6  mov     ebx, eax
0x1800395c8  mov     [rsp+900h+var_8C0], eax
0x1800395cc  test    eax, eax
0x1800395ce  jz      short loc_1800395E9
0x1800395d0  cmp     qword ptr cs:xmmword_1800710A0, r12
0x1800395d7  jz      loc_180039757
0x1800395dd  lea     rdx, aSCopyipv4addre_1; "%s: CopyIPv4AddressList(DHCP) failed wi"...
0x1800395e4  jmp     loc_1800396F7
0x1800395e9  lea     r9, [rsi+48h]; struct _MPRI_IPV6_ADDRESS_LIST *
0x1800395ed  lea     r8, [rdi+2B8h]; struct _MPRI_IPV6_ADDRESS_LIST *
0x1800395f4  mov     edx, r14d; int
0x1800395f7  mov     rcx, rdi; this
0x1800395fa  call    ?CopyIPv6AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV6_ADDRESS_LIST@@0@Z; RRasRoutingDomainConfig::CopyIPv6AddressList(int,_MPRI_IPV6_ADDRESS_LIST *,_MPRI_IPV6_ADDRESS_LIST *)
0x1800395ff  mov     ebx, eax
0x180039601  mov     [rsp+900h+var_8C0], eax
0x180039605  test    eax, eax
0x180039607  jz      short loc_180039622
0x180039609  cmp     qword ptr cs:xmmword_1800710A0, r12
0x180039610  jz      loc_180039757
0x180039616  lea     rdx, aSCopyipv6addre; "%s: CopyIPv6AddressList(DHCP) failed wi"...
0x18003961d  jmp     loc_1800396F7
0x180039622  lea     r9, [rsi+8]; struct _MPRI_IPV4_ADDRESS_LIST *
0x180039626  lea     r8, [rdi+278h]; struct _MPRI_IPV4_ADDRESS_LIST *
0x18003962d  mov     edx, r14d; int
0x180039630  mov     rcx, rdi; this
0x180039633  call    ?CopyIPv4AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_ADDRESS_LIST@@0@Z; RRasRoutingDomainConfig::CopyIPv4AddressList(int,_MPRI_IPV4_ADDRESS_LIST *,_MPRI_IPV4_ADDRESS_LIST *)
0x180039638  mov     ebx, eax
0x18003963a  mov     [rsp+900h+var_8C0], eax
0x18003963e  test    eax, eax
0x180039640  jz      short loc_18003965B
0x180039642  cmp     qword ptr cs:xmmword_1800710A0, r12
0x180039649  jz      loc_180039757
0x18003964f  lea     rdx, aSCopyipv4addre_0; "%s: CopyIPv4AddressList(DNS) failed wit"...
0x180039656  jmp     loc_1800396F7
0x18003965b  lea     r9, [rsi+38h]; struct _MPRI_IPV6_ADDRESS_LIST *
0x18003965f  lea     r8, [rdi+2A8h]; struct _MPRI_IPV6_ADDRESS_LIST *
0x180039666  mov     edx, r14d; int
0x180039669  mov     rcx, rdi; this
0x18003966c  call    ?CopyIPv6AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV6_ADDRESS_LIST@@0@Z; RRasRoutingDomainConfig::CopyIPv6AddressList(int,_MPRI_IPV6_ADDRESS_LIST *,_MPRI_IPV6_ADDRESS_LIST *)
0x180039671  mov     ebx, eax
0x180039673  mov     [rsp+900h+var_8C0], eax
0x180039677  test    eax, eax
0x180039679  jz      short loc_180039691
0x18003967b  cmp     qword ptr cs:xmmword_1800710A0, r12
0x180039682  jz      loc_180039757
0x180039688  lea     rdx, aSCopyipv6addre_0; "%s: CopyIPv6AddressList(DNS) failed wit"...
0x18003968f  jmp     short loc_1800396F7
0x180039691  lea     r9, [rsi+28h]; struct _MPRI_IPV4_ADDRESS_LIST *
0x180039695  lea     r8, [rdi+298h]; struct _MPRI_IPV4_ADDRESS_LIST *
0x18003969c  mov     edx, r14d; int
0x18003969f  mov     rcx, rdi; this
0x1800396a2  call    ?CopyIPv4AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_ADDRESS_LIST@@0@Z; RRasRoutingDomainConfig::CopyIPv4AddressList(int,_MPRI_IPV4_ADDRESS_LIST *,_MPRI_IPV4_ADDRESS_LIST *)
0x1800396a7  mov     ebx, eax
0x1800396a9  mov     [rsp+900h+var_8C0], eax
0x1800396ad  test    eax, eax
0x1800396af  jz      short loc_1800396C7
0x1800396b1  cmp     qword ptr cs:xmmword_1800710A0, r12
0x1800396b8  jz      loc_180039757
0x1800396be  lea     rdx, aSCopyipv4addre; "%s: CopyIPv4AddressList(NetBIOS) failed"...
0x1800396c5  jmp     short loc_1800396F7
0x1800396c7  lea     r9, [rsi+58h]; struct _MPRI_STRING_LIST *
0x1800396cb  lea     r8, [rdi+2C8h]; struct _MPRI_STRING_LIST *
0x1800396d2  mov     edx, r14d; int
0x1800396d5  mov     rcx, rdi; this
0x1800396d8  call    ?CopyStringList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_STRING_LIST@@0@Z; RRasRoutingDomainConfig::CopyStringList(int,_MPRI_STRING_LIST *,_MPRI_STRING_LIST *)
0x1800396dd  mov     ebx, eax
0x1800396df  mov     [rsp+900h+var_8C0], eax
0x1800396e3  test    eax, eax
0x1800396e5  jz      short loc_180039757
0x1800396e7  cmp     qword ptr cs:xmmword_1800710A0, r12
0x1800396ee  jz      short loc_180039757
0x1800396f0  lea     rdx, aSCopystringlis; "%s: CopyStringList(TenantID) failed wit"...
0x1800396f7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800396fe  mov     word ptr [rbp+800h+var_840], r12w
0x180039703  movdqu  [rbp+800h+var_880], xmm0
0x180039708  mov     word ptr [rbp+800h+var_870], r12w
0x18003970d  mov     r9d, eax
0x180039710  mov     r8, r13
0x180039713  lea     rcx, [rbp+800h+var_840]
0x180039717  call    FormatRRASErrorString
0x18003971c  lea     rax, [rbp+800h+var_870]
0x180039720  mov     [rsp+900h+var_8D8], rax
0x180039725  lea     r9, [rbp+800h+var_880]
0x180039729  test    r15, r15
0x18003972c  mov     [rsp+900h+var_8E0], r12
0x180039731  cmovnz  r9, r15
0x180039735  lea     r8, [rbp+800h+var_840]
0x180039739  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180039740  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180039747  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003974e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039753  mov     ebx, [rsp+900h+var_8C0]
0x180039757  lea     rcx, [rsp+900h+var_8B8]; this
0x18003975c  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180039761  mov     eax, ebx
0x180039763  mov     rcx, [rbp+800h+var_40]
0x18003976a  xor     rcx, rsp; StackCookie
0x18003976d  call    __security_check_cookie
0x180039772  mov     rbx, [rsp+900h+arg_18]
0x18003977a  add     rsp, 8D0h
0x180039781  pop     r15
0x180039783  pop     r14
0x180039785  pop     r13
0x180039787  pop     r12
0x180039789  pop     rdi
0x18003978a  pop     rsi
0x18003978b  pop     rbp
0x18003978c  retn
```
