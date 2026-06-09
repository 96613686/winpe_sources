# ComputeChangeInFraming(IKsPin *,ulong,_GUID,ulong *)

- ea: `0x180034694`
- end: `0x1800349fa`
- name: `?ComputeChangeInFraming@@YAHPEAUIKsPin@@KU_GUID@@PEAK@Z`
- size: `870`
- prototype: `__int64 __fastcall(struct IKsPin *, int, struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001de40`

## callees

- `0x180016a28`
- `0x18001ce34`
- `0x18001e4dc`
- `0x18001f620`
- `0x18001ffb0`
- `0x180034694`
- `0x1800380f8`
- `0x180038804`
- `0x180038824`
- `0x180044844`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall ComputeChangeInFraming(struct IKsPin *a1, int a2, struct _GUID *a3, unsigned int *a4)
{
  IKsPin_vtbl *v8; // rax
  int v10; // eax
  __int64 v11; // xmm0_8
  unsigned int Stepping; // eax
  int v13; // eax
  int v14; // eax
  struct _GUID v15; // [rsp+30h] [rbp-D0h] BYREF
  enum FRAMING_PROP v16; // [rsp+40h] [rbp-C0h] BYREF
  struct KSALLOCATOR_FRAMING_EX *v17; // [rsp+48h] [rbp-B8h] BYREF
  enum FRAMING_PROP v18; // [rsp+50h] [rbp-B0h] BYREF
  struct KSALLOCATOR_FRAMING_EX *v19; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Buf2[56]; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+A8h] [rbp-58h]
  struct KS_FRAMING_RANGE v23; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v24; // [rsp+C0h] [rbp-40h]
  int v25; // [rsp+C4h] [rbp-3Ch]
  int v26; // [rsp+C8h] [rbp-38h]
  struct KS_FRAMING_RANGE v27; // [rsp+CCh] [rbp-34h] BYREF
  _BYTE Buf1[56]; // [rsp+F0h] [rbp-10h] BYREF
  int v29; // [rsp+128h] [rbp+28h]
  struct KS_FRAMING_RANGE v30; // [rsp+134h] [rbp+34h] BYREF
  unsigned int v31; // [rsp+140h] [rbp+40h]
  int v32; // [rsp+144h] [rbp+44h]
  int v33; // [rsp+148h] [rbp+48h]
  struct KS_FRAMING_RANGE v34; // [rsp+14Ch] [rbp+4Ch] BYREF

  v19 = 0;
  v17 = 0;
  v18 = FramingProp_Uninitialized;
  v16 = FramingProp_Uninitialized;
  memset_0(Buf1, 0, 0x74u);
  memset_0(Buf2, 0, 0x74u);
  v8 = a1->__vftable;
  v20 = 0;
  if ( v8->QueryInterface(a1, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, (void **)&v20) < 0 )
  {
    v20 = 0;
    return 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  *a4 = 0;
  if ( !(unsigned int)GetPinFramingFromCache(a1, &v19, &v18, Framing_Cache_ReadOrig)
    || !(unsigned int)GetPinFramingFromCache(a1, &v17, &v16, Framing_Cache_Update) )
  {
    return 0;
  }
  if ( v18 != FramingProp_None )
  {
    v15 = *a3;
    if ( v16 != FramingProp_None )
    {
      if ( !(unsigned int)GetFramingFixedFromFramingByMemoryType(v19, &v15, (struct KS_FRAMING_FIXED *)Buf1) )
        GetFramingFixedFromFramingByIndex(v19, 0, (struct KS_FRAMING_FIXED *)Buf1);
      v15 = *a3;
      if ( !(unsigned int)GetFramingFixedFromFramingByMemoryType(v17, &v15, (struct KS_FRAMING_FIXED *)Buf2) )
        GetFramingFixedFromFramingByIndex(v17, 0, (struct KS_FRAMING_FIXED *)Buf2);
      if ( memcmp_0(Buf1, Buf2, 0x10u) )
        *a4 |= 1u;
      if ( (((unsigned __int8)v22 ^ (unsigned __int8)v29) & 8) != 0 )
        *a4 |= 2u;
      if ( a2 != 4 && (v31 != v24 || v32 != v25 || v33 != v26) )
        *a4 |= 4u;
      if ( !(unsigned int)IsFramingRangeEqual(&v30, &v23) )
        *a4 |= 8u;
      v13 = IsFramingRangeEqual(&v34, &v27);
      goto LABEL_46;
    }
    if ( !(unsigned int)GetFramingFixedFromFramingByMemoryType(v19, &v15, (struct KS_FRAMING_FIXED *)Buf1) )
    {
      *a4 |= 1u;
      GetFramingFixedFromFramingByIndex(v19, 0, (struct KS_FRAMING_FIXED *)Buf1);
    }
    if ( (v29 & 8) != 0 )
      *a4 |= 2u;
    if ( a2 != 4 )
    {
      v15.Data1 = v31;
      *(_DWORD *)&v15.Data2 = v32;
      *(_DWORD *)v15.Data4 = v33;
      if ( !(unsigned int)IsCompressionDontCare((struct KS_COMPRESSION *)&v15) )
        *a4 |= 4u;
    }
    *(_QWORD *)&v15.Data1 = *(_QWORD *)&v30.MinFrameSize;
    *(_DWORD *)v15.Data4 = v30.Stepping;
    LOBYTE(v14) = IsFramingRangeDontCare((struct KS_FRAMING_RANGE *)&v15);
    if ( !v14 )
      *a4 |= 8u;
    v11 = *(_QWORD *)&v34.MinFrameSize;
    Stepping = v34.Stepping;
LABEL_18:
    *(_QWORD *)&v15.Data1 = v11;
    *(_DWORD *)v15.Data4 = Stepping;
    LOBYTE(v13) = IsFramingRangeDontCare((struct KS_FRAMING_RANGE *)&v15);
LABEL_46:
    if ( !v13 )
      *a4 |= 0x10u;
    goto LABEL_48;
  }
  if ( v16 != FramingProp_None )
  {
    v15 = *a3;
    if ( !(unsigned int)GetFramingFixedFromFramingByMemoryType(v17, &v15, (struct KS_FRAMING_FIXED *)Buf2) )
    {
      *a4 |= 1u;
      GetFramingFixedFromFramingByIndex(v17, 0, (struct KS_FRAMING_FIXED *)Buf2);
    }
    if ( (v22 & 8) != 0 )
      *a4 |= 2u;
    if ( a2 != 4 )
    {
      v15.Data1 = v24;
      *(_DWORD *)&v15.Data2 = v25;
      *(_DWORD *)v15.Data4 = v26;
      if ( !(unsigned int)IsCompressionDontCare((struct KS_COMPRESSION *)&v15) )
        *a4 |= 4u;
    }
    *(_QWORD *)&v15.Data1 = *(_QWORD *)&v23.MinFrameSize;
    *(_DWORD *)v15.Data4 = v23.Stepping;
    LOBYTE(v10) = IsFramingRangeDontCare((struct KS_FRAMING_RANGE *)&v15);
    if ( !v10 )
      *a4 |= 8u;
    v11 = *(_QWORD *)&v27.MinFrameSize;
    Stepping = v27.Stepping;
    goto LABEL_18;
  }
LABEL_48:
  (*(void (__fastcall **)(__int64, struct KSALLOCATOR_FRAMING_EX *, enum FRAMING_PROP *, __int64))(*(_QWORD *)v20 + 32LL))(
    v20,
    v17,
    &v16,
    2);
  return 1;
}

