# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *)

- ea: `0x1800193f0`
- end: `0x180019643`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBG@Z`
- size: `595`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, XPerf::Internal *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180019b50`

## callees

- `0x180001804`
- `0x180008f10`
- `0x18000958c`
- `0x18000c120`
- `0x18000c3d8`
- `0x180013a4c`
- `0x1800193f0`
- `0x18001964c`
- `0x18001a75c`
- `0x18002389c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800195a5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800195b6`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800195a5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800195b6`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        XPerf::Internal *a2)
{
  void **v4; // r12
  void **v5; // rsi
  union _CVDD *v6; // rax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // ebx
  unsigned int v11; // r15d
  unsigned int v13; // r15d
  bool v14; // bl
  unsigned int v15; // r8d
  const struct _RSDS *v16; // r13
  _BYTE *v17; // rdx
  unsigned __int64 v18; // rcx
  wchar_t *v19; // rbx
  wchar_t *v20; // rax
  unsigned __int16 *v21; // rbx
  int v22; // [rsp+28h] [rbp-28h]
  int v23; // [rsp+28h] [rbp-28h]
  int v24; // [rsp+30h] [rbp-20h]
  int v25; // [rsp+30h] [rbp-20h]
  int v26; // [rsp+38h] [rbp-18h]
  int v27; // [rsp+38h] [rbp-18h]
  int v28; // [rsp+40h] [rbp-10h]
  int v29; // [rsp+40h] [rbp-10h]
  bool v30; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v31; // [rsp+A0h] [rbp+50h]
  unsigned __int16 *v32; // [rsp+A8h] [rbp+58h] BYREF

  v30 = 0;
  v31 = *((_DWORD *)this + 40);
  v4 = (void **)((char *)this + 168);
  if ( !*((_QWORD *)this + 21) )
    return 2147942414LL;
  v5 = (void **)((char *)this + 176);
  v6 = (union _CVDD *)*((_QWORD *)this + 22);
  if ( !v6 )
    return 2147942414LL;
  v7 = CvDbgInfoFromImage(a2, v6, v22, v24, v26, v28, (unsigned int)&v30);
  v10 = v7;
  if ( v7 >= 0 )
    goto LABEL_11;
  if ( v7 != -2146893023 )
  {
LABEL_8:
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v9, v8, a2, (unsigned int)v10);
    return (unsigned int)v10;
  }
  *((_DWORD *)this + 40) = 0;
  operator delete(*v4);
  *v4 = 0;
  operator delete(*v5);
  *v5 = 0;
  v11 = v31;
  if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(v4, v31)
    || !ATL::CAutoVectorPtr<unsigned long>::Allocate(v5, v11) )
  {
    return 2147942414LL;
  }
  *((_DWORD *)this + 40) = v11;
  v10 = CvDbgInfoFromImage(a2, (union _CVDD *)*v5, v23, v25, v27, v29, (unsigned int)&v30);
  if ( v10 < 0 )
    goto LABEL_8;
LABEL_11:
  v13 = 0;
  v14 = v30;
  while ( v13 < v31 )
  {
    v15 = *((_DWORD *)*v5 + v13);
    if ( v15 > 0x18 )
    {
      v16 = (const struct _RSDS *)((char *)*v4 + 1576 * v13);
      if ( *(_DWORD *)v16 == 1396986706 )
      {
        v17 = (char *)v16 + 24;
        if ( v16 != (const struct _RSDS *)-24LL )
        {
          v18 = v15 - 24;
          if ( v18 <= 0x7FFFFFFF )
          {
            do
            {
              if ( !*v17 )
                break;
              ++v17;
              --v18;
            }
            while ( v18 );
            if ( v18
              && (int)Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
                        this,
                        *((const unsigned __int16 **)this + 8),
                        (const unsigned __int16 *)a2,
                        v16,
                        v14) < 0 )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v32);
              v19 = wcsrchr((const wchar_t *)a2, 0x2Fu);
              v20 = wcsrchr((const wchar_t *)a2, 0x5Cu);
              if ( v19 > v20 )
                v20 = v19;
              if ( !v20 )
              {
                ATL::CStringData::Release((ATL::CStringData *)(v32 - 12));
                return 1;
              }
              ATL::CSimpleStringT<unsigned short,0>::SetString(
                &v32,
                a2,
                (unsigned int)(((char *)v20 - (char *)a2) >> 1));
              v21 = v32;
              Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
                this,
                v32,
                (const unsigned __int16 *)a2,
                v16,
                v30);
              ATL::CStringData::Release((ATL::CStringData *)(v21 - 12));
              v14 = v30;
            }
          }
        }
      }
    }
    ++v13;
  }
  return 0;
}

```

