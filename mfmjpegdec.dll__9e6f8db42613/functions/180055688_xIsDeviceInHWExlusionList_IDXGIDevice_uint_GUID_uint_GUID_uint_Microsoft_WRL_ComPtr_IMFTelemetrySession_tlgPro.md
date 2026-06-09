# xIsDeviceInHWExlusionList(IDXGIDevice *,uint,_GUID *,uint,_GUID *,uint *,Microsoft::WRL::ComPtr<IMFTelemetrySession>,_tlgProvider_t const *)

- ea: `0x180055688`
- end: `0x180055be4`
- name: `?xIsDeviceInHWExlusionList@@YA_NPEAUIDXGIDevice@@IPEAU_GUID@@I1PEAIV?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@PEBU_tlgProvider_t@@@Z`
- size: `1372`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004bd00`

## callees

- `0x180014874`
- `0x1800151b0`
- `0x180024220`
- `0x180024bf4`
- `0x18004a11c`
- `0x18004aa94`
- `0x180055590`
- `0x180055650`
- `0x180055688`
- `0x18006ef8f`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall xIsDeviceInHWExlusionList(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int *a6,
        __int64 a7,
        __int64 a8)
{
  int v9; // r12d
  int v10; // r13d
  char v11; // si
  char v12; // r15
  char v13; // r14
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  unsigned int v15; // ecx
  __int64 v16; // r14
  struct __tagHWExclusionListEntry near **v17; // r11
  unsigned int v18; // r15d
  __int64 v19; // r13
  unsigned int v20; // r12d
  __m128i *v21; // rdi
  __m128i v22; // xmm2
  char v23; // cl
  char v24; // dl
  char v25; // bl
  char v26; // di
  bool v27; // bl
  _QWORD *v28; // rdi
  _DWORD *v29; // r14
  __int64 v30; // r8
  int v31; // r8d
  int v32; // r9d
  __int64 v33; // rcx
  char v35; // [rsp+60h] [rbp-A0h]
  char v36; // [rsp+61h] [rbp-9Fh] BYREF
  char v37; // [rsp+62h] [rbp-9Eh]
  char v38; // [rsp+63h] [rbp-9Dh] BYREF
  int v39; // [rsp+64h] [rbp-9Ch]
  int v40; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+6Ch] [rbp-94h] BYREF
  int v42; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v43; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v44; // [rsp+78h] [rbp-88h] BYREF
  __int64 v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  __int128 v49; // [rsp+A0h] [rbp-60h] BYREF
  int *v50; // [rsp+B0h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-48h]
  GUID v52; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v53[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v54[256]; // [rsp+130h] [rbp+30h] BYREF
  int v55; // [rsp+230h] [rbp+130h]
  int v56; // [rsp+234h] [rbp+134h]
  int v57; // [rsp+238h] [rbp+138h]
  int v58; // [rsp+23Ch] [rbp+13Ch]

  LODWORD(v45) = a4;
  *(_QWORD *)&v49 = a3;
  v47 = a2;
  *(_QWORD *)&v52.Data1 = a5;
  v50 = a6;
  v48 = a7;
  v51 = a7;
  v53[0] = a8;
  v9 = 0;
  v42 = 0;
  v46 = 0;
  memset_0(v54, 0, 0x130u);
  v10 = 0;
  v43 = 0;
  v41 = 0;
  v44 = 0;
  v40 = 0;
  v11 = 1;
  v12 = 1;
  v38 = 1;
  v13 = 1;
  v36 = 1;
  v37 = 0;
  v35 = 0;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 56LL);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v46);
  v15 = v14(a1, &v46);
  v39 = v15;
  if ( !v15 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v46 + 64LL))(v46, v54);
    v39 = v15;
    if ( !v15 )
    {
      v16 = 0;
      v17 = &g_rgHWExclusionList;
      v18 = v47;
      v19 = v49;
      v20 = v45;
      do
      {
        if ( LODWORD(v17[10 * v16 + 9]) )
        {
          v49 = *(_OWORD *)((char *)&v17[10 * v16] + 4);
          if ( (unsigned __int8)_DoesHWExclusionEntryGuidMatch(&v49, v18, v19) )
          {
            v21 = (__m128i *)&v17[10 * v16];
            v22 = v21[2];
            v23 = 1;
            v24 = _mm_cvtsi128_si32(_mm_srli_si128(v21[3], 4));
            if ( (v24 & 1) != 0 )
              v23 = v55 == _mm_cvtsi128_si32(_mm_srli_si128(v22, 4));
            if ( (v24 & 2) != 0 )
              v23 &= v56 == _mm_cvtsi128_si32(_mm_srli_si128(v22, 8));
            if ( (v24 & 4) != 0 )
              v23 &= v57 == _mm_cvtsi128_si32(_mm_srli_si128(v22, 12));
            if ( (v24 & 8) != 0 )
              v23 &= v58 == _mm_cvtsi128_si32(v21[3]);
            if ( v23 )
            {
              v45 = 0;
              v15 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v46 + 72LL))(
                      v46,
                      &GUID_9b7e4c0f_342c_4106_a19f_4f2704f689f0,
                      &v45);
              v39 = v15;
              if ( v15 )
                goto LABEL_23;
              if ( !memcmp_0((char *)v21[1].m128i_i64 + 4, qword_180092560, 0x10u)
                || (v49 = *(_OWORD *)((char *)&g_rgHWExclusionList + 80 * v16 + 20),
                    !(unsigned __int8)_DoesHWExclusionEntryGuidMatch(&v49, v20, *(_QWORD *)&v52.Data1)) )
              {
                v35 = 1;
                __CheckDriverVersionRule(v45, v21, &v38, &v43, &v41);
              }
              else
              {
                v37 = 1;
                __CheckDriverVersionRule(v45, v21, &v36, &v44, &v40);
              }
              v17 = &g_rgHWExclusionList;
            }
          }
        }
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < 6 );
      v15 = v39;
LABEL_23:
      v10 = v43;
      v12 = v38;
      v13 = v36;
      v25 = v37;
      v9 = v42;
      if ( v37 && v36 )
      {
        v26 = v35;
      }
      else
      {
        v26 = v35;
        if ( !v35 || !v38 )
          goto LABEL_39;
      }
      if ( v26 && v38 )
      {
        if ( g_wppLevels >= 8u )
        {
          WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8d9918f97da234c60b38903eb04d5f47_Traceguids, v43, 0);
          v15 = v39;
        }
        v9 = 1;
      }
      if ( v25 && v13 )
      {
        if ( g_wppLevels >= 8u )
          WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_8d9918f97da234c60b38903eb04d5f47_Traceguids, v44, 0);
        v9 |= 2u;
        v15 = v39;
      }
LABEL_39:
      if ( !v15 )
        goto LABEL_44;
      goto LABEL_42;
    }
  }
  v26 = 0;
  v25 = 0;
LABEL_42:
  if ( g_wppLevels >= 8u )
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_8d9918f97da234c60b38903eb04d5f47_Traceguids, v15, 0);
LABEL_44:
  v27 = v25 && v13 || v26 && v12;
  v28 = (_QWORD *)v48;
  if ( !*(_QWORD *)v48
    || !(*(unsigned int (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v48 + 320LL))(
          *(_QWORD *)v48,
          MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT) )
  {
    v29 = (_DWORD *)v53[0];
    if ( v53[0] )
    {
      v52 = GUID_00000000_0000_0000_0000_000000000000;
      v30 = 0;
      if ( *v28 )
      {
        v52 = *(GUID *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(*(_QWORD *)*v28 + 280LL))(*v28, v53, 0);
        v30 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v28 + 296LL))(*v28);
      }
      if ( *v29 > 5u && (unsigned __int8)tlgKeywordOn(v29, 0x400000000000LL, v30) )
      {
        v42 = v10;
        if ( v27 && (v9 & 2) != 0 )
        {
          v36 = 1;
        }
        else
        {
          v36 = 0;
          if ( !v27 )
            goto LABEL_62;
        }
        if ( (v9 & 1) != 0 )
        {
LABEL_63:
          v38 = v11;
          v41 = v39;
          v40 = v31;
          v53[0] = &v52;
          v48 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
            (_DWORD)v29,
            (unsigned int)&unk_180094B78,
            v31,
            v32,
            (__int64)&v48,
            (__int64)v53,
            (__int64)&v40,
            (__int64)&v41,
            (__int64)&v38,
            (__int64)&v36,
            (__int64)&v42);
          goto LABEL_64;
        }
LABEL_62:
        v11 = 0;
        goto LABEL_63;
      }
    }
  }
LABEL_64:
  if ( v50 )
    *v50 = v9;
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v46);
  v33 = *v28;
  if ( *v28 )
  {
    *v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  return v27;
}

```

