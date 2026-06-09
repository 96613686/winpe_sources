# CPreloadManager::InitAndSetPrerenderBrokerStructs(_HIDDENTAB_REQUEST_ACTION,CPreloadManager::PredictivePrerenderPage const * const,_BROKER_BIND_INFO * const,_BROKER_REDIRECT_DETAIL * const,_HIDDENTAB_REQUEST_INFO * const)

- ea: `0x1808fb680`
- end: `0x1808fb8ba`
- name: `?InitAndSetPrerenderBrokerStructs@CPreloadManager@@AEAAJW4_HIDDENTAB_REQUEST_ACTION@@QEBUPredictivePrerenderPage@1@QEAU_BROKER_BIND_INFO@@QEAU_BROKER_REDIRECT_DETAIL@@QEAU_HIDDENTAB_REQUEST_INFO@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(__int64, int, _DWORD *, _QWORD *, char *, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180712898`
- `0x1808fb030`
- `0x1808fbe70`

## callees

- `0x1801086ac`
- `0x1803ddae0`
- `0x1805f7f7c`
- `0x1808fb680`
- `0x1810f6516`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1808fb80f`
- `KERNEL32!GetCurrentProcessId` at `0x1808fb80f`
- `KERNEL32!GetCurrentThreadId` at `0x1808fb864`
- `KERNEL32!GetCurrentThreadId` at `0x1808fb864`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808fb841`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808fb841`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1808fb87d`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1808fb87d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808fb850`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808fb850`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808fb823`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808fb823`
- `OLEAUT32!__imp_SysAllocString` at `0x1808fb6fe`
- `OLEAUT32!__imp_SysAllocString` at `0x1808fb6fe`
- `OLEAUT32!__imp_VariantInit` at `0x1808fb799`
- `OLEAUT32!__imp_VariantInit` at `0x1808fb7f2`
- `OLEAUT32!__imp_VariantInit` at `0x1808fb799`
- `OLEAUT32!__imp_VariantInit` at `0x1808fb7f2`
- `OLEAUT32!__imp_VariantClear` at `0x1808fb803`
- `OLEAUT32!__imp_VariantClear` at `0x1808fb803`

## pseudocode

