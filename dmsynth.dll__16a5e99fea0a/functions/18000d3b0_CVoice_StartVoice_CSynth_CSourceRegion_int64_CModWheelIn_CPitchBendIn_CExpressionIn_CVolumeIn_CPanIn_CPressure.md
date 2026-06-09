# CVoice::StartVoice(CSynth *,CSourceRegion *,__int64,CModWheelIn *,CPitchBendIn *,CExpressionIn *,CVolumeIn *,CPanIn *,CPressureIn *,CReverbIn *,CChorusIn *,CCutOffFreqIn *,CBusIds *,ushort,ushort,long,long)

- ea: `0x18000d3b0`
- end: `0x18000dc99`
- name: `?StartVoice@CVoice@@QEAAHPEAVCSynth@@PEAVCSourceRegion@@_JPEAVCModWheelIn@@PEAVCPitchBendIn@@PEAVCExpressionIn@@PEAVCVolumeIn@@PEAVCPanIn@@PEAVCPressureIn@@PEAVCReverbIn@@PEAVCChorusIn@@PEAVCCutOffFreqIn@@PEAVCBusIds@@GGJJ@Z`
- size: `2281`
- prototype: `__int64 __usercall@<rax>(CVoice *__hidden this@<rcx>, struct CSynth *@<rdx>, struct CSourceRegion *@<r8>, __int64@<r9>, struct CModWheelIn *, struct CPitchBendIn *, struct CExpressionIn *, struct CVolumeIn *, struct CPanIn *, struct CPressureIn *, struct CReverbIn *, struct CChorusIn *, struct CCutOffFreqIn *, struct CBusIds *, unsigned __int16, unsigned __int16, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180004120`

## callees

- `0x18000b1d0`
- `0x18000b710`
- `0x18000bb20`
- `0x18000d0f0`
- `0x18000d3b0`
- `0x18000dca0`

## pseudocode