## disassembly

```asm
0x180055688  mov     [rsp-8+arg_8], rbx
0x18005568d  push    rbp
0x18005568e  push    rsi
0x18005568f  push    rdi
0x180055690  push    r12
0x180055692  push    r13
0x180055694  push    r14
0x180055696  push    r15
0x180055698  lea     rbp, [rsp-170h]
0x1800556a0  sub     rsp, 270h
0x1800556a7  mov     rax, cs:__security_cookie
0x1800556ae  xor     rax, rsp
0x1800556b1  mov     [rbp+1A0h+var_40], rax
0x1800556b8  mov     dword ptr [rbp+1A0h+var_220], r9d
0x1800556bc  mov     qword ptr [rbp+1A0h+var_200], r8
0x1800556c0  mov     [rbp+1A0h+var_210], edx
0x1800556c3  mov     rdi, rcx
0x1800556c6  mov     rax, [rbp+1A0h+arg_20]
0x1800556cd  mov     qword ptr [rbp+1A0h+var_190], rax
0x1800556d1  mov     rcx, [rbp+1A0h+arg_28]
0x1800556d8  mov     [rbp+1A0h+var_1F0], rcx
0x1800556dc  mov     rax, [rbp+1A0h+arg_30]
0x1800556e3  mov     [rbp+1A0h+var_208], rax
0x1800556e7  mov     [rbp+1A0h+var_1E8], rax
0x1800556eb  mov     rax, [rbp+1A0h+arg_38]
0x1800556f2  mov     [rbp+1A0h+var_180], rax
0x1800556f6  xor     ebx, ebx
0x1800556f8  mov     r12d, ebx
0x1800556fb  mov     [rsp+2A0h+var_230], ebx
0x1800556ff  mov     [rbp+1A0h+var_218], rbx
0x180055703  xor     edx, edx; Val
0x180055705  mov     r8d, 130h; Size
0x18005570b  lea     rcx, [rbp+1A0h+var_170]; void *
0x18005570f  call    memset_0
0x180055714  mov     r13d, ebx
0x180055717  mov     [rsp+2A0h+var_22C], ebx
0x18005571b  mov     [rsp+2A0h+var_234], ebx
0x18005571f  mov     [rsp+2A0h+var_228], ebx
0x180055723  mov     [rsp+2A0h+var_238], ebx
0x180055727  lea     esi, [rbx+1]
0x18005572a  mov     r15b, sil
0x18005572d  mov     [rsp+2A0h+var_23D], sil
0x180055732  mov     r14b, sil
0x180055735  mov     [rsp+2A0h+var_23F], sil
0x18005573a  mov     [rsp+2A0h+var_23E], bl
0x18005573e  mov     [rsp+2A0h+var_240], bl
0x180055742  mov     rax, [rdi]
0x180055745  mov     rbx, [rax+38h]
0x180055749  lea     rcx, [rbp+1A0h+var_218]
0x18005574d  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180055752  lea     rdx, [rbp+1A0h+var_218]
0x180055756  mov     rcx, rdi
0x180055759  mov     rax, rbx
0x18005575c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055761  mov     ecx, eax
0x180055763  mov     [rsp+2A0h+var_23C], eax
0x180055767  test    eax, eax
0x180055769  jnz     loc_1800559F6
0x18005576f  mov     rcx, [rbp+1A0h+var_218]
0x180055773  mov     rax, [rcx]
0x180055776  lea     rdx, [rbp+1A0h+var_170]
0x18005577a  mov     rax, [rax+40h]
0x18005577e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055783  mov     ecx, eax
0x180055785  mov     [rsp+2A0h+var_23C], eax
0x180055789  test    eax, eax
0x18005578b  jnz     loc_1800559F6
0x180055791  xor     r14d, r14d
0x180055794  lea     r11, ?g_rgHWExclusionList@@3PAU__tagHWExclusionListEntry@@A; __tagHWExclusionListEntry near * g_rgHWExclusionList
0x18005579b  mov     r15d, [rbp+1A0h+var_210]
0x18005579f  mov     r13, qword ptr [rbp+1A0h+var_200]
0x1800557a3  mov     r12d, dword ptr [rbp+1A0h+var_220]
0x1800557a7  lea     rbx, [r14+r14*4]
0x1800557ab  add     rbx, rbx
0x1800557ae  cmp     dword ptr [r11+rbx*8+48h], 0
0x1800557b4  jz      loc_18005591A
0x1800557ba  movups  xmm0, xmmword ptr [r11+rbx*8+4]
0x1800557c0  movdqu  [rbp+1A0h+var_200], xmm0
0x1800557c5  mov     r8, r13
0x1800557c8  mov     edx, r15d
0x1800557cb  lea     rcx, [rbp+1A0h+var_200]
0x1800557cf  call    __DoesHWExclusionEntryGuidMatch
0x1800557d4  test    al, al
0x1800557d6  jz      loc_18005591A
0x1800557dc  lea     rdi, [r11+rbx*8]
0x1800557e0  movups  xmm2, xmmword ptr [rdi+20h]
0x1800557e4  movups  xmm3, xmmword ptr [rdi+30h]
0x1800557e8  mov     cl, sil
0x1800557eb  movdqa  xmm1, xmm3
0x1800557ef  psrldq  xmm1, 4
0x1800557f4  movd    edx, xmm1
0x1800557f8  test    sil, dl
0x1800557fb  jz      short loc_180055813
0x1800557fd  movdqa  xmm0, xmm2
0x180055801  psrldq  xmm0, 4
0x180055806  movd    eax, xmm0
0x18005580a  cmp     [rbp+1A0h+var_70], eax
0x180055810  setz    cl
0x180055813  test    dl, 2
0x180055816  jz      short loc_180055830
0x180055818  movdqa  xmm0, xmm2
0x18005581c  psrldq  xmm0, 8
0x180055821  movd    eax, xmm0
0x180055825  cmp     [rbp+1A0h+var_6C], eax
0x18005582b  setz    al
0x18005582e  and     cl, al
0x180055830  test    dl, 4
0x180055833  jz      short loc_180055849
0x180055835  psrldq  xmm2, 0Ch
0x18005583a  movd    eax, xmm2
0x18005583e  cmp     [rbp+1A0h+var_68], eax
0x180055844  setz    al
0x180055847  and     cl, al
0x180055849  test    dl, 8
0x18005584c  jz      short loc_18005585D
0x18005584e  movd    eax, xmm3
0x180055852  cmp     [rbp+1A0h+var_64], eax
0x180055858  setz    al
0x18005585b  and     cl, al
0x18005585d  test    cl, cl
0x18005585f  jz      loc_18005591A
0x180055865  mov     [rbp+1A0h+var_220], 0
0x18005586d  mov     rcx, [rbp+1A0h+var_218]
0x180055871  mov     rax, [rcx]
0x180055874  lea     r8, [rbp+1A0h+var_220]
0x180055878  lea     rdx, _GUID_9b7e4c0f_342c_4106_a19f_4f2704f689f0
0x18005587f  mov     rax, [rax+48h]
0x180055883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055888  mov     ecx, eax
0x18005588a  mov     [rsp+2A0h+var_23C], eax
0x18005588e  test    eax, eax
0x180055890  jnz     loc_18005592B
0x180055896  lea     rcx, [rdi+14h]; Buf1
0x18005589a  lea     r8d, [rax+10h]; Size
0x18005589e  lea     rdx, qword_180092560; Buf2
0x1800558a5  call    memcmp_0
0x1800558aa  test    eax, eax
0x1800558ac  jz      short loc_1800558EE
0x1800558ae  lea     rax, ?g_rgHWExclusionList@@3PAU__tagHWExclusionListEntry@@A; __tagHWExclusionListEntry near * g_rgHWExclusionList
0x1800558b5  movups  xmm0, xmmword ptr [rax+rbx*8+14h]
0x1800558ba  movdqu  [rbp+1A0h+var_200], xmm0
0x1800558bf  mov     r8, qword ptr [rbp+1A0h+var_190]
0x1800558c3  mov     edx, r12d
0x1800558c6  lea     rcx, [rbp+1A0h+var_200]
0x1800558ca  call    __DoesHWExclusionEntryGuidMatch
0x1800558cf  test    al, al
0x1800558d1  jz      short loc_1800558EE
0x1800558d3  mov     [rsp+2A0h+var_23E], sil
0x1800558d8  lea     rcx, [rsp+2A0h+var_238]
0x1800558dd  mov     [rsp+2A0h+var_280], rcx
0x1800558e2  lea     r9, [rsp+2A0h+var_228]
0x1800558e7  lea     r8, [rsp+2A0h+var_23F]
0x1800558ec  jmp     short loc_180055907
0x1800558ee  mov     [rsp+2A0h+var_240], sil
0x1800558f3  lea     rax, [rsp+2A0h+var_234]
0x1800558f8  mov     [rsp+2A0h+var_280], rax
0x1800558fd  lea     r9, [rsp+2A0h+var_22C]
0x180055902  lea     r8, [rsp+2A0h+var_23D]
0x180055907  mov     rdx, rdi
0x18005590a  mov     rcx, [rbp+1A0h+var_220]
0x18005590e  call    ?__CheckDriverVersionRule@@YAXU__tagDriverVersion@@PEAU__tagHWExclusionListEntry@@PEA_NPEAI3@Z; __CheckDriverVersionRule(__tagDriverVersion,__tagHWExclusionListEntry *,bool *,uint *,uint *)
0x180055913  lea     r11, ?g_rgHWExclusionList@@3PAU__tagHWExclusionListEntry@@A; __tagHWExclusionListEntry near * g_rgHWExclusionList
0x18005591a  add     r14d, esi
0x18005591d  cmp     r14d, 6
0x180055921  jb      loc_1800557A7
0x180055927  mov     ecx, [rsp+2A0h+var_23C]
0x18005592b  mov     r13d, [rsp+2A0h+var_22C]
0x180055930  mov     r15b, [rsp+2A0h+var_23D]
0x180055935  mov     r14b, [rsp+2A0h+var_23F]
0x18005593a  mov     bl, [rsp+2A0h+var_23E]
0x18005593e  test    bl, bl
0x180055940  mov     r12d, [rsp+2A0h+var_230]
0x180055945  jz      short loc_18005594C
0x180055947  test    r14b, r14b
0x18005594a  jnz     short loc_180055965
0x18005594c  mov     dil, [rsp+2A0h+var_240]
0x180055951  test    dil, dil
0x180055954  jz      loc_1800559F0
0x18005595a  test    r15b, r15b
0x18005595d  jz      loc_1800559F0
0x180055963  jmp     short loc_18005596A
0x180055965  mov     dil, [rsp+2A0h+var_240]
0x18005596a  test    dil, dil
0x18005596d  jz      short loc_1800559AC
0x18005596f  test    r15b, r15b
0x180055972  jz      short loc_1800559AC
0x180055974  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18005597b  jb      short loc_1800559A9
0x18005597d  mov     edx, 0Ah
0x180055982  mov     [rsp+2A0h+var_280], 0
0x18005598b  mov     r9d, r13d
0x18005598e  lea     r8, WPP_8d9918f97da234c60b38903eb04d5f47_Traceguids
0x180055995  mov     rcx, cs:WPP_GLOBAL_Control
0x18005599c  mov     rcx, [rcx+10h]
0x1800559a0  call    WPP_SF_dq
0x1800559a5  mov     ecx, [rsp+2A0h+var_23C]
0x1800559a9  mov     r12d, esi
0x1800559ac  test    bl, bl
0x1800559ae  jz      short loc_1800559F0
0x1800559b0  test    r14b, r14b
0x1800559b3  jz      short loc_1800559F0
0x1800559b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800559bc  jb      short loc_1800559E8
0x1800559be  mov     edx, 0Bh
0x1800559c3  mov     [rsp+2A0h+var_280], 0
0x1800559cc  mov     r9d, [rsp+2A0h+var_228]
0x1800559d1  lea     r8, WPP_8d9918f97da234c60b38903eb04d5f47_Traceguids
0x1800559d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800559df  mov     rcx, [rcx+10h]
0x1800559e3  call    WPP_SF_dq
0x1800559e8  or      r12d, 2
0x1800559ec  mov     ecx, [rsp+2A0h+var_23C]
0x1800559f0  test    ecx, ecx
0x1800559f2  jz      short loc_180055A2D
0x1800559f4  jmp     short loc_1800559FC
0x1800559f6  mov     dil, r13b
0x1800559f9  mov     bl, r13b
0x1800559fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180055a03  jb      short loc_180055A2D
0x180055a05  mov     edx, 0Ch
0x180055a0a  mov     [rsp+2A0h+var_280], 0
0x180055a13  mov     r9d, ecx
0x180055a16  lea     r8, WPP_8d9918f97da234c60b38903eb04d5f47_Traceguids
0x180055a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180055a24  mov     rcx, [rcx+10h]
0x180055a28  call    WPP_SF_dq
0x180055a2d  test    bl, bl
0x180055a2f  jz      short loc_180055A36
0x180055a31  test    r14b, r14b
0x180055a34  jnz     short loc_180055A40
0x180055a36  test    dil, dil
0x180055a39  jz      short loc_180055A45
0x180055a3b  test    r15b, r15b
0x180055a3e  jz      short loc_180055A45
0x180055a40  mov     bl, sil
0x180055a43  jmp     short loc_180055A47
0x180055a45  xor     bl, bl
0x180055a47  mov     rdi, [rbp+1A0h+var_208]
0x180055a4b  mov     rcx, [rdi]
0x180055a4e  test    rcx, rcx
0x180055a51  jz      short loc_180055A71
0x180055a53  mov     rax, [rcx]
0x180055a56  lea     rdx, MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT
0x180055a5d  mov     rax, [rax+140h]
0x180055a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a69  test    eax, eax
0x180055a6b  jnz     loc_180055B87
0x180055a71  mov     r14, [rbp+1A0h+var_180]
0x180055a75  test    r14, r14
0x180055a78  jz      loc_180055B87
0x180055a7e  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180055a85  movdqu  [rbp+1A0h+var_190], xmm0
0x180055a8a  xor     r8d, r8d
0x180055a8d  mov     rcx, [rdi]
0x180055a90  test    rcx, rcx
0x180055a93  jz      short loc_180055AC5
0x180055a95  mov     rax, [rcx]
0x180055a98  lea     rdx, [rbp+1A0h+var_180]
0x180055a9c  mov     rax, [rax+118h]
0x180055aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055aa8  movups  xmm0, xmmword ptr [rax]
0x180055aab  movdqu  [rbp+1A0h+var_190], xmm0
0x180055ab0  mov     rcx, [rdi]
0x180055ab3  mov     rax, [rcx]
0x180055ab6  mov     rax, [rax+128h]
0x180055abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ac2  mov     r8d, eax
0x180055ac5  mov     ecx, [r14]
0x180055ac8  cmp     ecx, 5
0x180055acb  jbe     loc_180055B87
0x180055ad1  mov     rdx, 400000000000h
0x180055adb  mov     rcx, r14
0x180055ade  call    _tlgKeywordOn
0x180055ae3  test    al, al
0x180055ae5  jz      loc_180055B87
0x180055aeb  mov     [rsp+2A0h+var_230], r13d
0x180055af0  test    bl, bl
0x180055af2  jz      short loc_180055B01
0x180055af4  test    r12b, 2
0x180055af8  jz      short loc_180055B01
0x180055afa  mov     [rsp+2A0h+var_23F], sil
0x180055aff  jmp     short loc_180055B0A
0x180055b01  mov     [rsp+2A0h+var_23F], 0
0x180055b06  test    bl, bl
0x180055b08  jz      short loc_180055B0F
0x180055b0a  test    sil, r12b
0x180055b0d  jnz     short loc_180055B12
0x180055b0f  xor     sil, sil
0x180055b12  mov     [rsp+2A0h+var_23D], sil
0x180055b17  mov     eax, [rsp+2A0h+var_23C]
0x180055b1b  mov     [rsp+2A0h+var_234], eax
0x180055b1f  mov     [rsp+2A0h+var_238], r8d
0x180055b24  lea     rax, [rbp+1A0h+var_190]
0x180055b28  mov     [rbp+1A0h+var_180], rax
0x180055b2c  mov     [rbp+1A0h+var_208], 2000000h
0x180055b34  lea     rax, [rsp+2A0h+var_230]
0x180055b39  mov     [rsp+2A0h+var_250], rax
0x180055b3e  lea     rax, [rsp+2A0h+var_23F]
0x180055b43  mov     [rsp+2A0h+var_258], rax
0x180055b48  lea     rax, [rsp+2A0h+var_23D]
  ... truncated ...
```
