# VFPVSwitch::AddorDeleteVNicRdid(_GUID const &,_GUID const &,uint const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,uint,bool)

- ea: `0x180250688`
- end: `0x180250c24`
- name: `?AddorDeleteVNicRdid@VFPVSwitch@@QEAAXAEBU_GUID@@0PEBIAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@I_N@Z`
- size: `1436`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801cce80`

## callees

- `0x180001b68`
- `0x180004630`
- `0x18005f0c0`
- `0x18005ffac`
- `0x18005ffc4`
- `0x180061240`
- `0x180063a98`
- `0x1800653f0`
- `0x1800666b4`
- `0x18006c530`
- `0x18007f21c`
- `0x18008c69c`
- `0x180250688`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180250b3d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180250b49`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180250b3d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180250b49`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1802507ce`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1802508dc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1802507ce`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1802508dc`
- `NetMgmtIF!NetMgmtAddVirtualSwitchPortProperty` at `0x180250a52`
- `NetMgmtIF!NetMgmtAddVirtualSwitchPortProperty` at `0x180250a52`
- `NetMgmtIF!NetMgmtDeleteVirtualSwitchPortProperty` at `0x180250a9a`
- `NetMgmtIF!NetMgmtDeleteVirtualSwitchPortProperty` at `0x180250a9a`

## string_xrefs

