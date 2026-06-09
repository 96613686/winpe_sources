# FwLogCSRuleDetails(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_CS_RULE *,ulong)

- ea: `0x18008f92c`
- end: `0x18008fe2e`
- name: `?FwLogCSRuleDetails@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGPEAU_tag_FW_CS_RULE@@K@Z`
- size: `1282`
- prototype: `unsigned int __usercall@<eax>(const struct _EVENT_DESCRIPTOR *@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, struct _tag_FW_CS_RULE *@<r9>, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180071204`
- `0x18007218c`

## callees

- `0x18002d340`
- `0x180048250`
- `0x18006b940`
- `0x18006b9ac`
- `0x1800729c0`
- `0x180073488`
- `0x18008f92c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008fa24`
- `OLEAUT32!__imp_SysAllocString` at `0x18008fa61`
- `OLEAUT32!__imp_SysAllocString` at `0x18008fa24`
- `OLEAUT32!__imp_SysAllocString` at `0x18008fa61`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fdc6`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fdda`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fdc6`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fdda`
- `WS2_32!__imp_htonl` at `0x18008fb64`
- `WS2_32!__imp_htonl` at `0x18008fbb5`
- `WS2_32!__imp_htonl` at `0x18008fb64`
- `WS2_32!__imp_htonl` at `0x18008fbb5`
- `fwbase!FwPortsToString` at `0x18008fa13`
- `fwbase!FwPortsToString` at `0x18008fa50`
- `fwbase!FwPortsToString` at `0x18008fa13`
- `fwbase!FwPortsToString` at `0x18008fa50`
- `fwbase!FwFree` at `0x18008fa38`
- `fwbase!FwFree` at `0x18008fa75`
- `fwbase!FwFree` at `0x18008fdeb`
- `fwbase!FwFree` at `0x18008fdfc`
- `fwbase!FwFree` at `0x18008fa38`
- `fwbase!FwFree` at `0x18008fa75`
- `fwbase!FwFree` at `0x18008fdeb`
- `fwbase!FwFree` at `0x18008fdfc`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008fa8d`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008faa5`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008fa8d`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008faa5`

## pseudocode

