# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *)

- ea: `0x180019e28`
- end: `0x18001a088`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBG@Z`
- size: `608`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a5d0`

## callees

- `0x180001824`
- `0x18000938c`
- `0x180009a4c`
- `0x18000c6e4`
- `0x18000c9a8`
- `0x180014240`
- `0x180019e28`
- `0x18001a090`
- `0x18001b208`
- `0x18002469c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180019fdd`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180019ff4`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180019fdd`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180019ff4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(v5, v11) )
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
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v32);
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
0x180019e28  mov     [rsp-38h+arg_8], rbx
0x180019e2d  push    rbp
0x180019e2e  push    rsi
0x180019e2f  push    rdi
0x180019e30  push    r12
0x180019e32  push    r13
0x180019e34  push    r14
0x180019e36  push    r15
0x180019e38  mov     rbp, rsp
0x180019e3b  sub     rsp, 50h
0x180019e3f  mov     r14, rdx
0x180019e42  mov     rdi, rcx
0x180019e45  xor     r13d, r13d
0x180019e48  mov     [rbp+arg_0], r13b
0x180019e4c  mov     eax, [rcx+0A0h]
0x180019e52  mov     [rbp+arg_10], eax
0x180019e55  lea     r12, [rcx+0A8h]
0x180019e5c  mov     r9, [r12]
0x180019e60  test    r9, r9
0x180019e63  jz      loc_18001A06A
0x180019e69  lea     rsi, [rcx+0B0h]
0x180019e70  mov     rax, [rsi]
0x180019e73  test    rax, rax
0x180019e76  jz      loc_18001A06A
0x180019e7c  lea     rcx, [rbp+arg_0]
0x180019e80  mov     qword ptr [rsp+50h+var_8], rcx; unsigned int
0x180019e85  mov     [rsp+50h+var_30], rax; union _CVDD *
0x180019e8a  lea     r8, [rbp+arg_10]
0x180019e8e  mov     rcx, rdx; this
0x180019e91  call    CvDbgInfoFromImage
0x180019e96  mov     ebx, eax
0x180019e98  test    eax, eax
0x180019e9a  jns     loc_180019F39
0x180019ea0  cmp     eax, 80090321h
0x180019ea5  jnz     short loc_180019F1E
0x180019ea7  mov     [rdi+0A0h], r13d
0x180019eae  mov     rcx, [r12]; void *
0x180019eb2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019eb7  mov     [r12], r13
0x180019ebb  mov     rcx, [rsi]; void *
0x180019ebe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019ec3  mov     [rsi], r13
0x180019ec6  mov     r15d, [rbp+arg_10]
0x180019eca  mov     edx, r15d
0x180019ecd  mov     rcx, r12
0x180019ed0  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x180019ed5  test    al, al
0x180019ed7  jz      loc_18001A06A
0x180019edd  mov     edx, r15d
0x180019ee0  mov     rcx, rsi
0x180019ee3  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180019ee8  test    al, al
0x180019eea  jz      loc_18001A06A
0x180019ef0  mov     [rdi+0A0h], r15d
0x180019ef7  lea     rax, [rbp+arg_0]
0x180019efb  mov     qword ptr [rsp+50h+var_8], rax; unsigned int
0x180019f00  mov     rax, [rsi]
0x180019f03  mov     [rsp+50h+var_30], rax; union _CVDD *
0x180019f08  mov     r9, [r12]
0x180019f0c  lea     r8, [rbp+arg_10]
0x180019f10  mov     rcx, r14; this
0x180019f13  call    CvDbgInfoFromImage
0x180019f18  mov     ebx, eax
0x180019f1a  test    eax, eax
0x180019f1c  jns     short loc_180019F39
0x180019f1e  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x180019f25  jz      short loc_180019F32
0x180019f27  mov     r9d, ebx
0x180019f2a  mov     r8, r14
0x180019f2d  call    McTemplateU0zq_EventWriteTransfer
0x180019f32  mov     eax, ebx
0x180019f34  jmp     loc_18001A06F
0x180019f39  mov     r15d, r13d
0x180019f3c  mov     bl, [rbp+arg_0]
0x180019f3f  cmp     r15d, [rbp+arg_10]
0x180019f43  jnb     loc_18001A066
0x180019f49  mov     ecx, r15d
0x180019f4c  mov     rax, [rsi]
0x180019f4f  mov     r8d, [rax+rcx*4]
0x180019f53  cmp     r8d, 18h
0x180019f57  jbe     loc_18001A04A
0x180019f5d  imul    r13, rcx, 628h
0x180019f64  add     r13, [r12]
0x180019f68  cmp     dword ptr [r13+0], 53445352h
0x180019f70  jnz     loc_18001A04A
0x180019f76  lea     rdx, [r13+18h]
0x180019f7a  test    rdx, rdx
0x180019f7d  jz      loc_18001A04A
0x180019f83  lea     eax, [r8-18h]
0x180019f87  mov     ecx, eax
0x180019f89  cmp     rcx, 7FFFFFFFh
0x180019f90  ja      loc_18001A04A
0x180019f96  test    eax, eax
0x180019f98  jz      short loc_180019FA8
0x180019f9a  cmp     byte ptr [rdx], 0
0x180019f9d  jz      short loc_180019FA8
0x180019f9f  inc     rdx
0x180019fa2  sub     rcx, 1
0x180019fa6  jnz     short loc_180019F9A
0x180019fa8  test    rcx, rcx
0x180019fab  jz      loc_18001A04A
0x180019fb1  mov     byte ptr [rsp+50h+var_30], bl; bool
0x180019fb5  mov     r9, r13; struct _RSDS *
0x180019fb8  mov     r8, r14; unsigned __int16 *
0x180019fbb  mov     rdx, [rdi+40h]; unsigned __int16 *
0x180019fbf  mov     rcx, rdi; this
0x180019fc2  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x180019fc7  test    eax, eax
0x180019fc9  jns     short loc_18001A04A
0x180019fcb  lea     rcx, [rbp+arg_18]
0x180019fcf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180019fd4  nop
0x180019fd5  mov     edx, 2Fh ; '/'; Ch
0x180019fda  mov     rcx, r14; Str
0x180019fdd  call    cs:__imp_wcsrchr
0x180019fe4  nop     dword ptr [rax+rax+00h]
0x180019fe9  mov     rbx, rax
0x180019fec  mov     edx, 5Ch ; '\'; Ch
0x180019ff1  mov     rcx, r14; Str
0x180019ff4  call    cs:__imp_wcsrchr
0x180019ffb  nop     dword ptr [rax+rax+00h]
0x18001a000  cmp     rbx, rax
0x18001a003  cmova   rax, rbx
0x18001a007  test    rax, rax
0x18001a00a  jz      short loc_18001A052
0x18001a00c  sub     rax, r14
0x18001a00f  sar     rax, 1
0x18001a012  mov     r8d, eax
0x18001a015  mov     rdx, r14
0x18001a018  lea     rcx, [rbp+arg_18]
0x18001a01c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001a021  mov     al, [rbp+arg_0]
0x18001a024  mov     byte ptr [rsp+50h+var_30], al; bool
0x18001a028  mov     r9, r13; struct _RSDS *
0x18001a02b  mov     r8, r14; unsigned __int16 *
0x18001a02e  mov     rbx, [rbp+arg_18]
0x18001a032  mov     rdx, rbx; unsigned __int16 *
0x18001a035  mov     rcx, rdi; this
0x18001a038  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x18001a03d  nop
0x18001a03e  lea     rcx, [rbx-18h]; this
0x18001a042  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a047  mov     bl, [rbp+arg_0]
0x18001a04a  inc     r15d
0x18001a04d  jmp     loc_180019F3F
0x18001a052  mov     rcx, [rbp+arg_18]
0x18001a056  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001a05a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a05f  mov     eax, 1
0x18001a064  jmp     short loc_18001A06F
0x18001a066  xor     eax, eax
0x18001a068  jmp     short loc_18001A06F
0x18001a06a  mov     eax, 8007000Eh
0x18001a06f  mov     rbx, [rsp+50h+arg_8]
0x18001a077  add     rsp, 50h
0x18001a07b  pop     r15
0x18001a07d  pop     r14
0x18001a07f  pop     r13
0x18001a081  pop     r12
0x18001a083  pop     rdi
0x18001a084  pop     rsi
0x18001a085  pop     rbp
0x18001a086  retn
```
