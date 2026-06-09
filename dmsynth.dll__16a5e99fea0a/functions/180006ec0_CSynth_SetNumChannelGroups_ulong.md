# CSynth::SetNumChannelGroups(ulong)

- ea: `0x180006ec0`
- end: `0x180007330`
- name: `?SetNumChannelGroups@CSynth@@QEAAJK@Z`
- size: `1136`
- prototype: `__int64 __fastcall(CSynth *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180012460`
- `0x180013360`

## callees

- `0x180001514`
- `0x180001520`
- `0x180001d5e`
- `0x180001d76`
- `0x180001d9a`
- `0x180002fb0`
- `0x180005dd0`
- `0x180006030`
- `0x180006ec0`
- `0x18000b940`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000706e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000706e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072e1`

## pseudocode

```c
__int64 __fastcall CSynth::SetNumChannelGroups(CSynth *this, unsigned int a2)
{
  unsigned __int64 v2; // r13
  CSynth *v3; // rsi
  unsigned int v4; // r14d
  unsigned int *v5; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rcx
  double v8; // xmm7_8
  double v9; // xmm8_8
  double v10; // xmm9_8
  double v11; // xmm11_8
  double v12; // xmm12_8
  double v13; // xmm13_8
  double v14; // xmm6_8
  double v15; // xmm10_8
  CControlLogic *v16; // rax
  CControlLogic *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int j; // edi
  int k; // edi
  unsigned __int16 m; // di
  _QWORD *v23; // r15
  __int64 v24; // rcx
  void *v25; // rcx
  unsigned int v27; // edx
  unsigned int i; // ebx
  CControlLogic *v29; // rcx
  _QWORD *v30; // [rsp+20h] [rbp-D8h]
  unsigned int *v31; // [rsp+28h] [rbp-D0h]
  _QWORD *v32; // [rsp+30h] [rbp-C8h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+38h] [rbp-C0h]
  unsigned int *v36; // [rsp+110h] [rbp+18h]
  unsigned int v37; // [rsp+110h] [rbp+18h]
  unsigned int *v38; // [rsp+118h] [rbp+20h]

  v2 = a2;
  v3 = this;
  v4 = 0;
  if ( a2 - 1 > 0x3E7 )
    return 2147942487LL;
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1048);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  v5 = (unsigned int *)((char *)v3 + 1040);
  v38 = (unsigned int *)((char *)v3 + 1040);
  v36 = (unsigned int *)((char *)v3 + 1040);
  if ( *((_DWORD *)v3 + 260) == (_DWORD)v2 )
  {
LABEL_41:
    LeaveCriticalSection(lpCriticalSection);
    return v4;
  }
  try
  {
    v23 = operator new[](saturated_mul(v2, 8u));
    v30 = v23;
  }
  catch ( ... )
  {
    v30 = 0;
    v3 = this;
    LODWORD(v2) = a2;
    v23 = 0;
    v5 = v36;
    v38 = v36;
  }
  v32 = v23;
  if ( !v23 )
  {
    v4 = -2147024882;
    goto LABEL_41;
  }
  v31 = v5;
  if ( (_DWORD)v2 )
    memset_0(v23, 0, 8LL * (unsigned int)v2);
  if ( *v5 >= (unsigned int)v2 )
  {
    CSynth::AllNotesOff(v3);
    for ( i = 0; i < (unsigned int)v2; ++i )
    {
      v27 = i;
      v23[i] = *(_QWORD *)(*((_QWORD *)v3 + 129) + 8LL * i);
    }
    if ( i < *v5 )
    {
      do
      {
        v29 = *(CControlLogic **)(*((_QWORD *)v3 + 129) + 8LL * i);
        if ( v29 )
          CControlLogic::`scalar deleting destructor'(v29, v27);
        ++i;
      }
      while ( i < *((_DWORD *)v3 + 260) );
    }
  }
  else
  {
    v6 = 0;
    v37 = 0;
    if ( *v5 )
    {
      do
      {
        v7 = *(_QWORD *)(*((_QWORD *)v3 + 129) + 8LL * v6);
        v23[v6++] = v7;
      }
      while ( v6 < *v5 );
      v37 = v6;
    }
    v8 = DOUBLE_6_283185307;
    v9 = DOUBLE_0_00390625;
    v10 = DOUBLE_100_0;
    v11 = DOUBLE_200_0;
    v12 = DOUBLE_10000_0;
    v13 = DOUBLE_96_0;
    v14 = DOUBLE_1000_0;
    v15 = DOUBLE_127_0;
    while ( v6 < (unsigned int)v2 )
    {
      try
      {
        v16 = (CControlLogic *)malloc(0x1BC8u);
        if ( v16 )
          v17 = CControlLogic::CControlLogic(v16);
        else
          v17 = 0;
        v18 = v6;
        v23[v6] = v17;
      }
      catch ( ... )
      {
        v30[v37] = 0;
        v6 = v37;
        v18 = v37;
        v3 = this;
        LODWORD(v2) = a2;
        v23 = v30;
        v8 = DOUBLE_6_283185307;
        v9 = DOUBLE_0_00390625;
        v10 = DOUBLE_100_0;
        v11 = DOUBLE_200_0;
        v12 = DOUBLE_10000_0;
        v13 = DOUBLE_96_0;
        v14 = DOUBLE_1000_0;
        v15 = DOUBLE_127_0;
        v38 = v31;
      }
      v19 = v23[v18];
      if ( !v19 )
      {
        LODWORD(v2) = v6;
        break;
      }
      *(_QWORD *)v19 = v3;
      *(_QWORD *)(v19 + 8) = (char *)v3 + 216;
      *(_DWORD *)(v19 + 3436) = 0;
      if ( !dword_1800200F8 )
      {
        dword_1800200F8 = 1;
        for ( j = 0; j < 256; ++j )
          *((_WORD *)&CVoiceLFO::m_snSineTable + (unsigned int)j) = (int)(o_sin_0((double)j * v8 * v9) * v10);
        LOWORD(CVoiceEG::m_snAttackTable) = 0;
        for ( k = 1; k <= 200; ++k )
          *((_WORD *)&CVoiceEG::m_snAttackTable + (unsigned int)k) = (int)(o_log10_0((double)k / v11 * ((double)k / v11))
                                                                         * v12
                                                                         / v13
                                                                         + v14);
        CDigitalAudio::Init();
        for ( m = 1; m < 0x80u; ++m )
          *((_DWORD *)&CVoice::m_svrPanToVREL + m) = (int)(o_log10_0((double)m / v15) * v14);
        LODWORD(CVoice::m_svrPanToVREL) = -2500;
        v23 = v30;
      }
      v24 = v32[v6];
      *(_DWORD *)(v24 + 3436) = *((_DWORD *)v3 + 44);
      v37 = ++v6;
    }
    v5 = v38;
  }
  v25 = (void *)*((_QWORD *)v3 + 129);
  if ( v25 )
    operator delete(v25);
  *((_QWORD *)v3 + 129) = v23;
  *v5 = v2;
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x180006ec0  mov     rax, rsp
0x180006ec3  mov     [rax+10h], edx
0x180006ec6  mov     [rax+8], rcx
0x180006eca  push    rbx
0x180006ecb  push    rsi
0x180006ecc  push    rdi
0x180006ecd  push    r12
0x180006ecf  push    r13
0x180006ed1  push    r14
0x180006ed3  push    r15
0x180006ed5  sub     rsp, 0C0h
0x180006edc  movaps  xmmword ptr [rax-48h], xmm6
0x180006ee0  movaps  xmmword ptr [rax-58h], xmm7
0x180006ee4  movaps  xmmword ptr [rax-68h], xmm8
0x180006ee9  movaps  xmmword ptr [rax-78h], xmm9
0x180006eee  movaps  [rsp+0F8h+var_88], xmm10
0x180006ef4  movaps  [rsp+0F8h+var_98], xmm11
0x180006efa  movaps  [rsp+0F8h+var_A8], xmm12
0x180006f00  movaps  [rsp+0F8h+var_B8], xmm13
0x180006f06  mov     r13d, edx
0x180006f09  mov     rsi, rcx
0x180006f0c  xor     r14d, r14d
0x180006f0f  mov     [rsp+0F8h+var_D8], r14
0x180006f14  lea     eax, [r13-1]
0x180006f18  cmp     eax, 3E7h
0x180006f1d  ja      loc_1800072EC
0x180006f23  add     rcx, 418h; lpCriticalSection
0x180006f2a  mov     [rsp+0F8h+lpCriticalSection], rcx
0x180006f2f  call    cs:__imp_EnterCriticalSection
0x180006f35  lea     rdi, [rsi+410h]
0x180006f3c  mov     [rsp+0F8h+arg_18], rdi
0x180006f44  mov     [rsp+0F8h+arg_10], rdi
0x180006f4c  cmp     [rdi], r13d
0x180006f4f  jz      loc_1800072DC
0x180006f55  mov     eax, 8
0x180006f5a  mul     r13
0x180006f5d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006f64  cmovb   rax, rcx
0x180006f68  mov     rcx, rax; unsigned __int64
0x180006f6b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006f70  mov     r15, rax
0x180006f73  mov     [rsp+0F8h+var_D8], rax
0x180006f78  jmp     short loc_180006FA2
0x180006f7a  xor     r14d, r14d
0x180006f7d  mov     rsi, [rsp+0F8h+arg_0]
0x180006f85  mov     r13d, [rsp+0F8h+arg_8]
0x180006f8d  mov     r15, [rsp+0F8h+var_D8]
0x180006f92  mov     rdi, [rsp+0F8h+arg_10]
0x180006f9a  mov     [rsp+0F8h+arg_18], rdi
0x180006fa2  mov     [rsp+0F8h+var_C8], r15
0x180006fa7  test    r15, r15
0x180006faa  jz      loc_1800072D6
0x180006fb0  mov     [rsp+0F8h+var_D0], rdi
0x180006fb5  test    r13d, r13d
0x180006fb8  jz      short loc_180006FCB
0x180006fba  mov     r8d, r13d
0x180006fbd  shl     r8, 3; Size
0x180006fc1  xor     edx, edx; Val
0x180006fc3  mov     rcx, r15; void *
0x180006fc6  call    memset_0
0x180006fcb  mov     eax, [rdi]
0x180006fcd  cmp     eax, r13d
0x180006fd0  jnb     loc_18000727B
0x180006fd6  mov     ebx, r14d
0x180006fd9  mov     dword ptr [rsp+0F8h+arg_10], ebx
0x180006fe0  test    eax, eax
0x180006fe2  jz      short loc_18000700E
0x180006fe4  nop     dword ptr [rax+00h]
0x180006fe8  nop     dword ptr [rax+rax+00000000h]
0x180006ff0  mov     edx, ebx
0x180006ff2  mov     rax, [rsi+408h]
0x180006ff9  mov     rcx, [rax+rdx*8]
0x180006ffd  mov     [r15+rdx*8], rcx
0x180007001  inc     ebx
0x180007003  cmp     ebx, [rdi]
0x180007005  jb      short loc_180006FF0
0x180007007  mov     dword ptr [rsp+0F8h+arg_10], ebx
0x18000700e  lea     r12, cs:180000000h
0x180007015  movsd   xmm7, cs:__real@401921fb54411744
0x18000701d  movsd   xmm8, cs:__real@3f70000000000000
0x180007026  movsd   xmm9, cs:__real@4059000000000000
0x18000702f  movsd   xmm11, cs:__real@4069000000000000
0x180007038  movsd   xmm12, cs:__real@40c3880000000000
0x180007041  movsd   xmm13, cs:__real@4058000000000000
0x18000704a  movsd   xmm6, cs:__real@408f400000000000
0x180007052  movsd   xmm10, cs:__real@405fc00000000000
0x18000705b  mov     edi, 1
0x180007060  cmp     ebx, r13d
0x180007063  jnb     loc_180007248
0x180007069  mov     ecx, 1BC8h; Size
0x18000706e  call    cs:__imp_malloc
0x180007074  test    rax, rax
0x180007077  jz      short loc_180007083
0x180007079  mov     rcx, rax; this
0x18000707c  call    ??0CControlLogic@@QEAA@XZ; CControlLogic::CControlLogic(void)
0x180007081  jmp     short loc_180007086
0x180007083  mov     rax, r14
0x180007086  mov     ecx, ebx
0x180007088  mov     [r15+rcx*8], rax
0x18000708c  jmp     loc_180007111
0x180007091  mov     ebx, dword ptr [rsp+0F8h+arg_10]
0x180007098  mov     ecx, ebx
0x18000709a  xor     r14d, r14d
0x18000709d  mov     edi, 1
0x1800070a2  lea     r12, cs:180000000h
0x1800070a9  mov     rsi, [rsp+0F8h+arg_0]
0x1800070b1  mov     r13d, [rsp+0F8h+arg_8]
0x1800070b9  mov     r15, [rsp+0F8h+var_D8]
0x1800070be  movsd   xmm7, cs:__real@401921fb54411744
0x1800070c6  movsd   xmm8, cs:__real@3f70000000000000
0x1800070cf  movsd   xmm9, cs:__real@4059000000000000
0x1800070d8  movsd   xmm11, cs:__real@4069000000000000
0x1800070e1  movsd   xmm12, cs:__real@40c3880000000000
0x1800070ea  movsd   xmm13, cs:__real@4058000000000000
0x1800070f3  movsd   xmm6, cs:__real@408f400000000000
0x1800070fb  movsd   xmm10, cs:__real@405fc00000000000
0x180007104  mov     rax, [rsp+0F8h+var_D0]
0x180007109  mov     [rsp+0F8h+arg_18], rax
0x180007111  mov     rcx, [r15+rcx*8]
0x180007115  test    rcx, rcx
0x180007118  jz      loc_180007245
0x18000711e  mov     [rcx], rsi
0x180007121  lea     rax, [rsi+0D8h]
0x180007128  mov     [rcx+8], rax
0x18000712c  mov     [rcx+0D6Ch], r14d
0x180007133  cmp     cs:dword_1800200F8, 0
0x18000713a  jnz     loc_180007220
0x180007140  mov     cs:dword_1800200F8, edi
0x180007146  mov     edi, r14d
0x180007149  nop     dword ptr [rax+00000000h]
0x180007150  movd    xmm0, edi
0x180007154  cvtdq2pd xmm0, xmm0
0x180007158  mulsd   xmm0, xmm7
0x18000715c  mulsd   xmm0, xmm8; X
0x180007161  call    _o_sin_0
0x180007166  mulsd   xmm0, xmm9
0x18000716b  cvttsd2si ecx, xmm0
0x18000716f  mov     eax, edi
0x180007171  mov     rva ?m_snSineTable@CVoiceLFO@@0PAFA[r12+rax*2], cx; short near * CVoiceLFO::m_snSineTable ...
0x18000717a  inc     edi
0x18000717c  cmp     edi, 100h
0x180007182  jl      short loc_180007150
0x180007184  mov     cs:?m_snAttackTable@CVoiceEG@@0PAFA, r14w; short near * CVoiceEG::m_snAttackTable
0x18000718c  mov     edi, 1
0x180007191  movd    xmm0, edi
0x180007195  cvtdq2pd xmm0, xmm0
0x180007199  divsd   xmm0, xmm11
0x18000719e  mulsd   xmm0, xmm0; X
0x1800071a2  call    _o_log10_0
0x1800071a7  mulsd   xmm0, xmm12
0x1800071ac  divsd   xmm0, xmm13
0x1800071b1  addsd   xmm0, xmm6
0x1800071b5  cvttsd2si ecx, xmm0
0x1800071b9  mov     eax, edi
0x1800071bb  mov     rva ?m_snAttackTable@CVoiceEG@@0PAFA[r12+rax*2], cx; short near * CVoiceEG::m_snAttackTable ...
0x1800071c4  inc     edi
0x1800071c6  cmp     edi, 0C8h
0x1800071cc  jle     short loc_180007191
0x1800071ce  call    ?Init@CDigitalAudio@@SAXXZ; CDigitalAudio::Init(void)
0x1800071d3  mov     edi, 1
0x1800071d8  mov     r15d, 80h
0x1800071de  xchg    ax, ax
0x1800071e0  movzx   eax, di
0x1800071e3  movd    xmm0, eax
0x1800071e7  cvtdq2pd xmm0, xmm0
0x1800071eb  divsd   xmm0, xmm10; X
0x1800071f0  call    _o_log10_0
0x1800071f5  mulsd   xmm0, xmm6
0x1800071f9  cvttsd2si ecx, xmm0
0x1800071fd  movzx   eax, di
0x180007200  mov     rva ?m_svrPanToVREL@CVoice@@0PAJA[r12+rax*4], ecx; long near * CVoice::m_svrPanToVREL ...
0x180007208  inc     di
0x18000720b  cmp     di, r15w
0x18000720f  jb      short loc_1800071E0
0x180007211  mov     cs:?m_svrPanToVREL@CVoice@@0PAJA, 0FFFFF63Ch; long near * CVoice::m_svrPanToVREL
0x18000721b  mov     r15, [rsp+0F8h+var_D8]
0x180007220  mov     ecx, ebx
0x180007222  mov     rax, [rsp+0F8h+var_C8]
0x180007227  mov     rcx, [rax+rcx*8]
0x18000722b  mov     eax, [rsi+0B0h]
0x180007231  mov     [rcx+0D6Ch], eax
0x180007237  inc     ebx
0x180007239  mov     dword ptr [rsp+0F8h+arg_10], ebx
0x180007240  jmp     loc_18000705B
0x180007245  mov     r13d, ebx
0x180007248  mov     rdi, [rsp+0F8h+arg_18]
0x180007250  mov     rcx, [rsi+408h]; void *
0x180007257  test    rcx, rcx
0x18000725a  jz      short loc_180007261
0x18000725c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007261  mov     [rsi+408h], r15
0x180007268  mov     [rdi], r13d
0x18000726b  mov     rcx, [rsp+0F8h+lpCriticalSection]; lpCriticalSection
0x180007270  call    cs:__imp_LeaveCriticalSection
0x180007276  mov     eax, r14d
0x180007279  jmp     short loc_1800072F1
0x18000727b  mov     rcx, rsi; this
0x18000727e  call    ?AllNotesOff@CSynth@@QEAAJXZ; CSynth::AllNotesOff(void)
0x180007283  mov     ebx, r14d
0x180007286  test    r13d, r13d
0x180007289  jz      short loc_1800072A8
0x18000728b  nop     dword ptr [rax+rax+00h]
0x180007290  mov     edx, ebx; unsigned int
0x180007292  mov     rax, [rsi+408h]
0x180007299  mov     rcx, [rax+rdx*8]
0x18000729d  mov     [r15+rdx*8], rcx
0x1800072a1  inc     ebx
0x1800072a3  cmp     ebx, r13d
0x1800072a6  jb      short loc_180007290
0x1800072a8  cmp     ebx, [rdi]
0x1800072aa  jnb     short loc_180007250
0x1800072ac  nop     dword ptr [rax+00h]
0x1800072b0  mov     ecx, ebx
0x1800072b2  mov     rax, [rsi+408h]
0x1800072b9  mov     rcx, [rax+rcx*8]; this
0x1800072bd  test    rcx, rcx
0x1800072c0  jz      short loc_1800072C7
0x1800072c2  call    ??_GCControlLogic@@QEAAPEAXI@Z; CControlLogic::`scalar deleting destructor'(uint)
0x1800072c7  inc     ebx
0x1800072c9  cmp     ebx, [rsi+410h]
0x1800072cf  jb      short loc_1800072B0
0x1800072d1  jmp     loc_180007250
0x1800072d6  mov     r14d, 8007000Eh
0x1800072dc  mov     rcx, [rsp+0F8h+lpCriticalSection]; lpCriticalSection
0x1800072e1  call    cs:__imp_LeaveCriticalSection
0x1800072e7  mov     eax, r14d
0x1800072ea  jmp     short loc_1800072F1
0x1800072ec  mov     eax, 80070057h
0x1800072f1  lea     r11, [rsp+0F8h+var_38]
0x1800072f9  movaps  xmm6, xmmword ptr [r11-10h]
0x1800072fe  movaps  xmm7, xmmword ptr [r11-20h]
0x180007303  movaps  xmm8, xmmword ptr [r11-30h]
0x180007308  movaps  xmm9, xmmword ptr [r11-40h]
0x18000730d  movaps  xmm10, xmmword ptr [r11-50h]
0x180007312  movaps  xmm11, xmmword ptr [r11-60h]
0x180007317  movaps  xmm12, xmmword ptr [r11-70h]
0x18000731c  movaps  xmm13, xmmword ptr [r11-80h]
0x180007321  mov     rsp, r11
0x180007324  pop     r15
0x180007326  pop     r14
0x180007328  pop     r13
0x18000732a  pop     r12
0x18000732c  pop     rdi
0x18000732d  pop     rsi
0x18000732e  pop     rbx
0x18000732f  retn
```
