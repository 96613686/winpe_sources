# ColorTranslationSequence::Initialize(IDeviceModel *,IColorAppearanceModel *,CITEArray<IGamutMapModel *> *,IColorAppearanceModel *,IDeviceModel *,int,ColorChannelInfo *,ColorChannelInfo *,float,float,CTSOptimizationMode::Enum,QualityMode::Enum,IGamutBoundaryDescription *)

- ea: `0x1800788d0`
- end: `0x180078cd4`
- name: `?Initialize@ColorTranslationSequence@@UEAAJPEAVIDeviceModel@@PEAVIColorAppearanceModel@@PEAU?$CITEArray@PEAVIGamutMapModel@@@@10HPEAUColorChannelInfo@@3MMW4Enum@CTSOptimizationMode@@W46QualityMode@@PEAVIGamutBoundaryDescription@@@Z`
- size: `1028`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18002e5f0`
- `0x1800634ec`
- `0x1800786f4`
- `0x180078808`
- `0x1800788d0`
- `0x18007e564`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180078bd7`
- `ntdll!EtwEventWrite` at `0x180078bd7`

## pseudocode

```c
__int64 __fastcall ColorTranslationSequence::Initialize(
        __int64 a1,
        struct IDeviceModel *a2,
        struct IColorAppearanceModel *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        _DWORD *a8,
        __int64 a9,
        float a10,
        float a11,
        int a12,
        int a13,
        struct IGamutBoundaryDescription *a14)
{
  bool v18; // zf
  int v19; // ecx
  unsigned int v20; // r12d
  unsigned int v21; // eax
  __int64 i; // rcx
  __int64 j; // rcx
  int v24; // r13d
  __int64 k; // rsi
  __int64 v26; // rcx
  int NonEnhancedDestinationTranslator; // eax
  unsigned int v28; // edx
  __int64 v29; // rax
  unsigned int v30; // r9d
  unsigned int v31; // r8d
  __int64 v32; // rdx
  int v34; // [rsp+60h] [rbp-A8h] BYREF
  int v35; // [rsp+64h] [rbp-A4h]
  int v36; // [rsp+68h] [rbp-A0h]
  unsigned int v37; // [rsp+6Ch] [rbp-9Ch]
  struct IColorAppearanceModel *v38; // [rsp+70h] [rbp-98h]
  struct IDeviceModel *v39; // [rsp+78h] [rbp-90h]
  __int64 v40; // [rsp+80h] [rbp-88h]
  __int64 v41; // [rsp+88h] [rbp-80h]
  struct IGamutBoundaryDescription *v42[2]; // [rsp+90h] [rbp-78h] BYREF

  v38 = a3;
  v18 = *(_DWORD *)(a1 + 32) == 0;
  v39 = a2;
  v41 = a5;
  v40 = a6;
  v42[0] = a14;
  if ( v18 )
  {
    if ( a2 && a3 && a4 && a5 && a6 && a8 && a9 && a10 < a11 && (a14 || a12 != 2) && a12 < 3 && *(_DWORD *)a4 )
    {
      NCoreLibrary::TRefSmartPtr<CGamutBoundaryDescription>::operator=((__int64 *)(a1 + 16), (__int64)a2);
      NCoreLibrary::TRefSmartPtr<CGamutBoundaryDescription>::operator=((__int64 *)(a1 + 24), (__int64)a3);
      *(_DWORD *)(a1 + 160) = a7;
      *(_DWORD *)(a1 + 56) = 0;
      *(_DWORD *)(a1 + 164) = 0;
      v20 = (*(__int64 (__fastcall **)(struct IDeviceModel *))(*(_QWORD *)a2 + 24LL))(a2);
      v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a6 + 24LL))(a6);
      v37 = v21;
      for ( i = 0; (unsigned int)i < v20; i = (unsigned int)(i + 1) )
      {
        if ( a8[i + 1] == 7 )
        {
          if ( *(_DWORD *)(a1 + 56) )
            return (unsigned int)-2147467263;
          *(_DWORD *)(a1 + 56) = 1;
          *(_DWORD *)(a1 + 60) = i;
        }
      }
      for ( j = 0; (unsigned int)j < v21; j = (unsigned int)(j + 1) )
      {
        if ( *(_DWORD *)(a9 + 4 * j + 4) == 7 )
        {
          if ( *(_DWORD *)(a1 + 168) )
            return (unsigned int)-2147467263;
          *(_DWORD *)(a1 + 168) = 1;
        }
      }
      *(_DWORD *)(a1 + 164) = *a8;
      v36 = (*(__int64 (__fastcall **)(struct IDeviceModel *))(*(_QWORD *)a2 + 56LL))(a2);
      v24 = 0;
      v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a6 + 56LL))(a6);
      for ( k = 0; (unsigned int)k < *(_DWORD *)a4; k = (unsigned int)(k + 1) )
      {
        v26 = *(_QWORD *)(*(_QWORD *)(a4 + 8) + 8 * k);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v26 + 40LL))(v26) )
        {
          v24 = 1;
          break;
        }
      }
      v34 = 0;
      if ( (unsigned int)a12 <= 1 )
        NonEnhancedDestinationTranslator = ColorTranslationSequence::CreateNonEnhancedDestinationTranslator(
                                             a12 != 0,
                                             v20,
                                             *(_DWORD *)(a1 + 56),
                                             *(_DWORD *)(a1 + 168),
                                             v36,
                                             v24,
                                             v35,
                                             (struct ColorDestinationTranslation **)(a1 + 176),
                                             (enum TransformOptimizationType::Enum *)&v34);
      else
        NonEnhancedDestinationTranslator = ColorTranslationSequence::CreateEnhancedDestinationTranslator(
                                             v20,
                                             v42[0],
                                             v39,
                                             v38,
                                             *(_DWORD *)(a1 + 56),
                                             *(_DWORD *)(a1 + 168),
                                             v36,
                                             v24,
                                             v35,
                                             (struct ColorDestinationTranslation **)(a1 + 176),
                                             (enum TransformOptimizationType::Enum *)&v34);
      v19 = NonEnhancedDestinationTranslator;
      if ( NonEnhancedDestinationTranslator >= 0 )
      {
        v42[0] = (struct IGamutBoundaryDescription *)&v34;
        v42[1] = (struct IGamutBoundaryDescription *)4;
        EtwEventWrite(g_etwHandle, TRANSFORM_OPTIMIZATION, 1, v42);
        v19 = ColorDestinationTranslation::Initialize(
                *(_QWORD *)(a1 + 176),
                a13,
                v34,
                a4,
                v41,
                v40,
                a7,
                a9,
                LODWORD(a10),
                LODWORD(a11));
        if ( v19 >= 0 )
        {
          v28 = 0;
          if ( v20 )
          {
            v29 = 0;
            do
            {
              ++v28;
              *(float *)(a1 + 4 * v29 + 64) = (float)((float)(*(float *)&a8[v29 + 17] - *(float *)&a8[v29 + 9]) * 0.5)
                                            + *(float *)&a8[v29 + 9];
              ++v29;
            }
            while ( v28 < v20 );
          }
          v30 = v37;
          v31 = 0;
          if ( v37 )
          {
            v32 = 0;
            do
            {
              ++v31;
              *(_DWORD *)(a1 + 4 * v32 + 96) = *(_DWORD *)(a9 + 4 * v32 + 36);
              *(_DWORD *)(a1 + 4 * v32 + 128) = *(_DWORD *)(a9 + 4 * v32 + 68);
              ++v32;
            }
            while ( v31 < v30 );
          }
          *(_DWORD *)(a1 + 32) = 1;
        }
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800788d0  mov     rax, rsp
0x1800788d3  push    rbx
0x1800788d4  push    rsi
0x1800788d5  push    rdi
0x1800788d6  push    r12
0x1800788d8  push    r13
0x1800788da  push    r14
0x1800788dc  push    r15
0x1800788de  sub     rsp, 0D0h
0x1800788e5  movaps  xmmword ptr [rax-48h], xmm6
0x1800788e9  movaps  xmmword ptr [rax-58h], xmm7
0x1800788ed  mov     rax, cs:__security_cookie
0x1800788f4  xor     rax, rsp
0x1800788f7  mov     [rsp+108h+var_68], rax
0x1800788ff  mov     r13, [rsp+108h+arg_28]
0x180078907  mov     rbx, rcx
0x18007890a  mov     rcx, [rsp+108h+arg_20]
0x180078912  mov     r15, r9
0x180078915  mov     rax, [rsp+108h+arg_68]
0x18007891d  mov     r12, r8
0x180078920  mov     [rsp+108h+var_98], r8
0x180078925  mov     rsi, rdx
0x180078928  cmp     dword ptr [rbx+20h], 0
0x18007892c  mov     [rsp+108h+var_90], rdx
0x180078931  mov     [rsp+108h+var_80], rcx
0x180078939  mov     [rsp+108h+var_88], r13
0x180078941  mov     [rsp+108h+var_78], rax
0x180078949  jz      short loc_180078955
0x18007894b  mov     ecx, 80004005h
0x180078950  jmp     loc_180078CA1
0x180078955  test    rsi, rsi
0x180078958  jz      loc_180078C9C
0x18007895e  test    r12, r12
0x180078961  jz      loc_180078C9C
0x180078967  test    r15, r15
0x18007896a  jz      loc_180078C9C
0x180078970  test    rcx, rcx
0x180078973  jz      loc_180078C9C
0x180078979  test    r13, r13
0x18007897c  jz      loc_180078C9C
0x180078982  mov     r14, [rsp+108h+arg_38]
0x18007898a  test    r14, r14
0x18007898d  jz      loc_180078C9C
0x180078993  mov     rdi, [rsp+108h+arg_40]
0x18007899b  test    rdi, rdi
0x18007899e  jz      loc_180078C9C
0x1800789a4  movss   xmm6, [rsp+108h+arg_48]
0x1800789ad  movss   xmm7, [rsp+108h+arg_50]
0x1800789b6  comiss  xmm6, xmm7
0x1800789b9  jnb     loc_180078C9C
0x1800789bf  test    rax, rax
0x1800789c2  jnz     short loc_1800789D2
0x1800789c4  cmp     [rsp+108h+arg_58], 2
0x1800789cc  jz      loc_180078C9C
0x1800789d2  cmp     [rsp+108h+arg_58], 3
0x1800789da  jge     loc_180078C9C
0x1800789e0  cmp     dword ptr [r9], 1
0x1800789e4  jb      loc_180078C9C
0x1800789ea  lea     rcx, [rbx+10h]
0x1800789ee  call    ??4?$TRefSmartPtr@VCGamutBoundaryDescription@@@NCoreLibrary@@QEAAAEAV01@PEAVCGamutBoundaryDescription@@@Z; NCoreLibrary::TRefSmartPtr<CGamutBoundaryDescription>::operator=(CGamutBoundaryDescription *)
0x1800789f3  lea     rcx, [rbx+18h]
0x1800789f7  mov     rdx, r12
0x1800789fa  call    ??4?$TRefSmartPtr@VCGamutBoundaryDescription@@@NCoreLibrary@@QEAAAEAV01@PEAVCGamutBoundaryDescription@@@Z; NCoreLibrary::TRefSmartPtr<CGamutBoundaryDescription>::operator=(CGamutBoundaryDescription *)
0x1800789ff  mov     eax, [rsp+108h+arg_30]
0x180078a06  mov     rcx, rsi
0x180078a09  mov     [rbx+0A0h], eax
0x180078a0f  mov     dword ptr [rbx+38h], 0
0x180078a16  mov     dword ptr [rbx+0A4h], 0
0x180078a20  mov     rax, [rsi]
0x180078a23  mov     rax, [rax+18h]
0x180078a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a2c  mov     r12d, eax
0x180078a2f  mov     rcx, r13
0x180078a32  mov     rax, [r13+0]
0x180078a36  mov     rax, [rax+18h]
0x180078a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a3f  mov     [rsp+108h+var_9C], eax
0x180078a43  xor     ecx, ecx
0x180078a45  cmp     ecx, r12d
0x180078a48  jnb     short loc_180078A70
0x180078a4a  cmp     dword ptr [r14+rcx*4+4], 7
0x180078a50  jnz     short loc_180078A62
0x180078a52  cmp     dword ptr [rbx+38h], 0
0x180078a56  jnz     short loc_180078A66
0x180078a58  mov     dword ptr [rbx+38h], 1
0x180078a5f  mov     [rbx+3Ch], ecx
0x180078a62  inc     ecx
0x180078a64  jmp     short loc_180078A45
0x180078a66  mov     ecx, 80004001h
0x180078a6b  jmp     loc_180078CA1
0x180078a70  xor     ecx, ecx
0x180078a72  cmp     ecx, eax
0x180078a74  jnb     short loc_180078A94
0x180078a76  cmp     dword ptr [rdi+rcx*4+4], 7
0x180078a7b  jnz     short loc_180078A90
0x180078a7d  cmp     dword ptr [rbx+0A8h], 0
0x180078a84  jnz     short loc_180078A66
0x180078a86  mov     dword ptr [rbx+0A8h], 1
0x180078a90  inc     ecx
0x180078a92  jmp     short loc_180078A72
0x180078a94  mov     eax, [r14]
0x180078a97  mov     rcx, rsi
0x180078a9a  mov     [rbx+0A4h], eax
0x180078aa0  mov     rax, [rsi]
0x180078aa3  mov     rax, [rax+38h]
0x180078aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078aac  mov     [rsp+108h+var_A0], eax
0x180078ab0  mov     rcx, r13
0x180078ab3  mov     rax, [r13+0]
0x180078ab7  mov     rax, [rax+38h]
0x180078abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ac0  xor     r13d, r13d
0x180078ac3  mov     [rsp+108h+var_A4], eax
0x180078ac7  xor     esi, esi
0x180078ac9  cmp     esi, [r15]
0x180078acc  jnb     short loc_180078AF0
0x180078ace  mov     rax, [r15+8]
0x180078ad2  mov     rcx, [rax+rsi*8]
0x180078ad6  mov     rax, [rcx]
0x180078ad9  mov     rax, [rax+28h]
0x180078add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ae2  test    eax, eax
0x180078ae4  jnz     short loc_180078AEA
0x180078ae6  inc     esi
0x180078ae8  jmp     short loc_180078AC9
0x180078aea  mov     r13d, 1
0x180078af0  cmp     [rsp+108h+arg_58], 1
0x180078af8  lea     rsi, [rbx+0B0h]
0x180078aff  mov     [rsp+108h+var_A8], 0
0x180078b07  lea     rax, [rsp+108h+var_A8]
0x180078b0c  jbe     short loc_180078B5A
0x180078b0e  mov     r9, [rsp+108h+var_98]; struct IColorAppearanceModel *
0x180078b13  mov     ecx, r12d; unsigned int
0x180078b16  mov     r8, [rsp+108h+var_90]; struct IDeviceModel *
0x180078b1b  mov     rdx, [rsp+108h+var_78]; struct IGamutBoundaryDescription *
0x180078b23  mov     [rsp+108h+var_B8], rax; enum TransformOptimizationType::Enum *
0x180078b28  mov     eax, [rsp+108h+var_A4]
0x180078b2c  mov     [rsp+108h+var_C0], rsi; struct ColorDestinationTranslation **
0x180078b31  mov     dword ptr [rsp+108h+var_C8], eax; int
0x180078b35  mov     eax, [rsp+108h+var_A0]
0x180078b39  mov     dword ptr [rsp+108h+var_D0], r13d; int
0x180078b3e  mov     [rsp+108h+var_D8], eax; int
0x180078b42  mov     eax, [rbx+0A8h]
0x180078b48  mov     [rsp+108h+var_E0], eax; int
0x180078b4c  mov     eax, [rbx+38h]
0x180078b4f  mov     [rsp+108h+var_E8], eax; int
0x180078b53  call    ?CreateEnhancedDestinationTranslator@ColorTranslationSequence@@CAJIPEAVIGamutBoundaryDescription@@PEAVIDeviceModel@@PEAVIColorAppearanceModel@@HHHHHPEAPEAVColorDestinationTranslation@@PEAW4Enum@TransformOptimizationType@@@Z; ColorTranslationSequence::CreateEnhancedDestinationTranslator(uint,IGamutBoundaryDescription *,IDeviceModel *,IColorAppearanceModel *,int,int,int,int,int,ColorDestinationTranslation * *,TransformOptimizationType::Enum *)
0x180078b58  jmp     short loc_180078B98
0x180078b5a  mov     r9d, [rbx+0A8h]; int
0x180078b61  xor     ecx, ecx
0x180078b63  cmp     [rsp+108h+arg_58], ecx
0x180078b6a  mov     edx, r12d; unsigned int
0x180078b6d  mov     r8d, [rbx+38h]; int
0x180078b71  mov     [rsp+108h+var_C8], rax; enum TransformOptimizationType::Enum *
0x180078b76  setnz   cl; int
0x180078b79  mov     eax, [rsp+108h+var_A4]
0x180078b7d  mov     [rsp+108h+var_D0], rsi; struct ColorDestinationTranslation **
0x180078b82  mov     [rsp+108h+var_D8], eax; int
0x180078b86  mov     eax, [rsp+108h+var_A0]
0x180078b8a  mov     [rsp+108h+var_E0], r13d; int
0x180078b8f  mov     [rsp+108h+var_E8], eax; int
0x180078b93  call    ?CreateNonEnhancedDestinationTranslator@ColorTranslationSequence@@CAJHIHHHHHPEAPEAVColorDestinationTranslation@@PEAW4Enum@TransformOptimizationType@@@Z; ColorTranslationSequence::CreateNonEnhancedDestinationTranslator(int,uint,int,int,int,int,int,ColorDestinationTranslation * *,TransformOptimizationType::Enum *)
0x180078b98  mov     ecx, eax
0x180078b9a  test    eax, eax
0x180078b9c  js      loc_180078CA1
0x180078ba2  mov     rcx, cs:g_etwHandle
0x180078ba9  lea     rax, [rsp+108h+var_A8]
0x180078bae  lea     r9, [rsp+108h+var_78]
0x180078bb6  mov     [rsp+108h+var_78], rax
0x180078bbe  mov     r8d, 1
0x180078bc4  mov     [rsp+108h+var_70], 4
0x180078bd0  lea     rdx, TRANSFORM_OPTIMIZATION
0x180078bd7  call    cs:__imp_EtwEventWrite
0x180078bdd  mov     eax, [rsp+108h+arg_30]
0x180078be4  mov     r9, r15
0x180078be7  mov     r8d, [rsp+108h+var_A8]
0x180078bec  mov     edx, [rsp+108h+arg_60]
0x180078bf3  mov     rcx, [rsi]
0x180078bf6  movss   dword ptr [rsp+108h+var_C0], xmm7
0x180078bfc  movss   dword ptr [rsp+108h+var_C8], xmm6
0x180078c02  mov     [rsp+108h+var_D0], rdi
0x180078c07  mov     [rsp+108h+var_D8], eax
0x180078c0b  mov     rax, [rsp+108h+var_88]
0x180078c13  mov     qword ptr [rsp+108h+var_E0], rax
0x180078c18  mov     rax, [rsp+108h+var_80]
0x180078c20  mov     qword ptr [rsp+108h+var_E8], rax
0x180078c25  call    ?Initialize@ColorDestinationTranslation@@QEAAJW4Enum@QualityMode@@W42TransformOptimizationType@@PEAU?$CITEArray@PEAVIGamutMapModel@@@@PEAVIColorAppearanceModel@@PEAVIDeviceModel@@HPEAUColorChannelInfo@@MM@Z; ColorDestinationTranslation::Initialize(QualityMode::Enum,TransformOptimizationType::Enum,CITEArray<IGamutMapModel *> *,IColorAppearanceModel *,IDeviceModel *,int,ColorChannelInfo *,float,float)
0x180078c2a  mov     ecx, eax
0x180078c2c  test    eax, eax
0x180078c2e  js      short loc_180078CA1
0x180078c30  xor     edx, edx
0x180078c32  test    r12d, r12d
0x180078c35  jz      short loc_180078C66
0x180078c37  xor     eax, eax
0x180078c39  movss   xmm0, dword ptr [r14+rax*4+44h]
0x180078c40  inc     edx
0x180078c42  subss   xmm0, dword ptr [r14+rax*4+24h]
0x180078c49  mulss   xmm0, cs:__real@3f000000
0x180078c51  addss   xmm0, dword ptr [r14+rax*4+24h]
0x180078c58  movss   dword ptr [rbx+rax*4+40h], xmm0
0x180078c5e  inc     rax
0x180078c61  cmp     edx, r12d
0x180078c64  jb      short loc_180078C39
0x180078c66  mov     r9d, [rsp+108h+var_9C]
0x180078c6b  xor     r8d, r8d
0x180078c6e  test    r9d, r9d
0x180078c71  jz      short loc_180078C93
0x180078c73  xor     edx, edx
0x180078c75  mov     eax, [rdi+rdx*4+24h]
0x180078c79  inc     r8d
0x180078c7c  mov     [rbx+rdx*4+60h], eax
0x180078c80  mov     eax, [rdi+rdx*4+44h]
0x180078c84  mov     [rbx+rdx*4+80h], eax
0x180078c8b  inc     rdx
0x180078c8e  cmp     r8d, r9d
0x180078c91  jb      short loc_180078C75
0x180078c93  mov     dword ptr [rbx+20h], 1
0x180078c9a  jmp     short loc_180078CA1
0x180078c9c  mov     ecx, 80070057h
0x180078ca1  mov     eax, ecx
0x180078ca3  mov     rcx, [rsp+108h+var_68]
0x180078cab  xor     rcx, rsp; StackCookie
0x180078cae  call    __security_check_cookie
0x180078cb3  lea     r11, [rsp+108h+var_38]
0x180078cbb  movaps  xmm6, xmmword ptr [r11-10h]
0x180078cc0  movaps  xmm7, xmmword ptr [r11-20h]
0x180078cc5  mov     rsp, r11
0x180078cc8  pop     r15
0x180078cca  pop     r14
0x180078ccc  pop     r13
0x180078cce  pop     r12
0x180078cd0  pop     rdi
0x180078cd1  pop     rsi
0x180078cd2  pop     rbx
0x180078cd3  retn
```
