# NgcPackGestureCollectionInputSerializationBuffer

- ea: `0x180011680`
- end: `0x180011b17`
- name: `NgcPackGestureCollectionInputSerializationBuffer`
- size: `1175`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000113c`
- `0x180003080`
- `0x18000530d`
- `0x18000a5b4`
- `0x18000ce04`
- `0x18000cfcc`
- `0x18000ed84`
- `0x180011680`
- `0x180012788`
- `0x180055cd0`
- `0x180056728`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800119d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800119d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a8e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011756`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011756`

## string_xrefs

- `0x1800116de`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011709`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011735`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x18001199b`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011a6e`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall NgcPackGestureCollectionInputSerializationBuffer(
        int a1,
        int a2,
        int a3,
        void *a4,
        int a5,
        int a6,
        LPVOID *a7,
        _DWORD *a8)
{
  DWORD LengthSid; // eax
  __int64 v13; // rdi
  char *v14; // rbx
  int *v15; // rax
  int *v16; // rcx
  __int64 *v17; // rdx
  int v18; // ebx
  signed __int64 v19; // rbx
  _BYTE *v20; // rax
  void **v21; // r9
  _BYTE *v22; // rcx
  int v23; // ebx
  void *v24; // rcx
  void *v25; // rcx
  int v26; // [rsp+20h] [rbp-118h]
  int v27; // [rsp+30h] [rbp-108h] BYREF
  int v28; // [rsp+38h] [rbp-100h] BYREF
  int v29; // [rsp+40h] [rbp-F8h] BYREF
  int v30; // [rsp+48h] [rbp-F0h] BYREF
  __int64 v31; // [rsp+50h] [rbp-E8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-E0h] BYREF
  int v33; // [rsp+60h] [rbp-D8h] BYREF
  int v34; // [rsp+68h] [rbp-D0h] BYREF
  NgcUtils *v35[2]; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+80h] [rbp-B8h]
  void *v37[2]; // [rsp+88h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+98h] [rbp-A0h]
  LPVOID *p_pv; // [rsp+A0h] [rbp-98h]
  unsigned __int64 v40; // [rsp+A8h] [rbp-90h] BYREF
  char v41; // [rsp+B0h] [rbp-88h]
  NgcUtils **v42; // [rsp+B8h] [rbp-80h] BYREF
  _QWORD v43[4]; // [rsp+C0h] [rbp-78h] BYREF
  int *v44; // [rsp+E0h] [rbp-58h]
  __int64 v45; // [rsp+E8h] [rbp-50h]
  NgcUtils ***v46; // [rsp+F0h] [rbp-48h]
  __int64 v47; // [rsp+F8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v27 = a1;
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v26);
    return 2147500035LL;
  }
  if ( !a7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v26);
    return 2147500035LL;
  }
  if ( !a8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v26);
    return 2147500035LL;
  }
  *a7 = 0;
  LengthSid = GetLengthSid(a4);
  v13 = LengthSid;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  if ( LengthSid )
  {
    std::vector<unsigned char>::_Buy_nonzero(v37, LengthSid);
    v14 = (char *)v37[0];
    memmove_0(v37[0], a4, (unsigned int)v13);
    v37[1] = &v14[v13];
    v31 = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v31);
  }
  *(_OWORD *)v35 = 0;
  v36 = 0;
  v42 = v35;
  v30 = a6;
  LODWORD(v31) = a5;
  v34 = a3;
  v28 = a2;
  v33 = v27;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
  {
    if ( (v28 & 0xFFFFFFA0) != 0 )
    {
      if ( (unsigned int)dword_180075000 <= 2 )
      {
LABEL_14:
        v18 = -2147024809;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
          (const char *)(unsigned int)v18,
          v26);
        std::vector<unsigned char>::~vector<unsigned char>(v35);
        std::vector<unsigned char>::~vector<unsigned char>(v37);
        return (unsigned int)v18;
      }
      v27 = v28;
      v29 = -2147024809;
      v15 = &v27;
      v16 = &v29;
      v17 = (__int64 *)byte_180069D1D;
LABEL_13:
      v44 = v16;
      v46 = (NgcUtils ***)v15;
      v47 = 4;
      v45 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180075000, v17, 0, 0, 4, v43);
      goto LABEL_14;
    }
  }
  else if ( (v28 & 0xFFFFFFE0) != 0 )
  {
    if ( (unsigned int)dword_180075000 <= 2 )
      goto LABEL_14;
    v29 = v28;
    v27 = -2147024809;
    v15 = &v29;
    v16 = &v27;
    v17 = (__int64 *)&dword_180069CEC;
    goto LABEL_13;
  }
  if ( (v30 & 0xFFFFFC05) != 0 )
  {
    if ( (unsigned int)dword_180075000 <= 2 )
      goto LABEL_14;
    v29 = v30;
    v27 = -2147024809;
    v15 = &v29;
    v16 = &v27;
    v17 = qword_180069D88;
    goto LABEL_13;
  }
  v43[0] = &v33;
  v43[1] = &v28;
  v43[2] = &v34;
  v43[3] = v37;
  v44 = (int *)&v31;
  v45 = (__int64)&v30;
  v46 = &v42;
  v18 = HResultErrorContract__lambda_fa453f05c3bac5fae8f1dc9aaa6e387f_(v43);
  if ( v18 < 0 )
    goto LABEL_22;
  v19 = v35[1] - v35[0];
  v20 = CoTaskMemAlloc(v35[1] - v35[0]);
  pv = v20;
  if ( v20 )
  {
    v22 = &v20[v19];
    while ( v20 != v22 )
      *v20++ = 0;
  }
  p_pv = &pv;
  v40 = 0;
  v41 = 1;
  v23 = NgcUtils::CoMemAllocCopy(v35[0], v35[1] - v35[0], (unsigned __int64)&v40, v21);
  if ( v41 )
  {
    v24 = *p_pv;
    *p_pv = (LPVOID)v40;
    if ( v24 )
      CoTaskMemFree(v24);
  }
  if ( v23 >= 0 )
  {
    *a7 = pv;
    *a8 = LODWORD(v35[1]) - LODWORD(v35[0]);
    pv = 0;
    std::vector<unsigned char>::~vector<unsigned char>(v35);
    std::vector<unsigned char>::~vector<unsigned char>(v37);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)(unsigned int)v23,
      v26);
    v25 = pv;
    pv = 0;
    if ( v25 )
      CoTaskMemFree(v25);
    std::vector<unsigned char>::~vector<unsigned char>(v35);
    std::vector<unsigned char>::~vector<unsigned char>(v37);
    return (unsigned int)v23;
  }
}

```

