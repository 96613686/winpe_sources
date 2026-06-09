# CServiceProvider::Unassociate(ushort const *)

- ea: `0x18000b5c0`
- end: `0x18000b8cb`
- name: `?Unassociate@CServiceProvider@@UEAAJPEBG@Z`
- size: `779`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x180008880`

## callees

- `0x180009748`
- `0x18000a854`
- `0x18000b2e4`
- `0x18000b5c0`
- `0x18000bc18`
- `0x18000bce4`
- `0x18000bd30`
- `0x18000f198`
- `0x18000f6a0`
- `0x18000f858`
- `0x18000fc84`
- `0x18000fce0`
- `0x180014010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18000b78c`
- `ole32!PropVariantClear` at `0x18000b80e`
- `ole32!PropVariantClear` at `0x18000b818`
- `ole32!PropVariantClear` at `0x18000b78c`
- `ole32!PropVariantClear` at `0x18000b80e`
- `ole32!PropVariantClear` at `0x18000b818`
- `ole32!CoTaskMemFree` at `0x18000b827`
- `ole32!CoTaskMemFree` at `0x18000b83e`
- `ole32!CoTaskMemFree` at `0x18000b827`
- `ole32!CoTaskMemFree` at `0x18000b83e`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Unassociate(CServiceProvider *this, const unsigned __int16 *a2)
{
  __int64 *v3; // rcx
  int v4; // r14d
  __int64 v5; // rax
  int FiCategory; // eax
  int v7; // r9d
  unsigned int v8; // eax
  unsigned int v9; // edi
  unsigned int v10; // ebx
  int v11; // eax
  bool v12; // cf
  unsigned __int16 *v14; // [rsp+20h] [rbp-39h]
  __int64 v15; // [rsp+30h] [rbp-29h] BYREF
  __int128 v16; // [rsp+38h] [rbp-21h] BYREF
  struct tagPROPVARIANT v17; // [rsp+48h] [rbp-11h] BYREF
  struct tagPROPVARIANT v18; // [rsp+60h] [rbp+7h] BYREF
  PROPVARIANT pvar[2]; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v20; // [rsp+88h] [rbp+2Fh]
  unsigned int v21; // [rsp+C0h] [rbp+67h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp+77h] BYREF
  unsigned __int16 *v23; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v14 = (unsigned __int16 *)((char *)this - 8);
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  v15 = 0;
  v3 = (__int64 *)*((_QWORD *)this + 10);
  v4 = 0;
  pv = 0;
  v23 = 0;
  memset(&v18, 0, sizeof(v18));
  memset(&v17, 0, sizeof(v17));
  v5 = *v3;
  v16 = 0;
  FiCategory = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v5 + 48))(v3, 0, &v15);
  if ( FiCategory )
    goto LABEL_28;
  FiCategory = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)v15 + 40LL))(
                 v15,
                 &PKEY_PNPX_GlobalIdentity,
                 &v18);
  if ( FiCategory )
    goto LABEL_28;
  FiCategory = CServiceProvider::GetFiCategory((CServiceProvider *)((char *)this - 8), (unsigned __int16 **)&pv, &v23);
  if ( FiCategory )
    goto LABEL_28;
  if ( !*((_QWORD *)this + 11) )
    goto LABEL_15;
  FiCategory = GetRootDevNode(&v18, &v17);
  if ( FiCategory )
    goto LABEL_28;
  if ( v17.vt != 31 )
    goto LABEL_15;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_8299e7f36ddb39903502156c86dec960_Traceguids,
      v7,
      v17.hVal.QuadPart);
  FiCategory = CServiceProvider::SetupPnpNotification(
                 (CServiceProvider *)((char *)this - 8),
                 1,
                 QUA_REMOVE,
                 *((struct IFunctionDiscoveryNotification **)this + 11),
                 v17.bstrVal);
  if ( FiCategory )
  {
LABEL_28:
    v9 = FiCategory;
    goto LABEL_29;
  }
  v4 = 1;
LABEL_15:
  if ( CPnpxDafHelper::Init((CPnpxDafHelper *)&v16, (const unsigned __int16 *)pv) )
  {
    v20 = 0;
    *(_OWORD *)pvar = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v15 + 40LL))(
           v15,
           DEVPKEY_Aep_AepId,
           pvar);
    if ( !v8 )
    {
      if ( LOWORD(pvar[0]) != 31 || !pvar[1] )
      {
        v9 = -2147467259;
LABEL_21:
        PropVariantClear(pvar);
        if ( v9 )
          goto LABEL_29;
        goto LABEL_22;
      }
      v8 = CPnpxDafHelper::InitFromAepId((CPnpxDafHelper *)&v16, (const unsigned __int16 *)pvar[1]);
    }
    v9 = v8;
    goto LABEL_21;
  }
LABEL_22:
  v21 = CPnpxDafHelper::DoDafRemoveAssociation((CPnpxDafHelper *)&v16, v18.bstrVal);
  v10 = v21;
  PnpxTelemetry::Unassociate<unsigned short * &,unsigned short * &,unsigned short * &,long &>(
    &pv,
    &v23,
    &v18.decVal.Lo32,
    &v21,
    v14);
  if ( v10 == -2140930031 )
  {
    v9 = 0;
    goto LABEL_26;
  }
  v9 = v10;
  if ( !v10 )
  {
LABEL_26:
    if ( v4 )
      v9 = -2147483638;
    goto LABEL_31;
  }
LABEL_29:
  if ( v4 )
    CServiceProvider::SetupPnpNotification(
      (CServiceProvider *)((char *)this - 8),
      0,
      QUA_REMOVE,
      *((struct IFunctionDiscoveryNotification **)this + 11),
      v17.bstrVal);
LABEL_31:
  PropVariantClear((PROPVARIANT *)&v18);
  PropVariantClear((PROPVARIANT *)&v17);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v23 )
  {
    CoTaskMemFree(v23);
    v23 = 0;
  }
  v11 = 0;
  if ( v9 )
    v12 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v12 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v11) = !v12;
    if ( v11 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  CPnpxDafHelper::~CPnpxDafHelper((CPnpxDafHelper *)&v16);
  return v9;
}

```