```c
__int64 __fastcall FwLogCSRuleDetails(
        const struct _EVENT_DESCRIPTOR *a1,
        void *a2,
        const unsigned __int16 *a3,
        struct _tag_FW_CS_RULE *a4,
        unsigned int a5)
{
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // rdi
  __int16 v9; // ax
  __int16 v10; // cx
  u_long v11; // eax
  __int128 v12; // xmm0
  u_long v13; // ecx
  u_long v14; // eax
  __int128 v15; // xmm0
  const unsigned __int16 *v16; // rdx
  bool v17; // zf
  bool v18; // al
  bool v19; // al
  unsigned int v20; // ebx
  OLECHAR *psz; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v25; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v28; // [rsp+4Ch] [rbp-B4h] BYREF
  __int16 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v30; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v31; // [rsp+58h] [rbp-A8h] BYREF
  u_long v32; // [rsp+5Ch] [rbp-A4h] BYREF
  u_long v33; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+68h] [rbp-98h] BYREF
  __int128 v35; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v36[528]; // [rsp+90h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+2A0h] [rbp+1A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+2B0h] [rbp+1B0h] BYREF
  char *v39; // [rsp+2C0h] [rbp+1C0h]
  __int64 v40; // [rsp+2C8h] [rbp+1C8h]
  __int16 *v41; // [rsp+2D0h] [rbp+1D0h]
  __int64 v42; // [rsp+2D8h] [rbp+1D8h]
  char *v43; // [rsp+2E0h] [rbp+1E0h]
  __int64 v44; // [rsp+2E8h] [rbp+1E8h]
  struct _EVENT_DATA_DESCRIPTOR v45; // [rsp+2F0h] [rbp+1F0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v46; // [rsp+300h] [rbp+200h] BYREF
  u_long *v47; // [rsp+310h] [rbp+210h]
  __int64 v48; // [rsp+318h] [rbp+218h]
  __int128 *v49; // [rsp+320h] [rbp+220h]
  __int64 v50; // [rsp+328h] [rbp+228h]
  u_long *v51; // [rsp+330h] [rbp+230h]
  __int64 v52; // [rsp+338h] [rbp+238h]
  __int128 *v53; // [rsp+340h] [rbp+240h]
  __int64 v54; // [rsp+348h] [rbp+248h]
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+350h] [rbp+250h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v56; // [rsp+360h] [rbp+260h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v57; // [rsp+370h] [rbp+270h] BYREF
  char *v58; // [rsp+380h] [rbp+280h]
  __int64 v59; // [rsp+388h] [rbp+288h]
  char *v60; // [rsp+390h] [rbp+290h]
  __int64 v61; // [rsp+398h] [rbp+298h]
  struct _EVENT_DATA_DESCRIPTOR v62; // [rsp+3A0h] [rbp+2A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v63; // [rsp+3B0h] [rbp+2B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v64; // [rsp+3C0h] [rbp+2C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v65; // [rsp+3D0h] [rbp+2D0h] BYREF
  char *v66; // [rsp+3E0h] [rbp+2E0h]
  __int64 v67; // [rsp+3E8h] [rbp+2E8h]
  __int16 *v68; // [rsp+3F0h] [rbp+2F0h]
  __int64 v69; // [rsp+3F8h] [rbp+2F8h]
  __int16 *v70; // [rsp+400h] [rbp+300h]
  __int64 v71; // [rsp+408h] [rbp+308h]
  __int16 *v72; // [rsp+410h] [rbp+310h]
  __int64 v73; // [rsp+418h] [rbp+318h]
  __int16 *v74; // [rsp+420h] [rbp+320h]
  __int64 v75; // [rsp+428h] [rbp+328h]
  struct _EVENT_DATA_DESCRIPTOR v76; // [rsp+430h] [rbp+330h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v77; // [rsp+440h] [rbp+340h] BYREF
  char *v78; // [rsp+450h] [rbp+350h]
  __int64 v79; // [rsp+458h] [rbp+358h]
  char *v80; // [rsp+460h] [rbp+360h]
  __int64 v81; // [rsp+468h] [rbp+368h]
  unsigned int *v82; // [rsp+470h] [rbp+370h]
  __int64 v83; // [rsp+478h] [rbp+378h]

  v25 = 0;
  v26 = 0;
  v31 = 0;
  v27 = 0;
  v6 = 0;
  v29 = 0;
  v7 = 0;
  v30 = 0;
  v28 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0u;
  v35 = 0u;
  memset_0(v36, 0, 0x208u);
  if ( a4 )
  {
    v9 = *((_WORD *)a4 + 152);
    if ( v9 == 6 || v9 == 17 )
    {
      psz = 0;
      FwPortsToString((struct _tag_FW_CS_RULE *)((char *)a4 + 256), &psz);
      v6 = SysAllocString(psz);
      FwFree(psz);
      FwPortsToString((struct _tag_FW_CS_RULE *)((char *)a4 + 280), &psz);
      v7 = SysAllocString(psz);
      FwFree(psz);
    }
    GetOpenPortorAuthAppAddrAsString((char *)a4 + 48, &v25, 1);
    GetOpenPortorAuthAppAddrAsString((char *)a4 + 120, &v26, 1);
  }
  else
  {
    a4 = (struct _tag_FW_CS_RULE *)v36;
  }
  FwSerializeStringEventParam(&v37, *((const unsigned __int16 **)a4 + 2));
  FwSerializeStringEventParam(&v38, *((const unsigned __int16 **)a4 + 3));
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
  v40 = 4;
  v39 = (char *)a4 + 368;
  v10 = *((_WORD *)a4 + 170) & 1;
  v42 = 2;
  v31 = v10;
  v44 = 2;
  v43 = (char *)a4 + 304;
  v41 = &v31;
  FwSerializeStringEventParam(&v45, v6);
  FwSerializeStringEventParam(&v46, v7);
  v11 = htonl(*((_DWORD *)a4 + 53));
  v12 = *(_OWORD *)((char *)a4 + 216);
  v13 = *((_DWORD *)a4 + 58);
  v32 = v11;
  v47 = &v32;
  v49 = &v34;
  v48 = 4;
  v34 = v12;
  v50 = 16;
  v14 = htonl(v13);
  v15 = *(_OWORD *)((char *)a4 + 236);
  v16 = (const unsigned __int16 *)*((_QWORD *)a4 + 39);
  v33 = v14;
  v51 = &v33;
  v53 = &v35;
  v52 = 4;
  v35 = v15;
  v54 = 16;
  FwSerializeStringEventParam(&v55, v16);
  FwSerializeStringEventParam(&v56, *((const unsigned __int16 **)a4 + 41));
  FwSerializeStringEventParam(&v57, *((const unsigned __int16 **)a4 + 40));
  v58 = (char *)a4 + 336;
  v59 = 4;
  v60 = (char *)a4 + 40;
  v61 = 4;
  FwSerializeStringEventParam(&v62, v25);
  FwSerializeStringEventParam(&v63, v26);
  FwSerializeStringEventParam(&v64, *((const unsigned __int16 **)a4 + 49));
  FwSerializeStringEventParam(&v65, *((const unsigned __int16 **)a4 + 43));
  v69 = 2;
  v17 = (*((_BYTE *)a4 + 340) & 2) == 0;
  v67 = 2;
  v27 = !v17;
  v68 = &v27;
  v18 = (*((_BYTE *)a4 + 340) & 0x20) != 0;
  v66 = (char *)a4 + 340;
  v17 = (*((_BYTE *)a4 + 340) & 8) == 0;
  v28 = v18;
  v70 = &v28;
  v19 = !v17;
  v71 = 2;
  v17 = (*((_BYTE *)a4 + 340) & 0x10) == 0;
  v29 = v19;
  v72 = &v29;
  v73 = 2;
  v30 = !v17;
  v75 = 2;
  v74 = &v30;
  FwSerializeSIDEventParam(&v76, a2);
  FwSerializeStringEventParam(&v77, a3);
  v79 = 2;
  v78 = (char *)a4 + 8;
  v81 = 4;
  v80 = (char *)a4 + 384;
  v83 = 4;
  v82 = &a5;
  v20 = FwLogEvent(a1, 0x1Eu, &v37);
  if ( v6 )
    SysFreeString(v6);
  if ( v7 )
    SysFreeString(v7);
  FwFree(v25);
  FwFree(v26);
  return v20;
}

```

