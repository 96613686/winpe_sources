# CDecodeContext::BeginFrame(ID3D11VideoDecoderOutputView *,void const *,uint,uint,uint const *,ID3D11Buffer * const *)

- ea: `0x18005dbe0`
- end: `0x18005e1b9`
- name: `?BeginFrame@CDecodeContext@@UEAAJPEAUID3D11VideoDecoderOutputView@@PEBXIIPEBIPEBQEAUID3D11Buffer@@@Z`
- size: `1497`
- prototype: `__int64 __fastcall(CDecodeContext *this, unsigned __int64, struct IDXGIResourceInternal *, int, unsigned int, const unsigned int *, struct ID3D11Buffer *const *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18005d9b0`
- `0x1800ccd60`

## callees

- `0x180008ae0`
- `0x180022400`
- `0x18002d8f0`
- `0x18005dbe0`
- `0x18005e1c0`
- `0x1800a6af0`
- `0x1800a9d20`
- `0x1800aa9a8`
- `0x180154f60`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dd87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dd87`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005de11`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005de11`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDecodeContext::BeginFrame(
        CDecodeContext *this,
        unsigned __int64 a2,
        struct IDXGIResourceInternal *a3,
        int a4,
        unsigned int a5,
        const unsigned int *a6,
        struct ID3D11Buffer *const *a7)
{
  struct ID3D11VideoDecoderOutputView *v7; // rbx
  CDevice **v9; // r14
  struct ID3D11VideoDecoderOutputViewVtbl *lpVtbl; // r13
  int v11; // eax
  __int64 v12; // r8
  CContext *v13; // r9
  struct ID3D11VideoDecoderOutputViewVtbl *v14; // rax
  bool v15; // zf
  unsigned int j; // ebx
  __int64 v17; // rsi
  int v18; // r15d
  __int64 v19; // rbx
  __int64 v20; // rcx
  unsigned __int8 v21; // al
  __int64 v22; // rcx
  char *v23; // rdx
  struct ID3D11VideoDecoderOutputView **v24; // r8
  int v25; // eax
  __int64 v26; // r8
  LARGE_INTEGER v27; // rax
  __int64 v28; // rdx
  int v30; // eax
  struct ID3D11Buffer *v31; // rax
  struct ID3D11Buffer *v32; // rdx
  unsigned int v33; // r8d
  __int64 v34; // rcx
  struct ID3D11Buffer *v35; // r13
  char v36; // cl
  __int64 i; // r9
  int v38; // ecx
  const unsigned int *v39; // rax
  int lpVtbl_high; // eax
  ULONG (__stdcall **p_Release)(ID3D11VideoDecoderOutputView *); // rdx
  unsigned __int64 v42; // r13
  unsigned int v43; // [rsp+40h] [rbp-1B8h]
  struct ID3D11Buffer *v44; // [rsp+48h] [rbp-1B0h]
  int v45; // [rsp+48h] [rbp-1B0h]
  struct IDXGIResourceInternal *AddRef; // [rsp+50h] [rbp-1A8h] BYREF
  int v47; // [rsp+58h] [rbp-1A0h]
  CDecodeContext *v48; // [rsp+60h] [rbp-198h]
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-190h] BYREF
  __int128 *v50; // [rsp+70h] [rbp-188h]
  _BYTE v51[28]; // [rsp+78h] [rbp-180h] BYREF
  __int64 v52; // [rsp+94h] [rbp-164h]
  int v53; // [rsp+9Ch] [rbp-15Ch]
  __int128 v54; // [rsp+A0h] [rbp-158h] BYREF
  __int128 v55; // [rsp+B0h] [rbp-148h]
  __int128 v56; // [rsp+C0h] [rbp-138h]
  struct ID3D11VideoDecoderOutputView *v57; // [rsp+E0h] [rbp-118h] BYREF
  __int128 *v58; // [rsp+E8h] [rbp-110h]
  int v59; // [rsp+F0h] [rbp-108h]
  int v60; // [rsp+F4h] [rbp-104h]
  _DWORD v61[2]; // [rsp+F8h] [rbp-100h] BYREF
  __int64 v62; // [rsp+100h] [rbp-F8h]
  unsigned int v63; // [rsp+108h] [rbp-F0h]
  __int64 v64; // [rsp+110h] [rbp-E8h]
  unsigned int v65; // [rsp+118h] [rbp-E0h]
  __int64 v66; // [rsp+120h] [rbp-D8h]
  unsigned int v67; // [rsp+128h] [rbp-D0h]
  __int64 v68; // [rsp+130h] [rbp-C8h]
  _QWORD v69[2]; // [rsp+140h] [rbp-B8h] BYREF
  int v70; // [rsp+150h] [rbp-A8h]
  int v71; // [rsp+154h] [rbp-A4h]
  __int64 v72; // [rsp+158h] [rbp-A0h]
  __int64 v73; // [rsp+160h] [rbp-98h]
  __int64 v74; // [rsp+168h] [rbp-90h]
  __int64 v75; // [rsp+170h] [rbp-88h]
  __int64 v76; // [rsp+178h] [rbp-80h]
  __int64 v77; // [rsp+180h] [rbp-78h]
  __int64 v78; // [rsp+188h] [rbp-70h]
  __int64 v79; // [rsp+190h] [rbp-68h]
  unsigned __int64 v80; // [rsp+1A0h] [rbp-58h] BYREF
  _BYTE v81[12]; // [rsp+1A8h] [rbp-50h]
  int v82; // [rsp+1B4h] [rbp-44h]

  v47 = a4;
  v50 = (__int128 *)a3;
  v7 = (struct ID3D11VideoDecoderOutputView *)a2;
  v48 = this;
  *((_QWORD *)this + 50) = this;
  v9 = (CDevice **)((char *)this + 160);
  if ( a5 > 4 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)*v9 + 156) + 32LL))(
      *((_QWORD *)*v9 + 156),
      3146261,
      a5);
    ThrowFailure(-2147024809);
  }
  if ( a5 )
  {
    *(_OWORD *)v51 = *((_OWORD *)this + 13);
    *(_OWORD *)&v51[12] = *(_OWORD *)((char *)this + 220);
    v52 = 0;
    v53 = 0;
    v38 = CDevice::CheckFeatureSupport(*v9, D3D11_FEATURE_VIDEO_DECODER_HISTOGRAM, v51, 0x28u);
    ThrowFailure(v38);
    v45 = 4 * HIDWORD(v52);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v43 = i;
      if ( (unsigned int)i >= a5 )
        break;
      a3 = (struct IDXGIResourceInternal *)(unsigned int)i;
      AddRef = (struct IDXGIResourceInternal *)(unsigned int)i;
      if ( a7[(unsigned int)i] )
      {
        v36 = 0;
        if ( ((unsigned int)v52 & (1 << i)) != 1 << i )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)*v9 + 156) + 32LL))(*((_QWORD *)*v9 + 156), 3146262);
          v36 = 1;
          a3 = AddRef;
          i = v43;
        }
        v39 = a6;
        if ( LOBYTE(a6[(_QWORD)a3]) )
        {
          (*(void (__fastcall **)(_QWORD, __int64, struct IDXGIResourceInternal *, __int64))(**((_QWORD **)*v9 + 156)
                                                                                           + 32LL))(
            *((_QWORD *)*v9 + 156),
            3146266,
            a3,
            i);
          v36 = 1;
          a3 = AddRef;
          i = v43;
          v39 = a6;
        }
        v35 = a7[(_QWORD)a3];
        a2 = v39[(_QWORD)a3] + v45;
        if ( (unsigned int)a2 < v39[(_QWORD)a3] || (unsigned int)a2 > LODWORD(v35[41].lpVtbl) )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)*v9 + 156) + 32LL))(*((_QWORD *)*v9 + 156), 3146263);
          v36 = 1;
          a3 = AddRef;
          i = v43;
        }
        if ( BYTE2(v35[31].lpVtbl) )
        {
          (*(void (__fastcall **)(_QWORD, __int64, struct IDXGIResourceInternal *, __int64))(**((_QWORD **)*v9 + 156)
                                                                                           + 32LL))(
            *((_QWORD *)*v9 + 156),
            3146264,
            a3,
            i);
          v36 = 1;
          LODWORD(i) = v43;
        }
        lpVtbl_high = HIDWORD(v35[35].lpVtbl);
        if ( (lpVtbl_high & 0xFFFF968D) != 0 )
        {
          v80 = (unsigned int)i | 0xFFFF968D00000000uLL;
          *(_DWORD *)v81 = lpVtbl_high;
          (*(void (__fastcall **)(_QWORD, __int64, unsigned __int64 *))(**((_QWORD **)*v9 + 156) + 32LL))(
            *((_QWORD *)*v9 + 156),
            3146265,
            &v80);
        }
        else if ( !v36 )
        {
          continue;
        }
        ThrowFailure(-2147024809);
        LODWORD(i) = v43;
      }
    }
  }
  if ( !v7 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)*v9 + 156) + 32LL))(
      *((_QWORD *)*v9 + 156),
      3145784,
      0);
    ThrowFailure(-2147024809);
  }
  if ( ((__int64)v7[32].lpVtbl->QueryInterface & 2) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)*v9 + 156) + 32LL))(
      *((_QWORD *)*v9 + 156),
      3145785,
      0x10000000);
    ThrowFailure(-2147024809);
  }
  if ( v7[32].lpVtbl->QueryInterface )
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)*v9 + 156) + 32LL))(
      *((_QWORD *)*v9 + 156),
      3145785,
      0x2000000);
    ThrowFailure(-2147024809);
  }
  lpVtbl = v7[26].lpVtbl;
  v11 = CView<ID3D11VideoDecoderOutputView>::SubresourceMask(v7, a2, a3, *((_QWORD *)*v9 + 135));
  if ( *((_DWORD *)v13 + 928) )
  {
    BYTE5(lpVtbl[5].SetPrivateDataInterface) = 1;
    if ( (BYTE1(lpVtbl[5].SetPrivateDataInterface) & 2) == 0 )
      HIDWORD(lpVtbl[5].GetDesc) |= v11;
  }
  else if ( BYTE5(lpVtbl[5].SetPrivateDataInterface) && !(unsigned __int8)CContext::AcquireResource(v13) )
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)*v9 + 156) + 32LL))(
      *((_QWORD *)*v9 + 156),
      3145785,
      0x2000000);
    ThrowFailure(-2147024809);
  }
  v14 = v7[32].lpVtbl;
  v15 = LODWORD(v14->Release)++ == -1;
  if ( v15 && (BYTE4(lpVtbl[3].GetResource) & 8) != 0 )
  {
    LOBYTE(v12) = 1;
    DDIContextST::DDIContextST(&v80, *((_QWORD *)*v9 + 135), v12);
    p_Release = &lpVtbl[6].Release;
    v42 = v80;
    (*(void (__fastcall **)(__int64, ULONG (__stdcall **)(ID3D11VideoDecoderOutputView *)))(v80 + 1736))(
      *((_QWORD *)*v9 + 135) + 40768LL,
      p_Release);
    *(_DWORD *)(v42 + 3688) = *(_DWORD *)v81;
    *(_QWORD *)(v42 + 3692) = *(_QWORD *)&v81[4];
  }
  BYTE1(v7[32].lpVtbl->QueryInterface) &= ~1u;
  v57 = v7 + 36;
  v58 = v50;
  v59 = v47;
  v60 = 0;
  memset_0(v61, 0, 0x40u);
  for ( j = 0; j < 4; ++j )
  {
    if ( a7 )
    {
      v31 = a7[j];
      v44 = v31;
      if ( v31 )
      {
        if ( j < a5 )
        {
          v32 = v31 + 52;
          if ( BYTE4(v31[51].lpVtbl) )
          {
            v33 = 240;
          }
          else
          {
            if ( !LODWORD(v32->lpVtbl) )
            {
LABEL_44:
              v34 = 2LL * j;
              v61[2 * v34] = a6[j];
              *(&v62 + v34) = (__int64)&v44[56];
              continue;
            }
            v33 = 0;
          }
          AddRef = (struct IDXGIResourceInternal *)v31[27].lpVtbl[1].AddRef;
          if ( LODWORD(v32->lpVtbl) )
            v33 |= 0x20Fu;
          CDevice::FlushResourceDeletion(
            *(CDevice **)(*((_QWORD *)*v9 + 135) + 160LL),
            &AddRef,
            1u,
            0,
            v33,
            0x2000u,
            0,
            1);
          goto LABEL_44;
        }
      }
    }
  }
  v54 = 0;
  v55 = 0;
  v56 = 0;
  if ( *((_BYTE *)this + 368) && v50 && v47 == 48 )
  {
    *((_QWORD *)&v54 + 1) = *((_QWORD *)v50 + 2);
    LODWORD(v55) = *((_DWORD *)v50 + 2);
    *(_QWORD *)&v56 = *((_QWORD *)v50 + 5);
    DWORD2(v56) = *((_DWORD *)v50 + 8);
    *((_QWORD *)&v55 + 1) = *((_QWORD *)v50 + 3);
    if ( *(_QWORD *)v50 )
      *(_QWORD *)&v54 = *(_QWORD *)v50 + 288LL;
    v58 = &v54;
  }
  v17 = *((_QWORD *)*v9 + 135);
  *(_QWORD *)v51 = v17;
  v18 = *(_DWORD *)(v17 + 3688);
  *(_DWORD *)&v51[8] = v18;
  v19 = *(_QWORD *)(v17 + 3692);
  *(_QWORD *)&v51[12] = v19;
  *(_DWORD *)(v17 + 3688) = GetCurrentThreadId();
  *(_BYTE *)(v17 + 3692) = 0;
  *(_WORD *)(v17 + 3693) = *(_WORD *)((char *)&v48 + 1);
  *(_BYTE *)(v17 + 3695) = BYTE3(v48);
  *(_DWORD *)(v17 + 3696) = 0;
  v20 = *((_QWORD *)*v9 + 135);
  v21 = *(_BYTE *)(v20 + 3708);
  v22 = v20 + 40768;
  v23 = (char *)this + 488;
  if ( v21 >= 0xDu )
  {
    v24 = &v57;
    goto LABEL_21;
  }
  if ( v21 >= 0xCu )
  {
    v69[0] = v57;
    v69[1] = v58;
    v70 = v59;
    v71 = 0;
    v72 = v61[0];
    v73 = v62;
    v74 = v63;
    v75 = v64;
    v76 = v65;
    v77 = v66;
    v78 = v67;
    v79 = v68;
    v24 = (struct ID3D11VideoDecoderOutputView **)v69;
LABEL_21:
    v25 = (*(__int64 (__fastcall **)(__int64, char *, struct ID3D11VideoDecoderOutputView **))(v17 + 2992))(
            v22,
            v23,
            v24);
    ThrowFailure(v25);
  }
  else
  {
    v80 = (unsigned __int64)v57;
    *(_QWORD *)v81 = v58;
    *(_DWORD *)&v81[8] = v59;
    v82 = v60;
    v30 = (*(__int64 (__fastcall **)(__int64, char *, unsigned __int64 *))(v17 + 2992))(v22, v23, &v80);
    ThrowFailure(v30);
  }
  *((_BYTE *)this + 361) = 1;
  ++*((_DWORD *)this + 94);
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v26 = *((_QWORD *)this + 54);
  v27 = PerformanceCount;
  if ( v26 )
  {
    v28 = 100LL * *((_QWORD *)this + 55);
    if ( v28 >= PerformanceCount.QuadPart - v26 )
      v28 = PerformanceCount.QuadPart - v26;
    *((_QWORD *)this + 53) += v28;
  }
  *((LARGE_INTEGER *)this + 54) = v27;
  *(_DWORD *)(v17 + 3688) = v18;
  *(_QWORD *)(v17 + 3692) = v19;
  return 0;
}

```