## disassembly

```asm
0x1800193f0  mov     [rsp-38h+arg_8], rbx
0x1800193f5  push    rbp
0x1800193f6  push    rsi
0x1800193f7  push    rdi
0x1800193f8  push    r12
0x1800193fa  push    r13
0x1800193fc  push    r14
0x1800193fe  push    r15
0x180019400  mov     rbp, rsp
0x180019403  sub     rsp, 50h
0x180019407  mov     r14, rdx
0x18001940a  mov     rdi, rcx
0x18001940d  xor     r13d, r13d
0x180019410  mov     [rbp+arg_0], r13b
0x180019414  mov     eax, [rcx+0A0h]
0x18001941a  mov     [rbp+arg_10], eax
0x18001941d  lea     r12, [rcx+0A8h]
0x180019424  mov     r9, [r12]
0x180019428  test    r9, r9
0x18001942b  jz      loc_180019626
0x180019431  lea     rsi, [rcx+0B0h]
0x180019438  mov     rax, [rsi]
0x18001943b  test    rax, rax
0x18001943e  jz      loc_180019626
0x180019444  lea     rcx, [rbp+arg_0]
0x180019448  mov     qword ptr [rsp+50h+var_8], rcx; unsigned int
0x18001944d  mov     [rsp+50h+var_30], rax; union _CVDD *
0x180019452  lea     r8, [rbp+arg_10]
0x180019456  mov     rcx, rdx; this
0x180019459  call    CvDbgInfoFromImage
0x18001945e  mov     ebx, eax
0x180019460  test    eax, eax
0x180019462  jns     loc_180019501
0x180019468  cmp     eax, 80090321h
0x18001946d  jnz     short loc_1800194E6
0x18001946f  mov     [rdi+0A0h], r13d
0x180019476  mov     rcx, [r12]; void *
0x18001947a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001947f  mov     [r12], r13
0x180019483  mov     rcx, [rsi]; void *
0x180019486  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001948b  mov     [rsi], r13
0x18001948e  mov     r15d, [rbp+arg_10]
0x180019492  mov     edx, r15d
0x180019495  mov     rcx, r12
0x180019498  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18001949d  test    al, al
0x18001949f  jz      loc_180019626
0x1800194a5  mov     edx, r15d
0x1800194a8  mov     rcx, rsi
0x1800194ab  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x1800194b0  test    al, al
0x1800194b2  jz      loc_180019626
0x1800194b8  mov     [rdi+0A0h], r15d
0x1800194bf  lea     rax, [rbp+arg_0]
0x1800194c3  mov     qword ptr [rsp+50h+var_8], rax; unsigned int
0x1800194c8  mov     rax, [rsi]
0x1800194cb  mov     [rsp+50h+var_30], rax; union _CVDD *
0x1800194d0  mov     r9, [r12]
0x1800194d4  lea     r8, [rbp+arg_10]
0x1800194d8  mov     rcx, r14; this
0x1800194db  call    CvDbgInfoFromImage
0x1800194e0  mov     ebx, eax
0x1800194e2  test    eax, eax
0x1800194e4  jns     short loc_180019501
0x1800194e6  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x1800194ed  jz      short loc_1800194FA
0x1800194ef  mov     r9d, ebx
0x1800194f2  mov     r8, r14
0x1800194f5  call    McTemplateU0zq_EventWriteTransfer
0x1800194fa  mov     eax, ebx
0x1800194fc  jmp     loc_18001962B
0x180019501  mov     r15d, r13d
0x180019504  mov     bl, [rbp+arg_0]
0x180019507  cmp     r15d, [rbp+arg_10]
0x18001950b  jnb     loc_180019622
0x180019511  mov     ecx, r15d
0x180019514  mov     rax, [rsi]
0x180019517  mov     r8d, [rax+rcx*4]
0x18001951b  cmp     r8d, 18h
0x18001951f  jbe     loc_180019606
0x180019525  imul    r13, rcx, 628h
0x18001952c  add     r13, [r12]
0x180019530  cmp     dword ptr [r13+0], 53445352h
0x180019538  jnz     loc_180019606
0x18001953e  lea     rdx, [r13+18h]
0x180019542  test    rdx, rdx
0x180019545  jz      loc_180019606
0x18001954b  lea     eax, [r8-18h]
0x18001954f  mov     ecx, eax
0x180019551  cmp     rcx, 7FFFFFFFh
0x180019558  ja      loc_180019606
0x18001955e  test    eax, eax
0x180019560  jz      short loc_180019570
0x180019562  cmp     byte ptr [rdx], 0
0x180019565  jz      short loc_180019570
0x180019567  inc     rdx
0x18001956a  sub     rcx, 1
0x18001956e  jnz     short loc_180019562
0x180019570  test    rcx, rcx
0x180019573  jz      loc_180019606
0x180019579  mov     byte ptr [rsp+50h+var_30], bl; bool
0x18001957d  mov     r9, r13; struct _RSDS *
0x180019580  mov     r8, r14; unsigned __int16 *
0x180019583  mov     rdx, [rdi+40h]; unsigned __int16 *
0x180019587  mov     rcx, rdi; this
0x18001958a  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x18001958f  test    eax, eax
0x180019591  jns     short loc_180019606
0x180019593  lea     rcx, [rbp+arg_18]
0x180019597  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001959c  nop
0x18001959d  mov     edx, 2Fh ; '/'; Ch
0x1800195a2  mov     rcx, r14; Str
0x1800195a5  call    cs:__imp_wcsrchr
0x1800195ab  mov     rbx, rax
0x1800195ae  mov     edx, 5Ch ; '\'; Ch
0x1800195b3  mov     rcx, r14; Str
0x1800195b6  call    cs:__imp_wcsrchr
0x1800195bc  cmp     rbx, rax
0x1800195bf  cmova   rax, rbx
0x1800195c3  test    rax, rax
0x1800195c6  jz      short loc_18001960E
0x1800195c8  sub     rax, r14
0x1800195cb  sar     rax, 1
0x1800195ce  mov     r8d, eax
0x1800195d1  mov     rdx, r14
0x1800195d4  lea     rcx, [rbp+arg_18]
0x1800195d8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800195dd  mov     al, [rbp+arg_0]
0x1800195e0  mov     byte ptr [rsp+50h+var_30], al; bool
0x1800195e4  mov     r9, r13; struct _RSDS *
0x1800195e7  mov     r8, r14; unsigned __int16 *
0x1800195ea  mov     rbx, [rbp+arg_18]
0x1800195ee  mov     rdx, rbx; unsigned __int16 *
0x1800195f1  mov     rcx, rdi; this
0x1800195f4  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x1800195f9  nop
0x1800195fa  lea     rcx, [rbx-18h]; this
0x1800195fe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019603  mov     bl, [rbp+arg_0]
0x180019606  inc     r15d
0x180019609  jmp     loc_180019507
0x18001960e  mov     rcx, [rbp+arg_18]
0x180019612  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019616  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001961b  mov     eax, 1
0x180019620  jmp     short loc_18001962B
0x180019622  xor     eax, eax
0x180019624  jmp     short loc_18001962B
0x180019626  mov     eax, 8007000Eh
0x18001962b  mov     rbx, [rsp+50h+arg_8]
0x180019633  add     rsp, 50h
0x180019637  pop     r15
0x180019639  pop     r14
0x18001963b  pop     r13
0x18001963d  pop     r12
0x18001963f  pop     rdi
0x180019640  pop     rsi
0x180019641  pop     rbp
0x180019642  retn
```
