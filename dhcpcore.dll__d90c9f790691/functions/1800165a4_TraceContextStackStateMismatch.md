# TraceContextStackStateMismatch

- ea: `0x1800165a4`
- end: `0x180016a27`
- name: `TraceContextStackStateMismatch`
- size: `1155`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001568c`

## callees

- `0x18000f98c`
- `0x180015668`
- `0x1800165a4`
- `0x18001cef0`
- `0x18004a310`
- `0x18004e0c4`

## string_xrefs

- `0x18001661b`: `Compartment ID`

## pseudocode

```c
char __fastcall TraceContextStackStateMismatch(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        unsigned int a14,
        int a15,
        int a16)
{
  const char *v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // r10d
  int v20; // r11d
  __int64 i; // rbx
  int v23; // [rsp+30h] [rbp-278h] BYREF
  int v24; // [rsp+34h] [rbp-274h] BYREF
  int v25; // [rsp+38h] [rbp-270h] BYREF
  int v26; // [rsp+3Ch] [rbp-26Ch] BYREF
  int v27; // [rsp+40h] [rbp-268h] BYREF
  int v28; // [rsp+44h] [rbp-264h] BYREF
  int v29; // [rsp+48h] [rbp-260h] BYREF
  int v30; // [rsp+4Ch] [rbp-25Ch] BYREF
  int v31; // [rsp+50h] [rbp-258h] BYREF
  int v32; // [rsp+54h] [rbp-254h] BYREF
  int v33; // [rsp+58h] [rbp-250h] BYREF
  int v34; // [rsp+5Ch] [rbp-24Ch] BYREF
  unsigned int v35; // [rsp+60h] [rbp-248h] BYREF
  int v36; // [rsp+64h] [rbp-244h] BYREF
  int v37; // [rsp+68h] [rbp-240h] BYREF
  __int64 v38; // [rsp+70h] [rbp-238h] BYREF
  _DWORD v39[2]; // [rsp+80h] [rbp-228h]
  const char *v40; // [rsp+88h] [rbp-220h]
  int v41; // [rsp+90h] [rbp-218h]
  const char *v42; // [rsp+98h] [rbp-210h]
  int v43; // [rsp+A0h] [rbp-208h]
  const char *v44; // [rsp+A8h] [rbp-200h]
  int v45; // [rsp+B0h] [rbp-1F8h]
  const char *v46; // [rsp+B8h] [rbp-1F0h]
  int v47; // [rsp+C0h] [rbp-1E8h]
  const char *v48; // [rsp+C8h] [rbp-1E0h]
  int v49; // [rsp+D0h] [rbp-1D8h]
  const char *v50; // [rsp+D8h] [rbp-1D0h]
  int v51; // [rsp+E0h] [rbp-1C8h]
  const char *v52; // [rsp+E8h] [rbp-1C0h]
  int v53; // [rsp+F0h] [rbp-1B8h]
  const char *v54; // [rsp+F8h] [rbp-1B0h]
  int v55; // [rsp+100h] [rbp-1A8h]
  const char *v56; // [rsp+108h] [rbp-1A0h]
  int v57; // [rsp+110h] [rbp-198h]
  const char *v58; // [rsp+118h] [rbp-190h]
  int v59; // [rsp+120h] [rbp-188h]
  const char *v60; // [rsp+128h] [rbp-180h]
  int v61; // [rsp+130h] [rbp-178h]
  const char *v62; // [rsp+138h] [rbp-170h]
  char v63[32]; // [rsp+140h] [rbp-168h] BYREF
  int *v64; // [rsp+160h] [rbp-148h]
  __int64 v65; // [rsp+168h] [rbp-140h]
  int *v66; // [rsp+170h] [rbp-138h]
  __int64 v67; // [rsp+178h] [rbp-130h]
  int *v68; // [rsp+180h] [rbp-128h]
  __int64 v69; // [rsp+188h] [rbp-120h]
  int *v70; // [rsp+190h] [rbp-118h]
  __int64 v71; // [rsp+198h] [rbp-110h]
  int *v72; // [rsp+1A0h] [rbp-108h]
  __int64 v73; // [rsp+1A8h] [rbp-100h]
  int *v74; // [rsp+1B0h] [rbp-F8h]
  __int64 v75; // [rsp+1B8h] [rbp-F0h]
  int *v76; // [rsp+1C0h] [rbp-E8h]
  __int64 v77; // [rsp+1C8h] [rbp-E0h]
  int *v78; // [rsp+1D0h] [rbp-D8h]
  __int64 v79; // [rsp+1D8h] [rbp-D0h]
  int *v80; // [rsp+1E0h] [rbp-C8h]
  __int64 v81; // [rsp+1E8h] [rbp-C0h]
  int *v82; // [rsp+1F0h] [rbp-B8h]
  __int64 v83; // [rsp+1F8h] [rbp-B0h]
  int *v84; // [rsp+200h] [rbp-A8h]
  __int64 v85; // [rsp+208h] [rbp-A0h]
  int *v86; // [rsp+210h] [rbp-98h]
  __int64 v87; // [rsp+218h] [rbp-90h]
  int *v88; // [rsp+220h] [rbp-88h]
  __int64 v89; // [rsp+228h] [rbp-80h]
  int *v90; // [rsp+230h] [rbp-78h]
  __int64 v91; // [rsp+238h] [rbp-70h]
  int *v92; // [rsp+240h] [rbp-68h]
  __int64 v93; // [rsp+248h] [rbp-60h]
  __int64 *v94; // [rsp+250h] [rbp-58h]
  __int64 v95; // [rsp+258h] [rbp-50h]

  v40 = "LUID";
  v42 = "Interface index";
  v44 = "Interface GUID";
  v46 = "Compartment ID";
  v48 = "Hardware address type";
  v50 = "Hardware address length";
  v52 = "Hardware address";
  v53 = a9;
  v54 = "Is unidirectional";
  v55 = a10;
  v56 = "NDIS medium";
  v57 = a11;
  v58 = "NDIS physical medium";
  v59 = a12;
  v60 = "IP address state";
  v39[0] = a2;
  v61 = a13;
  v16 = "Randomized epoch";
  v62 = "Randomized epoch";
  v41 = a3;
  v43 = a4;
  v45 = a5;
  v47 = a6;
  v49 = a7;
  v51 = a8;
  if ( !(_DWORD)a1 )
  {
    LOBYTE(v16) = dword_1800610D8;
    if ( (unsigned int)dword_1800610D8 > 5 )
    {
      LOBYTE(v16) = tlgKeywordOn((__int64)&dword_1800610D8, 0x400000000000LL);
      if ( (_BYTE)v16 )
      {
        v23 = v19;
        v64 = &v23;
        v65 = 4;
        v66 = &v24;
        v68 = &v25;
        v70 = &v26;
        v72 = &v27;
        v74 = &v28;
        v76 = &v29;
        v30 = a9;
        v78 = &v30;
        v31 = a10;
        v80 = &v31;
        v32 = a11;
        v82 = &v32;
        v33 = a12;
        v84 = &v33;
        v34 = a13;
        v86 = &v34;
        v88 = (int *)&v35;
        v90 = &v36;
        v92 = &v37;
        v94 = &v38;
        v24 = v20;
        v67 = 4;
        v25 = v18;
        v69 = 4;
        v26 = a5;
        v71 = 4;
        v27 = a6;
        v73 = 4;
        v28 = a7;
        v75 = 4;
        v29 = a8;
        v77 = 4;
        v79 = 4;
        v81 = 4;
        v83 = 4;
        v85 = 4;
        v87 = 4;
        v35 = a14;
        v89 = 4;
        v36 = a15;
        v91 = 4;
        v37 = a16;
        v93 = 4;
        v38 = 0x1000000;
        v95 = 8;
        LOBYTE(v16) = tlgWriteTransfer_EtwEventWriteTransfer(
                        a1,
                        (unsigned __int8 *)word_1800592B2,
                        v17,
                        v18,
                        18,
                        (__int64)v63);
      }
    }
    if ( (byte_180061688 & 2) != 0 )
    {
      LOBYTE(v16) = xmmword_1800616A0;
      for ( i = 0; i != 12; ++i )
      {
        if ( !v39[4 * i] && ((unsigned __int8)v16 & 0x10) != 0 )
        {
          WPP_SF_s(1028, 200, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, (&v40)[2 * i]);
          LOBYTE(v16) = xmmword_1800616A0;
        }
      }
      if ( ((unsigned __int8)v16 & 0x10) != 0 )
        LOBYTE(v16) = WPP_SF_lll(a1, 201, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, a14, a15, a16);
    }
  }
  return (char)v16;
}

