# ToneResponseCurvesProcessor::ProcessElement(IXMLDOMNode *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,HDRToneResponseCurves *)

- ea: `0x18005ad2c`
- end: `0x18005afac`
- name: `?ProcessElement@ToneResponseCurvesProcessor@@SAJPEAUIXMLDOMNode@@PEBG1111PEAUHDRToneResponseCurves@@@Z`
- size: `640`
- prototype: `__int64 __usercall@<rax>(struct IXMLDOMNode *this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, struct HDRToneResponseCurves *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180058904`
- `0x18005ace4`

## callees

- `0x18002b98c`
- `0x18002e614`
- `0x18002eab4`
- `0x180059ce4`
- `0x180059e04`
- `0x18005ad2c`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18005ad66`
- `OLEAUT32!__imp_VariantInit` at `0x18005ad66`

## pseudocode

```c
__int64 __fastcall ToneResponseCurvesProcessor::ProcessElement(
        struct IXMLDOMNode *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        struct HDRToneResponseCurves *a7)
{
  ProcessSimpleTypeElement *v7; // r12
  int RequiredAttributeValue; // ebx
  bool v12; // cc
  __int64 v13; // r14
  const unsigned __int16 *v14; // rdx
  void *v15; // rax
  unsigned __int64 v16; // rcx
  void *v17; // rax
  struct IXMLDOMNode *v18; // r15
  struct IXMLDOMNode *v19; // rsi
  int RequiredDOMNode; // eax
  float *v21; // r9
  struct IXMLDOMNode *v22; // r12
  int v23; // eax
  float *v24; // r9
  __int64 v25; // r8
  __int64 v26; // rcx
  struct IXMLDOMNode *v28; // [rsp+20h] [rbp-91h] BYREF
  struct IXMLDOMNode *v29; // [rsp+28h] [rbp-89h] BYREF
  struct IXMLDOMNode *v30; // [rsp+30h] [rbp-81h] BYREF
  unsigned int v31[2]; // [rsp+38h] [rbp-79h]
  unsigned int v32[2]; // [rsp+40h] [rbp-71h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-69h] BYREF
  unsigned __int16 *v34[3]; // [rsp+60h] [rbp-51h]
  _QWORD v35[15]; // [rsp+78h] [rbp-39h]