```c
__int64 __fastcall CVoice::StartVoice(
        CVoice *this,
        struct CSynth *a2,
        struct CSourceRegion *a3,
        __int64 a4,
        struct CModWheelIn *a5,
        struct CPitchBendIn *a6,
        struct CExpressionIn *a7,
        struct CVolumeIn *a8,
        struct CPanIn *a9,
        struct CPressureIn *a10,
        struct CReverbIn *a11,
        struct CChorusIn *a12,
        struct CCutOffFreqIn *a13,
        struct CBusIds *a14,
        unsigned __int16 a15,
        unsigned __int16 a16,
        int a17,
        int a18)
{
  __int64 v18; // rbp
  __int64 v19; // r11
  struct CSynth *v21; // rsi
  __int64 *v23; // rax
  int v24; // ecx
  int v25; // edi
  struct CBusIds *v26; // r12
  int v27; // ecx
  unsigned int v28; // edi
  unsigned int v29; // r8d
  __int64 v30; // rcx
  __int64 *v31; // rax
  int v32; // ecx
  int v33; // edx
  int v34; // ecx
  int v35; // r15d
  __int64 v36; // r14
  unsigned int v37; // ebp
  __int64 v38; // r9
  unsigned int v39; // r8d
  __int64 v40; // rcx
  __int64 v41; // rdx
  unsigned int v42; // ecx
  int v43; // eax
  struct CModWheelIn *v44; // r8
  _DWORD *v45; // rdi
  struct CPressureIn *v46; // r9
  __int64 v47; // rcx
  bool v48; // zf
  __int64 v49; // rax
  int v50; // r14d
  __int64 started; // rax
  __int64 v52; // rax
  __int64 v53; // rcx
  __int128 v54; // xmm0
  int v55; // eax
  int v56; // ecx
  int v57; // edx
  int v58; // ecx
  __int64 v59; // rax
  struct CSynth *v60; // r11
  int v61; // eax
  int v62; // ecx
  __int64 v63; // rax
  int v64; // eax
  _DWORD *v65; // r8
  unsigned int v66; // eax
  __int64 v67; // r11
  int v68; // eax
  unsigned int v69; // r9d
  unsigned __int64 v70; // rcx
  unsigned __int64 v71; // rax
  unsigned __int64 v72; // rdx
  struct CPitchBendIn *v73; // rax
  __int64 **v74; // rax
  __int64 *v75; // rcx
  int i; // eax
  int v77; // r8d
  unsigned int v79; // [rsp+70h] [rbp-58h] BYREF
  int v80; // [rsp+74h] [rbp-54h]
  __int64 v81; // [rsp+78h] [rbp-50h]
  unsigned int v82; // [rsp+D0h] [rbp+8h] BYREF
  struct CSynth *v83; // [rsp+D8h] [rbp+10h] BYREF
  unsigned int v84; // [rsp+E0h] [rbp+18h] BYREF
  __int64 v85; // [rsp+E8h] [rbp+20h]

  v85 = a4;
  v83 = a2;
  *((_QWORD *)this + 60) = a2;
  v18 = a4;
  v19 = *((_QWORD *)a3 + 6);
  v81 = v19;
  v21 = a2;
  if ( !v19 )
    return 0;
  *((_DWORD *)this + 217) = *((_DWORD *)a3 + 11);
  if ( *((_DWORD *)a2 + 46) )
  {
    v25 = a17;
  }
  else
  {
    v23 = *(__int64 **)a8;
    v24 = *((_DWORD *)a8 + 4);
    if ( *(_QWORD *)a8 )
    {
      do
      {
        if ( v23[1] > a4 )
          break;
        v24 = *((_DWORD *)v23 + 4);
        v23 = (__int64 *)*v23;
      }
      while ( v23 );
    }
    v25 = *((_DWORD *)&CMIDIRecorder::m_vrMIDIToVREL + v24) + a17;
  }
  v26 = a14;
  LOWORD(v82) = *((_WORD *)a3 + 29);
  v27 = *((_DWORD *)&CMIDIRecorder::m_vrMIDIToVREL + a16);
  *((_DWORD *)this + 143) = *((unsigned __int8 *)a3 + 63);
  *((_DWORD *)this + 142) = *((unsigned __int8 *)a3 + 60);
  v28 = *((__int16 *)a3 + 28) + v27 + v25;
  *((_DWORD *)this + 126) = *(__int16 *)(*((_QWORD *)a3 + 6) + 158LL);
  *((_DWORD *)this + 218) = *((_WORD *)a3 + 33) & 2;
  if ( *(_DWORD *)v26 == 1 )
  {
    v29 = *((_DWORD *)a2 + 8);
    if ( v29 )
    {
      v30 = 0;
      while ( *(_DWORD *)(*((_QWORD *)a2 + 1) + 4 * v30) != *((_DWORD *)v26 + 1) )
      {
        v30 = (unsigned int)(v30 + 1);
        if ( (unsigned int)v30 >= v29 )
          goto LABEL_16;
      }
      if ( !*(_DWORD *)(4 * v30 + *((_QWORD *)a2 + 2)) )
        *((_DWORD *)this + 218) = 1;
    }
  }
LABEL_16:
  if ( !*((_DWORD *)a2 + 53) || *((_DWORD *)a2 + 45) || *((_DWORD *)this + 218) )
  {
    v84 = v28;
    v79 = v28;
  }
  else
  {
    v31 = *(__int64 **)a9;
    v32 = *((_DWORD *)a9 + 4);
    if ( *(_QWORD *)a9 )
    {
      do
      {
        if ( v31[1] > a4 )
          break;
        v32 = *((_DWORD *)v31 + 4);
        v31 = (__int64 *)*v31;
      }
      while ( v31 );
    }
    v33 = 0;
    v34 = *((_DWORD *)this + 126) + v32;
    if ( v34 >= 0 )
      v33 = v34;
    if ( v33 > 127 )
      v33 = 127;
    v84 = v28 + *((_DWORD *)&CVoice::m_svrPanToVREL + 127 - v33);
    v79 = v28 + *((_DWORD *)&CVoice::m_svrPanToVREL + v33);
  }
  v35 = 0;
  v80 = 0;
  v36 = 0;
  if ( *(_DWORD *)v26 )
  {
    v37 = v84;
    while ( 1 )
    {
      v38 = *((_QWORD *)this + 60);
      v39 = *(_DWORD *)(v38 + 32);
      if ( v39 )
        break;
LABEL_53:
      v36 = (unsigned int)(v36 + 1);
      if ( (unsigned int)v36 >= *(_DWORD *)v26 )
      {
        v18 = v85;
        v21 = v83;
        v19 = v81;
        goto LABEL_55;
      }
    }
    v40 = 0;
    while ( 1 )
    {
      v41 = 4 * v40;
      if ( *(_DWORD *)(4 * v40 + *(_QWORD *)(v38 + 8)) == *((_DWORD *)v26 + v36 + 1) )
        break;
      v40 = (unsigned int)(v40 + 1);
      if ( (unsigned int)v40 >= v39 )
        goto LABEL_53;
    }
    v42 = *(_DWORD *)(v41 + *(_QWORD *)(v38 + 16));
    if ( !v35 )
      v80 = *(_DWORD *)(v41 + *(_QWORD *)(v38 + 24));
    *((_DWORD *)this + v36 + 251) = -9600;
    if ( v42 > 0x11 )
    {
      if ( v42 != 64 && v42 != 65 )
      {
        if ( v42 == 512 )
        {
          v35 = 1;
        }
        else if ( v42 == -1 )
        {
          goto LABEL_52;
        }
      }
    }
    else
    {
      if ( (*((_BYTE *)a3 + 66) & 2) == 0 )
      {
        if ( v42 )
        {
          if ( v42 == 1 )
            *((_DWORD *)this + v36 + 251) = v79;
        }
        else
        {
          *((_DWORD *)this + v36 + 251) = v37;
        }
        goto LABEL_52;
      }
      v43 = *((_DWORD *)a3 + 17);
      if ( !_bittest(&v43, v42) )
      {
LABEL_52:
        *((_DWORD *)this + v36 + 283) = dword_18001EB10;
        *((_DWORD *)this + v36 + 219) = -9600;
        goto LABEL_53;
      }
    }
    *((_DWORD *)this + v36 + 251) = v28;
    goto LABEL_52;
  }
LABEL_55:
  v44 = a5;
  v45 = (_DWORD *)((char *)this + 8);
  v46 = a10;
  v47 = 44100;
  *((_DWORD *)this + 20) = 1;
  *((_QWORD *)this + 7) = v44;
  *((_QWORD *)this + 9) = v46;
  *(_OWORD *)((char *)this + 8) = *(_OWORD *)(v19 + 112);
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)(v19 + 128);
  *((_QWORD *)this + 5) = *(_QWORD *)(v19 + 144);
  v48 = *((_WORD *)this + 13) == 0;
  *((_QWORD *)this + 6) = v18;
  if ( !v48 || *((_WORD *)this + 12) || *((_WORD *)this + 15) || *((_WORD *)this + 14) )
    v49 = 0x200000 / *v45;
  else
    v49 = 44100;
  *((_QWORD *)this + 8) = v49;
  *((_QWORD *)this + 61) = v49;
  *((_DWORD *)this + 182) = 1;
  *((_QWORD *)this + 88) = v44;
  *((_QWORD *)this + 90) = v46;
  *((_OWORD *)this + 41) = *(_OWORD *)(v19 + 160);
  *((_OWORD *)this + 42) = *(_OWORD *)(v19 + 176);
  *((_QWORD *)this + 86) = *(_QWORD *)(v19 + 192);
  v48 = *((_WORD *)this + 337) == 0;
  *((_QWORD *)this + 87) = v18;
  if ( !v48 || *((_WORD *)this + 336) || *((_WORD *)this + 339) || *((_WORD *)this + 338) )
    v47 = 0x200000 / *((_DWORD *)this + 164);
  *((_QWORD *)this + 89) = v47;
  if ( v47 < *((_QWORD *)this + 61) )
    *((_QWORD *)this + 61) = v47;
  v50 = a15;
  started = CVoiceEG::StartVoice((CVoice *)((char *)this + 88), (struct CSourceEG *)v19, v18, a15, a16, 0);
  if ( started < *((_QWORD *)this + 61) )
    *((_QWORD *)this + 61) = started;
  v52 = CVoiceEG::StartVoice(
          (CVoice *)((char *)this + 168),
          (struct CSourceEG *)(v81 + 56),
          v18,
          v50,
          a16,
          *((_DWORD *)v21 + 52) / 0x3E8u);
  if ( v52 >= *((_QWORD *)this + 61) )
    v52 = *((_QWORD *)this + 61);
  else
    *((_QWORD *)this + 61) = v52;
  v53 = *((_QWORD *)v21 + 25);
  if ( v52 > v53 )
    *((_QWORD *)this + 61) = v53;
  v54 = *(_OWORD *)(v81 + 200);
  v55 = a16;
  *((_QWORD *)this + 79) = (char *)this + 88;
  *((_OWORD *)this + 38) = v54;
  v56 = v55 * *((__int16 *)this + 310);
  *((_QWORD *)this + 78) = v45;
  v57 = (unsigned __int64)(2164392969LL * v56) >> 32;
  v58 = v50 * *((__int16 *)this + 311);
  *((_DWORD *)this + 162) = ((unsigned int)v57 >> 31) + (v57 >> 6);
  *((_DWORD *)this + 163) = v58 / 127;
  v59 = *((_QWORD *)a3 + 1);
  if ( !v59 || !*(_QWORD *)(v59 + 32) )
    return 0;
  v60 = v83;
  *((_DWORD *)this + 78) = 0;
  *(_QWORD *)((char *)this + 388) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 96) = 0;
  *(_OWORD *)((char *)this + 248) = *(_OWORD *)((char *)a3 + 8);
  *(_OWORD *)((char *)this + 264) = *(_OWORD *)((char *)a3 + 24);
  *((_QWORD *)this + 35) = *((_QWORD *)a3 + 5);
  v61 = *((unsigned __int8 *)this + 281);
  *((_QWORD *)this + 37) = *(_QWORD *)(*((_QWORD *)a3 + 1) + 32LL);
  v62 = (__int16)v82;
  *((_DWORD *)this + 93) = v61;
  *((_QWORD *)this + 36) = v60;
  ++*(_WORD *)(*((_QWORD *)a3 + 1) + 44LL);
  v63 = *((_QWORD *)a3 + 1);
  ++*(_WORD *)(v63 + 46);
  ++*(_WORD *)(v63 + 44);
  v64 = CDigitalAudio::PRELToPFRACT(100 * (v50 - (unsigned int)*((unsigned __int8 *)a3 + 42))
                                  + a18
                                  + *((__int16 *)a3 + 16) + v62);
  *((_DWORD *)this + 76) = v64;
  v65 = (_DWORD *)((char *)this + 372);
  v66 = *((_DWORD *)a3 + 7) * v64;
  *((_DWORD *)this + 76) = v66;
  v68 = v66 / *(_DWORD *)(v67 + 208);
  *((_DWORD *)this + 76) = v68;
  *((_DWORD *)this + 77) = v68;
  v69 = *((_DWORD *)a3 + 6);
  *((_DWORD *)this + 83) = v69 >= 0x80000;
  if ( (unsigned int)(*((_DWORD *)a3 + 5) - *((_DWORD *)a3 + 4)) >= 0x80000 )
    *v65 = 1;
  *((_QWORD *)this + 42) = 0;
  v70 = (unsigned __int64)*((unsigned int *)a3 + 4) << 12;
  *((_QWORD *)this + 43) = v70;
  v71 = (unsigned __int64)*((unsigned int *)a3 + 5) << 12;
  *((_QWORD *)this + 44) = v71;
  v72 = (unsigned __int64)*((unsigned int *)a3 + 6) << 12;
  *((_QWORD *)this + 45) = v72;
  *((_DWORD *)this + 79) = 0;
  *((_DWORD *)this + 80) = v70;
  *((_DWORD *)this + 81) = v71;
  if ( v71 <= v70 )
    *v65 = 1;
  if ( v69 >= 0x80000 )
    LODWORD(v72) = 0x7FFFFFFF;
  v73 = a6;
  *((_DWORD *)this + 82) = v72;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = v73;
  *((_QWORD *)this + 54) = a7;
  *((_QWORD *)this + 56) = a9;
  *((_QWORD *)this + 57) = a11;
  *((_QWORD *)this + 58) = a12;
  *((_QWORD *)this + 59) = a13;
  *((_QWORD *)this + 55) = a8;
  *((_OWORD *)this + 46) = *(_OWORD *)v26;
  *((_OWORD *)this + 47) = *((_OWORD *)v26 + 1);
  *((_OWORD *)this + 48) = *((_OWORD *)v26 + 2);
  *((_OWORD *)this + 49) = *((_OWORD *)v26 + 3);
  *((_OWORD *)this + 50) = *((_OWORD *)v26 + 4);
  *((_OWORD *)this + 51) = *((_OWORD *)v26 + 5);
  *((_OWORD *)this + 52) = *((_OWORD *)v26 + 6);
  *((_OWORD *)this + 53) = *((_OWORD *)v26 + 7);
  *((_DWORD *)this + 216) = *((_DWORD *)v26 + 32);
  *((_QWORD *)this + 62) = v18 - 1;
  *((_QWORD *)this + 66) = 0x7FFFFFFFFFFFFFFFLL;
  *(_QWORD *)((char *)this + 548) = 1;
  *((_DWORD *)this + 140) = 0;
  *((_QWORD *)this + 65) = v18;
  *((_QWORD *)this + 67) = 0;
  if ( !*((_QWORD *)this + 61) )
  {
    LODWORD(v83) = 0;
    v79 = 0;
    v84 = 0;
    v82 = 0;
    CVoice::GetNewPitch(this, v18, (int *)&v83);
    v74 = (__int64 **)*((_QWORD *)this + 59);
    v75 = *v74;
    for ( i = *((_DWORD *)v74 + 4); v75; v75 = (__int64 *)*v75 )
    {
      if ( v75[1] > v18 )
        break;
      i = *((_DWORD *)v75 + 4);
    }
    v77 = 100 * (i - 64);
    *((_DWORD *)this + 127) = v77;
    CVoiceFilter::GetCoeff((CVoice *)((char *)this + 608), v18, v77, &v79, &v84, &v82);
    CDigitalAudio::Mix(
      (CVoice *)((char *)this + 248),
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      v80 + (_DWORD)v83,
      *((_WORD *)this + 305) != 0x7FFF,
      v79,
      v84,
      v82);
  }
  *((_DWORD *)this + 139) = 0;
  return 1;
}

```

