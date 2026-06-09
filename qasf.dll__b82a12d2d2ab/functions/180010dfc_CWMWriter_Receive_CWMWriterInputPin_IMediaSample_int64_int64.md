# CWMWriter::Receive(CWMWriterInputPin *,IMediaSample *,__int64 *,__int64 *)

- ea: `0x180010dfc`
- end: `0x180011268`
- name: `?Receive@CWMWriter@@IEAAJPEAVCWMWriterInputPin@@PEAUIMediaSample@@PEA_J2@Z`
- size: `1132`
- prototype: `__int64 __fastcall(CWMWriter *this, struct CWMWriterInputPin *, struct IMediaSample *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180014ac0`

## callees

- `0x180001020`
- `0x180001460`
- `0x18000f2d0`
- `0x180010dfc`
- `0x180013028`
- `0x1800130a4`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriter::Receive(
        CWMWriter *this,
        struct CWMWriterInputPin *a2,
        struct IMediaSample *a3,
        __int64 *a4,
        __int64 *a5)
{
  int v9; // ebx
  _QWORD *v10; // rax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, struct INSSBuffer **); // rbx
  unsigned int v14; // eax
  CWMWriter *v15; // rcx
  int v16; // ebx
  int v17; // eax
  unsigned int v18; // r15d
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned int *v21; // rbx
  unsigned int *v22; // rdi
  unsigned int v23; // r10d
  unsigned int v24; // r8d
  unsigned int v25; // r9d
  unsigned int v26; // eax
  unsigned int v27; // eax
  int v28; // edx
  int v29; // ecx
  int i; // eax
  int v31; // eax
  bool v32; // sf
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned int v36[4]; // [rsp+40h] [rbp-31h] BYREF
  IID v37; // [rsp+50h] [rbp-21h] BYREF
  struct INSSBuffer *v38; // [rsp+60h] [rbp-11h] BYREF
  __int64 *v39; // [rsp+68h] [rbp-9h] BYREF
  __int16 v40; // [rsp+70h] [rbp-1h] BYREF

  if ( !*((_DWORD *)this + 10) || *((_DWORD *)this + 75) )
    return 0;
  v38 = 0;
  if ( *((_DWORD *)a2 + 114) || *((_DWORD *)this + 58) )
  {
    v12 = *((_QWORD *)this + 39);
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, struct INSSBuffer **))(*(_QWORD *)v12 + 104LL);
    v14 = ((__int64 (__fastcall *)(struct IMediaSample *))a3->lpVtbl->GetSize)(a3);
    v9 = v13(v12, v14, &v38);
    if ( v9 < 0 )
      goto LABEL_10;
    v11 = CWMWriter::CopyOurSampleToNSBuffer(v15, v38, a3);
  }
  else
  {
    v9 = 0;
    v10 = operator new(0x40u);
    if ( !v10 )
      goto LABEL_10;
    _InterlockedIncrement(&CBaseObject::m_cObjects);
    v10[6] = a3;
    *v10 = &CWMSample::`vftable';
    v10[1] = 0;
    v10[2] = 0;
    *((_DWORD *)v10 + 6) = 0;
    v10[4] = 10;
    v10[5] = 0;
    *((_DWORD *)v10 + 14) = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct INSSBuffer **))*v10)(v10, &IID_INSSBuffer, &v38);
  }
  v9 = v11;
LABEL_10:
  if ( v38 && v9 >= 0 )
  {
    v16 = 2;
    if ( ((unsigned int (__fastcall *)(struct IMediaSample *))a3->lpVtbl->IsDiscontinuity)(a3) )
      v16 = 0;
    v17 = ((__int64 (__fastcall *)(struct IMediaSample *))a3->lpVtbl->IsSyncPoint)(a3);
    v39 = 0;
    v18 = v16 | 1;
    if ( v17 )
      v18 = v16;
    if ( ((__int64 (__fastcall *)(struct INSSBuffer *, GUID *, __int64 **))v38->lpVtbl->QueryInterface)(
           v38,
           &IID_INSSBuffer3,
           &v39) >= 0 )
    {
      v19 = *((_QWORD *)a2 + 65);
      if ( v19 )
        (*(void (__fastcall **)(__int64, __int64 *, char *, __int64 *, __int64 *))(*(_QWORD *)v19 + 24LL))(
          v19,
          v39,
          (char *)a2 + 24,
          a4,
          a5);
      if ( *((_DWORD *)a2 + 126) )
      {
        v36[0] = 0;
        if ( (int)GetInterlaceFlagsFromMediaType((const struct _AMMediaType *)((char *)a2 + 104), v36) >= 0 )
        {
          LOBYTE(v40) = 0;
          if ( (v36[0] & 1) != 0 )
            LOBYTE(v40) = (v36[0] & 4) != 0 ? -64 : -96;
          v20 = *v39;
          v37 = WM_SampleExtensionGUID_ContentType;
          (*(void (__fastcall **)(__int64 *, IID *, __int16 *, __int64))(v20 + 80))(v39, &v37, &v40, 1);
        }
      }
      if ( *((_DWORD *)a2 + 127) )
      {
        v21 = (unsigned int *)((char *)a2 + 516);
        v22 = (unsigned int *)((char *)a2 + 512);
        if ( (int)GetPixelAspectRatio((const struct _AMMediaType *)((char *)a2 + 104), (int *)a2 + 128, (int *)a2 + 129) >= 0 )
        {
          v23 = *v22;
          v24 = *v22;
          v25 = *v21;
          if ( *v22 >= *v21 )
            v24 = *v21;
          if ( v23 >= v25 )
            v25 = *v22;
          if ( v24 )
          {
            v26 = v25;
            while ( v26 % v24 )
            {
              v27 = v25;
              v25 = v24;
              v28 = v27 % v24;
              v26 = v24;
              v24 = v28;
            }
          }
          else
          {
            v24 = 1;
          }
          v29 = v23 / v24;
          *v22 = v23 / v24;
          for ( i = *v21 / v24; ; i >>= 1 )
          {
            *v21 = i;
            if ( v29 <= 255 && i <= 255 )
              break;
            v29 >>= 1;
            *v22 = v29;
          }
          v40 = (*(_WORD *)v21 << 8) | (unsigned __int8)*(_WORD *)v22;
          v37 = WM_SampleExtensionGUID_PixelAspectRatio;
          (*(void (__fastcall **)(__int64 *, IID *, __int16 *, __int64))(*v39 + 80))(v39, &v37, &v40, 2);
        }
      }
      (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
    }
    if ( *((_DWORD *)this + 56) )
    {
      if ( *((_DWORD *)a2 + 116) )
      {
        v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, struct INSSBuffer *))(**((_QWORD **)this + 44)
                                                                                             + 48LL))(
                *((_QWORD *)this + 44),
                *((unsigned int *)a2 + 99),
                *a4,
                v18,
                v38);
        if ( (unsigned int)v31 > 1 )
        {
          *((_DWORD *)this + 75) = 1;
LABEL_52:
          v32 = v31 < 0;
          goto LABEL_53;
        }
      }
    }
    else if ( *((_DWORD *)a2 + 114) || *((_DWORD *)this + 58) )
    {
      v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 40) + 56LL))(
              *((_QWORD *)this + 40),
              (unsigned __int16)(*((_WORD *)a2 + 198) + 1),
              *a4);
      if ( v31 )
      {
        *((_DWORD *)this + 75) = 1;
        goto LABEL_52;
      }
    }
    else
    {
      v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, struct INSSBuffer *))(**((_QWORD **)this + 39)
                                                                                           + 112LL))(
              *((_QWORD *)this + 39),
              *((unsigned int *)a2 + 99),
              *a4,
              v18,
              v38);
      v32 = v31 < 0;
      if ( v31 )
      {
        *((_DWORD *)this + 75) = 1;
LABEL_53:
        if ( v32 )
        {
          v33 = *((_QWORD *)this + 13);
          if ( v33 )
            (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v33 + 24LL))(v33, 3, v31);
        }
      }
    }
    ((void (__fastcall *)(struct INSSBuffer *))v38->lpVtbl->Release)(v38);
    *((_QWORD *)a2 + 61) = *a4;
    *((_QWORD *)a2 + 62) = *a5;
    return 0;
  }
  v34 = *((_QWORD *)this + 13);
  *((_DWORD *)this + 75) = 1;
  if ( v34 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v34 + 24LL))(v34, 3, v9);
  return 0;
}

```

## disassembly

```asm
0x180010dfc  push    rbp
0x180010dfe  push    rbx
0x180010dff  push    rsi
0x180010e00  push    rdi
0x180010e01  push    r12
0x180010e03  push    r13
0x180010e05  push    r14
0x180010e07  push    r15
0x180010e09  lea     rbp, [rsp-17h]
0x180010e0e  sub     rsp, 88h
0x180010e15  mov     rax, cs:__security_cookie
0x180010e1c  xor     rax, rsp
0x180010e1f  mov     [rbp+4Fh+var_48], rax
0x180010e23  mov     r13, [rbp+4Fh+arg_20]
0x180010e27  xor     edi, edi
0x180010e29  mov     r12, r9
0x180010e2c  mov     r15, r8
0x180010e2f  mov     r14, rdx
0x180010e32  mov     rsi, rcx
0x180010e35  cmp     [rcx+28h], edi
0x180010e38  jz      loc_180011246
0x180010e3e  cmp     [rcx+12Ch], edi
0x180010e44  jnz     loc_180011246
0x180010e4a  mov     [rbp+4Fh+var_60], rdi
0x180010e4e  cmp     [rdx+1C8h], edi
0x180010e54  jnz     short loc_180010EBB
0x180010e56  cmp     [rcx+0E8h], edi
0x180010e5c  jnz     short loc_180010EBB
0x180010e5e  lea     ecx, [rdi+40h]; Size
0x180010e61  mov     ebx, edi
0x180010e63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010e68  mov     rcx, rax
0x180010e6b  test    rax, rax
0x180010e6e  jz      loc_180010EFF
0x180010e74  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180010e7b  lea     rax, ??_7CWMSample@@6B@; const CWMSample::`vftable'
0x180010e82  mov     [rcx+30h], r15
0x180010e86  mov     [rcx], rax
0x180010e89  lea     r8, [rbp+4Fh+var_60]
0x180010e8d  mov     [rcx+8], rdi
0x180010e91  lea     rdx, IID_INSSBuffer
0x180010e98  mov     [rcx+10h], rdi
0x180010e9c  mov     [rcx+18h], edi
0x180010e9f  mov     qword ptr [rcx+20h], 0Ah
0x180010ea7  mov     [rcx+28h], rdi
0x180010eab  mov     [rcx+38h], edi
0x180010eae  mov     rax, [rcx]
0x180010eb1  mov     rax, [rax]
0x180010eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eb9  jmp     short loc_180010EFD
0x180010ebb  mov     rdi, [rcx+138h]
0x180010ec2  mov     rcx, r15
0x180010ec5  mov     rdx, [r8]
0x180010ec8  mov     rax, [rdi]
0x180010ecb  mov     rbx, [rax+68h]
0x180010ecf  mov     rax, [rdx+20h]
0x180010ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ed8  mov     edx, eax
0x180010eda  lea     r8, [rbp+4Fh+var_60]
0x180010ede  mov     rax, rbx
0x180010ee1  mov     rcx, rdi
0x180010ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ee9  xor     edi, edi
0x180010eeb  mov     ebx, eax
0x180010eed  test    eax, eax
0x180010eef  js      short loc_180010EFF
0x180010ef1  mov     rdx, [rbp+4Fh+var_60]; struct INSSBuffer *
0x180010ef5  mov     r8, r15; struct IMediaSample *
0x180010ef8  call    ?CopyOurSampleToNSBuffer@CWMWriter@@IEAAJPEAUINSSBuffer@@PEAUIMediaSample@@@Z; CWMWriter::CopyOurSampleToNSBuffer(INSSBuffer *,IMediaSample *)
0x180010efd  mov     ebx, eax
0x180010eff  cmp     [rbp+4Fh+var_60], rdi
0x180010f03  jz      loc_18001121D
0x180010f09  test    ebx, ebx
0x180010f0b  js      loc_18001121D
0x180010f11  mov     rax, [r15]
0x180010f14  mov     rcx, r15
0x180010f17  mov     rax, [rax+78h]
0x180010f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f20  test    eax, eax
0x180010f22  mov     ebx, 2
0x180010f27  mov     rax, [r15]
0x180010f2a  mov     rcx, r15
0x180010f2d  cmovnz  ebx, edi
0x180010f30  mov     rax, [rax+38h]
0x180010f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f39  mov     rcx, [rbp+4Fh+var_60]
0x180010f3d  lea     r8, [rbp+4Fh+var_58]
0x180010f41  mov     [rbp+4Fh+var_58], rdi
0x180010f45  lea     rdx, IID_INSSBuffer3
0x180010f4c  mov     r15d, ebx
0x180010f4f  or      r15d, 1
0x180010f53  test    eax, eax
0x180010f55  mov     rax, [rcx]
0x180010f58  cmovnz  r15d, ebx
0x180010f5c  mov     rax, [rax]
0x180010f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f64  test    eax, eax
0x180010f66  js      loc_1800110E6
0x180010f6c  mov     rcx, [r14+208h]
0x180010f73  test    rcx, rcx
0x180010f76  jz      short loc_180010F94
0x180010f78  mov     rax, [rcx]
0x180010f7b  lea     r8, [r14+18h]
0x180010f7f  mov     rdx, [rbp+4Fh+var_58]
0x180010f83  mov     r9, r12
0x180010f86  mov     [rsp+0C0h+var_A0], r13
0x180010f8b  mov     rax, [rax+18h]
0x180010f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f94  cmp     [r14+1F8h], edi
0x180010f9b  jz      short loc_180010FF5
0x180010f9d  lea     rcx, [r14+68h]; struct _AMMediaType *
0x180010fa1  mov     [rbp+4Fh+var_80], edi
0x180010fa4  lea     rdx, [rbp+4Fh+var_80]; unsigned int *
0x180010fa8  call    ?GetInterlaceFlagsFromMediaType@@YAJPEBU_AMMediaType@@PEAK@Z; GetInterlaceFlagsFromMediaType(_AMMediaType const *,ulong *)
0x180010fad  test    eax, eax
0x180010faf  js      short loc_180010FF5
0x180010fb1  mov     eax, [rbp+4Fh+var_80]
0x180010fb4  mov     edx, 1
0x180010fb9  mov     byte ptr [rbp+4Fh+var_50], dil
0x180010fbd  test    dl, al
0x180010fbf  jz      short loc_180010FCE
0x180010fc1  and     al, 4
0x180010fc3  neg     al
0x180010fc5  sbb     al, al
0x180010fc7  and     al, 20h
0x180010fc9  add     al, 0A0h
0x180010fcb  mov     byte ptr [rbp+4Fh+var_50], al
0x180010fce  mov     rcx, [rbp+4Fh+var_58]
0x180010fd2  lea     r8, [rbp+4Fh+var_50]
0x180010fd6  movups  xmm0, xmmword ptr cs:WM_SampleExtensionGUID_ContentType.Data1
0x180010fdd  mov     r9d, edx
0x180010fe0  lea     rdx, [rbp+4Fh+var_70]
0x180010fe4  mov     rax, [rcx]
0x180010fe7  movdqu  [rbp+4Fh+var_70], xmm0
0x180010fec  mov     rax, [rax+50h]
0x180010ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ff5  cmp     [r14+1FCh], edi
0x180010ffc  jz      loc_1800110D6
0x180011002  lea     rbx, [r14+204h]
0x180011009  lea     rdi, [r14+200h]
0x180011010  mov     r8, rbx; int *
0x180011013  mov     rdx, rdi; int *
0x180011016  lea     rcx, [r14+68h]; struct _AMMediaType *
0x18001101a  call    ?GetPixelAspectRatio@@YAJPEBU_AMMediaType@@PEAJ1@Z; GetPixelAspectRatio(_AMMediaType const *,long *,long *)
0x18001101f  test    eax, eax
0x180011021  js      loc_1800110D4
0x180011027  mov     r10d, [rdi]
0x18001102a  mov     r8d, r10d
0x18001102d  cmp     r10d, [rbx]
0x180011030  mov     r9d, [rbx]
0x180011033  cmovnb  r8d, [rbx]
0x180011037  cmp     r10d, r9d
0x18001103a  cmovnb  r9d, r10d
0x18001103e  test    r8d, r8d
0x180011041  jz      short loc_180011066
0x180011043  mov     eax, r9d
0x180011046  jmp     short loc_18001105B
0x180011048  mov     eax, r9d
0x18001104b  mov     ecx, r8d
0x18001104e  xor     edx, edx
0x180011050  mov     r9d, ecx
0x180011053  div     r8d
0x180011056  mov     eax, ecx
0x180011058  mov     r8d, edx
0x18001105b  xor     edx, edx
0x18001105d  div     r8d
0x180011060  test    edx, edx
0x180011062  jnz     short loc_180011048
0x180011064  jmp     short loc_18001106C
0x180011066  mov     r8d, 1
0x18001106c  xor     edx, edx
0x18001106e  mov     eax, r10d
0x180011071  div     r8d
0x180011074  xor     edx, edx
0x180011076  mov     ecx, eax
0x180011078  mov     [rdi], eax
0x18001107a  mov     eax, [rbx]
0x18001107c  div     r8d
0x18001107f  mov     edx, 0FFh
0x180011084  mov     [rbx], eax
0x180011086  cmp     ecx, edx
0x180011088  jg      short loc_18001108E
0x18001108a  cmp     eax, edx
0x18001108c  jle     short loc_180011096
0x18001108e  sar     ecx, 1
0x180011090  mov     [rdi], ecx
0x180011092  sar     eax, 1
0x180011094  jmp     short loc_180011084
0x180011096  movzx   ecx, word ptr [rdi]
0x180011099  lea     r8, [rbp+4Fh+var_50]
0x18001109d  movzx   eax, word ptr [rbx]
0x1800110a0  and     cx, dx
0x1800110a3  movups  xmm0, xmmword ptr cs:WM_SampleExtensionGUID_PixelAspectRatio.Data1
0x1800110aa  shl     ax, 8
0x1800110ae  lea     rdx, [rbp+4Fh+var_70]
0x1800110b2  or      cx, ax
0x1800110b5  mov     r9d, 2
0x1800110bb  mov     [rbp+4Fh+var_50], cx
0x1800110bf  mov     rcx, [rbp+4Fh+var_58]
0x1800110c3  movdqu  [rbp+4Fh+var_70], xmm0
0x1800110c8  mov     rax, [rcx]
0x1800110cb  mov     rax, [rax+50h]
0x1800110cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d4  xor     edi, edi
0x1800110d6  mov     rcx, [rbp+4Fh+var_58]
0x1800110da  mov     rax, [rcx]
0x1800110dd  mov     rax, [rax+10h]
0x1800110e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e6  cmp     [rsi+0E0h], edi
0x1800110ec  jz      short loc_18001113D
0x1800110ee  cmp     [r14+1D0h], edi
0x1800110f5  jbe     loc_1800111F5
0x1800110fb  mov     rdx, [rbp+4Fh+var_60]
0x1800110ff  mov     r9d, r15d
0x180011102  mov     rcx, [rsi+160h]
0x180011109  mov     r8, [r12]
0x18001110d  mov     [rsp+0C0h+var_A0], rdx
0x180011112  mov     edx, [r14+18Ch]
0x180011119  mov     rax, [rcx]
0x18001111c  mov     rax, [rax+30h]
0x180011120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011125  mov     ecx, 1
0x18001112a  cmp     eax, ecx
0x18001112c  jbe     loc_1800111F5
0x180011132  mov     [rsi+12Ch], ecx
0x180011138  jmp     loc_1800111D2
0x18001113d  cmp     [r14+1C8h], edi
0x180011144  jnz     short loc_180011188
0x180011146  cmp     [rsi+0E8h], edi
0x18001114c  jnz     short loc_180011188
0x18001114e  mov     rdx, [rbp+4Fh+var_60]
0x180011152  mov     r9d, r15d
0x180011155  mov     rcx, [rsi+138h]
0x18001115c  mov     r8, [r12]
0x180011160  mov     [rsp+0C0h+var_A0], rdx
0x180011165  mov     edx, [r14+18Ch]
0x18001116c  mov     rax, [rcx]
0x18001116f  mov     rax, [rax+70h]
0x180011173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011178  test    eax, eax
0x18001117a  jz      short loc_1800111F5
0x18001117c  mov     dword ptr [rsi+12Ch], 1
0x180011186  jmp     short loc_1800111D4
0x180011188  mov     r8, [rbp+4Fh+var_60]
0x18001118c  mov     r9d, 0FFFFFFFFh
0x180011192  mov     rcx, [rsi+140h]
0x180011199  mov     ebx, 1
0x18001119e  movzx   edx, word ptr [r14+18Ch]
0x1800111a6  mov     [rsp+0C0h+var_90], r8
0x1800111ab  add     dx, bx
0x1800111ae  mov     r8, [r12]
0x1800111b2  mov     rax, [rcx]
0x1800111b5  mov     [rsp+0C0h+var_98], r15d
0x1800111ba  mov     [rsp+0C0h+var_A0], r9
0x1800111bf  mov     rax, [rax+38h]
0x1800111c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111c8  test    eax, eax
0x1800111ca  jz      short loc_1800111F5
0x1800111cc  mov     [rsi+12Ch], ebx
0x1800111d2  test    eax, eax
0x1800111d4  jns     short loc_1800111F5
0x1800111d6  mov     rcx, [rsi+68h]
0x1800111da  test    rcx, rcx
0x1800111dd  jz      short loc_1800111F5
0x1800111df  mov     rdx, [rcx]
0x1800111e2  xor     r9d, r9d
0x1800111e5  movsxd  r8, eax
0x1800111e8  mov     rax, [rdx+18h]
0x1800111ec  lea     edx, [r9+3]
0x1800111f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111f5  mov     rcx, [rbp+4Fh+var_60]
0x1800111f9  mov     rax, [rcx]
0x1800111fc  mov     rax, [rax+10h]
0x180011200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011205  mov     rax, [r12]
0x180011209  mov     [r14+1E8h], rax
0x180011210  mov     rax, [r13+0]
0x180011214  mov     [r14+1F0h], rax
0x18001121b  jmp     short loc_180011246
0x18001121d  mov     rcx, [rsi+68h]
0x180011221  mov     dword ptr [rsi+12Ch], 1
0x18001122b  test    rcx, rcx
0x18001122e  jz      short loc_180011246
0x180011230  mov     rax, [rcx]
0x180011233  xor     r9d, r9d
0x180011236  movsxd  r8, ebx
0x180011239  mov     rax, [rax+18h]
0x18001123d  lea     edx, [r9+3]
0x180011241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011246  xor     eax, eax
0x180011248  mov     rcx, [rbp+4Fh+var_48]
0x18001124c  xor     rcx, rsp; StackCookie
0x18001124f  call    __security_check_cookie
0x180011254  add     rsp, 88h
0x18001125b  pop     r15
0x18001125d  pop     r14
0x18001125f  pop     r13
0x180011261  pop     r12
0x180011263  pop     rdi
0x180011264  pop     rsi
  ... truncated ...
```