  v7 = (ProcessSimpleTypeElement *)this;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  *(_OWORD *)a7 = 0;
  *((_OWORD *)a7 + 1) = 0;
  *((_OWORD *)a7 + 2) = 0;
  *((_QWORD *)a7 + 6) = 0;
  RequiredAttributeValue = ProcessSimpleTypeElement::GetRequiredAttributeValue(
                             v7,
                             (struct IXMLDOMNode *)&stru_18008E538,
                             (const unsigned __int16 *)0x13,
                             (unsigned __int16)&pvarg,
                             (struct tagVARIANT *)v28);
  if ( RequiredAttributeValue >= 0 )
  {
    v12 = pvarg.lVal <= 0x3FFFFFFFu;
    *(_DWORD *)a7 = pvarg.lVal;
    if ( !v12 )
      RequiredAttributeValue = -2147022885;
    if ( RequiredAttributeValue >= 0 )
    {
      v34[1] = a3;
      v35[1] = (char *)a7 + 16;
      v34[2] = a4;
      v35[2] = (char *)a7 + 24;
      v13 = 0;
      v34[0] = a2;
      v35[3] = (char *)a7 + 32;
      v35[0] = (char *)a7 + 8;
      v35[4] = (char *)a7 + 40;
      v35[5] = (char *)a7 + 48;
      while ( 1 )
      {
        v14 = v34[v13];
        v29 = 0;
        RequiredAttributeValue = FindRequiredDOMNode((struct IXMLDOMNode *)v7, v14, &v29);
        if ( RequiredAttributeValue < 0 )
          break;
        v15 = operator new[](saturated_mul(*(unsigned int *)a7, 4u));
        v16 = *(unsigned int *)a7;
        *(_QWORD *)v31 = v15;
        v17 = operator new[](saturated_mul(v16, 4u));
        v18 = v29;
        v19 = 0;
        *(_QWORD *)v32 = v17;
        v30 = 0;
        v28 = 0;
        RequiredDOMNode = FindRequiredDOMNode(v29, a5, &v30);
        v22 = v30;
        RequiredAttributeValue = RequiredDOMNode;
        if ( RequiredDOMNode >= 0 )
        {
          RequiredAttributeValue = ProcessSimpleTypeElement::GetFloatsFromNodeValue(
                                     (ProcessSimpleTypeElement *)v30,
                                     (struct IXMLDOMNode *)*(unsigned int *)a7,
                                     v31[0],
                                     v21);
          if ( RequiredAttributeValue >= 0 )
          {
            v23 = FindRequiredDOMNode(v18, a6, &v28);
            v19 = v28;
            RequiredAttributeValue = v23;
            if ( v23 >= 0 )
              RequiredAttributeValue = ProcessSimpleTypeElement::GetFloatsFromNodeValue(
                                         (ProcessSimpleTypeElement *)v28,
                                         (struct IXMLDOMNode *)*(unsigned int *)a7,
                                         v32[0],
                                         v24);
          }
        }
        if ( v22 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v22->lpVtbl->Release)(v22);
        if ( v19 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
        if ( RequiredAttributeValue >= 0 )
        {
          v25 = (unsigned int)(2 * v13);
          v26 = *(_QWORD *)v32;
          *(_QWORD *)v35[v25] = *(_QWORD *)v31;
          *(_QWORD *)v35[(unsigned int)(v25 + 1)] = v26;
        }
        if ( v18 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v18->lpVtbl->Release)(v18);
        if ( RequiredAttributeValue < 0 )
          break;
        v7 = (ProcessSimpleTypeElement *)this;
        v13 = (unsigned int)(v13 + 1);
        if ( (unsigned int)v13 >= 3 )
          return (unsigned int)RequiredAttributeValue;
      }
      operator delete(*((void **)a7 + 1));
      operator delete(*((void **)a7 + 2));
      operator delete(*((void **)a7 + 3));
      operator delete(*((void **)a7 + 4));
      operator delete(*((void **)a7 + 5));
      operator delete(*((void **)a7 + 6));
      *(_OWORD *)a7 = 0;
      *((_OWORD *)a7 + 1) = 0;
      *((_OWORD *)a7 + 2) = 0;
      *((_QWORD *)a7 + 6) = 0;
    }
  }
  return (unsigned int)RequiredAttributeValue;
}

```

## disassembly

```asm
0x18005ad2c  mov     [rsp-8+arg_0], rcx
0x18005ad31  push    rbp
0x18005ad32  push    rbx
0x18005ad33  push    rsi
0x18005ad34  push    rdi
0x18005ad35  push    r12
0x18005ad37  push    r13
0x18005ad39  push    r14
0x18005ad3b  push    r15
0x18005ad3d  lea     rbp, [rsp-7]
0x18005ad42  sub     rsp, 0B8h
0x18005ad49  mov     r12, rcx
0x18005ad4c  xorps   xmm0, xmm0
0x18005ad4f  xor     eax, eax
0x18005ad51  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x18005ad55  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x18005ad59  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x18005ad5d  mov     rsi, r9
0x18005ad60  mov     r14, r8
0x18005ad63  mov     r15, rdx
0x18005ad66  call    cs:__imp_VariantInit
0x18005ad6c  mov     rdi, [rbp+3Fh+arg_30]
0x18005ad70  lea     r9, [rbp+3Fh+pvarg]; unsigned __int16
0x18005ad74  xorps   xmm0, xmm0
0x18005ad77  lea     rdx, stru_18008E538; struct IXMLDOMNode *
0x18005ad7e  xor     eax, eax
0x18005ad80  mov     rcx, r12; this
0x18005ad83  movups  xmmword ptr [rdi], xmm0
0x18005ad86  movups  xmmword ptr [rdi+10h], xmm0
0x18005ad8a  lea     r8d, [rax+13h]; unsigned __int16 *
0x18005ad8e  movups  xmmword ptr [rdi+20h], xmm0
0x18005ad92  mov     [rdi+30h], rax
0x18005ad96  call    ?GetRequiredAttributeValue@ProcessSimpleTypeElement@@YAJPEAUIXMLDOMNode@@PEBGGPEAUtagVARIANT@@@Z; ProcessSimpleTypeElement::GetRequiredAttributeValue(IXMLDOMNode *,ushort const *,ushort,tagVARIANT *)
0x18005ad9b  mov     ebx, eax
0x18005ad9d  test    eax, eax
0x18005ad9f  js      loc_18005AF96
0x18005ada5  mov     ecx, dword ptr [rbp+3Fh+pvarg+8]
0x18005ada8  mov     eax, 800707DBh
0x18005adad  cmp     ecx, 3FFFFFFFh
0x18005adb3  mov     [rdi], ecx
0x18005adb5  cmova   ebx, eax
0x18005adb8  test    ebx, ebx
0x18005adba  js      loc_18005AF96
0x18005adc0  lea     rax, [rdi+10h]
0x18005adc4  mov     [rbp+3Fh+var_88], r14
0x18005adc8  mov     [rbp+3Fh+var_70], rax
0x18005adcc  lea     r13, [rdi+8]
0x18005add0  lea     rax, [rdi+18h]
0x18005add4  mov     [rbp+3Fh+var_80], rsi
0x18005add8  mov     [rbp+3Fh+var_68], rax
0x18005addc  xor     r14d, r14d
0x18005addf  lea     rax, [rdi+20h]
0x18005ade3  mov     [rbp+3Fh+var_90], r15
0x18005ade7  mov     [rbp+3Fh+var_60], rax
0x18005adeb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005adef  lea     rax, [rdi+28h]
0x18005adf3  mov     [rbp+3Fh+var_78], r13
0x18005adf7  mov     [rbp+3Fh+var_58], rax
0x18005adfb  lea     rax, [rdi+30h]
0x18005adff  mov     [rbp+3Fh+var_50], rax
0x18005ae03  mov     rdx, [rbp+r14*8+3Fh+var_90]; unsigned __int16 *
0x18005ae08  lea     r8, [rsp+0F0h+var_C8]; struct IXMLDOMNode **
0x18005ae0d  mov     rcx, r12; struct IXMLDOMNode *
0x18005ae10  mov     [rsp+0F0h+var_C8], 0
0x18005ae19  call    ?FindRequiredDOMNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; FindRequiredDOMNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005ae1e  mov     ebx, eax
0x18005ae20  test    eax, eax
0x18005ae22  js      loc_18005AF4C
0x18005ae28  mov     ecx, [rdi]
0x18005ae2a  mov     eax, 4
0x18005ae2f  mul     rcx
0x18005ae32  cmovb   rax, rsi
0x18005ae36  mov     rcx, rax; unsigned __int64
0x18005ae39  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005ae3e  mov     ecx, [rdi]
0x18005ae40  mov     qword ptr [rbp+3Fh+var_B8], rax
0x18005ae44  mov     eax, 4
0x18005ae49  mul     rcx
0x18005ae4c  cmovb   rax, rsi
0x18005ae50  mov     rcx, rax; unsigned __int64
0x18005ae53  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005ae58  mov     r15, [rsp+0F0h+var_C8]
0x18005ae5d  lea     r8, [rsp+0F0h+var_C0]; struct IXMLDOMNode **
0x18005ae62  mov     rdx, [rbp+3Fh+arg_20]; unsigned __int16 *
0x18005ae66  xor     esi, esi
0x18005ae68  mov     rcx, r15; struct IXMLDOMNode *
0x18005ae6b  mov     qword ptr [rbp+3Fh+var_B0], rax
0x18005ae6f  mov     [rsp+0F0h+var_C0], 0
0x18005ae78  mov     [rsp+0F0h+var_D0], rsi
0x18005ae7d  call    ?FindRequiredDOMNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; FindRequiredDOMNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005ae82  mov     r12, [rsp+0F0h+var_C0]
0x18005ae87  mov     ebx, eax
0x18005ae89  test    eax, eax
0x18005ae8b  js      short loc_18005AECD
0x18005ae8d  mov     r8, qword ptr [rbp+3Fh+var_B8]; unsigned int
0x18005ae91  mov     rcx, r12; this
0x18005ae94  mov     edx, [rdi]; struct IXMLDOMNode *
0x18005ae96  call    ?GetFloatsFromNodeValue@ProcessSimpleTypeElement@@YAJPEAUIXMLDOMNode@@IPEAM@Z; ProcessSimpleTypeElement::GetFloatsFromNodeValue(IXMLDOMNode *,uint,float *)
0x18005ae9b  mov     ebx, eax
0x18005ae9d  test    eax, eax
0x18005ae9f  js      short loc_18005AECD
0x18005aea1  mov     rdx, [rbp+3Fh+arg_28]; unsigned __int16 *
0x18005aea5  lea     r8, [rsp+0F0h+var_D0]; struct IXMLDOMNode **
0x18005aeaa  mov     rcx, r15; struct IXMLDOMNode *
0x18005aead  call    ?FindRequiredDOMNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; FindRequiredDOMNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005aeb2  mov     rsi, [rsp+0F0h+var_D0]
0x18005aeb7  mov     ebx, eax
0x18005aeb9  test    eax, eax
0x18005aebb  js      short loc_18005AECD
0x18005aebd  mov     r8, qword ptr [rbp+3Fh+var_B0]; unsigned int
0x18005aec1  mov     rcx, rsi; this
0x18005aec4  mov     edx, [rdi]; struct IXMLDOMNode *
0x18005aec6  call    ?GetFloatsFromNodeValue@ProcessSimpleTypeElement@@YAJPEAUIXMLDOMNode@@IPEAM@Z; ProcessSimpleTypeElement::GetFloatsFromNodeValue(IXMLDOMNode *,uint,float *)
0x18005aecb  mov     ebx, eax
0x18005aecd  test    r12, r12
0x18005aed0  jz      short loc_18005AEE2
0x18005aed2  mov     rax, [r12]
0x18005aed6  mov     rcx, r12
0x18005aed9  mov     rax, [rax+10h]
0x18005aedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aee2  test    rsi, rsi
0x18005aee5  jz      short loc_18005AEF6
0x18005aee7  mov     rax, [rsi]
0x18005aeea  mov     rcx, rsi
0x18005aeed  mov     rax, [rax+10h]
0x18005aef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aef6  test    ebx, ebx
0x18005aef8  js      short loc_18005AF1A
0x18005aefa  mov     rax, qword ptr [rbp+3Fh+var_B8]
0x18005aefe  lea     r8d, [r14+r14]
0x18005af02  mov     rdx, [rbp+r8*8+3Fh+var_78]
0x18005af07  mov     rcx, qword ptr [rbp+3Fh+var_B0]
0x18005af0b  mov     [rdx], rax
0x18005af0e  lea     eax, [r8+1]
0x18005af12  mov     rax, [rbp+rax*8+3Fh+var_78]
0x18005af17  mov     [rax], rcx
0x18005af1a  test    r15, r15
0x18005af1d  jz      short loc_18005AF2E
0x18005af1f  mov     rax, [r15]
0x18005af22  mov     rcx, r15
0x18005af25  mov     rax, [rax+10h]
0x18005af29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af2e  test    ebx, ebx
0x18005af30  js      short loc_18005AF4C
0x18005af32  mov     r12, [rbp+3Fh+arg_0]
0x18005af36  inc     r14d
0x18005af39  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18005af40  cmp     r14d, 3
0x18005af44  jb      loc_18005AE03
0x18005af4a  jmp     short loc_18005AF96
0x18005af4c  mov     rcx, [r13+0]; void *
0x18005af50  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005af55  mov     rcx, [rdi+10h]; void *
0x18005af59  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005af5e  mov     rcx, [rdi+18h]; void *
0x18005af62  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005af67  mov     rcx, [rdi+20h]; void *
0x18005af6b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005af70  mov     rcx, [rdi+28h]; void *
0x18005af74  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005af79  mov     rcx, [rdi+30h]; void *
0x18005af7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005af82  xorps   xmm0, xmm0
0x18005af85  xor     eax, eax
0x18005af87  movups  xmmword ptr [rdi], xmm0
0x18005af8a  movups  xmmword ptr [rdi+10h], xmm0
0x18005af8e  movups  xmmword ptr [rdi+20h], xmm0
0x18005af92  mov     [rdi+30h], rax
0x18005af96  mov     eax, ebx
0x18005af98  add     rsp, 0B8h
0x18005af9f  pop     r15
0x18005afa1  pop     r14
0x18005afa3  pop     r13
0x18005afa5  pop     r12
0x18005afa7  pop     rdi
0x18005afa8  pop     rsi
0x18005afa9  pop     rbx
0x18005afaa  pop     rbp
0x18005afab  retn
```