## disassembly

```asm
0x18005dbe0  push    rbx
0x18005dbe2  push    rsi
0x18005dbe3  push    rdi
0x18005dbe4  push    r12
0x18005dbe6  push    r13
0x18005dbe8  push    r14
0x18005dbea  push    r15
0x18005dbec  sub     rsp, 1C0h
0x18005dbf3  mov     rax, cs:__security_cookie
0x18005dbfa  xor     rax, rsp
0x18005dbfd  mov     [rsp+1F8h+var_40], rax
0x18005dc05  mov     [rsp+1F8h+var_1A0], r9d
0x18005dc0a  mov     [rsp+1F8h+var_188], r8
0x18005dc0f  mov     rbx, rdx
0x18005dc12  mov     rdi, rcx
0x18005dc15  mov     [rsp+1F8h+var_198], rcx
0x18005dc1a  mov     rsi, [rsp+1F8h+arg_30]
0x18005dc22  mov     [rcx+190h], rcx
0x18005dc29  lea     r14, [rcx+0A0h]
0x18005dc30  mov     r15d, [rsp+1F8h+arg_20]
0x18005dc38  cmp     r15d, 4
0x18005dc3c  ja      loc_18005E074
0x18005dc42  test    r15d, r15d
0x18005dc45  jnz     loc_1800EBCFC
0x18005dc4b  xor     r12d, r12d
0x18005dc4e  test    rbx, rbx
0x18005dc51  jz      loc_18005E0DE
0x18005dc57  mov     rax, [rbx+100h]
0x18005dc5e  test    byte ptr [rax], 2
0x18005dc61  jnz     loc_18005E10B
0x18005dc67  mov     rax, [rbx+100h]
0x18005dc6e  cmp     byte ptr [rax], 0
0x18005dc71  jnz     loc_18005E13B
0x18005dc77  mov     r13, [rbx+0D0h]
0x18005dc7e  mov     rax, [r14]
0x18005dc81  mov     r9, [rax+438h]
0x18005dc88  mov     rcx, rbx
0x18005dc8b  call    ?SubresourceMask@?$CView@UID3D11VideoDecoderOutputView@@@@QEBAIXZ; CView<ID3D11VideoDecoderOutputView>::SubresourceMask(void)
0x18005dc90  lea     rdx, [r13+188h]
0x18005dc97  cmp     dword ptr [r9+0E80h], 0
0x18005dc9f  jnz     loc_18005DE7E
0x18005dca5  cmp     byte ptr [rdx+15h], 0
0x18005dca9  jz      short loc_18005DCBE
0x18005dcab  mov     r8d, eax
0x18005dcae  mov     rcx, r9; this
0x18005dcb1  call    ?AcquireResource@CContext@@QEAA_NPEAUCLS@?$CResource@UID3D11Resource@@@@I@Z; CContext::AcquireResource(CResource<ID3D11Resource>::CLS *,uint)
0x18005dcb6  test    al, al
0x18005dcb8  jz      loc_18005E16B
0x18005dcbe  mov     rax, [rbx+100h]
0x18005dcc5  add     dword ptr [rax+10h], 1
0x18005dcc9  jz      loc_1800EBE6A
0x18005dccf  mov     rax, [rbx+100h]
0x18005dcd6  and     byte ptr [rax+1], 0FEh
0x18005dcda  lea     rax, [rbx+120h]
0x18005dce1  mov     [rsp+1F8h+var_118], rax
0x18005dce9  mov     r13, [rsp+1F8h+var_188]
0x18005dcee  mov     [rsp+1F8h+var_110], r13
0x18005dcf6  mov     eax, [rsp+1F8h+var_1A0]
0x18005dcfa  mov     [rsp+1F8h+var_108], eax
0x18005dd01  xor     eax, eax
0x18005dd03  mov     [rsp+1F8h+var_104], eax
0x18005dd0a  xor     edx, edx; Val
0x18005dd0c  mov     r8d, 40h ; '@'; Size
0x18005dd12  lea     rcx, [rsp+1F8h+var_100]; void *
0x18005dd1a  call    memset_0
0x18005dd1f  mov     ebx, r12d
0x18005dd22  test    rsi, rsi
0x18005dd25  jnz     loc_18005DF77
0x18005dd2b  inc     ebx
0x18005dd2d  cmp     ebx, 4
0x18005dd30  jb      short loc_18005DD22
0x18005dd32  xorps   xmm0, xmm0
0x18005dd35  movups  [rsp+1F8h+var_158], xmm0
0x18005dd3d  movups  [rsp+1F8h+var_148], xmm0
0x18005dd45  movups  [rsp+1F8h+var_138], xmm0
0x18005dd4d  cmp     byte ptr [rdi+170h], 0
0x18005dd54  jnz     loc_18005DEF8
0x18005dd5a  mov     rax, [r14]
0x18005dd5d  mov     rsi, [rax+438h]
0x18005dd64  mov     qword ptr [rsp+1F8h+var_180], rsi
0x18005dd69  mov     r15d, [rsi+0E68h]
0x18005dd70  mov     dword ptr [rsp+1F8h+var_180+8], r15d
0x18005dd78  mov     rbx, [rsi+0E6Ch]
0x18005dd7f  mov     qword ptr [rsp+1F8h+var_180+0Ch], rbx
0x18005dd87  call    cs:__imp_GetCurrentThreadId
0x18005dd8d  mov     [rsi+0E68h], eax
0x18005dd93  mov     byte ptr [rsi+0E6Ch], 0
0x18005dd9a  movzx   eax, word ptr [rsp+1F8h+var_198+1]
0x18005dd9f  mov     [rsi+0E6Dh], ax
0x18005dda6  movzx   eax, byte ptr [rsp+1F8h+var_198+3]
0x18005ddab  mov     [rsi+0E6Fh], al
0x18005ddb1  mov     [rsi+0E70h], r12d
0x18005ddb8  mov     rax, [r14]
0x18005ddbb  mov     rcx, [rax+438h]
0x18005ddc2  movzx   eax, byte ptr [rcx+0E7Ch]
0x18005ddc9  add     rcx, 9F40h
0x18005ddd0  lea     rdx, [rdi+1E8h]
0x18005ddd7  cmp     al, 0Dh
0x18005ddd9  jb      loc_18005DE94
0x18005dddf  lea     r8, [rsp+1F8h+var_118]
0x18005dde7  mov     rax, [rsi+0BB0h]
0x18005ddee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ddf3  mov     ecx, eax; int
0x18005ddf5  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005ddfa  mov     byte ptr [rdi+169h], 1
0x18005de01  inc     dword ptr [rdi+178h]
0x18005de07  mov     qword ptr [rsp+1F8h+PerformanceCount], r12
0x18005de0c  lea     rcx, [rsp+1F8h+PerformanceCount]; lpPerformanceCount
0x18005de11  call    cs:__imp_QueryPerformanceCounter
0x18005de17  mov     r8, [rdi+1B0h]
0x18005de1e  mov     rax, qword ptr [rsp+1F8h+PerformanceCount]
0x18005de23  test    r8, r8
0x18005de26  jz      short loc_18005DE44
0x18005de28  imul    rdx, [rdi+1B8h], 64h ; 'd'
0x18005de30  mov     rcx, rax
0x18005de33  sub     rcx, r8
0x18005de36  cmp     rdx, rcx
0x18005de39  cmovge  rdx, rcx
0x18005de3d  add     [rdi+1A8h], rdx
0x18005de44  mov     [rdi+1B0h], rax
0x18005de4b  mov     [rsi+0E68h], r15d
0x18005de52  mov     [rsi+0E6Ch], rbx
0x18005de59  xor     eax, eax
0x18005de5b  mov     rcx, [rsp+1F8h+var_40]
0x18005de63  xor     rcx, rsp; StackCookie
0x18005de66  call    __security_check_cookie
0x18005de6b  add     rsp, 1C0h
0x18005de72  pop     r15
0x18005de74  pop     r14
0x18005de76  pop     r13
0x18005de78  pop     r12
0x18005de7a  pop     rdi
0x18005de7b  pop     rsi
0x18005de7c  pop     rbx
0x18005de7d  retn
0x18005de7e  mov     byte ptr [rdx+15h], 1
0x18005de82  test    byte ptr [rdx+11h], 2
0x18005de86  jnz     loc_18005DCBE
0x18005de8c  or      [rdx+24h], eax
0x18005de8f  jmp     loc_18005DCBE
0x18005de94  cmp     al, 0Ch
0x18005de96  mov     rax, [rsp+1F8h+var_118]
0x18005de9e  jnb     loc_1800EBEE2
0x18005dea4  mov     [rsp+1F8h+var_58], rax
0x18005deac  mov     rax, [rsp+1F8h+var_110]
0x18005deb4  mov     [rsp+1F8h+var_50], rax
0x18005debc  mov     eax, [rsp+1F8h+var_108]
0x18005dec3  mov     [rsp+1F8h+var_48], eax
0x18005deca  mov     eax, [rsp+1F8h+var_104]
0x18005ded1  mov     [rsp+1F8h+var_44], eax
0x18005ded8  lea     r8, [rsp+1F8h+var_58]
0x18005dee0  mov     rax, [rsi+0BB0h]
0x18005dee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005deec  mov     ecx, eax; int
0x18005deee  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005def3  jmp     loc_18005DDFA
0x18005def8  mov     r13, [rsp+1F8h+var_188]
0x18005defd  test    r13, r13
0x18005df00  jz      loc_18005DD5A
0x18005df06  cmp     [rsp+1F8h+var_1A0], 30h ; '0'
0x18005df0b  jnz     loc_18005DD5A
0x18005df11  mov     rax, [r13+10h]
0x18005df15  mov     qword ptr [rsp+1F8h+var_158+8], rax
0x18005df1d  mov     eax, [r13+8]
0x18005df21  mov     dword ptr [rsp+1F8h+var_148], eax
0x18005df28  mov     rax, [r13+28h]
0x18005df2c  mov     qword ptr [rsp+1F8h+var_138], rax
0x18005df34  mov     eax, [r13+20h]
0x18005df38  mov     dword ptr [rsp+1F8h+var_138+8], eax
0x18005df3f  mov     rax, [r13+18h]
0x18005df43  mov     qword ptr [rsp+1F8h+var_148+8], rax
0x18005df4b  mov     rax, [r13+0]
0x18005df4f  test    rax, rax
0x18005df52  jz      short loc_18005DF62
0x18005df54  add     rax, 120h
0x18005df5a  mov     qword ptr [rsp+1F8h+var_158], rax
0x18005df62  lea     rax, [rsp+1F8h+var_158]
0x18005df6a  mov     [rsp+1F8h+var_110], rax
0x18005df72  jmp     loc_18005DD5A
0x18005df77  mov     r13d, ebx
0x18005df7a  mov     rax, [rsi+r13*8]
0x18005df7e  mov     [rsp+1F8h+var_1B0], rax
0x18005df83  test    rax, rax
0x18005df86  jz      loc_18005DD2B
0x18005df8c  cmp     ebx, r15d
0x18005df8f  jnb     loc_18005DD2B
0x18005df95  lea     rdx, [rax+1A0h]
0x18005df9c  cmp     byte ptr [rax+19Ch], 0
0x18005dfa3  jnz     loc_18005E19B
0x18005dfa9  cmp     dword ptr [rdx], 0
0x18005dfac  jz      short loc_18005E008
0x18005dfae  mov     r8d, r12d
0x18005dfb1  mov     rax, [rax+0D8h]
0x18005dfb8  mov     rcx, [rax+60h]
0x18005dfbc  mov     [rsp+1F8h+var_1A8], rcx
0x18005dfc1  cmp     dword ptr [rdx], 0
0x18005dfc4  jz      short loc_18005DFCD
0x18005dfc6  or      r8d, 20Fh
0x18005dfcd  mov     rax, [r14]
0x18005dfd0  mov     rcx, [rax+438h]
0x18005dfd7  mov     [rsp+1F8h+var_1C0], 1; bool
0x18005dfdc  mov     [rsp+1F8h+var_1C8], 0; bool
0x18005dfe1  mov     [rsp+1F8h+var_1D0], 2000h; unsigned int
0x18005dfe9  mov     [rsp+1F8h+var_1D8], r8d; unsigned int
0x18005dfee  xor     r9d, r9d; bool
0x18005dff1  mov     r8d, 1; unsigned int
0x18005dff7  lea     rdx, [rsp+1F8h+var_1A8]; struct IDXGIResourceInternal **
0x18005dffc  mov     rcx, [rcx+0A0h]; this
0x18005e003  call    ?FlushResourceDeletion@CDevice@@QEAAXPEBQEAUIDXGIResourceInternal@@I_NII11@Z; CDevice::FlushResourceDeletion(IDXGIResourceInternal * const *,uint,bool,uint,uint,bool,bool)
0x18005e008  mov     rcx, r13
0x18005e00b  add     rcx, rcx
0x18005e00e  mov     rax, [rsp+1F8h+arg_28]
0x18005e016  mov     eax, [rax+r13*4]
0x18005e01a  mov     [rsp+rcx*8+1F8h+var_100], eax
0x18005e021  mov     rax, [rsp+1F8h+var_1B0]
0x18005e026  add     rax, 1C0h
0x18005e02c  mov     [rsp+rcx*8+1F8h+var_F8], rax
0x18005e034  jmp     loc_18005DD2B
0x18005e039  mov     r13, [rsi+r8*8]
0x18005e03d  mov     edx, dword ptr [rsp+1F8h+var_1B0]
0x18005e041  add     edx, [rax+r8*4]
0x18005e045  cmp     edx, [rax+r8*4]
0x18005e049  jnb     short loc_18005E0A1
0x18005e04b  mov     rax, [r14]
0x18005e04e  mov     rcx, [rax+4E0h]
0x18005e055  mov     rax, [rcx]
0x18005e058  mov     edx, 300217h
0x18005e05d  mov     rax, [rax+20h]
0x18005e061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e066  mov     cl, 1
0x18005e068  mov     r8, [rsp+1F8h+var_1A8]
0x18005e06d  mov     r9d, [rsp+1F8h+var_1B8]
0x18005e072  jmp     short loc_18005E0AA
0x18005e074  mov     rax, [r14]
0x18005e077  mov     rcx, [rax+4E0h]
0x18005e07e  mov     rax, [rcx]
0x18005e081  mov     r8, r15
0x18005e084  mov     edx, 300215h
0x18005e089  mov     rax, [rax+20h]
0x18005e08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e092  mov     ecx, 80070057h; int
0x18005e097  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005e09c  jmp     loc_18005DC42
0x18005e0a1  cmp     edx, [r13+148h]
0x18005e0a8  ja      short loc_18005E04B
0x18005e0aa  cmp     [r13+0FAh], r12b
0x18005e0b1  jz      loc_1800EBE02
0x18005e0b7  mov     rax, [r14]
0x18005e0ba  mov     rcx, [rax+4E0h]
0x18005e0c1  mov     rax, [rcx]
0x18005e0c4  mov     edx, 300218h
0x18005e0c9  mov     rax, [rax+20h]
0x18005e0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e0d2  mov     cl, 1
0x18005e0d4  mov     r9d, [rsp+1F8h+var_1B8]
0x18005e0d9  jmp     loc_1800EBE02
0x18005e0de  mov     rax, [r14]
0x18005e0e1  mov     rcx, [rax+4E0h]
0x18005e0e8  mov     rax, [rcx]
0x18005e0eb  xor     r8d, r8d
0x18005e0ee  mov     edx, 300038h
0x18005e0f3  mov     rax, [rax+20h]
0x18005e0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e0fc  mov     ecx, 80070057h; int
0x18005e101  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005e106  jmp     loc_18005DC57
0x18005e10b  mov     rax, [r14]
0x18005e10e  mov     rcx, [rax+4E0h]
0x18005e115  mov     rax, [rcx]
0x18005e118  mov     edx, 300039h
0x18005e11d  mov     r8d, 10000000h
0x18005e123  mov     rax, [rax+20h]
0x18005e127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e12c  mov     ecx, 80070057h; int
0x18005e131  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005e136  jmp     loc_18005DC67
0x18005e13b  mov     rax, [r14]
0x18005e13e  mov     rcx, [rax+4E0h]
0x18005e145  mov     rax, [rcx]
0x18005e148  mov     edx, 300039h
0x18005e14d  mov     r8d, 2000000h
0x18005e153  mov     rax, [rax+20h]
0x18005e157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e15c  mov     ecx, 80070057h; int
0x18005e161  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005e166  jmp     loc_18005DC77
0x18005e16b  mov     rax, [r14]
0x18005e16e  mov     rcx, [rax+4E0h]
0x18005e175  mov     rax, [rcx]
0x18005e178  mov     edx, 300039h
0x18005e17d  mov     r8d, 2000000h
0x18005e183  mov     rax, [rax+20h]
0x18005e187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e18c  mov     ecx, 80070057h; int
0x18005e191  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005e196  jmp     loc_18005DCBE
0x18005e19b  mov     r8d, 0F0h
0x18005e1a1  jmp     loc_18005DFB1
0x18005e1a6  mov     eax, 8007000Eh
0x18005e1ab  jmp     loc_18005DE5B
  ... truncated ...
```