## disassembly

```asm
0x18000b5c0  mov     [rsp-8+arg_8], rbx
0x18000b5c5  push    rbp
0x18000b5c6  push    rsi
0x18000b5c7  push    rdi
0x18000b5c8  push    r14
0x18000b5ca  push    r15
0x18000b5cc  lea     rbp, [rsp-37h]
0x18000b5d1  sub     rsp, 90h
0x18000b5d8  mov     rsi, rcx
0x18000b5db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5e2  lea     rax, WPP_GLOBAL_Control
0x18000b5e9  cmp     rcx, rax
0x18000b5ec  jz      short loc_18000B612
0x18000b5ee  cmp     byte ptr [rcx+19h], 4
0x18000b5f2  jb      short loc_18000B612
0x18000b5f4  mov     rcx, [rcx+10h]
0x18000b5f8  lea     rax, [rsi-8]
0x18000b5fc  mov     edx, 16h
0x18000b601  mov     [rsp+0B0h+var_90], rax
0x18000b606  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000b60d  call    WPP_SF_sq
0x18000b612  xor     eax, eax
0x18000b614  mov     [rbp+57h+var_80], 0
0x18000b61c  xorps   xmm0, xmm0
0x18000b61f  mov     [rbp+57h+var_40], rax
0x18000b623  mov     [rbp+57h+var_58], rax
0x18000b627  lea     r15, [rsi-8]
0x18000b62b  mov     rcx, [r15+58h]
0x18000b62f  lea     r8, [rbp+57h+var_80]
0x18000b633  xor     r14d, r14d
0x18000b636  xorps   xmm1, xmm1
0x18000b639  mov     [rbp+57h+pv], r14
0x18000b63d  xor     edx, edx
0x18000b63f  mov     [rbp+57h+arg_18], r14
0x18000b643  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18000b647  movups  xmmword ptr [rbp+57h+var_68], xmm1
0x18000b64b  mov     rax, [rcx]
0x18000b64e  movdqu  [rbp+57h+var_78], xmm0
0x18000b653  mov     rax, [rax+30h]
0x18000b657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b65c  mov     ebx, eax
0x18000b65e  test    eax, eax
0x18000b660  jnz     loc_18000B7E8
0x18000b666  mov     rcx, [rbp+57h+var_80]
0x18000b66a  lea     r8, [rbp+57h+var_50]
0x18000b66e  lea     rdx, PKEY_PNPX_GlobalIdentity
0x18000b675  mov     rax, [rcx]
0x18000b678  mov     rax, [rax+28h]
0x18000b67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b681  mov     ebx, eax
0x18000b683  test    eax, eax
0x18000b685  jnz     loc_18000B7E8
0x18000b68b  lea     r8, [rbp+57h+arg_18]; unsigned __int16 **
0x18000b68f  mov     rcx, r15; this
0x18000b692  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x18000b696  call    ?GetFiCategory@CServiceProvider@@IEAAJPEAPEAG0@Z; CServiceProvider::GetFiCategory(ushort * *,ushort * *)
0x18000b69b  mov     ebx, eax
0x18000b69d  test    eax, eax
0x18000b69f  jnz     loc_18000B7E8
0x18000b6a5  lea     edi, [rax+1Fh]
0x18000b6a8  cmp     [rsi+58h], r14
0x18000b6ac  jz      short loc_18000B72D
0x18000b6ae  lea     rdx, [rbp+57h+var_68]; struct tagPROPVARIANT *
0x18000b6b2  lea     rcx, [rbp+57h+var_50]; struct tagPROPVARIANT *
0x18000b6b6  call    ?GetRootDevNode@@YAJAEBUtagPROPVARIANT@@PEAU1@@Z; GetRootDevNode(tagPROPVARIANT const &,tagPROPVARIANT *)
0x18000b6bb  mov     ebx, eax
0x18000b6bd  test    eax, eax
0x18000b6bf  jnz     loc_18000B7E8
0x18000b6c5  cmp     di, word ptr [rbp+57h+var_68]
0x18000b6c9  jnz     short loc_18000B72D
0x18000b6cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6d2  lea     rax, WPP_GLOBAL_Control
0x18000b6d9  cmp     rcx, rax
0x18000b6dc  jz      short loc_18000B700
0x18000b6de  cmp     byte ptr [rcx+19h], 4
0x18000b6e2  jb      short loc_18000B700
0x18000b6e4  mov     rax, [rbp+57h+var_68+8]
0x18000b6e8  lea     edx, [rdi-8]
0x18000b6eb  mov     rcx, [rcx+10h]
0x18000b6ef  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000b6f6  mov     [rsp+0B0h+var_90], rax
0x18000b6fb  call    WPP_SF_sS
0x18000b700  mov     rax, [rbp+57h+var_68+8]
0x18000b704  mov     rcx, r15; this
0x18000b707  mov     r9, [rsi+58h]; struct IFunctionDiscoveryNotification *
0x18000b70b  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x18000b710  mov     eax, 1
0x18000b715  mov     r8d, eax; enum tagQueryUpdateAction
0x18000b718  mov     edx, eax; int
0x18000b71a  call    ?SetupPnpNotification@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG@Z; CServiceProvider::SetupPnpNotification(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *)
0x18000b71f  mov     ebx, eax
0x18000b721  test    eax, eax
0x18000b723  jnz     loc_18000B7E8
0x18000b729  lea     r14d, [rax+1]
0x18000b72d  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18000b731  lea     rcx, [rbp+57h+var_78]; this
0x18000b735  call    ?Init@CPnpxDafHelper@@QEAAJPEBG@Z; CPnpxDafHelper::Init(ushort const *)
0x18000b73a  test    eax, eax
0x18000b73c  jz      short loc_18000B796
0x18000b73e  mov     rcx, [rbp+57h+var_80]
0x18000b742  lea     r8, [rbp+57h+pvar]
0x18000b746  xor     eax, eax
0x18000b748  lea     rdx, DEVPKEY_Aep_AepId
0x18000b74f  mov     [rbp+57h+var_28], rax
0x18000b753  xorps   xmm0, xmm0
0x18000b756  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000b75a  mov     rax, [rcx]
0x18000b75d  mov     rax, [rax+28h]
0x18000b761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b766  mov     ebx, eax
0x18000b768  test    eax, eax
0x18000b76a  jnz     short loc_18000B786
0x18000b76c  cmp     di, word ptr [rbp+57h+pvar]
0x18000b770  jnz     short loc_18000B7CB
0x18000b772  mov     rdx, [rbp+57h+pvar+8]; unsigned __int16 *
0x18000b776  test    rdx, rdx
0x18000b779  jz      short loc_18000B7CB
0x18000b77b  lea     rcx, [rbp+57h+var_78]; this
0x18000b77f  call    ?InitFromAepId@CPnpxDafHelper@@QEAAJPEBG@Z; CPnpxDafHelper::InitFromAepId(ushort const *)
0x18000b784  mov     ebx, eax
0x18000b786  mov     edi, eax
0x18000b788  lea     rcx, [rbp+57h+pvar]; pvar
0x18000b78c  call    cs:__imp_PropVariantClear
0x18000b792  test    edi, edi
0x18000b794  jnz     short loc_18000B7EA
0x18000b796  mov     rdx, [rbp+57h+var_50+8]; unsigned __int16 *
0x18000b79a  lea     rcx, [rbp+57h+var_78]; this
0x18000b79e  call    ?DoDafRemoveAssociation@CPnpxDafHelper@@QEAAJPEBG@Z; CPnpxDafHelper::DoDafRemoveAssociation(ushort const *)
0x18000b7a3  lea     r9, [rbp+57h+arg_0]
0x18000b7a7  mov     [rbp+57h+arg_0], eax
0x18000b7aa  lea     r8, [rbp+57h+var_50+8]
0x18000b7ae  mov     ebx, eax
0x18000b7b0  lea     rdx, [rbp+57h+arg_18]
0x18000b7b4  lea     rcx, [rbp+57h+pv]
0x18000b7b8  call    ??$Unassociate@AEAPEAGAEAPEAGAEAPEAGAEAJ@PnpxTelemetry@@SAXAEAPEAG00AEAJ@Z; PnpxTelemetry::Unassociate<ushort * &,ushort * &,ushort * &,long &>(ushort * &,ushort * &,ushort * &,long &)
0x18000b7bd  cmp     ebx, 80640011h
0x18000b7c3  jnz     short loc_18000B7D4
0x18000b7c5  xor     ebx, ebx
0x18000b7c7  xor     edi, edi
0x18000b7c9  jmp     short loc_18000B7DA
0x18000b7cb  mov     ebx, 80004005h
0x18000b7d0  mov     edi, ebx
0x18000b7d2  jmp     short loc_18000B788
0x18000b7d4  mov     edi, ebx
0x18000b7d6  test    ebx, ebx
0x18000b7d8  jnz     short loc_18000B7EA
0x18000b7da  test    r14d, r14d
0x18000b7dd  jz      short loc_18000B80A
0x18000b7df  mov     ebx, 8000000Ah
0x18000b7e4  mov     edi, ebx
0x18000b7e6  jmp     short loc_18000B80A
0x18000b7e8  mov     edi, eax
0x18000b7ea  test    r14d, r14d
0x18000b7ed  jz      short loc_18000B80A
0x18000b7ef  mov     rax, [rbp+57h+var_68+8]
0x18000b7f3  xor     edx, edx; int
0x18000b7f5  mov     r9, [rsi+58h]; struct IFunctionDiscoveryNotification *
0x18000b7f9  mov     rcx, r15; this
0x18000b7fc  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x18000b801  lea     r8d, [rdx+1]; enum tagQueryUpdateAction
0x18000b805  call    ?SetupPnpNotification@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG@Z; CServiceProvider::SetupPnpNotification(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *)
0x18000b80a  lea     rcx, [rbp+57h+var_50]; pvar
0x18000b80e  call    cs:__imp_PropVariantClear
0x18000b814  lea     rcx, [rbp+57h+var_68]; pvar
0x18000b818  call    cs:__imp_PropVariantClear
0x18000b81e  mov     rcx, [rbp+57h+pv]; pv
0x18000b822  test    rcx, rcx
0x18000b825  jz      short loc_18000B835
0x18000b827  call    cs:__imp_CoTaskMemFree
0x18000b82d  mov     [rbp+57h+pv], 0
0x18000b835  mov     rcx, [rbp+57h+arg_18]; pv
0x18000b839  test    rcx, rcx
0x18000b83c  jz      short loc_18000B84C
0x18000b83e  call    cs:__imp_CoTaskMemFree
0x18000b844  mov     [rbp+57h+arg_18], 0
0x18000b84c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b853  xor     eax, eax
0x18000b855  test    edi, edi
0x18000b857  jnz     short loc_18000B85F
0x18000b859  cmp     byte ptr [rcx+19h], 4
0x18000b85d  jmp     short loc_18000B863
0x18000b85f  cmp     byte ptr [rcx+19h], 2
0x18000b863  setnb   al
0x18000b866  lea     rdx, WPP_GLOBAL_Control
0x18000b86d  cmp     rcx, rdx
0x18000b870  jz      short loc_18000B894
0x18000b872  test    eax, eax
0x18000b874  jz      short loc_18000B894
0x18000b876  mov     rcx, [rcx+10h]
0x18000b87a  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000b881  mov     edx, 18h
0x18000b886  mov     [rsp+0B0h+var_88], ebx
0x18000b88a  mov     [rsp+0B0h+var_90], r15
0x18000b88f  call    WPP_SF_sqd
0x18000b894  mov     rcx, [rbp+57h+var_80]
0x18000b898  test    rcx, rcx
0x18000b89b  jz      short loc_18000B8A9
0x18000b89d  mov     rdx, [rcx]
0x18000b8a0  mov     rax, [rdx+10h]
0x18000b8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8a9  lea     rcx, [rbp+57h+var_78]; this
0x18000b8ad  call    ??1CPnpxDafHelper@@QEAA@XZ; CPnpxDafHelper::~CPnpxDafHelper(void)
0x18000b8b2  mov     rbx, [rsp+0B0h+arg_8]
0x18000b8ba  mov     eax, edi
0x18000b8bc  add     rsp, 90h
0x18000b8c3  pop     r15
0x18000b8c5  pop     r14
0x18000b8c7  pop     rdi
0x18000b8c8  pop     rsi
0x18000b8c9  pop     rbp
0x18000b8ca  retn
```