## disassembly

```asm
0x18008f92c  push    rbp
0x18008f92e  push    rbx
0x18008f92f  push    rsi
0x18008f930  push    rdi
0x18008f931  push    r12
0x18008f933  push    r13
0x18008f935  push    r14
0x18008f937  push    r15
0x18008f939  lea     rbp, [rsp-398h]
0x18008f941  sub     rsp, 498h
0x18008f948  mov     rax, cs:__security_cookie
0x18008f94f  xor     rax, rsp
0x18008f952  mov     [rbp+3D0h+var_50], rax
0x18008f959  xor     r13d, r13d
0x18008f95c  mov     [rsp+4D0h+var_4A8], r8
0x18008f961  xor     eax, eax
0x18008f963  mov     [rsp+4D0h+var_4B0], rdx
0x18008f968  mov     r12, rcx
0x18008f96b  mov     [rsp+4D0h+var_498], r13
0x18008f970  xor     edx, edx; Val
0x18008f972  mov     [rsp+4D0h+var_490], r13
0x18008f977  mov     r8d, 208h; Size
0x18008f97d  mov     [rsp+4D0h+var_478], r13w
0x18008f983  lea     rcx, [rbp+3D0h+var_440]; void *
0x18008f987  mov     [rsp+4D0h+var_488], r13w
0x18008f98d  mov     esi, r13d
0x18008f990  mov     [rsp+4D0h+var_480], r13w
0x18008f996  mov     edi, r13d
0x18008f999  mov     [rsp+4D0h+var_47C], r13w
0x18008f99f  mov     [rsp+4D0h+var_484], r13w
0x18008f9a5  mov     rbx, r9
0x18008f9a8  mov     [rsp+4D0h+var_474], r13d
0x18008f9ad  mov     [rsp+4D0h+var_470], r13d
0x18008f9b2  mov     byte ptr [rsp+4D0h+var_468], r13b
0x18008f9b7  mov     qword ptr [rsp+4D0h+var_468+1], rax
0x18008f9bc  mov     dword ptr [rsp+4D0h+var_468+9], eax
0x18008f9c0  mov     word ptr [rsp+4D0h+var_468+0Dh], ax
0x18008f9c5  mov     byte ptr [rsp+4D0h+var_468+0Fh], al
0x18008f9c9  mov     byte ptr [rsp+4D0h+var_458], r13b
0x18008f9ce  mov     qword ptr [rsp+4D0h+var_458+1], rax
0x18008f9d3  mov     dword ptr [rbp+3D0h+var_458+9], eax
0x18008f9d6  mov     word ptr [rbp+3D0h+var_458+0Dh], ax
0x18008f9da  mov     byte ptr [rbp+3D0h+var_458+0Fh], al
0x18008f9dd  call    memset_0
0x18008f9e2  lea     r14d, [r13+1]
0x18008f9e6  test    rbx, rbx
0x18008f9e9  jz      loc_18008FAB3
0x18008f9ef  movzx   eax, word ptr [rbx+130h]
0x18008f9f6  cmp     ax, 6
0x18008f9fa  jz      short loc_18008FA02
0x18008f9fc  cmp     ax, 11h
0x18008fa00  jnz     short loc_18008FA81
0x18008fa02  lea     rcx, [rbx+100h]
0x18008fa09  mov     [rsp+4D0h+psz], r13
0x18008fa0e  lea     rdx, [rsp+4D0h+psz]
0x18008fa13  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x18008fa1a  nop     dword ptr [rax+rax+00h]
0x18008fa1f  mov     rcx, [rsp+4D0h+psz]; psz
0x18008fa24  call    cs:__imp_SysAllocString
0x18008fa2b  nop     dword ptr [rax+rax+00h]
0x18008fa30  mov     rcx, [rsp+4D0h+psz]
0x18008fa35  mov     rsi, rax
0x18008fa38  call    cs:__imp_FwFree
0x18008fa3f  nop     dword ptr [rax+rax+00h]
0x18008fa44  lea     rcx, [rbx+118h]
0x18008fa4b  lea     rdx, [rsp+4D0h+psz]
0x18008fa50  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x18008fa57  nop     dword ptr [rax+rax+00h]
0x18008fa5c  mov     rcx, [rsp+4D0h+psz]; psz
0x18008fa61  call    cs:__imp_SysAllocString
0x18008fa68  nop     dword ptr [rax+rax+00h]
0x18008fa6d  mov     rcx, [rsp+4D0h+psz]
0x18008fa72  mov     rdi, rax
0x18008fa75  call    cs:__imp_FwFree
0x18008fa7c  nop     dword ptr [rax+rax+00h]
0x18008fa81  lea     rcx, [rbx+30h]
0x18008fa85  mov     r8d, r14d
0x18008fa88  lea     rdx, [rsp+4D0h+var_498]
0x18008fa8d  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18008fa94  nop     dword ptr [rax+rax+00h]
0x18008fa99  lea     rcx, [rbx+78h]
0x18008fa9d  mov     r8d, r14d
0x18008faa0  lea     rdx, [rsp+4D0h+var_490]
0x18008faa5  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18008faac  nop     dword ptr [rax+rax+00h]
0x18008fab1  jmp     short loc_18008FAB7
0x18008fab3  lea     rbx, [rbp+3D0h+var_440]
0x18008fab7  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18008fabb  lea     rcx, [rbp+3D0h+var_230]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fac2  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fac7  mov     rdx, [rbx+18h]; unsigned __int16 *
0x18008facb  lea     rcx, [rbp+3D0h+var_220]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fad2  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fad7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18008fade  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18008fae3  lea     rdx, [rbx+170h]
0x18008faea  mov     [rbp+3D0h+var_208], 4
0x18008faf5  mov     [rbp+3D0h+var_210], rdx
0x18008fafc  lea     r15, [rbx+154h]
0x18008fb03  movzx   ecx, word ptr [r15]
0x18008fb07  mov     r13d, 2
0x18008fb0d  and     cx, r14w
0x18008fb11  mov     [rbp+3D0h+var_1F8], r13
0x18008fb18  mov     [rsp+4D0h+var_478], cx
0x18008fb1d  test    al, al
0x18008fb1f  lea     rcx, [rbx+130h]
0x18008fb26  mov     [rbp+3D0h+var_1E8], r13
0x18008fb2d  mov     [rbp+3D0h+var_1F0], rcx
0x18008fb34  lea     rax, [rsp+4D0h+var_478]
0x18008fb39  lea     rcx, [rbp+3D0h+var_1E0]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fb40  mov     [rbp+3D0h+var_200], rax
0x18008fb47  mov     rdx, rsi; unsigned __int16 *
0x18008fb4a  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fb4f  lea     rcx, [rbp+3D0h+var_1D0]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fb56  mov     rdx, rdi; unsigned __int16 *
0x18008fb59  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fb5e  mov     ecx, [rbx+0D4h]; hostlong
0x18008fb64  call    cs:__imp_htonl
0x18008fb6b  nop     dword ptr [rax+rax+00h]
0x18008fb70  movups  xmm0, xmmword ptr [rbx+0D8h]
0x18008fb77  mov     ecx, [rbx+0E8h]; hostlong
0x18008fb7d  mov     [rsp+4D0h+var_474], eax
0x18008fb81  lea     rax, [rsp+4D0h+var_474]
0x18008fb86  mov     [rbp+3D0h+var_1C0], rax
0x18008fb8d  lea     rax, [rsp+4D0h+var_468]
0x18008fb92  mov     [rbp+3D0h+var_1B0], rax
0x18008fb99  mov     [rbp+3D0h+var_1B8], 4
0x18008fba4  movdqu  [rsp+4D0h+var_468], xmm0
0x18008fbaa  mov     [rbp+3D0h+var_1A8], 10h
0x18008fbb5  call    cs:__imp_htonl
0x18008fbbc  nop     dword ptr [rax+rax+00h]
0x18008fbc1  movups  xmm0, xmmword ptr [rbx+0ECh]
0x18008fbc8  mov     rdx, [rbx+138h]; unsigned __int16 *
0x18008fbcf  lea     rcx, [rbp+3D0h+var_180]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fbd6  mov     [rsp+4D0h+var_470], eax
0x18008fbda  lea     rax, [rsp+4D0h+var_470]
0x18008fbdf  mov     [rbp+3D0h+var_1A0], rax
0x18008fbe6  lea     rax, [rsp+4D0h+var_458]
0x18008fbeb  mov     [rbp+3D0h+var_190], rax
0x18008fbf2  mov     [rbp+3D0h+var_198], 4
0x18008fbfd  movdqu  [rsp+4D0h+var_458], xmm0
0x18008fc03  mov     [rbp+3D0h+var_188], 10h
0x18008fc0e  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fc13  mov     rdx, [rbx+148h]; unsigned __int16 *
0x18008fc1a  lea     rcx, [rbp+3D0h+var_170]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fc21  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fc26  mov     rdx, [rbx+140h]; unsigned __int16 *
0x18008fc2d  lea     rcx, [rbp+3D0h+var_160]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fc34  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fc39  mov     rdx, [rsp+4D0h+var_498]; unsigned __int16 *
0x18008fc3e  lea     rax, [rbx+150h]
0x18008fc45  mov     [rbp+3D0h+var_150], rax
0x18008fc4c  lea     rcx, [rbp+3D0h+var_130]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fc53  lea     rax, [rbx+28h]
0x18008fc57  mov     [rbp+3D0h+var_148], 4
0x18008fc62  mov     [rbp+3D0h+var_140], rax
0x18008fc69  mov     [rbp+3D0h+var_138], 4
0x18008fc74  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fc79  mov     rdx, [rsp+4D0h+var_490]; unsigned __int16 *
0x18008fc7e  lea     rcx, [rbp+3D0h+var_120]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fc85  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fc8a  mov     rdx, [rbx+188h]; unsigned __int16 *
0x18008fc91  lea     rcx, [rbp+3D0h+var_110]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fc98  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fc9d  mov     rdx, [rbx+158h]; unsigned __int16 *
0x18008fca4  lea     rcx, [rbp+3D0h+var_100]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fcab  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fcb0  xor     ecx, ecx
0x18008fcb2  mov     [rbp+3D0h+var_D8], r13
0x18008fcb9  test    [r15], r13b
0x18008fcbc  mov     eax, ecx
0x18008fcbe  mov     [rbp+3D0h+var_E8], r13
0x18008fcc5  setnbe  al
0x18008fcc8  mov     [rsp+4D0h+var_488], ax
0x18008fccd  lea     rax, [rsp+4D0h+var_488]
0x18008fcd2  mov     [rbp+3D0h+var_E0], rax
0x18008fcd9  test    byte ptr [r15], 20h
0x18008fcdd  mov     eax, ecx
0x18008fcdf  mov     rdx, [rsp+4D0h+var_4B0]; void *
0x18008fce4  setnbe  al
0x18008fce7  mov     [rbp+3D0h+var_F0], r15
0x18008fcee  test    byte ptr [r15], 8
0x18008fcf2  mov     [rsp+4D0h+var_484], ax
0x18008fcf7  lea     rax, [rsp+4D0h+var_484]
0x18008fcfc  mov     [rbp+3D0h+var_D0], rax
0x18008fd03  mov     eax, ecx
0x18008fd05  setnbe  al
0x18008fd08  mov     [rbp+3D0h+var_C8], r13
0x18008fd0f  test    byte ptr [r15], 10h
0x18008fd13  mov     [rsp+4D0h+var_480], ax
0x18008fd18  lea     rax, [rsp+4D0h+var_480]
0x18008fd1d  mov     [rbp+3D0h+var_C0], rax
0x18008fd24  mov     eax, ecx
0x18008fd26  setnbe  al
0x18008fd29  mov     [rbp+3D0h+var_B8], r13
0x18008fd30  mov     [rsp+4D0h+var_47C], ax
0x18008fd35  lea     rcx, [rbp+3D0h+var_A0]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fd3c  lea     rax, [rsp+4D0h+var_47C]
0x18008fd41  mov     [rbp+3D0h+var_A8], r13
0x18008fd48  mov     [rbp+3D0h+var_B0], rax
0x18008fd4f  call    ?FwSerializeSIDEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEAX@Z; FwSerializeSIDEventParam(_EVENT_DATA_DESCRIPTOR *,void *)
0x18008fd54  mov     rdx, [rsp+4D0h+var_4A8]; unsigned __int16 *
0x18008fd59  lea     rcx, [rbp+3D0h+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fd60  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008fd65  lea     rax, [rbx+8]
0x18008fd69  mov     [rbp+3D0h+var_78], r13
0x18008fd70  mov     [rbp+3D0h+var_80], rax
0x18008fd77  lea     r8, [rbp+3D0h+var_230]; struct _EVENT_DATA_DESCRIPTOR *
0x18008fd7e  lea     rax, [rbx+180h]
0x18008fd85  mov     [rbp+3D0h+var_68], 4
0x18008fd90  mov     [rbp+3D0h+var_70], rax
0x18008fd97  lea     edx, [r13+1Ch]; unsigned int
0x18008fd9b  lea     rax, [rbp+3D0h+arg_20]
0x18008fda2  mov     [rbp+3D0h+var_58], 4
0x18008fdad  mov     rcx, r12; struct _EVENT_DESCRIPTOR *
0x18008fdb0  mov     [rbp+3D0h+var_60], rax
0x18008fdb7  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18008fdbc  mov     ebx, eax
0x18008fdbe  test    rsi, rsi
0x18008fdc1  jz      short loc_18008FDD2
0x18008fdc3  mov     rcx, rsi; bstrString
0x18008fdc6  call    cs:__imp_SysFreeString
0x18008fdcd  nop     dword ptr [rax+rax+00h]
0x18008fdd2  test    rdi, rdi
0x18008fdd5  jz      short loc_18008FDE6
0x18008fdd7  mov     rcx, rdi; bstrString
0x18008fdda  call    cs:__imp_SysFreeString
0x18008fde1  nop     dword ptr [rax+rax+00h]
0x18008fde6  mov     rcx, [rsp+4D0h+var_498]
0x18008fdeb  call    cs:__imp_FwFree
0x18008fdf2  nop     dword ptr [rax+rax+00h]
0x18008fdf7  mov     rcx, [rsp+4D0h+var_490]
0x18008fdfc  call    cs:__imp_FwFree
0x18008fe03  nop     dword ptr [rax+rax+00h]
0x18008fe08  mov     eax, ebx
0x18008fe0a  mov     rcx, [rbp+3D0h+var_50]
0x18008fe11  xor     rcx, rsp; StackCookie
0x18008fe14  call    __security_check_cookie
0x18008fe19  add     rsp, 498h
0x18008fe20  pop     r15
0x18008fe22  pop     r14
0x18008fe24  pop     r13
0x18008fe26  pop     r12
0x18008fe28  pop     rdi
0x18008fe29  pop     rsi
0x18008fe2a  pop     rbx
0x18008fe2b  pop     rbp
0x18008fe2c  retn
```
