# AdaptiveRgb2Yuv444Shader::InitShader(int)

- ea: `0x180149040`
- end: `0x180149572`
- name: `?InitShader@AdaptiveRgb2Yuv444Shader@@MEAAJH@Z`
- size: `1330`
- prototype: `__int64 __fastcall(AdaptiveRgb2Yuv444Shader *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180149580`

## callees

- `0x18002e600`
- `0x180031954`
- `0x1800598d0`
- `0x180148aac`
- `0x180149040`
- `0x18014a288`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149088`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801490cf`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149159`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801491c3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149234`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801492a5`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149312`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149365`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801493b5`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18014943c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149490`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801494dd`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18014952b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149088`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801490cf`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149159`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801491c3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149234`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801492a5`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149312`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149365`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801493b5`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18014943c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180149490`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801494dd`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18014952b`

## string_xrefs

- `0x1801491ce`: `CreateVertexShader(Y) error`
- `0x18014923f`: `CreatePixelShader error`
- `0x180149164`: `Create444VSAndPS failed`
- `0x180149447`: `CreateInputLayout error`
- `0x1801494e8`: `CreateRenderTexture m_pTextureNV12Luma failed`
- `0x180149370`: `CreateVertexBuffer error`
- `0x1801493c0`: `CreateInstanceBuffer error`
- `0x180149536`: `CreateRenderTexture m_pTextureNV12Chroma failed`

## pseudocode

```c
__int64 __fastcall AdaptiveRgb2Yuv444Shader::InitShader(AdaptiveRgb2Yuv444Shader *this)
{
  int VertexBuffer; // ebx
  int ActivityIdPrefix; // eax
  __int64 v4; // rcx
  int v5; // eax
  int v6; // eax
  int v7; // edx
  const char *v8; // rcx
  __int64 v9; // rcx
  __int64 (__fastcall *v10)(__int64, char **, __int64, __int64 *, __int64, char *); // rax
  int v11; // r8d
  int v12; // r8d
  __int64 v14; // [rsp+28h] [rbp-20h]
  int v15; // [rsp+28h] [rbp-20h]
  char *v16; // [rsp+28h] [rbp-20h]

  if ( !*((_DWORD *)this + 28) )
  {
    VertexBuffer = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      v15 = -2147024809;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_1b9841f72f8330d68cb930480f2b3dfa_Traceguids,
        ActivityIdPrefix,
        (__int64)"unsupported dx11!",
        v15);
    }
    return (unsigned int)VertexBuffer;
  }
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    if ( *((_DWORD *)this + 30) )
    {
      VertexBuffer = (*(__int64 (__fastcall **)(AdaptiveRgb2Yuv444Shader *))(*(_QWORD *)this + 64LL))(this);
      if ( VertexBuffer < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)VertexBuffer;
        }
        v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v7 = 12;
        v8 = "Create444VSAndPS failed";
        goto LABEL_74;
      }
LABEL_41:
      VertexBuffer = AdaptiveRgb2Yuv444Shader::CreateVertexBuffer(this);
      if ( VertexBuffer < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)VertexBuffer;
        }
        v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v7 = 17;
        v8 = "CreateVertexBuffer error";
        goto LABEL_74;
      }
      VertexBuffer = AdaptiveRgb2Yuv444Shader::CreateInstanceBuffer(this);
      if ( VertexBuffer < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)VertexBuffer;
        }
        v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v7 = 18;
        v8 = "CreateInstanceBuffer error";
        goto LABEL_74;
      }
      v9 = *((_QWORD *)this + 1);
      v16 = (char *)this + 216;
      v10 = *(__int64 (__fastcall **)(__int64, char **, __int64, __int64 *, __int64, char *))(*(_QWORD *)v9 + 88LL);
      if ( *((_DWORD *)this + 30) )
      {
        VertexBuffer = v10(v9, &off_180154230, 2, qword_18018AB40, 512, v16);
        if ( VertexBuffer < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return (unsigned int)VertexBuffer;
          }
          v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
          v7 = 19;
LABEL_57:
          v8 = "CreateInputLayout error";
          goto LABEL_74;
        }
      }
      else
      {
        VertexBuffer = v10(v9, &off_180154230, 2, qword_18018AD40, 512, v16);
        if ( VertexBuffer < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return (unsigned int)VertexBuffer;
          }
          v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
          v7 = 20;
          goto LABEL_57;
        }
      }
      VertexBuffer = CBaseShaderFilter::CreateRenderTexture(this, (struct CTextureNV12DMA **)this + 21, v11);
      if ( VertexBuffer >= 0 )
      {
        if ( !*((_DWORD *)this + 30) )
          return (unsigned int)VertexBuffer;
        VertexBuffer = CBaseShaderFilter::CreateRenderTexture(this, (struct CTextureNV12DMA **)this + 22, v12);
        if ( VertexBuffer >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)VertexBuffer;
        }
        v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v7 = 22;
        v8 = "CreateRenderTexture m_pTextureNV12Chroma failed";
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)VertexBuffer;
        }
        v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v7 = 21;
        v8 = "CreateRenderTexture m_pTextureNV12Luma failed";
      }