```

## disassembly

```asm
0x1800165a4  push    rbx
0x1800165a6  push    rsi
0x1800165a7  push    rdi
0x1800165a8  push    r12
0x1800165aa  push    r13
0x1800165ac  push    r14
0x1800165ae  push    r15
0x1800165b0  sub     rsp, 270h
0x1800165b7  mov     rax, cs:__security_cookie
0x1800165be  xor     rax, rsp
0x1800165c1  mov     [rsp+2A8h+var_48], rax
0x1800165c9  mov     ebx, [rsp+2A8h+arg_20]
0x1800165d0  lea     rax, aLuid; "LUID"
0x1800165d7  mov     r15d, [rsp+2A8h+arg_28]
0x1800165df  mov     r10d, edx
0x1800165e2  mov     r12d, [rsp+2A8h+arg_30]
0x1800165ea  mov     r11d, r8d
0x1800165ed  mov     r13d, [rsp+2A8h+arg_38]
0x1800165f5  mov     [rsp+2A8h+var_220], rax
0x1800165fd  lea     rax, aInterfaceIndex; "Interface index"
0x180016604  mov     [rsp+2A8h+var_210], rax
0x18001660c  lea     rax, aInterfaceGuid; "Interface GUID"
0x180016613  mov     [rsp+2A8h+var_200], rax
0x18001661b  lea     rax, aCompartmentId; "Compartment ID"
0x180016622  mov     [rsp+2A8h+var_1F0], rax
0x18001662a  lea     rax, aHardwareAddres_1; "Hardware address type"
0x180016631  mov     [rsp+2A8h+var_1E0], rax
0x180016639  lea     rax, aHardwareAddres_0; "Hardware address length"
0x180016640  mov     [rsp+2A8h+var_1D0], rax
0x180016648  lea     rax, aHardwareAddres; "Hardware address"
0x18001664f  mov     [rsp+2A8h+var_1C0], rax
0x180016657  mov     eax, [rsp+2A8h+arg_40]
0x18001665e  mov     [rsp+2A8h+var_1B8], eax
0x180016665  lea     rax, aIsUnidirection; "Is unidirectional"
0x18001666c  mov     [rsp+2A8h+var_1B0], rax
0x180016674  mov     eax, [rsp+2A8h+arg_48]
0x18001667b  mov     [rsp+2A8h+var_1A8], eax
0x180016682  lea     rax, aNdisMedium; "NDIS medium"
0x180016689  mov     [rsp+2A8h+var_1A0], rax
0x180016691  mov     eax, [rsp+2A8h+arg_50]
0x180016698  mov     [rsp+2A8h+var_198], eax
0x18001669f  lea     rax, aNdisPhysicalMe; "NDIS physical medium"
0x1800166a6  mov     [rsp+2A8h+var_190], rax
0x1800166ae  mov     eax, [rsp+2A8h+arg_58]
0x1800166b5  mov     [rsp+2A8h+var_188], eax
0x1800166bc  lea     rax, aIpAddressState; "IP address state"
0x1800166c3  mov     [rsp+2A8h+var_180], rax
0x1800166cb  mov     eax, [rsp+2A8h+arg_60]
0x1800166d2  mov     [rsp+2A8h+var_228], edx
0x1800166d9  xor     edx, edx
0x1800166db  mov     [rsp+2A8h+var_178], eax
0x1800166e2  lea     rax, aRandomizedEpoc; "Randomized epoch"
0x1800166e9  mov     [rsp+2A8h+var_170], rax
0x1800166f1  mov     [rsp+2A8h+var_218], r8d
0x1800166f9  mov     [rsp+2A8h+var_208], r9d
0x180016701  mov     [rsp+2A8h+var_1F8], ebx
0x180016708  mov     [rsp+2A8h+var_1E8], r15d
0x180016710  mov     [rsp+2A8h+var_1D8], r12d
0x180016718  mov     [rsp+2A8h+var_1C8], r13d
0x180016720  test    ecx, ecx
0x180016722  jnz     loc_180016A04
0x180016728  mov     eax, cs:dword_1800610D8
0x18001672e  mov     edi, [rsp+2A8h+arg_78]
0x180016735  mov     esi, [rsp+2A8h+arg_70]
0x18001673c  mov     r14d, [rsp+2A8h+arg_68]
0x180016744  cmp     eax, 5
0x180016747  jbe     loc_18001698F
0x18001674d  mov     rdx, 400000000000h
0x180016757  lea     rcx, dword_1800610D8
0x18001675e  call    _tlgKeywordOn
0x180016763  xor     edx, edx
0x180016765  test    al, al
0x180016767  jz      loc_18001698F
0x18001676d  lea     rax, [rsp+2A8h+var_278]
0x180016772  mov     [rsp+2A8h+var_278], r10d
0x180016777  mov     [rsp+2A8h+var_148], rax
0x18001677f  lea     rdx, word_1800592B2
0x180016786  lea     rax, [rsp+2A8h+var_274]
0x18001678b  mov     [rsp+2A8h+var_140], 4
0x180016797  mov     [rsp+2A8h+var_138], rax
0x18001679f  lea     rax, [rsp+2A8h+var_270]
0x1800167a4  mov     [rsp+2A8h+var_128], rax
0x1800167ac  lea     rax, [rsp+2A8h+var_26C]
0x1800167b1  mov     [rsp+2A8h+var_118], rax
0x1800167b9  lea     rax, [rsp+2A8h+var_268]
0x1800167be  mov     [rsp+2A8h+var_108], rax
0x1800167c6  lea     rax, [rsp+2A8h+var_264]
0x1800167cb  mov     [rsp+2A8h+var_F8], rax
0x1800167d3  lea     rax, [rsp+2A8h+var_260]
0x1800167d8  mov     [rsp+2A8h+var_E8], rax
0x1800167e0  mov     eax, [rsp+2A8h+arg_40]
0x1800167e7  mov     [rsp+2A8h+var_25C], eax
0x1800167eb  lea     rax, [rsp+2A8h+var_25C]
0x1800167f0  mov     [rsp+2A8h+var_D8], rax
0x1800167f8  mov     eax, [rsp+2A8h+arg_48]
0x1800167ff  mov     [rsp+2A8h+var_258], eax
0x180016803  lea     rax, [rsp+2A8h+var_258]
0x180016808  mov     [rsp+2A8h+var_C8], rax
0x180016810  mov     eax, [rsp+2A8h+arg_50]
0x180016817  mov     [rsp+2A8h+var_254], eax
0x18001681b  lea     rax, [rsp+2A8h+var_254]
0x180016820  mov     [rsp+2A8h+var_B8], rax
0x180016828  mov     eax, [rsp+2A8h+arg_58]
0x18001682f  mov     [rsp+2A8h+var_250], eax
0x180016833  lea     rax, [rsp+2A8h+var_250]
0x180016838  mov     [rsp+2A8h+var_A8], rax
0x180016840  mov     eax, [rsp+2A8h+arg_60]
0x180016847  mov     [rsp+2A8h+var_24C], eax
0x18001684b  lea     rax, [rsp+2A8h+var_24C]
0x180016850  mov     [rsp+2A8h+var_98], rax
0x180016858  lea     rax, [rsp+2A8h+var_248]
0x18001685d  mov     [rsp+2A8h+var_88], rax
0x180016865  lea     rax, [rsp+2A8h+var_244]
0x18001686a  mov     [rsp+2A8h+var_78], rax
0x180016872  lea     rax, [rsp+2A8h+var_240]
0x180016877  mov     [rsp+2A8h+var_68], rax
0x18001687f  lea     rax, [rsp+2A8h+var_238]
0x180016884  mov     [rsp+2A8h+var_58], rax
0x18001688c  lea     rax, [rsp+2A8h+var_168]
0x180016894  mov     [rsp+2A8h+var_280], rax
0x180016899  mov     [rsp+2A8h+var_288], 12h
0x1800168a1  mov     [rsp+2A8h+var_274], r11d
0x1800168a6  mov     [rsp+2A8h+var_130], 4
0x1800168b2  mov     [rsp+2A8h+var_270], r9d
0x1800168b7  mov     [rsp+2A8h+var_120], 4
0x1800168c3  mov     [rsp+2A8h+var_26C], ebx
0x1800168c7  mov     [rsp+2A8h+var_110], 4
0x1800168d3  mov     [rsp+2A8h+var_268], r15d
0x1800168d8  mov     [rsp+2A8h+var_100], 4
0x1800168e4  mov     [rsp+2A8h+var_264], r12d
0x1800168e9  mov     [rsp+2A8h+var_F0], 4
0x1800168f5  mov     [rsp+2A8h+var_260], r13d
0x1800168fa  mov     [rsp+2A8h+var_E0], 4
0x180016906  mov     [rsp+2A8h+var_D0], 4
0x180016912  mov     [rsp+2A8h+var_C0], 4
0x18001691e  mov     [rsp+2A8h+var_B0], 4
0x18001692a  mov     [rsp+2A8h+var_A0], 4
0x180016936  mov     [rsp+2A8h+var_90], 4
0x180016942  mov     [rsp+2A8h+var_248], r14d
0x180016947  mov     [rsp+2A8h+var_80], 4
0x180016953  mov     [rsp+2A8h+var_244], esi
0x180016957  mov     [rsp+2A8h+var_70], 4
0x180016963  mov     [rsp+2A8h+var_240], edi
0x180016967  mov     [rsp+2A8h+var_60], 4
0x180016973  mov     [rsp+2A8h+var_238], 1000000h
0x18001697c  mov     [rsp+2A8h+var_50], 8
0x180016988  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18001698d  xor     edx, edx
0x18001698f  test    cs:byte_180061688, 2
0x180016996  jz      short loc_180016A04
0x180016998  mov     al, byte ptr cs:xmmword_1800616A0
0x18001699e  mov     rbx, rdx
0x1800169a1  mov     r9, rbx
0x1800169a4  add     r9, r9
0x1800169a7  cmp     [rsp+r9*8+2A8h+var_228], edx
0x1800169af  jnz     short loc_1800169DB
0x1800169b1  test    al, 10h
0x1800169b3  jz      short loc_1800169DB
0x1800169b5  mov     r9, [rsp+r9*8+2A8h+var_220]
0x1800169bd  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800169c4  mov     edx, 0C8h
0x1800169c9  mov     ecx, 404h
0x1800169ce  call    WPP_SF_s
0x1800169d3  mov     al, byte ptr cs:xmmword_1800616A0
0x1800169d9  xor     edx, edx
0x1800169db  inc     rbx
0x1800169de  cmp     rbx, 0Ch
0x1800169e2  jnz     short loc_1800169A1
0x1800169e4  test    al, 10h
0x1800169e6  jz      short loc_180016A04
0x1800169e8  mov     edx, 0C9h
0x1800169ed  mov     dword ptr [rsp+2A8h+var_280], edi
0x1800169f1  mov     r9d, r14d
0x1800169f4  mov     [rsp+2A8h+var_288], esi
0x1800169f8  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800169ff  call    WPP_SF_lll
0x180016a04  mov     rcx, [rsp+2A8h+var_48]
0x180016a0c  xor     rcx, rsp; StackCookie
0x180016a0f  call    __security_check_cookie
0x180016a14  add     rsp, 270h
0x180016a1b  pop     r15
0x180016a1d  pop     r14
0x180016a1f  pop     r13
0x180016a21  pop     r12
0x180016a23  pop     rdi
0x180016a24  pop     rsi
0x180016a25  pop     rbx
0x180016a26  retn
```
