# CVoice::StartWave(CSynth *,CWaveArt *,ulong,__int64,CPitchBendIn *,CExpressionIn *,CVolumeIn *,CPanIn *,CReverbIn *,CChorusIn *,CCutOffFreqIn *,CBusIds *,long,long,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x18000e040`
- end: `0x18000e39e`
- name: `?StartWave@CVoice@@QEAAHPEAVCSynth@@PEAVCWaveArt@@K_JPEAVCPitchBendIn@@PEAVCExpressionIn@@PEAVCVolumeIn@@PEAVCPanIn@@PEAVCReverbIn@@PEAVCChorusIn@@PEAVCCutOffFreqIn@@PEAVCBusIds@@JJ_K_K_K@Z`
- size: `862`
- prototype: `int(CVoice *__hidden this, struct CSynth *, struct CWaveArt *, unsigned int, __int64, struct CPitchBendIn *, struct CExpressionIn *, struct CVolumeIn *, struct CPanIn *, struct CReverbIn *, struct CChorusIn *, struct CCutOffFreqIn *, struct CBusIds *, int, int, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180004c90`

## callees

- `0x18000dca0`
- `0x18000ddf0`
- `0x18000e040`

## pseudocode

```c
__int64 __fastcall CVoice::StartWave(
        CVoice *this,
        struct CSynth *a2,
        struct CWaveArt *a3,
        int a4,
        __int64 a5,
        struct CPitchBendIn *a6,
        struct CExpressionIn *a7,
        struct CVolumeIn *a8,
        struct CPanIn *a9,
        struct CReverbIn *a10,
        struct CChorusIn *a11,
        struct CCutOffFreqIn *a12,
        struct CBusIds *a13,
        int a14,
        int a15,
        unsigned __int64 a16,
        unsigned __int64 a17,
        unsigned __int64 a18)
{
  int v18; // r15d
  unsigned int v20; // r12d
  BOOL v23; // eax
  unsigned int v24; // r8d
  __int64 v25; // rcx
  __int64 v26; // rsi
  int v27; // r15d
  __int64 v28; // rdi
  unsigned int v29; // edx
  __int64 v30; // rax
  unsigned int v31; // edx
  unsigned int v32; // kr00_4
  __int64 started; // rax
  __int64 v34; // rcx
  __int128 v36; // [rsp+40h] [rbp-88h] BYREF
  __int64 v37; // [rsp+50h] [rbp-78h]
  int v38; // [rsp+58h] [rbp-70h]
  int v39; // [rsp+5Ch] [rbp-6Ch]
  __int128 v40; // [rsp+60h] [rbp-68h]
  __int16 v41; // [rsp+72h] [rbp-56h]

  v18 = a4;
  *((_QWORD *)this + 60) = a2;
  v20 = *((_DWORD *)a3 + 4);
  v23 = v20 <= 0x11 && (*((_BYTE *)a3 + 28) & 2) != 0;
  *((_DWORD *)this + 218) = v23;
  if ( *(_DWORD *)a13 == 1 )
  {
    v24 = *((_DWORD *)a2 + 8);
    if ( v24 )
    {
      v25 = 0;
      while ( *(_DWORD *)(*((_QWORD *)a2 + 1) + 4 * v25) != *((_DWORD *)a13 + 1) )
      {
        v25 = (unsigned int)(v25 + 1);
        if ( (unsigned int)v25 >= v24 )
          goto LABEL_13;
      }
      if ( !*(_DWORD *)(4 * v25 + *((_QWORD *)a2 + 2)) )
        *((_DWORD *)this + 218) = 1;
    }
  }
LABEL_13:
  v26 = 0;
  if ( !*(_DWORD *)a13 )
    goto LABEL_31;
  v27 = dword_18001EB10;
  do
  {
    *((_DWORD *)this + v26 + 251) = -9600;
    v28 = *((_QWORD *)this + 60);
    v29 = *(_DWORD *)(v28 + 32);
    if ( !v29 )
      goto LABEL_29;
    v30 = 0;
    while ( *(_DWORD *)(*(_QWORD *)(v28 + 8) + 4 * v30) != *((_DWORD *)a13 + v26 + 1) )
    {
      v30 = (unsigned int)(v30 + 1);
      if ( (unsigned int)v30 >= v29 )
        goto LABEL_29;
    }
    v31 = *(_DWORD *)(4 * v30 + *(_QWORD *)(v28 + 16));
    if ( v31 > 0x11 )
    {
      if ( v31 != -1 )
LABEL_27:
        *((_DWORD *)this + v26 + 251) = a14;
    }
    else if ( (*((_BYTE *)a3 + 28) & 2) != 0 )
    {
      if ( v20 == v31 )
        goto LABEL_27;
    }
    else if ( v31 <= 1 )
    {
      goto LABEL_27;
    }
    *((_DWORD *)this + v26 + 219) = -9600;
    *((_DWORD *)this + v26 + 283) = v27;
LABEL_29:
    v26 = (unsigned int)(v26 + 1);
  }
  while ( (unsigned int)v26 < *(_DWORD *)a13 );
  v18 = a4;
LABEL_31:
  v39 = 1000;
  v37 = 0;
  v38 = 0;
  v32 = *((_DWORD *)a2 + 52);
  v36 = 0;
  v40 = 0;
  v41 = 0;
  started = CVoiceEG::StartVoice((CVoice *)((char *)this + 168), (struct CSourceEG *)&v36, a5, 0, 0, v32 / 0xFA);
  *((_QWORD *)this + 61) = started;
  v34 = *((_QWORD *)a2 + 25);
  if ( started > v34 )
    *((_QWORD *)this + 61) = v34;
  *((_QWORD *)this + 53) = a6;
  *((_QWORD *)this + 54) = a7;
  *((_QWORD *)this + 56) = a9;
  *((_QWORD *)this + 57) = a10;
  *((_QWORD *)this + 58) = a11;
  *((_QWORD *)this + 59) = a12;
  *((_QWORD *)this + 55) = a8;
  *((_OWORD *)this + 46) = *(_OWORD *)a13;
  *((_OWORD *)this + 47) = *((_OWORD *)a13 + 1);
  *((_OWORD *)this + 48) = *((_OWORD *)a13 + 2);
  *((_OWORD *)this + 49) = *((_OWORD *)a13 + 3);
  *((_OWORD *)this + 50) = *((_OWORD *)a13 + 4);
  *((_OWORD *)this + 51) = *((_OWORD *)a13 + 5);
  *((_OWORD *)this + 52) = *((_OWORD *)a13 + 6);
  *((_OWORD *)this + 53) = *((_OWORD *)a13 + 7);
  *((_DWORD *)this + 216) = *((_DWORD *)a13 + 32);
  *((_QWORD *)this + 62) = a5 - 1;
  *((_QWORD *)this + 66) = 0x7FFFFFFFFFFFFFFFLL;
  *(_QWORD *)((char *)this + 548) = 1;
  *((_QWORD *)this + 65) = a5;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_DWORD *)this + 126) = 0;
  *(_QWORD *)((char *)this + 556) = 0;
  *((_DWORD *)this + 148) = v18;
  *((_DWORD *)this + 20) = 0;
  *((_DWORD *)this + 182) = 0;
  *((_DWORD *)this + 40) = 0;
  *((_WORD *)this + 305) = 0x7FFF;
  CDigitalAudio::StartWave((CVoice *)((char *)this + 248), a2, a3, a15, a16, a17, a18);
  return 1;
}

```