LABEL_74:
      LODWORD(v14) = VertexBuffer;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        (unsigned int)WPP_1b9841f72f8330d68cb930480f2b3dfa_Traceguids,
        v6,
        (__int64)v8,
        v14);
      return (unsigned int)VertexBuffer;
    }
    VertexBuffer = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD, char *))(*(_QWORD *)v4 + 96LL))(
                     v4,
                     qword_18018AD40,
                     512,
                     0,
                     (char *)this + 40);
    if ( VertexBuffer < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)VertexBuffer;
      }
      v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      v7 = 13;
LABEL_23:
      v8 = "CreateVertexShader(Y) error";
      goto LABEL_74;
    }
    VertexBuffer = (*(__int64 (__fastcall **)(_QWORD, void *, __int64, _QWORD, char *))(**((_QWORD **)this + 1) + 120LL))(
                     *((_QWORD *)this + 1),
                     &unk_18018AF40,
                     592,
                     0,
                     (char *)this + 24);
    if ( VertexBuffer >= 0 )
    {
      VertexBuffer = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD, char *))(**((_QWORD **)this + 1)
                                                                                           + 96LL))(
                       *((_QWORD *)this + 1),
                       qword_18018B190,
                       512,
                       0,
                       (char *)this + 128);
      if ( VertexBuffer < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)VertexBuffer;
        }
        v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v7 = 15;
        goto LABEL_23;
      }
      VertexBuffer = (*(__int64 (__fastcall **)(_QWORD, void *, __int64, _QWORD, char *))(**((_QWORD **)this + 1) + 120LL))(
                       *((_QWORD *)this + 1),
                       &unk_18018B390,
                       1368,
                       0,
                       (char *)this + 136);
      if ( VertexBuffer >= 0 )
      {
        *((_DWORD *)this + 40) = 16;
        goto LABEL_41;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)VertexBuffer;
      }
      v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      v7 = 16;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)VertexBuffer;
      }
      v6 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      v7 = 14;
    }
    v8 = "CreatePixelShader error";
    goto LABEL_74;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_1b9841f72f8330d68cb930480f2b3dfa_Traceguids,
      v5,
      (__int64)"m_spD3D11Device");
  }
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x180149040  mov     [rsp+arg_0], rbx
0x180149045  mov     [rsp+arg_8], rbp
0x18014904a  push    rdi
0x18014904b  sub     rsp, 40h
0x18014904f  cmp     dword ptr [rcx+70h], 0
0x180149053  mov     rdi, rcx
0x180149056  jnz     short loc_1801490A7
0x180149058  mov     ebx, 80070057h
0x18014905d  mov     rcx, cs:WPP_GLOBAL_Control
0x180149064  lea     rax, WPP_GLOBAL_Control
0x18014906b  cmp     rcx, rax
0x18014906e  jz      loc_180149560
0x180149074  test    byte ptr [rcx+1Ch], 8
0x180149078  jz      loc_180149560
0x18014907e  cmp     byte ptr [rcx+19h], 2
0x180149082  jb      loc_180149560
0x180149088  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18014908e  mov     edx, 0Ah
0x180149093  mov     dword ptr [rsp+48h+var_20], 80070057h
0x18014909b  lea     rcx, aUnsupportedDx1; "unsupported dx11!"
0x1801490a2  jmp     loc_180149541
0x1801490a7  mov     rcx, [rcx+8]
0x1801490ab  test    rcx, rcx
0x1801490ae  jnz     short loc_18014910A
0x1801490b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801490b7  lea     rax, WPP_GLOBAL_Control
0x1801490be  cmp     rcx, rax
0x1801490c1  jz      short loc_180149100
0x1801490c3  test    byte ptr [rcx+1Ch], 8
0x1801490c7  jz      short loc_180149100
0x1801490c9  cmp     byte ptr [rcx+19h], 2
0x1801490cd  jb      short loc_180149100
0x1801490cf  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801490d5  lea     rcx, aMSpd3d11device; "m_spD3D11Device"
0x1801490dc  mov     edx, 0Bh
0x1801490e1  mov     [rsp+48h+var_28], rcx
0x1801490e6  lea     r8, WPP_1b9841f72f8330d68cb930480f2b3dfa_Traceguids
0x1801490ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1801490f4  mov     r9d, eax
0x1801490f7  mov     rcx, [rcx+10h]
0x1801490fb  call    WPP_SF_Ds
0x180149100  mov     ebx, 80004003h
0x180149105  jmp     loc_180149560
0x18014910a  cmp     dword ptr [rdi+78h], 0
0x18014910e  mov     ebp, 200h
0x180149113  jz      short loc_180149170
0x180149115  mov     rax, [rdi]
0x180149118  mov     rcx, rdi
0x18014911b  mov     rax, [rax+40h]
0x18014911f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149124  mov     ebx, eax
0x180149126  test    eax, eax
0x180149128  jns     loc_18014932C
0x18014912e  mov     rcx, cs:WPP_GLOBAL_Control
0x180149135  lea     rax, WPP_GLOBAL_Control
0x18014913c  cmp     rcx, rax
0x18014913f  jz      loc_180149560
0x180149145  test    byte ptr [rcx+1Ch], 8
0x180149149  jz      loc_180149560
0x18014914f  cmp     byte ptr [rcx+19h], 2
0x180149153  jb      loc_180149560
0x180149159  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18014915f  mov     edx, 0Ch
0x180149164  lea     rcx, aCreate444vsand; "Create444VSAndPS failed"
0x18014916b  jmp     loc_18014953D
0x180149170  mov     rax, [rcx]
0x180149173  lea     rdx, [rdi+28h]
0x180149177  mov     [rsp+48h+var_28], rdx
0x18014917c  xor     r9d, r9d
0x18014917f  mov     r8, rbp
0x180149182  lea     rdx, qword_18018AD40
0x180149189  mov     rax, [rax+60h]
0x18014918d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149192  mov     ebx, eax
0x180149194  test    eax, eax
0x180149196  jns     short loc_1801491DA
0x180149198  mov     rcx, cs:WPP_GLOBAL_Control
0x18014919f  lea     rax, WPP_GLOBAL_Control
0x1801491a6  cmp     rcx, rax
0x1801491a9  jz      loc_180149560
0x1801491af  test    byte ptr [rcx+1Ch], 8
0x1801491b3  jz      loc_180149560
0x1801491b9  cmp     byte ptr [rcx+19h], 2
0x1801491bd  jb      loc_180149560
0x1801491c3  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801491c9  mov     edx, 0Dh
0x1801491ce  lea     rcx, aCreatevertexsh_0; "CreateVertexShader(Y) error"
0x1801491d5  jmp     loc_18014953D
0x1801491da  mov     rcx, [rdi+8]
0x1801491de  lea     rdx, [rdi+18h]
0x1801491e2  mov     [rsp+48h+var_28], rdx
0x1801491e7  xor     r9d, r9d
0x1801491ea  mov     r8d, 250h
0x1801491f0  lea     rdx, unk_18018AF40
0x1801491f7  mov     rax, [rcx]
0x1801491fa  mov     rax, [rax+78h]
0x1801491fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149203  mov     ebx, eax
0x180149205  test    eax, eax
0x180149207  jns     short loc_18014924B
0x180149209  mov     rcx, cs:WPP_GLOBAL_Control
0x180149210  lea     rax, WPP_GLOBAL_Control
0x180149217  cmp     rcx, rax
0x18014921a  jz      loc_180149560
0x180149220  test    byte ptr [rcx+1Ch], 8
0x180149224  jz      loc_180149560
0x18014922a  cmp     byte ptr [rcx+19h], 2
0x18014922e  jb      loc_180149560
0x180149234  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18014923a  mov     edx, 0Eh
0x18014923f  lea     rcx, aCreatepixelsha; "CreatePixelShader error"
0x180149246  jmp     loc_18014953D
0x18014924b  mov     rcx, [rdi+8]
0x18014924f  lea     rdx, [rdi+80h]
0x180149256  mov     [rsp+48h+var_28], rdx
0x18014925b  xor     r9d, r9d
0x18014925e  mov     r8, rbp
0x180149261  lea     rdx, qword_18018B190
0x180149268  mov     rax, [rcx]
0x18014926b  mov     rax, [rax+60h]
0x18014926f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149274  mov     ebx, eax
0x180149276  test    eax, eax
0x180149278  jns     short loc_1801492B5
0x18014927a  mov     rcx, cs:WPP_GLOBAL_Control
0x180149281  lea     rax, WPP_GLOBAL_Control
0x180149288  cmp     rcx, rax
0x18014928b  jz      loc_180149560
0x180149291  test    byte ptr [rcx+1Ch], 8
0x180149295  jz      loc_180149560
0x18014929b  cmp     byte ptr [rcx+19h], 2
0x18014929f  jb      loc_180149560
0x1801492a5  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801492ab  mov     edx, 0Fh
0x1801492b0  jmp     loc_1801491CE
0x1801492b5  mov     rcx, [rdi+8]
0x1801492b9  lea     rdx, [rdi+88h]
0x1801492c0  mov     [rsp+48h+var_28], rdx
0x1801492c5  xor     r9d, r9d
0x1801492c8  mov     r8d, 558h
0x1801492ce  lea     rdx, unk_18018B390
0x1801492d5  mov     rax, [rcx]
0x1801492d8  mov     rax, [rax+78h]
0x1801492dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801492e1  mov     ebx, eax
0x1801492e3  test    eax, eax
0x1801492e5  jns     short loc_180149322
0x1801492e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801492ee  lea     rax, WPP_GLOBAL_Control
0x1801492f5  cmp     rcx, rax
0x1801492f8  jz      loc_180149560
0x1801492fe  test    byte ptr [rcx+1Ch], 8
0x180149302  jz      loc_180149560
0x180149308  cmp     byte ptr [rcx+19h], 2
0x18014930c  jb      loc_180149560
0x180149312  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180149318  mov     edx, 10h
0x18014931d  jmp     loc_18014923F
0x180149322  mov     dword ptr [rdi+0A0h], 10h
0x18014932c  mov     rcx, rdi; this
0x18014932f  call    ?CreateVertexBuffer@AdaptiveRgb2Yuv444Shader@@AEAAJXZ; AdaptiveRgb2Yuv444Shader::CreateVertexBuffer(void)
0x180149334  mov     ebx, eax
0x180149336  test    eax, eax
0x180149338  jns     short loc_18014937C
0x18014933a  mov     rcx, cs:WPP_GLOBAL_Control
0x180149341  lea     rax, WPP_GLOBAL_Control
0x180149348  cmp     rcx, rax
0x18014934b  jz      loc_180149560
0x180149351  test    byte ptr [rcx+1Ch], 8
0x180149355  jz      loc_180149560
0x18014935b  cmp     byte ptr [rcx+19h], 2
0x18014935f  jb      loc_180149560
0x180149365  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18014936b  mov     edx, 11h
0x180149370  lea     rcx, aCreatevertexbu; "CreateVertexBuffer error"
0x180149377  jmp     loc_18014953D
0x18014937c  mov     rcx, rdi; this
0x18014937f  call    ?CreateInstanceBuffer@AdaptiveRgb2Yuv444Shader@@AEAAJXZ; AdaptiveRgb2Yuv444Shader::CreateInstanceBuffer(void)
0x180149384  mov     ebx, eax
0x180149386  test    eax, eax
0x180149388  jns     short loc_1801493CC
0x18014938a  mov     rcx, cs:WPP_GLOBAL_Control
0x180149391  lea     rax, WPP_GLOBAL_Control
0x180149398  cmp     rcx, rax
0x18014939b  jz      loc_180149560
0x1801493a1  test    byte ptr [rcx+1Ch], 8
0x1801493a5  jz      loc_180149560
0x1801493ab  cmp     byte ptr [rcx+19h], 2
0x1801493af  jb      loc_180149560
0x1801493b5  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801493bb  mov     edx, 12h
0x1801493c0  lea     rcx, aCreateinstance; "CreateInstanceBuffer error"
0x1801493c7  jmp     loc_18014953D
0x1801493cc  cmp     dword ptr [rdi+78h], 0
0x1801493d0  lea     rax, [rdi+0D8h]
0x1801493d7  mov     rcx, [rdi+8]
0x1801493db  lea     rdx, off_180154230; "POSITION"
0x1801493e2  mov     [rsp+48h+var_20], rax
0x1801493e7  mov     r8d, 2
0x1801493ed  mov     [rsp+48h+var_28], rbp
0x1801493f2  mov     r10, [rcx]
0x1801493f5  mov     rax, [r10+58h]
0x1801493f9  jz      short loc_180149453
0x1801493fb  lea     r9, qword_18018AB40
0x180149402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149407  mov     ebx, eax
0x180149409  test    eax, eax
0x18014940b  jns     loc_18014949D
0x180149411  mov     rcx, cs:WPP_GLOBAL_Control
0x180149418  lea     rax, WPP_GLOBAL_Control
0x18014941f  cmp     rcx, rax
0x180149422  jz      loc_180149560
0x180149428  test    byte ptr [rcx+1Ch], 8
0x18014942c  jz      loc_180149560
0x180149432  cmp     byte ptr [rcx+19h], 2
0x180149436  jb      loc_180149560
0x18014943c  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180149442  mov     edx, 13h
0x180149447  lea     rcx, aCreateinputlay; "CreateInputLayout error"
0x18014944e  jmp     loc_18014953D
0x180149453  lea     r9, qword_18018AD40
0x18014945a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014945f  mov     ebx, eax
0x180149461  test    eax, eax
0x180149463  jns     short loc_18014949D
0x180149465  mov     rcx, cs:WPP_GLOBAL_Control
0x18014946c  lea     rax, WPP_GLOBAL_Control
0x180149473  cmp     rcx, rax
0x180149476  jz      loc_180149560
0x18014947c  test    byte ptr [rcx+1Ch], 8
0x180149480  jz      loc_180149560
0x180149486  cmp     byte ptr [rcx+19h], 2
0x18014948a  jb      loc_180149560
0x180149490  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180149496  mov     edx, 14h
0x18014949b  jmp     short loc_180149447
0x18014949d  lea     rdx, [rdi+0A8h]; struct CTextureNV12DMA **
0x1801494a4  mov     rcx, rdi; this
0x1801494a7  call    ?CreateRenderTexture@CBaseShaderFilter@@IEAAJPEAPEAVCTextureNV12DMA@@H@Z; CBaseShaderFilter::CreateRenderTexture(CTextureNV12DMA * *,int)
0x1801494ac  mov     ebx, eax
0x1801494ae  test    eax, eax
0x1801494b0  jns     short loc_1801494F1
0x1801494b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801494b9  lea     rax, WPP_GLOBAL_Control
0x1801494c0  cmp     rcx, rax
0x1801494c3  jz      loc_180149560
0x1801494c9  test    byte ptr [rcx+1Ch], 8
0x1801494cd  jz      loc_180149560
0x1801494d3  cmp     byte ptr [rcx+19h], 2
0x1801494d7  jb      loc_180149560
0x1801494dd  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801494e3  mov     edx, 15h
0x1801494e8  lea     rcx, aCreaterenderte_0; "CreateRenderTexture m_pTextureNV12Luma "...
0x1801494ef  jmp     short loc_18014953D
0x1801494f1  cmp     dword ptr [rdi+78h], 0
0x1801494f5  jz      short loc_180149560
0x1801494f7  lea     rdx, [rdi+0B0h]; struct CTextureNV12DMA **
0x1801494fe  mov     rcx, rdi; this
0x180149501  call    ?CreateRenderTexture@CBaseShaderFilter@@IEAAJPEAPEAVCTextureNV12DMA@@H@Z; CBaseShaderFilter::CreateRenderTexture(CTextureNV12DMA * *,int)
0x180149506  mov     ebx, eax
0x180149508  test    eax, eax
0x18014950a  jns     short loc_180149560
0x18014950c  mov     rcx, cs:WPP_GLOBAL_Control
0x180149513  lea     rax, WPP_GLOBAL_Control
0x18014951a  cmp     rcx, rax
0x18014951d  jz      short loc_180149560
0x18014951f  test    byte ptr [rcx+1Ch], 8
0x180149523  jz      short loc_180149560
0x180149525  cmp     byte ptr [rcx+19h], 2
0x180149529  jb      short loc_180149560
0x18014952b  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180149531  mov     edx, 16h
0x180149536  lea     rcx, aCreaterenderte; "CreateRenderTexture m_pTextureNV12Chrom"...
0x18014953d  mov     dword ptr [rsp+48h+var_20], ebx
0x180149541  mov     [rsp+48h+var_28], rcx
0x180149546  lea     r8, WPP_1b9841f72f8330d68cb930480f2b3dfa_Traceguids
0x18014954d  mov     rcx, cs:WPP_GLOBAL_Control
0x180149554  mov     r9d, eax
0x180149557  mov     rcx, [rcx+10h]
0x18014955b  call    WPP_SF_DsD
0x180149560  mov     rbp, [rsp+48h+arg_8]
0x180149565  mov     eax, ebx
0x180149567  mov     rbx, [rsp+48h+arg_0]
0x18014956c  add     rsp, 40h
0x180149570  pop     rdi
0x180149571  retn
```