```c
__int64 __fastcall CPreloadManager::InitAndSetPrerenderBrokerStructs(
        __int64 a1,
        int a2,
        _DWORD *a3,
        _QWORD *a4,
        char *a5,
        __int64 a6)
{
  int v10; // ebp
  const OLECHAR *Url; // rax
  BSTR v12; // rax
  __int64 v13; // rax
  CMarkup *v14; // rcx
  CMarkup *v15; // rcx
  CMarkup *v16; // rcx
  struct CDoc *v17; // rax
  char Integrity; // al
  DWORD CurrentThreadId; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-58h] BYREF

  memset_0(a4, 0, 0x90u);
  memset_0(a5, 0, 0x44u);
  *(_OWORD *)a6 = 0;
  *(_DWORD *)(a6 + 16) = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)a3 + 56LL))(*(_QWORD *)a3, a4);
  if ( v10 < 0 )
    return (unsigned int)v10;
  Url = CMarkup::GetUrl(*(const struct CMarkup *const *)(a1 + 96));
  v12 = SysAllocString(Url);
  if ( !v12 )
    return (unsigned int)-2147024882;
  a4[3] = v12;
  if ( a3[6] == 26 )
    goto LABEL_8;
  if ( a3[6] != 27 )
  {
    if ( a3[6] != 99 )
    {
      if ( a3[6] != 100 )
        goto LABEL_10;
      goto LABEL_7;
    }
LABEL_8:
    v13 = 0x2000000000LL;
    goto LABEL_9;
  }
LABEL_7:
  v13 = 0x4000000000LL;
LABEL_9:
  a4[14] |= v13;
LABEL_10:
  v14 = *(CMarkup **)(a1 + 96);
  if ( v14 )
  {
    if ( CMarkup::Doc(v14) )
    {
      if ( *((_QWORD *)CMarkup::Doc(v15) + 8) )
      {
        if ( *((char *)CMarkup::Doc(v16) + 4868) >= 0 )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          v17 = CMarkup::Doc(*(CMarkup **)(a1 + 96));
          if ( (int)CTExec(*((struct IUnknown **)v17 + 8), &CGID_Explorer, 0x78u, 0, 0, &pvarg) >= 0 )
          {
            if ( pvarg.vt == 8 )
            {
              a4[10] = pvarg.llVal;
              VariantInit(&pvarg);
            }
            VariantClear(&pvarg);
          }
        }
      }
    }
  }
  *((_DWORD *)a5 + 6) = GetCurrentProcessId();
  Integrity = IsoGetIntegrity(1);
  *((_DWORD *)a5 + 8) = 0;
  *((_DWORD *)a5 + 7) = Integrity & 0x7F;
  *((_DWORD *)a5 + 10) = IEConfiguration_GetDWORD(536870929);
  *(_OWORD *)(a5 + 52) = *(_OWORD *)GlobalThreadState();
  CurrentThreadId = GetCurrentThreadId();
  LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, (unsigned int *)a5, 0);
  *((_DWORD *)a5 + 12) = a3[3];
  *(_DWORD *)a6 = a2;
  *(_DWORD *)(a6 + 12) = a3[2];
  *(_DWORD *)(a6 + 8) = 37748736;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1808fb680  push    rbx
0x1808fb682  push    rbp
0x1808fb683  push    rsi
0x1808fb684  push    rdi
0x1808fb685  push    r12
0x1808fb687  push    r14
0x1808fb689  push    r15
0x1808fb68b  sub     rsp, 50h
0x1808fb68f  mov     rdi, r8
0x1808fb692  mov     r12d, edx
0x1808fb695  mov     r14, rcx
0x1808fb698  xor     edx, edx; Val
0x1808fb69a  mov     r8d, 90h; Size
0x1808fb6a0  mov     rcx, r9; void *
0x1808fb6a3  mov     rbx, r9
0x1808fb6a6  call    memset_0
0x1808fb6ab  mov     rsi, [rsp+88h+arg_20]
0x1808fb6b3  xor     edx, edx; Val
0x1808fb6b5  mov     rcx, rsi; void *
0x1808fb6b8  lea     r8d, [rdx+44h]; Size
0x1808fb6bc  call    memset_0
0x1808fb6c1  mov     r15, [rsp+88h+arg_28]
0x1808fb6c9  xor     eax, eax
0x1808fb6cb  xorps   xmm0, xmm0
0x1808fb6ce  mov     rdx, rbx
0x1808fb6d1  movups  xmmword ptr [r15], xmm0
0x1808fb6d5  mov     [r15+10h], eax
0x1808fb6d9  mov     rcx, [rdi]
0x1808fb6dc  mov     rax, [rcx]
0x1808fb6df  mov     rax, [rax+38h]
0x1808fb6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808fb6e8  mov     ebp, eax
0x1808fb6ea  test    eax, eax
0x1808fb6ec  js      loc_1808FB8A8
0x1808fb6f2  mov     rcx, [r14+60h]; struct CMarkup *
0x1808fb6f6  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x1808fb6fb  mov     rcx, rax; psz
0x1808fb6fe  call    cs:__imp_SysAllocString
0x1808fb705  nop     dword ptr [rax+rax+00h]
0x1808fb70a  test    rax, rax
0x1808fb70d  jz      loc_1808FB8A3
0x1808fb713  mov     [rbx+18h], rax
0x1808fb717  mov     ecx, [rdi+18h]
0x1808fb71a  sub     ecx, 1Ah
0x1808fb71d  jz      short loc_1808FB73A
0x1808fb71f  sub     ecx, 1
0x1808fb722  jz      short loc_1808FB72E
0x1808fb724  sub     ecx, 48h ; 'H'
0x1808fb727  jz      short loc_1808FB73A
0x1808fb729  cmp     ecx, 1
0x1808fb72c  jnz     short loc_1808FB748
0x1808fb72e  mov     rax, 4000000000h
0x1808fb738  jmp     short loc_1808FB744
0x1808fb73a  mov     rax, 2000000000h
0x1808fb744  or      [rbx+70h], rax
0x1808fb748  mov     rcx, [r14+60h]; this
0x1808fb74c  test    rcx, rcx
0x1808fb74f  jz      loc_1808FB80F
0x1808fb755  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x1808fb75a  test    rax, rax
0x1808fb75d  jz      loc_1808FB80F
0x1808fb763  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x1808fb768  cmp     qword ptr [rax+40h], 0
0x1808fb76d  jz      loc_1808FB80F
0x1808fb773  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x1808fb778  test    byte ptr [rax+1304h], 80h
0x1808fb77f  jnz     loc_1808FB80F
0x1808fb785  xorps   xmm0, xmm0
0x1808fb788  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1808fb78d  xor     eax, eax
0x1808fb78f  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x1808fb794  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x1808fb799  call    cs:__imp_VariantInit
0x1808fb7a0  nop     dword ptr [rax+rax+00h]
0x1808fb7a5  mov     rcx, [r14+60h]; this
0x1808fb7a9  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x1808fb7ae  xor     r9d, r9d; unsigned int
0x1808fb7b1  lea     rcx, [rsp+88h+pvarg]
0x1808fb7b6  mov     [rsp+88h+var_60], rcx; struct tagVARIANT *
0x1808fb7bb  lea     rdx, CGID_Explorer; struct _GUID *
0x1808fb7c2  mov     [rsp+88h+var_68], 0; struct tagVARIANT *
0x1808fb7cb  mov     rcx, [rax+40h]; struct IUnknown *
0x1808fb7cf  lea     r8d, [r9+78h]; unsigned int
0x1808fb7d3  call    ?CTExec@@YAJPEAUIUnknown@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z; CTExec(IUnknown *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x1808fb7d8  test    eax, eax
0x1808fb7da  js      short loc_1808FB80F
0x1808fb7dc  cmp     word ptr [rsp+88h+pvarg], 8
0x1808fb7e2  jnz     short loc_1808FB7FE
0x1808fb7e4  mov     rax, qword ptr [rsp+88h+pvarg+8]
0x1808fb7e9  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1808fb7ee  mov     [rbx+50h], rax
0x1808fb7f2  call    cs:__imp_VariantInit
0x1808fb7f9  nop     dword ptr [rax+rax+00h]
0x1808fb7fe  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1808fb803  call    cs:__imp_VariantClear
0x1808fb80a  nop     dword ptr [rax+rax+00h]
0x1808fb80f  call    cs:__imp_GetCurrentProcessId
0x1808fb816  nop     dword ptr [rax+rax+00h]
0x1808fb81b  mov     ecx, 1
0x1808fb820  mov     [rsi+18h], eax
0x1808fb823  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1808fb82a  nop     dword ptr [rax+rax+00h]
0x1808fb82f  mov     ecx, 20000011h
0x1808fb834  mov     dword ptr [rsi+20h], 0
0x1808fb83b  and     eax, 7Fh
0x1808fb83e  mov     [rsi+1Ch], eax
0x1808fb841  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1808fb848  nop     dword ptr [rax+rax+00h]
0x1808fb84d  mov     [rsi+28h], eax
0x1808fb850  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808fb857  nop     dword ptr [rax+rax+00h]
0x1808fb85c  movups  xmm0, xmmword ptr [rax]
0x1808fb85f  movdqu  xmmword ptr [rsi+34h], xmm0
0x1808fb864  call    cs:__imp_GetCurrentThreadId
0x1808fb86b  nop     dword ptr [rax+rax+00h]
0x1808fb870  xor     r9d, r9d
0x1808fb873  mov     r8, rsi
0x1808fb876  mov     edx, eax
0x1808fb878  mov     ecx, 203h
0x1808fb87d  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x1808fb884  nop     dword ptr [rax+rax+00h]
0x1808fb889  mov     eax, [rdi+0Ch]
0x1808fb88c  mov     [rsi+30h], eax
0x1808fb88f  mov     [r15], r12d
0x1808fb892  mov     eax, [rdi+8]
0x1808fb895  mov     [r15+0Ch], eax
0x1808fb899  mov     dword ptr [r15+8], 2400000h
0x1808fb8a1  jmp     short loc_1808FB8A8
0x1808fb8a3  mov     ebp, 8007000Eh
0x1808fb8a8  mov     eax, ebp
0x1808fb8aa  add     rsp, 50h
0x1808fb8ae  pop     r15
0x1808fb8b0  pop     r14
0x1808fb8b2  pop     r12
0x1808fb8b4  pop     rdi
0x1808fb8b5  pop     rsi
0x1808fb8b6  pop     rbp
0x1808fb8b7  pop     rbx
0x1808fb8b8  retn
```
