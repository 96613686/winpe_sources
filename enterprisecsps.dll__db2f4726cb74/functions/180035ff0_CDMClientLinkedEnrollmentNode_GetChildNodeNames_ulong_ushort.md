# CDMClientLinkedEnrollmentNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180035ff0`
- end: `0x1800361f6`
- name: `?GetChildNodeNames@CDMClientLinkedEnrollmentNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `518`
- prototype: `__int64 __fastcall(CDMClientLinkedEnrollmentNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009cc4`
- `0x180015e90`
- `0x18002f3c0`
- `0x180035ff0`
- `0x1800386c4`
- `0x1800397e0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003612c`
- `OLEAUT32!__imp_SysAllocString` at `0x18003612c`
- `OLEAUT32!__imp_SysFreeString` at `0x180036173`
- `OLEAUT32!__imp_SysFreeString` at `0x180036173`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800360e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800360e7`

## string_xrefs

- `0x1800361b5`: `CDMClientLinkedEnrollmentNode::GetChildNodeNames`

## pseudocode

```c
__int64 __fastcall CDMClientLinkedEnrollmentNode::GetChildNodeNames(
        CDMClientLinkedEnrollmentNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  unsigned int *v4; // r12
  int v6; // r9d
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ebx
  unsigned int v14; // r14d
  __int64 i; // rcx
  unsigned int v16; // eax
  size_t v17; // rsi
  unsigned __int16 **v18; // rax
  unsigned __int16 **v19; // rdi
  __int64 v20; // rsi
  __int64 v21; // r15
  const OLECHAR *v22; // rcx
  BSTR v23; // rax
  __int64 j; // rsi
  OLECHAR *v25; // rcx
  int v27; // [rsp+20h] [rbp-30h] BYREF
  __int64 v28; // [rsp+28h] [rbp-28h] BYREF
  _QWORD v29[2]; // [rsp+30h] [rbp-20h] BYREF
  char v30; // [rsp+40h] [rbp-10h]
  SIZE_T cb; // [rsp+A8h] [rbp+58h] BYREF

  v27 = 0;
  v4 = a2;
  v28 = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_Desktop>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_MMPC_Desktop>::GetImpl'::`2'::impl,
    a2);
  if ( !v4 || !a3 )
    return 2147942487LL;
  v7 = *((_DWORD *)this + 11);
  v29[0] = &v28;
  v29[1] = &v27;
  v8 = v7 - 79;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 && (v10 = v9 - 1) != 0 && (v11 = v10 - 2) != 0 && (v12 = v11 - 1) != 0 && (unsigned int)(v12 - 10) >= 2 )
      v13 = -2147418113;
    else
      v13 = -2046820335;
  }
  else
  {
    v14 = 0;
    *a3 = 0;
    LODWORD(cb) = 0;
    *v4 = 0;
    v28 = 0;
    for ( i = 0; i != 6; ++i )
    {
      v16 = v14 + 1;
      if ( !(&c_rgLinkedEnrollmentNodes)[i] )
        v16 = v14;
      v14 = v16;
    }
    v13 = ULongLongToULong(8LL * v16, (unsigned int *)&cb);
    if ( v13 >= 0 )
    {
      v17 = (unsigned int)cb;
      v18 = (unsigned __int16 **)CoTaskMemAlloc((unsigned int)cb);
      v19 = v18;
      if ( v18 )
      {
        memset_0(v18, 0, v17);
        v20 = 0;
        v21 = 0;
        while ( (unsigned int)v20 < v14 )
        {
          v22 = (const OLECHAR *)(&c_rgLinkedEnrollmentNodes)[v21];
          if ( v22 )
          {
            v23 = SysAllocString(v22);
            v19[v20] = v23;
            if ( !v23 )
            {
              v13 = -2147024882;
              goto LABEL_28;
            }
            v20 = (unsigned int)(v20 + 1);
          }
          v21 = (unsigned int)(v21 + 1);
          if ( (int)v21 >= 6 )
          {
            if ( (_DWORD)v20 == v14 )
            {
              *v4 = v20;
              *a3 = v19;
              v28 = 0;
              goto LABEL_35;
            }
            break;
          }
        }
        v13 = -2147418113;
LABEL_28:
        for ( j = 0; (unsigned int)j < v14; j = (unsigned int)(j + 1) )
        {
          v25 = v19[j];
          if ( v25 )
          {
            SysFreeString(v25);
            v19[j] = 0;
          }
        }
        CoTaskMemFree(v19);
      }
      else
      {
        v13 = -2147024882;
      }
    }
  }