## disassembly

```asm
0x180011680  mov     [rsp+arg_0], rbx
0x180011685  mov     [rsp+arg_8], rsi
0x18001168a  push    rdi
0x18001168b  push    r12
0x18001168d  push    r13
0x18001168f  push    r14
0x180011691  push    r15
0x180011693  sub     rsp, 110h
0x18001169a  mov     rax, cs:__security_cookie
0x1800116a1  xor     rax, rsp
0x1800116a4  mov     [rsp+138h+var_38], rax
0x1800116ac  mov     rsi, r9
0x1800116af  mov     r12d, r8d
0x1800116b2  mov     r13d, edx
0x1800116b5  mov     [rsp+138h+var_108], ecx
0x1800116b9  mov     r14, [rsp+138h+arg_30]
0x1800116c1  mov     r15, [rsp+138h+arg_38]
0x1800116c9  test    r9, r9
0x1800116cc  jnz     short loc_1800116F4
0x1800116ce  mov     rcx, [rsp+138h]; this
0x1800116d6  mov     ebx, 80004003h
0x1800116db  mov     r9d, ebx; char *
0x1800116de  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800116e5  lea     edx, [rsi+46h]; void *
0x1800116e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800116ed  mov     eax, ebx
0x1800116ef  jmp     loc_180011AE9
0x1800116f4  test    r14, r14
0x1800116f7  jnz     short loc_180011720
0x1800116f9  mov     rcx, [rsp+138h]; this
0x180011701  mov     ebx, 80004003h
0x180011706  mov     r9d, ebx; char *
0x180011709  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011710  lea     edx, [r14+47h]; void *
0x180011714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011719  mov     eax, ebx
0x18001171b  jmp     loc_180011AE9
0x180011720  test    r15, r15
0x180011723  jnz     short loc_18001174C
0x180011725  mov     rcx, [rsp+138h]; this
0x18001172d  mov     ebx, 80004003h
0x180011732  mov     r9d, ebx; char *
0x180011735  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001173c  lea     edx, [r15+48h]; void *
0x180011740  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011745  mov     eax, ebx
0x180011747  jmp     loc_180011AE9
0x18001174c  mov     qword ptr [r14], 0
0x180011753  mov     rcx, rsi; pSid
0x180011756  call    cs:__imp_GetLengthSid
0x18001175c  mov     edi, eax
0x18001175e  xorps   xmm0, xmm0
0x180011761  movdqu  xmmword ptr [rsp+138h+var_B0], xmm0
0x18001176a  mov     [rsp+138h+var_A0], 0
0x180011776  test    eax, eax
0x180011778  jz      short loc_1800117BE
0x18001177a  mov     edx, edi
0x18001177c  lea     rcx, [rsp+138h+var_B0]
0x180011784  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x180011789  mov     rbx, [rsp+138h+var_B0]
0x180011791  mov     r8d, edi; Size
0x180011794  mov     rdx, rsi; Src
0x180011797  mov     rcx, rbx; void *
0x18001179a  call    memmove_0
0x18001179f  lea     rax, [rdi+rbx]
0x1800117a3  mov     [rsp+138h+var_B0+8], rax
0x1800117ab  xor     edi, edi
0x1800117ad  mov     [rsp+138h+var_E8], rdi
0x1800117b2  lea     rcx, [rsp+138h+var_E8]
0x1800117b7  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x1800117bc  jmp     short loc_1800117C0
0x1800117be  xor     edi, edi
0x1800117c0  xorps   xmm0, xmm0
0x1800117c3  movdqu  xmmword ptr [rsp+138h+var_C8], xmm0
0x1800117c9  mov     [rsp+138h+var_B8], rdi
0x1800117d1  lea     rax, [rsp+138h+var_C8]
0x1800117d6  mov     [rsp+138h+var_80], rax
0x1800117de  mov     eax, [rsp+138h+arg_28]
0x1800117e5  mov     [rsp+138h+var_F0], eax
0x1800117e9  mov     eax, [rsp+138h+arg_20]
0x1800117f0  mov     dword ptr [rsp+138h+var_E8], eax
0x1800117f4  mov     [rsp+138h+var_D0], r12d
0x1800117f9  mov     [rsp+138h+var_100], r13d
0x1800117fe  mov     eax, [rsp+138h+var_108]
0x180011802  mov     [rsp+138h+var_D8], eax
0x180011806  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x18001180d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180011812  test    al, al
0x180011814  jz      loc_1800118A6
0x18001181a  test    [rsp+138h+var_100], 0FFFFFFA0h
0x180011822  jz      loc_1800118E1
0x180011828  mov     eax, cs:dword_180075000
0x18001182e  cmp     eax, 2
0x180011831  jbe     short loc_18001189C
0x180011833  mov     eax, [rsp+138h+var_100]
0x180011837  mov     [rsp+138h+var_108], eax
0x18001183b  mov     [rsp+138h+var_F8], 80070057h
0x180011843  lea     rax, [rsp+138h+var_108]
0x180011848  lea     rcx, [rsp+138h+var_F8]
0x18001184d  lea     rdx, byte_180069D1D
0x180011854  mov     [rsp+138h+var_58], rcx
0x18001185c  mov     [rsp+138h+var_48], rax
0x180011864  lea     rcx, [rsp+138h+var_78]
0x18001186c  mov     eax, 4
0x180011871  mov     [rsp+138h+var_110], rcx
0x180011876  xor     r9d, r9d
0x180011879  mov     [rsp+138h+var_40], rax
0x180011881  mov     [rsp+138h+var_50], rax
0x180011889  mov     [rsp+138h+var_118], eax
0x18001188d  xor     r8d, r8d
0x180011890  lea     rcx, dword_180075000
0x180011897  call    _tlgWriteTransfer_EventWriteTransfer
0x18001189c  mov     ebx, 80070057h
0x1800118a1  jmp     loc_180011990
0x1800118a6  test    [rsp+138h+var_100], 0FFFFFFE0h
0x1800118ae  jz      short loc_1800118E1
0x1800118b0  mov     eax, cs:dword_180075000
0x1800118b6  cmp     eax, 2
0x1800118b9  jbe     short loc_18001189C
0x1800118bb  mov     eax, [rsp+138h+var_100]
0x1800118bf  mov     [rsp+138h+var_F8], eax
0x1800118c3  mov     [rsp+138h+var_108], 80070057h
0x1800118cb  lea     rax, [rsp+138h+var_F8]
0x1800118d0  lea     rcx, [rsp+138h+var_108]
0x1800118d5  lea     rdx, dword_180069CEC
0x1800118dc  jmp     loc_180011854
0x1800118e1  test    [rsp+138h+var_F0], 0FFFFFC05h
0x1800118e9  jz      short loc_18001191C
0x1800118eb  mov     eax, cs:dword_180075000
0x1800118f1  cmp     eax, 2
0x1800118f4  jbe     short loc_18001189C
0x1800118f6  mov     eax, [rsp+138h+var_F0]
0x1800118fa  mov     [rsp+138h+var_F8], eax
0x1800118fe  mov     [rsp+138h+var_108], 80070057h
0x180011906  lea     rax, [rsp+138h+var_F8]
0x18001190b  lea     rcx, [rsp+138h+var_108]
0x180011910  lea     rdx, qword_180069D88
0x180011917  jmp     loc_180011854
0x18001191c  lea     rax, [rsp+138h+var_D8]
0x180011921  mov     [rsp+138h+var_78], rax
0x180011929  lea     rax, [rsp+138h+var_100]
0x18001192e  mov     [rsp+138h+var_70], rax
0x180011936  lea     rax, [rsp+138h+var_D0]
0x18001193b  mov     [rsp+138h+var_68], rax
0x180011943  lea     rax, [rsp+138h+var_B0]
0x18001194b  mov     [rsp+138h+var_60], rax
0x180011953  lea     rax, [rsp+138h+var_E8]
0x180011958  mov     [rsp+138h+var_58], rax
0x180011960  lea     rax, [rsp+138h+var_F0]
0x180011965  mov     [rsp+138h+var_50], rax
0x18001196d  lea     rax, [rsp+138h+var_80]
0x180011975  mov     [rsp+138h+var_48], rax
0x18001197d  lea     rcx, [rsp+138h+var_78]
0x180011985  call    HResultErrorContract__lambda_fa453f05c3bac5fae8f1dc9aaa6e387f___; HResultErrorContract__lambda_fa453f05c3bac5fae8f1dc9aaa6e387f_
0x18001198a  mov     ebx, eax
0x18001198c  test    eax, eax
0x18001198e  jns     short loc_1800119CC
0x180011990  mov     rcx, [rsp+138h]; this
0x180011998  mov     r9d, ebx; char *
0x18001199b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800119a2  mov     edx, 4Eh ; 'N'; void *
0x1800119a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800119ac  nop
0x1800119ad  lea     rcx, [rsp+138h+var_C8]
0x1800119b2  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800119b7  nop
0x1800119b8  lea     rcx, [rsp+138h+var_B0]
0x1800119c0  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800119c5  mov     eax, ebx
0x1800119c7  jmp     loc_180011AE9
0x1800119cc  mov     rbx, [rsp+138h+var_C8+8]
0x1800119d1  sub     rbx, [rsp+138h+var_C8]
0x1800119d6  mov     rcx, rbx; cb
0x1800119d9  call    cs:__imp_CoTaskMemAlloc
0x1800119df  mov     [rsp+138h+pv], rax
0x1800119e4  test    rax, rax
0x1800119e7  jz      short loc_1800119FB
0x1800119e9  lea     rcx, [rbx+rax]
0x1800119ed  jmp     short loc_1800119F6
0x1800119ef  xor     edx, edx
0x1800119f1  mov     [rax], dl
0x1800119f3  inc     rax
0x1800119f6  cmp     rax, rcx
0x1800119f9  jnz     short loc_1800119EF
0x1800119fb  lea     rax, [rsp+138h+pv]
0x180011a00  mov     [rsp+138h+var_98], rax
0x180011a08  mov     [rsp+138h+var_90], rdi
0x180011a10  mov     [rsp+138h+var_88], 1
0x180011a18  mov     rcx, [rsp+138h+var_C8]; this
0x180011a1d  mov     rdx, [rsp+138h+var_C8+8]
0x180011a22  sub     rdx, rcx; Size
0x180011a25  lea     r8, [rsp+138h+var_90]; unsigned __int64
0x180011a2d  call    ?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z; NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)
0x180011a32  mov     ebx, eax
0x180011a34  cmp     [rsp+138h+var_88], dil
0x180011a3c  jz      short loc_180011A5F
0x180011a3e  mov     r8, [rsp+138h+var_98]
0x180011a46  mov     rcx, [r8]; pv
0x180011a49  mov     rdx, [rsp+138h+var_90]
0x180011a51  mov     [r8], rdx
0x180011a54  test    rcx, rcx
0x180011a57  jz      short loc_180011A5F
0x180011a59  call    cs:__imp_CoTaskMemFree
0x180011a5f  test    ebx, ebx
0x180011a61  jns     short loc_180011AB1
0x180011a63  mov     rcx, [rsp+138h]; this
0x180011a6b  mov     r9d, ebx; char *
0x180011a6e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011a75  mov     edx, 51h ; 'Q'; void *
0x180011a7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a7f  mov     rcx, [rsp+138h+pv]; pv
0x180011a84  mov     [rsp+138h+pv], rdi
0x180011a89  test    rcx, rcx
0x180011a8c  jz      short loc_180011A95
0x180011a8e  call    cs:__imp_CoTaskMemFree
0x180011a94  nop
0x180011a95  lea     rcx, [rsp+138h+var_C8]
0x180011a9a  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011a9f  nop
0x180011aa0  lea     rcx, [rsp+138h+var_B0]
0x180011aa8  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011aad  mov     eax, ebx
0x180011aaf  jmp     short loc_180011AE9
0x180011ab1  mov     rax, [rsp+138h+pv]
0x180011ab6  mov     [r14], rax
0x180011ab9  mov     eax, dword ptr [rsp+138h+var_C8+8]
0x180011abd  sub     eax, dword ptr [rsp+138h+var_C8]
0x180011ac1  mov     [r15], eax
0x180011ac4  mov     [rsp+138h+pv], rdi
0x180011ac9  lea     rcx, [rsp+138h+var_C8]
0x180011ace  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011ad3  nop
0x180011ad4  lea     rcx, [rsp+138h+var_B0]
0x180011adc  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011ae1  xor     eax, eax
0x180011ae3  jmp     short loc_180011AE9
0x180011ae5  mov     eax, dword ptr [rsp+138h+var_E8]
0x180011ae9  mov     rcx, [rsp+138h+var_38]
0x180011af1  xor     rcx, rsp; StackCookie
0x180011af4  call    __security_check_cookie
0x180011af9  lea     r11, [rsp+138h+var_28]
0x180011b01  mov     rbx, [r11+30h]
0x180011b05  mov     rsi, [r11+38h]
0x180011b09  mov     rsp, r11
0x180011b0c  pop     r15
0x180011b0e  pop     r14
0x180011b10  pop     r13
0x180011b12  pop     r12
0x180011b14  pop     rdi
0x180011b15  retn
```
