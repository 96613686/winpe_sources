# FwLuidsToSafearray(_tag_FW_INTERFACE_LUIDS const *,tagVARIANT *)

- ea: `0x18003225c`
- end: `0x1800324f3`
- name: `?FwLuidsToSafearray@@YAJPEBU_tag_FW_INTERFACE_LUIDS@@PEAUtagVARIANT@@@Z`
- size: `663`
- prototype: `int(const struct _tag_FW_INTERFACE_LUIDS *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800228f0`
- `0x18003a170`

## callees

- `0x180005e0c`
- `0x1800294b0`
- `0x180031a00`
- `0x18003203c`
- `0x18003225c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800323bd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800323bd`
- `OLEAUT32!__imp_SysFreeString` at `0x180032401`
- `OLEAUT32!__imp_SysFreeString` at `0x18003249c`
- `OLEAUT32!__imp_SysFreeString` at `0x180032401`
- `OLEAUT32!__imp_SysFreeString` at `0x18003249c`
- `OLEAUT32!__imp_VariantInit` at `0x18003229a`
- `OLEAUT32!__imp_VariantInit` at `0x1800323a1`
- `OLEAUT32!__imp_VariantInit` at `0x18003229a`
- `OLEAUT32!__imp_VariantInit` at `0x1800323a1`
- `OLEAUT32!__imp_VariantClear` at `0x1800323f2`
- `OLEAUT32!__imp_VariantClear` at `0x1800323f2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800322cd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800322cd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800324bf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800324bf`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800323dc`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800323dc`
- `fwbase!FwBaseFree` at `0x1800324ac`
- `fwbase!FwBaseFree` at `0x1800324ac`

## pseudocode

```c
__int64 __fastcall FwLuidsToSafearray(ULONG *a1, struct tagVARIANT *a2)
{
  OLECHAR *v3; // rdi
  ULONG v5; // eax
  SAFEARRAY *v6; // r15
  int Adapters; // ebx
  FwPolicy2 *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int i; // r14d
  BSTR v12; // rax
  HRESULT v13; // eax
  OLECHAR *psz; // [rsp+20h] [rbp-40h] BYREF
  struct _IP_ADAPTER_ADDRESSES_LH *v16; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-30h] BYREF
  LONG rgIndices; // [rsp+48h] [rbp-18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-10h] BYREF

  v16 = 0;
  v3 = 0;
  psz = 0;
  VariantInit(a2);
  v5 = *a1;
  if ( !*a1 )
  {
    v6 = 0;
    a2->vt = 0;
    Adapters = 0;
    goto LABEL_27;
  }
  rgsabound.lLbound = 0;
  rgsabound.cElements = v5;
  v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  if ( v6 )
  {
    Adapters = FwGetAdapters(&v16);
    if ( Adapters >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= *a1 )
        {
          a2->vt = 8204;
          a2->llVal = (LONGLONG)v6;
          goto LABEL_25;
        }
        if ( (int)FwLuidToInterfaceNameBstr(v16, (const struct _GUID *)(*((_QWORD *)a1 + 1) + 16LL * i), &psz) < 0 )
          break;
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v3 = psz;
        pvarg.vt = 8;
        v12 = SysAllocString(psz);
        rgIndices = i;
        pvarg.llVal = (LONGLONG)v12;
        v13 = SafeArrayPutElement(v6, &rgIndices, &pvarg);
        Adapters = v13;
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids,
              (unsigned int)v13);
          goto LABEL_25;
        }
        VariantClear(&pvarg);
        SysFreeString(v3);
        v3 = 0;
        psz = 0;
      }
      Adapters = -2147418113;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, 2147549183LL);
      v3 = psz;
LABEL_25:
      if ( v3 )
        SysFreeString(v3);
    }
    else
    {
      v10 = 2147549183LL;
      Adapters = -2147418113;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 47;
        goto LABEL_7;
      }
    }
  }
  else
  {
    Adapters = -2147024882;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 46;
      v10 = 2147942414LL;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, v10);
    }
  }
LABEL_27:
  FwBaseFree(v16);
  if ( Adapters < 0 )
    SafeArrayDestroy(v6);
  return (unsigned int)Adapters;
}

```

## disassembly