LABEL_35:
  DmClientLogging::Write(L"CDMClientLinkedEnrollmentNode::GetChildNodeNames", *((_DWORD *)this + 11), v13, v6);
  v30 = 0;
  lambda_4997a9584601948fbcd5a72b97f6ebe0_::operator()(v29);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180035ff0  mov     [rsp-38h+arg_8], rbx
0x180035ff5  mov     [rsp-38h+arg_0], rcx
0x180035ffa  push    rbp
0x180035ffb  push    rsi
0x180035ffc  push    rdi
0x180035ffd  push    r12
0x180035fff  push    r13
0x180036001  push    r14
0x180036003  push    r15
0x180036005  mov     rbp, rsp
0x180036008  sub     rsp, 50h
0x18003600c  mov     r13, r8
0x18003600f  mov     [rbp+var_30], 0
0x180036016  mov     r12, rdx
0x180036019  mov     [rbp+var_28], 0
0x180036021  mov     rbx, rcx
0x180036024  mov     dl, 1
0x180036026  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MMPC_Desktop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MMPC_Desktop@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_Desktop> `wil::Feature<__WilFeatureTraits_Feature_MMPC_Desktop>::GetImpl(void)'::`2'::impl
0x18003602d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_MMPC_Desktop@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_Desktop>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180036032  test    r12, r12
0x180036035  jz      loc_1800361D8
0x18003603b  test    r13, r13
0x18003603e  jz      loc_1800361D8
0x180036044  mov     ecx, [rbx+2Ch]
0x180036047  lea     rax, [rbp+var_28]
0x18003604b  mov     [rbp+var_20], rax
0x18003604f  lea     rax, [rbp+var_30]
0x180036053  mov     [rbp+var_18], rax
0x180036057  sub     ecx, 4Fh ; 'O'
0x18003605a  jz      short loc_18003608E
0x18003605c  sub     ecx, 1
0x18003605f  jz      short loc_180036084
0x180036061  sub     ecx, 1
0x180036064  jz      short loc_180036084
0x180036066  sub     ecx, 2
0x180036069  jz      short loc_180036084
0x18003606b  sub     ecx, 1
0x18003606e  jz      short loc_180036084
0x180036070  sub     ecx, 0Ah
0x180036073  jz      short loc_180036084
0x180036075  cmp     ecx, 1
0x180036078  jz      short loc_180036084
0x18003607a  mov     ebx, 8000FFFFh
0x18003607f  jmp     loc_1800361B1
0x180036084  mov     ebx, 86000011h
0x180036089  jmp     loc_1800361B1
0x18003608e  xor     r14d, r14d
0x180036091  mov     qword ptr [r13+0], 0
0x180036099  xor     edi, edi
0x18003609b  mov     dword ptr [rbp+cb], r14d
0x18003609f  mov     [r12], r14d
0x1800360a3  lea     rdx, ?c_rgLinkedEnrollmentNodes@@3PAPEBGA; ushort const * near * c_rgLinkedEnrollmentNodes
0x1800360aa  mov     [rbp+var_28], rdi
0x1800360ae  xor     ecx, ecx
0x1800360b0  cmp     [rdx+rcx*8], rdi
0x1800360b4  lea     eax, [r14+1]
0x1800360b8  cmovz   eax, r14d
0x1800360bc  inc     rcx
0x1800360bf  mov     r14d, eax
0x1800360c2  cmp     rcx, 6
0x1800360c6  jnz     short loc_1800360B0
0x1800360c8  mov     ecx, r14d
0x1800360cb  lea     rdx, [rbp+cb]; unsigned int *
0x1800360cf  shl     rcx, 3; unsigned __int64
0x1800360d3  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800360d8  mov     ebx, eax
0x1800360da  test    eax, eax
0x1800360dc  js      loc_1800361A1
0x1800360e2  mov     esi, dword ptr [rbp+cb]
0x1800360e5  mov     ecx, esi; cb
0x1800360e7  call    cs:__imp_CoTaskMemAlloc
0x1800360ee  nop     dword ptr [rax+rax+00h]
0x1800360f3  mov     rdi, rax
0x1800360f6  test    rax, rax
0x1800360f9  jnz     short loc_180036105
0x1800360fb  mov     ebx, 8007000Eh
0x180036100  jmp     loc_1800361B1
0x180036105  mov     r8, rsi; Size
0x180036108  xor     edx, edx; Val
0x18003610a  mov     rcx, rdi; void *
0x18003610d  call    memset_0
0x180036112  xor     esi, esi
0x180036114  xor     r15d, r15d
0x180036117  cmp     esi, r14d
0x18003611a  jnb     short loc_18003615E
0x18003611c  lea     rcx, ?c_rgLinkedEnrollmentNodes@@3PAPEBGA; ushort const * near * c_rgLinkedEnrollmentNodes
0x180036123  mov     rcx, [rcx+r15*8]; psz
0x180036127  test    rcx, rcx
0x18003612a  jz      short loc_180036143
0x18003612c  call    cs:__imp_SysAllocString
0x180036133  nop     dword ptr [rax+rax+00h]
0x180036138  mov     [rdi+rsi*8], rax
0x18003613c  test    rax, rax
0x18003613f  jz      short loc_180036157
0x180036141  inc     esi
0x180036143  inc     r15d
0x180036146  cmp     r15d, 6
0x18003614a  jl      short loc_180036117
0x18003614c  cmp     esi, r14d
0x18003614f  jnz     short loc_18003615E
0x180036151  mov     [r12], esi
0x180036155  jmp     short loc_1800361A5
0x180036157  mov     ebx, 8007000Eh
0x18003615c  jmp     short loc_180036163
0x18003615e  mov     ebx, 8000FFFFh
0x180036163  xor     esi, esi
0x180036165  test    r14d, r14d
0x180036168  jz      short loc_18003618E
0x18003616a  mov     rcx, [rdi+rsi*8]; bstrString
0x18003616e  test    rcx, rcx
0x180036171  jz      short loc_180036187
0x180036173  call    cs:__imp_SysFreeString
0x18003617a  nop     dword ptr [rax+rax+00h]
0x18003617f  mov     qword ptr [rdi+rsi*8], 0
0x180036187  inc     esi
0x180036189  cmp     esi, r14d
0x18003618c  jb      short loc_18003616A
0x18003618e  mov     rcx, rdi; pv
0x180036191  call    cs:__imp_CoTaskMemFree
0x180036198  nop     dword ptr [rax+rax+00h]
0x18003619d  mov     rdi, [rbp+var_28]
0x1800361a1  test    ebx, ebx
0x1800361a3  js      short loc_1800361B1
0x1800361a5  mov     [r13+0], rdi
0x1800361a9  mov     [rbp+var_28], 0
0x1800361b1  mov     rdx, [rbp+arg_0]
0x1800361b5  lea     rcx, aCdmclientlinke_1; "CDMClientLinkedEnrollmentNode::GetChild"...
0x1800361bc  mov     r8d, ebx; int
0x1800361bf  mov     edx, [rdx+2Ch]; unsigned int
0x1800361c2  call    ?Write@DmClientLogging@@SAXPEBGKJH@Z; DmClientLogging::Write(ushort const *,ulong,long,int)
0x1800361c7  lea     rcx, [rbp+var_20]
0x1800361cb  mov     [rbp+var_10], 0
0x1800361cf  call    _lambda_4997a9584601948fbcd5a72b97f6ebe0___operator__
0x1800361d4  mov     eax, ebx
0x1800361d6  jmp     short loc_1800361DD
0x1800361d8  mov     eax, 80070057h
0x1800361dd  mov     rbx, [rsp+50h+arg_8]
0x1800361e5  add     rsp, 50h
0x1800361e9  pop     r15
0x1800361eb  pop     r14
0x1800361ed  pop     r13
0x1800361ef  pop     r12
0x1800361f1  pop     rdi
0x1800361f2  pop     rsi
0x1800361f3  pop     rbp
0x1800361f4  retn
```