## disassembly

```asm
0x18000d3b0  mov     [rsp+arg_18], r9
0x18000d3b5  mov     [rsp+arg_8], rdx
0x18000d3ba  push    rbx
0x18000d3bb  push    rbp
0x18000d3bc  push    rsi
0x18000d3bd  push    rdi
0x18000d3be  push    r12
0x18000d3c0  push    r13
0x18000d3c2  push    r14
0x18000d3c4  sub     rsp, 90h
0x18000d3cb  mov     [rcx+1E0h], rdx
0x18000d3d2  mov     rbp, r9
0x18000d3d5  mov     r11, [r8+30h]
0x18000d3d9  mov     r13, r8
0x18000d3dc  mov     [rsp+0C8h+var_50], r11
0x18000d3e1  mov     rsi, rdx
0x18000d3e4  mov     rbx, rcx
0x18000d3e7  test    r11, r11
0x18000d3ea  jz      loc_18000DC85
0x18000d3f0  mov     eax, [r8+2Ch]
0x18000d3f4  lea     r14, cs:180000000h
0x18000d3fb  mov     [rcx+364h], eax
0x18000d401  cmp     dword ptr [rdx+0B8h], 0
0x18000d408  mov     [rsp+0C8h+var_40], r15
0x18000d410  jnz     short loc_18000D44A
0x18000d412  mov     rcx, [rsp+0C8h+arg_38]
0x18000d41a  mov     rax, [rcx]
0x18000d41d  mov     ecx, [rcx+10h]
0x18000d420  test    rax, rax
0x18000d423  jz      short loc_18000D436
0x18000d425  cmp     [rax+8], rbp
0x18000d429  jg      short loc_18000D436
0x18000d42b  mov     ecx, [rax+10h]
0x18000d42e  mov     rax, [rax]
0x18000d431  test    rax, rax
0x18000d434  jnz     short loc_18000D425
0x18000d436  mov     edi, [rsp+0C8h+arg_80]
0x18000d43d  movsxd  rax, ecx
0x18000d440  add     edi, ds:rva ?m_vrMIDIToVREL@CMIDIRecorder@@1PAJA[r14+rax*4]; long near * CMIDIRecorder::m_vrMIDIToVREL ...
0x18000d448  jmp     short loc_18000D451
0x18000d44a  mov     edi, [rsp+0C8h+arg_80]
0x18000d451  movzx   eax, word ptr [r8+3Ah]
0x18000d456  movzx   ecx, [rsp+0C8h+arg_78]
0x18000d45e  mov     r12, [rsp+0C8h+arg_68]
0x18000d466  mov     word ptr [rsp+0C8h+arg_0], ax
0x18000d46e  movzx   eax, byte ptr [r8+3Fh]
0x18000d473  mov     ecx, ds:rva ?m_vrMIDIToVREL@CMIDIRecorder@@1PAJA[r14+rcx*4]; long near * CMIDIRecorder::m_vrMIDIToVREL ...
0x18000d47b  mov     [rbx+23Ch], eax
0x18000d481  movzx   eax, byte ptr [r8+3Ch]
0x18000d486  mov     [rbx+238h], eax
0x18000d48c  movsx   eax, word ptr [r8+38h]
0x18000d491  add     ecx, eax
0x18000d493  mov     rax, [r8+30h]
0x18000d497  add     edi, ecx
0x18000d499  movsx   ecx, word ptr [rax+9Eh]
0x18000d4a0  mov     [rbx+1F8h], ecx
0x18000d4a6  movsx   eax, word ptr [r8+42h]
0x18000d4ab  and     eax, 2
0x18000d4ae  mov     [rbx+368h], eax
0x18000d4b4  cmp     dword ptr [r12], 1
0x18000d4b9  jnz     short loc_18000D4FB
0x18000d4bb  mov     r8d, [rdx+20h]
0x18000d4bf  test    r8d, r8d
0x18000d4c2  jz      short loc_18000D4FB
0x18000d4c4  mov     r9d, [r12+4]
0x18000d4c9  xor     ecx, ecx
0x18000d4cb  mov     r10, [rdx+8]
0x18000d4cf  nop
0x18000d4d0  cmp     [r10+rcx*4], r9d
0x18000d4d4  lea     rdx, ds:0[rcx*4]
0x18000d4dc  jz      short loc_18000D4E7
0x18000d4de  inc     ecx
0x18000d4e0  cmp     ecx, r8d
0x18000d4e3  jb      short loc_18000D4D0
0x18000d4e5  jmp     short loc_18000D4FB
0x18000d4e7  mov     rax, [rsi+10h]
0x18000d4eb  cmp     dword ptr [rdx+rax], 0
0x18000d4ef  jnz     short loc_18000D4FB
0x18000d4f1  mov     dword ptr [rbx+368h], 1
0x18000d4fb  cmp     dword ptr [rsi+0D4h], 0
0x18000d502  jz      short loc_18000D57E
0x18000d504  cmp     dword ptr [rsi+0B4h], 0
0x18000d50b  jnz     short loc_18000D57E
0x18000d50d  cmp     dword ptr [rbx+368h], 0
0x18000d514  jnz     short loc_18000D57E
0x18000d516  mov     rcx, [rsp+0C8h+arg_40]
0x18000d51e  mov     rax, [rcx]
0x18000d521  mov     ecx, [rcx+10h]
0x18000d524  test    rax, rax
0x18000d527  jz      short loc_18000D541
0x18000d529  nop     dword ptr [rax+00000000h]
0x18000d530  cmp     [rax+8], rbp
0x18000d534  jg      short loc_18000D541
0x18000d536  mov     ecx, [rax+10h]
0x18000d539  mov     rax, [rax]
0x18000d53c  test    rax, rax
0x18000d53f  jnz     short loc_18000D530
0x18000d541  xor     edx, edx
0x18000d543  mov     eax, 7Fh
0x18000d548  add     ecx, [rbx+1F8h]
0x18000d54e  cmovns  edx, ecx
0x18000d551  cmp     edx, eax
0x18000d553  cmovg   edx, eax
0x18000d556  sub     eax, edx
0x18000d558  cdqe
0x18000d55a  mov     ecx, rva ?m_svrPanToVREL@CVoice@@0PAJA[r14+rax*4]; long near * CVoice::m_svrPanToVREL ...
0x18000d562  add     ecx, edi
0x18000d564  movsxd  rax, edx
0x18000d567  mov     [rsp+0C8h+arg_10], ecx
0x18000d56e  mov     eax, rva ?m_svrPanToVREL@CVoice@@0PAJA[r14+rax*4]; long near * CVoice::m_svrPanToVREL ...
0x18000d576  add     eax, edi
0x18000d578  mov     [rsp+0C8h+var_58], eax
0x18000d57c  jmp     short loc_18000D589
0x18000d57e  mov     [rsp+0C8h+arg_10], edi
0x18000d585  mov     [rsp+0C8h+var_58], edi
0x18000d589  xor     r15d, r15d
0x18000d58c  mov     [rsp+0C8h+var_54], 0
0x18000d594  xor     r14d, r14d
0x18000d597  cmp     [r12], r14d
0x18000d59b  jbe     loc_18000D6A8
0x18000d5a1  mov     ebp, [rsp+0C8h+arg_10]
0x18000d5a8  nop     dword ptr [rax+rax+00000000h]
0x18000d5b0  mov     r9, [rbx+1E0h]
0x18000d5b7  mov     r8d, [r9+20h]
0x18000d5bb  test    r8d, r8d
0x18000d5be  jz      loc_18000D686
0x18000d5c4  mov     r10d, [r12+r14*4+4]
0x18000d5c9  xor     ecx, ecx
0x18000d5cb  mov     r11, [r9+8]
0x18000d5cf  nop
0x18000d5d0  lea     rdx, ds:0[rcx*4]
0x18000d5d8  cmp     [rdx+r11], r10d
0x18000d5dc  jz      short loc_18000D5EA
0x18000d5de  inc     ecx
0x18000d5e0  cmp     ecx, r8d
0x18000d5e3  jb      short loc_18000D5D0
0x18000d5e5  jmp     loc_18000D686
0x18000d5ea  mov     rax, [r9+10h]
0x18000d5ee  mov     ecx, [rdx+rax]
0x18000d5f1  test    r15d, r15d
0x18000d5f4  jnz     short loc_18000D601
0x18000d5f6  mov     rax, [r9+18h]
0x18000d5fa  mov     edx, [rdx+rax]
0x18000d5fd  mov     [rsp+0C8h+var_54], edx
0x18000d601  mov     dword ptr [rbx+r14*4+3ECh], 0FFFFDA80h
0x18000d60d  cmp     ecx, 11h
0x18000d610  ja      short loc_18000D645
0x18000d612  test    byte ptr [r13+42h], 2
0x18000d617  jz      short loc_18000D624
0x18000d619  mov     eax, [r13+44h]
0x18000d61d  bt      eax, ecx
0x18000d620  jnb     short loc_18000D66C
0x18000d622  jmp     short loc_18000D664
0x18000d624  test    ecx, ecx
0x18000d626  jz      short loc_18000D63B
0x18000d628  cmp     ecx, 1
0x18000d62b  jnz     short loc_18000D66C
0x18000d62d  mov     eax, [rsp+0C8h+var_58]
0x18000d631  mov     [rbx+r14*4+3ECh], eax
0x18000d639  jmp     short loc_18000D66C
0x18000d63b  mov     [rbx+r14*4+3ECh], ebp
0x18000d643  jmp     short loc_18000D66C
0x18000d645  cmp     ecx, 40h ; '@'
0x18000d648  jz      short loc_18000D664
0x18000d64a  cmp     ecx, 41h ; 'A'
0x18000d64d  jz      short loc_18000D664
0x18000d64f  cmp     ecx, 200h
0x18000d655  jz      short loc_18000D65E
0x18000d657  cmp     ecx, 0FFFFFFFFh
0x18000d65a  jnz     short loc_18000D664
0x18000d65c  jmp     short loc_18000D66C
0x18000d65e  mov     r15d, 1
0x18000d664  mov     [rbx+r14*4+3ECh], edi
0x18000d66c  mov     eax, cs:dword_18001EB10
0x18000d672  mov     [rbx+r14*4+46Ch], eax
0x18000d67a  mov     dword ptr [rbx+r14*4+36Ch], 0FFFFDA80h
0x18000d686  inc     r14d
0x18000d689  cmp     r14d, [r12]
0x18000d68d  jb      loc_18000D5B0
0x18000d693  mov     rbp, [rsp+0C8h+arg_18]
0x18000d69b  mov     rsi, [rsp+0C8h+arg_8]
0x18000d6a3  mov     r11, [rsp+0C8h+var_50]
0x18000d6a8  mov     r8, [rsp+0C8h+arg_20]
0x18000d6b0  lea     rdi, [rbx+8]
0x18000d6b4  mov     r9, [rsp+0C8h+arg_48]
0x18000d6bc  mov     ecx, 0AC44h
0x18000d6c1  mov     dword ptr [rdi+48h], 1
0x18000d6c8  mov     [rdi+30h], r8
0x18000d6cc  mov     [rdi+40h], r9
0x18000d6d0  movups  xmm0, xmmword ptr [r11+70h]
0x18000d6d5  movups  xmmword ptr [rdi], xmm0
0x18000d6d8  movups  xmm1, xmmword ptr [r11+80h]
0x18000d6e0  movups  xmmword ptr [rdi+10h], xmm1
0x18000d6e4  movsd   xmm0, qword ptr [r11+90h]
0x18000d6ed  movsd   qword ptr [rdi+20h], xmm0
0x18000d6f2  cmp     word ptr [rdi+12h], 0
0x18000d6f7  mov     [rdi+28h], rbp
0x18000d6fb  jnz     short loc_18000D716
0x18000d6fd  cmp     word ptr [rdi+10h], 0
0x18000d702  jnz     short loc_18000D716
0x18000d704  cmp     word ptr [rdi+16h], 0
0x18000d709  jnz     short loc_18000D716
0x18000d70b  cmp     word ptr [rdi+14h], 0
0x18000d710  jnz     short loc_18000D716
0x18000d712  mov     eax, ecx
0x18000d714  jmp     short loc_18000D720
0x18000d716  mov     eax, 200000h
0x18000d71b  cdq
0x18000d71c  idiv    dword ptr [rdi]
0x18000d71e  cdqe
0x18000d720  mov     [rdi+38h], rax
0x18000d724  mov     [rbx+1E8h], rax
0x18000d72b  mov     dword ptr [rbx+2D8h], 1
0x18000d735  mov     [rbx+2C0h], r8
0x18000d73c  mov     [rbx+2D0h], r9
0x18000d743  movups  xmm0, xmmword ptr [r11+0A0h]
0x18000d74b  movups  xmmword ptr [rbx+290h], xmm0
0x18000d752  movups  xmm1, xmmword ptr [r11+0B0h]
0x18000d75a  movups  xmmword ptr [rbx+2A0h], xmm1
0x18000d761  movsd   xmm0, qword ptr [r11+0C0h]
0x18000d76a  movsd   qword ptr [rbx+2B0h], xmm0
0x18000d772  cmp     word ptr [rbx+2A2h], 0
0x18000d77a  mov     [rbx+2B8h], rbp
0x18000d781  jnz     short loc_18000D7A1
0x18000d783  cmp     word ptr [rbx+2A0h], 0
0x18000d78b  jnz     short loc_18000D7A1
0x18000d78d  cmp     word ptr [rbx+2A6h], 0
0x18000d795  jnz     short loc_18000D7A1
0x18000d797  cmp     word ptr [rbx+2A4h], 0
0x18000d79f  jz      short loc_18000D7B0
0x18000d7a1  mov     eax, 200000h
0x18000d7a6  cdq
0x18000d7a7  idiv    dword ptr [rbx+290h]
0x18000d7ad  movsxd  rcx, eax
0x18000d7b0  mov     [rbx+2C8h], rcx
0x18000d7b7  cmp     rcx, [rbx+1E8h]
0x18000d7be  jge     short loc_18000D7C7
0x18000d7c0  mov     [rbx+1E8h], rcx
0x18000d7c7  movzx   eax, [rsp+0C8h+arg_78]
0x18000d7cf  lea     r15, [rbx+58h]
0x18000d7d3  movzx   r14d, [rsp+0C8h+arg_70]
0x18000d7dc  mov     rcx, r15; this
0x18000d7df  movzx   r9d, r14w; unsigned __int16
0x18000d7e3  mov     [rsp+0C8h+var_A0], 0; __int64
0x18000d7ec  mov     r8, rbp; __int64
0x18000d7ef  mov     word ptr [rsp+0C8h+var_A8], ax; unsigned __int16
0x18000d7f4  mov     rdx, r11; struct CSourceEG *
0x18000d7f7  call    ?StartVoice@CVoiceEG@@QEAA_JPEAVCSourceEG@@_JGG1@Z; CVoiceEG::StartVoice(CSourceEG *,__int64,ushort,ushort,__int64)
0x18000d7fc  cmp     rax, [rbx+1E8h]
0x18000d803  jge     short loc_18000D80C
0x18000d805  mov     [rbx+1E8h], rax
0x18000d80c  mov     eax, 10624DD3h
0x18000d811  lea     rcx, [rbx+0A8h]; this
0x18000d818  mul     dword ptr [rsi+0D0h]
0x18000d81e  movzx   r9d, r14w; unsigned __int16
0x18000d822  mov     r8, rbp; __int64
0x18000d825  shr     edx, 6
0x18000d828  mov     eax, edx
0x18000d82a  mov     rdx, [rsp+0C8h+var_50]
0x18000d82f  mov     [rsp+0C8h+var_A0], rax; __int64
0x18000d834  add     rdx, 38h ; '8'; struct CSourceEG *
0x18000d838  movzx   eax, [rsp+0C8h+arg_78]
0x18000d840  mov     word ptr [rsp+0C8h+var_A8], ax; unsigned __int16
0x18000d845  call    ?StartVoice@CVoiceEG@@QEAA_JPEAVCSourceEG@@_JGG1@Z; CVoiceEG::StartVoice(CSourceEG *,__int64,ushort,ushort,__int64)
0x18000d84a  mov     rcx, [rbx+1E8h]
0x18000d851  cmp     rax, rcx
0x18000d854  jge     short loc_18000D85F
0x18000d856  mov     [rbx+1E8h], rax
0x18000d85d  jmp     short loc_18000D862
0x18000d85f  mov     rax, rcx
0x18000d862  mov     rcx, [rsi+0C8h]
0x18000d869  cmp     rax, rcx
0x18000d86c  jle     short loc_18000D875
0x18000d86e  mov     [rbx+1E8h], rcx
0x18000d875  mov     rax, [rsp+0C8h+var_50]
0x18000d87a  lea     rsi, [rbx+260h]
0x18000d881  mov     r8d, r14d
0x18000d884  movups  xmm0, xmmword ptr [rax+0C8h]
0x18000d88b  movzx   eax, [rsp+0C8h+arg_78]
0x18000d893  mov     [rsi+18h], r15
0x18000d897  mov     r15, [rsp+0C8h+var_40]
0x18000d89f  movups  xmmword ptr [rsi], xmm0
0x18000d8a2  movsx   ecx, word ptr [rsi+0Ch]
0x18000d8a6  imul    ecx, eax
0x18000d8a9  mov     eax, 81020409h
0x18000d8ae  mov     [rsi+10h], rdi
0x18000d8b2  imul    ecx
0x18000d8b4  add     edx, ecx
0x18000d8b6  movsx   ecx, word ptr [rsi+0Eh]
0x18000d8ba  sar     edx, 6
0x18000d8bd  mov     eax, edx
0x18000d8bf  imul    ecx, r14d
0x18000d8c3  shr     eax, 1Fh
0x18000d8c6  add     edx, eax
0x18000d8c8  mov     eax, 81020409h
0x18000d8cd  mov     [rsi+28h], edx
0x18000d8d0  imul    ecx
0x18000d8d2  add     edx, ecx
0x18000d8d4  sar     edx, 6
0x18000d8d7  mov     eax, edx
  ... truncated ...
```