- `0x180250b94`: `onecore\vm\dv\net\hns\service\common\vfp\src\vfpvswitch.cpp`
- `0x180250ba9`: `onecore\vm\dv\net\hns\service\common\vfp\src\vfpvswitch.cpp`
- `0x180250bbb`: `onecore\vm\dv\net\hns\service\common\vfp\src\vfpvswitch.cpp`
- `0x180250bd0`: `onecore\vm\dv\net\hns\service\common\vfp\src\vfpvswitch.cpp`
- `0x180250be5`: `onecore\vm\dv\net\hns\service\common\vfp\src\vfpvswitch.cpp`
- `0x180250bf7`: `onecore\vm\dv\net\hns\service\common\vfp\src\vfpvswitch.cpp`
- `0x180250c0f`: `onecore\vm\dv\net\hns\service\common\vfp\src\vfpvswitch.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall VFPVSwitch::AddorDeleteVNicRdid(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        void *a4,
        _QWORD *a5,
        unsigned int a6,
        char a7)
{
  __int64 v9; // r15
  unsigned int v10; // edi
  const struct _tlgProvider_t *v11; // rax
  unsigned __int64 i; // rcx
  unsigned __int16 *v13; // rbx
  const char *v14; // r9
  _OWORD *v15; // rsi
  _QWORD *v16; // r9
  int v17; // eax
  _QWORD *v18; // r9
  int v19; // eax
  const char *v20; // r9
  char *v21; // r15
  unsigned __int64 v22; // rdi
  __int64 v23; // rsi
  unsigned __int16 v24; // cx
  __int64 v25; // r8
  _QWORD *v26; // rdx
  size_t v27; // rbx
  const struct _tlgProvider_t *v28; // rax
  int v29; // r9d
  _QWORD *v30; // rdx
  _QWORD *v31; // rdx
  _QWORD *v32; // rcx
  int v33; // eax
  _QWORD *v34; // rcx
  int v35; // eax
  const struct _tlgProvider_t *v36; // rax
  unsigned int v37; // eax
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  _BYTE v40[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v41; // [rsp+34h] [rbp-CCh] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  void *v43; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v44; // [rsp+48h] [rbp-B8h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h]
  _OWORD *v46; // [rsp+58h] [rbp-A8h]
  __int64 v47; // [rsp+60h] [rbp-A0h]
  __int64 v48; // [rsp+68h] [rbp-98h]
  void **v49; // [rsp+70h] [rbp-90h]
  char v50; // [rsp+78h] [rbp-88h]
  void **p_Block; // [rsp+80h] [rbp-80h]
  char v52; // [rsp+88h] [rbp-78h]
  __int128 v53; // [rsp+90h] [rbp-70h] BYREF
  __int128 v54; // [rsp+A0h] [rbp-60h]
  _QWORD v55[3]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v56; // [rsp+C8h] [rbp-38h]
  _QWORD v57[3]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v58; // [rsp+E8h] [rbp-18h]
  _BYTE v59[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v60[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v61; // [rsp+130h] [rbp+30h]
  __int64 v62; // [rsp+138h] [rbp+38h]
  _OWORD *v63; // [rsp+140h] [rbp+40h]
  __int64 v64; // [rsp+148h] [rbp+48h]
  int *v65; // [rsp+150h] [rbp+50h]
  __int64 v66; // [rsp+158h] [rbp+58h]
  _BYTE *v67; // [rsp+160h] [rbp+60h]
  __int64 v68; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  Src = a4;
  v46 = a3;
  v48 = a2;
  v47 = a1;
  v53 = 0;
  v54 = 0;
  memset(v59, 0, 28);
  v43 = 0;
  v9 = 4 * a6 + 356;
  v10 = 4 * a6 + 356;
  v11 = HNSTraceProvider::Provider();
  if ( *(_DWORD *)v11 > 4u )
  {
    v40[0] = a7;
    v41 = a6;
    v67 = v40;
    v68 = 1;
    v65 = (int *)&v41;
    v66 = 4;
    v63 = a3;
    v64 = 16;
    v61 = a2;
    v62 = 16;
    tlgWriteTransfer_EventWriteTransfer(v11, &unk_180344050, 0, 0, 6, v60);
  }
  Block = 0;
  GuidToString(v57, a2, 0);
  GuidToString(v55, a3, 0);
  if ( a6 )
  {
    for ( i = 0; i < a6; v10 += 2 * *(_DWORD *)(32 * i++ + *a5 + 16) + 4 )
      ;
  }
  v13 = (unsigned __int16 *)malloc(v10);
  v43 = v13;
  if ( !v13 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x317,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\vfpvswitch.cpp",
      v14);
  v49 = &v43;
  v50 = 1;
  memset_0(v13, 0, v10);
  memset(v59, 0, 28);
  LODWORD(v54) = 0;
  v15 = v46;
  v53 = *v46;
  DWORD1(v54) = v10;
  *((_QWORD *)&v54 + 1) = v43;
  *v13 = 78;
  v16 = v55;
  if ( v56 > 7 )
    v16 = (_QWORD *)v55[0];
  v17 = StringCchPrintfW(v13 + 1, 0x27u, L"{%s}", v16);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x329,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\vfpvswitch.cpp",
      (const char *)(unsigned int)v17,
      v38);
  v13[40] = 78;
  v18 = v55;
  if ( v56 > 7 )
    v18 = (_QWORD *)v55[0];
  v19 = StringCchPrintfW(v13 + 41, 0x27u, L"{%s}", v18);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32C,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\vfpvswitch.cpp",
      (const char *)(unsigned int)v19,
      v38);
  *((_DWORD *)v13 + 85) = a6;
  *((_DWORD *)v13 + 86) = 356;
  memcpy_0((char *)v43 + 356, Src, 4LL * a6);
  *((_DWORD *)v13 + 87) = a6;
  Block = malloc(258LL * a6);
  if ( !Block )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x335,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\vfpvswitch.cpp",
      v20);
  p_Block = &Block;
  v52 = 1;
  *((_DWORD *)v13 + 88) = v9;
  v21 = (char *)v43 + v9;
  v22 = 0;
  if ( a6 )
  {
    do
    {
      v23 = 32 * v22;
      if ( *(_QWORD *)(*a5 + 32 * v22 + 16) > 0x7Fu )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x33F,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\vfpvswitch.cpp",
          (const char *)0x8007000ELL,
          v38);
      v24 = 2 * (*(_WORD *)(*a5 + v23 + 16) + 1);
      v25 = 258 * v22;
      v44 = (_QWORD *)v25;
      *(_WORD *)((char *)Block + v25) = v24;
      v26 = (_QWORD *)(v23 + *a5);
      if ( v26[3] > 7u )
        v26 = (_QWORD *)*v26;
      v27 = v24;
      memcpy_0((char *)Block + v25 + 2, v26, v24);
      v27 += 2LL;
      memcpy_0(v21, (char *)v44 + (_QWORD)Block, v27);
      v21 += v27;
      v28 = HNSTraceProvider::Provider();
      if ( *(_DWORD *)v28 > 4u )
      {
        v30 = (_QWORD *)(v23 + *a5);
        if ( v30[3] > 7u )
          v30 = (_QWORD *)*v30;
        v44 = v30;
        v41 = *((_DWORD *)Src + v22);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v28,
          (unsigned int)&unk_180344019,
          (_DWORD)v28,
          v29,
          (__int64)&v41,
          (__int64)&v44);
      }
      ++v22;
    }
    while ( v22 < a6 );
    v15 = v46;
  }
  v31 = v57;
  if ( a7 )
  {
    if ( v58 > 7 )
      v31 = (_QWORD *)v57[0];
    v32 = (_QWORD *)(v47 + 56);
    if ( *(_QWORD *)(v47 + 80) > 7u )
      v32 = (_QWORD *)*v32;
    v33 = NetMgmtAddVirtualSwitchPortProperty(v32, v31, &VMS_PORT_POLICY_ROUTING_DOMAIN_SETTINGS_GUID, &v53, 1, v59);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x357,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\vfpvswitch.cpp",
        (const char *)(unsigned int)v33,
        v39);
  }
  else
  {
    if ( v58 > 7 )
      v31 = (_QWORD *)v57[0];
    v34 = (_QWORD *)(v47 + 56);
    if ( *(_QWORD *)(v47 + 80) > 7u )
      v34 = (_QWORD *)*v34;
    v35 = NetMgmtDeleteVirtualSwitchPortProperty(v34, v31, &VMS_PORT_POLICY_ROUTING_DOMAIN_SETTINGS_GUID, &v53);
    if ( v35 < 0 && v35 != -2147024894 && v35 != -2147023728 && v35 != -1073741772 )
    {
      v37 = wil::verify_hresult<long>((unsigned int)v35);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x361,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\vfpvswitch.cpp",
        (const char *)v37,
        1);
    }
  }
  v36 = HNSTraceProvider::Provider();
  if ( *(_DWORD *)v36 > 4u )
  {
    v40[0] = a7;
    v41 = a6;
    v67 = v40;
    v68 = 1;
    v65 = (int *)&v41;
    v66 = 4;
    v63 = v15;
    v64 = 16;
    v61 = v48;
    v62 = 16;
    tlgWriteTransfer_EventWriteTransfer(v36, &unk_180343FC6, 0, 0, 6, v60);
  }
  free(Block);
  free(v43);
  std::wstring::~wstring(v55);
  std::wstring::~wstring(v57);
}

```