```

## disassembly

```asm
0x180034694  mov     [rsp-8+arg_8], rbx
0x180034699  mov     [rsp-8+arg_10], rsi
0x18003469e  push    rbp
0x18003469f  push    rdi
0x1800346a0  push    r14
0x1800346a2  lea     rbp, [rsp-80h]
0x1800346a7  sub     rsp, 180h
0x1800346ae  mov     rax, cs:__security_cookie
0x1800346b5  xor     rax, rsp
0x1800346b8  mov     [rbp+90h+var_20], rax
0x1800346bc  mov     esi, edx
0x1800346be  mov     [rsp+190h+var_138], 0
0x1800346c7  xor     edx, edx; Val
0x1800346c9  mov     [rsp+190h+var_148], 0
0x1800346d2  mov     rdi, r8
0x1800346d5  mov     [rsp+190h+var_140], 0
0x1800346dd  mov     r14, rcx
0x1800346e0  mov     [rsp+190h+var_150], 0
0x1800346e8  lea     rcx, [rbp+90h+Buf1]; void *
0x1800346ec  mov     rbx, r9
0x1800346ef  lea     r8d, [rdx+74h]; Size
0x1800346f3  call    memset_0
0x1800346f8  xor     edx, edx; Val
0x1800346fa  lea     rcx, [rsp+190h+Buf2]; void *
0x1800346ff  lea     r8d, [rdx+74h]; Size
0x180034703  call    memset_0
0x180034708  mov     rax, [r14]
0x18003470b  lea     r8, [rsp+190h+var_130]
0x180034710  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x180034717  mov     [rsp+190h+var_130], 0
0x180034720  mov     rcx, r14
0x180034723  mov     rax, [rax]
0x180034726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003472b  test    eax, eax
0x18003472d  jns     short loc_18003475F
0x18003472f  mov     [rsp+190h+var_130], 0
0x180034738  xor     eax, eax
0x18003473a  mov     rcx, [rbp+90h+var_20]
0x18003473e  xor     rcx, rsp; StackCookie
0x180034741  call    __security_check_cookie
0x180034746  lea     r11, [rsp+190h+var_10]
0x18003474e  mov     rbx, [r11+28h]
0x180034752  mov     rsi, [r11+30h]
0x180034756  mov     rsp, r11
0x180034759  pop     r14
0x18003475b  pop     rdi
0x18003475c  pop     rbp
0x18003475d  retn
0x18003475f  mov     rcx, [rsp+190h+var_130]
0x180034764  mov     rax, [rcx]
0x180034767  mov     rax, [rax+10h]
0x18003476b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034770  mov     r9d, 2; enum FRAMING_CACHE_OPS
0x180034776  mov     dword ptr [rbx], 0
0x18003477c  lea     r8, [rsp+190h+var_140]; enum FRAMING_PROP *
0x180034781  mov     rcx, r14; struct IKsPin *
0x180034784  lea     rdx, [rsp+190h+var_138]; struct KSALLOCATOR_FRAMING_EX **
0x180034789  call    ?GetPinFramingFromCache@@YAHPEAUIKsPin@@PEAPEAUKSALLOCATOR_FRAMING_EX@@PEAW4FRAMING_PROP@@W4FRAMING_CACHE_OPS@@@Z; GetPinFramingFromCache(IKsPin *,KSALLOCATOR_FRAMING_EX * *,FRAMING_PROP *,FRAMING_CACHE_OPS)
0x18003478e  test    eax, eax
0x180034790  jz      short loc_180034738
0x180034792  xor     r9d, r9d; enum FRAMING_CACHE_OPS
0x180034795  lea     r8, [rsp+190h+var_150]; enum FRAMING_PROP *
0x18003479a  lea     rdx, [rsp+190h+var_148]; struct KSALLOCATOR_FRAMING_EX **
0x18003479f  mov     rcx, r14; struct IKsPin *
0x1800347a2  call    ?GetPinFramingFromCache@@YAHPEAUIKsPin@@PEAPEAUKSALLOCATOR_FRAMING_EX@@PEAW4FRAMING_PROP@@W4FRAMING_CACHE_OPS@@@Z; GetPinFramingFromCache(IKsPin *,KSALLOCATOR_FRAMING_EX * *,FRAMING_PROP *,FRAMING_CACHE_OPS)
0x1800347a7  test    eax, eax
0x1800347a9  jz      short loc_180034738
0x1800347ab  mov     r14d, 1
0x1800347b1  cmp     [rsp+190h+var_140], r14d
0x1800347b6  jnz     loc_180034874
0x1800347bc  cmp     [rsp+190h+var_150], r14d
0x1800347c1  jz      loc_1800349D1
0x1800347c7  movaps  xmm0, xmmword ptr [rdi]
0x1800347ca  lea     r8, [rsp+190h+Buf2]; struct KS_FRAMING_FIXED *
0x1800347cf  mov     rcx, [rsp+190h+var_148]; struct KSALLOCATOR_FRAMING_EX *
0x1800347d4  lea     rdx, [rsp+190h+var_160]; struct _GUID
0x1800347d9  movdqa  [rsp+190h+var_160], xmm0
0x1800347df  call    ?GetFramingFixedFromFramingByMemoryType@@YAHPEAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PEAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByMemoryType(KSALLOCATOR_FRAMING_EX *,_GUID,KS_FRAMING_FIXED *)
0x1800347e4  test    eax, eax
0x1800347e6  jnz     short loc_1800347FC
0x1800347e8  or      [rbx], r14d
0x1800347eb  lea     r8, [rsp+190h+Buf2]; struct KS_FRAMING_FIXED *
0x1800347f0  mov     rcx, [rsp+190h+var_148]; struct KSALLOCATOR_FRAMING_EX *
0x1800347f5  xor     edx, edx; unsigned int
0x1800347f7  call    ?GetFramingFixedFromFramingByIndex@@YAHPEAUKSALLOCATOR_FRAMING_EX@@KPEAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByIndex(KSALLOCATOR_FRAMING_EX *,ulong,KS_FRAMING_FIXED *)
0x1800347fc  test    byte ptr [rbp+90h+var_E8], 8
0x180034800  jz      short loc_180034805
0x180034802  or      dword ptr [rbx], 2
0x180034805  cmp     esi, 4
0x180034808  jz      short loc_180034830
0x18003480a  mov     eax, [rbp+90h+var_D0]
0x18003480d  lea     rcx, [rsp+190h+var_160]; struct KS_COMPRESSION
0x180034812  mov     dword ptr [rsp+190h+var_160], eax
0x180034816  mov     eax, [rbp+90h+var_CC]
0x180034819  mov     dword ptr [rsp+190h+var_160+4], eax
0x18003481d  mov     eax, [rbp+90h+var_C8]
0x180034820  mov     dword ptr [rsp+190h+var_160+8], eax
0x180034824  call    ?IsCompressionDontCare@@YAHUKS_COMPRESSION@@@Z; IsCompressionDontCare(KS_COMPRESSION)
0x180034829  test    eax, eax
0x18003482b  jnz     short loc_180034830
0x18003482d  or      dword ptr [rbx], 4
0x180034830  mov     eax, [rbp+90h+var_DC.Stepping]
0x180034833  lea     rcx, [rsp+190h+var_160]; struct KS_FRAMING_RANGE
0x180034838  movsd   xmm0, qword ptr [rbp+90h+var_DC.MinFrameSize]
0x18003483d  movsd   qword ptr [rsp+190h+var_160], xmm0
0x180034843  mov     dword ptr [rsp+190h+var_160+8], eax
0x180034847  call    ?IsFramingRangeDontCare@@YAHUKS_FRAMING_RANGE@@@Z; IsFramingRangeDontCare(KS_FRAMING_RANGE)
0x18003484c  test    eax, eax
0x18003484e  jnz     short loc_180034853
0x180034850  or      dword ptr [rbx], 8
0x180034853  movsd   xmm0, qword ptr [rbp+90h+var_C4.MinFrameSize]
0x180034858  mov     eax, [rbp+90h+var_C4.Stepping]
0x18003485b  lea     rcx, [rsp+190h+var_160]; struct KS_FRAMING_RANGE
0x180034860  movsd   qword ptr [rsp+190h+var_160], xmm0
0x180034866  mov     dword ptr [rsp+190h+var_160+8], eax
0x18003486a  call    ?IsFramingRangeDontCare@@YAHUKS_FRAMING_RANGE@@@Z; IsFramingRangeDontCare(KS_FRAMING_RANGE)
0x18003486f  jmp     loc_1800349CA
0x180034874  lea     r8, [rbp+90h+Buf1]; struct KS_FRAMING_FIXED *
0x180034878  movaps  xmm0, xmmword ptr [rdi]
0x18003487b  lea     rdx, [rsp+190h+var_160]; struct _GUID
0x180034880  mov     rcx, [rsp+190h+var_138]; struct KSALLOCATOR_FRAMING_EX *
0x180034885  movdqa  [rsp+190h+var_160], xmm0
0x18003488b  cmp     [rsp+190h+var_150], r14d
0x180034890  jnz     loc_180034916
0x180034896  call    ?GetFramingFixedFromFramingByMemoryType@@YAHPEAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PEAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByMemoryType(KSALLOCATOR_FRAMING_EX *,_GUID,KS_FRAMING_FIXED *)
0x18003489b  test    eax, eax
0x18003489d  jnz     short loc_1800348B2
0x18003489f  or      [rbx], r14d
0x1800348a2  lea     r8, [rbp+90h+Buf1]; struct KS_FRAMING_FIXED *
0x1800348a6  mov     rcx, [rsp+190h+var_138]; struct KSALLOCATOR_FRAMING_EX *
0x1800348ab  xor     edx, edx; unsigned int
0x1800348ad  call    ?GetFramingFixedFromFramingByIndex@@YAHPEAUKSALLOCATOR_FRAMING_EX@@KPEAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByIndex(KSALLOCATOR_FRAMING_EX *,ulong,KS_FRAMING_FIXED *)
0x1800348b2  test    byte ptr [rbp+90h+var_68], 8
0x1800348b6  jz      short loc_1800348BB
0x1800348b8  or      dword ptr [rbx], 2
0x1800348bb  cmp     esi, 4
0x1800348be  jz      short loc_1800348E6
0x1800348c0  mov     eax, [rbp+90h+var_50]
0x1800348c3  lea     rcx, [rsp+190h+var_160]; struct KS_COMPRESSION
0x1800348c8  mov     dword ptr [rsp+190h+var_160], eax
0x1800348cc  mov     eax, [rbp+90h+var_4C]
0x1800348cf  mov     dword ptr [rsp+190h+var_160+4], eax
0x1800348d3  mov     eax, [rbp+90h+var_48]
0x1800348d6  mov     dword ptr [rsp+190h+var_160+8], eax
0x1800348da  call    ?IsCompressionDontCare@@YAHUKS_COMPRESSION@@@Z; IsCompressionDontCare(KS_COMPRESSION)
0x1800348df  test    eax, eax
0x1800348e1  jnz     short loc_1800348E6
0x1800348e3  or      dword ptr [rbx], 4
0x1800348e6  mov     eax, [rbp+90h+var_5C.Stepping]
0x1800348e9  lea     rcx, [rsp+190h+var_160]; struct KS_FRAMING_RANGE
0x1800348ee  movsd   xmm0, qword ptr [rbp+90h+var_5C.MinFrameSize]
0x1800348f3  movsd   qword ptr [rsp+190h+var_160], xmm0
0x1800348f9  mov     dword ptr [rsp+190h+var_160+8], eax
0x1800348fd  call    ?IsFramingRangeDontCare@@YAHUKS_FRAMING_RANGE@@@Z; IsFramingRangeDontCare(KS_FRAMING_RANGE)
0x180034902  test    eax, eax
0x180034904  jnz     short loc_180034909
0x180034906  or      dword ptr [rbx], 8
0x180034909  movsd   xmm0, qword ptr [rbp+90h+var_44.MinFrameSize]
0x18003490e  mov     eax, [rbp+90h+var_44.Stepping]
0x180034911  jmp     loc_18003485B
0x180034916  call    ?GetFramingFixedFromFramingByMemoryType@@YAHPEAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PEAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByMemoryType(KSALLOCATOR_FRAMING_EX *,_GUID,KS_FRAMING_FIXED *)
0x18003491b  test    eax, eax
0x18003491d  jnz     short loc_18003492F
0x18003491f  mov     rcx, [rsp+190h+var_138]; struct KSALLOCATOR_FRAMING_EX *
0x180034924  lea     r8, [rbp+90h+Buf1]; struct KS_FRAMING_FIXED *
0x180034928  xor     edx, edx; unsigned int
0x18003492a  call    ?GetFramingFixedFromFramingByIndex@@YAHPEAUKSALLOCATOR_FRAMING_EX@@KPEAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByIndex(KSALLOCATOR_FRAMING_EX *,ulong,KS_FRAMING_FIXED *)
0x18003492f  movaps  xmm0, xmmword ptr [rdi]
0x180034932  lea     r8, [rsp+190h+Buf2]; struct KS_FRAMING_FIXED *
0x180034937  mov     rcx, [rsp+190h+var_148]; struct KSALLOCATOR_FRAMING_EX *
0x18003493c  lea     rdx, [rsp+190h+var_160]; struct _GUID
0x180034941  movdqa  [rsp+190h+var_160], xmm0
0x180034947  call    ?GetFramingFixedFromFramingByMemoryType@@YAHPEAUKSALLOCATOR_FRAMING_EX@@U_GUID@@PEAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByMemoryType(KSALLOCATOR_FRAMING_EX *,_GUID,KS_FRAMING_FIXED *)
0x18003494c  test    eax, eax
0x18003494e  jnz     short loc_180034961
0x180034950  mov     rcx, [rsp+190h+var_148]; struct KSALLOCATOR_FRAMING_EX *
0x180034955  lea     r8, [rsp+190h+Buf2]; struct KS_FRAMING_FIXED *
0x18003495a  xor     edx, edx; unsigned int
0x18003495c  call    ?GetFramingFixedFromFramingByIndex@@YAHPEAUKSALLOCATOR_FRAMING_EX@@KPEAUKS_FRAMING_FIXED@@@Z; GetFramingFixedFromFramingByIndex(KSALLOCATOR_FRAMING_EX *,ulong,KS_FRAMING_FIXED *)
0x180034961  mov     r8d, 10h; Size
0x180034967  lea     rdx, [rsp+190h+Buf2]; Buf2
0x18003496c  lea     rcx, [rbp+90h+Buf1]; Buf1
0x180034970  call    memcmp_0
0x180034975  test    eax, eax
0x180034977  jz      short loc_18003497C
0x180034979  or      [rbx], r14d
0x18003497c  mov     eax, [rbp+90h+var_68]
0x18003497f  xor     eax, [rbp+90h+var_E8]
0x180034982  test    al, 8
0x180034984  jz      short loc_180034989
0x180034986  or      dword ptr [rbx], 2
0x180034989  cmp     esi, 4
0x18003498c  jz      short loc_1800349A9
0x18003498e  mov     eax, [rbp+90h+var_D0]
0x180034991  cmp     [rbp+90h+var_50], eax
0x180034994  jnz     short loc_1800349A6
0x180034996  mov     eax, [rbp+90h+var_CC]
0x180034999  cmp     [rbp+90h+var_4C], eax
0x18003499c  jnz     short loc_1800349A6
0x18003499e  mov     eax, [rbp+90h+var_C8]
0x1800349a1  cmp     [rbp+90h+var_48], eax
0x1800349a4  jz      short loc_1800349A9
0x1800349a6  or      dword ptr [rbx], 4
0x1800349a9  lea     rdx, [rbp+90h+var_DC]; struct KS_FRAMING_RANGE *
0x1800349ad  lea     rcx, [rbp+90h+var_5C]; struct KS_FRAMING_RANGE *
0x1800349b1  call    ?IsFramingRangeEqual@@YAHPEAUKS_FRAMING_RANGE@@0@Z; IsFramingRangeEqual(KS_FRAMING_RANGE *,KS_FRAMING_RANGE *)
0x1800349b6  test    eax, eax
0x1800349b8  jnz     short loc_1800349BD
0x1800349ba  or      dword ptr [rbx], 8
0x1800349bd  lea     rdx, [rbp+90h+var_C4]; struct KS_FRAMING_RANGE *
0x1800349c1  lea     rcx, [rbp+90h+var_44]; struct KS_FRAMING_RANGE *
0x1800349c5  call    ?IsFramingRangeEqual@@YAHPEAUKS_FRAMING_RANGE@@0@Z; IsFramingRangeEqual(KS_FRAMING_RANGE *,KS_FRAMING_RANGE *)
0x1800349ca  test    eax, eax
0x1800349cc  jnz     short loc_1800349D1
0x1800349ce  or      dword ptr [rbx], 10h
0x1800349d1  mov     rcx, [rsp+190h+var_130]
0x1800349d6  lea     r8, [rsp+190h+var_150]
0x1800349db  mov     r9d, 2
0x1800349e1  mov     rdx, [rcx]
0x1800349e4  mov     rax, [rdx+20h]
0x1800349e8  mov     rdx, [rsp+190h+var_148]
0x1800349ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800349f2  mov     eax, r14d
0x1800349f5  jmp     loc_18003473A
```
