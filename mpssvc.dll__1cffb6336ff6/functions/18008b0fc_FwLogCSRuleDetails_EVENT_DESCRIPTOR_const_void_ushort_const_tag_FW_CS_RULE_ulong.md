# FwLogCSRuleDetails(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_CS_RULE *,ulong)

- ea: `0x18008b0fc`
- end: `0x18008b5a9`
- name: `?FwLogCSRuleDetails@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGPEAU_tag_FW_CS_RULE@@K@Z`
- size: `1197`
- prototype: `unsigned int __usercall@<eax>(const struct _EVENT_DESCRIPTOR *@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, struct _tag_FW_CS_RULE *@<r9>, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18006de10`
- `0x18006ed1c`

## callees

- `0x180029b48`
- `0x180049d98`
- `0x180067fc8`
- `0x180068034`
- `0x18006f520`
- `0x18006ffc8`
- `0x18008b0fc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008b1ee`
- `OLEAUT32!__imp_SysAllocString` at `0x18008b219`
- `OLEAUT32!__imp_SysAllocString` at `0x18008b1ee`
- `OLEAUT32!__imp_SysAllocString` at `0x18008b219`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b55a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b568`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b55a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b568`
- `WS2_32!__imp_htonl` at `0x18008b304`
- `WS2_32!__imp_htonl` at `0x18008b34f`
- `WS2_32!__imp_htonl` at `0x18008b304`
- `WS2_32!__imp_htonl` at `0x18008b34f`
- `fwbase!FwPortsToString` at `0x18008b1e3`
- `fwbase!FwPortsToString` at `0x18008b20e`
- `fwbase!FwPortsToString` at `0x18008b1e3`
- `fwbase!FwPortsToString` at `0x18008b20e`
- `fwbase!FwFree` at `0x18008b1fc`
- `fwbase!FwFree` at `0x18008b227`
- `fwbase!FwFree` at `0x18008b573`
- `fwbase!FwFree` at `0x18008b57e`
- `fwbase!FwFree` at `0x18008b1fc`
- `fwbase!FwFree` at `0x18008b227`
- `fwbase!FwFree` at `0x18008b573`
- `fwbase!FwFree` at `0x18008b57e`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008b239`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008b24b`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008b239`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008b24b`

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
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
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
0x18008b0fc  push    rbp
0x18008b0fe  push    rbx
0x18008b0ff  push    rsi
0x18008b100  push    rdi
0x18008b101  push    r12
0x18008b103  push    r13
0x18008b105  push    r14
0x18008b107  push    r15
0x18008b109  lea     rbp, [rsp-398h]
0x18008b111  sub     rsp, 498h
0x18008b118  mov     rax, cs:__security_cookie
0x18008b11f  xor     rax, rsp
0x18008b122  mov     [rbp+3D0h+var_50], rax
0x18008b129  xor     r13d, r13d
0x18008b12c  mov     [rsp+4D0h+var_4A8], r8
0x18008b131  xor     eax, eax
0x18008b133  mov     [rsp+4D0h+var_4B0], rdx
0x18008b138  mov     r12, rcx
0x18008b13b  mov     [rsp+4D0h+var_498], r13
0x18008b140  xor     edx, edx; Val
0x18008b142  mov     [rsp+4D0h+var_490], r13
0x18008b147  mov     r8d, 208h; Size
0x18008b14d  mov     [rsp+4D0h+var_478], r13w
0x18008b153  lea     rcx, [rbp+3D0h+var_440]; void *
0x18008b157  mov     [rsp+4D0h+var_488], r13w
0x18008b15d  mov     esi, r13d
0x18008b160  mov     [rsp+4D0h+var_480], r13w
0x18008b166  mov     edi, r13d
0x18008b169  mov     [rsp+4D0h+var_47C], r13w
0x18008b16f  mov     [rsp+4D0h+var_484], r13w
0x18008b175  mov     rbx, r9
0x18008b178  mov     [rsp+4D0h+var_474], r13d
0x18008b17d  mov     [rsp+4D0h+var_470], r13d
0x18008b182  mov     byte ptr [rsp+4D0h+var_468], r13b
0x18008b187  mov     qword ptr [rsp+4D0h+var_468+1], rax
0x18008b18c  mov     dword ptr [rsp+4D0h+var_468+9], eax
0x18008b190  mov     word ptr [rsp+4D0h+var_468+0Dh], ax
0x18008b195  mov     byte ptr [rsp+4D0h+var_468+0Fh], al
0x18008b199  mov     byte ptr [rsp+4D0h+var_458], r13b
0x18008b19e  mov     qword ptr [rsp+4D0h+var_458+1], rax
0x18008b1a3  mov     dword ptr [rbp+3D0h+var_458+9], eax
0x18008b1a6  mov     word ptr [rbp+3D0h+var_458+0Dh], ax
0x18008b1aa  mov     byte ptr [rbp+3D0h+var_458+0Fh], al
0x18008b1ad  call    memset_0
0x18008b1b2  lea     r14d, [r13+1]
0x18008b1b6  test    rbx, rbx
0x18008b1b9  jz      loc_18008B253
0x18008b1bf  movzx   eax, word ptr [rbx+130h]
0x18008b1c6  cmp     ax, 6
0x18008b1ca  jz      short loc_18008B1D2
0x18008b1cc  cmp     ax, 11h
0x18008b1d0  jnz     short loc_18008B22D
0x18008b1d2  lea     rcx, [rbx+100h]
0x18008b1d9  mov     [rsp+4D0h+psz], r13
0x18008b1de  lea     rdx, [rsp+4D0h+psz]
0x18008b1e3  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x18008b1e9  mov     rcx, [rsp+4D0h+psz]; psz
0x18008b1ee  call    cs:__imp_SysAllocString
0x18008b1f4  mov     rcx, [rsp+4D0h+psz]
0x18008b1f9  mov     rsi, rax
0x18008b1fc  call    cs:__imp_FwFree
0x18008b202  lea     rcx, [rbx+118h]
0x18008b209  lea     rdx, [rsp+4D0h+psz]
0x18008b20e  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x18008b214  mov     rcx, [rsp+4D0h+psz]; psz
0x18008b219  call    cs:__imp_SysAllocString
0x18008b21f  mov     rcx, [rsp+4D0h+psz]
0x18008b224  mov     rdi, rax
0x18008b227  call    cs:__imp_FwFree
0x18008b22d  lea     rcx, [rbx+30h]
0x18008b231  mov     r8d, r14d
0x18008b234  lea     rdx, [rsp+4D0h+var_498]
0x18008b239  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18008b23f  lea     rcx, [rbx+78h]
0x18008b243  mov     r8d, r14d
0x18008b246  lea     rdx, [rsp+4D0h+var_490]
0x18008b24b  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18008b251  jmp     short loc_18008B257
0x18008b253  lea     rbx, [rbp+3D0h+var_440]
0x18008b257  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18008b25b  lea     rcx, [rbp+3D0h+var_230]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b262  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b267  mov     rdx, [rbx+18h]; unsigned __int16 *
0x18008b26b  lea     rcx, [rbp+3D0h+var_220]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b272  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b277  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18008b27e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18008b283  lea     rdx, [rbx+170h]
0x18008b28a  mov     [rbp+3D0h+var_208], 4
0x18008b295  mov     [rbp+3D0h+var_210], rdx
0x18008b29c  lea     r15, [rbx+154h]
0x18008b2a3  movzx   ecx, word ptr [r15]
0x18008b2a7  mov     r13d, 2
0x18008b2ad  and     cx, r14w
0x18008b2b1  mov     [rbp+3D0h+var_1F8], r13
0x18008b2b8  mov     [rsp+4D0h+var_478], cx
0x18008b2bd  test    al, al
0x18008b2bf  lea     rcx, [rbx+130h]
0x18008b2c6  mov     [rbp+3D0h+var_1E8], r13
0x18008b2cd  mov     [rbp+3D0h+var_1F0], rcx
0x18008b2d4  lea     rax, [rsp+4D0h+var_478]
0x18008b2d9  lea     rcx, [rbp+3D0h+var_1E0]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b2e0  mov     [rbp+3D0h+var_200], rax
0x18008b2e7  mov     rdx, rsi; unsigned __int16 *
0x18008b2ea  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b2ef  lea     rcx, [rbp+3D0h+var_1D0]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b2f6  mov     rdx, rdi; unsigned __int16 *
0x18008b2f9  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b2fe  mov     ecx, [rbx+0D4h]; hostlong
0x18008b304  call    cs:__imp_htonl
0x18008b30a  movups  xmm0, xmmword ptr [rbx+0D8h]
0x18008b311  mov     ecx, [rbx+0E8h]; hostlong
0x18008b317  mov     [rsp+4D0h+var_474], eax
0x18008b31b  lea     rax, [rsp+4D0h+var_474]
0x18008b320  mov     [rbp+3D0h+var_1C0], rax
0x18008b327  lea     rax, [rsp+4D0h+var_468]
0x18008b32c  mov     [rbp+3D0h+var_1B0], rax
0x18008b333  mov     [rbp+3D0h+var_1B8], 4
0x18008b33e  movdqu  [rsp+4D0h+var_468], xmm0
0x18008b344  mov     [rbp+3D0h+var_1A8], 10h
0x18008b34f  call    cs:__imp_htonl
0x18008b355  movups  xmm0, xmmword ptr [rbx+0ECh]
0x18008b35c  mov     rdx, [rbx+138h]; unsigned __int16 *
0x18008b363  lea     rcx, [rbp+3D0h+var_180]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b36a  mov     [rsp+4D0h+var_470], eax
0x18008b36e  lea     rax, [rsp+4D0h+var_470]
0x18008b373  mov     [rbp+3D0h+var_1A0], rax
0x18008b37a  lea     rax, [rsp+4D0h+var_458]
0x18008b37f  mov     [rbp+3D0h+var_190], rax
0x18008b386  mov     [rbp+3D0h+var_198], 4
0x18008b391  movdqu  [rsp+4D0h+var_458], xmm0
0x18008b397  mov     [rbp+3D0h+var_188], 10h
0x18008b3a2  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b3a7  mov     rdx, [rbx+148h]; unsigned __int16 *
0x18008b3ae  lea     rcx, [rbp+3D0h+var_170]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b3b5  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b3ba  mov     rdx, [rbx+140h]; unsigned __int16 *
0x18008b3c1  lea     rcx, [rbp+3D0h+var_160]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b3c8  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b3cd  mov     rdx, [rsp+4D0h+var_498]; unsigned __int16 *
0x18008b3d2  lea     rax, [rbx+150h]
0x18008b3d9  mov     [rbp+3D0h+var_150], rax
0x18008b3e0  lea     rcx, [rbp+3D0h+var_130]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b3e7  lea     rax, [rbx+28h]
0x18008b3eb  mov     [rbp+3D0h+var_148], 4
0x18008b3f6  mov     [rbp+3D0h+var_140], rax
0x18008b3fd  mov     [rbp+3D0h+var_138], 4
0x18008b408  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b40d  mov     rdx, [rsp+4D0h+var_490]; unsigned __int16 *
0x18008b412  lea     rcx, [rbp+3D0h+var_120]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b419  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b41e  mov     rdx, [rbx+188h]; unsigned __int16 *
0x18008b425  lea     rcx, [rbp+3D0h+var_110]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b42c  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b431  mov     rdx, [rbx+158h]; unsigned __int16 *
0x18008b438  lea     rcx, [rbp+3D0h+var_100]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b43f  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b444  xor     ecx, ecx
0x18008b446  mov     [rbp+3D0h+var_D8], r13
0x18008b44d  test    [r15], r13b
0x18008b450  mov     eax, ecx
0x18008b452  mov     [rbp+3D0h+var_E8], r13
0x18008b459  setnbe  al
0x18008b45c  mov     [rsp+4D0h+var_488], ax
0x18008b461  lea     rax, [rsp+4D0h+var_488]
0x18008b466  mov     [rbp+3D0h+var_E0], rax
0x18008b46d  test    byte ptr [r15], 20h
0x18008b471  mov     eax, ecx
0x18008b473  mov     rdx, [rsp+4D0h+var_4B0]; void *
0x18008b478  setnbe  al
0x18008b47b  mov     [rbp+3D0h+var_F0], r15
0x18008b482  test    byte ptr [r15], 8
0x18008b486  mov     [rsp+4D0h+var_484], ax
0x18008b48b  lea     rax, [rsp+4D0h+var_484]
0x18008b490  mov     [rbp+3D0h+var_D0], rax
0x18008b497  mov     eax, ecx
0x18008b499  setnbe  al
0x18008b49c  mov     [rbp+3D0h+var_C8], r13
0x18008b4a3  test    byte ptr [r15], 10h
0x18008b4a7  mov     [rsp+4D0h+var_480], ax
0x18008b4ac  lea     rax, [rsp+4D0h+var_480]
0x18008b4b1  mov     [rbp+3D0h+var_C0], rax
0x18008b4b8  mov     eax, ecx
0x18008b4ba  setnbe  al
0x18008b4bd  mov     [rbp+3D0h+var_B8], r13
0x18008b4c4  mov     [rsp+4D0h+var_47C], ax
0x18008b4c9  lea     rcx, [rbp+3D0h+var_A0]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b4d0  lea     rax, [rsp+4D0h+var_47C]
0x18008b4d5  mov     [rbp+3D0h+var_A8], r13
0x18008b4dc  mov     [rbp+3D0h+var_B0], rax
0x18008b4e3  call    ?FwSerializeSIDEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEAX@Z; FwSerializeSIDEventParam(_EVENT_DATA_DESCRIPTOR *,void *)
0x18008b4e8  mov     rdx, [rsp+4D0h+var_4A8]; unsigned __int16 *
0x18008b4ed  lea     rcx, [rbp+3D0h+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b4f4  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b4f9  lea     rax, [rbx+8]
0x18008b4fd  mov     [rbp+3D0h+var_78], r13
0x18008b504  mov     [rbp+3D0h+var_80], rax
0x18008b50b  lea     r8, [rbp+3D0h+var_230]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b512  lea     rax, [rbx+180h]
0x18008b519  mov     [rbp+3D0h+var_68], 4
0x18008b524  mov     [rbp+3D0h+var_70], rax
0x18008b52b  lea     edx, [r13+1Ch]; unsigned int
0x18008b52f  lea     rax, [rbp+3D0h+arg_20]
0x18008b536  mov     [rbp+3D0h+var_58], 4
0x18008b541  mov     rcx, r12; struct _EVENT_DESCRIPTOR *
0x18008b544  mov     [rbp+3D0h+var_60], rax
0x18008b54b  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18008b550  mov     ebx, eax
0x18008b552  test    rsi, rsi
0x18008b555  jz      short loc_18008B560
0x18008b557  mov     rcx, rsi; bstrString
0x18008b55a  call    cs:__imp_SysFreeString
0x18008b560  test    rdi, rdi
0x18008b563  jz      short loc_18008B56E
0x18008b565  mov     rcx, rdi; bstrString
0x18008b568  call    cs:__imp_SysFreeString
0x18008b56e  mov     rcx, [rsp+4D0h+var_498]
0x18008b573  call    cs:__imp_FwFree
0x18008b579  mov     rcx, [rsp+4D0h+var_490]
0x18008b57e  call    cs:__imp_FwFree
0x18008b584  mov     eax, ebx
0x18008b586  mov     rcx, [rbp+3D0h+var_50]
0x18008b58d  xor     rcx, rsp; StackCookie
0x18008b590  call    __security_check_cookie
0x18008b595  add     rsp, 498h
0x18008b59c  pop     r15
0x18008b59e  pop     r14
0x18008b5a0  pop     r13
0x18008b5a2  pop     r12
0x18008b5a4  pop     rdi
0x18008b5a5  pop     rsi
0x18008b5a6  pop     rbx
0x18008b5a7  pop     rbp
0x18008b5a8  retn
```