```asm
0x18003225c  mov     [rsp-28h+arg_10], rbx
0x180032261  mov     [rsp-28h+arg_18], rsi
0x180032266  push    rbp
0x180032267  push    rdi
0x180032268  push    r12
0x18003226a  push    r14
0x18003226c  push    r15
0x18003226e  mov     rbp, rsp
0x180032271  sub     rsp, 60h
0x180032275  mov     rax, cs:__security_cookie
0x18003227c  xor     rax, rsp
0x18003227f  mov     [rbp+var_8], rax
0x180032283  mov     r12, rcx
0x180032286  mov     [rbp+var_38], 0
0x18003228e  xor     edi, edi
0x180032290  mov     rcx, rdx; pvarg
0x180032293  mov     [rbp+psz], rdi
0x180032297  mov     rsi, rdx
0x18003229a  call    cs:__imp_VariantInit
0x1800322a1  nop     dword ptr [rax+rax+00h]
0x1800322a6  mov     eax, [r12]
0x1800322aa  test    eax, eax
0x1800322ac  jnz     short loc_1800322BB
0x1800322ae  xor     r15d, r15d
0x1800322b1  mov     [rsi], ax
0x1800322b4  xor     ebx, ebx
0x1800322b6  jmp     loc_1800324A8
0x1800322bb  mov     ecx, 0Ch; vt
0x1800322c0  mov     [rbp+rgsabound.lLbound], edi
0x1800322c3  lea     r8, [rbp+rgsabound]; rgsabound
0x1800322c7  mov     [rbp+rgsabound.cElements], eax
0x1800322ca  lea     edx, [rcx-0Bh]; cDims
0x1800322cd  call    cs:__imp_SafeArrayCreate
0x1800322d4  nop     dword ptr [rax+rax+00h]
0x1800322d9  mov     r15, rax
0x1800322dc  test    rax, rax
0x1800322df  jnz     short loc_180032322
0x1800322e1  mov     ebx, 8007000Eh
0x1800322e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800322ed  lea     rdx, WPP_GLOBAL_Control
0x1800322f4  cmp     rcx, rdx
0x1800322f7  jz      loc_1800324A8
0x1800322fd  test    byte ptr [rcx+1Ch], 1
0x180032301  jz      loc_1800324A8
0x180032307  lea     edx, [rax+2Eh]
0x18003230a  mov     r9d, ebx
0x18003230d  mov     rcx, [rcx+10h]
0x180032311  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180032318  call    WPP_SF_d
0x18003231d  jmp     loc_1800324A8
0x180032322  lea     rcx, [rbp+var_38]; struct _IP_ADAPTER_ADDRESSES_LH **
0x180032326  call    ?FwGetAdapters@@YAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; FwGetAdapters(_IP_ADAPTER_ADDRESSES_LH * *)
0x18003232b  mov     ebx, eax
0x18003232d  test    eax, eax
0x18003232f  jns     short loc_180032362
0x180032331  mov     r9d, 8000FFFFh
0x180032337  mov     ebx, r9d
0x18003233a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032341  lea     rdx, WPP_GLOBAL_Control
0x180032348  cmp     rcx, rdx
0x18003234b  jz      loc_1800324A8
0x180032351  test    byte ptr [rcx+1Ch], 1
0x180032355  jz      loc_1800324A8
0x18003235b  mov     edx, 2Fh ; '/'
0x180032360  jmp     short loc_18003230D
0x180032362  xor     r14d, r14d
0x180032365  cmp     r14d, [r12]
0x180032369  jnb     loc_18003248B
0x18003236f  mov     rcx, [rbp+var_38]; struct _IP_ADAPTER_ADDRESSES_LH *
0x180032373  lea     r8, [rbp+psz]; unsigned __int16 **
0x180032377  mov     edx, r14d
0x18003237a  shl     rdx, 4
0x18003237e  add     rdx, [r12+8]; struct _GUID *
0x180032383  call    ?FwLuidToInterfaceNameBstr@@YAJPEAU_IP_ADAPTER_ADDRESSES_LH@@PEBU_GUID@@PEAPEAG@Z; FwLuidToInterfaceNameBstr(_IP_ADAPTER_ADDRESSES_LH *,_GUID const *,ushort * *)
0x180032388  test    eax, eax
0x18003238a  js      loc_18003244E
0x180032390  xorps   xmm0, xmm0
0x180032393  lea     rcx, [rbp+pvarg]; pvarg
0x180032397  xor     eax, eax
0x180032399  movups  xmmword ptr [rbp+pvarg], xmm0
0x18003239d  mov     qword ptr [rbp+pvarg+10h], rax
0x1800323a1  call    cs:__imp_VariantInit
0x1800323a8  nop     dword ptr [rax+rax+00h]
0x1800323ad  mov     rdi, [rbp+psz]
0x1800323b1  mov     eax, 8
0x1800323b6  mov     rcx, rdi; psz
0x1800323b9  mov     word ptr [rbp+pvarg], ax
0x1800323bd  call    cs:__imp_SysAllocString
0x1800323c4  nop     dword ptr [rax+rax+00h]
0x1800323c9  lea     r8, [rbp+pvarg]; pv
0x1800323cd  mov     [rbp+rgIndices], r14d
0x1800323d1  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800323d5  mov     qword ptr [rbp+pvarg+8], rax
0x1800323d9  mov     rcx, r15; psa
0x1800323dc  call    cs:__imp_SafeArrayPutElement
0x1800323e3  nop     dword ptr [rax+rax+00h]
0x1800323e8  mov     ebx, eax
0x1800323ea  test    eax, eax
0x1800323ec  js      short loc_18003241B
0x1800323ee  lea     rcx, [rbp+pvarg]; pvarg
0x1800323f2  call    cs:__imp_VariantClear
0x1800323f9  nop     dword ptr [rax+rax+00h]
0x1800323fe  mov     rcx, rdi; bstrString
0x180032401  call    cs:__imp_SysFreeString
0x180032408  nop     dword ptr [rax+rax+00h]
0x18003240d  xor     edi, edi
0x18003240f  mov     [rbp+psz], rdi
0x180032413  inc     r14d
0x180032416  jmp     loc_180032365
0x18003241b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032422  lea     rdx, WPP_GLOBAL_Control
0x180032429  cmp     rcx, rdx
0x18003242c  jz      short loc_180032494
0x18003242e  test    byte ptr [rcx+1Ch], 1
0x180032432  jz      short loc_180032494
0x180032434  mov     rcx, [rcx+10h]
0x180032438  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18003243f  mov     edx, 31h ; '1'
0x180032444  mov     r9d, eax
0x180032447  call    WPP_SF_d
0x18003244c  jmp     short loc_180032494
0x18003244e  mov     r9d, 8000FFFFh
0x180032454  mov     ebx, r9d
0x180032457  mov     rcx, cs:WPP_GLOBAL_Control
0x18003245e  lea     rdx, WPP_GLOBAL_Control
0x180032465  cmp     rcx, rdx
0x180032468  jz      short loc_180032485
0x18003246a  test    byte ptr [rcx+1Ch], 1
0x18003246e  jz      short loc_180032485
0x180032470  mov     rcx, [rcx+10h]
0x180032474  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18003247b  mov     edx, 30h ; '0'
0x180032480  call    WPP_SF_d
0x180032485  mov     rdi, [rbp+psz]
0x180032489  jmp     short loc_180032494
0x18003248b  mov     word ptr [rsi], 200Ch
0x180032490  mov     [rsi+8], r15
0x180032494  test    rdi, rdi
0x180032497  jz      short loc_1800324A8
0x180032499  mov     rcx, rdi; bstrString
0x18003249c  call    cs:__imp_SysFreeString
0x1800324a3  nop     dword ptr [rax+rax+00h]
0x1800324a8  mov     rcx, [rbp+var_38]
0x1800324ac  call    cs:__imp_FwBaseFree
0x1800324b3  nop     dword ptr [rax+rax+00h]
0x1800324b8  test    ebx, ebx
0x1800324ba  jns     short loc_1800324CB
0x1800324bc  mov     rcx, r15; psa
0x1800324bf  call    cs:__imp_SafeArrayDestroy
0x1800324c6  nop     dword ptr [rax+rax+00h]
0x1800324cb  mov     eax, ebx
0x1800324cd  mov     rcx, [rbp+var_8]
0x1800324d1  xor     rcx, rsp; StackCookie
0x1800324d4  call    __security_check_cookie
0x1800324d9  lea     r11, [rsp+60h+var_s0]
0x1800324de  mov     rbx, [r11+40h]
0x1800324e2  mov     rsi, [r11+48h]
0x1800324e6  mov     rsp, r11
0x1800324e9  pop     r15
0x1800324eb  pop     r14
0x1800324ed  pop     r12
0x1800324ef  pop     rdi
0x1800324f0  pop     rbp
0x1800324f1  retn
```