## disassembly

```asm
0x18000e040  mov     [rsp+arg_18], r9d
0x18000e045  push    rbx
0x18000e046  push    rbp
0x18000e047  push    rsi
0x18000e048  push    rdi
0x18000e049  push    r12
0x18000e04b  push    r13
0x18000e04d  push    r14
0x18000e04f  push    r15
0x18000e051  sub     rsp, 88h
0x18000e058  mov     rbp, [rsp+0C8h+arg_60]
0x18000e060  mov     r15d, r9d
0x18000e063  mov     [rcx+1E0h], rdx
0x18000e06a  mov     r14, r8
0x18000e06d  mov     r12d, [r8+10h]
0x18000e071  mov     r13, rdx
0x18000e074  mov     rbx, rcx
0x18000e077  cmp     r12d, 11h
0x18000e07b  ja      short loc_18000E08B
0x18000e07d  test    byte ptr [r8+1Ch], 2
0x18000e082  jz      short loc_18000E08B
0x18000e084  mov     eax, 1
0x18000e089  jmp     short loc_18000E08D
0x18000e08b  xor     eax, eax
0x18000e08d  mov     [rcx+368h], eax
0x18000e093  cmp     dword ptr [rbp+0], 1
0x18000e097  jnz     short loc_18000E0DB
0x18000e099  mov     r8d, [rdx+20h]
0x18000e09d  test    r8d, r8d
0x18000e0a0  jz      short loc_18000E0DB
0x18000e0a2  mov     r9d, [rbp+4]
0x18000e0a6  xor     ecx, ecx
0x18000e0a8  mov     r10, [rdx+8]
0x18000e0ac  nop     dword ptr [rax+00h]
0x18000e0b0  cmp     [r10+rcx*4], r9d
0x18000e0b4  lea     rdx, ds:0[rcx*4]
0x18000e0bc  jz      short loc_18000E0C7
0x18000e0be  inc     ecx
0x18000e0c0  cmp     ecx, r8d
0x18000e0c3  jb      short loc_18000E0B0
0x18000e0c5  jmp     short loc_18000E0DB
0x18000e0c7  mov     rax, [r13+10h]
0x18000e0cb  cmp     dword ptr [rdx+rax], 0
0x18000e0cf  jnz     short loc_18000E0DB
0x18000e0d1  mov     dword ptr [rbx+368h], 1
0x18000e0db  xor     esi, esi
0x18000e0dd  cmp     [rbp+0], esi
0x18000e0e0  jbe     loc_18000E194
0x18000e0e6  mov     r10d, [rsp+0C8h+arg_68]
0x18000e0ee  mov     r15d, cs:dword_18001EB10
0x18000e0f5  mov     dword ptr [rbx+rsi*4+3ECh], 0FFFFDA80h
0x18000e100  mov     rdi, [rbx+1E0h]
0x18000e107  mov     edx, [rdi+20h]
0x18000e10a  test    edx, edx
0x18000e10c  jz      short loc_18000E181
0x18000e10e  mov     r8d, [rbp+rsi*4+4]
0x18000e113  xor     eax, eax
0x18000e115  mov     r9, [rdi+8]
0x18000e119  nop     dword ptr [rax+00000000h]
0x18000e120  cmp     [r9+rax*4], r8d
0x18000e124  lea     rcx, ds:0[rax*4]
0x18000e12c  jz      short loc_18000E136
0x18000e12e  inc     eax
0x18000e130  cmp     eax, edx
0x18000e132  jb      short loc_18000E120
0x18000e134  jmp     short loc_18000E181
0x18000e136  mov     rax, [rdi+10h]
0x18000e13a  mov     edx, [rcx+rax]
0x18000e13d  cmp     edx, 11h
0x18000e140  ja      short loc_18000E157
0x18000e142  test    byte ptr [r14+1Ch], 2
0x18000e147  jz      short loc_18000E150
0x18000e149  cmp     r12d, edx
0x18000e14c  jnz     short loc_18000E16E
0x18000e14e  jmp     short loc_18000E166
0x18000e150  cmp     edx, 1
0x18000e153  ja      short loc_18000E16E
0x18000e155  jmp     short loc_18000E166
0x18000e157  cmp     edx, 40h ; '@'
0x18000e15a  jz      short loc_18000E166
0x18000e15c  cmp     edx, 41h ; 'A'
0x18000e15f  jz      short loc_18000E166
0x18000e161  cmp     edx, 0FFFFFFFFh
0x18000e164  jz      short loc_18000E16E
0x18000e166  mov     [rbx+rsi*4+3ECh], r10d
0x18000e16e  mov     dword ptr [rbx+rsi*4+36Ch], 0FFFFDA80h
0x18000e179  mov     [rbx+rsi*4+46Ch], r15d
0x18000e181  inc     esi
0x18000e183  cmp     esi, [rbp+0]
0x18000e186  jb      loc_18000E0F5
0x18000e18c  mov     r15d, [rsp+0C8h+arg_18]
0x18000e194  mov     rdi, [rsp+0C8h+arg_20]
0x18000e19c  lea     rcx, [rbx+0A8h]; this
0x18000e1a3  xor     esi, esi
0x18000e1a5  mov     [rsp+0C8h+var_6C], 3E8h
0x18000e1ad  xorps   xmm0, xmm0
0x18000e1b0  mov     [rsp+0C8h+var_78], rsi
0x18000e1b5  mov     eax, 10624DD3h
0x18000e1ba  mov     [rsp+0C8h+var_70], esi
0x18000e1be  mul     dword ptr [r13+0D0h]
0x18000e1c5  movdqu  [rsp+0C8h+var_88], xmm0
0x18000e1cb  movdqu  [rsp+0C8h+var_68], xmm0
0x18000e1d1  xor     r9d, r9d; unsigned __int16
0x18000e1d4  mov     [rsp+0C8h+var_56], si
0x18000e1d9  shr     edx, 4
0x18000e1dc  mov     r8, rdi; __int64
0x18000e1df  mov     eax, edx
0x18000e1e1  lea     rdx, [rsp+0C8h+var_88]; struct CSourceEG *
0x18000e1e6  mov     [rsp+0C8h+var_A0], rax; __int64
0x18000e1eb  mov     [rsp+0C8h+var_A8], si; unsigned __int16
0x18000e1f0  call    ?StartVoice@CVoiceEG@@QEAA_JPEAVCSourceEG@@_JGG1@Z; CVoiceEG::StartVoice(CSourceEG *,__int64,ushort,ushort,__int64)
0x18000e1f5  mov     [rbx+1E8h], rax
0x18000e1fc  mov     rcx, [r13+0C8h]
0x18000e203  cmp     rax, rcx
0x18000e206  jle     short loc_18000E20F
0x18000e208  mov     [rbx+1E8h], rcx
0x18000e20f  mov     rax, [rsp+0C8h+arg_28]
0x18000e217  lea     rcx, [rbx+0F8h]; this
0x18000e21e  mov     rdx, [rsp+0C8h+arg_88]
0x18000e226  mov     r8, r14; struct CWaveArt *
0x18000e229  mov     r9d, [rsp+0C8h+arg_70]; int
0x18000e231  mov     [rbx+1A8h], rax
0x18000e238  mov     rax, [rsp+0C8h+arg_30]
0x18000e240  mov     [rbx+1B0h], rax
0x18000e247  mov     rax, [rsp+0C8h+arg_40]
0x18000e24f  mov     [rbx+1C0h], rax
0x18000e256  mov     rax, [rsp+0C8h+arg_48]
0x18000e25e  mov     [rbx+1C8h], rax
0x18000e265  mov     rax, [rsp+0C8h+arg_50]
0x18000e26d  mov     [rbx+1D0h], rax
0x18000e274  mov     rax, [rsp+0C8h+arg_58]
0x18000e27c  mov     [rbx+1D8h], rax
0x18000e283  mov     rax, [rsp+0C8h+arg_38]
0x18000e28b  mov     [rbx+1B8h], rax
0x18000e292  movups  xmm0, xmmword ptr [rbp+0]
0x18000e296  mov     [rsp+0C8h+var_98], rdx; unsigned __int64
0x18000e29b  mov     rdx, [rsp+0C8h+arg_80]
0x18000e2a3  movups  xmmword ptr [rbx+2E0h], xmm0
0x18000e2aa  mov     [rsp+0C8h+var_A0], rdx; unsigned __int64
0x18000e2af  movups  xmm1, xmmword ptr [rbp+10h]
0x18000e2b3  mov     rdx, [rsp+0C8h+arg_78]
0x18000e2bb  mov     qword ptr [rsp+0C8h+var_A8], rdx; unsigned __int64
0x18000e2c0  mov     rdx, r13; struct CSynth *
0x18000e2c3  movups  xmmword ptr [rbx+2F0h], xmm1
0x18000e2ca  movups  xmm0, xmmword ptr [rbp+20h]
0x18000e2ce  movups  xmmword ptr [rbx+300h], xmm0
0x18000e2d5  movups  xmm1, xmmword ptr [rbp+30h]
0x18000e2d9  movups  xmmword ptr [rbx+310h], xmm1
0x18000e2e0  movups  xmm0, xmmword ptr [rbp+40h]
0x18000e2e4  movups  xmmword ptr [rbx+320h], xmm0
0x18000e2eb  movups  xmm1, xmmword ptr [rbp+50h]
0x18000e2ef  movups  xmmword ptr [rbx+330h], xmm1
0x18000e2f6  movups  xmm0, xmmword ptr [rbp+60h]
0x18000e2fa  movups  xmmword ptr [rbx+340h], xmm0
0x18000e301  movups  xmm1, xmmword ptr [rbp+70h]
0x18000e305  movups  xmmword ptr [rbx+350h], xmm1
0x18000e30c  mov     eax, [rbp+80h]
0x18000e312  mov     [rbx+360h], eax
0x18000e318  lea     rax, [rdi-1]
0x18000e31c  mov     [rbx+1F0h], rax
0x18000e323  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000e32d  mov     [rbx+210h], rax
0x18000e334  mov     qword ptr [rbx+224h], 1
0x18000e33f  mov     [rbx+208h], rdi
0x18000e346  mov     [rbx+218h], rsi
0x18000e34d  mov     [rbx+238h], rsi
0x18000e354  mov     [rbx+1F8h], esi
0x18000e35a  mov     [rbx+22Ch], rsi
0x18000e361  mov     [rbx+250h], r15d
0x18000e368  mov     [rbx+50h], esi
0x18000e36b  mov     [rbx+2D8h], esi
0x18000e371  mov     [rbx+0A0h], esi
0x18000e377  mov     word ptr [rbx+262h], 7FFFh
0x18000e380  call    ?StartWave@CDigitalAudio@@QEAA_JPEAVCSynth@@PEAVCWaveArt@@J_K22@Z; CDigitalAudio::StartWave(CSynth *,CWaveArt *,long,unsigned __int64,unsigned __int64,unsigned __int64)
0x18000e385  mov     eax, 1
0x18000e38a  add     rsp, 88h
0x18000e391  pop     r15
0x18000e393  pop     r14
0x18000e395  pop     r13
0x18000e397  pop     r12
0x18000e399  pop     rdi
0x18000e39a  pop     rsi
0x18000e39b  pop     rbp
0x18000e39c  pop     rbx
0x18000e39d  retn
```
