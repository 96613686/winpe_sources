# EventClass_RenderTarget_CreateSolidColorBrush::EventClass_RenderTarget_CreateSolidColorBrush(TraceLogPolicy *,ID2D1RenderTarget const *,_D3DCOLORVALUE const *,D2D1_BRUSH_PROPERTIES const *,ID2D1SolidColorBrush * *)

- ea: `0x180142010`
- end: `0x180142425`
- name: `??0EventClass_RenderTarget_CreateSolidColorBrush@@QEAA@PEAVTraceLogPolicy@@PEBUID2D1RenderTarget@@PEBU_D3DCOLORVALUE@@PEBUD2D1_BRUSH_PROPERTIES@@PEAPEAUID2D1SolidColorBrush@@@Z`
- size: `1045`
- prototype: `EventClass_RenderTarget_CreateSolidColorBrush *__fastcall(EventClass_RenderTarget_CreateSolidColorBrush *__hidden this, struct TraceLogPolicy *, const struct ID2D1RenderTarget *, const struct _D3DCOLORVALUE *, const struct D2D1_BRUSH_PROPERTIES *, struct ID2D1SolidColorBrush **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801417e0`
- `0x180141ba0`

## callees

- `0x180142010`
- `0x1801ccb7c`
- `0x18025b100`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1801423f5`
- `ntdll!EtwEventWriteTransfer` at `0x1801423f5`

## string_xrefs

- `0x1801422be`: `CreateSolidColorBrush`

## pseudocode

```c
EventClass_RenderTarget_CreateSolidColorBrush *__fastcall EventClass_RenderTarget_CreateSolidColorBrush::EventClass_RenderTarget_CreateSolidColorBrush(
        EventClass_RenderTarget_CreateSolidColorBrush *this,
        struct TraceLogPolicy *a2,
        const struct ID2D1RenderTarget *a3,
        const struct _D3DCOLORVALUE *a4,
        const struct D2D1_BRUSH_PROPERTIES *a5,
        struct ID2D1SolidColorBrush **a6)
{
  int v8; // ecx
  unsigned int v9; // eax
  __int64 *v10; // rax
  __int64 v11; // rcx
  int v13; // [rsp+80h] [rbp-80h] BYREF
  int v14; // [rsp+84h] [rbp-7Ch] BYREF
  int v15; // [rsp+88h] [rbp-78h] BYREF
  int v16; // [rsp+8Ch] [rbp-74h] BYREF
  int v17; // [rsp+90h] [rbp-70h] BYREF
  int v18; // [rsp+94h] [rbp-6Ch] BYREF
  int v19; // [rsp+98h] [rbp-68h] BYREF
  int v20; // [rsp+9Ch] [rbp-64h] BYREF
  int v21; // [rsp+A0h] [rbp-60h] BYREF
  int v22; // [rsp+A4h] [rbp-5Ch] BYREF
  int v23; // [rsp+A8h] [rbp-58h] BYREF
  int v24; // [rsp+ACh] [rbp-54h] BYREF
  _DWORD v25[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v27; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD v29[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v30; // [rsp+D8h] [rbp-28h]
  char *v31; // [rsp+E0h] [rbp-20h] BYREF
  int v32; // [rsp+E8h] [rbp-18h]
  int v33; // [rsp+ECh] [rbp-14h]
  char *v34; // [rsp+F0h] [rbp-10h]
  int v35; // [rsp+F8h] [rbp-8h]
  int v36; // [rsp+FCh] [rbp-4h]
  const char *v37; // [rsp+100h] [rbp+0h]
  __int64 v38; // [rsp+108h] [rbp+8h]
  const char *v39; // [rsp+110h] [rbp+10h]
  __int64 v40; // [rsp+118h] [rbp+18h]
  _DWORD *v41; // [rsp+120h] [rbp+20h]
  __int64 v42; // [rsp+128h] [rbp+28h]
  __int64 *v43; // [rsp+130h] [rbp+30h]
  __int64 v44; // [rsp+138h] [rbp+38h]
  int *v45; // [rsp+140h] [rbp+40h]
  __int64 v46; // [rsp+148h] [rbp+48h]
  int *v47; // [rsp+150h] [rbp+50h]
  __int64 v48; // [rsp+158h] [rbp+58h]
  int *v49; // [rsp+160h] [rbp+60h]
  __int64 v50; // [rsp+168h] [rbp+68h]
  int *v51; // [rsp+170h] [rbp+70h]
  __int64 v52; // [rsp+178h] [rbp+78h]
  int *v53; // [rsp+180h] [rbp+80h]
  __int64 v54; // [rsp+188h] [rbp+88h]
  int *v55; // [rsp+190h] [rbp+90h]
  __int64 v56; // [rsp+198h] [rbp+98h]
  int *v57; // [rsp+1A0h] [rbp+A0h]
  __int64 v58; // [rsp+1A8h] [rbp+A8h]
  int *v59; // [rsp+1B0h] [rbp+B0h]
  __int64 v60; // [rsp+1B8h] [rbp+B8h]
  int *v61; // [rsp+1C0h] [rbp+C0h]
  __int64 v62; // [rsp+1C8h] [rbp+C8h]
  int *v63; // [rsp+1D0h] [rbp+D0h]
  __int64 v64; // [rsp+1D8h] [rbp+D8h]
  int *v65; // [rsp+1E0h] [rbp+E0h]
  __int64 v66; // [rsp+1E8h] [rbp+E8h]
  int *v67; // [rsp+1F0h] [rbp+F0h]
  __int64 v68; // [rsp+1F8h] [rbp+F8h]
  __int64 *v69; // [rsp+200h] [rbp+100h]
  __int64 v70; // [rsp+208h] [rbp+108h]
  __int64 *v71; // [rsp+210h] [rbp+110h]
  __int64 v72; // [rsp+218h] [rbp+118h]

  *(_QWORD *)this = a3;
  *(struct _D3DCOLORVALUE *)((char *)this + 8) = *(const struct _D3DCOLORVALUE *)&a4->r;
  if ( a5 )
  {
    *((_DWORD *)this + 6) = 1;
    *(_OWORD *)((char *)this + 28) = *(_OWORD *)&a5->opacity;
    *(_OWORD *)((char *)this + 40) = *(_OWORD *)&a5->transform.m[1][0];
    v8 = 1;
  }
  else
  {
    *((_DWORD *)this + 6) = 0;
    v8 = 0;
  }
  *((_QWORD *)this + 7) = a6;
  if ( (Microsoft_Windows_D2D1EnableBits & 1) != 0 )
    McTemplateU0pffffqfffffffp_EtwEventWriteTransfer(
      v8,
      (unsigned int)RenderTarget_CreateSolidColorBrush_Start,
      (_DWORD)a3,
      (_DWORD)a4,
      *((_DWORD *)this + 3),
      *((_DWORD *)this + 4),
      *((_DWORD *)this + 5),
      v8,
      *((_DWORD *)this + 7),
      *((_DWORD *)this + 8),
      *((_DWORD *)this + 9),
      *((_DWORD *)this + 10),
      *((_DWORD *)this + 11),
      *((_DWORD *)this + 12),
      *((_DWORD *)this + 13),
      (char)*a6);
  if ( *((_BYTE *)a2 + 108) )
  {
    _InterlockedIncrement((volatile signed __int32 *)a2 + 8);
    if ( *((_BYTE *)a2 + 84) )
    {
      if ( *((_DWORD *)a2 + 20) < *((_DWORD *)a2 + 3) )
      {
        v9 = 214013 * *((_DWORD *)a2 + 22) + 2531011;
        *((_DWORD *)a2 + 22) = v9;
        if ( (signed int)(HIWORD(v9) & 0x7FFF) <= *((_DWORD *)a2 + 11) )
        {
          _InterlockedIncrement((volatile signed __int32 *)a2 + 20);
          if ( (unsigned int)dword_1805DAC58 > 5
            && (qword_1805DAC68 & 0x200000000000LL) != 0
            && (qword_1805DAC70 & 0x200000000000LL) == qword_1805DAC70 )
          {
            v10 = (__int64 *)*((_QWORD *)this + 7);
            v26 = 0x1000000;
            v72 = 8;
            v70 = 8;
            v11 = *v10;
            v13 = *((_DWORD *)this + 13);
            v14 = *((_DWORD *)this + 12);
            v15 = *((_DWORD *)this + 11);
            v16 = *((_DWORD *)this + 10);
            v17 = *((_DWORD *)this + 9);
            v18 = *((_DWORD *)this + 8);
            v19 = *((_DWORD *)this + 7);
            v20 = *((_DWORD *)this + 6);
            v21 = *((_DWORD *)this + 5);
            v22 = *((_DWORD *)this + 4);
            v23 = *((_DWORD *)this + 3);
            v24 = *((_DWORD *)this + 2);
            v28 = *(_QWORD *)this;
            v71 = &v26;
            v69 = &v27;
            v67 = &v13;
            v65 = &v14;
            v63 = &v15;
            v61 = &v16;
            v59 = &v17;
            v57 = &v18;
            v55 = &v19;
            v53 = &v20;
            v51 = &v21;
            v49 = &v22;
            v47 = &v23;
            v45 = &v24;
            v43 = &v28;
            v41 = v25;
            v39 = "CreateSolidColorBrush";
            v27 = v11;
            v25[0] = 1;
            v68 = 4;
            v66 = 4;
            v64 = 4;
            v62 = 4;
            v60 = 4;
            v58 = 4;
            v56 = 4;
            v54 = 4;
            v52 = 4;
            v50 = 4;
            v48 = 4;
            v46 = 4;
            v44 = 8;
            v42 = 4;
            v30 = 0x200000000000LL;
            v37 = "IRenderTarget";
            v29[1] = 5;
            v31 = (char *)off_1805DAC60;
            v40 = 22;
            v38 = 14;
            v29[0] = 184549376;
            v32 = *(unsigned __int16 *)off_1805DAC60;
            v34 = byte_1805A70FD;
            v33 = 2;
            v35 = 365;
            v36 = 1;
            v25[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(RegHandle, v29, 0, 0, 20, &v31);
          }
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180142010  mov     [rsp-8+arg_10], rbx
0x180142015  mov     [rsp-8+arg_18], rsi
0x18014201a  push    rbp
0x18014201b  push    rdi
0x18014201c  push    r14
0x18014201e  lea     rbp, [rsp-130h]
0x180142026  sub     rsp, 230h
0x18014202d  mov     rax, cs:__security_cookie
0x180142034  xor     rax, rsp
0x180142037  mov     [rbp+140h+var_20], rax
0x18014203e  mov     rax, [rbp+140h+arg_20]
0x180142045  xor     r14d, r14d
0x180142048  mov     [rcx], r8
0x18014204b  mov     rdi, rdx
0x18014204e  mov     rbx, rcx
0x180142051  movups  xmm0, xmmword ptr [r9]
0x180142055  movups  xmmword ptr [rcx+8], xmm0
0x180142059  test    rax, rax
0x18014205c  jz      short loc_18014207B
0x18014205e  mov     dword ptr [rcx+18h], 1
0x180142065  movups  xmm0, xmmword ptr [rax]
0x180142068  movups  xmmword ptr [rcx+1Ch], xmm0
0x18014206c  movups  xmm1, xmmword ptr [rax+0Ch]
0x180142070  movups  xmmword ptr [rcx+28h], xmm1
0x180142074  mov     ecx, 1
0x180142079  jmp     short loc_180142082
0x18014207b  mov     [rcx+18h], r14d
0x18014207f  mov     ecx, r14d
0x180142082  mov     rax, [rbp+140h+arg_28]
0x180142089  mov     [rbx+38h], rax
0x18014208d  test    byte ptr cs:Microsoft_Windows_D2D1EnableBits, 1
0x180142094  jz      loc_180142125
0x18014209a  movss   xmm0, dword ptr [rbx+34h]
0x18014209f  lea     rdx, RenderTarget_CreateSolidColorBrush_Start
0x1801420a6  movss   xmm1, dword ptr [rbx+30h]
0x1801420ab  mov     rax, [rax]
0x1801420ae  movss   xmm3, dword ptr [rbx+8]
0x1801420b3  mov     [rsp+240h+var_1C8], rax
0x1801420b8  movss   [rsp+240h+var_1D0], xmm0
0x1801420be  movss   xmm0, dword ptr [rbx+2Ch]
0x1801420c3  movss   [rsp+240h+var_1D8], xmm1
0x1801420c9  movss   xmm1, dword ptr [rbx+28h]
0x1801420ce  movss   [rsp+240h+var_1E0], xmm0
0x1801420d4  movss   xmm0, dword ptr [rbx+24h]
0x1801420d9  movss   [rsp+240h+var_1E8], xmm1
0x1801420df  movss   xmm1, dword ptr [rbx+20h]
0x1801420e4  movss   [rsp+240h+var_1F0], xmm0
0x1801420ea  movss   xmm0, dword ptr [rbx+1Ch]
0x1801420ef  movss   [rsp+240h+var_1F8], xmm1
0x1801420f5  movss   xmm1, dword ptr [rbx+14h]
0x1801420fa  movss   [rsp+240h+var_200], xmm0
0x180142100  movss   xmm0, dword ptr [rbx+10h]
0x180142105  mov     [rsp+240h+var_208], ecx
0x180142109  movss   [rsp+240h+var_210], xmm1
0x18014210f  movss   xmm1, dword ptr [rbx+0Ch]
0x180142114  movss   dword ptr [rsp+240h+var_218], xmm0
0x18014211a  movss   [rsp+240h+var_220], xmm1
0x180142120  call    McTemplateU0pffffqfffffffp_EtwEventWriteTransfer
0x180142125  cmp     [rdi+6Ch], r14b
0x180142129  jz      loc_1801423FB
0x18014212f  lock inc dword ptr [rdi+20h]
0x180142133  cmp     [rdi+54h], r14b
0x180142137  jz      loc_1801423FB
0x18014213d  mov     eax, [rdi+0Ch]
0x180142140  cmp     [rdi+50h], eax
0x180142143  jnb     loc_1801423FB
0x180142149  imul    eax, [rdi+58h], 343FDh
0x180142150  add     eax, 269EC3h
0x180142155  mov     [rdi+58h], eax
0x180142158  shr     eax, 10h
0x18014215b  and     eax, 7FFFh
0x180142160  cmp     eax, [rdi+2Ch]
0x180142163  jg      loc_1801423FB
0x180142169  lock inc dword ptr [rdi+50h]
0x18014216d  mov     eax, cs:dword_1805DAC58
0x180142173  cmp     eax, 5
0x180142176  jbe     loc_1801423FB
0x18014217c  mov     rcx, cs:qword_1805DAC70
0x180142183  mov     rdx, 200000000000h
0x18014218d  mov     rax, cs:qword_1805DAC68
0x180142194  test    rdx, rax
0x180142197  jz      loc_1801423FB
0x18014219d  mov     rax, rcx
0x1801421a0  and     rax, rdx
0x1801421a3  cmp     rax, rcx
0x1801421a6  jnz     loc_1801423FB
0x1801421ac  mov     rax, [rbx+38h]
0x1801421b0  mov     [rbp+140h+var_188], 1000000h
0x1801421b8  mov     [rbp+140h+var_28], 8
0x1801421c3  mov     [rbp+140h+var_38], 8
0x1801421ce  mov     rcx, [rax]
0x1801421d1  mov     eax, [rbx+34h]
0x1801421d4  mov     [rbp+140h+var_1C0], eax
0x1801421d7  mov     eax, [rbx+30h]
0x1801421da  mov     [rbp+140h+var_1BC], eax
0x1801421dd  mov     eax, [rbx+2Ch]
0x1801421e0  mov     [rbp+140h+var_1B8], eax
0x1801421e3  mov     eax, [rbx+28h]
0x1801421e6  mov     [rbp+140h+var_1B4], eax
0x1801421e9  mov     eax, [rbx+24h]
0x1801421ec  mov     [rbp+140h+var_1B0], eax
0x1801421ef  mov     eax, [rbx+20h]
0x1801421f2  mov     [rbp+140h+var_1AC], eax
0x1801421f5  mov     eax, [rbx+1Ch]
0x1801421f8  mov     [rbp+140h+var_1A8], eax
0x1801421fb  mov     eax, [rbx+18h]
0x1801421fe  mov     [rbp+140h+var_1A4], eax
0x180142201  mov     eax, [rbx+14h]
0x180142204  mov     [rbp+140h+var_1A0], eax
0x180142207  mov     eax, [rbx+10h]
0x18014220a  mov     [rbp+140h+var_19C], eax
0x18014220d  mov     eax, [rbx+0Ch]
0x180142210  mov     [rbp+140h+var_198], eax
0x180142213  mov     eax, [rbx+8]
0x180142216  mov     [rbp+140h+var_194], eax
0x180142219  mov     rax, [rbx]
0x18014221c  mov     [rbp+140h+var_178], rax
0x180142220  lea     rax, [rbp+140h+var_188]
0x180142224  mov     [rbp+140h+var_30], rax
0x18014222b  lea     rax, [rbp+140h+var_180]
0x18014222f  mov     [rbp+140h+var_40], rax
0x180142236  lea     rax, [rbp+140h+var_1C0]
0x18014223a  mov     [rbp+140h+var_50], rax
0x180142241  lea     rax, [rbp+140h+var_1BC]
0x180142245  mov     [rbp+140h+var_60], rax
0x18014224c  lea     rax, [rbp+140h+var_1B8]
0x180142250  mov     [rbp+140h+var_70], rax
0x180142257  lea     rax, [rbp+140h+var_1B4]
0x18014225b  mov     [rbp+140h+var_80], rax
0x180142262  lea     rax, [rbp+140h+var_1B0]
0x180142266  mov     [rbp+140h+var_90], rax
0x18014226d  lea     rax, [rbp+140h+var_1AC]
0x180142271  mov     [rbp+140h+var_A0], rax
0x180142278  lea     rax, [rbp+140h+var_1A8]
0x18014227c  mov     [rbp+140h+var_B0], rax
0x180142283  lea     rax, [rbp+140h+var_1A4]
0x180142287  mov     [rbp+140h+var_C0], rax
0x18014228e  lea     rax, [rbp+140h+var_1A0]
0x180142292  mov     [rbp+140h+var_D0], rax
0x180142296  lea     rax, [rbp+140h+var_19C]
0x18014229a  mov     [rbp+140h+var_E0], rax
0x18014229e  lea     rax, [rbp+140h+var_198]
0x1801422a2  mov     [rbp+140h+var_F0], rax
0x1801422a6  lea     rax, [rbp+140h+var_194]
0x1801422aa  mov     [rbp+140h+var_100], rax
0x1801422ae  lea     rax, [rbp+140h+var_178]
0x1801422b2  mov     [rbp+140h+var_110], rax
0x1801422b6  lea     rax, [rbp+140h+var_190]
0x1801422ba  mov     [rbp+140h+var_120], rax
0x1801422be  lea     rax, aCreatesolidcol; "CreateSolidColorBrush"
0x1801422c5  mov     [rbp+140h+var_130], rax
0x1801422c9  mov     [rbp+140h+var_180], rcx
0x1801422cd  mov     [rbp+140h+var_190], 1
0x1801422d4  mov     [rbp+140h+var_48], 4
0x1801422df  mov     [rbp+140h+var_58], 4
0x1801422ea  mov     [rbp+140h+var_68], 4
0x1801422f5  mov     [rbp+140h+var_78], 4
0x180142300  mov     [rbp+140h+var_88], 4
0x18014230b  mov     [rbp+140h+var_98], 4
0x180142316  mov     [rbp+140h+var_A8], 4
0x180142321  mov     [rbp+140h+var_B8], 4
0x18014232c  mov     [rbp+140h+var_C8], 4
0x180142334  mov     [rbp+140h+var_D8], 4
0x18014233c  mov     [rbp+140h+var_E8], 4
0x180142344  mov     [rbp+140h+var_F8], 4
0x18014234c  mov     [rbp+140h+var_108], 8
0x180142354  mov     [rbp+140h+var_118], 4
0x18014235c  mov     [rbp+140h+var_168], rdx
0x180142360  lea     rax, aIrendertarget; "IRenderTarget"
0x180142367  mov     [rbp+140h+var_140], rax
0x18014236b  lea     rcx, _TraceLoggingMetadataEnd
0x180142372  movzx   eax, cs:word_1805A70F3
0x180142379  lea     rdx, [rbp+140h+var_170]
0x18014237d  mov     [rbp+140h+var_16C], eax
0x180142380  xor     r9d, r9d
0x180142383  mov     rax, cs:off_1805DAC60
0x18014238a  xor     r8d, r8d
0x18014238d  mov     [rbp+140h+var_160], rax
0x180142391  mov     [rbp+140h+var_128], 16h
0x180142399  mov     [rbp+140h+var_138], 0Eh
0x1801423a1  mov     [rbp+140h+var_170], 0B000000h
0x1801423a8  movzx   eax, word ptr [rax]
0x1801423ab  mov     [rbp+140h+var_158], eax
0x1801423ae  lea     rax, byte_1805A70FD
0x1801423b5  mov     [rbp+140h+var_150], rax
0x1801423b9  lea     rax, _TraceLoggingMetadata
0x1801423c0  sub     ecx, eax
0x1801423c2  mov     [rbp+140h+var_154], 2
0x1801423c9  mov     [rbp+140h+var_148], 16Dh
0x1801423d0  lea     rax, [rbp+140h+var_160]
0x1801423d4  mov     [rbp+140h+var_144], 1
0x1801423db  mov     [rbp+140h+var_18C], ecx
0x1801423de  mov     ecx, [rbp+140h+var_18C]
0x1801423e1  mov     rcx, cs:RegHandle
0x1801423e8  mov     [rsp+240h+var_218], rax
0x1801423ed  mov     [rsp+240h+var_220], 14h
0x1801423f5  call    cs:__imp_EtwEventWriteTransfer
0x1801423fb  mov     rax, rbx
0x1801423fe  mov     rcx, [rbp+140h+var_20]
0x180142405  xor     rcx, rsp; StackCookie
0x180142408  call    __security_check_cookie
0x18014240d  lea     r11, [rsp+240h+var_10]
0x180142415  mov     rbx, [r11+30h]
0x180142419  mov     rsi, [r11+38h]
0x18014241d  mov     rsp, r11
0x180142420  pop     r14
0x180142422  pop     rdi
0x180142423  pop     rbp
0x180142424  retn
```