## disassembly

```asm
0x180250688  push    rbp
0x18025068a  push    rbx
0x18025068b  push    rsi
0x18025068c  push    rdi
0x18025068d  push    r12
0x18025068f  push    r13
0x180250691  push    r14
0x180250693  push    r15
0x180250695  lea     rbp, [rsp-88h]
0x18025069d  sub     rsp, 188h
0x1802506a4  mov     rax, cs:__security_cookie
0x1802506ab  xor     rax, rsp
0x1802506ae  mov     [rbp+0C0h+var_50], rax
0x1802506b2  mov     [rsp+1C0h+Src], r9
0x1802506b7  mov     rbx, r8
0x1802506ba  mov     [rsp+1C0h+var_168], rbx
0x1802506bf  mov     rsi, rdx
0x1802506c2  mov     [rsp+1C0h+var_158], rdx
0x1802506c7  mov     [rsp+1C0h+var_160], rcx
0x1802506cc  mov     r13, [rbp+0C0h+arg_20]
0x1802506d3  mov     r12d, [rbp+0C0h+arg_28]
0x1802506da  xorps   xmm0, xmm0
0x1802506dd  movups  [rbp+0C0h+var_130], xmm0
0x1802506e1  movups  [rbp+0C0h+var_120], xmm0
0x1802506e5  xorps   xmm1, xmm1
0x1802506e8  movups  xmmword ptr [rbp+0C0h+var_D0], xmm1
0x1802506ec  movups  xmmword ptr [rbp+0C0h+var_D0+0Ch], xmm1
0x1802506f0  xor     r14d, r14d
0x1802506f3  mov     [rsp+1C0h+var_180], r14
0x1802506f8  lea     r15d, ds:164h[r12*4]
0x180250700  mov     edi, r15d
0x180250703  call    ?Provider@HNSTraceProvider@@SAPEBU_tlgProvider_t@@XZ; HNSTraceProvider::Provider(void)
0x180250708  mov     ecx, [rax]
0x18025070a  cmp     ecx, 4
0x18025070d  jbe     short loc_18025077E
0x18025070f  mov     cl, [rbp+0C0h+arg_30]
0x180250715  mov     [rsp+1C0h+var_190], cl
0x180250719  mov     [rsp+1C0h+var_18C], r12d
0x18025071e  lea     rcx, [rsp+1C0h+var_190]
0x180250723  mov     [rbp+0C0h+var_60], rcx
0x180250727  mov     [rbp+0C0h+var_58], 1
0x18025072f  lea     rcx, [rsp+1C0h+var_18C]
0x180250734  mov     [rbp+0C0h+var_70], rcx
0x180250738  mov     [rbp+0C0h+var_68], 4
0x180250740  mov     [rbp+0C0h+var_80], rbx
0x180250744  mov     [rbp+0C0h+var_78], 10h
0x18025074c  mov     [rbp+0C0h+var_90], rsi
0x180250750  mov     [rbp+0C0h+var_88], 10h
0x180250758  lea     rcx, [rbp+0C0h+var_B0]
0x18025075c  mov     [rsp+1C0h+var_198], rcx
0x180250761  mov     [rsp+1C0h+var_1A0], 6; int
0x180250769  xor     r9d, r9d
0x18025076c  xor     r8d, r8d
0x18025076f  lea     rdx, unk_180344050
0x180250776  mov     rcx, rax
0x180250779  call    _tlgWriteTransfer_EventWriteTransfer
0x18025077e  mov     [rsp+1C0h+Block], r14
0x180250783  xor     r8d, r8d
0x180250786  mov     rdx, rsi
0x180250789  lea     rcx, [rbp+0C0h+var_F0]
0x18025078d  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x180250792  nop
0x180250793  xor     r8d, r8d
0x180250796  mov     rdx, rbx
0x180250799  lea     rcx, [rbp+0C0h+var_110]
0x18025079d  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x1802507a2  nop
0x1802507a3  mov     r14, r12
0x1802507a6  test    r12d, r12d
0x1802507a9  jz      short loc_1802507CA
0x1802507ab  xor     ecx, ecx
0x1802507ad  mov     rdx, [r13+0]
0x1802507b1  mov     rax, rcx
0x1802507b4  shl     rax, 5
0x1802507b8  mov     eax, [rax+rdx+10h]
0x1802507bc  lea     edi, [rdi+rax*2]
0x1802507bf  add     edi, 4
0x1802507c2  inc     rcx
0x1802507c5  cmp     rcx, r14
0x1802507c8  jb      short loc_1802507B1
0x1802507ca  mov     esi, edi
0x1802507cc  mov     ecx, edi; Size
0x1802507ce  call    cs:__imp_malloc
0x1802507d4  mov     rbx, rax
0x1802507d7  mov     [rsp+1C0h+var_180], rax
0x1802507dc  mov     rcx, [rbp+0C8h]; this
0x1802507e3  test    rax, rax
0x1802507e6  jz      loc_180250BBB
0x1802507ec  lea     rax, [rsp+1C0h+var_180]
0x1802507f1  mov     [rsp+1C0h+var_150], rax
0x1802507f6  mov     [rsp+1C0h+var_148], 1
0x1802507fb  mov     r8d, esi; Size
0x1802507fe  xor     edx, edx; Val
0x180250800  mov     rcx, rbx; void *
0x180250803  call    memset_0
0x180250808  xorps   xmm0, xmm0
0x18025080b  xor     eax, eax
0x18025080d  movups  xmmword ptr [rbp+0C0h+var_D0], xmm0
0x180250811  movups  xmmword ptr [rbp+0C0h+var_D0+0Ch], xmm0
0x180250815  mov     dword ptr [rbp+0C0h+var_120], eax
0x180250818  mov     rsi, [rsp+1C0h+var_168]
0x18025081d  movups  xmm0, xmmword ptr [rsi]
0x180250820  movdqu  [rbp+0C0h+var_130], xmm0
0x180250825  mov     dword ptr [rbp+0C0h+var_120+4], edi
0x180250828  mov     rax, [rsp+1C0h+var_180]
0x18025082d  mov     qword ptr [rbp+0C0h+var_120+8], rax
0x180250831  mov     word ptr [rbx], 4Eh ; 'N'
0x180250836  lea     r9, [rbp+0C0h+var_110]
0x18025083a  cmp     [rbp+0C0h+var_F8], 7
0x18025083f  cmova   r9, [rbp+0C0h+var_110]
0x180250844  lea     rcx, [rbx+2]; unsigned __int16 *
0x180250848  lea     r8, aS; "{%s}"
0x18025084f  mov     edi, 27h ; '''
0x180250854  mov     edx, edi; unsigned __int64
0x180250856  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18025085b  mov     rcx, [rbp+0C8h]; this
0x180250862  test    eax, eax
0x180250864  js      loc_180250BCD
0x18025086a  mov     word ptr [rbx+50h], 4Eh ; 'N'
0x180250870  lea     r9, [rbp+0C0h+var_110]
0x180250874  cmp     [rbp+0C0h+var_F8], 7
0x180250879  cmova   r9, [rbp+0C0h+var_110]
0x18025087e  lea     rcx, [rbx+52h]; unsigned __int16 *
0x180250882  lea     r8, aS; "{%s}"
0x180250889  mov     edx, edi; unsigned __int64
0x18025088b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180250890  mov     rcx, [rbp+0C8h]; this
0x180250897  test    eax, eax
0x180250899  js      loc_180250BE2
0x18025089f  mov     [rbx+154h], r12d
0x1802508a6  mov     dword ptr [rbx+158h], 164h
0x1802508b0  lea     r8, ds:0[r12*4]; Size
0x1802508b8  mov     rcx, [rsp+1C0h+var_180]
0x1802508bd  add     rcx, 164h; void *
0x1802508c4  mov     rdx, [rsp+1C0h+Src]; Src
0x1802508c9  call    memcpy_0
0x1802508ce  mov     [rbx+15Ch], r12d
0x1802508d5  imul    rcx, r14, 102h; Size
0x1802508dc  call    cs:__imp_malloc
0x1802508e2  mov     [rsp+1C0h+Block], rax
0x1802508e7  mov     rcx, [rbp+0C8h]; this
0x1802508ee  test    rax, rax
0x1802508f1  jz      loc_180250BF7
0x1802508f7  lea     rax, [rsp+1C0h+Block]
0x1802508fc  mov     [rbp+0C0h+var_140], rax
0x180250900  lea     r8d, [rdi-26h]
0x180250904  mov     [rbp+0C0h+var_138], r8b
0x180250908  mov     [rbx+160h], r15d
0x18025090f  add     r15, [rsp+1C0h+var_180]
0x180250914  xor     edi, edi
0x180250916  test    r12d, r12d
0x180250919  jz      loc_180250A0E
0x18025091f  mov     rsi, rdi
0x180250922  shl     rsi, 5
0x180250926  mov     rcx, [r13+0]
0x18025092a  mov     rax, [rbp+0C8h]
0x180250931  cmp     qword ptr [rcx+rsi+10h], 7Fh
0x180250937  ja      loc_180250C09
0x18025093d  movzx   ecx, word ptr [rcx+rsi+10h]
0x180250942  add     cx, r8w
0x180250946  add     cx, cx
0x180250949  imul    r8, rdi, 102h
0x180250950  mov     [rsp+1C0h+var_178], r8
0x180250955  mov     rax, [rsp+1C0h+Block]
0x18025095a  mov     [r8+rax], cx
0x18025095f  mov     rdx, [r13+0]
0x180250963  add     rdx, rsi
0x180250966  cmp     qword ptr [rdx+18h], 7
0x18025096b  jbe     short loc_180250970
0x18025096d  mov     rdx, [rdx]; Src
0x180250970  movzx   ebx, cx
0x180250973  mov     rcx, [rsp+1C0h+Block]
0x180250978  add     rcx, 2
0x18025097c  add     rcx, r8; void *
0x18025097f  mov     r8d, ebx; Size
0x180250982  call    memcpy_0
0x180250987  add     rbx, 2
0x18025098b  mov     rdx, [rsp+1C0h+var_178]
0x180250990  add     rdx, [rsp+1C0h+Block]; Src
0x180250995  mov     r8, rbx; Size
0x180250998  mov     rcx, r15; void *
0x18025099b  call    memcpy_0
0x1802509a0  add     r15, rbx
0x1802509a3  call    ?Provider@HNSTraceProvider@@SAPEBU_tlgProvider_t@@XZ; HNSTraceProvider::Provider(void)
0x1802509a8  mov     r8, rax
0x1802509ab  mov     ecx, [rax]
0x1802509ad  cmp     ecx, 4
0x1802509b0  jbe     short loc_1802509F7
0x1802509b2  mov     rdx, [r13+0]
0x1802509b6  add     rdx, rsi
0x1802509b9  cmp     qword ptr [rdx+18h], 7
0x1802509be  jbe     short loc_1802509C3
0x1802509c0  mov     rdx, [rdx]
0x1802509c3  mov     [rsp+1C0h+var_178], rdx
0x1802509c8  mov     rax, [rsp+1C0h+Src]
0x1802509cd  mov     eax, [rax+rdi*4]
0x1802509d0  mov     [rsp+1C0h+var_18C], eax
0x1802509d4  lea     rax, [rsp+1C0h+var_178]
0x1802509d9  mov     [rsp+1C0h+var_198], rax
0x1802509de  lea     rax, [rsp+1C0h+var_18C]
0x1802509e3  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x1802509e8  lea     rdx, unk_180344019
0x1802509ef  mov     rcx, r8
0x1802509f2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1802509f7  mov     r8d, 1
0x1802509fd  add     rdi, r8
0x180250a00  cmp     rdi, r14
0x180250a03  jb      loc_18025091F
0x180250a09  mov     rsi, [rsp+1C0h+var_168]
0x180250a0e  mov     bl, [rbp+0C0h+arg_30]
0x180250a14  lea     rdx, [rbp+0C0h+var_F0]
0x180250a18  mov     rcx, [rsp+1C0h+var_160]
0x180250a1d  test    bl, bl
0x180250a1f  jz      short loc_180250A69
0x180250a21  cmp     [rbp+0C0h+var_D8], 7
0x180250a26  cmova   rdx, [rbp+0C0h+var_F0]
0x180250a2b  add     rcx, 38h ; '8'
0x180250a2f  cmp     qword ptr [rcx+18h], 7
0x180250a34  jbe     short loc_180250A39
0x180250a36  mov     rcx, [rcx]
0x180250a39  lea     rax, [rbp+0C0h+var_D0]
0x180250a3d  mov     [rsp+1C0h+var_198], rax
0x180250a42  mov     [rsp+1C0h+var_1A0], r8d; int
0x180250a47  lea     r9, [rbp+0C0h+var_130]
0x180250a4b  lea     r8, VMS_PORT_POLICY_ROUTING_DOMAIN_SETTINGS_GUID
0x180250a52  call    cs:__imp_NetMgmtAddVirtualSwitchPortProperty
0x180250a58  mov     rcx, [rbp+0C8h]; this
0x180250a5f  test    eax, eax
0x180250a61  js      loc_180250BA6
0x180250a67  jmp     short loc_180250ABD
0x180250a69  cmp     [rbp+0C0h+var_D8], 7
0x180250a6e  cmova   rdx, [rbp+0C0h+var_F0]
0x180250a73  add     rcx, 38h ; '8'
0x180250a77  cmp     qword ptr [rcx+18h], 7
0x180250a7c  jbe     short loc_180250A81
0x180250a7e  mov     rcx, [rcx]
0x180250a81  lea     rax, [rbp+0C0h+var_D0]
0x180250a85  mov     [rsp+1C0h+var_198], rax
0x180250a8a  mov     [rsp+1C0h+var_1A0], r8d; int
0x180250a8f  lea     r9, [rbp+0C0h+var_130]
0x180250a93  lea     r8, VMS_PORT_POLICY_ROUTING_DOMAIN_SETTINGS_GUID
0x180250a9a  call    cs:__imp_NetMgmtDeleteVirtualSwitchPortProperty
0x180250aa0  test    eax, eax
0x180250aa2  jns     short loc_180250ABD
0x180250aa4  cmp     eax, 80070002h
0x180250aa9  jz      short loc_180250ABD
0x180250aab  cmp     eax, 80070490h
0x180250ab0  jz      short loc_180250ABD
0x180250ab2  cmp     eax, 0C0000034h
0x180250ab7  jnz     loc_180250B83
0x180250abd  call    ?Provider@HNSTraceProvider@@SAPEBU_tlgProvider_t@@XZ; HNSTraceProvider::Provider(void)
0x180250ac2  mov     ecx, [rax]
0x180250ac4  cmp     ecx, 4
0x180250ac7  jbe     short loc_180250B38
0x180250ac9  mov     [rsp+1C0h+var_190], bl
0x180250acd  mov     [rsp+1C0h+var_18C], r12d
0x180250ad2  lea     rcx, [rsp+1C0h+var_190]
0x180250ad7  mov     [rbp+0C0h+var_60], rcx
0x180250adb  mov     [rbp+0C0h+var_58], 1
0x180250ae3  lea     rcx, [rsp+1C0h+var_18C]
0x180250ae8  mov     [rbp+0C0h+var_70], rcx
0x180250aec  mov     [rbp+0C0h+var_68], 4
0x180250af4  mov     [rbp+0C0h+var_80], rsi
0x180250af8  mov     [rbp+0C0h+var_78], 10h
0x180250b00  mov     rcx, [rsp+1C0h+var_158]
0x180250b05  mov     [rbp+0C0h+var_90], rcx
0x180250b09  mov     [rbp+0C0h+var_88], 10h
0x180250b11  lea     rcx, [rbp+0C0h+var_B0]
0x180250b15  mov     [rsp+1C0h+var_198], rcx
0x180250b1a  mov     [rsp+1C0h+var_1A0], 6
0x180250b22  xor     r9d, r9d
0x180250b25  xor     r8d, r8d
0x180250b28  lea     rdx, unk_180343FC6
0x180250b2f  mov     rcx, rax
0x180250b32  call    _tlgWriteTransfer_EventWriteTransfer
0x180250b37  nop
0x180250b38  mov     rcx, [rsp+1C0h+Block]; Block
0x180250b3d  call    cs:__imp_free
0x180250b43  nop
0x180250b44  mov     rcx, [rsp+1C0h+var_180]; Block
0x180250b49  call    cs:__imp_free
0x180250b4f  nop
0x180250b50  lea     rcx, [rbp+0C0h+var_110]; void *
0x180250b54  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180250b59  nop
0x180250b5a  lea     rcx, [rbp+0C0h+var_F0]; void *
0x180250b5e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180250b63  mov     rcx, [rbp+0C0h+var_50]
0x180250b67  xor     rcx, rsp; StackCookie
0x180250b6a  call    __security_check_cookie
0x180250b6f  add     rsp, 188h
0x180250b76  pop     r15
0x180250b78  pop     r14
0x180250b7a  pop     r13
0x180250b7c  pop     r12
0x180250b7e  pop     rdi
0x180250b7f  pop     rsi
0x180250b80  pop     rbx
0x180250b81  pop     rbp
0x180250b82  retn
  ... truncated ...
```
